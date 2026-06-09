# CorrelationId::CorrelationId(void)

- ea: `0x180009580`
- end: `0x180009614`
- name: `??0CorrelationId@@QEAA@XZ`
- size: `148`
- prototype: `CorrelationId *__fastcall(CorrelationId *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000961c`

## callees

- `0x1800090d0`
- `0x180009580`
- `0x18001532c`
- `0x180016d2c`
- `0x1800189e0`
- `0x180019c98`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800095d6`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800095d6`
- `RPCRT4!UuidCreate` at `0x1800095b5`
- `RPCRT4!UuidCreate` at `0x1800095b5`

## pseudocode

```c
CorrelationId *__fastcall CorrelationId::CorrelationId(CorrelationId *this)
{
  CorrelationId *v2; // rdi
  OLECHAR *BufferSetLength; // rax
  int v4; // eax
  __int64 v5; // rdx

  LOBYTE(this->connId.Data1) = 0;
  v2 = this + 1;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&this[1]);
  *(_OWORD *)&this->connId.Data2 = 0;
  if ( !UuidCreate((UUID *)&this->connId.Data2) )
  {
    BufferSetLength = (OLECHAR *)ATL::CSimpleStringT<unsigned short,0>::GetBufferSetLength(v2, 38);
    v4 = StringFromGUID2((const GUID *const)&this->connId.Data2, BufferSetLength, 39);
    v5 = (unsigned int)(v4 - 1);
    if ( v4 <= 0 )
      v5 = 0;
    ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(v2, v5);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Trim(v2);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::MakeLower(v2);
  }
  return this;
}

```

## disassembly

```asm
0x180009580  mov     [rsp+arg_8], rbx
0x180009585  mov     [rsp+arg_10], rsi
0x18000958a  mov     [rsp+arg_0], rcx
0x18000958f  push    rdi
0x180009590  sub     rsp, 20h
0x180009594  mov     rbx, rcx
0x180009597  mov     byte ptr [rcx], 0
0x18000959a  lea     rdi, [rcx+18h]
0x18000959e  mov     rcx, rdi; void *
0x1800095a1  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800095a6  nop
0x1800095a7  xorps   xmm0, xmm0
0x1800095aa  lea     rsi, [rbx+4]
0x1800095ae  movdqu  xmmword ptr [rsi], xmm0
0x1800095b2  mov     rcx, rsi; Uuid
0x1800095b5  call    cs:__imp_UuidCreate
0x1800095bb  test    eax, eax
0x1800095bd  jnz     short loc_180009601
0x1800095bf  lea     edx, [rax+26h]
0x1800095c2  mov     rcx, rdi
0x1800095c5  call    ?GetBufferSetLength@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::GetBufferSetLength(int)
0x1800095ca  mov     rdx, rax; lpsz
0x1800095cd  mov     r8d, 27h ; '''; cchMax
0x1800095d3  mov     rcx, rsi; rguid
0x1800095d6  call    cs:__imp_StringFromGUID2
0x1800095dc  lea     edx, [rax-1]
0x1800095df  xor     r8d, r8d
0x1800095e2  test    eax, eax
0x1800095e4  cmovle  edx, r8d
0x1800095e8  mov     rcx, rdi
0x1800095eb  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x1800095f0  mov     rcx, rdi
0x1800095f3  call    ?Trim@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Trim(ushort const *)
0x1800095f8  mov     rcx, rdi
0x1800095fb  call    ?MakeLower@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::MakeLower(void)
0x180009600  nop
0x180009601  mov     rax, rbx
0x180009604  mov     rbx, [rsp+28h+arg_8]
0x180009609  mov     rsi, [rsp+28h+arg_10]
0x18000960e  add     rsp, 20h
0x180009612  pop     rdi
0x180009613  retn
```
