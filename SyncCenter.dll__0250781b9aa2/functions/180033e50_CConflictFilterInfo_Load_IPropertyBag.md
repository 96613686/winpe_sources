# CConflictFilterInfo::Load(IPropertyBag *)

- ea: `0x180033e50`
- end: `0x180033f04`
- name: `?Load@CConflictFilterInfo@@QEAAJPEAUIPropertyBag@@@Z`
- size: `180`
- prototype: `__int64 __fastcall(CConflictFilterInfo *__hidden this, IPropertyBag *propBag)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180033f10`

## callees

- `0x180005660`
- `0x180033e50`

## import_xrefs

- `PROPSYS!PSPropertyBag_ReadBSTR` at `0x180033e8c`
- `PROPSYS!PSPropertyBag_ReadBSTR` at `0x180033ecb`
- `PROPSYS!PSPropertyBag_ReadBSTR` at `0x180033e8c`
- `PROPSYS!PSPropertyBag_ReadBSTR` at `0x180033ecb`
- `OLEAUT32!__imp_SysFreeString` at `0x180033ead`
- `OLEAUT32!__imp_SysFreeString` at `0x180033eec`
- `OLEAUT32!__imp_SysFreeString` at `0x180033ead`
- `OLEAUT32!__imp_SysFreeString` at `0x180033eec`

## pseudocode

```c
__int64 __fastcall CConflictFilterInfo::Load(CConflictFilterInfo *this, IPropertyBag *propBag)
{
  unsigned __int16 *v2; // rsi
  BSTR bstrString; // [rsp+30h] [rbp+8h] BYREF
  BSTR value; // [rsp+38h] [rbp+10h] BYREF

  v2 = (unsigned __int16 *)((char *)this + 128);
  *(_WORD *)this = 0;
  *((_WORD *)this + 64) = 0;
  if ( propBag )
  {
    bstrString = 0;
    if ( PSPropertyBag_ReadBSTR(propBag, L"SyncHandlerFilter", &bstrString) >= 0 )
    {
      StringCchCopyW((unsigned __int16 *)this, 0x40u, bstrString);
      SysFreeString(bstrString);
    }
    value = 0;
    if ( PSPropertyBag_ReadBSTR(propBag, L"ContentGroupFilter", &value) >= 0 )
    {
      StringCchCopyW(v2, 0x40u, value);
      SysFreeString(value);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180033e50  mov     r11, rsp
0x180033e53  mov     [r11+18h], rbx
0x180033e57  mov     [r11+20h], rsi
0x180033e5b  push    rdi
0x180033e5c  sub     rsp, 20h
0x180033e60  xor     eax, eax
0x180033e62  lea     rsi, [rcx+80h]
0x180033e69  mov     [rcx], ax
0x180033e6c  mov     rdi, rdx
0x180033e6f  mov     [rsi], ax
0x180033e72  mov     rbx, rcx
0x180033e75  test    rdx, rdx
0x180033e78  jz      short loc_180033EF2
0x180033e7a  lea     r8, [r11+8]; value
0x180033e7e  mov     [r11+8], rax
0x180033e82  lea     rdx, propName; "SyncHandlerFilter"
0x180033e89  mov     rcx, rdi; propBag
0x180033e8c  call    cs:__imp_PSPropertyBag_ReadBSTR
0x180033e92  test    eax, eax
0x180033e94  js      short loc_180033EB3
0x180033e96  mov     r8, [rsp+28h+bstrString]; unsigned __int16 *
0x180033e9b  mov     edx, 40h ; '@'; unsigned __int64
0x180033ea0  mov     rcx, rbx; unsigned __int16 *
0x180033ea3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180033ea8  mov     rcx, [rsp+28h+bstrString]; bstrString
0x180033ead  call    cs:__imp_SysFreeString
0x180033eb3  lea     r8, [rsp+28h+value]; value
0x180033eb8  mov     [rsp+28h+value], 0
0x180033ec1  lea     rdx, aContentgroupfi; "ContentGroupFilter"
0x180033ec8  mov     rcx, rdi; propBag
0x180033ecb  call    cs:__imp_PSPropertyBag_ReadBSTR
0x180033ed1  test    eax, eax
0x180033ed3  js      short loc_180033EF2
0x180033ed5  mov     r8, [rsp+28h+value]; unsigned __int16 *
0x180033eda  mov     edx, 40h ; '@'; unsigned __int64
0x180033edf  mov     rcx, rsi; unsigned __int16 *
0x180033ee2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180033ee7  mov     rcx, [rsp+28h+value]; bstrString
0x180033eec  call    cs:__imp_SysFreeString
0x180033ef2  mov     rbx, [rsp+28h+arg_10]
0x180033ef7  xor     eax, eax
0x180033ef9  mov     rsi, [rsp+28h+arg_18]
0x180033efe  add     rsp, 20h
0x180033f02  pop     rdi
0x180033f03  retn
```
