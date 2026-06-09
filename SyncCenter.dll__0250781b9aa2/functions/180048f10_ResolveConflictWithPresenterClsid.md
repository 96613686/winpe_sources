# _ResolveConflictWithPresenterClsid

- ea: `0x180048f10`
- end: `0x180048fec`
- name: `_ResolveConflictWithPresenterClsid`
- size: `220`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180048c3c`
- `0x180048ff4`

## callees

- `0x1800134e8`
- `0x180048f10`
- `0x180053010`

## import_xrefs

- `SHELL32!__imp_SHExtCoCreateInstance` at `0x180048f66`
- `SHELL32!__imp_SHExtCoCreateInstance` at `0x180048f66`
- `SHLWAPI!__imp_IUnknown_SetSite` at `0x180048f8d`
- `SHLWAPI!__imp_IUnknown_SetSite` at `0x180048fb3`
- `SHLWAPI!__imp_IUnknown_SetSite` at `0x180048f8d`
- `SHLWAPI!__imp_IUnknown_SetSite` at `0x180048fb3`

## pseudocode

```c
__int64 __fastcall ResolveConflictWithPresenterClsid(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  int v8; // edi
  IUnknown *punk; // [rsp+30h] [rbp-38h] BYREF
  IUnknown punkSite; // [rsp+38h] [rbp-30h] BYREF
  __int64 v12; // [rsp+40h] [rbp-28h]

  punk = 0;
  v8 = SHExtCoCreateInstance(a2, 0, 1025, 2, &GUID_0b4f5353_fd2b_42cd_8763_4779f2d508a3, &punk);
  if ( v8 >= 0 )
  {
    punkSite.lpVtbl = (struct IUnknownVtbl *)&CObjectWithWindow::`vftable';
    v12 = a1;
    IUnknown_SetSite(punk, &punkSite);
    v8 = ((__int64 (__fastcall *)(IUnknown *, __int64, __int64))punk->lpVtbl[1].QueryInterface)(punk, a4, a5);
    IUnknown_SetSite(punk, 0);
  }
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a5 + 32LL))(a5, a6);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&punk);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180048f10  mov     r11, rsp
0x180048f13  mov     [r11+8], rbx
0x180048f17  mov     [r11+18h], rbp
0x180048f1b  push    rsi
0x180048f1c  push    rdi
0x180048f1d  push    r14
0x180048f1f  sub     rsp, 50h
0x180048f23  mov     rbx, [rsp+68h+arg_20]
0x180048f2b  mov     rbp, rcx
0x180048f2e  mov     rsi, [rsp+68h+arg_28]
0x180048f36  lea     rcx, [r11-38h]
0x180048f3a  mov     [r11-40h], rcx
0x180048f3e  mov     rax, rdx
0x180048f41  xor     edx, edx
0x180048f43  mov     qword ptr [r11-38h], 0
0x180048f4b  lea     rcx, _GUID_0b4f5353_fd2b_42cd_8763_4779f2d508a3
0x180048f52  mov     r14, r9
0x180048f55  mov     [r11-48h], rcx
0x180048f59  mov     r8d, 401h
0x180048f5f  mov     rcx, rax
0x180048f62  lea     r9d, [rdx+2]
0x180048f66  call    cs:__imp_SHExtCoCreateInstance
0x180048f6c  mov     edi, eax
0x180048f6e  test    eax, eax
0x180048f70  js      short loc_180048FB9
0x180048f72  mov     rcx, [rsp+68h+punk]; punk
0x180048f77  lea     rax, ??_7CObjectWithWindow@@6B@; const CObjectWithWindow::`vftable'
0x180048f7e  lea     rdx, [rsp+68h+punkSite]; punkSite
0x180048f83  mov     [rsp+68h+punkSite.lpVtbl], rax
0x180048f88  mov     [rsp+68h+var_28], rbp
0x180048f8d  call    cs:__imp_IUnknown_SetSite
0x180048f93  mov     rcx, [rsp+68h+punk]
0x180048f98  mov     r8, rbx
0x180048f9b  mov     rdx, r14
0x180048f9e  mov     rax, [rcx]
0x180048fa1  mov     rax, [rax+18h]
0x180048fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048faa  mov     rcx, [rsp+68h+punk]; punk
0x180048faf  xor     edx, edx; punkSite
0x180048fb1  mov     edi, eax
0x180048fb3  call    cs:__imp_IUnknown_SetSite
0x180048fb9  mov     rax, [rbx]
0x180048fbc  mov     rdx, rsi
0x180048fbf  mov     rcx, rbx
0x180048fc2  mov     rax, [rax+20h]
0x180048fc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048fcb  lea     rcx, [rsp+68h+punk]
0x180048fd0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180048fd5  lea     r11, [rsp+68h+var_18]
0x180048fda  mov     eax, edi
0x180048fdc  mov     rbx, [r11+20h]
0x180048fe0  mov     rbp, [r11+30h]
0x180048fe4  mov     rsp, r11
0x180048fe7  pop     r14
0x180048fe9  pop     rdi
0x180048fea  pop     rsi
0x180048feb  retn
```
