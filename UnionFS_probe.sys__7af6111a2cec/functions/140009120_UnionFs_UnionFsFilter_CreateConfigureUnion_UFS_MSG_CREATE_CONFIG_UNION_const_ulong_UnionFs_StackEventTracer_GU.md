# UnionFs::UnionFsFilter::CreateConfigureUnion(UFS_MSG_CREATE_CONFIG_UNION const &,ulong,UnionFs::StackEventTracer &,_GUID const *)

- ea: `0x140009120`
- end: `0x1400093f6`
- name: `?CreateConfigureUnion@UnionFsFilter@UnionFs@@AEAAJAEBUUFS_MSG_CREATE_CONFIG_UNION@@KAEAVStackEventTracer@2@PEBU_GUID@@@Z`
- size: `726`
- prototype: `int(UnionFs::UnionFsFilter *__hidden this, const struct UFS_MSG_CREATE_CONFIG_UNION *, unsigned int, struct UnionFs::StackEventTracer *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x14000c2b0`

## callees

- `0x140009120`
- `0x1400093fc`
- `0x1400276c4`
- `0x140056afc`
- `0x14006ed30`
- `0x14006f20c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400091be`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400092eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009385`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400093ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400091be`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400092eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009385`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400093ce`
- `FLTMGR!FltReleaseContext` at `0x1400092bb`
- `FLTMGR!FltReleaseContext` at `0x140009355`
- `FLTMGR!FltReleaseContext` at `0x14000939e`
- `FLTMGR!FltReleaseContext` at `0x1400092bb`
- `FLTMGR!FltReleaseContext` at `0x140009355`
- `FLTMGR!FltReleaseContext` at `0x14000939e`
- `FLTMGR!FltObjectDereference` at `0x140009241`
- `FLTMGR!FltObjectDereference` at `0x1400092cf`
- `FLTMGR!FltObjectDereference` at `0x140009369`
- `FLTMGR!FltObjectDereference` at `0x1400093b2`
- `FLTMGR!FltObjectDereference` at `0x140009241`
- `FLTMGR!FltObjectDereference` at `0x1400092cf`
- `FLTMGR!FltObjectDereference` at `0x140009369`
- `FLTMGR!FltObjectDereference` at `0x1400093b2`

## string_xrefs

- `0x140009197`: `UnionFs::UnionFsFilter::CreateConfigureUnion`
- `0x140009222`: `UnionFs::UnionFsFilter::CreateConfigureUnion`
- `0x14000929c`: `UnionFs::UnionFsFilter::CreateConfigureUnion`
- `0x140009336`: `UnionFs::UnionFsFilter::CreateConfigureUnion`
- `0x140009325`: `PUSH: Calling CreateConfigureUnion`

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
      (struct UnionFs::StackEventTracer *)0x42400011076LL,
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
      (struct UnionFs::StackEventTracer *)0x4250001107ELL,
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
        (struct UnionFs::StackEventTracer *)0x4320001108DLL,
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
      (struct UnionFs::StackEventTracer *)0x42700011084LL,
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
0x140009120  mov     r11, rsp
0x140009123  mov     [r11+18h], rbx
0x140009127  mov     [r11+20h], rsi
0x14000912b  mov     [r11+8], rcx
0x14000912f  push    rbp
0x140009130  push    rdi
0x140009131  push    r12
0x140009133  push    r14
0x140009135  push    r15
0x140009137  mov     rbp, rsp
0x14000913a  sub     rsp, 70h
0x14000913e  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140009146  lea     rax, [rbp+P]
0x14000914a  mov     r14, r9
0x14000914d  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFFh
0x140009155  mov     [r11-68h], r14
0x140009159  lea     r9, [rdx+28h]; int
0x14000915d  mov     [r11-70h], rax
0x140009161  mov     r15, rdx
0x140009164  mov     eax, [rdx+8]
0x140009167  mov     rcx, r15; int
0x14000916a  mov     edx, 28h ; '('; int
0x14000916f  mov     dword ptr [rsp+70h+var_50], eax; int
0x140009173  mov     r12d, r8d
0x140009176  movdqu  xmmword ptr [rbp+P], xmm0
0x14000917b  call    ?GetPathRootIDsFromMsg@Utils@UnionFs@@YAJPEBXKKQEBUUFS_PATH_ENTRY@@KAEAV?$vector@PEAVCONTAINER_ROOT_ID@UnionFs@@V?$allocator@PEAVCONTAINER_ROOT_ID@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::GetPathRootIDsFromMsg(void const *,ulong,ulong,UFS_PATH_ENTRY const * const,ulong,utl::vector<UnionFs::CONTAINER_ROOT_ID *,utl::allocator<UnionFs::CONTAINER_ROOT_ID *>> &,UnionFs::StackEventTracer &)
0x140009180  mov     ebx, eax
0x140009182  test    eax, eax
0x140009184  jns     short loc_1400091D1
0x140009186  lea     rax, aPushGettingLay_2; "PUSH: Getting layer list"
0x14000918d  mov     r8, 42400011076h; struct UnionFs::StackEventTracer *
0x140009197  lea     r9, aUnionfsUnionfs_53; "UnionFs::UnionFsFilter::CreateConfigure"...
0x14000919e  mov     [rsp+70h+var_50], rax; char *
0x1400091a3  mov     rdx, r14; int
0x1400091a6  mov     ecx, ebx; this
0x1400091a8  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400091ad  mov     rcx, [rbp+P]; P
0x1400091b1  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400091b5  jz      short loc_1400091CA
0x1400091b7  test    rcx, rcx
0x1400091ba  jz      short loc_1400091CA
0x1400091bc  xor     edx, edx; Tag
0x1400091be  call    cs:__imp_ExFreePoolWithTag
0x1400091c5  nop     dword ptr [rax+rax+00h]
0x1400091ca  mov     eax, ebx
0x1400091cc  jmp     loc_1400093DC
0x1400091d1  mov     rdi, [rbp+P]
0x1400091d5  lea     rdx, [rbp+FltObject]
0x1400091d9  xorps   xmm0, xmm0
0x1400091dc  mov     [rbp+FltObject], 0
0x1400091e4  mov     r8, r14
0x1400091e7  mov     rcx, [rdi]
0x1400091ea  movups  xmmword ptr [rbp+VolumeName.Length], xmm0
0x1400091ee  movzx   eax, word ptr [rcx+4]
0x1400091f2  mov     [rbp+VolumeName.MaximumLength], ax
0x1400091f6  mov     [rbp+VolumeName.Length], ax
0x1400091fa  lea     rax, [rcx+6]
0x1400091fe  lea     rcx, [rbp+VolumeName]; VolumeName
0x140009202  mov     [rbp+VolumeName.Buffer], rax
0x140009206  call    ?GetInstanceFromVolumeName@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_FLT_INSTANCE@@P6AXPEAX@Z$1?FltObjectDereference@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::GetInstanceFromVolumeName(_UNICODE_STRING const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_FLT_INSTANCE *,void (*)(void *),&FltObjectDereference(void *),wistd::integral_constant<unsigned __int64,0>,_FLT_INSTANCE *,_FLT_INSTANCE *,0,std::nullptr_t>>> &,UnionFs::StackEventTracer &)
0x14000920b  mov     ebx, eax
0x14000920d  test    eax, eax
0x14000920f  jns     short loc_140009268
0x140009211  lea     rax, aPushGettingScr; "PUSH: Getting scratch instance"
0x140009218  mov     r8, 4250001107Eh; struct UnionFs::StackEventTracer *
0x140009222  lea     r9, aUnionfsUnionfs_53; "UnionFs::UnionFsFilter::CreateConfigure"...
0x140009229  mov     [rsp+70h+var_50], rax; char *
0x14000922e  mov     rdx, r14; int
0x140009231  mov     ecx, ebx; this
0x140009233  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140009238  mov     rcx, [rbp+FltObject]; FltObject
0x14000923c  test    rcx, rcx
0x14000923f  jz      short loc_14000924D
0x140009241  call    cs:__imp_FltObjectDereference
0x140009248  nop     dword ptr [rax+rax+00h]
0x14000924d  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x140009251  jz      loc_1400091CA
0x140009257  test    rdi, rdi
0x14000925a  jz      loc_1400091CA
0x140009260  mov     rcx, rdi
0x140009263  jmp     loc_1400091BC
0x140009268  mov     rbx, [rbp+FltObject]
0x14000926c  lea     r8, [rbp+Context]
0x140009270  mov     rcx, rbx; Instance
0x140009273  mov     [rbp+Context], 0
0x14000927b  mov     r9, r14
0x14000927e  xor     edx, edx
0x140009280  call    ?FltGet@UfsInstanceCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@_NAEAV?$unique_ptr@VUfsInstanceCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsInstanceCtx::FltGet(_FLT_INSTANCE const &,bool,wistd::unique_ptr<UnionFs::UfsInstanceCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)
0x140009285  mov     esi, eax
0x140009287  test    eax, eax
0x140009289  jns     short loc_1400092FE
0x14000928b  lea     rax, aPushGettingIns; "PUSH: Getting instance ctx"
0x140009292  mov     r8, 42700011084h; struct UnionFs::StackEventTracer *
0x14000929c  lea     r9, aUnionfsUnionfs_53; "UnionFs::UnionFsFilter::CreateConfigure"...
0x1400092a3  mov     [rsp+70h+var_50], rax; char *
0x1400092a8  mov     rdx, r14; int
0x1400092ab  mov     ecx, esi; this
0x1400092ad  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400092b2  mov     rcx, [rbp+Context]; Context
0x1400092b6  test    rcx, rcx
0x1400092b9  jz      short loc_1400092C7
0x1400092bb  call    cs:__imp_FltReleaseContext
0x1400092c2  nop     dword ptr [rax+rax+00h]
0x1400092c7  test    rbx, rbx
0x1400092ca  jz      short loc_1400092DB
0x1400092cc  mov     rcx, rbx; FltObject
0x1400092cf  call    cs:__imp_FltObjectDereference
0x1400092d6  nop     dword ptr [rax+rax+00h]
0x1400092db  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1400092df  jz      short loc_1400092F7
0x1400092e1  test    rdi, rdi
0x1400092e4  jz      short loc_1400092F7
0x1400092e6  xor     edx, edx; Tag
0x1400092e8  mov     rcx, rdi; P
0x1400092eb  call    cs:__imp_ExFreePoolWithTag
0x1400092f2  nop     dword ptr [rax+rax+00h]
0x1400092f7  mov     eax, esi
0x1400092f9  jmp     loc_1400093DC
0x1400092fe  mov     rsi, [rbp+Context]
0x140009302  mov     r8d, r12d; unsigned int
0x140009305  mov     r9, rsi; struct UnionFs::UfsInstanceCtx *
0x140009308  mov     [rsp+70h+var_48], 0; char *
0x140009311  mov     rdx, r15; struct UFS_MSG_CREATE_CONFIG_UNION *
0x140009314  mov     [rsp+70h+var_50], r14; struct UnionFs::StackEventTracer *
0x140009319  call    ?CreateConfigureUnion@UnionFsFilter@UnionFs@@AEAAJAEBUUFS_MSG_CREATE_CONFIG_UNION@@KAEAVUfsInstanceCtx@2@AEAVStackEventTracer@2@PEBU_GUID@@@Z; UnionFs::UnionFsFilter::CreateConfigureUnion(UFS_MSG_CREATE_CONFIG_UNION const &,ulong,UnionFs::UfsInstanceCtx &,UnionFs::StackEventTracer &,_GUID const *)
0x14000931e  mov     r15d, eax
0x140009321  test    eax, eax
0x140009323  jns     short loc_140009396
0x140009325  lea     rax, aPushCallingCre; "PUSH: Calling CreateConfigureUnion"
0x14000932c  mov     r8, 4320001108Dh; struct UnionFs::StackEventTracer *
0x140009336  lea     r9, aUnionfsUnionfs_53; "UnionFs::UnionFsFilter::CreateConfigure"...
0x14000933d  mov     [rsp+70h+var_50], rax; char *
0x140009342  mov     rdx, r14; int
0x140009345  mov     ecx, r15d; this
0x140009348  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14000934d  test    rsi, rsi
0x140009350  jz      short loc_140009361
0x140009352  mov     rcx, rsi; Context
0x140009355  call    cs:__imp_FltReleaseContext
0x14000935c  nop     dword ptr [rax+rax+00h]
0x140009361  test    rbx, rbx
0x140009364  jz      short loc_140009375
0x140009366  mov     rcx, rbx; FltObject
0x140009369  call    cs:__imp_FltObjectDereference
0x140009370  nop     dword ptr [rax+rax+00h]
0x140009375  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x140009379  jz      short loc_140009391
0x14000937b  test    rdi, rdi
0x14000937e  jz      short loc_140009391
0x140009380  xor     edx, edx; Tag
0x140009382  mov     rcx, rdi; P
0x140009385  call    cs:__imp_ExFreePoolWithTag
0x14000938c  nop     dword ptr [rax+rax+00h]
0x140009391  mov     eax, r15d
0x140009394  jmp     short loc_1400093DC
0x140009396  test    rsi, rsi
0x140009399  jz      short loc_1400093AA
0x14000939b  mov     rcx, rsi; Context
0x14000939e  call    cs:__imp_FltReleaseContext
0x1400093a5  nop     dword ptr [rax+rax+00h]
0x1400093aa  test    rbx, rbx
0x1400093ad  jz      short loc_1400093BE
0x1400093af  mov     rcx, rbx; FltObject
0x1400093b2  call    cs:__imp_FltObjectDereference
0x1400093b9  nop     dword ptr [rax+rax+00h]
0x1400093be  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1400093c2  jz      short loc_1400093DA
0x1400093c4  test    rdi, rdi
0x1400093c7  jz      short loc_1400093DA
0x1400093c9  xor     edx, edx; Tag
0x1400093cb  mov     rcx, rdi; P
0x1400093ce  call    cs:__imp_ExFreePoolWithTag
0x1400093d5  nop     dword ptr [rax+rax+00h]
0x1400093da  xor     eax, eax
0x1400093dc  lea     r11, [rsp+70h+var_s0]
0x1400093e1  mov     rbx, [r11+40h]
0x1400093e5  mov     rsi, [r11+48h]
0x1400093e9  mov     rsp, r11
0x1400093ec  pop     r15
0x1400093ee  pop     r14
0x1400093f0  pop     r12
0x1400093f2  pop     rdi
0x1400093f3  pop     rbp
0x1400093f4  retn
```
