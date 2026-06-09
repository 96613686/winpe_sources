# SpeechMicDiagnostic::CSpeechMicDiagnostic::UpdateRegistryValues(int)

- ea: `0x18000d2a0`
- end: `0x18000d3cd`
- name: `?UpdateRegistryValues@CSpeechMicDiagnostic@SpeechMicDiagnostic@@UEAAJH@Z`
- size: `301`
- prototype: `__int64 __fastcall(SpeechMicDiagnostic::CSpeechMicDiagnostic *__hidden this, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180002910`
- `0x180005b28`
- `0x18000744c`
- `0x180007510`
- `0x180007f18`
- `0x18000a868`
- `0x18000d2a0`
- `0x18000d3f8`

## string_xrefs

- `0x18000d2c9`: `UpdateRegistryValues`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SpeechMicDiagnostic::CSpeechMicDiagnostic::UpdateRegistryValues(
        SpeechMicDiagnostic::CSpeechMicDiagnostic *this,
        int a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  unsigned __int64 v6; // r9
  __int64 v7; // rdx
  __int64 v8; // rax
  int v9; // eax
  int v11[84]; // [rsp+20h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v11,
    "UpdateRegistryValues");
  *(_QWORD *)v11 = &SpeechMicDiagnostic::SmdTraceProvider::UpdateRegistryValues::`vftable';
  SpeechMicDiagnostic::SmdTraceProvider::UpdateRegistryValues::StartActivity(
    (SpeechMicDiagnostic::SmdTraceProvider::UpdateRegistryValues *)v11,
    a2 != 0);
  if ( !a2 )
  {
    v8 = *((_QWORD *)this + 2);
    if ( v8 )
    {
      v5 = -2147188734;
      if ( *(_DWORD *)(v8 + 12) == -2147188734 )
      {
        v7 = 321;
      }
      else
      {
        if ( *(int *)(v8 + 12) >= 0 )
        {
          v9 = SpeechMicDiagnostic::CSpeechMicDiagnostic::WriteRegistry(this, *(double *)v8, *(_DWORD *)(v8 + 8));
          v5 = v9;
          if ( v9 < 0 )
          {
            v6 = (unsigned int)v9;
            v7 = 327;
            goto LABEL_7;
          }
LABEL_14:
          v5 = 0;
          goto LABEL_15;
        }
        v5 = -2147188733;
        v7 = 322;
      }
    }
    else
    {
      v5 = -2147188735;
      v7 = 317;
    }
    v6 = v5;
    goto LABEL_7;
  }
  v4 = SpeechMicDiagnostic::CSpeechMicDiagnostic::WriteRegistry(this, 0.0, 0x2711u);
  v5 = v4;
  if ( v4 >= 0 )
    goto LABEL_14;
  v6 = (unsigned int)v4;
  v7 = 313;
LABEL_7:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\speechmicdiagnostic.cpp",
    (const char *)v6,
    v11[0]);
LABEL_15:
  *(_QWORD *)v11 = &SpeechMicDiagnostic::SmdTraceProvider::UpdateRegistryValues::`vftable';
  wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v11);
  wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v11);
  return v5;
}

```

## disassembly

```asm
0x18000d2a0  mov     [rsp+arg_8], rbx
0x18000d2a5  mov     [rsp+arg_10], rsi
0x18000d2aa  push    rdi
0x18000d2ab  sub     rsp, 180h
0x18000d2b2  mov     rax, cs:__security_cookie
0x18000d2b9  xor     rax, rsp
0x18000d2bc  mov     [rsp+188h+var_18], rax
0x18000d2c4  mov     ebx, edx
0x18000d2c6  mov     rdi, rcx
0x18000d2c9  lea     rdx, aUpdateregistry_0; "UpdateRegistryValues"
0x18000d2d0  lea     rcx, [rsp+188h+var_168]
0x18000d2d5  call    ??0?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000d2da  lea     rsi, ??_7UpdateRegistryValues@SmdTraceProvider@SpeechMicDiagnostic@@6B@; const SpeechMicDiagnostic::SmdTraceProvider::UpdateRegistryValues::`vftable'
0x18000d2e1  mov     qword ptr [rsp+188h+var_168], rsi; int
0x18000d2e6  test    ebx, ebx
0x18000d2e8  setnz   dl; bool
0x18000d2eb  lea     rcx, [rsp+188h+var_168]; this
0x18000d2f0  call    ?StartActivity@UpdateRegistryValues@SmdTraceProvider@SpeechMicDiagnostic@@QEAAX_N@Z; SpeechMicDiagnostic::SmdTraceProvider::UpdateRegistryValues::StartActivity(bool)
0x18000d2f5  nop
0x18000d2f6  test    ebx, ebx
0x18000d2f8  jz      short loc_18000D31B
0x18000d2fa  mov     r8d, 2711h; unsigned int
0x18000d300  xorps   xmm1, xmm1; double
0x18000d303  mov     rcx, rdi; this
0x18000d306  call    ?WriteRegistry@CSpeechMicDiagnostic@SpeechMicDiagnostic@@QEAAJNK@Z; SpeechMicDiagnostic::CSpeechMicDiagnostic::WriteRegistry(double,ulong)
0x18000d30b  mov     ebx, eax
0x18000d30d  test    eax, eax
0x18000d30f  jns     short loc_18000D38A
0x18000d311  mov     r9d, eax
0x18000d314  mov     edx, 139h
0x18000d319  jmp     short loc_18000D331
0x18000d31b  mov     rax, [rdi+10h]
0x18000d31f  test    rax, rax
0x18000d322  jnz     short loc_18000D347
0x18000d324  mov     ebx, 80048001h
0x18000d329  mov     edx, 13Dh; void *
0x18000d32e  mov     r9d, ebx; char *
0x18000d331  mov     rcx, [rsp+188h]; this
0x18000d339  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x18000d340  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d345  jmp     short loc_18000D38C
0x18000d347  mov     ebx, 80048002h
0x18000d34c  cmp     [rax+0Ch], ebx
0x18000d34f  jnz     short loc_18000D358
0x18000d351  mov     edx, 141h
0x18000d356  jmp     short loc_18000D32E
0x18000d358  cmp     dword ptr [rax+0Ch], 0
0x18000d35c  jge     short loc_18000D36A
0x18000d35e  mov     ebx, 80048003h
0x18000d363  mov     edx, 142h
0x18000d368  jmp     short loc_18000D32E
0x18000d36a  mov     r8d, [rax+8]; unsigned int
0x18000d36e  movsd   xmm1, qword ptr [rax]; double
0x18000d372  mov     rcx, rdi; this
0x18000d375  call    ?WriteRegistry@CSpeechMicDiagnostic@SpeechMicDiagnostic@@QEAAJNK@Z; SpeechMicDiagnostic::CSpeechMicDiagnostic::WriteRegistry(double,ulong)
0x18000d37a  mov     ebx, eax
0x18000d37c  test    eax, eax
0x18000d37e  jns     short loc_18000D38A
0x18000d380  mov     r9d, eax
0x18000d383  mov     edx, 147h
0x18000d388  jmp     short loc_18000D331
0x18000d38a  xor     ebx, ebx
0x18000d38c  mov     qword ptr [rsp+188h+var_168], rsi
0x18000d391  lea     rcx, [rsp+188h+var_168]
0x18000d396  call    ?Destroy@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000d39b  lea     rcx, [rsp+188h+var_168]
0x18000d3a0  call    ??1?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000d3a5  mov     eax, ebx
0x18000d3a7  mov     rcx, [rsp+188h+var_18]
0x18000d3af  xor     rcx, rsp; StackCookie
0x18000d3b2  call    __security_check_cookie
0x18000d3b7  lea     r11, [rsp+188h+var_8]
0x18000d3bf  mov     rbx, [r11+18h]
0x18000d3c3  mov     rsi, [r11+20h]
0x18000d3c7  mov     rsp, r11
0x18000d3ca  pop     rdi
0x18000d3cb  retn
```
