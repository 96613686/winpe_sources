# CFileDownload_DMChannel::GetBlockIndexToRead(long &)

- ea: `0x180011980`
- end: `0x1800119f6`
- name: `?GetBlockIndexToRead@CFileDownload_DMChannel@@QEAAJAEAJ@Z`
- size: `118`
- prototype: `__int64 __fastcall(CFileDownload_DMChannel *__hidden this, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a010`

## callees

- `0x18000108c`
- `0x180011108`
- `0x180011980`

## string_xrefs

- `0x180011995`: `BlockIndexToRead`

## pseudocode

```c
__int64 __fastcall CFileDownload_DMChannel::GetBlockIndexToRead(CFileDownload_DMChannel *this, unsigned int *a2)
{
  int v3; // ebx
  __int64 v4; // r8
  __int64 v5; // r9
  unsigned int v7; // [rsp+40h] [rbp+8h] BYREF
  int v8; // [rsp+50h] [rbp+18h] BYREF
  unsigned int v9; // [rsp+58h] [rbp+20h] BYREF

  v7 = 0;
  v3 = CRegUtils::QueryDWORDValue(this, L"BlockIndexToRead", &v7);
  if ( v3 >= 0 )
    *a2 = v7;
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    v8 = v3;
    v9 = v7;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v7,
      (__int64)&dword_18003FBB4,
      v4,
      v5,
      (__int64)&v9,
      (__int64)&v8);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180011980  mov     [rsp+arg_8], rbx
0x180011985  push    rdi
0x180011986  sub     rsp, 30h
0x18001198a  mov     rdi, rdx
0x18001198d  mov     [rsp+38h+arg_0], 0
0x180011995  lea     rdx, aBlockindextore; "BlockIndexToRead"
0x18001199c  lea     r8, [rsp+38h+arg_0]; unsigned int *
0x1800119a1  call    ?QueryDWORDValue@CRegUtils@@SAJAEAVCRegKey@ATL@@PEBGAEAK@Z; CRegUtils::QueryDWORDValue(ATL::CRegKey &,ushort const *,ulong &)
0x1800119a6  mov     ebx, eax
0x1800119a8  test    eax, eax
0x1800119aa  js      short loc_1800119B2
0x1800119ac  mov     ecx, [rsp+38h+arg_0]
0x1800119b0  mov     [rdi], ecx
0x1800119b2  mov     ecx, cs:dword_180048E90
0x1800119b8  cmp     ecx, 5
0x1800119bb  jbe     short loc_1800119E9
0x1800119bd  mov     ecx, [rsp+38h+arg_0]
0x1800119c1  lea     rax, [rsp+38h+arg_10]
0x1800119c6  mov     [rsp+38h+var_10], rax
0x1800119cb  lea     rdx, dword_18003FBB4
0x1800119d2  lea     rax, [rsp+38h+arg_18]
0x1800119d7  mov     [rsp+38h+arg_10], ebx
0x1800119db  mov     [rsp+38h+var_18], rax
0x1800119e0  mov     [rsp+38h+arg_18], ecx
0x1800119e4  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800119e9  mov     eax, ebx
0x1800119eb  mov     rbx, [rsp+38h+arg_8]
0x1800119f0  add     rsp, 30h
0x1800119f4  pop     rdi
0x1800119f5  retn
```
