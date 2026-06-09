# midiStreamOpen

- ea: `0x180017d30`
- end: `0x1800183ae`
- name: `midiStreamOpen`
- size: `1662`
- prototype: `MMRESULT __stdcall(LPHMIDISTRM phms, LPUINT puDeviceID, DWORD cMidi, DWORD_PTR dwCallback, DWORD_PTR dwInstance, DWORD fdwOpen)`
- caller_count: `0`
- callee_count: `18`
- tags: ``

## callees

- `0x180001b70`
- `0x180007d70`
- `0x18000aef0`
- `0x18000c570`
- `0x18000e0d0`
- `0x18000e828`
- `0x1800106c0`
- `0x180011dac`
- `0x180012d08`
- `0x180012d30`
- `0x1800174ec`
- `0x180017578`
- `0x180017cc0`
- `0x180017d30`
- `0x1800194d0`
- `0x18001dc78`
- `0x18001fb58`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001827a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001827a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017e66`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017e66`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180018183`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180018183`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017e53`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017e53`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800182d3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800182d3`

## pseudocode

```c
MMRESULT __stdcall midiStreamOpen(
        LPHMIDISTRM phms,
        LPUINT puDeviceID,
        DWORD cMidi,
        DWORD_PTR dwCallback,
        DWORD_PTR dwInstance,
        DWORD fdwOpen)
{
  LPHMIDISTRM v6; // rax
  HDRVR v11; // r14
  MMRESULT DevCapsA; // ebx
  __int64 v13; // r15
  __int64 v14; // rax
  HDRVR v15; // rdi
  PVOID *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r8
  MMRESULT v19; // eax
  struct HDRVR__ *v20; // r8
  int v21; // ecx
  HDRVR v22; // rdi
  __int64 (__fastcall *v23)(_QWORD, __int64, HDRVR, struct HDRVR__ *, __int64); // rax
  int v24; // ecx
  HDRVR v25; // rsi
  PVOID *v26; // rcx
  struct _MMDRV **v27; // rax
  unsigned int v28; // r12d
  struct _MMDRV **v29; // rsi
  unsigned int v30; // eax
  unsigned int i; // esi
  unsigned int v32; // [rsp+40h] [rbp-79h]
  struct _MMDRV **v34; // [rsp+50h] [rbp-69h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-61h]
  __int64 v36; // [rsp+60h] [rbp-59h] BYREF
  LPHMIDISTRM v37; // [rsp+68h] [rbp-51h]
  __int64 v38; // [rsp+70h] [rbp-49h]
  struct tagMIDIOUTCAPSA pmoc; // [rsp+78h] [rbp-41h] BYREF

  v37 = phms;
  v6 = phms;
  memset(&pmoc, 0, sizeof(pmoc));
  if ( !phms )
    return 11;
  if ( dwCallback )
  {
    if ( !(unsigned int)ValidateCallbackType(dwCallback, HIWORD(fdwOpen)) )
      return 11;
    v6 = v37;
  }
  if ( !puDeviceID )
  {
    if ( !cMidi )
      *v6 = 0;
    return 11;
  }
  *v6 = 0;
  if ( cMidi != 1 )
    return 11;
  v38 = NewHandle(9);
  v11 = (HDRVR)v38;
  if ( !v38 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_df1b99d7603f3114e281f38f1879dcaa_Traceguids);
    }
    return 7;
  }
  LeaveCriticalSection(&HandleListCritSec);
  hMem = LocalAlloc(0x40u, 0x2Cu);
  if ( !hMem )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_df1b99d7603f3114e281f38f1879dcaa_Traceguids);
    }
    DevCapsA = 7;
    v13 = v38;
    goto LABEL_78;
  }
  DevCapsA = 0;
  *(_QWORD *)(v38 + 16) = dwInstance;
  v13 = (__int64)v11;
  *(_DWORD *)v11 = fdwOpen;
  v14 = 0;
  *((_QWORD *)v11 + 1) = dwCallback;
  *((_DWORD *)v11 + 7) = 1;
  v15 = v11 + 8;
  v16 = (PVOID *)WPP_GLOBAL_Control;
  while ( 1 )
  {
    v32 = v14;
    if ( (_DWORD)v14 )
      break;
    if ( v16 != &WPP_GLOBAL_Control && (*((_DWORD *)v16 + 7) & 0x400000) != 0 && *((_BYTE *)v16 + 25) )
    {
      WPP_SF_D(v16[2], 15, &WPP_df1b99d7603f3114e281f38f1879dcaa_Traceguids, *((unsigned int *)v15 + 8));
      v14 = v32;
    }
    if ( puDeviceID[v14] == -2 )
    {
      DevCapsA = 2;
      goto LABEL_78;
    }
    DevCapsA = midiOutGetDevCapsA(puDeviceID[v14], &pmoc, 0x34u);
    if ( DevCapsA )
      goto LABEL_50;
    if ( (pmoc.dwSupport & 8) == 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_df1b99d7603f3114e281f38f1879dcaa_Traceguids, v32);
      }
      *((_DWORD *)v15 + 8) |= 1u;
      *(_QWORD *)v15 = 0;
      *((_DWORD *)v15 + 2) = puDeviceID[v32];
      goto LABEL_45;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_DL(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, v18, v32, pmoc.dwSupport);
    }
    v36 = 0;
    LODWORD(v34) = 0;
    v19 = midiReferenceDriverById(&midioutdrvZ, puDeviceID[v32], &v36, &v34);
    DevCapsA = v19;
    if ( v19 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_df1b99d7603f3114e281f38f1879dcaa_Traceguids, v19);
LABEL_50:
      puDeviceID[v32] = -2;
      goto LABEL_78;
    }
    *(_QWORD *)v15 = v36;
    *((_DWORD *)v15 + 2) = (_DWORD)v34;
    v16 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_P(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v19 + 18,
        &WPP_df1b99d7603f3114e281f38f1879dcaa_Traceguids,
        *(_QWORD *)v15);
LABEL_45:
      v16 = (PVOID *)WPP_GLOBAL_Control;
    }
    v14 = v32 + 1;
    v15 += 20;
  }
  v20 = (struct HDRVR__ *)hMem;
  *(_QWORD *)hMem = v11;
  *((_QWORD *)v20 + 1) = midiOutStreamCallback;
  *((_QWORD *)v20 + 2) = 0;
  *((_DWORD *)v11 + 6) = 0;
LABEL_53:
  v21 = 0;
  v22 = v11 + 8;
  while ( !v21 )
  {
    if ( ((_BYTE)v22[8] & 4) == 0 )
    {
      *((_DWORD *)v20 + 8) = 0;
      v20[10] = v22[2];
      *((_DWORD *)v20 + 9) = v21;
      *((_DWORD *)v20 + 8) = 1;
      *((_DWORD *)v22 + 8) |= 2u;
      if ( ((_BYTE)v22[8] & 1) != 0 )
      {
        DevCapsA = mseMessage(3u, (struct midiemu_tag *)(v22 + 6), (unsigned __int8 *)v20, 0x30000u);
        if ( !DevCapsA )
          goto LABEL_61;
LABEL_67:
        puDeviceID[((int)v22 - (int)v11 - 32) / 80] = -2;
        goto LABEL_78;
      }
      v23 = *(__int64 (__fastcall **)(_QWORD, __int64, HDRVR, struct HDRVR__ *, __int64))(*(_QWORD *)v22 + 80LL);
      *((_QWORD *)v22 + 2) = v23;
      DevCapsA = v23(0, 3, v22 + 6, v20, 196610);
      if ( DevCapsA )
        goto LABEL_67;
      _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)v22 + 92LL), 1u);
LABEL_61:
      ++*((_DWORD *)v11 + 6);
      v24 = 0;
      LODWORD(v34) = 0;
      v25 = v11 + 8;
      do
      {
        if ( *(_QWORD *)v25 == *(_QWORD *)v22 )
        {
          *((_DWORD *)v25 + 8) |= 4u;
          if ( ((_BYTE)v22[8] & 1) == 0 )
          {
            InitializeCriticalSection((LPCRITICAL_SECTION)v25 + 1);
            *((_DWORD *)v25 + 8) |= 8u;
            v24 = (int)v34;
          }
        }
        ++v24;
        v25 += 20;
        LODWORD(v34) = v24;
      }
      while ( !v24 );
      v20 = (struct HDRVR__ *)hMem;
      goto LABEL_53;
    }
    ++v21;
    v22 += 20;
  }
  if ( CreatehwndNotify() )
  {
    v26 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v26 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_df1b99d7603f3114e281f38f1879dcaa_Traceguids);
      v26 = (PVOID *)WPP_GLOBAL_Control;
    }
    DevCapsA = 1;
  }
  if ( v26 != &WPP_GLOBAL_Control && (*((_DWORD *)v26 + 7) & 0x400000) != 0 && *((_BYTE *)v26 + 25) >= 2u )
    WPP_SF_q(v26[2], 21, &WPP_df1b99d7603f3114e281f38f1879dcaa_Traceguids, v11);
LABEL_78:
  v27 = (struct _MMDRV **)(v11 + 8);
  v34 = (struct _MMDRV **)(v11 + 8);
  if ( hMem )
  {
    LocalFree(hMem);
    v27 = v34;
  }
  if ( !DevCapsA )
  {
    *v37 = (HMIDISTRM)v11;
    DriverCallback(*((_QWORD *)v11 + 1), *((unsigned __int16 *)v11 + 1), v11, 0x3C7u, *((_QWORD *)v11 + 2), 0, 0);
    goto LABEL_95;
  }
  v28 = 0;
  v29 = v27;
  if ( *(_DWORD *)(v13 + 28) )
  {
    do
    {
      if ( ((_BYTE)v29[4] & 6) == 6 )
      {
        v30 = midiStreamMessage(v29, 4, 0);
        if ( v30 || ((_BYTE)v29[4] & 1) != 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_df1b99d7603f3114e281f38f1879dcaa_Traceguids, v30);
          }
        }
        else
        {
          if ( ((_BYTE)v29[4] & 8) != 0 )
          {
            DeleteCriticalSection((LPCRITICAL_SECTION)v29 + 1);
            *((_DWORD *)v29 + 8) &= ~8u;
          }
          mregDecUsagePtr(*v29);
        }
      }
      ++v28;
      v29 += 10;
    }
    while ( v28 < *(_DWORD *)(v13 + 28) );
    v11 = (HDRVR)v38;
LABEL_95:
    v27 = v34;
  }
  for ( i = 0; i < *(_DWORD *)(v13 + 28); v34 = v27 )
  {
    if ( *v27 )
    {
      mregDecUsagePtr(*v27);
      v27 = v34;
    }
    v27 += 10;
    ++i;
  }
  if ( DevCapsA )
    FreeHandle(v11);
  return DevCapsA;
}

```

## disassembly

```asm
0x180017d30  push    rbp
0x180017d32  push    rbx
0x180017d33  push    rsi
0x180017d34  push    rdi
0x180017d35  push    r12
0x180017d37  push    r13
0x180017d39  push    r14
0x180017d3b  push    r15
0x180017d3d  lea     rbp, [rsp-0Fh]
0x180017d42  sub     rsp, 0C8h
0x180017d49  mov     rax, cs:__security_cookie
0x180017d50  xor     rax, rsp
0x180017d53  mov     [rbp+47h+var_50], rax
0x180017d57  xorps   xmm0, xmm0
0x180017d5a  mov     [rbp+47h+var_98], rcx
0x180017d5e  mov     rax, rcx
0x180017d61  mov     [rbp+47h+var_B8], rdx
0x180017d65  xor     ecx, ecx
0x180017d67  mov     rdi, r9
0x180017d6a  mov     [rbp+47h+pmoc.dwSupport], ecx
0x180017d6d  mov     r12d, r8d
0x180017d70  mov     rbx, rdx
0x180017d73  movups  xmmword ptr [rbp+47h+pmoc.wMid], xmm0
0x180017d77  movups  xmmword ptr [rbp+47h+pmoc.szPname+8], xmm0
0x180017d7b  movups  xmmword ptr [rbp+47h+pmoc.szPname+18h], xmm0
0x180017d7f  test    rax, rax
0x180017d82  jz      short loc_180017DAE
0x180017d84  mov     esi, [rbp+47h+fdwOpen]
0x180017d87  test    r9, r9
0x180017d8a  jz      short loc_180017DA1
0x180017d8c  mov     edx, esi
0x180017d8e  mov     rcx, r9
0x180017d91  shr     edx, 10h
0x180017d94  call    ValidateCallbackType
0x180017d99  test    eax, eax
0x180017d9b  jz      short loc_180017DAE
0x180017d9d  mov     rax, [rbp+47h+var_98]
0x180017da1  test    rbx, rbx
0x180017da4  jnz     short loc_180017DD3
0x180017da6  test    r12d, r12d
0x180017da9  jnz     short loc_180017DAE
0x180017dab  mov     [rax], rbx
0x180017dae  mov     eax, 0Bh
0x180017db3  mov     rcx, [rbp+47h+var_50]
0x180017db7  xor     rcx, rsp; StackCookie
0x180017dba  call    __security_check_cookie
0x180017dbf  add     rsp, 0C8h
0x180017dc6  pop     r15
0x180017dc8  pop     r14
0x180017dca  pop     r13
0x180017dcc  pop     r12
0x180017dce  pop     rdi
0x180017dcf  pop     rsi
0x180017dd0  pop     rbx
0x180017dd1  pop     rbp
0x180017dd2  retn
0x180017dd3  mov     qword ptr [rax], 0
0x180017dda  cmp     r12d, 1
0x180017dde  jnz     short loc_180017DAE
0x180017de0  lea     r8d, [r12+r12*4]
0x180017de4  shl     r8d, 4
0x180017de8  add     r8d, 20h ; ' '
0x180017dec  cmp     r8d, 10000h
0x180017df3  jnb     short loc_180017DAE
0x180017df5  xor     edx, edx
0x180017df7  lea     ecx, [rdx+9]
0x180017dfa  call    NewHandle
0x180017dff  mov     [rbp+47h+var_90], rax
0x180017e03  mov     r14, rax
0x180017e06  test    rax, rax
0x180017e09  jnz     short loc_180017E4C
0x180017e0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180017e12  lea     rax, WPP_GLOBAL_Control
0x180017e19  cmp     rcx, rax
0x180017e1c  jz      short loc_180017E42
0x180017e1e  test    dword ptr [rcx+1Ch], 400000h
0x180017e25  jz      short loc_180017E42
0x180017e27  cmp     [rcx+19h], r12b
0x180017e2b  jb      short loc_180017E42
0x180017e2d  mov     rcx, [rcx+10h]
0x180017e31  lea     edx, [r12+0Ch]
0x180017e36  lea     r8, WPP_df1b99d7603f3114e281f38f1879dcaa_Traceguids
0x180017e3d  call    WPP_SF_
0x180017e42  mov     eax, 7
0x180017e47  jmp     loc_180017DB3
0x180017e4c  lea     rcx, HandleListCritSec; lpCriticalSection
0x180017e53  call    cs:__imp_LeaveCriticalSection
0x180017e59  lea     edx, ds:24h[r12*8]; uBytes
0x180017e61  mov     ecx, 40h ; '@'; uFlags
0x180017e66  call    cs:__imp_LocalAlloc
0x180017e6c  mov     [rbp+47h+hMem], rax
0x180017e70  test    rax, rax
0x180017e73  jnz     short loc_180017EB9
0x180017e75  mov     rcx, cs:WPP_GLOBAL_Control
0x180017e7c  lea     rax, WPP_GLOBAL_Control
0x180017e83  cmp     rcx, rax
0x180017e86  jz      short loc_180017EAC
0x180017e88  test    dword ptr [rcx+1Ch], 400000h
0x180017e8f  jz      short loc_180017EAC
0x180017e91  cmp     byte ptr [rcx+19h], 1
0x180017e95  jb      short loc_180017EAC
0x180017e97  mov     rcx, [rcx+10h]
0x180017e9b  lea     r8, WPP_df1b99d7603f3114e281f38f1879dcaa_Traceguids
0x180017ea2  mov     edx, 0Eh
0x180017ea7  call    WPP_SF_
0x180017eac  mov     ebx, 7
0x180017eb1  mov     r15, r14
0x180017eb4  jmp     loc_180018253
0x180017eb9  mov     rax, [rbp+47h+dwInstance]
0x180017ebd  xor     ebx, ebx
0x180017ebf  mov     [r14+10h], rax
0x180017ec3  mov     r15, r14
0x180017ec6  mov     [r14], esi
0x180017ec9  xor     eax, eax
0x180017ecb  mov     [r14+8], rdi
0x180017ecf  lea     rsi, WPP_GLOBAL_Control
0x180017ed6  mov     [r14+1Ch], r12d
0x180017eda  lea     rdi, [r14+20h]
0x180017ede  mov     rcx, cs:WPP_GLOBAL_Control
0x180017ee5  mov     r13d, 400000h
0x180017eeb  mov     [rbp+47h+var_C0], eax
0x180017eee  cmp     eax, r12d
0x180017ef1  jnb     loc_18001809B
0x180017ef7  cmp     rcx, rsi
0x180017efa  jz      short loc_180017F24
0x180017efc  test    [rcx+1Ch], r13d
0x180017f00  jz      short loc_180017F24
0x180017f02  cmp     byte ptr [rcx+19h], 1
0x180017f06  jb      short loc_180017F24
0x180017f08  mov     r9d, [rdi+20h]
0x180017f0c  lea     r8, WPP_df1b99d7603f3114e281f38f1879dcaa_Traceguids
0x180017f13  mov     rcx, [rcx+10h]
0x180017f17  mov     edx, 0Fh
0x180017f1c  call    WPP_SF_D
0x180017f21  mov     eax, [rbp+47h+var_C0]
0x180017f24  mov     rcx, [rbp+47h+var_B8]
0x180017f28  cmp     dword ptr [rcx+rax*4], 0FFFFFFFEh
0x180017f2c  jz      loc_180018091
0x180017f32  mov     ecx, [rcx+rax*4]; uDeviceID
0x180017f35  lea     rdx, [rbp+47h+pmoc]; pmoc
0x180017f39  mov     r8d, 34h ; '4'; cbmoc
0x180017f3f  call    midiOutGetDevCapsA
0x180017f44  mov     ebx, eax
0x180017f46  test    eax, eax
0x180017f48  jnz     loc_18001807E
0x180017f4e  mov     eax, [rbp+47h+pmoc.dwSupport]
0x180017f51  test    al, 8
0x180017f53  jz      loc_180017FF6
0x180017f59  mov     rcx, cs:WPP_GLOBAL_Control
0x180017f60  cmp     rcx, rsi
0x180017f63  jz      short loc_180017F82
0x180017f65  test    [rcx+1Ch], r13d
0x180017f69  jz      short loc_180017F82
0x180017f6b  cmp     byte ptr [rcx+19h], 1
0x180017f6f  jb      short loc_180017F82
0x180017f71  mov     r9d, [rbp+47h+var_C0]
0x180017f75  mov     rcx, [rcx+10h]
0x180017f79  mov     dword ptr [rsp+100h+dwUser], eax
0x180017f7d  call    WPP_SF_DL
0x180017f82  mov     ecx, [rbp+47h+var_C0]
0x180017f85  lea     r9, [rbp+47h+var_B0]
0x180017f89  mov     rdx, [rbp+47h+var_B8]
0x180017f8d  lea     r8, [rbp+47h+var_A0]
0x180017f91  mov     [rbp+47h+var_A0], 0
0x180017f99  mov     dword ptr [rbp+47h+var_B0], 0
0x180017fa0  mov     edx, [rdx+rcx*4]
0x180017fa3  lea     rcx, midioutdrvZ
0x180017faa  call    midiReferenceDriverById
0x180017faf  mov     ebx, eax
0x180017fb1  test    eax, eax
0x180017fb3  jnz     loc_180018054
0x180017fb9  mov     rax, [rbp+47h+var_A0]
0x180017fbd  mov     [rdi], rax
0x180017fc0  mov     eax, dword ptr [rbp+47h+var_B0]
0x180017fc3  mov     [rdi+8], eax
0x180017fc6  mov     rcx, cs:WPP_GLOBAL_Control
0x180017fcd  cmp     rcx, rsi
0x180017fd0  jz      short loc_180018046
0x180017fd2  test    [rcx+1Ch], r13d
0x180017fd6  jz      short loc_180018046
0x180017fd8  cmp     byte ptr [rcx+19h], 1
0x180017fdc  jb      short loc_180018046
0x180017fde  mov     r9, [rdi]
0x180017fe1  lea     edx, [rbx+12h]
0x180017fe4  mov     rcx, [rcx+10h]
0x180017fe8  lea     r8, WPP_df1b99d7603f3114e281f38f1879dcaa_Traceguids
0x180017fef  call    WPP_SF_P
0x180017ff4  jmp     short loc_18001803F
0x180017ff6  mov     rcx, cs:WPP_GLOBAL_Control
0x180017ffd  cmp     rcx, rsi
0x180018000  jz      short loc_180018027
0x180018002  test    [rcx+1Ch], r13d
0x180018006  jz      short loc_180018027
0x180018008  cmp     byte ptr [rcx+19h], 1
0x18001800c  jb      short loc_180018027
0x18001800e  mov     r9d, [rbp+47h+var_C0]
0x180018012  lea     r8, WPP_df1b99d7603f3114e281f38f1879dcaa_Traceguids
0x180018019  mov     rcx, [rcx+10h]
0x18001801d  mov     edx, 13h
0x180018022  call    WPP_SF_D
0x180018027  mov     ecx, [rbp+47h+var_C0]
0x18001802a  mov     rdx, [rbp+47h+var_B8]
0x18001802e  or      dword ptr [rdi+20h], 1
0x180018032  mov     qword ptr [rdi], 0
0x180018039  mov     eax, [rdx+rcx*4]
0x18001803c  mov     [rdi+8], eax
0x18001803f  mov     rcx, cs:WPP_GLOBAL_Control
0x180018046  mov     eax, [rbp+47h+var_C0]
0x180018049  inc     eax
0x18001804b  add     rdi, 50h ; 'P'
0x18001804f  jmp     loc_180017EEB
0x180018054  mov     rcx, cs:WPP_GLOBAL_Control
0x18001805b  cmp     rcx, rsi
0x18001805e  jz      short loc_18001807E
0x180018060  test    [rcx+1Ch], r13d
0x180018064  jz      short loc_18001807E
0x180018066  mov     rcx, [rcx+10h]
0x18001806a  lea     r8, WPP_df1b99d7603f3114e281f38f1879dcaa_Traceguids
0x180018071  mov     edx, 11h
0x180018076  mov     r9d, eax
0x180018079  call    WPP_SF_D
0x18001807e  mov     ecx, [rbp+47h+var_C0]
0x180018081  mov     rdx, [rbp+47h+var_B8]
0x180018085  mov     dword ptr [rdx+rcx*4], 0FFFFFFFEh
0x18001808c  jmp     loc_180018253
0x180018091  mov     ebx, 2
0x180018096  jmp     loc_180018253
0x18001809b  mov     r8, [rbp+47h+hMem]; unsigned __int8 *
0x18001809f  lea     rax, midiOutStreamCallback
0x1800180a6  mov     [r8], r14
0x1800180a9  mov     [r8+8], rax
0x1800180ad  mov     qword ptr [r8+10h], 0
0x1800180b5  mov     dword ptr [r14+18h], 0
0x1800180bd  lea     rdx, [r14+20h]
0x1800180c1  xor     ecx, ecx
0x1800180c3  mov     rdi, rdx
0x1800180c6  lea     esi, [rcx+1]
0x1800180c9  cmp     ecx, r12d
0x1800180cc  jnb     loc_1800181D8
0x1800180d2  test    byte ptr [rdi+20h], 4
0x1800180d6  jz      short loc_1800180E0
0x1800180d8  add     ecx, esi
0x1800180da  add     rdi, 50h ; 'P'
0x1800180de  jmp     short loc_1800180C9
0x1800180e0  mov     dword ptr [r8+20h], 0
0x1800180e8  lea     rdx, [rdi+18h]; struct midiemu_tag *
0x1800180ec  mov     eax, [rdi+8]
0x1800180ef  mov     [r8+28h], eax
0x1800180f3  mov     [r8+24h], ecx
0x1800180f7  mov     [r8+20h], esi
0x1800180fb  or      dword ptr [rdi+20h], 2
0x1800180ff  test    [rdi+20h], sil
0x180018103  jnz     short loc_18001813A
0x180018105  mov     rax, [rdi]
0x180018108  mov     r9, r8
0x18001810b  mov     r8, rdx
0x18001810e  mov     [rsp+100h+dwUser], 30002h
0x180018117  mov     edx, 3
0x18001811c  xor     ecx, ecx
0x18001811e  mov     rax, [rax+50h]
0x180018122  mov     [rdi+10h], rax
0x180018126  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001812b  mov     ebx, eax
0x18001812d  test    eax, eax
0x18001812f  jnz     short loc_1800181A7
0x180018131  mov     rax, [rdi]
0x180018134  lock add [rax+5Ch], esi
0x180018138  jmp     short loc_180018150
0x18001813a  mov     ecx, 3; uMsg
0x18001813f  mov     r9d, 30000h; unsigned int
0x180018145  call    mseMessage
0x18001814a  mov     ebx, eax
0x18001814c  test    eax, eax
0x18001814e  jnz     short loc_1800181A7
0x180018150  add     [r14+18h], esi
0x180018154  lea     rdx, [r14+20h]
0x180018158  mov     r8, [rbp+47h+hMem]
0x18001815c  xor     ecx, ecx
0x18001815e  mov     dword ptr [rbp+47h+var_B0], ecx
0x180018161  mov     rsi, rdx
0x180018164  test    r12d, r12d
0x180018167  jz      loc_1800180C1
0x18001816d  mov     rax, [rdi]
0x180018170  cmp     [rsi], rax
0x180018173  jnz     short loc_180018190
0x180018175  or      dword ptr [rsi+20h], 4
0x180018179  test    byte ptr [rdi+20h], 1
0x18001817d  jnz     short loc_180018190
0x18001817f  lea     rcx, [rsi+28h]; lpCriticalSection
0x180018183  call    cs:__imp_InitializeCriticalSection
0x180018189  or      dword ptr [rsi+20h], 8
0x18001818d  mov     ecx, dword ptr [rbp+47h+var_B0]
0x180018190  inc     ecx
0x180018192  add     rsi, 50h ; 'P'
0x180018196  mov     dword ptr [rbp+47h+var_B0], ecx
0x180018199  cmp     ecx, r12d
0x18001819c  jb      short loc_18001816D
0x18001819e  mov     r8, [rbp+47h+hMem]
0x1800181a2  jmp     loc_1800180BD
0x1800181a7  mov     rcx, [rbp+47h+var_B8]
  ... truncated ...
```
