# CRuleWriter::CheckPathAllowed(RULE_PATH_INFO const *,tagPROPVARIANT const *,PathAllowedType::Enum *)

- ea: `0x1800111d0`
- end: `0x1800112d3`
- name: `?CheckPathAllowed@CRuleWriter@@UEAAJPEBURULE_PATH_INFO@@PEBUtagPROPVARIANT@@PEAW4Enum@PathAllowedType@@@Z`
- size: `259`
- prototype: `__int64 __fastcall(CRuleWriter *__hidden this, const struct RULE_PATH_INFO *, const struct tagPROPVARIANT *, enum PathAllowedType::Enum *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011120`

## callees

- `0x180007b20`
- `0x18000b3bc`
- `0x18000bac0`
- `0x1800111d0`
- `0x1800129d8`
- `0x18001cd84`
- `0x180028010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180011249`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180011249`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800112b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800112b8`

## pseudocode

```c
__int64 __fastcall CRuleWriter::CheckPathAllowed(
        CRuleWriter *this,
        const struct RULE_PATH_INFO *a2,
        const struct tagPROPVARIANT *a3,
        enum PathAllowedType::Enum *a4)
{
  wchar_t *v4; // rsi
  unsigned int v5; // edi
  int v9; // eax
  __int64 v10; // rdx
  int v11; // ebx
  wchar_t *Str; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  *(_DWORD *)a4 = 1;
  v5 = 0;
  Str = 0;
  if ( *((_DWORD *)a2 + 5) )
  {
    *(_DWORD *)a4 = 2;
LABEL_11:
    v10 = *((_QWORD *)a2 + 5);
    if ( v10 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &Str,
        v10);
      v11 = ATL::CSimpleArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Find(
              (char *)this + 56,
              &Str);
      ATL::CStringData::Release((ATL::CStringData *)(Str - 12));
      if ( v11 == -1 )
        *(_DWORD *)a4 = 2;
    }
    goto LABEL_14;
  }
  if ( !*((_DWORD *)a2 + 4) )
    goto LABEL_11;
  v9 = PIXStrDup(*((const unsigned __int16 **)a2 + 3), &Str);
  v5 = v9;
  if ( v9 >= 0 )
  {
    v4 = Str;
    *wcsrchr(Str, 0x2Fu) = 0;
    if ( (*(int (__fastcall **)(_QWORD, wchar_t *, _QWORD))(**((_QWORD **)this + 5) + 40LL))(
           *((_QWORD *)this + 5),
           v4,
           0) < 0 )
      *(_DWORD *)a4 = 0;
    goto LABEL_11;
  }
  if ( g_doStackCaptures )
    DoStackCapture(v9);
  v4 = Str;
LABEL_14:
  CoTaskMemFree(v4);
  return v5;
}

```

## disassembly

```asm
0x1800111d0  mov     [rsp+arg_0], rbx
0x1800111d5  mov     [rsp+arg_10], rbp
0x1800111da  push    rsi
0x1800111db  push    rdi
0x1800111dc  push    r14
0x1800111de  sub     rsp, 20h
0x1800111e2  xor     esi, esi
0x1800111e4  mov     dword ptr [r9], 1
0x1800111eb  xor     edi, edi
0x1800111ed  mov     [rsp+38h+Str], rsi
0x1800111f2  mov     r14, r9
0x1800111f5  mov     rbx, rdx
0x1800111f8  mov     rbp, rcx
0x1800111fb  cmp     [rdx+14h], esi
0x1800111fe  jz      short loc_180011209
0x180011200  mov     dword ptr [r9], 2
0x180011207  jmp     short loc_180011278
0x180011209  cmp     [rdx+10h], esi
0x18001120c  jz      short loc_180011278
0x18001120e  mov     rcx, [rbx+18h]; unsigned __int16 *
0x180011212  lea     rdx, [rsp+38h+Str]; unsigned __int16 **
0x180011217  call    ?PIXStrDup@@YAJPEBGPEAPEAG@Z; PIXStrDup(ushort const *,ushort * *)
0x18001121c  mov     edi, eax
0x18001121e  test    eax, eax
0x180011220  jns     short loc_18001123C
0x180011222  cmp     cs:?g_doStackCaptures@@3HA, esi; int g_doStackCaptures
0x180011228  jz      short loc_180011238
0x18001122a  mov     ecx, eax; int
0x18001122c  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180011231  mov     rsi, [rsp+38h+Str]
0x180011236  jmp     short loc_1800112B5
0x180011238  test    eax, eax
0x18001123a  js      short loc_180011231
0x18001123c  mov     rsi, [rsp+38h+Str]
0x180011241  mov     edx, 2Fh ; '/'; Ch
0x180011246  mov     rcx, rsi; Str
0x180011249  call    cs:__imp_wcsrchr
0x18001124f  xor     r8d, r8d
0x180011252  mov     rdx, rsi
0x180011255  mov     rcx, rax
0x180011258  xor     eax, eax
0x18001125a  mov     [rcx], ax
0x18001125d  mov     rcx, [rbp+28h]
0x180011261  mov     rax, [rcx]
0x180011264  mov     rax, [rax+28h]
0x180011268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001126d  test    eax, eax
0x18001126f  jns     short loc_180011278
0x180011271  mov     dword ptr [r14], 0
0x180011278  mov     rdx, [rbx+28h]
0x18001127c  test    rdx, rdx
0x18001127f  jz      short loc_1800112B5
0x180011281  lea     rcx, [rsp+38h+Str]
0x180011286  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001128b  lea     rcx, [rbp+38h]
0x18001128f  lea     rdx, [rsp+38h+Str]
0x180011294  call    ?Find@?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAHAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@@Z; ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Find(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180011299  mov     rcx, [rsp+38h+Str]
0x18001129e  mov     ebx, eax
0x1800112a0  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800112a4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800112a9  cmp     ebx, 0FFFFFFFFh
0x1800112ac  jnz     short loc_1800112B5
0x1800112ae  mov     dword ptr [r14], 2
0x1800112b5  mov     rcx, rsi; pv
0x1800112b8  call    cs:__imp_CoTaskMemFree
0x1800112be  mov     rbx, [rsp+38h+arg_0]
0x1800112c3  mov     eax, edi
0x1800112c5  mov     rbp, [rsp+38h+arg_10]
0x1800112ca  add     rsp, 20h
0x1800112ce  pop     r14
0x1800112d0  pop     rdi
0x1800112d1  pop     rsi
0x1800112d2  retn
```
