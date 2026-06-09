# ConvertDelimitedString(tagPROPVARIANT const *,ushort const *,tagPROPVARIANT *)

- ea: `0x180008b7c`
- end: `0x180008c20`
- name: `?ConvertDelimitedString@@YAJPEBUtagPROPVARIANT@@PEBGPEAU1@@Z`
- size: `164`
- prototype: `int(const struct tagPROPVARIANT *, const unsigned __int16 *, struct tagPROPVARIANT *)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007990`
- `0x180007af0`
- `0x18001f0e4`

## callees

- `0x1800076f0`
- `0x180008b7c`
- `0x180008c28`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008c01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008c01`

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
0x180008b7c  mov     [rsp+arg_8], rbx
0x180008b81  mov     [rsp+arg_10], rsi
0x180008b86  push    rdi
0x180008b87  sub     rsp, 20h
0x180008b8b  xor     eax, eax
0x180008b8d  xorps   xmm0, xmm0
0x180008b90  movups  xmmword ptr [r8], xmm0
0x180008b94  mov     [r8+10h], rax
0x180008b98  mov     rdi, r8
0x180008b9b  movzx   r9d, word ptr [rcx]
0x180008b9f  mov     rsi, rdx
0x180008ba2  sub     r9d, 1Eh
0x180008ba6  jz      short loc_180008BD1
0x180008ba8  sub     r9d, 1
0x180008bac  jz      short loc_180008BC4
0x180008bae  cmp     r9d, 0FF2h
0x180008bb5  jz      short loc_180008BBE
0x180008bb7  mov     ebx, 80070057h
0x180008bbc  jmp     short loc_180008C0D
0x180008bbe  mov     rcx, [rcx+10h]
0x180008bc2  jmp     short loc_180008BC8
0x180008bc4  mov     rcx, [rcx+8]; unsigned __int16 *
0x180008bc8  call    ?ConvertDelimitedStringToPropvar@@YAJPEBG0PEAUtagPROPVARIANT@@@Z; ConvertDelimitedStringToPropvar(ushort const *,ushort const *,tagPROPVARIANT *)
0x180008bcd  mov     ebx, eax
0x180008bcf  jmp     short loc_180008C0D
0x180008bd1  mov     rcx, [rcx+8]; lpMultiByteStr
0x180008bd5  lea     r8, [rsp+28h+pv]; unsigned __int16 **
0x180008bda  mov     [rsp+28h+pv], rax
0x180008bdf  call    ?SniffAndConvertToWideString@@YAJPEBDPEAHPEAPEAG@Z; SniffAndConvertToWideString(char const *,int *,ushort * *)
0x180008be4  mov     ebx, eax
0x180008be6  test    eax, eax
0x180008be8  js      short loc_180008C0D
0x180008bea  mov     rcx, [rsp+28h+pv]; unsigned __int16 *
0x180008bef  mov     r8, rdi; pvar
0x180008bf2  mov     rdx, rsi; Delimiter
0x180008bf5  call    ?ConvertDelimitedStringToPropvar@@YAJPEBG0PEAUtagPROPVARIANT@@@Z; ConvertDelimitedStringToPropvar(ushort const *,ushort const *,tagPROPVARIANT *)
0x180008bfa  mov     rcx, [rsp+28h+pv]; pv
0x180008bff  mov     ebx, eax
0x180008c01  call    cs:__imp_CoTaskMemFree
0x180008c08  nop     dword ptr [rax+rax+00h]
0x180008c0d  mov     rsi, [rsp+28h+arg_10]
0x180008c12  mov     eax, ebx
0x180008c14  mov     rbx, [rsp+28h+arg_8]
0x180008c19  add     rsp, 20h
0x180008c1d  pop     rdi
0x180008c1e  retn
```
