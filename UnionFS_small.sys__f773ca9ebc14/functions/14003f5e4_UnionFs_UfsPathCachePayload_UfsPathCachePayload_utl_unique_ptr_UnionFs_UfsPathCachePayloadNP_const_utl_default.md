# UnionFs::UfsPathCachePayload::UfsPathCachePayload(utl::unique_ptr<UnionFs::UfsPathCachePayloadNP const,utl::default_delete<UnionFs::UfsPathCachePayloadNP const>> &&,utl::shared_ptr<UnionFs::UfsLayerCtx>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &&,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &&,wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>> &&,utl::unique_ptr<_SECURITY_DESCRIPTOR,utl::default_delete<_SECURITY_DESCRIPTOR>> &&,bool)

- ea: `0x14003f5e4`
- end: `0x14003f7aa`
- name: `??0UfsPathCachePayload@UnionFs@@AEAA@$$QEAV?$unique_ptr@$$CBVUfsPathCachePayloadNP@UnionFs@@U?$default_delete@$$CBVUfsPathCachePayloadNP@UnionFs@@@utl@@@utl@@V?$shared_ptr@VUfsLayerCtx@UnionFs@@@3@$$QEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@3@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@$$QEAV?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@$$QEAV?$unique_ptr@U_SECURITY_DESCRIPTOR@@U?$default_delete@U_SECURITY_DESCRIPTOR@@@utl@@@3@_N@Z`
- size: `454`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned __int8 DaclDefaulted, PACL Dacl, __int64, unsigned __int8 DaclPresent)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14003ff88`

## callees

- `0x14000f7fc`
- `0x14003f5e4`
- `0x140044e10`

## import_xrefs

- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14003f6f6`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14003f6f6`
- `ntoskrnl!RtlFindAceByType` at `0x14003f754`
- `ntoskrnl!RtlFindAceByType` at `0x14003f77a`
- `ntoskrnl!RtlFindAceByType` at `0x14003f754`
- `ntoskrnl!RtlFindAceByType` at `0x14003f77a`
- `ntoskrnl!RtlOwnerAcesPresent` at `0x14003f70f`
- `ntoskrnl!RtlOwnerAcesPresent` at `0x14003f70f`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x14003f737`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x14003f737`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPathCachePayload::UfsPathCachePayload(
        __int64 a1,
        __int64 *a2,
        _QWORD *a3,
        __int64 *a4,
        _QWORD *DaclDefaulted,
        PACL Dacl,
        __int64 *a7,
        unsigned __int8 DaclPresent)
{
  __int64 v10; // rcx
  __int64 v11; // rax
  _QWORD *v12; // rcx
  PACL v13; // rax
  struct _ACL v14; // rcx
  __int64 *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rax
  UnionFs::UfsPathName *v18; // rcx
  void *v19; // rcx
  void *v20; // rcx
  utl::_RefCountBase *v21; // rcx

  *(_WORD *)(a1 + 8) = 1;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)a1 = &UnionFs::UfsPathCachePayload::`vftable';
  v10 = a3[1];
  *(_QWORD *)(a1 + 32) = *a3;
  *(_QWORD *)(a1 + 40) = v10;
  if ( v10 )
    _InterlockedIncrement((volatile signed __int32 *)(v10 + 8));
  v11 = *a4;
  v12 = DaclDefaulted;
  *a4 = 0;
  *(_QWORD *)(a1 + 48) = v11;
  *(_QWORD *)(a1 + 56) = *v12;
  v13 = Dacl;
  *v12 = 0;
  v14 = *v13;
  *v13 = 0;
  v15 = a7;
  *(struct _ACL *)(a1 + 64) = v14;
  *(_QWORD *)(a1 + 72) = 0;
  v16 = *v15;
  *v15 = 0;
  *(_QWORD *)(a1 + 80) = v16;
  *(_DWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 96) = a1 + 96;
  *(_QWORD *)(a1 + 104) = a1 + 96;
  *(_QWORD *)(a1 + 112) = 0;
  *(_QWORD *)(a1 + 120) = 0;
  *(_WORD *)(a1 + 128) = 2048;
  v17 = *a2;
  *a2 = 0;
  v18 = *(UnionFs::UfsPathName **)(a1 + 48);
  *(_QWORD *)(a1 + 136) = v17;
  *(_QWORD *)(a1 + 144) = 0;
  *(_BYTE *)(a1 + 152) = 0;
  *(_QWORD *)(a1 + 156) = 0;
  *(_WORD *)(a1 + 164) = 257;
  *(_QWORD *)(a1 + 168) = 0;
  *(_QWORD *)(a1 + 176) = 0;
  *(_QWORD *)(a1 + 184) = 0;
  *(_QWORD *)(a1 + 192) = 0;
  *(_QWORD *)(a1 + 200) = 0;
  *(_QWORD *)(a1 + 208) = 0;
  UnionFs::UfsPathName::StripTrailingBackslash(v18);
  v19 = *(void **)(a1 + 80);
  Dacl = 0;
  DaclPresent = 0;
  LOBYTE(DaclDefaulted) = 0;
  RtlGetDaclSecurityDescriptor(v19, &DaclPresent, &Dacl, (PBOOLEAN)&DaclDefaulted);
  *(_DWORD *)(a1 + 88) = 0;
  if ( !DaclPresent || !(unsigned __int8)RtlOwnerAcesPresent(Dacl) )
    *(_DWORD *)(a1 + 88) |= 1u;
  v20 = *(void **)(a1 + 80);
  DaclPresent = 0;
  RtlGetSaclSecurityDescriptor(v20, &DaclPresent, &Dacl, (PBOOLEAN)&DaclDefaulted);
  if ( !DaclPresent || !RtlFindAceByType(Dacl, 17) )
    *(_DWORD *)(a1 + 88) |= 2u;
  if ( !DaclPresent || !RtlFindAceByType(Dacl, 21) )
    *(_DWORD *)(a1 + 88) |= 4u;
  v21 = (utl::_RefCountBase *)a3[1];
  if ( v21 )
    utl::_RefCountBase::_DecStrong(v21);
  return a1;
}

```

## disassembly

```asm
0x14003f5e4  push    rbp
0x14003f5e6  push    rbx
0x14003f5e7  push    rsi
0x14003f5e8  push    rdi
0x14003f5e9  mov     rbp, rsp
0x14003f5ec  sub     rsp, 28h
0x14003f5f0  xor     esi, esi
0x14003f5f2  mov     word ptr [rcx+8], 1
0x14003f5f8  mov     rbx, rcx
0x14003f5fb  mov     [rcx+10h], rsi
0x14003f5ff  lea     rax, ??_7UfsPathCachePayload@UnionFs@@6B@; const UnionFs::UfsPathCachePayload::`vftable'
0x14003f606  mov     [rcx+18h], rsi
0x14003f60a  mov     [rcx], rax
0x14003f60d  mov     rdi, r8
0x14003f610  mov     rcx, [r8+8]
0x14003f614  mov     rax, [r8]
0x14003f617  mov     [rbx+20h], rax
0x14003f61b  mov     [rbx+28h], rcx
0x14003f61f  test    rcx, rcx
0x14003f622  jz      short loc_14003F628
0x14003f624  lock inc dword ptr [rcx+8]
0x14003f628  mov     rax, [r9]
0x14003f62b  mov     rcx, [rbp+DaclDefaulted]
0x14003f62f  mov     [r9], rsi
0x14003f632  mov     [rbx+30h], rax
0x14003f636  mov     rax, [rcx]
0x14003f639  mov     [rbx+38h], rax
0x14003f63d  mov     rax, [rbp+Dacl]
0x14003f641  mov     [rcx], rsi
0x14003f644  mov     rcx, [rax]
0x14003f647  mov     [rax], rsi
0x14003f64a  mov     rax, [rbp+arg_30]
0x14003f64e  mov     [rbx+40h], rcx
0x14003f652  mov     [rbx+48h], rsi
0x14003f656  mov     rcx, [rax]
0x14003f659  mov     [rax], rsi
0x14003f65c  lea     rax, [rbx+60h]
0x14003f660  mov     [rbx+50h], rcx
0x14003f664  mov     [rbx+58h], esi
0x14003f667  mov     [rax], rax
0x14003f66a  mov     [rax+8], rax
0x14003f66e  mov     [rax+10h], rsi
0x14003f672  mov     [rax+18h], rsi
0x14003f676  mov     word ptr [rax+20h], 800h
0x14003f67c  mov     rax, [rdx]
0x14003f67f  mov     [rdx], rsi
0x14003f682  mov     rcx, [rbx+30h]; this
0x14003f686  mov     [rbx+88h], rax
0x14003f68d  mov     [rbx+90h], rsi
0x14003f694  mov     [rbx+98h], sil
0x14003f69b  mov     [rbx+9Ch], rsi
0x14003f6a2  mov     word ptr [rbx+0A4h], 101h
0x14003f6ab  mov     [rbx+0A8h], rsi
0x14003f6b2  mov     [rbx+0B0h], rsi
0x14003f6b9  mov     [rbx+0B8h], rsi
0x14003f6c0  mov     [rbx+0C0h], rsi
0x14003f6c7  mov     [rbx+0C8h], rsi
0x14003f6ce  mov     [rbx+0D0h], rsi
0x14003f6d5  call    ?StripTrailingBackslash@UfsPathName@UnionFs@@QEAAXXZ; UnionFs::UfsPathName::StripTrailingBackslash(void)
0x14003f6da  mov     rcx, [rbx+50h]; SecurityDescriptor
0x14003f6de  lea     r9, [rbp+DaclDefaulted]; DaclDefaulted
0x14003f6e2  lea     r8, [rbp+Dacl]; Dacl
0x14003f6e6  mov     [rbp+Dacl], rsi
0x14003f6ea  lea     rdx, [rbp+DaclPresent]; DaclPresent
0x14003f6ee  mov     [rbp+DaclPresent], sil
0x14003f6f2  mov     byte ptr [rbp+DaclDefaulted], sil
0x14003f6f6  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x14003f6fd  nop     dword ptr [rax+rax+00h]
0x14003f702  mov     [rbx+58h], esi
0x14003f705  cmp     [rbp+DaclPresent], sil
0x14003f709  jz      short loc_14003F71F
0x14003f70b  mov     rcx, [rbp+Dacl]
0x14003f70f  call    cs:__imp_RtlOwnerAcesPresent
0x14003f716  nop     dword ptr [rax+rax+00h]
0x14003f71b  test    al, al
0x14003f71d  jnz     short loc_14003F723
0x14003f71f  or      dword ptr [rbx+58h], 1
0x14003f723  mov     rcx, [rbx+50h]; SecurityDescriptor
0x14003f727  lea     r9, [rbp+DaclDefaulted]; SaclDefaulted
0x14003f72b  lea     r8, [rbp+Dacl]; Sacl
0x14003f72f  mov     [rbp+DaclPresent], sil
0x14003f733  lea     rdx, [rbp+DaclPresent]; SaclPresent
0x14003f737  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x14003f73e  nop     dword ptr [rax+rax+00h]
0x14003f743  cmp     [rbp+DaclPresent], sil
0x14003f747  jz      short loc_14003F765
0x14003f749  mov     rcx, [rbp+Dacl]
0x14003f74d  xor     r8d, r8d
0x14003f750  lea     edx, [r8+11h]
0x14003f754  call    cs:__imp_RtlFindAceByType
0x14003f75b  nop     dword ptr [rax+rax+00h]
0x14003f760  test    rax, rax
0x14003f763  jnz     short loc_14003F769
0x14003f765  or      dword ptr [rbx+58h], 2
0x14003f769  cmp     [rbp+DaclPresent], sil
0x14003f76d  jz      short loc_14003F78B
0x14003f76f  mov     rcx, [rbp+Dacl]
0x14003f773  xor     r8d, r8d
0x14003f776  lea     edx, [r8+15h]
0x14003f77a  call    cs:__imp_RtlFindAceByType
0x14003f781  nop     dword ptr [rax+rax+00h]
0x14003f786  test    rax, rax
0x14003f789  jnz     short loc_14003F78F
0x14003f78b  or      dword ptr [rbx+58h], 4
0x14003f78f  mov     rcx, [rdi+8]; this
0x14003f793  test    rcx, rcx
0x14003f796  jz      short loc_14003F79D
0x14003f798  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003f79d  mov     rax, rbx
0x14003f7a0  add     rsp, 28h
0x14003f7a4  pop     rdi
0x14003f7a5  pop     rsi
0x14003f7a6  pop     rbx
0x14003f7a7  pop     rbp
0x14003f7a8  retn
```
