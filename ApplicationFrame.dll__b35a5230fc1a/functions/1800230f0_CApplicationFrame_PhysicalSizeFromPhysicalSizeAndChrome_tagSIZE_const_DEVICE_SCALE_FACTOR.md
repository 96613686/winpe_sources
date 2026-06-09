# CApplicationFrame::_PhysicalSizeFromPhysicalSizeAndChrome(tagSIZE const &,DEVICE_SCALE_FACTOR)

- ea: `0x1800230f0`
- end: `0x18002338d`
- name: `?_PhysicalSizeFromPhysicalSizeAndChrome@CApplicationFrame@@AEAA?AUtagSIZE@@AEBU2@W4DEVICE_SCALE_FACTOR@@@Z`
- size: `669`
- prototype: `struct tagSIZE __fastcall(CApplicationFrame *__hidden this, const struct tagSIZE *, enum DEVICE_SCALE_FACTOR)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18005343c`

## callees

- `0x1800230f0`
- `0x180023c60`
- `0x180024184`
- `0x180040270`
- `0x180043c30`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002315d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002315d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180023129`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180023129`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180023303`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180023303`
- `ext-ms-win-ntuser-window-l1-1-0!AdjustWindowRectEx` at `0x180023205`
- `ext-ms-win-ntuser-window-l1-1-0!AdjustWindowRectEx` at `0x180023205`
- `USER32!GetWindowLongPtrW` at `0x1800231e0`
- `USER32!GetWindowLongPtrW` at `0x1800231f2`
- `USER32!GetWindowLongPtrW` at `0x1800231e0`
- `USER32!GetWindowLongPtrW` at `0x1800231f2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct tagSIZE __fastcall CApplicationFrame::_PhysicalSizeFromPhysicalSizeAndChrome(
        CApplicationFrame *this,
        const struct tagSIZE *a2,
        _DWORD *a3,
        int a4)
{
  RTL_SRWLOCK *v8; // rdi
  int v9; // ebx
  int v10; // eax
  LONG top; // r12d
  TabletModeHelpers *v13; // rcx
  DWORD WindowLongPtrW; // ebx
  DWORD v15; // eax
  int v16; // eax
  int v17; // r13d
  int v18; // eax
  float v19; // xmm0_4
  __int64 v20; // rcx
  __int64 v21; // r9
  int v22; // [rsp+20h] [rbp-68h] BYREF
  int v23; // [rsp+24h] [rbp-64h] BYREF
  struct tagRECT Rect; // [rsp+28h] [rbp-60h] BYREF
  struct tagRECT rc; // [rsp+38h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v8 = (RTL_SRWLOCK *)((char *)this + 136);
  AcquireSRWLockShared((PSRWLOCK)this + 17);
  *(_QWORD *)&Rect.left = v8;
  v9 = 0;
  if ( (*((_BYTE *)this + 272) & 1) != 0 )
  {
    rc = 0;
    if ( *((_QWORD *)this + 24) )
    {
      SetRectEmpty(&rc);
      v20 = *((_QWORD *)this + 24);
      if ( v20 )
      {
        rc.top = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 248LL))(v20);
        v21 = 0;
      }
      else
      {
        v21 = 2147943568LL;
      }
      if ( (int)v21 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x6B5,
          (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\appframe.cpp",
          (const char *)v21,
          v22);
    }
    top = rc.top;
    v13 = (TabletModeHelpers *)*((_QWORD *)this + 24);
    if ( v13 )
    {
      v22 = 0;
      v16 = (*(__int64 (__fastcall **)(TabletModeHelpers *, int *))(*(_QWORD *)v13 + 112LL))(v13, &v22);
      v17 = v16;
      if ( v16 >= 0 )
        v17 = 0;
      else
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x41C,
          (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\appframe.cpp",
          (const char *)(unsigned int)v16,
          v22);
      v13 = retaddr;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x6BF,
          (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\appframe.cpp",
          (const char *)(unsigned int)v17,
          v22);
      }
      else if ( !v22 )
      {
        v23 = 0;
        v18 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 24) + 40LL))(*((_QWORD *)this + 24), &v23);
        v13 = retaddr;
        if ( v18 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x6C6,
            (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\appframe.cpp",
            (const char *)(unsigned int)v18,
            v22);
        }
        else if ( v23 )
        {
          top = (int)(float)((float)(32 * *((_DWORD *)this + 86)) / 100.0);
        }
      }
    }
    if ( TabletModeHelpers::IsTabletMode(v13) )
    {
      v19 = (float)a4 / 100.0;
      v9 = (int)v19 + top;
      v10 = 2 * (int)v19;
    }
    else
    {
      *(_QWORD *)&Rect.left = 0;
      Rect.right = *((_DWORD *)this + 64);
      Rect.bottom = *((_DWORD *)this + 65);
      WindowLongPtrW = GetWindowLongPtrW(*((HWND *)this + 3), -16);
      v15 = GetWindowLongPtrW(*((HWND *)this + 3), -20);
      AdjustWindowRectEx(&Rect, WindowLongPtrW, 0, v15);
      v9 = top + Rect.bottom - *((_DWORD *)this + 65);
      v10 = Rect.right - Rect.left - *((_DWORD *)this + 64);
    }
  }
  else
  {
    v10 = 0;
  }
  a2->cx = v10 + *a3;
  a2->cy = v9 + a3[1];
  if ( v8 )
    ReleaseSRWLockShared(v8);
  return (struct tagSIZE)a2;
}

```

## disassembly

```asm
0x1800230f0  mov     [rsp+arg_10], rbx
0x1800230f5  push    rbp
0x1800230f6  push    rsi
0x1800230f7  push    rdi
0x1800230f8  push    r12
0x1800230fa  push    r13
0x1800230fc  push    r14
0x1800230fe  push    r15
0x180023100  sub     rsp, 50h
0x180023104  mov     rax, cs:__security_cookie
0x18002310b  xor     rax, rsp
0x18002310e  mov     [rsp+88h+var_40], rax
0x180023113  mov     r15d, r9d
0x180023116  mov     r14, r8
0x180023119  mov     rsi, rdx
0x18002311c  mov     rbp, rcx
0x18002311f  lea     rdi, [rcx+88h]
0x180023126  mov     rcx, rdi; SRWLock
0x180023129  call    cs:__imp_AcquireSRWLockShared
0x18002312f  mov     qword ptr [rsp+88h+Rect.left], rdi
0x180023134  xor     ebx, ebx
0x180023136  test    byte ptr [rbp+110h], 1
0x18002313d  jnz     short loc_18002318B
0x18002313f  mov     eax, ebx
0x180023141  mov     r8d, [r14]
0x180023144  add     r8d, eax
0x180023147  mov     [rsi], r8d
0x18002314a  mov     r8d, [r14+4]
0x18002314e  add     r8d, ebx
0x180023151  mov     [rsi+4], r8d
0x180023155  test    rdi, rdi
0x180023158  jz      short loc_180023163
0x18002315a  mov     rcx, rdi; SRWLock
0x18002315d  call    cs:__imp_ReleaseSRWLockShared
0x180023163  mov     rax, rsi
0x180023166  mov     rcx, [rsp+88h+var_40]
0x18002316b  xor     rcx, rsp; StackCookie
0x18002316e  call    __security_check_cookie
0x180023173  mov     rbx, [rsp+88h+arg_10]
0x18002317b  add     rsp, 50h
0x18002317f  pop     r15
0x180023181  pop     r14
0x180023183  pop     r13
0x180023185  pop     r12
0x180023187  pop     rdi
0x180023188  pop     rsi
0x180023189  pop     rbp
0x18002318a  retn
0x18002318b  xorps   xmm0, xmm0
0x18002318e  movups  xmmword ptr [rsp+88h+rc.left], xmm0
0x180023193  cmp     [rbp+0C0h], rbx
0x18002319a  jnz     loc_1800232FE
0x1800231a0  mov     r12d, [rsp+88h+rc.top]
0x1800231a5  mov     rcx, [rbp+0C0h]; this
0x1800231ac  test    rcx, rcx
0x1800231af  jnz     short loc_18002322B
0x1800231b1  call    ?IsTabletMode@TabletModeHelpers@@YA_NXZ; TabletModeHelpers::IsTabletMode(void)
0x1800231b6  test    al, al
0x1800231b8  jnz     loc_1800232DF
0x1800231be  mov     qword ptr [rsp+88h+Rect.left], rbx
0x1800231c3  mov     eax, [rbp+100h]
0x1800231c9  mov     [rsp+88h+Rect.right], eax
0x1800231cd  mov     eax, [rbp+104h]
0x1800231d3  mov     [rsp+88h+Rect.bottom], eax
0x1800231d7  mov     edx, 0FFFFFFF0h; nIndex
0x1800231dc  mov     rcx, [rbp+18h]; hWnd
0x1800231e0  call    cs:__imp_GetWindowLongPtrW
0x1800231e6  mov     rbx, rax
0x1800231e9  mov     edx, 0FFFFFFECh; nIndex
0x1800231ee  mov     rcx, [rbp+18h]; hWnd
0x1800231f2  call    cs:__imp_GetWindowLongPtrW
0x1800231f8  mov     r9, rax; dwExStyle
0x1800231fb  xor     r8d, r8d; bMenu
0x1800231fe  mov     edx, ebx; dwStyle
0x180023200  lea     rcx, [rsp+88h+Rect]; lpRect
0x180023205  call    cs:__imp_AdjustWindowRectEx
0x18002320b  mov     ebx, [rsp+88h+Rect.bottom]
0x18002320f  sub     ebx, [rbp+104h]
0x180023215  add     ebx, r12d
0x180023218  mov     eax, [rsp+88h+Rect.right]
0x18002321c  sub     eax, [rsp+88h+Rect.left]
0x180023220  sub     eax, [rbp+100h]
0x180023226  jmp     loc_180023141
0x18002322b  mov     [rsp+88h+var_68], ebx; int
0x18002322f  mov     rax, [rcx]
0x180023232  lea     rdx, [rsp+88h+var_68]
0x180023237  mov     rax, [rax+70h]
0x18002323b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023240  mov     r13d, eax
0x180023243  test    eax, eax
0x180023245  jns     loc_1800232DA
0x18002324b  mov     rcx, [rsp+88h]; this
0x180023253  mov     r9d, eax; char *
0x180023256  lea     r8, aPcshellShellAp_1; "pcshell\\shell\\applicationframe\\frame"...
0x18002325d  mov     edx, 41Ch; void *
0x180023262  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023267  mov     rcx, [rsp+88h]; this
0x18002326f  test    r13d, r13d
0x180023272  js      loc_180023352
0x180023278  cmp     [rsp+88h+var_68], ebx
0x18002327c  jnz     loc_1800231B1
0x180023282  mov     [rsp+88h+var_64], ebx
0x180023286  mov     rcx, [rbp+0C0h]
0x18002328d  mov     rax, [rcx]
0x180023290  lea     rdx, [rsp+88h+var_64]
0x180023295  mov     rax, [rax+28h]
0x180023299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002329e  mov     rcx, [rsp+88h]; this
0x1800232a6  test    eax, eax
0x1800232a8  js      loc_18002336B
0x1800232ae  cmp     [rsp+88h+var_64], ebx
0x1800232b2  jz      loc_1800231B1
0x1800232b8  mov     eax, [rbp+158h]
0x1800232be  shl     eax, 5
0x1800232c1  movd    xmm0, eax
0x1800232c5  cvtdq2ps xmm0, xmm0
0x1800232c8  divss   xmm0, cs:__real@42c80000
0x1800232d0  cvttss2si r12d, xmm0
0x1800232d5  jmp     loc_1800231B1
0x1800232da  mov     r13d, ebx
0x1800232dd  jmp     short loc_180023267
0x1800232df  movd    xmm0, r15d
0x1800232e4  cvtdq2ps xmm0, xmm0
0x1800232e7  divss   xmm0, cs:__real@42c80000
0x1800232ef  cvttss2si eax, xmm0
0x1800232f3  lea     ebx, [rax+r12]
0x1800232f7  add     eax, eax
0x1800232f9  jmp     loc_180023141
0x1800232fe  lea     rcx, [rsp+88h+rc]; lprc
0x180023303  call    cs:__imp_SetRectEmpty
0x180023309  mov     rcx, [rbp+0C0h]
0x180023310  test    rcx, rcx
0x180023313  jz      short loc_180023384
0x180023315  mov     rax, [rcx]
0x180023318  mov     rax, [rax+0F8h]
0x18002331f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023324  mov     [rsp+88h+rc.top], eax
0x180023328  mov     r9d, ebx; char *
0x18002332b  mov     rcx, [rsp+88h]; this
0x180023333  test    r9d, r9d
0x180023336  jns     loc_1800231A0
0x18002333c  lea     r8, aPcshellShellAp_1; "pcshell\\shell\\applicationframe\\frame"...
0x180023343  mov     edx, 6B5h; void *
0x180023348  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002334d  jmp     loc_1800231A0
0x180023352  mov     r9d, r13d; char *
0x180023355  lea     r8, aPcshellShellAp_1; "pcshell\\shell\\applicationframe\\frame"...
0x18002335c  mov     edx, 6BFh; void *
0x180023361  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180023366  jmp     loc_1800231B1
0x18002336b  mov     r9d, eax; char *
0x18002336e  lea     r8, aPcshellShellAp_1; "pcshell\\shell\\applicationframe\\frame"...
0x180023375  mov     edx, 6C6h; void *
0x18002337a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002337f  jmp     loc_1800231B1
0x180023384  mov     r9d, 80070490h
0x18002338a  jmp     short loc_18002332B
```
