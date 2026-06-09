# StructuredQuery1::BaseCondition::Load(IStream *)

- ea: `0x18003db30`
- end: `0x18003dc8d`
- name: `?Load@BaseCondition@StructuredQuery1@@UEAAJPEAUIStream@@@Z`
- size: `349`
- prototype: `int(StructuredQuery1::BaseCondition *__hidden this, struct IStream *)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x18003d4d0`
- `0x18003d560`
- `0x18003d820`

## callees

- `0x180009770`
- `0x18003d6c4`
- `0x18003db30`
- `0x18005daf0`
- `0x18005db64`
- `0x18006749c`
- `0x18008b010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003db79`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003dbab`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003db79`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003dbab`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StructuredQuery1::BaseCondition::Load(StructuredQuery1::BaseCondition *this, struct IStream *a2)
{
  struct IConditionAttribute **v3; // r14
  int KnownImplFromStream; // ebx
  unsigned int i; // edi
  unsigned __int8 IsEnabled; // al
  GUID *v7; // rdx
  struct IConditionAttribute *v8; // rax
  struct StructuredQuery1::AttributeList *v9; // r9
  unsigned int pv; // [rsp+30h] [rbp-48h] BYREF
  struct IConditionAttribute *v12[2]; // [rsp+38h] [rbp-40h] BYREF
  struct _GUID v13; // [rsp+48h] [rbp-30h] BYREF

  v3 = (struct IConditionAttribute **)((char *)this + 40);
  *((_QWORD *)this + 5) = 0;
  if ( a2 )
  {
    pv = 0;
    KnownImplFromStream = IStream_Read(a2, &pv, 4u);
    if ( KnownImplFromStream >= 0 )
    {
      for ( i = 0; i < pv; ++i )
      {
        v13 = 0;
        KnownImplFromStream = IStream_Read(a2, &v13, 0x10u);
        if ( KnownImplFromStream >= 0 )
        {
          v12[0] = 0;
          IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45262758>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_FI45262758>::GetImpl'::`2'::impl);
          v7 = &g_rgClassIdAttribute;
          if ( !IsEnabled )
            v7 = &g_oldRgClassIdAttribute;
          KnownImplFromStream = SQ_IUnknown_LoadKnownImplFromStream(
                                  a2,
                                  (const struct _GUID *const *)v7,
                                  (unsigned int)IsEnabled + 2,
                                  &GUID_522e34a4_07f7_40a1_94d0_1bfe832efc3a,
                                  v12);
          if ( KnownImplFromStream < 0 )
            return (unsigned int)KnownImplFromStream;
          v8 = (struct IConditionAttribute *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
          v12[1] = v8;
          if ( v8 )
            v8 = (struct IConditionAttribute *)StructuredQuery1::AttributeList::AttributeList(v8, &v13, v12[0], v9);
          if ( v8 )
          {
            *v3 = v8;
            v3 = (struct IConditionAttribute **)((char *)v8 + 24);
          }
          else
          {
            KnownImplFromStream = -2147024882;
          }
          (*(void (__fastcall **)(struct IConditionAttribute *))(*(_QWORD *)v12[0] + 16LL))(v12[0]);
        }
        if ( KnownImplFromStream < 0 )
          return (unsigned int)KnownImplFromStream;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)KnownImplFromStream;
}

```

## disassembly

```asm
0x18003db30  mov     [rsp+arg_10], rbx
0x18003db35  push    rsi
0x18003db36  push    rdi
0x18003db37  push    r14
0x18003db39  sub     rsp, 60h
0x18003db3d  mov     rax, cs:__security_cookie
0x18003db44  xor     rax, rsp
0x18003db47  mov     [rsp+78h+var_20], rax
0x18003db4c  mov     rsi, rdx
0x18003db4f  lea     r14, [rcx+28h]
0x18003db53  mov     qword ptr [r14], 0
0x18003db5a  test    rdx, rdx
0x18003db5d  jz      loc_18003DC68
0x18003db63  mov     [rsp+78h+pv], 0
0x18003db6b  mov     r8d, 4; cb
0x18003db71  lea     rdx, [rsp+78h+pv]; pv
0x18003db76  mov     rcx, rsi; pstm
0x18003db79  call    cs:__imp_IStream_Read
0x18003db7f  mov     ebx, eax
0x18003db81  test    eax, eax
0x18003db83  js      loc_18003DC6D
0x18003db89  xor     edi, edi
0x18003db8b  cmp     edi, [rsp+78h+pv]
0x18003db8f  jnb     loc_18003DC6D
0x18003db95  xorps   xmm0, xmm0
0x18003db98  movups  xmmword ptr [rsp+78h+var_30.Data1], xmm0
0x18003db9d  mov     r8d, 10h; cb
0x18003dba3  lea     rdx, [rsp+78h+var_30]; pv
0x18003dba8  mov     rcx, rsi; pstm
0x18003dbab  call    cs:__imp_IStream_Read
0x18003dbb1  mov     ebx, eax
0x18003dbb3  test    eax, eax
0x18003dbb5  js      loc_18003DC5C
0x18003dbbb  mov     [rsp+78h+var_40], 0
0x18003dbc4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FI45262758@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FI45262758@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45262758> `wil::Feature<__WilFeatureTraits_Feature_FI45262758>::GetImpl(void)'::`2'::impl
0x18003dbcb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FI45262758@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45262758>::__private_IsEnabled(void)
0x18003dbd0  movzx   eax, al
0x18003dbd3  lea     r8d, [rax+2]
0x18003dbd7  lea     rcx, ?g_oldRgClassIdAttribute@@3QBQEBU_GUID@@B; _GUID const * const near * const g_oldRgClassIdAttribute
0x18003dbde  lea     rdx, ?g_rgClassIdAttribute@@3QBQEBU_GUID@@B; _GUID const * const near * const g_rgClassIdAttribute
0x18003dbe5  test    al, al
0x18003dbe7  cmovz   rdx, rcx
0x18003dbeb  lea     rax, [rsp+78h+var_40]
0x18003dbf0  mov     [rsp+78h+var_58], rax
0x18003dbf5  lea     r9, _GUID_522e34a4_07f7_40a1_94d0_1bfe832efc3a
0x18003dbfc  mov     rcx, rsi
0x18003dbff  call    SQ_IUnknown_LoadKnownImplFromStream
0x18003dc04  mov     ebx, eax
0x18003dc06  test    eax, eax
0x18003dc08  js      short loc_18003DC6D
0x18003dc0a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003dc11  mov     ecx, 20h ; ' '; unsigned __int64
0x18003dc16  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003dc1b  mov     [rsp+78h+var_38], rax
0x18003dc20  test    rax, rax
0x18003dc23  jz      short loc_18003DC38
0x18003dc25  mov     r8, [rsp+78h+var_40]; struct IConditionAttribute *
0x18003dc2a  lea     rdx, [rsp+78h+var_30]; struct _GUID *
0x18003dc2f  mov     rcx, rax; this
0x18003dc32  call    ??0AttributeList@StructuredQuery1@@QEAA@AEBU_GUID@@PEAUIConditionAttribute@@PEAV01@@Z; StructuredQuery1::AttributeList::AttributeList(_GUID const &,IConditionAttribute *,StructuredQuery1::AttributeList *)
0x18003dc37  nop
0x18003dc38  test    rax, rax
0x18003dc3b  jz      short loc_18003DC46
0x18003dc3d  mov     [r14], rax
0x18003dc40  lea     r14, [rax+18h]
0x18003dc44  jmp     short loc_18003DC4B
0x18003dc46  mov     ebx, 8007000Eh
0x18003dc4b  mov     rcx, [rsp+78h+var_40]
0x18003dc50  mov     rax, [rcx]
0x18003dc53  mov     rax, [rax+10h]
0x18003dc57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dc5c  inc     edi
0x18003dc5e  test    ebx, ebx
0x18003dc60  jns     loc_18003DB8B
0x18003dc66  jmp     short loc_18003DC6D
0x18003dc68  mov     ebx, 80070057h
0x18003dc6d  mov     eax, ebx
0x18003dc6f  mov     rcx, [rsp+78h+var_20]
0x18003dc74  xor     rcx, rsp; StackCookie
0x18003dc77  call    __security_check_cookie
0x18003dc7c  mov     rbx, [rsp+78h+arg_10]
0x18003dc84  add     rsp, 60h
0x18003dc88  pop     r14
0x18003dc8a  pop     rdi
0x18003dc8b  pop     rsi
0x18003dc8c  retn
```
