# OpenFontFile

- ea: `0x180022614`
- end: `0x180022a18`
- name: `OpenFontFile`
- size: `1028`
- prototype: `char *__fastcall(HANDLE hPrinter)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180021650`

## callees

- `0x180022614`
- `0x180022a20`
- `0x180033e78`
- `0x18003a7ac`
- `0x180049d00`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180022795`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180022898`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800228d8`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180022969`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180022795`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180022898`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800228d8`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180022969`
- `WINSPOOL!GetPrinterDataW` at `0x180022873`
- `WINSPOOL!GetPrinterDataW` at `0x180022873`
- `WINSPOOL!GetPrinterDriverW` at `0x1800226b8`
- `WINSPOOL!GetPrinterDriverW` at `0x18002271c`
- `WINSPOOL!GetPrinterDriverW` at `0x1800226b8`
- `WINSPOOL!GetPrinterDriverW` at `0x18002271c`
- `KERNEL32!CloseHandle` at `0x1800229c1`
- `KERNEL32!CloseHandle` at `0x1800229c1`
- `KERNEL32!GetLastError` at `0x1800226cc`
- `KERNEL32!GetLastError` at `0x1800226cc`
- `KERNEL32!LocalFree` at `0x18002277f`
- `KERNEL32!LocalFree` at `0x1800227df`
- `KERNEL32!LocalFree` at `0x18002277f`
- `KERNEL32!LocalFree` at `0x1800227df`
- `KERNEL32!LocalAlloc` at `0x18002265d`
- `KERNEL32!LocalAlloc` at `0x1800226e7`
- `KERNEL32!LocalAlloc` at `0x18002265d`
- `KERNEL32!LocalAlloc` at `0x1800226e7`

## pseudocode

```c
char *__fastcall OpenFontFile(HANDLE hPrinter)
{
  char *result; // rax
  char *v3; // rbx
  char *v4; // r12
  BYTE *v5; // rax
  BYTE *v6; // rdi
  _WORD *v7; // r8
  __int64 v8; // r14
  _WORD *v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rdx
  _WORD *v12; // rcx
  wchar_t *v13; // rax
  __int64 v14; // r8
  const wchar_t *v15; // rcx
  bool v16; // zf
  __int64 v17; // rax
  char *v18; // r8
  char *v19; // rdx
  DWORD PrinterDataW; // eax
  wchar_t *v21; // rax
  const wchar_t *v22; // rax
  _WORD *v23; // rax
  __int64 v24; // rdx
  wchar_t *v25; // rax
  unsigned __int64 v26; // rdx
  wchar_t *v27; // rax
  _DWORD *v28; // rcx
  __int64 v29; // r8
  DWORD v30; // [rsp+30h] [rbp-D0h] BYREF
  DWORD pcbNeeded; // [rsp+34h] [rbp-CCh] BYREF
  DWORD pType; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE hObject[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pData[264]; // [rsp+50h] [rbp-B0h] BYREF

  v30 = 0;
  pType = 0;
  hObject[0] = 0;
  result = (char *)LocalAlloc(0, 0x258u);
  v3 = result;
  if ( result )
  {
    v4 = result + 576;
    *(_DWORD *)result = 1718514793;
    *((_QWORD *)result + 1) = hPrinter;
    *((_QWORD *)result + 2) = 0;
    *((_DWORD *)result + 143) = 0;
    *((_QWORD *)result + 72) = 0;
    pcbNeeded = 0;
    if ( !GetPrinterDriverW(hPrinter, 0, 3u, 0, 0, &pcbNeeded) && GetLastError() == 122 )
    {
      v5 = (BYTE *)LocalAlloc(0, pcbNeeded);
      v6 = v5;
      if ( v5 )
      {
        if ( GetPrinterDriverW(hPrinter, 0, 3u, v5, pcbNeeded, &pcbNeeded) )
        {
          v7 = (_WORD *)*((_QWORD *)v6 + 3);
          v8 = 2147483646;
          v9 = v3 + 24;
          v10 = 2147483646;
          v11 = 260;
          do
          {
            if ( !v10 )
              break;
            if ( !*v7 )
              break;
            *v9++ = *v7++;
            --v10;
            --v11;
          }
          while ( v11 );
          v12 = v9 - 1;
          if ( v11 )
            v12 = v9;
          *v12 = 0;
          LocalFree(v6);
          v13 = wcsrchr((const wchar_t *)v3 + 12, 0x5Cu);
          if ( v13 )
          {
            *v13 = 0;
            v27 = wcsrchr((const wchar_t *)v3 + 12, 0x5Cu);
            if ( v27 )
            {
              *v27 = 0;
              v25 = wcsrchr((const wchar_t *)v3 + 12, 0x5Cu);
              if ( v25 )
              {
                *v25 = 0;
                v24 = 260;
                v23 = v3 + 24;
                do
                {
                  if ( !*v23 )
                    break;
                  ++v23;
                  --v24;
                }
                while ( v24 );
                v14 = (260 - v24) & -(__int64)(v24 != 0);
                if ( v24 )
                {
                  v15 = L"\\unifont\\";
                  v17 = 260 - v14;
                  v16 = v14 == 260;
                  v18 = &v3[2 * v14 + 24];
                  if ( !v16 )
                  {
                    do
                    {
                      if ( !v8 )
                        break;
                      if ( !*v15 )
                        break;
                      *(_WORD *)v18 = *v15++;
                      v18 += 2;
                      --v8;
                      --v17;
                    }
                    while ( v17 );
                  }
                  v19 = v18 - 2;
                  if ( v17 )
                    v19 = v18;
                  *(_WORD *)v19 = 0;
                }
                v30 = 520;
                PrinterDataW = GetPrinterDataW(
                                 hPrinter,
                                 (LPWSTR)L"ExternalFontFile",
                                 &pType,
                                 (LPBYTE)pData,
                                 0x208u,
                                 &v30);
                if ( PrinterDataW == 234 || !PrinterDataW )
                {
                  v21 = wcsrchr(pData, 0x5Cu);
                  v22 = v21 ? v21 + 1 : pData;
                  StringCchCatW((STRSAFE_LPWSTR)v3 + 12, 0x104u, v22);
                  *((_QWORD *)v3 + 68) = MapFileIntoMemory((const WCHAR *)v3 + 12, (__int64)v4, &v30, hObject);
                  if ( *(_QWORD *)v4 )
                  {
                    CloseHandle(hObject[0]);
                    v28 = *(_DWORD **)v4;
                    *((_QWORD *)v3 + 69) = *(_QWORD *)v4;
                    if ( v30 >= 0x30 && *v28 == 826689109 && v28[1] == 65537 && v28[2] == 48 )
                    {
                      v29 = (unsigned int)v28[6];
                      if ( !(_DWORD)v29 )
                        goto LABEL_37;
                      v26 = 36LL * (unsigned int)v28[3];
                      if ( v26 <= 0xFFFFFFFF && (int)v26 + (int)v29 >= (unsigned int)v26 && v30 >= (int)v26 + (int)v29 )
                      {
                        *((_QWORD *)v3 + 70) = (char *)v28 + v29;
LABEL_37:
                        *((_DWORD *)v3 + 142) = 0;
                        *((_DWORD *)v3 + 143) = 1;
                        *((_QWORD *)v3 + 73) = 0;
                        *((_DWORD *)v3 + 148) = 0;
                        return v3;
                      }
                    }
                  }
                }
              }
            }
          }
        }
        else
        {
          LocalFree(v6);
        }
      }
    }
    FICloseFontFile(v3);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180022614  push    rbp
0x180022616  push    rbx
0x180022617  push    rsi
0x180022618  push    rdi
0x180022619  push    r12
0x18002261b  push    r13
0x18002261d  push    r14
0x18002261f  push    r15
0x180022621  lea     rbp, [rsp-178h]
0x180022629  sub     rsp, 278h
0x180022630  mov     rax, cs:__security_cookie
0x180022637  xor     rax, rsp
0x18002263a  mov     [rbp+1B0h+var_50], rax
0x180022641  xor     r13d, r13d
0x180022644  mov     r15, rcx
0x180022647  xor     ecx, ecx; uFlags
0x180022649  mov     [rsp+2B0h+var_280], r13d
0x18002264e  mov     edx, 258h; uBytes
0x180022653  mov     [rsp+2B0h+pType], r13d
0x180022658  mov     [rsp+2B0h+hObject], r13
0x18002265d  call    cs:__imp_LocalAlloc
0x180022664  nop     dword ptr [rax+rax+00h]
0x180022669  mov     rbx, rax
0x18002266c  test    rax, rax
0x18002266f  jz      loc_18002295B
0x180022675  lea     r12, [rax+240h]
0x18002267c  mov     dword ptr [rax], 666E7469h
0x180022682  mov     [rax+8], r15
0x180022686  lea     esi, [r13+3]
0x18002268a  mov     [rax+10h], r13
0x18002268e  xor     r9d, r9d; pDriverInfo
0x180022691  mov     [rax+23Ch], r13d
0x180022698  mov     r8d, esi; Level
0x18002269b  lea     rax, [rsp+2B0h+var_27C]
0x1800226a0  mov     [r12], r13
0x1800226a4  mov     [rsp+2B0h+pcbNeeded], rax; pcbNeeded
0x1800226a9  xor     edx, edx; pEnvironment
0x1800226ab  mov     rcx, r15; hPrinter
0x1800226ae  mov     [rsp+2B0h+cbBuf], r13d; cbBuf
0x1800226b3  mov     [rsp+2B0h+var_27C], r13d
0x1800226b8  call    cs:__imp_GetPrinterDriverW
0x1800226bf  nop     dword ptr [rax+rax+00h]
0x1800226c4  test    eax, eax
0x1800226c6  jnz     loc_1800227AA
0x1800226cc  call    cs:__imp_GetLastError
0x1800226d3  nop     dword ptr [rax+rax+00h]
0x1800226d8  cmp     eax, 7Ah ; 'z'
0x1800226db  jnz     loc_1800227AA
0x1800226e1  mov     edx, [rsp+2B0h+var_27C]; uBytes
0x1800226e5  xor     ecx, ecx; uFlags
0x1800226e7  call    cs:__imp_LocalAlloc
0x1800226ee  nop     dword ptr [rax+rax+00h]
0x1800226f3  mov     rdi, rax
0x1800226f6  test    rax, rax
0x1800226f9  jz      loc_1800227AA
0x1800226ff  lea     rax, [rsp+2B0h+var_27C]
0x180022704  mov     r9, rdi; pDriverInfo
0x180022707  mov     [rsp+2B0h+pcbNeeded], rax; pcbNeeded
0x18002270c  mov     r8d, esi; Level
0x18002270f  mov     eax, [rsp+2B0h+var_27C]
0x180022713  xor     edx, edx; pEnvironment
0x180022715  mov     rcx, r15; hPrinter
0x180022718  mov     [rsp+2B0h+cbBuf], eax; cbBuf
0x18002271c  call    cs:__imp_GetPrinterDriverW
0x180022723  nop     dword ptr [rax+rax+00h]
0x180022728  test    eax, eax
0x18002272a  jz      loc_1800227DC
0x180022730  mov     r8, [rdi+18h]
0x180022734  lea     rsi, [rbx+18h]
0x180022738  mov     r14d, 7FFFFFFEh
0x18002273e  mov     rax, rsi
0x180022741  mov     ecx, r14d
0x180022744  mov     edx, 104h
0x180022749  test    rcx, rcx
0x18002274c  jz      short loc_18002276D
0x18002274e  movzx   r9d, word ptr [r8]
0x180022752  test    r9w, r9w
0x180022756  jz      short loc_18002276D
0x180022758  mov     [rax], r9w
0x18002275c  add     r8, 2
0x180022760  add     rax, 2
0x180022764  dec     rcx
0x180022767  sub     rdx, 1
0x18002276b  jnz     short loc_180022749
0x18002276d  test    rdx, rdx
0x180022770  lea     rcx, [rax-2]
0x180022774  cmovnz  rcx, rax
0x180022778  mov     [rcx], r13w
0x18002277c  mov     rcx, rdi; hMem
0x18002277f  call    cs:__imp_LocalFree
0x180022786  nop     dword ptr [rax+rax+00h]
0x18002278b  mov     edi, 5Ch ; '\'
0x180022790  mov     rcx, rsi; Str
0x180022793  mov     edx, edi; Ch
0x180022795  call    cs:__imp_wcsrchr
0x18002279c  nop     dword ptr [rax+rax+00h]
0x1800227a1  test    rax, rax
0x1800227a4  jnz     loc_180022960
0x1800227aa  mov     rcx, rbx; hMem
0x1800227ad  call    FICloseFontFile
0x1800227b2  mov     rbx, r13
0x1800227b5  mov     rax, rbx
0x1800227b8  mov     rcx, [rbp+1B0h+var_50]
0x1800227bf  xor     rcx, rsp; StackCookie
0x1800227c2  call    __security_check_cookie
0x1800227c7  add     rsp, 278h
0x1800227ce  pop     r15
0x1800227d0  pop     r14
0x1800227d2  pop     r13
0x1800227d4  pop     r12
0x1800227d6  pop     rdi
0x1800227d7  pop     rsi
0x1800227d8  pop     rbx
0x1800227d9  pop     rbp
0x1800227da  retn
0x1800227dc  mov     rcx, rdi; hMem
0x1800227df  call    cs:__imp_LocalFree
0x1800227e6  nop     dword ptr [rax+rax+00h]
0x1800227eb  jmp     short loc_1800227AA
0x1800227ed  mov     rcx, rdi
0x1800227f0  mov     rax, rdx
0x1800227f3  sub     rcx, rdx
0x1800227f6  neg     rax
0x1800227f9  sbb     r8, r8
0x1800227fc  and     r8, rcx
0x1800227ff  test    rdx, rdx
0x180022802  jz      short loc_180022848
0x180022804  mov     rax, rdi
0x180022807  lea     rcx, aUnifont; "\\unifont\\"
0x18002280e  sub     rax, r8
0x180022811  lea     r8, [rsi+r8*2]
0x180022815  jz      short loc_180022839
0x180022817  test    r14, r14
0x18002281a  jz      short loc_180022839
0x18002281c  movzx   edx, word ptr [rcx]
0x18002281f  test    dx, dx
0x180022822  jz      short loc_180022839
0x180022824  mov     [r8], dx
0x180022828  add     rcx, 2
0x18002282c  add     r8, 2
0x180022830  dec     r14
0x180022833  sub     rax, 1
0x180022837  jnz     short loc_180022817
0x180022839  test    rax, rax
0x18002283c  lea     rdx, [r8-2]
0x180022840  cmovnz  rdx, r8
0x180022844  mov     [rdx], r13w
0x180022848  mov     ecx, 208h
0x18002284d  lea     rax, [rsp+2B0h+var_280]
0x180022852  mov     [rsp+2B0h+pcbNeeded], rax; pcbNeeded
0x180022857  lea     r9, [rsp+2B0h+pData]; pData
0x18002285c  mov     [rsp+2B0h+cbBuf], ecx; nSize
0x180022860  lea     r8, [rsp+2B0h+pType]; pType
0x180022865  mov     [rsp+2B0h+var_280], ecx
0x180022869  lea     rdx, aExternalfontfi; "ExternalFontFile"
0x180022870  mov     rcx, r15; hPrinter
0x180022873  call    cs:__imp_GetPrinterDataW
0x18002287a  nop     dword ptr [rax+rax+00h]
0x18002287f  cmp     eax, 0EAh
0x180022884  jz      short loc_18002288E
0x180022886  test    eax, eax
0x180022888  jnz     loc_1800227AA
0x18002288e  mov     edx, 5Ch ; '\'; Ch
0x180022893  lea     rcx, [rsp+2B0h+pData]; Str
0x180022898  call    cs:__imp_wcsrchr
0x18002289f  nop     dword ptr [rax+rax+00h]
0x1800228a4  test    rax, rax
0x1800228a7  jz      loc_180022983
0x1800228ad  add     rax, 2
0x1800228b1  jmp     loc_180022988
0x1800228b6  cmp     [rax], r13w
0x1800228ba  jz      loc_1800227ED
0x1800228c0  add     rax, 2
0x1800228c4  sub     rdx, 1
0x1800228c8  jnz     short loc_1800228B6
0x1800228ca  jmp     loc_1800227ED
0x1800228cf  mov     edx, edi; Ch
0x1800228d1  mov     [rax], r13w
0x1800228d5  mov     rcx, rsi; Str
0x1800228d8  call    cs:__imp_wcsrchr
0x1800228df  nop     dword ptr [rax+rax+00h]
0x1800228e4  test    rax, rax
0x1800228e7  jz      loc_1800227AA
0x1800228ed  mov     edi, 104h
0x1800228f2  mov     [rax], r13w
0x1800228f6  mov     edx, edi
0x1800228f8  mov     rax, rsi
0x1800228fb  jmp     short loc_1800228B6
0x1800228fd  mov     eax, [rcx+0Ch]
0x180022900  lea     rdx, [rax+rax*8]
0x180022904  mov     eax, 0FFFFFFFFh
0x180022909  shl     rdx, 2
0x18002290d  cmp     rdx, rax
0x180022910  ja      loc_1800227AA
0x180022916  lea     eax, [rdx+r8]
0x18002291a  cmp     eax, edx
0x18002291c  jb      loc_1800227AA
0x180022922  cmp     [rsp+2B0h+var_280], eax
0x180022926  jb      loc_1800227AA
0x18002292c  lea     rax, [rcx+r8]
0x180022930  mov     [rbx+230h], rax
0x180022937  mov     [rbx+238h], r13d
0x18002293e  mov     dword ptr [rbx+23Ch], 1
0x180022948  mov     [rbx+248h], r13
0x18002294f  mov     [rbx+250h], r13d
0x180022956  jmp     loc_1800227B5
0x18002295b  jmp     loc_1800227B8
0x180022960  mov     edx, edi; Ch
0x180022962  mov     [rax], r13w
0x180022966  mov     rcx, rsi; Str
0x180022969  call    cs:__imp_wcsrchr
0x180022970  nop     dword ptr [rax+rax+00h]
0x180022975  test    rax, rax
0x180022978  jz      loc_1800227AA
0x18002297e  jmp     loc_1800228CF
0x180022983  lea     rax, [rsp+2B0h+pData]
0x180022988  mov     r8, rax; pszSrc
0x18002298b  mov     rdx, rdi; cchDest
0x18002298e  mov     rcx, rsi; pszDest
0x180022991  call    StringCchCatW
0x180022996  lea     r9, [rsp+2B0h+hObject]
0x18002299b  mov     rdx, r12
0x18002299e  lea     r8, [rsp+2B0h+var_280]
0x1800229a3  mov     rcx, rsi
0x1800229a6  call    MapFileIntoMemory
0x1800229ab  mov     [rbx+220h], rax
0x1800229b2  cmp     [r12], r13
0x1800229b6  jz      loc_1800227AA
0x1800229bc  mov     rcx, [rsp+2B0h+hObject]; hObject
0x1800229c1  call    cs:__imp_CloseHandle
0x1800229c8  nop     dword ptr [rax+rax+00h]
0x1800229cd  mov     rcx, [r12]
0x1800229d1  mov     [rbx+228h], rcx
0x1800229d8  cmp     [rsp+2B0h+var_280], 30h ; '0'
0x1800229dd  jb      loc_1800227AA
0x1800229e3  cmp     dword ptr [rcx], 31464655h
0x1800229e9  jnz     loc_1800227AA
0x1800229ef  cmp     dword ptr [rcx+4], 10001h
0x1800229f6  jnz     loc_1800227AA
0x1800229fc  cmp     dword ptr [rcx+8], 30h ; '0'
0x180022a00  jnz     loc_1800227AA
0x180022a06  mov     r8d, [rcx+18h]
0x180022a0a  test    r8d, r8d
0x180022a0d  jz      loc_180022937
0x180022a13  jmp     loc_1800228FD
```
