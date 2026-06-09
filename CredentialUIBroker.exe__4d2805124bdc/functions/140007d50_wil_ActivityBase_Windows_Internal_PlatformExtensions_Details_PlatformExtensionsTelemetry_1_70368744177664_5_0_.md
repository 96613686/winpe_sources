# wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)

- ea: `0x140007d50`
- end: `0x140007e06`
- name: `??0?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z`
- size: `182`
- prototype: `struct wil::details::IFailureCallback *__fastcall(struct wil::details::IFailureCallback *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140016a54`

## callees

- `0x1400042c4`
- `0x1400084c8`

## string_xrefs

- `0x140007d81`: `TryActivateContractExtension`

## pseudocode

```c
struct wil::details::IFailureCallback *__fastcall wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(
        struct wil::details::IFailureCallback *a1)
{
  char *v1; // rbx
  _QWORD *v3; // rcx

  v1 = (char *)a1 + 8;
  *(_QWORD *)a1 = &wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::`vftable';
  *((_DWORD *)a1 + 2) = 0;
  v3 = (_QWORD *)((char *)a1 + 88);
  v1[4] = 0;
  *((_QWORD *)v1 + 6) = "TryActivateContractExtension";
  v1[64] = 0;
  *((_DWORD *)v1 + 10) = 0;
  *((_QWORD *)v1 + 7) = 0;
  *((_DWORD *)v1 + 18) = 0;
  v3[19] = 0;
  v3[20] = 0;
  memset_0(v3, 0, 0x98u);
  *((_DWORD *)v1 + 62) = 1;
  *((_QWORD *)v1 + 32) = 0;
  *((_QWORD *)a1 + 34) = v1;
  *((_QWORD *)a1 + 35) = 0;
  wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
    (struct wil::details::IFailureCallback *)((char *)a1 + 288),
    a1,
    (struct wil::details::IFailureCallback *)((char *)a1 + 48),
    0);
  return a1;
}

```

## disassembly

```asm
0x140007d50  mov     [rsp+arg_0], rbx
0x140007d55  push    rdi
0x140007d56  sub     rsp, 20h
0x140007d5a  lea     rbx, [rcx+8]
0x140007d5e  mov     rdi, rcx
0x140007d61  lea     rax, ??_7?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@6B@; const wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::`vftable'
0x140007d68  xor     edx, edx; Val
0x140007d6a  mov     [rcx], rax
0x140007d6d  mov     r8d, 98h; Size
0x140007d73  mov     dword ptr [rbx], 0
0x140007d79  lea     rcx, [rbx+50h]; void *
0x140007d7d  mov     byte ptr [rbx+4], 0
0x140007d81  lea     rax, aTryactivatecon; "TryActivateContractExtension"
0x140007d88  mov     [rbx+30h], rax
0x140007d8c  mov     byte ptr [rbx+40h], 0
0x140007d90  mov     dword ptr [rbx+28h], 0
0x140007d97  mov     qword ptr [rbx+38h], 0
0x140007d9f  mov     dword ptr [rbx+48h], 0
0x140007da6  mov     qword ptr [rcx+98h], 0
0x140007db1  mov     qword ptr [rcx+0A0h], 0
0x140007dbc  call    memset_0
0x140007dc1  mov     dword ptr [rbx+0F8h], 1
0x140007dcb  lea     r8, [rdi+30h]; struct wil::CallContextInfo *
0x140007dcf  xor     eax, eax
0x140007dd1  lea     rcx, [rdi+120h]; this
0x140007dd8  mov     [rbx+100h], rax
0x140007ddf  xor     r9d, r9d; bool
0x140007de2  mov     [rdi+110h], rbx
0x140007de9  mov     rdx, rdi; struct wil::details::IFailureCallback *
0x140007dec  mov     [rdi+118h], rax
0x140007df3  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x140007df8  mov     rbx, [rsp+28h+arg_0]
0x140007dfd  mov     rax, rdi
0x140007e00  add     rsp, 20h
0x140007e04  pop     rdi
0x140007e05  retn
```
