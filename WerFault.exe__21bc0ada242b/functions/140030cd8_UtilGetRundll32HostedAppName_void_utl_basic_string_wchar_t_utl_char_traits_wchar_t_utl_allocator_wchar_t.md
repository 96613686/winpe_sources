# UtilGetRundll32HostedAppName(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x140030cd8`
- end: `0x1400312e1`
- name: `?UtilGetRundll32HostedAppName@@YAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `1545`
- prototype: `__int64 __fastcall(HANDLE hProcess)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x14001bdbc`

## callees

- `0x140002470`
- `0x140002728`
- `0x14000b408`
- `0x14000c8a0`
- `0x140010cdc`
- `0x1400112cc`
- `0x14001183c`
- `0x14001444c`
- `0x140014474`
- `0x140030cd8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x140030ed8`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1400310f3`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x140030ed8`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1400310f3`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x140030e93`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x140030ee9`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x140030e93`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x140030ee9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031186`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031186`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x140031003`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x140031003`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140030eff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140030eff`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x140030f10`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x140030f10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003120c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003120c`
- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x140030dc8`
- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x140030dc8`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall UtilGetRundll32HostedAppName(HANDLE hProcess, __int64 a2)
{
  LPWSTR *v4; // r15
  _WORD *v5; // rcx
  _WORD *v6; // r8
  unsigned int ProcessCommandLine; // ebx
  CUserModeHangReport *v8; // rcx
  __int64 v9; // rdx
  CUserModeHangReport *v10; // rcx
  __int64 v11; // rdx
  int i; // edx
  const wchar_t *v13; // rsi
  wchar_t *v14; // rax
  wchar_t *v15; // r14
  HANDLE CurrentProcess; // rax
  signed int WindowsDirectory; // eax
  __int64 v18; // r9
  int v19; // ebx
  const WCHAR *v20; // r12
  DWORD v21; // eax
  __int64 v22; // rax
  __int64 v23; // rdx
  WCHAR *v24; // r8
  wchar_t v25; // cx
  WCHAR *v26; // rcx
  unsigned __int64 v27; // r8
  signed int LastError; // eax
  unsigned __int16 v30[2]; // [rsp+30h] [rbp-D0h] BYREF
  int pNumArgs; // [rsp+34h] [rbp-CCh] BYREF
  void *v32[2]; // [rsp+38h] [rbp-C8h] BYREF
  _WORD v33[8]; // [rsp+48h] [rbp-B8h] BYREF
  void *v34[2]; // [rsp+58h] [rbp-A8h] BYREF
  _WORD v35[8]; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpCmdLine[2]; // [rsp+78h] [rbp-88h] BYREF
  _WORD v37[8]; // [rsp+88h] [rbp-78h] BYREF
  LPCWSTR lpPath[3]; // [rsp+98h] [rbp-68h]
  WCHAR Buffer[264]; // [rsp+B0h] [rbp-50h] BYREF

  lpCmdLine[0] = v37;
  lpCmdLine[1] = v37;
  v37[0] = 0;
  v4 = 0;
  pNumArgs = 0;
  v30[0] = 0;
  v5 = v33;
  v32[0] = v33;
  v32[1] = v33;
  v33[0] = 0;
  v6 = v35;
  v34[0] = v35;
  v34[1] = v35;
  v35[0] = 0;
  if ( hProcess && a2 )
  {
    Buffer[0] = 0;
    ProcessCommandLine = UtilGetProcessCommandLine(hProcess, (__int64)lpCmdLine);
    if ( (ProcessCommandLine & 0x80000000) != 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_79;
      }
      v9 = 64;
      goto LABEL_77;
    }
    v4 = CommandLineToArgvW(lpCmdLine[0], &pNumArgs);
    lpPath[0] = (LPCWSTR)v4;
    if ( v4 )
    {
      if ( pNumArgs < 2 )
      {
        ProcessCommandLine = -2147467259;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_79;
        }
        v11 = 66;
        goto LABEL_12;
      }
      for ( i = 1; i < pNumArgs; ++i )
      {
        if ( ((*v4[i] - 45) & 0xFFFD) != 0 )
          break;
      }
      if ( i == pNumArgs )
      {
        ProcessCommandLine = -2147467259;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_79;
        }
        v11 = 67;
        goto LABEL_12;
      }
      v13 = v4[i];
      v14 = wcschr(v13, 0x2Cu);
      if ( !v14 )
      {
        ProcessCommandLine = -2147467259;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_79;
        }
        v11 = 68;
LABEL_12:
        WPP_SF_(*((_QWORD *)v10 + 2), v11, WPP_5958ded8188d3319535ef35cd392335c_Traceguids);
        goto LABEL_79;
      }
      *v14 = 0;
      v15 = wcsrchr(v13, 0x2Eu);
      if ( !wcschr(v13, 0x5Cu) )
      {
        CurrentProcess = GetCurrentProcess();
        if ( !(unsigned int)IsWow64Process2(CurrentProcess, v30, 0) )
        {
          if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              69,
              WPP_5958ded8188d3319535ef35cd392335c_Traceguids,
              ProcessCommandLine);
          }
          v30[0] = 0;
        }
        WindowsDirectory = UtilGetWindowsDirectory(v32);
        ProcessCommandLine = WindowsDirectory;
        if ( WindowsDirectory < 0 )
        {
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_79;
          }
          v9 = 70;
          goto LABEL_34;
        }
        WindowsDirectory = UtilGetSystemDirectory2((__int64)v34, v30[0]);
        ProcessCommandLine = WindowsDirectory;
        if ( WindowsDirectory >= 0 )
        {
          lpPath[0] = (LPCWSTR)v32[0];
          lpPath[1] = (LPCWSTR)v34[0];
          v19 = 0;
          v20 = L".dll";
          if ( v15 )
            v20 = 0;
          while ( 1 )
          {
            v21 = SearchPathW(lpPath[v19], v13, v20, 0x104u, Buffer, 0);
            if ( v21 > 0x104 )
              break;
            if ( v21 )
              goto LABEL_60;
            if ( (unsigned int)++v19 >= 2 )
            {
              ProcessCommandLine = -2147024894;
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v11 = 73;
                goto LABEL_12;
              }
              goto LABEL_79;
            }
          }
          ProcessCommandLine = -2147024774;
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v11 = 72;
            goto LABEL_12;
          }
          goto LABEL_79;
        }
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v9 = 71;
LABEL_34:
          v18 = (unsigned int)WindowsDirectory;
LABEL_78:
          WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_5958ded8188d3319535ef35cd392335c_Traceguids, v18);
          goto LABEL_79;
        }
        goto LABEL_79;
      }
      v22 = 2147483646;
      v23 = 260;
      v24 = Buffer;
      do
      {
        if ( !v22 )
          break;
        v25 = *v13;
        if ( !*v13 )
          break;
        ++v13;
        *v24++ = v25;
        --v22;
        --v23;
      }
      while ( v23 );
      ProcessCommandLine = v23 == 0 ? 0x8007007A : 0;
      v26 = v24 - 1;
      if ( v23 )
        v26 = v24;
      *v26 = 0;
      if ( v23 )
      {
LABEL_60:
        if ( !wcsrchr(Buffer, 0x2Eu) )
        {
          WindowsDirectory = StringCchCatW(Buffer, 0x104u, L".dll");
          ProcessCommandLine = WindowsDirectory;
          if ( WindowsDirectory < 0 )
          {
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_79;
            }
            v9 = 75;
            goto LABEL_34;
          }
        }
        v27 = -1;
        do
          ++v27;
        while ( Buffer[v27] );
        if ( !utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(a2, Buffer, v27) )
        {
          ProcessCommandLine = -2147024882;
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_79;
          }
          v9 = 76;
          v18 = 2147942414LL;
          goto LABEL_78;
        }
        ProcessCommandLine = 0;
LABEL_79:
        if ( v34[0] != v35 )
          operator delete(v34[0], (const struct std::nothrow_t *)&std::nothrow);
        if ( v32[0] != v33 )
          operator delete(v32[0], (const struct std::nothrow_t *)&std::nothrow);
        if ( v4 )
          LocalFree(v4);
        if ( lpCmdLine[0] != v37 )
          operator delete((void *)lpCmdLine[0], (const struct std::nothrow_t *)&std::nothrow);
        return ProcessCommandLine;
      }
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_79;
      }
      v9 = 74;
    }
    else
    {
      LastError = GetLastError();
      ProcessCommandLine = LastError;
      if ( LastError > 0 )
        ProcessCommandLine = (unsigned __int16)LastError | 0x80070000;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_79;
      }
      v9 = 65;
    }
LABEL_77:
    v18 = ProcessCommandLine;
    goto LABEL_78;
  }
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_5958ded8188d3319535ef35cd392335c_Traceguids);
    v5 = v32[0];
    v6 = v34[0];
  }
  if ( v6 != v35 )
  {
    operator delete(v6, (const struct std::nothrow_t *)&std::nothrow);
    v5 = v32[0];
  }
  if ( v5 != v33 )
    operator delete(v5, (const struct std::nothrow_t *)&std::nothrow);
  if ( lpCmdLine[0] != v37 )
    operator delete((void *)lpCmdLine[0], (const struct std::nothrow_t *)&std::nothrow);
  return 2147942487LL;
}

```

## disassembly

```asm
0x140030cd8  mov     [rsp-8+arg_10], rbx
0x140030cdd  push    rbp
0x140030cde  push    rsi
0x140030cdf  push    rdi
0x140030ce0  push    r12
0x140030ce2  push    r13
0x140030ce4  push    r14
0x140030ce6  push    r15
0x140030ce8  lea     rbp, [rsp-1D0h]
0x140030cf0  sub     rsp, 2D0h
0x140030cf7  mov     rax, cs:__security_cookie
0x140030cfe  xor     rax, rsp
0x140030d01  mov     [rbp+200h+var_40], rax
0x140030d08  mov     r13, rdx
0x140030d0b  mov     r9, rcx
0x140030d0e  lea     rax, [rbp+200h+var_278]
0x140030d12  mov     [rsp+300h+lpCmdLine], rax
0x140030d17  lea     rax, [rbp+200h+var_278]
0x140030d1b  mov     [rbp+200h+var_280], rax
0x140030d1f  xor     r12d, r12d
0x140030d22  mov     [rbp+200h+var_278], r12w
0x140030d27  mov     r15d, r12d
0x140030d2a  mov     [rsp+300h+pNumArgs], r12d
0x140030d2f  mov     [rsp+300h+var_2D0], r12w
0x140030d35  lea     rcx, [rsp+300h+var_2B8]
0x140030d3a  mov     [rsp+300h+var_2C8], rcx
0x140030d3f  lea     rax, [rsp+300h+var_2B8]
0x140030d44  mov     [rsp+300h+var_2C0], rax
0x140030d49  mov     [rsp+300h+var_2B8], r12w
0x140030d4f  lea     r8, [rsp+300h+var_298]
0x140030d54  mov     [rsp+300h+var_2A8], r8
0x140030d59  lea     rax, [rsp+300h+var_298]
0x140030d5e  mov     [rsp+300h+var_2A0], rax
0x140030d63  mov     [rsp+300h+var_298], r12w
0x140030d69  test    r9, r9
0x140030d6c  jz      loc_140031230
0x140030d72  test    rdx, rdx
0x140030d75  jz      loc_140031230
0x140030d7b  mov     [rbp+200h+Buffer], r12w
0x140030d80  lea     rdx, [rsp+300h+lpCmdLine]
0x140030d85  mov     rcx, r9; hProcess
0x140030d88  call    ?UtilGetProcessCommandLine@@YAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetProcessCommandLine(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x140030d8d  mov     ebx, eax
0x140030d8f  test    eax, eax
0x140030d91  jns     short loc_140030DBE
0x140030d93  lea     rdi, WPP_GLOBAL_Control
0x140030d9a  mov     rcx, cs:WPP_GLOBAL_Control
0x140030da1  cmp     rcx, rdi
0x140030da4  jz      loc_1400311CD
0x140030daa  test    byte ptr [rcx+1Ch], 1
0x140030dae  jz      loc_1400311CD
0x140030db4  lea     edx, [r12+40h]
0x140030db9  jmp     loc_1400311B9
0x140030dbe  lea     rdx, [rsp+300h+pNumArgs]; pNumArgs
0x140030dc3  mov     rcx, [rsp+300h+lpCmdLine]; lpCmdLine
0x140030dc8  call    cs:__imp_CommandLineToArgvW
0x140030dce  mov     r15, rax
0x140030dd1  mov     [rbp+200h+lpPath], rax
0x140030dd5  test    rax, rax
0x140030dd8  jz      loc_140031186
0x140030dde  mov     r8d, [rsp+300h+pNumArgs]
0x140030de3  cmp     r8d, 2
0x140030de7  jge     short loc_140030E29
0x140030de9  mov     ebx, 80004005h
0x140030dee  lea     rdi, WPP_GLOBAL_Control
0x140030df5  mov     rcx, cs:WPP_GLOBAL_Control
0x140030dfc  cmp     rcx, rdi
0x140030dff  jz      loc_1400311CD
0x140030e05  test    byte ptr [rcx+1Ch], 1
0x140030e09  jz      loc_1400311CD
0x140030e0f  mov     edx, 42h ; 'B'
0x140030e14  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x140030e1b  mov     rcx, [rcx+10h]
0x140030e1f  call    WPP_SF_
0x140030e24  jmp     loc_1400311CD
0x140030e29  mov     edx, 1
0x140030e2e  cmp     edx, r8d
0x140030e31  jge     short loc_140030E55
0x140030e33  movsxd  rax, edx
0x140030e36  mov     rcx, [r15+rax*8]
0x140030e3a  movzx   eax, word ptr [rcx]
0x140030e3d  sub     ax, 2Dh ; '-'
0x140030e41  mov     ecx, 0FFFDh
0x140030e46  test    cx, ax
0x140030e49  jnz     short loc_140030E52
0x140030e4b  inc     edx
0x140030e4d  cmp     edx, r8d
0x140030e50  jl      short loc_140030E33
0x140030e52  cmp     edx, r8d
0x140030e55  jnz     short loc_140030E84
0x140030e57  mov     ebx, 80004005h
0x140030e5c  lea     rdi, WPP_GLOBAL_Control
0x140030e63  mov     rcx, cs:WPP_GLOBAL_Control
0x140030e6a  cmp     rcx, rdi
0x140030e6d  jz      loc_1400311CD
0x140030e73  test    byte ptr [rcx+1Ch], 1
0x140030e77  jz      loc_1400311CD
0x140030e7d  mov     edx, 43h ; 'C'
0x140030e82  jmp     short loc_140030E14
0x140030e84  movsxd  rax, edx
0x140030e87  mov     rsi, [r15+rax*8]
0x140030e8b  mov     edx, 2Ch ; ','; Ch
0x140030e90  mov     rcx, rsi; Str
0x140030e93  call    cs:__imp_wcschr
0x140030e99  test    rax, rax
0x140030e9c  jnz     short loc_140030ECC
0x140030e9e  mov     ebx, 80004005h
0x140030ea3  lea     rdi, WPP_GLOBAL_Control
0x140030eaa  mov     rcx, cs:WPP_GLOBAL_Control
0x140030eb1  cmp     rcx, rdi
0x140030eb4  jz      loc_1400311CD
0x140030eba  test    byte ptr [rcx+1Ch], 1
0x140030ebe  jz      loc_1400311CD
0x140030ec4  lea     edx, [rax+44h]
0x140030ec7  jmp     loc_140030E14
0x140030ecc  mov     [rax], r12w
0x140030ed0  mov     edx, 2Eh ; '.'; Ch
0x140030ed5  mov     rcx, rsi; Str
0x140030ed8  call    cs:__imp_wcsrchr
0x140030ede  mov     r14, rax
0x140030ee1  mov     edx, 5Ch ; '\'; Ch
0x140030ee6  mov     rcx, rsi; Str
0x140030ee9  call    cs:__imp_wcschr
0x140030eef  lea     rdi, WPP_GLOBAL_Control
0x140030ef6  test    rax, rax
0x140030ef9  jnz     loc_14003106D
0x140030eff  call    cs:__imp_GetCurrentProcess
0x140030f05  mov     rcx, rax
0x140030f08  xor     r8d, r8d
0x140030f0b  lea     rdx, [rsp+300h+var_2D0]
0x140030f10  call    cs:__imp_IsWow64Process2
0x140030f16  test    eax, eax
0x140030f18  jnz     short loc_140030F48
0x140030f1a  mov     rcx, cs:WPP_GLOBAL_Control
0x140030f21  cmp     rcx, rdi
0x140030f24  jz      short loc_140030F42
0x140030f26  test    byte ptr [rcx+1Ch], 1
0x140030f2a  jz      short loc_140030F42
0x140030f2c  lea     edx, [rax+45h]
0x140030f2f  mov     r9d, ebx
0x140030f32  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x140030f39  mov     rcx, [rcx+10h]
0x140030f3d  call    WPP_SF_d
0x140030f42  mov     [rsp+300h+var_2D0], r12w
0x140030f48  lea     rcx, [rsp+300h+var_2C8]
0x140030f4d  call    ?UtilGetWindowsDirectory@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetWindowsDirectory(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x140030f52  mov     ebx, eax
0x140030f54  test    eax, eax
0x140030f56  jns     short loc_140030F7F
0x140030f58  mov     rcx, cs:WPP_GLOBAL_Control
0x140030f5f  cmp     rcx, rdi
0x140030f62  jz      loc_1400311CD
0x140030f68  test    byte ptr [rcx+1Ch], 1
0x140030f6c  jz      loc_1400311CD
0x140030f72  mov     edx, 46h ; 'F'
0x140030f77  mov     r9d, eax
0x140030f7a  jmp     loc_1400311BC
0x140030f7f  movzx   edx, [rsp+300h+var_2D0]
0x140030f84  lea     rcx, [rsp+300h+var_2A8]
0x140030f89  call    ?UtilGetSystemDirectory2@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@G_N@Z; UtilGetSystemDirectory2(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,ushort,bool)
0x140030f8e  mov     ebx, eax
0x140030f90  test    eax, eax
0x140030f92  jns     short loc_140030FB5
0x140030f94  mov     rcx, cs:WPP_GLOBAL_Control
0x140030f9b  cmp     rcx, rdi
0x140030f9e  jz      loc_1400311CD
0x140030fa4  test    byte ptr [rcx+1Ch], 1
0x140030fa8  jz      loc_1400311CD
0x140030fae  mov     edx, 47h ; 'G'
0x140030fb3  jmp     short loc_140030F77
0x140030fb5  mov     rax, [rsp+300h+var_2C8]
0x140030fba  mov     [rbp+200h+lpPath], rax
0x140030fbe  mov     rax, [rsp+300h+var_2A8]
0x140030fc3  mov     [rbp+200h+var_260], rax
0x140030fc7  mov     ebx, r12d
0x140030fca  lea     r12, aDll; ".dll"
0x140030fd1  xor     eax, eax
0x140030fd3  test    r14, r14
0x140030fd6  cmovnz  r12, rax
0x140030fda  mov     r14d, 104h
0x140030fe0  movsxd  rcx, ebx
0x140030fe3  mov     [rsp+300h+lpFilePart], 0; lpFilePart
0x140030fec  lea     rax, [rbp+200h+Buffer]
0x140030ff0  mov     [rsp+300h+lpBuffer], rax; lpBuffer
0x140030ff5  mov     r9d, r14d; nBufferLength
0x140030ff8  mov     r8, r12; lpExtension
0x140030ffb  mov     rdx, rsi; lpFileName
0x140030ffe  mov     rcx, [rbp+rcx*8+200h+lpPath]; lpPath
0x140031003  call    cs:__imp_SearchPathW
0x140031009  cmp     eax, r14d
0x14003100c  ja      short loc_140031044
0x14003100e  test    eax, eax
0x140031010  jnz     loc_1400310E7
0x140031016  inc     ebx
0x140031018  cmp     ebx, 2
0x14003101b  jb      short loc_140030FE0
0x14003101d  mov     ebx, 80070002h
0x140031022  mov     rcx, cs:WPP_GLOBAL_Control
0x140031029  cmp     rcx, rdi
0x14003102c  jz      loc_1400311CD
0x140031032  test    byte ptr [rcx+1Ch], 1
0x140031036  jz      loc_1400311CD
0x14003103c  lea     edx, [rax+49h]
0x14003103f  jmp     loc_140030E14
0x140031044  mov     ebx, 8007007Ah
0x140031049  mov     rcx, cs:WPP_GLOBAL_Control
0x140031050  cmp     rcx, rdi
0x140031053  jz      loc_1400311CD
0x140031059  test    byte ptr [rcx+1Ch], 1
0x14003105d  jz      loc_1400311CD
0x140031063  mov     edx, 48h ; 'H'
0x140031068  jmp     loc_140030E14
0x14003106d  mov     eax, 7FFFFFFEh
0x140031072  mov     r14d, 104h
0x140031078  mov     edx, r14d
0x14003107b  lea     r8, [rbp+200h+Buffer]
0x14003107f  test    rax, rax
0x140031082  jz      short loc_1400310A1
0x140031084  movzx   ecx, word ptr [rsi]
0x140031087  test    cx, cx
0x14003108a  jz      short loc_1400310A1
0x14003108c  add     rsi, 2
0x140031090  mov     [r8], cx
0x140031094  add     r8, 2
0x140031098  dec     rax
0x14003109b  sub     rdx, 1
0x14003109f  jnz     short loc_14003107F
0x1400310a1  mov     rax, rdx
0x1400310a4  neg     rax
0x1400310a7  sbb     ecx, ecx
0x1400310a9  not     ecx
0x1400310ab  mov     ebx, 8007007Ah
0x1400310b0  and     ebx, ecx
0x1400310b2  lea     rcx, [r8-2]
0x1400310b6  test    rdx, rdx
0x1400310b9  cmovnz  rcx, r8
0x1400310bd  mov     [rcx], r12w
0x1400310c1  jnz     short loc_1400310EA
0x1400310c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400310ca  cmp     rcx, rdi
0x1400310cd  jz      loc_1400311CD
0x1400310d3  test    byte ptr [rcx+1Ch], 1
0x1400310d7  jz      loc_1400311CD
0x1400310dd  mov     edx, 4Ah ; 'J'
0x1400310e2  jmp     loc_1400311B9
0x1400310e7  xor     r12d, r12d
0x1400310ea  mov     edx, 2Eh ; '.'; Ch
0x1400310ef  lea     rcx, [rbp+200h+Buffer]; Str
0x1400310f3  call    cs:__imp_wcsrchr
0x1400310f9  test    rax, rax
0x1400310fc  jnz     short loc_14003113B
0x1400310fe  lea     r8, aDll; ".dll"
0x140031105  mov     rdx, r14; unsigned __int64
0x140031108  lea     rcx, [rbp+200h+Buffer]; wchar_t *
0x14003110c  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140031111  mov     ebx, eax
0x140031113  test    eax, eax
0x140031115  jns     short loc_14003113B
0x140031117  mov     rcx, cs:WPP_GLOBAL_Control
0x14003111e  cmp     rcx, rdi
0x140031121  jz      loc_1400311CD
0x140031127  test    byte ptr [rcx+1Ch], 1
0x14003112b  jz      loc_1400311CD
0x140031131  mov     edx, 4Bh ; 'K'
0x140031136  jmp     loc_140030F77
0x14003113b  lea     rax, [rbp+200h+Buffer]
0x14003113f  or      r8, 0FFFFFFFFFFFFFFFFh
0x140031143  inc     r8
0x140031146  cmp     [rax+r8*2], r12w
0x14003114b  jnz     short loc_140031143
0x14003114d  lea     rdx, [rbp+200h+Buffer]
0x140031151  mov     rcx, r13
0x140031154  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x140031159  test    al, al
0x14003115b  jnz     short loc_140031181
0x14003115d  mov     ebx, 8007000Eh
0x140031162  mov     rcx, cs:WPP_GLOBAL_Control
0x140031169  cmp     rcx, rdi
0x14003116c  jz      short loc_1400311CD
0x14003116e  test    byte ptr [rcx+1Ch], 1
0x140031172  jz      short loc_1400311CD
0x140031174  mov     edx, 4Ch ; 'L'
0x140031179  mov     r9d, 8007000Eh
0x14003117f  jmp     short loc_1400311BC
0x140031181  mov     ebx, r12d
0x140031184  jmp     short loc_1400311CD
0x140031186  call    cs:__imp_GetLastError
0x14003118c  mov     ebx, eax
0x14003118e  test    eax, eax
0x140031190  jle     short loc_14003119B
0x140031192  movzx   ebx, ax
0x140031195  or      ebx, 80070000h
0x14003119b  lea     rdi, WPP_GLOBAL_Control
0x1400311a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400311a9  cmp     rcx, rdi
0x1400311ac  jz      short loc_1400311CD
0x1400311ae  test    byte ptr [rcx+1Ch], 1
0x1400311b2  jz      short loc_1400311CD
0x1400311b4  mov     edx, 41h ; 'A'
0x1400311b9  mov     r9d, ebx
  ... truncated ...
```
