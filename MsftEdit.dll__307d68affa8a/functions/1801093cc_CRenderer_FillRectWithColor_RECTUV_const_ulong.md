# CRenderer::FillRectWithColor(RECTUV const *,ulong)

- ea: `0x1801093cc`
- end: `0x1801094f7`
- name: `?FillRectWithColor@CRenderer@@QEAAXPEBURECTUV@@K@Z`
- size: `299`
- prototype: `void(CRenderer *__hidden this, const struct RECTUV *, unsigned int)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x1800b2f24`
- `0x18014d7e4`
- `0x18014d9b8`
- `0x180191268`
- `0x1801cbd88`

## callees

- `0x18006e4d4`
- `0x1801093cc`
- `0x18013bad0`
- `0x18027a010`

## import_xrefs

- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180109465`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801094a5`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180109465`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801094a5`
- `ext-ms-win-gdi-draw-l1-1-0!CreateSolidBrush` at `0x18010943a`
- `ext-ms-win-gdi-draw-l1-1-0!CreateSolidBrush` at `0x18010943a`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1801094ae`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1801094ae`

## pseudocode

```c
void __fastcall CRenderer::FillRectWithColor(CRenderer *this, const struct RECTUV *a2, COLORREF a3)
{
  CDisplay *v5; // rcx
  HBRUSH SolidBrush; // rbp
  HDC v7; // rax
  HGDIOBJ v8; // rbx
  HDC v9; // rax
  __int64 v10; // rcx
  COLORREF v11; // [rsp+30h] [rbp-38h] BYREF
  struct tagRECT v12; // [rsp+38h] [rbp-30h] BYREF

  if ( (*((_BYTE *)this + 500) & 1) != 0 )
    a3 = *((_DWORD *)this + 109);
  v5 = (CDisplay *)*((_QWORD *)this + 19);
  v12 = 0;
  CDisplay::RectFromRectuv(v5, &v12, a2, 1, 0);
  if ( (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 42) + 48LL))(*((_QWORD *)this + 42)) )
  {
    SolidBrush = CreateSolidBrush(a3);
    if ( SolidBrush )
    {
      v7 = (HDC)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 42) + 48LL))(*((_QWORD *)this + 42));
      v8 = SelectObject(v7, SolidBrush);
      (*(void (__fastcall **)(_QWORD, struct tagRECT *, _QWORD))(**((_QWORD **)this + 42) + 248LL))(
        *((_QWORD *)this + 42),
        &v12,
        a3);
      v9 = (HDC)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 42) + 48LL))(*((_QWORD *)this + 42));
      SelectObject(v9, v8);
      DeleteObject(SolidBrush);
    }
  }
  else
  {
    v10 = *((_QWORD *)this + 42);
    v11 = a3;
    (*(void (__fastcall **)(__int64, struct tagRECT *, COLORREF *))(*(_QWORD *)v10 + 256LL))(v10, &v12, &v11);
  }
}

```

## disassembly

```asm
0x1801093cc  mov     [rsp+arg_18], rbx
0x1801093d1  push    rbp
0x1801093d2  push    rsi
0x1801093d3  push    rdi
0x1801093d4  sub     rsp, 50h
0x1801093d8  mov     rax, cs:__security_cookie
0x1801093df  xor     rax, rsp
0x1801093e2  mov     [rsp+68h+var_20], rax
0x1801093e7  mov     r9b, 1; bool
0x1801093ea  mov     esi, r8d
0x1801093ed  mov     rdi, rcx
0x1801093f0  test    [rcx+1F4h], r9b
0x1801093f7  jz      short loc_1801093FF
0x1801093f9  mov     esi, [rcx+1B4h]
0x1801093ff  mov     rcx, [rcx+98h]; this
0x180109406  xorps   xmm0, xmm0
0x180109409  mov     r8, rdx; struct RECTUV *
0x18010940c  mov     [rsp+68h+var_48], 0; bool
0x180109411  lea     rdx, [rsp+68h+var_30]; struct tagRECT *
0x180109416  movups  xmmword ptr [rsp+68h+var_30.left], xmm0
0x18010941b  call    ?RectFromRectuv@CDisplay@@QEBAXAEAUtagRECT@@AEBURECTUV@@_N2@Z; CDisplay::RectFromRectuv(tagRECT &,RECTUV const &,bool,bool)
0x180109420  mov     rcx, [rdi+150h]
0x180109427  mov     rax, [rcx]
0x18010942a  mov     rax, [rax+30h]
0x18010942e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109433  test    rax, rax
0x180109436  jz      short loc_1801094B6
0x180109438  mov     ecx, esi; color
0x18010943a  call    cs:__imp_CreateSolidBrush
0x180109440  mov     rbp, rax
0x180109443  test    rax, rax
0x180109446  jz      loc_1801094DA
0x18010944c  mov     rcx, [rdi+150h]
0x180109453  mov     rdx, [rcx]
0x180109456  mov     rax, [rdx+30h]
0x18010945a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010945f  mov     rdx, rbp; h
0x180109462  mov     rcx, rax; hdc
0x180109465  call    cs:__imp_SelectObject
0x18010946b  mov     rcx, [rdi+150h]
0x180109472  mov     r8d, esi
0x180109475  mov     rbx, rax
0x180109478  mov     rdx, [rcx]
0x18010947b  mov     rax, [rdx+0F8h]
0x180109482  lea     rdx, [rsp+68h+var_30]
0x180109487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010948c  mov     rcx, [rdi+150h]
0x180109493  mov     rdx, [rcx]
0x180109496  mov     rax, [rdx+30h]
0x18010949a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010949f  mov     rdx, rbx; h
0x1801094a2  mov     rcx, rax; hdc
0x1801094a5  call    cs:__imp_SelectObject
0x1801094ab  mov     rcx, rbp; ho
0x1801094ae  call    cs:__imp_DeleteObject
0x1801094b4  jmp     short loc_1801094DA
0x1801094b6  mov     rcx, [rdi+150h]
0x1801094bd  lea     r8, [rsp+68h+var_38]
0x1801094c2  mov     [rsp+68h+var_38], esi
0x1801094c6  lea     rdx, [rsp+68h+var_30]
0x1801094cb  mov     rax, [rcx]
0x1801094ce  mov     rax, [rax+100h]
0x1801094d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801094da  mov     rcx, [rsp+68h+var_20]
0x1801094df  xor     rcx, rsp; StackCookie
0x1801094e2  call    __security_check_cookie
0x1801094e7  mov     rbx, [rsp+68h+arg_18]
0x1801094ef  add     rsp, 50h
0x1801094f3  pop     rdi
0x1801094f4  pop     rsi
0x1801094f5  pop     rbp
0x1801094f6  retn
```
