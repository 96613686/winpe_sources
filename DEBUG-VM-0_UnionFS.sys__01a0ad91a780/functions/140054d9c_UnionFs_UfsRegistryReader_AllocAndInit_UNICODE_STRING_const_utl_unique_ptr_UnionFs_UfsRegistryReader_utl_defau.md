# UnionFs::UfsRegistryReader::AllocAndInit(_UNICODE_STRING const &,utl::unique_ptr<UnionFs::UfsRegistryReader,utl::default_delete<UnionFs::UfsRegistryReader>> &,UnionFs::StackEventTracer &)

- ea: `0x140054d9c`
- end: `0x140054fde`
- name: `?AllocAndInit@UfsRegistryReader@UnionFs@@SAJAEBU_UNICODE_STRING@@AEAV?$unique_ptr@VUfsRegistryReader@UnionFs@@U?$default_delete@VUfsRegistryReader@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `578`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140050ef8`
- `0x140055350`

## callees

- `0x140054d2c`
- `0x140054d9c`
- `0x140056bd0`
- `0x140056c44`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x140054e4e`
- `ntoskrnl!ZwOpenKey` at `0x140054e4e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054eb9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054ed4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054f20`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054f45`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054f71`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054f96`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054eb9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054ed4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054f20`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054f45`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054f71`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054f96`
- `ntoskrnl!ExAllocatePool2` at `0x140054dbe`
- `ntoskrnl!ExAllocatePool2` at `0x140054dbe`
- `ntoskrnl!ZwClose` at `0x140054e2e`
- `ntoskrnl!ZwClose` at `0x140054f34`
- `ntoskrnl!ZwClose` at `0x140054f85`
- `ntoskrnl!ZwClose` at `0x140054e2e`
- `ntoskrnl!ZwClose` at `0x140054f34`
- `ntoskrnl!ZwClose` at `0x140054f85`

## string_xrefs

- `0x140054fa6`: `ORIGIN: Allocating UfsRegistryReader`
- `0x140054e71`: `UnionFs::UfsRegistryReader::AllocAndInit`
- `0x140054efc`: `UnionFs::UfsRegistryReader::AllocAndInit`
- `0x140054fb9`: `UnionFs::UfsRegistryReader::AllocAndInit`
- `0x140054e60`: `API: Opening config key`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsRegistryReader::AllocAndInit(struct _UNICODE_STRING *a1, __int64 *a2, int a3)
{
  __int64 Pool2; // rax
  __int64 v7; // rbx
  unsigned int v8; // edi
  __int64 *v9; // rax
  __int64 v10; // rdx
  void *v11; // rcx
  __int64 v12; // rax
  void *v13; // rcx
  __int64 v14; // rdi
  void *v15; // rcx
  const char *v17; // [rsp+28h] [rbp-60h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-58h] BYREF
  PVOID P; // [rsp+A8h] [rbp+20h] BYREF

  Pool2 = ExAllocatePool2(256, 40, 1735542357);
  v7 = Pool2;
  if ( !Pool2 )
  {
    v8 = -1073741670;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      a3,
      (struct UnionFs::StackEventTracer *)0xAA00190025LL,
      (unsigned __int64)"UnionFs::UfsRegistryReader::AllocAndInit",
      "ORIGIN: Allocating UfsRegistryReader",
      v17);
    return v8;
  }
  *(_QWORD *)Pool2 = 0;
  *(_QWORD *)(Pool2 + 8) = 0;
  *(_QWORD *)(Pool2 + 16) = 0;
  *(_QWORD *)(Pool2 + 24) = 0;
  *(_QWORD *)(Pool2 + 32) = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = a1;
  if ( *(_QWORD *)Pool2 )
    ZwClose(*(HANDLE *)Pool2);
  *(_QWORD *)v7 = 0;
  v8 = ZwOpenKey((PHANDLE)v7, 0x20019u, &ObjectAttributes);
  if ( (v8 & 0x80000000) != 0 )
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)v8,
      a3,
      (struct UnionFs::StackEventTracer *)0xAB00190032LL,
      (unsigned __int64)"UnionFs::UfsRegistryReader::AllocAndInit",
      "API: Opening config key",
      v17);
LABEL_12:
    v13 = *(void **)(v7 + 8);
    if ( v13 )
      ExFreePoolWithTag(v13, 0);
    if ( *(_QWORD *)v7 )
      ZwClose(*(HANDLE *)v7);
    ExFreePoolWithTag((PVOID)v7, 0);
    return v8;
  }
  v9 = (__int64 *)utl::make_unique_pool<enum gsl::byte [0],256,1735542357,0>(&P, 94);
  v10 = *v9;
  *v9 = 0;
  v11 = *(void **)(v7 + 8);
  *(_QWORD *)(v7 + 8) = v10;
  if ( v11 )
    ExFreePoolWithTag(v11, 0);
  if ( P )
    ExFreePoolWithTag(P, 0);
  v12 = *(_QWORD *)(v7 + 8);
  if ( !v12 )
  {
    v8 = -1073741670;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      a3,
      (struct UnionFs::StackEventTracer *)0xAC0019003ELL,
      (unsigned __int64)"UnionFs::UfsRegistryReader::AllocAndInit",
      "ORIGIN: Allocating value buffer",
      v17);
    goto LABEL_12;
  }
  *(_QWORD *)(v7 + 16) = 94;
  *(_QWORD *)(v7 + 24) = v12;
  v14 = *a2;
  *a2 = v7;
  if ( v14 )
  {
    v15 = *(void **)(v14 + 8);
    if ( v15 )
      ExFreePoolWithTag(v15, 0);
    if ( *(_QWORD *)v14 )
      ZwClose(*(HANDLE *)v14);
    ExFreePoolWithTag((PVOID)v14, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x140054d9c  push    rbx
0x140054d9e  push    rbp
0x140054d9f  push    rsi
0x140054da0  push    rdi
0x140054da1  sub     rsp, 68h
0x140054da5  mov     rbp, r8
0x140054da8  mov     rsi, rdx
0x140054dab  mov     rdi, rcx
0x140054dae  mov     edx, 28h ; '('
0x140054db3  mov     ecx, 100h
0x140054db8  mov     r8d, 67724655h
0x140054dbe  call    cs:__imp_ExAllocatePool2
0x140054dc5  nop     dword ptr [rax+rax+00h]
0x140054dca  mov     rbx, rax
0x140054dcd  test    rax, rax
0x140054dd0  jz      loc_140054FA6
0x140054dd6  mov     qword ptr [rax], 0
0x140054ddd  xorps   xmm0, xmm0
0x140054de0  mov     qword ptr [rax+8], 0
0x140054de8  mov     qword ptr [rax+10h], 0
0x140054df0  mov     qword ptr [rax+18h], 0
0x140054df8  mov     qword ptr [rax+20h], 0
0x140054e00  movdqu  xmmword ptr [rsp+88h+ObjectAttributes.SecurityDescriptor], xmm0
0x140054e06  mov     qword ptr [rsp+88h+ObjectAttributes.Length], 30h ; '0'
0x140054e0f  mov     qword ptr [rsp+88h+ObjectAttributes.Attributes], 240h
0x140054e18  mov     [rsp+88h+ObjectAttributes.RootDirectory], 0
0x140054e21  mov     [rsp+88h+ObjectAttributes.ObjectName], rdi
0x140054e26  mov     rcx, [rax]; Handle
0x140054e29  test    rcx, rcx
0x140054e2c  jz      short loc_140054E3A
0x140054e2e  call    cs:__imp_ZwClose
0x140054e35  nop     dword ptr [rax+rax+00h]
0x140054e3a  lea     r8, [rsp+88h+ObjectAttributes]; ObjectAttributes
0x140054e3f  mov     qword ptr [rbx], 0
0x140054e46  mov     edx, 20019h; DesiredAccess
0x140054e4b  mov     rcx, rbx; KeyHandle
0x140054e4e  call    cs:__imp_ZwOpenKey
0x140054e55  nop     dword ptr [rax+rax+00h]
0x140054e5a  mov     edi, eax
0x140054e5c  test    eax, eax
0x140054e5e  jns     short loc_140054E8C
0x140054e60  lea     rax, aApiOpeningConf; "API: Opening config key"
0x140054e67  mov     r8, 0AB00190032h; struct UnionFs::StackEventTracer *
0x140054e71  lea     r9, aUnionfsUfsregi_1; "UnionFs::UfsRegistryReader::AllocAndIni"...
0x140054e78  mov     [rsp+88h+var_68], rax; char *
0x140054e7d  mov     rdx, rbp; int
0x140054e80  mov     ecx, edi; this
0x140054e82  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140054e87  jmp     loc_140054F15
0x140054e8c  mov     edi, 5Eh ; '^'
0x140054e91  lea     rcx, [rsp+88h+P]
0x140054e99  mov     edx, edi
0x140054e9b  call    ??$make_unique_pool@$$BY0A@W4byte@gsl@@$0BAA@$0GHHCEGFF@$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@utl@@@0@_K@Z; utl::make_unique_pool<gsl::byte [0],256,1735542357,0>(unsigned __int64)
0x140054ea0  mov     rdx, [rax]
0x140054ea3  mov     qword ptr [rax], 0
0x140054eaa  mov     rcx, [rbx+8]; P
0x140054eae  mov     [rbx+8], rdx
0x140054eb2  test    rcx, rcx
0x140054eb5  jz      short loc_140054EC5
0x140054eb7  xor     edx, edx; Tag
0x140054eb9  call    cs:__imp_ExFreePoolWithTag
0x140054ec0  nop     dword ptr [rax+rax+00h]
0x140054ec5  mov     rcx, [rsp+88h+P]; P
0x140054ecd  test    rcx, rcx
0x140054ed0  jz      short loc_140054EE0
0x140054ed2  xor     edx, edx; Tag
0x140054ed4  call    cs:__imp_ExFreePoolWithTag
0x140054edb  nop     dword ptr [rax+rax+00h]
0x140054ee0  mov     rax, [rbx+8]
0x140054ee4  test    rax, rax
0x140054ee7  jnz     short loc_140054F53
0x140054ee9  lea     rax, aOriginAllocati_85; "ORIGIN: Allocating value buffer"
0x140054ef0  mov     edi, 0C000009Ah
0x140054ef5  mov     ecx, edi; this
0x140054ef7  mov     [rsp+88h+var_68], rax; char *
0x140054efc  lea     r9, aUnionfsUfsregi_1; "UnionFs::UfsRegistryReader::AllocAndIni"...
0x140054f03  mov     r8, 0AC0019003Eh; struct UnionFs::StackEventTracer *
0x140054f0d  mov     rdx, rbp; int
0x140054f10  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140054f15  mov     rcx, [rbx+8]; P
0x140054f19  test    rcx, rcx
0x140054f1c  jz      short loc_140054F2C
0x140054f1e  xor     edx, edx; Tag
0x140054f20  call    cs:__imp_ExFreePoolWithTag
0x140054f27  nop     dword ptr [rax+rax+00h]
0x140054f2c  mov     rcx, [rbx]; Handle
0x140054f2f  test    rcx, rcx
0x140054f32  jz      short loc_140054F40
0x140054f34  call    cs:__imp_ZwClose
0x140054f3b  nop     dword ptr [rax+rax+00h]
0x140054f40  xor     edx, edx; Tag
0x140054f42  mov     rcx, rbx; P
0x140054f45  call    cs:__imp_ExFreePoolWithTag
0x140054f4c  nop     dword ptr [rax+rax+00h]
0x140054f51  jmp     short loc_140054FD2
0x140054f53  mov     [rbx+10h], rdi
0x140054f57  mov     [rbx+18h], rax
0x140054f5b  mov     rdi, [rsi]
0x140054f5e  mov     [rsi], rbx
0x140054f61  test    rdi, rdi
0x140054f64  jz      short loc_140054FA2
0x140054f66  mov     rcx, [rdi+8]; P
0x140054f6a  test    rcx, rcx
0x140054f6d  jz      short loc_140054F7D
0x140054f6f  xor     edx, edx; Tag
0x140054f71  call    cs:__imp_ExFreePoolWithTag
0x140054f78  nop     dword ptr [rax+rax+00h]
0x140054f7d  mov     rcx, [rdi]; Handle
0x140054f80  test    rcx, rcx
0x140054f83  jz      short loc_140054F91
0x140054f85  call    cs:__imp_ZwClose
0x140054f8c  nop     dword ptr [rax+rax+00h]
0x140054f91  xor     edx, edx; Tag
0x140054f93  mov     rcx, rdi; P
0x140054f96  call    cs:__imp_ExFreePoolWithTag
0x140054f9d  nop     dword ptr [rax+rax+00h]
0x140054fa2  xor     eax, eax
0x140054fa4  jmp     short loc_140054FD4
0x140054fa6  lea     rax, aOriginAllocati_60; "ORIGIN: Allocating UfsRegistryReader"
0x140054fad  mov     edi, 0C000009Ah
0x140054fb2  mov     ecx, edi; this
0x140054fb4  mov     [rsp+88h+var_68], rax; char *
0x140054fb9  lea     r9, aUnionfsUfsregi_1; "UnionFs::UfsRegistryReader::AllocAndIni"...
0x140054fc0  mov     r8, 0AA00190025h; struct UnionFs::StackEventTracer *
0x140054fca  mov     rdx, rbp; int
0x140054fcd  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140054fd2  mov     eax, edi
0x140054fd4  add     rsp, 68h
0x140054fd8  pop     rdi
0x140054fd9  pop     rsi
0x140054fda  pop     rbp
0x140054fdb  pop     rbx
0x140054fdc  retn
```
