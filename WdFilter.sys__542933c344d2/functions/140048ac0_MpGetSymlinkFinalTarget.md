# MpGetSymlinkFinalTarget

- ea: `0x140048ac0`
- end: `0x140048c96`
- name: `MpGetSymlinkFinalTarget`
- size: `470`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400484fc`

## callees

- `0x1400118d0`
- `0x140048ac0`
- `0x140050850`
- `0x140066180`
- `0x14006d300`

## import_xrefs

- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x140048b84`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x140048bc7`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x140048b84`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x140048bc7`
- `ntoskrnl!ZwOpenSymbolicLinkObject` at `0x140048b54`
- `ntoskrnl!ZwOpenSymbolicLinkObject` at `0x140048b54`
- `ntoskrnl!ZwClose` at `0x140048c11`
- `ntoskrnl!ZwClose` at `0x140048c58`
- `ntoskrnl!ZwClose` at `0x140048c11`
- `ntoskrnl!ZwClose` at `0x140048c58`

## pseudocode

```c
__int64 __fastcall MpGetSymlinkFinalTarget(struct _UNICODE_STRING *a1, PUNICODE_STRING *a2)
{
  PUNICODE_STRING v2; // rbx
  struct _UNICODE_STRING *v5; // rdi
  NTSTATUS SymbolicLinkObject; // esi
  int v7; // eax
  char v8; // r15
  PUNICODE_STRING v10; // [rsp+20h] [rbp-60h] BYREF
  void *LinkHandle; // [rsp+28h] [rbp-58h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-50h] BYREF
  ULONG ReturnedLength; // [rsp+60h] [rbp-20h] BYREF
  struct _UNICODE_STRING LinkTarget; // [rsp+68h] [rbp-18h] BYREF

  v2 = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  LinkHandle = 0;
  v10 = 0;
  v5 = a1;
  if ( !a1 || !a2 )
    return 3221225485LL;
  do
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 512;
    ObjectAttributes.ObjectName = v5;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    SymbolicLinkObject = ZwOpenSymbolicLinkObject(&LinkHandle, 0x80000000, &ObjectAttributes);
    if ( SymbolicLinkObject < 0 )
      break;
    ReturnedLength = 0;
    LinkTarget = 0;
    SymbolicLinkObject = ZwQuerySymbolicLinkObject(LinkHandle, &LinkTarget, &ReturnedLength);
    if ( ((SymbolicLinkObject + 0x80000000) & 0x80000000) == 0 && SymbolicLinkObject != -1073741789 )
      break;
    v7 = MpAllocateString((unsigned __int16)ReturnedLength, &v10);
    v2 = v10;
    SymbolicLinkObject = v7;
    if ( v7 < 0 )
      break;
    SymbolicLinkObject = ZwQuerySymbolicLinkObject(LinkHandle, v10, 0);
    if ( SymbolicLinkObject < 0 )
      break;
    if ( (unsigned __int8)MpIsRenameOrLinkTargetPossibleSymLink(0, v2->Length, v2->Buffer) )
    {
      if ( v5 != a1 )
        MpFreeString(v5);
      v8 = 1;
      v5 = v2;
    }
    else
    {
      *a2 = v2;
      v8 = 0;
    }
    v2 = 0;
    v10 = 0;
    ZwClose(LinkHandle);
    LinkHandle = 0;
  }
  while ( v8 );
  if ( v2 )
    MpFreeString(v2);
  if ( v5 && v5 != a1 )
    MpFreeString(v5);
  if ( LinkHandle )
    ZwClose(LinkHandle);
  return (unsigned int)SymbolicLinkObject;
}

```

## disassembly

```asm
0x140048ac0  mov     [rsp-28h+arg_10], rbx
0x140048ac5  mov     [rsp-28h+arg_18], rsi
0x140048aca  push    rbp
0x140048acb  push    rdi
0x140048acc  push    r12
0x140048ace  push    r14
0x140048ad0  push    r15
0x140048ad2  mov     rbp, rsp
0x140048ad5  sub     rsp, 80h
0x140048adc  mov     rax, cs:__security_cookie
0x140048ae3  xor     rax, rsp
0x140048ae6  mov     [rbp+var_8], rax
0x140048aea  xor     ebx, ebx
0x140048aec  mov     dword ptr [rbp+ObjectAttributes+4], 0
0x140048af3  mov     dword ptr [rbp+ObjectAttributes+1Ch], 0
0x140048afa  mov     r12, rdx
0x140048afd  mov     [rbp+LinkHandle], 0
0x140048b05  mov     r14, rcx
0x140048b08  mov     [rbp+var_60], rbx
0x140048b0c  mov     rdi, rcx
0x140048b0f  test    rcx, rcx
0x140048b12  jz      loc_140048C68
0x140048b18  test    rdx, rdx
0x140048b1b  jz      loc_140048C68
0x140048b21  mov     r15d, 80000000h
0x140048b27  xorps   xmm0, xmm0
0x140048b2a  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140048b31  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140048b35  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140048b3d  mov     edx, r15d; DesiredAccess
0x140048b40  mov     [rbp+ObjectAttributes.Attributes], 200h
0x140048b47  lea     rcx, [rbp+LinkHandle]; LinkHandle
0x140048b4b  mov     [rbp+ObjectAttributes.ObjectName], rdi
0x140048b4f  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140048b54  call    cs:__imp_ZwOpenSymbolicLinkObject
0x140048b5b  nop     dword ptr [rax+rax+00h]
0x140048b60  mov     esi, eax
0x140048b62  test    eax, eax
0x140048b64  js      loc_140048C30
0x140048b6a  mov     rcx, [rbp+LinkHandle]; LinkHandle
0x140048b6e  lea     r8, [rbp+ReturnedLength]; ReturnedLength
0x140048b72  xorps   xmm0, xmm0
0x140048b75  mov     [rbp+ReturnedLength], 0
0x140048b7c  lea     rdx, [rbp+LinkTarget]; LinkTarget
0x140048b80  movups  xmmword ptr [rbp+LinkTarget.Length], xmm0
0x140048b84  call    cs:__imp_ZwQuerySymbolicLinkObject
0x140048b8b  nop     dword ptr [rax+rax+00h]
0x140048b90  mov     esi, eax
0x140048b92  add     eax, r15d
0x140048b95  test    r15d, eax
0x140048b98  jnz     short loc_140048BA6
0x140048b9a  cmp     esi, 0C0000023h
0x140048ba0  jnz     loc_140048C30
0x140048ba6  movzx   ecx, word ptr [rbp+ReturnedLength]
0x140048baa  lea     rdx, [rbp+var_60]
0x140048bae  call    MpAllocateString
0x140048bb3  mov     rbx, [rbp+var_60]
0x140048bb7  mov     esi, eax
0x140048bb9  test    eax, eax
0x140048bbb  js      short loc_140048C30
0x140048bbd  mov     rcx, [rbp+LinkHandle]; LinkHandle
0x140048bc1  xor     r8d, r8d; ReturnedLength
0x140048bc4  mov     rdx, rbx; LinkTarget
0x140048bc7  call    cs:__imp_ZwQuerySymbolicLinkObject
0x140048bce  nop     dword ptr [rax+rax+00h]
0x140048bd3  mov     esi, eax
0x140048bd5  test    eax, eax
0x140048bd7  js      short loc_140048C30
0x140048bd9  movzx   edx, word ptr [rbx]
0x140048bdc  xor     ecx, ecx
0x140048bde  mov     r8, [rbx+8]
0x140048be2  call    MpIsRenameOrLinkTargetPossibleSymLink
0x140048be7  test    al, al
0x140048be9  jnz     short loc_140048BF4
0x140048beb  mov     [r12], rbx
0x140048bef  xor     r15b, r15b
0x140048bf2  jmp     short loc_140048C07
0x140048bf4  cmp     rdi, r14
0x140048bf7  jz      short loc_140048C01
0x140048bf9  mov     rcx, rdi
0x140048bfc  call    MpFreeString
0x140048c01  mov     r15b, 1
0x140048c04  mov     rdi, rbx
0x140048c07  mov     rcx, [rbp+LinkHandle]; Handle
0x140048c0b  xor     ebx, ebx
0x140048c0d  mov     [rbp+var_60], rbx
0x140048c11  call    cs:__imp_ZwClose
0x140048c18  nop     dword ptr [rax+rax+00h]
0x140048c1d  test    r15b, r15b
0x140048c20  mov     [rbp+LinkHandle], rbx
0x140048c24  mov     r15d, 80000000h
0x140048c2a  jnz     loc_140048B27
0x140048c30  test    rbx, rbx
0x140048c33  jz      short loc_140048C3D
0x140048c35  mov     rcx, rbx
0x140048c38  call    MpFreeString
0x140048c3d  test    rdi, rdi
0x140048c40  jz      short loc_140048C4F
0x140048c42  cmp     rdi, r14
0x140048c45  jz      short loc_140048C4F
0x140048c47  mov     rcx, rdi
0x140048c4a  call    MpFreeString
0x140048c4f  mov     rcx, [rbp+LinkHandle]; Handle
0x140048c53  test    rcx, rcx
0x140048c56  jz      short loc_140048C64
0x140048c58  call    cs:__imp_ZwClose
0x140048c5f  nop     dword ptr [rax+rax+00h]
0x140048c64  mov     eax, esi
0x140048c66  jmp     short loc_140048C6D
0x140048c68  mov     eax, 0C000000Dh
0x140048c6d  mov     rcx, [rbp+var_8]
0x140048c71  xor     rcx, rsp; StackCookie
0x140048c74  call    __security_check_cookie
0x140048c79  lea     r11, [rsp+80h+var_s0]
0x140048c81  mov     rbx, [r11+40h]
0x140048c85  mov     rsi, [r11+48h]
0x140048c89  mov     rsp, r11
0x140048c8c  pop     r15
0x140048c8e  pop     r14
0x140048c90  pop     r12
0x140048c92  pop     rdi
0x140048c93  pop     rbp
0x140048c94  retn
```
