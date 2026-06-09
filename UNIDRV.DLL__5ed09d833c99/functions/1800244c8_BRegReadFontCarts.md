# BRegReadFontCarts

- ea: `0x1800244c8`
- end: `0x1800246e9`
- name: `BRegReadFontCarts`
- size: `545`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180024d0c`

## callees

- `0x1800244c8`
- `0x180049d00`
- `0x18004a71c`
- `0x180058cd8`

## import_xrefs

- `WINSPOOL!GetPrinterDataW` at `0x18002454a`
- `WINSPOOL!GetPrinterDataW` at `0x1800245f4`
- `WINSPOOL!GetPrinterDataW` at `0x18002454a`
- `WINSPOOL!GetPrinterDataW` at `0x1800245f4`
- `KERNEL32!LocalFree` at `0x180024609`
- `KERNEL32!LocalFree` at `0x1800246c2`
- `KERNEL32!LocalFree` at `0x1800246d6`
- `KERNEL32!LocalFree` at `0x180024609`
- `KERNEL32!LocalFree` at `0x1800246c2`
- `KERNEL32!LocalFree` at `0x1800246d6`
- `KERNEL32!LocalAlloc` at `0x1800245b9`
- `KERNEL32!LocalAlloc` at `0x1800245b9`
- `KERNEL32!SetLastError` at `0x180024571`
- `KERNEL32!SetLastError` at `0x180024617`
- `KERNEL32!SetLastError` at `0x180024571`
- `KERNEL32!SetLastError` at `0x180024617`

## pseudocode

```c
__int64 __fastcall BRegReadFontCarts(__int64 a1)
{
  __int64 v1; // rsi
  void *v2; // rbx
  int v3; // r14d
  __int64 v4; // r15
  DWORD PrinterDataW; // eax
  wchar_t *v7; // rdi
  DWORD v8; // ebx
  size_t v9; // rdx
  __int64 v10; // rax
  int i; // edx
  unsigned __int16 *v12; // rcx
  int v13; // r10d
  int v14; // r8d
  DWORD pcbNeeded; // [rsp+30h] [rbp-79h] BYREF
  DWORD pType; // [rsp+34h] [rbp-75h] BYREF
  DWORD v17; // [rsp+38h] [rbp-71h] BYREF
  BYTE *v18; // [rsp+40h] [rbp-69h] BYREF
  wchar_t psz[64]; // [rsp+50h] [rbp-59h] BYREF

  v1 = *(_QWORD *)(a1 + 4136);
  v2 = *(void **)(a1 + 24);
  pType = 0;
  pcbNeeded = 0;
  v3 = *(_DWORD *)(v1 + 208);
  *(_DWORD *)(v1 + 212) = 0;
  if ( !v3 )
    return 1;
  v4 = *(_QWORD *)(v1 + 200);
  pType = 7;
  PrinterDataW = GetPrinterDataW(v2, (LPWSTR)L"FontCart", &pType, 0, 0, &pcbNeeded);
  if ( !PrinterDataW )
    return 0;
  if ( PrinterDataW == 2 )
    return 1;
  if ( PrinterDataW != 122 && PrinterDataW != 234 )
  {
    SetLastError(PrinterDataW);
    return 1;
  }
  if ( !pcbNeeded )
    return 0;
  v18 = (BYTE *)LocalAlloc(0x40u, pcbNeeded);
  v7 = (wchar_t *)v18;
  if ( !v18 )
    return 0;
  v8 = GetPrinterDataW(v2, (LPWSTR)L"FontCart", &pType, v18, pcbNeeded, &pcbNeeded);
  if ( v8 )
  {
    LocalFree(v7);
    SetLastError(v8);
    return 0;
  }
  v17 = pcbNeeded >> 1;
LABEL_14:
  while ( *(_WORD *)v18 )
  {
    memset_0(psz, 0, sizeof(psz));
    if ( !v17 )
    {
      LocalFree(v7);
      return 0;
    }
    VGetFromBuffer(psz, v9, (const wchar_t **)&v18, (int *)&v17);
    v10 = v4;
    for ( i = 0; i < v3; ++i )
    {
      if ( v10 )
      {
        v12 = (unsigned __int16 *)(v10 + 8);
        do
        {
          v13 = *(unsigned __int16 *)((char *)&psz[-4] + (_QWORD)v12 - v10);
          v14 = *v12 - v13;
          if ( v14 )
            break;
          ++v12;
        }
        while ( v13 );
        if ( !v14 )
        {
          *(_DWORD *)(v10 + 136) = 1;
          ++*(_DWORD *)(v1 + 212);
          goto LABEL_14;
        }
      }
      v10 += 144;
    }
  }
  LocalFree(v7);
  return 1;
}

```

## disassembly

```asm
0x1800244c8  mov     [rsp-8+arg_8], rbx
0x1800244cd  mov     [rsp-8+arg_10], rsi
0x1800244d2  push    rbp
0x1800244d3  push    rdi
0x1800244d4  push    r12
0x1800244d6  push    r14
0x1800244d8  push    r15
0x1800244da  lea     rbp, [rsp-37h]
0x1800244df  sub     rsp, 0E0h
0x1800244e6  mov     rax, cs:__security_cookie
0x1800244ed  xor     rax, rsp
0x1800244f0  mov     [rbp+57h+var_30], rax
0x1800244f4  mov     rsi, [rcx+1028h]
0x1800244fb  xor     r12d, r12d
0x1800244fe  mov     rbx, [rcx+18h]
0x180024502  mov     [rbp+57h+pType], r12d
0x180024506  mov     [rbp+57h+var_D0], r12d
0x18002450a  mov     r14d, [rsi+0D0h]
0x180024511  mov     [rsi+0D4h], r12d
0x180024518  test    r14d, r14d
0x18002451b  jz      short loc_18002457D
0x18002451d  mov     r15, [rsi+0C8h]
0x180024524  lea     rax, [rbp+57h+var_D0]
0x180024528  mov     [rsp+100h+pcbNeeded], rax; pcbNeeded
0x18002452d  lea     r8, [rbp+57h+pType]; pType
0x180024531  xor     r9d, r9d; pData
0x180024534  mov     [rsp+100h+nSize], r12d; nSize
0x180024539  lea     rdx, aFontcart; "FontCart"
0x180024540  mov     [rbp+57h+pType], 7
0x180024547  mov     rcx, rbx; hPrinter
0x18002454a  call    cs:__imp_GetPrinterDataW
0x180024551  nop     dword ptr [rax+rax+00h]
0x180024556  test    eax, eax
0x180024558  jz      loc_180024623
0x18002455e  cmp     eax, 2
0x180024561  jz      short loc_18002457D
0x180024563  cmp     eax, 7Ah ; 'z'
0x180024566  jz      short loc_1800245AB
0x180024568  cmp     eax, 0EAh
0x18002456d  jz      short loc_1800245AB
0x18002456f  mov     ecx, eax; dwErrCode
0x180024571  call    cs:__imp_SetLastError
0x180024578  nop     dword ptr [rax+rax+00h]
0x18002457d  mov     eax, 1
0x180024582  mov     rcx, [rbp+57h+var_30]
0x180024586  xor     rcx, rsp; StackCookie
0x180024589  call    __security_check_cookie
0x18002458e  lea     r11, [rsp+100h+var_20]
0x180024596  mov     rbx, [r11+38h]
0x18002459a  mov     rsi, [r11+40h]
0x18002459e  mov     rsp, r11
0x1800245a1  pop     r15
0x1800245a3  pop     r14
0x1800245a5  pop     r12
0x1800245a7  pop     rdi
0x1800245a8  pop     rbp
0x1800245a9  retn
0x1800245ab  mov     eax, [rbp+57h+var_D0]
0x1800245ae  test    eax, eax
0x1800245b0  jz      short loc_180024623
0x1800245b2  mov     edx, eax; uBytes
0x1800245b4  mov     ecx, 40h ; '@'; uFlags
0x1800245b9  call    cs:__imp_LocalAlloc
0x1800245c0  nop     dword ptr [rax+rax+00h]
0x1800245c5  mov     [rbp+57h+var_C0], rax
0x1800245c9  mov     rdi, rax
0x1800245cc  test    rax, rax
0x1800245cf  jz      short loc_180024623
0x1800245d1  mov     r8d, [rbp+57h+var_D0]
0x1800245d5  lea     rax, [rbp+57h+var_D0]
0x1800245d9  mov     [rsp+100h+pcbNeeded], rax; pcbNeeded
0x1800245de  lea     rdx, aFontcart; "FontCart"
0x1800245e5  mov     [rsp+100h+nSize], r8d; nSize
0x1800245ea  mov     r9, rdi; pData
0x1800245ed  lea     r8, [rbp+57h+pType]; pType
0x1800245f1  mov     rcx, rbx; hPrinter
0x1800245f4  call    cs:__imp_GetPrinterDataW
0x1800245fb  nop     dword ptr [rax+rax+00h]
0x180024600  mov     ebx, eax
0x180024602  test    eax, eax
0x180024604  jz      short loc_18002462A
0x180024606  mov     rcx, rdi; hMem
0x180024609  call    cs:__imp_LocalFree
0x180024610  nop     dword ptr [rax+rax+00h]
0x180024615  mov     ecx, ebx; dwErrCode
0x180024617  call    cs:__imp_SetLastError
0x18002461e  nop     dword ptr [rax+rax+00h]
0x180024623  xor     eax, eax
0x180024625  jmp     loc_180024582
0x18002462a  mov     eax, [rbp+57h+var_D0]
0x18002462d  mov     ebx, 1
0x180024632  shr     eax, 1
0x180024634  mov     [rbp+57h+var_C8], eax
0x180024637  mov     rax, [rbp+57h+var_C0]
0x18002463b  cmp     [rax], r12w
0x18002463f  jz      loc_1800246D3
0x180024645  xor     edx, edx; Val
0x180024647  lea     rcx, [rbp+57h+psz]; void *
0x18002464b  mov     r8d, 80h; Size
0x180024651  call    memset_0
0x180024656  cmp     [rbp+57h+var_C8], r12d
0x18002465a  jz      short loc_1800246BF
0x18002465c  lea     r9, [rbp+57h+var_C8]
0x180024660  lea     r8, [rbp+57h+var_C0]
0x180024664  lea     rcx, [rbp+57h+psz]; psz
0x180024668  call    VGetFromBuffer
0x18002466d  mov     rax, r15
0x180024670  mov     edx, r12d
0x180024673  cmp     edx, r14d
0x180024676  jge     short loc_180024637
0x180024678  test    rax, rax
0x18002467b  jz      short loc_1800246A4
0x18002467d  lea     rcx, [rax+8]
0x180024681  lea     r9, [rbp+57h+psz]
0x180024685  sub     r9, rcx
0x180024688  movzx   r8d, word ptr [rcx]
0x18002468c  movzx   r10d, word ptr [rcx+r9]
0x180024691  sub     r8d, r10d
0x180024694  jnz     short loc_18002469F
0x180024696  add     rcx, 2
0x18002469a  test    r10d, r10d
0x18002469d  jnz     short loc_180024688
0x18002469f  test    r8d, r8d
0x1800246a2  jz      short loc_1800246AE
0x1800246a4  add     edx, ebx
0x1800246a6  add     rax, 90h
0x1800246ac  jmp     short loc_180024673
0x1800246ae  mov     [rax+88h], ebx
0x1800246b4  add     [rsi+0D4h], ebx
0x1800246ba  jmp     loc_180024637
0x1800246bf  mov     rcx, rdi; hMem
0x1800246c2  call    cs:__imp_LocalFree
0x1800246c9  nop     dword ptr [rax+rax+00h]
0x1800246ce  jmp     loc_180024623
0x1800246d3  mov     rcx, rdi; hMem
0x1800246d6  call    cs:__imp_LocalFree
0x1800246dd  nop     dword ptr [rax+rax+00h]
0x1800246e2  mov     eax, ebx
0x1800246e4  jmp     loc_180024582
```
