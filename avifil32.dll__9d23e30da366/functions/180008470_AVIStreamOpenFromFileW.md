# AVIStreamOpenFromFileW

- ea: `0x180008470`
- end: `0x1800084ff`
- name: `AVIStreamOpenFromFileW`
- size: `143`
- prototype: `HRESULT __stdcall(PAVISTREAM *ppavi, LPCWSTR szFile, DWORD fccType, LONG lParam, UINT mode, CLSID *pclsidHandler)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001460`
- `0x180007c00`
- `0x180008470`
- `0x180018010`

## pseudocode

```c
HRESULT __stdcall AVIStreamOpenFromFileW(
        PAVISTREAM *ppavi,
        LPCWSTR szFile,
        DWORD fccType,
        LONG lParam,
        UINT mode,
        CLSID *pclsidHandler)
{
  int v9; // ebx
  PAVIFILE ppfile; // [rsp+30h] [rbp-38h] BYREF

  ppfile = 0;
  v9 = AVIFileOpenW(&ppfile, szFile, mode, pclsidHandler);
  if ( v9 >= 0 )
  {
    v9 = ((__int64 (__fastcall *)(PAVIFILE, PAVISTREAM *, _QWORD, _QWORD))ppfile->lpVtbl->GetStream)(
           ppfile,
           ppavi,
           fccType,
           (unsigned int)lParam);
    ((void (__fastcall *)(PAVIFILE))ppfile->lpVtbl->Release)(ppfile);
  }
  return v9;
}

```

## disassembly

```asm
0x180008470  push    rbx
0x180008472  push    rbp
0x180008473  push    rsi
0x180008474  push    rdi
0x180008475  sub     rsp, 48h
0x180008479  mov     rax, cs:__security_cookie
0x180008480  xor     rax, rsp
0x180008483  mov     [rsp+68h+var_30], rax
0x180008488  mov     ebp, r9d
0x18000848b  mov     [rsp+68h+ppfile], 0
0x180008494  mov     r9, [rsp+68h+pclsidHandler]; lpHandler
0x18000849c  mov     esi, r8d
0x18000849f  mov     r8d, [rsp+68h+mode]; uMode
0x1800084a7  mov     rdi, rcx
0x1800084aa  lea     rcx, [rsp+68h+ppfile]; ppfile
0x1800084af  call    AVIFileOpenW
0x1800084b4  mov     ebx, eax
0x1800084b6  test    eax, eax
0x1800084b8  js      short loc_1800084E7
0x1800084ba  mov     rcx, [rsp+68h+ppfile]
0x1800084bf  mov     r9d, ebp
0x1800084c2  mov     r8d, esi
0x1800084c5  mov     rdx, rdi
0x1800084c8  mov     rax, [rcx]
0x1800084cb  mov     rax, [rax+20h]
0x1800084cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084d4  mov     rcx, [rsp+68h+ppfile]
0x1800084d9  mov     ebx, eax
0x1800084db  mov     rax, [rcx]
0x1800084de  mov     rax, [rax+10h]
0x1800084e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084e7  mov     eax, ebx
0x1800084e9  mov     rcx, [rsp+68h+var_30]
0x1800084ee  xor     rcx, rsp; StackCookie
0x1800084f1  call    __security_check_cookie
0x1800084f6  add     rsp, 48h
0x1800084fa  pop     rdi
0x1800084fb  pop     rsi
0x1800084fc  pop     rbp
0x1800084fd  pop     rbx
0x1800084fe  retn
```
