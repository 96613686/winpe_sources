# ConvertLPWSTRToBytesOnWrite(tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x18002000c`
- end: `0x1800200b9`
- name: `?ConvertLPWSTRToBytesOnWrite@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z`
- size: `173`
- prototype: `int(const struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001d1f0`

## callees

- `0x1800096a0`
- `0x18000c5a0`
- `0x18000d090`
- `0x18002000c`
- `0x180021580`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002002f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002002f`

## pseudocode

```c
HRESULT __fastcall ConvertLPWSTRToBytesOnWrite(const struct tagPROPVARIANT *a1, struct tagPROPVARIANT *a2)
{
  HRESULT result; // eax
  const unsigned __int16 *bstrVal; // rcx
  unsigned int v6; // ecx
  unsigned __int64 v7; // rdx
  unsigned __int16 *pElems; // rcx
  unsigned __int64 pulResult; // [rsp+30h] [rbp+8h] BYREF

  result = -2147467259;
  if ( a1->vt == 31 )
  {
    PropVariantClear(a2);
    bstrVal = a1->bstrVal;
    pulResult = 0;
    result = StringCchLengthW(bstrVal, 0x7FFFFFFFu, &pulResult);
    if ( result >= 0 )
    {
      v6 = pulResult + 1;
      LODWORD(pulResult) = 0;
      result = ULongLongToULong(2LL * v6, (ULONG *)&pulResult);
      if ( result >= 0 )
      {
        result = CoTaskMemAllocWithInit((unsigned int)pulResult, (void **)&a2->bstrblobVal.pData);
        if ( result >= 0 )
        {
          v7 = (unsigned int)pulResult;
          pElems = a2->caui.pElems;
          a2->lVal = pulResult;
          a2->vt = 4113;
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
0x18002000c  mov     [rsp+arg_8], rbx
0x180020011  mov     [rsp+arg_10], rsi
0x180020016  push    rdi
0x180020017  sub     rsp, 20h
0x18002001b  cmp     word ptr [rcx], 1Fh
0x18002001f  mov     rbx, rdx
0x180020022  mov     rdi, rcx
0x180020025  mov     eax, 80004005h
0x18002002a  jnz     short loc_1800200A8
0x18002002c  mov     rcx, rdx; pvar
0x18002002f  call    cs:__imp_PropVariantClear
0x180020036  nop     dword ptr [rax+rax+00h]
0x18002003b  mov     rcx, [rdi+8]; unsigned __int16 *
0x18002003f  lea     r8, [rsp+28h+pulResult]; unsigned __int64 *
0x180020044  mov     edx, 7FFFFFFFh; unsigned __int64
0x180020049  mov     [rsp+28h+pulResult], 0
0x180020052  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180020057  test    eax, eax
0x180020059  js      short loc_1800200A8
0x18002005b  mov     rcx, [rsp+28h+pulResult]
0x180020060  lea     rdx, [rsp+28h+pulResult]; pulResult
0x180020065  inc     rcx
0x180020068  mov     dword ptr [rsp+28h+pulResult], 0
0x180020070  mov     ecx, ecx
0x180020072  add     rcx, rcx; ullOperand
0x180020075  call    ULongLongToULong
0x18002007a  test    eax, eax
0x18002007c  js      short loc_1800200A8
0x18002007e  mov     ecx, dword ptr [rsp+28h+pulResult]; Size
0x180020082  lea     rdx, [rbx+10h]; void **
0x180020086  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x18002008b  test    eax, eax
0x18002008d  js      short loc_1800200A8
0x18002008f  mov     edx, dword ptr [rsp+28h+pulResult]; unsigned __int64
0x180020093  mov     rcx, [rbx+10h]; unsigned __int16 *
0x180020097  mov     [rbx+8], edx
0x18002009a  mov     word ptr [rbx], 1011h
0x18002009f  mov     r8, [rdi+8]; unsigned __int16 *
0x1800200a3  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1800200a8  mov     rbx, [rsp+28h+arg_8]
0x1800200ad  mov     rsi, [rsp+28h+arg_10]
0x1800200b2  add     rsp, 20h
0x1800200b6  pop     rdi
0x1800200b7  retn
```
