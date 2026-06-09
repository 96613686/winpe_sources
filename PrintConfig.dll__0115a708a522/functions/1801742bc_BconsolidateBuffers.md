# BconsolidateBuffers

- ea: `0x1801742bc`
- end: `0x180174647`
- name: `BconsolidateBuffers`
- size: `907`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, __int64, _QWORD *, DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180174c64`

## callees

- `0x180003400`
- `0x18016a374`
- `0x18016c854`
- `0x1801742bc`
- `0x1801b56bc`

## import_xrefs

- `KERNEL32!WriteFile` at `0x18017457d`
- `KERNEL32!WriteFile` at `0x18017457d`
- `KERNEL32!DeleteFileW` at `0x180174516`
- `KERNEL32!DeleteFileW` at `0x1801745b5`
- `KERNEL32!DeleteFileW` at `0x180174516`
- `KERNEL32!DeleteFileW` at `0x1801745b5`
- `KERNEL32!GetFileAttributesExW` at `0x180174503`
- `KERNEL32!GetFileAttributesExW` at `0x180174503`
- `KERNEL32!CreateFileW` at `0x180174551`
- `KERNEL32!CreateFileW` at `0x180174551`
- `KERNEL32!CloseHandle` at `0x1801745a1`
- `KERNEL32!CloseHandle` at `0x1801745a1`
- `KERNEL32!LocalFree` at `0x1801745c4`
- `KERNEL32!LocalFree` at `0x1801745e4`
- `KERNEL32!LocalFree` at `0x1801745c4`
- `KERNEL32!LocalFree` at `0x1801745e4`
- `KERNEL32!LocalAlloc` at `0x1801743a8`
- `KERNEL32!LocalAlloc` at `0x1801743a8`

## pseudocode

```c
__int64 __fastcall BconsolidateBuffers(STRSAFE_LPCWSTR pszSrc, __int64 a2, _QWORD *a3, DWORD *a4)
{
  __int64 v4; // r12
  __int64 v8; // rax
  int i; // edx
  DWORD v10; // ebx
  unsigned int v11; // r9d
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // rax
  unsigned __int64 v15; // r8
  unsigned int v16; // eax
  char *v17; // rax
  char *v18; // rsi
  __int64 v19; // r15
  __int64 v20; // xmm0_8
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  __int128 v30; // xmm0
  __int128 v31; // xmm1
  wchar_t *GPDfilename; // rax
  WCHAR *v33; // rdi
  HANDLE FileW; // rax
  void *v35; // r15
  BOOL v36; // r12d
  DWORD *v37; // rax
  __int64 result; // rax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  DWORD *v40; // [rsp+48h] [rbp-B8h]
  _OWORD v41[13]; // [rsp+50h] [rbp-B0h]
  __int64 v42; // [rsp+120h] [rbp+20h]
  _OWORD FileInformation[2]; // [rsp+130h] [rbp+30h] BYREF
  int v44; // [rsp+150h] [rbp+50h]

  v4 = 0;
  v40 = a4;
  if ( a3 )
    *a3 = 0;
  v8 = 1;
  for ( i = 0; i < 4; ++i )
  {
    *(_DWORD *)(a2 + 24 * v8 + 12) = *(_DWORD *)(a2 + 24 * v8 + 8);
    v8 = (unsigned int)(i + 11);
  }
  v10 = 288;
  v11 = 0;
  *(_DWORD *)(a2 + 24 * v8 + 12) = *(_DWORD *)(a2 + 24 * v8 + 8);
  *(_DWORD *)(a2 + 60) = *(_DWORD *)(a2 + 56);
  *(_DWORD *)(a2 + 372) = *(_DWORD *)(a2 + 368);
  *(_DWORD *)(a2 + 396) = *(_DWORD *)(a2 + 392);
  do
  {
    v12 = 3LL * v11;
    *((_DWORD *)v41 + v12) = v10;
    v13 = *(unsigned int *)(a2 + 24LL * v11 + 16);
    v14 = *(unsigned int *)(a2 + 24LL * v11 + 12);
    *((_DWORD *)v41 + v12 + 2) = v13;
    v15 = v14 * v13;
    *((_DWORD *)v41 + v12 + 1) = v14;
    if ( v15 > 0xFFFFFFFF )
      goto LABEL_29;
    v16 = v15 + v10;
    if ( (unsigned int)v15 + v10 < (unsigned int)v15 || v16 + 3 < v16 )
    {
      v10 = -1;
      goto LABEL_29;
    }
    v10 = (v16 + 3) & 0xFFFFFFFC;
    ++v11;
  }
  while ( v11 < 0x12 );
  v17 = (char *)LocalAlloc(0, v10);
  v18 = v17;
  if ( !v17 )
  {
LABEL_29:
    WriteDbgTraceErrorGpd("BconsolidateBuffers", "Fatal: unable to alloc requested memory: %d bytes.", v10);
    result = 0;
    *(_DWORD *)(a2 + 2224) = 2;
    *(_DWORD *)(a2 + 2220) = 3;
    return result;
  }
  *(_DWORD *)(a2 + 720) = v10;
  v19 = 0;
  *(_QWORD *)(a2 + 768) = 0;
  *(_QWORD *)(a2 + 748) = 0;
  *(_OWORD *)v17 = *(_OWORD *)(a2 + 720);
  *((_OWORD *)v17 + 1) = *(_OWORD *)(a2 + 736);
  *((_OWORD *)v17 + 2) = *(_OWORD *)(a2 + 752);
  *((_OWORD *)v17 + 3) = *(_OWORD *)(a2 + 768);
  v20 = *(_QWORD *)(a2 + 784);
  *(_OWORD *)(v17 + 72) = v41[0];
  v21 = v41[2];
  *((_QWORD *)v17 + 8) = v20;
  *(_OWORD *)(v17 + 88) = v41[1];
  v22 = v41[3];
  *(_OWORD *)(v17 + 104) = v21;
  v23 = v41[4];
  *(_OWORD *)(v17 + 120) = v22;
  v24 = v41[5];
  *(_OWORD *)(v17 + 136) = v23;
  v25 = v41[6];
  *(_OWORD *)(v17 + 152) = v24;
  v26 = v41[7];
  *(_OWORD *)(v17 + 168) = v25;
  v27 = v41[8];
  *(_OWORD *)(v17 + 184) = v26;
  v28 = v41[9];
  *(_OWORD *)(v17 + 200) = v27;
  v29 = v41[10];
  *(_OWORD *)(v17 + 216) = v28;
  v30 = v41[11];
  *(_OWORD *)(v17 + 232) = v29;
  v31 = v41[12];
  *(_OWORD *)(v17 + 248) = v30;
  *(_OWORD *)(v17 + 264) = v31;
  *((_QWORD *)v17 + 35) = v42;
  do
  {
    memcpy_0(
      &v18[*(unsigned int *)((char *)v41 + v4)],
      *(const void **)(a2 + 24 * v19++),
      (unsigned int)(*(_DWORD *)((char *)v41 + v4 + 4) * *(_DWORD *)((char *)v41 + v4 + 8)));
    v4 += 12;
  }
  while ( v19 != 18 );
  NumberOfBytesWritten = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  v44 = 0;
  GPDfilename = pwstrGenerateGPDfilename(pszSrc);
  v33 = GPDfilename;
  if ( GPDfilename )
  {
    if ( !GetFileAttributesExW(GPDfilename, GetFileExInfoStandard, FileInformation) || DeleteFileW(v33) )
    {
      FileW = CreateFileW(v33, 0x40000000u, 0, 0, 2u, 0x8100080u, 0);
      v35 = FileW;
      if ( FileW != (HANDLE)-1LL )
      {
        v36 = WriteFile(FileW, v18, v10, &NumberOfBytesWritten, 0) && NumberOfBytesWritten == v10;
        CloseHandle(v35);
        if ( !v36 )
          DeleteFileW(v33);
      }
    }
    LocalFree(v33);
  }
  if ( a3 )
  {
    v37 = v40;
    *a3 = v18;
    *v37 = v10;
  }
  else
  {
    LocalFree(v18);
  }
  return 1;
}

```

## disassembly

```asm
0x1801742bc  push    rbp
0x1801742be  push    rbx
0x1801742bf  push    rsi
0x1801742c0  push    rdi
0x1801742c1  push    r12
0x1801742c3  push    r13
0x1801742c5  push    r14
0x1801742c7  push    r15
0x1801742c9  lea     rbp, [rsp-68h]
0x1801742ce  sub     rsp, 168h
0x1801742d5  mov     rax, cs:__security_cookie
0x1801742dc  xor     rax, rsp
0x1801742df  mov     [rbp+0A0h+var_48], rax
0x1801742e3  xor     r12d, r12d
0x1801742e6  mov     [rsp+1A0h+var_158], r9
0x1801742eb  mov     r14, r8
0x1801742ee  mov     rdi, rdx
0x1801742f1  mov     r13, rcx
0x1801742f4  test    r8, r8
0x1801742f7  jz      short loc_1801742FC
0x1801742f9  mov     [r8], r12
0x1801742fc  mov     eax, 1
0x180174301  mov     edx, r12d
0x180174304  lea     rcx, [rax+rax*2]
0x180174308  mov     eax, [rdi+rcx*8+8]
0x18017430c  mov     [rdi+rcx*8+0Ch], eax
0x180174310  lea     eax, [rdx+0Bh]
0x180174313  inc     edx
0x180174315  cmp     edx, 4
0x180174318  jl      short loc_180174304
0x18017431a  lea     rcx, [rax+rax*2]
0x18017431e  mov     ebx, 120h
0x180174323  mov     eax, [rdi+rcx*8+8]
0x180174327  mov     r9d, r12d
0x18017432a  mov     [rdi+rcx*8+0Ch], eax
0x18017432e  mov     r10d, 0FFFFFFFFh
0x180174334  mov     eax, [rdi+38h]
0x180174337  mov     [rdi+3Ch], eax
0x18017433a  mov     eax, [rdi+170h]
0x180174340  mov     [rdi+174h], eax
0x180174346  mov     eax, [rdi+188h]
0x18017434c  mov     [rdi+18Ch], eax
0x180174352  mov     eax, r9d
0x180174355  lea     rdx, [rax+rax*2]
0x180174359  lea     rcx, [rax+rax*2]
0x18017435d  mov     dword ptr [rsp+rdx*4+1A0h+var_150], ebx
0x180174361  mov     r8d, [rdi+rcx*8+10h]
0x180174366  mov     eax, [rdi+rcx*8+0Ch]
0x18017436a  mov     dword ptr [rsp+rdx*4+1A0h+var_150+8], r8d
0x18017436f  imul    r8, rax
0x180174373  mov     dword ptr [rsp+rdx*4+1A0h+var_150+4], eax
0x180174377  cmp     r8, r10
0x18017437a  ja      loc_1801745FA
0x180174380  lea     eax, [r8+rbx]
0x180174384  cmp     eax, r8d
0x180174387  jb      loc_1801745F7
0x18017438d  lea     ebx, [rax+3]
0x180174390  cmp     ebx, eax
0x180174392  jb      loc_1801745F7
0x180174398  and     ebx, 0FFFFFFFCh
0x18017439b  inc     r9d
0x18017439e  cmp     r9d, 12h
0x1801743a2  jb      short loc_180174352
0x1801743a4  mov     edx, ebx; uBytes
0x1801743a6  xor     ecx, ecx; uFlags
0x1801743a8  call    cs:__imp_LocalAlloc
0x1801743af  nop     dword ptr [rax+rax+00h]
0x1801743b4  mov     rsi, rax
0x1801743b7  test    rax, rax
0x1801743ba  jz      loc_1801745FA
0x1801743c0  mov     [rdi+2D0h], ebx
0x1801743c6  mov     r15, r12
0x1801743c9  mov     [rdi+300h], r12
0x1801743d0  mov     [rdi+2ECh], r12
0x1801743d7  movups  xmm0, xmmword ptr [rdi+2D0h]
0x1801743de  movups  xmmword ptr [rax], xmm0
0x1801743e1  movups  xmm1, xmmword ptr [rdi+2E0h]
0x1801743e8  movups  xmmword ptr [rax+10h], xmm1
0x1801743ec  movups  xmm0, xmmword ptr [rdi+2F0h]
0x1801743f3  movups  xmmword ptr [rax+20h], xmm0
0x1801743f7  movups  xmm1, xmmword ptr [rdi+300h]
0x1801743fe  movups  xmmword ptr [rax+30h], xmm1
0x180174402  movsd   xmm0, qword ptr [rdi+310h]
0x18017440a  movaps  xmm1, [rsp+1A0h+var_150]
0x18017440f  movups  xmmword ptr [rax+48h], xmm1
0x180174413  movaps  xmm1, [rsp+1A0h+var_130]
0x180174418  movsd   qword ptr [rax+40h], xmm0
0x18017441d  movaps  xmm0, [rsp+1A0h+var_140]
0x180174422  movups  xmmword ptr [rax+58h], xmm0
0x180174426  movaps  xmm0, [rbp+0A0h+var_120]
0x18017442a  movups  xmmword ptr [rax+68h], xmm1
0x18017442e  movaps  xmm1, [rbp+0A0h+var_110]
0x180174432  movups  xmmword ptr [rax+78h], xmm0
0x180174436  movaps  xmm0, [rbp+0A0h+var_100]
0x18017443a  movups  xmmword ptr [rax+88h], xmm1
0x180174441  movaps  xmm1, [rbp+0A0h+var_F0]
0x180174445  movups  xmmword ptr [rax+98h], xmm0
0x18017444c  movaps  xmm0, [rbp+0A0h+var_E0]
0x180174450  movups  xmmword ptr [rax+0A8h], xmm1
0x180174457  movaps  xmm1, [rbp+0A0h+var_D0]
0x18017445b  movups  xmmword ptr [rax+0B8h], xmm0
0x180174462  movaps  xmm0, [rbp+0A0h+var_C0]
0x180174466  movups  xmmword ptr [rax+0C8h], xmm1
0x18017446d  movaps  xmm1, [rbp+0A0h+var_B0]
0x180174471  movups  xmmword ptr [rax+0D8h], xmm0
0x180174478  movaps  xmm0, [rbp+0A0h+var_A0]
0x18017447c  movups  xmmword ptr [rax+0E8h], xmm1
0x180174483  movaps  xmm1, [rbp+0A0h+var_90]
0x180174487  movups  xmmword ptr [rax+0F8h], xmm0
0x18017448e  movups  xmmword ptr [rax+108h], xmm1
0x180174495  mov     rax, [rbp+0A0h+var_80]
0x180174499  mov     [rsi+118h], rax
0x1801744a0  mov     r8d, dword ptr [rsp+r12+1A0h+var_150+8]
0x1801744a5  lea     rdx, [r15+r15*2]
0x1801744a9  imul    r8d, dword ptr [rsp+r12+1A0h+var_150+4]; Size
0x1801744af  mov     ecx, dword ptr [rsp+r12+1A0h+var_150]
0x1801744b4  mov     rdx, [rdi+rdx*8]; Src
0x1801744b8  add     rcx, rsi; void *
0x1801744bb  call    memcpy_0
0x1801744c0  inc     r15
0x1801744c3  lea     r12, [r12+0Ch]
0x1801744c8  cmp     r15, 12h
0x1801744cc  jnz     short loc_1801744A0
0x1801744ce  xorps   xmm0, xmm0
0x1801744d1  mov     [rsp+1A0h+NumberOfBytesWritten], 0
0x1801744d9  xor     eax, eax
0x1801744db  mov     rcx, r13; pszSrc
0x1801744de  movups  [rbp+0A0h+FileInformation], xmm0
0x1801744e2  mov     [rbp+0A0h+var_50], eax
0x1801744e5  movups  [rbp+0A0h+var_60], xmm0
0x1801744e9  call    pwstrGenerateGPDfilename
0x1801744ee  mov     rdi, rax
0x1801744f1  test    rax, rax
0x1801744f4  jz      loc_1801745D0
0x1801744fa  lea     r8, [rbp+0A0h+FileInformation]; lpFileInformation
0x1801744fe  xor     edx, edx; fInfoLevelId
0x180174500  mov     rcx, rax; lpFileName
0x180174503  call    cs:__imp_GetFileAttributesExW
0x18017450a  nop     dword ptr [rax+rax+00h]
0x18017450f  test    eax, eax
0x180174511  jz      short loc_18017452A
0x180174513  mov     rcx, rdi; lpFileName
0x180174516  call    cs:__imp_DeleteFileW
0x18017451d  nop     dword ptr [rax+rax+00h]
0x180174522  test    eax, eax
0x180174524  jz      loc_1801745C1
0x18017452a  mov     [rsp+1A0h+hTemplateFile], 0; hTemplateFile
0x180174533  xor     r9d, r9d; lpSecurityAttributes
0x180174536  mov     [rsp+1A0h+dwFlagsAndAttributes], 8100080h; dwFlagsAndAttributes
0x18017453e  xor     r8d, r8d; dwShareMode
0x180174541  mov     edx, 40000000h; dwDesiredAccess
0x180174546  mov     [rsp+1A0h+dwCreationDisposition], 2; dwCreationDisposition
0x18017454e  mov     rcx, rdi; lpFileName
0x180174551  call    cs:__imp_CreateFileW
0x180174558  nop     dword ptr [rax+rax+00h]
0x18017455d  mov     r15, rax
0x180174560  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180174564  jz      short loc_1801745C1
0x180174566  lea     r9, [rsp+1A0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18017456b  mov     qword ptr [rsp+1A0h+dwCreationDisposition], 0; lpOverlapped
0x180174574  mov     r8d, ebx; nNumberOfBytesToWrite
0x180174577  mov     rdx, rsi; lpBuffer
0x18017457a  mov     rcx, rax; hFile
0x18017457d  call    cs:__imp_WriteFile
0x180174584  nop     dword ptr [rax+rax+00h]
0x180174589  test    eax, eax
0x18017458b  jz      short loc_18017459B
0x18017458d  cmp     [rsp+1A0h+NumberOfBytesWritten], ebx
0x180174591  jnz     short loc_18017459B
0x180174593  mov     r12d, 1
0x180174599  jmp     short loc_18017459E
0x18017459b  xor     r12d, r12d
0x18017459e  mov     rcx, r15; hObject
0x1801745a1  call    cs:__imp_CloseHandle
0x1801745a8  nop     dword ptr [rax+rax+00h]
0x1801745ad  test    r12d, r12d
0x1801745b0  jnz     short loc_1801745C1
0x1801745b2  mov     rcx, rdi; lpFileName
0x1801745b5  call    cs:__imp_DeleteFileW
0x1801745bc  nop     dword ptr [rax+rax+00h]
0x1801745c1  mov     rcx, rdi; hMem
0x1801745c4  call    cs:__imp_LocalFree
0x1801745cb  nop     dword ptr [rax+rax+00h]
0x1801745d0  test    r14, r14
0x1801745d3  jz      short loc_1801745E1
0x1801745d5  mov     rax, [rsp+1A0h+var_158]
0x1801745da  mov     [r14], rsi
0x1801745dd  mov     [rax], ebx
0x1801745df  jmp     short loc_1801745F0
0x1801745e1  mov     rcx, rsi; hMem
0x1801745e4  call    cs:__imp_LocalFree
0x1801745eb  nop     dword ptr [rax+rax+00h]
0x1801745f0  mov     eax, 1
0x1801745f5  jmp     short loc_180174626
0x1801745f7  mov     ebx, r10d
0x1801745fa  mov     r8d, ebx
0x1801745fd  lea     rdx, aFatalUnableToA; "Fatal: unable to alloc requested memory"...
0x180174604  lea     rcx, aBconsolidatebu; "BconsolidateBuffers"
0x18017460b  call    WriteDbgTraceErrorGpd
0x180174610  xor     eax, eax
0x180174612  mov     dword ptr [rdi+8B0h], 2
0x18017461c  mov     dword ptr [rdi+8ACh], 3
0x180174626  mov     rcx, [rbp+0A0h+var_48]
0x18017462a  xor     rcx, rsp; StackCookie
0x18017462d  call    __security_check_cookie
0x180174632  add     rsp, 168h
0x180174639  pop     r15
0x18017463b  pop     r14
0x18017463d  pop     r13
0x18017463f  pop     r12
0x180174641  pop     rdi
0x180174642  pop     rsi
0x180174643  pop     rbx
0x180174644  pop     rbp
0x180174645  retn
```
