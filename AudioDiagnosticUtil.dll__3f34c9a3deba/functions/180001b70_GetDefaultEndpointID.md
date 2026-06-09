# GetDefaultEndpointID

- ea: `0x180001b70`
- end: `0x180001c66`
- name: `GetDefaultEndpointID`
- size: `246`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001eb0`

## callees

- `0x180001b70`
- `0x180003010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180001ba2`
- `msvcrt!_wcsicmp` at `0x180001ba2`
- `ole32!CoCreateInstance` at `0x180001bd4`
- `ole32!CoCreateInstance` at `0x180001bd4`

## pseudocode

```c
__int64 __fastcall GetDefaultEndpointID(const wchar_t *a1, _QWORD *a2)
{
  BOOL v3; // esi
  HRESULT v4; // ebx
  _QWORD v6[3]; // [rsp+30h] [rbp-18h] BYREF
  __int64 v7; // [rsp+60h] [rbp+18h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp+20h] BYREF

  ppv = 0;
  v7 = 0;
  v6[0] = 0;
  v3 = _wcsicmp(a1, L"Render") != 0;
  v4 = CoCreateInstance(
         &GUID_bcde0395_e52f_467c_8e3d_c4579291692e,
         0,
         0x17u,
         &GUID_a95664d2_9614_4f35_a746_de8db63617e6,
         &ppv);
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(LPVOID, BOOL, _QWORD, __int64 *))(*(_QWORD *)ppv + 32LL))(ppv, v3, 0, &v7);
    if ( v4 >= 0 )
      v4 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v7 + 40LL))(v7, v6);
    *a2 = v6[0];
  }
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180001b70  mov     rax, rsp
0x180001b73  mov     [rax+8], rbx
0x180001b77  mov     [rax+10h], rsi
0x180001b7b  push    rdi
0x180001b7c  sub     rsp, 40h
0x180001b80  mov     rdi, rdx
0x180001b83  mov     qword ptr [rax+20h], 0
0x180001b8b  lea     rdx, aRender; "Render"
0x180001b92  mov     qword ptr [rax+18h], 0
0x180001b9a  mov     qword ptr [rax-18h], 0
0x180001ba2  call    cs:__imp__wcsicmp
0x180001ba9  nop     dword ptr [rax+rax+00h]
0x180001bae  xor     esi, esi
0x180001bb0  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x180001bb7  test    eax, eax
0x180001bb9  lea     rcx, _GUID_bcde0395_e52f_467c_8e3d_c4579291692e; rclsid
0x180001bc0  lea     rax, [rsp+48h+arg_18]
0x180001bc5  setnz   sil
0x180001bc9  mov     [rsp+48h+ppv], rax; ppv
0x180001bce  xor     edx, edx; pUnkOuter
0x180001bd0  lea     r8d, [rdx+17h]; dwClsContext
0x180001bd4  call    cs:__imp_CoCreateInstance
0x180001bdb  nop     dword ptr [rax+rax+00h]
0x180001be0  mov     ebx, eax
0x180001be2  test    eax, eax
0x180001be4  js      short loc_180001C27
0x180001be6  mov     rcx, [rsp+48h+arg_18]
0x180001beb  lea     r9, [rsp+48h+arg_10]
0x180001bf0  xor     r8d, r8d
0x180001bf3  mov     edx, esi
0x180001bf5  mov     rax, [rcx]
0x180001bf8  mov     rax, [rax+20h]
0x180001bfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c01  mov     ebx, eax
0x180001c03  test    eax, eax
0x180001c05  js      short loc_180001C1F
0x180001c07  mov     rcx, [rsp+48h+arg_10]
0x180001c0c  lea     rdx, [rsp+48h+var_18]
0x180001c11  mov     rax, [rcx]
0x180001c14  mov     rax, [rax+28h]
0x180001c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c1d  mov     ebx, eax
0x180001c1f  mov     rax, [rsp+48h+var_18]
0x180001c24  mov     [rdi], rax
0x180001c27  mov     rcx, [rsp+48h+arg_10]
0x180001c2c  test    rcx, rcx
0x180001c2f  jz      short loc_180001C3D
0x180001c31  mov     rax, [rcx]
0x180001c34  mov     rax, [rax+10h]
0x180001c38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c3d  mov     rcx, [rsp+48h+arg_18]
0x180001c42  test    rcx, rcx
0x180001c45  jz      short loc_180001C53
0x180001c47  mov     rax, [rcx]
0x180001c4a  mov     rax, [rax+10h]
0x180001c4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c53  mov     rsi, [rsp+48h+arg_8]
0x180001c58  mov     eax, ebx
0x180001c5a  mov     rbx, [rsp+48h+arg_0]
0x180001c5f  add     rsp, 40h
0x180001c63  pop     rdi
0x180001c64  retn
```
