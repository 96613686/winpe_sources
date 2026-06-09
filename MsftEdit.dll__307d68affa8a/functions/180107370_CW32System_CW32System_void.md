# CW32System::~CW32System(void)

- ea: `0x180107370`
- end: `0x180107434`
- name: `??1CW32System@@QEAA@XZ`
- size: `196`
- prototype: `void __fastcall(CW32System *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180107344`

## callees

- `0x1800e5578`
- `0x180107370`
- `0x18010743c`
- `0x18013bea0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18010738d`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18010738d`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x1801073b5`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x18010740e`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x1801073b5`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x18010740e`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180107421`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180107421`

## pseudocode

```c
void __fastcall CW32System::~CW32System(CW32System *this)
{
  CArrayBase *v1; // rbx

  v1 = CW32System::_arTmpDisplayAttrib;
  if ( CW32System::_arTmpDisplayAttrib )
  {
    CArrayBase::Clear(CW32System::_arTmpDisplayAttrib, 2);
    operator delete(v1, 0x20u);
    CW32System::_arTmpDisplayAttrib = 0;
  }
  if ( CThreadData::_dwTlsIndex != -1 )
    TlsFree(CThreadData::_dwTlsIndex);
  operator delete(CW32System::_pNotCountingSingleton, 8u);
  CW32System::FreeOle();
  if ( CW32System::_hdcScreenIC )
  {
    DeleteDC(CW32System::_hdcScreenIC);
    CW32System::_hdcScreenIC = 0;
  }
  if ( CW32System::_hdcScreenDC )
  {
    DeleteDC((HDC)CW32System::_hdcScreenDC);
    CW32System::_hdcScreenDC = 0;
  }
  if ( CW32System::_hDefaultFont )
  {
    DeleteObject(CW32System::_hDefaultFont);
    CW32System::_hDefaultFont = 0;
  }
}

```

## disassembly

```asm
0x180107370  push    rbx
0x180107372  sub     rsp, 20h
0x180107376  mov     rbx, cs:?_arTmpDisplayAttrib@CW32System@@2PEAVCTmpDisplayAttrArray@@EA; CTmpDisplayAttrArray * CW32System::_arTmpDisplayAttrib
0x18010737d  test    rbx, rbx
0x180107380  jnz     short loc_1801073E4
0x180107382  mov     ecx, cs:?_dwTlsIndex@CThreadData@@0KA; dwTlsIndex
0x180107388  cmp     ecx, 0FFFFFFFFh
0x18010738b  jz      short loc_180107393
0x18010738d  call    cs:__imp_TlsFree
0x180107393  mov     rcx, cs:?_pNotCountingSingleton@CW32System@@2PEAVCThreadData@@EA; void *
0x18010739a  mov     edx, 8; unsigned __int64
0x18010739f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1801073a4  call    ?FreeOle@CW32System@@SAXXZ; CW32System::FreeOle(void)
0x1801073a9  mov     rcx, cs:?_hdcScreenIC@CW32System@@0PEAUHDC__@@EA; hdc
0x1801073b0  test    rcx, rcx
0x1801073b3  jz      short loc_1801073C6
0x1801073b5  call    cs:__imp_DeleteDC
0x1801073bb  mov     cs:?_hdcScreenIC@CW32System@@0PEAUHDC__@@EA, 0; HDC__ * CW32System::_hdcScreenIC
0x1801073c6  mov     rcx, cs:?_hdcScreenDC@CW32System@@0PEAUHDC__@@EA; hdc
0x1801073cd  test    rcx, rcx
0x1801073d0  jnz     short loc_18010740E
0x1801073d2  mov     rcx, cs:?_hDefaultFont@CW32System@@0PEAUHFONT__@@EA; ho
0x1801073d9  test    rcx, rcx
0x1801073dc  jnz     short loc_180107421
0x1801073de  add     rsp, 20h
0x1801073e2  pop     rbx
0x1801073e3  retn
0x1801073e4  mov     edx, 2
0x1801073e9  mov     rcx, rbx
0x1801073ec  call    ?Clear@CArrayBase@@QEAAXW4tagArrayFlag@@@Z; CArrayBase::Clear(tagArrayFlag)
0x1801073f1  mov     edx, 20h ; ' '; unsigned __int64
0x1801073f6  mov     rcx, rbx; void *
0x1801073f9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1801073fe  mov     cs:?_arTmpDisplayAttrib@CW32System@@2PEAVCTmpDisplayAttrArray@@EA, 0; CTmpDisplayAttrArray * CW32System::_arTmpDisplayAttrib
0x180107409  jmp     loc_180107382
0x18010740e  call    cs:__imp_DeleteDC
0x180107414  mov     cs:?_hdcScreenDC@CW32System@@0PEAUHDC__@@EA, 0; HDC__ * CW32System::_hdcScreenDC
0x18010741f  jmp     short loc_1801073D2
0x180107421  call    cs:__imp_DeleteObject
0x180107427  mov     cs:?_hDefaultFont@CW32System@@0PEAUHFONT__@@EA, 0; HFONT__ * CW32System::_hDefaultFont
0x180107432  jmp     short loc_1801073DE
```
