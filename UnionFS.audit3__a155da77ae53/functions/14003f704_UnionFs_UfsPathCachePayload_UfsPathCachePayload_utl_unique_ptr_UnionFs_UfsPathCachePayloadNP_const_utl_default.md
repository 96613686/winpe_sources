# UnionFs::UfsPathCachePayload::UfsPathCachePayload(utl::unique_ptr<UnionFs::UfsPathCachePayloadNP const,utl::default_delete<UnionFs::UfsPathCachePayloadNP const>> &&,utl::shared_ptr<UnionFs::UfsLayerCtx>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &&,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &&,wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>> &&,utl::unique_ptr<_SECURITY_DESCRIPTOR,utl::default_delete<_SECURITY_DESCRIPTOR>> &&,bool)

- ea: `0x14003f704`
- end: `0x14003f8ce`
- name: `??0UfsPathCachePayload@UnionFs@@AEAA@$$QEAV?$unique_ptr@$$CBVUfsPathCachePayloadNP@UnionFs@@U?$default_delete@$$CBVUfsPathCachePayloadNP@UnionFs@@@utl@@@utl@@V?$shared_ptr@VUfsLayerCtx@UnionFs@@@3@$$QEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@3@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@$$QEAV?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@$$QEAV?$unique_ptr@U_SECURITY_DESCRIPTOR@@U?$default_delete@U_SECURITY_DESCRIPTOR@@@utl@@@3@_N@Z`
- size: `458`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned __int8 DaclDefaulted, PACL Dacl, __int64, unsigned __int8 DaclPresent)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140040110`

## callees

- `0x14000f81c`
- `0x14003f704`
- `0x140044f90`

## import_xrefs

- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14003f81a`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14003f81a`
- `ntoskrnl!RtlFindAceByType` at `0x14003f878`
- `ntoskrnl!RtlFindAceByType` at `0x14003f89e`
- `ntoskrnl!RtlFindAceByType` at `0x14003f878`
- `ntoskrnl!RtlFindAceByType` at `0x14003f89e`
- `ntoskrnl!RtlOwnerAcesPresent` at `0x14003f833`
- `ntoskrnl!RtlOwnerAcesPresent` at `0x14003f833`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x14003f85b`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x14003f85b`

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
  *(_QWORD *)(a1 + 96) = 0;
  *(_QWORD *)(a1 + 104) = a1 + 104;
  *(_QWORD *)(a1 + 112) = a1 + 104;
  *(_QWORD *)(a1 + 120) = 0;
  *(_QWORD *)(a1 + 128) = 0;
  *(_WORD *)(a1 + 136) = 2048;
  v17 = *a2;
  *a2 = 0;
  v18 = *(UnionFs::UfsPathName **)(a1 + 48);
  *(_QWORD *)(a1 + 144) = v17;
  *(_QWORD *)(a1 + 152) = 0;
  *(_BYTE *)(a1 + 160) = 0;
  *(_QWORD *)(a1 + 164) = 0;
  *(_WORD *)(a1 + 172) = 257;
  *(_QWORD *)(a1 + 176) = 0;
  *(_QWORD *)(a1 + 184) = 0;
  *(_QWORD *)(a1 + 192) = 0;
  *(_QWORD *)(a1 + 200) = 0;
  *(_QWORD *)(a1 + 208) = 0;
  *(_QWORD *)(a1 + 216) = 0;
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
0x14003f704  push    rbp
0x14003f706  push    rbx
0x14003f707  push    rsi
0x14003f708  push    rdi
0x14003f709  mov     rbp, rsp
0x14003f70c  sub     rsp, 28h
0x14003f710  xor     esi, esi
0x14003f712  mov     word ptr [rcx+8], 1
0x14003f718  mov     rbx, rcx
0x14003f71b  mov     [rcx+10h], rsi
0x14003f71f  lea     rax, ??_7UfsPathCachePayload@UnionFs@@6B@; const UnionFs::UfsPathCachePayload::`vftable'
0x14003f726  mov     [rcx+18h], rsi
0x14003f72a  mov     [rcx], rax
0x14003f72d  mov     rdi, r8
0x14003f730  mov     rcx, [r8+8]
0x14003f734  mov     rax, [r8]
0x14003f737  mov     [rbx+20h], rax
0x14003f73b  mov     [rbx+28h], rcx
0x14003f73f  test    rcx, rcx
0x14003f742  jz      short loc_14003F748
0x14003f744  lock inc dword ptr [rcx+8]
0x14003f748  mov     rax, [r9]
0x14003f74b  mov     rcx, [rbp+DaclDefaulted]
0x14003f74f  mov     [r9], rsi
0x14003f752  mov     [rbx+30h], rax
0x14003f756  mov     rax, [rcx]
0x14003f759  mov     [rbx+38h], rax
0x14003f75d  mov     rax, [rbp+Dacl]
0x14003f761  mov     [rcx], rsi
0x14003f764  mov     rcx, [rax]
0x14003f767  mov     [rax], rsi
0x14003f76a  mov     rax, [rbp+arg_30]
0x14003f76e  mov     [rbx+40h], rcx
0x14003f772  mov     [rbx+48h], rsi
0x14003f776  mov     rcx, [rax]
0x14003f779  mov     [rax], rsi
0x14003f77c  lea     rax, [rbx+68h]
0x14003f780  mov     [rbx+50h], rcx
0x14003f784  mov     [rbx+58h], esi
0x14003f787  mov     [rbx+60h], rsi
0x14003f78b  mov     [rax], rax
0x14003f78e  mov     [rax+8], rax
0x14003f792  mov     [rax+10h], rsi
0x14003f796  mov     [rax+18h], rsi
0x14003f79a  mov     word ptr [rax+20h], 800h
0x14003f7a0  mov     rax, [rdx]
0x14003f7a3  mov     [rdx], rsi
0x14003f7a6  mov     rcx, [rbx+30h]; this
0x14003f7aa  mov     [rbx+90h], rax
0x14003f7b1  mov     [rbx+98h], rsi
0x14003f7b8  mov     [rbx+0A0h], sil
0x14003f7bf  mov     [rbx+0A4h], rsi
0x14003f7c6  mov     word ptr [rbx+0ACh], 101h
0x14003f7cf  mov     [rbx+0B0h], rsi
0x14003f7d6  mov     [rbx+0B8h], rsi
0x14003f7dd  mov     [rbx+0C0h], rsi
0x14003f7e4  mov     [rbx+0C8h], rsi
0x14003f7eb  mov     [rbx+0D0h], rsi
0x14003f7f2  mov     [rbx+0D8h], rsi
0x14003f7f9  call    ?StripTrailingBackslash@UfsPathName@UnionFs@@QEAAXXZ; UnionFs::UfsPathName::StripTrailingBackslash(void)
0x14003f7fe  mov     rcx, [rbx+50h]; SecurityDescriptor
0x14003f802  lea     r9, [rbp+DaclDefaulted]; DaclDefaulted
0x14003f806  lea     r8, [rbp+Dacl]; Dacl
0x14003f80a  mov     [rbp+Dacl], rsi
0x14003f80e  lea     rdx, [rbp+DaclPresent]; DaclPresent
0x14003f812  mov     [rbp+DaclPresent], sil
0x14003f816  mov     byte ptr [rbp+DaclDefaulted], sil
0x14003f81a  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x14003f821  nop     dword ptr [rax+rax+00h]
0x14003f826  mov     [rbx+58h], esi
0x14003f829  cmp     [rbp+DaclPresent], sil
0x14003f82d  jz      short loc_14003F843
0x14003f82f  mov     rcx, [rbp+Dacl]
0x14003f833  call    cs:__imp_RtlOwnerAcesPresent
0x14003f83a  nop     dword ptr [rax+rax+00h]
0x14003f83f  test    al, al
0x14003f841  jnz     short loc_14003F847
0x14003f843  or      dword ptr [rbx+58h], 1
0x14003f847  mov     rcx, [rbx+50h]; SecurityDescriptor
0x14003f84b  lea     r9, [rbp+DaclDefaulted]; SaclDefaulted
0x14003f84f  lea     r8, [rbp+Dacl]; Sacl
0x14003f853  mov     [rbp+DaclPresent], sil
0x14003f857  lea     rdx, [rbp+DaclPresent]; SaclPresent
0x14003f85b  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x14003f862  nop     dword ptr [rax+rax+00h]
0x14003f867  cmp     [rbp+DaclPresent], sil
0x14003f86b  jz      short loc_14003F889
0x14003f86d  mov     rcx, [rbp+Dacl]
0x14003f871  xor     r8d, r8d
0x14003f874  lea     edx, [r8+11h]
0x14003f878  call    cs:__imp_RtlFindAceByType
0x14003f87f  nop     dword ptr [rax+rax+00h]
0x14003f884  test    rax, rax
0x14003f887  jnz     short loc_14003F88D
0x14003f889  or      dword ptr [rbx+58h], 2
0x14003f88d  cmp     [rbp+DaclPresent], sil
0x14003f891  jz      short loc_14003F8AF
0x14003f893  mov     rcx, [rbp+Dacl]
0x14003f897  xor     r8d, r8d
0x14003f89a  lea     edx, [r8+15h]
0x14003f89e  call    cs:__imp_RtlFindAceByType
0x14003f8a5  nop     dword ptr [rax+rax+00h]
0x14003f8aa  test    rax, rax
0x14003f8ad  jnz     short loc_14003F8B3
0x14003f8af  or      dword ptr [rbx+58h], 4
0x14003f8b3  mov     rcx, [rdi+8]; this
0x14003f8b7  test    rcx, rcx
0x14003f8ba  jz      short loc_14003F8C1
0x14003f8bc  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003f8c1  mov     rax, rbx
0x14003f8c4  add     rsp, 28h
0x14003f8c8  pop     rdi
0x14003f8c9  pop     rsi
0x14003f8ca  pop     rbx
0x14003f8cb  pop     rbp
0x14003f8cc  retn
```
