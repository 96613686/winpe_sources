# CPolicyComponent::CreateAndInitializeRuleReader(KEY_LIST_ENTRY const *,IWICMetadataQueryReader *,CRuleReader * *)

- ea: `0x180001a20`
- end: `0x180001b46`
- name: `?CreateAndInitializeRuleReader@CPolicyComponent@@AEAAJPEBUKEY_LIST_ENTRY@@PEAUIWICMetadataQueryReader@@PEAPEAVCRuleReader@@@Z`
- size: `294`
- prototype: `__int64 __fastcall(CPolicyComponent *__hidden this, const struct KEY_LIST_ENTRY *, struct IWICMetadataQueryReader *, struct CRuleReader **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001870`
- `0x180012950`

## callees

- `0x180001a20`
- `0x180001b50`
- `0x180029010`

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
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v8 = (*(__int64 (**)(void))(*(_QWORD *)this + 56LL))();
      if ( v8 >= 0 )
        v8 = (*(__int64 (__fastcall **)(struct CRuleReader *, const struct KEY_LIST_ENTRY *, const struct CAPABILITIES_LIST_ENTRY near *const *, struct IWICMetadataQueryReader *, const struct RULE_PATH_INFO near *const *, int))(*(_QWORD *)*v4 + 16LL))(
               *v4,
               a2,
               &gc_rgCapList + 9 * v12,
               a3,
               &gc_rgReadPathList + 8 * (unsigned __int64)DWORD2(v11),
               HIDWORD(v11) - DWORD2(v11) + 1);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', &v10) )
      {
        v4 = a4;
        v8 = *(_DWORD *)v10;
        __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_180001B23);
      }
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
0x180001a20  mov     [rsp+arg_8], rbx
0x180001a25  mov     [rsp+arg_10], rsi
0x180001a2a  mov     [rsp+arg_18], r9
0x180001a2f  push    rdi
0x180001a30  push    r14
0x180001a32  push    r15
0x180001a34  sub     rsp, 60h
0x180001a38  mov     rdi, r9
0x180001a3b  mov     r15, r8
0x180001a3e  mov     r14, rdx
0x180001a41  mov     rsi, rcx
0x180001a44  mov     qword ptr [r9], 0
0x180001a4b  xorps   xmm0, xmm0
0x180001a4e  xor     eax, eax
0x180001a50  movups  [rsp+78h+var_30], xmm0
0x180001a55  mov     [rsp+78h+var_20], eax
0x180001a59  lea     rax, [rsp+78h+var_30]
0x180001a5e  mov     [rsp+78h+var_50], rax; struct RULE_LIST_INDEX_ENTRY *
0x180001a63  mov     eax, [rcx+44h]
0x180001a66  mov     [rsp+78h+var_58], eax; unsigned int
0x180001a6a  mov     r9d, [rdx+4]; unsigned int
0x180001a6e  mov     r8d, 3B2h; unsigned int
0x180001a74  lea     rdx, ?gc_rgReadPathIndex@@3QBURULE_LIST_INDEX_ENTRY@@B; struct RULE_LIST_INDEX_ENTRY *
0x180001a7b  call    ?_SearchForIndexEntry@CPolicyComponent@@AEAAJPEBURULE_LIST_INDEX_ENTRY@@IKKPEAU2@@Z; CPolicyComponent::_SearchForIndexEntry(RULE_LIST_INDEX_ENTRY const *,uint,ulong,ulong,RULE_LIST_INDEX_ENTRY *)
0x180001a80  mov     ebx, eax
0x180001a82  test    eax, eax
0x180001a84  js      short loc_180001AF5
0x180001a86  mov     rax, [rsi]
0x180001a89  mov     r8, rdi
0x180001a8c  mov     edx, [r14]
0x180001a8f  mov     rcx, rsi
0x180001a92  mov     rax, [rax+38h]
0x180001a96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a9b  mov     ebx, eax
0x180001a9d  test    eax, eax
0x180001a9f  js      short loc_180001AF5
0x180001aa1  mov     rcx, [rdi]
0x180001aa4  mov     r10, [rcx]
0x180001aa7  mov     r11d, dword ptr [rsp+78h+var_30+0Ch]
0x180001aac  mov     eax, dword ptr [rsp+78h+var_30+8]
0x180001ab0  sub     r11d, eax
0x180001ab3  inc     r11d
0x180001ab6  mov     r9d, eax
0x180001ab9  shl     r9, 6
0x180001abd  lea     rax, ?gc_rgReadPathList@@3QBURULE_PATH_INFO@@B; RULE_PATH_INFO const near * const gc_rgReadPathList
0x180001ac4  add     r9, rax
0x180001ac7  mov     eax, [rsp+78h+var_20]
0x180001acb  lea     rdx, [rax+rax*8]
0x180001acf  lea     rax, ?gc_rgCapList@@3QBUCAPABILITIES_LIST_ENTRY@@B; CAPABILITIES_LIST_ENTRY const near * const gc_rgCapList
0x180001ad6  lea     r8, [rax+rdx*8]
0x180001ada  mov     dword ptr [rsp+78h+var_50], r11d
0x180001adf  mov     qword ptr [rsp+78h+var_58], r9
0x180001ae4  mov     r9, r15
0x180001ae7  mov     rdx, r14
0x180001aea  mov     rax, [r10+10h]
0x180001aee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001af3  mov     ebx, eax
0x180001af5  test    ebx, ebx
0x180001af7  js      short loc_180001B12
0x180001af9  mov     eax, ebx
0x180001afb  lea     r11, [rsp+78h+var_18]
0x180001b00  mov     rbx, [r11+28h]
0x180001b04  mov     rsi, [r11+30h]
0x180001b08  mov     rsp, r11
0x180001b0b  pop     r15
0x180001b0d  pop     r14
0x180001b0f  pop     rdi
0x180001b10  retn
0x180001b12  mov     rcx, [rdi]
0x180001b15  test    rcx, rcx
0x180001b18  jnz     short loc_180001B34
0x180001b1a  mov     qword ptr [rdi], 0
0x180001b21  jmp     short loc_180001AF9
0x180001b23  mov     rdi, [rsp+78h+arg_18]
0x180001b2b  mov     ebx, [rsp+78h+arg_0]
0x180001b32  jmp     short loc_180001AF5
0x180001b34  mov     rax, [rcx]
0x180001b37  mov     edx, 1
0x180001b3c  mov     rax, [rax]
0x180001b3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b44  jmp     short loc_180001B1A
```
