# ATL::CComCreator<ATL::CComObject<CPimcSurrogate>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000c5f8`
- end: `0x18000c6fd`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCPimcSurrogate@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `261`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000c4e0`

## callees

- `0x180003124`
- `0x18000c5f8`
- `0x18000d438`
- `0x18000e4a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CPimcSurrogate>>::CreateInstance(
        __int64 a1,
        const struct _GUID *a2,
        void **a3)
{
  void **v3; // rsi
  const struct _GUID *v4; // r14
  unsigned int v6; // edi
  _QWORD *v7; // rax
  _DWORD *v8; // rbx
  __int64 (__fastcall *v9)(_DWORD *, const struct _GUID *, void **); // rax
  unsigned int Interface; // eax
  _DWORD *v11; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  try
  {
    v7 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
    v8 = v7;
    if ( v7 )
    {
      *((_DWORD *)v7 + 2) = 0;
      *v7 = &ATL::CComObject<CPimcSurrogate>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    else
    {
      v8 = 0;
    }
    v11 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v8 = v11;
  }
  if ( v8 )
  {
    v8[2] = v8[2];
    v9 = **(__int64 (__fastcall ***)(_DWORD *, const struct _GUID *, void **))v8;
    if ( (char *)v9 == (char *)&ATL::CComObject<CPimcSurrogate>::QueryInterface )
      Interface = ATL::AtlInternalQueryInterface(
                    v8,
                    (const struct ATL::_ATL_INTMAP_ENTRY *)&`CPimcSurrogate::_GetEntries'::`2'::_entries,
                    v4,
                    v3);
    else
      Interface = v9(v8, v4, v3);
    v6 = Interface;
    if ( Interface )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v8 + 32LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x18000c5f8  mov     [rsp+arg_10], r8
0x18000c5fd  mov     [rsp+arg_8], rdx
0x18000c602  mov     [rsp+arg_0], rcx
0x18000c607  push    rbx
0x18000c608  push    rsi
0x18000c609  push    rdi
0x18000c60a  push    r14
0x18000c60c  sub     rsp, 38h
0x18000c610  mov     rsi, r8
0x18000c613  mov     r14, rdx
0x18000c616  test    r8, r8
0x18000c619  jnz     short loc_18000C625
0x18000c61b  mov     eax, 80004003h
0x18000c620  jmp     loc_18000C6F3
0x18000c625  and     qword ptr [r8], 0
0x18000c629  mov     edi, 8007000Eh
0x18000c62e  mov     dword ptr [rsp+58h+arg_0], edi
0x18000c632  and     [rsp+58h+var_38], 0
0x18000c638  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c63f  mov     ecx, 10h; unsigned __int64
0x18000c644  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000c649  mov     rbx, rax
0x18000c64c  mov     [rsp+58h+arg_18], rax
0x18000c651  test    rax, rax
0x18000c654  jz      short loc_18000C67A
0x18000c656  and     dword ptr [rax+8], 0
0x18000c65a  lea     rax, ??_7?$CComObject@VCPimcSurrogate@@@ATL@@6B@; const ATL::CComObject<CPimcSurrogate>::`vftable'
0x18000c661  mov     [rbx], rax
0x18000c664  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000c66b  mov     rax, [rcx]
0x18000c66e  mov     rax, [rax+8]
0x18000c672  call    cs:__guard_dispatch_icall_fptr
0x18000c678  jmp     short loc_18000C67C
0x18000c67a  xor     ebx, ebx
0x18000c67c  mov     [rsp+58h+var_38], rbx
0x18000c681  jmp     short loc_18000C696
0x18000c683  mov     rsi, [rsp+58h+arg_10]
0x18000c688  mov     r14, [rsp+58h+arg_8]
0x18000c68d  mov     edi, dword ptr [rsp+58h+arg_0]
0x18000c691  mov     rbx, [rsp+58h+var_38]
0x18000c696  test    rbx, rbx
0x18000c699  jz      short loc_18000C6F1
0x18000c69b  mov     eax, [rbx+8]
0x18000c69e  mov     [rbx+8], eax
0x18000c6a1  mov     rax, [rbx]
0x18000c6a4  mov     rax, [rax]
0x18000c6a7  lea     rcx, ?QueryInterface@?$CComObject@VCPimcSurrogate@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CPimcSurrogate>::QueryInterface(_GUID const &,void * *)
0x18000c6ae  cmp     rax, rcx
0x18000c6b1  mov     rcx, rbx; void *
0x18000c6b4  jnz     short loc_18000C6CA
0x18000c6b6  mov     r9, rsi; void **
0x18000c6b9  mov     r8, r14; struct _GUID *
0x18000c6bc  lea     rdx, ?_entries@?1??_GetEntries@CPimcSurrogate@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000c6c3  call    ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x18000c6c8  jmp     short loc_18000C6D6
0x18000c6ca  mov     r8, rsi
0x18000c6cd  mov     rdx, r14
0x18000c6d0  call    cs:__guard_dispatch_icall_fptr
0x18000c6d6  mov     edi, eax
0x18000c6d8  test    eax, eax
0x18000c6da  jz      short loc_18000C6F1
0x18000c6dc  mov     rax, [rbx]
0x18000c6df  mov     edx, 1
0x18000c6e4  mov     rcx, rbx
0x18000c6e7  mov     rax, [rax+20h]
0x18000c6eb  call    cs:__guard_dispatch_icall_fptr
0x18000c6f1  mov     eax, edi
0x18000c6f3  add     rsp, 38h
0x18000c6f7  pop     r14
0x18000c6f9  pop     rdi
0x18000c6fa  pop     rsi
0x18000c6fb  pop     rbx
0x18000c6fc  retn
```
