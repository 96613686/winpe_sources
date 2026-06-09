# GetProcessElevationStates(LuaElevationStates *)

- ea: `0x18002647c`
- end: `0x1800267cb`
- name: `?GetProcessElevationStates@@YAJPEAW4LuaElevationStates@@@Z`
- size: `847`
- prototype: `__int64 __fastcall(enum LuaElevationStates *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180026130`

## callees

- `0x18000ee68`
- `0x18002647c`
- `0x180348990`
- `0x18034f504`
- `0x1803a4cb0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800264bc`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800264bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800264ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800264ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800266c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800267c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800266c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800267c0`
- `ntdll!NtQueryInformationToken` at `0x180026506`
- `ntdll!NtQueryInformationToken` at `0x1800265f1`
- `ntdll!NtQueryInformationToken` at `0x18002662b`
- `ntdll!NtQueryInformationToken` at `0x18002666e`
- `ntdll!NtQueryInformationToken` at `0x180026506`
- `ntdll!NtQueryInformationToken` at `0x1800265f1`
- `ntdll!NtQueryInformationToken` at `0x18002662b`
- `ntdll!NtQueryInformationToken` at `0x18002666e`
- `ntdll!RtlCompareUnicodeString` at `0x1800266e2`
- `ntdll!RtlCompareUnicodeString` at `0x180026706`
- `ntdll!RtlCompareUnicodeString` at `0x180026726`
- `ntdll!RtlCompareUnicodeString` at `0x180026757`
- `ntdll!RtlCompareUnicodeString` at `0x1800266e2`
- `ntdll!RtlCompareUnicodeString` at `0x180026706`
- `ntdll!RtlCompareUnicodeString` at `0x180026726`
- `ntdll!RtlCompareUnicodeString` at `0x180026757`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026646`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026646`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026567`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026567`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetProcessElevationStates(enum LuaElevationStates *a1)
{
  BOOL v2; // r14d
  HANDLE CurrentProcess; // rax
  wil::details *v4; // rcx
  void *v5; // rsi
  int v6; // r15d
  int v7; // r12d
  int v8; // r13d
  NTSTATUS v9; // edi
  unsigned int LastErrorFailHr; // ebx
  bool v12; // zf
  __int64 v13; // rsi
  HLOCAL v14; // r15
  int v15; // eax
  int ReturnLength; // [rsp+20h] [rbp-48h]
  int TokenInformation; // [rsp+30h] [rbp-38h] BYREF
  ULONG TokenInformationLength; // [rsp+34h] [rbp-34h] BYREF
  int v19; // [rsp+38h] [rbp-30h]
  __int64 v20; // [rsp+40h] [rbp-28h] BYREF
  ULONG v21; // [rsp+48h] [rbp-20h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]

  v2 = 0;
  *(_DWORD *)a1 = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v4);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    return LastErrorFailHr;
  }
  v5 = TokenHandle;
  TokenInformationLength = 0;
  v6 = 0;
  v19 = 0;
  v21 = 0;
  LODWORD(v20) = 0;
  TokenInformation = 1;
  v7 = 1;
  v8 = 0;
  v9 = NtQueryInformationToken(TokenHandle, TokenElevationType, &TokenInformation, 4u, &v21);
  if ( v9 < 0 )
    goto LABEL_5;
  if ( TokenInformation != 2 )
  {
    if ( TokenInformation == 1 )
    {
      v7 = 0;
      v9 = NtQueryInformationToken(v5, TokenElevation, &v20, 4u, &v21);
      if ( v9 >= 0 )
      {
        if ( (_DWORD)v20 )
        {
          LODWORD(v13) = 0;
          goto LABEL_12;
        }
      }
    }
LABEL_5:
    if ( v9 < 0 )
      goto LABEL_6;
    LODWORD(v13) = 0;
    goto LABEL_11;
  }
  v9 = NtQueryInformationToken(v5, TokenSecurityAttributes, 0, 0, &TokenInformationLength);
  if ( v9 == -1073741789 )
  {
    v14 = LocalAlloc(0x40u, TokenInformationLength);
    if ( !v14 )
    {
      v9 = -1073741801;
      goto LABEL_6;
    }
    v9 = NtQueryInformationToken(v5, TokenSecurityAttributes, v14, TokenInformationLength, &TokenInformationLength);
    v13 = 0;
    if ( v9 < 0 )
    {
      v8 = 1;
      v7 = 1;
    }
    else
    {
      v7 = 1;
      while ( 1 )
      {
        if ( (unsigned int)v13 >= *((_DWORD *)v14 + 1) )
        {
          v15 = v19;
          goto LABEL_34;
        }
        v20 = 5 * v13;
        if ( !RtlCompareUnicodeString(&String1, (PCUNICODE_STRING)(*((_QWORD *)v14 + 1) + 40 * v13), 1u) )
          break;
        if ( !RtlCompareUnicodeString(&stru_180667540, (PCUNICODE_STRING)(*((_QWORD *)v14 + 1) + 8 * v20), 1u) )
          goto LABEL_47;
        if ( RtlCompareUnicodeString(&stru_180667550, (PCUNICODE_STRING)(*((_QWORD *)v14 + 1) + 8 * v20), 1u) )
        {
          if ( !RtlCompareUnicodeString(&stru_180667E70, (PCUNICODE_STRING)(*((_QWORD *)v14 + 1) + 8 * v20), 1u) )
            v2 = 1;
        }
        else
        {
          v8 = 1;
          v2 = 1;
        }
        v13 = (unsigned int)(v13 + 1);
      }
      v8 = 1;
LABEL_47:
      v15 = 1;
      v19 = 1;
LABEL_34:
      LODWORD(v13) = 0;
      if ( v2 )
        LODWORD(v13) = v15 == 0;
      v12 = v8 == 0;
      v8 = 1;
      v2 = !v12;
    }
    LocalFree(v14);
    v6 = v19;
  }
  else
  {
    LODWORD(v13) = 0;
    v8 = 1;
    v7 = 1;
  }
  if ( v9 < 0 )
  {
LABEL_6:
    LastErrorFailHr = wil::details::in1diag3::Return_NtStatus(
                        retaddr,
                        (void *)0x16B2,
                        (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\util.cpp",
                        (const char *)(unsigned int)v9,
                        ReturnLength);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return LastErrorFailHr;
  }
LABEL_11:
  if ( v8 )
LABEL_12:
    *(_DWORD *)a1 |= 1u;
  if ( v7 )
    *(_DWORD *)a1 |= 2u;
  if ( v6 )
    *(_DWORD *)a1 |= 4u;
  if ( (_DWORD)v13 )
    *(_DWORD *)a1 |= 8u;
  if ( v2 )
    *(_DWORD *)a1 |= 0x10u;
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x18002647c  push    rbp
0x18002647e  push    rbx
0x18002647f  push    rsi
0x180026480  push    rdi
0x180026481  push    r12
0x180026483  push    r13
0x180026485  push    r14
0x180026487  push    r15
0x180026489  mov     rbp, rsp
0x18002648c  sub     rsp, 68h
0x180026490  mov     rax, cs:__security_cookie
0x180026497  xor     rax, rsp
0x18002649a  mov     [rbp+var_10], rax
0x18002649e  mov     rbx, rcx
0x1800264a1  xor     r14d, r14d
0x1800264a4  mov     [rcx], r14d
0x1800264a7  mov     [rbp+TokenHandle], r14
0x1800264ab  call    cs:__imp_GetCurrentProcess
0x1800264b1  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800264b5  lea     edx, [r14+8]; DesiredAccess
0x1800264b9  mov     rcx, rax; ProcessHandle
0x1800264bc  call    cs:__imp_OpenProcessToken
0x1800264c2  test    eax, eax
0x1800264c4  jz      loc_1800266A7
0x1800264ca  mov     rsi, [rbp+TokenHandle]
0x1800264ce  mov     [rbp+TokenInformationLength], r14d
0x1800264d2  mov     r15d, r14d
0x1800264d5  mov     [rbp+var_30], r14d
0x1800264d9  mov     [rbp+var_20], r14d
0x1800264dd  mov     dword ptr [rbp+var_28], r14d
0x1800264e1  lea     eax, [r14+1]
0x1800264e5  mov     [rbp+TokenInformation], eax
0x1800264e8  mov     r12d, eax
0x1800264eb  mov     r13d, r14d
0x1800264ee  lea     rax, [rbp+var_20]
0x1800264f2  mov     qword ptr [rsp+68h+ReturnLength], rax; int
0x1800264f7  lea     r9d, [r14+4]; TokenInformationLength
0x1800264fb  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800264ff  lea     edx, [r14+12h]; TokenInformationClass
0x180026503  mov     rcx, rsi; TokenHandle
0x180026506  call    cs:__imp_NtQueryInformationToken
0x18002650c  mov     edi, eax
0x18002650e  test    eax, eax
0x180026510  js      short loc_180026526
0x180026512  cmp     [rbp+TokenInformation], 2
0x180026516  jz      loc_180026612
0x18002651c  cmp     [rbp+TokenInformation], r12d
0x180026520  jz      loc_1800265D4
0x180026526  test    edi, edi
0x180026528  jns     loc_1800265D0
0x18002652e  mov     rcx, [rbp+40h]; this
0x180026532  mov     r9d, edi; char *
0x180026535  lea     r8, aOnecoreuapShel_50; "onecoreuap\\shell\\windows.storage\\sha"...
0x18002653c  mov     edx, 16B2h; void *
0x180026541  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180026546  mov     ebx, eax
0x180026548  lea     rcx, [rbp+TokenHandle]
0x18002654c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180026551  mov     eax, ebx
0x180026553  jmp     short loc_1800265B3
0x180026555  xor     r14d, r14d
0x180026558  test    r13d, r13d
0x18002655b  mov     r13d, r12d
0x18002655e  jnz     loc_180026790
0x180026564  mov     rcx, r15; hMem
0x180026567  call    cs:__imp_LocalFree
0x18002656d  mov     r15d, [rbp+var_30]
0x180026571  test    edi, edi
0x180026573  js      short loc_18002652E
0x180026575  test    r13d, r13d
0x180026578  jz      short loc_18002657D
0x18002657a  or      dword ptr [rbx], 1
0x18002657d  test    r12d, r12d
0x180026580  jz      short loc_180026585
0x180026582  or      dword ptr [rbx], 2
0x180026585  test    r15d, r15d
0x180026588  jnz     loc_180026765
0x18002658e  test    esi, esi
0x180026590  jnz     loc_1800267B8
0x180026596  test    r14d, r14d
0x180026599  jnz     loc_18002676D
0x18002659f  mov     rcx, [rbp+TokenHandle]; hObject
0x1800265a3  lea     rax, [rcx-1]
0x1800265a7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800265ab  jbe     loc_1800267C0
0x1800265b1  xor     eax, eax
0x1800265b3  mov     rcx, [rbp+var_10]
0x1800265b7  xor     rcx, rsp; StackCookie
0x1800265ba  call    __security_check_cookie
0x1800265bf  add     rsp, 68h
0x1800265c3  pop     r15
0x1800265c5  pop     r14
0x1800265c7  pop     r13
0x1800265c9  pop     r12
0x1800265cb  pop     rdi
0x1800265cc  pop     rsi
0x1800265cd  pop     rbx
0x1800265ce  pop     rbp
0x1800265cf  retn
0x1800265d0  xor     esi, esi
0x1800265d2  jmp     short loc_180026575
0x1800265d4  mov     r12d, r14d
0x1800265d7  lea     rax, [rbp+var_20]
0x1800265db  mov     qword ptr [rsp+68h+ReturnLength], rax; ReturnLength
0x1800265e0  mov     r9d, 4; TokenInformationLength
0x1800265e6  lea     r8, [rbp+var_28]; TokenInformation
0x1800265ea  lea     edx, [r9+10h]; TokenInformationClass
0x1800265ee  mov     rcx, rsi; TokenHandle
0x1800265f1  call    cs:__imp_NtQueryInformationToken
0x1800265f7  mov     edi, eax
0x1800265f9  test    eax, eax
0x1800265fb  js      loc_180026526
0x180026601  cmp     dword ptr [rbp+var_28], r14d
0x180026605  jz      loc_180026526
0x18002660b  xor     esi, esi
0x18002660d  jmp     loc_18002657A
0x180026612  lea     rax, [rbp+TokenInformationLength]
0x180026616  mov     qword ptr [rsp+68h+ReturnLength], rax; ReturnLength
0x18002661b  xor     r9d, r9d; TokenInformationLength
0x18002661e  xor     r8d, r8d; TokenInformation
0x180026621  lea     r12d, [r9+27h]
0x180026625  mov     edx, r12d; TokenInformationClass
0x180026628  mov     rcx, rsi; TokenHandle
0x18002662b  call    cs:__imp_NtQueryInformationToken
0x180026631  mov     edi, eax
0x180026633  cmp     eax, 0C0000023h
0x180026638  jnz     loc_1800267A8
0x18002663e  mov     edx, [rbp+TokenInformationLength]; uBytes
0x180026641  lea     ecx, [r12+19h]; uFlags
0x180026646  call    cs:__imp_LocalAlloc
0x18002664c  mov     r15, rax
0x18002664f  test    rax, rax
0x180026652  jz      loc_180026786
0x180026658  lea     rax, [rbp+TokenInformationLength]
0x18002665c  mov     qword ptr [rsp+68h+ReturnLength], rax; ReturnLength
0x180026661  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180026665  mov     r8, r15; TokenInformation
0x180026668  mov     edx, r12d; TokenInformationClass
0x18002666b  mov     rcx, rsi; TokenHandle
0x18002666e  call    cs:__imp_NtQueryInformationToken
0x180026674  mov     edi, eax
0x180026676  xor     esi, esi
0x180026678  test    eax, eax
0x18002667a  js      loc_180026798
0x180026680  lea     r8d, [r12-26h]; CaseInsensitive
0x180026685  mov     r12d, r8d
0x180026688  cmp     esi, [r15+4]
0x18002668c  jb      short loc_1800266CB
0x18002668e  mov     eax, [rbp+var_30]
0x180026691  xor     esi, esi
0x180026693  test    r14d, r14d
0x180026696  jz      loc_180026555
0x18002669c  test    eax, eax
0x18002669e  cmovz   esi, r8d
0x1800266a2  jmp     loc_180026555
0x1800266a7  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800266ac  mov     ebx, eax
0x1800266ae  mov     rcx, [rbp+TokenHandle]; hObject
0x1800266b2  lea     rdx, [rcx-1]
0x1800266b6  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800266ba  ja      loc_180026551
0x1800266c0  call    cs:__imp_CloseHandle
0x1800266c6  jmp     loc_180026551
0x1800266cb  lea     rcx, [rsi+rsi*4]
0x1800266cf  mov     [rbp+var_28], rcx
0x1800266d3  mov     rax, [r15+8]
0x1800266d7  lea     rdx, [rax+rcx*8]; String2
0x1800266db  lea     rcx, String1; String1
0x1800266e2  call    cs:__imp_RtlCompareUnicodeString
0x1800266e8  test    eax, eax
0x1800266ea  jz      loc_180026775
0x1800266f0  mov     rax, [r15+8]
0x1800266f4  mov     rcx, [rbp+var_28]
0x1800266f8  lea     rdx, [rax+rcx*8]; String2
0x1800266fc  mov     r8b, r12b; CaseInsensitive
0x1800266ff  lea     rcx, stru_180667540; String1
0x180026706  call    cs:__imp_RtlCompareUnicodeString
0x18002670c  test    eax, eax
0x18002670e  jz      short loc_180026778
0x180026710  mov     rax, [r15+8]
0x180026714  mov     rcx, [rbp+var_28]
0x180026718  lea     rdx, [rax+rcx*8]; String2
0x18002671c  mov     r8b, r12b; CaseInsensitive
0x18002671f  lea     rcx, stru_180667550; String1
0x180026726  call    cs:__imp_RtlCompareUnicodeString
0x18002672c  test    eax, eax
0x18002672e  jnz     short loc_180026741
0x180026730  mov     r13d, r12d
0x180026733  mov     r14d, r12d
0x180026736  mov     r8d, r12d
0x180026739  add     esi, r12d
0x18002673c  jmp     loc_180026688
0x180026741  mov     rax, [r15+8]
0x180026745  mov     rcx, [rbp+var_28]
0x180026749  lea     rdx, [rax+rcx*8]; String2
0x18002674d  mov     r8b, r12b; CaseInsensitive
0x180026750  lea     rcx, stru_180667E70; String1
0x180026757  call    cs:__imp_RtlCompareUnicodeString
0x18002675d  test    eax, eax
0x18002675f  cmovz   r14d, r12d
0x180026763  jmp     short loc_180026736
0x180026765  or      dword ptr [rbx], 4
0x180026768  jmp     loc_18002658E
0x18002676d  or      dword ptr [rbx], 10h
0x180026770  jmp     loc_18002659F
0x180026775  mov     r13d, r12d
0x180026778  mov     r8d, r12d
0x18002677b  mov     eax, r12d
0x18002677e  mov     [rbp+var_30], eax
0x180026781  jmp     loc_180026691
0x180026786  mov     edi, 0C0000017h
0x18002678b  jmp     loc_18002652E
0x180026790  mov     r14d, r8d
0x180026793  jmp     loc_180026564
0x180026798  mov     eax, 1
0x18002679d  mov     r13d, eax
0x1800267a0  mov     r12d, eax
0x1800267a3  jmp     loc_180026564
0x1800267a8  xor     esi, esi
0x1800267aa  lea     eax, [rsi+1]
0x1800267ad  mov     r13d, eax
0x1800267b0  mov     r12d, eax
0x1800267b3  jmp     loc_180026571
0x1800267b8  or      dword ptr [rbx], 8
0x1800267bb  jmp     loc_180026596
0x1800267c0  call    cs:__imp_CloseHandle
0x1800267c6  jmp     loc_1800265B1
```
