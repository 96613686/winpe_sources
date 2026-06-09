# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformation *>,Microsoft::WRL::FtmBase>::`scalar deleting destructor'(uint)

- ea: `0x1800049f0`
- end: `0x180004a48`
- name: `??_G?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVDeviceInformation@Enumeration@Devices@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1800049f0`
- `0x18000b010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180004a2d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004a2d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformation *>,Microsoft::WRL::FtmBase>::`scalar deleting destructor'(
        __int64 a1,
        char a2)
{
  __int64 v4; // rcx

  *(_DWORD *)(a1 + 44) = -1073741823;
  v4 = *(_QWORD *)(a1 + 32);
  if ( v4 )
  {
    *(_QWORD *)(a1 + 32) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  if ( (a2 & 1) != 0 )
    operator delete((void *)a1);
  return a1;
}

```

## disassembly

```asm
0x1800049f0  mov     [rsp+arg_0], rbx
0x1800049f5  push    rdi
0x1800049f6  sub     rsp, 20h
0x1800049fa  mov     edi, edx
0x1800049fc  mov     rbx, rcx
0x1800049ff  mov     dword ptr [rcx+2Ch], 0C0000001h
0x180004a06  mov     rcx, [rcx+20h]
0x180004a0a  test    rcx, rcx
0x180004a0d  jz      short loc_180004A24
0x180004a0f  mov     qword ptr [rbx+20h], 0
0x180004a17  mov     rax, [rcx]
0x180004a1a  mov     rax, [rax+10h]
0x180004a1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a23  nop
0x180004a24  test    dil, 1
0x180004a28  jz      short loc_180004A39
0x180004a2a  mov     rcx, rbx
0x180004a2d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004a34  nop     dword ptr [rax+rax+00h]
0x180004a39  mov     rax, rbx
0x180004a3c  mov     rbx, [rsp+28h+arg_0]
0x180004a41  add     rsp, 20h
0x180004a45  pop     rdi
0x180004a46  retn
```
