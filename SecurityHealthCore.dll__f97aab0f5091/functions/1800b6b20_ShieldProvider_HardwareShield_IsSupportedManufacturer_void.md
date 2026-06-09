# ShieldProvider::HardwareShield::IsSupportedManufacturer(void)

- ea: `0x1800b6b20`
- end: `0x1800b6be5`
- name: `?IsSupportedManufacturer@HardwareShield@ShieldProvider@@AEAAHXZ`
- size: `197`
- prototype: `__int64 __fastcall(ShieldProvider::HardwareShield *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800ba120`

## callees

- `0x180004710`
- `0x1800b6b20`
- `0x1800e7010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800b6b9f`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800b6b9f`
- `ole32!CoTaskMemFree` at `0x1800b6b64`
- `ole32!CoTaskMemFree` at `0x1800b6bca`
- `ole32!CoTaskMemFree` at `0x1800b6b64`
- `ole32!CoTaskMemFree` at `0x1800b6bca`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ShieldProvider::HardwareShield::IsSupportedManufacturer(ShieldProvider::HardwareShield *this)
{
  const wchar_t **v2; // rbx
  unsigned int v3; // ebx
  LPVOID pv; // [rsp+20h] [rbp-38h] BYREF
  _QWORD v5[3]; // [rsp+28h] [rbp-30h] BYREF
  __int64 v6; // [rsp+40h] [rbp-18h] BYREF

  pv = 0;
  if ( (*(int (__fastcall **)(char *, LPVOID *))(*((_QWORD *)this + 6) + 496LL))((char *)this + 48, &pv) >= 0 )
  {
    v5[0] = L"dell";
    v5[1] = L"hewlett-packard";
    v5[2] = L"lenovo";
    v2 = (const wchar_t **)v5;
    while ( _wcsicmp((const wchar_t *)pv, *v2) )
    {
      if ( ++v2 == (const wchar_t **)&v6 )
      {
        v3 = 0;
        goto LABEL_10;
      }
    }
    v3 = 1;
LABEL_10:
    if ( pv )
      CoTaskMemFree(pv);
    return v3;
  }
  else
  {
    if ( pv )
      CoTaskMemFree(pv);
    return 0;
  }
}

```

## disassembly

```asm
0x1800b6b20  push    rbx
0x1800b6b22  sub     rsp, 50h
0x1800b6b26  mov     rax, cs:__security_cookie
0x1800b6b2d  xor     rax, rsp
0x1800b6b30  mov     [rsp+58h+var_18], rax
0x1800b6b35  mov     [rsp+58h+pv], 0
0x1800b6b3e  add     rcx, 30h ; '0'
0x1800b6b42  mov     rax, [rcx]
0x1800b6b45  lea     rdx, [rsp+58h+pv]
0x1800b6b4a  mov     rax, [rax+1F0h]
0x1800b6b51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6b56  test    eax, eax
0x1800b6b58  jns     short loc_1800B6B6E
0x1800b6b5a  mov     rcx, [rsp+58h+pv]; pv
0x1800b6b5f  test    rcx, rcx
0x1800b6b62  jz      short loc_1800B6B6A
0x1800b6b64  call    cs:__imp_CoTaskMemFree
0x1800b6b6a  xor     eax, eax
0x1800b6b6c  jmp     short loc_1800B6BD2
0x1800b6b6e  lea     rax, aDell; "dell"
0x1800b6b75  mov     [rsp+58h+var_30], rax
0x1800b6b7a  lea     rax, aHewlettPackard; "hewlett-packard"
0x1800b6b81  mov     [rsp+58h+var_28], rax
0x1800b6b86  lea     rax, aLenovo; "lenovo"
0x1800b6b8d  mov     [rsp+58h+var_20], rax
0x1800b6b92  lea     rbx, [rsp+58h+var_30]
0x1800b6b97  mov     rdx, [rbx]; String2
0x1800b6b9a  mov     rcx, [rsp+58h+pv]; String1
0x1800b6b9f  call    cs:__imp__wcsicmp
0x1800b6ba5  test    eax, eax
0x1800b6ba7  jz      short loc_1800B6BBB
0x1800b6ba9  add     rbx, 8
0x1800b6bad  lea     rax, [rsp+58h+var_18]
0x1800b6bb2  cmp     rbx, rax
0x1800b6bb5  jnz     short loc_1800B6B97
0x1800b6bb7  xor     ebx, ebx
0x1800b6bb9  jmp     short loc_1800B6BC0
0x1800b6bbb  mov     ebx, 1
0x1800b6bc0  mov     rcx, [rsp+58h+pv]; pv
0x1800b6bc5  test    rcx, rcx
0x1800b6bc8  jz      short loc_1800B6BD0
0x1800b6bca  call    cs:__imp_CoTaskMemFree
0x1800b6bd0  mov     eax, ebx
0x1800b6bd2  mov     rcx, [rsp+58h+var_18]
0x1800b6bd7  xor     rcx, rsp; StackCookie
0x1800b6bda  call    __security_check_cookie
0x1800b6bdf  add     rsp, 50h
0x1800b6be3  pop     rbx
0x1800b6be4  retn
```
