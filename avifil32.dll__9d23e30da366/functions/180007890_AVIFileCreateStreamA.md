# AVIFileCreateStreamA

- ea: `0x180007890`
- end: `0x180007950`
- name: `AVIFileCreateStreamA`
- size: `192`
- prototype: `HRESULT __stdcall(PAVIFILE pfile, PAVISTREAM *ppavi, AVISTREAMINFOA *psi)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001460`
- `0x180001d0c`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180007918`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180007918`

## pseudocode

```c
HRESULT __stdcall AVIFileCreateStreamA(PAVIFILE pfile, PAVISTREAM *ppavi, AVISTREAMINFOA *psi)
{
  __int128 v6; // xmm1
  __int128 v7; // xmm0
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  _OWORD v11[3]; // [rsp+30h] [rbp-F8h] BYREF
  _BYTE v12[28]; // [rsp+60h] [rbp-C8h]
  WCHAR WideCharStr[66]; // [rsp+7Ch] [rbp-ACh] BYREF

  *ppavi = 0;
  memset_0(v11, 0, 0xCCu);
  v6 = *(_OWORD *)&psi->wPriority;
  v11[0] = *(_OWORD *)&psi->fccType;
  v7 = *(_OWORD *)&psi->dwLength;
  v11[1] = v6;
  v8 = *(_OWORD *)&psi->dwSampleSize;
  v11[2] = v7;
  v9 = *(_OWORD *)&psi->rcFrame.right;
  *(_OWORD *)v12 = v8;
  *(_OWORD *)&v12[12] = v9;
  MultiByteToWideChar(0, 0, psi->szName, 64, WideCharStr, 64);
  return ((__int64 (__fastcall *)(PAVIFILE, PAVISTREAM *, _OWORD *))pfile->lpVtbl->CreateStream)(pfile, ppavi, v11);
}

```

## disassembly

```asm
0x180007890  push    rbx
0x180007892  push    rsi
0x180007893  push    rdi
0x180007894  sub     rsp, 110h
0x18000789b  mov     rax, cs:__security_cookie
0x1800078a2  xor     rax, rsp
0x1800078a5  mov     [rsp+128h+var_28], rax
0x1800078ad  mov     rbx, r8
0x1800078b0  mov     qword ptr [rdx], 0
0x1800078b7  mov     rsi, rdx
0x1800078ba  mov     rdi, rcx
0x1800078bd  xor     edx, edx; Val
0x1800078bf  lea     rcx, [rsp+128h+var_F8]; void *
0x1800078c4  mov     r8d, 0CCh; Size
0x1800078ca  call    memset_0
0x1800078cf  movups  xmm0, xmmword ptr [rbx]
0x1800078d2  mov     r9d, 40h ; '@'; cbMultiByte
0x1800078d8  lea     rax, [rsp+128h+WideCharStr]
0x1800078dd  movups  xmm1, xmmword ptr [rbx+10h]
0x1800078e1  lea     r8, [rbx+4Ch]; lpMultiByteStr
0x1800078e5  mov     [rsp+128h+cchWideChar], r9d; cchWideChar
0x1800078ea  movaps  [rsp+128h+var_F8], xmm0
0x1800078ef  xor     edx, edx; dwFlags
0x1800078f1  movups  xmm0, xmmword ptr [rbx+20h]
0x1800078f5  xor     ecx, ecx; CodePage
0x1800078f7  mov     [rsp+128h+lpWideCharStr], rax; lpWideCharStr
0x1800078fc  movaps  [rsp+128h+var_E8], xmm1
0x180007901  movups  xmm1, xmmword ptr [rbx+30h]
0x180007905  movaps  [rsp+128h+var_D8], xmm0
0x18000790a  movups  xmm0, xmmword ptr [rbx+3Ch]
0x18000790e  movaps  xmmword ptr [rsp+128h+var_C8], xmm1
0x180007913  movups  xmmword ptr [rsp+128h+var_C8+0Ch], xmm0
0x180007918  call    cs:__imp_MultiByteToWideChar
0x18000791e  mov     rax, [rdi]
0x180007921  lea     r8, [rsp+128h+var_F8]
0x180007926  mov     rdx, rsi
0x180007929  mov     rcx, rdi
0x18000792c  mov     rax, [rax+28h]
0x180007930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007935  mov     rcx, [rsp+128h+var_28]
0x18000793d  xor     rcx, rsp; StackCookie
0x180007940  call    __security_check_cookie
0x180007945  add     rsp, 110h
0x18000794c  pop     rdi
0x18000794d  pop     rsi
0x18000794e  pop     rbx
0x18000794f  retn
```
