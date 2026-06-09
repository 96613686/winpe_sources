# SpeechMicDiagnostic::CreateSpeechMicDiagnostic(SpeechMicDiagnostic::ISpeechMicDiagnostic * *)

- ea: `0x180007e38`
- end: `0x180007f12`
- name: `?CreateSpeechMicDiagnostic@SpeechMicDiagnostic@@YAJPEAPEAUISpeechMicDiagnostic@1@@Z`
- size: `218`
- prototype: `__int64 __fastcall(SpeechMicDiagnostic *__hidden this, struct SpeechMicDiagnostic::ISpeechMicDiagnostic **)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800068a0`

## callees

- `0x180002910`
- `0x180005b28`
- `0x18000744c`
- `0x180007510`
- `0x180007c88`
- `0x180007e38`
- `0x180007f18`
- `0x180009df0`
- `0x18000a964`

## string_xrefs

- `0x180007e57`: `CreateInstance`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SpeechMicDiagnostic::CreateSpeechMicDiagnostic(
        SpeechMicDiagnostic *this,
        struct SpeechMicDiagnostic::ISpeechMicDiagnostic **a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  struct SpeechMicDiagnostic::CSpeechMicDiagnostic *v5; // [rsp+20h] [rbp-178h] BYREF
  _QWORD v6[42]; // [rsp+30h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]

  wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v6,
    "CreateInstance");
  v6[0] = &SpeechMicDiagnostic::SmdTraceProvider::CreateInstance::`vftable';
  SpeechMicDiagnostic::SmdTraceProvider::CreateInstance::StartActivity(
    (SpeechMicDiagnostic::SmdTraceProvider::CreateInstance *)v6,
    &g_pSpeechDiagnostic);
  v5 = 0;
  v2 = SpeechMicDiagnostic::CSpeechMicDiagnostic::CreateInstance(&v5);
  v3 = v2;
  if ( v2 >= 0 )
  {
    g_pSpeechDiagnostic = v5;
    SpeechMicDiagnostic::SmdTraceProvider::CreateInstance::Stop(
      (SpeechMicDiagnostic::SmdTraceProvider::CreateInstance *)v6,
      (RTL_SRWLOCK *)v5);
    v3 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4C,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\speechmicdiagnostic.cpp",
      (const char *)(unsigned int)v2,
      (int)v5);
  }
  v6[0] = &SpeechMicDiagnostic::SmdTraceProvider::CreateInstance::`vftable';
  wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v6);
  wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v6);
  return v3;
}

```

## disassembly

```asm
0x180007e38  mov     [rsp+arg_0], rbx
0x180007e3d  push    rdi
0x180007e3e  sub     rsp, 190h
0x180007e45  mov     rax, cs:__security_cookie
0x180007e4c  xor     rax, rsp
0x180007e4f  mov     [rsp+198h+var_18], rax
0x180007e57  lea     rdx, aCreateinstance; "CreateInstance"
0x180007e5e  lea     rcx, [rsp+198h+var_168]
0x180007e63  call    ??0?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180007e68  lea     rdi, ??_7CreateInstance@SmdTraceProvider@SpeechMicDiagnostic@@6B@; const SpeechMicDiagnostic::SmdTraceProvider::CreateInstance::`vftable'
0x180007e6f  mov     [rsp+198h+var_168], rdi
0x180007e74  lea     rdx, ?g_pSpeechDiagnostic@@3PEAUISpeechMicDiagnostic@SpeechMicDiagnostic@@EA; void *
0x180007e7b  lea     rcx, [rsp+198h+var_168]; this
0x180007e80  call    ?StartActivity@CreateInstance@SmdTraceProvider@SpeechMicDiagnostic@@QEAAXPEAX@Z; SpeechMicDiagnostic::SmdTraceProvider::CreateInstance::StartActivity(void *)
0x180007e85  nop
0x180007e86  mov     [rsp+198h+var_178], 0; int
0x180007e8f  lea     rcx, [rsp+198h+var_178]; struct SpeechMicDiagnostic::CSpeechMicDiagnostic **
0x180007e94  call    ?CreateInstance@CSpeechMicDiagnostic@SpeechMicDiagnostic@@SAJPEAPEAV12@@Z; SpeechMicDiagnostic::CSpeechMicDiagnostic::CreateInstance(SpeechMicDiagnostic::CSpeechMicDiagnostic * *)
0x180007e99  mov     ebx, eax
0x180007e9b  test    eax, eax
0x180007e9d  jns     short loc_180007EBD
0x180007e9f  mov     rcx, [rsp+198h]; this
0x180007ea7  mov     r9d, eax; char *
0x180007eaa  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x180007eb1  mov     edx, 4Ch ; 'L'; void *
0x180007eb6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007ebb  jmp     short loc_180007ED5
0x180007ebd  mov     rdx, [rsp+198h+var_178]; void *
0x180007ec2  mov     cs:?g_pSpeechDiagnostic@@3PEAUISpeechMicDiagnostic@SpeechMicDiagnostic@@EA, rdx; SpeechMicDiagnostic::ISpeechMicDiagnostic * g_pSpeechDiagnostic
0x180007ec9  lea     rcx, [rsp+198h+var_168]; this
0x180007ece  call    ?Stop@CreateInstance@SmdTraceProvider@SpeechMicDiagnostic@@QEAAXPEAX@Z; SpeechMicDiagnostic::SmdTraceProvider::CreateInstance::Stop(void *)
0x180007ed3  xor     ebx, ebx
0x180007ed5  mov     [rsp+198h+var_168], rdi
0x180007eda  lea     rcx, [rsp+198h+var_168]
0x180007edf  call    ?Destroy@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180007ee4  lea     rcx, [rsp+198h+var_168]
0x180007ee9  call    ??1?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180007eee  mov     eax, ebx
0x180007ef0  mov     rcx, [rsp+198h+var_18]
0x180007ef8  xor     rcx, rsp; StackCookie
0x180007efb  call    __security_check_cookie
0x180007f00  mov     rbx, [rsp+198h+arg_0]
0x180007f08  add     rsp, 190h
0x180007f0f  pop     rdi
0x180007f10  retn
```
