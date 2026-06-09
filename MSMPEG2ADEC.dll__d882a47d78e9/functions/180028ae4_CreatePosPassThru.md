# CreatePosPassThru

- ea: `0x180028ae4`
- end: `0x180028bc4`
- name: `CreatePosPassThru`
- size: `224`
- prototype: `__int64 __fastcall(LPUNKNOWN pUnkOuter)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800298d0`

## callees

- `0x180028ae4`
- `0x180088750`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180028b28`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180028b28`

## pseudocode

```c
HRESULT __fastcall CreatePosPassThru(LPUNKNOWN pUnkOuter, __int64 a2, __int64 a3, _QWORD *a4)
{
  HRESULT result; // eax
  int v7; // ebx
  _QWORD v8[3]; // [rsp+30h] [rbp-18h] BYREF
  LPVOID v9; // [rsp+68h] [rbp+20h] BYREF

  *a4 = 0;
  v9 = 0;
  result = CoCreateInstance(&CLSID_SeekingPassThru, pUnkOuter, 1u, &IID_IUnknown, &v9);
  if ( result >= 0 )
  {
    v8[0] = 0;
    v7 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, _QWORD *))v9)(v9, &IID_ISeekingPassThru, v8);
    if ( v7 < 0
      || (v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(*(_QWORD *)v8[0] + 24LL))(v8[0], 0, a3),
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v8[0] + 16LL))(v8[0]),
          v7 < 0) )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v9 + 16LL))(v9);
      return v7;
    }
    else
    {
      *a4 = v9;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180028ae4  mov     r11, rsp
0x180028ae7  mov     [r11+8], rbx
0x180028aeb  mov     [r11+10h], rsi
0x180028aef  push    rdi
0x180028af0  sub     rsp, 40h
0x180028af4  mov     rdi, r9
0x180028af7  mov     qword ptr [r9], 0
0x180028afe  mov     rsi, r8
0x180028b01  mov     qword ptr [r11+20h], 0
0x180028b09  lea     rax, [r11+20h]
0x180028b0d  mov     rdx, rcx; pUnkOuter
0x180028b10  lea     r9, IID_IUnknown; riid
0x180028b17  mov     [r11-28h], rax
0x180028b1b  mov     r8d, 1; dwClsContext
0x180028b21  lea     rcx, CLSID_SeekingPassThru; rclsid
0x180028b28  call    cs:__imp_CoCreateInstance
0x180028b2f  nop     dword ptr [rax+rax+00h]
0x180028b34  test    eax, eax
0x180028b36  js      short loc_180028BB3
0x180028b38  mov     rcx, [rsp+48h+arg_18]
0x180028b3d  lea     r8, [rsp+48h+var_18]
0x180028b42  mov     [rsp+48h+var_18], 0
0x180028b4b  lea     rdx, IID_ISeekingPassThru
0x180028b52  mov     rax, [rcx]
0x180028b55  mov     rax, [rax]
0x180028b58  call    cs:__guard_dispatch_icall_fptr
0x180028b5e  mov     ebx, eax
0x180028b60  test    eax, eax
0x180028b62  jns     short loc_180028B7A
0x180028b64  mov     rcx, [rsp+48h+arg_18]
0x180028b69  mov     rdx, [rcx]
0x180028b6c  mov     rax, [rdx+10h]
0x180028b70  call    cs:__guard_dispatch_icall_fptr
0x180028b76  mov     eax, ebx
0x180028b78  jmp     short loc_180028BB3
0x180028b7a  mov     rcx, [rsp+48h+var_18]
0x180028b7f  mov     r8, rsi
0x180028b82  xor     edx, edx
0x180028b84  mov     rax, [rcx]
0x180028b87  mov     rax, [rax+18h]
0x180028b8b  call    cs:__guard_dispatch_icall_fptr
0x180028b91  mov     rcx, [rsp+48h+var_18]
0x180028b96  mov     ebx, eax
0x180028b98  mov     rdx, [rcx]
0x180028b9b  mov     rax, [rdx+10h]
0x180028b9f  call    cs:__guard_dispatch_icall_fptr
0x180028ba5  test    ebx, ebx
0x180028ba7  js      short loc_180028B64
0x180028ba9  mov     rax, [rsp+48h+arg_18]
0x180028bae  mov     [rdi], rax
0x180028bb1  xor     eax, eax
0x180028bb3  mov     rbx, [rsp+48h+arg_0]
0x180028bb8  mov     rsi, [rsp+48h+arg_8]
0x180028bbd  add     rsp, 40h
0x180028bc1  pop     rdi
0x180028bc2  retn
```
