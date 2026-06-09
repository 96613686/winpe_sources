# UnionFs::Utils::RemoveShareAccess(_FILE_OBJECT &,UnionFs::ShareAccessCaller,UnionFs::UfsFsContext *)

- ea: `0x140075c30`
- end: `0x140075dc5`
- name: `?RemoveShareAccess@Utils@UnionFs@@YAXAEAU_FILE_OBJECT@@W4ShareAccessCaller@2@PEAVUfsFsContext@2@@Z`
- size: `405`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1400578fc`
- `0x140057e88`
- `0x1400700c8`

## callees

- `0x140057b40`
- `0x14005a2e0`
- `0x140067778`
- `0x140075c30`
- `0x140079a6c`

## import_xrefs

- `ntoskrnl!IoRemoveShareAccess` at `0x140075d08`
- `ntoskrnl!IoRemoveShareAccess` at `0x140075d08`
- `ntoskrnl!ExFreePoolWithTag` at `0x140075ca9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140075da4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140075ca9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140075da4`
- `ntoskrnl!ExReleaseResourceLite` at `0x140075d82`
- `ntoskrnl!ExReleaseResourceLite` at `0x140075d82`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140075d8e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140075d8e`

## pseudocode

```c
void __fastcall UnionFs::Utils::RemoveShareAccess(__int64 a1, int a2, __int64 a3)
{
  __int64 v3; // rsi
  void *v5; // rbx
  _OWORD *v6; // r15
  _OWORD *v7; // rdi
  void **v8; // rax
  __int128 v9; // xmm1
  __int128 v10; // xmm1
  PVOID P; // [rsp+20h] [rbp-30h] BYREF
  _OWORD v12[2]; // [rsp+28h] [rbp-28h]
  int v13; // [rsp+88h] [rbp+38h] BYREF
  void *v14; // [rsp+90h] [rbp+40h] BYREF
  PERESOURCE Resource; // [rsp+98h] [rbp+48h] BYREF

  v13 = a2;
  v3 = a3;
  if ( !a3 )
    v3 = *(_QWORD *)(a1 + 24);
  v5 = 0;
  v6 = (_OWORD *)(v3 + 152);
  v14 = 0;
  if ( (unsigned int)Feature_UnionFS_SharingDiagnostics__private_IsEnabledDeviceUsageNoInline() )
  {
    LODWORD(v14) = 3;
    Resource = (PERESOURCE)a1;
    v8 = (void **)utl::make_unique<UnionFs::ShareAccessDbg,_FILE_OBJECT *,enum UnionFs::ShareAccessCaller &,enum UnionFs::ShareAccessOperation,0>(
                    &P,
                    &Resource,
                    &v13,
                    &v14);
    v5 = *v8;
    *v8 = 0;
    v14 = v5;
    if ( P )
      ExFreePoolWithTag(P, 0);
    v7 = v5;
    if ( !v5 )
      _InterlockedIncrement((volatile signed __int32 *)(v3 + 204));
  }
  else
  {
    v7 = 0;
  }
  FsFltWil::AcquireResourceExclusive(&Resource, *(_QWORD *)(v3 + 120) + 56LL);
  if ( (unsigned int)Feature_UnionFS_SharingDiagnostics__private_IsEnabledDeviceUsageNoInline() && v7 )
  {
    v9 = *(_OWORD *)(v3 + 164);
    v12[0] = *v6;
    *(_OWORD *)((char *)v12 + 12) = v9;
    *(_OWORD *)((char *)v7 + 24) = v12[0];
    *(_OWORD *)((char *)v7 + 36) = v9;
  }
  IoRemoveShareAccess((PFILE_OBJECT)a1, (PSHARE_ACCESS)(v3 + 152));
  if ( (unsigned int)Feature_UnionFS_SharingDiagnostics__private_IsEnabledDeviceUsageNoInline() && v7 )
  {
    v10 = *(_OWORD *)(v3 + 164);
    v12[0] = *v6;
    *(_OWORD *)((char *)v12 + 12) = v10;
    v7[4] = v12[0];
    *(_OWORD *)((char *)v7 + 76) = v10;
    *((_BYTE *)v7 + 104) = *(_BYTE *)(a1 + 74);
    *((_BYTE *)v7 + 105) = *(_BYTE *)(a1 + 75);
    *((_BYTE *)v7 + 106) = *(_BYTE *)(a1 + 76);
    *((_BYTE *)v7 + 107) = *(_BYTE *)(a1 + 77);
    *((_BYTE *)v7 + 108) = *(_BYTE *)(a1 + 78);
    *((_BYTE *)v7 + 109) = *(_BYTE *)(a1 + 79);
    UnionFs::UfsFsContext::AddShareAccessDbgEntry(v3, &v14);
    v5 = v14;
  }
  if ( Resource )
  {
    ExReleaseResourceLite(Resource);
    KeLeaveCriticalRegion();
  }
  if ( v5 )
    ExFreePoolWithTag(v5, 0);
}

```

## disassembly

```asm
0x140075c30  mov     [rsp-28h+arg_0], rbx
0x140075c35  mov     [rsp-28h+arg_8], edx
0x140075c39  push    rbp
0x140075c3a  push    rsi
0x140075c3b  push    rdi
0x140075c3c  push    r14
0x140075c3e  push    r15
0x140075c40  mov     rbp, rsp
0x140075c43  sub     rsp, 50h
0x140075c47  mov     rsi, r8
0x140075c4a  mov     r14, rcx
0x140075c4d  test    r8, r8
0x140075c50  jnz     short loc_140075C56
0x140075c52  mov     rsi, [rcx+18h]
0x140075c56  xor     ebx, ebx
0x140075c58  lea     r15, [rsi+98h]
0x140075c5f  mov     [rbp+arg_10], rbx
0x140075c63  call    Feature_UnionFS_SharingDiagnostics__private_IsEnabledDeviceUsageNoInline
0x140075c68  test    eax, eax
0x140075c6a  jnz     short loc_140075C70
0x140075c6c  xor     edi, edi
0x140075c6e  jmp     short loc_140075CC6
0x140075c70  lea     r9, [rbp+arg_10]
0x140075c74  mov     dword ptr [rbp+arg_10], 3
0x140075c7b  lea     r8, [rbp+arg_8]
0x140075c7f  mov     [rbp+Resource], r14
0x140075c83  lea     rdx, [rbp+Resource]
0x140075c87  lea     rcx, [rbp+P]
0x140075c8b  call    ??$make_unique@UShareAccessDbg@UnionFs@@PEAU_FILE_OBJECT@@AEAW4ShareAccessCaller@2@W4ShareAccessOperation@2@$0A@@utl@@YA?AV?$unique_ptr@UShareAccessDbg@UnionFs@@U?$default_delete@UShareAccessDbg@UnionFs@@@utl@@@0@$$QEAPEAU_FILE_OBJECT@@AEAW4ShareAccessCaller@UnionFs@@$$QEAW4ShareAccessOperation@4@@Z; utl::make_unique<UnionFs::ShareAccessDbg,_FILE_OBJECT *,UnionFs::ShareAccessCaller &,UnionFs::ShareAccessOperation,0>(_FILE_OBJECT * &&,UnionFs::ShareAccessCaller &,UnionFs::ShareAccessOperation &&)
0x140075c90  mov     rbx, [rax]
0x140075c93  mov     qword ptr [rax], 0
0x140075c9a  mov     rcx, [rbp+P]; P
0x140075c9e  mov     [rbp+arg_10], rbx
0x140075ca2  test    rcx, rcx
0x140075ca5  jz      short loc_140075CB5
0x140075ca7  xor     edx, edx; Tag
0x140075ca9  call    cs:__imp_ExFreePoolWithTag
0x140075cb0  nop     dword ptr [rax+rax+00h]
0x140075cb5  mov     rdi, rbx
0x140075cb8  test    rbx, rbx
0x140075cbb  jnz     short loc_140075CC6
0x140075cbd  nop
0x140075cbe  lock inc dword ptr [rsi+0CCh]
0x140075cc5  nop
0x140075cc6  mov     rdx, [rsi+78h]
0x140075cca  lea     rcx, [rbp+Resource]
0x140075cce  add     rdx, 38h ; '8'
0x140075cd2  call    ?AcquireResourceExclusive@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceExclusive(_ERESOURCE &)
0x140075cd7  call    Feature_UnionFS_SharingDiagnostics__private_IsEnabledDeviceUsageNoInline
0x140075cdc  test    eax, eax
0x140075cde  jz      short loc_140075D02
0x140075ce0  test    rdi, rdi
0x140075ce3  jz      short loc_140075D02
0x140075ce5  movups  xmm0, xmmword ptr [r15]
0x140075ce9  movups  xmm1, xmmword ptr [r15+0Ch]
0x140075cee  movups  xmmword ptr [rbp+var_28], xmm0
0x140075cf2  movups  xmmword ptr [rbp+var_28+0Ch], xmm1
0x140075cf6  movups  xmm0, xmmword ptr [rbp+var_28]
0x140075cfa  movups  xmmword ptr [rdi+18h], xmm0
0x140075cfe  movups  xmmword ptr [rdi+24h], xmm1
0x140075d02  mov     rdx, r15; ShareAccess
0x140075d05  mov     rcx, r14; FileObject
0x140075d08  call    cs:__imp_IoRemoveShareAccess
0x140075d0f  nop     dword ptr [rax+rax+00h]
0x140075d14  call    Feature_UnionFS_SharingDiagnostics__private_IsEnabledDeviceUsageNoInline
0x140075d19  test    eax, eax
0x140075d1b  jz      short loc_140075D79
0x140075d1d  test    rdi, rdi
0x140075d20  jz      short loc_140075D79
0x140075d22  movups  xmm0, xmmword ptr [r15]
0x140075d26  lea     rdx, [rbp+arg_10]
0x140075d2a  mov     rcx, rsi
0x140075d2d  movups  xmm1, xmmword ptr [r15+0Ch]
0x140075d32  movups  xmmword ptr [rbp+var_28], xmm0
0x140075d36  movups  xmmword ptr [rbp+var_28+0Ch], xmm1
0x140075d3a  movups  xmm0, xmmword ptr [rbp+var_28]
0x140075d3e  movups  xmmword ptr [rdi+40h], xmm0
0x140075d42  movups  xmmword ptr [rdi+4Ch], xmm1
0x140075d46  mov     al, [r14+4Ah]
0x140075d4a  mov     [rdi+68h], al
0x140075d4d  mov     al, [r14+4Bh]
0x140075d51  mov     [rdi+69h], al
0x140075d54  mov     al, [r14+4Ch]
0x140075d58  mov     [rdi+6Ah], al
0x140075d5b  mov     al, [r14+4Dh]
0x140075d5f  mov     [rdi+6Bh], al
0x140075d62  mov     al, [r14+4Eh]
0x140075d66  mov     [rdi+6Ch], al
0x140075d69  mov     al, [r14+4Fh]
0x140075d6d  mov     [rdi+6Dh], al
0x140075d70  call    ?AddShareAccessDbgEntry@UfsFsContext@UnionFs@@QEAAX$$QEAV?$unique_ptr@UShareAccessDbg@UnionFs@@U?$default_delete@UShareAccessDbg@UnionFs@@@utl@@@utl@@@Z; UnionFs::UfsFsContext::AddShareAccessDbgEntry(utl::unique_ptr<UnionFs::ShareAccessDbg,utl::default_delete<UnionFs::ShareAccessDbg>> &&)
0x140075d75  mov     rbx, [rbp+arg_10]
0x140075d79  mov     rcx, [rbp+Resource]; Resource
0x140075d7d  test    rcx, rcx
0x140075d80  jz      short loc_140075D9A
0x140075d82  call    cs:__imp_ExReleaseResourceLite
0x140075d89  nop     dword ptr [rax+rax+00h]
0x140075d8e  call    cs:__imp_KeLeaveCriticalRegion
0x140075d95  nop     dword ptr [rax+rax+00h]
0x140075d9a  test    rbx, rbx
0x140075d9d  jz      short loc_140075DB0
0x140075d9f  xor     edx, edx; Tag
0x140075da1  mov     rcx, rbx; P
0x140075da4  call    cs:__imp_ExFreePoolWithTag
0x140075dab  nop     dword ptr [rax+rax+00h]
0x140075db0  mov     rbx, [rsp+50h+arg_0]
0x140075db8  add     rsp, 50h
0x140075dbc  pop     r15
0x140075dbe  pop     r14
0x140075dc0  pop     rdi
0x140075dc1  pop     rsi
0x140075dc2  pop     rbp
0x140075dc3  retn
```
