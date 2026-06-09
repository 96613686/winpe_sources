# LocalPrintConfigData::GetFileByRole(PrinterDriverRole,bool,bool)

- ea: `0x180034f20`
- end: `0x1800354f5`
- name: `?GetFileByRole@LocalPrintConfigData@@UEAAPEBGW4PrinterDriverRole@@_N1@Z`
- size: `1493`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callees

- `0x18000298c`
- `0x18001fe90`
- `0x180034c5c`
- `0x180034f20`
- `0x18005d010`

## import_xrefs

- `WINSPOOL!GetPrinterDataW` at `0x180035044`
- `WINSPOOL!GetPrinterDataW` at `0x1800350b7`
- `WINSPOOL!GetPrinterDataW` at `0x1800353d5`
- `WINSPOOL!GetPrinterDataW` at `0x18003544b`
- `WINSPOOL!GetPrinterDataW` at `0x180035044`
- `WINSPOOL!GetPrinterDataW` at `0x1800350b7`
- `WINSPOOL!GetPrinterDataW` at `0x1800353d5`
- `WINSPOOL!GetPrinterDataW` at `0x18003544b`

## string_xrefs

- `0x1800351d7`: `unires.dll`
- `0x1800351fe`: `unires.dll`
- `0x180035085`: `V4_Merged_ConfigFile_Name`
- `0x180035039`: `PrintQueueV4DriverDirectory`
- `0x1800353bf`: `PrintQueueV4DriverDirectory`
- `0x18003523e`: `PCLXL.dll`
- `0x18003534d`: `PCL5ERES.dll`
- `0x1800354af`: `PCL4RES.dll`
- `0x1800354a6`: `PCL5URES.dll`

## pseudocode

```c
const wchar_t *__fastcall LocalPrintConfigData::GetFileByRole(__int64 a1, signed int a2, __int64 a3, char a4)
{
  char v6; // r12
  unsigned __int8 v7; // cl
  int v8; // eax
  LPBYTE v10; // rdi
  char v11; // si
  int v12; // edx
  int v13; // edx
  int v14; // edx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  void *v18; // rcx
  HRESULT v19; // eax
  __int64 v20; // rcx
  __int64 v21; // rax
  DWORD nSize; // r14d
  void *v23; // rcx
  signed int PrinterDataW; // eax
  bool v25; // sf
  __int64 v26; // rax
  int v27; // edx
  int v28; // edx
  int v29; // edx
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  int v34; // edx
  int v35; // edx
  int v36; // edx
  int v37; // edx
  const wchar_t *v38; // rdx
  wchar_t *v39; // rsi
  __int64 v40; // rcx
  const unsigned __int16 *v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // rax
  int v48; // edx
  int v49; // edx
  int v50; // edx
  BYTE *v51; // rax
  void *v52; // rcx
  HRESULT v53; // eax
  __int64 v54; // rdx
  __int64 v55; // rcx
  __int64 v56; // rax
  int v57; // r14d
  void *v58; // rcx
  BYTE *v59; // r15
  signed int v60; // eax
  bool v61; // sf
  __int64 v62; // rax
  DWORD pType; // [rsp+30h] [rbp-18h] BYREF
  DWORD v64; // [rsp+34h] [rbp-14h] BYREF
  DWORD v65[2]; // [rsp+38h] [rbp-10h] BYREF
  DWORD pcbNeeded; // [rsp+98h] [rbp+50h] BYREF

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
      v10 = (LPBYTE)(**(__int64 (__fastcall ***)(__int64, const wchar_t *))a1)(a1, L"unires.dll");
      if ( v10 )
      {
        if ( !a4 )
          return L"unires.dll";
        return (const wchar_t *)v10;
      }
      goto LABEL_141;
    }
    if ( a2 > 5 )
    {
      v27 = a2 - 6;
      if ( v27 )
      {
        v28 = v27 - 1;
        if ( v28 )
        {
          v29 = v28 - 2;
          if ( v29 )
          {
            if ( v29 != 1 )
              goto LABEL_141;
            if ( v7 )
              v30 = *(_QWORD *)(a1 + 104);
            else
              v30 = *(_QWORD *)(a1 + 96);
            if ( v30 )
              v10 = *(LPBYTE *)(v30 + 80);
          }
          else
          {
            if ( v7 )
              v31 = *(_QWORD *)(a1 + 104);
            else
              v31 = *(_QWORD *)(a1 + 96);
            if ( v31 )
              v10 = *(LPBYTE *)(v31 + 72);
          }
        }
        else
        {
          if ( v7 )
            v32 = *(_QWORD *)(a1 + 104);
          else
            v32 = *(_QWORD *)(a1 + 96);
          if ( v32 )
            v10 = *(LPBYTE *)(v32 + 64);
        }
      }
      else
      {
        if ( v7 )
          v33 = *(_QWORD *)(a1 + 104);
        else
          v33 = *(_QWORD *)(a1 + 96);
        if ( v33 )
          v10 = *(LPBYTE *)(v33 + 56);
      }
    }
    else if ( a2 == 5 )
    {
      if ( v7 )
        v26 = *(_QWORD *)(a1 + 104);
      else
        v26 = *(_QWORD *)(a1 + 96);
      if ( v26 )
        v10 = *(LPBYTE *)(v26 + 40);
    }
    else
    {
      if ( !a2 )
      {
        if ( **(_DWORD **)(a1 + 8) >= 4u && v7 )
          v10 = *(LPBYTE *)(a1 + 64);
        else
          v10 = *(LPBYTE *)(a1 + 32);
        goto LABEL_141;
      }
      v12 = a2 - 1;
      if ( !v12 )
      {
        v10 = *(LPBYTE *)(32LL * v7 + a1 + 40);
        goto LABEL_141;
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
                  &pcbNeeded) )
          {
            v19 = StringCchCatW((STRSAFE_LPWSTR)(a1 + 144), 0x104u, L"\\");
            a3 = 0;
            if ( v19 >= 0 )
            {
              v20 = -1;
              do
                ++v20;
              while ( *(_WORD *)(a1 + 144 + 2 * v20) );
              v64 = 0;
              v21 = (unsigned int)v20 + 72LL;
              nSize = 2 * (260 - v20);
              v23 = *(void **)(a1 + 112);
              *(_QWORD *)v65 = a1 + 2 * v21;
              PrinterDataW = GetPrinterDataW(v23, (LPWSTR)L"V4_Merged_ConfigFile_Name", 0, *(LPBYTE *)v65, nSize, &v64);
              v25 = PrinterDataW < 0;
              if ( PrinterDataW > 0 )
                v25 = 1;
              if ( !v25 )
              {
                v10 = *(LPBYTE *)v65;
                *(_WORD *)(a1 + 662) = 0;
                if ( a4 )
                  return (const wchar_t *)(a1 + 144);
                return (const wchar_t *)v10;
              }
            }
          }
        }
        else
        {
          v10 = *(LPBYTE *)(v17 + 32);
        }
        goto LABEL_141;
      }
      v14 = v13 - 1;
      if ( v14 )
      {
        if ( v14 != 1 )
        {
LABEL_141:
          if ( a4 && v11 )
          {
            if ( v10 )
            {
              LOBYTE(a3) = v6;
              return (const wchar_t *)(**(__int64 (__fastcall ***)(__int64, LPBYTE, __int64))a1)(a1, v10, a3);
            }
          }
          return (const wchar_t *)v10;
        }
        if ( v7 )
          v15 = *(_QWORD *)(a1 + 104);
        else
          v15 = *(_QWORD *)(a1 + 96);
        if ( v15 )
          v10 = *(LPBYTE *)(v15 + 48);
      }
      else
      {
        if ( v7 )
          v16 = *(_QWORD *)(a1 + 104);
        else
          v16 = *(_QWORD *)(a1 + 96);
        if ( v16 )
          v10 = *(LPBYTE *)(v16 + 32);
      }
    }
LABEL_28:
    v11 = 1;
    goto LABEL_141;
  }
  if ( a2 > 17 )
  {
    v48 = a2 - 18;
    if ( !v48 )
    {
      v38 = L"PCL4RES.dll";
      goto LABEL_140;
    }
    v49 = v48 - 1;
    if ( !v49 )
    {
      v38 = L"PCL5URES.dll";
      goto LABEL_140;
    }
    v50 = v49 - 1;
    if ( !v50 )
    {
      if ( v7 )
        v62 = *(_QWORD *)(a1 + 104);
      else
        v62 = *(_QWORD *)(a1 + 96);
      if ( v62 )
        v10 = *(LPBYTE *)(v62 + 112);
      goto LABEL_28;
    }
    if ( v50 != 1 )
      goto LABEL_141;
    v51 = *(BYTE **)(a1 + 664);
    if ( !v51 )
    {
      v51 = (BYTE *)operator new(0x208u, (const struct std::nothrow_t *)byte_18006C430);
      *(_QWORD *)(a1 + 664) = v51;
      if ( !v51 )
        goto LABEL_141;
    }
    v64 = 0;
    v52 = *(void **)(a1 + 112);
    v65[0] = 0;
    if ( GetPrinterDataW(v52, (LPWSTR)L"PrintQueueV4DriverDirectory", v65, v51, 0x208u, &v64) )
      goto LABEL_141;
    v53 = StringCchCatW(*(STRSAFE_LPWSTR *)(a1 + 664), 0x104u, L"\\");
    a3 = 0;
    if ( v53 < 0 )
      goto LABEL_141;
    v54 = *(_QWORD *)(a1 + 664);
    v55 = -1;
    do
      ++v55;
    while ( *(_WORD *)(v54 + 2 * v55) );
    v56 = (unsigned int)v55;
    v57 = 260 - v55;
    v58 = *(void **)(a1 + 112);
    pcbNeeded = 0;
    v59 = (BYTE *)(v54 + 2 * v56);
    v60 = GetPrinterDataW(v58, (LPWSTR)L"V4_PrintDeviceCapabilities", 0, v59, 2 * v57, &pcbNeeded);
    v61 = v60 < 0;
    if ( v60 > 0 )
      v61 = 1;
    if ( v61 )
      goto LABEL_141;
    *(_WORD *)(*(_QWORD *)(a1 + 664) + 518LL) = 0;
    if ( a4 )
      return *(const wchar_t **)(a1 + 664);
    else
      return (const wchar_t *)v59;
  }
  if ( a2 == 17 )
  {
    v38 = L"PCL5ERES.dll";
    goto LABEL_140;
  }
  v34 = a2 - 12;
  if ( !v34 )
  {
    if ( v7 )
      v47 = *(_QWORD *)(a1 + 104);
    else
      v47 = *(_QWORD *)(a1 + 96);
    if ( v47 )
      v10 = *(LPBYTE *)(v47 + 88);
    goto LABEL_28;
  }
  v35 = v34 - 1;
  if ( !v35 )
  {
    if ( v7 )
      v46 = *(_QWORD *)(a1 + 104);
    else
      v46 = *(_QWORD *)(a1 + 96);
    if ( v46 )
      v10 = *(LPBYTE *)(v46 + 104);
    goto LABEL_28;
  }
  v36 = v35 - 1;
  if ( v36 )
  {
    v37 = v36 - 1;
    if ( v37 )
    {
      if ( v37 != 1 )
        goto LABEL_141;
      v38 = L"PCLXL.dll";
LABEL_140:
      v10 = (LPBYTE)(**(__int64 (__fastcall ***)(__int64, const wchar_t *))a1)(a1, v38);
      goto LABEL_141;
    }
    if ( !a4 )
      return (const wchar_t *)v10;
    v39 = (wchar_t *)(a1 + 1192);
    v40 = -1;
    do
      ++v40;
    while ( v39[v40] );
    if ( v40 )
      return v39;
    v41 = (const unsigned __int16 *)(a1 + 2232);
  }
  else
  {
    if ( !a4 )
      return (const wchar_t *)v10;
    v42 = -1;
    v39 = (wchar_t *)(a1 + 672);
    v43 = -1;
    do
      ++v43;
    while ( v39[v43] );
    if ( v43 )
      return v39;
    v44 = *(_QWORD *)(a1 + 96);
    if ( v44 && *(_QWORD *)(v44 + 72) )
    {
      v41 = *(const unsigned __int16 **)(a1 + 128);
      if ( !v41 )
        return (const wchar_t *)v10;
    }
    else
    {
      v45 = *(_QWORD *)(a1 + 104);
      if ( !v45 || !*(_QWORD *)(v45 + 72) )
        return (const wchar_t *)v10;
      do
        ++v42;
      while ( *(_WORD *)(a1 + 2 * v42 + 1712) );
      if ( !v42 )
        return (const wchar_t *)v10;
      v41 = (const unsigned __int16 *)(a1 + 1712);
    }
  }
  if ( (int)GetCatalogPathFromInfPath(v41, v39, a3) >= 0 )
    return v39;
  return (const wchar_t *)v10;
}

```

## disassembly

```asm
0x180034f20  push    rbp
0x180034f22  push    rbx
0x180034f23  push    rsi
0x180034f24  push    rdi
0x180034f25  push    r12
0x180034f27  push    r13
0x180034f29  push    r14
0x180034f2b  push    r15
0x180034f2d  mov     rbp, rsp
0x180034f30  sub     rsp, 48h
0x180034f34  xor     r14d, r14d
0x180034f37  mov     rbx, rcx
0x180034f3a  mov     r13b, r9b
0x180034f3d  mov     r12b, r8b
0x180034f40  mov     cl, r14b
0x180034f43  cmp     edx, 15h
0x180034f46  ja      short loc_180034F52
0x180034f48  mov     eax, 20C004h
0x180034f4d  bt      eax, edx
0x180034f50  jb      short loc_180034F80
0x180034f52  test    byte ptr [rbx+78h], 8
0x180034f56  jz      short loc_180034F70
0x180034f58  test    r12b, r12b
0x180034f5b  jnz     short loc_180034F80
0x180034f5d  xor     eax, eax
0x180034f5f  add     rsp, 48h
0x180034f63  pop     r15
0x180034f65  pop     r14
0x180034f67  pop     r13
0x180034f69  pop     r12
0x180034f6b  pop     rdi
0x180034f6c  pop     rsi
0x180034f6d  pop     rbx
0x180034f6e  pop     rbp
0x180034f6f  retn
0x180034f70  test    byte ptr [rbx+78h], 10h
0x180034f74  jz      short loc_180034F7B
0x180034f76  mov     cl, r12b
0x180034f79  jmp     short loc_180034F80
0x180034f7b  test    r12b, r12b
0x180034f7e  jnz     short loc_180034F5D
0x180034f80  mov     rdi, r14
0x180034f83  mov     sil, r14b
0x180034f86  cmp     edx, 0Bh
0x180034f89  jg      loc_18003520A
0x180034f8f  jz      loc_1800351D4
0x180034f95  cmp     edx, 5
0x180034f98  jg      loc_18003513C
0x180034f9e  jz      loc_18003511C
0x180034fa4  test    edx, edx
0x180034fa6  jz      loc_1800350FD
0x180034fac  sub     edx, 1
0x180034faf  jz      loc_1800350EC
0x180034fb5  sub     edx, 1
0x180034fb8  jz      short loc_180035000
0x180034fba  sub     edx, 1
0x180034fbd  jz      short loc_180034FE1
0x180034fbf  cmp     edx, 1
0x180034fc2  jnz     loc_1800354C7
0x180034fc8  test    cl, cl
0x180034fca  jnz     short loc_180034FD2
0x180034fcc  mov     rax, [rbx+60h]
0x180034fd0  jmp     short loc_180034FD6
0x180034fd2  mov     rax, [rbx+68h]
0x180034fd6  test    rax, rax
0x180034fd9  jz      short loc_180034FF8
0x180034fdb  mov     rdi, [rax+30h]
0x180034fdf  jmp     short loc_180034FF8
0x180034fe1  test    cl, cl
0x180034fe3  jnz     short loc_180034FEB
0x180034fe5  mov     rax, [rbx+60h]
0x180034fe9  jmp     short loc_180034FEF
0x180034feb  mov     rax, [rbx+68h]
0x180034fef  test    rax, rax
0x180034ff2  jz      short loc_180034FF8
0x180034ff4  mov     rdi, [rax+20h]
0x180034ff8  mov     sil, 1
0x180034ffb  jmp     loc_1800354C7
0x180035000  mov     rax, [rbx+8]
0x180035004  cmp     dword ptr [rax], 4
0x180035007  jnb     short loc_180035012
0x180035009  mov     rdi, [rax+20h]
0x18003500d  jmp     loc_1800354C7
0x180035012  mov     rcx, [rbx+70h]; hPrinter
0x180035016  lea     rax, [rbp+arg_8]
0x18003501a  mov     [rsp+48h+pcbNeeded], rax; pcbNeeded
0x18003501f  lea     r15, [rbx+90h]
0x180035026  mov     r9, r15; pData
0x180035029  mov     [rsp+48h+nSize], 208h; nSize
0x180035031  lea     r8, [rbp+pType]; pType
0x180035035  mov     [rbp+arg_8], r14d
0x180035039  lea     rdx, aPrintqueuev4dr; "PrintQueueV4DriverDirectory"
0x180035040  mov     [rbp+pType], r14d
0x180035044  call    cs:__imp_GetPrinterDataW
0x18003504a  test    eax, eax
0x18003504c  jnz     loc_1800354C7
0x180035052  mov     r14d, 104h
0x180035058  lea     r8, SubBlock; "\\"
0x18003505f  mov     edx, r14d; cchDest
0x180035062  mov     rcx, r15; pszDest
0x180035065  call    StringCchCatW
0x18003506a  xor     r8d, r8d; pType
0x18003506d  test    eax, eax
0x18003506f  js      loc_1800354C7
0x180035075  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180035079  inc     rcx
0x18003507c  cmp     [r15+rcx*2], r8w
0x180035081  jnz     short loc_180035079
0x180035083  mov     eax, ecx
0x180035085  lea     rdx, aV4MergedConfig; "V4_Merged_ConfigFile_Name"
0x18003508c  sub     r14d, ecx
0x18003508f  mov     [rbp+var_14], r8d
0x180035093  add     rax, 48h ; 'H'
0x180035097  lea     rcx, [rbp+var_14]
0x18003509b  mov     [rsp+48h+pcbNeeded], rcx; pcbNeeded
0x1800350a0  add     r14d, r14d
0x1800350a3  mov     rcx, [rbx+70h]; hPrinter
0x1800350a7  mov     [rsp+48h+nSize], r14d; nSize
0x1800350ac  lea     rax, [rbx+rax*2]
0x1800350b0  mov     r9, rax; pData
0x1800350b3  mov     qword ptr [rbp+var_10], rax
0x1800350b7  call    cs:__imp_GetPrinterDataW
0x1800350bd  xor     r14d, r14d
0x1800350c0  test    eax, eax
0x1800350c2  jle     short loc_1800350CE
0x1800350c4  movzx   eax, ax
0x1800350c7  or      eax, 80070000h
0x1800350cc  test    eax, eax
0x1800350ce  js      loc_1800354C7
0x1800350d4  mov     rdi, qword ptr [rbp+var_10]
0x1800350d8  test    r13b, r13b
0x1800350db  mov     [rbx+296h], r14w
0x1800350e3  cmovnz  rdi, r15
0x1800350e7  jmp     loc_1800354ED
0x1800350ec  movzx   eax, cl
0x1800350ef  shl     rax, 5
0x1800350f3  mov     rdi, [rax+rbx+28h]
0x1800350f8  jmp     loc_1800354C7
0x1800350fd  mov     rax, [rbx+8]
0x180035101  cmp     dword ptr [rax], 4
0x180035104  jb      short loc_180035113
0x180035106  test    cl, cl
0x180035108  jz      short loc_180035113
0x18003510a  mov     rdi, [rbx+40h]
0x18003510e  jmp     loc_1800354C7
0x180035113  mov     rdi, [rbx+20h]
0x180035117  jmp     loc_1800354C7
0x18003511c  test    cl, cl
0x18003511e  jnz     short loc_180035126
0x180035120  mov     rax, [rbx+60h]
0x180035124  jmp     short loc_18003512A
0x180035126  mov     rax, [rbx+68h]
0x18003512a  test    rax, rax
0x18003512d  jz      loc_180034FF8
0x180035133  mov     rdi, [rax+28h]
0x180035137  jmp     loc_180034FF8
0x18003513c  sub     edx, 6
0x18003513f  jz      short loc_1800351B4
0x180035141  sub     edx, 1
0x180035144  jz      short loc_180035194
0x180035146  sub     edx, 2
0x180035149  jz      short loc_180035174
0x18003514b  cmp     edx, 1
0x18003514e  jnz     loc_1800354C7
0x180035154  test    cl, cl
0x180035156  jnz     short loc_18003515E
0x180035158  mov     rax, [rbx+60h]
0x18003515c  jmp     short loc_180035162
0x18003515e  mov     rax, [rbx+68h]
0x180035162  test    rax, rax
0x180035165  jz      loc_180034FF8
0x18003516b  mov     rdi, [rax+50h]
0x18003516f  jmp     loc_180034FF8
0x180035174  test    cl, cl
0x180035176  jnz     short loc_18003517E
0x180035178  mov     rax, [rbx+60h]
0x18003517c  jmp     short loc_180035182
0x18003517e  mov     rax, [rbx+68h]
0x180035182  test    rax, rax
0x180035185  jz      loc_180034FF8
0x18003518b  mov     rdi, [rax+48h]
0x18003518f  jmp     loc_180034FF8
0x180035194  test    cl, cl
0x180035196  jnz     short loc_18003519E
0x180035198  mov     rax, [rbx+60h]
0x18003519c  jmp     short loc_1800351A2
0x18003519e  mov     rax, [rbx+68h]
0x1800351a2  test    rax, rax
0x1800351a5  jz      loc_180034FF8
0x1800351ab  mov     rdi, [rax+40h]
0x1800351af  jmp     loc_180034FF8
0x1800351b4  test    cl, cl
0x1800351b6  jnz     short loc_1800351BE
0x1800351b8  mov     rax, [rbx+60h]
0x1800351bc  jmp     short loc_1800351C2
0x1800351be  mov     rax, [rbx+68h]
0x1800351c2  test    rax, rax
0x1800351c5  jz      loc_180034FF8
0x1800351cb  mov     rdi, [rax+38h]
0x1800351cf  jmp     loc_180034FF8
0x1800351d4  mov     rax, [rbx]
0x1800351d7  lea     rdx, aUniresDll; "unires.dll"
0x1800351de  mov     rcx, rbx
0x1800351e1  mov     rax, [rax]
0x1800351e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800351e9  mov     rdi, rax
0x1800351ec  test    rax, rax
0x1800351ef  jz      loc_1800354C7
0x1800351f5  test    r13b, r13b
0x1800351f8  jnz     loc_1800354ED
0x1800351fe  lea     rdi, aUniresDll; "unires.dll"
0x180035205  jmp     loc_1800354ED
0x18003520a  cmp     edx, 11h
0x18003520d  jg      loc_180035359
0x180035213  jz      loc_18003534D
0x180035219  sub     edx, 0Ch
0x18003521c  jz      loc_18003532D
0x180035222  sub     edx, 1
0x180035225  jz      loc_18003530D
0x18003522b  sub     edx, 1
0x18003522e  jz      short loc_18003528C
0x180035230  sub     edx, 1
0x180035233  jz      short loc_18003524A
0x180035235  cmp     edx, 1
0x180035238  jnz     loc_1800354C7
0x18003523e  lea     rdx, aPclxlDll; "PCLXL.dll"
0x180035245  jmp     loc_1800354B6
0x18003524a  test    r13b, r13b
0x18003524d  jz      loc_1800354ED
0x180035253  lea     rsi, [rbx+4A8h]
0x18003525a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003525e  inc     rcx
0x180035261  cmp     [rsi+rcx*2], r14w
0x180035266  jnz     short loc_18003525E
0x180035268  test    rcx, rcx
0x18003526b  jnz     short loc_180035284
0x18003526d  lea     rcx, [rbx+8B8h]; unsigned __int16 *
0x180035274  mov     rdx, rsi; Str
0x180035277  call    ?GetCatalogPathFromInfPath@@YAJPEBGPEAGK@Z; GetCatalogPathFromInfPath(ushort const *,ushort *,ulong)
0x18003527c  test    eax, eax
0x18003527e  js      loc_1800354ED
0x180035284  mov     rdi, rsi
0x180035287  jmp     loc_1800354ED
0x18003528c  test    r13b, r13b
0x18003528f  jz      loc_1800354ED
0x180035295  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180035299  lea     rsi, [rbx+2A0h]
0x1800352a0  mov     rax, rcx
0x1800352a3  inc     rax
0x1800352a6  cmp     [rsi+rax*2], r14w
0x1800352ab  jnz     short loc_1800352A3
0x1800352ad  test    rax, rax
0x1800352b0  jnz     short loc_180035284
0x1800352b2  mov     rax, [rbx+60h]
0x1800352b6  test    rax, rax
0x1800352b9  jz      short loc_1800352D3
0x1800352bb  cmp     [rax+48h], r14
0x1800352bf  jz      short loc_1800352D3
0x1800352c1  mov     rcx, [rbx+80h]
0x1800352c8  test    rcx, rcx
0x1800352cb  jz      loc_1800354ED
0x1800352d1  jmp     short loc_180035274
0x1800352d3  mov     rax, [rbx+68h]
0x1800352d7  test    rax, rax
0x1800352da  jz      loc_1800354ED
0x1800352e0  cmp     [rax+48h], r14
0x1800352e4  jz      loc_1800354ED
0x1800352ea  inc     rcx
0x1800352ed  cmp     [rbx+rcx*2+6B0h], r14w
0x1800352f6  jnz     short loc_1800352EA
0x1800352f8  test    rcx, rcx
0x1800352fb  jz      loc_1800354ED
0x180035301  lea     rcx, [rbx+6B0h]
0x180035308  jmp     loc_180035274
0x18003530d  test    cl, cl
0x18003530f  jnz     short loc_180035317
0x180035311  mov     rax, [rbx+60h]
0x180035315  jmp     short loc_18003531B
0x180035317  mov     rax, [rbx+68h]
0x18003531b  test    rax, rax
0x18003531e  jz      loc_180034FF8
0x180035324  mov     rdi, [rax+68h]
0x180035328  jmp     loc_180034FF8
0x18003532d  test    cl, cl
0x18003532f  jnz     short loc_180035337
0x180035331  mov     rax, [rbx+60h]
0x180035335  jmp     short loc_18003533B
0x180035337  mov     rax, [rbx+68h]
0x18003533b  test    rax, rax
0x18003533e  jz      loc_180034FF8
0x180035344  mov     rdi, [rax+58h]
0x180035348  jmp     loc_180034FF8
0x18003534d  lea     rdx, aPcl5eresDll; "PCL5ERES.dll"
0x180035354  jmp     loc_1800354B6
0x180035359  sub     edx, 12h
0x18003535c  jz      loc_1800354AF
0x180035362  sub     edx, 1
0x180035365  jz      loc_1800354A6
0x18003536b  sub     edx, 1
0x18003536e  jz      loc_180035486
  ... truncated ...
```
