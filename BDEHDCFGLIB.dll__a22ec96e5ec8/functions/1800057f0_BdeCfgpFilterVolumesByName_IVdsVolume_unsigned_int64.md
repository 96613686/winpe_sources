# BdeCfgpFilterVolumesByName(IVdsVolume *,unsigned __int64)

- ea: `0x1800057f0`
- end: `0x18000587c`
- name: `?BdeCfgpFilterVolumesByName@@YAHPEAUIVdsVolume@@_K@Z`
- size: `140`
- prototype: `__int64 __fastcall(struct IVdsVolume *, const wchar_t *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1800057f0`
- `0x1800135c0`
- `0x180015010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180005844`
- `msvcrt!_wcsicmp` at `0x180005844`
- `ole32!CoTaskMemFree` at `0x180005859`
- `ole32!CoTaskMemFree` at `0x180005859`

## pseudocode

```c
__int64 __fastcall BdeCfgpFilterVolumesByName(struct IVdsVolume *a1, const wchar_t *a2)
{
  struct IVdsVolumeVtbl *lpVtbl; // rax
  unsigned int v4; // ebx
  _OWORD v6[3]; // [rsp+20h] [rbp-48h] BYREF
  wchar_t *String1; // [rsp+50h] [rbp-18h]

  String1 = 0;
  lpVtbl = a1->lpVtbl;
  v4 = 0;
  memset(v6, 0, sizeof(v6));
  if ( ((int (__fastcall *)(struct IVdsVolume *, _OWORD *))lpVtbl->GetProperties)(a1, v6) >= 0 )
  {
    LOBYTE(v4) = _wcsicmp(String1, a2) == 0;
    if ( String1 )
      CoTaskMemFree(String1);
  }
  return v4;
}

```

## disassembly

```asm
0x1800057f0  mov     [rsp+arg_10], rbx
0x1800057f5  push    rdi
0x1800057f6  sub     rsp, 60h
0x1800057fa  mov     rax, cs:__security_cookie
0x180005801  xor     rax, rsp
0x180005804  mov     [rsp+68h+var_10], rax
0x180005809  xor     eax, eax
0x18000580b  xorps   xmm0, xmm0
0x18000580e  mov     [rsp+68h+String1], rax
0x180005813  mov     rdi, rdx
0x180005816  mov     rax, [rcx]
0x180005819  lea     rdx, [rsp+68h+var_48]
0x18000581e  xor     ebx, ebx
0x180005820  movups  [rsp+68h+var_48], xmm0
0x180005825  mov     rax, [rax+18h]
0x180005829  movups  [rsp+68h+var_38], xmm0
0x18000582e  movups  [rsp+68h+var_28], xmm0
0x180005833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005838  test    eax, eax
0x18000583a  js      short loc_18000585F
0x18000583c  mov     rcx, [rsp+68h+String1]; String1
0x180005841  mov     rdx, rdi; String2
0x180005844  call    cs:__imp__wcsicmp
0x18000584a  mov     rcx, [rsp+68h+String1]; pv
0x18000584f  test    eax, eax
0x180005851  setz    bl
0x180005854  test    rcx, rcx
0x180005857  jz      short loc_18000585F
0x180005859  call    cs:__imp_CoTaskMemFree
0x18000585f  mov     eax, ebx
0x180005861  mov     rcx, [rsp+68h+var_10]
0x180005866  xor     rcx, rsp; StackCookie
0x180005869  call    __security_check_cookie
0x18000586e  mov     rbx, [rsp+68h+arg_10]
0x180005876  add     rsp, 60h
0x18000587a  pop     rdi
0x18000587b  retn
```
