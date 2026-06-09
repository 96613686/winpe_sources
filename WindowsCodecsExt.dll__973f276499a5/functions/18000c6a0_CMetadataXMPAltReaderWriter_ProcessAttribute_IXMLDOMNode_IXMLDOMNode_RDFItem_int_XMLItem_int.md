# CMetadataXMPAltReaderWriter::ProcessAttribute(IXMLDOMNode *,IXMLDOMNode *,RDFItem * *,int *,XMLItem * *,int *)

- ea: `0x18000c6a0`
- end: `0x18000c7a4`
- name: `?ProcessAttribute@CMetadataXMPAltReaderWriter@@MEAAJPEAUIXMLDOMNode@@0PEAPEAVRDFItem@@PEAHPEAPEAVXMLItem@@2@Z`
- size: `260`
- prototype: `__int64 __fastcall(CMetadataXMPAltReaderWriter *__hidden this, struct IXMLDOMNode *, struct IXMLDOMNode *, struct RDFItem **, int *, struct XMLItem **, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x18000c6a0`
- `0x18000c7b0`
- `0x1800171c4`
- `0x180033010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000c78b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c78b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000c737`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000c737`

## string_xrefs

- `0x18000c730`: `xml:lang`

## pseudocode

```c
__int64 __fastcall CMetadataXMPAltReaderWriter::ProcessAttribute(
        CMetadataXMPAltReaderWriter *this,
        struct IXMLDOMNode *a2,
        struct IXMLDOMNode *a3,
        struct RDFItem **a4,
        int *a5,
        struct XMLItem **a6,
        int *a7)
{
  struct XMLItem **v11; // rdi
  int *v12; // rsi
  int *v13; // r14
  int v14; // eax
  unsigned int v15; // ebx
  LPCWSTR lpString1; // [rsp+98h] [rbp+10h] BYREF

  lpString1 = 0;
  if ( a4 )
    *a4 = 0;
  v11 = a6;
  if ( a6 )
    *a6 = 0;
  v12 = a5;
  if ( a5 )
    *a5 = 0;
  v13 = a7;
  if ( a7 )
    *a7 = 0;
  v14 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, LPCWSTR *))a2->lpVtbl->get_nodeName)(a2, &lpString1);
  v15 = v14;
  if ( v14 < 0 )
  {
    if ( !g_doStackCaptures )
      goto LABEL_18;
    goto LABEL_17;
  }
  if ( v14 || lstrcmpW(lpString1, L"xml:lang") )
  {
    v14 = CMetadataRDFReaderWriter::ProcessAttribute(this, a2, a3, a4, v12, v11, v13);
    v15 = v14;
    if ( v14 < 0 && g_doStackCaptures )
LABEL_17:
      DoStackCapture(v14);
  }
  else
  {
    *((_DWORD *)this + 62) = 1;
  }
LABEL_18:
  SysFreeString((BSTR)lpString1);
  return v15;
}

```

## disassembly

```asm
0x18000c6a0  mov     r11, rsp
0x18000c6a3  push    rbx
0x18000c6a4  push    rbp
0x18000c6a5  push    rsi
0x18000c6a6  push    rdi
0x18000c6a7  push    r12
0x18000c6a9  push    r13
0x18000c6ab  push    r14
0x18000c6ad  push    r15
0x18000c6af  sub     rsp, 48h
0x18000c6b3  xor     eax, eax
0x18000c6b5  mov     r15, r9
0x18000c6b8  mov     [r11+10h], rax
0x18000c6bc  mov     r13, r8
0x18000c6bf  mov     r12, rdx
0x18000c6c2  mov     rbp, rcx
0x18000c6c5  test    r9, r9
0x18000c6c8  jz      short loc_18000C6CD
0x18000c6ca  mov     [r9], rax
0x18000c6cd  mov     rdi, [rsp+88h+arg_28]
0x18000c6d5  test    rdi, rdi
0x18000c6d8  jz      short loc_18000C6DD
0x18000c6da  mov     [rdi], rax
0x18000c6dd  mov     rsi, [rsp+88h+arg_20]
0x18000c6e5  test    rsi, rsi
0x18000c6e8  jz      short loc_18000C6EC
0x18000c6ea  mov     [rsi], eax
0x18000c6ec  mov     r14, [rsp+88h+arg_30]
0x18000c6f4  test    r14, r14
0x18000c6f7  jz      short loc_18000C6FC
0x18000c6f9  mov     [r14], eax
0x18000c6fc  mov     rax, [rdx]
0x18000c6ff  mov     rcx, r12
0x18000c702  lea     rdx, [rsp+88h+lpString1]
0x18000c70a  mov     rax, [rax+38h]
0x18000c70e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c713  mov     ebx, eax
0x18000c715  test    eax, eax
0x18000c717  jns     short loc_18000C726
0x18000c719  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000c720  jnz     short loc_18000C77C
0x18000c722  test    eax, eax
0x18000c724  js      short loc_18000C783
0x18000c726  jnz     short loc_18000C74D
0x18000c728  mov     rcx, [rsp+88h+lpString1]; lpString1
0x18000c730  lea     rdx, psz; "xml:lang"
0x18000c737  call    cs:__imp_lstrcmpW
0x18000c73d  test    eax, eax
0x18000c73f  jnz     short loc_18000C74D
0x18000c741  mov     dword ptr [rbp+0F8h], 1
0x18000c74b  jmp     short loc_18000C783
0x18000c74d  mov     [rsp+88h+var_58], r14; int *
0x18000c752  mov     r9, r15; struct RDFItem **
0x18000c755  mov     [rsp+88h+var_60], rdi; struct XMLItem **
0x18000c75a  mov     r8, r13; struct IXMLDOMNode *
0x18000c75d  mov     rdx, r12; struct IXMLDOMNode *
0x18000c760  mov     [rsp+88h+var_68], rsi; int *
0x18000c765  mov     rcx, rbp; this
0x18000c768  call    ?ProcessAttribute@CMetadataRDFReaderWriter@@MEAAJPEAUIXMLDOMNode@@0PEAPEAVRDFItem@@PEAHPEAPEAVXMLItem@@2@Z; CMetadataRDFReaderWriter::ProcessAttribute(IXMLDOMNode *,IXMLDOMNode *,RDFItem * *,int *,XMLItem * *,int *)
0x18000c76d  mov     ebx, eax
0x18000c76f  test    eax, eax
0x18000c771  jns     short loc_18000C783
0x18000c773  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000c77a  jz      short loc_18000C783
0x18000c77c  mov     ecx, eax; int
0x18000c77e  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000c783  mov     rcx, [rsp+88h+lpString1]; bstrString
0x18000c78b  call    cs:__imp_SysFreeString
0x18000c791  mov     eax, ebx
0x18000c793  add     rsp, 48h
0x18000c797  pop     r15
0x18000c799  pop     r14
0x18000c79b  pop     r13
0x18000c79d  pop     r12
0x18000c79f  pop     rdi
0x18000c7a0  pop     rsi
0x18000c7a1  pop     rbp
0x18000c7a2  pop     rbx
0x18000c7a3  retn
```
