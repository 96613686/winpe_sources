# CWMResampleMediaObject::SetInputType(ulong,_DMOMediaType const *,ulong)

- ea: `0x180006f00`
- end: `0x180007156`
- name: `?SetInputType@CWMResampleMediaObject@@UEAAJKPEBU_DMOMediaType@@K@Z`
- size: `598`
- prototype: `__int64 __fastcall(CWMResampleMediaObject *this, int, const struct _DMOMediaType *, char)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180006f00`
- `0x18000715c`
- `0x1800071b0`
- `0x18000737c`
- `0x180008e50`
- `0x180084684`

## import_xrefs

- `msdmo!MoCopyMediaType` at `0x18000700c`
- `msdmo!MoCopyMediaType` at `0x18000700c`
- `msdmo!MoFreeMediaType` at `0x1800070fe`
- `msdmo!MoFreeMediaType` at `0x18000710d`
- `msdmo!MoFreeMediaType` at `0x180007137`
- `msdmo!MoFreeMediaType` at `0x1800070fe`
- `msdmo!MoFreeMediaType` at `0x18000710d`
- `msdmo!MoFreeMediaType` at `0x180007137`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006f37`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000709d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800070d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006f37`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000709d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800070d8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006f24`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006f24`

## pseudocode

```c
__int64 __fastcall CWMResampleMediaObject::SetInputType(
        CWMResampleMediaObject *this,
        int a2,
        const struct _DMOMediaType *a3,
        char a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // r15
  void *v9; // rcx
  unsigned int v10; // ebx
  __int64 v12; // rax
  __int64 v13; // rbp
  __int64 v14; // rax
  unsigned int v15; // eax
  HRESULT v16; // eax
  unsigned int v17; // edx
  NResampler *v18; // rcx
  bool v19; // zf
  __int64 v20; // rax
  _OWORD v21[6]; // [rsp+20h] [rbp-68h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 200);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 5);
  if ( a2 )
  {
    v10 = -2147220991;
LABEL_3:
    LeaveCriticalSection(v4);
    return v10;
  }
  v10 = 0;
  if ( (a4 & 2) != 0 )
  {
    if ( *((_DWORD *)this + 2) )
    {
      if ( (a4 & 1) == 0 )
      {
        *((_DWORD *)this + 2) = 0;
        MoFreeMediaType((DMO_MEDIA_TYPE *)((char *)this + 16));
      }
    }
    else
    {
      v10 = 1;
    }
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v10 = -2147467261;
    goto LABEL_3;
  }
  if ( !(unsigned int)ValidateAudioType(v9, a3) )
    goto LABEL_34;
  v12 = *((_QWORD *)a3 + 2) - *(_QWORD *)&MEDIASUBTYPE_PCM.Data1;
  if ( !v12 )
    v12 = *((_QWORD *)a3 + 3) - *(_QWORD *)MEDIASUBTYPE_PCM.Data4;
  if ( v12 )
  {
    v20 = *((_QWORD *)a3 + 2) - *(_QWORD *)&MEDIASUBTYPE_IEEE_FLOAT.Data1;
    if ( !v20 )
      v20 = *((_QWORD *)a3 + 3) - *(_QWORD *)MEDIASUBTYPE_IEEE_FLOAT.Data4;
    if ( v20 )
      goto LABEL_34;
  }
  v13 = *((_QWORD *)a3 + 10);
  if ( !ResampIsValidWaveFormat((struct WAVEFORMATEXTENSIBLE *)v13) )
    goto LABEL_34;
  if ( !*((_DWORD *)this + 2) )
    goto LABEL_19;
  v14 = *((_QWORD *)a3 + 2) - *((_QWORD *)this + 4);
  if ( !v14 )
    v14 = *((_QWORD *)a3 + 3) - *((_QWORD *)this + 5);
  if ( !v14 )
  {
    v15 = *((_DWORD *)this + 22);
    if ( v15 >= *((_DWORD *)a3 + 18) )
      v15 = *((_DWORD *)a3 + 18);
    if ( !memcmp_0((const void *)v13, *((const void **)this + 12), v15) )
      goto LABEL_3;
  }
  if ( *((_QWORD *)this + 63) )
  {
LABEL_34:
    LeaveCriticalSection(v4);
    return 2147746309LL;
  }
  else
  {
LABEL_19:
    if ( (a4 & 1) != 0 )
      goto LABEL_3;
    if ( *((_DWORD *)this + 2) )
      MoFreeMediaType((DMO_MEDIA_TYPE *)((char *)this + 16));
    v16 = MoCopyMediaType((DMO_MEDIA_TYPE *)((char *)this + 16), (const DMO_MEDIA_TYPE *)a3);
    if ( v16 < 0 )
    {
      v10 = v16;
      goto LABEL_3;
    }
    *((_DWORD *)this + 2) = 1;
    if ( *((_DWORD *)this + 3) )
    {
      MoFreeMediaType((DMO_MEDIA_TYPE *)((char *)this + 104));
      *((_DWORD *)this + 3) = 0;
    }
    v18 = (NResampler *)*((_QWORD *)this + 33);
    if ( v18 )
    {
      NResampler::`scalar deleting destructor'(v18, v17);
      *((_QWORD *)this + 33) = 0;
    }
    memset(v21, 0, 34);
    *((_OWORD *)this + 17) = v21[0];
    *((_OWORD *)this + 18) = v21[1];
    *((_QWORD *)this + 38) = 0;
    v19 = *(_WORD *)v13 == 0xFFFE;
    *((_OWORD *)this + 17) = *(_OWORD *)v13;
    if ( v19 )
    {
      *((_OWORD *)this + 18) = *(_OWORD *)(v13 + 16);
      *((_QWORD *)this + 38) = *(_QWORD *)(v13 + 32);
    }
    else
    {
      *((_WORD *)this + 144) = *(_WORD *)(v13 + 16);
    }
    WaveFormatEx2PCMFormat((char *)this + 272, (char *)this + 352);
    LeaveCriticalSection(v4);
    return 0;
  }
}

```

## disassembly

```asm
0x180006f00  push    rbx
0x180006f02  push    rbp
0x180006f03  push    rsi
0x180006f04  push    rdi
0x180006f05  push    r12
0x180006f07  push    r14
0x180006f09  push    r15
0x180006f0b  sub     rsp, 50h
0x180006f0f  lea     r15, [rcx+0C8h]
0x180006f16  mov     rdi, rcx
0x180006f19  mov     rcx, r15; lpCriticalSection
0x180006f1c  mov     r12d, r9d
0x180006f1f  mov     rsi, r8
0x180006f22  mov     ebx, edx
0x180006f24  call    cs:__imp_EnterCriticalSection
0x180006f2a  cmp     ebx, 1
0x180006f2d  jb      short loc_180006F4E
0x180006f2f  mov     ebx, 80040201h
0x180006f34  mov     rcx, r15; lpCriticalSection
0x180006f37  call    cs:__imp_LeaveCriticalSection
0x180006f3d  mov     eax, ebx
0x180006f3f  add     rsp, 50h
0x180006f43  pop     r15
0x180006f45  pop     r14
0x180006f47  pop     r12
0x180006f49  pop     rdi
0x180006f4a  pop     rsi
0x180006f4b  pop     rbp
0x180006f4c  pop     rbx
0x180006f4d  retn
0x180006f4e  xor     ebx, ebx
0x180006f50  test    r12b, 2
0x180006f54  jnz     loc_1800070E8
0x180006f5a  test    rsi, rsi
0x180006f5d  jz      loc_180007122
0x180006f63  mov     rdx, rsi; struct _DMOMediaType *
0x180006f66  call    ?ValidateAudioType@@YAHPEAXPEBU_DMOMediaType@@@Z; ValidateAudioType(void *,_DMOMediaType const *)
0x180006f6b  test    eax, eax
0x180006f6d  jz      loc_1800070D5
0x180006f73  mov     rax, [rsi+10h]
0x180006f77  sub     rax, qword ptr cs:MEDIASUBTYPE_PCM.Data1
0x180006f7e  jnz     short loc_180006F8B
0x180006f80  mov     rax, [rsi+18h]
0x180006f84  sub     rax, qword ptr cs:MEDIASUBTYPE_PCM.Data4
0x180006f8b  test    rax, rax
0x180006f8e  jnz     loc_1800070B4
0x180006f94  mov     rbp, [rsi+50h]
0x180006f98  mov     rcx, rbp; struct WAVEFORMATEXTENSIBLE *
0x180006f9b  call    ?ResampIsValidWaveFormat@@YAHPEAUWAVEFORMATEXTENSIBLE@@@Z; ResampIsValidWaveFormat(WAVEFORMATEXTENSIBLE *)
0x180006fa0  test    eax, eax
0x180006fa2  jz      loc_1800070D5
0x180006fa8  cmp     [rdi+8], ebx
0x180006fab  jz      short loc_180006FF2
0x180006fad  mov     rax, [rsi+10h]
0x180006fb1  sub     rax, [rdi+20h]
0x180006fb5  jnz     short loc_180006FBF
0x180006fb7  mov     rax, [rsi+18h]
0x180006fbb  sub     rax, [rdi+28h]
0x180006fbf  test    rax, rax
0x180006fc2  jnz     short loc_180006FE5
0x180006fc4  mov     eax, [rdi+58h]
0x180006fc7  mov     rcx, rbp; Buf1
0x180006fca  cmp     eax, [rsi+48h]
0x180006fcd  mov     rdx, [rdi+60h]; Buf2
0x180006fd1  cmovnb  eax, [rsi+48h]
0x180006fd5  mov     r8d, eax; Size
0x180006fd8  call    memcmp_0
0x180006fdd  test    eax, eax
0x180006fdf  jz      loc_180006F34
0x180006fe5  cmp     [rdi+1F8h], rbx
0x180006fec  jnz     loc_1800070D5
0x180006ff2  test    r12b, 1
0x180006ff6  jnz     loc_180006F34
0x180006ffc  cmp     [rdi+8], ebx
0x180006fff  jnz     loc_180007109
0x180007005  mov     rdx, rsi; pmtSrc
0x180007008  lea     rcx, [rdi+10h]; pmtDest
0x18000700c  call    cs:__imp_MoCopyMediaType
0x180007012  test    eax, eax
0x180007014  js      loc_18000712C
0x18000701a  mov     dword ptr [rdi+8], 1
0x180007021  cmp     [rdi+0Ch], ebx
0x180007024  jnz     loc_180007133
0x18000702a  mov     rcx, [rdi+108h]; this
0x180007031  test    rcx, rcx
0x180007034  jnz     loc_180007145
0x18000703a  xorps   xmm0, xmm0
0x18000703d  mov     word ptr [rsp+88h+var_68], bx
0x180007042  lea     rcx, [rdi+110h]
0x180007049  xor     eax, eax
0x18000704b  movups  [rsp+88h+var_68+2], xmm0
0x180007050  movups  [rsp+88h+var_56], xmm0
0x180007055  movups  xmm0, [rsp+88h+var_68]
0x18000705a  movups  xmm1, xmmword ptr [rsp+30h]
0x18000705f  movups  xmmword ptr [rcx], xmm0
0x180007062  movups  xmmword ptr [rcx+10h], xmm1
0x180007066  mov     [rcx+20h], rax
0x18000706a  mov     eax, 0FFFEh
0x18000706f  movups  xmm0, xmmword ptr [rbp+0]
0x180007073  cmp     [rbp+0], ax
0x180007077  movups  xmmword ptr [rcx], xmm0
0x18000707a  jnz     short loc_1800070AA
0x18000707c  movups  xmm1, xmmword ptr [rbp+10h]
0x180007080  movups  xmmword ptr [rcx+10h], xmm1
0x180007084  movsd   xmm0, qword ptr [rbp+20h]
0x180007089  movsd   qword ptr [rcx+20h], xmm0
0x18000708e  lea     rdx, [rdi+160h]
0x180007095  call    WaveFormatEx2PCMFormat
0x18000709a  mov     rcx, r15; lpCriticalSection
0x18000709d  call    cs:__imp_LeaveCriticalSection
0x1800070a3  xor     eax, eax
0x1800070a5  jmp     loc_180006F3F
0x1800070aa  movzx   eax, word ptr [rbp+10h]
0x1800070ae  mov     [rcx+10h], ax
0x1800070b2  jmp     short loc_18000708E
0x1800070b4  mov     rax, [rsi+10h]
0x1800070b8  sub     rax, qword ptr cs:MEDIASUBTYPE_IEEE_FLOAT.Data1
0x1800070bf  jnz     short loc_1800070CC
0x1800070c1  mov     rax, [rsi+18h]
0x1800070c5  sub     rax, qword ptr cs:MEDIASUBTYPE_IEEE_FLOAT.Data4
0x1800070cc  test    rax, rax
0x1800070cf  jz      loc_180006F94
0x1800070d5  mov     rcx, r15; lpCriticalSection
0x1800070d8  call    cs:__imp_LeaveCriticalSection
0x1800070de  mov     eax, 80040205h
0x1800070e3  jmp     loc_180006F3F
0x1800070e8  cmp     [rdi+8], ebx
0x1800070eb  jz      short loc_180007118
0x1800070ed  test    r12b, 1
0x1800070f1  jnz     loc_180006F34
0x1800070f7  lea     rcx, [rdi+10h]; pmt
0x1800070fb  mov     [rdi+8], ebx
0x1800070fe  call    cs:__imp_MoFreeMediaType
0x180007104  jmp     loc_180006F34
0x180007109  lea     rcx, [rdi+10h]; pmt
0x18000710d  call    cs:__imp_MoFreeMediaType
0x180007113  jmp     loc_180007005
0x180007118  mov     ebx, 1
0x18000711d  jmp     loc_180006F34
0x180007122  mov     ebx, 80004003h
0x180007127  jmp     loc_180006F34
0x18000712c  mov     ebx, eax
0x18000712e  jmp     loc_180006F34
0x180007133  lea     rcx, [rdi+68h]; pmt
0x180007137  call    cs:__imp_MoFreeMediaType
0x18000713d  mov     [rdi+0Ch], ebx
0x180007140  jmp     loc_18000702A
0x180007145  call    ??_GNResampler@@QEAAPEAXI@Z; NResampler::`scalar deleting destructor'(uint)
0x18000714a  mov     [rdi+108h], rbx
0x180007151  jmp     loc_18000703A
```
