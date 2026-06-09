# UnionFs::UfsRegistryReader::AllocAndInit(_UNICODE_STRING const &,utl::unique_ptr<UnionFs::UfsRegistryReader,utl::default_delete<UnionFs::UfsRegistryReader>> &,UnionFs::StackEventTracer &)

- ea: `0x140054c18`
- end: `0x140054e5a`
- name: `?AllocAndInit@UfsRegistryReader@UnionFs@@SAJAEBU_UNICODE_STRING@@AEAV?$unique_ptr@VUfsRegistryReader@UnionFs@@U?$default_delete@VUfsRegistryReader@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `578`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140050d78`
- `0x1400551cc`

## callees

- `0x140054ba8`
- `0x140054c18`
- `0x140056a50`
- `0x140056ac4`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x140054cca`
- `ntoskrnl!ZwOpenKey` at `0x140054cca`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054d35`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054d50`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054d9c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054dc1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054ded`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054e12`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054d35`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054d50`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054d9c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054dc1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054ded`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054e12`
- `ntoskrnl!ExAllocatePool2` at `0x140054c3a`
- `ntoskrnl!ExAllocatePool2` at `0x140054c3a`
- `ntoskrnl!ZwClose` at `0x140054caa`
- `ntoskrnl!ZwClose` at `0x140054db0`
- `ntoskrnl!ZwClose` at `0x140054e01`
- `ntoskrnl!ZwClose` at `0x140054caa`
- `ntoskrnl!ZwClose` at `0x140054db0`
- `ntoskrnl!ZwClose` at `0x140054e01`

## string_xrefs

- `0x140054e22`: `ORIGIN: Allocating UfsRegistryReader`
- `0x140054ced`: `UnionFs::UfsRegistryReader::AllocAndInit`
- `0x140054d78`: `UnionFs::UfsRegistryReader::AllocAndInit`
- `0x140054e35`: `UnionFs::UfsRegistryReader::AllocAndInit`
- `0x140054cdc`: `API: Opening config key`

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
0x140054c18  push    rbx
0x140054c1a  push    rbp
0x140054c1b  push    rsi
0x140054c1c  push    rdi
0x140054c1d  sub     rsp, 68h
0x140054c21  mov     rbp, r8
0x140054c24  mov     rsi, rdx
0x140054c27  mov     rdi, rcx
0x140054c2a  mov     edx, 28h ; '('
0x140054c2f  mov     ecx, 100h
0x140054c34  mov     r8d, 67724655h
0x140054c3a  call    cs:__imp_ExAllocatePool2
0x140054c41  nop     dword ptr [rax+rax+00h]
0x140054c46  mov     rbx, rax
0x140054c49  test    rax, rax
0x140054c4c  jz      loc_140054E22
0x140054c52  mov     qword ptr [rax], 0
0x140054c59  xorps   xmm0, xmm0
0x140054c5c  mov     qword ptr [rax+8], 0
0x140054c64  mov     qword ptr [rax+10h], 0
0x140054c6c  mov     qword ptr [rax+18h], 0
0x140054c74  mov     qword ptr [rax+20h], 0
0x140054c7c  movdqu  xmmword ptr [rsp+88h+ObjectAttributes.SecurityDescriptor], xmm0
0x140054c82  mov     qword ptr [rsp+88h+ObjectAttributes.Length], 30h ; '0'
0x140054c8b  mov     qword ptr [rsp+88h+ObjectAttributes.Attributes], 240h
0x140054c94  mov     [rsp+88h+ObjectAttributes.RootDirectory], 0
0x140054c9d  mov     [rsp+88h+ObjectAttributes.ObjectName], rdi
0x140054ca2  mov     rcx, [rax]; Handle
0x140054ca5  test    rcx, rcx
0x140054ca8  jz      short loc_140054CB6
0x140054caa  call    cs:__imp_ZwClose
0x140054cb1  nop     dword ptr [rax+rax+00h]
0x140054cb6  lea     r8, [rsp+88h+ObjectAttributes]; ObjectAttributes
0x140054cbb  mov     qword ptr [rbx], 0
0x140054cc2  mov     edx, 20019h; DesiredAccess
0x140054cc7  mov     rcx, rbx; KeyHandle
0x140054cca  call    cs:__imp_ZwOpenKey
0x140054cd1  nop     dword ptr [rax+rax+00h]
0x140054cd6  mov     edi, eax
0x140054cd8  test    eax, eax
0x140054cda  jns     short loc_140054D08
0x140054cdc  lea     rax, aApiOpeningConf; "API: Opening config key"
0x140054ce3  mov     r8, 0AB00190032h; struct UnionFs::StackEventTracer *
0x140054ced  lea     r9, aUnionfsUfsregi_1; "UnionFs::UfsRegistryReader::AllocAndIni"...
0x140054cf4  mov     [rsp+88h+var_68], rax; char *
0x140054cf9  mov     rdx, rbp; int
0x140054cfc  mov     ecx, edi; this
0x140054cfe  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140054d03  jmp     loc_140054D91
0x140054d08  mov     edi, 5Eh ; '^'
0x140054d0d  lea     rcx, [rsp+88h+P]
0x140054d15  mov     edx, edi
0x140054d17  call    ??$make_unique_pool@$$BY0A@W4byte@gsl@@$0BAA@$0GHHCEGFF@$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@utl@@@0@_K@Z; utl::make_unique_pool<gsl::byte [0],256,1735542357,0>(unsigned __int64)
0x140054d1c  mov     rdx, [rax]
0x140054d1f  mov     qword ptr [rax], 0
0x140054d26  mov     rcx, [rbx+8]; P
0x140054d2a  mov     [rbx+8], rdx
0x140054d2e  test    rcx, rcx
0x140054d31  jz      short loc_140054D41
0x140054d33  xor     edx, edx; Tag
0x140054d35  call    cs:__imp_ExFreePoolWithTag
0x140054d3c  nop     dword ptr [rax+rax+00h]
0x140054d41  mov     rcx, [rsp+88h+P]; P
0x140054d49  test    rcx, rcx
0x140054d4c  jz      short loc_140054D5C
0x140054d4e  xor     edx, edx; Tag
0x140054d50  call    cs:__imp_ExFreePoolWithTag
0x140054d57  nop     dword ptr [rax+rax+00h]
0x140054d5c  mov     rax, [rbx+8]
0x140054d60  test    rax, rax
0x140054d63  jnz     short loc_140054DCF
0x140054d65  lea     rax, aOriginAllocati_84; "ORIGIN: Allocating value buffer"
0x140054d6c  mov     edi, 0C000009Ah
0x140054d71  mov     ecx, edi; this
0x140054d73  mov     [rsp+88h+var_68], rax; char *
0x140054d78  lea     r9, aUnionfsUfsregi_1; "UnionFs::UfsRegistryReader::AllocAndIni"...
0x140054d7f  mov     r8, 0AC0019003Eh; struct UnionFs::StackEventTracer *
0x140054d89  mov     rdx, rbp; int
0x140054d8c  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140054d91  mov     rcx, [rbx+8]; P
0x140054d95  test    rcx, rcx
0x140054d98  jz      short loc_140054DA8
0x140054d9a  xor     edx, edx; Tag
0x140054d9c  call    cs:__imp_ExFreePoolWithTag
0x140054da3  nop     dword ptr [rax+rax+00h]
0x140054da8  mov     rcx, [rbx]; Handle
0x140054dab  test    rcx, rcx
0x140054dae  jz      short loc_140054DBC
0x140054db0  call    cs:__imp_ZwClose
0x140054db7  nop     dword ptr [rax+rax+00h]
0x140054dbc  xor     edx, edx; Tag
0x140054dbe  mov     rcx, rbx; P
0x140054dc1  call    cs:__imp_ExFreePoolWithTag
0x140054dc8  nop     dword ptr [rax+rax+00h]
0x140054dcd  jmp     short loc_140054E4E
0x140054dcf  mov     [rbx+10h], rdi
0x140054dd3  mov     [rbx+18h], rax
0x140054dd7  mov     rdi, [rsi]
0x140054dda  mov     [rsi], rbx
0x140054ddd  test    rdi, rdi
0x140054de0  jz      short loc_140054E1E
0x140054de2  mov     rcx, [rdi+8]; P
0x140054de6  test    rcx, rcx
0x140054de9  jz      short loc_140054DF9
0x140054deb  xor     edx, edx; Tag
0x140054ded  call    cs:__imp_ExFreePoolWithTag
0x140054df4  nop     dword ptr [rax+rax+00h]
0x140054df9  mov     rcx, [rdi]; Handle
0x140054dfc  test    rcx, rcx
0x140054dff  jz      short loc_140054E0D
0x140054e01  call    cs:__imp_ZwClose
0x140054e08  nop     dword ptr [rax+rax+00h]
0x140054e0d  xor     edx, edx; Tag
0x140054e0f  mov     rcx, rdi; P
0x140054e12  call    cs:__imp_ExFreePoolWithTag
0x140054e19  nop     dword ptr [rax+rax+00h]
0x140054e1e  xor     eax, eax
0x140054e20  jmp     short loc_140054E50
0x140054e22  lea     rax, aOriginAllocati_59; "ORIGIN: Allocating UfsRegistryReader"
0x140054e29  mov     edi, 0C000009Ah
0x140054e2e  mov     ecx, edi; this
0x140054e30  mov     [rsp+88h+var_68], rax; char *
0x140054e35  lea     r9, aUnionfsUfsregi_1; "UnionFs::UfsRegistryReader::AllocAndIni"...
0x140054e3c  mov     r8, 0AA00190025h; struct UnionFs::StackEventTracer *
0x140054e46  mov     rdx, rbp; int
0x140054e49  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140054e4e  mov     eax, edi
0x140054e50  add     rsp, 68h
0x140054e54  pop     rdi
0x140054e55  pop     rsi
0x140054e56  pop     rbp
0x140054e57  pop     rbx
0x140054e58  retn
```
