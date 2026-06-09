# UtilGetRundll32HostedAppName(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x140032ec4`
- end: `0x14003350a`
- name: `?UtilGetRundll32HostedAppName@@YAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `1606`
- prototype: `__int64 __fastcall(HANDLE hProcess, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x14001cf1c`

## callees

- `0x140002490`
- `0x140002748`
- `0x14000b448`
- `0x14000ca20`
- `0x1400113b8`
- `0x140011a04`
- `0x140011fec`
- `0x140014ee4`
- `0x140014f14`
- `0x140032ec4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1400330d0`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x140033309`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1400330d0`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x140033309`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x140033085`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1400330e7`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x140033085`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1400330e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400333a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400333a2`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x140033213`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x140033213`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140033103`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140033103`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x14003311a`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x14003311a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003342e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003342e`
- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x140032fb4`
- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x140032fb4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  int WindowsDirectory; // eax
  __int64 v18; // r9
  int v19; // ebx
  const WCHAR *v20; // r12
  DWORD v21; // eax
  __int64 v22; // rax
  __int64 v23; // rdx
  WCHAR *v24; // r8
  wchar_t v25; // cx
  WCHAR *v26; // rcx
  __int64 v27; // r8
  signed int LastError; // eax
  _WORD v30[2]; // [rsp+30h] [rbp-D0h] BYREF
  int pNumArgs; // [rsp+34h] [rbp-CCh] BYREF
  void *v32[2]; // [rsp+38h] [rbp-C8h] BYREF
  _WORD v33[8]; // [rsp+48h] [rbp-B8h] BYREF
  void *v34[2]; // [rsp+58h] [rbp-A8h] BYREF
  _WORD v35[8]; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpCmdLine; // [rsp+78h] [rbp-88h]
  _WORD *v37; // [rsp+80h] [rbp-80h]
  _WORD v38[8]; // [rsp+88h] [rbp-78h] BYREF
  LPCWSTR lpPath[3]; // [rsp+98h] [rbp-68h]
  WCHAR Buffer[264]; // [rsp+B0h] [rbp-50h] BYREF

  lpCmdLine = v38;
  v37 = v38;
  v38[0] = 0;
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
    ProcessCommandLine = UtilGetProcessCommandLine(hProcess);
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
    v4 = CommandLineToArgvW(lpCmdLine, &pNumArgs);
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
        WindowsDirectory = UtilGetSystemDirectory2(v34, v30[0]);
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
        if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                 a2,
                                 Buffer) )
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
        if ( lpCmdLine != v38 )
          operator delete((void *)lpCmdLine, (const struct std::nothrow_t *)&std::nothrow);
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
  if ( lpCmdLine != v38 )
    operator delete((void *)lpCmdLine, (const struct std::nothrow_t *)&std::nothrow);
  return 2147942487LL;
}

```

## disassembly

```asm
0x140032ec4  mov     [rsp-8+arg_10], rbx
0x140032ec9  push    rbp
0x140032eca  push    rsi
0x140032ecb  push    rdi
0x140032ecc  push    r12
0x140032ece  push    r13
0x140032ed0  push    r14
0x140032ed2  push    r15
0x140032ed4  lea     rbp, [rsp-1D0h]
0x140032edc  sub     rsp, 2D0h
0x140032ee3  mov     rax, cs:__security_cookie
0x140032eea  xor     rax, rsp
0x140032eed  mov     [rbp+200h+var_40], rax
0x140032ef4  mov     r13, rdx
0x140032ef7  mov     r9, rcx
0x140032efa  lea     rax, [rbp+200h+var_278]
0x140032efe  mov     [rsp+300h+lpCmdLine], rax
0x140032f03  lea     rax, [rbp+200h+var_278]
0x140032f07  mov     [rbp+200h+var_280], rax
0x140032f0b  xor     r12d, r12d
0x140032f0e  mov     [rbp+200h+var_278], r12w
0x140032f13  mov     r15d, r12d
0x140032f16  mov     [rsp+300h+pNumArgs], r12d
0x140032f1b  mov     [rsp+300h+var_2D0], r12w
0x140032f21  lea     rcx, [rsp+300h+var_2B8]
0x140032f26  mov     [rsp+300h+var_2C8], rcx
0x140032f2b  lea     rax, [rsp+300h+var_2B8]
0x140032f30  mov     [rsp+300h+var_2C0], rax
0x140032f35  mov     [rsp+300h+var_2B8], r12w
0x140032f3b  lea     r8, [rsp+300h+var_298]
0x140032f40  mov     [rsp+300h+var_2A8], r8
0x140032f45  lea     rax, [rsp+300h+var_298]
0x140032f4a  mov     [rsp+300h+var_2A0], rax
0x140032f4f  mov     [rsp+300h+var_298], r12w
0x140032f55  test    r9, r9
0x140032f58  jz      loc_140033458
0x140032f5e  test    rdx, rdx
0x140032f61  jz      loc_140033458
0x140032f67  mov     [rbp+200h+Buffer], r12w
0x140032f6c  lea     rdx, [rsp+300h+lpCmdLine]
0x140032f71  mov     rcx, r9; hProcess
0x140032f74  call    ?UtilGetProcessCommandLine@@YAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetProcessCommandLine(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x140032f79  mov     ebx, eax
0x140032f7b  test    eax, eax
0x140032f7d  jns     short loc_140032FAA
0x140032f7f  lea     rdi, WPP_GLOBAL_Control
0x140032f86  mov     rcx, cs:WPP_GLOBAL_Control
0x140032f8d  cmp     rcx, rdi
0x140032f90  jz      loc_1400333EF
0x140032f96  test    byte ptr [rcx+1Ch], 1
0x140032f9a  jz      loc_1400333EF
0x140032fa0  lea     edx, [r12+40h]
0x140032fa5  jmp     loc_1400333DB
0x140032faa  lea     rdx, [rsp+300h+pNumArgs]; pNumArgs
0x140032faf  mov     rcx, [rsp+300h+lpCmdLine]; lpCmdLine
0x140032fb4  call    cs:__imp_CommandLineToArgvW
0x140032fbb  nop     dword ptr [rax+rax+00h]
0x140032fc0  mov     r15, rax
0x140032fc3  mov     [rbp+200h+lpPath], rax
0x140032fc7  test    rax, rax
0x140032fca  jz      loc_1400333A2
0x140032fd0  mov     r8d, [rsp+300h+pNumArgs]
0x140032fd5  cmp     r8d, 2
0x140032fd9  jge     short loc_14003301B
0x140032fdb  mov     ebx, 80004005h
0x140032fe0  lea     rdi, WPP_GLOBAL_Control
0x140032fe7  mov     rcx, cs:WPP_GLOBAL_Control
0x140032fee  cmp     rcx, rdi
0x140032ff1  jz      loc_1400333EF
0x140032ff7  test    byte ptr [rcx+1Ch], 1
0x140032ffb  jz      loc_1400333EF
0x140033001  mov     edx, 42h ; 'B'
0x140033006  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x14003300d  mov     rcx, [rcx+10h]
0x140033011  call    WPP_SF_
0x140033016  jmp     loc_1400333EF
0x14003301b  mov     edx, 1
0x140033020  cmp     edx, r8d
0x140033023  jge     short loc_140033047
0x140033025  movsxd  rax, edx
0x140033028  mov     rcx, [r15+rax*8]
0x14003302c  movzx   eax, word ptr [rcx]
0x14003302f  sub     ax, 2Dh ; '-'
0x140033033  mov     ecx, 0FFFDh
0x140033038  test    cx, ax
0x14003303b  jnz     short loc_140033044
0x14003303d  inc     edx
0x14003303f  cmp     edx, r8d
0x140033042  jl      short loc_140033025
0x140033044  cmp     edx, r8d
0x140033047  jnz     short loc_140033076
0x140033049  mov     ebx, 80004005h
0x14003304e  lea     rdi, WPP_GLOBAL_Control
0x140033055  mov     rcx, cs:WPP_GLOBAL_Control
0x14003305c  cmp     rcx, rdi
0x14003305f  jz      loc_1400333EF
0x140033065  test    byte ptr [rcx+1Ch], 1
0x140033069  jz      loc_1400333EF
0x14003306f  mov     edx, 43h ; 'C'
0x140033074  jmp     short loc_140033006
0x140033076  movsxd  rax, edx
0x140033079  mov     rsi, [r15+rax*8]
0x14003307d  mov     edx, 2Ch ; ','; Ch
0x140033082  mov     rcx, rsi; Str
0x140033085  call    cs:__imp_wcschr
0x14003308c  nop     dword ptr [rax+rax+00h]
0x140033091  test    rax, rax
0x140033094  jnz     short loc_1400330C4
0x140033096  mov     ebx, 80004005h
0x14003309b  lea     rdi, WPP_GLOBAL_Control
0x1400330a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400330a9  cmp     rcx, rdi
0x1400330ac  jz      loc_1400333EF
0x1400330b2  test    byte ptr [rcx+1Ch], 1
0x1400330b6  jz      loc_1400333EF
0x1400330bc  lea     edx, [rax+44h]
0x1400330bf  jmp     loc_140033006
0x1400330c4  mov     [rax], r12w
0x1400330c8  mov     edx, 2Eh ; '.'; Ch
0x1400330cd  mov     rcx, rsi; Str
0x1400330d0  call    cs:__imp_wcsrchr
0x1400330d7  nop     dword ptr [rax+rax+00h]
0x1400330dc  mov     r14, rax
0x1400330df  mov     edx, 5Ch ; '\'; Ch
0x1400330e4  mov     rcx, rsi; Str
0x1400330e7  call    cs:__imp_wcschr
0x1400330ee  nop     dword ptr [rax+rax+00h]
0x1400330f3  lea     rdi, WPP_GLOBAL_Control
0x1400330fa  test    rax, rax
0x1400330fd  jnz     loc_140033283
0x140033103  call    cs:__imp_GetCurrentProcess
0x14003310a  nop     dword ptr [rax+rax+00h]
0x14003310f  mov     rcx, rax
0x140033112  xor     r8d, r8d
0x140033115  lea     rdx, [rsp+300h+var_2D0]
0x14003311a  call    cs:__imp_IsWow64Process2
0x140033121  nop     dword ptr [rax+rax+00h]
0x140033126  test    eax, eax
0x140033128  jnz     short loc_140033158
0x14003312a  mov     rcx, cs:WPP_GLOBAL_Control
0x140033131  cmp     rcx, rdi
0x140033134  jz      short loc_140033152
0x140033136  test    byte ptr [rcx+1Ch], 1
0x14003313a  jz      short loc_140033152
0x14003313c  lea     edx, [rax+45h]
0x14003313f  mov     r9d, ebx
0x140033142  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x140033149  mov     rcx, [rcx+10h]
0x14003314d  call    WPP_SF_d
0x140033152  mov     [rsp+300h+var_2D0], r12w
0x140033158  lea     rcx, [rsp+300h+var_2C8]
0x14003315d  call    ?UtilGetWindowsDirectory@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetWindowsDirectory(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x140033162  mov     ebx, eax
0x140033164  test    eax, eax
0x140033166  jns     short loc_14003318F
0x140033168  mov     rcx, cs:WPP_GLOBAL_Control
0x14003316f  cmp     rcx, rdi
0x140033172  jz      loc_1400333EF
0x140033178  test    byte ptr [rcx+1Ch], 1
0x14003317c  jz      loc_1400333EF
0x140033182  mov     edx, 46h ; 'F'
0x140033187  mov     r9d, eax
0x14003318a  jmp     loc_1400333DE
0x14003318f  movzx   edx, [rsp+300h+var_2D0]
0x140033194  lea     rcx, [rsp+300h+var_2A8]
0x140033199  call    ?UtilGetSystemDirectory2@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@G_N@Z; UtilGetSystemDirectory2(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,ushort,bool)
0x14003319e  mov     ebx, eax
0x1400331a0  test    eax, eax
0x1400331a2  jns     short loc_1400331C5
0x1400331a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400331ab  cmp     rcx, rdi
0x1400331ae  jz      loc_1400333EF
0x1400331b4  test    byte ptr [rcx+1Ch], 1
0x1400331b8  jz      loc_1400333EF
0x1400331be  mov     edx, 47h ; 'G'
0x1400331c3  jmp     short loc_140033187
0x1400331c5  mov     rax, [rsp+300h+var_2C8]
0x1400331ca  mov     [rbp+200h+lpPath], rax
0x1400331ce  mov     rax, [rsp+300h+var_2A8]
0x1400331d3  mov     [rbp+200h+var_260], rax
0x1400331d7  mov     ebx, r12d
0x1400331da  lea     r12, aDll; ".dll"
0x1400331e1  xor     eax, eax
0x1400331e3  test    r14, r14
0x1400331e6  cmovnz  r12, rax
0x1400331ea  mov     r14d, 104h
0x1400331f0  movsxd  rcx, ebx
0x1400331f3  mov     [rsp+300h+lpFilePart], 0; lpFilePart
0x1400331fc  lea     rax, [rbp+200h+Buffer]
0x140033200  mov     [rsp+300h+lpBuffer], rax; lpBuffer
0x140033205  mov     r9d, r14d; nBufferLength
0x140033208  mov     r8, r12; lpExtension
0x14003320b  mov     rdx, rsi; lpFileName
0x14003320e  mov     rcx, [rbp+rcx*8+200h+lpPath]; lpPath
0x140033213  call    cs:__imp_SearchPathW
0x14003321a  nop     dword ptr [rax+rax+00h]
0x14003321f  cmp     eax, r14d
0x140033222  ja      short loc_14003325A
0x140033224  test    eax, eax
0x140033226  jnz     loc_1400332FD
0x14003322c  inc     ebx
0x14003322e  cmp     ebx, 2
0x140033231  jb      short loc_1400331F0
0x140033233  mov     ebx, 80070002h
0x140033238  mov     rcx, cs:WPP_GLOBAL_Control
0x14003323f  cmp     rcx, rdi
0x140033242  jz      loc_1400333EF
0x140033248  test    byte ptr [rcx+1Ch], 1
0x14003324c  jz      loc_1400333EF
0x140033252  lea     edx, [rax+49h]
0x140033255  jmp     loc_140033006
0x14003325a  mov     ebx, 8007007Ah
0x14003325f  mov     rcx, cs:WPP_GLOBAL_Control
0x140033266  cmp     rcx, rdi
0x140033269  jz      loc_1400333EF
0x14003326f  test    byte ptr [rcx+1Ch], 1
0x140033273  jz      loc_1400333EF
0x140033279  mov     edx, 48h ; 'H'
0x14003327e  jmp     loc_140033006
0x140033283  mov     eax, 7FFFFFFEh
0x140033288  mov     r14d, 104h
0x14003328e  mov     edx, r14d
0x140033291  lea     r8, [rbp+200h+Buffer]
0x140033295  test    rax, rax
0x140033298  jz      short loc_1400332B7
0x14003329a  movzx   ecx, word ptr [rsi]
0x14003329d  test    cx, cx
0x1400332a0  jz      short loc_1400332B7
0x1400332a2  add     rsi, 2
0x1400332a6  mov     [r8], cx
0x1400332aa  add     r8, 2
0x1400332ae  dec     rax
0x1400332b1  sub     rdx, 1
0x1400332b5  jnz     short loc_140033295
0x1400332b7  mov     rax, rdx
0x1400332ba  neg     rax
0x1400332bd  sbb     ecx, ecx
0x1400332bf  not     ecx
0x1400332c1  mov     ebx, 8007007Ah
0x1400332c6  and     ebx, ecx
0x1400332c8  lea     rcx, [r8-2]
0x1400332cc  test    rdx, rdx
0x1400332cf  cmovnz  rcx, r8
0x1400332d3  mov     [rcx], r12w
0x1400332d7  jnz     short loc_140033300
0x1400332d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400332e0  cmp     rcx, rdi
0x1400332e3  jz      loc_1400333EF
0x1400332e9  test    byte ptr [rcx+1Ch], 1
0x1400332ed  jz      loc_1400333EF
0x1400332f3  mov     edx, 4Ah ; 'J'
0x1400332f8  jmp     loc_1400333DB
0x1400332fd  xor     r12d, r12d
0x140033300  mov     edx, 2Eh ; '.'; Ch
0x140033305  lea     rcx, [rbp+200h+Buffer]; Str
0x140033309  call    cs:__imp_wcsrchr
0x140033310  nop     dword ptr [rax+rax+00h]
0x140033315  test    rax, rax
0x140033318  jnz     short loc_140033357
0x14003331a  lea     r8, aDll; ".dll"
0x140033321  mov     rdx, r14; unsigned __int64
0x140033324  lea     rcx, [rbp+200h+Buffer]; wchar_t *
0x140033328  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x14003332d  mov     ebx, eax
0x14003332f  test    eax, eax
0x140033331  jns     short loc_140033357
0x140033333  mov     rcx, cs:WPP_GLOBAL_Control
0x14003333a  cmp     rcx, rdi
0x14003333d  jz      loc_1400333EF
0x140033343  test    byte ptr [rcx+1Ch], 1
0x140033347  jz      loc_1400333EF
0x14003334d  mov     edx, 4Bh ; 'K'
0x140033352  jmp     loc_140033187
0x140033357  lea     rax, [rbp+200h+Buffer]
0x14003335b  or      r8, 0FFFFFFFFFFFFFFFFh
0x14003335f  inc     r8
0x140033362  cmp     [rax+r8*2], r12w
0x140033367  jnz     short loc_14003335F
0x140033369  lea     rdx, [rbp+200h+Buffer]
0x14003336d  mov     rcx, r13
0x140033370  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x140033375  test    al, al
0x140033377  jnz     short loc_14003339D
0x140033379  mov     ebx, 8007000Eh
0x14003337e  mov     rcx, cs:WPP_GLOBAL_Control
0x140033385  cmp     rcx, rdi
0x140033388  jz      short loc_1400333EF
0x14003338a  test    byte ptr [rcx+1Ch], 1
0x14003338e  jz      short loc_1400333EF
0x140033390  mov     edx, 4Ch ; 'L'
0x140033395  mov     r9d, 8007000Eh
0x14003339b  jmp     short loc_1400333DE
0x14003339d  mov     ebx, r12d
0x1400333a0  jmp     short loc_1400333EF
0x1400333a2  call    cs:__imp_GetLastError
0x1400333a9  nop     dword ptr [rax+rax+00h]
0x1400333ae  mov     ebx, eax
0x1400333b0  test    eax, eax
0x1400333b2  jle     short loc_1400333BD
0x1400333b4  movzx   ebx, ax
  ... truncated ...
```
