# UnChunkProofOfPossessionCacheEntry(_CREDENTIALW *,uchar * *,ulong *)

- ea: `0x180011118`
- end: `0x1800112e8`
- name: `?UnChunkProofOfPossessionCacheEntry@@YAJPEAU_CREDENTIALW@@PEAPEAEPEAK@Z`
- size: `464`
- prototype: `__int64 __fastcall(struct _CREDENTIALW *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e75c`

## callees

- `0x180007eb8`
- `0x180008440`
- `0x18000baac`
- `0x18000d824`
- `0x18000d904`
- `0x18000deac`
- `0x18000e678`
- `0x18000fcf4`
- `0x180010064`
- `0x180010830`
- `0x180011118`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180011223`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180011223`

## string_xrefs

- `0x180011172`: `onecoreuap\ds\ext\live\identity\cloudapplugin\utils.cpp`
- `0x18001114e`: `UnChunkProofOfPossessionCacheEntry`

## pseudocode

```c
__int64 __fastcall UnChunkProofOfPossessionCacheEntry(struct _CREDENTIALW *a1, unsigned __int8 **a2, unsigned int *a3)
{
  unsigned __int8 *v6; // r12
  unsigned int v7; // r15d
  DWORD v8; // r14d
  PCREDENTIAL_ATTRIBUTEW Attributes; // rdi
  DWORD v10; // eax
  __int64 v11; // rbx
  errno_t v12; // eax
  unsigned int v13; // ebx
  const unsigned __int16 *v15; // [rsp+20h] [rbp-50h]
  DWORD v16; // [rsp+20h] [rbp-50h]
  __int64 v17; // [rsp+28h] [rbp-48h] BYREF
  unsigned __int8 *v18; // [rsp+30h] [rbp-40h] BYREF
  __int64 v19; // [rsp+38h] [rbp-38h]
  __int64 v20; // [rsp+40h] [rbp-30h]
  _QWORD v21[5]; // [rsp+48h] [rbp-28h] BYREF
  int v22; // [rsp+B0h] [rbp+40h] BYREF
  unsigned __int8 **v23; // [rsp+B8h] [rbp+48h]
  DWORD v24; // [rsp+C8h] [rbp+58h]

  v23 = a2;
  v22 = 0;
  v18 = 0;
  v20 = 0;
  v19 = 0;
  v21[0] = "UnChunkProofOfPossessionCacheEntry";
  v21[1] = &v22;
  v21[2] = 0;
  v21[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\utils.cpp",
    "UnChunkProofOfPossessionCacheEntry",
    (const char *)0x627,
    0,
    v15);
  if ( !a1 || !a2 || !a3 )
  {
    v22 = -1073741811;
    goto LABEL_20;
  }
  *a2 = 0;
  *a3 = 0;
  v16 = a1->AttributeCount << 8;
  v6 = (unsigned __int8 *)LiveAllocate(v16);
  Auto<_UnsignedProofOfPossessionTokenParameter *,LiveMemoryFunctor<_UnsignedProofOfPossessionTokenParameter *>,DummyContext>::Clear(&v18);
  v18 = v6;
  if ( !v6 )
  {
    v22 = -1073741670;
    goto LABEL_20;
  }
  v7 = 0;
  v8 = 0;
  while ( 2 )
  {
    if ( v8 >= a1->AttributeCount )
    {
LABEL_18:
      v18 = 0;
      v19 = 0;
      *v23 = v6;
      *a3 = v7;
      goto LABEL_20;
    }
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v17);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      &v17,
      L"%ls%-d",
      L"Microsoft_WindowsLive:SerializedMaterial:",
      v8);
    Attributes = a1->Attributes;
    if ( !Attributes )
    {
      ATL::CStringData::Release((ATL::CStringData *)(v17 - 24));
      goto LABEL_18;
    }
    v10 = 0;
    v11 = v17;
    while ( 1 )
    {
      v24 = v10;
      if ( v10 >= a1->AttributeCount )
        goto LABEL_15;
      if ( !(unsigned int)_o__wcsicmp(v11, Attributes->Keyword) )
        break;
      ++Attributes;
      v10 = v24 + 1;
    }
    v12 = memcpy_s_0(&v6[v7], v16 - v7, Attributes->Value, Attributes->ValueSize);
    v22 = LiveMapHResultToNtStatus(v12 != 0 ? 0x8000FFFF : 0);
    if ( v22 >= 0 )
    {
      v7 += Attributes->ValueSize;
LABEL_15:
      ATL::CStringData::Release((ATL::CStringData *)(v11 - 24));
      ++v8;
      continue;
    }
    break;
  }
  ATL::CStringData::Release((ATL::CStringData *)(v11 - 24));
LABEL_20:
  v13 = v22;
  CTraceFuncW<long>::~CTraceFuncW<long>(v21);
  Auto<unsigned char *,LiveMemoryFunctor<unsigned char *>,DummyContext>::~Auto<unsigned char *,LiveMemoryFunctor<unsigned char *>,DummyContext>(&v18);
  return v13;
}

```

## disassembly

```asm
0x180011118  mov     [rsp-38h+arg_10], rbx
0x18001111d  mov     [rsp-38h+arg_8], rdx
0x180011122  push    rbp
0x180011123  push    rsi
0x180011124  push    rdi
0x180011125  push    r12
0x180011127  push    r13
0x180011129  push    r14
0x18001112b  push    r15
0x18001112d  mov     rbp, rsp
0x180011130  sub     rsp, 70h
0x180011134  mov     r13, r8
0x180011137  mov     rbx, rdx
0x18001113a  mov     rsi, rcx
0x18001113d  xor     edi, edi
0x18001113f  mov     [rbp+arg_0], edi
0x180011142  mov     [rbp+var_40], rdi
0x180011146  mov     [rbp+var_30], rdi
0x18001114a  mov     [rbp+var_38], rdi
0x18001114e  lea     rdx, aUnchunkproofof; "UnChunkProofOfPossessionCacheEntry"
0x180011155  mov     [rbp+var_28], rdx
0x180011159  lea     rax, [rbp+arg_0]
0x18001115d  mov     [rbp+var_20], rax
0x180011161  mov     [rbp+var_18], rdi
0x180011165  mov     [rbp+var_10], rdi
0x180011169  xor     r9d, r9d; unsigned int
0x18001116c  mov     r8d, 627h; char *
0x180011172  lea     rcx, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x180011179  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18001117e  nop
0x18001117f  test    rsi, rsi
0x180011182  jz      loc_1800112B1
0x180011188  test    rbx, rbx
0x18001118b  jz      loc_1800112B1
0x180011191  test    r13, r13
0x180011194  jz      loc_1800112B1
0x18001119a  mov     [rbx], rdi
0x18001119d  mov     [r13+0], edi
0x1800111a1  mov     eax, [rsi+34h]
0x1800111a4  shl     eax, 8
0x1800111a7  mov     dword ptr [rbp+var_50], eax
0x1800111aa  mov     ecx, eax; unsigned __int64
0x1800111ac  call    ?LiveAllocate@@YAPEAX_K@Z; LiveAllocate(unsigned __int64)
0x1800111b1  mov     r12, rax
0x1800111b4  lea     rcx, [rbp+var_40]
0x1800111b8  call    ?Clear@?$Auto@PEAU_UnsignedProofOfPossessionTokenParameter@@V?$LiveMemoryFunctor@PEAU_UnsignedProofOfPossessionTokenParameter@@@@VDummyContext@@@@QEAAXXZ; Auto<_UnsignedProofOfPossessionTokenParameter *,LiveMemoryFunctor<_UnsignedProofOfPossessionTokenParameter *>,DummyContext>::Clear(void)
0x1800111bd  mov     [rbp+var_40], r12
0x1800111c1  test    r12, r12
0x1800111c4  jnz     short loc_1800111D2
0x1800111c6  mov     [rbp+arg_0], 0C000009Ah
0x1800111cd  jmp     loc_1800112B8
0x1800111d2  mov     r15d, edi
0x1800111d5  mov     r14d, edi
0x1800111d8  cmp     r14d, [rsi+34h]
0x1800111dc  jnb     loc_180011294
0x1800111e2  lea     rcx, [rbp+var_48]
0x1800111e6  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800111eb  nop
0x1800111ec  mov     r9d, r14d
0x1800111ef  lea     r8, aMicrosoftWindo; "Microsoft_WindowsLive:SerializedMateria"...
0x1800111f6  lea     rdx, aLsD; "%ls%-d"
0x1800111fd  lea     rcx, [rbp+var_48]
0x180011201  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180011206  mov     rdi, [rsi+38h]
0x18001120a  test    rdi, rdi
0x18001120d  jz      short loc_180011287
0x18001120f  xor     eax, eax
0x180011211  mov     rbx, [rbp+var_48]
0x180011215  mov     [rbp+arg_18], eax
0x180011218  cmp     eax, [rsi+34h]
0x18001121b  jnb     short loc_18001126B
0x18001121d  mov     rdx, [rdi]
0x180011220  mov     rcx, rbx
0x180011223  call    cs:__imp__o__wcsicmp
0x180011229  test    eax, eax
0x18001122b  jz      short loc_180011238
0x18001122d  add     rdi, 18h
0x180011231  mov     eax, [rbp+arg_18]
0x180011234  inc     eax
0x180011236  jmp     short loc_180011215
0x180011238  mov     ecx, r15d
0x18001123b  add     rcx, r12; Destination
0x18001123e  mov     r9d, [rdi+0Ch]; SourceSize
0x180011242  mov     edx, dword ptr [rbp+var_50]
0x180011245  sub     edx, r15d; DestinationSize
0x180011248  mov     r8, [rdi+10h]; Source
0x18001124c  call    memcpy_s_0
0x180011251  neg     eax
0x180011253  sbb     ecx, ecx
0x180011255  and     ecx, 8000FFFFh; int
0x18001125b  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x180011260  mov     [rbp+arg_0], eax
0x180011263  test    eax, eax
0x180011265  js      short loc_18001127C
0x180011267  add     r15d, [rdi+0Ch]
0x18001126b  lea     rcx, [rbx-18h]; this
0x18001126f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180011274  inc     r14d
0x180011277  jmp     loc_1800111D8
0x18001127c  lea     rcx, [rbx-18h]; this
0x180011280  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180011285  jmp     short loc_1800112B8
0x180011287  mov     rcx, [rbp+var_48]
0x18001128b  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001128f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180011294  mov     [rbp+var_40], 0
0x18001129c  mov     [rbp+var_38], 0
0x1800112a4  mov     rax, [rbp+arg_8]
0x1800112a8  mov     [rax], r12
0x1800112ab  mov     [r13+0], r15d
0x1800112af  jmp     short loc_1800112B8
0x1800112b1  mov     [rbp+arg_0], 0C000000Dh
0x1800112b8  mov     ebx, [rbp+arg_0]
0x1800112bb  lea     rcx, [rbp+var_28]
0x1800112bf  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800112c4  nop
0x1800112c5  lea     rcx, [rbp+var_40]
0x1800112c9  call    ??1?$Auto@PEAEV?$LiveMemoryFunctor@PEAE@@VDummyContext@@@@QEAA@XZ; Auto<uchar *,LiveMemoryFunctor<uchar *>,DummyContext>::~Auto<uchar *,LiveMemoryFunctor<uchar *>,DummyContext>(void)
0x1800112ce  mov     eax, ebx
0x1800112d0  mov     rbx, [rsp+70h+arg_10]
0x1800112d8  add     rsp, 70h
0x1800112dc  pop     r15
0x1800112de  pop     r14
0x1800112e0  pop     r13
0x1800112e2  pop     r12
0x1800112e4  pop     rdi
0x1800112e5  pop     rsi
0x1800112e6  pop     rbp
0x1800112e7  retn
```
