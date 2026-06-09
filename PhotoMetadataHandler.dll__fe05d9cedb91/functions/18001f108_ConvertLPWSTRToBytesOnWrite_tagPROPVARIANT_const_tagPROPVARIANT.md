# ConvertLPWSTRToBytesOnWrite(tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x18001f108`
- end: `0x18001f19c`
- name: `?ConvertLPWSTRToBytesOnWrite@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z`
- size: `148`
- prototype: `int(const struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001c4c0`

## callees

- `0x180007d90`
- `0x18000bff0`
- `0x18000ca70`
- `0x18001f108`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001f126`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001f126`

## pseudocode

```c
__int64 __fastcall ConvertLPWSTRToBytesOnWrite(const struct tagPROPVARIANT *a1, struct tagPROPVARIANT *a2)
{
  __int64 result; // rax
  const unsigned __int16 *bstrVal; // rcx
  unsigned __int64 v6; // rcx
  unsigned int v7; // esi
  unsigned __int16 *pElems; // rcx
  unsigned __int64 v9; // [rsp+50h] [rbp+8h] BYREF

  result = 2147500037LL;
  if ( a1->vt == 31 )
  {
    PropVariantClear(a2);
    bstrVal = a1->bstrVal;
    v9 = 0;
    result = StringCchLengthW(bstrVal, 0x7FFFFFFFu, &v9);
    if ( (int)result >= 0 )
    {
      v6 = 2LL * (unsigned int)(v9 + 1);
      if ( v6 > 0xFFFFFFFF )
      {
        return 2147942934LL;
      }
      else
      {
        v7 = 2 * (v9 + 1);
        result = CoTaskMemAllocWithInit((unsigned int)v6, (void **)&a2->bstrblobVal.pData);
        if ( (int)result >= 0 )
        {
          pElems = a2->caui.pElems;
          a2->vt = 4113;
          a2->lVal = v7;
          return StringCbCopyW(pElems, v7, a1->bstrVal);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001f108  push    rbx
0x18001f10a  push    rsi
0x18001f10b  push    rdi
0x18001f10c  push    r14
0x18001f10e  sub     rsp, 28h
0x18001f112  cmp     word ptr [rcx], 1Fh
0x18001f116  mov     rdi, rdx
0x18001f119  mov     rbx, rcx
0x18001f11c  mov     eax, 80004005h
0x18001f121  jnz     short loc_18001F192
0x18001f123  mov     rcx, rdx; pvar
0x18001f126  call    cs:__imp_PropVariantClear
0x18001f12c  mov     rcx, [rbx+8]; unsigned __int16 *
0x18001f130  lea     r8, [rsp+48h+arg_0]; unsigned __int64 *
0x18001f135  mov     edx, 7FFFFFFFh; unsigned __int64
0x18001f13a  mov     [rsp+48h+arg_0], 0
0x18001f143  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001f148  test    eax, eax
0x18001f14a  js      short loc_18001F192
0x18001f14c  mov     rcx, [rsp+48h+arg_0]
0x18001f151  mov     eax, 0FFFFFFFFh
0x18001f156  inc     rcx
0x18001f159  mov     ecx, ecx
0x18001f15b  add     rcx, rcx
0x18001f15e  cmp     rcx, rax
0x18001f161  ja      short loc_18001F18D
0x18001f163  mov     esi, ecx
0x18001f165  lea     rdx, [rdi+10h]; void **
0x18001f169  mov     ecx, ecx; Size
0x18001f16b  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x18001f170  test    eax, eax
0x18001f172  js      short loc_18001F192
0x18001f174  mov     rcx, [rdi+10h]; unsigned __int16 *
0x18001f178  mov     edx, esi; unsigned __int64
0x18001f17a  mov     word ptr [rdi], 1011h
0x18001f17f  mov     [rdi+8], esi
0x18001f182  mov     r8, [rbx+8]; unsigned __int16 *
0x18001f186  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18001f18b  jmp     short loc_18001F192
0x18001f18d  mov     eax, 80070216h
0x18001f192  add     rsp, 28h
0x18001f196  pop     r14
0x18001f198  pop     rdi
0x18001f199  pop     rsi
0x18001f19a  pop     rbx
0x18001f19b  retn
```
