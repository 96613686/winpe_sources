# Microsoft::WRL::ComPtr<DockingInputManager>::Attach(DockingInputManager *)

- ea: `0x180013898`
- end: `0x1800138d4`
- name: `?Attach@?$ComPtr@VDockingInputManager@@@WRL@Microsoft@@QEAAXPEAVDockingInputManager@@@Z`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800130c8`

## callees

- `0x180013898`
- `0x180014050`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::ComPtr<DockingInputManager>::Attach(_QWORD *a1, __int64 a2)
{
  _QWORD *result; // rax

  if ( *a1 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDockingInputManager,Microsoft::WRL::FtmBase>::Release(*a1);
  result = a1;
  *a1 = a2;
  return result;
}

```

## disassembly

```asm
0x180013898  mov     [rsp+arg_8], rdx
0x18001389d  mov     [rsp+arg_0], rcx
0x1800138a2  sub     rsp, 38h
0x1800138a6  mov     rax, [rsp+38h+arg_0]
0x1800138ab  cmp     qword ptr [rax], 0
0x1800138af  jz      short loc_1800138C2
0x1800138b1  mov     rax, [rsp+38h+arg_0]
0x1800138b6  mov     rcx, [rax]
0x1800138b9  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIDockingInputManager@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDockingInputManager,Microsoft::WRL::FtmBase>::Release(void)
0x1800138be  mov     [rsp+38h+var_18], eax
0x1800138c2  mov     rax, [rsp+38h+arg_0]
0x1800138c7  mov     rcx, [rsp+38h+arg_8]
0x1800138cc  mov     [rax], rcx
0x1800138cf  add     rsp, 38h
0x1800138d3  retn
```
