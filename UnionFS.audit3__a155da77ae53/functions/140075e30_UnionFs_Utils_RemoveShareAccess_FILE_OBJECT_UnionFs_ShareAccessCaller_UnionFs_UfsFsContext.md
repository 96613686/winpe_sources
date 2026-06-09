# UnionFs::Utils::RemoveShareAccess(_FILE_OBJECT &,UnionFs::ShareAccessCaller,UnionFs::UfsFsContext *)

- ea: `0x140075e30`
- end: `0x140075fc5`
- name: `?RemoveShareAccess@Utils@UnionFs@@YAXAEAU_FILE_OBJECT@@W4ShareAccessCaller@2@PEAVUfsFsContext@2@@Z`
- size: `405`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140057a7c`
- `0x140058008`
- `0x1400702b8`

## callees

- `0x140057cc0`
- `0x14005a460`
- `0x1400678f8`
- `0x140075e30`
- `0x140079d8c`

## import_xrefs

- `ntoskrnl!IoRemoveShareAccess` at `0x140075f08`
- `ntoskrnl!IoRemoveShareAccess` at `0x140075f08`
- `ntoskrnl!ExFreePoolWithTag` at `0x140075ea9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140075fa4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140075ea9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140075fa4`
- `ntoskrnl!ExReleaseResourceLite` at `0x140075f82`
- `ntoskrnl!ExReleaseResourceLite` at `0x140075f82`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140075f8e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140075f8e`

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
0x140075e30  mov     [rsp-28h+arg_0], rbx
0x140075e35  mov     [rsp-28h+arg_8], edx
0x140075e39  push    rbp
0x140075e3a  push    rsi
0x140075e3b  push    rdi
0x140075e3c  push    r14
0x140075e3e  push    r15
0x140075e40  mov     rbp, rsp
0x140075e43  sub     rsp, 50h
0x140075e47  mov     rsi, r8
0x140075e4a  mov     r14, rcx
0x140075e4d  test    r8, r8
0x140075e50  jnz     short loc_140075E56
0x140075e52  mov     rsi, [rcx+18h]
0x140075e56  xor     ebx, ebx
0x140075e58  lea     r15, [rsi+98h]
0x140075e5f  mov     [rbp+arg_10], rbx
0x140075e63  call    Feature_UnionFS_SharingDiagnostics__private_IsEnabledDeviceUsageNoInline
0x140075e68  test    eax, eax
0x140075e6a  jnz     short loc_140075E70
0x140075e6c  xor     edi, edi
0x140075e6e  jmp     short loc_140075EC6
0x140075e70  lea     r9, [rbp+arg_10]
0x140075e74  mov     dword ptr [rbp+arg_10], 3
0x140075e7b  lea     r8, [rbp+arg_8]
0x140075e7f  mov     [rbp+Resource], r14
0x140075e83  lea     rdx, [rbp+Resource]
0x140075e87  lea     rcx, [rbp+P]
0x140075e8b  call    ??$make_unique@UShareAccessDbg@UnionFs@@PEAU_FILE_OBJECT@@AEAW4ShareAccessCaller@2@W4ShareAccessOperation@2@$0A@@utl@@YA?AV?$unique_ptr@UShareAccessDbg@UnionFs@@U?$default_delete@UShareAccessDbg@UnionFs@@@utl@@@0@$$QEAPEAU_FILE_OBJECT@@AEAW4ShareAccessCaller@UnionFs@@$$QEAW4ShareAccessOperation@4@@Z; utl::make_unique<UnionFs::ShareAccessDbg,_FILE_OBJECT *,UnionFs::ShareAccessCaller &,UnionFs::ShareAccessOperation,0>(_FILE_OBJECT * &&,UnionFs::ShareAccessCaller &,UnionFs::ShareAccessOperation &&)
0x140075e90  mov     rbx, [rax]
0x140075e93  mov     qword ptr [rax], 0
0x140075e9a  mov     rcx, [rbp+P]; P
0x140075e9e  mov     [rbp+arg_10], rbx
0x140075ea2  test    rcx, rcx
0x140075ea5  jz      short loc_140075EB5
0x140075ea7  xor     edx, edx; Tag
0x140075ea9  call    cs:__imp_ExFreePoolWithTag
0x140075eb0  nop     dword ptr [rax+rax+00h]
0x140075eb5  mov     rdi, rbx
0x140075eb8  test    rbx, rbx
0x140075ebb  jnz     short loc_140075EC6
0x140075ebd  nop
0x140075ebe  lock inc dword ptr [rsi+0CCh]
0x140075ec5  nop
0x140075ec6  mov     rdx, [rsi+78h]
0x140075eca  lea     rcx, [rbp+Resource]
0x140075ece  add     rdx, 38h ; '8'
0x140075ed2  call    ?AcquireResourceExclusive@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceExclusive(_ERESOURCE &)
0x140075ed7  call    Feature_UnionFS_SharingDiagnostics__private_IsEnabledDeviceUsageNoInline
0x140075edc  test    eax, eax
0x140075ede  jz      short loc_140075F02
0x140075ee0  test    rdi, rdi
0x140075ee3  jz      short loc_140075F02
0x140075ee5  movups  xmm0, xmmword ptr [r15]
0x140075ee9  movups  xmm1, xmmword ptr [r15+0Ch]
0x140075eee  movups  xmmword ptr [rbp+var_28], xmm0
0x140075ef2  movups  xmmword ptr [rbp+var_28+0Ch], xmm1
0x140075ef6  movups  xmm0, xmmword ptr [rbp+var_28]
0x140075efa  movups  xmmword ptr [rdi+18h], xmm0
0x140075efe  movups  xmmword ptr [rdi+24h], xmm1
0x140075f02  mov     rdx, r15; ShareAccess
0x140075f05  mov     rcx, r14; FileObject
0x140075f08  call    cs:__imp_IoRemoveShareAccess
0x140075f0f  nop     dword ptr [rax+rax+00h]
0x140075f14  call    Feature_UnionFS_SharingDiagnostics__private_IsEnabledDeviceUsageNoInline
0x140075f19  test    eax, eax
0x140075f1b  jz      short loc_140075F79
0x140075f1d  test    rdi, rdi
0x140075f20  jz      short loc_140075F79
0x140075f22  movups  xmm0, xmmword ptr [r15]
0x140075f26  lea     rdx, [rbp+arg_10]
0x140075f2a  mov     rcx, rsi
0x140075f2d  movups  xmm1, xmmword ptr [r15+0Ch]
0x140075f32  movups  xmmword ptr [rbp+var_28], xmm0
0x140075f36  movups  xmmword ptr [rbp+var_28+0Ch], xmm1
0x140075f3a  movups  xmm0, xmmword ptr [rbp+var_28]
0x140075f3e  movups  xmmword ptr [rdi+40h], xmm0
0x140075f42  movups  xmmword ptr [rdi+4Ch], xmm1
0x140075f46  mov     al, [r14+4Ah]
0x140075f4a  mov     [rdi+68h], al
0x140075f4d  mov     al, [r14+4Bh]
0x140075f51  mov     [rdi+69h], al
0x140075f54  mov     al, [r14+4Ch]
0x140075f58  mov     [rdi+6Ah], al
0x140075f5b  mov     al, [r14+4Dh]
0x140075f5f  mov     [rdi+6Bh], al
0x140075f62  mov     al, [r14+4Eh]
0x140075f66  mov     [rdi+6Ch], al
0x140075f69  mov     al, [r14+4Fh]
0x140075f6d  mov     [rdi+6Dh], al
0x140075f70  call    ?AddShareAccessDbgEntry@UfsFsContext@UnionFs@@QEAAX$$QEAV?$unique_ptr@UShareAccessDbg@UnionFs@@U?$default_delete@UShareAccessDbg@UnionFs@@@utl@@@utl@@@Z; UnionFs::UfsFsContext::AddShareAccessDbgEntry(utl::unique_ptr<UnionFs::ShareAccessDbg,utl::default_delete<UnionFs::ShareAccessDbg>> &&)
0x140075f75  mov     rbx, [rbp+arg_10]
0x140075f79  mov     rcx, [rbp+Resource]; Resource
0x140075f7d  test    rcx, rcx
0x140075f80  jz      short loc_140075F9A
0x140075f82  call    cs:__imp_ExReleaseResourceLite
0x140075f89  nop     dword ptr [rax+rax+00h]
0x140075f8e  call    cs:__imp_KeLeaveCriticalRegion
0x140075f95  nop     dword ptr [rax+rax+00h]
0x140075f9a  test    rbx, rbx
0x140075f9d  jz      short loc_140075FB0
0x140075f9f  xor     edx, edx; Tag
0x140075fa1  mov     rcx, rbx; P
0x140075fa4  call    cs:__imp_ExFreePoolWithTag
0x140075fab  nop     dword ptr [rax+rax+00h]
0x140075fb0  mov     rbx, [rsp+50h+arg_0]
0x140075fb8  add     rsp, 50h
0x140075fbc  pop     r15
0x140075fbe  pop     r14
0x140075fc0  pop     rdi
0x140075fc1  pop     rsi
0x140075fc2  pop     rbp
0x140075fc3  retn
```
