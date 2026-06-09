# UnionFs::UnionFsFilter::CreateConfigureUnion(UFS_MSG_CREATE_CONFIG_UNION const &,ulong,UnionFs::StackEventTracer &,_GUID const *)

- ea: `0x1400090f0`
- end: `0x1400093c6`
- name: `?CreateConfigureUnion@UnionFsFilter@UnionFs@@AEAAJAEBUUFS_MSG_CREATE_CONFIG_UNION@@KAEAVStackEventTracer@2@PEBU_GUID@@@Z`
- size: `726`
- prototype: `int(UnionFs::UnionFsFilter *__hidden this, const struct UFS_MSG_CREATE_CONFIG_UNION *, unsigned int, struct UnionFs::StackEventTracer *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x14000c280`

## callees

- `0x1400090f0`
- `0x1400093cc`
- `0x140027764`
- `0x140056c7c`
- `0x14006ef20`
- `0x14006f3fc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000918e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400092bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009355`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000939e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000918e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400092bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009355`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000939e`
- `FLTMGR!FltReleaseContext` at `0x14000928b`
- `FLTMGR!FltReleaseContext` at `0x140009325`
- `FLTMGR!FltReleaseContext` at `0x14000936e`
- `FLTMGR!FltReleaseContext` at `0x14000928b`
- `FLTMGR!FltReleaseContext` at `0x140009325`
- `FLTMGR!FltReleaseContext` at `0x14000936e`
- `FLTMGR!FltObjectDereference` at `0x140009211`
- `FLTMGR!FltObjectDereference` at `0x14000929f`
- `FLTMGR!FltObjectDereference` at `0x140009339`
- `FLTMGR!FltObjectDereference` at `0x140009382`
- `FLTMGR!FltObjectDereference` at `0x140009211`
- `FLTMGR!FltObjectDereference` at `0x14000929f`
- `FLTMGR!FltObjectDereference` at `0x140009339`
- `FLTMGR!FltObjectDereference` at `0x140009382`

## string_xrefs

- `0x140009167`: `UnionFs::UnionFsFilter::CreateConfigureUnion`
- `0x1400091f2`: `UnionFs::UnionFsFilter::CreateConfigureUnion`
- `0x14000926c`: `UnionFs::UnionFsFilter::CreateConfigureUnion`
- `0x140009306`: `UnionFs::UnionFsFilter::CreateConfigureUnion`
- `0x1400092f5`: `PUSH: Calling CreateConfigureUnion`

## pseudocode

```c
__int64 __fastcall UnionFs::UnionFsFilter::CreateConfigureUnion(
        UnionFs::UnionFsFilter *this,
        const struct UFS_MSG_CREATE_CONFIG_UNION *a2,
        unsigned int a3,
        struct UnionFs::StackEventTracer *a4)
{
  unsigned int v6; // eax
  unsigned int PathRootIDsFromMsg; // ebx
  PVOID v9; // rcx
  PVOID v11; // rdi
  __int64 v12; // rcx
  UnionFs::UnionFsFilter *v13; // rcx
  int v14; // esi
  int ConfigureUnion; // r15d
  struct _GUID *v16; // [rsp+28h] [rbp-48h]
  struct _GUID *v17; // [rsp+28h] [rbp-48h]
  UNICODE_STRING VolumeName; // [rsp+40h] [rbp-30h] BYREF
  PVOID P[2]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v20; // [rsp+60h] [rbp-10h]

  v20 = -1;
  v6 = *((_DWORD *)a2 + 2);
  *(__m128i *)P = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  PathRootIDsFromMsg = UnionFs::Utils::GetPathRootIDsFromMsg(
                         (unsigned __int64)a2,
                         0x28u,
                         a3,
                         (__int64)a2 + 40,
                         v6,
                         (__int64 *)P,
                         a4);
  if ( (PathRootIDsFromMsg & 0x80000000) != 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)PathRootIDsFromMsg,
      (int)a4,
      (struct UnionFs::StackEventTracer *)0x42400011083LL,
      (unsigned __int64)"UnionFs::UnionFsFilter::CreateConfigureUnion",
      "PUSH: Getting layer list",
      (const char *)v16);
    v9 = P[0];
    if ( P[0] == (PVOID)-1LL || !P[0] )
      return PathRootIDsFromMsg;
    goto LABEL_4;
  }
  v11 = P[0];
  v12 = *(_QWORD *)P[0];
  VolumeName = 0;
  VolumeName.MaximumLength = *(_WORD *)(v12 + 4);
  VolumeName.Length = VolumeName.MaximumLength;
  VolumeName.Buffer = (PWSTR)(v12 + 6);
  PathRootIDsFromMsg = UnionFs::Utils::GetInstanceFromVolumeName(&VolumeName);
  if ( (PathRootIDsFromMsg & 0x80000000) != 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)PathRootIDsFromMsg,
      (int)a4,
      (struct UnionFs::StackEventTracer *)0x4250001108BLL,
      (unsigned __int64)"UnionFs::UnionFsFilter::CreateConfigureUnion",
      "PUSH: Getting scratch instance",
      (const char *)v16);
    if ( v11 == (PVOID)-1LL || !v11 )
      return PathRootIDsFromMsg;
    v9 = v11;
LABEL_4:
    ExFreePoolWithTag(v9, 0);
    return PathRootIDsFromMsg;
  }
  v14 = UnionFs::UfsInstanceCtx::FltGet(0);
  if ( v14 >= 0 )
  {
    ConfigureUnion = UnionFs::UnionFsFilter::CreateConfigureUnion(v13, a2, a3, 0, a4, 0);
    if ( ConfigureUnion >= 0 )
    {
      if ( v11 != (PVOID)-1LL && v11 )
        ExFreePoolWithTag(v11, 0);
      return 0;
    }
    else
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)ConfigureUnion,
        (int)a4,
        (struct UnionFs::StackEventTracer *)0x4320001109ALL,
        (unsigned __int64)"UnionFs::UnionFsFilter::CreateConfigureUnion",
        "PUSH: Calling CreateConfigureUnion",
        (const char *)v17);
      if ( v11 != (PVOID)-1LL && v11 )
        ExFreePoolWithTag(v11, 0);
      return (unsigned int)ConfigureUnion;
    }
  }
  else
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v14,
      (int)a4,
      (struct UnionFs::StackEventTracer *)0x42700011091LL,
      (unsigned __int64)"UnionFs::UnionFsFilter::CreateConfigureUnion",
      "PUSH: Getting instance ctx",
      (const char *)v16);
    if ( v11 != (PVOID)-1LL && v11 )
      ExFreePoolWithTag(v11, 0);
    return (unsigned int)v14;
  }
}

```

## disassembly

```asm
0x1400090f0  mov     r11, rsp
0x1400090f3  mov     [r11+18h], rbx
0x1400090f7  mov     [r11+20h], rsi
0x1400090fb  mov     [r11+8], rcx
0x1400090ff  push    rbp
0x140009100  push    rdi
0x140009101  push    r12
0x140009103  push    r14
0x140009105  push    r15
0x140009107  mov     rbp, rsp
0x14000910a  sub     rsp, 70h
0x14000910e  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140009116  lea     rax, [rbp+P]
0x14000911a  mov     r14, r9
0x14000911d  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFFh
0x140009125  mov     [r11-68h], r14
0x140009129  lea     r9, [rdx+28h]; int
0x14000912d  mov     [r11-70h], rax
0x140009131  mov     r15, rdx
0x140009134  mov     eax, [rdx+8]
0x140009137  mov     rcx, r15; int
0x14000913a  mov     edx, 28h ; '('; int
0x14000913f  mov     dword ptr [rsp+70h+var_50], eax; int
0x140009143  mov     r12d, r8d
0x140009146  movdqu  xmmword ptr [rbp+P], xmm0
0x14000914b  call    ?GetPathRootIDsFromMsg@Utils@UnionFs@@YAJPEBXKKQEBUUFS_PATH_ENTRY@@KAEAV?$vector@PEAVCONTAINER_ROOT_ID@UnionFs@@V?$allocator@PEAVCONTAINER_ROOT_ID@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::GetPathRootIDsFromMsg(void const *,ulong,ulong,UFS_PATH_ENTRY const * const,ulong,utl::vector<UnionFs::CONTAINER_ROOT_ID *,utl::allocator<UnionFs::CONTAINER_ROOT_ID *>> &,UnionFs::StackEventTracer &)
0x140009150  mov     ebx, eax
0x140009152  test    eax, eax
0x140009154  jns     short loc_1400091A1
0x140009156  lea     rax, aPushGettingLay_2; "PUSH: Getting layer list"
0x14000915d  mov     r8, 42400011083h; struct UnionFs::StackEventTracer *
0x140009167  lea     r9, aUnionfsUnionfs_54; "UnionFs::UnionFsFilter::CreateConfigure"...
0x14000916e  mov     [rsp+70h+var_50], rax; char *
0x140009173  mov     rdx, r14; int
0x140009176  mov     ecx, ebx; this
0x140009178  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14000917d  mov     rcx, [rbp+P]; P
0x140009181  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140009185  jz      short loc_14000919A
0x140009187  test    rcx, rcx
0x14000918a  jz      short loc_14000919A
0x14000918c  xor     edx, edx; Tag
0x14000918e  call    cs:__imp_ExFreePoolWithTag
0x140009195  nop     dword ptr [rax+rax+00h]
0x14000919a  mov     eax, ebx
0x14000919c  jmp     loc_1400093AC
0x1400091a1  mov     rdi, [rbp+P]
0x1400091a5  lea     rdx, [rbp+FltObject]
0x1400091a9  xorps   xmm0, xmm0
0x1400091ac  mov     [rbp+FltObject], 0
0x1400091b4  mov     r8, r14
0x1400091b7  mov     rcx, [rdi]
0x1400091ba  movups  xmmword ptr [rbp+VolumeName.Length], xmm0
0x1400091be  movzx   eax, word ptr [rcx+4]
0x1400091c2  mov     [rbp+VolumeName.MaximumLength], ax
0x1400091c6  mov     [rbp+VolumeName.Length], ax
0x1400091ca  lea     rax, [rcx+6]
0x1400091ce  lea     rcx, [rbp+VolumeName]; VolumeName
0x1400091d2  mov     [rbp+VolumeName.Buffer], rax
0x1400091d6  call    ?GetInstanceFromVolumeName@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_FLT_INSTANCE@@P6AXPEAX@Z$1?FltObjectDereference@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::GetInstanceFromVolumeName(_UNICODE_STRING const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_FLT_INSTANCE *,void (*)(void *),&FltObjectDereference(void *),wistd::integral_constant<unsigned __int64,0>,_FLT_INSTANCE *,_FLT_INSTANCE *,0,std::nullptr_t>>> &,UnionFs::StackEventTracer &)
0x1400091db  mov     ebx, eax
0x1400091dd  test    eax, eax
0x1400091df  jns     short loc_140009238
0x1400091e1  lea     rax, aPushGettingScr; "PUSH: Getting scratch instance"
0x1400091e8  mov     r8, 4250001108Bh; struct UnionFs::StackEventTracer *
0x1400091f2  lea     r9, aUnionfsUnionfs_54; "UnionFs::UnionFsFilter::CreateConfigure"...
0x1400091f9  mov     [rsp+70h+var_50], rax; char *
0x1400091fe  mov     rdx, r14; int
0x140009201  mov     ecx, ebx; this
0x140009203  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140009208  mov     rcx, [rbp+FltObject]; FltObject
0x14000920c  test    rcx, rcx
0x14000920f  jz      short loc_14000921D
0x140009211  call    cs:__imp_FltObjectDereference
0x140009218  nop     dword ptr [rax+rax+00h]
0x14000921d  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x140009221  jz      loc_14000919A
0x140009227  test    rdi, rdi
0x14000922a  jz      loc_14000919A
0x140009230  mov     rcx, rdi
0x140009233  jmp     loc_14000918C
0x140009238  mov     rbx, [rbp+FltObject]
0x14000923c  lea     r8, [rbp+Context]
0x140009240  mov     rcx, rbx; Instance
0x140009243  mov     [rbp+Context], 0
0x14000924b  mov     r9, r14
0x14000924e  xor     edx, edx
0x140009250  call    ?FltGet@UfsInstanceCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@_NAEAV?$unique_ptr@VUfsInstanceCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsInstanceCtx::FltGet(_FLT_INSTANCE const &,bool,wistd::unique_ptr<UnionFs::UfsInstanceCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)
0x140009255  mov     esi, eax
0x140009257  test    eax, eax
0x140009259  jns     short loc_1400092CE
0x14000925b  lea     rax, aPushGettingIns; "PUSH: Getting instance ctx"
0x140009262  mov     r8, 42700011091h; struct UnionFs::StackEventTracer *
0x14000926c  lea     r9, aUnionfsUnionfs_54; "UnionFs::UnionFsFilter::CreateConfigure"...
0x140009273  mov     [rsp+70h+var_50], rax; char *
0x140009278  mov     rdx, r14; int
0x14000927b  mov     ecx, esi; this
0x14000927d  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140009282  mov     rcx, [rbp+Context]; Context
0x140009286  test    rcx, rcx
0x140009289  jz      short loc_140009297
0x14000928b  call    cs:__imp_FltReleaseContext
0x140009292  nop     dword ptr [rax+rax+00h]
0x140009297  test    rbx, rbx
0x14000929a  jz      short loc_1400092AB
0x14000929c  mov     rcx, rbx; FltObject
0x14000929f  call    cs:__imp_FltObjectDereference
0x1400092a6  nop     dword ptr [rax+rax+00h]
0x1400092ab  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1400092af  jz      short loc_1400092C7
0x1400092b1  test    rdi, rdi
0x1400092b4  jz      short loc_1400092C7
0x1400092b6  xor     edx, edx; Tag
0x1400092b8  mov     rcx, rdi; P
0x1400092bb  call    cs:__imp_ExFreePoolWithTag
0x1400092c2  nop     dword ptr [rax+rax+00h]
0x1400092c7  mov     eax, esi
0x1400092c9  jmp     loc_1400093AC
0x1400092ce  mov     rsi, [rbp+Context]
0x1400092d2  mov     r8d, r12d; unsigned int
0x1400092d5  mov     r9, rsi; struct UnionFs::UfsInstanceCtx *
0x1400092d8  mov     [rsp+70h+var_48], 0; char *
0x1400092e1  mov     rdx, r15; struct UFS_MSG_CREATE_CONFIG_UNION *
0x1400092e4  mov     [rsp+70h+var_50], r14; struct UnionFs::StackEventTracer *
0x1400092e9  call    ?CreateConfigureUnion@UnionFsFilter@UnionFs@@AEAAJAEBUUFS_MSG_CREATE_CONFIG_UNION@@KAEAVUfsInstanceCtx@2@AEAVStackEventTracer@2@PEBU_GUID@@@Z; UnionFs::UnionFsFilter::CreateConfigureUnion(UFS_MSG_CREATE_CONFIG_UNION const &,ulong,UnionFs::UfsInstanceCtx &,UnionFs::StackEventTracer &,_GUID const *)
0x1400092ee  mov     r15d, eax
0x1400092f1  test    eax, eax
0x1400092f3  jns     short loc_140009366
0x1400092f5  lea     rax, aPushCallingCre; "PUSH: Calling CreateConfigureUnion"
0x1400092fc  mov     r8, 4320001109Ah; struct UnionFs::StackEventTracer *
0x140009306  lea     r9, aUnionfsUnionfs_54; "UnionFs::UnionFsFilter::CreateConfigure"...
0x14000930d  mov     [rsp+70h+var_50], rax; char *
0x140009312  mov     rdx, r14; int
0x140009315  mov     ecx, r15d; this
0x140009318  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14000931d  test    rsi, rsi
0x140009320  jz      short loc_140009331
0x140009322  mov     rcx, rsi; Context
0x140009325  call    cs:__imp_FltReleaseContext
0x14000932c  nop     dword ptr [rax+rax+00h]
0x140009331  test    rbx, rbx
0x140009334  jz      short loc_140009345
0x140009336  mov     rcx, rbx; FltObject
0x140009339  call    cs:__imp_FltObjectDereference
0x140009340  nop     dword ptr [rax+rax+00h]
0x140009345  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x140009349  jz      short loc_140009361
0x14000934b  test    rdi, rdi
0x14000934e  jz      short loc_140009361
0x140009350  xor     edx, edx; Tag
0x140009352  mov     rcx, rdi; P
0x140009355  call    cs:__imp_ExFreePoolWithTag
0x14000935c  nop     dword ptr [rax+rax+00h]
0x140009361  mov     eax, r15d
0x140009364  jmp     short loc_1400093AC
0x140009366  test    rsi, rsi
0x140009369  jz      short loc_14000937A
0x14000936b  mov     rcx, rsi; Context
0x14000936e  call    cs:__imp_FltReleaseContext
0x140009375  nop     dword ptr [rax+rax+00h]
0x14000937a  test    rbx, rbx
0x14000937d  jz      short loc_14000938E
0x14000937f  mov     rcx, rbx; FltObject
0x140009382  call    cs:__imp_FltObjectDereference
0x140009389  nop     dword ptr [rax+rax+00h]
0x14000938e  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x140009392  jz      short loc_1400093AA
0x140009394  test    rdi, rdi
0x140009397  jz      short loc_1400093AA
0x140009399  xor     edx, edx; Tag
0x14000939b  mov     rcx, rdi; P
0x14000939e  call    cs:__imp_ExFreePoolWithTag
0x1400093a5  nop     dword ptr [rax+rax+00h]
0x1400093aa  xor     eax, eax
0x1400093ac  lea     r11, [rsp+70h+var_s0]
0x1400093b1  mov     rbx, [r11+40h]
0x1400093b5  mov     rsi, [r11+48h]
0x1400093b9  mov     rsp, r11
0x1400093bc  pop     r15
0x1400093be  pop     r14
0x1400093c0  pop     r12
0x1400093c2  pop     rdi
0x1400093c3  pop     rbp
0x1400093c4  retn
```
