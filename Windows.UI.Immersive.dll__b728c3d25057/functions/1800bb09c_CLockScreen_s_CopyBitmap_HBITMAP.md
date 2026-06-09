# CLockScreen::_s_CopyBitmap(HBITMAP__ *)

- ea: `0x1800bb09c`
- end: `0x1800bb1d3`
- name: `?_s_CopyBitmap@CLockScreen@@KAPEAUHBITMAP__@@PEAU2@@Z`
- size: `311`
- prototype: `HBITMAP __fastcall(HBITMAP h)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800bb718`

## callees

- `0x1800af8ec`
- `0x1800bb09c`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x1800bb0ba`
- `GDI32!CreateCompatibleDC` at `0x1800bb0e6`
- `GDI32!CreateCompatibleDC` at `0x1800bb0ba`
- `GDI32!CreateCompatibleDC` at `0x1800bb0e6`
- `GDI32!DeleteDC` at `0x1800bb1a1`
- `GDI32!DeleteDC` at `0x1800bb1b6`
- `GDI32!DeleteDC` at `0x1800bb1a1`
- `GDI32!DeleteDC` at `0x1800bb1b6`
- `GDI32!SelectObject` at `0x1800bb0d2`
- `GDI32!SelectObject` at `0x1800bb14e`
- `GDI32!SelectObject` at `0x1800bb198`
- `GDI32!SelectObject` at `0x1800bb1ad`
- `GDI32!SelectObject` at `0x1800bb0d2`
- `GDI32!SelectObject` at `0x1800bb14e`
- `GDI32!SelectObject` at `0x1800bb198`
- `GDI32!SelectObject` at `0x1800bb1ad`
- `GDI32!GetObjectW` at `0x1800bb10d`
- `GDI32!GetObjectW` at `0x1800bb10d`
- `GDI32!BitBlt` at `0x1800bb18c`
- `GDI32!BitBlt` at `0x1800bb18c`

## pseudocode

```c
HGDIOBJ __fastcall CLockScreen::_s_CopyBitmap(HBITMAP h)
{
  HGDIOBJ v2; // rbx
  HDC CompatibleDC; // rax
  HDC hdcSrc; // rdi
  HGDIOBJ v5; // r15
  HDC v6; // rsi
  int v7; // eax
  HGDIOBJ v8; // r14
  _OWORD pv[2]; // [rsp+50h] [rbp-20h] BYREF
  HGDIOBJ ha; // [rsp+A8h] [rbp+38h] BYREF
  tagSIZE v12; // [rsp+B0h] [rbp+40h] BYREF
  void *v13; // [rsp+B8h] [rbp+48h] BYREF

  v2 = 0;
  ha = 0;
  CompatibleDC = CreateCompatibleDC(0);
  hdcSrc = CompatibleDC;
  if ( CompatibleDC )
  {
    v5 = SelectObject(CompatibleDC, h);
    if ( v5 )
    {
      v6 = CreateCompatibleDC(0);
      if ( v6 )
      {
        memset(pv, 0, sizeof(pv));
        if ( GetObjectW(h, 32, pv) == 32 )
        {
          v12 = *(tagSIZE *)((char *)pv + 4);
          v13 = 0;
          v7 = Create32BitHBITMAP(v6, &v12, &v13, (HBITMAP *)&ha);
          v2 = ha;
          if ( v7 >= 0 )
          {
            v8 = SelectObject(v6, ha);
            if ( v8 )
            {
              BitBlt(v6, 0, 0, SDWORD1(pv[0]), SDWORD2(pv[0]), hdcSrc, 0, 0, 0xCC0020u);
              SelectObject(v6, v8);
            }
          }
        }
        DeleteDC(v6);
      }
      SelectObject(hdcSrc, v5);
    }
    DeleteDC(hdcSrc);
  }
  return v2;
}

```

## disassembly

```asm
0x1800bb09c  mov     [rsp-28h+arg_0], rbx
0x1800bb0a1  push    rbp
0x1800bb0a2  push    rsi
0x1800bb0a3  push    rdi
0x1800bb0a4  push    r14
0x1800bb0a6  push    r15
0x1800bb0a8  mov     rbp, rsp
0x1800bb0ab  sub     rsp, 70h
0x1800bb0af  mov     r14, rcx
0x1800bb0b2  xor     ebx, ebx
0x1800bb0b4  xor     ecx, ecx; hdc
0x1800bb0b6  mov     [rbp+h], rbx
0x1800bb0ba  call    cs:__imp_CreateCompatibleDC
0x1800bb0c0  mov     rdi, rax
0x1800bb0c3  test    rax, rax
0x1800bb0c6  jz      loc_1800BB1BC
0x1800bb0cc  mov     rdx, r14; h
0x1800bb0cf  mov     rcx, rax; hdc
0x1800bb0d2  call    cs:__imp_SelectObject
0x1800bb0d8  mov     r15, rax
0x1800bb0db  test    rax, rax
0x1800bb0de  jz      loc_1800BB1B3
0x1800bb0e4  xor     ecx, ecx; hdc
0x1800bb0e6  call    cs:__imp_CreateCompatibleDC
0x1800bb0ec  mov     rsi, rax
0x1800bb0ef  test    rax, rax
0x1800bb0f2  jz      loc_1800BB1A7
0x1800bb0f8  xorps   xmm0, xmm0
0x1800bb0fb  lea     r8, [rbp+pv]; pv
0x1800bb0ff  lea     edx, [rbx+20h]; c
0x1800bb102  mov     rcx, r14; h
0x1800bb105  movups  [rbp+pv], xmm0
0x1800bb109  movups  [rbp+var_10], xmm0
0x1800bb10d  call    cs:__imp_GetObjectW
0x1800bb113  cmp     eax, 20h ; ' '
0x1800bb116  jnz     loc_1800BB19E
0x1800bb11c  mov     eax, dword ptr [rbp+pv+4]
0x1800bb11f  lea     r9, [rbp+h]; HBITMAP *
0x1800bb123  mov     [rbp+arg_10.cx], eax
0x1800bb126  lea     r8, [rbp+arg_18]; void **
0x1800bb12a  mov     eax, dword ptr [rbp+pv+8]
0x1800bb12d  lea     rdx, [rbp+arg_10]; struct tagSIZE *
0x1800bb131  mov     rcx, rsi; hDC
0x1800bb134  mov     [rbp+arg_10.cy], eax
0x1800bb137  mov     [rbp+arg_18], rbx
0x1800bb13b  call    ?Create32BitHBITMAP@@YAJPEAUHDC__@@PEBUtagSIZE@@PEAPEAXPEAPEAUHBITMAP__@@@Z; Create32BitHBITMAP(HDC__ *,tagSIZE const *,void * *,HBITMAP__ * *)
0x1800bb140  mov     rbx, [rbp+h]
0x1800bb144  test    eax, eax
0x1800bb146  js      short loc_1800BB19E
0x1800bb148  mov     rdx, rbx; h
0x1800bb14b  mov     rcx, rsi; hdc
0x1800bb14e  call    cs:__imp_SelectObject
0x1800bb154  mov     r14, rax
0x1800bb157  test    rax, rax
0x1800bb15a  jz      short loc_1800BB19E
0x1800bb15c  mov     eax, dword ptr [rbp+pv+8]
0x1800bb15f  xor     r8d, r8d; y
0x1800bb162  mov     r9d, dword ptr [rbp+pv+4]; cx
0x1800bb166  xor     edx, edx; x
0x1800bb168  mov     [rsp+70h+rop], 0CC0020h; rop
0x1800bb170  mov     rcx, rsi; hdc
0x1800bb173  mov     [rsp+70h+y1], 0; y1
0x1800bb17b  mov     [rsp+70h+x1], 0; x1
0x1800bb183  mov     [rsp+70h+hdcSrc], rdi; hdcSrc
0x1800bb188  mov     [rsp+70h+cy], eax; cy
0x1800bb18c  call    cs:__imp_BitBlt
0x1800bb192  mov     rdx, r14; h
0x1800bb195  mov     rcx, rsi; hdc
0x1800bb198  call    cs:__imp_SelectObject
0x1800bb19e  mov     rcx, rsi; hdc
0x1800bb1a1  call    cs:__imp_DeleteDC
0x1800bb1a7  mov     rdx, r15; h
0x1800bb1aa  mov     rcx, rdi; hdc
0x1800bb1ad  call    cs:__imp_SelectObject
0x1800bb1b3  mov     rcx, rdi; hdc
0x1800bb1b6  call    cs:__imp_DeleteDC
0x1800bb1bc  mov     rax, rbx
0x1800bb1bf  mov     rbx, [rsp+70h+arg_0]
0x1800bb1c7  add     rsp, 70h
0x1800bb1cb  pop     r15
0x1800bb1cd  pop     r14
0x1800bb1cf  pop     rdi
0x1800bb1d0  pop     rsi
0x1800bb1d1  pop     rbp
0x1800bb1d2  retn
```
