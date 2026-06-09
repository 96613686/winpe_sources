# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180001980`
- end: `0x180001a88`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `264`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001980`
- `0x180003124`
- `0x18000d438`
- `0x18000e4a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(
        __int64 a1,
        const struct _GUID *a2,
        void **a3)
{
  void **v3; // rsi
  const struct _GUID *v4; // r14
  __int64 v5; // r15
  unsigned int v7; // edi
  _QWORD *v8; // rax
  _QWORD *v9; // rbx
  __int64 (__fastcall *v10)(_QWORD *, const struct _GUID *, void **); // rax
  unsigned int Interface; // eax
  _QWORD *v12; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  v5 = a1;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  try
  {
    v8 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    v9 = v8;
    if ( v8 )
    {
      *((_DWORD *)v8 + 2) = 0;
      *v8 = &ATL::CComClassFactory::`vftable';
      *v8 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
    }
    else
    {
      v9 = 0;
    }
    v12 = v9;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v5 = a1;
    v7 = -2147024882;
    v9 = v12;
  }
  if ( v9 )
  {
    v9[2] = v5;
    v10 = *(__int64 (__fastcall **)(_QWORD *, const struct _GUID *, void **))*v9;
    if ( (char *)v10 == (char *)&ATL::CComObjectCached<ATL::CComClassFactory>::QueryInterface )
      Interface = ATL::AtlInternalQueryInterface(
                    v9,
                    (const struct ATL::_ATL_INTMAP_ENTRY *)&`ATL::CComClassFactory::_GetEntries'::`2'::_entries,
                    v4,
                    v3);
    else
      Interface = v10(v9, v4, v3);
    v7 = Interface;
    if ( Interface )
      (*(void (__fastcall **)(_QWORD *, __int64))(*v9 + 40LL))(v9, 1);
  }
  return v7;
}

```

## disassembly

```asm
0x180001980  mov     [rsp+arg_10], r8
0x180001985  mov     [rsp+arg_8], rdx
0x18000198a  mov     [rsp+arg_0], rcx
0x18000198f  push    rbx
0x180001990  push    rsi
0x180001991  push    rdi
0x180001992  push    r14
0x180001994  push    r15
0x180001996  sub     rsp, 30h
0x18000199a  mov     rsi, r8
0x18000199d  mov     r14, rdx
0x1800019a0  mov     r15, rcx
0x1800019a3  test    r8, r8
0x1800019a6  jnz     short loc_1800019B2
0x1800019a8  mov     eax, 80004003h
0x1800019ad  jmp     loc_180001A7C
0x1800019b2  and     qword ptr [r8], 0
0x1800019b6  mov     edi, 8007000Eh
0x1800019bb  mov     [rsp+58h+arg_18], edi
0x1800019bf  and     [rsp+58h+var_38], 0
0x1800019c5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800019cc  mov     ecx, 18h; unsigned __int64
0x1800019d1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800019d6  mov     rbx, rax
0x1800019d9  mov     [rsp+58h+var_30], rax
0x1800019de  test    rax, rax
0x1800019e1  jz      short loc_180001A00
0x1800019e3  mov     dword ptr [rax+8], 0
0x1800019ea  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x1800019f1  mov     [rbx], rax
0x1800019f4  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x1800019fb  mov     [rbx], rax
0x1800019fe  jmp     short loc_180001A02
0x180001a00  xor     ebx, ebx
0x180001a02  mov     [rsp+58h+var_38], rbx
0x180001a07  jmp     short loc_180001A21
0x180001a09  mov     rsi, [rsp+58h+arg_10]
0x180001a0e  mov     r14, [rsp+58h+arg_8]
0x180001a13  mov     r15, [rsp+58h+arg_0]
0x180001a18  mov     edi, [rsp+58h+arg_18]
0x180001a1c  mov     rbx, [rsp+58h+var_38]
0x180001a21  test    rbx, rbx
0x180001a24  jz      short loc_180001A7A
0x180001a26  mov     [rbx+10h], r15
0x180001a2a  mov     rax, [rbx]
0x180001a2d  mov     rax, [rax]
0x180001a30  lea     rcx, ?QueryInterface@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObjectCached<ATL::CComClassFactory>::QueryInterface(_GUID const &,void * *)
0x180001a37  cmp     rax, rcx
0x180001a3a  mov     rcx, rbx; void *
0x180001a3d  jnz     short loc_180001A53
0x180001a3f  mov     r9, rsi; void **
0x180001a42  mov     r8, r14; struct _GUID *
0x180001a45  lea     rdx, ?_entries@?1??_GetEntries@CComClassFactory@ATL@@SAPEBU_ATL_INTMAP_ENTRY@3@XZ@4QBU43@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180001a4c  call    ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180001a51  jmp     short loc_180001A5F
0x180001a53  mov     r8, rsi
0x180001a56  mov     rdx, r14
0x180001a59  call    cs:__guard_dispatch_icall_fptr
0x180001a5f  mov     edi, eax
0x180001a61  test    eax, eax
0x180001a63  jz      short loc_180001A7A
0x180001a65  mov     rax, [rbx]
0x180001a68  mov     edx, 1
0x180001a6d  mov     rcx, rbx
0x180001a70  mov     rax, [rax+28h]
0x180001a74  call    cs:__guard_dispatch_icall_fptr
0x180001a7a  mov     eax, edi
0x180001a7c  add     rsp, 30h
0x180001a80  pop     r15
0x180001a82  pop     r14
0x180001a84  pop     rdi
0x180001a85  pop     rsi
0x180001a86  pop     rbx
0x180001a87  retn
```
