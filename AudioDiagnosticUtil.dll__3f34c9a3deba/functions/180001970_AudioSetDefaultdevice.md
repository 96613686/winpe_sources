# AudioSetDefaultdevice

- ea: `0x180001970`
- end: `0x180001a18`
- name: `AudioSetDefaultdevice`
- size: `168`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001970`
- `0x180003010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800019a3`
- `ole32!CoCreateInstance` at `0x1800019a3`
- `ole32!CoUninitialize` at `0x1800019e8`
- `ole32!CoUninitialize` at `0x1800019e8`

## pseudocode

```c
__int64 __fastcall AudioSetDefaultdevice(__int64 a1)
{
  HRESULT v2; // ebx
  LPVOID v4; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  v2 = CoCreateInstance(
         &GUID_870af99c_171d_4f9e_af0d_e63df40c2bc9,
         0,
         0x17u,
         &GUID_e8478600_a74b_4b3a_a96b_1fc3e796fc46,
         &v4);
  if ( v2 >= 0 )
  {
    (*(void (__fastcall **)(LPVOID, __int64, _QWORD))(*(_QWORD *)v4 + 104LL))(v4, a1, 0);
    v2 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v4 + 104LL))(v4, a1, 1);
  }
  CoUninitialize();
  if ( v4 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v4 + 16LL))(v4);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180001970  mov     r11, rsp
0x180001973  mov     [r11+8], rbx
0x180001977  push    rdi
0x180001978  sub     rsp, 30h
0x18000197c  xor     edx, edx; pUnkOuter
0x18000197e  mov     qword ptr [r11+10h], 0
0x180001986  mov     rdi, rcx
0x180001989  lea     rax, [r11+10h]
0x18000198d  lea     r9, _GUID_e8478600_a74b_4b3a_a96b_1fc3e796fc46; riid
0x180001994  mov     [r11-18h], rax
0x180001998  lea     rcx, _GUID_870af99c_171d_4f9e_af0d_e63df40c2bc9; rclsid
0x18000199f  lea     r8d, [rdx+17h]; dwClsContext
0x1800019a3  call    cs:__imp_CoCreateInstance
0x1800019aa  nop     dword ptr [rax+rax+00h]
0x1800019af  mov     ebx, eax
0x1800019b1  test    eax, eax
0x1800019b3  js      short loc_1800019E8
0x1800019b5  mov     rcx, [rsp+38h+arg_8]
0x1800019ba  xor     r8d, r8d
0x1800019bd  mov     rdx, rdi
0x1800019c0  mov     rax, [rcx]
0x1800019c3  mov     rax, [rax+68h]
0x1800019c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800019cc  mov     rcx, [rsp+38h+arg_8]
0x1800019d1  mov     r8d, 1
0x1800019d7  mov     rdx, rdi
0x1800019da  mov     rax, [rcx]
0x1800019dd  mov     rax, [rax+68h]
0x1800019e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800019e6  mov     ebx, eax
0x1800019e8  call    cs:__imp_CoUninitialize
0x1800019ef  nop     dword ptr [rax+rax+00h]
0x1800019f4  mov     rcx, [rsp+38h+arg_8]
0x1800019f9  test    rcx, rcx
0x1800019fc  jz      short loc_180001A0A
0x1800019fe  mov     rax, [rcx]
0x180001a01  mov     rax, [rax+10h]
0x180001a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a0a  mov     eax, ebx
0x180001a0c  mov     rbx, [rsp+38h+arg_0]
0x180001a11  add     rsp, 30h
0x180001a15  pop     rdi
0x180001a16  retn
```
