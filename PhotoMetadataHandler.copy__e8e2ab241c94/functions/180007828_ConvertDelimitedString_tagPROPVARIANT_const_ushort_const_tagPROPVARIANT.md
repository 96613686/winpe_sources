# ConvertDelimitedString(tagPROPVARIANT const *,ushort const *,tagPROPVARIANT *)

- ea: `0x180007828`
- end: `0x1800078c5`
- name: `?ConvertDelimitedString@@YAJPEBUtagPROPVARIANT@@PEBGPEAU1@@Z`
- size: `157`
- prototype: `__int64 __fastcall(const struct tagPROPVARIANT *, wchar_t *, struct tagPROPVARIANT *)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006720`
- `0x180006860`
- `0x18001e2a0`

## callees

- `0x180007828`
- `0x1800078cc`
- `0x180008b60`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800078ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800078ad`

## pseudocode

```c
__int64 __fastcall ConvertDelimitedString(const struct tagPROPVARIANT *a1, wchar_t *a2, struct tagPROPVARIANT *a3)
{
  int v5; // ebx
  BYTE *pbVal; // rcx
  const CHAR *pszVal; // rcx
  LPVOID pv; // [rsp+30h] [rbp+8h] BYREF

  *(_OWORD *)&a3->vt = 0;
  a3->bstrblobVal.pData = 0;
  if ( a1->vt != 30 )
  {
    if ( a1->vt == 31 )
    {
      pbVal = a1->pbVal;
    }
    else
    {
      if ( a1->vt != 4113 )
        return (unsigned int)-2147024809;
      pbVal = a1->bstrblobVal.pData;
    }
    return (unsigned int)ConvertDelimitedStringToPropvar((const unsigned __int16 *)pbVal, a2, a3);
  }
  pszVal = a1->pszVal;
  pv = 0;
  v5 = SniffAndConvertToWideString(pszVal, (int *)a2, &pv);
  if ( v5 >= 0 )
  {
    v5 = ConvertDelimitedStringToPropvar((const unsigned __int16 *)pv, a2, a3);
    CoTaskMemFree(pv);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180007828  mov     [rsp+arg_8], rbx
0x18000782d  mov     [rsp+arg_10], rsi
0x180007832  push    rdi
0x180007833  sub     rsp, 20h
0x180007837  xor     eax, eax
0x180007839  xorps   xmm0, xmm0
0x18000783c  movups  xmmword ptr [r8], xmm0
0x180007840  mov     [r8+10h], rax
0x180007844  mov     rdi, r8
0x180007847  movzx   r9d, word ptr [rcx]
0x18000784b  mov     rsi, rdx
0x18000784e  sub     r9d, 1Eh
0x180007852  jz      short loc_18000787D
0x180007854  sub     r9d, 1
0x180007858  jz      short loc_180007870
0x18000785a  cmp     r9d, 0FF2h
0x180007861  jz      short loc_18000786A
0x180007863  mov     ebx, 80070057h
0x180007868  jmp     short loc_1800078B3
0x18000786a  mov     rcx, [rcx+10h]
0x18000786e  jmp     short loc_180007874
0x180007870  mov     rcx, [rcx+8]; unsigned __int16 *
0x180007874  call    ?ConvertDelimitedStringToPropvar@@YAJPEBG0PEAUtagPROPVARIANT@@@Z; ConvertDelimitedStringToPropvar(ushort const *,ushort const *,tagPROPVARIANT *)
0x180007879  mov     ebx, eax
0x18000787b  jmp     short loc_1800078B3
0x18000787d  mov     rcx, [rcx+8]; lpMultiByteStr
0x180007881  lea     r8, [rsp+28h+pv]; unsigned __int16 **
0x180007886  mov     [rsp+28h+pv], rax
0x18000788b  call    ?SniffAndConvertToWideString@@YAJPEBDPEAHPEAPEAG@Z; SniffAndConvertToWideString(char const *,int *,ushort * *)
0x180007890  mov     ebx, eax
0x180007892  test    eax, eax
0x180007894  js      short loc_1800078B3
0x180007896  mov     rcx, [rsp+28h+pv]; unsigned __int16 *
0x18000789b  mov     r8, rdi; pvar
0x18000789e  mov     rdx, rsi; Delimiter
0x1800078a1  call    ?ConvertDelimitedStringToPropvar@@YAJPEBG0PEAUtagPROPVARIANT@@@Z; ConvertDelimitedStringToPropvar(ushort const *,ushort const *,tagPROPVARIANT *)
0x1800078a6  mov     rcx, [rsp+28h+pv]; pv
0x1800078ab  mov     ebx, eax
0x1800078ad  call    cs:__imp_CoTaskMemFree
0x1800078b3  mov     rsi, [rsp+28h+arg_10]
0x1800078b8  mov     eax, ebx
0x1800078ba  mov     rbx, [rsp+28h+arg_8]
0x1800078bf  add     rsp, 20h
0x1800078c3  pop     rdi
0x1800078c4  retn
```
