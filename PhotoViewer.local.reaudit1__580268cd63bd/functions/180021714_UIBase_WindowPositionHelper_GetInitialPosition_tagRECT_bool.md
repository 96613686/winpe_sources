# UIBase::WindowPositionHelper::GetInitialPosition(tagRECT *,bool *)

- ea: `0x180021714`
- end: `0x180021a88`
- name: `?GetInitialPosition@WindowPositionHelper@UIBase@@QEAAXPEAUtagRECT@@PEA_N@Z`
- size: `884`
- prototype: `void __fastcall(UIBase::WindowPositionHelper *__hidden this, struct tagRECT *, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180021244`

## callees

- `0x180021714`
- `0x180029e38`
- `0x18003f800`
- `0x180072b6c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180021a5b`
- `ADVAPI32!RegCloseKey` at `0x180021a5b`
- `ADVAPI32!RegOpenKeyExW` at `0x18002179c`
- `ADVAPI32!RegOpenKeyExW` at `0x18002179c`
- `USER32!OffsetRect` at `0x18002195c`
- `USER32!OffsetRect` at `0x180021a39`
- `USER32!OffsetRect` at `0x18002195c`
- `USER32!OffsetRect` at `0x180021a39`
- `USER32!EnumDisplayMonitors` at `0x180021803`
- `USER32!EnumDisplayMonitors` at `0x180021803`
- `USER32!SystemParametersInfoW` at `0x18002175c`
- `USER32!SystemParametersInfoW` at `0x18002175c`

## pseudocode

```c
void __fastcall UIBase::WindowPositionHelper::GetInitialPosition(
        UIBase::WindowPositionHelper *this,
        struct tagRECT *a2,
        bool *a3)
{
  const WCHAR *v4; // rdx
  HKEY v5; // r15
  int v6; // eax
  __int128 v7; // xmm0
  __int128 v8; // rdi
  unsigned __int64 v9; // r9
  __int64 v10; // rcx
  int v11; // r11d
  float v12; // xmm0_4
  int v13; // r8d
  int v14; // r10d
  int v15; // ecx
  int v16; // r11d
  int v17; // r9d
  int v18; // eax
  int v19; // r12d
  int v20; // r14d
  int v21; // r10d
  int v22; // eax
  unsigned __int64 v23; // r8
  int v24; // r8d
  int v25; // r10d
  int v26; // r8d
  int v27; // r9d
  float v28; // xmm0_4
  int v29; // r11d
  float v30; // xmm0_4
  int v31; // r8d
  int v32; // ecx
  int v33; // eax
  int v34; // r11d
  int v35; // eax
  int v36; // r8d
  int v37; // edi
  int v38; // r8d
  int v39; // r10d
  int v40; // edx
  bool *v41; // rcx
  unsigned int v42; // [rsp+30h] [rbp-49h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-41h] BYREF
  struct tagRECT *v44; // [rsp+40h] [rbp-39h]
  bool *v45; // [rsp+48h] [rbp-31h]
  __int128 pvParam; // [rsp+50h] [rbp-29h] BYREF
  LPARAM dwData[2]; // [rsp+60h] [rbp-19h] BYREF
  __int64 v48; // [rsp+70h] [rbp-9h]
  int v49; // [rsp+78h] [rbp-1h]
  __int128 v50; // [rsp+7Ch] [rbp+3h]

  v44 = a2;
  v45 = a3;
  pvParam = 0;
  SystemParametersInfoW(0x30u, 0, &pvParam, 0);
  v4 = (const WCHAR *)*((_QWORD *)this + 4);
  dwData[0] = 0;
  dwData[1] = 0;
  v48 = 0;
  v5 = 0;
  v42 = 20;
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_CURRENT_USER, v4, 0, 0x20019u, &hKey)
    || (v6 = ATL::CRegKey::Close((ATL::CRegKey *)dwData), v5 = hKey, dwData[0] = (LPARAM)hKey, v6)
    || (unsigned int)ATL::CRegKey::QueryBinaryValue(
                       (ATL::CRegKey *)dwData,
                       *((const unsigned __int16 **)this + 5),
                       this,
                       &v42)
    || v42 != 20 )
  {
    v8 = pvParam;
    v9 = DWORD1(pvParam);
    v10 = HIDWORD(*((_QWORD *)&pvParam + 1));
    v11 = (int)(float)((float)(DWORD2(pvParam) - pvParam) * 0.85000002);
    v12 = (float)(HIDWORD(pvParam) - DWORD1(pvParam));
    v13 = (DWORD2(pvParam) - v11 - (int)pvParam) / 2 + pvParam;
    *(_DWORD *)this = v13;
    v14 = (int)(float)(v12 * 0.85000002);
    LODWORD(v10) = ((int)v10 - v14 - (int)v9) / 2 + v9;
    *((_DWORD *)this + 1) = v10;
    *((_DWORD *)this + 2) = v13 + v11;
    *((_DWORD *)this + 3) = v10 + v14;
    *((_BYTE *)this + 16) = 0;
  }
  else
  {
    v7 = *(_OWORD *)this;
    v48 = 0;
    v49 = 0;
    *(_OWORD *)dwData = v7;
    v50 = 0;
    EnumDisplayMonitors(0, 0, UIBase::GetInitialPosMonitorEnumProc, (LPARAM)dwData);
    if ( HIDWORD(v48) )
      pvParam = v50;
    v8 = pvParam;
  }
  v15 = *((_DWORD *)this + 5);
  v16 = *((_DWORD *)this + 2);
  v17 = *(_DWORD *)this;
  v18 = *(_DWORD *)this + v15 - v16;
  LODWORD(hKey) = v15;
  if ( v18 > 0 )
  {
    v17 -= v18 / 2;
    *(_DWORD *)this = v17;
    v16 = v17 + v15;
    *((_DWORD *)this + 2) = v17 + v15;
  }
  v19 = *((_DWORD *)this + 6);
  v20 = *((_DWORD *)this + 3);
  v21 = *((_DWORD *)this + 1);
  v22 = v21 + v19 - v20;
  if ( v22 > 0 )
  {
    v21 -= v22 / 2;
    *((_DWORD *)this + 1) = v21;
    v20 = v21 + v19;
    *((_DWORD *)this + 3) = v21 + v19;
  }
  if ( DWORD2(v8) - (int)v8 < v16 - v17 || (v23 = DWORD1(v8), HIDWORD(v8) - DWORD1(v8) < v20 - v21) )
  {
    v25 = DWORD1(pvParam);
    v26 = HIDWORD(pvParam);
    v27 = (int)(float)((float)(DWORD2(v8) - v8) * 0.89999998);
    v28 = (float)(HIDWORD(pvParam) - DWORD1(pvParam));
    v29 = (DWORD2(v8) - v27 - (int)v8) / 2 + v8;
    *(_DWORD *)this = v29;
    v30 = v28 * 0.89999998;
    v31 = (v26 - (int)v30 - v25) / 2 + v25;
    *((_DWORD *)this + 1) = v31;
    *((_DWORD *)this + 2) = v29 + v27;
    v32 = (int)hKey;
    v33 = (_DWORD)hKey - v27;
    *((_DWORD *)this + 3) = v31 + (int)v30;
    if ( v33 > 0 )
    {
      v34 = v29 - v33 / 2;
      *(_DWORD *)this = v34;
      *((_DWORD *)this + 2) = v34 + v32;
    }
    v35 = v19 - (int)v30;
    if ( v35 > 0 )
    {
      v36 = v31 - v35 / 2;
      *((_DWORD *)this + 1) = v36;
      *((_DWORD *)this + 3) = v36 + v19;
    }
    *((_BYTE *)this + 16) = 1;
  }
  else
  {
    if ( v17 >= (int)v8 )
    {
      LODWORD(v8) = 0;
      if ( SDWORD2(v8) < v16 )
        LODWORD(v8) = DWORD2(v8) - v16;
    }
    else
    {
      LODWORD(v8) = v8 - v17;
    }
    if ( v21 >= (int)v23 )
    {
      v24 = 0;
      if ( SHIDWORD(v8) < v20 )
        v24 = HIDWORD(v8) - v20;
    }
    else
    {
      v24 = v23 - v21;
    }
    OffsetRect((LPRECT)this, v8, v24);
    v25 = DWORD1(pvParam);
    LODWORD(v8) = pvParam;
  }
  v37 = v8 - *(_DWORD *)this;
  v38 = 0;
  v39 = v25 - *((_DWORD *)this + 1);
  if ( v39 >= 0 )
    v38 = v39;
  v40 = 0;
  if ( v37 >= 0 )
    v40 = v37;
  OffsetRect((LPRECT)this, v40, v38);
  v41 = v45;
  *v44 = *(struct tagRECT *)this;
  *v41 = *((_BYTE *)this + 16);
  if ( v5 )
    RegCloseKey(v5);
}

```

## disassembly

```asm
0x180021714  mov     [rsp-8+arg_18], rbx
0x180021719  push    rbp
0x18002171a  push    rsi
0x18002171b  push    rdi
0x18002171c  push    r12
0x18002171e  push    r13
0x180021720  push    r14
0x180021722  push    r15
0x180021724  lea     rbp, [rsp-27h]
0x180021729  sub     rsp, 0A0h
0x180021730  mov     rax, cs:__security_cookie
0x180021737  xor     rax, rsp
0x18002173a  mov     [rbp+57h+var_40], rax
0x18002173e  mov     [rbp+57h+var_90], rdx
0x180021742  mov     rbx, rcx
0x180021745  xor     edx, edx; uiParam
0x180021747  mov     [rbp+57h+var_88], r8
0x18002174b  xorps   xmm0, xmm0
0x18002174e  lea     r8, [rbp+57h+pvParam]; pvParam
0x180021752  xor     r9d, r9d; fWinIni
0x180021755  movups  [rbp+57h+pvParam], xmm0
0x180021759  lea     ecx, [rdx+30h]; uiAction
0x18002175c  call    cs:__imp_SystemParametersInfoW
0x180021762  mov     rdx, [rbx+20h]; lpSubKey
0x180021766  lea     rax, [rbp+57h+hKey]
0x18002176a  xor     r13d, r13d
0x18002176d  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180021772  mov     r9d, 20019h; samDesired
0x180021778  mov     [rbp+57h+dwData], r13
0x18002177c  xor     r8d, r8d; ulOptions
0x18002177f  mov     [rbp+57h+dwData+8], r13
0x180021783  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002178a  mov     [rbp+57h+var_60], r13
0x18002178e  mov     r15d, r13d
0x180021791  mov     [rbp+57h+var_A0], 14h
0x180021798  mov     [rbp+57h+hKey], r13
0x18002179c  call    cs:__imp_RegOpenKeyExW
0x1800217a2  lea     r14d, [r13+2]
0x1800217a6  test    eax, eax
0x1800217a8  jnz     short loc_180021822
0x1800217aa  lea     rcx, [rbp+57h+dwData]; this
0x1800217ae  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800217b3  mov     r15, [rbp+57h+hKey]
0x1800217b7  mov     [rbp+57h+dwData], r15
0x1800217bb  test    eax, eax
0x1800217bd  jnz     short loc_180021822
0x1800217bf  mov     rdx, [rbx+28h]; unsigned __int16 *
0x1800217c3  lea     r9, [rbp+57h+var_A0]; unsigned int *
0x1800217c7  mov     r8, rbx; void *
0x1800217ca  lea     rcx, [rbp+57h+dwData]; this
0x1800217ce  call    ?QueryBinaryValue@CRegKey@ATL@@QEAAJPEBGPEAXPEAK@Z; ATL::CRegKey::QueryBinaryValue(ushort const *,void *,ulong *)
0x1800217d3  test    eax, eax
0x1800217d5  jnz     short loc_180021822
0x1800217d7  cmp     [rbp+57h+var_A0], 14h
0x1800217db  jnz     short loc_180021822
0x1800217dd  movups  xmm0, xmmword ptr [rbx]
0x1800217e0  lea     r9, [rbp+57h+dwData]; dwData
0x1800217e4  mov     [rbp+57h+var_60], r13
0x1800217e8  lea     r8, UIBase__GetInitialPosMonitorEnumProc; lpfnEnum
0x1800217ef  mov     [rbp+57h+var_58], r13d
0x1800217f3  movdqu  xmmword ptr [rbp+57h+dwData], xmm0
0x1800217f8  xor     edx, edx; lprcClip
0x1800217fa  xor     ecx, ecx; hdc
0x1800217fc  xorps   xmm0, xmm0
0x1800217ff  movups  [rbp+57h+var_54], xmm0
0x180021803  call    cs:__imp_EnumDisplayMonitors
0x180021809  cmp     dword ptr [rbp+57h+var_60+4], 1
0x18002180d  jb      short loc_180021818
0x18002180f  movups  xmm0, [rbp+57h+var_54]
0x180021813  movdqu  [rbp+57h+pvParam], xmm0
0x180021818  mov     rsi, qword ptr [rbp+57h+pvParam+8]
0x18002181c  mov     rdi, qword ptr [rbp+57h+pvParam]
0x180021820  jmp     short loc_1800218A0
0x180021822  mov     rdi, qword ptr [rbp+57h+pvParam]
0x180021826  mov     rsi, qword ptr [rbp+57h+pvParam+8]
0x18002182a  mov     r9, rdi
0x18002182d  shr     r9, 20h
0x180021831  mov     eax, esi
0x180021833  sub     eax, edi
0x180021835  mov     rcx, rsi
0x180021838  shr     rcx, 20h
0x18002183c  movd    xmm0, eax
0x180021840  mov     eax, ecx
0x180021842  sub     eax, r9d
0x180021845  cvtdq2ps xmm0, xmm0
0x180021848  mulss   xmm0, cs:__real@3f59999a
0x180021850  cvttss2si r11d, xmm0
0x180021855  movd    xmm0, eax
0x180021859  mov     eax, esi
0x18002185b  sub     eax, r11d
0x18002185e  sub     eax, edi
0x180021860  cdq
0x180021861  idiv    r14d
0x180021864  cvtdq2ps xmm0, xmm0
0x180021867  lea     r8d, [rax+rdi]
0x18002186b  mov     [rbx], r8d
0x18002186e  mulss   xmm0, cs:__real@3f59999a
0x180021876  cvttss2si r10d, xmm0
0x18002187b  sub     ecx, r10d
0x18002187e  sub     ecx, r9d
0x180021881  mov     eax, ecx
0x180021883  cdq
0x180021884  idiv    r14d
0x180021887  lea     ecx, [rax+r9]
0x18002188b  lea     eax, [r8+r11]
0x18002188f  mov     [rbx+4], ecx
0x180021892  mov     [rbx+8], eax
0x180021895  lea     eax, [rcx+r10]
0x180021899  mov     [rbx+0Ch], eax
0x18002189c  mov     [rbx+10h], r13b
0x1800218a0  mov     ecx, [rbx+14h]
0x1800218a3  mov     eax, ecx
0x1800218a5  mov     r11d, [rbx+8]
0x1800218a9  sub     eax, r11d
0x1800218ac  mov     r9d, [rbx]
0x1800218af  add     eax, r9d
0x1800218b2  mov     dword ptr [rbp+57h+hKey], ecx
0x1800218b5  test    eax, eax
0x1800218b7  jle     short loc_1800218CB
0x1800218b9  cdq
0x1800218ba  idiv    r14d
0x1800218bd  sub     r9d, eax
0x1800218c0  mov     [rbx], r9d
0x1800218c3  lea     r11d, [r9+rcx]
0x1800218c7  mov     [rbx+8], r11d
0x1800218cb  mov     r12d, [rbx+18h]
0x1800218cf  mov     eax, r12d
0x1800218d2  mov     r14d, [rbx+0Ch]
0x1800218d6  sub     eax, r14d
0x1800218d9  mov     r10d, [rbx+4]
0x1800218dd  add     eax, r10d
0x1800218e0  test    eax, eax
0x1800218e2  jle     short loc_1800218FB
0x1800218e4  cdq
0x1800218e5  mov     ecx, 2
0x1800218ea  idiv    ecx
0x1800218ec  sub     r10d, eax
0x1800218ef  mov     [rbx+4], r10d
0x1800218f3  lea     r14d, [r10+r12]
0x1800218f7  mov     [rbx+0Ch], r14d
0x1800218fb  mov     r13d, esi
0x1800218fe  mov     eax, r11d
0x180021901  sub     r13d, edi
0x180021904  sub     eax, r9d
0x180021907  cmp     r13d, eax
0x18002190a  jl      short loc_18002196F
0x18002190c  mov     rdx, rsi
0x18002190f  mov     r8, rdi
0x180021912  shr     rdx, 20h
0x180021916  mov     ecx, r14d
0x180021919  shr     r8, 20h
0x18002191d  mov     eax, edx
0x18002191f  sub     eax, r8d
0x180021922  sub     ecx, r10d
0x180021925  cmp     eax, ecx
0x180021927  jl      short loc_18002196F
0x180021929  cmp     r9d, edi
0x18002192c  jge     short loc_180021933
0x18002192e  sub     edi, r9d
0x180021931  jmp     short loc_18002193F
0x180021933  xor     edi, edi
0x180021935  cmp     esi, r11d
0x180021938  jge     short loc_18002193F
0x18002193a  sub     esi, r11d
0x18002193d  mov     edi, esi
0x18002193f  cmp     r10d, r8d
0x180021942  jge     short loc_180021949
0x180021944  sub     r8d, r10d
0x180021947  jmp     short loc_180021957
0x180021949  xor     r8d, r8d
0x18002194c  cmp     edx, r14d
0x18002194f  jge     short loc_180021957
0x180021951  sub     edx, r14d
0x180021954  mov     r8d, edx; dy
0x180021957  mov     edx, edi; dx
0x180021959  mov     rcx, rbx; lprc
0x18002195c  call    cs:__imp_OffsetRect
0x180021962  mov     r10d, dword ptr [rbp+57h+pvParam+4]
0x180021966  mov     rdi, qword ptr [rbp+57h+pvParam]
0x18002196a  jmp     loc_180021A1F
0x18002196f  mov     r10d, dword ptr [rbp+57h+pvParam+4]
0x180021973  mov     r14d, 2
0x180021979  mov     r8d, dword ptr [rbp+57h+pvParam+0Ch]
0x18002197d  mov     ecx, r8d
0x180021980  sub     ecx, r10d
0x180021983  movd    xmm0, r13d
0x180021988  cvtdq2ps xmm0, xmm0
0x18002198b  mulss   xmm0, cs:__real@3f666666
0x180021993  cvttss2si r9d, xmm0
0x180021998  movd    xmm0, ecx
0x18002199c  sub     esi, r9d
0x18002199f  sub     esi, edi
0x1800219a1  mov     eax, esi
0x1800219a3  cdq
0x1800219a4  idiv    r14d
0x1800219a7  cvtdq2ps xmm0, xmm0
0x1800219aa  lea     r11d, [rax+rdi]
0x1800219ae  mov     [rbx], r11d
0x1800219b1  mulss   xmm0, cs:__real@3f666666
0x1800219b9  cvttss2si ecx, xmm0
0x1800219bd  sub     r8d, ecx
0x1800219c0  sub     r8d, r10d
0x1800219c3  mov     eax, r8d
0x1800219c6  cdq
0x1800219c7  idiv    r14d
0x1800219ca  lea     r8d, [rax+r10]
0x1800219ce  lea     eax, [r11+r9]
0x1800219d2  mov     [rbx+4], r8d
0x1800219d6  lea     esi, [r8+rcx]
0x1800219da  mov     [rbx+8], eax
0x1800219dd  mov     ecx, dword ptr [rbp+57h+hKey]
0x1800219e0  mov     eax, ecx
0x1800219e2  sub     eax, r9d
0x1800219e5  mov     [rbx+0Ch], esi
0x1800219e8  test    eax, eax
0x1800219ea  jle     short loc_1800219FD
0x1800219ec  cdq
0x1800219ed  idiv    r14d
0x1800219f0  sub     r11d, eax
0x1800219f3  mov     [rbx], r11d
0x1800219f6  lea     eax, [r11+rcx]
0x1800219fa  mov     [rbx+8], eax
0x1800219fd  mov     eax, r8d
0x180021a00  sub     eax, esi
0x180021a02  add     eax, r12d
0x180021a05  test    eax, eax
0x180021a07  jle     short loc_180021A1B
0x180021a09  cdq
0x180021a0a  idiv    r14d
0x180021a0d  sub     r8d, eax
0x180021a10  mov     [rbx+4], r8d
0x180021a14  lea     eax, [r8+r12]
0x180021a18  mov     [rbx+0Ch], eax
0x180021a1b  mov     byte ptr [rbx+10h], 1
0x180021a1f  sub     edi, [rbx]
0x180021a21  mov     r8d, 0
0x180021a27  sub     r10d, [rbx+4]
0x180021a2b  mov     rcx, rbx; lprc
0x180021a2e  cmovns  r8d, r10d; dy
0x180021a32  xor     edx, edx
0x180021a34  test    edi, edi
0x180021a36  cmovns  edx, edi; dx
0x180021a39  call    cs:__imp_OffsetRect
0x180021a3f  mov     rax, [rbp+57h+var_90]
0x180021a43  mov     rcx, [rbp+57h+var_88]
0x180021a47  movups  xmm0, xmmword ptr [rbx]
0x180021a4a  movdqu  xmmword ptr [rax], xmm0
0x180021a4e  mov     al, [rbx+10h]
0x180021a51  mov     [rcx], al
0x180021a53  test    r15, r15
0x180021a56  jz      short loc_180021A61
0x180021a58  mov     rcx, r15; hKey
0x180021a5b  call    cs:__imp_RegCloseKey
0x180021a61  mov     rcx, [rbp+57h+var_40]
0x180021a65  xor     rcx, rsp; StackCookie
0x180021a68  call    __security_check_cookie
0x180021a6d  mov     rbx, [rsp+0D0h+arg_18]
0x180021a75  add     rsp, 0A0h
0x180021a7c  pop     r15
0x180021a7e  pop     r14
0x180021a80  pop     r13
0x180021a82  pop     r12
0x180021a84  pop     rdi
0x180021a85  pop     rsi
0x180021a86  pop     rbp
0x180021a87  retn
```
