# CAACDecTransform::DoCheckOutputType(IMFMediaType *,IMFMediaType *)

- ea: `0x18003f8c0`
- end: `0x18003fbd7`
- name: `?DoCheckOutputType@CAACDecTransform@@MEAAJPEAUIMFMediaType@@0@Z`
- size: `791`
- prototype: `__int64 __fastcall(CAACDecTransform *this, struct IMFMediaType *, struct IMFMediaType *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003af0`
- `0x18003f8c0`
- `0x18003fbe0`
- `0x180096060`

## import_xrefs

- `MFPlat!MFCreateWaveFormatExFromMFMediaType` at `0x18003f925`
- `MFPlat!MFCreateWaveFormatExFromMFMediaType` at `0x18003f9c2`
- `MFPlat!MFCreateWaveFormatExFromMFMediaType` at `0x18003f925`
- `MFPlat!MFCreateWaveFormatExFromMFMediaType` at `0x18003f9c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f946`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f95b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f946`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f95b`

## pseudocode

```c
__int64 __fastcall CAACDecTransform::DoCheckOutputType(
        CAACDecTransform *this,
        struct IMFMediaType *a2,
        struct IMFMediaType *a3)
{
  TraceLoggingHelperBase *v6; // r12
  HRESULT v7; // ebx
  void *v8; // rdi
  WAVEFORMATEX *v10; // rsi
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  WORD nChannels; // ax
  DWORD nSamplesPerSec; // eax
  unsigned int v16; // eax
  int v17; // r8d
  LPVOID pv; // [rsp+80h] [rbp+40h] BYREF
  WAVEFORMATEX *ppWF; // [rsp+98h] [rbp+58h] BYREF

  v6 = (CAACDecTransform *)((char *)this + 246640);
  TraceLoggingHelperBase::TraceVA(
    (CAACDecTransform *)((char *)this + 246640),
    4u,
    "CAACDecTransform::DoCheckOutputType",
    0x33Du,
    "CAACDecTransform::DoCheckOutputType()");
  ppWF = 0;
  pv = 0;
  v7 = MFCreateWaveFormatExFromMFMediaType(a2, &ppWF, 0, 0);
  if ( v7 < 0 )
    goto LABEL_2;
  CAACDecTransform::LogMediaTypeAttributes((CAACDecTransform *)((char *)this - 24), a2);
  if ( ppWF->wFormatTag != 5648
    && ((unsigned __int16)(ppWF->nChannels - 1) > 5u || ((ppWF->wBitsPerSample - 16) & 0xFFEF) != 0) )
  {
LABEL_19:
    v7 = -1072875852;
    goto LABEL_20;
  }
  v10 = 0;
  if ( ppWF->wFormatTag != 1 && ppWF->wFormatTag != 3 )
  {
    if ( ppWF->wFormatTag == 5648 )
    {
      if ( ppWF->cbSize < 0xCu )
        goto LABEL_19;
    }
    else
    {
      if ( ppWF->wFormatTag != 65534 || ppWF->cbSize != 22 )
        goto LABEL_19;
      v10 = ppWF;
      v12 = *(_QWORD *)((char *)&ppWF[1].nSamplesPerSec + 2)
          - *(_QWORD *)&GUID_00000003_0000_0010_8000_00aa00389b71.Data1;
      if ( !v12 )
        v12 = *(_QWORD *)&ppWF[1].wBitsPerSample - *(_QWORD *)GUID_00000003_0000_0010_8000_00aa00389b71.Data4;
      if ( v12 )
      {
        v13 = *(_QWORD *)((char *)&ppWF[1].nSamplesPerSec + 2)
            - *(_QWORD *)&GUID_00000001_0000_0010_8000_00aa00389b71.Data1;
        if ( !v13 )
          v13 = *(_QWORD *)&ppWF[1].wBitsPerSample - *(_QWORD *)GUID_00000001_0000_0010_8000_00aa00389b71.Data4;
        if ( v13 )
          goto LABEL_19;
      }
    }
  }
  if ( !a3 || (v7 = MFCreateWaveFormatExFromMFMediaType(a3, (WAVEFORMATEX **)&pv, 0, 0), v7 < 0) )
  {
LABEL_2:
    v8 = pv;
    goto LABEL_3;
  }
  v8 = pv;
  if ( ppWF->wFormatTag == 5648 )
  {
    nChannels = ppWF->nChannels;
    if ( nChannels && *((_WORD *)pv + 1) != nChannels )
      goto LABEL_19;
    nSamplesPerSec = ppWF->nSamplesPerSec;
    if ( nSamplesPerSec )
    {
      if ( *((_DWORD *)pv + 1) != nSamplesPerSec )
        goto LABEL_19;
    }
    v16 = ppWF->cbSize - 12;
    if ( ppWF->cbSize != 12 )
    {
      v17 = *((_DWORD *)this + 61658);
      if ( v17 )
      {
        if ( v16 != v17 )
        {
          TraceLoggingHelperBase::TraceVA(
            v6,
            4u,
            "CAACDecTransform::DoCheckOutputType",
            0x3E2u,
            "CAACDecTransform::DoCheckOutputType() ASC blob size does not match");
          goto LABEL_19;
        }
        if ( memcmp_0(&ppWF[1].nBlockAlign, (char *)this + 246504, v16) )
        {
          TraceLoggingHelperBase::TraceVA(
            v6,
            4u,
            "CAACDecTransform::DoCheckOutputType",
            0x3E9u,
            "CAACDecTransform::DoCheckOutputType() ASC blob does not match");
          goto LABEL_19;
        }
      }
    }
  }
  else
  {
    if ( *(_WORD *)pv != ppWF->wFormatTag
      || *((_WORD *)pv + 1) != ppWF->nChannels
      || *((_DWORD *)pv + 1) != ppWF->nSamplesPerSec
      || *((_WORD *)pv + 7) != ppWF->wBitsPerSample )
    {
      goto LABEL_19;
    }
    if ( *(_WORD *)pv == 0xFFFE )
    {
      v11 = *((_QWORD *)pv + 3) - *(_QWORD *)((char *)&v10[1].nSamplesPerSec + 2);
      if ( !v11 )
        v11 = *((_QWORD *)pv + 4) - *(_QWORD *)&v10[1].wBitsPerSample;
      if ( v11 || *((_DWORD *)pv + 5) != *(_DWORD *)&v10[1].nChannels )
        goto LABEL_19;
    }
  }
LABEL_3:
  if ( v7 )
  {
LABEL_20:
    TraceLoggingHelperBase::TraceVA(
      v6,
      2u,
      "CAACDecTransform::DoCheckOutputType",
      0x3F4u,
      "Error %08X returned: File: %s, Line: %d",
      v7,
      "avcore\\codecdsp\\audio\\aacdec\\current\\mft\\aacdectransformxheaac.cpp",
      1012);
    v8 = pv;
  }
  CoTaskMemFree(v8);
  pv = 0;
  CoTaskMemFree(ppWF);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003f8c0  mov     [rsp-38h+arg_8], rbx
0x18003f8c5  push    rbp
0x18003f8c6  push    rsi
0x18003f8c7  push    rdi
0x18003f8c8  push    r12
0x18003f8ca  push    r13
0x18003f8cc  push    r14
0x18003f8ce  push    r15
0x18003f8d0  mov     rbp, rsp
0x18003f8d3  sub     rsp, 40h
0x18003f8d7  mov     r15, r8
0x18003f8da  mov     rdi, rdx
0x18003f8dd  mov     r14, rcx
0x18003f8e0  lea     r12, [rcx+3C370h]
0x18003f8e7  lea     rax, aCaacdectransfo_24; "CAACDecTransform::DoCheckOutputType()"
0x18003f8ee  mov     [rsp+40h+Format], rax; Format
0x18003f8f3  mov     r9d, 33Dh; unsigned int
0x18003f8f9  lea     r8, aCaacdectransfo_10; "CAACDecTransform::DoCheckOutputType"
0x18003f900  mov     edx, 4; unsigned __int8
0x18003f905  mov     rcx, r12; this
0x18003f908  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18003f90d  xor     r13d, r13d
0x18003f910  mov     [rbp+ppWF], r13
0x18003f914  mov     [rbp+pv], r13
0x18003f918  xor     r9d, r9d; Flags
0x18003f91b  xor     r8d, r8d; pcbSize
0x18003f91e  lea     rdx, [rbp+ppWF]; ppWF
0x18003f922  mov     rcx, rdi; pMFType
0x18003f925  call    cs:__imp_MFCreateWaveFormatExFromMFMediaType
0x18003f92c  nop     dword ptr [rax+rax+00h]
0x18003f931  mov     ebx, eax
0x18003f933  test    eax, eax
0x18003f935  jns     short loc_18003F983
0x18003f937  mov     rdi, [rbp+pv]
0x18003f93b  test    ebx, ebx
0x18003f93d  jnz     loc_18003FA43
0x18003f943  mov     rcx, rdi; pv
0x18003f946  call    cs:__imp_CoTaskMemFree
0x18003f94d  nop     dword ptr [rax+rax+00h]
0x18003f952  nop
0x18003f953  mov     [rbp+pv], r13
0x18003f957  mov     rcx, [rbp+ppWF]; pv
0x18003f95b  call    cs:__imp_CoTaskMemFree
0x18003f962  nop     dword ptr [rax+rax+00h]
0x18003f967  nop
0x18003f968  mov     eax, ebx
0x18003f96a  mov     rbx, [rsp+40h+arg_8]
0x18003f972  add     rsp, 40h
0x18003f976  pop     r15
0x18003f978  pop     r14
0x18003f97a  pop     r13
0x18003f97c  pop     r12
0x18003f97e  pop     rdi
0x18003f97f  pop     rsi
0x18003f980  pop     rbp
0x18003f981  retn
0x18003f983  lea     rcx, [r14-18h]; this
0x18003f987  mov     rdx, rdi; struct IMFMediaType *
0x18003f98a  call    ?LogMediaTypeAttributes@CAACDecTransform@@AEAAXPEAUIMFMediaType@@@Z; CAACDecTransform::LogMediaTypeAttributes(IMFMediaType *)
0x18003f98f  mov     rcx, [rbp+ppWF]
0x18003f993  mov     edi, 1610h
0x18003f998  cmp     [rcx], di
0x18003f99b  jnz     loc_18003FAD1
0x18003f9a1  mov     rsi, r13
0x18003f9a4  movzx   edx, word ptr [rcx]
0x18003f9a7  sub     edx, 1
0x18003f9aa  jnz     loc_18003FAFD
0x18003f9b0  test    r15, r15
0x18003f9b3  jz      short loc_18003F937
0x18003f9b5  xor     r9d, r9d; Flags
0x18003f9b8  xor     r8d, r8d; pcbSize
0x18003f9bb  lea     rdx, [rbp+pv]; ppWF
0x18003f9bf  mov     rcx, r15; pMFType
0x18003f9c2  call    cs:__imp_MFCreateWaveFormatExFromMFMediaType
0x18003f9c9  nop     dword ptr [rax+rax+00h]
0x18003f9ce  mov     ebx, eax
0x18003f9d0  test    eax, eax
0x18003f9d2  js      loc_18003F937
0x18003f9d8  mov     rcx, [rbp+ppWF]
0x18003f9dc  movzx   eax, word ptr [rcx]
0x18003f9df  cmp     ax, di
0x18003f9e2  mov     rdi, [rbp+pv]
0x18003f9e6  jz      loc_18003FB3A
0x18003f9ec  cmp     [rdi], ax
0x18003f9ef  jnz     short loc_18003FA3E
0x18003f9f1  movzx   eax, word ptr [rcx+2]
0x18003f9f5  cmp     [rdi+2], ax
0x18003f9f9  jnz     short loc_18003FA3E
0x18003f9fb  mov     eax, [rcx+4]
0x18003f9fe  cmp     [rdi+4], eax
0x18003fa01  jnz     short loc_18003FA3E
0x18003fa03  movzx   eax, word ptr [rcx+0Eh]
0x18003fa07  cmp     [rdi+0Eh], ax
0x18003fa0b  jnz     short loc_18003FA3E
0x18003fa0d  mov     eax, 0FFFEh
0x18003fa12  cmp     ax, [rdi]
0x18003fa15  jnz     loc_18003F93B
0x18003fa1b  mov     rax, [rdi+18h]
0x18003fa1f  sub     rax, [rsi+18h]
0x18003fa23  jnz     short loc_18003FA2D
0x18003fa25  mov     rax, [rdi+20h]
0x18003fa29  sub     rax, [rsi+20h]
0x18003fa2d  test    rax, rax
0x18003fa30  jnz     short loc_18003FA3E
0x18003fa32  mov     eax, [rsi+14h]
0x18003fa35  cmp     [rdi+14h], eax
0x18003fa38  jz      loc_18003F93B
0x18003fa3e  mov     ebx, 0C00D36B4h
0x18003fa43  mov     r9d, 3F4h; unsigned int
0x18003fa49  mov     [rsp+40h+var_8], r9d
0x18003fa4e  lea     rax, aAvcoreCodecdsp_0; "avcore\\codecdsp\\audio\\aacdec\\curren"...
0x18003fa55  mov     [rsp+40h+var_10], rax
0x18003fa5a  mov     [rsp+40h+var_18], ebx
0x18003fa5e  lea     rax, aError08xReturn; "Error %08X returned: File: %s, Line: %d"
0x18003fa65  mov     [rsp+40h+Format], rax; Format
0x18003fa6a  lea     r8, aCaacdectransfo_10; "CAACDecTransform::DoCheckOutputType"
0x18003fa71  mov     edx, 2; unsigned __int8
0x18003fa76  mov     rcx, r12; this
0x18003fa79  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18003fa7e  mov     rdi, [rbp+pv]
0x18003fa82  jmp     loc_18003F943
0x18003fa87  mov     rsi, rcx
0x18003fa8a  mov     rax, [rcx+18h]
0x18003fa8e  sub     rax, qword ptr cs:_GUID_00000003_0000_0010_8000_00aa00389b71.Data1
0x18003fa95  jnz     short loc_18003FAA2
0x18003fa97  mov     rax, [rcx+20h]
0x18003fa9b  sub     rax, qword ptr cs:_GUID_00000003_0000_0010_8000_00aa00389b71.Data4
0x18003faa2  test    rax, rax
0x18003faa5  jz      loc_18003F9B0
0x18003faab  mov     rax, [rcx+18h]
0x18003faaf  sub     rax, qword ptr cs:_GUID_00000001_0000_0010_8000_00aa00389b71.Data1
0x18003fab6  jnz     short loc_18003FAC3
0x18003fab8  mov     rax, [rcx+20h]
0x18003fabc  sub     rax, qword ptr cs:_GUID_00000001_0000_0010_8000_00aa00389b71.Data4
0x18003fac3  test    rax, rax
0x18003fac6  jz      loc_18003F9B0
0x18003facc  jmp     loc_18003FA3E
0x18003fad1  movzx   eax, word ptr [rcx+2]
0x18003fad5  dec     ax
0x18003fad8  cmp     ax, 5
0x18003fadc  ja      loc_18003FA3E
0x18003fae2  movzx   eax, word ptr [rcx+0Eh]
0x18003fae6  sub     ax, 10h
0x18003faea  mov     edx, 0FFEFh
0x18003faef  test    dx, ax
0x18003faf2  jz      loc_18003F9A1
0x18003faf8  jmp     loc_18003FA3E
0x18003fafd  sub     edx, 2
0x18003fb00  jz      loc_18003F9B0
0x18003fb06  sub     edx, 160Dh
0x18003fb0c  jz      short loc_18003FB2A
0x18003fb0e  cmp     edx, 0E9EEh
0x18003fb14  jnz     loc_18003FA3E
0x18003fb1a  cmp     word ptr [rcx+10h], 16h
0x18003fb1f  jnz     loc_18003FA3E
0x18003fb25  jmp     loc_18003FA87
0x18003fb2a  cmp     word ptr [rcx+10h], 0Ch
0x18003fb2f  jb      loc_18003FA3E
0x18003fb35  jmp     loc_18003F9B0
0x18003fb3a  movzx   eax, word ptr [rcx+2]
0x18003fb3e  test    ax, ax
0x18003fb41  jz      short loc_18003FB4D
0x18003fb43  cmp     [rdi+2], ax
0x18003fb47  jnz     loc_18003FA3E
0x18003fb4d  mov     eax, [rcx+4]
0x18003fb50  test    eax, eax
0x18003fb52  jz      short loc_18003FB5D
0x18003fb54  cmp     [rdi+4], eax
0x18003fb57  jnz     loc_18003FA3E
0x18003fb5d  movzx   eax, word ptr [rcx+10h]
0x18003fb61  add     eax, 0FFFFFFF4h
0x18003fb64  jz      loc_18003F93B
0x18003fb6a  mov     r8d, [r14+3C368h]
0x18003fb71  test    r8d, r8d
0x18003fb74  jz      loc_18003F93B
0x18003fb7a  cmp     eax, r8d
0x18003fb7d  jz      short loc_18003FBB9
0x18003fb7f  lea     rax, aCaacdectransfo_25; "CAACDecTransform::DoCheckOutputType() A"...
0x18003fb86  mov     r9d, 3E2h
0x18003fb8c  jmp     short loc_18003FB9B
0x18003fb8e  lea     rax, aCaacdectransfo_52; "CAACDecTransform::DoCheckOutputType() A"...
0x18003fb95  mov     r9d, 3E9h; unsigned int
0x18003fb9b  mov     [rsp+40h+Format], rax; Format
0x18003fba0  lea     r8, aCaacdectransfo_10; "CAACDecTransform::DoCheckOutputType"
0x18003fba7  mov     edx, 4; unsigned __int8
0x18003fbac  mov     rcx, r12; this
0x18003fbaf  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18003fbb4  jmp     loc_18003FA3E
0x18003fbb9  mov     r8d, eax; Size
0x18003fbbc  lea     rdx, [r14+3C2E8h]; Buf2
0x18003fbc3  add     rcx, 1Eh; Buf1
0x18003fbc7  call    memcmp_0
0x18003fbcc  test    eax, eax
0x18003fbce  jz      loc_18003F93B
0x18003fbd4  jmp     short loc_18003FB8E
```
