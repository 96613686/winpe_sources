# CPolicyComponent::CreateAndInitializeRuleReader(KEY_LIST_ENTRY const *,IWICMetadataQueryReader *,CRuleReader * *)

- ea: `0x180001990`
- end: `0x180001ab5`
- name: `?CreateAndInitializeRuleReader@CPolicyComponent@@AEAAJPEBUKEY_LIST_ENTRY@@PEAUIWICMetadataQueryReader@@PEAPEAVCRuleReader@@@Z`
- size: `293`
- prototype: `__int64 __fastcall(CPolicyComponent *__hidden this, const struct KEY_LIST_ENTRY *, struct IWICMetadataQueryReader *, struct CRuleReader **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800017f0`
- `0x1800120a8`

## callees

- `0x180001990`
- `0x180001ac0`
- `0x180028010`

## pseudocode

```c
__int64 __fastcall CPolicyComponent::CreateAndInitializeRuleReader(
        CPolicyComponent *this,
        const struct KEY_LIST_ENTRY *a2,
        struct IWICMetadataQueryReader *a3,
        struct CRuleReader **a4)
{
  struct CRuleReader **v4; // rdi
  int v8; // ebx
  const ATL::CAtlException *v10; // [rsp+40h] [rbp-38h] BYREF
  __int128 v11; // [rsp+48h] [rbp-30h] BYREF
  unsigned int v12; // [rsp+58h] [rbp-20h]

  v4 = a4;
  *a4 = 0;
  v11 = 0;
  v12 = 0;
  v8 = CPolicyComponent::_SearchForIndexEntry(
         this,
         (const struct RULE_LIST_INDEX_ENTRY *)&gc_rgReadPathIndex,
         0x3B2u,
         *((_DWORD *)a2 + 1),
         *((_DWORD *)this + 17),
         (struct RULE_LIST_INDEX_ENTRY *)&v11);
  if ( v8 >= 0 )
  {
    try
    {
      v8 = (*(__int64 (**)(void))(*(_QWORD *)this + 56LL))();
      if ( v8 >= 0 )
        v8 = (*(__int64 (__fastcall **)(struct CRuleReader *, const struct KEY_LIST_ENTRY *, const struct CAPABILITIES_LIST_ENTRY near *const *, struct IWICMetadataQueryReader *, char *, int))(*(_QWORD *)*v4 + 16LL))(
               *v4,
               a2,
               &gc_rgCapList + 9 * v12,
               a3,
               (char *)&gc_rgReadPathList + 64 * (unsigned __int64)DWORD2(v11),
               HIDWORD(v11) - DWORD2(v11) + 1);
    }
    catch ( const ATL::CAtlException *v10 )
    {
      v4 = a4;
      v8 = *(_DWORD *)v10;
    }
  }
  if ( v8 < 0 )
  {
    if ( *v4 )
      (**(void (__fastcall ***)(struct CRuleReader *, __int64))*v4)(*v4, 1);
    *v4 = 0;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180001990  mov     [rsp+arg_8], rbx
0x180001995  mov     [rsp+arg_10], rsi
0x18000199a  mov     [rsp+arg_18], r9
0x18000199f  push    rdi
0x1800019a0  push    r14
0x1800019a2  push    r15
0x1800019a4  sub     rsp, 60h
0x1800019a8  mov     rdi, r9
0x1800019ab  mov     r15, r8
0x1800019ae  mov     r14, rdx
0x1800019b1  mov     rsi, rcx
0x1800019b4  mov     qword ptr [r9], 0
0x1800019bb  xorps   xmm0, xmm0
0x1800019be  xor     eax, eax
0x1800019c0  movups  [rsp+78h+var_30], xmm0
0x1800019c5  mov     [rsp+78h+var_20], eax
0x1800019c9  lea     rax, [rsp+78h+var_30]
0x1800019ce  mov     [rsp+78h+var_50], rax; struct RULE_LIST_INDEX_ENTRY *
0x1800019d3  mov     eax, [rcx+44h]
0x1800019d6  mov     [rsp+78h+var_58], eax; unsigned int
0x1800019da  mov     r9d, [rdx+4]; unsigned int
0x1800019de  mov     r8d, 3B2h; unsigned int
0x1800019e4  lea     rdx, ?gc_rgReadPathIndex@@3QBURULE_LIST_INDEX_ENTRY@@B; struct RULE_LIST_INDEX_ENTRY *
0x1800019eb  call    ?_SearchForIndexEntry@CPolicyComponent@@AEAAJPEBURULE_LIST_INDEX_ENTRY@@IKKPEAU2@@Z; CPolicyComponent::_SearchForIndexEntry(RULE_LIST_INDEX_ENTRY const *,uint,ulong,ulong,RULE_LIST_INDEX_ENTRY *)
0x1800019f0  mov     ebx, eax
0x1800019f2  test    eax, eax
0x1800019f4  js      short loc_180001A65
0x1800019f6  mov     rax, [rsi]
0x1800019f9  mov     r8, rdi
0x1800019fc  mov     edx, [r14]
0x1800019ff  mov     rcx, rsi
0x180001a02  mov     rax, [rax+38h]
0x180001a06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a0b  mov     ebx, eax
0x180001a0d  test    eax, eax
0x180001a0f  js      short loc_180001A65
0x180001a11  mov     rcx, [rdi]
0x180001a14  mov     r10, [rcx]
0x180001a17  mov     r11d, dword ptr [rsp+78h+var_30+0Ch]
0x180001a1c  mov     eax, dword ptr [rsp+78h+var_30+8]
0x180001a20  sub     r11d, eax
0x180001a23  inc     r11d
0x180001a26  mov     r9d, eax
0x180001a29  shl     r9, 6
0x180001a2d  lea     rax, ?gc_rgReadPathList@@3QBURULE_PATH_INFO@@B; RULE_PATH_INFO const near * const gc_rgReadPathList
0x180001a34  add     r9, rax
0x180001a37  mov     eax, [rsp+78h+var_20]
0x180001a3b  lea     rdx, [rax+rax*8]
0x180001a3f  lea     rax, ?gc_rgCapList@@3QBUCAPABILITIES_LIST_ENTRY@@B; CAPABILITIES_LIST_ENTRY const near * const gc_rgCapList
0x180001a46  lea     r8, [rax+rdx*8]
0x180001a4a  mov     dword ptr [rsp+78h+var_50], r11d
0x180001a4f  mov     qword ptr [rsp+78h+var_58], r9
0x180001a54  mov     r9, r15
0x180001a57  mov     rdx, r14
0x180001a5a  mov     rax, [r10+10h]
0x180001a5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a63  mov     ebx, eax
0x180001a65  test    ebx, ebx
0x180001a67  js      short loc_180001A81
0x180001a69  mov     eax, ebx
0x180001a6b  lea     r11, [rsp+78h+var_18]
0x180001a70  mov     rbx, [r11+28h]
0x180001a74  mov     rsi, [r11+30h]
0x180001a78  mov     rsp, r11
0x180001a7b  pop     r15
0x180001a7d  pop     r14
0x180001a7f  pop     rdi
0x180001a80  retn
0x180001a81  mov     rcx, [rdi]
0x180001a84  test    rcx, rcx
0x180001a87  jnz     short loc_180001AA3
0x180001a89  mov     qword ptr [rdi], 0
0x180001a90  jmp     short loc_180001A69
0x180001a92  mov     rdi, [rsp+78h+arg_18]
0x180001a9a  mov     ebx, [rsp+78h+arg_0]
0x180001aa1  jmp     short loc_180001A65
0x180001aa3  mov     rax, [rcx]
0x180001aa6  mov     edx, 1
0x180001aab  mov     rax, [rax]
0x180001aae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ab3  jmp     short loc_180001A89
```
