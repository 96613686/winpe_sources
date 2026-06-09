# Windows::System::ProcessLauncherImpl::RunToCompletionAsync(HSTRING__ *,HSTRING__ *,Windows::Foundation::IAsyncOperation<Windows::System::ProcessLauncherResult *> * *)

- ea: `0x180017f50`
- end: `0x180018018`
- name: `?RunToCompletionAsync@ProcessLauncherImpl@System@Windows@@UEAAJPEAUHSTRING__@@0PEAPEAU?$IAsyncOperation@PEAVProcessLauncherResult@System@Windows@@@Foundation@3@@Z`
- size: `200`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180002dc0`
- `0x180007d74`
- `0x18000d164`
- `0x18000ee00`
- `0x180017ef4`
- `0x180017f50`
- `0x180018170`
- `0x18002b010`

## string_xrefs

- `0x180017f74`: `RunToCompletionAsyncActivity`

## pseudocode

```c
__int64 __fastcall Windows::System::ProcessLauncherImpl::RunToCompletionAsync(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4)
{
  int v8; // eax
  unsigned int v9; // ebx
  int v11; // [rsp+20h] [rbp-198h]
  _QWORD v12[42]; // [rsp+30h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v12,
    "RunToCompletionAsyncActivity");
  v12[0] = &Windows::System::SysAdminTraceLoggingProvider::RunToCompletionAsyncActivity::`vftable';
  Windows::System::SysAdminTraceLoggingProvider::RunToCompletionAsyncActivity::StartActivity((Windows::System::SysAdminTraceLoggingProvider::RunToCompletionAsyncActivity *)v12);
  v11 = a4;
  v8 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)a1 + 56LL))(a1, a2, a3, 0);
  v9 = v8;
  if ( v8 >= 0 )
  {
    wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
      v12,
      0);
    v9 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17,
      (unsigned int)"onecoreuap\\windows\\iot\\winrt\\sysadmin\\lib\\processlauncher\\processlauncherimpl.cpp",
      (const char *)(unsigned int)v8,
      v11);
  }
  Windows::System::SysAdminTraceLoggingProvider::RunToCompletionAsyncActivity::~RunToCompletionAsyncActivity((Windows::System::SysAdminTraceLoggingProvider::RunToCompletionAsyncActivity *)v12);
  return v9;
}

```

## disassembly

```asm
0x180017f50  push    rbx
0x180017f52  push    rbp
0x180017f53  push    rsi
0x180017f54  push    rdi
0x180017f55  sub     rsp, 198h
0x180017f5c  mov     rax, cs:__security_cookie
0x180017f63  xor     rax, rsp
0x180017f66  mov     [rsp+1B8h+var_38], rax
0x180017f6e  mov     rsi, rdx
0x180017f71  mov     rdi, rcx
0x180017f74  lea     rdx, aRuntocompletio; "RunToCompletionAsyncActivity"
0x180017f7b  mov     rbx, r9
0x180017f7e  lea     rcx, [rsp+1B8h+var_188]
0x180017f83  mov     rbp, r8
0x180017f86  call    ??0?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180017f8b  lea     rax, ??_7RunToCompletionAsyncActivity@SysAdminTraceLoggingProvider@System@Windows@@6B@; const Windows::System::SysAdminTraceLoggingProvider::RunToCompletionAsyncActivity::`vftable'
0x180017f92  lea     rcx, [rsp+1B8h+var_188]; this
0x180017f97  mov     [rsp+1B8h+var_188], rax
0x180017f9c  call    ?StartActivity@RunToCompletionAsyncActivity@SysAdminTraceLoggingProvider@System@Windows@@QEAAXXZ; Windows::System::SysAdminTraceLoggingProvider::RunToCompletionAsyncActivity::StartActivity(void)
0x180017fa1  mov     rax, [rdi]
0x180017fa4  xor     r9d, r9d
0x180017fa7  mov     r8, rbp
0x180017faa  mov     qword ptr [rsp+1B8h+var_198], rbx; int
0x180017faf  mov     rdx, rsi
0x180017fb2  mov     rcx, rdi
0x180017fb5  mov     rax, [rax+38h]
0x180017fb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017fbe  mov     ebx, eax
0x180017fc0  test    eax, eax
0x180017fc2  jns     short loc_180017FE2
0x180017fc4  mov     rcx, [rsp+1B8h]; this
0x180017fcc  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\iot\\winrt\\sysadm"...
0x180017fd3  mov     r9d, eax; char *
0x180017fd6  mov     edx, 17h; void *
0x180017fdb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017fe0  jmp     short loc_180017FF0
0x180017fe2  xor     edx, edx
0x180017fe4  lea     rcx, [rsp+1B8h+var_188]
0x180017fe9  call    ?Stop@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180017fee  xor     ebx, ebx
0x180017ff0  lea     rcx, [rsp+1B8h+var_188]; this
0x180017ff5  call    ??1RunToCompletionAsyncActivity@SysAdminTraceLoggingProvider@System@Windows@@QEAA@XZ; Windows::System::SysAdminTraceLoggingProvider::RunToCompletionAsyncActivity::~RunToCompletionAsyncActivity(void)
0x180017ffa  mov     eax, ebx
0x180017ffc  mov     rcx, [rsp+1B8h+var_38]
0x180018004  xor     rcx, rsp; StackCookie
0x180018007  call    __security_check_cookie
0x18001800c  add     rsp, 198h
0x180018013  pop     rdi
0x180018014  pop     rsi
0x180018015  pop     rbp
0x180018016  pop     rbx
0x180018017  retn
```
