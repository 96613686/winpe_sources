# CMetadataRDFReaderWriter::AddRDFItemToRDFXMLNode(IXMLDOMDocument *,IXMLDOMNode *,IXMLDOMNode *,RDFItem *)

- ea: `0x180023470`
- end: `0x180023590`
- name: `?AddRDFItemToRDFXMLNode@CMetadataRDFReaderWriter@@MEAAJPEAUIXMLDOMDocument@@PEAUIXMLDOMNode@@1PEAVRDFItem@@@Z`
- size: `288`
- prototype: `__int64 __fastcall(CMetadataRDFReaderWriter *__hidden this, struct IXMLDOMDocument *, struct IXMLDOMNode *, struct IXMLDOMNode *, struct RDFItem *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x1800171c4`
- `0x180023470`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::AddRDFItemToRDFXMLNode(
        CMetadataRDFReaderWriter *this,
        struct IXMLDOMDocument *a2,
        struct IXMLDOMNode *a3,
        struct IXMLDOMNode *a4,
        struct RDFItem *a5)
{
  struct IXMLDOMNodeVtbl *lpVtbl; // rax
  int v7; // eax
  unsigned int v8; // ebx
  int v9; // ecx
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rdi
  __int64 v14; // [rsp+20h] [rbp-18h] BYREF
  __int64 v15; // [rsp+28h] [rbp-10h] BYREF

  lpVtbl = a4->lpVtbl;
  v14 = 0;
  v15 = 0;
  if ( (*((_BYTE *)a5 + 8) & 0x10) != 0 )
  {
    v7 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64 *))lpVtbl->get_attributes)(a4, &v15);
    v8 = v7;
    if ( v7 < 0 )
    {
      if ( !g_doStackCaptures )
        goto LABEL_19;
      v9 = v7;
      goto LABEL_10;
    }
    v10 = (*(__int64 (__fastcall **)(__int64, struct IXMLDOMNode *, __int64 *))(*(_QWORD *)v15 + 64LL))(v15, a3, &v14);
  }
  else
  {
    v10 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMNode *, __int64 *))lpVtbl->appendChild)(
            a4,
            a3,
            &v14);
  }
  v8 = v10;
  if ( v10 >= 0 )
  {
    if ( v10 )
    {
      v8 = -2147467259;
      if ( !g_doStackCaptures )
        goto LABEL_19;
      goto LABEL_9;
    }
    v11 = *((_QWORD *)a5 + 2);
    v12 = v14;
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    *((_QWORD *)a5 + 2) = v12;
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
  }
  else if ( g_doStackCaptures )
  {
LABEL_9:
    v9 = v8;
LABEL_10:
    DoStackCapture(v9);
  }
LABEL_19:
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v14 = 0;
  }
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  return v8;
}

```

## disassembly

```asm
0x180023470  mov     r11, rsp
0x180023473  mov     [r11+8], rbx
0x180023477  mov     [r11+10h], rsi
0x18002347b  push    rdi
0x18002347c  sub     rsp, 30h
0x180023480  mov     rsi, [rsp+38h+arg_20]
0x180023485  mov     rdi, r8
0x180023488  mov     rax, [r9]
0x18002348b  mov     rcx, r9
0x18002348e  mov     qword ptr [r11-18h], 0
0x180023496  mov     qword ptr [r11-10h], 0
0x18002349e  test    byte ptr [rsi+8], 10h
0x1800234a2  jz      short loc_1800234F1
0x1800234a4  mov     rax, [rax+88h]
0x1800234ab  lea     rdx, [r11-10h]
0x1800234af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800234b4  mov     ebx, eax
0x1800234b6  test    eax, eax
0x1800234b8  jns     short loc_1800234CB
0x1800234ba  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800234c1  jz      loc_180023549
0x1800234c7  mov     ecx, eax
0x1800234c9  jmp     short loc_1800234EA
0x1800234cb  mov     rcx, [rsp+38h+var_10]
0x1800234d0  mov     rax, [rcx]
0x1800234d3  mov     rax, [rax+40h]
0x1800234d7  jmp     short loc_1800234F8
0x1800234d9  test    ebx, ebx
0x1800234db  js      short loc_180023549
0x1800234dd  jz      short loc_180023517
0x1800234df  mov     ebx, 80004005h
0x1800234e4  test    eax, eax
0x1800234e6  jz      short loc_180023549
0x1800234e8  mov     ecx, ebx; int
0x1800234ea  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800234ef  jmp     short loc_180023549
0x1800234f1  mov     rax, [rax+0A8h]
0x1800234f8  lea     r8, [rsp+38h+var_18]
0x1800234fd  mov     rdx, rdi
0x180023500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023505  mov     ebx, eax
0x180023507  test    eax, eax
0x180023509  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18002350f  jns     short loc_1800234DD
0x180023511  test    eax, eax
0x180023513  jz      short loc_1800234D9
0x180023515  jmp     short loc_1800234E8
0x180023517  mov     rcx, [rsi+10h]
0x18002351b  mov     rdi, [rsp+38h+var_18]
0x180023520  test    rcx, rcx
0x180023523  jz      short loc_180023531
0x180023525  mov     rax, [rcx]
0x180023528  mov     rax, [rax+10h]
0x18002352c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023531  mov     [rsi+10h], rdi
0x180023535  test    rdi, rdi
0x180023538  jz      short loc_180023549
0x18002353a  mov     rax, [rdi]
0x18002353d  mov     rcx, rdi
0x180023540  mov     rax, [rax+8]
0x180023544  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023549  mov     rcx, [rsp+38h+var_18]
0x18002354e  test    rcx, rcx
0x180023551  jz      short loc_180023568
0x180023553  mov     rax, [rcx]
0x180023556  mov     rax, [rax+10h]
0x18002355a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002355f  mov     [rsp+38h+var_18], 0
0x180023568  mov     rcx, [rsp+38h+var_10]
0x18002356d  test    rcx, rcx
0x180023570  jz      short loc_18002357E
0x180023572  mov     rdx, [rcx]
0x180023575  mov     rax, [rdx+10h]
0x180023579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002357e  mov     rsi, [rsp+38h+arg_8]
0x180023583  mov     eax, ebx
0x180023585  mov     rbx, [rsp+38h+arg_0]
0x18002358a  add     rsp, 30h
0x18002358e  pop     rdi
0x18002358f  retn
```
