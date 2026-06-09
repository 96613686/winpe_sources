# CRuleWriter::CheckPathAllowed(RULE_PATH_INFO const *,tagPROPVARIANT const *,PathAllowedType::Enum *)

- ea: `0x180011990`
- end: `0x180011aa3`
- name: `?CheckPathAllowed@CRuleWriter@@UEAAJPEBURULE_PATH_INFO@@PEBUtagPROPVARIANT@@PEAW4Enum@PathAllowedType@@@Z`
- size: `275`
- prototype: `__int64 __fastcall(CRuleWriter *__hidden this, const struct RULE_PATH_INFO *, const struct tagPROPVARIANT *, enum PathAllowedType::Enum *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800118e0`

## callees

- `0x180008ea0`
- `0x18000b90c`
- `0x18000c048`
- `0x180011990`
- `0x1800132dc`
- `0x18001db20`
- `0x180029010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180011a0c`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180011a0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011a81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011a81`

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
        v10,
        a3);
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
0x180011990  mov     [rsp+arg_0], rbx
0x180011995  mov     [rsp+arg_10], rbp
0x18001199a  push    rsi
0x18001199b  push    rdi
0x18001199c  push    r14
0x18001199e  sub     rsp, 20h
0x1800119a2  xor     esi, esi
0x1800119a4  mov     dword ptr [r9], 1
0x1800119ab  xor     edi, edi
0x1800119ad  mov     [rsp+38h+Str], rsi
0x1800119b2  mov     r14, r9
0x1800119b5  mov     rbx, rdx
0x1800119b8  mov     rbp, rcx
0x1800119bb  cmp     [rdx+14h], esi
0x1800119be  jz      short loc_1800119C9
0x1800119c0  mov     dword ptr [r9], 2
0x1800119c7  jmp     short loc_180011A41
0x1800119c9  cmp     [rdx+10h], esi
0x1800119cc  jz      short loc_180011A41
0x1800119ce  mov     rcx, [rbx+18h]; unsigned __int16 *
0x1800119d2  lea     rdx, [rsp+38h+Str]; unsigned __int16 **
0x1800119d7  call    ?PIXStrDup@@YAJPEBGPEAPEAG@Z; PIXStrDup(ushort const *,ushort * *)
0x1800119dc  mov     edi, eax
0x1800119de  test    eax, eax
0x1800119e0  jns     short loc_1800119FF
0x1800119e2  cmp     cs:?g_doStackCaptures@@3HA, esi; int g_doStackCaptures
0x1800119e8  jz      short loc_1800119FB
0x1800119ea  mov     ecx, eax; int
0x1800119ec  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800119f1  mov     rsi, [rsp+38h+Str]
0x1800119f6  jmp     loc_180011A7E
0x1800119fb  test    eax, eax
0x1800119fd  js      short loc_1800119F1
0x1800119ff  mov     rsi, [rsp+38h+Str]
0x180011a04  mov     edx, 2Fh ; '/'; Ch
0x180011a09  mov     rcx, rsi; Str
0x180011a0c  call    cs:__imp_wcsrchr
0x180011a13  nop     dword ptr [rax+rax+00h]
0x180011a18  xor     r8d, r8d
0x180011a1b  mov     rdx, rsi
0x180011a1e  mov     rcx, rax
0x180011a21  xor     eax, eax
0x180011a23  mov     [rcx], ax
0x180011a26  mov     rcx, [rbp+28h]
0x180011a2a  mov     rax, [rcx]
0x180011a2d  mov     rax, [rax+28h]
0x180011a31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a36  test    eax, eax
0x180011a38  jns     short loc_180011A41
0x180011a3a  mov     dword ptr [r14], 0
0x180011a41  mov     rdx, [rbx+28h]
0x180011a45  test    rdx, rdx
0x180011a48  jz      short loc_180011A7E
0x180011a4a  lea     rcx, [rsp+38h+Str]
0x180011a4f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180011a54  lea     rcx, [rbp+38h]
0x180011a58  lea     rdx, [rsp+38h+Str]
0x180011a5d  call    ?Find@?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAHAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@@Z; ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Find(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180011a62  mov     rcx, [rsp+38h+Str]
0x180011a67  mov     ebx, eax
0x180011a69  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180011a6d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180011a72  cmp     ebx, 0FFFFFFFFh
0x180011a75  jnz     short loc_180011A7E
0x180011a77  mov     dword ptr [r14], 2
0x180011a7e  mov     rcx, rsi; pv
0x180011a81  call    cs:__imp_CoTaskMemFree
0x180011a88  nop     dword ptr [rax+rax+00h]
0x180011a8d  mov     rbx, [rsp+38h+arg_0]
0x180011a92  mov     eax, edi
0x180011a94  mov     rbp, [rsp+38h+arg_10]
0x180011a99  add     rsp, 20h
0x180011a9d  pop     r14
0x180011a9f  pop     rdi
0x180011aa0  pop     rsi
0x180011aa1  retn
```
