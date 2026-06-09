# BaseSrvCheckProcessAccess

- ea: `0x180008ab0`
- end: `0x180008b6f`
- name: `BaseSrvCheckProcessAccess`
- size: `191`
- prototype: `__int64 __fastcall(int, int, void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180009afc`
- `0x180009da4`

## callees

- `0x180008ab0`

## import_xrefs

- `ntdll!NtOpenProcess` at `0x180008b2a`
- `ntdll!NtOpenProcess` at `0x180008b2a`
- `CSRSRV!CsrRevertToSelf` at `0x180008b3c`
- `CSRSRV!CsrRevertToSelf` at `0x180008b3c`
- `CSRSRV!CsrImpersonateClient` at `0x180008ae1`
- `CSRSRV!CsrImpersonateClient` at `0x180008ae1`

## pseudocode

```c
__int64 __fastcall BaseSrvCheckProcessAccess(int a1, int a2, void **a3)
{
  unsigned int v3; // ebx
  void *v4; // r14
  __int64 v8; // rcx
  NTSTATUS v9; // esi
  _CLIENT_ID ClientId; // [rsp+20h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF

  v3 = 0;
  v4 = (void *)a1;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  if ( a2 && !(unsigned __int8)CsrImpersonateClient(0) )
    return 3221225637LL;
  ClientId.UniqueThread = 0;
  ClientId.UniqueProcess = v4;
  ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 20);
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v9 = NtOpenProcess(a3, 0x400u, &ObjectAttributes, &ClientId);
  if ( a2 )
    CsrRevertToSelf(v8);
  if ( v9 < 0 )
    return (unsigned int)-1073741811;
  return v3;
}

```

## disassembly

```asm
0x180008ab0  mov     rax, rsp
0x180008ab3  mov     [rax+8], rbx
0x180008ab7  mov     [rax+10h], rsi
0x180008abb  mov     [rax+18h], rdi
0x180008abf  mov     [rax+20h], r14
0x180008ac3  push    rbp
0x180008ac4  mov     rbp, rsp
0x180008ac7  sub     rsp, 60h
0x180008acb  xor     ebx, ebx
0x180008acd  movsxd  r14, ecx
0x180008ad0  mov     dword ptr [rbp+ObjectAttributes+4], ebx
0x180008ad3  mov     rsi, r8
0x180008ad6  mov     dword ptr [rbp+ObjectAttributes+1Ch], ebx
0x180008ad9  mov     edi, edx
0x180008adb  test    edx, edx
0x180008add  jz      short loc_180008AF8
0x180008adf  xor     ecx, ecx
0x180008ae1  call    cs:__imp_CsrImpersonateClient
0x180008ae8  nop     dword ptr [rax+rax+00h]
0x180008aed  test    al, al
0x180008aef  jnz     short loc_180008AF8
0x180008af1  mov     eax, 0C00000A5h
0x180008af6  jmp     short loc_180008B54
0x180008af8  xorps   xmm0, xmm0
0x180008afb  mov     [rbp+ClientId.UniqueThread], rbx
0x180008aff  lea     r9, [rbp+ClientId]; ClientId
0x180008b03  mov     [rbp+ClientId.UniqueProcess], r14
0x180008b07  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180008b0b  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180008b12  mov     edx, 400h; DesiredAccess
0x180008b17  mov     [rbp+ObjectAttributes.RootDirectory], rbx
0x180008b1b  mov     rcx, rsi; ProcessHandle
0x180008b1e  mov     [rbp+ObjectAttributes.Attributes], ebx
0x180008b21  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180008b26  mov     [rbp+ObjectAttributes.ObjectName], rbx
0x180008b2a  call    cs:__imp_NtOpenProcess
0x180008b31  nop     dword ptr [rax+rax+00h]
0x180008b36  mov     esi, eax
0x180008b38  test    edi, edi
0x180008b3a  jz      short loc_180008B48
0x180008b3c  call    cs:__imp_CsrRevertToSelf
0x180008b43  nop     dword ptr [rax+rax+00h]
0x180008b48  mov     eax, 0C000000Dh
0x180008b4d  test    esi, esi
0x180008b4f  cmovs   ebx, eax
0x180008b52  mov     eax, ebx
0x180008b54  lea     r11, [rsp+60h+var_s0]
0x180008b59  mov     rbx, [r11+10h]
0x180008b5d  mov     rsi, [r11+18h]
0x180008b61  mov     rdi, [r11+20h]
0x180008b65  mov     r14, [r11+28h]
0x180008b69  mov     rsp, r11
0x180008b6c  pop     rbp
0x180008b6d  retn
```
