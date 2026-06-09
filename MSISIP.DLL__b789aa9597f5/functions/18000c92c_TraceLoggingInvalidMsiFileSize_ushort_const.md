# TraceLoggingInvalidMsiFileSize(ushort const *)

- ea: `0x18000c92c`
- end: `0x18000c97b`
- name: `?TraceLoggingInvalidMsiFileSize@@YAXPEBG@Z`
- size: `79`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800022b0`

## callees

- `0x1800010a8`
- `0x180001138`
- `0x18000c92c`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18000c935`
- `msvcrt!wcsrchr` at `0x18000c935`

## pseudocode

```c
void __fastcall TraceLoggingInvalidMsiFileSize(const unsigned __int16 *a1)
{
  __int64 v1; // rdx
  wchar_t *v2; // r8
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 *v6; // [rsp+48h] [rbp+10h] BYREF

  v2 = wcsrchr(a1, 0x5Cu);
  if ( v2 && (unsigned int)dword_180013000 > 4 )
  {
    if ( (unsigned __int8)tlgKeywordOn((unsigned int)dword_180013000, v1, v2) )
    {
      v6 = (__int64 *)(v4 + 2);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        v3,
        (unsigned __int8 *)byte_180010A91,
        v4,
        v5,
        &v6);
    }
  }
}

```

## disassembly

```asm
0x18000c92c  sub     rsp, 38h
0x18000c930  mov     edx, 5Ch ; '\'; Ch
0x18000c935  call    cs:__imp_wcsrchr
0x18000c93b  mov     r8, rax
0x18000c93e  test    rax, rax
0x18000c941  jz      short loc_18000C976
0x18000c943  mov     ecx, cs:dword_180013000
0x18000c949  cmp     ecx, 4
0x18000c94c  jbe     short loc_18000C976
0x18000c94e  call    _tlgKeywordOn
0x18000c953  test    al, al
0x18000c955  jz      short loc_18000C976
0x18000c957  lea     rax, [r8+2]
0x18000c95b  mov     [rsp+38h+arg_8], rax
0x18000c960  lea     rdx, byte_180010A91
0x18000c967  lea     rax, [rsp+38h+arg_8]
0x18000c96c  mov     [rsp+38h+var_18], rax
0x18000c971  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000c976  add     rsp, 38h
0x18000c97a  retn
```
