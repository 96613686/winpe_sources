# CRuntimePlugin::AskModuleToClaimCrash(wchar_t const *,void *,ulong *,long (**)(void *,_WER_RUNTIME_EXCEPTION_INFORMATION * const,ulong,wchar_t *,ulong *,wchar_t *,ulong *),long (**)(void *,_WER_RUNTIME_EXCEPTION_INFORMATION * const,int *,wchar_t *,ulong *,int *),tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>> *)

- ea: `0x14004ec4c`
- end: `0x14004f004`
- name: `?AskModuleToClaimCrash@CRuntimePlugin@@AEAAJPEB_WPEAXPEAKPEAP6AJ1QEAU_WER_RUNTIME_EXCEPTION_INFORMATION@@KPEA_W242@ZPEAP6AJ13PEAH426@ZPEAV?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@@Z`
- size: `952`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, __int64, __int64, FARPROC *, FARPROC *, HMODULE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x14004f02c`

## callees

- `0x140002490`
- `0x14000ca20`
- `0x140014ee4`
- `0x140014f14`
- `0x140016564`
- `0x14004ec4c`
- `0x140061010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14004ed04`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14004ef9a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14004ed04`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14004ef9a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004ed98`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004eeb2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004ef48`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004ed98`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004eeb2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004ef48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004ed15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004ed15`
- `ntdll!RtlSetThreadErrorMode` at `0x14004ecde`
- `ntdll!RtlSetThreadErrorMode` at `0x14004ed40`
- `ntdll!RtlSetThreadErrorMode` at `0x14004ecde`
- `ntdll!RtlSetThreadErrorMode` at `0x14004ed40`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x14004eced`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x14004eced`

## pseudocode

```c
__int64 __fastcall CRuntimePlugin::AskModuleToClaimCrash(
        __int64 a1,
        const WCHAR *a2,
        __int64 a3,
        __int64 a4,
        FARPROC *a5,
        FARPROC *a6,
        HMODULE *a7)
{
  signed int v7; // ebx
  HMODULE LibraryW; // rax
  HMODULE v13; // rcx
  signed int LastError; // eax
  FARPROC ProcAddress; // rax
  CUserModeHangReport *v16; // rcx
  __int64 v17; // rdx
  CUserModeHangReport *v18; // rcx
  __int64 v19; // rdx
  int v20; // eax
  FARPROC v21; // rax
  __int64 v22; // r8
  FARPROC v23; // rax
  HMODULE v24; // rcx
  int v26; // [rsp+40h] [rbp-C0h] BYREF
  ULONG OldMode; // [rsp+44h] [rbp-BCh] BYREF
  int v28; // [rsp+48h] [rbp-B8h] BYREF
  FARPROC *v29; // [rsp+50h] [rbp-B0h]
  _WORD v30[264]; // [rsp+60h] [rbp-A0h] BYREF

  v7 = 0;
  v29 = a6;
  OldMode = 0;
  v26 = 0;
  v28 = 0;
  if ( a4 && a7 && a5 && a2 )
  {
    v30[0] = 0;
    RtlSetThreadErrorMode(0x10u, &OldMode);
    LibraryW = LoadLibraryW(a2);
    v13 = *a7;
    *a7 = LibraryW;
    if ( v13 )
      FreeLibrary(v13);
    if ( !*a7 )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      if ( v7 >= 0 )
        v7 = -2147467259;
    }
    RtlSetThreadErrorMode(OldMode, 0);
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          37,
          WPP_f577d8521c9b39ef05153804ed8add08_Traceguids,
          (unsigned int)v7);
      }
      goto LABEL_48;
    }
    ProcAddress = GetProcAddress(*a7, "OutOfProcessExceptionEventCallback");
    if ( !ProcAddress )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_21;
      }
      v17 = 38;
LABEL_20:
      WPP_SF_(*((_QWORD *)v16 + 2), v17, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids);
LABEL_21:
      v7 = -2147467259;
      goto LABEL_48;
    }
    v28 = 260;
    v7 = ((__int64 (__fastcall *)(__int64, __int64, int *, _WORD *, int *, __int64))ProcAddress)(
           a3,
           a1 + 848,
           &v26,
           v30,
           &v28,
           a4);
    if ( v7 < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v19 = 39;
LABEL_42:
        WPP_SF_(*((_QWORD *)v18 + 2), v19, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids);
        goto LABEL_48;
      }
      goto LABEL_48;
    }
    v20 = v26;
    v7 = 0;
    if ( v26 )
    {
      if ( *(_DWORD *)(a1 + 2808) )
      {
        v26 = 0;
        if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        {
          goto LABEL_47;
        }
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          40,
          (unsigned int)WPP_f577d8521c9b39ef05153804ed8add08_Traceguids,
          (_DWORD)a2,
          (__int64)v30);
        v20 = v26;
      }
      if ( v20 )
      {
        v21 = GetProcAddress(*a7, "OutOfProcessExceptionEventSignatureCallback");
        *a5 = v21;
        if ( !v21 )
        {
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_21;
          }
          v17 = 41;
          goto LABEL_20;
        }
        v22 = -1;
        do
          ++v22;
        while ( v30[v22] );
        if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                a1 + 728,
                                v30) )
        {
          v23 = GetProcAddress(*a7, "OutOfProcessExceptionEventDebuggerLaunchCallback");
          *v29 = v23;
          if ( !v23
            && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids);
          }
          return (unsigned int)v7;
        }
        v7 = -2147024882;
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v19 = 42;
          goto LABEL_42;
        }
LABEL_48:
        v24 = *a7;
        *a7 = 0;
        if ( v24 )
          FreeLibrary(v24);
        *a5 = 0;
        return (unsigned int)v7;
      }
    }
LABEL_47:
    v7 = -2147467263;
    goto LABEL_48;
  }
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids);
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x14004ec4c  push    rbp
0x14004ec4e  push    rbx
0x14004ec4f  push    rsi
0x14004ec50  push    rdi
0x14004ec51  push    r12
0x14004ec53  push    r13
0x14004ec55  push    r14
0x14004ec57  push    r15
0x14004ec59  lea     rbp, [rsp-188h]
0x14004ec61  sub     rsp, 288h
0x14004ec68  mov     rax, cs:__security_cookie
0x14004ec6f  xor     rax, rsp
0x14004ec72  mov     [rbp+1C0h+var_50], rax
0x14004ec79  mov     rax, [rbp+1C0h+arg_28]
0x14004ec80  xor     ebx, ebx
0x14004ec82  mov     rsi, [rbp+1C0h+arg_30]
0x14004ec89  mov     rdi, r9
0x14004ec8c  mov     r15, [rbp+1C0h+arg_20]
0x14004ec93  mov     r12, r8
0x14004ec96  mov     [rsp+2C0h+var_270], rax
0x14004ec9b  mov     r14, rdx
0x14004ec9e  mov     [rsp+2C0h+OldMode], ebx
0x14004eca2  mov     r13, rcx
0x14004eca5  mov     [rsp+2C0h+var_280], ebx
0x14004eca9  mov     [rsp+2C0h+var_278], ebx
0x14004ecad  test    r9, r9
0x14004ecb0  jz      loc_14004EFAD
0x14004ecb6  test    rsi, rsi
0x14004ecb9  jz      loc_14004EFAD
0x14004ecbf  test    r15, r15
0x14004ecc2  jz      loc_14004EFAD
0x14004ecc8  test    rdx, rdx
0x14004eccb  jz      loc_14004EFAD
0x14004ecd1  lea     rdx, [rsp+2C0h+OldMode]; OldMode
0x14004ecd6  mov     [rsp+2C0h+var_260], bx
0x14004ecdb  lea     ecx, [rbx+10h]; NewMode
0x14004ecde  call    cs:__imp_RtlSetThreadErrorMode
0x14004ece5  nop     dword ptr [rax+rax+00h]
0x14004ecea  mov     rcx, r14; lpLibFileName
0x14004eced  call    cs:__imp_LoadLibraryW
0x14004ecf4  nop     dword ptr [rax+rax+00h]
0x14004ecf9  mov     rcx, [rsi]; hLibModule
0x14004ecfc  mov     [rsi], rax
0x14004ecff  test    rcx, rcx
0x14004ed02  jz      short loc_14004ED10
0x14004ed04  call    cs:__imp_FreeLibrary
0x14004ed0b  nop     dword ptr [rax+rax+00h]
0x14004ed10  cmp     [rsi], rbx
0x14004ed13  jnz     short loc_14004ED3A
0x14004ed15  call    cs:__imp_GetLastError
0x14004ed1c  nop     dword ptr [rax+rax+00h]
0x14004ed21  mov     ebx, eax
0x14004ed23  test    eax, eax
0x14004ed25  jle     short loc_14004ED30
0x14004ed27  movzx   ebx, ax
0x14004ed2a  or      ebx, 80070000h
0x14004ed30  test    ebx, ebx
0x14004ed32  mov     eax, 80004005h
0x14004ed37  cmovns  ebx, eax
0x14004ed3a  mov     ecx, [rsp+2C0h+OldMode]; NewMode
0x14004ed3e  xor     edx, edx; OldMode
0x14004ed40  call    cs:__imp_RtlSetThreadErrorMode
0x14004ed47  nop     dword ptr [rax+rax+00h]
0x14004ed4c  test    ebx, ebx
0x14004ed4e  jns     short loc_14004ED8E
0x14004ed50  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ed57  lea     rdi, WPP_GLOBAL_Control
0x14004ed5e  cmp     rcx, rdi
0x14004ed61  jz      loc_14004EF8D
0x14004ed67  test    byte ptr [rcx+1Ch], 1
0x14004ed6b  jz      loc_14004EF8D
0x14004ed71  mov     rcx, [rcx+10h]
0x14004ed75  lea     r8, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids
0x14004ed7c  mov     edx, 25h ; '%'
0x14004ed81  mov     r9d, ebx
0x14004ed84  call    WPP_SF_d
0x14004ed89  jmp     loc_14004EF8D
0x14004ed8e  mov     rcx, [rsi]; hModule
0x14004ed91  lea     rdx, aOutofprocessex_0; "OutOfProcessExceptionEventCallback"
0x14004ed98  call    cs:__imp_GetProcAddress
0x14004ed9f  nop     dword ptr [rax+rax+00h]
0x14004eda4  test    rax, rax
0x14004eda7  jnz     short loc_14004EDDF
0x14004eda9  mov     rcx, cs:WPP_GLOBAL_Control
0x14004edb0  lea     rdi, WPP_GLOBAL_Control
0x14004edb7  cmp     rcx, rdi
0x14004edba  jz      short loc_14004EDD5
0x14004edbc  test    byte ptr [rcx+1Ch], 1
0x14004edc0  jz      short loc_14004EDD5
0x14004edc2  lea     edx, [rax+26h]
0x14004edc5  mov     rcx, [rcx+10h]
0x14004edc9  lea     r8, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids
0x14004edd0  call    WPP_SF_
0x14004edd5  mov     ebx, 80004005h
0x14004edda  jmp     loc_14004EF8D
0x14004eddf  lea     rcx, [rsp+2C0h+var_278]
0x14004ede4  mov     [rsp+2C0h+var_298], rdi
0x14004ede9  mov     [rsp+2C0h+var_2A0], rcx
0x14004edee  lea     rdx, [r13+350h]
0x14004edf5  mov     rcx, r12
0x14004edf8  mov     [rsp+2C0h+var_278], 104h
0x14004ee00  lea     r9, [rsp+2C0h+var_260]
0x14004ee05  lea     r8, [rsp+2C0h+var_280]
0x14004ee0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ee0f  mov     ebx, eax
0x14004ee11  test    eax, eax
0x14004ee13  jns     short loc_14004EE40
0x14004ee15  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ee1c  lea     rdi, WPP_GLOBAL_Control
0x14004ee23  cmp     rcx, rdi
0x14004ee26  jz      loc_14004EF8D
0x14004ee2c  test    byte ptr [rcx+1Ch], 1
0x14004ee30  jz      loc_14004EF8D
0x14004ee36  mov     edx, 27h ; '''
0x14004ee3b  jmp     loc_14004EF2C
0x14004ee40  mov     eax, [rsp+2C0h+var_280]
0x14004ee44  xor     ebx, ebx
0x14004ee46  test    eax, eax
0x14004ee48  jz      loc_14004EF88
0x14004ee4e  lea     rdi, WPP_GLOBAL_Control
0x14004ee55  cmp     [r13+0AF8h], ebx
0x14004ee5c  jz      short loc_14004EEA0
0x14004ee5e  mov     [rsp+2C0h+var_280], ebx
0x14004ee62  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ee69  cmp     rcx, rdi
0x14004ee6c  jz      loc_14004EF88
0x14004ee72  test    byte ptr [rcx+1Ch], 4
0x14004ee76  jz      loc_14004EF88
0x14004ee7c  mov     rcx, [rcx+10h]
0x14004ee80  lea     rax, [rsp+2C0h+var_260]
0x14004ee85  lea     edx, [rbx+28h]
0x14004ee88  mov     [rsp+2C0h+var_2A0], rax
0x14004ee8d  mov     r9, r14
0x14004ee90  lea     r8, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids
0x14004ee97  call    WPP_SF_SS
0x14004ee9c  mov     eax, [rsp+2C0h+var_280]
0x14004eea0  test    eax, eax
0x14004eea2  jz      loc_14004EF88
0x14004eea8  mov     rcx, [rsi]; hModule
0x14004eeab  lea     rdx, aOutofprocessex_1; "OutOfProcessExceptionEventSignatureCall"...
0x14004eeb2  call    cs:__imp_GetProcAddress
0x14004eeb9  nop     dword ptr [rax+rax+00h]
0x14004eebe  mov     [r15], rax
0x14004eec1  test    rax, rax
0x14004eec4  jnz     short loc_14004EEE8
0x14004eec6  mov     rcx, cs:WPP_GLOBAL_Control
0x14004eecd  cmp     rcx, rdi
0x14004eed0  jz      loc_14004EDD5
0x14004eed6  test    byte ptr [rcx+1Ch], 1
0x14004eeda  jz      loc_14004EDD5
0x14004eee0  lea     edx, [rax+29h]
0x14004eee3  jmp     loc_14004EDC5
0x14004eee8  lea     rax, [rsp+2C0h+var_260]
0x14004eeed  or      r8, 0FFFFFFFFFFFFFFFFh
0x14004eef1  inc     r8
0x14004eef4  cmp     [rax+r8*2], bx
0x14004eef9  jnz     short loc_14004EEF1
0x14004eefb  lea     rcx, [r13+2D8h]
0x14004ef02  lea     rdx, [rsp+2C0h+var_260]
0x14004ef07  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14004ef0c  test    al, al
0x14004ef0e  jnz     short loc_14004EF3E
0x14004ef10  mov     ebx, 8007000Eh
0x14004ef15  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ef1c  cmp     rcx, rdi
0x14004ef1f  jz      short loc_14004EF8D
0x14004ef21  test    byte ptr [rcx+1Ch], 1
0x14004ef25  jz      short loc_14004EF8D
0x14004ef27  mov     edx, 2Ah ; '*'
0x14004ef2c  mov     rcx, [rcx+10h]
0x14004ef30  lea     r8, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids
0x14004ef37  call    WPP_SF_
0x14004ef3c  jmp     short loc_14004EF8D
0x14004ef3e  mov     rcx, [rsi]; hModule
0x14004ef41  lea     rdx, aOutofprocessex; "OutOfProcessExceptionEventDebuggerLaunc"...
0x14004ef48  call    cs:__imp_GetProcAddress
0x14004ef4f  nop     dword ptr [rax+rax+00h]
0x14004ef54  mov     rcx, [rsp+2C0h+var_270]
0x14004ef59  mov     [rcx], rax
0x14004ef5c  test    rax, rax
0x14004ef5f  jnz     short loc_14004EFA9
0x14004ef61  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ef68  cmp     rcx, rdi
0x14004ef6b  jz      short loc_14004EFA9
0x14004ef6d  test    byte ptr [rcx+1Ch], 1
0x14004ef71  jz      short loc_14004EFA9
0x14004ef73  mov     rcx, [rcx+10h]
0x14004ef77  lea     edx, [rax+2Bh]
0x14004ef7a  lea     r8, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids
0x14004ef81  call    WPP_SF_
0x14004ef86  jmp     short loc_14004EFA9
0x14004ef88  mov     ebx, 80004001h
0x14004ef8d  mov     rcx, [rsi]; hLibModule
0x14004ef90  xor     edi, edi
0x14004ef92  mov     [rsi], rdi
0x14004ef95  test    rcx, rcx
0x14004ef98  jz      short loc_14004EFA6
0x14004ef9a  call    cs:__imp_FreeLibrary
0x14004efa1  nop     dword ptr [rax+rax+00h]
0x14004efa6  mov     [r15], rdi
0x14004efa9  mov     eax, ebx
0x14004efab  jmp     short loc_14004EFE0
0x14004efad  mov     rcx, cs:WPP_GLOBAL_Control
0x14004efb4  lea     rdi, WPP_GLOBAL_Control
0x14004efbb  cmp     rcx, rdi
0x14004efbe  jz      short loc_14004EFDB
0x14004efc0  test    byte ptr [rcx+1Ch], 1
0x14004efc4  jz      short loc_14004EFDB
0x14004efc6  mov     rcx, [rcx+10h]
0x14004efca  lea     r8, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids
0x14004efd1  mov     edx, 24h ; '$'
0x14004efd6  call    WPP_SF_
0x14004efdb  mov     eax, 80070057h
0x14004efe0  mov     rcx, [rbp+1C0h+var_50]
0x14004efe7  xor     rcx, rsp; StackCookie
0x14004efea  call    __security_check_cookie
0x14004efef  add     rsp, 288h
0x14004eff6  pop     r15
0x14004eff8  pop     r14
0x14004effa  pop     r13
0x14004effc  pop     r12
0x14004effe  pop     rdi
0x14004efff  pop     rsi
0x14004f000  pop     rbx
0x14004f001  pop     rbp
0x14004f002  retn
```
