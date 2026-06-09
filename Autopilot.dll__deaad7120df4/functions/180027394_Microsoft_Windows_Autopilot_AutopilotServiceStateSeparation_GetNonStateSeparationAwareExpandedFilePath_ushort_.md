# Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetNonStateSeparationAwareExpandedFilePath(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180027394`
- end: `0x1800275a3`
- name: `?GetNonStateSeparationAwareExpandedFilePath@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `527`
- prototype: `__int64 __fastcall(LPCWSTR lpSrc, __int128 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180027724`

## callees

- `0x1800045d0`
- `0x1800053c4`
- `0x180010744`
- `0x180010764`
- `0x180013de4`
- `0x180017a20`
- `0x180027394`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800273dc`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800273dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800273c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800273c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027416`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027488`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800274d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027569`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027416`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027488`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800274d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027569`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x18002744e`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x18002744e`

## string_xrefs

- `0x1800273f4`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateseparation.cpp`
- `0x180027466`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateseparation.cpp`
- `0x1800274b2`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateseparation.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetNonStateSeparationAwareExpandedFilePath(
        LPCWSTR lpSrc,
        __int128 *a2)
{
  HANDLE CurrentProcess; // rax
  const char *v5; // r9
  unsigned int v6; // ebx
  unsigned int v8; // eax
  const char *v9; // r9
  unsigned int LastError; // ebx
  __int64 v11; // r8
  void *TokenHandle; // [rsp+20h] [rbp-258h] BYREF
  __int128 v13; // [rsp+28h] [rbp-250h] BYREF
  __m128i si128; // [rsp+38h] [rbp-240h]
  WCHAR Dest[264]; // [rsp+50h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0xEu, &TokenHandle) )
  {
    memset_0(Dest, 0, 0x208u);
    v8 = ExpandEnvironmentStringsForUserW(TokenHandle, lpSrc, Dest, 0x104u);
    if ( v8 )
    {
      if ( v8 <= 0x104 )
      {
        v13 = 0;
        si128 = 0;
        v11 = -1;
        do
          ++v11;
        while ( Dest[v11] );
        std::wstring::_Construct<1,unsigned short const *>(&v13, Dest);
        if ( a2 != &v13 )
        {
          std::wstring::_Tidy_deallocate(a2);
          *a2 = v13;
          a2[1] = (__int128)si128;
          si128 = _mm_load_si128((const __m128i *)&_xmm);
          LOWORD(v13) = 0;
        }
        std::wstring::_Tidy_deallocate(&v13);
        if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(TokenHandle);
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC0,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateseparation.cpp",
          (const char *)0x8007007ALL,
          (int)TokenHandle);
        if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(TokenHandle);
        return 2147942522LL;
      }
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xBF,
                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateseparation.cpp",
                    v9);
      if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(TokenHandle);
      return LastError;
    }
  }
  else
  {
    v6 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0xBB,
           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateseparation.cpp",
           v5);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    return v6;
  }
}

```

## disassembly

```asm
0x180027394  mov     [rsp+arg_10], rbx
0x180027399  mov     [rsp+arg_18], rsi
0x18002739e  push    rdi
0x18002739f  sub     rsp, 270h
0x1800273a6  mov     rax, cs:__security_cookie
0x1800273ad  xor     rax, rsp
0x1800273b0  mov     [rsp+278h+var_18], rax
0x1800273b8  mov     rbx, rdx
0x1800273bb  mov     rdi, rcx
0x1800273be  xor     esi, esi
0x1800273c0  mov     [rsp+278h+TokenHandle], rsi; int
0x1800273c5  call    cs:__imp_GetCurrentProcess
0x1800273cc  nop     dword ptr [rax+rax+00h]
0x1800273d1  lea     r8, [rsp+278h+TokenHandle]; TokenHandle
0x1800273d6  lea     edx, [rsi+0Eh]; DesiredAccess
0x1800273d9  mov     rcx, rax; ProcessHandle
0x1800273dc  call    cs:__imp_OpenProcessToken
0x1800273e3  nop     dword ptr [rax+rax+00h]
0x1800273e8  test    eax, eax
0x1800273ea  jnz     short loc_180027429
0x1800273ec  mov     rcx, [rsp+278h]; this
0x1800273f4  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800273fb  mov     edx, 0BBh; void *
0x180027400  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180027405  mov     ebx, eax
0x180027407  mov     rcx, [rsp+278h+TokenHandle]; hObject
0x18002740c  lea     rdx, [rcx-1]
0x180027410  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180027414  ja      short loc_180027422
0x180027416  call    cs:__imp_CloseHandle
0x18002741d  nop     dword ptr [rax+rax+00h]
0x180027422  mov     eax, ebx
0x180027424  jmp     loc_18002757D
0x180027429  xor     edx, edx; Val
0x18002742b  mov     r8d, 208h; Size
0x180027431  lea     rcx, [rsp+278h+Dest]; void *
0x180027436  call    memset_0
0x18002743b  mov     r9d, 104h; dwSize
0x180027441  lea     r8, [rsp+278h+Dest]; lpDest
0x180027446  mov     rdx, rdi; lpSrc
0x180027449  mov     rcx, [rsp+278h+TokenHandle]; hToken
0x18002744e  call    cs:__imp_ExpandEnvironmentStringsForUserW
0x180027455  nop     dword ptr [rax+rax+00h]
0x18002745a  test    eax, eax
0x18002745c  jnz     short loc_18002749B
0x18002745e  mov     rcx, [rsp+278h]; this
0x180027466  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002746d  mov     edx, 0BFh; void *
0x180027472  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180027477  mov     ebx, eax
0x180027479  mov     rcx, [rsp+278h+TokenHandle]; hObject
0x18002747e  lea     rdx, [rcx-1]
0x180027482  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180027486  ja      short loc_180027494
0x180027488  call    cs:__imp_CloseHandle
0x18002748f  nop     dword ptr [rax+rax+00h]
0x180027494  mov     eax, ebx
0x180027496  jmp     loc_18002757D
0x18002749b  cmp     eax, 104h
0x1800274a0  jbe     short loc_1800274E6
0x1800274a2  mov     rcx, [rsp+278h]; this
0x1800274aa  mov     ebx, 8007007Ah
0x1800274af  mov     r9d, ebx; char *
0x1800274b2  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800274b9  mov     edx, 0C0h; void *
0x1800274be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800274c3  nop
0x1800274c4  mov     rcx, [rsp+278h+TokenHandle]; hObject
0x1800274c9  lea     rdx, [rcx-1]
0x1800274cd  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800274d1  ja      short loc_1800274DF
0x1800274d3  call    cs:__imp_CloseHandle
0x1800274da  nop     dword ptr [rax+rax+00h]
0x1800274df  mov     eax, ebx
0x1800274e1  jmp     loc_18002757D
0x1800274e6  xorps   xmm0, xmm0
0x1800274e9  movups  [rsp+278h+var_250], xmm0
0x1800274ee  xorps   xmm1, xmm1
0x1800274f1  movdqu  [rsp+278h+var_240], xmm1
0x1800274f7  lea     rax, [rsp+278h+Dest]
0x1800274fc  or      r8, 0FFFFFFFFFFFFFFFFh
0x180027500  inc     r8
0x180027503  cmp     [rax+r8*2], si
0x180027508  jnz     short loc_180027500
0x18002750a  lea     rdx, [rsp+278h+Dest]
0x18002750f  lea     rcx, [rsp+278h+var_250]
0x180027514  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180027519  lea     rax, [rsp+278h+var_250]
0x18002751e  cmp     rbx, rax
0x180027521  jz      short loc_18002754F
0x180027523  mov     rcx, rbx
0x180027526  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002752b  movups  xmm0, [rsp+278h+var_250]
0x180027530  movups  xmmword ptr [rbx], xmm0
0x180027533  movups  xmm1, [rsp+278h+var_240]
0x180027538  movups  xmmword ptr [rbx+10h], xmm1
0x18002753c  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180027544  movdqu  [rsp+278h+var_240], xmm0
0x18002754a  mov     word ptr [rsp+278h+var_250], si
0x18002754f  lea     rcx, [rsp+278h+var_250]
0x180027554  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180027559  nop
0x18002755a  mov     rcx, [rsp+278h+TokenHandle]; hObject
0x18002755f  lea     rax, [rcx-1]
0x180027563  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180027567  ja      short loc_180027575
0x180027569  call    cs:__imp_CloseHandle
0x180027570  nop     dword ptr [rax+rax+00h]
0x180027575  xor     eax, eax
0x180027577  jmp     short loc_18002757D
0x180027579  mov     eax, dword ptr [rsp+278h+TokenHandle]
0x18002757d  mov     rcx, [rsp+278h+var_18]
0x180027585  xor     rcx, rsp; StackCookie
0x180027588  call    __security_check_cookie
0x18002758d  lea     r11, [rsp+278h+var_8]
0x180027595  mov     rbx, [r11+20h]
0x180027599  mov     rsi, [r11+28h]
0x18002759d  mov     rsp, r11
0x1800275a0  pop     rdi
0x1800275a1  retn
```
