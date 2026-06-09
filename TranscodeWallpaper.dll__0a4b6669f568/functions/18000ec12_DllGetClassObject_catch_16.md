# DllGetClassObject$catch$16

- ea: `0x18000ec12`
- end: `0x18000ec3e`
- name: `DllGetClassObject$catch$16`
- size: `44`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000d4ac`

## pseudocode

```c
__int64 __fastcall DllGetClassObject_catch_16(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 48) = *winrt::to_hresult((_DWORD *)(a2 + 48));
  return 0;
}

```

## disassembly

```asm
0x18000ec12  mov     [rsp+arg_8], rdx
0x18000ec17  push    rbp
0x18000ec18  sub     rsp, 30h
0x18000ec1c  mov     rbp, rdx
0x18000ec1f  lea     rcx, [rbp+30h]
0x18000ec23  call    ?to_hresult@winrt@@YA?AUhresult@1@XZ; winrt::to_hresult(void)
0x18000ec28  mov     ecx, [rax]
0x18000ec2a  mov     [rbp+30h], ecx
0x18000ec2d  mov     rax, 0
0x18000ec37  add     rsp, 30h
0x18000ec3b  pop     rbp
0x18000ec3c  retn
```
