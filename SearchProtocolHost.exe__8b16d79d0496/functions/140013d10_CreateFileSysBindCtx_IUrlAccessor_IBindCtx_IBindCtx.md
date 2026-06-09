# CreateFileSysBindCtx(IUrlAccessor *,IBindCtx *,IBindCtx * *)

- ea: `0x140013d10`
- end: `0x140013e55`
- name: `?CreateFileSysBindCtx@@YAJPEAUIUrlAccessor@@PEAUIBindCtx@@PEAPEAU2@@Z`
- size: `325`
- prototype: `__int64 __fastcall(struct IUrlAccessor *, struct IBindCtx *, struct IBindCtx **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14001263c`

## callees

- `0x140005240`
- `0x14000e898`
- `0x140013d10`
- `0x140070010`

## import_xrefs

- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x140013d52`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x140013d52`

## string_xrefs

- `0x140013da0`: `ItemCacheContext`
- `0x140013e05`: `Folders As Read Only`

## pseudocode

```c
__int64 __fastcall CreateFileSysBindCtx(struct IUrlAccessor *a1, struct IBindCtx *a2, struct IBindCtx **a3)
{
  HRESULT v6; // ebx
  struct IBindCtx *v7; // rax
  LPBC ppbc; // [rsp+20h] [rbp-30h] BYREF
  _QWORD v10[2]; // [rsp+28h] [rbp-28h] BYREF
  _DWORD v11[2]; // [rsp+38h] [rbp-18h] BYREF
  __int64 v12; // [rsp+40h] [rbp-10h]

  v10[1] = -2;
  *a3 = 0;
  ppbc = 0;
  v6 = CreateBindCtx(0, &ppbc);
  if ( v6 >= 0 )
  {
    v11[0] = 16;
    v11[1] = 2;
    v12 = 4096;
    v6 = ((__int64 (__fastcall *)(LPBC, _DWORD *))ppbc->lpVtbl->SetBindOptions)(ppbc, v11);
    if ( v6 >= 0 )
    {
      v6 = ((__int64 (__fastcall *)(LPBC, const wchar_t *, struct IBindCtx *))ppbc->lpVtbl->RegisterObjectParam)(
             ppbc,
             L"ItemCacheContext",
             a2);
      if ( v6 >= 0 )
      {
        v10[0] = 0;
        if ( ((__int64 (__fastcall *)(struct IUrlAccessor *, GUID *, _QWORD *))a1->lpVtbl->QueryInterface)(
               a1,
               &GUID_01e18d10_4d8b_11d2_855d_006008059367,
               v10) >= 0 )
        {
          v6 = ((__int64 (__fastcall *)(LPBC, const wchar_t *, struct IUrlAccessor *))ppbc->lpVtbl->RegisterObjectParam)(
                 ppbc,
                 L"File System Bind Data",
                 a1);
          if ( v6 >= 0 )
            v6 = ((__int64 (__fastcall *)(LPBC, const wchar_t *, struct IUrlAccessor *))ppbc->lpVtbl->RegisterObjectParam)(
                   ppbc,
                   L"Folders As Read Only",
                   a1);
        }
        TComPointer<IBindCtx>::~TComPointer<IBindCtx>(v10);
        if ( v6 >= 0 )
        {
          v7 = ppbc;
          ppbc = 0;
          *a3 = v7;
        }
      }
    }
  }
  TComPointer<IBindCtx>::~TComPointer<IBindCtx>(&ppbc);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140013d10  push    rbp
0x140013d12  push    rbx
0x140013d13  push    rsi
0x140013d14  push    rdi
0x140013d15  push    r14
0x140013d17  mov     rbp, rsp
0x140013d1a  sub     rsp, 50h
0x140013d1e  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFEh
0x140013d26  mov     rax, cs:__security_cookie
0x140013d2d  xor     rax, rsp
0x140013d30  mov     [rbp+var_8], rax
0x140013d34  mov     rsi, r8
0x140013d37  mov     r14, rdx
0x140013d3a  mov     rdi, rcx
0x140013d3d  mov     qword ptr [r8], 0
0x140013d44  mov     [rbp+ppbc], 0
0x140013d4c  lea     rdx, [rbp+ppbc]; ppbc
0x140013d50  xor     ecx, ecx; reserved
0x140013d52  call    cs:__imp_CreateBindCtx
0x140013d58  mov     ebx, eax
0x140013d5a  test    eax, eax
0x140013d5c  js      loc_140013E33
0x140013d62  mov     [rbp+var_18], 10h
0x140013d69  mov     [rbp+var_14], 2
0x140013d70  mov     [rbp+var_10], 1000h
0x140013d78  mov     rcx, [rbp+ppbc]
0x140013d7c  mov     rax, [rcx]
0x140013d7f  lea     rdx, [rbp+var_18]
0x140013d83  mov     rax, [rax+30h]
0x140013d87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013d8c  mov     ebx, eax
0x140013d8e  test    eax, eax
0x140013d90  js      loc_140013E33
0x140013d96  mov     rcx, [rbp+ppbc]
0x140013d9a  mov     rax, [rcx]
0x140013d9d  mov     r8, r14
0x140013da0  lea     rdx, aItemcacheconte; "ItemCacheContext"
0x140013da7  mov     rax, [rax+48h]
0x140013dab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013db0  mov     ebx, eax
0x140013db2  test    eax, eax
0x140013db4  js      short loc_140013E33
0x140013db6  mov     [rbp+var_28], 0
0x140013dbe  mov     rax, [rdi]
0x140013dc1  lea     r8, [rbp+var_28]
0x140013dc5  lea     rdx, _GUID_01e18d10_4d8b_11d2_855d_006008059367
0x140013dcc  mov     rcx, rdi
0x140013dcf  mov     rax, [rax]
0x140013dd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013dd7  test    eax, eax
0x140013dd9  js      short loc_140013E17
0x140013ddb  mov     rcx, [rbp+ppbc]
0x140013ddf  mov     rax, [rcx]
0x140013de2  mov     r8, rdi
0x140013de5  lea     rdx, aFileSystemBind; "File System Bind Data"
0x140013dec  mov     rax, [rax+48h]
0x140013df0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013df5  mov     ebx, eax
0x140013df7  test    eax, eax
0x140013df9  js      short loc_140013E17
0x140013dfb  mov     rcx, [rbp+ppbc]
0x140013dff  mov     rax, [rcx]
0x140013e02  mov     r8, rdi
0x140013e05  lea     rdx, aFoldersAsReadO; "Folders As Read Only"
0x140013e0c  mov     rax, [rax+48h]
0x140013e10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013e15  mov     ebx, eax
0x140013e17  lea     rcx, [rbp+var_28]
0x140013e1b  call    ??1?$TComPointer@UIBindCtx@@@@QEAA@XZ; TComPointer<IBindCtx>::~TComPointer<IBindCtx>(void)
0x140013e20  test    ebx, ebx
0x140013e22  js      short loc_140013E33
0x140013e24  mov     rax, [rbp+ppbc]
0x140013e28  mov     [rbp+ppbc], 0
0x140013e30  mov     [rsi], rax
0x140013e33  lea     rcx, [rbp+ppbc]
0x140013e37  call    ??1?$TComPointer@UIBindCtx@@@@QEAA@XZ; TComPointer<IBindCtx>::~TComPointer<IBindCtx>(void)
0x140013e3c  mov     eax, ebx
0x140013e3e  mov     rcx, [rbp+var_8]
0x140013e42  xor     rcx, rsp; StackCookie
0x140013e45  call    __security_check_cookie
0x140013e4a  add     rsp, 50h
0x140013e4e  pop     r14
0x140013e50  pop     rdi
0x140013e51  pop     rsi
0x140013e52  pop     rbx
0x140013e53  pop     rbp
0x140013e54  retn
```
