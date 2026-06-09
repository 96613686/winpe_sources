# CInvalidateMgr::PostInvalidate(HWND__ *,tagRECT *,HRGN__ *,uint)

- ea: `0x1800c9fac`
- end: `0x1800ca150`
- name: `?PostInvalidate@CInvalidateMgr@@QEAAHPEAUHWND__@@PEAUtagRECT@@PEAUHRGN__@@I@Z`
- size: `420`
- prototype: `int(CInvalidateMgr *__hidden this, HWND, struct tagRECT *, HRGN, unsigned int)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800b1810`
- `0x1800e0ab0`
- `0x1800e5634`
- `0x1800f1088`

## callees

- `0x180002740`
- `0x180010350`
- `0x180030ae8`
- `0x1800365f8`
- `0x180036824`
- `0x1800c9fac`

## import_xrefs

- `USER32!PostMessageW` at `0x1800ca10e`
- `USER32!PostMessageW` at `0x1800ca10e`
- `USER32!IsWindow` at `0x1800c9fe5`
- `USER32!IsWindow` at `0x1800c9fe5`
- `GDI32!CombineRgn` at `0x1800ca035`
- `GDI32!CombineRgn` at `0x1800ca035`
- `GDI32!CreateRectRgn` at `0x1800ca01f`
- `GDI32!CreateRectRgn` at `0x1800ca01f`
- `GDI32!DeleteObject` at `0x1800ca042`
- `GDI32!DeleteObject` at `0x1800ca042`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CInvalidateMgr::PostInvalidate(
        CInvalidateMgr *this,
        HWND a2,
        struct tagRECT *a3,
        HRGN a4,
        unsigned int a5)
{
  _QWORD *v9; // rax
  _QWORD *v10; // rdi
  struct tagRECT *v11; // rsi
  HRGN RectRgn; // r14
  struct tagRECT *v14; // rax
  __int64 v15; // rsi
  unsigned __int64 v16; // r14
  bool v17; // cl
  __int64 v18; // rax
  __int64 v19; // rdi
  __int64 result; // rax
  _QWORD *v21; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v22[16]; // [rsp+28h] [rbp-50h] BYREF
  std::bad_alloc *v23; // [rsp+38h] [rbp-40h] BYREF

  if ( !*((_QWORD *)this + 3) )
    return 0;
  CInkAutoDataLock::CInkAutoDataLock((CInkAutoDataLock *)v22, (struct _RTL_CRITICAL_SECTION *)((char *)this + 32));
  if ( !IsWindow(a2) || (v9 = WinMalloc(0x20u), v10 = v9, (v21 = v9) == 0) )
  {
LABEL_26:
    CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v22);
    return 0;
  }
  v11 = 0;
  if ( a4 )
  {
    RectRgn = CreateRectRgn(0, 0, 0, 0);
    if ( !CombineRgn(RectRgn, a4, 0, 5) )
    {
      DeleteObject(RectRgn);
LABEL_7:
      WinFree(v10);
      goto LABEL_26;
    }
  }
  else
  {
    RectRgn = 0;
    if ( a3 )
    {
      v14 = (struct tagRECT *)WinMalloc(0x10u);
      v11 = v14;
      if ( !v14 )
        goto LABEL_7;
      *v14 = *a3;
    }
  }
  *v10 = a2;
  v10[1] = RectRgn;
  v10[2] = v11;
  *((_DWORD *)v10 + 6) = a5;
  v15 = *(_QWORD *)this;
  v16 = *((_QWORD *)this + 1);
  v17 = (unsigned __int64)&v21 < v16 && *(_QWORD *)this <= (unsigned __int64)&v21;
  try
  {
    try
    {
      v18 = *((_QWORD *)this + 2);
      if ( v17 )
      {
        v19 = *(_QWORD *)this;
        if ( *((_QWORD *)this + 1) == v18 )
          std::vector<PIInkCollectorBackDoor *,inkobj_allocator<PIInkCollectorBackDoor *>>::_Reserve(this);
        **((_QWORD **)this + 1) = *(_QWORD *)(*(_QWORD *)this + 8 * ((__int64)&v22[-v19 - 8] >> 3));
      }
      else
      {
        if ( *((_QWORD *)this + 1) == v18 )
          std::vector<PIInkCollectorBackDoor *,inkobj_allocator<PIInkCollectorBackDoor *>>::_Reserve(this);
        **((_QWORD **)this + 1) = v10;
      }
      *((_QWORD *)this + 1) += 8LL;
    }
    catch ( std::bad_alloc *v23 )
    {
      CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v22);
      return 0;
    }
    if ( v15 == v16 )
      PostMessageW(a2, *((_DWORD *)this + 18), 0, *((_QWORD *)this + 3));
    CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v22);
    result = 1;
  }
  catch ( ... )
  {
    ReportWispException();
    goto LABEL_26;
  }
  return result;
}

```

## disassembly

```asm
0x1800c9fac  push    rbx
0x1800c9fae  push    rsi
0x1800c9faf  push    rdi
0x1800c9fb0  push    r12
0x1800c9fb2  push    r13
0x1800c9fb4  push    r14
0x1800c9fb6  push    r15
0x1800c9fb8  sub     rsp, 40h
0x1800c9fbc  mov     r12, r9
0x1800c9fbf  mov     r15, r8
0x1800c9fc2  mov     r13, rdx
0x1800c9fc5  mov     rbx, rcx
0x1800c9fc8  cmp     qword ptr [rcx+18h], 0
0x1800c9fcd  jz      loc_1800CA13E
0x1800c9fd3  lea     rdx, [rcx+20h]; struct _RTL_CRITICAL_SECTION *
0x1800c9fd7  lea     rcx, [rsp+78h+var_50]; this
0x1800c9fdc  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800c9fe1  nop
0x1800c9fe2  mov     rcx, r13; hWnd
0x1800c9fe5  call    cs:__imp_IsWindow
0x1800c9feb  test    eax, eax
0x1800c9fed  jz      loc_1800CA134
0x1800c9ff3  mov     ecx, 20h ; ' '; unsigned __int64
0x1800c9ff8  call    ?WinMalloc@@YAPEAX_K@Z; WinMalloc(unsigned __int64)
0x1800c9ffd  mov     rdi, rax
0x1800ca000  mov     [rsp+78h+var_58], rax
0x1800ca005  test    rax, rax
0x1800ca008  jz      loc_1800CA134
0x1800ca00e  xor     esi, esi
0x1800ca010  test    r12, r12
0x1800ca013  jz      short loc_1800CA055
0x1800ca015  xor     r9d, r9d; y2
0x1800ca018  xor     r8d, r8d; x2
0x1800ca01b  xor     edx, edx; y1
0x1800ca01d  xor     ecx, ecx; x1
0x1800ca01f  call    cs:__imp_CreateRectRgn
0x1800ca025  mov     r14, rax
0x1800ca028  lea     r9d, [rsi+5]; iMode
0x1800ca02c  xor     r8d, r8d; hrgnSrc2
0x1800ca02f  mov     rdx, r12; hrgnSrc1
0x1800ca032  mov     rcx, rax; hrgnDst
0x1800ca035  call    cs:__imp_CombineRgn
0x1800ca03b  test    eax, eax
0x1800ca03d  jnz     short loc_1800CA076
0x1800ca03f  mov     rcx, r14; ho
0x1800ca042  call    cs:__imp_DeleteObject
0x1800ca048  mov     rcx, rdi; void *
0x1800ca04b  call    ?WinFree@@YAXPEAX@Z; WinFree(void *)
0x1800ca050  jmp     loc_1800CA134
0x1800ca055  xor     r14d, r14d
0x1800ca058  test    r15, r15
0x1800ca05b  jz      short loc_1800CA076
0x1800ca05d  lea     ecx, [r14+10h]; unsigned __int64
0x1800ca061  call    ?WinMalloc@@YAPEAX_K@Z; WinMalloc(unsigned __int64)
0x1800ca066  mov     rsi, rax
0x1800ca069  test    rax, rax
0x1800ca06c  jz      short loc_1800CA048
0x1800ca06e  movups  xmm0, xmmword ptr [r15]
0x1800ca072  movdqu  xmmword ptr [rax], xmm0
0x1800ca076  mov     [rdi], r13
0x1800ca079  mov     [rdi+8], r14
0x1800ca07d  mov     [rdi+10h], rsi
0x1800ca081  mov     eax, [rsp+78h+arg_20]
0x1800ca088  mov     [rdi+18h], eax
0x1800ca08b  mov     rsi, [rbx]
0x1800ca08e  mov     r14, [rbx+8]
0x1800ca092  lea     rax, [rsp+78h+var_58]
0x1800ca097  cmp     rax, [rbx+8]
0x1800ca09b  jnb     short loc_1800CA0AB
0x1800ca09d  lea     rax, [rsp+78h+var_58]
0x1800ca0a2  cmp     [rbx], rax
0x1800ca0a5  ja      short loc_1800CA0AB
0x1800ca0a7  mov     cl, 1
0x1800ca0a9  jmp     short loc_1800CA0AD
0x1800ca0ab  xor     cl, cl
0x1800ca0ad  mov     rax, [rbx+10h]
0x1800ca0b1  test    cl, cl
0x1800ca0b3  jz      short loc_1800CA0E2
0x1800ca0b5  mov     rdi, [rbx]
0x1800ca0b8  cmp     [rbx+8], rax
0x1800ca0bc  jnz     short loc_1800CA0C6
0x1800ca0be  mov     rcx, rbx
0x1800ca0c1  call    ?_Reserve@?$vector@PEAUPIInkCollectorBackDoor@@V?$inkobj_allocator@PEAUPIInkCollectorBackDoor@@@@@std@@IEAAX_K@Z; std::vector<PIInkCollectorBackDoor *,inkobj_allocator<PIInkCollectorBackDoor *>>::_Reserve(unsigned __int64)
0x1800ca0c6  lea     rdx, [rsp+78h+var_58]
0x1800ca0cb  sub     rdx, rdi
0x1800ca0ce  sar     rdx, 3
0x1800ca0d2  mov     rax, [rbx]
0x1800ca0d5  mov     rcx, [rbx+8]
0x1800ca0d9  mov     rax, [rax+rdx*8]
0x1800ca0dd  mov     [rcx], rax
0x1800ca0e0  jmp     short loc_1800CA0F7
0x1800ca0e2  cmp     [rbx+8], rax
0x1800ca0e6  jnz     short loc_1800CA0F0
0x1800ca0e8  mov     rcx, rbx
0x1800ca0eb  call    ?_Reserve@?$vector@PEAUPIInkCollectorBackDoor@@V?$inkobj_allocator@PEAUPIInkCollectorBackDoor@@@@@std@@IEAAX_K@Z; std::vector<PIInkCollectorBackDoor *,inkobj_allocator<PIInkCollectorBackDoor *>>::_Reserve(unsigned __int64)
0x1800ca0f0  mov     rax, [rbx+8]
0x1800ca0f4  mov     [rax], rdi
0x1800ca0f7  add     qword ptr [rbx+8], 8
0x1800ca0fc  cmp     rsi, r14
0x1800ca0ff  jnz     short loc_1800CA115
0x1800ca101  mov     r9, [rbx+18h]; lParam
0x1800ca105  xor     r8d, r8d; wParam
0x1800ca108  mov     edx, [rbx+48h]; Msg
0x1800ca10b  mov     rcx, r13; hWnd
0x1800ca10e  call    cs:__imp_PostMessageW
0x1800ca114  nop
0x1800ca115  lea     rcx, [rsp+78h+var_50]; this
0x1800ca11a  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800ca11f  mov     eax, 1
0x1800ca124  jmp     short loc_1800CA140
0x1800ca126  lea     rcx, [rsp+78h+var_50]; this
0x1800ca12b  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800ca130  xor     eax, eax
0x1800ca132  jmp     short loc_1800CA140
0x1800ca134  lea     rcx, [rsp+78h+var_50]; this
0x1800ca139  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800ca13e  xor     eax, eax
0x1800ca140  add     rsp, 40h
0x1800ca144  pop     r15
0x1800ca146  pop     r14
0x1800ca148  pop     r13
0x1800ca14a  pop     r12
0x1800ca14c  pop     rdi
0x1800ca14d  pop     rsi
0x1800ca14e  pop     rbx
0x1800ca14f  retn
```
