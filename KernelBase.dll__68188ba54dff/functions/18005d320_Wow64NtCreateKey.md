# Wow64NtCreateKey

- ea: `0x18005d320`
- end: `0x18005d6df`
- name: `Wow64NtCreateKey`
- size: `959`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005a0c0`
- `0x18005ee30`
- `0x1800c9130`
- `0x1800c9270`
- `0x1801839dc`

## callees

- `0x18005cc40`
- `0x18005d320`

## import_xrefs

- `ntdll!NtCreateKeyTransacted` at `0x18005d5cf`
- `ntdll!NtCreateKeyTransacted` at `0x18005d600`
- `ntdll!NtCreateKeyTransacted` at `0x18005d66c`
- `ntdll!NtCreateKeyTransacted` at `0x18005d5cf`
- `ntdll!NtCreateKeyTransacted` at `0x18005d600`
- `ntdll!NtCreateKeyTransacted` at `0x18005d66c`
- `ntdll!NtCreateKey` at `0x18005d402`
- `ntdll!NtCreateKey` at `0x18005d51d`
- `ntdll!NtCreateKey` at `0x18005d63f`
- `ntdll!NtCreateKey` at `0x18005d402`
- `ntdll!NtCreateKey` at `0x18005d51d`
- `ntdll!NtCreateKey` at `0x18005d63f`
- `ntdll!NtClose` at `0x18005d5af`
- `ntdll!NtClose` at `0x18005d5da`
- `ntdll!NtClose` at `0x18005d674`
- `ntdll!NtClose` at `0x18005d5af`
- `ntdll!NtClose` at `0x18005d5da`
- `ntdll!NtClose` at `0x18005d674`
- `ntdll!RtlFreeHeap` at `0x18005d441`
- `ntdll!RtlFreeHeap` at `0x18005d441`
- `ntdll!NtOpenKeyEx` at `0x18005d69a`
- `ntdll!NtOpenKeyEx` at `0x18005d69a`
- `ntdll!NtSetInformationKey` at `0x18005d59b`
- `ntdll!NtSetInformationKey` at `0x18005d59b`
- `ntdll!NtOpenKeyTransactedEx` at `0x18005d6d7`
- `ntdll!NtOpenKeyTransactedEx` at `0x18005d6d7`

## pseudocode

```c
__int64 __fastcall Wow64NtCreateKey(
        HANDLE *a1,
        ACCESS_MASK a2,
        __int128 *a3,
        int a4,
        PUNICODE_STRING Class,
        ULONG CreateOptions,
        __int64 a7,
        PULONG Disposition)
{
  __int128 v8; // xmm0
  HANDLE *v9; // r13
  __int128 v10; // xmm1
  __int128 v12; // xmm0
  __int64 result; // rax
  ULONG v14; // esi
  __int64 v15; // rdi
  ULONG *v16; // r14
  struct _UNICODE_STRING *v17; // r15
  NTSTATUS v18; // eax
  int v19; // ebx
  __int16 v20; // r8
  PUNICODE_STRING ObjectName; // rax
  USHORT Length; // r13
  __int16 v23; // dx
  WCHAR *v24; // rcx
  NTSTATUS v25; // eax
  WCHAR *v26; // rax
  __int16 v27; // ax
  NTSTATUS v28; // edi
  USHORT v29; // r13
  int v30; // eax
  int v31; // eax
  int KeySetInformation; // [rsp+40h] [rbp-59h] BYREF
  HANDLE KeyHandle; // [rsp+48h] [rbp-51h] BYREF
  WCHAR *v34; // [rsp+50h] [rbp-49h]
  PVOID P; // [rsp+58h] [rbp-41h] BYREF
  __int64 v36; // [rsp+60h] [rbp-39h] BYREF
  __int16 v37; // [rsp+68h] [rbp-31h]
  char v38; // [rsp+6Ah] [rbp-2Fh]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-29h] BYREF
  __int16 v41; // [rsp+F0h] [rbp+57h]
  int v42; // [rsp+F8h] [rbp+5Fh] BYREF

  v42 = a4;
  v8 = *a3;
  v9 = a1;
  v10 = a3[1];
  v36 = 0;
  v37 = 0;
  v38 = 0;
  LOBYTE(v42) = 0;
  *(_OWORD *)&ObjectAttributes.Length = v8;
  P = 0;
  v12 = a3[2];
  KeySetInformation = 0;
  KeyHandle = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = v12;
  *(_OWORD *)&ObjectAttributes.ObjectName = v10;
  result = ConstructKernelKeyPath(
             a2,
             (unsigned int)&ObjectAttributes,
             (unsigned int)&KeySetInformation,
             (unsigned int)&v36,
             (__int64)&v42,
             (__int64)&P);
  if ( (int)result < 0 )
    return result;
  v14 = CreateOptions;
  v15 = a7;
  v16 = Disposition;
  v17 = Class;
  if ( a7 )
    v18 = NtCreateKeyTransacted(&KeyHandle, a2, &ObjectAttributes, 0, Class, CreateOptions, a7, Disposition);
  else
    v18 = NtCreateKey(&KeyHandle, a2, &ObjectAttributes, 0, Class, CreateOptions, Disposition);
  v19 = v18;
  if ( v18 == -1073741772 )
  {
    if ( (_BYTE)v36 )
    {
      v20 = WORD2(v36);
      if ( WORD2(v36) )
      {
        ObjectName = ObjectAttributes.ObjectName;
        Length = ObjectAttributes.ObjectName->Length;
        if ( WORD1(v36) )
        {
          ObjectAttributes.ObjectName->Length = WORD1(v36);
          if ( v15 )
            v31 = NtOpenKeyTransactedEx(&KeyHandle, a2, &ObjectAttributes, v14, v15);
          else
            v31 = NtOpenKeyEx(&KeyHandle, a2, &ObjectAttributes, v14);
          v19 = v31;
          if ( v31 < 0 )
          {
LABEL_41:
            v9 = a1;
            goto LABEL_5;
          }
          Length -= WORD1(v36);
          v20 = WORD2(v36);
          ObjectAttributes.ObjectName->Buffer += (unsigned __int64)WORD1(v36) >> 1;
          ObjectAttributes.RootDirectory = KeyHandle;
          ObjectName = ObjectAttributes.ObjectName;
        }
        else
        {
          v19 = 0;
        }
        v23 = v20 - 2;
        v24 = ObjectName->Buffer + 1;
        ObjectName->Buffer = v24;
        ObjectAttributes.ObjectName->MaximumLength -= 2;
        while ( 1 )
        {
          v34 = v24;
          if ( !v23 )
            break;
          do
          {
            if ( *v24 == 92 )
              break;
            ++v24;
            v23 -= 2;
          }
          while ( v23 );
          v34 = v24;
          v41 = v23;
          ObjectAttributes.ObjectName->Length = 2
                                              * ((__int64)(unsigned int)((_DWORD)v24
                                                                       - LODWORD(ObjectAttributes.ObjectName->Buffer)) >> 1);
          if ( v15 )
            v25 = NtCreateKeyTransacted(&KeyHandle, a2, &ObjectAttributes, 0, v17, v14, v15, v16);
          else
            v25 = NtCreateKey(&KeyHandle, a2, &ObjectAttributes, 0, v17, v14, v16);
          v19 = v25;
          if ( ObjectAttributes.RootDirectory )
          {
            NtClose(ObjectAttributes.RootDirectory);
            ObjectAttributes.RootDirectory = 0;
          }
          if ( v19 < 0 )
            goto LABEL_41;
          v26 = v34 + 1;
          if ( !v41 )
            v26 = v34;
          v24 = v26;
          ObjectAttributes.ObjectName->Buffer = v26;
          ObjectAttributes.RootDirectory = KeyHandle;
          v27 = v41 - 2;
          if ( !v41 )
            v27 = 0;
          v23 = v27;
        }
        if ( v19 >= 0 )
        {
          v29 = Length - WORD2(v36);
          if ( v29 )
          {
            ObjectAttributes.ObjectName->Length = v29;
            v30 = v15
                ? NtCreateKeyTransacted(&KeyHandle, a2, &ObjectAttributes, 0, v17, v14, v15, v16)
                : NtCreateKey(&KeyHandle, a2, &ObjectAttributes, 0, v17, v14, v16);
            v19 = v30;
            if ( ObjectAttributes.RootDirectory )
            {
              NtClose(ObjectAttributes.RootDirectory);
              ObjectAttributes.RootDirectory = 0;
            }
          }
        }
        goto LABEL_41;
      }
    }
  }
LABEL_5:
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  if ( v19 >= 0 )
  {
    if ( (_BYTE)v42 )
    {
      if ( KeySetInformation )
      {
        KeySetInformation &= 0xF01u;
        v28 = NtSetInformationKey(KeyHandle, KeySetHandleTagsInformation, &KeySetInformation, 4u);
        if ( v28 < 0 )
        {
          NtClose(KeyHandle);
          return (unsigned int)v28;
        }
      }
    }
    *v9 = KeyHandle;
  }
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x18005d320  mov     [rsp-8+arg_18], r9d
0x18005d325  mov     [rsp-8+arg_0], rcx
0x18005d32a  push    rbp
0x18005d32b  push    r12
0x18005d32d  push    r13
0x18005d32f  lea     rbp, [rsp-27h]
0x18005d334  sub     rsp, 0C0h
0x18005d33b  movups  xmm0, xmmword ptr [r8]
0x18005d33f  xor     eax, eax
0x18005d341  mov     r13, rcx
0x18005d344  movups  xmm1, xmmword ptr [r8+10h]
0x18005d349  xor     ecx, ecx
0x18005d34b  mov     [rbp+37h+var_70], rax
0x18005d34f  mov     [rbp+37h+var_68], ax
0x18005d353  lea     r9, [rbp+37h+var_70]
0x18005d357  mov     [rbp+37h+var_66], al
0x18005d35a  mov     r12d, edx
0x18005d35d  mov     byte ptr [rbp+37h+arg_18], al
0x18005d360  lea     rdx, [rbp+37h+ObjectAttributes]
0x18005d364  movups  xmmword ptr [rbp+37h+ObjectAttributes.Length], xmm0
0x18005d368  lea     rax, [rbp+37h+P]
0x18005d36c  mov     [rbp+37h+P], rcx
0x18005d370  movups  xmm0, xmmword ptr [r8+20h]
0x18005d375  mov     qword ptr [rsp+0D0h+CreateOptions], rax
0x18005d37a  lea     r8, [rbp+37h+KeySetInformation]
0x18005d37e  mov     [rbp+37h+KeySetInformation], ecx
0x18005d381  lea     rax, [rbp+37h+arg_18]
0x18005d385  mov     [rbp+37h+KeyHandle], rcx
0x18005d389  mov     ecx, r12d
0x18005d38c  movups  xmmword ptr [rbp+37h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005d390  mov     [rsp+0D0h+Class], rax
0x18005d395  movups  xmmword ptr [rbp+37h+ObjectAttributes.ObjectName], xmm1
0x18005d399  call    ConstructKernelKeyPath
0x18005d39e  test    eax, eax
0x18005d3a0  js      loc_18005D46F
0x18005d3a6  mov     [rsp+0D0h+arg_8], rbx
0x18005d3ae  lea     r8, [rbp+37h+ObjectAttributes]; ObjectAttributes
0x18005d3b2  mov     [rsp+0D0h+var_18], rsi
0x18005d3ba  lea     rcx, [rbp+37h+KeyHandle]; KeyHandle
0x18005d3be  mov     esi, [rbp+37h+arg_28]
0x18005d3c1  xor     r9d, r9d; TitleIndex
0x18005d3c4  mov     [rsp+0D0h+var_20], rdi
0x18005d3cc  mov     edx, r12d; DesiredAccess
0x18005d3cf  mov     rdi, [rbp+37h+arg_30]
0x18005d3d3  mov     [rsp+0D0h+var_28], r14
0x18005d3db  mov     r14, [rbp+37h+arg_38]
0x18005d3df  mov     [rsp+0D0h+var_30], r15
0x18005d3e7  mov     r15, [rbp+37h+arg_20]
0x18005d3eb  test    rdi, rdi
0x18005d3ee  jnz     loc_18005D5BC
0x18005d3f4  mov     [rsp+0D0h+Disposition], r14; Disposition
0x18005d3f9  mov     [rsp+0D0h+CreateOptions], esi; CreateOptions
0x18005d3fd  mov     [rsp+0D0h+Class], r15; Class
0x18005d402  call    cs:__imp_NtCreateKey
0x18005d408  mov     ebx, eax
0x18005d40a  cmp     eax, 0C0000034h
0x18005d40f  jz      short loc_18005D47C
0x18005d411  mov     r8, [rbp+37h+P]; P
0x18005d415  mov     r15, [rsp+0D0h+var_30]
0x18005d41d  mov     r14, [rsp+0D0h+var_28]
0x18005d425  mov     rsi, [rsp+0D0h+var_18]
0x18005d42d  test    r8, r8
0x18005d430  jz      short loc_18005D447
0x18005d432  mov     rcx, gs:60h
0x18005d43b  xor     edx, edx; Flags
0x18005d43d  mov     rcx, [rcx+30h]; HeapHandle
0x18005d441  call    cs:__imp_RtlFreeHeap
0x18005d447  test    ebx, ebx
0x18005d449  js      short loc_18005D45D
0x18005d44b  cmp     byte ptr [rbp+37h+arg_18], 0
0x18005d44f  jnz     loc_18005D575
0x18005d455  mov     rax, [rbp+37h+KeyHandle]
0x18005d459  mov     [r13+0], rax
0x18005d45d  mov     eax, ebx
0x18005d45f  mov     rbx, [rsp+0D0h+arg_8]
0x18005d467  mov     rdi, [rsp+0D0h+var_20]
0x18005d46f  add     rsp, 0C0h
0x18005d476  pop     r13
0x18005d478  pop     r12
0x18005d47a  pop     rbp
0x18005d47b  retn
0x18005d47c  cmp     byte ptr [rbp+37h+var_70], 0
0x18005d480  jz      short loc_18005D411
0x18005d482  movzx   r8d, word ptr [rbp+37h+var_70+4]
0x18005d487  test    r8w, r8w
0x18005d48b  jz      short loc_18005D411
0x18005d48d  mov     rax, [rbp+37h+ObjectAttributes.ObjectName]
0x18005d491  movzx   ecx, word ptr [rbp+37h+var_70+2]
0x18005d495  movzx   r13d, word ptr [rax]
0x18005d499  test    cx, cx
0x18005d49c  jnz     loc_18005D684
0x18005d4a2  xor     ebx, ebx
0x18005d4a4  mov     rcx, [rax+8]
0x18005d4a8  lea     edx, [r8-2]
0x18005d4ac  add     rcx, 2
0x18005d4b0  mov     r8d, 0FFFEh
0x18005d4b6  mov     [rax+8], rcx
0x18005d4ba  mov     rax, [rbp+37h+ObjectAttributes.ObjectName]
0x18005d4be  add     [rax+2], r8w
0x18005d4c3  mov     [rbp+37h+var_80], rcx
0x18005d4c7  test    dx, dx
0x18005d4ca  jz      loc_18005D60B
0x18005d4d0  cmp     word ptr [rcx], 5Ch ; '\'
0x18005d4d4  jz      short loc_18005D4E0
0x18005d4d6  add     rcx, 2
0x18005d4da  add     dx, r8w
0x18005d4de  jnz     short loc_18005D4D0
0x18005d4e0  mov     rax, [rbp+37h+ObjectAttributes.ObjectName]
0x18005d4e4  lea     r8, [rbp+37h+ObjectAttributes]; ObjectAttributes
0x18005d4e8  mov     [rbp+37h+var_80], rcx
0x18005d4ec  xor     r9d, r9d; TitleIndex
0x18005d4ef  mov     [rbp+37h+arg_10], dx
0x18005d4f3  mov     edx, r12d; DesiredAccess
0x18005d4f6  sub     ecx, [rax+8]
0x18005d4f9  sar     rcx, 1
0x18005d4fc  add     cx, cx
0x18005d4ff  mov     [rax], cx
0x18005d502  lea     rcx, [rbp+37h+KeyHandle]; KeyHandle
0x18005d506  test    rdi, rdi
0x18005d509  jnz     loc_18005D5ED
0x18005d50f  mov     [rsp+0D0h+Disposition], r14; Disposition
0x18005d514  mov     [rsp+0D0h+CreateOptions], esi; CreateOptions
0x18005d518  mov     [rsp+0D0h+Class], r15; Class
0x18005d51d  call    cs:__imp_NtCreateKey
0x18005d523  mov     rcx, [rbp+37h+ObjectAttributes.RootDirectory]; Handle
0x18005d527  mov     ebx, eax
0x18005d529  test    rcx, rcx
0x18005d52c  jnz     loc_18005D5DA
0x18005d532  test    ebx, ebx
0x18005d534  js      loc_18005D650
0x18005d53a  movzx   edx, [rbp+37h+arg_10]
0x18005d53e  mov     r8d, 0FFFEh
0x18005d544  mov     rcx, [rbp+37h+var_80]
0x18005d548  test    dx, dx
0x18005d54b  lea     rax, [rcx+2]
0x18005d54f  cmovz   rax, rcx
0x18005d553  mov     rcx, rax
0x18005d556  mov     rax, [rbp+37h+ObjectAttributes.ObjectName]
0x18005d55a  mov     [rax+8], rcx
0x18005d55e  mov     rax, [rbp+37h+KeyHandle]
0x18005d562  mov     [rbp+37h+ObjectAttributes.RootDirectory], rax
0x18005d566  lea     eax, [rdx-2]
0x18005d569  cmovz   ax, dx
0x18005d56d  movzx   edx, ax
0x18005d570  jmp     loc_18005D4C3
0x18005d575  mov     eax, [rbp+37h+KeySetInformation]
0x18005d578  test    eax, eax
0x18005d57a  jz      loc_18005D455
0x18005d580  mov     rcx, [rbp+37h+KeyHandle]; KeyHandle
0x18005d584  lea     r8, [rbp+37h+KeySetInformation]; KeySetInformation
0x18005d588  and     eax, 0F01h
0x18005d58d  mov     r9d, 4; KeySetInformationLength
0x18005d593  mov     edx, 5; KeySetInformationClass
0x18005d598  mov     [rbp+37h+KeySetInformation], eax
0x18005d59b  call    cs:__imp_NtSetInformationKey
0x18005d5a1  mov     edi, eax
0x18005d5a3  test    eax, eax
0x18005d5a5  jns     loc_18005D455
0x18005d5ab  mov     rcx, [rbp+37h+KeyHandle]; Handle
0x18005d5af  call    cs:__imp_NtClose
0x18005d5b5  mov     eax, edi
0x18005d5b7  jmp     loc_18005D45F
0x18005d5bc  mov     [rsp+0D0h+var_98], r14
0x18005d5c1  mov     [rsp+0D0h+Disposition], rdi
0x18005d5c6  mov     [rsp+0D0h+CreateOptions], esi
0x18005d5ca  mov     [rsp+0D0h+Class], r15
0x18005d5cf  call    cs:__imp_NtCreateKeyTransacted
0x18005d5d5  jmp     loc_18005D408
0x18005d5da  call    cs:__imp_NtClose
0x18005d5e0  mov     [rbp+37h+ObjectAttributes.RootDirectory], 0
0x18005d5e8  jmp     loc_18005D532
0x18005d5ed  mov     [rsp+0D0h+var_98], r14
0x18005d5f2  mov     [rsp+0D0h+Disposition], rdi
0x18005d5f7  mov     [rsp+0D0h+CreateOptions], esi
0x18005d5fb  mov     [rsp+0D0h+Class], r15
0x18005d600  call    cs:__imp_NtCreateKeyTransacted
0x18005d606  jmp     loc_18005D523
0x18005d60b  test    ebx, ebx
0x18005d60d  js      short loc_18005D650
0x18005d60f  sub     r13w, word ptr [rbp+37h+var_70+4]
0x18005d614  jz      short loc_18005D650
0x18005d616  mov     rax, [rbp+37h+ObjectAttributes.ObjectName]
0x18005d61a  lea     r8, [rbp+37h+ObjectAttributes]; ObjectAttributes
0x18005d61e  xor     r9d, r9d; TitleIndex
0x18005d621  lea     rcx, [rbp+37h+KeyHandle]; KeyHandle
0x18005d625  mov     edx, r12d; DesiredAccess
0x18005d628  mov     [rax], r13w
0x18005d62c  test    rdi, rdi
0x18005d62f  jnz     short loc_18005D659
0x18005d631  mov     [rsp+0D0h+Disposition], r14; Disposition
0x18005d636  mov     [rsp+0D0h+CreateOptions], esi; CreateOptions
0x18005d63a  mov     [rsp+0D0h+Class], r15; Class
0x18005d63f  call    cs:__imp_NtCreateKey
0x18005d645  mov     rcx, [rbp+37h+ObjectAttributes.RootDirectory]; Handle
0x18005d649  mov     ebx, eax
0x18005d64b  test    rcx, rcx
0x18005d64e  jnz     short loc_18005D674
0x18005d650  mov     r13, [rbp+37h+arg_0]
0x18005d654  jmp     loc_18005D411
0x18005d659  mov     [rsp+0D0h+var_98], r14
0x18005d65e  mov     [rsp+0D0h+Disposition], rdi
0x18005d663  mov     [rsp+0D0h+CreateOptions], esi
0x18005d667  mov     [rsp+0D0h+Class], r15
0x18005d66c  call    cs:__imp_NtCreateKeyTransacted
0x18005d672  jmp     short loc_18005D645
0x18005d674  call    cs:__imp_NtClose
0x18005d67a  mov     [rbp+37h+ObjectAttributes.RootDirectory], 0
0x18005d682  jmp     short loc_18005D650
0x18005d684  mov     [rax], cx
0x18005d687  lea     rcx, [rbp+37h+KeyHandle]
0x18005d68b  lea     r8, [rbp+37h+ObjectAttributes]
0x18005d68f  mov     r9d, esi
0x18005d692  mov     edx, r12d
0x18005d695  test    rdi, rdi
0x18005d698  jnz     short loc_18005D6D2
0x18005d69a  call    cs:__imp_NtOpenKeyEx
0x18005d6a0  mov     ebx, eax
0x18005d6a2  test    eax, eax
0x18005d6a4  js      short loc_18005D650
0x18005d6a6  movzx   eax, word ptr [rbp+37h+var_70+2]
0x18005d6aa  mov     rcx, [rbp+37h+ObjectAttributes.ObjectName]
0x18005d6ae  sub     r13w, ax
0x18005d6b2  movzx   r8d, word ptr [rbp+37h+var_70+4]
0x18005d6b7  shr     rax, 1
0x18005d6ba  add     rax, rax
0x18005d6bd  add     [rcx+8], rax
0x18005d6c1  mov     rax, [rbp+37h+KeyHandle]
0x18005d6c5  mov     [rbp+37h+ObjectAttributes.RootDirectory], rax
0x18005d6c9  mov     rax, [rbp+37h+ObjectAttributes.ObjectName]
0x18005d6cd  jmp     loc_18005D4A4
0x18005d6d2  mov     [rsp+0D0h+Class], rdi
0x18005d6d7  call    cs:__imp_NtOpenKeyTransactedEx
0x18005d6dd  jmp     short loc_18005D6A0
```
