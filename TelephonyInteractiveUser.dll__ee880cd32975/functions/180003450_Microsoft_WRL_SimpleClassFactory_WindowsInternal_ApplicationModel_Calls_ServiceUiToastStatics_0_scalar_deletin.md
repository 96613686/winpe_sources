# Microsoft::WRL::SimpleClassFactory<WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics,0>::`scalar deleting destructor'(uint)

- ea: `0x180003450`
- end: `0x180003478`
- name: `??_G?$SimpleClassFactory@VServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@$0A@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800021b4`
- `0x180003450`

## pseudocode

```c
_DWORD *__fastcall Microsoft::WRL::SimpleClassFactory<WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics,0>::`scalar deleting destructor'(
        _DWORD *a1,
        char a2)
{
  a1[3] = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180003450  push    rbx
0x180003452  sub     rsp, 20h
0x180003456  mov     dword ptr [rcx+0Ch], 0C0000001h
0x18000345d  mov     rbx, rcx
0x180003460  test    dl, 1
0x180003463  jz      short loc_18000346F
0x180003465  mov     edx, 18h
0x18000346a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000346f  mov     rax, rbx
0x180003472  add     rsp, 20h
0x180003476  pop     rbx
0x180003477  retn
```
