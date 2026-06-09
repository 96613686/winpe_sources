# CACMCmpStream::SetUpCompression(void)

- ea: `0x180015e7c`
- end: `0x180016348`
- name: `?SetUpCompression@CACMCmpStream@@QEAAJXZ`
- size: `1228`
- prototype: `__int64 __fastcall(CACMCmpStream *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800156f0`
- `0x180015880`
- `0x180015cc0`

## callees

- `0x180001460`
- `0x180001d0c`
- `0x180008350`
- `0x1800086a0`
- `0x180015e7c`
- `0x18001734d`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180015f00`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18001603f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18001628c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800162a8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180015f00`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18001603f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18001628c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800162a8`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180015ef7`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180016036`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180016283`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18001629f`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180015ef7`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180016036`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180016283`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18001629f`
- `MSACM32!acmStreamPrepareHeader` at `0x180016321`
- `MSACM32!acmStreamPrepareHeader` at `0x180016321`
- `MSACM32!acmFormatSuggest` at `0x180016071`
- `MSACM32!acmFormatSuggest` at `0x180016071`
- `MSACM32!acmStreamOpen` at `0x1800161b9`
- `MSACM32!acmStreamOpen` at `0x1800161b9`
- `MSACM32!acmFormatDetailsW` at `0x1800160f5`
- `MSACM32!acmFormatDetailsW` at `0x180016152`
- `MSACM32!acmFormatDetailsW` at `0x1800160f5`
- `MSACM32!acmFormatDetailsW` at `0x180016152`
- `MSACM32!acmFormatTagDetailsW` at `0x180016125`
- `MSACM32!acmFormatTagDetailsW` at `0x180016182`
- `MSACM32!acmFormatTagDetailsW` at `0x180016125`
- `MSACM32!acmFormatTagDetailsW` at `0x180016182`
- `MSACM32!acmStreamSize` at `0x180016214`
- `MSACM32!acmStreamSize` at `0x18001626d`
- `MSACM32!acmStreamSize` at `0x180016214`
- `MSACM32!acmStreamSize` at `0x18001626d`
- `MSACM32!acmMetrics` at `0x18001602a`
- `MSACM32!acmMetrics` at `0x18001602a`

## pseudocode

```c
__int64 __fastcall CACMCmpStream::SetUpCompression(CACMCmpStream *this)
{
  unsigned int v2; // eax
  DWORD *v3; // rbx
  MMRESULT v4; // esi
  HGLOBAL v5; // rax
  LPVOID v6; // rax
  LPVOID v7; // rsi
  unsigned int v8; // eax
  unsigned __int64 v9; // rdx
  _WORD *v10; // r9
  DWORD *v11; // r14
  HGLOBAL v13; // rax
  _WORD *v14; // rax
  DWORD v15; // eax
  unsigned __int16 *v16; // rax
  DWORD v17; // eax
  unsigned __int16 *v18; // rax
  HACMSTREAM *v19; // r14
  __int64 v20; // rcx
  int v21; // eax
  IAVIStream *v22; // rcx
  int v23; // ebx
  DWORD v24; // eax
  unsigned int v25; // eax
  __int64 v26; // rax
  HACMSTREAM v27; // rcx
  DWORD v28; // edx
  HGLOBAL v29; // rax
  LPVOID v30; // rax
  SIZE_T v31; // rdx
  HGLOBAL v32; // rax
  LPVOID v33; // rax
  __int64 v34; // rcx
  HACMSTREAM v35; // rcx
  int v36; // eax
  struct tACMFORMATDETAILSW pafd; // [rsp+40h] [rbp-C0h] BYREF
  struct tACMFORMATDETAILSW v38; // [rsp+160h] [rbp+60h] BYREF
  struct tACMFORMATTAGDETAILSW paftd; // [rsp+280h] [rbp+180h] BYREF
  struct tACMFORMATTAGDETAILSW v40; // [rsp+300h] [rbp+200h] BYREF

  v2 = AVIStreamStart(*((PAVISTREAM *)this + 28));
  v3 = (DWORD *)((char *)this + 248);
  v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, char *))(**((_QWORD **)this + 28) + 48LL))(
         *((_QWORD *)this + 28),
         v2,
         0,
         (char *)this + 248);
  if ( (v4 & 0x80000000) != 0 )
    return v4;
  v5 = GlobalAlloc(0x2042u, (int)*v3);
  v6 = GlobalLock(v5);
  *((_QWORD *)this + 30) = v6;
  v7 = v6;
  if ( !v6 )
    return (MMRESULT)-2147205017;
  v8 = AVIStreamStart(*((PAVISTREAM *)this + 28));
  v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, LPVOID, char *))(**((_QWORD **)this + 28) + 48LL))(
         *((_QWORD *)this + 28),
         v8,
         v7,
         (char *)this + 248);
  if ( (v4 & 0x80000000) != 0 )
    return v4;
  v9 = *v3;
  if ( (unsigned __int64)(int)v9 < 0xE )
    return (MMRESULT)-2147205018;
  v10 = (_WORD *)*((_QWORD *)this + 30);
  if ( *v10 != 1 && ((unsigned __int64)(int)v9 < 0x12 || v9 < (unsigned __int64)(unsigned __int16)v10[8] + 18) )
    return (MMRESULT)-2147205018;
  if ( *((_QWORD *)this + 32) )
  {
    v11 = (DWORD *)((char *)this + 264);
    if ( (_DWORD)v9 == *((_DWORD *)this + 66)
      && !memcmp_0(*((const void **)this + 30), *((const void **)this + 32), (int)v9) )
    {
      goto LABEL_13;
    }
  }
  else
  {
    if ( *v10 == 1 )
      goto LABEL_13;
    v11 = (DWORD *)((char *)this + 264);
    acmMetrics(0, 0x32u, (char *)this + 264);
    v13 = GlobalAlloc(0x2042u, *((int *)this + 66));
    v14 = GlobalLock(v13);
    *((_QWORD *)this + 32) = v14;
    if ( !v14 )
      return (MMRESULT)-2147205017;
    *v14 = 1;
    if ( acmFormatSuggest(0, *((LPWAVEFORMATEX *)this + 30), *((LPWAVEFORMATEX *)this + 32), *v11, 0) )
    {
LABEL_13:
      *((_QWORD *)this + 32) = *((_QWORD *)this + 30);
      *((_DWORD *)this + 66) = *v3;
      *v3 = 0;
      *((_QWORD *)this + 30) = 0;
      *((_QWORD *)this + 29) = -1;
      return v4;
    }
  }
  memset_0(&pafd, 0, sizeof(pafd));
  memset_0(&paftd, 0, sizeof(paftd));
  memset_0(&v38, 0, sizeof(v38));
  memset_0(&v40, 0, sizeof(v40));
  v15 = *v3;
  pafd.pwfx = (LPWAVEFORMATEX)*((_QWORD *)this + 30);
  pafd.cbStruct = 284;
  pafd.cbwfx = v15;
  pafd.fdwSupport = 0;
  pafd.dwFormatTag = pafd.pwfx->wFormatTag;
  acmFormatDetailsW(0, &pafd, 1u);
  v16 = (unsigned __int16 *)*((_QWORD *)this + 30);
  paftd.cbStruct = 120;
  paftd.dwFormatTag = *v16;
  paftd.fdwSupport = 0;
  acmFormatTagDetailsW(0, &paftd, 1u);
  v17 = *v11;
  v38.pwfx = (LPWAVEFORMATEX)*((_QWORD *)this + 32);
  v38.cbStruct = 284;
  v38.cbwfx = v17;
  v38.dwFormatTag = v38.pwfx->wFormatTag;
  v38.fdwSupport = 0;
  acmFormatDetailsW(0, &v38, 1u);
  v18 = (unsigned __int16 *)*((_QWORD *)this + 32);
  v40.cbStruct = 120;
  v40.dwFormatTag = *v18;
  v40.fdwSupport = 0;
  acmFormatTagDetailsW(0, &v40, 1u);
  v19 = (HACMSTREAM *)((char *)this + 232);
  v4 = acmStreamOpen(
         (LPHACMSTREAM)this + 29,
         0,
         *((LPWAVEFORMATEX *)this + 30),
         *((LPWAVEFORMATEX *)this + 32),
         0,
         0,
         0,
         4u);
  if ( !*((_QWORD *)this + 29) )
    return (MMRESULT)-2147204921;
  v20 = *((_QWORD *)this + 32);
  *((_DWORD *)this + 17) = *(unsigned __int16 *)(v20 + 12);
  *((_DWORD *)this + 10) = *(unsigned __int16 *)(v20 + 12);
  v21 = *(_DWORD *)(v20 + 8);
  v22 = (IAVIStream *)*((_QWORD *)this + 28);
  *((_DWORD *)this + 11) = v21;
  v23 = *(unsigned __int16 *)(*((_QWORD *)this + 30) + 12LL);
  v24 = v23 * AVIStreamLength(v22);
  acmStreamSize(*v19, v24, (LPDWORD)this + 13, 0);
  v25 = *((_DWORD *)this + 13) / (unsigned int)*(unsigned __int16 *)(*((_QWORD *)this + 32) + 12LL);
  *((_DWORD *)this + 67) = 4096;
  *((_DWORD *)this + 13) = v25;
  v26 = *((_QWORD *)this + 30);
  *((_DWORD *)this + 16) = 0;
  v27 = *v19;
  v28 = 4096 - 0x1000u % *(unsigned __int16 *)(v26 + 12);
  *((_DWORD *)this + 67) = v28;
  acmStreamSize(v27, v28, (LPDWORD)this + 70, 0);
  v29 = GlobalAlloc(0x42u, *((int *)this + 67));
  v30 = GlobalLock(v29);
  v31 = *((int *)this + 70);
  *((_QWORD *)this + 34) = v30;
  v32 = GlobalAlloc(0x42u, v31);
  v33 = GlobalLock(v32);
  v34 = *((_QWORD *)this + 34);
  *((_QWORD *)this + 36) = v33;
  if ( !v34 || !v33 )
    return (MMRESULT)-2147205017;
  *((_DWORD *)this + 80) = *((_DWORD *)this + 67);
  *((_QWORD *)this + 39) = v34;
  v35 = *v19;
  *((_QWORD *)this + 42) = v33;
  v36 = *((_DWORD *)this + 70);
  *((_DWORD *)this + 74) = 124;
  *((_DWORD *)this + 75) = 0;
  *((_QWORD *)this + 38) = 0;
  *((_DWORD *)this + 81) = 0;
  *((_DWORD *)this + 86) = v36;
  *((_DWORD *)this + 87) = 0;
  if ( !acmStreamPrepareHeader(v35, (LPACMSTREAMHEADER)((char *)this + 296), 0) )
  {
    *(_QWORD *)((char *)this + 420) = 0;
    *((_DWORD *)this + 107) = 0;
    return v4;
  }
  return 2147762288LL;
}

```

## disassembly

```asm
0x180015e7c  push    rbp
0x180015e7e  push    rbx
0x180015e7f  push    rsi
0x180015e80  push    rdi
0x180015e81  push    r12
0x180015e83  push    r13
0x180015e85  push    r14
0x180015e87  push    r15
0x180015e89  lea     rbp, [rsp-298h]
0x180015e91  sub     rsp, 398h
0x180015e98  mov     rax, cs:__security_cookie
0x180015e9f  xor     rax, rsp
0x180015ea2  mov     [rbp+2D0h+var_50], rax
0x180015ea9  mov     rdi, rcx
0x180015eac  mov     rcx, [rcx+0E0h]; pavi
0x180015eb3  call    AVIStreamStart
0x180015eb8  mov     rcx, [rdi+0E0h]
0x180015ebf  lea     rbx, [rdi+0F8h]
0x180015ec6  mov     r10d, eax
0x180015ec9  mov     r9, rbx
0x180015ecc  xor     r8d, r8d
0x180015ecf  mov     rdx, [rcx]
0x180015ed2  mov     rax, [rdx+30h]
0x180015ed6  mov     edx, r10d
0x180015ed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ede  xor     r12d, r12d
0x180015ee1  mov     esi, eax
0x180015ee3  test    eax, eax
0x180015ee5  js      loc_180015FEE
0x180015eeb  movsxd  rdx, dword ptr [rbx]; dwBytes
0x180015eee  mov     r15d, 2042h
0x180015ef4  mov     ecx, r15d; uFlags
0x180015ef7  call    cs:__imp_GlobalAlloc
0x180015efd  mov     rcx, rax; hMem
0x180015f00  call    cs:__imp_GlobalLock
0x180015f06  mov     [rdi+0F0h], rax
0x180015f0d  mov     rsi, rax
0x180015f10  test    rax, rax
0x180015f13  jnz     short loc_180015F1F
0x180015f15  mov     esi, 80044067h
0x180015f1a  jmp     loc_180015FEE
0x180015f1f  mov     rcx, [rdi+0E0h]; pavi
0x180015f26  call    AVIStreamStart
0x180015f2b  mov     rcx, [rdi+0E0h]
0x180015f32  mov     r10d, eax
0x180015f35  mov     r9, rbx
0x180015f38  mov     r8, rsi
0x180015f3b  mov     rdx, [rcx]
0x180015f3e  mov     rax, [rdx+30h]
0x180015f42  mov     edx, r10d
0x180015f45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f4a  mov     esi, eax
0x180015f4c  test    eax, eax
0x180015f4e  js      loc_180015FEE
0x180015f54  mov     edx, [rbx]
0x180015f56  movsxd  r8, edx; Size
0x180015f59  cmp     r8, 0Eh
0x180015f5d  jnb     short loc_180015F69
0x180015f5f  mov     esi, 80044066h
0x180015f64  jmp     loc_180015FEE
0x180015f69  mov     r9, [rdi+0F0h]
0x180015f70  mov     r13d, 1
0x180015f76  movzx   r10d, word ptr [r9]
0x180015f7a  cmp     r10w, r13w
0x180015f7e  jz      short loc_180015F94
0x180015f80  cmp     r8, 12h
0x180015f84  jb      short loc_180015F5F
0x180015f86  movzx   ecx, word ptr [r9+10h]
0x180015f8b  add     rcx, 12h
0x180015f8f  cmp     rdx, rcx
0x180015f92  jb      short loc_180015F5F
0x180015f94  mov     rax, [rdi+100h]
0x180015f9b  test    rax, rax
0x180015f9e  jz      short loc_180016013
0x180015fa0  lea     r14, [rdi+108h]
0x180015fa7  cmp     edx, [r14]
0x180015faa  jnz     loc_18001607F
0x180015fb0  mov     rdx, rax; Buf2
0x180015fb3  mov     rcx, r9; Buf1
0x180015fb6  call    memcmp_0
0x180015fbb  test    eax, eax
0x180015fbd  jnz     loc_18001607F
0x180015fc3  mov     rax, [rdi+0F0h]
0x180015fca  mov     [rdi+100h], rax
0x180015fd1  mov     eax, [rbx]
0x180015fd3  mov     [rdi+108h], eax
0x180015fd9  mov     [rbx], r12d
0x180015fdc  mov     [rdi+0F0h], r12
0x180015fe3  mov     qword ptr [rdi+0E8h], 0FFFFFFFFFFFFFFFFh
0x180015fee  mov     eax, esi
0x180015ff0  mov     rcx, [rbp+2D0h+var_50]
0x180015ff7  xor     rcx, rsp; StackCookie
0x180015ffa  call    __security_check_cookie
0x180015fff  add     rsp, 398h
0x180016006  pop     r15
0x180016008  pop     r14
0x18001600a  pop     r13
0x18001600c  pop     r12
0x18001600e  pop     rdi
0x18001600f  pop     rsi
0x180016010  pop     rbx
0x180016011  pop     rbp
0x180016012  retn
0x180016013  cmp     r10w, r13w
0x180016017  jz      short loc_180015FC3
0x180016019  lea     r14, [rdi+108h]
0x180016020  mov     edx, 32h ; '2'; uMetric
0x180016025  mov     r8, r14; pMetric
0x180016028  xor     ecx, ecx; hao
0x18001602a  call    cs:__imp_acmMetrics
0x180016030  movsxd  rdx, dword ptr [r14]; dwBytes
0x180016033  mov     ecx, r15d; uFlags
0x180016036  call    cs:__imp_GlobalAlloc
0x18001603c  mov     rcx, rax; hMem
0x18001603f  call    cs:__imp_GlobalLock
0x180016045  mov     [rdi+100h], rax
0x18001604c  test    rax, rax
0x18001604f  jz      loc_180015F15
0x180016055  mov     [rax], r13w
0x180016059  xor     ecx, ecx; had
0x18001605b  mov     r9d, [r14]; cbwfxDst
0x18001605e  mov     r8, [rdi+100h]; pwfxDst
0x180016065  mov     rdx, [rdi+0F0h]; pwfxSrc
0x18001606c  mov     [rsp+3D0h+fdwSuggest], r12d; fdwSuggest
0x180016071  call    cs:__imp_acmFormatSuggest
0x180016077  test    eax, eax
0x180016079  jnz     loc_180015FC3
0x18001607f  mov     esi, 11Ch
0x180016084  lea     rcx, [rsp+3D0h+pafd]; void *
0x180016089  mov     r8d, esi; Size
0x18001608c  xor     edx, edx; Val
0x18001608e  call    memset_0
0x180016093  mov     r15d, 78h ; 'x'
0x180016099  lea     rcx, [rbp+2D0h+paftd]; void *
0x1800160a0  mov     r8d, r15d; Size
0x1800160a3  xor     edx, edx; Val
0x1800160a5  call    memset_0
0x1800160aa  mov     r8d, esi; Size
0x1800160ad  lea     rcx, [rbp+2D0h+var_270]; void *
0x1800160b1  xor     edx, edx; Val
0x1800160b3  call    memset_0
0x1800160b8  mov     r8d, r15d; Size
0x1800160bb  lea     rcx, [rbp+2D0h+var_D0]; void *
0x1800160c2  xor     edx, edx; Val
0x1800160c4  call    memset_0
0x1800160c9  mov     rcx, [rdi+0F0h]
0x1800160d0  lea     rdx, [rsp+3D0h+pafd]; pafd
0x1800160d5  mov     eax, [rbx]
0x1800160d7  mov     r8d, r13d; fdwDetails
0x1800160da  mov     [rsp+3D0h+pafd.pwfx], rcx
0x1800160df  mov     [rsp+3D0h+pafd.cbStruct], esi
0x1800160e3  mov     [rsp+3D0h+pafd.cbwfx], eax
0x1800160e7  mov     [rsp+3D0h+pafd.fdwSupport], r12d
0x1800160ec  movzx   eax, word ptr [rcx]
0x1800160ef  xor     ecx, ecx; had
0x1800160f1  mov     [rsp+3D0h+pafd.dwFormatTag], eax
0x1800160f5  call    cs:__imp_acmFormatDetailsW
0x1800160fb  mov     rax, [rdi+0F0h]
0x180016102  lea     rdx, [rbp+2D0h+paftd]; paftd
0x180016109  mov     [rbp+2D0h+paftd.cbStruct], r15d
0x180016110  mov     r8d, r13d; fdwDetails
0x180016113  movzx   ecx, word ptr [rax]
0x180016116  mov     [rbp+2D0h+paftd.dwFormatTag], ecx
0x18001611c  xor     ecx, ecx; had
0x18001611e  mov     [rbp+2D0h+paftd.fdwSupport], r12d
0x180016125  call    cs:__imp_acmFormatTagDetailsW
0x18001612b  mov     rcx, [rdi+100h]
0x180016132  lea     rdx, [rbp+2D0h+var_270]; pafd
0x180016136  mov     eax, [r14]
0x180016139  mov     r8d, r13d; fdwDetails
0x18001613c  mov     [rbp+2D0h+var_270.pwfx], rcx
0x180016140  mov     [rbp+2D0h+var_270.cbStruct], esi
0x180016143  mov     [rbp+2D0h+var_270.cbwfx], eax
0x180016146  movzx   eax, word ptr [rcx]
0x180016149  xor     ecx, ecx; had
0x18001614b  mov     [rbp+2D0h+var_270.dwFormatTag], eax
0x18001614e  mov     [rbp+2D0h+var_270.fdwSupport], r12d
0x180016152  call    cs:__imp_acmFormatDetailsW
0x180016158  mov     rax, [rdi+100h]
0x18001615f  lea     rdx, [rbp+2D0h+var_D0]; paftd
0x180016166  mov     [rbp+2D0h+var_D0.cbStruct], r15d
0x18001616d  mov     r8d, r13d; fdwDetails
0x180016170  movzx   ecx, word ptr [rax]
0x180016173  mov     [rbp+2D0h+var_D0.dwFormatTag], ecx
0x180016179  xor     ecx, ecx; had
0x18001617b  mov     [rbp+2D0h+var_D0.fdwSupport], r12d
0x180016182  call    cs:__imp_acmFormatTagDetailsW
0x180016188  mov     r9, [rdi+100h]; pwfxDst
0x18001618f  lea     r14, [rdi+0E8h]
0x180016196  mov     r8, [rdi+0F0h]; pwfxSrc
0x18001619d  mov     rcx, r14; phas
0x1800161a0  mov     [rsp+3D0h+fdwOpen], 4; fdwOpen
0x1800161a8  xor     edx, edx; had
0x1800161aa  mov     [rsp+3D0h+dwInstance], r12; dwInstance
0x1800161af  mov     [rsp+3D0h+dwCallback], r12; dwCallback
0x1800161b4  mov     qword ptr [rsp+3D0h+fdwSuggest], r12; pwfltr
0x1800161b9  call    cs:__imp_acmStreamOpen
0x1800161bf  mov     esi, eax
0x1800161c1  cmp     [r14], r12
0x1800161c4  jnz     short loc_1800161D0
0x1800161c6  mov     esi, 800440C7h
0x1800161cb  jmp     loc_180015FEE
0x1800161d0  mov     rcx, [rdi+100h]
0x1800161d7  movzx   eax, word ptr [rcx+0Ch]
0x1800161db  mov     [rdi+44h], eax
0x1800161de  movzx   eax, word ptr [rcx+0Ch]
0x1800161e2  mov     [rdi+28h], eax
0x1800161e5  mov     eax, [rcx+8]
0x1800161e8  mov     rcx, [rdi+0E0h]; pavi
0x1800161ef  mov     [rdi+2Ch], eax
0x1800161f2  mov     rax, [rdi+0F0h]
0x1800161f9  movzx   ebx, word ptr [rax+0Ch]
0x1800161fd  call    AVIStreamLength
0x180016202  mov     rcx, [r14]; has
0x180016205  xor     r9d, r9d; fdwSize
0x180016208  imul    eax, ebx
0x18001620b  lea     rbx, [rdi+34h]
0x18001620f  mov     r8, rbx; pdwOutputBytes
0x180016212  mov     edx, eax; cbInput
0x180016214  call    cs:__imp_acmStreamSize
0x18001621a  mov     rax, [rdi+100h]
0x180016221  xor     edx, edx
0x180016223  mov     r10d, 1000h
0x180016229  xor     r9d, r9d; fdwSize
0x18001622c  movzx   ecx, word ptr [rax+0Ch]
0x180016230  mov     eax, [rbx]
0x180016232  div     ecx
0x180016234  mov     [rdi+10Ch], r10d
0x18001623b  xor     edx, edx
0x18001623d  mov     [rbx], eax
0x18001623f  lea     rbx, [rdi+118h]
0x180016246  mov     rax, [rdi+0F0h]
0x18001624d  mov     r8, rbx; pdwOutputBytes
0x180016250  mov     [rdi+40h], r12d
0x180016254  movzx   ecx, word ptr [rax+0Ch]
0x180016258  mov     eax, r10d
0x18001625b  div     ecx
0x18001625d  mov     rcx, [r14]; has
0x180016260  sub     r10d, edx
0x180016263  mov     edx, r10d; cbInput
0x180016266  mov     [rdi+10Ch], r10d
0x18001626d  call    cs:__imp_acmStreamSize
0x180016273  movsxd  rdx, dword ptr [rdi+10Ch]; dwBytes
0x18001627a  mov     r15d, 42h ; 'B'
0x180016280  mov     ecx, r15d; uFlags
0x180016283  call    cs:__imp_GlobalAlloc
0x180016289  mov     rcx, rax; hMem
0x18001628c  call    cs:__imp_GlobalLock
0x180016292  movsxd  rdx, dword ptr [rbx]; dwBytes
0x180016295  mov     ecx, r15d; uFlags
0x180016298  mov     [rdi+110h], rax
0x18001629f  call    cs:__imp_GlobalAlloc
0x1800162a5  mov     rcx, rax; hMem
0x1800162a8  call    cs:__imp_GlobalLock
0x1800162ae  mov     rcx, [rdi+110h]
0x1800162b5  mov     [rdi+120h], rax
0x1800162bc  test    rcx, rcx
0x1800162bf  jz      loc_180015F15
0x1800162c5  test    rax, rax
0x1800162c8  jz      loc_180015F15
0x1800162ce  mov     r8d, [rdi+10Ch]
0x1800162d5  lea     rdx, [rdi+128h]; pash
0x1800162dc  mov     [rdi+140h], r8d
0x1800162e3  xor     r8d, r8d; fdwPrepare
0x1800162e6  mov     [rdi+138h], rcx
0x1800162ed  mov     rcx, [r14]; has
0x1800162f0  mov     [rdi+150h], rax
0x1800162f7  mov     eax, [rbx]
0x1800162f9  mov     dword ptr [rdx], 7Ch ; '|'
0x1800162ff  mov     [rdi+12Ch], r12d
0x180016306  mov     [rdi+130h], r12
0x18001630d  mov     [rdi+144h], r12d
0x180016314  mov     [rdi+158h], eax
0x18001631a  mov     [rdi+15Ch], r12d
0x180016321  call    cs:__imp_acmStreamPrepareHeader
0x180016327  test    eax, eax
0x180016329  jz      short loc_180016335
0x18001632b  mov     eax, 80044070h
0x180016330  jmp     loc_180015FF0
0x180016335  mov     [rdi+1A4h], r12
0x18001633c  mov     [rdi+1ACh], r12d
0x180016343  jmp     loc_180015FEE
```
