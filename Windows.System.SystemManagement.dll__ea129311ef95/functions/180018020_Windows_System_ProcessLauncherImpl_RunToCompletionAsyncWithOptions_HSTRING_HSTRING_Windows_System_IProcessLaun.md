# Windows::System::ProcessLauncherImpl::RunToCompletionAsyncWithOptions(HSTRING__ *,HSTRING__ *,Windows::System::IProcessLauncherOptions *,Windows::Foundation::IAsyncOperation<Windows::System::ProcessLauncherResult *> * *)

- ea: `0x180018020`
- end: `0x180018168`
- name: `?RunToCompletionAsyncWithOptions@ProcessLauncherImpl@System@Windows@@UEAAJPEAUHSTRING__@@0PEAUIProcessLauncherOptions@23@PEAPEAU?$IAsyncOperation@PEAVProcessLauncherResult@System@Windows@@@Foundation@3@@Z`
- size: `328`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180002dc0`
- `0x180007248`
- `0x18000d0a4`
- `0x18000ed24`
- `0x18000f824`
- `0x180017e14`
- `0x180017f20`
- `0x180018020`
- `0x180018210`
- `0x18001c6a8`
- `0x18002b010`

## string_xrefs

- `0x180018066`: `RunToCompletionAsyncWithOptionsActivity`

## pseudocode

```c
__int64 __fastcall Windows::System::ProcessLauncherImpl::RunToCompletionAsyncWithOptions(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5)
{
  int HasSystemManagementCapability; // ebx
  __int64 v8; // rcx
  int v9; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v10; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v11; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v12; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v13; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v14[42]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v13 = a2;
  v12 = a3;
  v11 = a4;
  v10 = 0;
  wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v14,
    "RunToCompletionAsyncWithOptionsActivity");
  v14[0] = &Windows::System::SysAdminTraceLoggingProvider::RunToCompletionAsyncWithOptionsActivity::`vftable';
  Windows::System::SysAdminTraceLoggingProvider::RunToCompletionAsyncWithOptionsActivity::StartActivity((Windows::System::SysAdminTraceLoggingProvider::RunToCompletionAsyncWithOptionsActivity *)v14);
  if ( !a2 || !a5 )
  {
    HasSystemManagementCapability = -2147024809;
LABEL_3:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x54,
      (unsigned int)"onecoreuap\\windows\\iot\\winrt\\sysadmin\\lib\\processlauncher\\processlauncherimpl.cpp",
      (const char *)(unsigned int)HasSystemManagementCapability,
      v9);
    goto LABEL_4;
  }
  *a5 = 0;
  LOBYTE(v9) = 0;
  HasSystemManagementCapability = Windows::System::SystemManagementUtil::HasSystemManagementCapability((unsigned __int8 *)&v9);
  if ( HasSystemManagementCapability < 0 )
    goto LABEL_3;
  if ( !(_BYTE)v9 )
  {
    HasSystemManagementCapability = -2147024891;
    goto LABEL_3;
  }
  HasSystemManagementCapability = Microsoft::WRL::Details::MakeAndInitialize<RunToCompletionAsyncOperationImpl,Windows::Foundation::IAsyncOperation<Windows::System::ProcessLauncherResult *>,HSTRING__ * &,HSTRING__ * &,Windows::System::IProcessLauncherOptions * &>(
                                    &v10,
                                    &v13,
                                    &v12,
                                    &v11);
  if ( HasSystemManagementCapability < 0 )
    goto LABEL_3;
  v8 = v10;
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
    v8 = v10;
  }
  *a5 = v8;
  HasSystemManagementCapability = 0;
LABEL_4:
  wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v14,
    (unsigned int)HasSystemManagementCapability);
  Windows::System::SysAdminTraceLoggingProvider::RunToCompletionAsyncWithOptionsActivity::~RunToCompletionAsyncWithOptionsActivity((Windows::System::SysAdminTraceLoggingProvider::RunToCompletionAsyncWithOptionsActivity *)v14);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v10);
  return (unsigned int)HasSystemManagementCapability;
}

```

## disassembly

```asm
0x180018020  push    rbp
0x180018022  push    rbx
0x180018023  push    rdi
0x180018024  lea     rbp, [rsp-0B0h]
0x18001802c  sub     rsp, 1B0h
0x180018033  mov     rax, cs:__security_cookie
0x18001803a  xor     rax, rsp
0x18001803d  mov     [rbp+0C0h+var_20], rax
0x180018044  mov     rbx, rdx
0x180018047  mov     [rsp+1C0h+var_180], rdx
0x18001804c  mov     [rsp+1C0h+var_188], r8
0x180018051  mov     [rsp+1C0h+var_190], r9
0x180018056  mov     rdi, [rbp+0C0h+arg_20]
0x18001805d  mov     [rsp+1C0h+var_198], 0
0x180018066  lea     rdx, aRuntocompletio_0; "RunToCompletionAsyncWithOptionsActivity"
0x18001806d  lea     rcx, [rsp+1C0h+var_170]
0x180018072  call    ??0?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180018077  lea     rax, ??_7RunToCompletionAsyncWithOptionsActivity@SysAdminTraceLoggingProvider@System@Windows@@6B@; const Windows::System::SysAdminTraceLoggingProvider::RunToCompletionAsyncWithOptionsActivity::`vftable'
0x18001807e  mov     [rsp+1C0h+var_170], rax
0x180018083  lea     rcx, [rsp+1C0h+var_170]; this
0x180018088  call    ?StartActivity@RunToCompletionAsyncWithOptionsActivity@SysAdminTraceLoggingProvider@System@Windows@@QEAAXXZ; Windows::System::SysAdminTraceLoggingProvider::RunToCompletionAsyncWithOptionsActivity::StartActivity(void)
0x18001808d  test    rbx, rbx
0x180018090  jnz     short loc_1800180EE
0x180018092  mov     ebx, 80070057h
0x180018097  mov     rcx, [rbp+0C8h]; this
0x18001809e  mov     r9d, ebx; char *
0x1800180a1  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\iot\\winrt\\sysadm"...
0x1800180a8  mov     edx, 54h ; 'T'; void *
0x1800180ad  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800180b2  mov     edx, ebx
0x1800180b4  lea     rcx, [rsp+1C0h+var_170]
0x1800180b9  call    ?Stop@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800180be  lea     rcx, [rsp+1C0h+var_170]; this
0x1800180c3  call    ??1RunToCompletionAsyncWithOptionsActivity@SysAdminTraceLoggingProvider@System@Windows@@QEAA@XZ; Windows::System::SysAdminTraceLoggingProvider::RunToCompletionAsyncWithOptionsActivity::~RunToCompletionAsyncWithOptionsActivity(void)
0x1800180c8  lea     rcx, [rsp+1C0h+var_198]
0x1800180cd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800180d2  mov     eax, ebx
0x1800180d4  mov     rcx, [rbp+0C0h+var_20]
0x1800180db  xor     rcx, rsp; StackCookie
0x1800180de  call    __security_check_cookie
0x1800180e3  add     rsp, 1B0h
0x1800180ea  pop     rdi
0x1800180eb  pop     rbx
0x1800180ec  pop     rbp
0x1800180ed  retn
0x1800180ee  test    rdi, rdi
0x1800180f1  jz      short loc_180018092
0x1800180f3  mov     qword ptr [rdi], 0
0x1800180fa  mov     byte ptr [rsp+1C0h+var_1A0], 0
0x1800180ff  lea     rcx, [rsp+1C0h+var_1A0]; unsigned __int8 *
0x180018104  call    ?HasSystemManagementCapability@SystemManagementUtil@System@Windows@@SAJPEAE@Z; Windows::System::SystemManagementUtil::HasSystemManagementCapability(uchar *)
0x180018109  mov     ebx, eax
0x18001810b  test    eax, eax
0x18001810d  js      short loc_180018097
0x18001810f  cmp     byte ptr [rsp+1C0h+var_1A0], 0
0x180018114  jnz     short loc_180018120
0x180018116  mov     ebx, 80070005h
0x18001811b  jmp     loc_180018097
0x180018120  lea     r9, [rsp+1C0h+var_190]
0x180018125  lea     r8, [rsp+1C0h+var_188]
0x18001812a  lea     rdx, [rsp+1C0h+var_180]
0x18001812f  lea     rcx, [rsp+1C0h+var_198]
0x180018134  call    ??$MakeAndInitialize@VRunToCompletionAsyncOperationImpl@@U?$IAsyncOperation@PEAVProcessLauncherResult@System@Windows@@@Foundation@Windows@@AEAPEAUHSTRING__@@AEAPEAU5@AEAPEAUIProcessLauncherOptions@System@4@@Details@WRL@Microsoft@@YAJPEAPEAU?$IAsyncOperation@PEAVProcessLauncherResult@System@Windows@@@Foundation@Windows@@AEAPEAUHSTRING__@@1AEAPEAUIProcessLauncherOptions@System@5@@Z; Microsoft::WRL::Details::MakeAndInitialize<RunToCompletionAsyncOperationImpl,Windows::Foundation::IAsyncOperation<Windows::System::ProcessLauncherResult *>,HSTRING__ * &,HSTRING__ * &,Windows::System::IProcessLauncherOptions * &>(Windows::Foundation::IAsyncOperation<Windows::System::ProcessLauncherResult *> * *,HSTRING__ * &,HSTRING__ * &,Windows::System::IProcessLauncherOptions * &)
0x180018139  mov     ebx, eax
0x18001813b  test    eax, eax
0x18001813d  js      loc_180018097
0x180018143  mov     rcx, [rsp+1C0h+var_198]
0x180018148  test    rcx, rcx
0x18001814b  jz      short loc_18001815E
0x18001814d  mov     rax, [rcx]
0x180018150  mov     rax, [rax+8]
0x180018154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018159  mov     rcx, [rsp+1C0h+var_198]
0x18001815e  mov     [rdi], rcx
0x180018161  xor     ebx, ebx
0x180018163  jmp     loc_1800180B2
```
