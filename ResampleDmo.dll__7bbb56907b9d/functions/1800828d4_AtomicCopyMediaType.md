# AtomicCopyMediaType

- ea: `0x1800828d4`
- end: `0x18008298e`
- name: `AtomicCopyMediaType`
- size: `186`
- prototype: `__int64 __fastcall(DMO_MEDIA_TYPE *pmtSrc, DMO_MEDIA_TYPE *pmt)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180082f50`

## callees

- `0x18000ab90`
- `0x18000b79c`
- `0x1800828d4`

## import_xrefs

- `msdmo!MoCopyMediaType` at `0x180082919`
- `msdmo!MoCopyMediaType` at `0x180082919`
- `msdmo!MoFreeMediaType` at `0x18008292a`
- `msdmo!MoFreeMediaType` at `0x18008292a`

## pseudocode

```c
HRESULT __fastcall AtomicCopyMediaType(DMO_MEDIA_TYPE *pmtSrc, DMO_MEDIA_TYPE *pmt, int a3)
{
  HRESULT result; // eax
  GUID subtype; // xmm1
  __int128 v8; // xmm0
  __int128 v9; // xmm1
  __int128 v10; // xmm0
  DMO_MEDIA_TYPE pmtDest; // [rsp+20h] [rbp-78h] BYREF

  memset_0(&pmtDest, 0, sizeof(pmtDest));
  result = MoCopyMediaType(&pmtDest, pmtSrc);
  if ( result >= 0 )
  {
    if ( a3 )
      MoFreeMediaType(pmt);
    result = 0;
    subtype = pmtDest.subtype;
    pmt->majortype = pmtDest.majortype;
    v8 = *(_OWORD *)&pmtDest.bFixedSizeSamples;
    pmt->subtype = subtype;
    v9 = *(_OWORD *)&pmtDest.formattype.Data2;
    *(_OWORD *)&pmt->bFixedSizeSamples = v8;
    v10 = *(_OWORD *)&pmtDest.pUnk;
    *(_OWORD *)&pmt->formattype.Data2 = v9;
    *(_QWORD *)&v9 = pmtDest.pbFormat;
    *(_OWORD *)&pmt->pUnk = v10;
    pmt->pbFormat = (BYTE *)v9;
  }
  return result;
}

```

## disassembly

```asm
0x1800828d4  mov     [rsp+arg_10], rbx
0x1800828d9  mov     [rsp+arg_18], rsi
0x1800828de  push    rdi
0x1800828df  sub     rsp, 90h
0x1800828e6  mov     rax, cs:__security_cookie
0x1800828ed  xor     rax, rsp
0x1800828f0  mov     [rsp+98h+var_18], rax
0x1800828f8  mov     rdi, rdx
0x1800828fb  mov     esi, r8d
0x1800828fe  xor     edx, edx; Val
0x180082900  mov     rbx, rcx
0x180082903  lea     rcx, [rsp+98h+pmtDest]; void *
0x180082908  lea     r8d, [rdx+58h]; Size
0x18008290c  call    memset_0
0x180082911  mov     rdx, rbx; pmtSrc
0x180082914  lea     rcx, [rsp+98h+pmtDest]; pmtDest
0x180082919  call    cs:__imp_MoCopyMediaType
0x18008291f  test    eax, eax
0x180082921  js      short loc_180082969
0x180082923  test    esi, esi
0x180082925  jz      short loc_180082930
0x180082927  mov     rcx, rdi; pmt
0x18008292a  call    cs:__imp_MoFreeMediaType
0x180082930  movaps  xmm0, xmmword ptr [rsp+98h+pmtDest.majortype.Data1]
0x180082935  xor     eax, eax
0x180082937  movaps  xmm1, xmmword ptr [rsp+98h+pmtDest.subtype.Data1]
0x18008293c  movups  xmmword ptr [rdi], xmm0
0x18008293f  movaps  xmm0, xmmword ptr [rsp+98h+pmtDest.bFixedSizeSamples]
0x180082944  movups  xmmword ptr [rdi+10h], xmm1
0x180082948  movaps  xmm1, xmmword ptr [rsp+98h+pmtDest.formattype.Data2]
0x18008294d  movups  xmmword ptr [rdi+20h], xmm0
0x180082951  movaps  xmm0, xmmword ptr [rsp+98h+pmtDest.pUnk]
0x180082956  movups  xmmword ptr [rdi+30h], xmm1
0x18008295a  movsd   xmm1, [rsp+98h+pmtDest.pbFormat]
0x180082960  movups  xmmword ptr [rdi+40h], xmm0
0x180082964  movsd   qword ptr [rdi+50h], xmm1
0x180082969  mov     rcx, [rsp+98h+var_18]
0x180082971  xor     rcx, rsp; StackCookie
0x180082974  call    __security_check_cookie
0x180082979  lea     r11, [rsp+98h+var_8]
0x180082981  mov     rbx, [r11+20h]
0x180082985  mov     rsi, [r11+28h]
0x180082989  mov     rsp, r11
0x18008298c  pop     rdi
0x18008298d  retn
```
