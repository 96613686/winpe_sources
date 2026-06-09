# CFileDownload_DMChannel::GetBlockIndexToRead(long &)

- ea: `0x1800122f4`
- end: `0x18001236b`
- name: `?GetBlockIndexToRead@CFileDownload_DMChannel@@QEAAJAEAJ@Z`
- size: `119`
- prototype: `__int64 __fastcall(CFileDownload_DMChannel *__hidden this, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a320`

## callees

- `0x180001090`
- `0x1800119c8`
- `0x1800122f4`

## string_xrefs

- `0x180012309`: `BlockIndexToRead`

## pseudocode

```c
__int64 __fastcall CFileDownload_DMChannel::GetBlockIndexToRead(CFileDownload_DMChannel *this, unsigned int *a2)
{
  int v3; // ebx
  int v4; // r8d
  int v5; // r9d
  unsigned int v7; // [rsp+40h] [rbp+8h] BYREF
  int v8; // [rsp+50h] [rbp+18h] BYREF
  unsigned int v9; // [rsp+58h] [rbp+20h] BYREF

  v7 = 0;
  v3 = CRegUtils::QueryDWORDValue(this, L"BlockIndexToRead", &v7);
  if ( v3 >= 0 )
    *a2 = v7;
  if ( (unsigned int)dword_18004AE90 > 5 )
  {
    v8 = v3;
    v9 = v7;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v7,
      (unsigned int)&dword_180041BB4,
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
0x1800122f4  mov     [rsp+arg_8], rbx
0x1800122f9  push    rdi
0x1800122fa  sub     rsp, 30h
0x1800122fe  mov     rdi, rdx
0x180012301  mov     [rsp+38h+arg_0], 0
0x180012309  lea     rdx, aBlockindextore; "BlockIndexToRead"
0x180012310  lea     r8, [rsp+38h+arg_0]; unsigned int *
0x180012315  call    ?QueryDWORDValue@CRegUtils@@SAJAEAVCRegKey@ATL@@PEBGAEAK@Z; CRegUtils::QueryDWORDValue(ATL::CRegKey &,ushort const *,ulong &)
0x18001231a  mov     ebx, eax
0x18001231c  test    eax, eax
0x18001231e  js      short loc_180012326
0x180012320  mov     ecx, [rsp+38h+arg_0]
0x180012324  mov     [rdi], ecx
0x180012326  mov     ecx, cs:dword_18004AE90
0x18001232c  cmp     ecx, 5
0x18001232f  jbe     short loc_18001235D
0x180012331  mov     ecx, [rsp+38h+arg_0]
0x180012335  lea     rax, [rsp+38h+arg_10]
0x18001233a  mov     [rsp+38h+var_10], rax
0x18001233f  lea     rdx, dword_180041BB4
0x180012346  lea     rax, [rsp+38h+arg_18]
0x18001234b  mov     [rsp+38h+arg_10], ebx
0x18001234f  mov     [rsp+38h+var_18], rax
0x180012354  mov     [rsp+38h+arg_18], ecx
0x180012358  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001235d  mov     eax, ebx
0x18001235f  mov     rbx, [rsp+38h+arg_8]
0x180012364  add     rsp, 30h
0x180012368  pop     rdi
0x180012369  retn
```
