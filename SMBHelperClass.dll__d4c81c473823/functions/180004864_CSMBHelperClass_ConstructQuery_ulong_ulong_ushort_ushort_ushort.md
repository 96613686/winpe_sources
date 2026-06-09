# CSMBHelperClass::ConstructQuery(ulong,ulong,ushort *,ushort *,ushort * *)

- ea: `0x180004864`
- end: `0x180004a53`
- name: `?ConstructQuery@CSMBHelperClass@@AEAAJKKPEAG0PEAPEAG@Z`
- size: `495`
- prototype: `__int64 __fastcall(CSMBHelperClass *this, unsigned int, int, unsigned __int16 *, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800046ac`

## callees

- `0x180004864`
- `0x180004ee0`
- `0x18000e3b8`
- `0x18000e49c`
- `0x18000ea24`
- `0x18000eddc`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004a16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004a30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004a3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004a16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004a30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004a3e`

## pseudocode

```c
__int64 __fastcall CSMBHelperClass::ConstructQuery(
        CSMBHelperClass *this,
        unsigned int a2,
        int a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 **a6)
{
  __int64 v6; // r15
  unsigned int v8; // r14d
  unsigned __int16 **v9; // rsi
  __int64 v10; // rcx
  __int64 v11; // rbx
  unsigned int v12; // edx
  unsigned __int16 *v13; // rax
  _OWORD *TestMemory; // rbx
  unsigned __int16 *v15; // rdi
  __int64 i; // rsi
  void *v17; // rcx
  unsigned __int16 **v19; // rbx
  unsigned __int16 **v20; // rbx
  _OWORD *v21; // [rsp+30h] [rbp-48h]
  __int128 v22; // [rsp+38h] [rbp-40h] BYREF
  __int64 v23; // [rsp+48h] [rbp-30h]
  __int64 v25; // [rsp+98h] [rbp+20h] BYREF

  v6 = a2;
  v8 = 0;
  v22 = 0;
  v23 = 0;
  LODWORD(v22) = 2;
  DWORD2(v22) = a3;
  v25 = 0;
  v9 = a6;
  if ( a6 )
  {
    try
    {
      v15 = ConvertAttributeValueToString((const struct Attribute *)&v22);
      v25 = (__int64)v15;
      TestMemory = AllocateTestMemory(0x20u);
      v21 = TestMemory;
      *TestMemory = 0;
      TestMemory[1] = 0;
      *(_QWORD *)TestMemory = AllocateAndCatStrings(
                                L"*[System/Provider/@Name='",
                                (unsigned __int16 *)(&ProviderString)[v6]);
      *((_QWORD *)TestMemory + 1) = AllocateAndCatStrings(L"' and System/EventID", a5);
      *((_QWORD *)TestMemory + 2) = AllocateAndCatStrings(v15, L" and EventData/Data[@Name='");
      *((_QWORD *)TestMemory + 3) = AllocateAndCatStrings(L"ErrorCode", L"'] != 0]");
      v13 = AllocateAndCatStrings((unsigned __int16 **)TestMemory, v12);
    }
    catch ( enum TestException )
    {
      if ( *((_QWORD *)this + 22) )
      {
        a6 = (unsigned __int16 **)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          &a6,
          L"CSMBHelperClass::ConstructQuery Alloc failure");
        v19 = a6;
        (*(void (__fastcall **)(_QWORD, __int64, _QWORD, const unsigned __int16 *, unsigned __int16 **))(**((_QWORD **)this + 22) + 24LL))(
          *((_QWORD *)this + 22),
          2,
          0,
          L"SMBHelperClass",
          a6);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v19 - 2, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD, unsigned __int16 **))(*(_QWORD *)*(v19 - 3) + 8LL))(*(v19 - 3), v19 - 3);
      }
      TestMemory = v21;
      v15 = (unsigned __int16 *)v25;
      v8 = -2147024882;
      goto LABEL_7;
    }
    catch ( exception )
    {
      if ( *((_QWORD *)this + 22) )
      {
        a6 = (unsigned __int16 **)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          &a6,
          L"CSMBHelperClass::ConstructQuery Unknown Exception");
        v20 = a6;
        (*(void (__fastcall **)(_QWORD, __int64, _QWORD, const unsigned __int16 *, unsigned __int16 **))(**((_QWORD **)this + 22) + 24LL))(
          *((_QWORD *)this + 22),
          2,
          0,
          L"SMBHelperClass",
          a6);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v20 - 2, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD, unsigned __int16 **))(*(_QWORD *)*(v20 - 3) + 8LL))(*(v20 - 3), v20 - 3);
      }
      TestMemory = v21;
      v15 = (unsigned __int16 *)v25;
      v8 = -2147467259;
      goto LABEL_7;
    }
    *v9 = v13;
LABEL_7:
    if ( TestMemory )
    {
      for ( i = 0; i != 4; ++i )
      {
        v17 = (void *)*((_QWORD *)TestMemory + i);
        if ( v17 )
        {
          CoTaskMemFree(v17);
          *((_QWORD *)TestMemory + i) = 0;
        }
      }
      CoTaskMemFree(TestMemory);
    }
    if ( v15 )
      CoTaskMemFree(v15);
  }
  else
  {
    if ( *((_QWORD *)this + 22) )
    {
      v25 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        &v25,
        L"CSMBHelperClass::ConstructQuery Invalid Parameter");
      v10 = *((_QWORD *)this + 22);
      v11 = v25;
      (*(void (__fastcall **)(__int64, __int64, _QWORD, const unsigned __int16 *, __int64))(*(_QWORD *)v10 + 24LL))(
        v10,
        2,
        0,
        L"SMBHelperClass",
        v25);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v11 - 24 + 16), 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v11 - 24) + 8LL))(*(_QWORD *)(v11 - 24));
    }
    return (unsigned int)-1073741811;
  }
  return v8;
}

```

## disassembly

```asm
0x180004864  mov     r11, rsp
0x180004867  mov     [r11+20h], r9
0x18000486b  mov     [r11+8], rcx
0x18000486f  push    rbx
0x180004870  push    rsi
0x180004871  push    rdi
0x180004872  push    r14
0x180004874  push    r15
0x180004876  sub     rsp, 50h
0x18000487a  mov     r15d, edx
0x18000487d  mov     rbx, rcx
0x180004880  xor     r14d, r14d
0x180004883  xorps   xmm0, xmm0
0x180004886  xor     eax, eax
0x180004888  movups  [rsp+78h+var_40], xmm0
0x18000488d  mov     [r11-30h], rax
0x180004891  lea     edi, [rax+2]
0x180004894  mov     dword ptr [rsp+78h+var_40], edi
0x180004898  mov     [r11-38h], r8d
0x18000489c  mov     [rsp+78h+arg_18], rax
0x1800048a4  mov     [rsp+78h+var_48], rax
0x1800048a9  mov     rsi, [rsp+78h+arg_28]
0x1800048b1  test    rsi, rsi
0x1800048b4  jnz     loc_180004956
0x1800048ba  cmp     [rcx+0B0h], rax
0x1800048c1  jz      loc_18000494B
0x1800048c7  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800048ce  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800048d5  mov     rax, [rax+18h]
0x1800048d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048de  add     rax, 18h
0x1800048e2  mov     [rsp+78h+arg_18], rax
0x1800048ea  lea     rdx, aCsmbhelperclas_4; "CSMBHelperClass::ConstructQuery Invalid"...
0x1800048f1  lea     rcx, [rsp+78h+arg_18]
0x1800048f9  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x1800048fe  mov     rcx, [rbx+0B0h]
0x180004905  mov     rax, [rcx]
0x180004908  xor     r8d, r8d
0x18000490b  mov     rbx, [rsp+78h+arg_18]
0x180004913  mov     [rsp+78h+var_58], rbx
0x180004918  lea     r9, aSmbhelperclass_0; "SMBHelperClass"
0x18000491f  mov     edx, edi
0x180004921  mov     rax, [rax+18h]
0x180004925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000492a  nop
0x18000492b  lea     rdx, [rbx-18h]
0x18000492f  or      eax, 0FFFFFFFFh
0x180004932  lock xadd [rdx+10h], eax
0x180004937  sub     eax, 1
0x18000493a  jg      short loc_18000494B
0x18000493c  mov     rcx, [rdx]
0x18000493f  mov     rax, [rcx]
0x180004942  mov     rax, [rax+8]
0x180004946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000494b  mov     r14d, 0C000000Dh
0x180004951  jmp     loc_180004A44
0x180004956  lea     rcx, [rsp+78h+var_40]; struct Attribute *
0x18000495b  call    ?ConvertAttributeValueToString@@YAPEAGAEBUAttribute@@@Z; ConvertAttributeValueToString(Attribute const &)
0x180004960  mov     rdi, rax
0x180004963  mov     [rsp+78h+arg_18], rax
0x18000496b  mov     ecx, 20h ; ' '; unsigned __int64
0x180004970  call    ?AllocateTestMemory@@YAPEAX_K@Z; AllocateTestMemory(unsigned __int64)
0x180004975  mov     rbx, rax
0x180004978  mov     [rsp+78h+var_48], rax
0x18000497d  xorps   xmm0, xmm0
0x180004980  movups  xmmword ptr [rax], xmm0
0x180004983  movups  xmmword ptr [rax+10h], xmm0
0x180004987  lea     rax, ?ProviderString@@3PAPEAGA; ushort * near * ProviderString
0x18000498e  mov     rdx, [rax+r15*8]; unsigned __int16 *
0x180004992  lea     rcx, aSystemProvider; "*[System/Provider/@Name='"
0x180004999  call    ?AllocateAndCatStrings@@YAPEAGPEAG0@Z; AllocateAndCatStrings(ushort *,ushort *)
0x18000499e  mov     [rbx], rax
0x1800049a1  mov     rdx, [rsp+78h+arg_20]; unsigned __int16 *
0x1800049a9  lea     rcx, aAndSystemEvent; "' and System/EventID"
0x1800049b0  call    ?AllocateAndCatStrings@@YAPEAGPEAG0@Z; AllocateAndCatStrings(ushort *,ushort *)
0x1800049b5  mov     [rbx+8], rax
0x1800049b9  lea     rdx, aAndEventdataDa; " and EventData/Data[@Name='"
0x1800049c0  mov     rcx, rdi; unsigned __int16 *
0x1800049c3  call    ?AllocateAndCatStrings@@YAPEAGPEAG0@Z; AllocateAndCatStrings(ushort *,ushort *)
0x1800049c8  mov     [rbx+10h], rax
0x1800049cc  lea     rdx, a0; "'] != 0]"
0x1800049d3  lea     rcx, aErrorcode; "ErrorCode"
0x1800049da  call    ?AllocateAndCatStrings@@YAPEAGPEAG0@Z; AllocateAndCatStrings(ushort *,ushort *)
0x1800049df  mov     [rbx+18h], rax
0x1800049e3  mov     rcx, rbx; unsigned __int16 **
0x1800049e6  call    ?AllocateAndCatStrings@@YAPEAGPEAPEAGK@Z; AllocateAndCatStrings(ushort * *,ulong)
0x1800049eb  nop
0x1800049ec  mov     [rsi], rax
0x1800049ef  jmp     short loc_180004A06
0x1800049f1  mov     rbx, [rsp+78h+var_48]
0x1800049f6  mov     rdi, [rsp+78h+arg_18]
0x1800049fe  mov     r14d, [rsp+78h+arg_10]
0x180004a06  test    rbx, rbx
0x180004a09  jz      short loc_180004A36
0x180004a0b  xor     esi, esi
0x180004a0d  mov     rcx, [rbx+rsi*8]; pv
0x180004a11  test    rcx, rcx
0x180004a14  jz      short loc_180004A24
0x180004a16  call    cs:__imp_CoTaskMemFree
0x180004a1c  mov     qword ptr [rbx+rsi*8], 0
0x180004a24  inc     rsi
0x180004a27  cmp     rsi, 4
0x180004a2b  jnz     short loc_180004A0D
0x180004a2d  mov     rcx, rbx; pv
0x180004a30  call    cs:__imp_CoTaskMemFree
0x180004a36  test    rdi, rdi
0x180004a39  jz      short loc_180004A44
0x180004a3b  mov     rcx, rdi; pv
0x180004a3e  call    cs:__imp_CoTaskMemFree
0x180004a44  mov     eax, r14d
0x180004a47  add     rsp, 50h
0x180004a4b  pop     r15
0x180004a4d  pop     r14
0x180004a4f  pop     rdi
0x180004a50  pop     rsi
0x180004a51  pop     rbx
0x180004a52  retn
```
