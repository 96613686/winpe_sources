# CMetadataHandler::GetIdFromVariant(DataSetDescription const *,uint,tagPROPVARIANT const *,ushort *)

- ea: `0x18001d5e0`
- end: `0x18001d6e1`
- name: `?GetIdFromVariant@CMetadataHandler@@MEAAJPEBUDataSetDescription@@IPEBUtagPROPVARIANT@@PEAG@Z`
- size: `257`
- prototype: `int(CMetadataHandler *__hidden this, const struct DataSetDescription *, unsigned int, const struct tagPROPVARIANT *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800027e0`
- `0x1800171c4`
- `0x18001d5e0`
- `0x18001d6e8`
- `0x18002be2c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d6d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d6d0`

## pseudocode

```c
__int64 __fastcall CMetadataHandler::GetIdFromVariant(
        CMetadataHandler *this,
        const struct DataSetDescription *a2,
        __int64 a3,
        const struct tagPROPVARIANT *a4,
        unsigned __int16 *a5)
{
  void *v5; // rdi
  unsigned int v6; // esi
  bool v7; // zf
  unsigned __int16 *DataSetDesc; // rax
  unsigned int v10; // ebx
  int v11; // eax
  CMetadataHandler *v12; // rcx
  unsigned __int16 *v13; // rax
  int v14; // ecx
  int v15; // eax
  LPVOID pv; // [rsp+68h] [rbp+20h] BYREF

  v5 = 0;
  v6 = a3;
  v7 = a4->vt == 31;
  pv = 0;
  if ( v7 )
  {
    DataSetDesc = (unsigned __int16 *)CMetadataHandler::FindDataSetDesc(this, a2, a3, a4->bstrVal);
    if ( DataSetDesc )
    {
      v10 = 0;
      *a5 = *DataSetDesc;
    }
    else
    {
      v10 = -2147024809;
      if ( g_doStackCaptures )
        DoStackCapture(-2147024809);
    }
    return v10;
  }
  if ( a4->vt == 30 )
  {
    v11 = CoerceAnsiStrToWideStr(a4->pszVal, (unsigned __int16 **)&pv, a3, (UINT)a4);
    v10 = v11;
    if ( v11 < 0 )
    {
      if ( g_doStackCaptures )
        DoStackCapture(v11);
      v5 = pv;
      goto LABEL_20;
    }
    v5 = pv;
    v13 = (unsigned __int16 *)CMetadataHandler::FindDataSetDesc(v12, a2, v6, (const unsigned __int16 *)pv);
    if ( v13 )
    {
      *a5 = *v13;
      goto LABEL_20;
    }
    v10 = -2147024809;
    if ( g_doStackCaptures )
    {
      v14 = -2147024809;
LABEL_19:
      DoStackCapture(v14);
    }
  }
  else
  {
    v15 = CMetadataHandler::CoerceVariantToUShort(this, a4, a5);
    v10 = v15;
    if ( v15 < 0 && g_doStackCaptures )
    {
      v14 = v15;
      goto LABEL_19;
    }
  }
LABEL_20:
  if ( v5 )
    CoTaskMemFree(v5);
  return v10;
}

```

## disassembly

```asm
0x18001d5e0  push    rbx
0x18001d5e2  push    rbp
0x18001d5e3  push    rsi
0x18001d5e4  push    rdi
0x18001d5e5  sub     rsp, 28h
0x18001d5e9  xor     edi, edi
0x18001d5eb  mov     esi, r8d
0x18001d5ee  cmp     word ptr [r9], 1Fh
0x18001d5f3  mov     rbp, rdx
0x18001d5f6  mov     [rsp+48h+pv], rdi
0x18001d5fb  jnz     short loc_18001D63A
0x18001d5fd  mov     r9, [r9+8]; unsigned __int16 *
0x18001d601  call    ?FindDataSetDesc@CMetadataHandler@@IEAAPEBUDataSetDescription@@PEBU2@IPEBG@Z; CMetadataHandler::FindDataSetDesc(DataSetDescription const *,uint,ushort const *)
0x18001d606  test    rax, rax
0x18001d609  jz      short loc_18001D61D
0x18001d60b  movzx   ecx, word ptr [rax]
0x18001d60e  xor     ebx, ebx
0x18001d610  mov     rax, [rsp+48h+arg_20]
0x18001d615  mov     [rax], cx
0x18001d618  jmp     loc_18001D6D6
0x18001d61d  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x18001d623  mov     ebx, 80070057h
0x18001d628  jz      loc_18001D6D6
0x18001d62e  mov     ecx, ebx; int
0x18001d630  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001d635  jmp     loc_18001D6D6
0x18001d63a  cmp     word ptr [r9], 1Eh
0x18001d63f  jnz     short loc_18001D6A6
0x18001d641  mov     rcx, [r9+8]; lpMultiByteStr
0x18001d645  lea     rdx, [rsp+48h+pv]; unsigned __int16 **
0x18001d64a  call    ?CoerceAnsiStrToWideStr@@YAJPEBDPEAPEAGIH@Z; CoerceAnsiStrToWideStr(char const *,ushort * *,uint,int)
0x18001d64f  mov     ebx, eax
0x18001d651  test    eax, eax
0x18001d653  jns     short loc_18001D66F
0x18001d655  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x18001d65b  jz      short loc_18001D66B
0x18001d65d  mov     ecx, eax; int
0x18001d65f  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001d664  mov     rdi, [rsp+48h+pv]
0x18001d669  jmp     short loc_18001D6C8
0x18001d66b  test    eax, eax
0x18001d66d  js      short loc_18001D664
0x18001d66f  mov     rdi, [rsp+48h+pv]
0x18001d674  mov     r8d, esi; unsigned int
0x18001d677  mov     r9, rdi; unsigned __int16 *
0x18001d67a  mov     rdx, rbp; struct DataSetDescription *
0x18001d67d  call    ?FindDataSetDesc@CMetadataHandler@@IEAAPEBUDataSetDescription@@PEBU2@IPEBG@Z; CMetadataHandler::FindDataSetDesc(DataSetDescription const *,uint,ushort const *)
0x18001d682  test    rax, rax
0x18001d685  jz      short loc_18001D694
0x18001d687  movzx   ecx, word ptr [rax]
0x18001d68a  mov     rax, [rsp+48h+arg_20]
0x18001d68f  mov     [rax], cx
0x18001d692  jmp     short loc_18001D6C8
0x18001d694  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18001d69b  mov     ebx, 80070057h
0x18001d6a0  jz      short loc_18001D6C8
0x18001d6a2  mov     ecx, ebx; this
0x18001d6a4  jmp     short loc_18001D6C3
0x18001d6a6  mov     r8, [rsp+48h+arg_20]; unsigned __int16 *
0x18001d6ab  mov     rdx, r9; struct tagPROPVARIANT *
0x18001d6ae  call    ?CoerceVariantToUShort@CMetadataHandler@@IEAAJPEBUtagPROPVARIANT@@PEAG@Z; CMetadataHandler::CoerceVariantToUShort(tagPROPVARIANT const *,ushort *)
0x18001d6b3  mov     ebx, eax
0x18001d6b5  test    eax, eax
0x18001d6b7  jns     short loc_18001D6C8
0x18001d6b9  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x18001d6bf  jz      short loc_18001D6C8
0x18001d6c1  mov     ecx, eax; int
0x18001d6c3  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001d6c8  test    rdi, rdi
0x18001d6cb  jz      short loc_18001D6D6
0x18001d6cd  mov     rcx, rdi; pv
0x18001d6d0  call    cs:__imp_CoTaskMemFree
0x18001d6d6  mov     eax, ebx
0x18001d6d8  add     rsp, 28h
0x18001d6dc  pop     rdi
0x18001d6dd  pop     rsi
0x18001d6de  pop     rbp
0x18001d6df  pop     rbx
0x18001d6e0  retn
```
