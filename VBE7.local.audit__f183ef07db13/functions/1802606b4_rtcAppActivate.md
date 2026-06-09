# rtcAppActivate

- ea: `0x1802606b4`
- end: `0x180260b99`
- name: `rtcAppActivate`
- size: `1253`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation`

## callees

- `0x1800e6178`
- `0x1800e6188`
- `0x1800f09f0`
- `0x1801012ec`
- `0x180102a4c`
- `0x1801426d8`
- `0x18014275c`
- `0x18021221c`
- `0x18024b0b4`
- `0x18024b120`
- `0x18024cc30`
- `0x1802606b4`
- `0x180379520`
- `0x180398cd0`

## import_xrefs

- `MSVCR100!_mbsnicmp` at `0x180260879`
- `MSVCR100!_mbsnicmp` at `0x18026091f`
- `MSVCR100!_mbsnicmp` at `0x180260879`
- `MSVCR100!_mbsnicmp` at `0x18026091f`
- `KERNEL32!WideCharToMultiByte` at `0x1802607a6`
- `KERNEL32!WideCharToMultiByte` at `0x18026081c`
- `KERNEL32!WideCharToMultiByte` at `0x1802607a6`
- `KERNEL32!WideCharToMultiByte` at `0x18026081c`
- `USER32!GetWindowTextA` at `0x18026085e`
- `USER32!GetWindowTextA` at `0x1802608e4`
- `USER32!GetWindowTextA` at `0x18026085e`
- `USER32!GetWindowTextA` at `0x1802608e4`
- `USER32!SetForegroundWindow` at `0x180260b56`
- `USER32!SetForegroundWindow` at `0x180260b56`
- `USER32!GetDesktopWindow` at `0x180260822`
- `USER32!GetDesktopWindow` at `0x1802608a8`
- `USER32!GetDesktopWindow` at `0x180260969`
- `USER32!GetDesktopWindow` at `0x1802609e3`
- `USER32!GetDesktopWindow` at `0x180260822`
- `USER32!GetDesktopWindow` at `0x1802608a8`
- `USER32!GetDesktopWindow` at `0x180260969`
- `USER32!GetDesktopWindow` at `0x1802609e3`
- `USER32!IsWindowVisible` at `0x1802609b8`
- `USER32!IsWindowVisible` at `0x180260a67`
- `USER32!IsWindowVisible` at `0x180260ad1`
- `USER32!IsWindowVisible` at `0x1802609b8`
- `USER32!IsWindowVisible` at `0x180260a67`
- `USER32!IsWindowVisible` at `0x180260ad1`
- `USER32!SetFocus` at `0x180260b61`
- `USER32!SetFocus` at `0x180260b61`
- `USER32!GetWindow` at `0x180260830`
- `USER32!GetWindow` at `0x18026088f`
- `USER32!GetWindow` at `0x1802608b6`
- `USER32!GetWindow` at `0x180260935`
- `USER32!GetWindow` at `0x180260977`
- `USER32!GetWindow` at `0x1802609ce`
- `USER32!GetWindow` at `0x1802609f1`
- `USER32!GetWindow` at `0x180260a2a`
- `USER32!GetWindow` at `0x180260a7c`
- `USER32!GetWindow` at `0x180260a93`
- `USER32!GetWindow` at `0x180260ab0`
- `USER32!GetWindow` at `0x180260aec`
- `USER32!GetWindow` at `0x180260830`
- `USER32!GetWindow` at `0x18026088f`
- `USER32!GetWindow` at `0x1802608b6`
- `USER32!GetWindow` at `0x180260935`
- `USER32!GetWindow` at `0x180260977`
- `USER32!GetWindow` at `0x1802609ce`
- `USER32!GetWindow` at `0x1802609f1`
- `USER32!GetWindow` at `0x180260a2a`
- `USER32!GetWindow` at `0x180260a7c`
- `USER32!GetWindow` at `0x180260a93`
- `USER32!GetWindow` at `0x180260ab0`
- `USER32!GetWindow` at `0x180260aec`
- `USER32!AttachThreadInput` at `0x180260b4b`
- `USER32!AttachThreadInput` at `0x180260b7e`
- `USER32!AttachThreadInput` at `0x180260b4b`
- `USER32!AttachThreadInput` at `0x180260b7e`
- `USER32!IsWindowEnabled` at `0x1802609a9`
- `USER32!IsWindowEnabled` at `0x180260a58`
- `USER32!IsWindowEnabled` at `0x180260ac2`
- `USER32!IsWindowEnabled` at `0x1802609a9`
- `USER32!IsWindowEnabled` at `0x180260a58`
- `USER32!IsWindowEnabled` at `0x180260ac2`
- `USER32!GetWindowThreadProcessId` at `0x180260994`
- `USER32!GetWindowThreadProcessId` at `0x180260a0e`
- `USER32!GetWindowThreadProcessId` at `0x180260b3b`
- `USER32!GetWindowThreadProcessId` at `0x180260b71`
- `USER32!GetWindowThreadProcessId` at `0x180260994`
- `USER32!GetWindowThreadProcessId` at `0x180260a0e`
- `USER32!GetWindowThreadProcessId` at `0x180260b3b`
- `USER32!GetWindowThreadProcessId` at `0x180260b71`

## pseudocode

```c
BOOL __fastcall rtcAppActivate(__int64 a1, VARIANTARG *a2)
{
  int v2; // eax
  int v3; // eax
  HWND DesktopWindow; // rax
  HWND v5; // rax
  HWND v6; // rax
  HWND v7; // rax
  HWND v8; // rax
  struct EBAPP *v9; // rax
  DWORD WindowThreadProcessId; // eax
  DWORD v11; // eax
  HWND hWnd; // [rsp+40h] [rbp-270h]
  int cbMultiByte; // [rsp+48h] [rbp-268h]
  __int16 v15; // [rsp+4Ch] [rbp-264h]
  HWND i; // [rsp+50h] [rbp-260h]
  HWND Window; // [rsp+50h] [rbp-260h]
  CHAR *lpMultiByteStr; // [rsp+58h] [rbp-258h]
  DWORD dwProcessId; // [rsp+60h] [rbp-250h] BYREF
  __int16 IsMissing; // [rsp+64h] [rbp-24Ch]
  int WindowTextA; // [rsp+68h] [rbp-248h]
  int v22; // [rsp+6Ch] [rbp-244h]
  DWORD v23; // [rsp+70h] [rbp-240h] BYREF
  VARIANTARG *pvarg; // [rsp+78h] [rbp-238h]
  __int16 v25[16]; // [rsp+80h] [rbp-230h] BYREF
  CHAR String[512]; // [rsp+A0h] [rbp-210h] BYREF
  VARIANTARG *v28; // [rsp+2C0h] [rbp+10h]

  IsMissing = rtIsMissing(a2);
  pvarg = (VARIANTARG *)((char *)PebthreadCur() + 152);
  v25[0] = 1;
  if ( IsMissing )
    v15 = 0;
  else
    v15 = rtI2FromVar(a2);
  v28 = (VARIANTARG *)AdjustObjVar(a1, v25);
  if ( v28->vt == 8 )
  {
    hWnd = (HWND)oFindWindow(0, v28->llVal);
    if ( !hWnd )
    {
      v2 = BstrLen(v28->llVal);
      cbMultiByte = WideCharToMultiByte(0, 0, v28->bstrVal, v2, 0, 0, 0, 0);
      if ( cbMultiByte )
      {
        lpMultiByteStr = (CHAR *)ProfMemAlloc(cbMultiByte);
        if ( lpMultiByteStr )
        {
          v3 = BstrLen(v28->llVal);
          WideCharToMultiByte(0, 0, v28->bstrVal, v3, lpMultiByteStr, cbMultiByte, 0, 0);
        }
      }
      else
      {
        lpMultiByteStr = 0;
      }
      DesktopWindow = GetDesktopWindow();
      for ( hWnd = GetWindow(DesktopWindow, 5u); hWnd; hWnd = GetWindow(hWnd, 2u) )
      {
        if ( !lpMultiByteStr )
          break;
        GetWindowTextA(hWnd, String, 511);
        if ( !_mbsnicmp((const unsigned __int8 *)lpMultiByteStr, (const unsigned __int8 *)String, cbMultiByte) )
          break;
      }
      if ( !hWnd )
      {
        v5 = GetDesktopWindow();
        for ( hWnd = GetWindow(v5, 5u); hWnd; hWnd = GetWindow(hWnd, 2u) )
        {
          if ( !lpMultiByteStr )
            break;
          WindowTextA = GetWindowTextA(hWnd, String, 511);
          if ( WindowTextA >= cbMultiByte
            && !_mbsnicmp(
                  (const unsigned __int8 *)lpMultiByteStr,
                  (const unsigned __int8 *)&String[WindowTextA - cbMultiByte],
                  cbMultiByte) )
          {
            break;
          }
        }
      }
      if ( lpMultiByteStr )
        ProfMemFree(lpMultiByteStr);
    }
  }
  else
  {
    v22 = rtI4FromVar(v28);
    v6 = GetDesktopWindow();
    for ( hWnd = GetWindow(v6, 5u); hWnd; hWnd = GetWindow(hWnd, 2u) )
    {
      GetWindowThreadProcessId(hWnd, &dwProcessId);
      if ( dwProcessId == v22 && IsWindowEnabled(hWnd) && IsWindowVisible(hWnd) )
        break;
    }
    if ( !hWnd )
    {
      v7 = GetDesktopWindow();
      for ( hWnd = GetWindow(v7, 5u); hWnd; hWnd = GetWindow(hWnd, 2u) )
      {
        GetWindowThreadProcessId(hWnd, &dwProcessId);
        if ( dwProcessId == v22 )
          break;
      }
    }
  }
  _vbaFreeVar(pvarg);
  if ( !hWnd )
    EbRaiseExceptionCode(5);
  if ( !IsWindowEnabled(hWnd) || !IsWindowVisible(hWnd) )
  {
    for ( i = GetWindow(hWnd, 0); i; i = v8 )
    {
      if ( GetWindow(i, 4u) == hWnd )
      {
        if ( IsWindowEnabled(i) && IsWindowVisible(i) )
          break;
        hWnd = i;
        Window = GetWindow(i, 0);
        v8 = GetWindow(Window, 2u);
      }
      else
      {
        v8 = GetWindow(i, 2u);
      }
    }
    if ( !i )
      EbRaiseExceptionCode(5);
    hWnd = i;
  }
  if ( v15 )
  {
    v9 = PebappCur();
    (*(void (**)(void))(*((_QWORD *)v9 + 7) + 296LL))();
  }
  WindowThreadProcessId = GetWindowThreadProcessId(hWnd, &v23);
  AttachThreadInput(0, WindowThreadProcessId, 1);
  SetForegroundWindow(hWnd);
  SetFocus(hWnd);
  v11 = GetWindowThreadProcessId(hWnd, &v23);
  return AttachThreadInput(0, v11, 0);
}

```

## disassembly

```asm
0x1802606b4  mov     [rsp-8+arg_8], rdx
0x1802606b9  mov     [rsp-8+arg_0], rcx
0x1802606be  push    rbp
0x1802606bf  mov     rbp, rsp
0x1802606c2  sub     rsp, 2B0h
0x1802606c9  mov     rax, cs:__security_cookie
0x1802606d0  xor     rax, rsp
0x1802606d3  mov     [rbp+var_10], rax
0x1802606d7  mov     rcx, [rbp+arg_8]
0x1802606db  call    rtIsMissing
0x1802606e0  mov     [rsp+2B0h+var_24C], ax
0x1802606e5  call    ?PebthreadCur@@YAPEAVEBTHREAD@@XZ; PebthreadCur(void)
0x1802606ea  add     rax, 98h
0x1802606f0  mov     [rsp+2B0h+pvarg], rax
0x1802606f5  mov     eax, 1
0x1802606fa  mov     [rsp+2B0h+var_230], ax
0x180260702  movsx   eax, [rsp+2B0h+var_24C]
0x180260707  test    eax, eax
0x180260709  jz      short loc_180260714
0x18026070b  xor     eax, eax
0x18026070d  mov     [rsp+2B0h+var_264], ax
0x180260712  jmp     short loc_180260722
0x180260714  mov     rcx, [rbp+arg_8]
0x180260718  call    rtI2FromVar
0x18026071d  mov     [rsp+2B0h+var_264], ax
0x180260722  lea     rdx, [rsp+2B0h+var_230]
0x18026072a  mov     rcx, [rbp+arg_0]
0x18026072e  call    AdjustObjVar
0x180260733  mov     [rbp+arg_0], rax
0x180260737  mov     rax, [rbp+arg_0]
0x18026073b  movzx   eax, word ptr [rax]
0x18026073e  cmp     eax, 8
0x180260741  jnz     loc_18026095C
0x180260747  mov     rax, [rbp+arg_0]
0x18026074b  mov     rdx, [rax+8]
0x18026074f  xor     ecx, ecx
0x180260751  call    oFindWindow
0x180260756  mov     [rsp+2B0h+hWnd], rax
0x18026075b  cmp     [rsp+2B0h+hWnd], 0
0x180260761  jnz     loc_180260957
0x180260767  mov     rax, [rbp+arg_0]
0x18026076b  mov     rcx, [rax+8]
0x18026076f  call    BstrLen
0x180260774  mov     [rsp+2B0h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18026077d  mov     [rsp+2B0h+lpDefaultChar], 0; lpDefaultChar
0x180260786  mov     [rsp+2B0h+cbMultiByte], 0; cbMultiByte
0x18026078e  mov     [rsp+2B0h+lpMultiByteStr], 0; lpMultiByteStr
0x180260797  mov     r9d, eax; cchWideChar
0x18026079a  mov     rax, [rbp+arg_0]
0x18026079e  mov     r8, [rax+8]; lpWideCharStr
0x1802607a2  xor     edx, edx; dwFlags
0x1802607a4  xor     ecx, ecx; CodePage
0x1802607a6  call    cs:__imp_WideCharToMultiByte
0x1802607ac  mov     [rsp+2B0h+var_268], eax
0x1802607b0  cmp     [rsp+2B0h+var_268], 0
0x1802607b5  jnz     short loc_1802607C2
0x1802607b7  mov     [rsp+2B0h+var_258], 0
0x1802607c0  jmp     short loc_180260822
0x1802607c2  movsxd  rax, [rsp+2B0h+var_268]
0x1802607c7  mov     rcx, rax
0x1802607ca  call    ProfMemAlloc
0x1802607cf  mov     [rsp+2B0h+var_258], rax
0x1802607d4  cmp     [rsp+2B0h+var_258], 0
0x1802607da  jz      short loc_180260822
0x1802607dc  mov     rax, [rbp+arg_0]
0x1802607e0  mov     rcx, [rax+8]
0x1802607e4  call    BstrLen
0x1802607e9  mov     [rsp+2B0h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x1802607f2  mov     [rsp+2B0h+lpDefaultChar], 0; lpDefaultChar
0x1802607fb  mov     ecx, [rsp+2B0h+var_268]
0x1802607ff  mov     [rsp+2B0h+cbMultiByte], ecx; cbMultiByte
0x180260803  mov     rcx, [rsp+2B0h+var_258]
0x180260808  mov     [rsp+2B0h+lpMultiByteStr], rcx; lpMultiByteStr
0x18026080d  mov     r9d, eax; cchWideChar
0x180260810  mov     rax, [rbp+arg_0]
0x180260814  mov     r8, [rax+8]; lpWideCharStr
0x180260818  xor     edx, edx; dwFlags
0x18026081a  xor     ecx, ecx; CodePage
0x18026081c  call    cs:__imp_WideCharToMultiByte
0x180260822  call    cs:__imp_GetDesktopWindow
0x180260828  mov     edx, 5; uCmd
0x18026082d  mov     rcx, rax; hWnd
0x180260830  call    cs:__imp_GetWindow
0x180260836  mov     [rsp+2B0h+hWnd], rax
0x18026083b  cmp     [rsp+2B0h+hWnd], 0
0x180260841  jz      short loc_18026089C
0x180260843  cmp     [rsp+2B0h+var_258], 0
0x180260849  jz      short loc_18026089C
0x18026084b  mov     r8d, 1FFh; nMaxCount
0x180260851  lea     rdx, [rsp+2B0h+String]; lpString
0x180260859  mov     rcx, [rsp+2B0h+hWnd]; hWnd
0x18026085e  call    cs:__imp_GetWindowTextA
0x180260864  movsxd  rax, [rsp+2B0h+var_268]
0x180260869  mov     r8, rax; MaxCount
0x18026086c  lea     rdx, [rsp+2B0h+String]; Str2
0x180260874  mov     rcx, [rsp+2B0h+var_258]; Str1
0x180260879  call    cs:__imp__mbsnicmp
0x18026087f  test    eax, eax
0x180260881  jnz     short loc_180260885
0x180260883  jmp     short loc_18026089C
0x180260885  mov     edx, 2; uCmd
0x18026088a  mov     rcx, [rsp+2B0h+hWnd]; hWnd
0x18026088f  call    cs:__imp_GetWindow
0x180260895  mov     [rsp+2B0h+hWnd], rax
0x18026089a  jmp     short loc_18026083B
0x18026089c  cmp     [rsp+2B0h+hWnd], 0
0x1802608a2  jnz     loc_180260945
0x1802608a8  call    cs:__imp_GetDesktopWindow
0x1802608ae  mov     edx, 5; uCmd
0x1802608b3  mov     rcx, rax; hWnd
0x1802608b6  call    cs:__imp_GetWindow
0x1802608bc  mov     [rsp+2B0h+hWnd], rax
0x1802608c1  cmp     [rsp+2B0h+hWnd], 0
0x1802608c7  jz      short loc_180260945
0x1802608c9  cmp     [rsp+2B0h+var_258], 0
0x1802608cf  jz      short loc_180260945
0x1802608d1  mov     r8d, 1FFh; nMaxCount
0x1802608d7  lea     rdx, [rsp+2B0h+String]; lpString
0x1802608df  mov     rcx, [rsp+2B0h+hWnd]; hWnd
0x1802608e4  call    cs:__imp_GetWindowTextA
0x1802608ea  mov     [rsp+2B0h+var_248], eax
0x1802608ee  mov     eax, [rsp+2B0h+var_268]
0x1802608f2  cmp     [rsp+2B0h+var_248], eax
0x1802608f6  jl      short loc_18026092B
0x1802608f8  movsxd  rax, [rsp+2B0h+var_268]
0x1802608fd  mov     ecx, [rsp+2B0h+var_268]
0x180260901  mov     edx, [rsp+2B0h+var_248]
0x180260905  sub     edx, ecx
0x180260907  mov     ecx, edx
0x180260909  movsxd  rcx, ecx
0x18026090c  lea     rcx, [rsp+rcx+2B0h+String]
0x180260914  mov     r8, rax; MaxCount
0x180260917  mov     rdx, rcx; Str2
0x18026091a  mov     rcx, [rsp+2B0h+var_258]; Str1
0x18026091f  call    cs:__imp__mbsnicmp
0x180260925  test    eax, eax
0x180260927  jnz     short loc_18026092B
0x180260929  jmp     short loc_180260945
0x18026092b  mov     edx, 2; uCmd
0x180260930  mov     rcx, [rsp+2B0h+hWnd]; hWnd
0x180260935  call    cs:__imp_GetWindow
0x18026093b  mov     [rsp+2B0h+hWnd], rax
0x180260940  jmp     loc_1802608C1
0x180260945  cmp     [rsp+2B0h+var_258], 0
0x18026094b  jz      short loc_180260957
0x18026094d  mov     rcx, [rsp+2B0h+var_258]
0x180260952  call    ProfMemFree
0x180260957  jmp     loc_180260A37
0x18026095c  mov     rcx, [rbp+arg_0]
0x180260960  call    rtI4FromVar
0x180260965  mov     [rsp+2B0h+var_244], eax
0x180260969  call    cs:__imp_GetDesktopWindow
0x18026096f  mov     edx, 5; uCmd
0x180260974  mov     rcx, rax; hWnd
0x180260977  call    cs:__imp_GetWindow
0x18026097d  mov     [rsp+2B0h+hWnd], rax
0x180260982  cmp     [rsp+2B0h+hWnd], 0
0x180260988  jz      short loc_1802609DB
0x18026098a  lea     rdx, [rsp+2B0h+dwProcessId]; lpdwProcessId
0x18026098f  mov     rcx, [rsp+2B0h+hWnd]; hWnd
0x180260994  call    cs:__imp_GetWindowThreadProcessId
0x18026099a  mov     eax, [rsp+2B0h+var_244]
0x18026099e  cmp     [rsp+2B0h+dwProcessId], eax
0x1802609a2  jnz     short loc_1802609C4
0x1802609a4  mov     rcx, [rsp+2B0h+hWnd]; hWnd
0x1802609a9  call    cs:__imp_IsWindowEnabled
0x1802609af  test    eax, eax
0x1802609b1  jz      short loc_1802609C4
0x1802609b3  mov     rcx, [rsp+2B0h+hWnd]; hWnd
0x1802609b8  call    cs:__imp_IsWindowVisible
0x1802609be  test    eax, eax
0x1802609c0  jz      short loc_1802609C4
0x1802609c2  jmp     short loc_1802609DB
0x1802609c4  mov     edx, 2; uCmd
0x1802609c9  mov     rcx, [rsp+2B0h+hWnd]; hWnd
0x1802609ce  call    cs:__imp_GetWindow
0x1802609d4  mov     [rsp+2B0h+hWnd], rax
0x1802609d9  jmp     short loc_180260982
0x1802609db  cmp     [rsp+2B0h+hWnd], 0
0x1802609e1  jnz     short loc_180260A37
0x1802609e3  call    cs:__imp_GetDesktopWindow
0x1802609e9  mov     edx, 5; uCmd
0x1802609ee  mov     rcx, rax; hWnd
0x1802609f1  call    cs:__imp_GetWindow
0x1802609f7  mov     [rsp+2B0h+hWnd], rax
0x1802609fc  cmp     [rsp+2B0h+hWnd], 0
0x180260a02  jz      short loc_180260A37
0x180260a04  lea     rdx, [rsp+2B0h+dwProcessId]; lpdwProcessId
0x180260a09  mov     rcx, [rsp+2B0h+hWnd]; hWnd
0x180260a0e  call    cs:__imp_GetWindowThreadProcessId
0x180260a14  mov     eax, [rsp+2B0h+var_244]
0x180260a18  cmp     [rsp+2B0h+dwProcessId], eax
0x180260a1c  jnz     short loc_180260A20
0x180260a1e  jmp     short loc_180260A37
0x180260a20  mov     edx, 2; uCmd
0x180260a25  mov     rcx, [rsp+2B0h+hWnd]; hWnd
0x180260a2a  call    cs:__imp_GetWindow
0x180260a30  mov     [rsp+2B0h+hWnd], rax
0x180260a35  jmp     short loc_1802609FC
0x180260a37  mov     rcx, [rsp+2B0h+pvarg]; pvarg
0x180260a3c  call    __vbaFreeVar
0x180260a41  cmp     [rsp+2B0h+hWnd], 0
0x180260a47  jnz     short loc_180260A53
0x180260a49  mov     ecx, 5
0x180260a4e  call    EbRaiseExceptionCode
0x180260a53  mov     rcx, [rsp+2B0h+hWnd]; hWnd
0x180260a58  call    cs:__imp_IsWindowEnabled
0x180260a5e  test    eax, eax
0x180260a60  jz      short loc_180260A75
0x180260a62  mov     rcx, [rsp+2B0h+hWnd]; hWnd
0x180260a67  call    cs:__imp_IsWindowVisible
0x180260a6d  test    eax, eax
0x180260a6f  jnz     loc_180260B19
0x180260a75  xor     edx, edx; uCmd
0x180260a77  mov     rcx, [rsp+2B0h+hWnd]; hWnd
0x180260a7c  call    cs:__imp_GetWindow
0x180260a82  mov     [rsp+2B0h+var_260], rax
0x180260a87  jmp     short loc_180260A9E
0x180260a89  mov     edx, 2; uCmd
0x180260a8e  mov     rcx, [rsp+2B0h+var_260]; hWnd
0x180260a93  call    cs:__imp_GetWindow
0x180260a99  mov     [rsp+2B0h+var_260], rax
0x180260a9e  cmp     [rsp+2B0h+var_260], 0
0x180260aa4  jz      short loc_180260AFD
0x180260aa6  mov     edx, 4; uCmd
0x180260aab  mov     rcx, [rsp+2B0h+var_260]; hWnd
0x180260ab0  call    cs:__imp_GetWindow
0x180260ab6  cmp     rax, [rsp+2B0h+hWnd]
0x180260abb  jnz     short loc_180260AFB
0x180260abd  mov     rcx, [rsp+2B0h+var_260]; hWnd
0x180260ac2  call    cs:__imp_IsWindowEnabled
0x180260ac8  test    eax, eax
0x180260aca  jz      short loc_180260ADB
0x180260acc  mov     rcx, [rsp+2B0h+var_260]; hWnd
0x180260ad1  call    cs:__imp_IsWindowVisible
0x180260ad7  test    eax, eax
0x180260ad9  jnz     short loc_180260AF9
0x180260adb  mov     rax, [rsp+2B0h+var_260]
0x180260ae0  mov     [rsp+2B0h+hWnd], rax
0x180260ae5  xor     edx, edx; uCmd
0x180260ae7  mov     rcx, [rsp+2B0h+hWnd]; hWnd
0x180260aec  call    cs:__imp_GetWindow
0x180260af2  mov     [rsp+2B0h+var_260], rax
0x180260af7  jmp     short loc_180260AFB
0x180260af9  jmp     short loc_180260AFD
0x180260afb  jmp     short loc_180260A89
0x180260afd  cmp     [rsp+2B0h+var_260], 0
0x180260b03  jnz     short loc_180260B0F
0x180260b05  mov     ecx, 5
0x180260b0a  call    EbRaiseExceptionCode
0x180260b0f  mov     rax, [rsp+2B0h+var_260]
0x180260b14  mov     [rsp+2B0h+hWnd], rax
0x180260b19  movsx   eax, [rsp+2B0h+var_264]
0x180260b1e  test    eax, eax
0x180260b20  jz      short loc_180260B31
0x180260b22  call    ?PebappCur@@YAPEAVEBAPP@@XZ; PebappCur(void)
0x180260b27  mov     rax, [rax+38h]
0x180260b2b  call    qword ptr [rax+128h]
0x180260b31  lea     rdx, [rsp+2B0h+var_240]; lpdwProcessId
0x180260b36  mov     rcx, [rsp+2B0h+hWnd]; hWnd
0x180260b3b  call    cs:__imp_GetWindowThreadProcessId
0x180260b41  mov     r8d, 1; fAttach
0x180260b47  mov     edx, eax; idAttachTo
0x180260b49  xor     ecx, ecx; idAttach
0x180260b4b  call    cs:__imp_AttachThreadInput
0x180260b51  mov     rcx, [rsp+2B0h+hWnd]; hWnd
0x180260b56  call    cs:__imp_SetForegroundWindow
0x180260b5c  mov     rcx, [rsp+2B0h+hWnd]; hWnd
0x180260b61  call    cs:__imp_SetFocus
0x180260b67  lea     rdx, [rsp+2B0h+var_240]; lpdwProcessId
0x180260b6c  mov     rcx, [rsp+2B0h+hWnd]; hWnd
0x180260b71  call    cs:__imp_GetWindowThreadProcessId
0x180260b77  xor     r8d, r8d; fAttach
0x180260b7a  mov     edx, eax; idAttachTo
0x180260b7c  xor     ecx, ecx; idAttach
0x180260b7e  call    cs:__imp_AttachThreadInput
0x180260b84  mov     rcx, [rbp+var_10]
0x180260b88  xor     rcx, rsp; StackCookie
0x180260b8b  call    __security_check_cookie
0x180260b90  add     rsp, 2B0h
0x180260b97  pop     rbp
0x180260b98  retn
```
