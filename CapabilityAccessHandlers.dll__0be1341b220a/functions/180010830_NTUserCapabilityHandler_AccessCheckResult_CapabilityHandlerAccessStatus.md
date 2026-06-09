# NTUserCapabilityHandler::AccessCheckResult(CapabilityHandlerAccessStatus)

- ea: `0x180010830`
- end: `0x180010965`
- name: `?AccessCheckResult@NTUserCapabilityHandler@@UEAAJW4CapabilityHandlerAccessStatus@@@Z`
- size: `309`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x1800102b8`
- `0x180010830`
- `0x18001096c`
- `0x180010be0`
- `0x180010d10`
- `0x180010d60`
- `0x180011360`
- `0x180013634`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800108e5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800108e5`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001089b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001089b`

## pseudocode

```c
__int64 __fastcall NTUserCapabilityHandler::AccessCheckResult(__int64 a1, int a2)
{
  const wchar_t *v2; // rdi
  const wchar_t *v5; // rcx
  NTUserCapabilityHandler *v6; // rcx
  const unsigned __int16 *v7; // rdx
  HANDLE v8; // rbx
  unsigned int v10; // ebx
  bool v11; // cc
  HANDLE v12; // [rsp+20h] [rbp-20h] BYREF
  __int128 v13; // [rsp+28h] [rbp-18h]
  void *TokenHandle; // [rsp+60h] [rbp+20h] BYREF
  HANDLE v15; // [rsp+70h] [rbp+30h] BYREF

  v2 = (const wchar_t *)(a1 + 32);
  if ( *(_QWORD *)(a1 + 56) <= 7u )
    v5 = (const wchar_t *)(a1 + 32);
  else
    v5 = *(const wchar_t **)v2;
  if ( !wcscmp_0(v5, L"graphicsCaptureProgrammatic") )
    return 0;
  if ( gHandlingAccessChanged )
  {
    v7 = *((_QWORD *)v2 + 3) <= 7u ? v2 : *(const unsigned __int16 **)v2;
    if ( !NTUserCapabilityHandler::IsCapabilityRelevantToNTUser(v6, v7) )
      return 0;
  }
  v8 = OpenProcess(0x1208u, 0, *(_DWORD *)(a1 + 24));
  v15 = v8;
  if ( (((unsigned __int64)v8 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    TokenHandle = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &TokenHandle,
      0);
    if ( OpenProcessToken(v8, 8u, &TokenHandle) )
    {
      if ( NTUserCapabilityHandler::ShouldApplyNTuserCapabilitiesChecks(TokenHandle) )
      {
        v12 = v8;
        v11 = *((_QWORD *)v2 + 3) <= 7u;
        v13 = 0;
        if ( !v11 )
          v2 = *(const wchar_t **)v2;
        SetNTUserCapabilityBitForString((struct tagPROCESS_WIN32_CAPABILITIES *)&v12, v2, a2 == 1);
        v10 = CallSetProcessWin32Capabilities((struct tagPROCESS_WIN32_CAPABILITIES *)&v12, 1u);
      }
      else
      {
        v10 = 0;
      }
    }
    else
    {
      v10 = -2147418113;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v15);
    return v10;
  }
  else
  {
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v15);
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x180010830  mov     [rsp-18h+arg_8], rbx
0x180010835  push    rbp
0x180010836  push    rsi
0x180010837  push    rdi
0x180010838  mov     rbp, rsp
0x18001083b  sub     rsp, 40h
0x18001083f  lea     rdi, [rcx+20h]
0x180010843  mov     esi, edx
0x180010845  cmp     qword ptr [rdi+18h], 7
0x18001084a  mov     rbx, rcx
0x18001084d  jbe     short loc_180010854
0x18001084f  mov     rcx, [rdi]
0x180010852  jmp     short loc_180010857
0x180010854  mov     rcx, rdi; String1
0x180010857  lea     rdx, aGraphicscaptur; "graphicsCaptureProgrammatic"
0x18001085e  call    wcscmp_0
0x180010863  test    eax, eax
0x180010865  jz      loc_180010956
0x18001086b  cmp     cs:?gHandlingAccessChanged@@3_NA, 0; bool gHandlingAccessChanged
0x180010872  jz      short loc_180010890
0x180010874  cmp     qword ptr [rdi+18h], 7
0x180010879  jbe     short loc_180010880
0x18001087b  mov     rdx, [rdi]
0x18001087e  jmp     short loc_180010883
0x180010880  mov     rdx, rdi; unsigned __int16 *
0x180010883  call    ?IsCapabilityRelevantToNTUser@NTUserCapabilityHandler@@AEBA_NPEBG@Z; NTUserCapabilityHandler::IsCapabilityRelevantToNTUser(ushort const *)
0x180010888  test    al, al
0x18001088a  jz      loc_180010956
0x180010890  mov     r8d, [rbx+18h]; dwProcessId
0x180010894  xor     edx, edx; bInheritHandle
0x180010896  mov     ecx, 1208h; dwDesiredAccess
0x18001089b  call    cs:__imp_OpenProcess
0x1800108a1  mov     rbx, rax
0x1800108a4  mov     [rbp+arg_10], rax
0x1800108a8  inc     rax
0x1800108ab  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800108b1  jnz     short loc_1800108C6
0x1800108b3  lea     rcx, [rbp+arg_10]
0x1800108b7  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800108bc  mov     eax, 8000FFFFh
0x1800108c1  jmp     loc_180010958
0x1800108c6  xor     edx, edx
0x1800108c8  mov     [rbp+TokenHandle], 0
0x1800108d0  lea     rcx, [rbp+TokenHandle]
0x1800108d4  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800108d9  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800108dd  mov     edx, 8; DesiredAccess
0x1800108e2  mov     rcx, rbx; ProcessHandle
0x1800108e5  call    cs:__imp_OpenProcessToken
0x1800108eb  test    eax, eax
0x1800108ed  jnz     short loc_1800108F6
0x1800108ef  mov     ebx, 8000FFFFh
0x1800108f4  jmp     short loc_180010940
0x1800108f6  mov     rcx, [rbp+TokenHandle]; void *
0x1800108fa  call    ?ShouldApplyNTuserCapabilitiesChecks@NTUserCapabilityHandler@@CA_NPEAX@Z; NTUserCapabilityHandler::ShouldApplyNTuserCapabilitiesChecks(void *)
0x1800108ff  test    al, al
0x180010901  jnz     short loc_180010907
0x180010903  xor     ebx, ebx
0x180010905  jmp     short loc_180010940
0x180010907  cmp     esi, 1
0x18001090a  mov     [rbp+var_20], rbx
0x18001090e  xorps   xmm0, xmm0
0x180010911  setz    r8b; bool
0x180010915  cmp     qword ptr [rdi+18h], 7
0x18001091a  movdqu  [rbp+var_18], xmm0
0x18001091f  jbe     short loc_180010924
0x180010921  mov     rdi, [rdi]
0x180010924  mov     rdx, rdi; unsigned __int16 *
0x180010927  lea     rcx, [rbp+var_20]; struct tagPROCESS_WIN32_CAPABILITIES *
0x18001092b  call    ?SetNTUserCapabilityBitForString@@YAXPEAUtagPROCESS_WIN32_CAPABILITIES@@PEBG_N@Z; SetNTUserCapabilityBitForString(tagPROCESS_WIN32_CAPABILITIES *,ushort const *,bool)
0x180010930  mov     edx, 1; unsigned int
0x180010935  lea     rcx, [rbp+var_20]; struct tagPROCESS_WIN32_CAPABILITIES *
0x180010939  call    ?CallSetProcessWin32Capabilities@@YAJPEAUtagPROCESS_WIN32_CAPABILITIES@@K@Z; CallSetProcessWin32Capabilities(tagPROCESS_WIN32_CAPABILITIES *,ulong)
0x18001093e  mov     ebx, eax
0x180010940  lea     rcx, [rbp+TokenHandle]
0x180010944  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180010949  lea     rcx, [rbp+arg_10]
0x18001094d  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180010952  mov     eax, ebx
0x180010954  jmp     short loc_180010958
0x180010956  xor     eax, eax
0x180010958  mov     rbx, [rsp+40h+arg_8]
0x18001095d  add     rsp, 40h
0x180010961  pop     rdi
0x180010962  pop     rsi
0x180010963  pop     rbp
0x180010964  retn
```
