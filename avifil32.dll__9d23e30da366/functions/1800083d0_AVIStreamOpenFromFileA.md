# AVIStreamOpenFromFileA

- ea: `0x1800083d0`
- end: `0x18000845f`
- name: `AVIStreamOpenFromFileA`
- size: `143`
- prototype: `HRESULT __stdcall(PAVISTREAM *ppavi, LPCSTR szFile, DWORD fccType, LONG lParam, UINT mode, CLSID *pclsidHandler)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001460`
- `0x180007b70`
- `0x1800083d0`
- `0x180018010`

## pseudocode

```c
HRESULT __stdcall AVIStreamOpenFromFileA(
        PAVISTREAM *ppavi,
        LPCSTR szFile,
        DWORD fccType,
        LONG lParam,
        UINT mode,
        CLSID *pclsidHandler)
{
  int v9; // ebx
  PAVIFILE ppfile; // [rsp+30h] [rbp-38h] BYREF

  ppfile = 0;
  v9 = AVIFileOpenA(&ppfile, szFile, mode, pclsidHandler);
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
0x1800083d0  push    rbx; AVIStreamOpenFromFile
0x1800083d2  push    rbp
0x1800083d3  push    rsi
0x1800083d4  push    rdi
0x1800083d5  sub     rsp, 48h
0x1800083d9  mov     rax, cs:__security_cookie
0x1800083e0  xor     rax, rsp
0x1800083e3  mov     [rsp+68h+var_30], rax
0x1800083e8  mov     ebp, r9d
0x1800083eb  mov     [rsp+68h+ppfile], 0
0x1800083f4  mov     r9, [rsp+68h+pclsidHandler]; lpHandler
0x1800083fc  mov     esi, r8d
0x1800083ff  mov     r8d, [rsp+68h+mode]; uMode
0x180008407  mov     rdi, rcx
0x18000840a  lea     rcx, [rsp+68h+ppfile]; ppfile
0x18000840f  call    AVIFileOpenA
0x180008414  mov     ebx, eax
0x180008416  test    eax, eax
0x180008418  js      short loc_180008447
0x18000841a  mov     rcx, [rsp+68h+ppfile]
0x18000841f  mov     r9d, ebp
0x180008422  mov     r8d, esi
0x180008425  mov     rdx, rdi
0x180008428  mov     rax, [rcx]
0x18000842b  mov     rax, [rax+20h]
0x18000842f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008434  mov     rcx, [rsp+68h+ppfile]
0x180008439  mov     ebx, eax
0x18000843b  mov     rax, [rcx]
0x18000843e  mov     rax, [rax+10h]
0x180008442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008447  mov     eax, ebx
0x180008449  mov     rcx, [rsp+68h+var_30]
0x18000844e  xor     rcx, rsp; StackCookie
0x180008451  call    __security_check_cookie
0x180008456  add     rsp, 48h
0x18000845a  pop     rdi
0x18000845b  pop     rsi
0x18000845c  pop     rbp
0x18000845d  pop     rbx
0x18000845e  retn
```
