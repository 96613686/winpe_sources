# LockDownPolicyTask::ApplyAppLockerPolicy(void)

- ea: `0x180022bfc`
- end: `0x180022dd3`
- name: `?ApplyAppLockerPolicy@LockDownPolicyTask@@AEAAXXZ`
- size: `471`
- prototype: `void __fastcall(LockDownPolicyTask *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180023200`

## callees

- `0x18001094c`
- `0x180022298`
- `0x18002231c`
- `0x180022448`
- `0x180022bfc`
- `0x18002315c`
- `0x180023720`
- `0x1800237f0`
- `0x180023838`
- `0x1800314dc`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180022d5b`
- `OLEAUT32!__imp_VariantClear` at `0x180022d5b`

## string_xrefs

- `0x180022d6f`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\lockdownpolicytask.cpp`
- `0x180022d84`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\lockdownpolicytask.cpp`
- `0x180022d98`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\lockdownpolicytask.cpp`
- `0x180022dac`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\lockdownpolicytask.cpp`
- `0x180022dc0`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\lockdownpolicytask.cpp`
- `0x180022c10`: `<RuleCollection Type="Appx"><FilePublisherRule Id="a9e18c21-ff8f-43cf-b9fc-db40eed693ba" Name="(Default Rule) All signed packaged apps" Description="Allows members of the Everyone group to run packaged apps that are signed." UserOrGroupSid="S-1-1-0" Action="Allow"><Conditions><FilePublisherCondition PublisherName="*" ProductName="*" BinaryName="*"><BinaryVersionRange LowSection="*" HighSection="*" /></FilePublisherCondition></Conditions></FilePublisherRule></RuleCollection>`
- `0x180022c75`: `<RuleCollection Type="Exe"><FilePathRule Id="921cc481-6e17-4653-8f75-050b80acca1f" Name="All files" Description="Allows everyone to run all applications" UserOrGroupSid="S-1-1-0" Action="Allow"><Conditions><FilePathCondition Path="*" /></Conditions></FilePathRule>`
- `0x180022cce`: `<FilePublisherRule Id="%s" Name="%s, by RetailDemoService" Description="" UserOrGroupSid="%s" Action="Deny"> <Conditions> <FilePublisherCondition PublisherName="O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US" ProductName="MICROSOFT® WINDOWS® OPERATING SYSTEM" BinaryName="%s"> <BinaryVersionRange LowSection="*" HighSection="*" /> </FilePublisherCondition> </Conditions> </FilePublisherRule>`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall LockDownPolicyTask::ApplyAppLockerPolicy(LockDownPolicyTask *this)
{
  int v2; // eax
  __int64 v3; // rdx
  __int64 v4; // r8
  int v5; // ebx
  __int64 *i; // rbx
  int v7; // eax
  int v8; // eax
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  const char *v12; // [rsp+20h] [rbp-68h]
  int UserSid; // [rsp+20h] [rbp-68h]
  unsigned __int16 *v14; // [rsp+30h] [rbp-58h] BYREF
  __int64 v15; // [rsp+38h] [rbp-50h]
  __int64 v16; // [rsp+40h] [rbp-48h]
  VARIANTARG pvarg; // [rsp+48h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  pvarg.vt = 0;
  v2 = wil::Variant::SetString(
         (wil::Variant *)&pvarg,
         L"<RuleCollection Type=\"Appx\"><FilePublisherRule Id=\"a9e18c21-ff8f-43cf-b9fc-db40eed693ba\" Name=\"(Default Ru"
          "le) All signed packaged apps\" Description=\"Allows members of the Everyone group to run packaged apps that ar"
          "e signed.\" UserOrGroupSid=\"S-1-1-0\" Action=\"Allow\"><Conditions><FilePublisherCondition PublisherName=\"*\""
          " ProductName=\"*\" BinaryName=\"*\"><BinaryVersionRange LowSection=\"*\" HighSection=\"*\" /></FilePublisherCo"
          "ndition></Conditions></FilePublisherRule></RuleCollection>");
  try
  {
    if ( v2 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xEF,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\lockdownpolicytask.cpp",
        (const char *)(unsigned int)v2,
        UserSid);
    RetailDemoUtil::PolicyManagerConfigure(1, v3, v4, &pvarg);
    v14 = 0;
    v15 = 0;
    v16 = 0;
    v5 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
           (__int64)&v14,
           0x108u);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF4,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\lockdownpolicytask.cpp",
        (const char *)(unsigned int)v5,
        UserSid);
    StringCchCopyNW(
      v14,
      0x109u,
      L"<RuleCollection Type=\"Exe\"><FilePathRule Id=\"921cc481-6e17-4653-8f75-050b80acca1f\" Name=\"All files\" Descript"
       "ion=\"Allows everyone to run all applications\" UserOrGroupSid=\"S-1-1-0\" Action=\"Allow\"><Conditions><FilePath"
       "Condition Path=\"*\" /></Conditions></FilePathRule>",
      0x108u);
    v15 = 264;
    for ( i = (__int64 *)off_1800548E0; i != &qword_180054980; i += 2 )
    {
      UserSid = (unsigned int)LockDownPolicyTask::GetUserSid(this);
      v7 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::ConcatFormat(
             &v14,
             L"<FilePublisherRule Id=\"%s\" Name=\"%s, by RetailDemoService\" Description=\"\" UserOrGroupSid=\"%s\" Actio"
              "n=\"Deny\"> <Conditions> <FilePublisherCondition PublisherName=\"O=MICROSOFT CORPORATION, L=REDMOND, S=WAS"
              "HINGTON, C=US\" ProductName=\"MICROSOFT® WINDOWS® OPERATING SYSTEM\" BinaryName=\"%s\"> <BinaryVersionRang"
              "e LowSection=\"*\" HighSection=\"*\" /> </FilePublisherCondition> </Conditions> </FilePublisherRule>",
             *i,
             i[1]);
      if ( v7 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xFA,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\lockdownpolicytask.cpp",
          (const char *)(unsigned int)v7,
          UserSid);
    }
    v8 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
           &v14,
           L"</RuleCollection>",
           17);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xFE,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\lockdownpolicytask.cpp",
        (const char *)(unsigned int)v8,
        UserSid);
    v9 = wil::Variant::SetString((wil::Variant *)&pvarg, v14);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x101,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\lockdownpolicytask.cpp",
        (const char *)(unsigned int)v9,
        UserSid);
    RetailDemoUtil::PolicyManagerConfigure(2, v10, v11, &pvarg);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v14);
    VariantClear(&pvarg);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtExceptionMsg(
      retaddr,
      (void *)0x104,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\lockdownpolicytask.cpp",
      "Apply AppLocker Policy failed",
      v12);
  }
}

```

## disassembly

```asm
0x180022bfc  push    rbx
0x180022bfe  push    rsi
0x180022bff  push    rdi
0x180022c00  push    r15
0x180022c02  sub     rsp, 68h
0x180022c06  mov     rdi, rcx
0x180022c09  xor     eax, eax
0x180022c0b  mov     word ptr [rsp+88h+pvarg], ax
0x180022c10  lea     rdx, aRulecollection_1; "<RuleCollection Type=\"Appx\"><FilePubl"...
0x180022c17  lea     rcx, [rsp+88h+pvarg]; this
0x180022c1c  call    ?SetString@Variant@wil@@QEAAJPEBG@Z; wil::Variant::SetString(ushort const *)
0x180022c21  mov     rcx, [rsp+88h]; this
0x180022c29  test    eax, eax
0x180022c2b  js      loc_180022D6C
0x180022c31  lea     r9, [rsp+88h+pvarg]
0x180022c36  mov     ecx, 1
0x180022c3b  call    ?PolicyManagerConfigure@RetailDemoUtil@@YAXW4PolicyType@1@PEBG1AEBUtagVARIANT@@@Z; RetailDemoUtil::PolicyManagerConfigure(RetailDemoUtil::PolicyType,ushort const *,ushort const *,tagVARIANT const &)
0x180022c40  mov     [rsp+88h+var_58], 0
0x180022c49  mov     [rsp+88h+var_50], 0
0x180022c52  mov     [rsp+88h+var_48], 0
0x180022c5b  mov     esi, 108h
0x180022c60  mov     edx, esi
0x180022c62  lea     rcx, [rsp+88h+var_58]
0x180022c67  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x180022c6c  mov     ebx, eax
0x180022c6e  test    eax, eax
0x180022c70  js      short loc_180022C8E
0x180022c72  mov     r9d, esi; unsigned __int64
0x180022c75  lea     r8, aRulecollection; "<RuleCollection Type=\"Exe\"><FilePathR"...
0x180022c7c  lea     edx, [rsi+1]; unsigned __int64
0x180022c7f  mov     rcx, [rsp+88h+var_58]; unsigned __int16 *
0x180022c84  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180022c89  mov     [rsp+88h+var_50], rsi
0x180022c8e  mov     rcx, [rsp+88h]; this
0x180022c96  test    ebx, ebx
0x180022c98  js      loc_180022D81
0x180022c9e  lea     rbx, off_1800548E0; "5a9a7aad-edc8-4dba-8722-558053d6f801"
0x180022ca5  lea     r15, qword_180054980
0x180022cac  cmp     rbx, r15
0x180022caf  jz      short loc_180022CF5
0x180022cb1  mov     rsi, [rbx+8]
0x180022cb5  mov     rcx, rdi; this
0x180022cb8  call    ?GetUserSid@LockDownPolicyTask@@AEAAPEBGXZ; LockDownPolicyTask::GetUserSid(void)
0x180022cbd  mov     [rsp+88h+var_60], rsi
0x180022cc2  mov     qword ptr [rsp+88h+var_68], rax; int
0x180022cc7  mov     r9, [rbx+8]
0x180022ccb  mov     r8, [rbx]
0x180022cce  lea     rdx, aFilepublisherr; "<FilePublisherRule Id=\"%s\" Name=\"%s,"...
0x180022cd5  lea     rcx, [rsp+88h+var_58]
0x180022cda  call    ?ConcatFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x180022cdf  mov     rcx, [rsp+88h]; this
0x180022ce7  test    eax, eax
0x180022ce9  js      loc_180022D95
0x180022cef  add     rbx, 10h
0x180022cf3  jmp     short loc_180022CAC
0x180022cf5  mov     r8d, 11h
0x180022cfb  lea     rdx, aRulecollection_0; "</RuleCollection>"
0x180022d02  lea     rcx, [rsp+88h+var_58]
0x180022d07  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x180022d0c  mov     rcx, [rsp+88h]; this
0x180022d14  test    eax, eax
0x180022d16  js      loc_180022DA9
0x180022d1c  mov     rdx, [rsp+88h+var_58]; unsigned __int16 *
0x180022d21  lea     rcx, [rsp+88h+pvarg]; this
0x180022d26  call    ?SetString@Variant@wil@@QEAAJPEBG@Z; wil::Variant::SetString(ushort const *)
0x180022d2b  mov     rcx, [rsp+88h]; this
0x180022d33  test    eax, eax
0x180022d35  js      loc_180022DBD
0x180022d3b  lea     r9, [rsp+88h+pvarg]
0x180022d40  mov     ecx, 2
0x180022d45  call    ?PolicyManagerConfigure@RetailDemoUtil@@YAXW4PolicyType@1@PEBG1AEBUtagVARIANT@@@Z; RetailDemoUtil::PolicyManagerConfigure(RetailDemoUtil::PolicyType,ushort const *,ushort const *,tagVARIANT const &)
0x180022d4a  nop
0x180022d4b  lea     rcx, [rsp+88h+var_58]
0x180022d50  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180022d55  nop
0x180022d56  lea     rcx, [rsp+88h+pvarg]; pvarg
0x180022d5b  call    cs:__imp_VariantClear
0x180022d61  nop
0x180022d62  add     rsp, 68h
0x180022d66  pop     r15
0x180022d68  pop     rdi
0x180022d69  pop     rsi
0x180022d6a  pop     rbx
0x180022d6b  retn
0x180022d6c  mov     r9d, eax; char *
0x180022d6f  lea     r8, aPcshellShellRe_3; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180022d76  mov     edx, 0EFh; void *
0x180022d7b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180022d81  mov     r9d, ebx; char *
0x180022d84  lea     r8, aPcshellShellRe_3; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180022d8b  mov     edx, 0F4h; void *
0x180022d90  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180022d95  mov     r9d, eax; char *
0x180022d98  lea     r8, aPcshellShellRe_3; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180022d9f  mov     edx, 0FAh; void *
0x180022da4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180022da9  mov     r9d, eax; char *
0x180022dac  lea     r8, aPcshellShellRe_3; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180022db3  mov     edx, 0FEh; void *
0x180022db8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180022dbd  mov     r9d, eax; char *
0x180022dc0  lea     r8, aPcshellShellRe_3; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180022dc7  mov     edx, 101h; void *
0x180022dcc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
