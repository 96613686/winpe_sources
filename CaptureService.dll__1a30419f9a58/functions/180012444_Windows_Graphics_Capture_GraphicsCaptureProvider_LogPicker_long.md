# Windows::Graphics::Capture::GraphicsCaptureProvider::LogPicker(long)

- ea: `0x180012444`
- end: `0x1800125cc`
- name: `?LogPicker@GraphicsCaptureProvider@Capture@Graphics@Windows@@SAXJ@Z`
- size: `392`
- prototype: `void __fastcall(int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180012f30`

## callees

- `0x180002e60`
- `0x180003bc8`
- `0x18000c858`
- `0x18000dec8`
- `0x18000f0d8`
- `0x180012444`
- `0x180017da0`
- `0x180017dc0`
- `0x18001892c`
- `0x18001f160`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800124f4`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800124f4`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180012577`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180012577`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180012523`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180012523`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800124af`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800124af`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001253c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001253c`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x18001255d`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x18001255d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800124e3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800124e3`

## string_xrefs

- `0x180012509`: `onecoreuap\windows\dwm\capture\svc\dll\CaptureTraceLogging.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Windows::Graphics::Capture::GraphicsCaptureProvider::LogPicker(int a1)
{
  HRESULT v2; // eax
  HANDLE CurrentThread; // rax
  unsigned int ApplicationUserModelIdFromToken; // eax
  void *v5; // rdx
  unsigned int v6; // r8d
  unsigned int ReturnLength; // [rsp+20h] [rbp-168h]
  int TokenInformation; // [rsp+30h] [rbp-158h] BYREF
  int v9; // [rsp+38h] [rbp-150h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-148h] BYREF
  DWORD v11; // [rsp+48h] [rbp-140h] BYREF
  UINT32 applicationUserModelIdLength; // [rsp+4Ch] [rbp-13Ch] BYREF
  HANDLE ProcessHandle; // [rsp+50h] [rbp-138h] BYREF
  HANDLE token; // [rsp+58h] [rbp-130h] BYREF
  WCHAR applicationUserModelId[136]; // [rsp+60h] [rbp-128h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  v9 = a1;
  memset_0(applicationUserModelId, 0, 0x104u);
  ProcessHandle = 0;
  try
  {
    Windows::Graphics::Capture::Server::GetClientProcessHandle();
    TokenHandle = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &TokenHandle,
      0);
    OpenProcessToken(ProcessHandle, 0x18u, &TokenHandle);
    TokenInformation = 0;
    v11 = 0;
    GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &v11);
    if ( TokenInformation )
    {
      v2 = CoImpersonateClient();
      if ( v2 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x6B,
          (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\CaptureTraceLogging.h",
          (const char *)(unsigned int)v2,
          ReturnLength);
      token = 0;
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 0x2000Cu, 1, &token) )
      {
        applicationUserModelIdLength = 130;
        ApplicationUserModelIdFromToken = GetApplicationUserModelIdFromToken(
                                            token,
                                            &applicationUserModelIdLength,
                                            applicationUserModelId);
        if ( ApplicationUserModelIdFromToken )
          wil::details::in1diag3::_Throw_Win32(
            retaddr,
            v5,
            v6,
            (const char *)ApplicationUserModelIdFromToken,
            ReturnLength);
      }
      CoRevertToSelf();
      Windows::Graphics::Capture::GraphicsCaptureProvider::PickAsync<unsigned short (&)[130],long &>(
        applicationUserModelId,
        &v9);
    }
    else
    {
      Windows::Graphics::Capture::GraphicsCaptureProvider::CaptureFunctionWin32(2, a1);
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ProcessHandle);
  }
  catch ( ... )
  {
    CoRevertToSelf();
    Windows::Graphics::Capture::GraphicsCaptureProvider::PickAsync<unsigned short (&)[130],long &>(
      applicationUserModelId,
      &v9);
  }
}

```

## disassembly

```asm
0x180012444  push    rbx
0x180012446  sub     rsp, 180h
0x18001244d  mov     rax, cs:__security_cookie
0x180012454  xor     rax, rsp
0x180012457  mov     [rsp+188h+var_18], rax
0x18001245f  mov     ebx, ecx
0x180012461  mov     [rsp+188h+var_150], ecx
0x180012465  xor     edx, edx; Val
0x180012467  mov     r8d, 104h; Size
0x18001246d  lea     rcx, [rsp+188h+applicationUserModelId]; void *
0x180012472  call    memset_0
0x180012477  nop
0x180012478  mov     [rsp+188h+ProcessHandle], 0
0x180012481  lea     rcx, [rsp+188h+ProcessHandle]
0x180012486  call    ?GetClientProcessHandle@Server@Capture@Graphics@Windows@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; Windows::Graphics::Capture::Server::GetClientProcessHandle(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)
0x18001248b  mov     [rsp+188h+TokenHandle], 0
0x180012494  xor     edx, edx
0x180012496  lea     rcx, [rsp+188h+TokenHandle]
0x18001249b  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800124a0  lea     r8, [rsp+188h+TokenHandle]; TokenHandle
0x1800124a5  mov     edx, 18h; DesiredAccess
0x1800124aa  mov     rcx, [rsp+188h+ProcessHandle]; ProcessHandle
0x1800124af  call    cs:__imp_OpenProcessToken
0x1800124b5  mov     [rsp+188h+TokenInformation], 0
0x1800124bd  mov     [rsp+188h+var_140], 0
0x1800124c5  lea     rax, [rsp+188h+var_140]
0x1800124ca  mov     qword ptr [rsp+188h+ReturnLength], rax; unsigned int
0x1800124cf  mov     r9d, 4; TokenInformationLength
0x1800124d5  lea     r8, [rsp+188h+TokenInformation]; TokenInformation
0x1800124da  lea     edx, [r9+19h]; TokenInformationClass
0x1800124de  mov     rcx, [rsp+188h+TokenHandle]; TokenHandle
0x1800124e3  call    cs:__imp_GetTokenInformation
0x1800124e9  cmp     [rsp+188h+TokenInformation], 0
0x1800124ee  jz      loc_18001258E
0x1800124f4  call    cs:__imp_CoImpersonateClient
0x1800124fa  mov     rcx, [rsp+188h]; this
0x180012502  test    eax, eax
0x180012504  jns     short loc_18001251A
0x180012506  mov     r9d, eax; char *
0x180012509  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x180012510  mov     edx, 6Bh ; 'k'; void *
0x180012515  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001251a  mov     [rsp+188h+token], 0
0x180012523  call    cs:__imp_GetCurrentThread
0x180012529  mov     rcx, rax; ThreadHandle
0x18001252c  lea     r9, [rsp+188h+token]; TokenHandle
0x180012531  mov     edx, 2000Ch; DesiredAccess
0x180012536  mov     r8d, 1; OpenAsSelf
0x18001253c  call    cs:__imp_OpenThreadToken
0x180012542  test    eax, eax
0x180012544  jz      short loc_180012577
0x180012546  mov     [rsp+188h+applicationUserModelIdLength], 82h
0x18001254e  lea     r8, [rsp+188h+applicationUserModelId]; applicationUserModelId
0x180012553  lea     rdx, [rsp+188h+applicationUserModelIdLength]; applicationUserModelIdLength
0x180012558  mov     rcx, [rsp+188h+token]; token
0x18001255d  call    cs:__imp_GetApplicationUserModelIdFromToken
0x180012563  mov     rcx, [rsp+188h]; this
0x18001256b  test    eax, eax
0x18001256d  jz      short loc_180012577
0x18001256f  mov     r9d, eax; char *
0x180012572  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180012577  call    cs:__imp_CoRevertToSelf
0x18001257d  lea     rdx, [rsp+188h+var_150]
0x180012582  lea     rcx, [rsp+188h+applicationUserModelId]
0x180012587  call    ??$PickAsync@AEAY0IC@GAEAJ@GraphicsCaptureProvider@Capture@Graphics@Windows@@SAXAEAY0IC@GAEAJ@Z; Windows::Graphics::Capture::GraphicsCaptureProvider::PickAsync<ushort (&)[130],long &>(ushort (&)[130],long &)
0x18001258c  jmp     short loc_18001259B
0x18001258e  mov     edx, ebx; int
0x180012590  mov     ecx, 2; unsigned int
0x180012595  call    ?CaptureFunctionWin32@GraphicsCaptureProvider@Capture@Graphics@Windows@@SAXIJ@Z; Windows::Graphics::Capture::GraphicsCaptureProvider::CaptureFunctionWin32(uint,long)
0x18001259a  nop
0x18001259b  lea     rcx, [rsp+188h+TokenHandle]
0x1800125a0  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800125a5  nop
0x1800125a6  lea     rcx, [rsp+188h+ProcessHandle]
0x1800125ab  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800125b0  nop
0x1800125b1  jmp     short $+2
0x1800125b3  mov     rcx, [rsp+188h+var_18]
0x1800125bb  xor     rcx, rsp; StackCookie
0x1800125be  call    __security_check_cookie
0x1800125c3  add     rsp, 180h
0x1800125ca  pop     rbx
0x1800125cb  retn
```
