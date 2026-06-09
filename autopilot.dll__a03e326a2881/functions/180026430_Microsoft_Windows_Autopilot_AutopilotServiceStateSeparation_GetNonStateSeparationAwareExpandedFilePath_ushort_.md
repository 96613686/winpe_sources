# Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetNonStateSeparationAwareExpandedFilePath(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180026430`
- end: `0x180026615`
- name: `?GetNonStateSeparationAwareExpandedFilePath@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `485`
- prototype: `__int64 __fastcall(LPCWSTR lpSrc, __int128 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180026794`

## callees

- `0x1800045b0`
- `0x180005374`
- `0x1800105d4`
- `0x1800105f4`
- `0x180013a40`
- `0x1800174f0`
- `0x180026430`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180026472`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180026472`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180026461`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180026461`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800264a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002650c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026551`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800265e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800264a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002650c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026551`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800265e1`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x1800264d8`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x1800264d8`

## string_xrefs

- `0x180026484`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateseparation.cpp`
- `0x1800264ea`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateseparation.cpp`
- `0x180026530`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateseparation.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
        std::wstring::_Construct<1,unsigned short const *>(&v13, Dest, v11);
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
0x180026430  mov     [rsp+arg_10], rbx
0x180026435  mov     [rsp+arg_18], rsi
0x18002643a  push    rdi
0x18002643b  sub     rsp, 270h
0x180026442  mov     rax, cs:__security_cookie
0x180026449  xor     rax, rsp
0x18002644c  mov     [rsp+278h+var_18], rax
0x180026454  mov     rbx, rdx
0x180026457  mov     rdi, rcx
0x18002645a  xor     esi, esi
0x18002645c  mov     [rsp+278h+TokenHandle], rsi; int
0x180026461  call    cs:__imp_GetCurrentProcess
0x180026467  lea     r8, [rsp+278h+TokenHandle]; TokenHandle
0x18002646c  lea     edx, [rsi+0Eh]; DesiredAccess
0x18002646f  mov     rcx, rax; ProcessHandle
0x180026472  call    cs:__imp_OpenProcessToken
0x180026478  test    eax, eax
0x18002647a  jnz     short loc_1800264B3
0x18002647c  mov     rcx, [rsp+278h]; this
0x180026484  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002648b  mov     edx, 0BBh; void *
0x180026490  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180026495  mov     ebx, eax
0x180026497  mov     rcx, [rsp+278h+TokenHandle]; hObject
0x18002649c  lea     rdx, [rcx-1]
0x1800264a0  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800264a4  ja      short loc_1800264AC
0x1800264a6  call    cs:__imp_CloseHandle
0x1800264ac  mov     eax, ebx
0x1800264ae  jmp     loc_1800265EF
0x1800264b3  xor     edx, edx; Val
0x1800264b5  mov     r8d, 208h; Size
0x1800264bb  lea     rcx, [rsp+278h+Dest]; void *
0x1800264c0  call    memset_0
0x1800264c5  mov     r9d, 104h; dwSize
0x1800264cb  lea     r8, [rsp+278h+Dest]; lpDest
0x1800264d0  mov     rdx, rdi; lpSrc
0x1800264d3  mov     rcx, [rsp+278h+TokenHandle]; hToken
0x1800264d8  call    cs:__imp_ExpandEnvironmentStringsForUserW
0x1800264de  test    eax, eax
0x1800264e0  jnz     short loc_180026519
0x1800264e2  mov     rcx, [rsp+278h]; this
0x1800264ea  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800264f1  mov     edx, 0BFh; void *
0x1800264f6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800264fb  mov     ebx, eax
0x1800264fd  mov     rcx, [rsp+278h+TokenHandle]; hObject
0x180026502  lea     rdx, [rcx-1]
0x180026506  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002650a  ja      short loc_180026512
0x18002650c  call    cs:__imp_CloseHandle
0x180026512  mov     eax, ebx
0x180026514  jmp     loc_1800265EF
0x180026519  cmp     eax, 104h
0x18002651e  jbe     short loc_18002655E
0x180026520  mov     rcx, [rsp+278h]; this
0x180026528  mov     ebx, 8007007Ah
0x18002652d  mov     r9d, ebx; char *
0x180026530  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\moderndeployment\\au"...
0x180026537  mov     edx, 0C0h; void *
0x18002653c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026541  nop
0x180026542  mov     rcx, [rsp+278h+TokenHandle]; hObject
0x180026547  lea     rdx, [rcx-1]
0x18002654b  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002654f  ja      short loc_180026557
0x180026551  call    cs:__imp_CloseHandle
0x180026557  mov     eax, ebx
0x180026559  jmp     loc_1800265EF
0x18002655e  xorps   xmm0, xmm0
0x180026561  movups  [rsp+278h+var_250], xmm0
0x180026566  xorps   xmm1, xmm1
0x180026569  movdqu  [rsp+278h+var_240], xmm1
0x18002656f  lea     rax, [rsp+278h+Dest]
0x180026574  or      r8, 0FFFFFFFFFFFFFFFFh
0x180026578  inc     r8
0x18002657b  cmp     [rax+r8*2], si
0x180026580  jnz     short loc_180026578
0x180026582  lea     rdx, [rsp+278h+Dest]
0x180026587  lea     rcx, [rsp+278h+var_250]
0x18002658c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180026591  lea     rax, [rsp+278h+var_250]
0x180026596  cmp     rbx, rax
0x180026599  jz      short loc_1800265C7
0x18002659b  mov     rcx, rbx
0x18002659e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800265a3  movups  xmm0, [rsp+278h+var_250]
0x1800265a8  movups  xmmword ptr [rbx], xmm0
0x1800265ab  movups  xmm1, [rsp+278h+var_240]
0x1800265b0  movups  xmmword ptr [rbx+10h], xmm1
0x1800265b4  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800265bc  movdqu  [rsp+278h+var_240], xmm0
0x1800265c2  mov     word ptr [rsp+278h+var_250], si
0x1800265c7  lea     rcx, [rsp+278h+var_250]
0x1800265cc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800265d1  nop
0x1800265d2  mov     rcx, [rsp+278h+TokenHandle]; hObject
0x1800265d7  lea     rax, [rcx-1]
0x1800265db  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800265df  ja      short loc_1800265E7
0x1800265e1  call    cs:__imp_CloseHandle
0x1800265e7  xor     eax, eax
0x1800265e9  jmp     short loc_1800265EF
0x1800265eb  mov     eax, dword ptr [rsp+278h+TokenHandle]
0x1800265ef  mov     rcx, [rsp+278h+var_18]
0x1800265f7  xor     rcx, rsp; StackCookie
0x1800265fa  call    __security_check_cookie
0x1800265ff  lea     r11, [rsp+278h+var_8]
0x180026607  mov     rbx, [r11+20h]
0x18002660b  mov     rsi, [r11+28h]
0x18002660f  mov     rsp, r11
0x180026612  pop     rdi
0x180026613  retn
```
