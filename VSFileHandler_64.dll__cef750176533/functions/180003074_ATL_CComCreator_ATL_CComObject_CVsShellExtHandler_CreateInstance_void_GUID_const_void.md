# ATL::CComCreator<ATL::CComObject<CVsShellExtHandler>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003074`
- end: `0x18000318e`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCVsShellExtHandler@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `282`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002d80`

## callees

- `0x180003074`
- `0x180003624`
- `0x180007db0`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CVsShellExtHandler>>::CreateInstance(
        __int64 a1,
        const struct _GUID *a2,
        void **a3)
{
  void **v3; // r14
  const struct _GUID *v4; // r15
  unsigned int v6; // esi
  _QWORD *v7; // rax
  _DWORD *v8; // rbx
  __int64 (__fastcall *v9)(_DWORD *, const struct _GUID *, void **); // r9
  unsigned int Interface; // eax
  _DWORD *v13; // [rsp+78h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
  try
  {
    v8 = v7;
    if ( v7 )
    {
      *((_DWORD *)v7 + 6) = 0;
      *((_BYTE *)v7 + 32) = 0;
      *((_DWORD *)v7 + 9) = -1;
      v7[5] = 0;
      *v7 = &ATL::CComObject<CVsShellExtHandler>::`vftable'{for `IPersistFile'};
      v7[1] = &ATL::CComObject<CVsShellExtHandler>::`vftable'{for `IExtractIconW'};
      v7[2] = &ATL::CComObject<CVsShellExtHandler>::`vftable'{for `IPropertySetStorage'};
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    else
    {
      v8 = 0;
    }
    v13 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v8 = v13;
  }
  if ( v8 )
  {
    v8[6] = v8[6];
    v9 = **(__int64 (__fastcall ***)(_DWORD *, const struct _GUID *, void **))v8;
    if ( (char *)v9 == (char *)&ATL::CComObject<CVsShellExtHandler>::QueryInterface )
      Interface = ATL::AtlInternalQueryInterface(
                    v8,
                    (const struct ATL::_ATL_INTMAP_ENTRY *)&`CVsShellExtHandler::_GetEntries'::`2'::_entries,
                    v4,
                    v3);
    else
      Interface = v9(v8, v4, v3);
    v6 = Interface;
    if ( Interface )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v8 + 72LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180003074  mov     [rsp+arg_10], r8
0x180003079  mov     [rsp+arg_8], rdx
0x18000307e  mov     [rsp+arg_0], rcx
0x180003083  push    rbx
0x180003084  push    rsi
0x180003085  push    r14
0x180003087  push    r15
0x180003089  sub     rsp, 38h
0x18000308d  mov     r14, r8
0x180003090  mov     r15, rdx
0x180003093  test    r8, r8
0x180003096  jnz     short loc_1800030A2
0x180003098  mov     eax, 80004003h
0x18000309d  jmp     loc_180003183
0x1800030a2  and     qword ptr [r8], 0
0x1800030a6  mov     esi, 8007000Eh
0x1800030ab  mov     dword ptr [rsp+58h+arg_0], esi
0x1800030af  and     [rsp+58h+arg_18], 0
0x1800030b5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800030bc  mov     ecx, 30h ; '0'; unsigned __int64
0x1800030c1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800030c6  mov     rbx, rax
0x1800030c9  mov     [rsp+58h+var_38], rax
0x1800030ce  test    rax, rax
0x1800030d1  jz      short loc_180003114
0x1800030d3  and     dword ptr [rax+18h], 0
0x1800030d7  mov     byte ptr [rax+20h], 0
0x1800030db  or      dword ptr [rax+24h], 0FFFFFFFFh
0x1800030df  and     qword ptr [rax+28h], 0
0x1800030e4  lea     rax, ??_7?$CComObject@VCVsShellExtHandler@@@ATL@@6BIPersistFile@@@; const ATL::CComObject<CVsShellExtHandler>::`vftable'{for `IPersistFile'}
0x1800030eb  mov     [rbx], rax
0x1800030ee  lea     rax, ??_7?$CComObject@VCVsShellExtHandler@@@ATL@@6BIExtractIconW@@@; const ATL::CComObject<CVsShellExtHandler>::`vftable'{for `IExtractIconW'}
0x1800030f5  mov     [rbx+8], rax
0x1800030f9  lea     rax, ??_7?$CComObject@VCVsShellExtHandler@@@ATL@@6BIPropertySetStorage@@@; const ATL::CComObject<CVsShellExtHandler>::`vftable'{for `IPropertySetStorage'}
0x180003100  mov     [rbx+10h], rax
0x180003104  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000310b  mov     rax, [rcx]
0x18000310e  call    qword ptr [rax+8]
0x180003111  nop
0x180003112  jmp     short loc_180003116
0x180003114  xor     ebx, ebx
0x180003116  mov     [rsp+58h+arg_18], rbx
0x18000311b  jmp     short loc_180003130
0x18000311d  mov     r14, [rsp+58h+arg_10]
0x180003122  mov     r15, [rsp+58h+arg_8]
0x180003127  mov     esi, dword ptr [rsp+58h+arg_0]
0x18000312b  mov     rbx, [rsp+58h+arg_18]
0x180003130  test    rbx, rbx
0x180003133  jz      short loc_180003181
0x180003135  mov     eax, [rbx+18h]
0x180003138  mov     [rbx+18h], eax
0x18000313b  mov     rax, [rbx]
0x18000313e  mov     r9, [rax]
0x180003141  lea     rax, ?QueryInterface@?$CComObject@VCVsShellExtHandler@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CVsShellExtHandler>::QueryInterface(_GUID const &,void * *)
0x180003148  mov     rcx, rbx; void *
0x18000314b  cmp     r9, rax
0x18000314e  jnz     short loc_180003164
0x180003150  mov     r9, r14; void **
0x180003153  mov     r8, r15; struct _GUID *
0x180003156  lea     rdx, ?_entries@?1??_GetEntries@CVsShellExtHandler@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000315d  call    ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180003162  jmp     short loc_18000316D
0x180003164  mov     r8, r14
0x180003167  mov     rdx, r15
0x18000316a  call    r9
0x18000316d  mov     esi, eax
0x18000316f  test    eax, eax
0x180003171  jz      short loc_180003181
0x180003173  mov     rax, [rbx]
0x180003176  mov     edx, 1
0x18000317b  mov     rcx, rbx
0x18000317e  call    qword ptr [rax+48h]
0x180003181  mov     eax, esi
0x180003183  add     rsp, 38h
0x180003187  pop     r15
0x180003189  pop     r14
0x18000318b  pop     rsi
0x18000318c  pop     rbx
0x18000318d  retn
```
