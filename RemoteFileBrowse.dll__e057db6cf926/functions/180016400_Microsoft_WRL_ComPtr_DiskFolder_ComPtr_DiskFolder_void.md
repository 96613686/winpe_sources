# Microsoft::WRL::ComPtr<DiskFolder>::~ComPtr<DiskFolder>(void)

- ea: `0x180016400`
- end: `0x180016420`
- name: `??1?$ComPtr@VDiskFolder@@@WRL@Microsoft@@QEAA@XZ`
- size: `32`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180018b5b`

## callees

- `0x180006f70`
- `0x180016400`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::ComPtr<DiskFolder>::~ComPtr<DiskFolder>(__int64 *a1)
{
  __int64 result; // rax

  result = *a1;
  if ( *a1 )
  {
    *a1 = 0;
    return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::MixIn<DiskFolder,RfbShellFolderBase,1>,IResolveShellLink>::Release(result);
  }
  return result;
}

```

## disassembly

```asm
0x180016400  sub     rsp, 28h
0x180016404  mov     rax, [rcx]
0x180016407  test    rax, rax
0x18001640a  jz      short loc_18001641B
0x18001640c  mov     qword ptr [rcx], 0
0x180016413  mov     rcx, rax
0x180016416  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$MixIn@VDiskFolder@@VRfbShellFolderBase@@$00@23@UIResolveShellLink@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::MixIn<DiskFolder,RfbShellFolderBase,1>,IResolveShellLink>::Release(void)
0x18001641b  add     rsp, 28h
0x18001641f  retn
```
