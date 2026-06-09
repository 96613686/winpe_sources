# Microsoft::WRL::ComPtr<RfbFileDialogEvents>::~ComPtr<RfbFileDialogEvents>(void)

- ea: `0x18000b2a0`
- end: `0x18000b2c0`
- name: `??1?$ComPtr@VRfbFileDialogEvents@@@WRL@Microsoft@@QEAA@XZ`
- size: `32`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180017c4f`

## callees

- `0x18000b2a0`
- `0x18000b4a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::ComPtr<RfbFileDialogEvents>::~ComPtr<RfbFileDialogEvents>(__int64 *a1)
{
  __int64 result; // rax

  result = *a1;
  if ( *a1 )
  {
    *a1 = 0;
    return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IFileDialogEvents>::Release(result);
  }
  return result;
}

```

## disassembly

```asm
0x18000b2a0  sub     rsp, 28h
0x18000b2a4  mov     rax, [rcx]
0x18000b2a7  test    rax, rax
0x18000b2aa  jz      short loc_18000B2BB
0x18000b2ac  mov     qword ptr [rcx], 0
0x18000b2b3  mov     rcx, rax
0x18000b2b6  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIFileDialogEvents@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IFileDialogEvents>::Release(void)
0x18000b2bb  add     rsp, 28h
0x18000b2bf  retn
```
