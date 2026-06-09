# CAudioTimeCompression::CAudioTimeCompression(int,int,long *)

- ea: `0x18004eba0`
- end: `0x18004ed5e`
- name: `??0CAudioTimeCompression@@QEAA@HHPEAJ@Z`
- size: `446`
- prototype: `CAudioTimeCompression *__fastcall(CAudioTimeCompression *__hidden this, int, int, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000b690`

## callees

- `0x18004eba0`
- `0x18004fae0`
- `0x1800511d0`
- `0x180051440`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18004ec7a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18004ec7a`
- `mfperfhelper!__imp_ippStaticInit` at `0x18004ec9c`
- `mfperfhelper!__imp_ippStaticInit` at `0x18004ec9c`

## pseudocode

```c
CAudioTimeCompression *__fastcall CAudioTimeCompression::CAudioTimeCompression(
        CAudioTimeCompression *this,
        int a2,
        int a3,
        int *a4)
{
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  int v11; // eax
  int FFTInfo; // ebx
  struct CIntelFFTInfo *v13; // rcx
  CAudioTimeCompression *result; // rax

  *(_DWORD *)this = 0;
  if ( !a2 || a2 > 96000 )
  {
    FFTInfo = -2147024809;
    goto LABEL_17;
  }
  *((_BYTE *)this + 22) = 0;
  *((_QWORD *)this + 3) = 0x3FF0000000000000LL;
  *((_QWORD *)this + 27) = 0;
  *((_DWORD *)this + 10) = 20;
  *(_DWORD *)this = 1;
  *((_DWORD *)this + 11) = 15;
  *((_DWORD *)this + 12) = 4000;
  *((_DWORD *)this + 15) = 200;
  *((_QWORD *)this + 10) = 0;
  *(_QWORD *)((char *)this + 68) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 0;
  *((_DWORD *)this + 52) = 0;
  *((_DWORD *)this + 38) = 0;
  *(_OWORD *)((char *)this + 4) = 0;
  *((_WORD *)this + 10) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 224));
  *((_QWORD *)this + 16) = 0;
  if ( _InterlockedIncrement(&dword_1800ADBEC) == 1 && (v11 = ippStaticInit(v9, v8, v10)) != 0 && v11 != 20 )
  {
    _InterlockedDecrement(&dword_1800ADBEC);
    FFTInfo = -2147467259;
  }
  else if ( *((_QWORD *)this + 16) )
  {
    FFTInfo = -2147467259;
  }
  else
  {
    FFTInfo = auippCreateFFTInfo((char *)this + 128);
    if ( !FFTInfo )
    {
      *((_BYTE *)this + 120) = 1;
      *((_QWORD *)this + 17) = ForwRealFFT_Intel;
      *((_QWORD *)this + 18) = InvComplexFFT_Intel;
LABEL_15:
      FFTInfo = CAudioTimeCompression::SetInputProperty(this, a2, a3);
      goto LABEL_17;
    }
  }
  v13 = (struct CIntelFFTInfo *)*((_QWORD *)this + 16);
  if ( v13 )
  {
    auippDeleteFFTInfo(v13);
    *((_QWORD *)this + 16) = 0;
  }
  if ( FFTInfo >= 0 )
    goto LABEL_15;
LABEL_17:
  result = this;
  if ( a4 )
    *a4 = FFTInfo;
  return result;
}

```

## disassembly

```asm
0x18004eba0  push    rbx
0x18004eba2  push    rdi
0x18004eba3  push    r14
0x18004eba5  sub     rsp, 30h
0x18004eba9  mov     [rsp+48h+arg_0], rbp
0x18004ebae  mov     r14, r9
0x18004ebb1  mov     [rsp+48h+arg_8], rsi
0x18004ebb6  mov     ebp, edx
0x18004ebb8  mov     [rsp+48h+arg_10], r12
0x18004ebbd  mov     rdi, rcx
0x18004ebc0  xor     r12d, r12d
0x18004ebc3  mov     [rsp+48h+arg_18], r15
0x18004ebc8  mov     [rcx], r12d
0x18004ebcb  mov     r15d, r8d
0x18004ebce  test    edx, edx
0x18004ebd0  jz      loc_18004ED30
0x18004ebd6  cmp     edx, 17700h
0x18004ebdc  jg      loc_18004ED30
0x18004ebe2  mov     [rcx+16h], r12b
0x18004ebe6  mov     rax, 3FF0000000000000h
0x18004ebf0  mov     [rcx+18h], rax
0x18004ebf4  xorps   xmm0, xmm0
0x18004ebf7  mov     [rcx+0D8h], r12
0x18004ebfe  xor     eax, eax
0x18004ec00  mov     dword ptr [rcx+28h], 14h
0x18004ec07  mov     ebx, 1
0x18004ec0c  mov     [rcx], ebx
0x18004ec0e  mov     dword ptr [rcx+2Ch], 0Fh
0x18004ec15  mov     dword ptr [rcx+30h], 0FA0h
0x18004ec1c  mov     dword ptr [rcx+3Ch], 0C8h
0x18004ec23  mov     [rcx+50h], r12
0x18004ec27  mov     [rcx+44h], r12
0x18004ec2b  mov     [rcx+58h], r12
0x18004ec2f  mov     [rcx+70h], r12
0x18004ec33  mov     [rcx+0A0h], r12
0x18004ec3a  mov     [rcx+0A8h], r12
0x18004ec41  mov     [rcx+0B0h], r12
0x18004ec48  mov     [rcx+0C8h], r12
0x18004ec4f  mov     [rcx+0B8h], r12
0x18004ec56  mov     [rcx+0C0h], r12
0x18004ec5d  mov     [rcx+0D0h], r12d
0x18004ec64  mov     [rcx+98h], r12d
0x18004ec6b  movups  xmmword ptr [rcx+4], xmm0
0x18004ec6f  mov     [rcx+14h], ax
0x18004ec73  add     rcx, 0E0h; lpCriticalSection
0x18004ec7a  call    cs:__imp_InitializeCriticalSection
0x18004ec81  nop     dword ptr [rax+rax+00h]
0x18004ec86  mov     [rdi+80h], r12
0x18004ec8d  lock xadd cs:dword_1800ADBEC, ebx
0x18004ec95  inc     ebx
0x18004ec97  cmp     ebx, 1
0x18004ec9a  jnz     short loc_18004ECBF
0x18004ec9c  call    cs:__imp_ippStaticInit
0x18004eca3  nop     dword ptr [rax+rax+00h]
0x18004eca8  test    eax, eax
0x18004ecaa  jz      short loc_18004ECBF
0x18004ecac  cmp     eax, 14h
0x18004ecaf  jz      short loc_18004ECBF
0x18004ecb1  lock dec cs:dword_1800ADBEC
0x18004ecb8  mov     ebx, 80004005h
0x18004ecbd  jmp     short loc_18004ECE1
0x18004ecbf  cmp     [rdi+80h], r12
0x18004ecc6  jz      short loc_18004ECCF
0x18004ecc8  mov     ebx, 80004005h
0x18004eccd  jmp     short loc_18004ECE1
0x18004eccf  lea     rcx, [rdi+80h]
0x18004ecd6  call    ?auippCreateFFTInfo@@YAJPEAPEAUCIntelFFTInfo@@KKW4CIntelFFTScaling@@W4CIntelFFTWorkBufAlloc@@PEAK@Z; auippCreateFFTInfo(CIntelFFTInfo * *,ulong,ulong,CIntelFFTScaling,CIntelFFTWorkBufAlloc,ulong *)
0x18004ecdb  mov     ebx, eax
0x18004ecdd  test    eax, eax
0x18004ecdf  jz      short loc_18004ECFF
0x18004ece1  mov     rcx, [rdi+80h]; Block
0x18004ece8  test    rcx, rcx
0x18004eceb  jz      short loc_18004ECF9
0x18004eced  call    ?auippDeleteFFTInfo@@YAXPEAUCIntelFFTInfo@@@Z; auippDeleteFFTInfo(CIntelFFTInfo *)
0x18004ecf2  mov     [rdi+80h], r12
0x18004ecf9  test    ebx, ebx
0x18004ecfb  jns     short loc_18004ED1F
0x18004ecfd  jmp     short loc_18004ED35
0x18004ecff  lea     rax, ?ForwRealFFT_Intel@@YAJPEAXPEAMG@Z; ForwRealFFT_Intel(void *,float *,ushort)
0x18004ed06  mov     byte ptr [rdi+78h], 1
0x18004ed0a  mov     [rdi+88h], rax
0x18004ed11  lea     rax, ?InvComplexFFT_Intel@@YAJPEAXQEAMG@Z; InvComplexFFT_Intel(void *,float * const,ushort)
0x18004ed18  mov     [rdi+90h], rax
0x18004ed1f  mov     r8d, r15d; int
0x18004ed22  mov     edx, ebp; int
0x18004ed24  mov     rcx, rdi; this
0x18004ed27  call    ?SetInputProperty@CAudioTimeCompression@@QEAAJHH@Z; CAudioTimeCompression::SetInputProperty(int,int)
0x18004ed2c  mov     ebx, eax
0x18004ed2e  jmp     short loc_18004ED35
0x18004ed30  mov     ebx, 80070057h
0x18004ed35  mov     r15, [rsp+48h+arg_18]
0x18004ed3a  mov     rax, rdi
0x18004ed3d  mov     r12, [rsp+48h+arg_10]
0x18004ed42  mov     rsi, [rsp+48h+arg_8]
0x18004ed47  mov     rbp, [rsp+48h+arg_0]
0x18004ed4c  test    r14, r14
0x18004ed4f  jz      short loc_18004ED54
0x18004ed51  mov     [r14], ebx
0x18004ed54  add     rsp, 30h
0x18004ed58  pop     r14
0x18004ed5a  pop     rdi
0x18004ed5b  pop     rbx
0x18004ed5c  retn
```
