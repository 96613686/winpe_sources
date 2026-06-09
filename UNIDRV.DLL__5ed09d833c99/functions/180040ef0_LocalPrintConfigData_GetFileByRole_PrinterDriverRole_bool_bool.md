# LocalPrintConfigData::GetFileByRole(PrinterDriverRole,bool,bool)

- ea: `0x180040ef0`
- end: `0x180041481`
- name: `?GetFileByRole@LocalPrintConfigData@@UEAAPEBGW4PrinterDriverRole@@_N1@Z`
- size: `1425`
- prototype: `const wchar_t *__fastcall(__int64, signed int, __int64, char)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callees

- `0x180033e78`
- `0x180040ef0`
- `0x1800487bc`
- `0x18004987c`
- `0x18004a728`
- `0x180053be4`
- `0x180077010`

## import_xrefs

- `WINSPOOL!GetPrinterDataW` at `0x18004101c`
- `WINSPOOL!GetPrinterDataW` at `0x18004138a`
- `WINSPOOL!GetPrinterDataW` at `0x18004101c`
- `WINSPOOL!GetPrinterDataW` at `0x18004138a`

## string_xrefs

- `0x180041010`: `PrintQueueV4DriverDirectory`
- `0x180041373`: `PrintQueueV4DriverDirectory`
- `0x180041188`: `unires.dll`
- `0x1800411af`: `unires.dll`
- `0x1800411ef`: `PCLXL.dll`
- `0x1800412fe`: `PCL5ERES.dll`
- `0x18004143b`: `PCL4RES.dll`
- `0x180041432`: `PCL5URES.dll`

## pseudocode

```c
const wchar_t *__fastcall LocalPrintConfigData::GetFileByRole(__int64 a1, signed int a2, __int64 a3, char a4)
{
  char v6; // r15
  unsigned __int8 v7; // cl
  int v8; // eax
  __int64 v10; // rdi
  char v11; // si
  int v12; // edx
  int v13; // edx
  int v14; // edx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  void *v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // r12
  __int64 v21; // rax
  int v22; // edx
  int v23; // edx
  int v24; // edx
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  int v29; // edx
  int v30; // edx
  int v31; // edx
  int v32; // edx
  const wchar_t *v33; // rdx
  wchar_t *v34; // rsi
  __int64 v35; // rcx
  const unsigned __int16 *v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  int v43; // edx
  int v44; // edx
  int v45; // edx
  BYTE *v46; // rax
  void *v47; // rcx
  __int64 v48; // rdx
  __int64 v49; // rcx
  BYTE *v50; // r14
  __int64 v51; // rax
  DWORD pType; // [rsp+30h] [rbp-58h] BYREF
  DWORD v53; // [rsp+34h] [rbp-54h] BYREF
  DWORD v54[20]; // [rsp+38h] [rbp-50h] BYREF
  DWORD pcbNeeded; // [rsp+98h] [rbp+10h] BYREF

  v6 = a3;
  v7 = 0;
  if ( (unsigned int)a2 > 0x15 || (v8 = 2146308, !_bittest(&v8, a2)) )
  {
    if ( (*(_BYTE *)(a1 + 120) & 8) != 0 )
    {
      if ( !(_BYTE)a3 )
        return 0;
    }
    else if ( (*(_BYTE *)(a1 + 120) & 0x10) != 0 )
    {
      v7 = a3;
    }
    else if ( (_BYTE)a3 )
    {
      return 0;
    }
  }
  v10 = 0;
  v11 = 0;
  if ( a2 <= 11 )
  {
    if ( a2 == 11 )
    {
      v10 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *))a1)(a1, L"unires.dll");
      if ( v10 )
      {
        if ( !a4 )
          return L"unires.dll";
        return (const wchar_t *)v10;
      }
      goto LABEL_137;
    }
    if ( a2 > 5 )
    {
      v22 = a2 - 6;
      if ( v22 )
      {
        v23 = v22 - 1;
        if ( v23 )
        {
          v24 = v23 - 2;
          if ( v24 )
          {
            if ( v24 != 1 )
              goto LABEL_137;
            if ( v7 )
              v25 = *(_QWORD *)(a1 + 104);
            else
              v25 = *(_QWORD *)(a1 + 96);
            if ( v25 )
              v10 = *(_QWORD *)(v25 + 80);
          }
          else
          {
            if ( v7 )
              v26 = *(_QWORD *)(a1 + 104);
            else
              v26 = *(_QWORD *)(a1 + 96);
            if ( v26 )
              v10 = *(_QWORD *)(v26 + 72);
          }
        }
        else
        {
          if ( v7 )
            v27 = *(_QWORD *)(a1 + 104);
          else
            v27 = *(_QWORD *)(a1 + 96);
          if ( v27 )
            v10 = *(_QWORD *)(v27 + 64);
        }
      }
      else
      {
        if ( v7 )
          v28 = *(_QWORD *)(a1 + 104);
        else
          v28 = *(_QWORD *)(a1 + 96);
        if ( v28 )
          v10 = *(_QWORD *)(v28 + 56);
      }
    }
    else if ( a2 == 5 )
    {
      if ( v7 )
        v21 = *(_QWORD *)(a1 + 104);
      else
        v21 = *(_QWORD *)(a1 + 96);
      if ( v21 )
        v10 = *(_QWORD *)(v21 + 40);
    }
    else
    {
      if ( !a2 )
      {
        if ( **(_DWORD **)(a1 + 8) >= 4u && v7 )
          v10 = *(_QWORD *)(a1 + 64);
        else
          v10 = *(_QWORD *)(a1 + 32);
        goto LABEL_137;
      }
      v12 = a2 - 1;
      if ( !v12 )
      {
        v10 = *(_QWORD *)(32LL * v7 + a1 + 40);
        goto LABEL_137;
      }
      v13 = v12 - 1;
      if ( !v13 )
      {
        v17 = *(_QWORD *)(a1 + 8);
        if ( *(_DWORD *)v17 >= 4u )
        {
          v18 = *(void **)(a1 + 112);
          pcbNeeded = 0;
          pType = 0;
          if ( !GetPrinterDataW(
                  v18,
                  (LPWSTR)L"PrintQueueV4DriverDirectory",
                  &pType,
                  (LPBYTE)(a1 + 144),
                  0x208u,
                  &pcbNeeded)
            && StringCchCatW((STRSAFE_LPWSTR)(a1 + 144), 0x104u, L"\\") >= 0 )
          {
            v19 = -1;
            do
              ++v19;
            while ( *(_WORD *)(a1 + 144 + 2 * v19) );
            v20 = a1 + 2LL * (unsigned int)v19;
            if ( GetMergedDataFile(*(void **)(a1 + 112), (BYTE *)(v20 + 144), 260 - v19) >= 0 )
            {
              v10 = v20 + 144;
              *(_WORD *)(a1 + 662) = 0;
              if ( a4 )
                return (const wchar_t *)(a1 + 144);
              return (const wchar_t *)v10;
            }
          }
        }
        else
        {
          v10 = *(_QWORD *)(v17 + 32);
        }
        goto LABEL_137;
      }
      v14 = v13 - 1;
      if ( v14 )
      {
        if ( v14 != 1 )
        {
LABEL_137:
          if ( a4 && v11 )
          {
            if ( v10 )
            {
              LOBYTE(a3) = v6;
              return (const wchar_t *)(**(__int64 (__fastcall ***)(__int64, __int64, __int64))a1)(a1, v10, a3);
            }
          }
          return (const wchar_t *)v10;
        }
        if ( v7 )
          v15 = *(_QWORD *)(a1 + 104);
        else
          v15 = *(_QWORD *)(a1 + 96);
        if ( v15 )
          v10 = *(_QWORD *)(v15 + 48);
      }
      else
      {
        if ( v7 )
          v16 = *(_QWORD *)(a1 + 104);
        else
          v16 = *(_QWORD *)(a1 + 96);
        if ( v16 )
          v10 = *(_QWORD *)(v16 + 32);
      }
    }
LABEL_28:
    v11 = 1;
    goto LABEL_137;
  }
  if ( a2 > 17 )
  {
    v43 = a2 - 18;
    if ( !v43 )
    {
      v33 = L"PCL4RES.dll";
      goto LABEL_136;
    }
    v44 = v43 - 1;
    if ( !v44 )
    {
      v33 = L"PCL5URES.dll";
      goto LABEL_136;
    }
    v45 = v44 - 1;
    if ( !v45 )
    {
      if ( v7 )
        v51 = *(_QWORD *)(a1 + 104);
      else
        v51 = *(_QWORD *)(a1 + 96);
      if ( v51 )
        v10 = *(_QWORD *)(v51 + 112);
      goto LABEL_28;
    }
    if ( v45 != 1 )
      goto LABEL_137;
    v46 = *(BYTE **)(a1 + 664);
    if ( !v46 )
    {
      v46 = (BYTE *)operator new(0x208u, (const struct std::nothrow_t *)byte_180081401);
      *(_QWORD *)(a1 + 664) = v46;
      if ( !v46 )
        goto LABEL_137;
    }
    v53 = 0;
    v47 = *(void **)(a1 + 112);
    v54[0] = 0;
    if ( GetPrinterDataW(v47, (LPWSTR)L"PrintQueueV4DriverDirectory", v54, v46, 0x208u, &v53) )
      goto LABEL_137;
    if ( StringCchCatW(*(STRSAFE_LPWSTR *)(a1 + 664), 0x104u, L"\\") < 0 )
      goto LABEL_137;
    v48 = *(_QWORD *)(a1 + 664);
    v49 = -1;
    do
      ++v49;
    while ( *(_WORD *)(v48 + 2 * v49) );
    v50 = (BYTE *)(v48 + 2LL * (unsigned int)v49);
    if ( GetPrintDeviceCapabilitiesFile(*(void **)(a1 + 112), v50, 260 - v49) < 0 )
      goto LABEL_137;
    *(_WORD *)(*(_QWORD *)(a1 + 664) + 518LL) = 0;
    if ( a4 )
      return *(const wchar_t **)(a1 + 664);
    else
      return (const wchar_t *)v50;
  }
  if ( a2 == 17 )
  {
    v33 = L"PCL5ERES.dll";
    goto LABEL_136;
  }
  v29 = a2 - 12;
  if ( !v29 )
  {
    if ( v7 )
      v42 = *(_QWORD *)(a1 + 104);
    else
      v42 = *(_QWORD *)(a1 + 96);
    if ( v42 )
      v10 = *(_QWORD *)(v42 + 88);
    goto LABEL_28;
  }
  v30 = v29 - 1;
  if ( !v30 )
  {
    if ( v7 )
      v41 = *(_QWORD *)(a1 + 104);
    else
      v41 = *(_QWORD *)(a1 + 96);
    if ( v41 )
      v10 = *(_QWORD *)(v41 + 104);
    goto LABEL_28;
  }
  v31 = v30 - 1;
  if ( v31 )
  {
    v32 = v31 - 1;
    if ( v32 )
    {
      if ( v32 != 1 )
        goto LABEL_137;
      v33 = L"PCLXL.dll";
LABEL_136:
      v10 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *))a1)(a1, v33);
      goto LABEL_137;
    }
    if ( !a4 )
      return (const wchar_t *)v10;
    v34 = (wchar_t *)(a1 + 1192);
    v35 = -1;
    do
      ++v35;
    while ( v34[v35] );
    if ( v35 )
      return v34;
    v36 = (const unsigned __int16 *)(a1 + 2232);
  }
  else
  {
    if ( !a4 )
      return (const wchar_t *)v10;
    v37 = -1;
    v34 = (wchar_t *)(a1 + 672);
    v38 = -1;
    do
      ++v38;
    while ( v34[v38] );
    if ( v38 )
      return v34;
    v39 = *(_QWORD *)(a1 + 96);
    if ( v39 && *(_QWORD *)(v39 + 72) )
    {
      v36 = *(const unsigned __int16 **)(a1 + 128);
      if ( !v36 )
        return (const wchar_t *)v10;
    }
    else
    {
      v40 = *(_QWORD *)(a1 + 104);
      if ( !v40 || !*(_QWORD *)(v40 + 72) )
        return (const wchar_t *)v10;
      do
        ++v37;
      while ( *(_WORD *)(a1 + 2 * v37 + 1712) );
      if ( !v37 )
        return (const wchar_t *)v10;
      v36 = (const unsigned __int16 *)(a1 + 1712);
    }
  }
  if ( (int)GetCatalogPathFromInfPath(v36, v34) >= 0 )
    return v34;
  return (const wchar_t *)v10;
}

```

## disassembly

```asm
0x180040ef0  push    rbx
0x180040ef2  push    rbp
0x180040ef3  push    rsi
0x180040ef4  push    rdi
0x180040ef5  push    r12
0x180040ef7  push    r13
0x180040ef9  push    r14
0x180040efb  push    r15
0x180040efd  sub     rsp, 48h
0x180040f01  xor     r12d, r12d
0x180040f04  mov     rbx, rcx
0x180040f07  mov     r13b, r9b
0x180040f0a  mov     r15b, r8b
0x180040f0d  mov     cl, r12b
0x180040f10  cmp     edx, 15h
0x180040f13  ja      short loc_180040F1F
0x180040f15  mov     eax, 20C004h
0x180040f1a  bt      eax, edx
0x180040f1d  jb      short loc_180040F4E
0x180040f1f  test    byte ptr [rbx+78h], 8
0x180040f23  jz      short loc_180040F3E
0x180040f25  test    r15b, r15b
0x180040f28  jnz     short loc_180040F4E
0x180040f2a  xor     eax, eax
0x180040f2c  add     rsp, 48h
0x180040f30  pop     r15
0x180040f32  pop     r14
0x180040f34  pop     r13
0x180040f36  pop     r12
0x180040f38  pop     rdi
0x180040f39  pop     rsi
0x180040f3a  pop     rbp
0x180040f3b  pop     rbx
0x180040f3c  retn
0x180040f3e  test    byte ptr [rbx+78h], 10h
0x180040f42  jz      short loc_180040F49
0x180040f44  mov     cl, r15b
0x180040f47  jmp     short loc_180040F4E
0x180040f49  test    r15b, r15b
0x180040f4c  jnz     short loc_180040F2A
0x180040f4e  mov     rdi, r12
0x180040f51  mov     sil, r12b
0x180040f54  cmp     edx, 0Bh
0x180040f57  jg      loc_1800411BB
0x180040f5d  jz      loc_180041185
0x180040f63  cmp     edx, 5
0x180040f66  jg      loc_1800410ED
0x180040f6c  jz      loc_1800410CD
0x180040f72  test    edx, edx
0x180040f74  jz      loc_1800410AE
0x180040f7a  sub     edx, 1
0x180040f7d  jz      loc_18004109D
0x180040f83  sub     edx, 1
0x180040f86  jz      short loc_180040FCE
0x180040f88  sub     edx, 1
0x180040f8b  jz      short loc_180040FAF
0x180040f8d  cmp     edx, 1
0x180040f90  jnz     loc_180041453
0x180040f96  test    cl, cl
0x180040f98  jnz     short loc_180040FA0
0x180040f9a  mov     rax, [rbx+60h]
0x180040f9e  jmp     short loc_180040FA4
0x180040fa0  mov     rax, [rbx+68h]
0x180040fa4  test    rax, rax
0x180040fa7  jz      short loc_180040FC6
0x180040fa9  mov     rdi, [rax+30h]
0x180040fad  jmp     short loc_180040FC6
0x180040faf  test    cl, cl
0x180040fb1  jnz     short loc_180040FB9
0x180040fb3  mov     rax, [rbx+60h]
0x180040fb7  jmp     short loc_180040FBD
0x180040fb9  mov     rax, [rbx+68h]
0x180040fbd  test    rax, rax
0x180040fc0  jz      short loc_180040FC6
0x180040fc2  mov     rdi, [rax+20h]
0x180040fc6  mov     sil, 1
0x180040fc9  jmp     loc_180041453
0x180040fce  mov     rax, [rbx+8]
0x180040fd2  cmp     dword ptr [rax], 4
0x180040fd5  jnb     short loc_180040FE0
0x180040fd7  mov     rdi, [rax+20h]
0x180040fdb  jmp     loc_180041453
0x180040fe0  mov     rcx, [rbx+70h]; hPrinter
0x180040fe4  lea     rax, [rsp+88h+arg_8]
0x180040fec  mov     [rsp+88h+pcbNeeded], rax; pcbNeeded
0x180040ff1  lea     r14, [rbx+90h]
0x180040ff8  mov     r9, r14; pData
0x180040ffb  mov     [rsp+88h+nSize], 208h; nSize
0x180041003  lea     r8, [rsp+88h+pType]; pType
0x180041008  mov     [rsp+88h+arg_8], r12d
0x180041010  lea     rdx, aPrintqueuev4dr; "PrintQueueV4DriverDirectory"
0x180041017  mov     [rsp+88h+pType], r12d
0x18004101c  call    cs:__imp_GetPrinterDataW
0x180041023  nop     dword ptr [rax+rax+00h]
0x180041028  test    eax, eax
0x18004102a  jnz     loc_180041453
0x180041030  mov     ebp, 104h
0x180041035  lea     r8, asc_180082C18; "\\"
0x18004103c  mov     edx, ebp; cchDest
0x18004103e  mov     rcx, r14; pszDest
0x180041041  call    StringCchCatW
0x180041046  test    eax, eax
0x180041048  js      loc_180041453
0x18004104e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180041052  inc     rcx
0x180041055  cmp     [r14+rcx*2], r12w
0x18004105a  jnz     short loc_180041052
0x18004105c  mov     eax, ecx
0x18004105e  sub     ebp, ecx
0x180041060  mov     rcx, [rbx+70h]; void *
0x180041064  mov     r8d, ebp; unsigned int
0x180041067  lea     r12, [rbx+rax*2]
0x18004106b  lea     rdx, [r12+90h]; unsigned __int16 *
0x180041073  call    ?GetMergedDataFile@@YAJPEAXPEAGK@Z; GetMergedDataFile(void *,ushort *,ulong)
0x180041078  test    eax, eax
0x18004107a  js      loc_180041453
0x180041080  xor     eax, eax
0x180041082  lea     rdi, [r12+90h]
0x18004108a  test    r13b, r13b
0x18004108d  mov     [rbx+296h], ax
0x180041094  cmovnz  rdi, r14
0x180041098  jmp     loc_180041479
0x18004109d  movzx   eax, cl
0x1800410a0  shl     rax, 5
0x1800410a4  mov     rdi, [rax+rbx+28h]
0x1800410a9  jmp     loc_180041453
0x1800410ae  mov     rax, [rbx+8]
0x1800410b2  cmp     dword ptr [rax], 4
0x1800410b5  jb      short loc_1800410C4
0x1800410b7  test    cl, cl
0x1800410b9  jz      short loc_1800410C4
0x1800410bb  mov     rdi, [rbx+40h]
0x1800410bf  jmp     loc_180041453
0x1800410c4  mov     rdi, [rbx+20h]
0x1800410c8  jmp     loc_180041453
0x1800410cd  test    cl, cl
0x1800410cf  jnz     short loc_1800410D7
0x1800410d1  mov     rax, [rbx+60h]
0x1800410d5  jmp     short loc_1800410DB
0x1800410d7  mov     rax, [rbx+68h]
0x1800410db  test    rax, rax
0x1800410de  jz      loc_180040FC6
0x1800410e4  mov     rdi, [rax+28h]
0x1800410e8  jmp     loc_180040FC6
0x1800410ed  sub     edx, 6
0x1800410f0  jz      short loc_180041165
0x1800410f2  sub     edx, 1
0x1800410f5  jz      short loc_180041145
0x1800410f7  sub     edx, 2
0x1800410fa  jz      short loc_180041125
0x1800410fc  cmp     edx, 1
0x1800410ff  jnz     loc_180041453
0x180041105  test    cl, cl
0x180041107  jnz     short loc_18004110F
0x180041109  mov     rax, [rbx+60h]
0x18004110d  jmp     short loc_180041113
0x18004110f  mov     rax, [rbx+68h]
0x180041113  test    rax, rax
0x180041116  jz      loc_180040FC6
0x18004111c  mov     rdi, [rax+50h]
0x180041120  jmp     loc_180040FC6
0x180041125  test    cl, cl
0x180041127  jnz     short loc_18004112F
0x180041129  mov     rax, [rbx+60h]
0x18004112d  jmp     short loc_180041133
0x18004112f  mov     rax, [rbx+68h]
0x180041133  test    rax, rax
0x180041136  jz      loc_180040FC6
0x18004113c  mov     rdi, [rax+48h]
0x180041140  jmp     loc_180040FC6
0x180041145  test    cl, cl
0x180041147  jnz     short loc_18004114F
0x180041149  mov     rax, [rbx+60h]
0x18004114d  jmp     short loc_180041153
0x18004114f  mov     rax, [rbx+68h]
0x180041153  test    rax, rax
0x180041156  jz      loc_180040FC6
0x18004115c  mov     rdi, [rax+40h]
0x180041160  jmp     loc_180040FC6
0x180041165  test    cl, cl
0x180041167  jnz     short loc_18004116F
0x180041169  mov     rax, [rbx+60h]
0x18004116d  jmp     short loc_180041173
0x18004116f  mov     rax, [rbx+68h]
0x180041173  test    rax, rax
0x180041176  jz      loc_180040FC6
0x18004117c  mov     rdi, [rax+38h]
0x180041180  jmp     loc_180040FC6
0x180041185  mov     rax, [rbx]
0x180041188  lea     rdx, aUniresDll; "unires.dll"
0x18004118f  mov     rcx, rbx
0x180041192  mov     rax, [rax]
0x180041195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004119a  mov     rdi, rax
0x18004119d  test    rax, rax
0x1800411a0  jz      loc_180041453
0x1800411a6  test    r13b, r13b
0x1800411a9  jnz     loc_180041479
0x1800411af  lea     rdi, aUniresDll; "unires.dll"
0x1800411b6  jmp     loc_180041479
0x1800411bb  cmp     edx, 11h
0x1800411be  jg      loc_18004130A
0x1800411c4  jz      loc_1800412FE
0x1800411ca  sub     edx, 0Ch
0x1800411cd  jz      loc_1800412DE
0x1800411d3  sub     edx, 1
0x1800411d6  jz      loc_1800412BE
0x1800411dc  sub     edx, 1
0x1800411df  jz      short loc_18004123D
0x1800411e1  sub     edx, 1
0x1800411e4  jz      short loc_1800411FB
0x1800411e6  cmp     edx, 1
0x1800411e9  jnz     loc_180041453
0x1800411ef  lea     rdx, aPclxlDll; "PCLXL.dll"
0x1800411f6  jmp     loc_180041442
0x1800411fb  test    r13b, r13b
0x1800411fe  jz      loc_180041479
0x180041204  lea     rsi, [rbx+4A8h]
0x18004120b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004120f  inc     rcx
0x180041212  cmp     [rsi+rcx*2], r12w
0x180041217  jnz     short loc_18004120F
0x180041219  test    rcx, rcx
0x18004121c  jnz     short loc_180041235
0x18004121e  lea     rcx, [rbx+8B8h]; unsigned __int16 *
0x180041225  mov     rdx, rsi; Str
0x180041228  call    ?GetCatalogPathFromInfPath@@YAJPEBGPEAGK@Z; GetCatalogPathFromInfPath(ushort const *,ushort *,ulong)
0x18004122d  test    eax, eax
0x18004122f  js      loc_180041479
0x180041235  mov     rdi, rsi
0x180041238  jmp     loc_180041479
0x18004123d  test    r13b, r13b
0x180041240  jz      loc_180041479
0x180041246  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004124a  lea     rsi, [rbx+2A0h]
0x180041251  mov     rax, rcx
0x180041254  inc     rax
0x180041257  cmp     [rsi+rax*2], r12w
0x18004125c  jnz     short loc_180041254
0x18004125e  test    rax, rax
0x180041261  jnz     short loc_180041235
0x180041263  mov     rax, [rbx+60h]
0x180041267  test    rax, rax
0x18004126a  jz      short loc_180041284
0x18004126c  cmp     [rax+48h], r12
0x180041270  jz      short loc_180041284
0x180041272  mov     rcx, [rbx+80h]
0x180041279  test    rcx, rcx
0x18004127c  jz      loc_180041479
0x180041282  jmp     short loc_180041225
0x180041284  mov     rax, [rbx+68h]
0x180041288  test    rax, rax
0x18004128b  jz      loc_180041479
0x180041291  cmp     [rax+48h], r12
0x180041295  jz      loc_180041479
0x18004129b  inc     rcx
0x18004129e  cmp     [rbx+rcx*2+6B0h], r12w
0x1800412a7  jnz     short loc_18004129B
0x1800412a9  test    rcx, rcx
0x1800412ac  jz      loc_180041479
0x1800412b2  lea     rcx, [rbx+6B0h]
0x1800412b9  jmp     loc_180041225
0x1800412be  test    cl, cl
0x1800412c0  jnz     short loc_1800412C8
0x1800412c2  mov     rax, [rbx+60h]
0x1800412c6  jmp     short loc_1800412CC
0x1800412c8  mov     rax, [rbx+68h]
0x1800412cc  test    rax, rax
0x1800412cf  jz      loc_180040FC6
0x1800412d5  mov     rdi, [rax+68h]
0x1800412d9  jmp     loc_180040FC6
0x1800412de  test    cl, cl
0x1800412e0  jnz     short loc_1800412E8
0x1800412e2  mov     rax, [rbx+60h]
0x1800412e6  jmp     short loc_1800412EC
0x1800412e8  mov     rax, [rbx+68h]
0x1800412ec  test    rax, rax
0x1800412ef  jz      loc_180040FC6
0x1800412f5  mov     rdi, [rax+58h]
0x1800412f9  jmp     loc_180040FC6
0x1800412fe  lea     rdx, aPcl5eresDll; "PCL5ERES.dll"
0x180041305  jmp     loc_180041442
0x18004130a  sub     edx, 12h
0x18004130d  jz      loc_18004143B
0x180041313  sub     edx, 1
0x180041316  jz      loc_180041432
0x18004131c  sub     edx, 1
0x18004131f  jz      loc_180041412
0x180041325  cmp     edx, 1
0x180041328  jnz     loc_180041453
0x18004132e  mov     rax, [rbx+298h]
0x180041335  test    rax, rax
0x180041338  jnz     short loc_18004135B
0x18004133a  lea     rdx, byte_180081401; struct std::nothrow_t *
0x180041341  mov     ecx, 208h; unsigned __int64
0x180041346  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004134b  mov     [rbx+298h], rax
0x180041352  test    rax, rax
0x180041355  jz      loc_180041453
0x18004135b  lea     rcx, [rsp+88h+var_54]
  ... truncated ...
```
