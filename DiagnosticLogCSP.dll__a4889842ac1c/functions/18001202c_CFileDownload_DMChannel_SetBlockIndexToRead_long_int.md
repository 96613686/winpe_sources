# CFileDownload_DMChannel::SetBlockIndexToRead(long,int)

- ea: `0x18001202c`
- end: `0x1800120c6`
- name: `?SetBlockIndexToRead@CFileDownload_DMChannel@@QEAAJJH@Z`
- size: `154`
- prototype: `__int64 __fastcall(CFileDownload_DMChannel *this, signed int, int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a250`
- `0x180011cd4`

## callees

- `0x18000108c`
- `0x18001156c`
- `0x1800116a4`
- `0x18001202c`

## string_xrefs

- `0x180012070`: `BlockIndexToRead`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFileDownload_DMChannel::SetBlockIndexToRead(CFileDownload_DMChannel *this, signed int a2, int a3)
{
  int BlockCount; // ebx
  int v6; // r8d
  int v7; // r9d
  int v9; // [rsp+50h] [rbp+18h] BYREF
  signed int v10; // [rsp+58h] [rbp+20h] BYREF

  if ( !a3 )
    goto LABEL_6;
  v9 = 0;
  BlockCount = CFileDownload_DMChannel::GetBlockCount(this, &v9);
  if ( BlockCount < 0 )
    goto LABEL_7;
  if ( a2 < 0 || a2 >= v9 )
    BlockCount = -2147024809;
  else
LABEL_6:
    BlockCount = CRegUtils::SetDWORDValue(this, L"BlockIndexToRead", a2);
LABEL_7:
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    v9 = BlockCount;
    v10 = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      dword_180048E90,
      (unsigned int)&word_18003FC56,
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
0x18001202c  mov     rax, rsp
0x18001202f  mov     [rax+8], rbx
0x180012033  mov     [rax+10h], rsi
0x180012037  push    rdi
0x180012038  sub     rsp, 30h
0x18001203c  mov     edi, edx
0x18001203e  mov     rsi, rcx
0x180012041  test    r8d, r8d
0x180012044  jz      short loc_18001206D
0x180012046  lea     rdx, [rax+18h]; int *
0x18001204a  mov     dword ptr [rax+18h], 0
0x180012051  call    ?GetBlockCount@CFileDownload_DMChannel@@QEAAJAEAJ@Z; CFileDownload_DMChannel::GetBlockCount(long &)
0x180012056  mov     ebx, eax
0x180012058  test    eax, eax
0x18001205a  js      short loc_180012081
0x18001205c  test    edi, edi
0x18001205e  js      short loc_180012066
0x180012060  cmp     edi, [rsp+38h+arg_10]
0x180012064  jl      short loc_18001206D
0x180012066  mov     ebx, 80070057h
0x18001206b  jmp     short loc_180012081
0x18001206d  mov     r8d, edi; unsigned int
0x180012070  lea     rdx, aBlockindextore; "BlockIndexToRead"
0x180012077  mov     rcx, rsi; struct ATL::CRegKey *
0x18001207a  call    ?SetDWORDValue@CRegUtils@@SAJAEAVCRegKey@ATL@@PEBGK@Z; CRegUtils::SetDWORDValue(ATL::CRegKey &,ushort const *,ulong)
0x18001207f  mov     ebx, eax
0x180012081  mov     ecx, cs:dword_180048E90
0x180012087  cmp     ecx, 5
0x18001208a  jbe     short loc_1800120B4
0x18001208c  lea     rax, [rsp+38h+arg_10]
0x180012091  mov     [rsp+38h+arg_10], ebx
0x180012095  mov     [rsp+38h+var_10], rax
0x18001209a  lea     rdx, word_18003FC56
0x1800120a1  lea     rax, [rsp+38h+arg_18]
0x1800120a6  mov     [rsp+38h+arg_18], edi
0x1800120aa  mov     [rsp+38h+var_18], rax
0x1800120af  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800120b4  mov     rsi, [rsp+38h+arg_8]
0x1800120b9  mov     eax, ebx
0x1800120bb  mov     rbx, [rsp+38h+arg_0]
0x1800120c0  add     rsp, 30h
0x1800120c4  pop     rdi
0x1800120c5  retn
```
