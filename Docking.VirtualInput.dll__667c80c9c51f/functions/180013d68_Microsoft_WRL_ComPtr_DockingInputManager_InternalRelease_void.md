# Microsoft::WRL::ComPtr<DockingInputManager>::InternalRelease(void)

- ea: `0x180013d68`
- end: `0x180013db1`
- name: `?InternalRelease@?$ComPtr@VDockingInputManager@@@WRL@Microsoft@@IEAAKXZ`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180013450`

## callees

- `0x180013d68`
- `0x180014050`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<DockingInputManager>::InternalRelease(__int64 *a1)
{
  unsigned int v2; // [rsp+20h] [rbp-18h]
  __int64 v3; // [rsp+28h] [rbp-10h]

  v2 = 0;
  v3 = *a1;
  if ( *a1 )
  {
    *a1 = 0;
    return (unsigned int)Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDockingInputManager,Microsoft::WRL::FtmBase>::Release(v3);
  }
  return v2;
}

```

## disassembly

```asm
0x180013d68  mov     [rsp+arg_0], rcx
0x180013d6d  sub     rsp, 38h
0x180013d71  mov     [rsp+38h+var_18], 0
0x180013d79  mov     rax, [rsp+38h+arg_0]
0x180013d7e  mov     rax, [rax]
0x180013d81  mov     [rsp+38h+var_10], rax
0x180013d86  cmp     [rsp+38h+var_10], 0
0x180013d8c  jz      short loc_180013DA8
0x180013d8e  mov     rax, [rsp+38h+arg_0]
0x180013d93  mov     qword ptr [rax], 0
0x180013d9a  mov     rcx, [rsp+38h+var_10]
0x180013d9f  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIDockingInputManager@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDockingInputManager,Microsoft::WRL::FtmBase>::Release(void)
0x180013da4  mov     [rsp+38h+var_18], eax
0x180013da8  mov     eax, [rsp+38h+var_18]
0x180013dac  add     rsp, 38h
0x180013db0  retn
```
