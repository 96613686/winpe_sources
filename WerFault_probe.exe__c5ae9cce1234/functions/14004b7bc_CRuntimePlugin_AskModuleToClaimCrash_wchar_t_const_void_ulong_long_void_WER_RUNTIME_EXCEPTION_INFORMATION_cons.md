# CRuntimePlugin::AskModuleToClaimCrash(wchar_t const *,void *,ulong *,long (**)(void *,_WER_RUNTIME_EXCEPTION_INFORMATION * const,ulong,wchar_t *,ulong *,wchar_t *,ulong *),long (**)(void *,_WER_RUNTIME_EXCEPTION_INFORMATION * const,int *,wchar_t *,ulong *,int *),tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>> *)

- ea: `0x14004b7bc`
- end: `0x14004bb3d`
- name: `?AskModuleToClaimCrash@CRuntimePlugin@@AEAAJPEB_WPEAXPEAKPEAP6AJ1QEAU_WER_RUNTIME_EXCEPTION_INFORMATION@@KPEA_W242@ZPEAP6AJ13PEAH426@ZPEAV?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@@Z`
- size: `897`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x14004bb6c`

## callees

- `0x140002470`
- `0x14000c8a0`
- `0x14001444c`
- `0x140014474`
- `0x1400159cc`
- `0x14004b7bc`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14004b868`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14004bada`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14004b868`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14004bada`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004b8ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004b9fe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004ba8e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004b8ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004b9fe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004ba8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004b873`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004b873`
- `ntdll!RtlSetThreadErrorMode` at `0x14004b84e`
- `ntdll!RtlSetThreadErrorMode` at `0x14004b898`
- `ntdll!RtlSetThreadErrorMode` at `0x14004b84e`
- `ntdll!RtlSetThreadErrorMode` at `0x14004b898`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x14004b857`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x14004b857`

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
          &WPP_f577d8521c9b39ef05153804ed8add08_Traceguids,
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
      WPP_SF_(*((_QWORD *)v16 + 2), v17, &WPP_f577d8521c9b39ef05153804ed8add08_Traceguids);
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
        WPP_SF_(*((_QWORD *)v18 + 2), v19, &WPP_f577d8521c9b39ef05153804ed8add08_Traceguids);
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
          (unsigned int)&WPP_f577d8521c9b39ef05153804ed8add08_Traceguids,
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
                                v30,
                                v22) )
        {
          v23 = GetProcAddress(*a7, "OutOfProcessExceptionEventDebuggerLaunchCallback");
          *v29 = v23;
          if ( !v23
            && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_f577d8521c9b39ef05153804ed8add08_Traceguids);
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_f577d8521c9b39ef05153804ed8add08_Traceguids);
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x14004b7bc  push    rbp
0x14004b7be  push    rbx
0x14004b7bf  push    rsi
0x14004b7c0  push    rdi
0x14004b7c1  push    r12
0x14004b7c3  push    r13
0x14004b7c5  push    r14
0x14004b7c7  push    r15
0x14004b7c9  lea     rbp, [rsp-188h]
0x14004b7d1  sub     rsp, 288h
0x14004b7d8  mov     rax, cs:__security_cookie
0x14004b7df  xor     rax, rsp
0x14004b7e2  mov     [rbp+1C0h+var_50], rax
0x14004b7e9  mov     rax, [rbp+1C0h+arg_28]
0x14004b7f0  xor     ebx, ebx
0x14004b7f2  mov     rsi, [rbp+1C0h+arg_30]
0x14004b7f9  mov     rdi, r9
0x14004b7fc  mov     r15, [rbp+1C0h+arg_20]
0x14004b803  mov     r12, r8
0x14004b806  mov     [rsp+2C0h+var_270], rax
0x14004b80b  mov     r14, rdx
0x14004b80e  mov     [rsp+2C0h+OldMode], ebx
0x14004b812  mov     r13, rcx
0x14004b815  mov     [rsp+2C0h+var_280], ebx
0x14004b819  mov     [rsp+2C0h+var_278], ebx
0x14004b81d  test    r9, r9
0x14004b820  jz      loc_14004BAE7
0x14004b826  test    rsi, rsi
0x14004b829  jz      loc_14004BAE7
0x14004b82f  test    r15, r15
0x14004b832  jz      loc_14004BAE7
0x14004b838  test    rdx, rdx
0x14004b83b  jz      loc_14004BAE7
0x14004b841  lea     rdx, [rsp+2C0h+OldMode]; OldMode
0x14004b846  mov     [rsp+2C0h+var_260], bx
0x14004b84b  lea     ecx, [rbx+10h]; NewMode
0x14004b84e  call    cs:__imp_RtlSetThreadErrorMode
0x14004b854  mov     rcx, r14; lpLibFileName
0x14004b857  call    cs:__imp_LoadLibraryW
0x14004b85d  mov     rcx, [rsi]; hLibModule
0x14004b860  mov     [rsi], rax
0x14004b863  test    rcx, rcx
0x14004b866  jz      short loc_14004B86E
0x14004b868  call    cs:__imp_FreeLibrary
0x14004b86e  cmp     [rsi], rbx
0x14004b871  jnz     short loc_14004B892
0x14004b873  call    cs:__imp_GetLastError
0x14004b879  mov     ebx, eax
0x14004b87b  test    eax, eax
0x14004b87d  jle     short loc_14004B888
0x14004b87f  movzx   ebx, ax
0x14004b882  or      ebx, 80070000h
0x14004b888  test    ebx, ebx
0x14004b88a  mov     eax, 80004005h
0x14004b88f  cmovns  ebx, eax
0x14004b892  mov     ecx, [rsp+2C0h+OldMode]; NewMode
0x14004b896  xor     edx, edx; OldMode
0x14004b898  call    cs:__imp_RtlSetThreadErrorMode
0x14004b89e  test    ebx, ebx
0x14004b8a0  jns     short loc_14004B8E0
0x14004b8a2  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b8a9  lea     rdi, WPP_GLOBAL_Control
0x14004b8b0  cmp     rcx, rdi
0x14004b8b3  jz      loc_14004BACD
0x14004b8b9  test    byte ptr [rcx+1Ch], 1
0x14004b8bd  jz      loc_14004BACD
0x14004b8c3  mov     rcx, [rcx+10h]
0x14004b8c7  lea     r8, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids
0x14004b8ce  mov     edx, 25h ; '%'
0x14004b8d3  mov     r9d, ebx
0x14004b8d6  call    WPP_SF_d
0x14004b8db  jmp     loc_14004BACD
0x14004b8e0  mov     rcx, [rsi]; hModule
0x14004b8e3  lea     rdx, aOutofprocessex_0; "OutOfProcessExceptionEventCallback"
0x14004b8ea  call    cs:__imp_GetProcAddress
0x14004b8f0  test    rax, rax
0x14004b8f3  jnz     short loc_14004B92B
0x14004b8f5  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b8fc  lea     rdi, WPP_GLOBAL_Control
0x14004b903  cmp     rcx, rdi
0x14004b906  jz      short loc_14004B921
0x14004b908  test    byte ptr [rcx+1Ch], 1
0x14004b90c  jz      short loc_14004B921
0x14004b90e  lea     edx, [rax+26h]
0x14004b911  mov     rcx, [rcx+10h]
0x14004b915  lea     r8, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids
0x14004b91c  call    WPP_SF_
0x14004b921  mov     ebx, 80004005h
0x14004b926  jmp     loc_14004BACD
0x14004b92b  lea     rcx, [rsp+2C0h+var_278]
0x14004b930  mov     [rsp+2C0h+var_298], rdi
0x14004b935  mov     [rsp+2C0h+var_2A0], rcx
0x14004b93a  lea     rdx, [r13+350h]
0x14004b941  mov     rcx, r12
0x14004b944  mov     [rsp+2C0h+var_278], 104h
0x14004b94c  lea     r9, [rsp+2C0h+var_260]
0x14004b951  lea     r8, [rsp+2C0h+var_280]
0x14004b956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004b95b  mov     ebx, eax
0x14004b95d  test    eax, eax
0x14004b95f  jns     short loc_14004B98C
0x14004b961  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b968  lea     rdi, WPP_GLOBAL_Control
0x14004b96f  cmp     rcx, rdi
0x14004b972  jz      loc_14004BACD
0x14004b978  test    byte ptr [rcx+1Ch], 1
0x14004b97c  jz      loc_14004BACD
0x14004b982  mov     edx, 27h ; '''
0x14004b987  jmp     loc_14004BA72
0x14004b98c  mov     eax, [rsp+2C0h+var_280]
0x14004b990  xor     ebx, ebx
0x14004b992  test    eax, eax
0x14004b994  jz      loc_14004BAC8
0x14004b99a  lea     rdi, WPP_GLOBAL_Control
0x14004b9a1  cmp     [r13+0AF8h], ebx
0x14004b9a8  jz      short loc_14004B9EC
0x14004b9aa  mov     [rsp+2C0h+var_280], ebx
0x14004b9ae  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b9b5  cmp     rcx, rdi
0x14004b9b8  jz      loc_14004BAC8
0x14004b9be  test    byte ptr [rcx+1Ch], 4
0x14004b9c2  jz      loc_14004BAC8
0x14004b9c8  mov     rcx, [rcx+10h]
0x14004b9cc  lea     rax, [rsp+2C0h+var_260]
0x14004b9d1  lea     edx, [rbx+28h]
0x14004b9d4  mov     [rsp+2C0h+var_2A0], rax
0x14004b9d9  mov     r9, r14
0x14004b9dc  lea     r8, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids
0x14004b9e3  call    WPP_SF_SS
0x14004b9e8  mov     eax, [rsp+2C0h+var_280]
0x14004b9ec  test    eax, eax
0x14004b9ee  jz      loc_14004BAC8
0x14004b9f4  mov     rcx, [rsi]; hModule
0x14004b9f7  lea     rdx, aOutofprocessex_1; "OutOfProcessExceptionEventSignatureCall"...
0x14004b9fe  call    cs:__imp_GetProcAddress
0x14004ba04  mov     [r15], rax
0x14004ba07  test    rax, rax
0x14004ba0a  jnz     short loc_14004BA2E
0x14004ba0c  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ba13  cmp     rcx, rdi
0x14004ba16  jz      loc_14004B921
0x14004ba1c  test    byte ptr [rcx+1Ch], 1
0x14004ba20  jz      loc_14004B921
0x14004ba26  lea     edx, [rax+29h]
0x14004ba29  jmp     loc_14004B911
0x14004ba2e  lea     rax, [rsp+2C0h+var_260]
0x14004ba33  or      r8, 0FFFFFFFFFFFFFFFFh
0x14004ba37  inc     r8
0x14004ba3a  cmp     [rax+r8*2], bx
0x14004ba3f  jnz     short loc_14004BA37
0x14004ba41  lea     rcx, [r13+2D8h]
0x14004ba48  lea     rdx, [rsp+2C0h+var_260]
0x14004ba4d  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14004ba52  test    al, al
0x14004ba54  jnz     short loc_14004BA84
0x14004ba56  mov     ebx, 8007000Eh
0x14004ba5b  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ba62  cmp     rcx, rdi
0x14004ba65  jz      short loc_14004BACD
0x14004ba67  test    byte ptr [rcx+1Ch], 1
0x14004ba6b  jz      short loc_14004BACD
0x14004ba6d  mov     edx, 2Ah ; '*'
0x14004ba72  mov     rcx, [rcx+10h]
0x14004ba76  lea     r8, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids
0x14004ba7d  call    WPP_SF_
0x14004ba82  jmp     short loc_14004BACD
0x14004ba84  mov     rcx, [rsi]; hModule
0x14004ba87  lea     rdx, aOutofprocessex; "OutOfProcessExceptionEventDebuggerLaunc"...
0x14004ba8e  call    cs:__imp_GetProcAddress
0x14004ba94  mov     rcx, [rsp+2C0h+var_270]
0x14004ba99  mov     [rcx], rax
0x14004ba9c  test    rax, rax
0x14004ba9f  jnz     short loc_14004BAE3
0x14004baa1  mov     rcx, cs:WPP_GLOBAL_Control
0x14004baa8  cmp     rcx, rdi
0x14004baab  jz      short loc_14004BAE3
0x14004baad  test    byte ptr [rcx+1Ch], 1
0x14004bab1  jz      short loc_14004BAE3
0x14004bab3  mov     rcx, [rcx+10h]
0x14004bab7  lea     edx, [rax+2Bh]
0x14004baba  lea     r8, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids
0x14004bac1  call    WPP_SF_
0x14004bac6  jmp     short loc_14004BAE3
0x14004bac8  mov     ebx, 80004001h
0x14004bacd  mov     rcx, [rsi]; hLibModule
0x14004bad0  xor     edi, edi
0x14004bad2  mov     [rsi], rdi
0x14004bad5  test    rcx, rcx
0x14004bad8  jz      short loc_14004BAE0
0x14004bada  call    cs:__imp_FreeLibrary
0x14004bae0  mov     [r15], rdi
0x14004bae3  mov     eax, ebx
0x14004bae5  jmp     short loc_14004BB1A
0x14004bae7  mov     rcx, cs:WPP_GLOBAL_Control
0x14004baee  lea     rdi, WPP_GLOBAL_Control
0x14004baf5  cmp     rcx, rdi
0x14004baf8  jz      short loc_14004BB15
0x14004bafa  test    byte ptr [rcx+1Ch], 1
0x14004bafe  jz      short loc_14004BB15
0x14004bb00  mov     rcx, [rcx+10h]
0x14004bb04  lea     r8, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids
0x14004bb0b  mov     edx, 24h ; '$'
0x14004bb10  call    WPP_SF_
0x14004bb15  mov     eax, 80070057h
0x14004bb1a  mov     rcx, [rbp+1C0h+var_50]
0x14004bb21  xor     rcx, rsp; StackCookie
0x14004bb24  call    __security_check_cookie
0x14004bb29  add     rsp, 288h
0x14004bb30  pop     r15
0x14004bb32  pop     r14
0x14004bb34  pop     r13
0x14004bb36  pop     r12
0x14004bb38  pop     rdi
0x14004bb39  pop     rsi
0x14004bb3a  pop     rbx
0x14004bb3b  pop     rbp
0x14004bb3c  retn
```
