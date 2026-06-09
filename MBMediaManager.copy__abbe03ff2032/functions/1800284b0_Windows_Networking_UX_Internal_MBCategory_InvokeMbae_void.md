# Windows::Networking::UX::Internal::MBCategory::InvokeMbae(void)

- ea: `0x1800284b0`
- end: `0x1800286de`
- name: `?InvokeMbae@MBCategory@Internal@UX@Networking@Windows@@UEAAJXZ`
- size: `558`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::MBCategory *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180002150`
- `0x18000ad20`
- `0x18000d6c0`
- `0x18000fd08`
- `0x18000fe20`
- `0x18001cb10`
- `0x1800284b0`
- `0x1800286e4`
- `0x18002cd20`
- `0x180059010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x1800285ba`
- `SHCORE!SHTaskPoolQueueTask` at `0x1800285ba`

## string_xrefs

- `0x180028657`: `LaunchMbaeAppInstall`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Networking::UX::Internal::MBCategory::InvokeMbae(
        Windows::Networking::UX::Internal::MBCategory *this)
{
  int v1; // ebx
  unsigned __int64 v2; // r9
  __int64 v3; // rdx
  _QWORD *v4; // rax
  __int64 v5; // rcx
  __int64 v6; // rdx
  int v8; // eax
  int v9; // [rsp+20h] [rbp-29h]
  int v10; // [rsp+20h] [rbp-29h]
  char v11; // [rsp+30h] [rbp-19h] BYREF
  char v12; // [rsp+31h] [rbp-18h] BYREF
  char v13; // [rsp+32h] [rbp-17h] BYREF
  int v14; // [rsp+34h] [rbp-15h] BYREF
  __int64 v15; // [rsp+38h] [rbp-11h] BYREF
  __int64 v16; // [rsp+40h] [rbp-9h] BYREF
  __int64 v17; // [rsp+48h] [rbp-1h] BYREF
  _QWORD v18[7]; // [rsp+50h] [rbp+7h] BYREF
  _QWORD *v19; // [rsp+88h] [rbp+3Fh]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v15 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v18[0] = off_18005D730;
  v18[1] = (char *)this - 216;
  v18[2] = &v11;
  v18[3] = &v12;
  v18[4] = &v13;
  v18[5] = &v15;
  v19 = v18;
  v1 = Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolWorkItemAndWaitForHResult(
         (__int64)this - 216,
         (__int64)v18);
  std::_Func_class<void,>::~_Func_class<void,>(v18);
  if ( v1 < 0 )
  {
    v2 = (unsigned int)v1;
    v3 = 2022;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbcategory.cpp",
      (const char *)v2,
      v9);
    goto LABEL_15;
  }
  if ( !v11 )
  {
    if ( v12 )
    {
      MBSettingUXLogging::Info(
        "Windows::Networking::UX::Internal::MBCategory::InvokeMbae",
        2053,
        "LaunchMbaeAppInstall");
      v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 48LL))(v15);
      v1 = v8;
      if ( v8 >= 0 )
        goto LABEL_14;
      v3 = 2054;
    }
    else
    {
      if ( !v13 )
        goto LABEL_14;
      MBSettingUXLogging::Info(
        "Windows::Networking::UX::Internal::MBCategory::InvokeMbae",
        2058,
        "LaunchAccountExperienceUrl");
      v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 112LL))(v15);
      v1 = v8;
      if ( v8 >= 0 )
        goto LABEL_14;
      v3 = 2059;
    }
    v2 = (unsigned int)v8;
    goto LABEL_20;
  }
  v16 = v15;
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
  v14 = 0;
  v19 = 0;
  v19 = (_QWORD *)std::_Func_impl_no_alloc__Windows::Networking::UX::Internal::MBCategory::InvokeMbae_::_12_::_lambda_2__long_::_Func_impl_no_alloc__Windows::Networking::UX::Internal::MBCategory::InvokeMbae_::_12_::_lambda_2__long___Windows::Networking::UX::Internal::MBCategory::InvokeMbae_::_12_::_lambda_2__const___0_(
                    v18,
                    &v16);
  v4 = (_QWORD *)Windows::Internal::ComTaskPool::WrapWithResultTask<std::function<long (void)>>(&v17, &v14, v18);
  v1 = SHTaskPoolQueueTask(1, 32, 0, 0, *v4, 0);
  v5 = v17;
  if ( v17 )
  {
    v17 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  std::_Func_class<void,>::~_Func_class<void,>(v18);
  if ( v1 >= 0 )
  {
    v1 = v14;
    if ( v14 < 0 )
    {
      v6 = 2045;
      goto LABEL_10;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
LABEL_14:
    v1 = 0;
    goto LABEL_15;
  }
  v6 = 2044;
LABEL_10:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbcategory.cpp",
    (const char *)(unsigned int)v1,
    v10);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
LABEL_15:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1800284b0  mov     [rsp-8+arg_8], rbx
0x1800284b5  push    rbp
0x1800284b6  lea     rbp, [rsp-57h]
0x1800284bb  sub     rsp, 0A0h
0x1800284c2  mov     rax, cs:__security_cookie
0x1800284c9  xor     rax, rsp
0x1800284cc  mov     [rbp+57h+var_10], rax
0x1800284d0  mov     [rbp+57h+var_68], 0
0x1800284d8  mov     [rbp+57h+var_70], 0
0x1800284dc  mov     [rbp+57h+var_6F], 0
0x1800284e0  mov     [rbp+57h+var_6E], 0
0x1800284e4  add     rcx, 0FFFFFFFFFFFFFF28h
0x1800284eb  lea     rax, off_18005D730
0x1800284f2  mov     [rbp+57h+var_50], rax
0x1800284f6  mov     [rbp+57h+var_48], rcx
0x1800284fa  lea     rax, [rbp+57h+var_70]
0x1800284fe  mov     [rbp+57h+var_40], rax
0x180028502  lea     rax, [rbp+57h+var_6F]
0x180028506  mov     [rbp+57h+var_38], rax
0x18002850a  lea     rax, [rbp+57h+var_6E]
0x18002850e  mov     [rbp+57h+var_30], rax
0x180028512  lea     rax, [rbp+57h+var_68]
0x180028516  mov     [rbp+57h+var_28], rax
0x18002851a  lea     rax, [rbp+57h+var_50]
0x18002851e  mov     [rbp+57h+var_18], rax
0x180028522  lea     rdx, [rbp+57h+var_50]
0x180028526  call    ?_SubmitThreadpoolWorkItemAndWaitForHResult@MBCategory@Internal@UX@Networking@Windows@@AEAAJ$$QEAV?$function@$$A6AJXZ@std@@@Z; Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolWorkItemAndWaitForHResult(std::function<long (void)> &&)
0x18002852b  mov     ebx, eax
0x18002852d  lea     rcx, [rbp+57h+var_50]
0x180028531  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x180028536  test    ebx, ebx
0x180028538  jns     short loc_180028547
0x18002853a  mov     r9d, ebx
0x18002853d  mov     edx, 7E6h
0x180028542  jmp     loc_18002868D
0x180028547  cmp     [rbp+57h+var_70], 0
0x18002854b  jz      loc_180028651
0x180028551  mov     rcx, [rbp+57h+var_68]
0x180028555  mov     [rbp+57h+var_60], rcx
0x180028559  test    rcx, rcx
0x18002855c  jz      short loc_18002856B
0x18002855e  mov     rax, [rcx]
0x180028561  mov     rax, [rax+8]
0x180028565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002856a  nop
0x18002856b  mov     [rbp+57h+var_6C], 0
0x180028572  mov     [rbp+57h+var_18], 0
0x18002857a  lea     rdx, [rbp+57h+var_60]
0x18002857e  lea     rcx, [rbp+57h+var_50]
0x180028582  call    std___Func_impl_no_alloc__Windows__Networking__UX__Internal__MBCategory__InvokeMbae____12____lambda_2__long____Func_impl_no_alloc__Windows__Networking__UX__Internal__MBCategory__InvokeMbae____12____lambda_2__long___Windows__Networking__UX__Internal__MBCategory__InvokeMbae____12____lambda_2__const___0_
0x180028587  mov     [rbp+57h+var_18], rax
0x18002858b  lea     r8, [rbp+57h+var_50]
0x18002858f  lea     rdx, [rbp+57h+var_6C]
0x180028593  lea     rcx, [rbp+57h+var_58]
0x180028597  call    ??$WrapWithResultTask@V?$function@$$A6AJXZ@std@@@ComTaskPool@Internal@Windows@@SA?AV?$ComPtr@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@AEAJ$$QEAV?$function@$$A6AJXZ@std@@@Z; Windows::Internal::ComTaskPool::WrapWithResultTask<std::function<long (void)>>(long &,std::function<long (void)> &&)
0x18002859c  mov     [rsp+0A0h+var_78], 0
0x1800285a5  mov     rax, [rax]
0x1800285a8  mov     qword ptr [rsp+0A0h+var_80], rax; int
0x1800285ad  xor     r9d, r9d
0x1800285b0  xor     r8d, r8d
0x1800285b3  lea     edx, [r9+20h]
0x1800285b7  lea     ecx, [rdx-1Fh]
0x1800285ba  call    cs:__imp_SHTaskPoolQueueTask
0x1800285c0  mov     ebx, eax
0x1800285c2  mov     rcx, [rbp+57h+var_58]
0x1800285c6  test    rcx, rcx
0x1800285c9  jz      short loc_1800285E0
0x1800285cb  mov     [rbp+57h+var_58], 0
0x1800285d3  mov     rdx, [rcx]
0x1800285d6  mov     rax, [rdx+10h]
0x1800285da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800285df  nop
0x1800285e0  lea     rcx, [rbp+57h+var_50]
0x1800285e4  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x1800285e9  test    ebx, ebx
0x1800285eb  jns     short loc_180028610
0x1800285ed  mov     edx, 7FCh; void *
0x1800285f2  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x1800285f9  mov     r9d, ebx; char *
0x1800285fc  mov     rcx, [rbp+5Fh]; this
0x180028600  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028605  lea     rcx, [rbp+57h+var_60]
0x180028609  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002860e  jmp     short loc_180028629
0x180028610  mov     ebx, [rbp+57h+var_6C]
0x180028613  test    ebx, ebx
0x180028615  jns     short loc_18002861E
0x180028617  mov     edx, 7FDh
0x18002861c  jmp     short loc_1800285F2
0x18002861e  lea     rcx, [rbp+57h+var_60]
0x180028622  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028627  xor     ebx, ebx
0x180028629  lea     rcx, [rbp+57h+var_68]
0x18002862d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028632  mov     eax, ebx
0x180028634  mov     rcx, [rbp+57h+var_10]
0x180028638  xor     rcx, rsp; StackCookie
0x18002863b  call    __security_check_cookie
0x180028640  mov     rbx, [rsp+0A0h+arg_8]
0x180028648  add     rsp, 0A0h
0x18002864f  pop     rbp
0x180028650  retn
0x180028651  cmp     [rbp+57h+var_6F], 0
0x180028655  jz      short loc_18002869F
0x180028657  lea     r8, aLaunchmbaeappi; "LaunchMbaeAppInstall"
0x18002865e  mov     edx, 805h; unsigned int
0x180028663  lea     rcx, aWindowsNetwork_124; "Windows::Networking::UX::Internal::MBCa"...
0x18002866a  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18002866f  mov     rcx, [rbp+57h+var_68]
0x180028673  mov     rax, [rcx]
0x180028676  mov     rax, [rax+30h]
0x18002867a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002867f  mov     ebx, eax
0x180028681  test    eax, eax
0x180028683  jns     short loc_180028627
0x180028685  mov     edx, 806h; void *
0x18002868a  mov     r9d, eax; char *
0x18002868d  mov     rcx, [rbp+5Fh]; this
0x180028691  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x180028698  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002869d  jmp     short loc_180028629
0x18002869f  cmp     [rbp+57h+var_6E], 0
0x1800286a3  jz      short loc_180028627
0x1800286a5  lea     r8, aLaunchaccounte; "LaunchAccountExperienceUrl"
0x1800286ac  mov     edx, 80Ah; unsigned int
0x1800286b1  lea     rcx, aWindowsNetwork_124; "Windows::Networking::UX::Internal::MBCa"...
0x1800286b8  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x1800286bd  mov     rcx, [rbp+57h+var_68]
0x1800286c1  mov     rax, [rcx]
0x1800286c4  mov     rax, [rax+70h]
0x1800286c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800286cd  mov     ebx, eax
0x1800286cf  test    eax, eax
0x1800286d1  jns     loc_180028627
0x1800286d7  mov     edx, 80Bh
0x1800286dc  jmp     short loc_18002868A
```
