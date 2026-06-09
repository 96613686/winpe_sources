# CFileDownload_DMChannel::SetBlockIndexToRead(long,int)

- ea: `0x1800129e4`
- end: `0x180012a7f`
- name: `?SetBlockIndexToRead@CFileDownload_DMChannel@@QEAAJJH@Z`
- size: `155`
- prototype: `__int64 __fastcall(CFileDownload_DMChannel *__hidden this, unsigned int, int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a570`
- `0x180012670`

## callees

- `0x180001090`
- `0x180011e94`
- `0x180011fe0`
- `0x1800129e4`

## string_xrefs

- `0x180012a28`: `BlockIndexToRead`

## pseudocode

```c
__int64 __fastcall CFileDownload_DMChannel::SetBlockIndexToRead(CFileDownload_DMChannel *this, int a2, int a3)
{
  int BlockCount; // ebx
  int v6; // r8d
  int v7; // r9d
  signed int v9; // [rsp+50h] [rbp+18h] BYREF
  int v10; // [rsp+58h] [rbp+20h] BYREF

  if ( !a3 )
    goto LABEL_6;
  v9 = 0;
  BlockCount = CFileDownload_DMChannel::GetBlockCount(this, (DWORD *)&v9);
  if ( BlockCount < 0 )
    goto LABEL_7;
  if ( a2 < 0 || a2 >= v9 )
    BlockCount = -2147024809;
  else
LABEL_6:
    BlockCount = CRegUtils::SetDWORDValue((HKEY *)this, L"BlockIndexToRead", a2);
LABEL_7:
  if ( (unsigned int)dword_18004AE90 > 5 )
  {
    v9 = BlockCount;
    v10 = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      dword_18004AE90,
      (unsigned int)&word_180041C56,
      v6,
      v7,
      (__int64)&v10,
      (__int64)&v9);
  }
  return (unsigned int)BlockCount;
}

```

## disassembly

```asm
0x1800129e4  mov     rax, rsp
0x1800129e7  mov     [rax+8], rbx
0x1800129eb  mov     [rax+10h], rsi
0x1800129ef  push    rdi
0x1800129f0  sub     rsp, 30h
0x1800129f4  mov     edi, edx
0x1800129f6  mov     rsi, rcx
0x1800129f9  test    r8d, r8d
0x1800129fc  jz      short loc_180012A25
0x1800129fe  lea     rdx, [rax+18h]; int *
0x180012a02  mov     dword ptr [rax+18h], 0
0x180012a09  call    ?GetBlockCount@CFileDownload_DMChannel@@QEAAJAEAJ@Z; CFileDownload_DMChannel::GetBlockCount(long &)
0x180012a0e  mov     ebx, eax
0x180012a10  test    eax, eax
0x180012a12  js      short loc_180012A39
0x180012a14  test    edi, edi
0x180012a16  js      short loc_180012A1E
0x180012a18  cmp     edi, [rsp+38h+arg_10]
0x180012a1c  jl      short loc_180012A25
0x180012a1e  mov     ebx, 80070057h
0x180012a23  jmp     short loc_180012A39
0x180012a25  mov     r8d, edi; unsigned int
0x180012a28  lea     rdx, aBlockindextore; "BlockIndexToRead"
0x180012a2f  mov     rcx, rsi; struct ATL::CRegKey *
0x180012a32  call    ?SetDWORDValue@CRegUtils@@SAJAEAVCRegKey@ATL@@PEBGK@Z; CRegUtils::SetDWORDValue(ATL::CRegKey &,ushort const *,ulong)
0x180012a37  mov     ebx, eax
0x180012a39  mov     ecx, cs:dword_18004AE90
0x180012a3f  cmp     ecx, 5
0x180012a42  jbe     short loc_180012A6C
0x180012a44  lea     rax, [rsp+38h+arg_10]
0x180012a49  mov     [rsp+38h+arg_10], ebx
0x180012a4d  mov     [rsp+38h+var_10], rax
0x180012a52  lea     rdx, word_180041C56
0x180012a59  lea     rax, [rsp+38h+arg_18]
0x180012a5e  mov     [rsp+38h+arg_18], edi
0x180012a62  mov     [rsp+38h+var_18], rax
0x180012a67  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180012a6c  mov     rsi, [rsp+38h+arg_8]
0x180012a71  mov     eax, ebx
0x180012a73  mov     rbx, [rsp+38h+arg_0]
0x180012a78  add     rsp, 30h
0x180012a7c  pop     rdi
0x180012a7d  retn
```
