# xpsrdr::VisualsRasterizer::ReadyWicBitmap(xpsrdr::XPSRDR_RECT_S const &,IWICBitmap *)

- ea: `0x18003a98c`
- end: `0x18003aacf`
- name: `?ReadyWicBitmap@VisualsRasterizer@xpsrdr@@AEAA?AV?$shared_ptr@UIWICBitmap@@@std@@AEBUXPSRDR_RECT_S@2@PEAUIWICBitmap@@@Z`
- size: `323`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800386d4`

## callees

- `0x18000e15c`
- `0x18000e4c4`
- `0x180016610`
- `0x180037278`
- `0x1800372e4`
- `0x18003a98c`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
const char *__fastcall xpsrdr::VisualsRasterizer::ReadyWicBitmap(xpsrdr *a1, const char *a2, _DWORD *a3, __int64 a4)
{
  unsigned int v6; // esi
  unsigned int v7; // ebx
  __int64 ***v8; // r9
  int v9; // eax
  const char *v10; // rdx
  xpsrdr *v11; // rcx
  const char *v12; // r8
  int v13; // r9d
  __int64 **v15; // r9
  __int64 *v16; // rcx
  __int64 v17; // rax
  int v18; // ebx
  int v19; // edx
  const char *v20; // r8
  int v21; // r9d
  unsigned int v22; // [rsp+40h] [rbp-20h] BYREF
  int v23; // [rsp+44h] [rbp-1Ch]
  _QWORD v24[3]; // [rsp+48h] [rbp-18h] BYREF
  xpsrdr *v25; // [rsp+90h] [rbp+30h] BYREF

  v23 = 0;
  v6 = a3[2] - *a3;
  if ( (v6 & 0x80000000) != 0 )
    xpsrdr::ThrowLogicException(a1, a2, (int)a3);
  v7 = a3[3] - a3[1];
  if ( (v7 & 0x80000000) != 0 )
    xpsrdr::ThrowLogicException(a1, a2, (int)a3);
  if ( v6 > 0x10000 )
    xpsrdr::ThrowLogicException(a1, a2, (int)a3);
  if ( v7 > 0x10000 )
    xpsrdr::ThrowLogicException(a1, a2, (int)a3);
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(a2);
  v23 = 1;
  LODWORD(v25) = 0;
  if ( a4 )
  {
    v22 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, xpsrdr **, unsigned int *))(*(_QWORD *)a4 + 24LL))(a4, &v25, &v22);
    if ( v9 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v9, (int)v10, v12, v13);
    if ( v6 > (unsigned int)v25 )
      xpsrdr::ThrowLogicException(v11, v10, (int)v12);
    if ( v7 > v22 )
      xpsrdr::ThrowLogicException(v11, v10, (int)v12);
    resetAddRef<IWICBitmap>(a2, a4);
  }
  else
  {
    v15 = *v8;
    v16 = *v15;
    v17 = **v15;
    v24[0] = 0;
    v24[1] = &v25;
    v24[2] = a2;
    v18 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, __int64, int, _QWORD *))(v17 + 136))(
            v16,
            v6,
            v7,
            (__int64)v15 + 100,
            2,
            v24);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v24);
    if ( (int)v25 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v25, v19, v20, v21);
    if ( v18 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v18, v19, v20, v21);
  }
  return a2;
}

```

## disassembly

```asm
0x18003a98c  mov     [rsp-18h+arg_0], rbx
0x18003a991  mov     [rsp-18h+arg_18], rsi
0x18003a996  mov     [rsp-18h+arg_8], rdx
0x18003a99b  push    rbp
0x18003a99c  push    rdi
0x18003a99d  push    r14
0x18003a99f  mov     rbp, rsp
0x18003a9a2  sub     rsp, 60h
0x18003a9a6  mov     r14, r9
0x18003a9a9  mov     rdi, rdx
0x18003a9ac  mov     r9, rcx
0x18003a9af  mov     [rbp+var_1C], 0
0x18003a9b6  mov     esi, [r8+8]
0x18003a9ba  sub     esi, [r8]
0x18003a9bd  jns     short loc_18003A9C5
0x18003a9bf  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x18003a9c5  mov     ebx, [r8+0Ch]
0x18003a9c9  sub     ebx, [r8+4]
0x18003a9cd  jns     short loc_18003A9D5
0x18003a9cf  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x18003a9d5  mov     eax, 10000h
0x18003a9da  cmp     esi, eax
0x18003a9dc  jbe     short loc_18003A9E4
0x18003a9de  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x18003a9e4  cmp     ebx, eax
0x18003a9e6  jbe     short loc_18003A9EE
0x18003a9e8  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x18003a9ee  mov     rcx, rdi
0x18003a9f1  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18003a9f6  mov     [rbp+var_1C], 1
0x18003a9fd  mov     dword ptr [rbp+arg_10], 0
0x18003aa04  lea     rdx, [rbp+arg_10]
0x18003aa08  test    r14, r14
0x18003aa0b  jz      short loc_18003AA6C
0x18003aa0d  mov     [rbp+var_20], 0
0x18003aa14  mov     rax, [r14]
0x18003aa17  lea     r8, [rbp+var_20]
0x18003aa1b  mov     rcx, r14
0x18003aa1e  mov     rax, [rax+18h]
0x18003aa22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aa27  test    eax, eax
0x18003aa29  jns     short loc_18003AA33
0x18003aa2b  mov     ecx, eax; this
0x18003aa2d  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003aa33  cmp     esi, dword ptr [rbp+arg_10]
0x18003aa36  jbe     short loc_18003AA3E
0x18003aa38  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x18003aa3e  cmp     ebx, [rbp+var_20]
0x18003aa41  jbe     short loc_18003AA49
0x18003aa43  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x18003aa49  mov     rdx, r14
0x18003aa4c  mov     rcx, rdi
0x18003aa4f  call    ??$resetAddRef@UIWICBitmap@@@@YAXAEAV?$shared_ptr@UIWICBitmap@@@std@@PEAUIWICBitmap@@@Z; resetAddRef<IWICBitmap>(std::shared_ptr<IWICBitmap> &,IWICBitmap *)
0x18003aa54  mov     rax, rdi
0x18003aa57  lea     r11, [rsp+60h+var_s0]
0x18003aa5c  mov     rbx, [r11+20h]
0x18003aa60  mov     rsi, [r11+38h]
0x18003aa64  mov     rsp, r11
0x18003aa67  pop     r14
0x18003aa69  pop     rdi
0x18003aa6a  pop     rbp
0x18003aa6b  retn
0x18003aa6c  mov     r9, [r9]
0x18003aa6f  mov     rcx, [r9]
0x18003aa72  mov     rax, [rcx]
0x18003aa75  mov     [rbp+var_18], 0
0x18003aa7d  mov     [rbp+var_10], rdx
0x18003aa81  mov     [rbp+var_8], rdi
0x18003aa85  add     r9, 64h ; 'd'
0x18003aa89  lea     rdx, [rbp+var_18]
0x18003aa8d  mov     [rsp+60h+var_38], rdx
0x18003aa92  mov     [rsp+60h+var_40], 2
0x18003aa9a  mov     r8d, ebx
0x18003aa9d  mov     edx, esi
0x18003aa9f  mov     rax, [rax+88h]
0x18003aaa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aaab  mov     ebx, eax
0x18003aaad  lea     rcx, [rbp+var_18]
0x18003aab1  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18003aab6  mov     ecx, dword ptr [rbp+arg_10]; this
0x18003aab9  test    ecx, ecx
0x18003aabb  jns     short loc_18003AAC3
0x18003aabd  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003aac3  test    ebx, ebx
0x18003aac5  jns     short loc_18003AA54
0x18003aac7  mov     ecx, ebx; this
0x18003aac9  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
```
