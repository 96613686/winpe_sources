# CWMResampleMediaObject::GetOutputType(ulong,_DMOMediaType *)

- ea: `0x18006b290`
- end: `0x18006b47e`
- name: `?GetOutputType@CWMResampleMediaObject@@UEAAJKPEAU_DMOMediaType@@@Z`
- size: `494`
- prototype: `int(CWMResampleMediaObject *__hidden this, unsigned int, struct _DMOMediaType *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18006b290`

## import_xrefs

- `msdmo!MoCopyMediaType` at `0x18006b33f`
- `msdmo!MoCopyMediaType` at `0x18006b427`
- `msdmo!MoCopyMediaType` at `0x18006b33f`
- `msdmo!MoCopyMediaType` at `0x18006b427`
- `msdmo!MoInitMediaType` at `0x18006b2d2`
- `msdmo!MoInitMediaType` at `0x18006b2d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b2e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b469`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b2e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b469`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b2af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b2af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006b373`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006b3d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006b373`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006b3d1`

## pseudocode

```c
__int64 __fastcall CWMResampleMediaObject::GetOutputType(
        CWMResampleMediaObject *this,
        unsigned int a2,
        DMO_MEDIA_TYPE *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // r14
  HRESULT inited; // ebp
  unsigned int v9; // ebx
  unsigned int v10; // ebx
  unsigned int v11; // ebx
  HRESULT v12; // ebx
  BYTE *v13; // rax
  BYTE *v14; // rcx
  BYTE *v15; // rax
  unsigned int v16; // ebx
  unsigned int v17; // ebx
  HRESULT v18; // eax
  GUID v19; // xmm0

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 248);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 248));
  if ( a2 > 3 )
    goto LABEL_31;
  if ( !a3 )
    goto LABEL_30;
  inited = MoInitMediaType(a3, 0);
  if ( inited < 0 )
  {
    LeaveCriticalSection(v3);
    return (unsigned int)inited;
  }
  a3->majortype = MEDIATYPE_Audio;
  if ( *((_DWORD *)this + 148) )
  {
    if ( a2 )
    {
      v9 = a2 - 1;
      if ( v9 )
      {
        v10 = v9 - 1;
        if ( !v10 )
        {
          a3->subtype = MEDIASUBTYPE_IEEE_FLOAT;
          a3->formattype = FORMAT_WaveFormatEx;
          v15 = (BYTE *)CoTaskMemAlloc(0x12u);
          a3->pbFormat = v15;
          v14 = v15;
          if ( v15 )
          {
            a3->cbFormat = 18;
            *(_DWORD *)v15 = 131075;
            *((_DWORD *)v15 + 1) = 48000;
            *((_DWORD *)v15 + 2) = 384000;
            *((_DWORD *)v15 + 3) = 2097160;
            goto LABEL_16;
          }
          goto LABEL_26;
        }
        v11 = v10 - 1;
        if ( v11 )
        {
          if ( v11 == 1 && *((_DWORD *)this + 14) )
          {
            v12 = MoCopyMediaType(a3, (const DMO_MEDIA_TYPE *)((char *)this + 64));
            if ( v12 < 0 )
              goto LABEL_32;
            goto LABEL_30;
          }
LABEL_31:
          v12 = -2147220986;
          goto LABEL_32;
        }
LABEL_14:
        a3->subtype = MEDIASUBTYPE_PCM;
        a3->formattype = FORMAT_WaveFormatEx;
        v13 = (BYTE *)CoTaskMemAlloc(0x12u);
        a3->pbFormat = v13;
        v14 = v13;
        if ( v13 )
        {
          a3->cbFormat = 18;
          *(_DWORD *)v13 = 131073;
          *((_DWORD *)v13 + 1) = 48000;
          *((_DWORD *)v13 + 2) = 192000;
          *((_DWORD *)v13 + 3) = 1048580;
LABEL_16:
          *((_WORD *)v14 + 8) = 0;
          goto LABEL_30;
        }
LABEL_26:
        v12 = -2147024882;
        goto LABEL_32;
      }
      goto LABEL_28;
    }
    goto LABEL_27;
  }
  if ( !a2 )
  {
LABEL_28:
    v19 = MEDIASUBTYPE_PCM;
    goto LABEL_29;
  }
  v16 = a2 - 1;
  if ( !v16 )
  {
LABEL_27:
    v19 = MEDIASUBTYPE_IEEE_FLOAT;
LABEL_29:
    a3->subtype = v19;
    a3->formattype = GUID_00000000_0000_0000_0000_000000000000;
    goto LABEL_30;
  }
  v17 = v16 - 1;
  if ( !v17 )
    goto LABEL_14;
  if ( v17 != 1 || !*((_DWORD *)this + 14) )
    goto LABEL_31;
  v18 = MoCopyMediaType(a3, (const DMO_MEDIA_TYPE *)((char *)this + 64));
  if ( v18 >= 0 )
  {
LABEL_30:
    v12 = 0;
    goto LABEL_32;
  }
  v12 = v18;
LABEL_32:
  LeaveCriticalSection(v3);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18006b290  push    rbx
0x18006b292  push    rbp
0x18006b293  push    rsi
0x18006b294  push    rdi
0x18006b295  push    r12
0x18006b297  push    r14
0x18006b299  sub     rsp, 28h
0x18006b29d  lea     r14, [rcx+0F8h]
0x18006b2a4  mov     rsi, rcx
0x18006b2a7  mov     rcx, r14; lpCriticalSection
0x18006b2aa  mov     rdi, r8
0x18006b2ad  mov     ebx, edx
0x18006b2af  call    cs:__imp_EnterCriticalSection
0x18006b2b5  mov     r12d, 3
0x18006b2bb  cmp     ebx, r12d
0x18006b2be  ja      loc_18006B461
0x18006b2c4  test    rdi, rdi
0x18006b2c7  jz      loc_18006B45D
0x18006b2cd  xor     edx, edx; cbFormat
0x18006b2cf  mov     rcx, rdi; pmt
0x18006b2d2  call    cs:__imp_MoInitMediaType
0x18006b2d8  mov     ebp, eax
0x18006b2da  test    eax, eax
0x18006b2dc  jns     short loc_18006B2EE
0x18006b2de  mov     rcx, r14; lpCriticalSection
0x18006b2e1  call    cs:__imp_LeaveCriticalSection
0x18006b2e7  mov     eax, ebp
0x18006b2e9  jmp     loc_18006B471
0x18006b2ee  movups  xmm0, xmmword ptr cs:MEDIATYPE_Audio.Data1
0x18006b2f5  movdqu  xmmword ptr [rdi], xmm0
0x18006b2f9  cmp     dword ptr [rsi+250h], 0
0x18006b300  jz      loc_18006B403
0x18006b306  test    ebx, ebx
0x18006b308  jz      loc_18006B43C
0x18006b30e  sub     ebx, 1
0x18006b311  jz      loc_18006B445
0x18006b317  sub     ebx, 1
0x18006b31a  jz      loc_18006B3B2
0x18006b320  sub     ebx, 1
0x18006b323  jz      short loc_18006B354
0x18006b325  cmp     ebx, 1
0x18006b328  jnz     loc_18006B461
0x18006b32e  cmp     dword ptr [rsi+38h], 0
0x18006b332  jz      loc_18006B461
0x18006b338  lea     rdx, [rsi+40h]; pmtSrc
0x18006b33c  mov     rcx, rdi; pmtDest
0x18006b33f  call    cs:__imp_MoCopyMediaType
0x18006b345  mov     ebx, eax
0x18006b347  test    eax, eax
0x18006b349  jns     loc_18006B45D
0x18006b34f  jmp     loc_18006B466
0x18006b354  movups  xmm0, xmmword ptr cs:MEDIASUBTYPE_PCM.Data1
0x18006b35b  mov     ebx, 12h
0x18006b360  mov     ecx, ebx; cb
0x18006b362  movdqu  xmmword ptr [rdi+10h], xmm0
0x18006b367  movups  xmm1, xmmword ptr cs:FORMAT_WaveFormatEx.Data1
0x18006b36e  movdqu  xmmword ptr [rdi+2Ch], xmm1
0x18006b373  call    cs:__imp_CoTaskMemAlloc
0x18006b379  mov     [rdi+50h], rax
0x18006b37d  mov     rcx, rax
0x18006b380  test    rax, rax
0x18006b383  jz      loc_18006B435
0x18006b389  mov     [rdi+48h], ebx
0x18006b38c  mov     dword ptr [rax], 20001h
0x18006b392  mov     dword ptr [rax+4], 0BB80h
0x18006b399  mov     dword ptr [rax+8], 2EE00h
0x18006b3a0  mov     dword ptr [rax+0Ch], 100004h
0x18006b3a7  xor     eax, eax
0x18006b3a9  mov     [rcx+10h], ax
0x18006b3ad  jmp     loc_18006B45D
0x18006b3b2  movups  xmm0, xmmword ptr cs:MEDIASUBTYPE_IEEE_FLOAT.Data1
0x18006b3b9  mov     ebx, 12h
0x18006b3be  mov     ecx, ebx; cb
0x18006b3c0  movdqu  xmmword ptr [rdi+10h], xmm0
0x18006b3c5  movups  xmm1, xmmword ptr cs:FORMAT_WaveFormatEx.Data1
0x18006b3cc  movdqu  xmmword ptr [rdi+2Ch], xmm1
0x18006b3d1  call    cs:__imp_CoTaskMemAlloc
0x18006b3d7  mov     [rdi+50h], rax
0x18006b3db  mov     rcx, rax
0x18006b3de  test    rax, rax
0x18006b3e1  jz      short loc_18006B435
0x18006b3e3  mov     [rdi+48h], ebx
0x18006b3e6  mov     dword ptr [rax], 20003h
0x18006b3ec  mov     dword ptr [rax+4], 0BB80h
0x18006b3f3  mov     dword ptr [rax+8], 5DC00h
0x18006b3fa  mov     dword ptr [rax+0Ch], 200008h
0x18006b401  jmp     short loc_18006B3A7
0x18006b403  test    ebx, ebx
0x18006b405  jz      short loc_18006B445
0x18006b407  sub     ebx, 1
0x18006b40a  jz      short loc_18006B43C
0x18006b40c  sub     ebx, 1
0x18006b40f  jz      loc_18006B354
0x18006b415  cmp     ebx, 1
0x18006b418  jnz     short loc_18006B461
0x18006b41a  cmp     dword ptr [rsi+38h], 0
0x18006b41e  jz      short loc_18006B461
0x18006b420  lea     rdx, [rsi+40h]; pmtSrc
0x18006b424  mov     rcx, rdi; pmtDest
0x18006b427  call    cs:__imp_MoCopyMediaType
0x18006b42d  test    eax, eax
0x18006b42f  jns     short loc_18006B45D
0x18006b431  mov     ebx, eax
0x18006b433  jmp     short loc_18006B466
0x18006b435  mov     ebx, 8007000Eh
0x18006b43a  jmp     short loc_18006B466
0x18006b43c  movups  xmm0, xmmword ptr cs:MEDIASUBTYPE_IEEE_FLOAT.Data1
0x18006b443  jmp     short loc_18006B44C
0x18006b445  movups  xmm0, xmmword ptr cs:MEDIASUBTYPE_PCM.Data1
0x18006b44c  movups  xmm1, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18006b453  movdqu  xmmword ptr [rdi+10h], xmm0
0x18006b458  movdqu  xmmword ptr [rdi+2Ch], xmm1
0x18006b45d  xor     ebx, ebx
0x18006b45f  jmp     short loc_18006B466
0x18006b461  mov     ebx, 80040206h
0x18006b466  mov     rcx, r14; lpCriticalSection
0x18006b469  call    cs:__imp_LeaveCriticalSection
0x18006b46f  mov     eax, ebx
0x18006b471  add     rsp, 28h
0x18006b475  pop     r14
0x18006b477  pop     r12
0x18006b479  pop     rdi
0x18006b47a  pop     rsi
0x18006b47b  pop     rbp
0x18006b47c  pop     rbx
0x18006b47d  retn
```
