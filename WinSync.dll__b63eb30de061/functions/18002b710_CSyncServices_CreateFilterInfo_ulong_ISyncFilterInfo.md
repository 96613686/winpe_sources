# CSyncServices::CreateFilterInfo(ulong,ISyncFilterInfo * *)

- ea: `0x18002b710`
- end: `0x18002b83b`
- name: `?CreateFilterInfo@CSyncServices@@UEAAJKPEAPEAUISyncFilterInfo@@@Z`
- size: `299`
- prototype: `__int64 __fastcall(struct IdParameters **this, unsigned int, struct ISyncFilterInfo **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x18002addc`
- `0x18002b710`
- `0x180094010`

## string_xrefs

- `0x18002b748`: `CSyncServices::CreateFilterInfo`
- `0x18002b810`: `CSyncServices::CreateFilterInfo`

## pseudocode

```c
__int64 __fastcall CSyncServices::CreateFilterInfo(
        struct IdParameters **this,
        unsigned int a2,
        struct ISyncFilterInfo **a3)
{
  PVOID *v6; // rcx
  unsigned int v7; // ebx
  FilterInfo *v8; // rax
  FilterInfo *v9; // rdi
  _QWORD *v10; // rcx

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      "CSyncServices::CreateFilterInfo");
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  v7 = -2147217407;
  if ( this[6] )
  {
    v7 = -2147467261;
    if ( a3 )
    {
      v7 = -2147024809;
      if ( (a2 & 0xFFFFFFFC) == 0 )
      {
        v7 = -2147024882;
        v8 = (FilterInfo *)SeAlloc(0x30u);
        v9 = v8;
        if ( v8 )
        {
          FilterInfo::FilterInfo(v8, this[6], a2);
          v10[5] = 0;
          *v10 = &ListBasedFilterInfo::`vftable'{for `FilterInfo'};
          v10[4] = &ListBasedFilterInfo::`vftable'{for `IChangeUnitListFilterInfo'};
          v7 = ((__int64 (__fastcall *)(_QWORD *, GUID *, struct ISyncFilterInfo **))ListBasedFilterInfo::`vftable'{for `FilterInfo'})(
                 v10,
                 &GUID_794eaaf8_3f2e_47e6_9728_17e6fcf94cb7,
                 a3);
          (*(void (__fastcall **)(FilterInfo *))(*(_QWORD *)v9 + 16LL))(v9);
        }
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 && *((_BYTE *)v6 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v6[2],
      19,
      (unsigned int)WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      (unsigned int)"CSyncServices::CreateFilterInfo",
      v7);
  return v7;
}

```

## disassembly

```asm
0x18002b710  push    rbx
0x18002b712  push    rbp
0x18002b713  push    rsi
0x18002b714  push    rdi
0x18002b715  push    r14
0x18002b717  push    r15
0x18002b719  sub     rsp, 38h
0x18002b71d  mov     rsi, r8
0x18002b720  mov     ebp, edx
0x18002b722  mov     r14, rcx
0x18002b725  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b72c  lea     r15, WPP_GLOBAL_Control
0x18002b733  cmp     rcx, r15
0x18002b736  jz      short loc_18002B767
0x18002b738  test    byte ptr [rcx+1Ch], 2
0x18002b73c  jz      short loc_18002B767
0x18002b73e  cmp     byte ptr [rcx+19h], 5
0x18002b742  jb      short loc_18002B767
0x18002b744  mov     rcx, [rcx+10h]
0x18002b748  lea     r9, aCsyncservicesC_6; "CSyncServices::CreateFilterInfo"
0x18002b74f  mov     edx, 12h
0x18002b754  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002b75b  call    WPP_SF_s
0x18002b760  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b767  cmp     qword ptr [r14+30h], 0
0x18002b76c  mov     ebx, 80041001h
0x18002b771  jz      loc_18002B7FB
0x18002b777  mov     ebx, 80004003h
0x18002b77c  test    rsi, rsi
0x18002b77f  jz      short loc_18002B7FB
0x18002b781  mov     ebx, 80070057h
0x18002b786  test    ebp, 0FFFFFFFCh
0x18002b78c  jnz     short loc_18002B7FB
0x18002b78e  mov     ecx, 30h ; '0'; unsigned __int64
0x18002b793  mov     ebx, 8007000Eh
0x18002b798  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x18002b79d  mov     rdi, rax
0x18002b7a0  test    rax, rax
0x18002b7a3  jz      short loc_18002B7F4
0x18002b7a5  mov     rdx, [r14+30h]; struct IdParameters *
0x18002b7a9  mov     r8d, ebp; unsigned int
0x18002b7ac  mov     rcx, rax; this
0x18002b7af  call    ??0FilterInfo@@IEAA@PEAVIdParameters@@K@Z; FilterInfo::FilterInfo(IdParameters *,ulong)
0x18002b7b4  lea     r9, ??_7ListBasedFilterInfo@@6BFilterInfo@@@; const ListBasedFilterInfo::`vftable'{for `FilterInfo'}
0x18002b7bb  mov     qword ptr [rcx+28h], 0
0x18002b7c3  lea     rax, ??_7ListBasedFilterInfo@@6BIChangeUnitListFilterInfo@@@; const ListBasedFilterInfo::`vftable'{for `IChangeUnitListFilterInfo'}
0x18002b7ca  mov     [rcx], r9
0x18002b7cd  mov     [rcx+20h], rax
0x18002b7d1  lea     rdx, _GUID_794eaaf8_3f2e_47e6_9728_17e6fcf94cb7
0x18002b7d8  mov     rax, [r9]
0x18002b7db  mov     r8, rsi
0x18002b7de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b7e3  mov     rcx, [rdi]
0x18002b7e6  mov     ebx, eax
0x18002b7e8  mov     rax, [rcx+10h]
0x18002b7ec  mov     rcx, rdi
0x18002b7ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b7f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b7fb  cmp     rcx, r15
0x18002b7fe  jz      short loc_18002B82C
0x18002b800  test    byte ptr [rcx+1Ch], 2
0x18002b804  jz      short loc_18002B82C
0x18002b806  cmp     byte ptr [rcx+19h], 5
0x18002b80a  jb      short loc_18002B82C
0x18002b80c  mov     rcx, [rcx+10h]
0x18002b810  lea     r9, aCsyncservicesC_6; "CSyncServices::CreateFilterInfo"
0x18002b817  mov     edx, 13h
0x18002b81c  mov     [rsp+68h+var_48], ebx
0x18002b820  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002b827  call    WPP_SF_sD
0x18002b82c  mov     eax, ebx
0x18002b82e  add     rsp, 38h
0x18002b832  pop     r15
0x18002b834  pop     r14
0x18002b836  pop     rdi
0x18002b837  pop     rsi
0x18002b838  pop     rbp
0x18002b839  pop     rbx
0x18002b83a  retn
```
