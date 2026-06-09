# PerflibCreateSD(ulong)

- ea: `0x1800019e0`
- end: `0x180001ca1`
- name: `?PerflibCreateSD@@YAHK@Z`
- size: `705`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180022f00`

## callees

- `0x1800019e0`
- `0x180002e40`
- `0x180064800`
- `0x180072042`
- `0x1800720b0`

## import_xrefs

- `ntdll!NtOpenProcessToken` at `0x180001a2b`
- `ntdll!NtOpenProcessToken` at `0x180001a2b`
- `ntdll!RtlLengthSid` at `0x180001abf`
- `ntdll!RtlLengthSid` at `0x180001abf`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180001b7a`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180001b9d`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180001b7a`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180001b9d`
- `ntdll!RtlCreateAcl` at `0x180001b4f`
- `ntdll!RtlCreateAcl` at `0x180001b4f`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x180001c30`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x180001c30`
- `ntdll!NtQueryInformationToken` at `0x180001a90`
- `ntdll!NtQueryInformationToken` at `0x180001a90`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001a13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001a13`
- `KERNEL32!LocalFree` at `0x180001bb2`
- `KERNEL32!LocalFree` at `0x180001bc1`
- `KERNEL32!LocalFree` at `0x180001c7e`
- `KERNEL32!LocalFree` at `0x180001bb2`
- `KERNEL32!LocalFree` at `0x180001bc1`
- `KERNEL32!LocalFree` at `0x180001c7e`
- `KERNEL32!CloseHandle` at `0x180001bd1`
- `KERNEL32!CloseHandle` at `0x180001c8e`
- `KERNEL32!CloseHandle` at `0x180001bd1`
- `KERNEL32!CloseHandle` at `0x180001c8e`

## pseudocode

```c
__int64 __fastcall PerflibCreateSD(int a1)
{
  HANDLE CurrentProcess; // rax
  PSID v2; // r12
  ULONG v3; // edi
  ULONG v4; // r15d
  __int64 v5; // rax
  _DWORD *v6; // rsi
  ACL *v7; // rax
  ACL *v8; // r14
  unsigned int v9; // edi
  PSID TokenInformation[6]; // [rsp+10h] [rbp-60h] BYREF
  ULONG TokenInformationLength; // [rsp+70h] [rbp+0h] BYREF
  HANDLE TokenHandle[2]; // [rsp+78h] [rbp+8h] BYREF
  size_t Size; // [rsp+88h] [rbp+18h]
  _DWORD pSid[4]; // [rsp+90h] [rbp+20h] BYREF

  TokenHandle[0] = 0;
  if ( a1 && a1 != 1008 )
    return 0;
  CurrentProcess = GetCurrentProcess();
  if ( NtOpenProcessToken(CurrentProcess, 8u, TokenHandle) < 0 )
    return 0;
  TokenInformationLength = 88;
  TokenHandle[1] = TokenInformation;
  if ( NtQueryInformationToken(TokenHandle[0], TokenUser, TokenInformation, 0x58u, &TokenInformationLength) < 0 )
  {
    v9 = 0;
LABEL_11:
    CloseHandle(TokenHandle[0]);
    return v9;
  }
  pSid[0] = 257;
  pSid[1] = 83886080;
  pSid[2] = 18;
  v2 = TokenInformation[0];
  TokenInformationLength = RtlLengthSid(TokenInformation[0]);
  v3 = TokenInformationLength + 36;
  v4 = TokenInformationLength + 36 + 2 * (TokenInformationLength + 10);
  v5 = operator new(v4);
  v6 = (_DWORD *)v5;
  if ( v5 )
  {
    *(_BYTE *)v5 = 1;
    *(_WORD *)(v5 + 2) = -32764;
    memcpy_0((void *)(v5 + 20), v2, TokenInformationLength);
    v6[1] = 20;
    memcpy_0((char *)v6 + TokenInformationLength + 20, v2, TokenInformationLength);
    v6[2] = TokenInformationLength + 20;
    Size = v3;
    v7 = (ACL *)operator new(v3);
    v8 = v7;
    if ( v7 )
    {
      if ( RtlCreateAcl(v7, v3, 2u) >= 0
        && RtlAddAccessAllowedAceEx(v8, 2u, 0, 0x1F0001u, pSid) >= 0
        && RtlAddAccessAllowedAceEx(v8, 2u, 0, 0x1F0001u, v2) >= 0
        && (memcpy_0((char *)v6 + 2 * TokenInformationLength + 20, v8, Size),
            v6[4] = 2 * TokenInformationLength + 20,
            RtlValidRelativeSecurityDescriptor(v6, v4, 7u)) )
      {
        v9 = 1;
        g_SizeSD = v4;
        memcpy_0(&g_RuntimeSD, v6, v4);
      }
      else
      {
        v9 = 0;
      }
      LocalFree(v6);
      LocalFree(v8);
      goto LABEL_11;
    }
    LocalFree(v6);
  }
  CloseHandle(TokenHandle[0]);
  return 0;
}

```

## disassembly

```asm
0x1800019e0  push    rbp
0x1800019e2  push    rsi
0x1800019e3  push    rdi
0x1800019e4  push    r12
0x1800019e6  push    r13
0x1800019e8  push    r14
0x1800019ea  push    r15
0x1800019ec  sub     rsp, 70h
0x1800019f0  lea     rbp, [rsp+30h]
0x1800019f5  mov     rax, cs:__security_cookie
0x1800019fc  xor     rax, rbp
0x1800019ff  mov     [rbp+70h+var_40], rax
0x180001a03  mov     [rbp+70h+TokenHandle], 0
0x180001a0b  test    ecx, ecx
0x180001a0d  jnz     loc_180001C67
0x180001a13  call    cs:__imp_GetCurrentProcess
0x180001a1a  nop     dword ptr [rax+rax+00h]
0x180001a1f  mov     rcx, rax; ProcessHandle
0x180001a22  lea     r8, [rbp+70h+TokenHandle]; TokenHandle
0x180001a26  mov     edx, 8; DesiredAccess
0x180001a2b  call    cs:__imp_NtOpenProcessToken
0x180001a32  nop     dword ptr [rax+rax+00h]
0x180001a37  test    eax, eax
0x180001a39  js      loc_180001BFC
0x180001a3f  mov     edi, 1
0x180001a44  lea     r9d, [rdi+57h]
0x180001a48  mov     [rbp+70h+TokenInformationLength], r9d
0x180001a4c  mov     eax, [rsp+0A0h+var_A0]
0x180001a4f  sub     rsp, 60h
0x180001a53  lea     rsi, [rsp+100h+TokenInformation]
0x180001a58  mov     eax, [rsi]
0x180001a5a  mov     [rbp+70h+var_60], rsi
0x180001a5e  jmp     short loc_180001A73
0x180001a60  mov     ecx, eax; unsigned int
0x180001a62  call    ?PerfpExceptionHandler@@YAXK@Z; PerfpExceptionHandler(ulong)
0x180001a67  xor     esi, esi
0x180001a69  mov     [rbp+70h+var_60], rsi
0x180001a6d  xor     edi, edi
0x180001a6f  mov     r9d, [rbp+70h+TokenInformationLength]; TokenInformationLength
0x180001a73  test    edi, edi
0x180001a75  jz      loc_180001BCD
0x180001a7b  lea     rax, [rbp+70h+TokenInformationLength]
0x180001a7f  mov     [rsp+100h+ReturnLength], rax; ReturnLength
0x180001a84  mov     r8, rsi; TokenInformation
0x180001a87  mov     edx, 1; TokenInformationClass
0x180001a8c  mov     rcx, [rbp+70h+TokenHandle]; TokenHandle
0x180001a90  call    cs:__imp_NtQueryInformationToken
0x180001a97  nop     dword ptr [rax+rax+00h]
0x180001a9c  test    eax, eax
0x180001a9e  js      loc_180001C74
0x180001aa4  mov     [rbp+70h+pSid], 101h
0x180001aab  mov     [rbp+70h+var_4C], 5000000h
0x180001ab2  mov     [rbp+70h+var_48], 12h
0x180001ab9  mov     r12, [rsi]
0x180001abc  mov     rcx, r12; Sid
0x180001abf  call    cs:__imp_RtlLengthSid
0x180001ac6  nop     dword ptr [rax+rax+00h]
0x180001acb  mov     [rbp+70h+TokenInformationLength], eax
0x180001ace  lea     edi, [rax+24h]
0x180001ad1  lea     eax, [rax+0Ah]
0x180001ad4  lea     r15d, [rdi+rax*2]
0x180001ad8  mov     r13d, r15d
0x180001adb  mov     ecx, r15d
0x180001ade  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x180001ae3  mov     rsi, rax
0x180001ae6  test    rax, rax
0x180001ae9  jz      loc_180001C8A
0x180001aef  mov     byte ptr [rax], 1
0x180001af2  mov     word ptr [rax+2], 8004h
0x180001af8  mov     r8d, [rbp+70h+TokenInformationLength]; Size
0x180001afc  lea     rcx, [rax+14h]; void *
0x180001b00  mov     rdx, r12; Src
0x180001b03  call    memcpy_0
0x180001b08  mov     dword ptr [rsi+4], 14h
0x180001b0f  mov     r8d, [rbp+70h+TokenInformationLength]; Size
0x180001b13  lea     rcx, [r8+14h]
0x180001b17  add     rcx, rsi; void *
0x180001b1a  mov     rdx, r12; Src
0x180001b1d  call    memcpy_0
0x180001b22  mov     eax, [rbp+70h+TokenInformationLength]
0x180001b25  add     eax, 14h
0x180001b28  mov     [rsi+8], eax
0x180001b2b  mov     eax, edi
0x180001b2d  mov     [rbp+70h+Size], rax
0x180001b31  mov     ecx, edi
0x180001b33  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x180001b38  mov     r14, rax
0x180001b3b  test    rax, rax
0x180001b3e  jz      loc_180001C7B
0x180001b44  mov     r8d, 2; AclRevision
0x180001b4a  mov     edx, edi; AclSize
0x180001b4c  mov     rcx, rax; Acl
0x180001b4f  call    cs:__imp_RtlCreateAcl
0x180001b56  nop     dword ptr [rax+rax+00h]
0x180001b5b  test    eax, eax
0x180001b5d  js      short loc_180001BAD
0x180001b5f  lea     rax, [rbp+70h+pSid]
0x180001b63  mov     [rsp+100h+ReturnLength], rax; pSid
0x180001b68  mov     r9d, 1F0001h; AccessMask
0x180001b6e  xor     r8d, r8d; AceFlags
0x180001b71  lea     edi, [r8+2]
0x180001b75  mov     edx, edi; dwAceRevision
0x180001b77  mov     rcx, r14; pAcl
0x180001b7a  call    cs:__imp_RtlAddAccessAllowedAceEx
0x180001b81  nop     dword ptr [rax+rax+00h]
0x180001b86  test    eax, eax
0x180001b88  js      short loc_180001BAD
0x180001b8a  mov     [rsp+100h+ReturnLength], r12; pSid
0x180001b8f  mov     r9d, 1F0001h; AccessMask
0x180001b95  xor     r8d, r8d; AceFlags
0x180001b98  mov     edx, edi; dwAceRevision
0x180001b9a  mov     rcx, r14; pAcl
0x180001b9d  call    cs:__imp_RtlAddAccessAllowedAceEx
0x180001ba4  nop     dword ptr [rax+rax+00h]
0x180001ba9  test    eax, eax
0x180001bab  jns     short loc_180001C00
0x180001bad  xor     edi, edi
0x180001baf  mov     rcx, rsi; hMem
0x180001bb2  call    cs:__imp_LocalFree
0x180001bb9  nop     dword ptr [rax+rax+00h]
0x180001bbe  mov     rcx, r14; hMem
0x180001bc1  call    cs:__imp_LocalFree
0x180001bc8  nop     dword ptr [rax+rax+00h]
0x180001bcd  mov     rcx, [rbp+70h+TokenHandle]; hObject
0x180001bd1  call    cs:__imp_CloseHandle
0x180001bd8  nop     dword ptr [rax+rax+00h]
0x180001bdd  mov     eax, edi
0x180001bdf  mov     rcx, [rbp+70h+var_40]
0x180001be3  xor     rcx, rbp; StackCookie
0x180001be6  call    __security_check_cookie
0x180001beb  lea     rsp, [rbp+40h]
0x180001bef  pop     r15
0x180001bf1  pop     r14
0x180001bf3  pop     r13
0x180001bf5  pop     r12
0x180001bf7  pop     rdi
0x180001bf8  pop     rsi
0x180001bf9  pop     rbp
0x180001bfa  retn
0x180001bfc  xor     edi, edi
0x180001bfe  jmp     short loc_180001BDD
0x180001c00  mov     eax, [rbp+70h+TokenInformationLength]
0x180001c03  add     rax, 0Ah
0x180001c07  lea     rcx, [rsi+rax*2]; void *
0x180001c0b  mov     r8, [rbp+70h+Size]; Size
0x180001c0f  mov     rdx, r14; Src
0x180001c12  call    memcpy_0
0x180001c17  mov     eax, [rbp+70h+TokenInformationLength]
0x180001c1a  lea     eax, ds:14h[rax*2]
0x180001c21  mov     [rsi+10h], eax
0x180001c24  mov     r8d, 7; RequiredInformation
0x180001c2a  mov     edx, r15d; SecurityDescriptorLength
0x180001c2d  mov     rcx, rsi; SecurityDescriptorInput
0x180001c30  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x180001c37  nop     dword ptr [rax+rax+00h]
0x180001c3c  test    al, al
0x180001c3e  jz      loc_180001BAD
0x180001c44  mov     edi, 1
0x180001c49  mov     cs:?g_SizeSD@@3KA, r15d; ulong g_SizeSD
0x180001c50  mov     r8, r13; Size
0x180001c53  mov     rdx, rsi; Src
0x180001c56  lea     rcx, ?g_RuntimeSD@@3PAKA; void *
0x180001c5d  call    memcpy_0
0x180001c62  jmp     loc_180001BAF
0x180001c67  cmp     ecx, 3F0h
0x180001c6d  jnz     short loc_180001BFC
0x180001c6f  jmp     loc_180001A13
0x180001c74  xor     edi, edi
0x180001c76  jmp     loc_180001BCD
0x180001c7b  mov     rcx, rsi; hMem
0x180001c7e  call    cs:__imp_LocalFree
0x180001c85  nop     dword ptr [rax+rax+00h]
0x180001c8a  mov     rcx, [rbp+70h+TokenHandle]; hObject
0x180001c8e  call    cs:__imp_CloseHandle
0x180001c95  nop     dword ptr [rax+rax+00h]
0x180001c9a  xor     eax, eax
0x180001c9c  jmp     loc_180001BDF
0x1800721c0  push    rbp
0x1800721c2  sub     rsp, 30h
0x1800721c6  lea     rbp, [rdx+30h]
0x1800721ca  mov     rax, [rcx]
0x1800721cd  xor     ecx, ecx
0x1800721cf  cmp     dword ptr [rax], 0C00000FDh
0x1800721d5  setz    cl
0x1800721d8  mov     eax, ecx
0x1800721da  add     rsp, 30h
0x1800721de  pop     rbp
0x1800721df  retn
```
