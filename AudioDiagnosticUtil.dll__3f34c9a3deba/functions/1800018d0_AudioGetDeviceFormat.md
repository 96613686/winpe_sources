# AudioGetDeviceFormat

- ea: `0x1800018d0`
- end: `0x180001965`
- name: `AudioGetDeviceFormat`
- size: `149`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800018d0`
- `0x180003010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180001909`
- `ole32!CoCreateInstance` at `0x180001909`
- `ole32!CoUninitialize` at `0x180001937`
- `ole32!CoUninitialize` at `0x180001937`

## pseudocode

```c
__int64 __fastcall AudioGetDeviceFormat(__int64 a1, unsigned __int8 a2, __int64 a3)
{
  unsigned int v3; // esi
  HRESULT v6; // ebx
  LPVOID ppv; // [rsp+78h] [rbp+20h] BYREF

  v3 = a2;
  ppv = 0;
  v6 = CoCreateInstance(
         &GUID_870af99c_171d_4f9e_af0d_e63df40c2bc9,
         0,
         0x17u,
         &GUID_e8478600_a74b_4b3a_a96b_1fc3e796fc46,
         &ppv);
  if ( v6 >= 0 )
    v6 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, __int64))(*(_QWORD *)ppv + 32LL))(ppv, a1, v3, a3);
  CoUninitialize();
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800018d0  push    rbx
0x1800018d2  push    rbp
0x1800018d3  push    rsi
0x1800018d4  push    rdi
0x1800018d5  sub     rsp, 38h
0x1800018d9  movzx   esi, dl
0x1800018dc  lea     rax, [rsp+58h+arg_18]
0x1800018e1  xor     edx, edx; pUnkOuter
0x1800018e3  mov     [rsp+58h+arg_18], 0
0x1800018ec  mov     rdi, r8
0x1800018ef  mov     [rsp+58h+ppv], rax; ppv
0x1800018f4  mov     rbp, rcx
0x1800018f7  lea     r9, _GUID_e8478600_a74b_4b3a_a96b_1fc3e796fc46; riid
0x1800018fe  lea     rcx, _GUID_870af99c_171d_4f9e_af0d_e63df40c2bc9; rclsid
0x180001905  lea     r8d, [rdx+17h]; dwClsContext
0x180001909  call    cs:__imp_CoCreateInstance
0x180001910  nop     dword ptr [rax+rax+00h]
0x180001915  mov     ebx, eax
0x180001917  test    eax, eax
0x180001919  js      short loc_180001937
0x18000191b  mov     rcx, [rsp+58h+arg_18]
0x180001920  mov     r8d, esi
0x180001923  mov     r9, rdi
0x180001926  mov     rdx, rbp
0x180001929  mov     rax, [rcx]
0x18000192c  mov     rax, [rax+20h]
0x180001930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001935  mov     ebx, eax
0x180001937  call    cs:__imp_CoUninitialize
0x18000193e  nop     dword ptr [rax+rax+00h]
0x180001943  mov     rcx, [rsp+58h+arg_18]
0x180001948  test    rcx, rcx
0x18000194b  jz      short loc_180001959
0x18000194d  mov     rax, [rcx]
0x180001950  mov     rax, [rax+10h]
0x180001954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001959  mov     eax, ebx
0x18000195b  add     rsp, 38h
0x18000195f  pop     rdi
0x180001960  pop     rsi
0x180001961  pop     rbp
0x180001962  pop     rbx
0x180001963  retn
```
