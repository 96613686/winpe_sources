# DllGetClassObject

- ea: `0x1800b7ad0`
- end: `0x1800b7b84`
- name: `DllGetClassObject`
- size: `180`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180048738`
- `0x18004df30`
- `0x1800b7ad0`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  __int64 v3; // rax
  __int64 v5; // rax
  __int64 v7; // rax
  _DWORD *v8; // rcx

  v3 = *(_QWORD *)&riid->Data1;
  if ( !*(_QWORD *)&riid->Data1 )
    v3 = *(_QWORD *)riid->Data4 - 0x46000000000000C0LL;
  if ( v3 )
  {
    v5 = *(_QWORD *)&riid->Data1 - 1LL;
    if ( *(_QWORD *)&riid->Data1 == 1 )
      v5 = *(_QWORD *)riid->Data4 - 0x46000000000000C0LL;
    if ( v5 )
      return -2147467262;
  }
  v7 = 0x11D1969D08C8F6D9LL - *(_QWORD *)&rclsid->Data1;
  if ( *(_QWORD *)&rclsid->Data1 == 0x11D1969D08C8F6D9LL )
    v7 = 0xCEFEB64FC000028EuLL - *(_QWORD *)rclsid->Data4;
  if ( v7 )
    return -2147467259;
  v8 = (_DWORD *)sub_180048738(16, riid);
  if ( v8 )
  {
    v8[2] = 0;
    *(_QWORD *)v8 = &CMgrClassFactory::`vftable';
  }
  else
  {
    v8 = 0;
  }
  *ppv = v8;
  if ( !v8 )
    return -2147024882;
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 8LL))(v8);
  return 0;
}

```

## disassembly

```asm
0x1800b7ad0  push    rbx
0x1800b7ad2  sub     rsp, 20h
0x1800b7ad6  mov     rax, [rdx]
0x1800b7ad9  mov     rbx, r8
0x1800b7adc  sub     rax, cs:qword_1800BAC88
0x1800b7ae3  jnz     short loc_1800B7AF0
0x1800b7ae5  mov     rax, [rdx+8]
0x1800b7ae9  sub     rax, cs:qword_1800BAC90
0x1800b7af0  test    rax, rax
0x1800b7af3  jz      short loc_1800B7B18
0x1800b7af5  mov     rax, [rdx]
0x1800b7af8  sub     rax, cs:qword_1800CA6A8
0x1800b7aff  jnz     short loc_1800B7B0C
0x1800b7b01  mov     rax, [rdx+8]
0x1800b7b05  sub     rax, cs:qword_1800CA6B0
0x1800b7b0c  test    rax, rax
0x1800b7b0f  jz      short loc_1800B7B18
0x1800b7b11  mov     eax, 80004002h
0x1800b7b16  jmp     short loc_1800B7B7E
0x1800b7b18  mov     rax, qword ptr cs:rguid.Data1
0x1800b7b1f  sub     rax, [rcx]
0x1800b7b22  jnz     short loc_1800B7B2F
0x1800b7b24  mov     rax, qword ptr cs:rguid.Data4
0x1800b7b2b  sub     rax, [rcx+8]
0x1800b7b2f  test    rax, rax
0x1800b7b32  jnz     short loc_1800B7B79
0x1800b7b34  lea     ecx, [rax+10h]
0x1800b7b37  call    sub_180048738
0x1800b7b3c  mov     rcx, rax
0x1800b7b3f  test    rax, rax
0x1800b7b42  jz      short loc_1800B7B57
0x1800b7b44  lea     rax, ??_7CMgrClassFactory@@6B@; const CMgrClassFactory::`vftable'
0x1800b7b4b  mov     dword ptr [rcx+8], 0
0x1800b7b52  mov     [rcx], rax
0x1800b7b55  jmp     short loc_1800B7B59
0x1800b7b57  xor     ecx, ecx
0x1800b7b59  mov     [rbx], rcx
0x1800b7b5c  test    rcx, rcx
0x1800b7b5f  jnz     short loc_1800B7B68
0x1800b7b61  mov     eax, 8007000Eh
0x1800b7b66  jmp     short loc_1800B7B7E
0x1800b7b68  mov     rax, [rcx]
0x1800b7b6b  mov     rax, [rax+8]
0x1800b7b6f  call    cs:__guard_dispatch_icall_fptr
0x1800b7b75  xor     eax, eax
0x1800b7b77  jmp     short loc_1800B7B7E
0x1800b7b79  mov     eax, 80004005h
0x1800b7b7e  add     rsp, 20h
0x1800b7b82  pop     rbx
0x1800b7b83  retn
```
