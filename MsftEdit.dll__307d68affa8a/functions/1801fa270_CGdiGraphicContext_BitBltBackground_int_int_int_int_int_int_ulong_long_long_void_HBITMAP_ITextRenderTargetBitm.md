# CGdiGraphicContext::BitBltBackground(int,int,int,int,int,int,ulong,long,long,void *,HBITMAP__ * *,ITextRenderTargetBitmap * *)

- ea: `0x1801fa270`
- end: `0x1801fa3ed`
- name: `?BitBltBackground@CGdiGraphicContext@@EEAA_NHHHHHHKJJPEAXPEAPEAUHBITMAP__@@PEAPEAUITextRenderTargetBitmap@@@Z`
- size: `381`
- prototype: `bool(CGdiGraphicContext *__hidden this, int, int, int, int, int, int, unsigned int, int, int, void *, HBITMAP *, struct ITextRenderTargetBitmap **)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18013beb8`
- `0x1801ddce4`
- `0x1801e4bb0`
- `0x1801e6130`
- `0x1801fa270`
- `0x18027a010`

## import_xrefs

- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x1801fa2b2`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x1801fa2b2`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801fa383`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801fa383`
- `ext-ms-win-gdi-draw-l1-1-0!BitBlt` at `0x1801fa3cd`
- `ext-ms-win-gdi-draw-l1-1-0!BitBlt` at `0x1801fa3cd`

## pseudocode

```c
bool __fastcall CGdiGraphicContext::BitBltBackground(
        HDC *this,
        int a2,
        int a3,
        int a4,
        int cy,
        int x1,
        int y1,
        DWORD rop,
        int a9,
        int a10,
        void *a11,
        HBITMAP *a12)
{
  int v14; // ebx
  HDC *v16; // r14
  HDC CompatibleDC; // rax
  void *v18; // rdx
  CBackgroundImage *v19; // rsi
  int v20; // ebx
  int v21; // eax
  CImage *v22; // rax
  CImage *v23; // rbx
  HBITMAP v24; // rax

  v14 = a2;
  if ( a12 )
  {
    v16 = this + 3;
    if ( this[4] )
      return BitBlt(*v16, v14, a3, a4, cy, this[4], x1, y1, rop);
    CompatibleDC = CreateCompatibleDC(*v16);
    this[4] = CompatibleDC;
    if ( CompatibleDC )
    {
      v18 = *a12;
      if ( *a12 )
      {
LABEL_10:
        this[5] = (HDC)SelectObject(this[4], v18);
        return BitBlt(*v16, v14, a3, a4, cy, this[4], x1, y1, rop);
      }
      v19 = (CBackgroundImage *)operator new(0xE0u);
      v20 = (*((__int64 (__fastcall **)(char *))this[1] + 2))((char *)this + 8);
      v21 = (*((__int64 (__fastcall **)(char *))this[1] + 1))((char *)this + 8);
      v22 = CBackgroundImage::CBackgroundImage(v19, v21, v20);
      v23 = v22;
      if ( v22 )
      {
        if ( !(unsigned int)CImage::LoadFromHglobal(v22, a9, a10, a11) )
        {
          CImage::CheckGdiBitmap(v23, *v16, 0);
          v24 = (HBITMAP)*((_QWORD *)v23 + 16);
          *((_QWORD *)v23 + 16) = 0;
          *a12 = v24;
        }
        (*(void (__fastcall **)(CImage *))(*(_QWORD *)v23 + 16LL))(v23);
        v18 = *a12;
        if ( *a12 )
        {
          v14 = a2;
          goto LABEL_10;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1801fa270  mov     [rsp+arg_8], edx
0x1801fa274  push    rbx
0x1801fa275  push    rbp
0x1801fa276  push    rsi
0x1801fa277  push    rdi
0x1801fa278  push    r12
0x1801fa27a  push    r13
0x1801fa27c  push    r14
0x1801fa27e  push    r15
0x1801fa280  sub     rsp, 58h
0x1801fa284  mov     r15, [rsp+98h+arg_58]
0x1801fa28c  mov     r12d, r9d
0x1801fa28f  mov     r13d, r8d
0x1801fa292  mov     ebx, edx
0x1801fa294  mov     rbp, rcx
0x1801fa297  test    r15, r15
0x1801fa29a  jz      loc_1801FA3DA
0x1801fa2a0  cmp     qword ptr [rcx+20h], 0
0x1801fa2a5  lea     r14, [rcx+18h]
0x1801fa2a9  jnz     loc_1801FA38D
0x1801fa2af  mov     rcx, [r14]; hdc
0x1801fa2b2  call    cs:__imp_CreateCompatibleDC
0x1801fa2b8  mov     [rbp+20h], rax
0x1801fa2bc  test    rax, rax
0x1801fa2bf  jz      loc_1801FA3DA
0x1801fa2c5  mov     rdx, [r15]
0x1801fa2c8  test    rdx, rdx
0x1801fa2cb  jnz     loc_1801FA37F
0x1801fa2d1  mov     ecx, 0E0h; Size
0x1801fa2d6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801fa2db  lea     rdi, [rbp+8]
0x1801fa2df  mov     rsi, rax
0x1801fa2e2  mov     rdx, [rdi]
0x1801fa2e5  mov     rcx, rdi
0x1801fa2e8  mov     rax, [rdx+10h]
0x1801fa2ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fa2f1  mov     rdx, [rdi]
0x1801fa2f4  mov     ebx, eax
0x1801fa2f6  mov     rcx, rdi
0x1801fa2f9  mov     rax, [rdx+8]
0x1801fa2fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fa302  mov     r8d, ebx; int
0x1801fa305  mov     edx, eax; int
0x1801fa307  mov     rcx, rsi; this
0x1801fa30a  call    ??0CBackgroundImage@@QEAA@JJ@Z; CBackgroundImage::CBackgroundImage(long,long)
0x1801fa30f  mov     rbx, rax
0x1801fa312  test    rax, rax
0x1801fa315  jz      loc_1801FA3DA
0x1801fa31b  mov     r9, [rsp+98h+arg_50]; void *
0x1801fa323  mov     rcx, rax; this
0x1801fa326  mov     r8d, [rsp+98h+arg_48]; int
0x1801fa32e  mov     edx, [rsp+98h+arg_40]; int
0x1801fa335  call    ?LoadFromHglobal@CImage@@QEAAJJJPEAX@Z; CImage::LoadFromHglobal(long,long,void *)
0x1801fa33a  test    eax, eax
0x1801fa33c  jnz     short loc_1801FA361
0x1801fa33e  mov     rdx, [r14]; HDC
0x1801fa341  xor     r8d, r8d; struct tagRECT *
0x1801fa344  mov     rcx, rbx; this
0x1801fa347  call    ?CheckGdiBitmap@CImage@@AEAAJPEAUHDC__@@PEBUtagRECT@@@Z; CImage::CheckGdiBitmap(HDC__ *,tagRECT const *)
0x1801fa34c  mov     rax, [rbx+80h]
0x1801fa353  mov     qword ptr [rbx+80h], 0
0x1801fa35e  mov     [r15], rax
0x1801fa361  mov     rax, [rbx]
0x1801fa364  mov     rcx, rbx
0x1801fa367  mov     rax, [rax+10h]
0x1801fa36b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fa370  mov     rdx, [r15]; h
0x1801fa373  test    rdx, rdx
0x1801fa376  jz      short loc_1801FA3DA
0x1801fa378  mov     ebx, [rsp+98h+arg_8]
0x1801fa37f  mov     rcx, [rbp+20h]; hdc
0x1801fa383  call    cs:__imp_SelectObject
0x1801fa389  mov     [rbp+28h], rax
0x1801fa38d  mov     eax, [rsp+98h+arg_38]
0x1801fa394  mov     r9d, r12d; cx
0x1801fa397  mov     rcx, [r14]; hdc
0x1801fa39a  mov     r8d, r13d; y
0x1801fa39d  mov     [rsp+98h+rop], eax; rop
0x1801fa3a1  mov     edx, ebx; x
0x1801fa3a3  mov     eax, [rsp+98h+arg_30]
0x1801fa3aa  mov     [rsp+98h+y1], eax; y1
0x1801fa3ae  mov     eax, [rsp+98h+arg_28]
0x1801fa3b5  mov     [rsp+98h+x1], eax; x1
0x1801fa3b9  mov     rax, [rbp+20h]
0x1801fa3bd  mov     [rsp+98h+hdcSrc], rax; hdcSrc
0x1801fa3c2  mov     eax, [rsp+98h+arg_20]
0x1801fa3c9  mov     [rsp+98h+cy], eax; cy
0x1801fa3cd  call    cs:__imp_BitBlt
0x1801fa3d3  test    eax, eax
0x1801fa3d5  setnz   al
0x1801fa3d8  jmp     short loc_1801FA3DC
0x1801fa3da  xor     al, al
0x1801fa3dc  add     rsp, 58h
0x1801fa3e0  pop     r15
0x1801fa3e2  pop     r14
0x1801fa3e4  pop     r13
0x1801fa3e6  pop     r12
0x1801fa3e8  pop     rdi
0x1801fa3e9  pop     rsi
0x1801fa3ea  pop     rbp
0x1801fa3eb  pop     rbx
0x1801fa3ec  retn
```
