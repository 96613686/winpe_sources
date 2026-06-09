# AudioSetEndPointVisibility

- ea: `0x180001ac0`
- end: `0x180001b5a`
- name: `AudioSetEndPointVisibility`
- size: `154`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001ac0`
- `0x180003010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180001afa`
- `ole32!CoCreateInstance` at `0x180001afa`
- `ole32!CoUninitialize` at `0x180001b25`
- `ole32!CoUninitialize` at `0x180001b25`

## pseudocode

```c
__int64 __fastcall AudioSetEndPointVisibility(__int64 a1, unsigned __int8 a2)
{
  unsigned int v2; // edi
  HRESULT v4; // ebx
  LPVOID v6; // [rsp+50h] [rbp+18h] BYREF

  v2 = a2;
  v6 = 0;
  v4 = CoCreateInstance(
         &GUID_870af99c_171d_4f9e_af0d_e63df40c2bc9,
         0,
         0x17u,
         &GUID_e8478600_a74b_4b3a_a96b_1fc3e796fc46,
         &v6);
  if ( v4 >= 0 )
    v4 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD))(*(_QWORD *)v6 + 112LL))(v6, a1, v2);
  CoUninitialize();
  if ( v6 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180001ac0  mov     r11, rsp
0x180001ac3  mov     [r11+8], rbx
0x180001ac7  mov     [r11+10h], rsi
0x180001acb  push    rdi
0x180001acc  sub     rsp, 30h
0x180001ad0  movzx   edi, dl
0x180001ad3  lea     rax, [r11+18h]
0x180001ad7  xor     edx, edx; pUnkOuter
0x180001ad9  mov     qword ptr [r11+18h], 0
0x180001ae1  mov     rsi, rcx
0x180001ae4  mov     [r11-18h], rax
0x180001ae8  lea     r9, _GUID_e8478600_a74b_4b3a_a96b_1fc3e796fc46; riid
0x180001aef  lea     rcx, _GUID_870af99c_171d_4f9e_af0d_e63df40c2bc9; rclsid
0x180001af6  lea     r8d, [rdx+17h]; dwClsContext
0x180001afa  call    cs:__imp_CoCreateInstance
0x180001b01  nop     dword ptr [rax+rax+00h]
0x180001b06  mov     ebx, eax
0x180001b08  test    eax, eax
0x180001b0a  js      short loc_180001B25
0x180001b0c  mov     rcx, [rsp+38h+arg_10]
0x180001b11  mov     r8d, edi
0x180001b14  mov     rdx, rsi
0x180001b17  mov     rax, [rcx]
0x180001b1a  mov     rax, [rax+70h]
0x180001b1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b23  mov     ebx, eax
0x180001b25  call    cs:__imp_CoUninitialize
0x180001b2c  nop     dword ptr [rax+rax+00h]
0x180001b31  mov     rcx, [rsp+38h+arg_10]
0x180001b36  test    rcx, rcx
0x180001b39  jz      short loc_180001B47
0x180001b3b  mov     rax, [rcx]
0x180001b3e  mov     rax, [rax+10h]
0x180001b42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b47  mov     rsi, [rsp+38h+arg_8]
0x180001b4c  mov     eax, ebx
0x180001b4e  mov     rbx, [rsp+38h+arg_0]
0x180001b53  add     rsp, 30h
0x180001b57  pop     rdi
0x180001b58  retn
```
