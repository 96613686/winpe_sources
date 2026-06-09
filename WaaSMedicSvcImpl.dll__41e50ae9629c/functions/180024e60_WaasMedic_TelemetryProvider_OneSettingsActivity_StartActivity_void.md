# WaasMedic::TelemetryProvider::OneSettingsActivity::StartActivity(void)

- ea: `0x180024e60`
- end: `0x180024fb6`
- name: `?StartActivity@OneSettingsActivity@TelemetryProvider@WaasMedic@@QEAAXXZ`
- size: `342`
- prototype: `void __fastcall(WaasMedic::TelemetryProvider::OneSettingsActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x180024bbc`

## callees

- `0x180001718`
- `0x1800050a0`
- `0x18000acc0`
- `0x18000d04c`
- `0x18001df78`
- `0x180024e60`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024ec5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024f83`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024ec5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024f83`

## pseudocode

```c
void __fastcall WaasMedic::TelemetryProvider::OneSettingsActivity::StartActivity(
        WaasMedic::TelemetryProvider::OneSettingsActivity *this)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // rdi
  __int64 v5; // r8
  char *v6; // rbx
  _QWORD *Local; // rax
  DWORD CurrentThreadId; // [rsp+30h] [rbp-68h] BYREF
  _QWORD v9[9]; // [rsp+38h] [rbp-60h] BYREF

  wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(this);
  v4 = *((_QWORD *)WaasMedic::TelemetryProvider::Instance() + 1);
  if ( *(_DWORD *)v4 > 5u )
  {
    v3 = *(_QWORD *)(v4 + 24);
    v2 = 0x400000000000LL;
    if ( (*(_QWORD *)(v4 + 16) & 0x400000000000LL) != 0 && (v3 & 0x400000000000LL) == v3 )
    {
      CurrentThreadId = GetCurrentThreadId();
      v9[0] = 0x1000000;
      v5 = *((_QWORD *)this + 34);
      v9[7] = &CurrentThreadId;
      v9[8] = 4;
      v9[5] = v9;
      v9[6] = 8;
      tlgWriteTransfer_EventWriteTransfer(v4, &unk_180092B1A, v5 + 8);
    }
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v6 = (char *)this + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      LOBYTE(v2) = 1;
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v3,
                          v2);
      *(_QWORD *)v6 = Local;
      if ( Local )
      {
        *((_QWORD *)v6 + 2) = *Local;
        *Local = v6;
        *((_DWORD *)v6 + 6) = GetCurrentThreadId();
      }
    }
    else
    {
      *(_QWORD *)v6 = 0;
    }
  }
}

```

## disassembly

```asm
0x180024e60  mov     [rsp+arg_8], rbx
0x180024e65  push    rdi
0x180024e66  sub     rsp, 90h
0x180024e6d  mov     rax, cs:__security_cookie
0x180024e74  xor     rax, rsp
0x180024e77  mov     [rsp+98h+var_18], rax
0x180024e7f  mov     rbx, rcx
0x180024e82  call    ?zInternalStart@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180024e87  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x180024e8c  mov     rdi, [rax+8]
0x180024e90  mov     eax, [rdi]
0x180024e92  cmp     eax, 5
0x180024e95  jbe     loc_180024F50
0x180024e9b  mov     rcx, [rdi+18h]
0x180024e9f  mov     rax, [rdi+10h]
0x180024ea3  mov     rdx, 400000000000h
0x180024ead  test    rdx, rax
0x180024eb0  jz      loc_180024F50
0x180024eb6  mov     rax, rcx
0x180024eb9  and     rax, rdx
0x180024ebc  cmp     rax, rcx
0x180024ebf  jnz     loc_180024F50
0x180024ec5  call    cs:__imp_GetCurrentThreadId
0x180024ecb  mov     [rsp+98h+var_68], eax
0x180024ecf  mov     [rsp+98h+var_60], 1000000h
0x180024ed8  mov     r8, [rbx+110h]
0x180024edf  cmp     byte ptr [r8+4], 0
0x180024ee4  jz      short loc_180024F05
0x180024ee6  lea     r9, [r8+18h]
0x180024eea  cmp     dword ptr [r9], 0
0x180024eee  jnz     short loc_180024F08
0x180024ef0  cmp     dword ptr [r9+4], 0
0x180024ef5  jnz     short loc_180024F08
0x180024ef7  cmp     dword ptr [r9+8], 0
0x180024efc  jnz     short loc_180024F08
0x180024efe  cmp     dword ptr [r9+0Ch], 0
0x180024f03  jnz     short loc_180024F08
0x180024f05  xor     r9d, r9d
0x180024f08  lea     rax, [rsp+98h+var_68]
0x180024f0d  mov     [rsp+98h+var_28], rax
0x180024f12  mov     ecx, 4
0x180024f17  mov     [rsp+98h+var_20], rcx
0x180024f1c  lea     rax, [rsp+98h+var_60]
0x180024f21  mov     [rsp+98h+var_38], rax
0x180024f26  mov     [rsp+98h+var_30], 8
0x180024f2f  add     r8, 8
0x180024f33  lea     rax, [rsp+98h+var_58]
0x180024f38  mov     [rsp+98h+var_70], rax
0x180024f3d  mov     [rsp+98h+var_78], ecx
0x180024f41  lea     rdx, unk_180092B1A
0x180024f48  mov     rcx, rdi
0x180024f4b  call    _tlgWriteTransfer_EventWriteTransfer
0x180024f50  cmp     dword ptr [rbx+138h], 0
0x180024f57  jnz     short loc_180024F95
0x180024f59  add     rbx, 120h
0x180024f60  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180024f68  jz      short loc_180024F8E
0x180024f6a  mov     dl, 1
0x180024f6c  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180024f71  mov     [rbx], rax
0x180024f74  test    rax, rax
0x180024f77  jz      short loc_180024F95
0x180024f79  mov     rcx, [rax]
0x180024f7c  mov     [rbx+10h], rcx
0x180024f80  mov     [rax], rbx
0x180024f83  call    cs:__imp_GetCurrentThreadId
0x180024f89  mov     [rbx+18h], eax
0x180024f8c  jmp     short loc_180024F95
0x180024f8e  mov     qword ptr [rbx], 0
0x180024f95  mov     rcx, [rsp+98h+var_18]
0x180024f9d  xor     rcx, rsp; StackCookie
0x180024fa0  call    __security_check_cookie
0x180024fa5  mov     rbx, [rsp+98h+arg_8]
0x180024fad  add     rsp, 90h
0x180024fb4  pop     rdi
0x180024fb5  retn
```
