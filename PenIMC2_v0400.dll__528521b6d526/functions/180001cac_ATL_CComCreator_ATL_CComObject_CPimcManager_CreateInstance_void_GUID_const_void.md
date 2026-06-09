# ATL::CComCreator<ATL::CComObject<CPimcManager>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180001cac`
- end: `0x180001df3`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCPimcManager@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180001970`

## callees

- `0x180001cac`
- `0x180003124`
- `0x18000a444`
- `0x18000d438`
- `0x18000e4a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CPimcManager>>::CreateInstance(
        __int64 a1,
        const struct _GUID *a2,
        void **a3)
{
  void **v3; // r14
  const struct _GUID *v4; // r15
  unsigned int v6; // esi
  void ***v7; // rax
  void ***v8; // rbx
  int v9; // eax
  __int64 (__fastcall *v10)(void ***, const struct _GUID *, void **); // rax
  unsigned int Interface; // eax
  void ***v12; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  try
  {
    v7 = (void ***)operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
    v8 = v7;
    if ( v7 )
    {
      *((_DWORD *)v7 + 2) = 0;
      v7[2] = 0;
      v7[3] = 0;
      v7[4] = 0;
      *((_DWORD *)v7 + 10) = 0;
      *((_BYTE *)v7 + 56) = 0;
      *((_DWORD *)v7 + 15) &= ~1u;
      v7[8] = 0;
      *((_BYTE *)v7 + 84) = 0;
      *v7 = &ATL::CComObject<CPimcManager>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    else
    {
      v8 = 0;
    }
    v12 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v8 = v12;
  }
  if ( v8 )
  {
    ++*((_DWORD *)v8 + 2);
    v9 = CPimcManager::FinalConstruct((CPimcManager *)v8);
    v6 = 0;
    if ( v9 < 0 )
      v6 = v9;
    --*((_DWORD *)v8 + 2);
    if ( v6
      || ((v10 = (__int64 (__fastcall *)(void ***, const struct _GUID *, void **))**v8,
           (char *)v10 != (char *)&ATL::CComObject<CPimcManager>::QueryInterface)
        ? (Interface = v10(v8, v4, v3))
        : (Interface = ATL::AtlInternalQueryInterface(
                         v8,
                         (const struct ATL::_ATL_INTMAP_ENTRY *)&`CPimcManager::_GetEntries'::`2'::_entries,
                         v4,
                         v3)),
          (v6 = Interface) != 0) )
    {
      ((void (__fastcall *)(void ***, __int64))(*v8)[6])(v8, 1);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180001cac  mov     [rsp+arg_10], r8
0x180001cb1  mov     [rsp+arg_8], rdx
0x180001cb6  mov     [rsp+arg_0], rcx
0x180001cbb  push    rbx
0x180001cbc  push    rsi
0x180001cbd  push    r14
0x180001cbf  push    r15
0x180001cc1  sub     rsp, 38h
0x180001cc5  mov     r14, r8
0x180001cc8  mov     r15, rdx
0x180001ccb  test    r8, r8
0x180001cce  jnz     short loc_180001CDA
0x180001cd0  mov     eax, 80004003h
0x180001cd5  jmp     loc_180001DE8
0x180001cda  and     qword ptr [r8], 0
0x180001cde  mov     esi, 8007000Eh
0x180001ce3  mov     dword ptr [rsp+58h+arg_0], esi
0x180001ce7  and     [rsp+58h+var_38], 0
0x180001ced  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180001cf4  mov     ecx, 58h ; 'X'; unsigned __int64
0x180001cf9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180001cfe  mov     rbx, rax
0x180001d01  mov     [rsp+58h+arg_18], rax
0x180001d06  test    rax, rax
0x180001d09  jz      short loc_180001D5C
0x180001d0b  and     dword ptr [rax+8], 0
0x180001d0f  and     qword ptr [rax+10h], 0
0x180001d14  and     qword ptr [rax+18h], 0
0x180001d19  add     rax, 20h ; ' '
0x180001d1d  mov     [rsp+58h+var_30], rax
0x180001d22  and     qword ptr [rax], 0
0x180001d26  and     dword ptr [rbx+28h], 0
0x180001d2a  mov     byte ptr [rbx+38h], 0
0x180001d2e  and     dword ptr [rbx+3Ch], 0FFFFFFFEh
0x180001d32  and     qword ptr [rbx+40h], 0
0x180001d37  mov     byte ptr [rbx+54h], 0
0x180001d3b  lea     rax, ??_7?$CComObject@VCPimcManager@@@ATL@@6B@; const ATL::CComObject<CPimcManager>::`vftable'
0x180001d42  mov     [rbx], rax
0x180001d45  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180001d4c  mov     rax, [rcx]
0x180001d4f  mov     rax, [rax+8]
0x180001d53  call    cs:__guard_dispatch_icall_fptr
0x180001d59  nop
0x180001d5a  jmp     short loc_180001D5E
0x180001d5c  xor     ebx, ebx
0x180001d5e  mov     [rsp+58h+var_38], rbx
0x180001d63  jmp     short loc_180001D78
0x180001d65  mov     r14, [rsp+58h+arg_10]
0x180001d6a  mov     r15, [rsp+58h+arg_8]
0x180001d6f  mov     esi, dword ptr [rsp+58h+arg_0]
0x180001d73  mov     rbx, [rsp+58h+var_38]
0x180001d78  test    rbx, rbx
0x180001d7b  jz      short loc_180001DE6
0x180001d7d  inc     dword ptr [rbx+8]
0x180001d80  mov     rcx, rbx; this
0x180001d83  call    ?FinalConstruct@CPimcManager@@QEAAJXZ; CPimcManager::FinalConstruct(void)
0x180001d88  xor     esi, esi
0x180001d8a  test    eax, eax
0x180001d8c  cmovs   esi, eax
0x180001d8f  dec     dword ptr [rbx+8]
0x180001d92  test    esi, esi
0x180001d94  jnz     short loc_180001DD1
0x180001d96  mov     rax, [rbx]
0x180001d99  mov     rax, [rax]
0x180001d9c  lea     rcx, ?QueryInterface@?$CComObject@VCPimcManager@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CPimcManager>::QueryInterface(_GUID const &,void * *)
0x180001da3  cmp     rax, rcx
0x180001da6  mov     rcx, rbx; void *
0x180001da9  jnz     short loc_180001DBF
0x180001dab  mov     r9, r14; void **
0x180001dae  mov     r8, r15; struct _GUID *
0x180001db1  lea     rdx, ?_entries@?1??_GetEntries@CPimcManager@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180001db8  call    ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180001dbd  jmp     short loc_180001DCB
0x180001dbf  mov     r8, r14
0x180001dc2  mov     rdx, r15
0x180001dc5  call    cs:__guard_dispatch_icall_fptr
0x180001dcb  mov     esi, eax
0x180001dcd  test    eax, eax
0x180001dcf  jz      short loc_180001DE6
0x180001dd1  mov     rax, [rbx]
0x180001dd4  mov     edx, 1
0x180001dd9  mov     rcx, rbx
0x180001ddc  mov     rax, [rax+30h]
0x180001de0  call    cs:__guard_dispatch_icall_fptr
0x180001de6  mov     eax, esi
0x180001de8  add     rsp, 38h
0x180001dec  pop     r15
0x180001dee  pop     r14
0x180001df0  pop     rsi
0x180001df1  pop     rbx
0x180001df2  retn
```
