# StateRepository::DataType::ProgId::Hasher::GetProgId(StateRepository::Text &)

- ea: `0x18002151c`
- end: `0x180021637`
- name: `?GetProgId@Hasher@ProgId@DataType@StateRepository@@QEAAJAEAVText@4@@Z`
- size: `283`
- prototype: `int(StateRepository::DataType::ProgId::Hasher *__hidden this, struct StateRepository::Text *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180020c78`

## callees

- `0x18000a3c0`
- `0x18000a77c`
- `0x180014814`
- `0x180014ca0`
- `0x18002151c`
- `0x18002cb80`
- `0x18002cdb4`

## string_xrefs

- `0x18002154e`: `onecore\base\appmodel\staterepository\dataaccesslayer\datatype-progid.cpp`
- `0x1800215a3`: `onecore\base\appmodel\staterepository\dataaccesslayer\datatype-progid.cpp`
- `0x18002161f`: `onecore\base\appmodel\staterepository\dataaccesslayer\datatype-progid.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::DataType::ProgId::Hasher::GetProgId(
        Common::CryptoProvider **this,
        struct StateRepository::Text *a2)
{
  Common::CryptoProvider *v2; // rcx
  int Digest; // edi
  __int64 v5; // rdx
  __int64 result; // rax
  int v7; // eax
  unsigned int v8; // edx
  unsigned __int16 *v9; // r9
  unsigned __int64 v10; // rdx
  int v11; // [rsp+20h] [rbp-28h]
  unsigned __int8 *v12[2]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  unsigned int v14; // [rsp+50h] [rbp+8h] BYREF

  v2 = *this;
  *(_OWORD *)v12 = 0;
  Digest = Common::CryptoProvider::GetDigest(v2, (struct Common::COMMON_BYTES *)v12);
  if ( Digest < 0 )
  {
    v5 = 130;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\datatype-progid.cpp",
      (const char *)(unsigned int)Digest,
      v11);
    return (unsigned int)Digest;
  }
  Digest = StateRepository::Text::EnsureCapacity(a2, 0x25u, 0);
  if ( Digest < 0 )
  {
    v5 = 136;
    goto LABEL_3;
  }
  v7 = StringCchCopyW(*(unsigned __int16 **)a2, 0x25u, L"AppX");
  if ( v7 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x89,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\datatype-progid.cpp",
      (const char *)(unsigned int)v7,
      v11);
  v8 = 20;
  v9 = (unsigned __int16 *)(*(_QWORD *)a2 + 8LL);
  v14 = 0;
  if ( LODWORD(v12[0]) < 0x14 )
    v8 = (unsigned int)v12[0];
  Digest = Common::Base32Encoding::GetChars(v12[1], v8, 0x20u, v9, &v14);
  if ( Digest < 0 )
  {
    v5 = 140;
    goto LABEL_3;
  }
  result = 0;
  v10 = v14 + 4LL;
  *(_WORD *)(*(_QWORD *)a2 + 2 * v10) = 0;
  if ( v10 > 0x27 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x8E,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\datatype-progid.cpp",
      (const char *)0x8000FFFFLL,
      v11);
  return result;
}

```

## disassembly

```asm
0x18002151c  mov     [rsp+arg_8], rbx
0x180021521  push    rdi
0x180021522  sub     rsp, 40h
0x180021526  mov     rcx, [rcx]; this
0x180021529  mov     rbx, rdx
0x18002152c  xorps   xmm0, xmm0
0x18002152f  lea     rdx, [rsp+48h+var_18]; struct Common::COMMON_BYTES *
0x180021534  movups  xmmword ptr [rsp+48h+var_18], xmm0
0x180021539  call    ?GetDigest@CryptoProvider@Common@@QEAAJPEAUCOMMON_BYTES@2@@Z; Common::CryptoProvider::GetDigest(Common::COMMON_BYTES *)
0x18002153e  mov     edi, eax
0x180021540  test    eax, eax
0x180021542  jns     short loc_18002156A
0x180021544  mov     edx, 82h; void *
0x180021549  mov     rcx, [rsp+48h]; this
0x18002154e  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\staterepositor"...
0x180021555  mov     r9d, edi; char *
0x180021558  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002155d  mov     eax, edi
0x18002155f  mov     rbx, [rsp+48h+arg_8]
0x180021564  add     rsp, 40h
0x180021568  pop     rdi
0x180021569  retn
0x18002156a  xor     r8d, r8d; bool
0x18002156d  mov     rcx, rbx; this
0x180021570  lea     edx, [r8+25h]; unsigned __int64
0x180021574  call    ?EnsureCapacity@Text@StateRepository@@QEAAJ_K_N@Z; StateRepository::Text::EnsureCapacity(unsigned __int64,bool)
0x180021579  mov     edi, eax
0x18002157b  test    eax, eax
0x18002157d  jns     short loc_180021586
0x18002157f  mov     edx, 88h
0x180021584  jmp     short loc_180021549
0x180021586  mov     rcx, [rbx]; unsigned __int16 *
0x180021589  lea     r8, aAppx; "AppX"
0x180021590  mov     edx, 25h ; '%'; unsigned __int64
0x180021595  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002159a  test    eax, eax
0x18002159c  jns     short loc_1800215B8
0x18002159e  mov     rcx, [rsp+48h]; this
0x1800215a3  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\staterepositor"...
0x1800215aa  mov     r9d, eax; char *
0x1800215ad  mov     edx, 89h; void *
0x1800215b2  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800215b8  mov     r9, [rbx]
0x1800215bb  lea     rax, [rsp+48h+arg_0]
0x1800215c0  mov     rcx, [rsp+48h+var_18+8]; unsigned __int8 *
0x1800215c5  mov     edx, 14h
0x1800215ca  add     r9, 8; unsigned __int16 *
0x1800215ce  mov     [rsp+48h+arg_0], 0
0x1800215d6  cmp     dword ptr [rsp+48h+var_18], edx
0x1800215da  mov     r8d, 20h ; ' '; unsigned int
0x1800215e0  mov     qword ptr [rsp+48h+var_28], rax; int
0x1800215e5  cmovb   edx, dword ptr [rsp+48h+var_18]; unsigned int
0x1800215ea  call    ?GetChars@Base32Encoding@Common@@SAJPEBEKKPEAGPEAK@Z; Common::Base32Encoding::GetChars(uchar const *,ulong,ulong,ushort *,ulong *)
0x1800215ef  mov     edi, eax
0x1800215f1  test    eax, eax
0x1800215f3  jns     short loc_1800215FF
0x1800215f5  mov     edx, 8Ch
0x1800215fa  jmp     loc_180021549
0x1800215ff  mov     edx, [rsp+48h+arg_0]
0x180021603  xor     eax, eax
0x180021605  mov     rcx, [rbx]
0x180021608  add     rdx, 4
0x18002160c  mov     [rcx+rdx*2], ax
0x180021610  cmp     rdx, 27h ; '''
0x180021614  jbe     loc_18002155F
0x18002161a  mov     rcx, [rsp+48h]; this
0x18002161f  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\staterepositor"...
0x180021626  mov     r9d, 8000FFFFh; char *
0x18002162c  mov     edx, 8Eh; void *
0x180021631  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
