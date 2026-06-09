# ValidateVideoEncoderCodecConfig(D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION const &,D3D12_VIDEO_ENCODER_CODEC const &,TDebugOutputFunctor &)

- ea: `0x180126168`
- end: `0x1801262e3`
- name: `?ValidateVideoEncoderCodecConfig@@YAJAEBUD3D12_VIDEO_ENCODER_CODEC_CONFIGURATION@@AEBW4D3D12_VIDEO_ENCODER_CODEC@@AEAUTDebugOutputFunctor@@@Z`
- size: `379`
- prototype: `__int64 __fastcall(const struct D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION *, const enum D3D12_VIDEO_ENCODER_CODEC *, struct TDebugOutputFunctor *)`
- caller_count: `8`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800b015c`
- `0x180120f6c`
- `0x180121330`
- `0x18012189c`
- `0x180124d88`
- `0x180124e00`
- `0x180125274`
- `0x1801262ec`

## callees

- `0x18002ef50`
- `0x180126168`

## string_xrefs

- `0x1801262ae`: `D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION_H264 structure arguments are not valid.`
- `0x180126295`: `The data size of the structure passed in D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION.pH264Config. does not match the expected size of D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION_H264 Expected size: %d Received size: %d`
- `0x1801261e9`: `D3D12_VIDEO_ENCODER_AV1_CODEC_CONFIGURATION structure arguments are not valid.`
- `0x18012624a`: `D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC structure arguments are not valid.`
- `0x1801261d0`: `The data size of the structure passed in D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION.pAV1Config. does not match the expected size of D3D12_VIDEO_ENCODER_AV1_CODEC_CONFIGURATION Expected size: %d Received size: %d`
- `0x180126231`: `The data size of the structure passed in D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION.pHEVCConfig. does not match the expected size of D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC Expected size: %d Received size: %d`

## pseudocode

```c
__int64 __fastcall ValidateVideoEncoderCodecConfig(
        const struct D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION *a1,
        const enum D3D12_VIDEO_ENCODER_CODEC *a2,
        struct TDebugOutputFunctor *a3)
{
  int v3; // r9d
  char v6; // bl
  int v7; // r9d
  _DWORD *v8; // rax
  int v9; // ebp
  bool v10; // si
  bool v11; // zf
  _DWORD *v12; // rax
  int v13; // ebp
  _DWORD *v14; // rax
  int v15; // ebp

  v3 = *(_DWORD *)a2;
  if ( *(int *)a2 >= 3 )
    return 2147942487LL;
  v6 = 0;
  if ( !v3 )
  {
    v14 = (_DWORD *)*((_QWORD *)a1 + 1);
    v6 = 1;
    v15 = *(_DWORD *)a1;
    v10 = v14 && (*v14 & 0xFFFFFFF0) == 0 && (int)v14[1] < 3;
    if ( v15 != 12 )
      TDebugOutputFunctor::operator()(
        a3,
        1309,
        "The data size of the structure passed in D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION.pH264Config. does not match the"
        " expected size of D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION_H264 Expected size: %d Received size: %d",
        12,
        *(_DWORD *)a1);
    if ( !v10 )
      TDebugOutputFunctor::operator()(
        a3,
        1309,
        "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION_H264 structure arguments are not valid.");
    v11 = v15 == 12;
    goto LABEL_34;
  }
  v7 = v3 - 1;
  if ( !v7 )
  {
    v12 = (_DWORD *)*((_QWORD *)a1 + 1);
    v6 = 1;
    v13 = *(_DWORD *)a1;
    v10 = v12 && (*v12 & 0xFFF80000) == 0;
    if ( v13 != 24 )
      TDebugOutputFunctor::operator()(
        a3,
        1309,
        "The data size of the structure passed in D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION.pHEVCConfig. does not match the"
        " expected size of D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC Expected size: %d Received size: %d",
        24,
        *(_DWORD *)a1);
    if ( !v10 )
      TDebugOutputFunctor::operator()(
        a3,
        1309,
        "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC structure arguments are not valid.");
    v11 = v13 == 24;
    goto LABEL_34;
  }
  if ( v7 == 1 )
  {
    v8 = (_DWORD *)*((_QWORD *)a1 + 1);
    v6 = 1;
    v9 = *(_DWORD *)a1;
    v10 = v8 && (*v8 & 0xF8000000) == 0;
    if ( v9 != 8 )
      TDebugOutputFunctor::operator()(
        a3,
        1309,
        "The data size of the structure passed in D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION.pAV1Config. does not match the "
        "expected size of D3D12_VIDEO_ENCODER_AV1_CODEC_CONFIGURATION Expected size: %d Received size: %d",
        8,
        *(_DWORD *)a1);
    if ( !v10 )
      TDebugOutputFunctor::operator()(
        a3,
        1309,
        "D3D12_VIDEO_ENCODER_AV1_CODEC_CONFIGURATION structure arguments are not valid.");
    v11 = v9 == 8;
LABEL_34:
    if ( !v11 || !v10 )
      v6 = 0;
  }
  return v6 == 0 ? 0x80070057 : 0;
}

```

## disassembly

```asm
0x180126168  push    rbx
0x18012616a  push    rbp
0x18012616b  push    rsi
0x18012616c  push    r14
0x18012616e  sub     rsp, 38h
0x180126172  mov     r9d, [rdx]
0x180126175  mov     r14, r8
0x180126178  cmp     r9d, 3
0x18012617c  jl      short loc_180126188
0x18012617e  mov     eax, 80070057h
0x180126183  jmp     loc_1801262D9
0x180126188  xor     bl, bl
0x18012618a  test    r9d, r9d
0x18012618d  jz      loc_180126263
0x180126193  sub     r9d, 1
0x180126197  jz      short loc_180126205
0x180126199  cmp     r9d, 1
0x18012619d  jnz     loc_1801262CE
0x1801261a3  mov     rax, [rcx+8]
0x1801261a7  mov     bl, r9b
0x1801261aa  mov     ebp, [rcx]
0x1801261ac  test    rax, rax
0x1801261af  jz      short loc_1801261BE
0x1801261b1  test    dword ptr [rax], 0F8000000h
0x1801261b7  jnz     short loc_1801261BE
0x1801261b9  mov     sil, bl
0x1801261bc  jmp     short loc_1801261C1
0x1801261be  xor     sil, sil
0x1801261c1  cmp     ebp, 8
0x1801261c4  jz      short loc_1801261E4
0x1801261c6  mov     r9d, 8
0x1801261cc  mov     [rsp+58h+var_38], ebp
0x1801261d0  lea     r8, aTheDataSizeOfT_7; "The data size of the structure passed i"...
0x1801261d7  mov     edx, 51Dh
0x1801261dc  mov     rcx, r14
0x1801261df  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1801261e4  test    sil, sil
0x1801261e7  jnz     short loc_1801261FD
0x1801261e9  lea     r8, aD3d12VideoEnco_130; "D3D12_VIDEO_ENCODER_AV1_CODEC_CONFIGURA"...
0x1801261f0  mov     edx, 51Dh
0x1801261f5  mov     rcx, r14
0x1801261f8  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1801261fd  cmp     ebp, 8
0x180126200  jmp     loc_1801262C5
0x180126205  mov     rax, [rcx+8]
0x180126209  mov     bl, 1
0x18012620b  mov     ebp, [rcx]
0x18012620d  test    rax, rax
0x180126210  jz      short loc_18012621F
0x180126212  test    dword ptr [rax], 0FFF80000h
0x180126218  jnz     short loc_18012621F
0x18012621a  mov     sil, bl
0x18012621d  jmp     short loc_180126222
0x18012621f  xor     sil, sil
0x180126222  cmp     ebp, 18h
0x180126225  jz      short loc_180126245
0x180126227  mov     r9d, 18h
0x18012622d  mov     [rsp+58h+var_38], ebp
0x180126231  lea     r8, aTheDataSizeOfT_16; "The data size of the structure passed i"...
0x180126238  mov     edx, 51Dh
0x18012623d  mov     rcx, r14
0x180126240  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180126245  test    sil, sil
0x180126248  jnz     short loc_18012625E
0x18012624a  lea     r8, aD3d12VideoEnco_52; "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION"...
0x180126251  mov     edx, 51Dh
0x180126256  mov     rcx, r14
0x180126259  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18012625e  cmp     ebp, 18h
0x180126261  jmp     short loc_1801262C5
0x180126263  mov     rax, [rcx+8]
0x180126267  mov     bl, 1
0x180126269  mov     ebp, [rcx]
0x18012626b  test    rax, rax
0x18012626e  jz      short loc_180126283
0x180126270  test    dword ptr [rax], 0FFFFFFF0h
0x180126276  jnz     short loc_180126283
0x180126278  cmp     dword ptr [rax+4], 3
0x18012627c  jge     short loc_180126283
0x18012627e  mov     sil, bl
0x180126281  jmp     short loc_180126286
0x180126283  xor     sil, sil
0x180126286  cmp     ebp, 0Ch
0x180126289  jz      short loc_1801262A9
0x18012628b  mov     r9d, 0Ch
0x180126291  mov     [rsp+58h+var_38], ebp
0x180126295  lea     r8, aTheDataSizeOfT_10; "The data size of the structure passed i"...
0x18012629c  mov     edx, 51Dh
0x1801262a1  mov     rcx, r14
0x1801262a4  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1801262a9  test    sil, sil
0x1801262ac  jnz     short loc_1801262C2
0x1801262ae  lea     r8, aD3d12VideoEnco_132; "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION"...
0x1801262b5  mov     edx, 51Dh
0x1801262ba  mov     rcx, r14
0x1801262bd  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1801262c2  cmp     ebp, 0Ch
0x1801262c5  jnz     short loc_1801262CC
0x1801262c7  test    sil, sil
0x1801262ca  jnz     short loc_1801262CE
0x1801262cc  xor     bl, bl
0x1801262ce  neg     bl
0x1801262d0  sbb     eax, eax
0x1801262d2  not     eax
0x1801262d4  and     eax, 80070057h
0x1801262d9  add     rsp, 38h
0x1801262dd  pop     r14
0x1801262df  pop     rsi
0x1801262e0  pop     rbp
0x1801262e1  pop     rbx
0x1801262e2  retn
```
