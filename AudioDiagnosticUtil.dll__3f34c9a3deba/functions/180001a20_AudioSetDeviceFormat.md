# AudioSetDeviceFormat

- ea: `0x180001a20`
- end: `0x180001ab5`
- name: `AudioSetDeviceFormat`
- size: `149`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001a20`
- `0x180003010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180001a59`
- `ole32!CoCreateInstance` at `0x180001a59`
- `ole32!CoUninitialize` at `0x180001a87`
- `ole32!CoUninitialize` at `0x180001a87`

## pseudocode

```c
__int64 __fastcall AudioSetDeviceFormat(__int64 a1, __int64 a2, __int64 a3)
{
  HRESULT v6; // ebx
  LPVOID ppv; // [rsp+78h] [rbp+20h] BYREF

  ppv = 0;
  v6 = CoCreateInstance(
         &GUID_870af99c_171d_4f9e_af0d_e63df40c2bc9,
         0,
         0x17u,
         &GUID_e8478600_a74b_4b3a_a96b_1fc3e796fc46,
         &ppv);
  if ( v6 >= 0 )
    v6 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64, __int64))(*(_QWORD *)ppv + 48LL))(ppv, a1, a2, a3);
  CoUninitialize();
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180001a20  push    rbx
0x180001a22  push    rbp
0x180001a23  push    rsi
0x180001a24  push    rdi
0x180001a25  sub     rsp, 38h
0x180001a29  mov     rsi, rdx
0x180001a2c  mov     [rsp+58h+arg_18], 0
0x180001a35  xor     edx, edx; pUnkOuter
0x180001a37  lea     rax, [rsp+58h+arg_18]
0x180001a3c  mov     rdi, r8
0x180001a3f  mov     [rsp+58h+ppv], rax; ppv
0x180001a44  mov     rbp, rcx
0x180001a47  lea     r9, _GUID_e8478600_a74b_4b3a_a96b_1fc3e796fc46; riid
0x180001a4e  lea     rcx, _GUID_870af99c_171d_4f9e_af0d_e63df40c2bc9; rclsid
0x180001a55  lea     r8d, [rdx+17h]; dwClsContext
0x180001a59  call    cs:__imp_CoCreateInstance
0x180001a60  nop     dword ptr [rax+rax+00h]
0x180001a65  mov     ebx, eax
0x180001a67  test    eax, eax
0x180001a69  js      short loc_180001A87
0x180001a6b  mov     rcx, [rsp+58h+arg_18]
0x180001a70  mov     r9, rdi
0x180001a73  mov     r8, rsi
0x180001a76  mov     rdx, rbp
0x180001a79  mov     rax, [rcx]
0x180001a7c  mov     rax, [rax+30h]
0x180001a80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a85  mov     ebx, eax
0x180001a87  call    cs:__imp_CoUninitialize
0x180001a8e  nop     dword ptr [rax+rax+00h]
0x180001a93  mov     rcx, [rsp+58h+arg_18]
0x180001a98  test    rcx, rcx
0x180001a9b  jz      short loc_180001AA9
0x180001a9d  mov     rax, [rcx]
0x180001aa0  mov     rax, [rax+10h]
0x180001aa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001aa9  mov     eax, ebx
0x180001aab  add     rsp, 38h
0x180001aaf  pop     rdi
0x180001ab0  pop     rsi
0x180001ab1  pop     rbp
0x180001ab2  pop     rbx
0x180001ab3  retn
```
