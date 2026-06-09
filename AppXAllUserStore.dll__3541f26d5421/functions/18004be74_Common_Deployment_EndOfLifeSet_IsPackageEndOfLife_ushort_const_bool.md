# Common::Deployment::EndOfLifeSet::IsPackageEndOfLife(ushort const *,bool &)

- ea: `0x18004be74`
- end: `0x18004bfca`
- name: `?IsPackageEndOfLife@EndOfLifeSet@Deployment@Common@@SAJPEBGAEA_N@Z`
- size: `342`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000bf10`

## callees

- `0x180004920`
- `0x180017f50`
- `0x180018248`
- `0x18001f6bc`
- `0x18001fd80`
- `0x180022188`
- `0x18004765c`
- `0x18004bb4c`
- `0x18004bde8`
- `0x18004be74`
- `0x18004bfd0`
- `0x18004c3ec`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x18004becf`
- `ntdll!RtlEnterCriticalSection` at `0x18004becf`
- `ntdll!RtlIsGenericTableEmptyAvl` at `0x18004bf20`
- `ntdll!RtlIsGenericTableEmptyAvl` at `0x18004bf20`

## string_xrefs

- `0x18004bea7`: `onecore\admin\appmodel\common\endoflifeset.cpp`
- `0x18004bef6`: `onecore\admin\appmodel\common\endoflifeset.cpp`
- `0x18004bf4a`: `onecore\admin\appmodel\common\endoflifeset.cpp`
- `0x18004bf7a`: `onecore\admin\appmodel\common\endoflifeset.cpp`

## pseudocode

```c
__int64 __fastcall Common::Deployment::EndOfLifeSet::IsPackageEndOfLife(
        const unsigned __int16 *a1,
        bool *a2,
        struct Common::StringBuffer *a3)
{
  int PackageFamilyNameFromFullName; // eax
  Common::StaticLock *v5; // rcx
  unsigned int v6; // ebx
  struct _RTL_AVL_TABLE *v7; // rcx
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v12[4]; // [rsp+20h] [rbp-28h] BYREF
  int v13; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  struct _RTL_CRITICAL_SECTION *v15; // [rsp+58h] [rbp+10h] BYREF

  *a2 = 0;
  v13 = 0;
  *(_OWORD *)v12 = 0;
  PackageFamilyNameFromFullName = Common::Deployment::GetPackageFamilyNameFromFullName(
                                    a1,
                                    (Common::StringBuffer *)v12,
                                    a3);
  v6 = PackageFamilyNameFromFullName;
  if ( PackageFamilyNameFromFullName < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecore\\admin\\appmodel\\common\\endoflifeset.cpp",
      (const char *)(unsigned int)PackageFamilyNameFromFullName,
      v12[0]);
    goto LABEL_17;
  }
  Common::StaticLock::EnsureInitialized(v5);
  RtlEnterCriticalSection(&Common::Deployment::EndOfLifeSet::staticLock);
  v7 = Common::Deployment::EndOfLifeSet::s_endOfLifePackageFamilyNameSet;
  v15 = &Common::Deployment::EndOfLifeSet::staticLock;
  if ( !Common::Deployment::EndOfLifeSet::s_endOfLifePackageFamilyNameSet )
  {
    v8 = Common::Deployment::EndOfLifeSet::Initialize();
    v6 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x34,
        (unsigned int)"onecore\\admin\\appmodel\\common\\endoflifeset.cpp",
        (const char *)(unsigned int)v8,
        v12[0]);
LABEL_6:
      Common::AutoLock::~AutoLock(&v15);
      goto LABEL_17;
    }
    v7 = Common::Deployment::EndOfLifeSet::s_endOfLifePackageFamilyNameSet;
  }
  if ( RtlIsGenericTableEmptyAvl(v7) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EOLSetTVSFix2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EOLSetTVSFix2>::GetImpl'::`2'::impl) )
    {
      v9 = Common::Deployment::EndOfLifeSet::PopulateAppxProvisionXmlLists();
      v6 = v9;
      if ( v9 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x3C,
          (int)"onecore\\admin\\appmodel\\common\\endoflifeset.cpp",
          (const char *)(unsigned int)v9);
        Common::GenericMap<unsigned short const *,unsigned short const *>::RemoveAll(Common::Deployment::EndOfLifeSet::s_endOfLifePackageFamilyNameSet);
        goto LABEL_6;
      }
    }
    else
    {
      v10 = Common::Deployment::EndOfLifeSet::PopulateAppxProvisionXmlLists();
      if ( v10 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x44,
          (int)"onecore\\admin\\appmodel\\common\\endoflifeset.cpp",
          (const char *)(unsigned int)v10);
    }
  }
  if ( Common::GenericMap<unsigned short const *,unsigned short const *>::Find(
         Common::Deployment::EndOfLifeSet::s_endOfLifePackageFamilyNameSet,
         *(_QWORD *)&v12[2]) )
  {
    *a2 = 1;
  }
  Common::AutoLock::~AutoLock(&v15);
  v6 = 0;
LABEL_17:
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v12);
  return v6;
}

```

## disassembly

```asm
0x18004be74  mov     [rsp+arg_0], rbx
0x18004be79  push    rdi
0x18004be7a  sub     rsp, 40h
0x18004be7e  mov     rdi, rdx
0x18004be81  mov     byte ptr [rdx], 0
0x18004be84  xor     eax, eax
0x18004be86  lea     rdx, [rsp+48h+var_28]; this
0x18004be8b  xorps   xmm0, xmm0
0x18004be8e  mov     [rsp+48h+var_18], eax
0x18004be92  movups  xmmword ptr [rsp+48h+var_28], xmm0; int
0x18004be97  call    ?GetPackageFamilyNameFromFullName@Deployment@Common@@YAJPEBGPEAVStringBuffer@2@@Z; Common::Deployment::GetPackageFamilyNameFromFullName(ushort const *,Common::StringBuffer *)
0x18004be9c  mov     ebx, eax
0x18004be9e  test    eax, eax
0x18004bea0  jns     short loc_18004BEC0
0x18004bea2  mov     rcx, [rsp+48h]; this
0x18004bea7  lea     r8, aOnecoreAdminAp_26; "onecore\\admin\\appmodel\\common\\endof"...
0x18004beae  mov     r9d, eax; char *
0x18004beb1  mov     edx, 2Dh ; '-'; void *
0x18004beb6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004bebb  jmp     loc_18004BFB3
0x18004bec0  call    ?EnsureInitialized@StaticLock@Common@@QEAAXXZ; Common::StaticLock::EnsureInitialized(void)
0x18004bec5  lea     rbx, ?staticLock@EndOfLifeSet@Deployment@Common@@0VStaticLock@3@A; Common::StaticLock Common::Deployment::EndOfLifeSet::staticLock
0x18004becc  mov     rcx, rbx; CriticalSection
0x18004becf  call    cs:__imp_RtlEnterCriticalSection
0x18004bed5  mov     rcx, cs:?s_endOfLifePackageFamilyNameSet@EndOfLifeSet@Deployment@Common@@0PEAVStringSet@@EA; StringSet * Common::Deployment::EndOfLifeSet::s_endOfLifePackageFamilyNameSet
0x18004bedc  mov     [rsp+48h+arg_8], rbx
0x18004bee1  test    rcx, rcx
0x18004bee4  jnz     short loc_18004BF20
0x18004bee6  call    ?Initialize@EndOfLifeSet@Deployment@Common@@SAJXZ; Common::Deployment::EndOfLifeSet::Initialize(void)
0x18004beeb  mov     ebx, eax
0x18004beed  test    eax, eax
0x18004beef  jns     short loc_18004BF19
0x18004bef1  mov     rcx, [rsp+48h]; this
0x18004bef6  lea     r8, aOnecoreAdminAp_26; "onecore\\admin\\appmodel\\common\\endof"...
0x18004befd  mov     r9d, eax; char *
0x18004bf00  mov     edx, 34h ; '4'; void *
0x18004bf05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004bf0a  lea     rcx, [rsp+48h+arg_8]; this
0x18004bf0f  call    ??1AutoLock@Common@@QEAA@XZ; Common::AutoLock::~AutoLock(void)
0x18004bf14  jmp     loc_18004BFB3
0x18004bf19  mov     rcx, cs:?s_endOfLifePackageFamilyNameSet@EndOfLifeSet@Deployment@Common@@0PEAVStringSet@@EA; Table
0x18004bf20  call    cs:__imp_RtlIsGenericTableEmptyAvl
0x18004bf26  test    al, al
0x18004bf28  jz      short loc_18004BF8E
0x18004bf2a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EOLSetTVSFix2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EOLSetTVSFix2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EOLSetTVSFix2> `wil::Feature<__WilFeatureTraits_Feature_EOLSetTVSFix2>::GetImpl(void)'::`2'::impl
0x18004bf31  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EOLSetTVSFix2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EOLSetTVSFix2>::__private_IsEnabled(void)
0x18004bf36  test    al, al
0x18004bf38  jz      short loc_18004BF6C
0x18004bf3a  call    ?PopulateAppxProvisionXmlLists@EndOfLifeSet@Deployment@Common@@CAJXZ; Common::Deployment::EndOfLifeSet::PopulateAppxProvisionXmlLists(void)
0x18004bf3f  mov     ebx, eax
0x18004bf41  test    eax, eax
0x18004bf43  jns     short loc_18004BF8E
0x18004bf45  mov     rcx, [rsp+48h]; this
0x18004bf4a  lea     r8, aOnecoreAdminAp_26; "onecore\\admin\\appmodel\\common\\endof"...
0x18004bf51  mov     r9d, eax; char *
0x18004bf54  mov     edx, 3Ch ; '<'; void *
0x18004bf59  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004bf5e  mov     rcx, cs:?s_endOfLifePackageFamilyNameSet@EndOfLifeSet@Deployment@Common@@0PEAVStringSet@@EA; Table
0x18004bf65  call    ?RemoveAll@?$GenericMap@PEBGPEBG@Common@@QEAAXXZ; Common::GenericMap<ushort const *,ushort const *>::RemoveAll(void)
0x18004bf6a  jmp     short loc_18004BF0A
0x18004bf6c  call    ?PopulateAppxProvisionXmlLists@EndOfLifeSet@Deployment@Common@@CAJXZ; Common::Deployment::EndOfLifeSet::PopulateAppxProvisionXmlLists(void)
0x18004bf71  test    eax, eax
0x18004bf73  jns     short loc_18004BF8E
0x18004bf75  mov     rcx, [rsp+48h]; this
0x18004bf7a  lea     r8, aOnecoreAdminAp_26; "onecore\\admin\\appmodel\\common\\endof"...
0x18004bf81  mov     r9d, eax; char *
0x18004bf84  mov     edx, 44h ; 'D'; void *
0x18004bf89  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004bf8e  mov     rdx, qword ptr [rsp+48h+var_28+8]
0x18004bf93  mov     rcx, cs:?s_endOfLifePackageFamilyNameSet@EndOfLifeSet@Deployment@Common@@0PEAVStringSet@@EA; StringSet * Common::Deployment::EndOfLifeSet::s_endOfLifePackageFamilyNameSet
0x18004bf9a  call    ?Find@?$GenericMap@PEBGPEBG@Common@@QEAAPEBGPEBG@Z; Common::GenericMap<ushort const *,ushort const *>::Find(ushort const *)
0x18004bf9f  test    rax, rax
0x18004bfa2  jz      short loc_18004BFA7
0x18004bfa4  mov     byte ptr [rdi], 1
0x18004bfa7  lea     rcx, [rsp+48h+arg_8]; this
0x18004bfac  call    ??1AutoLock@Common@@QEAA@XZ; Common::AutoLock::~AutoLock(void)
0x18004bfb1  xor     ebx, ebx
0x18004bfb3  lea     rcx, [rsp+48h+var_28]; this
0x18004bfb8  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18004bfbd  mov     eax, ebx
0x18004bfbf  mov     rbx, [rsp+48h+arg_0]
0x18004bfc4  add     rsp, 40h
0x18004bfc8  pop     rdi
0x18004bfc9  retn
```
