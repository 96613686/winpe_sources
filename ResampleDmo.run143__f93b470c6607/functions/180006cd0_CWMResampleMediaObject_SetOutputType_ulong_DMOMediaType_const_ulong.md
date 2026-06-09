# CWMResampleMediaObject::SetOutputType(ulong,_DMOMediaType const *,ulong)

- ea: `0x180006cd0`
- end: `0x180006ef1`
- name: `?SetOutputType@CWMResampleMediaObject@@UEAAJKPEBU_DMOMediaType@@K@Z`
- size: `545`
- prototype: `int(CWMResampleMediaObject *__hidden this, unsigned int, const struct _DMOMediaType *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180006cd0`
- `0x18000715c`
- `0x1800071b0`
- `0x18000737c`
- `0x180008e50`
- `0x180084684`

## import_xrefs

- `msdmo!MoCopyMediaType` at `0x180006e24`
- `msdmo!MoCopyMediaType` at `0x180006e24`
- `msdmo!MoFreeMediaType` at `0x180006d2b`
- `msdmo!MoFreeMediaType` at `0x180006e17`
- `msdmo!MoFreeMediaType` at `0x180006d2b`
- `msdmo!MoFreeMediaType` at `0x180006e17`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006e33`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006ecc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006ed9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006e33`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006ecc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006ed9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006cf2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006cf2`

## pseudocode

```c
__int64 __fastcall CWMResampleMediaObject::SetOutputType(
        CWMResampleMediaObject *this,
        int a2,
        const struct _DMOMediaType *a3,
        char a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // r14
  unsigned int v9; // ebx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rbp
  unsigned int v13; // eax
  HRESULT v14; // eax
  unsigned int v15; // edx
  NResampler *v17; // rcx
  bool v18; // zf
  _OWORD v19[6]; // [rsp+20h] [rbp-68h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 200);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 5);
  if ( a2 )
  {
    v9 = -2147220991;
LABEL_30:
    LeaveCriticalSection(v4);
    return v9;
  }
  if ( (a4 & 2) != 0 )
  {
    v9 = 1;
    if ( !*((_DWORD *)this + 3) )
      goto LABEL_30;
    if ( (a4 & 1) == 0 )
    {
      *((_DWORD *)this + 3) = 0;
      MoFreeMediaType((DMO_MEDIA_TYPE *)((char *)this + 104));
    }
LABEL_7:
    v9 = 0;
    goto LABEL_30;
  }
  if ( !a3 )
  {
    v9 = -2147467261;
    goto LABEL_30;
  }
  if ( (-(__int64)(*((_DWORD *)this + 2) != 0) & ((unsigned __int64)this + 16)) == 0 )
  {
    v9 = -2147220989;
    goto LABEL_30;
  }
  if ( !ValidateAudioType((char *)this + 16, a3) )
    goto LABEL_37;
  v10 = *((_QWORD *)a3 + 2) - *(_QWORD *)&MEDIASUBTYPE_PCM.Data1;
  if ( !v10 )
    v10 = *((_QWORD *)a3 + 3) - *(_QWORD *)MEDIASUBTYPE_PCM.Data4;
  if ( v10 )
  {
    v11 = *((_QWORD *)a3 + 2) - *(_QWORD *)&MEDIASUBTYPE_IEEE_FLOAT.Data1;
    if ( !v11 )
      v11 = *((_QWORD *)a3 + 3) - *(_QWORD *)MEDIASUBTYPE_IEEE_FLOAT.Data4;
    if ( v11 )
      goto LABEL_37;
  }
  v12 = *((_QWORD *)a3 + 10);
  if ( !ResampIsValidWaveFormat((struct WAVEFORMATEXTENSIBLE *)v12) )
    goto LABEL_37;
  if ( !*((_DWORD *)this + 3) )
    goto LABEL_25;
  v13 = *((_DWORD *)this + 44);
  if ( v13 >= *((_DWORD *)a3 + 18) )
    v13 = *((_DWORD *)a3 + 18);
  if ( !memcmp_0((const void *)v12, *((const void **)this + 23), v13) )
    goto LABEL_7;
  if ( *((_QWORD *)this + 63) )
  {
LABEL_37:
    LeaveCriticalSection(v4);
    return 2147746309LL;
  }
  else
  {
LABEL_25:
    if ( (a4 & 1) != 0 )
      goto LABEL_7;
    if ( *((_DWORD *)this + 3) )
      MoFreeMediaType((DMO_MEDIA_TYPE *)((char *)this + 104));
    v14 = MoCopyMediaType((DMO_MEDIA_TYPE *)((char *)this + 104), (const DMO_MEDIA_TYPE *)a3);
    if ( v14 < 0 )
    {
      v9 = v14;
      goto LABEL_30;
    }
    v17 = (NResampler *)*((_QWORD *)this + 33);
    *((_DWORD *)this + 3) = 1;
    if ( v17 )
    {
      NResampler::`scalar deleting destructor'(v17, v15);
      *((_QWORD *)this + 33) = 0;
    }
    memset(v19, 0, 34);
    *(_OWORD *)((char *)this + 312) = v19[0];
    *(_OWORD *)((char *)this + 328) = v19[1];
    *((_QWORD *)this + 43) = 0;
    v18 = *(_WORD *)v12 == 0xFFFE;
    *(_OWORD *)((char *)this + 312) = *(_OWORD *)v12;
    if ( v18 )
    {
      *(_OWORD *)((char *)this + 328) = *(_OWORD *)(v12 + 16);
      *((_QWORD *)this + 43) = *(_QWORD *)(v12 + 32);
    }
    else
    {
      *((_WORD *)this + 164) = *(_WORD *)(v12 + 16);
    }
    WaveFormatEx2PCMFormat((char *)this + 312, (char *)this + 376);
    LeaveCriticalSection(v4);
    return 0;
  }
}

```

## disassembly

```asm
0x180006cd0  push    rbx
0x180006cd2  push    rbp
0x180006cd3  push    rsi
0x180006cd4  push    rdi
0x180006cd5  push    r14
0x180006cd7  push    r15
0x180006cd9  sub     rsp, 58h
0x180006cdd  lea     r14, [rcx+0C8h]
0x180006ce4  mov     rdi, rcx
0x180006ce7  mov     rcx, r14; lpCriticalSection
0x180006cea  mov     r15d, r9d
0x180006ced  mov     rsi, r8
0x180006cf0  mov     ebx, edx
0x180006cf2  call    cs:__imp_EnterCriticalSection
0x180006cf8  test    ebx, ebx
0x180006cfa  jz      short loc_180006D06
0x180006cfc  mov     ebx, 80040201h
0x180006d01  jmp     loc_180006E30
0x180006d06  test    r15b, 2
0x180006d0a  jz      short loc_180006D38
0x180006d0c  cmp     dword ptr [rdi+0Ch], 0
0x180006d10  mov     ebx, 1
0x180006d15  jz      loc_180006E30
0x180006d1b  test    bl, r15b
0x180006d1e  jnz     short loc_180006D31
0x180006d20  lea     rcx, [rdi+68h]; pmt
0x180006d24  mov     dword ptr [rdi+0Ch], 0
0x180006d2b  call    cs:__imp_MoFreeMediaType
0x180006d31  xor     ebx, ebx
0x180006d33  jmp     loc_180006E30
0x180006d38  test    rsi, rsi
0x180006d3b  jnz     short loc_180006D47
0x180006d3d  mov     ebx, 80004003h
0x180006d42  jmp     loc_180006E30
0x180006d47  mov     eax, [rdi+8]
0x180006d4a  lea     rcx, [rdi+10h]; void *
0x180006d4e  neg     eax
0x180006d50  sbb     rax, rax
0x180006d53  test    rcx, rax
0x180006d56  jnz     short loc_180006D62
0x180006d58  mov     ebx, 80040203h
0x180006d5d  jmp     loc_180006E30
0x180006d62  mov     rdx, rsi; struct _DMOMediaType *
0x180006d65  call    ?ValidateAudioType@@YAHPEAXPEBU_DMOMediaType@@@Z; ValidateAudioType(void *,_DMOMediaType const *)
0x180006d6a  test    eax, eax
0x180006d6c  jz      loc_180006ED6
0x180006d72  mov     rax, [rsi+10h]
0x180006d76  sub     rax, qword ptr cs:MEDIASUBTYPE_PCM.Data1
0x180006d7d  jnz     short loc_180006D8A
0x180006d7f  mov     rax, [rsi+18h]
0x180006d83  sub     rax, qword ptr cs:MEDIASUBTYPE_PCM.Data4
0x180006d8a  test    rax, rax
0x180006d8d  jz      short loc_180006DB0
0x180006d8f  mov     rax, [rsi+10h]
0x180006d93  sub     rax, qword ptr cs:MEDIASUBTYPE_IEEE_FLOAT.Data1
0x180006d9a  jnz     short loc_180006DA7
0x180006d9c  mov     rax, [rsi+18h]
0x180006da0  sub     rax, qword ptr cs:MEDIASUBTYPE_IEEE_FLOAT.Data4
0x180006da7  test    rax, rax
0x180006daa  jnz     loc_180006ED6
0x180006db0  mov     rbp, [rsi+50h]
0x180006db4  mov     rcx, rbp; struct WAVEFORMATEXTENSIBLE *
0x180006db7  call    ?ResampIsValidWaveFormat@@YAHPEAUWAVEFORMATEXTENSIBLE@@@Z; ResampIsValidWaveFormat(WAVEFORMATEXTENSIBLE *)
0x180006dbc  test    eax, eax
0x180006dbe  jz      loc_180006ED6
0x180006dc4  cmp     dword ptr [rdi+0Ch], 0
0x180006dc8  jz      short loc_180006DFF
0x180006dca  mov     eax, [rdi+0B0h]
0x180006dd0  mov     rcx, rbp; Buf1
0x180006dd3  cmp     eax, [rsi+48h]
0x180006dd6  mov     rdx, [rdi+0B8h]; Buf2
0x180006ddd  cmovnb  eax, [rsi+48h]
0x180006de1  mov     r8d, eax; Size
0x180006de4  call    memcmp_0
0x180006de9  test    eax, eax
0x180006deb  jz      loc_180006D31
0x180006df1  cmp     qword ptr [rdi+1F8h], 0
0x180006df9  jnz     loc_180006ED6
0x180006dff  mov     ebx, 1
0x180006e04  test    bl, r15b
0x180006e07  jnz     loc_180006D31
0x180006e0d  cmp     dword ptr [rdi+0Ch], 0
0x180006e11  jz      short loc_180006E1D
0x180006e13  lea     rcx, [rdi+68h]; pmt
0x180006e17  call    cs:__imp_MoFreeMediaType
0x180006e1d  mov     rdx, rsi; pmtSrc
0x180006e20  lea     rcx, [rdi+68h]; pmtDest
0x180006e24  call    cs:__imp_MoCopyMediaType
0x180006e2a  test    eax, eax
0x180006e2c  jns     short loc_180006E40
0x180006e2e  mov     ebx, eax
0x180006e30  mov     rcx, r14; lpCriticalSection
0x180006e33  call    cs:__imp_LeaveCriticalSection
0x180006e39  mov     eax, ebx
0x180006e3b  jmp     loc_180006EE4
0x180006e40  mov     rcx, [rdi+108h]; this
0x180006e47  mov     [rdi+0Ch], ebx
0x180006e4a  test    rcx, rcx
0x180006e4d  jz      short loc_180006E5F
0x180006e4f  call    ??_GNResampler@@QEAAPEAXI@Z; NResampler::`scalar deleting destructor'(uint)
0x180006e54  mov     qword ptr [rdi+108h], 0
0x180006e5f  xor     eax, eax
0x180006e61  lea     rcx, [rdi+138h]
0x180006e68  xorps   xmm0, xmm0
0x180006e6b  mov     word ptr [rsp+88h+var_68], ax
0x180006e70  movups  [rsp+88h+var_68+2], xmm0
0x180006e75  movups  [rsp+88h+var_56], xmm0
0x180006e7a  movups  xmm0, [rsp+88h+var_68]
0x180006e7f  movups  xmm1, xmmword ptr [rsp+30h]
0x180006e84  movups  xmmword ptr [rcx], xmm0
0x180006e87  movups  xmmword ptr [rcx+10h], xmm1
0x180006e8b  mov     [rcx+20h], rax
0x180006e8f  mov     eax, 0FFFEh
0x180006e94  movups  xmm0, xmmword ptr [rbp+0]
0x180006e98  cmp     [rbp+0], ax
0x180006e9c  movups  xmmword ptr [rcx], xmm0
0x180006e9f  jnz     short loc_180006EB5
0x180006ea1  movups  xmm1, xmmword ptr [rbp+10h]
0x180006ea5  movups  xmmword ptr [rcx+10h], xmm1
0x180006ea9  movsd   xmm0, qword ptr [rbp+20h]
0x180006eae  movsd   qword ptr [rcx+20h], xmm0
0x180006eb3  jmp     short loc_180006EBD
0x180006eb5  movzx   eax, word ptr [rbp+10h]
0x180006eb9  mov     [rcx+10h], ax
0x180006ebd  lea     rdx, [rdi+178h]
0x180006ec4  call    WaveFormatEx2PCMFormat
0x180006ec9  mov     rcx, r14; lpCriticalSection
0x180006ecc  call    cs:__imp_LeaveCriticalSection
0x180006ed2  xor     eax, eax
0x180006ed4  jmp     short loc_180006EE4
0x180006ed6  mov     rcx, r14; lpCriticalSection
0x180006ed9  call    cs:__imp_LeaveCriticalSection
0x180006edf  mov     eax, 80040205h
0x180006ee4  add     rsp, 58h
0x180006ee8  pop     r15
0x180006eea  pop     r14
0x180006eec  pop     rdi
0x180006eed  pop     rsi
0x180006eee  pop     rbp
0x180006eef  pop     rbx
0x180006ef0  retn
```
