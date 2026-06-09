# PerflibCreateSD(ulong)

- ea: `0x18002fbe0`
- end: `0x18002fe4e`
- name: `?PerflibCreateSD@@YAHK@Z`
- size: `622`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180018470`

## callees

- `0x180017100`
- `0x18002fbe0`
- `0x180058678`
- `0x180065042`
- `0x180065090`

## import_xrefs

- `ntdll!NtOpenProcessToken` at `0x18002fc25`
- `ntdll!NtOpenProcessToken` at `0x18002fc25`
- `ntdll!RtlLengthSid` at `0x18002fcad`
- `ntdll!RtlLengthSid` at `0x18002fcad`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x18002fd5c`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x18002fd79`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x18002fd5c`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x18002fd79`
- `ntdll!RtlCreateAcl` at `0x18002fd37`
- `ntdll!RtlCreateAcl` at `0x18002fd37`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18002fdf3`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18002fdf3`
- `ntdll!NtQueryInformationToken` at `0x18002fc84`
- `ntdll!NtQueryInformationToken` at `0x18002fc84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002fc13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002fc13`
- `KERNEL32!LocalFree` at `0x18002fd88`
- `KERNEL32!LocalFree` at `0x18002fd91`
- `KERNEL32!LocalFree` at `0x18002fe37`
- `KERNEL32!LocalFree` at `0x18002fd88`
- `KERNEL32!LocalFree` at `0x18002fd91`
- `KERNEL32!LocalFree` at `0x18002fe37`
- `KERNEL32!CloseHandle` at `0x18002fd9b`
- `KERNEL32!CloseHandle` at `0x18002fe41`
- `KERNEL32!CloseHandle` at `0x18002fd9b`
- `KERNEL32!CloseHandle` at `0x18002fe41`

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
0x18002fbe0  push    rbp
0x18002fbe2  push    rsi
0x18002fbe3  push    rdi
0x18002fbe4  push    r12
0x18002fbe6  push    r13
0x18002fbe8  push    r14
0x18002fbea  push    r15
0x18002fbec  sub     rsp, 70h
0x18002fbf0  lea     rbp, [rsp+30h]
0x18002fbf5  mov     rax, cs:__security_cookie
0x18002fbfc  xor     rax, rbp
0x18002fbff  mov     [rbp+70h+var_40], rax
0x18002fc03  mov     [rbp+70h+TokenHandle], 0
0x18002fc0b  test    ecx, ecx
0x18002fc0d  jnz     loc_18002FE20
0x18002fc13  call    cs:__imp_GetCurrentProcess
0x18002fc19  mov     rcx, rax; ProcessHandle
0x18002fc1c  lea     r8, [rbp+70h+TokenHandle]; TokenHandle
0x18002fc20  mov     edx, 8; DesiredAccess
0x18002fc25  call    cs:__imp_NtOpenProcessToken
0x18002fc2b  test    eax, eax
0x18002fc2d  js      loc_18002FDBF
0x18002fc33  mov     edi, 1
0x18002fc38  lea     r9d, [rdi+57h]
0x18002fc3c  mov     [rbp+70h+TokenInformationLength], r9d
0x18002fc40  mov     eax, [rsp+0A0h+var_A0]
0x18002fc43  sub     rsp, 60h
0x18002fc47  lea     rsi, [rsp+100h+TokenInformation]
0x18002fc4c  mov     eax, [rsi]
0x18002fc4e  mov     [rbp+70h+var_60], rsi
0x18002fc52  jmp     short loc_18002FC67
0x18002fc54  mov     ecx, eax; unsigned int
0x18002fc56  call    ?PerfpExceptionHandler@@YAXK@Z; PerfpExceptionHandler(ulong)
0x18002fc5b  xor     esi, esi
0x18002fc5d  mov     [rbp+70h+var_60], rsi
0x18002fc61  xor     edi, edi
0x18002fc63  mov     r9d, [rbp+70h+TokenInformationLength]; TokenInformationLength
0x18002fc67  test    edi, edi
0x18002fc69  jz      loc_18002FD97
0x18002fc6f  lea     rax, [rbp+70h+TokenInformationLength]
0x18002fc73  mov     [rsp+100h+ReturnLength], rax; ReturnLength
0x18002fc78  mov     r8, rsi; TokenInformation
0x18002fc7b  mov     edx, 1; TokenInformationClass
0x18002fc80  mov     rcx, [rbp+70h+TokenHandle]; TokenHandle
0x18002fc84  call    cs:__imp_NtQueryInformationToken
0x18002fc8a  test    eax, eax
0x18002fc8c  js      loc_18002FE2D
0x18002fc92  mov     [rbp+70h+pSid], 101h
0x18002fc99  mov     [rbp+70h+var_4C], 5000000h
0x18002fca0  mov     [rbp+70h+var_48], 12h
0x18002fca7  mov     r12, [rsi]
0x18002fcaa  mov     rcx, r12; Sid
0x18002fcad  call    cs:__imp_RtlLengthSid
0x18002fcb3  mov     [rbp+70h+TokenInformationLength], eax
0x18002fcb6  lea     edi, [rax+24h]
0x18002fcb9  lea     eax, [rax+0Ah]
0x18002fcbc  lea     r15d, [rdi+rax*2]
0x18002fcc0  mov     r13d, r15d
0x18002fcc3  mov     ecx, r15d
0x18002fcc6  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x18002fccb  mov     rsi, rax
0x18002fcce  test    rax, rax
0x18002fcd1  jz      loc_18002FE3D
0x18002fcd7  mov     byte ptr [rax], 1
0x18002fcda  mov     word ptr [rax+2], 8004h
0x18002fce0  mov     r8d, [rbp+70h+TokenInformationLength]; Size
0x18002fce4  lea     rcx, [rax+14h]; void *
0x18002fce8  mov     rdx, r12; Src
0x18002fceb  call    memcpy_0
0x18002fcf0  mov     dword ptr [rsi+4], 14h
0x18002fcf7  mov     r8d, [rbp+70h+TokenInformationLength]; Size
0x18002fcfb  lea     rcx, [r8+14h]
0x18002fcff  add     rcx, rsi; void *
0x18002fd02  mov     rdx, r12; Src
0x18002fd05  call    memcpy_0
0x18002fd0a  mov     eax, [rbp+70h+TokenInformationLength]
0x18002fd0d  add     eax, 14h
0x18002fd10  mov     [rsi+8], eax
0x18002fd13  mov     eax, edi
0x18002fd15  mov     [rbp+70h+Size], rax
0x18002fd19  mov     ecx, edi
0x18002fd1b  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x18002fd20  mov     r14, rax
0x18002fd23  test    rax, rax
0x18002fd26  jz      loc_18002FE34
0x18002fd2c  mov     r8d, 2; AclRevision
0x18002fd32  mov     edx, edi; AclSize
0x18002fd34  mov     rcx, rax; Acl
0x18002fd37  call    cs:__imp_RtlCreateAcl
0x18002fd3d  test    eax, eax
0x18002fd3f  js      short loc_18002FD83
0x18002fd41  lea     rax, [rbp+70h+pSid]
0x18002fd45  mov     [rsp+100h+ReturnLength], rax; pSid
0x18002fd4a  mov     r9d, 1F0001h; AccessMask
0x18002fd50  xor     r8d, r8d; AceFlags
0x18002fd53  lea     edi, [r8+2]
0x18002fd57  mov     edx, edi; dwAceRevision
0x18002fd59  mov     rcx, r14; pAcl
0x18002fd5c  call    cs:__imp_RtlAddAccessAllowedAceEx
0x18002fd62  test    eax, eax
0x18002fd64  js      short loc_18002FD83
0x18002fd66  mov     [rsp+100h+ReturnLength], r12; pSid
0x18002fd6b  mov     r9d, 1F0001h; AccessMask
0x18002fd71  xor     r8d, r8d; AceFlags
0x18002fd74  mov     edx, edi; dwAceRevision
0x18002fd76  mov     rcx, r14; pAcl
0x18002fd79  call    cs:__imp_RtlAddAccessAllowedAceEx
0x18002fd7f  test    eax, eax
0x18002fd81  jns     short loc_18002FDC3
0x18002fd83  xor     edi, edi
0x18002fd85  mov     rcx, rsi; hMem
0x18002fd88  call    cs:__imp_LocalFree
0x18002fd8e  mov     rcx, r14; hMem
0x18002fd91  call    cs:__imp_LocalFree
0x18002fd97  mov     rcx, [rbp+70h+TokenHandle]; hObject
0x18002fd9b  call    cs:__imp_CloseHandle
0x18002fda1  mov     eax, edi
0x18002fda3  mov     rcx, [rbp+70h+var_40]
0x18002fda7  xor     rcx, rbp; StackCookie
0x18002fdaa  call    __security_check_cookie
0x18002fdaf  lea     rsp, [rbp+40h]
0x18002fdb3  pop     r15
0x18002fdb5  pop     r14
0x18002fdb7  pop     r13
0x18002fdb9  pop     r12
0x18002fdbb  pop     rdi
0x18002fdbc  pop     rsi
0x18002fdbd  pop     rbp
0x18002fdbe  retn
0x18002fdbf  xor     edi, edi
0x18002fdc1  jmp     short loc_18002FDA1
0x18002fdc3  mov     eax, [rbp+70h+TokenInformationLength]
0x18002fdc6  add     rax, 0Ah
0x18002fdca  lea     rcx, [rsi+rax*2]; void *
0x18002fdce  mov     r8, [rbp+70h+Size]; Size
0x18002fdd2  mov     rdx, r14; Src
0x18002fdd5  call    memcpy_0
0x18002fdda  mov     eax, [rbp+70h+TokenInformationLength]
0x18002fddd  lea     eax, ds:14h[rax*2]
0x18002fde4  mov     [rsi+10h], eax
0x18002fde7  mov     r8d, 7; RequiredInformation
0x18002fded  mov     edx, r15d; SecurityDescriptorLength
0x18002fdf0  mov     rcx, rsi; SecurityDescriptorInput
0x18002fdf3  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x18002fdf9  test    al, al
0x18002fdfb  jz      short loc_18002FD83
0x18002fdfd  mov     edi, 1
0x18002fe02  mov     cs:?g_SizeSD@@3KA, r15d; ulong g_SizeSD
0x18002fe09  mov     r8, r13; Size
0x18002fe0c  mov     rdx, rsi; Src
0x18002fe0f  lea     rcx, ?g_RuntimeSD@@3PAKA; void *
0x18002fe16  call    memcpy_0
0x18002fe1b  jmp     loc_18002FD85
0x18002fe20  cmp     ecx, 3F0h
0x18002fe26  jnz     short loc_18002FDBF
0x18002fe28  jmp     loc_18002FC13
0x18002fe2d  xor     edi, edi
0x18002fe2f  jmp     loc_18002FD97
0x18002fe34  mov     rcx, rsi; hMem
0x18002fe37  call    cs:__imp_LocalFree
0x18002fe3d  mov     rcx, [rbp+70h+TokenHandle]; hObject
0x18002fe41  call    cs:__imp_CloseHandle
0x18002fe47  xor     eax, eax
0x18002fe49  jmp     loc_18002FDA3
0x180065669  push    rbp
0x18006566b  sub     rsp, 30h
0x18006566f  lea     rbp, [rdx+30h]
0x180065673  mov     rax, [rcx]
0x180065676  xor     ecx, ecx
0x180065678  cmp     dword ptr [rax], 0C00000FDh
0x18006567e  setz    cl
0x180065681  mov     eax, ecx
0x180065683  add     rsp, 30h
0x180065687  pop     rbp
0x180065688  retn
```
