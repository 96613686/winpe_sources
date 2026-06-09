# wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)

- ea: `0x18000c5e0`
- end: `0x18000c660`
- name: `??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z`
- size: `128`
- prototype: `__int64 __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this, struct wil::details::IFailureCallback *, struct wil::CallContextInfo *, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000be08`

## callees

- `0x18000c5e0`
- `0x1800114d8`

## pseudocode

```c
wil::details::ThreadFailureCallbackHolder *__fastcall wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
        wil::details::ThreadFailureCallbackHolder *this,
        struct wil::details::IFailureCallback *a2,
        struct wil::CallContextInfo *a3,
        char a4)
{
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = a2;
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 4) = a3;
  *((_BYTE *)this + 40) = 0;
  if ( a4 )
    wil::details::ThreadFailureCallbackHolder::StartWatching(this, a2);
  return this;
}

```

## disassembly

```asm
0x18000c5e0  mov     [rsp+arg_18], r9b
0x18000c5e5  mov     [rsp+arg_10], r8
0x18000c5ea  mov     [rsp+arg_8], rdx
0x18000c5ef  mov     [rsp+arg_0], rcx
0x18000c5f4  sub     rsp, 28h
0x18000c5f8  mov     rax, [rsp+28h+arg_0]
0x18000c5fd  mov     qword ptr [rax], 0
0x18000c604  mov     rax, [rsp+28h+arg_0]
0x18000c609  mov     rcx, [rsp+28h+arg_8]
0x18000c60e  mov     [rax+8], rcx
0x18000c612  mov     rax, [rsp+28h+arg_0]
0x18000c617  mov     qword ptr [rax+10h], 0
0x18000c61f  mov     rax, [rsp+28h+arg_0]
0x18000c624  mov     dword ptr [rax+18h], 0
0x18000c62b  mov     rax, [rsp+28h+arg_0]
0x18000c630  mov     rcx, [rsp+28h+arg_10]
0x18000c635  mov     [rax+20h], rcx
0x18000c639  mov     rax, [rsp+28h+arg_0]
0x18000c63e  mov     byte ptr [rax+28h], 0
0x18000c642  movzx   eax, [rsp+28h+arg_18]
0x18000c647  test    eax, eax
0x18000c649  jz      short loc_18000C656
0x18000c64b  mov     rcx, [rsp+28h+arg_0]; this
0x18000c650  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18000c655  nop
0x18000c656  mov     rax, [rsp+28h+arg_0]
0x18000c65b  add     rsp, 28h
0x18000c65f  retn
```
