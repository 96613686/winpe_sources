# DCMutex::AcquireInternal(ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x18005a78c`
- end: `0x18005a9da`
- name: `?AcquireInternal@DCMutex@@AEAAJPEBG00K@Z`
- size: `590`
- prototype: `int(DCMutex *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005a67c`
- `0x180084570`

## callees

- `0x18000b9e0`
- `0x18000c8f4`
- `0x18000c984`
- `0x1800117dc`
- `0x180058630`
- `0x180059018`
- `0x18005a78c`
- `0x1800a1878`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005a92f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005a92f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18005a8bb`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18005a8bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a86e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a8c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a947`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a86e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a8c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a947`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005a8db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005a8db`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18005a85e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18005a85e`

## string_xrefs

- `0x18005a910`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\DCMutex.h`
- `0x18005a9ac`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\DCMutex.h`
- `0x18005a7f8`: `Global\OsConfig_%s_%s%s`

## pseudocode

```c
__int64 __fastcall DCMutex::AcquireInternal(
        DCMutex *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        DWORD dwMilliseconds)
{
  unsigned int v9; // ebx
  __int64 v10; // rdx
  signed int LastError; // eax
  HANDLE v12; // rbx
  signed int v13; // edi
  bool v14; // sf
  DWORD v15; // eax
  signed int v16; // eax
  int v18; // [rsp+20h] [rbp-E0h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE v20; // [rsp+48h] [rbp-B8h] BYREF
  _SECURITY_ATTRIBUTES MutexAttributes; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Buffer[256]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  if ( !a2 || !a3 )
  {
    v9 = -2147024809;
    v10 = 58;
    goto LABEL_31;
  }
  *((_BYTE *)this + 8) = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    this,
    0);
  memset_0(Buffer, 0, sizeof(Buffer));
  if ( !a4 )
    a4 = &word_180142E98;
  if ( snwprintf_s(Buffer, 0x100u, 0xFFFFFFFFFFFFFFFFuLL, L"Global\\OsConfig_%s_%s%s", a2, a3, a4) < 0 )
  {
    v9 = -2147024872;
    v10 = 66;
LABEL_31:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\DCMutex.h",
      (const char *)v9,
      v18);
    return v9;
  }
  SecurityDescriptor = 0;
  memset(&MutexAttributes, 0, sizeof(MutexAttributes));
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:P(A;;GA;;;SY)(A;;GA;;;BA)(A;;GA;;;IU)",
         1u,
         &SecurityDescriptor,
         0) )
  {
    MutexAttributes.lpSecurityDescriptor = SecurityDescriptor;
    MutexAttributes.nLength = 24;
    MutexAttributes.bInheritHandle = 0;
  }
  else
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( (v9 & 0x80000000) != 0 )
    {
      v10 = 71;
      goto LABEL_31;
    }
  }
  v12 = CreateMutexExW(&MutexAttributes, Buffer, 0, 0x1F0001u);
  v20 = v12;
  v13 = GetLastError();
  if ( SecurityDescriptor )
  {
    LocalFree(SecurityDescriptor);
    SecurityDescriptor = 0;
  }
  if ( (((unsigned __int64)v12 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v15 = WaitForSingleObject(v12, dwMilliseconds);
    if ( v15 )
    {
      if ( v15 == 128 )
      {
        *((_BYTE *)this + 8) = 1;
        wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
          this,
          &v20);
        v13 = -2147024161;
      }
      else if ( v15 == 258 )
      {
        v13 = -2147024775;
      }
      else
      {
        v16 = GetLastError();
        if ( v16 > 0 )
          v16 = (unsigned __int16)v16 | 0x80070000;
        v13 = v16;
      }
    }
    else
    {
      *((_BYTE *)this + 8) = 1;
      wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
        this,
        &v20);
      v13 = 0;
    }
  }
  else
  {
    v14 = v13 < 0;
    if ( v13 > 0 )
    {
      v13 = (unsigned __int16)v13 | 0x80070000;
      v14 = v13 < 0;
    }
    if ( v14 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x53,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\DCMutex.h",
        (const char *)(unsigned int)v13,
        v18);
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v20);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18005a78c  push    rbp
0x18005a78e  push    rbx
0x18005a78f  push    rsi
0x18005a790  push    rdi
0x18005a791  push    r14
0x18005a793  lea     rbp, [rsp-180h]
0x18005a79b  sub     rsp, 280h
0x18005a7a2  mov     rax, cs:__security_cookie
0x18005a7a9  xor     rax, rsp
0x18005a7ac  mov     [rbp+1A0h+var_30], rax
0x18005a7b3  mov     rdi, r9
0x18005a7b6  mov     rbx, r8
0x18005a7b9  mov     r14, rdx
0x18005a7bc  mov     rsi, rcx
0x18005a7bf  test    rdx, rdx
0x18005a7c2  jz      loc_18005A99B
0x18005a7c8  test    rbx, rbx
0x18005a7cb  jz      loc_18005A99B
0x18005a7d1  xor     edx, edx
0x18005a7d3  mov     byte ptr [rcx+8], 0
0x18005a7d7  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18005a7dc  xor     edx, edx; Val
0x18005a7de  lea     rcx, [rsp+2A0h+Buffer]; void *
0x18005a7e3  mov     r8d, 200h; Size
0x18005a7e9  call    memset_0
0x18005a7ee  lea     rax, word_180142E98
0x18005a7f5  test    rdi, rdi
0x18005a7f8  lea     r9, aGlobalOsconfig; "Global\\OsConfig_%s_%s%s"
0x18005a7ff  mov     edx, 100h; BufferCount
0x18005a804  cmovz   rdi, rax
0x18005a808  lea     rcx, [rsp+2A0h+Buffer]; Buffer
0x18005a80d  mov     [rsp+2A0h+var_270], rdi
0x18005a812  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18005a816  mov     [rsp+2A0h+var_278], rbx
0x18005a81b  mov     qword ptr [rsp+2A0h+var_280], r14; int
0x18005a820  call    _snwprintf_s
0x18005a825  test    eax, eax
0x18005a827  jns     short loc_18005A838
0x18005a829  mov     ebx, 80070018h
0x18005a82e  mov     edx, 42h ; 'B'
0x18005a833  jmp     loc_18005A9A5
0x18005a838  xor     eax, eax
0x18005a83a  lea     r8, [rsp+2A0h+SecurityDescriptor]; SecurityDescriptor
0x18005a83f  xorps   xmm0, xmm0
0x18005a842  mov     qword ptr [rsp+2A0h+MutexAttributes.bInheritHandle], rax
0x18005a847  xor     r9d, r9d; SecurityDescriptorSize
0x18005a84a  mov     [rsp+2A0h+SecurityDescriptor], rax
0x18005a84f  lea     rcx, StringSecurityDescriptor; "D:P(A;;GA;;;SY)(A;;GA;;;BA)(A;;GA;;;IU)"
0x18005a856  lea     edx, [rax+1]; StringSDRevision
0x18005a859  movups  xmmword ptr [rsp+2A0h+MutexAttributes.nLength], xmm0
0x18005a85e  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18005a864  mov     r14d, 80070000h
0x18005a86a  test    eax, eax
0x18005a86c  jnz     short loc_18005A88E
0x18005a86e  call    cs:__imp_GetLastError
0x18005a874  mov     ebx, eax
0x18005a876  test    eax, eax
0x18005a878  jle     short loc_18005A880
0x18005a87a  movzx   ebx, ax
0x18005a87d  or      ebx, r14d
0x18005a880  test    ebx, ebx
0x18005a882  jns     short loc_18005A8A8
0x18005a884  mov     edx, 47h ; 'G'
0x18005a889  jmp     loc_18005A9A5
0x18005a88e  mov     rax, [rsp+2A0h+SecurityDescriptor]
0x18005a893  mov     [rsp+2A0h+MutexAttributes.lpSecurityDescriptor], rax
0x18005a898  mov     [rsp+2A0h+MutexAttributes.nLength], 18h
0x18005a8a0  mov     [rsp+2A0h+MutexAttributes.bInheritHandle], 0
0x18005a8a8  mov     r9d, 1F0001h; dwDesiredAccess
0x18005a8ae  lea     rdx, [rsp+2A0h+Buffer]; lpName
0x18005a8b3  xor     r8d, r8d; dwFlags
0x18005a8b6  lea     rcx, [rsp+2A0h+MutexAttributes]; lpMutexAttributes
0x18005a8bb  call    cs:__imp_CreateMutexExW
0x18005a8c1  mov     rbx, rax
0x18005a8c4  mov     [rsp+2A0h+var_258], rax
0x18005a8c9  call    cs:__imp_GetLastError
0x18005a8cf  mov     rcx, [rsp+2A0h+SecurityDescriptor]; hMem
0x18005a8d4  mov     edi, eax
0x18005a8d6  test    rcx, rcx
0x18005a8d9  jz      short loc_18005A8EA
0x18005a8db  call    cs:__imp_LocalFree
0x18005a8e1  mov     [rsp+2A0h+SecurityDescriptor], 0
0x18005a8ea  lea     rcx, [rbx+1]
0x18005a8ee  test    rcx, 0FFFFFFFFFFFFFFFEh
0x18005a8f5  jnz     short loc_18005A926
0x18005a8f7  test    edi, edi
0x18005a8f9  jle     short loc_18005A903
0x18005a8fb  movzx   edi, di
0x18005a8fe  or      edi, r14d
0x18005a901  test    edi, edi
0x18005a903  jns     loc_18005A98D
0x18005a909  mov     rcx, [rbp+1A8h]; this
0x18005a910  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18005a917  mov     r9d, edi; char *
0x18005a91a  mov     edx, 53h ; 'S'; void *
0x18005a91f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a924  jmp     short loc_18005A98D
0x18005a926  mov     edx, [rbp+1A0h+dwMilliseconds]; dwMilliseconds
0x18005a92c  mov     rcx, rbx; hHandle
0x18005a92f  call    cs:__imp_WaitForSingleObject
0x18005a935  test    eax, eax
0x18005a937  jz      short loc_18005A97A
0x18005a939  cmp     eax, 80h
0x18005a93e  jz      short loc_18005A962
0x18005a940  cmp     eax, 102h
0x18005a945  jz      short loc_18005A95B
0x18005a947  call    cs:__imp_GetLastError
0x18005a94d  test    eax, eax
0x18005a94f  jle     short loc_18005A957
0x18005a951  movzx   eax, ax
0x18005a954  or      eax, r14d
0x18005a957  mov     edi, eax
0x18005a959  jmp     short loc_18005A98D
0x18005a95b  mov     edi, 80070079h
0x18005a960  jmp     short loc_18005A98D
0x18005a962  lea     rdx, [rsp+2A0h+var_258]
0x18005a967  mov     byte ptr [rsi+8], 1
0x18005a96b  mov     rcx, rsi
0x18005a96e  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x18005a973  mov     edi, 800702DFh
0x18005a978  jmp     short loc_18005A98D
0x18005a97a  lea     rdx, [rsp+2A0h+var_258]
0x18005a97f  mov     byte ptr [rsi+8], 1
0x18005a983  mov     rcx, rsi
0x18005a986  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x18005a98b  xor     edi, edi
0x18005a98d  lea     rcx, [rsp+2A0h+var_258]
0x18005a992  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18005a997  mov     eax, edi
0x18005a999  jmp     short loc_18005A9BD
0x18005a99b  mov     ebx, 80070057h
0x18005a9a0  mov     edx, 3Ah ; ':'; void *
0x18005a9a5  mov     rcx, [rbp+1A8h]; this
0x18005a9ac  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18005a9b3  mov     r9d, ebx; char *
0x18005a9b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a9bb  mov     eax, ebx
0x18005a9bd  mov     rcx, [rbp+1A0h+var_30]
0x18005a9c4  xor     rcx, rsp; StackCookie
0x18005a9c7  call    __security_check_cookie
0x18005a9cc  add     rsp, 280h
0x18005a9d3  pop     r14
0x18005a9d5  pop     rdi
0x18005a9d6  pop     rsi
0x18005a9d7  pop     rbx
0x18005a9d8  pop     rbp
0x18005a9d9  retn
```
