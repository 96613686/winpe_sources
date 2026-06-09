# DllGetClassObject

- ea: `0x180019e70`
- end: `0x180019f14`
- name: `DllGetClassObject`
- size: `164`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180019e70`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019eb7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019eb7`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT v6; // esi
  _DWORD *v7; // rax
  _DWORD *v8; // rbx

  if ( !ppv )
    return -2147467261;
  *ppv = 0;
  v6 = -2147221231;
  if ( *(_OWORD *)rclsid != *(_OWORD *)&CLSID_SIProfilesHandler )
    return v6;
  v7 = LocalAlloc(0, 0x10u);
  v8 = v7;
  if ( v7 )
  {
    v7[2] = 1;
    *(_QWORD *)v7 = &CProfilesHandlerClassFactory::`vftable';
    _InterlockedIncrement(&g_cRefThisDll);
    v6 = (**(__int64 (__fastcall ***)(HLOCAL, const IID *const, LPVOID *))v7)(v7, riid, ppv);
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 16LL))(v8);
    return v6;
  }
  return -2147024882;
}

```

## disassembly

```asm
0x180019e70  push    rbx
0x180019e72  push    rbp
0x180019e73  push    rsi
0x180019e74  push    rdi
0x180019e75  sub     rsp, 28h
0x180019e79  mov     rdi, r8
0x180019e7c  mov     rbp, rdx
0x180019e7f  test    r8, r8
0x180019e82  jnz     short loc_180019E8B
0x180019e84  mov     eax, 80004003h
0x180019e89  jmp     short loc_180019F04
0x180019e8b  mov     qword ptr [r8], 0
0x180019e92  mov     esi, 80040111h
0x180019e97  mov     rax, [rcx]
0x180019e9a  cmp     rax, qword ptr cs:CLSID_SIProfilesHandler.Data1
0x180019ea1  jnz     short loc_180019F02
0x180019ea3  mov     rax, [rcx+8]
0x180019ea7  cmp     rax, qword ptr cs:CLSID_SIProfilesHandler.Data4
0x180019eae  jnz     short loc_180019F02
0x180019eb0  mov     edx, 10h; uBytes
0x180019eb5  xor     ecx, ecx; uFlags
0x180019eb7  call    cs:__imp_LocalAlloc
0x180019ebd  mov     rbx, rax
0x180019ec0  test    rax, rax
0x180019ec3  jz      short loc_180019F0D
0x180019ec5  lea     rax, ??_7CProfilesHandlerClassFactory@@6B@; const CProfilesHandlerClassFactory::`vftable'
0x180019ecc  mov     dword ptr [rbx+8], 1
0x180019ed3  mov     [rbx], rax
0x180019ed6  lock inc cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x180019edd  mov     rax, [rbx]
0x180019ee0  mov     r8, rdi
0x180019ee3  mov     rdx, rbp
0x180019ee6  mov     rcx, rbx
0x180019ee9  mov     rax, [rax]
0x180019eec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ef1  mov     rcx, [rbx]
0x180019ef4  mov     esi, eax
0x180019ef6  mov     rax, [rcx+10h]
0x180019efa  mov     rcx, rbx
0x180019efd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f02  mov     eax, esi
0x180019f04  add     rsp, 28h
0x180019f08  pop     rdi
0x180019f09  pop     rsi
0x180019f0a  pop     rbp
0x180019f0b  pop     rbx
0x180019f0c  retn
0x180019f0d  mov     eax, 8007000Eh
0x180019f12  jmp     short loc_180019F04
```
