# CApplicationFrame::_GetMinimumSizeForScaleFactor(tagRECT const *,DEVICE_SCALE_FACTOR)

- ea: `0x180023610`
- end: `0x180023c5a`
- name: `?_GetMinimumSizeForScaleFactor@CApplicationFrame@@AEAA?AUtagSIZE@@PEBUtagRECT@@W4DEVICE_SCALE_FACTOR@@@Z`
- size: `1610`
- prototype: `struct tagSIZE __fastcall(CApplicationFrame *__hidden this, const struct tagRECT *, enum DEVICE_SCALE_FACTOR)`
- caller_count: `4`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180013430`
- `0x1800434b4`
- `0x1800437b0`
- `0x180050b80`

## callees

- `0x180022f88`
- `0x180023610`
- `0x180023c60`
- `0x180024184`
- `0x180040270`
- `0x180043c30`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002367f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800236c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002375b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180023801`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002367f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800236c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002375b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180023801`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180023651`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180023696`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180023742`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180023764`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180023651`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180023696`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180023742`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180023764`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800237b4`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800237e6`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800237b4`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800237e6`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180023aee`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180023b40`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180023aee`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180023b40`
- `ext-ms-win-ntuser-window-l1-1-0!AdjustWindowRectEx` at `0x180023891`
- `ext-ms-win-ntuser-window-l1-1-0!AdjustWindowRectEx` at `0x180023934`
- `ext-ms-win-ntuser-window-l1-1-0!AdjustWindowRectEx` at `0x180023891`
- `ext-ms-win-ntuser-window-l1-1-0!AdjustWindowRectEx` at `0x180023934`
- `USER32!GetWindowLongPtrW` at `0x18002386d`
- `USER32!GetWindowLongPtrW` at `0x18002387f`
- `USER32!GetWindowLongPtrW` at `0x180023910`
- `USER32!GetWindowLongPtrW` at `0x180023922`
- `USER32!GetWindowLongPtrW` at `0x18002386d`
- `USER32!GetWindowLongPtrW` at `0x18002387f`
- `USER32!GetWindowLongPtrW` at `0x180023910`
- `USER32!GetWindowLongPtrW` at `0x180023922`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct tagSIZE __fastcall CApplicationFrame::_GetMinimumSizeForScaleFactor(
        CApplicationFrame *this,
        const struct tagRECT *a2,
        enum DEVICE_SCALE_FACTOR a3,
        int a4)
{
  RTL_SRWLOCK *v6; // rbx
  __int64 v7; // r12
  __int64 v8; // rdi
  int v9; // ecx
  int v10; // eax
  LONG left; // esi
  LONG v12; // r12d
  __int64 v14; // rdi
  LONG v15; // r12d
  int v16; // r13d
  int v17; // esi
  int v18; // r15d
  LONG v19; // r13d
  int v20; // r15d
  TabletModeHelpers *v21; // rcx
  DWORD WindowLongPtrW; // esi
  DWORD v23; // eax
  int v24; // r12d
  TabletModeHelpers *v25; // rcx
  DWORD v26; // esi
  DWORD v27; // eax
  int v28; // eax
  const char *v29; // r9
  int v30; // eax
  int v31; // eax
  int v32; // r13d
  int v33; // eax
  float v34; // xmm0_4
  int v35; // eax
  __int64 v36; // rcx
  __int64 v37; // r9
  __int64 v38; // rcx
  __int64 v39; // r9
  LONG cx; // eax
  LONG cy; // ecx
  unsigned int v42; // [rsp+20h] [rbp-60h] BYREF
  LONG top; // [rsp+24h] [rbp-5Ch] BYREF
  int nDenominator; // [rsp+28h] [rbp-58h]
  tagSIZE v45; // [rsp+30h] [rbp-50h] BYREF
  enum DEVICE_SCALE_FACTOR v46[2]; // [rsp+38h] [rbp-48h] BYREF
  struct tagRECT Rect; // [rsp+40h] [rbp-40h] BYREF
  struct tagRECT rc; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  nDenominator = a4;
  v6 = (RTL_SRWLOCK *)((char *)this + 136);
  AcquireSRWLockShared((PSRWLOCK)this + 17);
  v7 = *((_QWORD *)this + 35);
  v8 = *((_QWORD *)this + 37);
  *(_QWORD *)v46 = v8;
  if ( v6 )
    ReleaseSRWLockShared(v6);
  *(_QWORD *)&a2->left = 0;
  if ( (int)v7 > 0 )
    goto LABEL_4;
  if ( SHIDWORD(v7) > 0 || (int)v8 > 0 || SHIDWORD(v8) > 0 )
  {
    if ( SHIDWORD(v7) <= 0 )
    {
LABEL_13:
      if ( (int)v8 > 0 || v46[1] > DEVICE_SCALE_FACTOR_INVALID )
      {
        CApplicationFrame::_PhysicalSizeFromLogicalSizeForScaleFactor(this, &v45, (enum DEVICE_SCALE_FACTOR)v46);
        cx = v45.cx;
        if ( a2->left > v45.cx )
          cx = a2->left;
        a2->left = cx;
        cy = v45.cy;
        if ( a2->top > v45.cy )
          cy = a2->top;
        a2->top = cy;
      }
      return (struct tagSIZE)a2;
    }
LABEL_4:
    AcquireSRWLockShared(v6);
    *(_QWORD *)&Rect.left = v6;
    if ( (*((_BYTE *)this + 272) & 1) != 0 )
    {
      rc = 0;
      if ( *((_QWORD *)this + 24) )
      {
        SetRectEmpty(&rc);
        v36 = *((_QWORD *)this + 24);
        if ( v36 )
        {
          rc.top = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 248LL))(v36);
          v37 = 0;
        }
        else
        {
          v37 = 2147943568LL;
        }
        if ( (int)v37 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x6B5,
            (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\appframe.cpp",
            (const char *)v37,
            v42);
      }
      top = rc.top;
      v21 = (TabletModeHelpers *)*((_QWORD *)this + 24);
      if ( v21 )
      {
        v45.cx = 0;
        v28 = (*(__int64 (__fastcall **)(TabletModeHelpers *, tagSIZE *))(*(_QWORD *)v21 + 112LL))(v21, &v45);
        v42 = v28;
        if ( v28 >= 0 )
        {
          v29 = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x41C,
            (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\appframe.cpp",
            (const char *)(unsigned int)v28,
            v42);
          v29 = (const char *)v42;
        }
        v21 = retaddr;
        if ( (int)v29 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x6BF,
            (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\appframe.cpp",
            v29,
            v42);
        }
        else if ( !v45.cx )
        {
          v42 = 0;
          v30 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)this + 24) + 40LL))(
                  *((_QWORD *)this + 24),
                  &v42);
          v21 = retaddr;
          if ( v30 < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x6C6,
              (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\appframe.cpp",
              (const char *)(unsigned int)v30,
              v42);
          }
          else if ( v42 )
          {
            top = (int)(float)((float)(32 * *((_DWORD *)this + 86)) / 100.0);
          }
        }
      }
      if ( TabletModeHelpers::IsTabletMode(v21) )
      {
        v34 = (float)nDenominator / 100.0;
        v9 = (int)v34 + top;
        v10 = 2 * (int)v34;
      }
      else
      {
        *(_QWORD *)&Rect.left = 0;
        Rect.right = *((_DWORD *)this + 64);
        Rect.bottom = *((_DWORD *)this + 65);
        WindowLongPtrW = GetWindowLongPtrW(*((HWND *)this + 3), -16);
        v23 = GetWindowLongPtrW(*((HWND *)this + 3), -20);
        AdjustWindowRectEx(&Rect, WindowLongPtrW, 0, v23);
        v9 = top + Rect.bottom - *((_DWORD *)this + 65);
        v10 = Rect.right - Rect.left - *((_DWORD *)this + 64);
      }
    }
    else
    {
      v9 = 0;
      v10 = 0;
    }
    left = v10 + v7;
    v12 = v9 + HIDWORD(v7);
    if ( v6 )
      ReleaseSRWLockShared(v6);
    if ( a2->left > left )
      left = a2->left;
    a2->left = left;
    if ( a2->top > v12 )
      v12 = a2->top;
    a2->top = v12;
    goto LABEL_13;
  }
  AcquireSRWLockShared(v6);
  v14 = *((_QWORD *)this + 32);
  *(_QWORD *)v46 = v14;
  if ( v6 )
    ReleaseSRWLockShared(v6);
  AcquireSRWLockShared(v6);
  *(_QWORD *)&Rect.left = v6;
  v45 = 0;
  if ( (*((_BYTE *)this + 272) & 1) != 0 )
  {
    rc = 0;
    if ( *((_QWORD *)this + 24) )
    {
      SetRectEmpty(&rc);
      v38 = *((_QWORD *)this + 24);
      if ( v38 )
      {
        rc.top = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v38 + 248LL))(v38);
        v39 = 0;
      }
      else
      {
        v39 = 2147943568LL;
      }
      if ( (int)v39 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x6B5,
          (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\appframe.cpp",
          (const char *)v39,
          v42);
    }
    v24 = rc.top;
    v45.cx = rc.top;
    v25 = (TabletModeHelpers *)*((_QWORD *)this + 24);
    if ( v25 )
    {
      top = 0;
      v31 = (*(__int64 (__fastcall **)(TabletModeHelpers *, LONG *))(*(_QWORD *)v25 + 112LL))(v25, &top);
      v32 = v31;
      if ( v31 >= 0 )
        v32 = 0;
      else
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x41C,
          (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\appframe.cpp",
          (const char *)(unsigned int)v31,
          v42);
      v25 = retaddr;
      if ( v32 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x6BF,
          (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\appframe.cpp",
          (const char *)(unsigned int)v32,
          v42);
      }
      else if ( !top )
      {
        v42 = 0;
        v33 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)this + 24) + 40LL))(
                *((_QWORD *)this + 24),
                &v42);
        v25 = retaddr;
        if ( v33 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x6C6,
            (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\appframe.cpp",
            (const char *)(unsigned int)v33,
            v42);
        }
        else if ( v42 )
        {
          v24 = (int)(float)((float)(32 * *((_DWORD *)this + 86)) / 100.0);
          v45.cx = v24;
        }
      }
    }
    if ( TabletModeHelpers::IsTabletMode(v25) )
    {
      v17 = nDenominator;
      v35 = (int)(float)((float)nDenominator / 100.0);
      v16 = 2 * v35;
      v15 = v35 + v24;
      goto LABEL_24;
    }
    *(_QWORD *)&Rect.left = 0;
    Rect.right = *((_DWORD *)this + 64);
    Rect.bottom = *((_DWORD *)this + 65);
    v26 = GetWindowLongPtrW(*((HWND *)this + 3), -16);
    v27 = GetWindowLongPtrW(*((HWND *)this + 3), -20);
    AdjustWindowRectEx(&Rect, v26, 0, v27);
    v16 = Rect.right - Rect.left - *((_DWORD *)this + 64);
    v15 = v45.cx + Rect.bottom - *((_DWORD *)this + 65);
  }
  else
  {
    v15 = v45.cy;
    v16 = 0;
  }
  v17 = nDenominator;
LABEL_24:
  v18 = (int)(float)((float)(v17 * v14) / 100.0);
  if ( (_DWORD)v14 != MulDiv(v18, 100, v17) )
    ++v18;
  v19 = v18 + v16;
  v20 = (int)(float)((float)(v17 * v46[1]) / 100.0);
  if ( v46[1] != MulDiv(v20, 100, v17) )
    ++v20;
  if ( v6 )
    ReleaseSRWLockShared(v6);
  a2->left = v19;
  a2->top = v20 + v15;
  return (struct tagSIZE)a2;
}

```

## disassembly

```asm
0x180023610  mov     [rsp-38h+arg_10], rbx
0x180023615  push    rbp
0x180023616  push    rsi
0x180023617  push    rdi
0x180023618  push    r12
0x18002361a  push    r13
0x18002361c  push    r14
0x18002361e  push    r15
0x180023620  mov     rbp, rsp
0x180023623  sub     rsp, 80h
0x18002362a  movaps  [rsp+80h+var_10], xmm6
0x18002362f  mov     rax, cs:__security_cookie
0x180023636  xor     rax, rsp
0x180023639  mov     [rbp+var_20], rax
0x18002363d  mov     [rbp+nDenominator], r9d
0x180023641  mov     r14, rdx
0x180023644  mov     r15, rcx
0x180023647  lea     rbx, [rcx+88h]
0x18002364e  mov     rcx, rbx; SRWLock
0x180023651  call    cs:__imp_AcquireSRWLockShared
0x180023657  mov     r12, [r15+118h]
0x18002365e  mov     r13, r12
0x180023661  shr     r13, 20h
0x180023665  mov     rdi, [r15+128h]
0x18002366c  mov     qword ptr [rbp+var_48], rdi
0x180023670  mov     rsi, rdi
0x180023673  shr     rsi, 20h
0x180023677  test    rbx, rbx
0x18002367a  jz      short loc_180023685
0x18002367c  mov     rcx, rbx; SRWLock
0x18002367f  call    cs:__imp_ReleaseSRWLockShared
0x180023685  xor     eax, eax
0x180023687  mov     [r14], rax
0x18002368a  test    r12d, r12d
0x18002368d  jle     loc_180023720
0x180023693  mov     rcx, rbx; SRWLock
0x180023696  call    cs:__imp_AcquireSRWLockShared
0x18002369c  mov     qword ptr [rbp+Rect.left], rbx
0x1800236a0  test    byte ptr [r15+110h], 1
0x1800236a8  jnz     loc_180023813
0x1800236ae  xor     ecx, ecx
0x1800236b0  mov     eax, ecx
0x1800236b2  lea     esi, [rax+r12]
0x1800236b6  lea     r12d, [rcx+r13]
0x1800236ba  test    rbx, rbx
0x1800236bd  jz      short loc_1800236C8
0x1800236bf  mov     rcx, rbx; SRWLock
0x1800236c2  call    cs:__imp_ReleaseSRWLockShared
0x1800236c8  cmp     [r14], esi
0x1800236cb  cmovg   esi, [r14]
0x1800236cf  mov     [r14], esi
0x1800236d2  cmp     [r14+4], r12d
0x1800236d6  cmovg   r12d, [r14+4]
0x1800236db  mov     [r14+4], r12d
0x1800236df  test    edi, edi
0x1800236e1  jg      loc_180023C23
0x1800236e7  cmp     [rbp+var_48+4], 0
0x1800236eb  jg      loc_180023C23
0x1800236f1  mov     rax, r14
0x1800236f4  mov     rcx, [rbp+var_20]
0x1800236f8  xor     rcx, rsp; StackCookie
0x1800236fb  call    __security_check_cookie
0x180023700  mov     rbx, [rsp+80h+arg_10]
0x180023708  movaps  xmm6, [rsp+80h+var_10]
0x18002370d  add     rsp, 80h
0x180023714  pop     r15
0x180023716  pop     r14
0x180023718  pop     r13
0x18002371a  pop     r12
0x18002371c  pop     rdi
0x18002371d  pop     rsi
0x18002371e  pop     rbp
0x18002371f  retn
0x180023720  mov     rax, r12
0x180023723  shr     rax, 20h
0x180023727  test    eax, eax
0x180023729  jg      loc_180023BEF
0x18002372f  test    edi, edi
0x180023731  jg      loc_180023BEF
0x180023737  test    esi, esi
0x180023739  jg      loc_180023BEF
0x18002373f  mov     rcx, rbx; SRWLock
0x180023742  call    cs:__imp_AcquireSRWLockShared
0x180023748  mov     rdi, [r15+100h]
0x18002374f  mov     qword ptr [rbp+var_48], rdi
0x180023753  test    rbx, rbx
0x180023756  jz      short loc_180023761
0x180023758  mov     rcx, rbx; SRWLock
0x18002375b  call    cs:__imp_ReleaseSRWLockShared
0x180023761  mov     rcx, rbx; SRWLock
0x180023764  call    cs:__imp_AcquireSRWLockShared
0x18002376a  mov     qword ptr [rbp+Rect.left], rbx
0x18002376e  xor     esi, esi
0x180023770  mov     qword ptr [rbp+var_50.cx], rsi
0x180023774  movss   xmm6, cs:__real@42c80000
0x18002377c  test    byte ptr [r15+110h], 1
0x180023784  jnz     loc_1800238B6
0x18002378a  mov     r12d, [rbp+var_50.cy]
0x18002378e  mov     r13d, esi
0x180023791  mov     esi, [rbp+nDenominator]
0x180023794  mov     eax, edi
0x180023796  imul    eax, esi
0x180023799  movd    xmm0, eax
0x18002379d  cvtdq2ps xmm0, xmm0
0x1800237a0  divss   xmm0, xmm6
0x1800237a4  cvttss2si r15d, xmm0
0x1800237a9  mov     r8d, esi; nDenominator
0x1800237ac  mov     edx, 64h ; 'd'; nNumerator
0x1800237b1  mov     ecx, r15d; nNumber
0x1800237b4  call    cs:__imp_MulDiv
0x1800237ba  cmp     edi, eax
0x1800237bc  jnz     loc_180023C08
0x1800237c2  add     r13d, r15d
0x1800237c5  mov     eax, [rbp+var_48+4]
0x1800237c8  imul    eax, esi
0x1800237cb  movd    xmm0, eax
0x1800237cf  cvtdq2ps xmm0, xmm0
0x1800237d2  divss   xmm0, xmm6
0x1800237d6  cvttss2si r15d, xmm0
0x1800237db  mov     r8d, esi; nDenominator
0x1800237de  mov     edx, 64h ; 'd'; nNumerator
0x1800237e3  mov     ecx, r15d; nNumber
0x1800237e6  call    cs:__imp_MulDiv
0x1800237ec  cmp     [rbp+var_48+4], eax
0x1800237ef  jnz     loc_180023C10
0x1800237f5  lea     edi, [r15+r12]
0x1800237f9  test    rbx, rbx
0x1800237fc  jz      short loc_180023807
0x1800237fe  mov     rcx, rbx; SRWLock
0x180023801  call    cs:__imp_ReleaseSRWLockShared
0x180023807  mov     [r14], r13d
0x18002380a  mov     [r14+4], edi
0x18002380e  jmp     loc_1800236F1
0x180023813  xorps   xmm0, xmm0
0x180023816  movups  xmmword ptr [rbp+rc.left], xmm0
0x18002381a  xor     esi, esi
0x18002381c  cmp     [r15+0C0h], rsi
0x180023823  jnz     loc_180023AEA
0x180023829  mov     eax, [rbp+rc.top]
0x18002382c  mov     dword ptr [rbp+var_60+4], eax
0x18002382f  mov     rcx, [r15+0C0h]; this
0x180023836  test    rcx, rcx
0x180023839  jnz     loc_18002395D
0x18002383f  call    ?IsTabletMode@TabletModeHelpers@@YA_NXZ; TabletModeHelpers::IsTabletMode(void)
0x180023844  test    al, al
0x180023846  jnz     loc_180023AA4
0x18002384c  mov     qword ptr [rbp+Rect.left], rsi
0x180023850  mov     eax, [r15+100h]
0x180023857  mov     [rbp+Rect.right], eax
0x18002385a  mov     eax, [r15+104h]
0x180023861  mov     [rbp+Rect.bottom], eax
0x180023864  mov     edx, 0FFFFFFF0h; nIndex
0x180023869  mov     rcx, [r15+18h]; hWnd
0x18002386d  call    cs:__imp_GetWindowLongPtrW
0x180023873  mov     rsi, rax
0x180023876  mov     edx, 0FFFFFFECh; nIndex
0x18002387b  mov     rcx, [r15+18h]; hWnd
0x18002387f  call    cs:__imp_GetWindowLongPtrW
0x180023885  mov     r9, rax; dwExStyle
0x180023888  xor     r8d, r8d; bMenu
0x18002388b  mov     edx, esi; dwStyle
0x18002388d  lea     rcx, [rbp+Rect]; lpRect
0x180023891  call    cs:__imp_AdjustWindowRectEx
0x180023897  mov     ecx, [rbp+Rect.bottom]
0x18002389a  sub     ecx, [r15+104h]
0x1800238a1  add     ecx, dword ptr [rbp+var_60+4]
0x1800238a4  mov     eax, [rbp+Rect.right]
0x1800238a7  sub     eax, [rbp+Rect.left]
0x1800238aa  sub     eax, [r15+100h]
0x1800238b1  jmp     loc_1800236B2
0x1800238b6  xorps   xmm0, xmm0
0x1800238b9  movups  xmmword ptr [rbp+rc.left], xmm0
0x1800238bd  cmp     [r15+0C0h], rsi
0x1800238c4  jnz     loc_180023B3C
0x1800238ca  mov     r12d, [rbp+rc.top]
0x1800238ce  mov     [rbp+var_50.cx], r12d
0x1800238d2  mov     rcx, [r15+0C0h]; this
0x1800238d9  test    rcx, rcx
0x1800238dc  jnz     loc_180023A06
0x1800238e2  call    ?IsTabletMode@TabletModeHelpers@@YA_NXZ; TabletModeHelpers::IsTabletMode(void)
0x1800238e7  test    al, al
0x1800238e9  jnz     loc_180023ACC
0x1800238ef  mov     qword ptr [rbp+Rect.left], rsi
0x1800238f3  mov     eax, [r15+100h]
0x1800238fa  mov     [rbp+Rect.right], eax
0x1800238fd  mov     eax, [r15+104h]
0x180023904  mov     [rbp+Rect.bottom], eax
0x180023907  mov     edx, 0FFFFFFF0h; nIndex
0x18002390c  mov     rcx, [r15+18h]; hWnd
0x180023910  call    cs:__imp_GetWindowLongPtrW
0x180023916  mov     rsi, rax
0x180023919  mov     edx, 0FFFFFFECh; nIndex
0x18002391e  mov     rcx, [r15+18h]; hWnd
0x180023922  call    cs:__imp_GetWindowLongPtrW
0x180023928  mov     r9, rax; dwExStyle
0x18002392b  xor     r8d, r8d; bMenu
0x18002392e  mov     edx, esi; dwStyle
0x180023930  lea     rcx, [rbp+Rect]; lpRect
0x180023934  call    cs:__imp_AdjustWindowRectEx
0x18002393a  mov     r13d, [rbp+Rect.right]
0x18002393e  sub     r13d, [rbp+Rect.left]
0x180023942  sub     r13d, [r15+100h]
0x180023949  mov     r12d, [rbp+Rect.bottom]
0x18002394d  sub     r12d, [r15+104h]
0x180023954  add     r12d, [rbp+var_50.cx]
0x180023958  jmp     loc_180023791
0x18002395d  mov     [rbp+var_50.cx], esi
0x180023960  mov     rax, [rcx]
0x180023963  lea     rdx, [rbp+var_50]
0x180023967  mov     rax, [rax+70h]
0x18002396b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023970  mov     dword ptr [rbp+var_60], eax
0x180023973  test    eax, eax
0x180023975  jns     loc_180023A01
0x18002397b  mov     rcx, [rbp+38h]; this
0x18002397f  mov     r9d, eax; char *
0x180023982  lea     r8, aPcshellShellAp_1; "pcshell\\shell\\applicationframe\\frame"...
0x180023989  mov     edx, 41Ch; void *
0x18002398e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023993  mov     r9d, dword ptr [rbp+var_60]; char *
0x180023997  mov     rcx, [rbp+38h]; this
0x18002399b  test    r9d, r9d
0x18002399e  js      loc_180023B8E
0x1800239a4  cmp     [rbp+var_50.cx], esi
0x1800239a7  jnz     loc_18002383F
0x1800239ad  mov     dword ptr [rbp+var_60], esi
0x1800239b0  mov     rcx, [r15+0C0h]
0x1800239b7  mov     rax, [rcx]
0x1800239ba  lea     rdx, [rbp+var_60]
0x1800239be  mov     rax, [rax+28h]
0x1800239c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800239c7  mov     rcx, [rbp+38h]; this
0x1800239cb  test    eax, eax
0x1800239cd  js      loc_180023BA4
0x1800239d3  cmp     dword ptr [rbp+var_60], esi
0x1800239d6  jz      loc_18002383F
0x1800239dc  mov     eax, [r15+158h]
0x1800239e3  shl     eax, 5
0x1800239e6  movd    xmm0, eax
0x1800239ea  cvtdq2ps xmm0, xmm0
0x1800239ed  divss   xmm0, cs:__real@42c80000
0x1800239f5  cvttss2si eax, xmm0
0x1800239f9  mov     dword ptr [rbp+var_60+4], eax
0x1800239fc  jmp     loc_18002383F
0x180023a01  mov     r9d, esi
0x180023a04  jmp     short loc_180023997
0x180023a06  mov     dword ptr [rbp+var_60+4], esi
0x180023a09  mov     rax, [rcx]
0x180023a0c  lea     rdx, [rbp+var_60+4]
0x180023a10  mov     rax, [rax+70h]
0x180023a14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a19  mov     r13d, eax
0x180023a1c  test    eax, eax
0x180023a1e  jns     loc_180023AC4
0x180023a24  mov     rcx, [rbp+38h]; this
0x180023a28  mov     r9d, eax; char *
0x180023a2b  lea     r8, aPcshellShellAp_1; "pcshell\\shell\\applicationframe\\frame"...
0x180023a32  mov     edx, 41Ch; void *
0x180023a37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023a3c  mov     rcx, [rbp+38h]; this
0x180023a40  test    r13d, r13d
0x180023a43  js      loc_180023BBD
0x180023a49  cmp     dword ptr [rbp+var_60+4], esi
0x180023a4c  jnz     loc_1800238E2
0x180023a52  mov     dword ptr [rbp+var_60], esi
0x180023a55  mov     rcx, [r15+0C0h]
0x180023a5c  mov     rax, [rcx]
0x180023a5f  lea     rdx, [rbp+var_60]
0x180023a63  mov     rax, [rax+28h]
0x180023a67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a6c  mov     rcx, [rbp+38h]; this
0x180023a70  test    eax, eax
0x180023a72  js      loc_180023BD6
0x180023a78  cmp     dword ptr [rbp+var_60], esi
0x180023a7b  jz      loc_1800238E2
0x180023a81  mov     eax, [r15+158h]
0x180023a88  shl     eax, 5
0x180023a8b  movd    xmm0, eax
0x180023a8f  cvtdq2ps xmm0, xmm0
0x180023a92  divss   xmm0, xmm6
0x180023a96  cvttss2si r12d, xmm0
0x180023a9b  mov     [rbp+var_50.cx], r12d
0x180023a9f  jmp     loc_1800238E2
0x180023aa4  movd    xmm0, [rbp+nDenominator]
0x180023aa9  cvtdq2ps xmm0, xmm0
0x180023aac  divss   xmm0, cs:__real@42c80000
0x180023ab4  cvttss2si eax, xmm0
0x180023ab8  mov     ecx, dword ptr [rbp+var_60+4]
0x180023abb  add     ecx, eax
0x180023abd  add     eax, eax
0x180023abf  jmp     loc_1800236B2
0x180023ac4  mov     r13d, esi
0x180023ac7  jmp     loc_180023A3C
0x180023acc  mov     esi, [rbp+nDenominator]
0x180023acf  movd    xmm0, esi
0x180023ad3  cvtdq2ps xmm0, xmm0
0x180023ad6  divss   xmm0, xmm6
0x180023ada  cvttss2si eax, xmm0
0x180023ade  lea     r13d, [rax+rax]
0x180023ae2  add     r12d, eax
  ... truncated ...
```
