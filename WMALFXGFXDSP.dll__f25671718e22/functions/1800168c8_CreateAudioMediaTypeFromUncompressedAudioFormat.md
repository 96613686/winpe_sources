# CreateAudioMediaTypeFromUncompressedAudioFormat

- ea: `0x1800168c8`
- end: `0x180016a08`
- name: `CreateAudioMediaTypeFromUncompressedAudioFormat`
- size: `320`
- prototype: `HRESULT __stdcall(const UNCOMPRESSEDAUDIOFORMAT *pUncompressedAudioFormat, IAudioMediaType **ppIAudioMediaType)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180006970`

## callees

- `0x180015190`
- `0x180016114`
- `0x1800168c8`

## pseudocode

```c
HRESULT __stdcall CreateAudioMediaTypeFromUncompressedAudioFormat(
        const UNCOMPRESSEDAUDIOFORMAT *pUncompressedAudioFormat,
        IAudioMediaType **ppIAudioMediaType)
{
  WORD dwSamplesPerFrame; // cx
  DWORD fFramesPerSecond; // edx
  WORD v7; // cx
  bool v8; // cc
  __int64 v9; // rax
  bool v10; // cl
  WORD v11; // ax
  unsigned int v12; // edx
  GUID guidFormatType; // xmm0
  struct tWAVEFORMATEX v14; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v15[22]; // [rsp+42h] [rbp-1Eh] BYREF

  memset(v15, 0, sizeof(v15));
  if ( !pUncompressedAudioFormat )
    return -2147467261;
  dwSamplesPerFrame = pUncompressedAudioFormat->dwSamplesPerFrame;
  fFramesPerSecond = (int)pUncompressedAudioFormat->fFramesPerSecond;
  v14.wBitsPerSample = 8 * LOWORD(pUncompressedAudioFormat->dwBytesPerSampleContainer);
  v14.nChannels = dwSamplesPerFrame;
  v7 = dwSamplesPerFrame * LOWORD(pUncompressedAudioFormat->dwBytesPerSampleContainer);
  v14.nSamplesPerSec = fFramesPerSecond;
  v14.nBlockAlign = v7;
  v8 = pUncompressedAudioFormat->dwSamplesPerFrame <= 2;
  v14.nAvgBytesPerSec = fFramesPerSecond * v7;
  if ( !v8 || pUncompressedAudioFormat->dwValidBitsPerSample != 8 * pUncompressedAudioFormat->dwBytesPerSampleContainer )
    goto LABEL_14;
  v9 = *(_QWORD *)&GUID_00000001_0000_0010_8000_00aa00389b71.Data1
     - *(_QWORD *)&pUncompressedAudioFormat->guidFormatType.Data1;
  if ( *(_QWORD *)&GUID_00000001_0000_0010_8000_00aa00389b71.Data1 == *(_QWORD *)&pUncompressedAudioFormat->guidFormatType.Data1 )
    v9 = *(_QWORD *)GUID_00000001_0000_0010_8000_00aa00389b71.Data4
       - *(_QWORD *)pUncompressedAudioFormat->guidFormatType.Data4;
  if ( ((v10 = v9 == 0, !v9)
     || *(_QWORD *)&GUID_00000003_0000_0010_8000_00aa00389b71.Data1 == *(_QWORD *)&pUncompressedAudioFormat->guidFormatType.Data1
     && *(_QWORD *)GUID_00000003_0000_0010_8000_00aa00389b71.Data4 == *(_QWORD *)pUncompressedAudioFormat->guidFormatType.Data4)
    && !pUncompressedAudioFormat->dwChannelMask )
  {
    v11 = 1;
    if ( !v10 )
      v11 = 3;
    v14.wFormatTag = v11;
    v12 = 18;
    v14.cbSize = 0;
  }
  else
  {
LABEL_14:
    guidFormatType = pUncompressedAudioFormat->guidFormatType;
    v12 = 40;
    v14.wFormatTag = -2;
    v14.cbSize = 22;
    *(_WORD *)v15 = pUncompressedAudioFormat->dwValidBitsPerSample;
    *(_DWORD *)&v15[2] = pUncompressedAudioFormat->dwChannelMask;
    *(GUID *)&v15[6] = guidFormatType;
  }
  return CAudioMediaType::Create(&v14, v12, ppIAudioMediaType, pUncompressedAudioFormat->fFramesPerSecond, 0);
}

```

## disassembly

```asm
0x1800168c8  push    rbp
0x1800168ca  mov     rbp, rsp
0x1800168cd  sub     rsp, 60h
0x1800168d1  mov     rax, cs:__security_cookie
0x1800168d8  xor     rax, rsp
0x1800168db  mov     [rbp+var_8], rax
0x1800168df  xor     r10d, r10d
0x1800168e2  xorps   xmm0, xmm0
0x1800168e5  mov     [rbp+var_E], r10d
0x1800168e9  mov     r9, rdx
0x1800168ec  mov     [rbp+var_A], r10w
0x1800168f1  mov     r8, rcx
0x1800168f4  movdqu  [rbp+var_1E], xmm0
0x1800168f9  test    rcx, rcx
0x1800168fc  jnz     short loc_180016908
0x1800168fe  mov     eax, 80004003h
0x180016903  jmp     loc_1800169F6
0x180016908  movzx   ecx, word ptr [rcx+10h]
0x18001690c  movzx   eax, word ptr [r8+14h]
0x180016911  cvttss2si rdx, dword ptr [r8+1Ch]
0x180016917  shl     ax, 3
0x18001691b  mov     [rbp+var_30.wBitsPerSample], ax
0x18001691f  mov     eax, ecx
0x180016921  mov     [rbp+var_30.nChannels], cx
0x180016925  movzx   ecx, word ptr [r8+14h]
0x18001692a  imul    ecx, eax
0x18001692d  mov     [rbp+var_30.nSamplesPerSec], edx
0x180016930  movzx   eax, cx
0x180016933  mov     [rbp+var_30.nBlockAlign], ax
0x180016937  imul    eax, edx
0x18001693a  cmp     dword ptr [r8+10h], 2
0x18001693f  mov     [rbp+var_30.nAvgBytesPerSec], eax
0x180016942  ja      short loc_1800169AF
0x180016944  mov     eax, [r8+14h]
0x180016948  shl     eax, 3
0x18001694b  cmp     [r8+18h], eax
0x18001694f  jnz     short loc_1800169AF
0x180016951  mov     rax, qword ptr cs:_GUID_00000001_0000_0010_8000_00aa00389b71.Data1
0x180016958  sub     rax, [r8]
0x18001695b  jnz     short loc_180016968
0x18001695d  mov     rax, qword ptr cs:_GUID_00000001_0000_0010_8000_00aa00389b71.Data4
0x180016964  sub     rax, [r8+8]
0x180016968  test    rax, rax
0x18001696b  setz    cl
0x18001696e  test    cl, cl
0x180016970  jnz     short loc_18001698B
0x180016972  mov     rax, qword ptr cs:_GUID_00000003_0000_0010_8000_00aa00389b71.Data1
0x180016979  cmp     rax, [r8]
0x18001697c  jnz     short loc_1800169AF
0x18001697e  mov     rax, qword ptr cs:_GUID_00000003_0000_0010_8000_00aa00389b71.Data4
0x180016985  cmp     rax, [r8+8]
0x180016989  jnz     short loc_1800169AF
0x18001698b  cmp     [r8+20h], r10d
0x18001698f  jnz     short loc_1800169AF
0x180016991  mov     eax, 1
0x180016996  test    cl, cl
0x180016998  jnz     short loc_18001699F
0x18001699a  mov     eax, 3
0x18001699f  mov     [rbp+var_30.wFormatTag], ax
0x1800169a3  mov     edx, 12h
0x1800169a8  mov     [rbp+var_30.cbSize], r10w
0x1800169ad  jmp     short loc_1800169DF
0x1800169af  movups  xmm0, xmmword ptr [r8]
0x1800169b3  mov     eax, 0FFFEh
0x1800169b8  mov     edx, 28h ; '('; unsigned int
0x1800169bd  mov     [rbp+var_30.wFormatTag], ax
0x1800169c1  mov     eax, 16h
0x1800169c6  mov     [rbp+var_30.cbSize], ax
0x1800169ca  movzx   eax, word ptr [r8+18h]
0x1800169cf  mov     word ptr [rbp+var_1E], ax
0x1800169d3  mov     eax, [r8+20h]
0x1800169d7  mov     dword ptr [rbp+var_1E+2], eax
0x1800169da  movdqu  [rbp+var_1E+6], xmm0
0x1800169df  movss   xmm3, dword ptr [r8+1Ch]; float
0x1800169e5  lea     rcx, [rbp+var_30]; struct tWAVEFORMATEX *
0x1800169e9  mov     r8, r9; struct IAudioMediaType **
0x1800169ec  mov     [rsp+60h+var_40], r10d; int
0x1800169f1  call    ?Create@CAudioMediaType@@SAJPEBUtWAVEFORMATEX@@IPEAPEAUIAudioMediaType@@MH@Z; CAudioMediaType::Create(tWAVEFORMATEX const *,uint,IAudioMediaType * *,float,int)
0x1800169f6  mov     rcx, [rbp+var_8]
0x1800169fa  xor     rcx, rsp; StackCookie
0x1800169fd  call    __security_check_cookie
0x180016a02  add     rsp, 60h
0x180016a06  pop     rbp
0x180016a07  retn
```
