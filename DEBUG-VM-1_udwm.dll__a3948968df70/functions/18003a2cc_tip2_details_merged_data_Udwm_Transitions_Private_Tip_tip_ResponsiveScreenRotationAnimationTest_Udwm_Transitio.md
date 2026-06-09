# tip2::details::merged_data<Udwm::Transitions::Private::Tip::_tip_ResponsiveScreenRotationAnimationTest,Udwm::Transitions::Private::Tip::_tip_ResponsiveScreenRotationAnimationTest>::Release(void)

- ea: `0x18003a2cc`
- end: `0x18003a306`
- name: `?Release@?$merged_data@U_tip_ResponsiveScreenRotationAnimationTest@Tip@Private@Transitions@Udwm@@U12345@@details@tip2@@AEAAKXZ`
- size: `58`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `8`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800397d0`
- `0x180039d4c`
- `0x180039e34`
- `0x180039f3c`
- `0x18003a078`
- `0x18003a10c`
- `0x1800719fc`
- `0x18008cb58`

## callees

- `0x18003a2cc`
- `0x180092544`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a2fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a2fe`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<Udwm::Transitions::Private::Tip::_tip_ResponsiveScreenRotationAnimationTest,Udwm::Transitions::Private::Tip::_tip_ResponsiveScreenRotationAnimationTest>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 72);
  if ( !v2 )
  {
    tip2::details::merged_data<Udwm::Transitions::Private::Tip::_tip_ResponsiveScreenRotationAnimationTest,Udwm::Transitions::Private::Tip::_tip_ResponsiveScreenRotationAnimationTest>::~merged_data<Udwm::Transitions::Private::Tip::_tip_ResponsiveScreenRotationAnimationTest,Udwm::Transitions::Private::Tip::_tip_ResponsiveScreenRotationAnimationTest>();
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x18003a2cc  mov     [rsp+arg_0], rbx
0x18003a2d1  push    rdi
0x18003a2d2  sub     rsp, 20h
0x18003a2d6  mov     rdi, rcx
0x18003a2d9  or      ebx, 0FFFFFFFFh
0x18003a2dc  lock xadd [rcx+120h], ebx
0x18003a2e4  sub     ebx, 1
0x18003a2e7  jz      short loc_18003A2F6
0x18003a2e9  mov     eax, ebx
0x18003a2eb  mov     rbx, [rsp+28h+arg_0]
0x18003a2f0  add     rsp, 20h
0x18003a2f4  pop     rdi
0x18003a2f5  retn
0x18003a2f6  call    ??1?$merged_data@U_tip_ResponsiveScreenRotationAnimationTest@Tip@Private@Transitions@Udwm@@U12345@@details@tip2@@QEAA@XZ; tip2::details::merged_data<Udwm::Transitions::Private::Tip::_tip_ResponsiveScreenRotationAnimationTest,Udwm::Transitions::Private::Tip::_tip_ResponsiveScreenRotationAnimationTest>::~merged_data<Udwm::Transitions::Private::Tip::_tip_ResponsiveScreenRotationAnimationTest,Udwm::Transitions::Private::Tip::_tip_ResponsiveScreenRotationAnimationTest>(void)
0x18003a2fb  mov     rcx, rdi; pv
0x18003a2fe  call    cs:__imp_CoTaskMemFree
0x18003a304  jmp     short loc_18003A2E9
```
