# EmbeddedSecureElement::GetIccId(wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> *,ulong &)

- ea: `0x18006e574`
- end: `0x18006e749`
- name: `?GetIccId@EmbeddedSecureElement@@QEAAJPEAV?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@AEAK@Z`
- size: `469`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800700a0`

## callees

- `0x18000c964`
- `0x18006e574`
- `0x18006e750`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e6d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e6f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e6d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e6f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006e60e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006e60e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EmbeddedSecureElement::GetIccId(__int64 a1, void **a2, int *a3)
{
  int Resource; // eax
  unsigned int v6; // esi
  volatile signed __int32 *v7; // rdi
  _BYTE *v9; // rax
  void *v10; // rbx
  _BYTE *v11; // rcx
  int v12; // eax
  void *v13; // rcx
  volatile signed __int32 *v14; // rdi
  int v15[4]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v17; // [rsp+50h] [rbp+8h] BYREF
  _BYTE *v18; // [rsp+68h] [rbp+20h]

  *(_OWORD *)v15 = 0;
  Resource = OnDemandResource<EseSmartcardConnection,EseSmartcardConnectionManager>::GetResource(
               *(_QWORD *)(a1 + 120),
               v15);
  v6 = Resource;
  if ( Resource < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x58,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\embeddedse\\src\\embeddedsecureelement.cpp",
      (const char *)(unsigned int)Resource,
      v15[0]);
LABEL_3:
    v7 = *(volatile signed __int32 **)&v15[2];
    if ( !*(_QWORD *)&v15[2] )
      return v6;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v15[2] + 8LL), 0xFFFFFFFF) != 1 )
      return v6;
    (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
    if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) != 1 )
      return v6;
    goto LABEL_6;
  }
  v17 = 16;
  v9 = CoTaskMemAlloc(0x10u);
  v10 = v9;
  v18 = v9;
  if ( v9 )
  {
    v11 = v9 + 16;
    do
      *v9++ = 0;
    while ( v9 != v11 );
  }
  if ( !v10 )
  {
    v6 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5C,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\embeddedse\\src\\embeddedsecureelement.cpp",
      (const char *)0x8007000ELL,
      v15[0]);
    v7 = *(volatile signed __int32 **)&v15[2];
    if ( !*(_QWORD *)&v15[2] )
      return v6;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v15[2] + 8LL), 0xFFFFFFFF) != 1 )
      return v6;
    (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
    if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) != 1 )
      return v6;
LABEL_6:
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
    return v6;
  }
  v12 = (*(__int64 (__fastcall **)(_QWORD, void *, int *))(**(_QWORD **)v15 + 48LL))(*(_QWORD *)v15, v10, &v17);
  v6 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5E,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\embeddedse\\src\\embeddedsecureelement.cpp",
      (const char *)(unsigned int)v12,
      v15[0]);
    CoTaskMemFree(v10);
    goto LABEL_3;
  }
  *a3 = v17;
  v13 = *a2;
  *a2 = v10;
  if ( v13 )
    CoTaskMemFree(v13);
  v14 = *(volatile signed __int32 **)&v15[2];
  if ( *(_QWORD *)&v15[2] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v15[2] + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
      if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18006e574  mov     [rsp+arg_8], rbx
0x18006e579  push    rsi
0x18006e57a  push    rdi
0x18006e57b  push    r14
0x18006e57d  sub     rsp, 30h
0x18006e581  mov     r14, r8
0x18006e584  mov     rdi, rdx
0x18006e587  xorps   xmm0, xmm0
0x18006e58a  movdqu  xmmword ptr [rsp+48h+var_28], xmm0; int
0x18006e590  lea     rdx, [rsp+48h+var_28]
0x18006e595  mov     rcx, [rcx+78h]
0x18006e599  call    ?GetResource@?$OnDemandResource@UEseSmartcardConnection@@VEseSmartcardConnectionManager@@@@QEAAJPEAV?$shared_ptr@UEseSmartcardConnection@@@std@@@Z; OnDemandResource<EseSmartcardConnection,EseSmartcardConnectionManager>::GetResource(std::shared_ptr<EseSmartcardConnection> *)
0x18006e59e  mov     esi, eax
0x18006e5a0  test    eax, eax
0x18006e5a2  jns     short loc_18006E605
0x18006e5a4  mov     rcx, [rsp+48h]; this
0x18006e5a9  mov     r9d, eax; char *
0x18006e5ac  lea     r8, aOnecoreuapDsNf_18; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x18006e5b3  mov     edx, 58h ; 'X'; void *
0x18006e5b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e5bd  nop
0x18006e5be  mov     rdi, qword ptr [rsp+48h+var_28+8]
0x18006e5c3  test    rdi, rdi
0x18006e5c6  jz      short loc_18006E5FE
0x18006e5c8  or      ebx, 0FFFFFFFFh
0x18006e5cb  mov     eax, ebx
0x18006e5cd  lock xadd [rdi+8], eax
0x18006e5d2  add     eax, ebx
0x18006e5d4  jnz     short loc_18006E5FE
0x18006e5d6  mov     rax, [rdi]
0x18006e5d9  mov     rcx, rdi
0x18006e5dc  mov     rax, [rax]
0x18006e5df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e5e4  mov     eax, ebx
0x18006e5e6  lock xadd [rdi+0Ch], eax
0x18006e5eb  add     eax, ebx
0x18006e5ed  jnz     short loc_18006E5FE
0x18006e5ef  mov     rax, [rdi]
0x18006e5f2  mov     rax, [rax+8]
0x18006e5f6  mov     rcx, rdi
0x18006e5f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e5fe  mov     eax, esi
0x18006e600  jmp     loc_18006E73B
0x18006e605  mov     ecx, 10h; cb
0x18006e60a  mov     [rsp+48h+arg_0], ecx
0x18006e60e  call    cs:__imp_CoTaskMemAlloc
0x18006e614  mov     rbx, rax
0x18006e617  mov     [rsp+48h+arg_18], rax
0x18006e61c  test    rax, rax
0x18006e61f  jz      short loc_18006E636
0x18006e621  lea     rcx, [rax+10h]
0x18006e625  cmp     rax, rcx
0x18006e628  jz      short loc_18006E636
0x18006e62a  xor     edx, edx
0x18006e62c  mov     [rax], dl
0x18006e62e  inc     rax
0x18006e631  cmp     rax, rcx
0x18006e634  jnz     short loc_18006E62A
0x18006e636  test    rbx, rbx
0x18006e639  jnz     short loc_18006E699
0x18006e63b  mov     rcx, [rsp+48h]; this
0x18006e640  mov     esi, 8007000Eh
0x18006e645  mov     r9d, esi; char *
0x18006e648  lea     r8, aOnecoreuapDsNf_18; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x18006e64f  lea     edx, [rbx+5Ch]; void *
0x18006e652  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e657  nop
0x18006e658  mov     rdi, qword ptr [rsp+48h+var_28+8]
0x18006e65d  test    rdi, rdi
0x18006e660  jz      short loc_18006E5FE
0x18006e662  or      ebx, 0FFFFFFFFh
0x18006e665  mov     eax, ebx
0x18006e667  lock xadd [rdi+8], eax
0x18006e66c  add     eax, ebx
0x18006e66e  jnz     short loc_18006E5FE
0x18006e670  mov     rax, [rdi]
0x18006e673  mov     rcx, rdi
0x18006e676  mov     rax, [rax]
0x18006e679  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e67e  mov     edx, ebx
0x18006e680  lock xadd [rdi+0Ch], edx
0x18006e685  add     edx, ebx
0x18006e687  jnz     loc_18006E5FE
0x18006e68d  mov     rdx, [rdi]
0x18006e690  mov     rax, [rdx+8]
0x18006e694  jmp     loc_18006E5F6
0x18006e699  mov     rcx, qword ptr [rsp+48h+var_28]
0x18006e69e  mov     rax, [rcx]
0x18006e6a1  lea     r8, [rsp+48h+arg_0]
0x18006e6a6  mov     rdx, rbx
0x18006e6a9  mov     rax, [rax+30h]
0x18006e6ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e6b2  mov     esi, eax
0x18006e6b4  test    eax, eax
0x18006e6b6  jns     short loc_18006E6E0
0x18006e6b8  mov     rcx, [rsp+48h]; this
0x18006e6bd  mov     r9d, eax; char *
0x18006e6c0  lea     r8, aOnecoreuapDsNf_18; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x18006e6c7  mov     edx, 5Eh ; '^'; void *
0x18006e6cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e6d1  nop
0x18006e6d2  mov     rcx, rbx; pv
0x18006e6d5  call    cs:__imp_CoTaskMemFree
0x18006e6db  jmp     loc_18006E5BE
0x18006e6e0  mov     eax, [rsp+48h+arg_0]
0x18006e6e4  mov     [r14], eax
0x18006e6e7  mov     rcx, [rdi]; pv
0x18006e6ea  mov     [rdi], rbx
0x18006e6ed  test    rcx, rcx
0x18006e6f0  jz      short loc_18006E6F9
0x18006e6f2  call    cs:__imp_CoTaskMemFree
0x18006e6f8  nop
0x18006e6f9  mov     rdi, qword ptr [rsp+48h+var_28+8]
0x18006e6fe  test    rdi, rdi
0x18006e701  jz      short loc_18006E739
0x18006e703  or      ebx, 0FFFFFFFFh
0x18006e706  mov     eax, ebx
0x18006e708  lock xadd [rdi+8], eax
0x18006e70d  add     eax, ebx
0x18006e70f  jnz     short loc_18006E739
0x18006e711  mov     rax, [rdi]
0x18006e714  mov     rcx, rdi
0x18006e717  mov     rax, [rax]
0x18006e71a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e71f  mov     eax, ebx
0x18006e721  lock xadd [rdi+0Ch], eax
0x18006e726  add     eax, ebx
0x18006e728  jnz     short loc_18006E739
0x18006e72a  mov     rax, [rdi]
0x18006e72d  mov     rcx, rdi
0x18006e730  mov     rax, [rax+8]
0x18006e734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e739  xor     eax, eax
0x18006e73b  mov     rbx, [rsp+48h+arg_8]
0x18006e740  add     rsp, 30h
0x18006e744  pop     r14
0x18006e746  pop     rdi
0x18006e747  pop     rsi
0x18006e748  retn
```
