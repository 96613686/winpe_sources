# CApplicationFrame::_GetChromeSize(DEVICE_SCALE_FACTOR)

- ea: `0x1800233a0`
- end: `0x18002360a`
- name: `?_GetChromeSize@CApplicationFrame@@AEAA?AUtagSIZE@@W4DEVICE_SCALE_FACTOR@@@Z`
- size: `618`
- prototype: `struct tagSIZE __fastcall(CApplicationFrame *__hidden this, enum DEVICE_SCALE_FACTOR)`
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x180013430`
- `0x180022f88`
- `0x18004ef1c`
- `0x18004f820`

## callees

- `0x1800233a0`
- `0x180023c60`
- `0x180024184`
- `0x180040270`
- `0x180043c30`
- `0x180072010`

## import_xrefs

- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x18002357b`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x18002357b`
- `ext-ms-win-ntuser-window-l1-1-0!AdjustWindowRectEx` at `0x180023473`
- `ext-ms-win-ntuser-window-l1-1-0!AdjustWindowRectEx` at `0x180023473`
- `USER32!GetWindowLongPtrW` at `0x18002344e`
- `USER32!GetWindowLongPtrW` at `0x180023460`
- `USER32!GetWindowLongPtrW` at `0x18002344e`
- `USER32!GetWindowLongPtrW` at `0x180023460`

## pseudocode

```c
struct tagSIZE __fastcall CApplicationFrame::_GetChromeSize(CApplicationFrame *this, __int64 a2, int a3)
{
  TabletModeHelpers *v7; // rcx
  LONG top; // ebp
  HWND v9; // rcx
  DWORD WindowLongPtrW; // ebx
  DWORD v11; // eax
  int v12; // ecx
  int v13; // eax
  unsigned int v14; // r14d
  __int64 v15; // rcx
  int v16; // eax
  float v17; // xmm0_4
  __int64 v18; // rcx
  int v19; // [rsp+20h] [rbp-58h] BYREF
  int v20; // [rsp+24h] [rbp-54h] BYREF
  struct tagRECT Rect; // [rsp+28h] [rbp-50h] BYREF
  struct tagRECT rc; // [rsp+38h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  *(_QWORD *)a2 = 0;
  if ( (*((_BYTE *)this + 272) & 1) != 0 )
  {
    rc = 0;
    if ( *((_QWORD *)this + 24) )
    {
      SetRectEmpty(&rc);
      v18 = *((_QWORD *)this + 24);
      if ( v18 )
        rc.top = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 248LL))(v18);
      else
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x6B5,
          (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\appframe.cpp",
          (const char *)0x80070490LL,
          v19);
    }
    v7 = (TabletModeHelpers *)*((_QWORD *)this + 24);
    top = rc.top;
    if ( v7 )
    {
      v19 = 0;
      v13 = (*(__int64 (__fastcall **)(TabletModeHelpers *, int *))(*(_QWORD *)v7 + 112LL))(v7, &v19);
      v14 = v13;
      if ( v13 >= 0 )
      {
        if ( !v19 )
        {
          v15 = *((_QWORD *)this + 24);
          v20 = 0;
          v16 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v15 + 40LL))(v15, &v20);
          if ( v16 < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x6C6,
              (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\appframe.cpp",
              (const char *)(unsigned int)v16,
              v19);
          }
          else if ( v20 )
          {
            top = (int)(float)((float)(32 * *((_DWORD *)this + 86)) / 100.0);
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x41C,
          (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\appframe.cpp",
          (const char *)(unsigned int)v13,
          v19);
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x6BF,
          (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\appframe.cpp",
          (const char *)v14,
          v19);
      }
    }
    if ( TabletModeHelpers::IsTabletMode(v7) )
    {
      v17 = (float)a3 / 100.0;
      *(_DWORD *)a2 = 2 * (int)v17;
      *(_DWORD *)(a2 + 4) = (int)v17 + top;
    }
    else
    {
      v9 = (HWND)*((_QWORD *)this + 3);
      Rect.right = *((_DWORD *)this + 64);
      Rect.bottom = *((_DWORD *)this + 65);
      *(_QWORD *)&Rect.left = 0;
      WindowLongPtrW = GetWindowLongPtrW(v9, -16);
      v11 = GetWindowLongPtrW(*((HWND *)this + 3), -20);
      AdjustWindowRectEx(&Rect, WindowLongPtrW, 0, v11);
      v12 = Rect.bottom - *((_DWORD *)this + 65);
      *(_DWORD *)a2 = Rect.right - *((_DWORD *)this + 64) - Rect.left;
      *(_DWORD *)(a2 + 4) = v12 + top;
    }
  }
  return (struct tagSIZE)a2;
}

```

## disassembly

```asm
0x1800233a0  push    rbx
0x1800233a2  push    rsi
0x1800233a3  push    rdi
0x1800233a4  sub     rsp, 60h
0x1800233a8  mov     rax, cs:__security_cookie
0x1800233af  xor     rax, rsp
0x1800233b2  mov     [rsp+78h+var_30], rax
0x1800233b7  xor     eax, eax
0x1800233b9  mov     ebx, r8d
0x1800233bc  mov     [rdx], rax
0x1800233bf  mov     rdi, rdx
0x1800233c2  test    byte ptr [rcx+110h], 1
0x1800233c9  mov     rsi, rcx
0x1800233cc  jnz     short loc_1800233E6
0x1800233ce  mov     rax, rdi
0x1800233d1  mov     rcx, [rsp+78h+var_30]
0x1800233d6  xor     rcx, rsp; StackCookie
0x1800233d9  call    __security_check_cookie
0x1800233de  add     rsp, 60h
0x1800233e2  pop     rdi
0x1800233e3  pop     rsi
0x1800233e4  pop     rbx
0x1800233e5  retn
0x1800233e6  xorps   xmm0, xmm0
0x1800233e9  mov     [rsp+78h+arg_10], rbp
0x1800233f1  movups  xmmword ptr [rsp+78h+rc.left], xmm0
0x1800233f6  mov     [rsp+78h+var_28], r15
0x1800233fb  cmp     [rcx+0C0h], rax
0x180023402  jnz     loc_180023576
0x180023408  mov     rcx, [rsi+0C0h]; this
0x18002340f  xor     r15d, r15d
0x180023412  mov     ebp, [rsp+78h+rc.top]
0x180023416  test    rcx, rcx
0x180023419  jnz     loc_1800234AB
0x18002341f  call    ?IsTabletMode@TabletModeHelpers@@YA_NXZ; TabletModeHelpers::IsTabletMode(void)
0x180023424  test    al, al
0x180023426  jnz     loc_180023546
0x18002342c  mov     eax, [rsi+100h]
0x180023432  mov     edx, 0FFFFFFF0h; nIndex
0x180023437  mov     rcx, [rsi+18h]; hWnd
0x18002343b  mov     [rsp+78h+Rect.right], eax
0x18002343f  mov     eax, [rsi+104h]
0x180023445  mov     [rsp+78h+Rect.bottom], eax
0x180023449  mov     qword ptr [rsp+78h+Rect.left], r15
0x18002344e  call    cs:__imp_GetWindowLongPtrW
0x180023454  mov     rcx, [rsi+18h]; hWnd
0x180023458  mov     edx, 0FFFFFFECh; nIndex
0x18002345d  mov     rbx, rax
0x180023460  call    cs:__imp_GetWindowLongPtrW
0x180023466  xor     r8d, r8d; bMenu
0x180023469  lea     rcx, [rsp+78h+Rect]; lpRect
0x18002346e  mov     r9, rax; dwExStyle
0x180023471  mov     edx, ebx; dwStyle
0x180023473  call    cs:__imp_AdjustWindowRectEx
0x180023479  mov     ecx, [rsp+78h+Rect.bottom]
0x18002347d  sub     ecx, [rsi+104h]
0x180023483  mov     eax, [rsp+78h+Rect.right]
0x180023487  sub     eax, [rsi+100h]
0x18002348d  sub     eax, [rsp+78h+Rect.left]
0x180023491  mov     r15, [rsp+78h+var_28]
0x180023496  mov     [rdi], eax
0x180023498  lea     eax, [rcx+rbp]
0x18002349b  mov     rbp, [rsp+78h+arg_10]
0x1800234a3  mov     [rdi+4], eax
0x1800234a6  jmp     loc_1800233CE
0x1800234ab  mov     [rsp+78h+var_58], r15d; int
0x1800234b0  lea     rdx, [rsp+78h+var_58]
0x1800234b5  mov     rax, [rcx]
0x1800234b8  mov     [rsp+78h+var_20], r14
0x1800234bd  mov     rax, [rax+70h]
0x1800234c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800234c6  mov     r14d, eax
0x1800234c9  test    eax, eax
0x1800234cb  jns     short loc_180023509
0x1800234cd  mov     rcx, [rsp+78h]; this
0x1800234d2  lea     r8, aPcshellShellAp_1; "pcshell\\shell\\applicationframe\\frame"...
0x1800234d9  mov     r9d, eax; char *
0x1800234dc  mov     edx, 41Ch; void *
0x1800234e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800234e6  mov     rcx, [rsp+78h]; this
0x1800234eb  lea     r8, aPcshellShellAp_1; "pcshell\\shell\\applicationframe\\frame"...
0x1800234f2  mov     r9d, r14d; char *
0x1800234f5  mov     edx, 6BFh; void *
0x1800234fa  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800234ff  mov     r14, [rsp+78h+var_20]
0x180023504  jmp     loc_18002341F
0x180023509  cmp     [rsp+78h+var_58], r15d
0x18002350e  jnz     short loc_18002353C
0x180023510  mov     rcx, [rsi+0C0h]
0x180023517  lea     rdx, [rsp+78h+var_54]
0x18002351c  mov     [rsp+78h+var_54], r15d
0x180023521  mov     rax, [rcx]
0x180023524  mov     rax, [rax+28h]
0x180023528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002352d  test    eax, eax
0x18002352f  js      short loc_1800235A5
0x180023531  cmp     [rsp+78h+var_54], r15d
0x180023536  jnz     loc_1800235E9
0x18002353c  mov     r14, [rsp+78h+var_20]
0x180023541  jmp     loc_18002341F
0x180023546  mov     r15, [rsp+78h+var_28]
0x18002354b  movd    xmm0, ebx
0x18002354f  cvtdq2ps xmm0, xmm0
0x180023552  divss   xmm0, cs:__real@42c80000
0x18002355a  cvttss2si edx, xmm0
0x18002355e  lea     ecx, [rdx+rdx]
0x180023561  mov     [rdi], ecx
0x180023563  lea     ecx, [rdx+rbp]
0x180023566  mov     rbp, [rsp+78h+arg_10]
0x18002356e  mov     [rdi+4], ecx
0x180023571  jmp     loc_1800233CE
0x180023576  lea     rcx, [rsp+78h+rc]; lprc
0x18002357b  call    cs:__imp_SetRectEmpty
0x180023581  mov     rcx, [rsi+0C0h]
0x180023588  test    rcx, rcx
0x18002358b  jz      short loc_1800235C8
0x18002358d  mov     rax, [rcx]
0x180023590  mov     rax, [rax+0F8h]
0x180023597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002359c  mov     [rsp+78h+rc.top], eax
0x1800235a0  jmp     loc_180023408
0x1800235a5  mov     rcx, [rsp+78h]; this
0x1800235aa  lea     r8, aPcshellShellAp_1; "pcshell\\shell\\applicationframe\\frame"...
0x1800235b1  mov     r9d, eax; char *
0x1800235b4  mov     edx, 6C6h; void *
0x1800235b9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800235be  mov     r14, [rsp+78h+var_20]
0x1800235c3  jmp     loc_18002341F
0x1800235c8  mov     rcx, [rsp+78h]; this
0x1800235cd  lea     r8, aPcshellShellAp_1; "pcshell\\shell\\applicationframe\\frame"...
0x1800235d4  mov     r9d, 80070490h; char *
0x1800235da  mov     edx, 6B5h; void *
0x1800235df  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800235e4  jmp     loc_180023408
0x1800235e9  mov     eax, [rsi+158h]
0x1800235ef  shl     eax, 5
0x1800235f2  movd    xmm0, eax
0x1800235f6  cvtdq2ps xmm0, xmm0
0x1800235f9  divss   xmm0, cs:__real@42c80000
0x180023601  cvttss2si ebp, xmm0
0x180023605  jmp     loc_18002353C
```
