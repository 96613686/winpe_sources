# AVISaveOptions

- ea: `0x1800032e0`
- end: `0x180003413`
- name: `AVISaveOptions`
- size: `307`
- prototype: `INT_PTR __stdcall(HWND hwnd, UINT uiFlags, int nStreams, PAVISTREAM *ppavi, LPAVICOMPRESSOPTIONS *plpOptions)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800032e0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180003334`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180003334`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800033fd`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800033fd`
- `USER32!DialogBoxParamW` at `0x1800033a3`
- `USER32!DialogBoxParamW` at `0x1800033a3`

## pseudocode

```c
INT_PTR __stdcall AVISaveOptions(
        HWND hwnd,
        UINT uiFlags,
        int nStreams,
        PAVISTREAM *ppavi,
        LPAVICOMPRESSOPTIONS *plpOptions)
{
  unsigned __int64 v7; // rdx
  _QWORD *v8; // rdi
  __int64 i; // r8
  LPAVICOMPRESSOPTIONS v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rax
  INT_PTR v13; // rax
  __int64 j; // r9
  LPAVICOMPRESSOPTIONS v15; // r8
  __int64 v16; // rcx
  INT_PTR v17; // rbx

  guiFlags = uiFlags;
  v7 = 56LL * (unsigned int)nStreams;
  gnNumStreams = nStreams;
  gnCurStream = -1;
  gapAVI = (__int64)ppavi;
  gapOpt = (__int64)plpOptions;
  if ( v7 > 0xFFFFFFFF )
    return 0;
  v8 = GlobalAlloc(0x40u, (unsigned int)v7);
  if ( !v8 )
    return 0;
  for ( i = 0; (int)i < nStreams; v8[v12 + 6] = *(_QWORD *)&v10->cbParms )
  {
    v10 = plpOptions[i];
    v11 = (unsigned int)i;
    i = (unsigned int)(i + 1);
    v12 = 7 * v11;
    *(_OWORD *)&v8[v12] = *(_OWORD *)&v10->fccType;
    *(_OWORD *)&v8[v12 + 2] = *(_OWORD *)&v10->dwBytesPerSecond;
    *(_OWORD *)&v8[v12 + 4] = *(_OWORD *)&v10->cbFormat;
  }
  v13 = DialogBoxParamW(ghMod, (LPCWSTR)0x6E, hwnd, (DLGPROC)AVICompressOptionsDlgProc, 0);
  if ( !v13 )
  {
    for ( j = 0; (int)j < nStreams; *(_QWORD *)&v15->cbParms = v8[7 * v16 + 6] )
    {
      v15 = plpOptions[j];
      v16 = (unsigned int)j;
      j = (unsigned int)(j + 1);
      *(_OWORD *)&v15->fccType = *(_OWORD *)&v8[7 * v16];
      *(_OWORD *)&v15->dwBytesPerSecond = *(_OWORD *)&v8[7 * v16 + 2];
      *(_OWORD *)&v15->cbFormat = *(_OWORD *)&v8[7 * v16 + 4];
    }
  }
  v17 = 0;
  if ( v13 != -1 )
    v17 = v13;
  GlobalFree(v8);
  return v17;
}

```

## disassembly

```asm
0x1800032e0  push    rbx
0x1800032e2  push    rbp
0x1800032e3  push    rsi
0x1800032e4  push    rdi
0x1800032e5  sub     rsp, 38h
0x1800032e9  mov     rsi, [rsp+58h+plpOptions]
0x1800032f1  mov     eax, 0FFFFFFFFh
0x1800032f6  mov     ebx, r8d
0x1800032f9  mov     rbp, rcx
0x1800032fc  mov     cs:guiFlags, edx
0x180003302  imul    rdx, rbx, 38h ; '8'
0x180003306  mov     cs:gnNumStreams, ebx
0x18000330c  mov     cs:gnCurStream, 0FFFFFFFFh
0x180003316  mov     cs:gapAVI, r9
0x18000331d  mov     cs:gapOpt, rsi
0x180003324  cmp     rdx, rax
0x180003327  ja      loc_180003408
0x18000332d  mov     edx, edx; dwBytes
0x18000332f  mov     ecx, 40h ; '@'; uFlags
0x180003334  call    cs:__imp_GlobalAlloc
0x18000333a  mov     rdi, rax
0x18000333d  test    rax, rax
0x180003340  jz      loc_180003408
0x180003346  xor     r8d, r8d
0x180003349  test    ebx, ebx
0x18000334b  jle     short loc_180003384
0x18000334d  mov     rdx, [rsi+r8*8]
0x180003351  mov     ecx, r8d
0x180003354  inc     r8d
0x180003357  imul    rax, rcx, 38h ; '8'
0x18000335b  movups  xmm0, xmmword ptr [rdx]
0x18000335e  movups  xmmword ptr [rax+rdi], xmm0
0x180003362  movups  xmm1, xmmword ptr [rdx+10h]
0x180003366  movups  xmmword ptr [rax+rdi+10h], xmm1
0x18000336b  movups  xmm0, xmmword ptr [rdx+20h]
0x18000336f  movups  xmmword ptr [rax+rdi+20h], xmm0
0x180003374  movsd   xmm1, qword ptr [rdx+30h]
0x180003379  movsd   qword ptr [rax+rdi+30h], xmm1
0x18000337f  cmp     r8d, ebx
0x180003382  jl      short loc_18000334D
0x180003384  mov     rcx, cs:ghMod; hInstance
0x18000338b  lea     r9, AVICompressOptionsDlgProc; lpDialogFunc
0x180003392  mov     r8, rbp; hWndParent
0x180003395  mov     [rsp+58h+dwInitParam], 0; dwInitParam
0x18000339e  mov     edx, 6Eh ; 'n'; lpTemplateName
0x1800033a3  call    cs:__imp_DialogBoxParamW
0x1800033a9  test    rax, rax
0x1800033ac  jnz     short loc_1800033F0
0x1800033ae  xor     r9d, r9d
0x1800033b1  test    ebx, ebx
0x1800033b3  jle     short loc_1800033F0
0x1800033b5  mov     r8, [rsi+r9*8]
0x1800033b9  mov     ecx, r9d
0x1800033bc  inc     r9d
0x1800033bf  imul    rdx, rcx, 38h ; '8'
0x1800033c3  movups  xmm0, xmmword ptr [rdx+rdi]
0x1800033c7  movups  xmmword ptr [r8], xmm0
0x1800033cb  movups  xmm1, xmmword ptr [rdx+rdi+10h]
0x1800033d0  movups  xmmword ptr [r8+10h], xmm1
0x1800033d5  movups  xmm0, xmmword ptr [rdx+rdi+20h]
0x1800033da  movups  xmmword ptr [r8+20h], xmm0
0x1800033df  movsd   xmm1, qword ptr [rdx+rdi+30h]
0x1800033e5  movsd   qword ptr [r8+30h], xmm1
0x1800033eb  cmp     r9d, ebx
0x1800033ee  jl      short loc_1800033B5
0x1800033f0  xor     ebx, ebx
0x1800033f2  mov     rcx, rdi; hMem
0x1800033f5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800033f9  cmovnz  rbx, rax
0x1800033fd  call    cs:__imp_GlobalFree
0x180003403  mov     rax, rbx
0x180003406  jmp     short loc_18000340A
0x180003408  xor     eax, eax
0x18000340a  add     rsp, 38h
0x18000340e  pop     rdi
0x18000340f  pop     rsi
0x180003410  pop     rbp
0x180003411  pop     rbx
0x180003412  retn
```
