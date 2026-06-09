# DllGetClassObject

- ea: `0x180002020`
- end: `0x1800020d0`
- name: `DllGetClassObject`
- size: `176`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001008`
- `0x180002020`
- `0x180003010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT v5; // ebx
  _DWORD *v6; // rax
  _DWORD *v7; // rdi

  if ( !ppv )
    return -2147024809;
  *ppv = 0;
  if ( *(_OWORD *)rclsid != *(_OWORD *)&CLSID_WiaExtensionHost64 )
    return -2147221231;
  v6 = operator new(0x10u);
  v7 = v6;
  if ( !v6 )
    return -2147024882;
  v6[2] = 1;
  *(_QWORD *)v6 = &CWiaExtensionHost64Factory::`vftable';
  _InterlockedIncrement((volatile signed __int32 *)&g_cRef);
  v5 = (**(__int64 (__fastcall ***)(void *, const IID *const, LPVOID *))v6)(v6, riid, ppv);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v7 + 16LL))(v7);
  return v5;
}

```

## disassembly

```asm
0x180002020  mov     [rsp+arg_0], rbx
0x180002025  mov     [rsp+arg_8], rsi
0x18000202a  push    rdi
0x18000202b  sub     rsp, 20h
0x18000202f  mov     rbx, r8
0x180002032  mov     rsi, rdx
0x180002035  test    r8, r8
0x180002038  jnz     short loc_180002041
0x18000203a  mov     ebx, 80070057h
0x18000203f  jmp     short loc_1800020BE
0x180002041  mov     qword ptr [r8], 0
0x180002048  mov     rax, [rcx]
0x18000204b  cmp     rax, qword ptr cs:CLSID_WiaExtensionHost64.Data1
0x180002052  jnz     short loc_1800020B9
0x180002054  mov     rax, [rcx+8]
0x180002058  cmp     rax, qword ptr cs:CLSID_WiaExtensionHost64.Data4
0x18000205f  jnz     short loc_1800020B9
0x180002061  mov     ecx, 10h; Size
0x180002066  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000206b  mov     rdi, rax
0x18000206e  test    rax, rax
0x180002071  jz      short loc_1800020B2
0x180002073  lea     rax, ??_7CWiaExtensionHost64Factory@@6B@; const CWiaExtensionHost64Factory::`vftable'
0x18000207a  mov     dword ptr [rdi+8], 1
0x180002081  mov     [rdi], rax
0x180002084  lock inc cs:?g_cRef@@3KA; ulong g_cRef
0x18000208b  mov     rax, [rdi]
0x18000208e  mov     r8, rbx
0x180002091  mov     rdx, rsi
0x180002094  mov     rcx, rdi
0x180002097  mov     rax, [rax]
0x18000209a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000209f  mov     rcx, [rdi]
0x1800020a2  mov     ebx, eax
0x1800020a4  mov     rax, [rcx+10h]
0x1800020a8  mov     rcx, rdi
0x1800020ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020b0  jmp     short loc_1800020BE
0x1800020b2  mov     ebx, 8007000Eh
0x1800020b7  jmp     short loc_1800020BE
0x1800020b9  mov     ebx, 80040111h
0x1800020be  mov     rsi, [rsp+28h+arg_8]
0x1800020c3  mov     eax, ebx
0x1800020c5  mov     rbx, [rsp+28h+arg_0]
0x1800020ca  add     rsp, 20h
0x1800020ce  pop     rdi
0x1800020cf  retn
```
