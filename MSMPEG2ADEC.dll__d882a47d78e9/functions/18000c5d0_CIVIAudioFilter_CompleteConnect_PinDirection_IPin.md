# CIVIAudioFilter::CompleteConnect(_PinDirection,IPin *)

- ea: `0x18000c5d0`
- end: `0x18000cf6b`
- name: `?CompleteConnect@CIVIAudioFilter@@MEAAJW4_PinDirection@@PEAUIPin@@@Z`
- size: `2459`
- prototype: `__int64 __fastcall(CIVIAudioFilter *__hidden this, enum _PinDirection, struct IPin *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800017b0`
- `0x1800021a8`
- `0x18000c5d0`
- `0x18001f440`
- `0x180025230`
- `0x1800886f0`
- `0x180088750`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18000cef9`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18000cef9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cf32`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cf32`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c64c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c64c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CIVIAudioFilter::CompleteConnect(CIVIAudioFilter *this, enum _PinDirection a2, struct IPin *a3)
{
  struct IPin *v3; // r12
  CIVIAudioFilter *v4; // r13
  struct _RTL_CRITICAL_SECTION *v5; // rdi
  int v6; // edx
  signed __int64 v7; // rax
  __int64 v8; // r8
  __int64 v9; // rcx
  unsigned int v10; // r9d
  unsigned int v11; // esi
  unsigned __int64 v12; // r13
  unsigned __int64 v13; // r15
  __int64 v14; // r13
  char *v15; // r9
  unsigned int v16; // ebx
  char *v17; // r9
  volatile unsigned int v18; // r10d
  signed int v19; // edx
  signed int v20; // r8d
  unsigned int v21; // ecx
  char v22; // r14
  __int64 v23; // r12
  char *v24; // rdi
  unsigned int v25; // ecx
  unsigned __int64 v26; // rdx
  unsigned __int64 v27; // r15
  __int64 v28; // r14
  __int64 v29; // rcx
  unsigned int v30; // r15d
  unsigned __int64 v31; // r14
  char *v32; // rsi
  __int64 v33; // rbx
  BOOL v34; // ecx
  __int64 v35; // rax
  int v36; // ebx
  __int64 v37; // rsi
  int v38; // eax
  int v39; // ecx
  void **v40; // rcx
  __int64 v41; // rdx
  int v42; // eax
  __int64 v44; // [rsp+20h] [rbp-E0h] BYREF
  void **v45; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v46; // [rsp+30h] [rbp-D0h] BYREF
  volatile unsigned int v47; // [rsp+38h] [rbp-C8h]
  unsigned int v48; // [rsp+3Ch] [rbp-C4h]
  enum _PinDirection v49; // [rsp+40h] [rbp-C0h]
  unsigned int v50; // [rsp+44h] [rbp-BCh]
  char *v51; // [rsp+48h] [rbp-B8h]
  char *v52; // [rsp+50h] [rbp-B0h]
  signed __int64 v53; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v54; // [rsp+60h] [rbp-A0h]
  struct _RTL_CRITICAL_SECTION *v55; // [rsp+68h] [rbp-98h]
  CIVIAudioFilter *v56; // [rsp+70h] [rbp-90h]
  struct IPin *v57; // [rsp+78h] [rbp-88h]
  char *v58; // [rsp+80h] [rbp-80h]
  _QWORD v59[34]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t Str[128]; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v61; // [rsp+2A0h] [rbp+1A0h]
  __int128 Buf1; // [rsp+2B0h] [rbp+1B0h] BYREF

  v3 = a3;
  v57 = a3;
  v49 = a2;
  v4 = this;
  v56 = this;
  memset_0(v59, 0, sizeof(v59));
  memset_0(Str, 0, 0x108u);
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)v4 + 136);
  v55 = (struct _RTL_CRITICAL_SECTION *)((char *)v4 + 136);
  v58 = (char *)v4 + 136;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v4 + 136));
  v6 = WarbirdRuntime::g_VerifiedSegmentData_1;
  if ( WarbirdRuntime::g_VerifiedSegmentData_1 < 0 )
  {
    v7 = WarbirdRuntime::g_VerifiedSegmentDataReadWrite_1;
    v53 = WarbirdRuntime::g_VerifiedSegmentDataReadWrite_1;
    v8 = WarbirdRuntime::g_VerifiedSegmentDataReadWrite_1 >> 63;
    v46 = WarbirdRuntime::g_VerifiedSegmentDataReadWrite_1 >> 63;
    v45 = &WarbirdCrypto::CHashFunctionSCP<0,2,2,8641855362498640525>::`vftable';
    v9 = 0;
    v44 = 0;
    v10 = 0;
    v48 = 0;
    if ( (WarbirdRuntime::g_VerifiedSegmentData_1 & 0x3FFFFFFF) != 0 )
    {
      v11 = v49;
      do
      {
        v12 = qword_1800A4A30[v10];
        v13 = v12 >> 36;
        v54 = v12 >> 36;
        v14 = (v12 >> 5) & 0xFFFFFFF;
        v15 = (char *)&_ImageBase + (unsigned int)v14;
        v52 = v15;
        v16 = 0;
        if ( (_DWORD)v8 )
        {
          v17 = (char *)&_ImageBase + WarbirdRuntime::g_PrivateRelocationsTable;
          v51 = v17;
          v18 = WarbirdRuntime::g_PrivateRelocationsTableCount;
          v47 = WarbirdRuntime::g_PrivateRelocationsTableCount;
          v19 = 0;
          v20 = WarbirdRuntime::g_PrivateRelocationsTableCount - 1;
          while ( v20 >= v19 )
          {
            v11 = (v20 + v19) / 2;
            v21 = *(_DWORD *)&v17[4 * v11] & 0xFFFFFFF;
            if ( (unsigned int)v14 >= v21 )
            {
              if ( (unsigned int)v14 <= v21 )
                goto LABEL_12;
              v19 = v11 + 1;
            }
            else
            {
              v20 = v11 - 1;
            }
          }
          v11 = v19;
LABEL_12:
          v50 = v13 + v14;
          if ( v11 >= WarbirdRuntime::g_PrivateRelocationsTableCount
            || (*(_DWORD *)&v17[4 * v11] & 0xFFFFFFFu) >= (int)v13 + (int)v14 )
          {
            v22 = 0;
            v6 = WarbirdRuntime::g_VerifiedSegmentData_1;
            v15 = v52;
            LODWORD(v8) = v46;
          }
          else
          {
            v16 = *(_DWORD *)&v17[4 * v11++];
            v22 = 1;
            v6 = WarbirdRuntime::g_VerifiedSegmentData_1;
            v15 = v52;
            LODWORD(v8) = v46;
          }
        }
        else
        {
          v51 = 0;
          v18 = 0;
          v47 = 0;
          v22 = 0;
        }
        v23 = 0;
        if ( (_DWORD)v13 )
        {
          v24 = v51;
          do
          {
            if ( (_DWORD)v8 && v22 && (_DWORD)v23 + (_DWORD)v14 == (v16 & 0xFFFFFFF) )
            {
              v25 = v16 >> 28;
              if ( v16 >> 28 )
              {
                v26 = WarbirdRuntime::g_preferedImageBase - (_QWORD)&_ImageBase;
                if ( v25 == 3 )
                {
                  LODWORD(Buf1) = v26 + *(_DWORD *)&v15[v23];
                  v27 = 4;
                }
                else if ( v25 == 10 )
                {
                  *(_QWORD *)&Buf1 = v26 + *(_QWORD *)&v15[v23];
                  v27 = 8;
                }
                else
                {
                  v27 = -1;
                }
                v28 = 0;
                do
                {
                  ((void (__fastcall *)(void ***, __int64 *, _QWORD, char *))v45[1])(
                    &v45,
                    &v44,
                    *((unsigned __int8 *)&Buf1 + v28),
                    v15);
                  v28 = (unsigned int)(v28 + 1);
                }
                while ( (unsigned int)v28 < v27 );
                v18 = v47;
                LODWORD(v13) = v54;
              }
              else
              {
                LODWORD(v28) = 0;
              }
              v23 = (unsigned int)(v28 + v23);
              if ( v11 >= v18 || (*(_DWORD *)&v24[4 * v11] & 0xFFFFFFFu) >= v50 )
              {
                v22 = 0;
              }
              else
              {
                v16 = *(_DWORD *)&v24[4 * v11++];
                v22 = 1;
              }
            }
            else
            {
              ((void (__fastcall *)(void ***, __int64 *, _QWORD))v45[1])(&v45, &v44, (unsigned __int8)v15[v23]);
              v23 = (unsigned int)(v23 + 1);
              v18 = v47;
            }
            v15 = v52;
            LODWORD(v8) = v46;
          }
          while ( (unsigned int)v23 < (unsigned int)v13 );
          v6 = WarbirdRuntime::g_VerifiedSegmentData_1;
        }
        v10 = v48 + 1;
        v48 = v10;
        LODWORD(v8) = v46;
      }
      while ( v10 < (v6 & 0x3FFFFFFFu) );
      v9 = v44;
      v5 = v55;
      v4 = v56;
      v3 = v57;
      v7 = v53;
    }
    if ( (v9 | 0x8000000000000000uLL) == (v7 | 0x8000000000000000uLL) )
    {
      if ( (_DWORD)v8 )
      {
        v29 = 0;
        v44 = 0;
        v30 = 0;
        if ( (v6 & 0x3FFFFFFF) != 0 )
        {
          do
          {
            v31 = (unsigned __int64)qword_1800A4A30[v30] >> 36;
            v32 = (char *)&_ImageBase + (((unsigned __int64)qword_1800A4A30[v30] >> 5) & 0xFFFFFFF);
            v33 = 0;
            if ( (_DWORD)v31 )
            {
              do
              {
                ((void (__fastcall *)(void ***, __int64 *, _QWORD))v45[1])(&v45, &v44, (unsigned __int8)v32[v33]);
                v33 = (unsigned int)(v33 + 1);
              }
              while ( (unsigned int)v33 < (unsigned int)v31 );
              v6 = WarbirdRuntime::g_VerifiedSegmentData_1;
            }
            ++v30;
          }
          while ( v30 < (v6 & 0x3FFFFFFFu) );
          v29 = v44;
        }
        v44 = v29 & 0x7FFFFFFFFFFFFFFFLL;
        _InterlockedCompareExchange64(
          (volatile signed __int64 *)&WarbirdRuntime::g_VerifiedSegmentDataReadWrite_1,
          v29 & 0x7FFFFFFFFFFFFFFFLL,
          v53);
      }
    }
    else
    {
      WarbirdRuntime::CTermination::TrashStack();
    }
  }
  if ( v49 != PINDIR_OUTPUT )
  {
    if ( v49 )
      goto LABEL_115;
    *((_DWORD *)v4 + 4293) = 0;
    if ( !v3 || ((int (__fastcall *)(struct IPin *, _QWORD *))v3->lpVtbl->QueryPinInfo)(v3, v59) < 0 || !v59[0] )
      goto LABEL_115;
    v45 = 0;
    v44 = 0;
    if ( (**(unsigned int (__fastcall ***)(_QWORD, GUID *, void ***))v59[0])(v59[0], &IID_IDTFilter, &v45)
      || (v40 = v45) == 0 )
    {
      v42 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))v59[0])(v59[0], &IID_IStreamBufferSource, &v44);
      v41 = v44;
      v40 = v45;
      if ( v42 || !v44 )
        goto LABEL_105;
    }
    else
    {
      v41 = v44;
    }
    *((_DWORD *)v4 + 4293) = 1;
LABEL_105:
    if ( v40 )
    {
      (*((void (__fastcall **)(void **, __int64))*v40 + 2))(v40, v41);
      v45 = 0;
      v41 = v44;
    }
    if ( v41 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
      v44 = 0;
    }
    if ( (*(int (__fastcall **)(_QWORD, wchar_t *))(*(_QWORD *)v59[0] + 96LL))(v59[0], Str) >= 0 )
    {
      if ( v61 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
        v61 = 0;
      }
      *((_BYTE *)v4 + 5952) = wcsstr(Str, L"Navigator") != 0;
    }
    goto LABEL_113;
  }
  *((_DWORD *)v4 + 4292) = 0;
  if ( *((_DWORD *)v4 + 1628) == 2 )
  {
    v34 = memcmp_0(&GUID_00000092_0000_0010_8000_00aa00389b71, (char *)v4 + 456, 0x10u) != 0;
    *((_DWORD *)v4 + 1628) = v34;
    v35 = *((_QWORD *)v4 + 2227);
    if ( !*(_DWORD *)(v35 + 8) && v34 )
      *(_DWORD *)(v35 + 16) = 1;
    *(_DWORD *)(v35 + 8) = v34;
  }
  if ( memcmp_0(&MEDIASUBTYPE_PCM, (char *)v4 + 456, 0x10u)
    && memcmp_0(&MEDIASUBTYPE_IEEE_FLOAT, (char *)v4 + 456, 0x10u) )
  {
    if ( memcmp_0(&GUID_00000008_0000_0010_8000_00aa00389b71, (char *)v4 + 456, 0x10u)
      && memcmp_0(&GUID_00000092_0000_0010_8000_00aa00389b71, (char *)v4 + 456, 0x10u) )
    {
      v36 = -2147467259;
      goto LABEL_116;
    }
    *((_BYTE *)v4 + 584) = 1;
    *((_DWORD *)v4 + 1612) = 1;
    *((_DWORD *)v4 + 1538) = 32;
    *((_DWORD *)v4 + 1622) = 3;
    *((_DWORD *)v4 + 63) = 7;
    *((_DWORD *)v4 + 150) = 6;
    *((_DWORD *)v4 + 1611) = 2;
LABEL_86:
    *((_QWORD *)v4 + 748) = v3;
    if ( v3 && ((int (__fastcall *)(struct IPin *, _QWORD *))v3->lpVtbl->QueryPinInfo)(v3, v59) >= 0 && v59[0] )
    {
      v46 = 0;
      if ( (**(int (__fastcall ***)(_QWORD, GUID *, __int64 *))v59[0])(v59[0], &IID_IPersistStream, &v46) >= 0 )
      {
        Buf1 = 0;
        if ( !(*(unsigned int (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v46 + 24LL))(v46, &Buf1)
          && !memcmp_0(&Buf1, &CLSID_DSoundRender, 0x10u) )
        {
          *((_DWORD *)v4 + 4292) = 1;
        }
        if ( v46 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
          v46 = 0;
        }
      }
LABEL_113:
      if ( v59[0] )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v59[0] + 16LL))(v59[0]);
        v59[0] = 0;
      }
    }
LABEL_115:
    v36 = 0;
    goto LABEL_116;
  }
  v37 = *((_QWORD *)v4 + 65);
  *((_BYTE *)v4 + 584) = 0;
  *((_DWORD *)v4 + 1612) = 0;
  if ( v4 != (CIVIAudioFilter *)-440LL
    && !memcmp_0((char *)v4 + 484, &FORMAT_WaveFormatEx, 0x10u)
    && *((_DWORD *)v4 + 128) >= 0x12u
    && v37
    && *(_WORD *)(v37 + 2) == 6
    || *((_DWORD *)v4 + 4291) && *((_DWORD *)v4 + 1611) == 6 && ((*((_DWORD *)v4 + 1622) - 1) & 0xFFFFFFFD) == 0 )
  {
    *((_DWORD *)v4 + 1493) = 2;
    if ( v4 != (CIVIAudioFilter *)-440LL
      && !memcmp_0((char *)v4 + 440, &MEDIATYPE_Audio, 0x10u)
      && (!memcmp_0((char *)v4 + 456, &MEDIASUBTYPE_PCM, 0x10u)
       || !memcmp_0((char *)v4 + 456, &MEDIASUBTYPE_IEEE_FLOAT, 0x10u))
      && !memcmp_0((char *)v4 + 484, &FORMAT_WaveFormatEx, 0x10u)
      && v37
      && *(_WORD *)v37 == 0xFFFE
      && *(_WORD *)(v37 + 2) == 6
      && *(_DWORD *)(v37 + 20) == 1551 )
    {
      *((_DWORD *)v4 + 1493) = 1;
    }
    *((_DWORD *)v4 + 1622) = 1;
    v38 = 5;
    v39 = 4;
  }
  else
  {
    *((_DWORD *)v4 + 1611) = 2;
    if ( ((*((_DWORD *)v4 + 1622) - 1) & 0xFFFFFFFD) == 0 )
      *((_DWORD *)v4 + 1622) = 0;
    v38 = 1;
    v39 = 1;
  }
  *((_DWORD *)v4 + 63) = v39;
  *((_DWORD *)v4 + 150) = v38;
  *((_DWORD *)v4 + 1538) = *(unsigned __int16 *)(v37 + 14);
  v36 = CLEQClient::SetPCMFormat(*((CLEQClient **)v4 + 2227), (CIVIAudioFilter *)((char *)v4 + 440));
  if ( v36 >= 0 )
    goto LABEL_86;
LABEL_116:
  LeaveCriticalSection(v5);
  return (unsigned int)v36;
}

```

## disassembly

```asm
0x18000c5d0  mov     [rsp-8+arg_8], rbx
0x18000c5d5  push    rbp
0x18000c5d6  push    rsi
0x18000c5d7  push    rdi
0x18000c5d8  push    r12
0x18000c5da  push    r13
0x18000c5dc  push    r14
0x18000c5de  push    r15
0x18000c5e0  lea     rbp, [rsp-1D0h]
0x18000c5e8  sub     rsp, 2D0h
0x18000c5ef  mov     rax, cs:__security_cookie
0x18000c5f6  xor     rax, rsp
0x18000c5f9  mov     [rbp+200h+var_40], rax
0x18000c600  mov     r12, r8
0x18000c603  mov     [rsp+300h+var_288], r8
0x18000c608  mov     [rsp+300h+var_2C0], edx
0x18000c60c  mov     r13, rcx
0x18000c60f  mov     [rsp+300h+var_290], rcx
0x18000c614  xor     edx, edx; Val
0x18000c616  mov     r8d, 110h; Size
0x18000c61c  lea     rcx, [rbp+200h+var_270]; void *
0x18000c620  call    memset_0
0x18000c625  xor     edx, edx; Val
0x18000c627  mov     r8d, 108h; Size
0x18000c62d  lea     rcx, [rbp+200h+Str]; void *
0x18000c634  call    memset_0
0x18000c639  lea     rdi, [r13+88h]
0x18000c640  mov     [rsp+300h+var_298], rdi
0x18000c645  mov     [rbp+200h+var_280], rdi
0x18000c649  mov     rcx, rdi; lpCriticalSection
0x18000c64c  call    cs:__imp_EnterCriticalSection
0x18000c653  nop     dword ptr [rax+rax+00h]
0x18000c658  nop
0x18000c659  mov     rdx, cs:?g_VerifiedSegmentData_1@WarbirdRuntime@@3UVERIFIED_SEGMENT_DATA_CONST_2@1@A; WarbirdRuntime::VERIFIED_SEGMENT_DATA_CONST_2 WarbirdRuntime::g_VerifiedSegmentData_1
0x18000c660  xor     r14d, r14d
0x18000c663  mov     r11d, 4
0x18000c669  test    edx, edx
0x18000c66b  jns     loc_18000CA1B
0x18000c671  mov     rax, cs:?g_VerifiedSegmentDataReadWrite_1@WarbirdRuntime@@3UVERIFIED_SEGMENT_DATA_READ_WRITE_2@1@A; WarbirdRuntime::VERIFIED_SEGMENT_DATA_READ_WRITE_2 WarbirdRuntime::g_VerifiedSegmentDataReadWrite_1
0x18000c678  mov     [rsp+300h+var_2A8], rax
0x18000c67d  mov     r8, rax
0x18000c680  shr     r8, 3Fh
0x18000c684  mov     [rsp+300h+var_2D0], r8
0x18000c689  lea     rcx, ??_7?$CHashFunctionSCP@$0A@$01$01$0HHOOAJKKGKAJDKIN@@WarbirdCrypto@@6B@; const WarbirdCrypto::CHashFunctionSCP<0,2,2,8641855362498640525>::`vftable'
0x18000c690  mov     [rsp+300h+var_2D8], rcx
0x18000c695  mov     ecx, r14d
0x18000c698  mov     [rsp+300h+var_2E0], rcx
0x18000c69d  mov     r9d, r14d
0x18000c6a0  mov     [rsp+300h+var_2C4], r14d
0x18000c6a5  lea     r10, __ImageBase
0x18000c6ac  test    edx, 3FFFFFFFh
0x18000c6b2  jbe     loc_18000C939
0x18000c6b8  mov     esi, [rsp+300h+var_2C0]
0x18000c6bc  nop     dword ptr [rax+00h]
0x18000c6c0  mov     eax, r9d
0x18000c6c3  mov     r13, ds:rva qword_1800A4A30[r10+rax*8]
0x18000c6cb  mov     r15, r13
0x18000c6ce  shr     r15, 24h
0x18000c6d2  mov     [rsp+300h+var_2A0], r15
0x18000c6d7  shr     r13, 5
0x18000c6db  and     r13d, 0FFFFFFFh
0x18000c6e2  mov     r9d, r13d
0x18000c6e5  add     r9, r10
0x18000c6e8  mov     [rsp+300h+var_2B0], r9
0x18000c6ed  mov     ebx, r14d
0x18000c6f0  test    r8d, r8d
0x18000c6f3  jz      loc_18000C79E
0x18000c6f9  mov     r9d, cs:?g_PrivateRelocationsTable@WarbirdRuntime@@3KC; ulong volatile WarbirdRuntime::g_PrivateRelocationsTable
0x18000c700  add     r9, r10
0x18000c703  mov     [rsp+300h+var_2B8], r9
0x18000c708  mov     r10d, cs:?g_PrivateRelocationsTableCount@WarbirdRuntime@@3KC; ulong volatile WarbirdRuntime::g_PrivateRelocationsTableCount
0x18000c70f  mov     [rsp+300h+var_2C8], r10d
0x18000c714  mov     edx, r14d
0x18000c717  lea     r8d, [r10-1]
0x18000c71b  test    r8d, r8d
0x18000c71e  js      short loc_18000C74E
0x18000c720  lea     esi, [r8+rdx]
0x18000c724  test    esi, esi
0x18000c726  jns     short loc_18000C72A
0x18000c728  inc     esi
0x18000c72a  sar     esi, 1
0x18000c72c  movsxd  rax, esi
0x18000c72f  mov     ecx, [r9+rax*4]
0x18000c733  and     ecx, 0FFFFFFFh
0x18000c739  cmp     r13d, ecx
0x18000c73c  jnb     short loc_18000C744
0x18000c73e  lea     r8d, [rsi-1]
0x18000c742  jmp     short loc_18000C749
0x18000c744  jbe     short loc_18000C750
0x18000c746  lea     edx, [rsi+1]
0x18000c749  cmp     r8d, edx
0x18000c74c  jge     short loc_18000C720
0x18000c74e  mov     esi, edx
0x18000c750  lea     edx, [r15+r13]
0x18000c754  mov     [rsp+300h+var_2BC], edx
0x18000c758  cmp     esi, r10d
0x18000c75b  jnb     short loc_18000C788
0x18000c75d  mov     eax, esi
0x18000c75f  mov     ecx, [r9+rax*4]
0x18000c763  mov     eax, ecx
0x18000c765  and     eax, 0FFFFFFFh
0x18000c76a  cmp     eax, edx
0x18000c76c  jnb     short loc_18000C788
0x18000c76e  mov     ebx, ecx
0x18000c770  inc     esi
0x18000c772  mov     r14b, 1
0x18000c775  mov     rdx, cs:?g_VerifiedSegmentData_1@WarbirdRuntime@@3UVERIFIED_SEGMENT_DATA_CONST_2@1@A; WarbirdRuntime::VERIFIED_SEGMENT_DATA_CONST_2 WarbirdRuntime::g_VerifiedSegmentData_1
0x18000c77c  mov     r9, [rsp+300h+var_2B0]
0x18000c781  mov     r8, [rsp+300h+var_2D0]
0x18000c786  jmp     short loc_18000C7AE
0x18000c788  xor     r14b, r14b
0x18000c78b  mov     rdx, cs:?g_VerifiedSegmentData_1@WarbirdRuntime@@3UVERIFIED_SEGMENT_DATA_CONST_2@1@A; WarbirdRuntime::VERIFIED_SEGMENT_DATA_CONST_2 WarbirdRuntime::g_VerifiedSegmentData_1
0x18000c792  mov     r9, [rsp+300h+var_2B0]
0x18000c797  mov     r8, [rsp+300h+var_2D0]
0x18000c79c  jmp     short loc_18000C7AE
0x18000c79e  mov     [rsp+300h+var_2B8], r14
0x18000c7a3  mov     r10d, r14d
0x18000c7a6  mov     [rsp+300h+var_2C8], r14d
0x18000c7ab  xor     r14b, r14b
0x18000c7ae  xor     r12d, r12d
0x18000c7b1  test    r15d, r15d
0x18000c7b4  jz      loc_18000C8EA
0x18000c7ba  mov     rdi, [rsp+300h+var_2B8]
0x18000c7bf  nop
0x18000c7c0  test    r8d, r8d
0x18000c7c3  jz      loc_18000C8A4
0x18000c7c9  test    r14b, r14b
0x18000c7cc  jz      loc_18000C8A4
0x18000c7d2  lea     ecx, [r12+r13]
0x18000c7d6  mov     eax, ebx
0x18000c7d8  and     eax, 0FFFFFFFh
0x18000c7dd  cmp     ecx, eax
0x18000c7df  jnz     loc_18000C8A4
0x18000c7e5  mov     rdx, cs:?g_preferedImageBase@WarbirdRuntime@@3_KC; unsigned __int64 volatile WarbirdRuntime::g_preferedImageBase
0x18000c7ec  mov     ecx, ebx
0x18000c7ee  shr     ecx, 1Ch
0x18000c7f1  test    ecx, ecx
0x18000c7f3  jz      loc_18000C879
0x18000c7f9  lea     rax, __ImageBase
0x18000c800  sub     rdx, rax
0x18000c803  cmp     ecx, 3
0x18000c806  jz      short loc_18000C82C
0x18000c808  cmp     ecx, 0Ah
0x18000c80b  jz      short loc_18000C816
0x18000c80d  mov     r15, 0FFFFFFFFFFFFFFFFh
0x18000c814  jmp     short loc_18000C83B
0x18000c816  mov     rcx, [r12+r9]
0x18000c81a  add     rcx, rdx
0x18000c81d  mov     qword ptr [rbp+200h+Buf1], rcx
0x18000c824  mov     r15d, 8
0x18000c82a  jmp     short loc_18000C83B
0x18000c82c  mov     ecx, [r12+r9]
0x18000c830  add     ecx, edx
0x18000c832  mov     dword ptr [rbp+200h+Buf1], ecx
0x18000c838  mov     r15, r11
0x18000c83b  xor     r14d, r14d
0x18000c83e  xchg    ax, ax
0x18000c840  mov     rax, [rsp+300h+var_2D8]
0x18000c845  movzx   r8d, byte ptr [rbp+r14+200h+Buf1]
0x18000c84e  lea     rdx, [rsp+300h+var_2E0]
0x18000c853  lea     rcx, [rsp+300h+var_2D8]
0x18000c858  mov     rax, [rax+8]
0x18000c85c  call    cs:__guard_dispatch_icall_fptr
0x18000c862  inc     r14d
0x18000c865  mov     eax, r14d
0x18000c868  cmp     rax, r15
0x18000c86b  jb      short loc_18000C840
0x18000c86d  mov     r10d, [rsp+300h+var_2C8]
0x18000c872  mov     r15, [rsp+300h+var_2A0]
0x18000c877  jmp     short loc_18000C87C
0x18000c879  xor     r14d, r14d
0x18000c87c  add     r12d, r14d
0x18000c87f  cmp     esi, r10d
0x18000c882  jnb     short loc_18000C89F
0x18000c884  mov     eax, esi
0x18000c886  mov     ecx, [rdi+rax*4]
0x18000c889  mov     eax, ecx
0x18000c88b  and     eax, 0FFFFFFFh
0x18000c890  cmp     eax, [rsp+300h+var_2BC]
0x18000c894  jnb     short loc_18000C89F
0x18000c896  mov     ebx, ecx
0x18000c898  inc     esi
0x18000c89a  mov     r14b, 1
0x18000c89d  jmp     short loc_18000C8CA
0x18000c89f  xor     r14b, r14b
0x18000c8a2  jmp     short loc_18000C8CA
0x18000c8a4  mov     rax, [rsp+300h+var_2D8]
0x18000c8a9  movzx   r8d, byte ptr [r12+r9]
0x18000c8ae  lea     rdx, [rsp+300h+var_2E0]
0x18000c8b3  lea     rcx, [rsp+300h+var_2D8]
0x18000c8b8  mov     rax, [rax+8]
0x18000c8bc  call    cs:__guard_dispatch_icall_fptr
0x18000c8c2  inc     r12d
0x18000c8c5  mov     r10d, [rsp+300h+var_2C8]
0x18000c8ca  cmp     r12d, r15d
0x18000c8cd  mov     r9, [rsp+300h+var_2B0]
0x18000c8d2  mov     r8, [rsp+300h+var_2D0]
0x18000c8d7  mov     r11d, 4
0x18000c8dd  jb      loc_18000C7C0
0x18000c8e3  mov     rdx, cs:?g_VerifiedSegmentData_1@WarbirdRuntime@@3UVERIFIED_SEGMENT_DATA_CONST_2@1@A; WarbirdRuntime::VERIFIED_SEGMENT_DATA_CONST_2 WarbirdRuntime::g_VerifiedSegmentData_1
0x18000c8ea  mov     r9d, [rsp+300h+var_2C4]
0x18000c8ef  inc     r9d
0x18000c8f2  mov     [rsp+300h+var_2C4], r9d
0x18000c8f7  mov     eax, edx
0x18000c8f9  and     eax, 3FFFFFFFh
0x18000c8fe  cmp     r9d, eax
0x18000c901  mov     r8, [rsp+300h+var_2D0]
0x18000c906  mov     r14d, 0
0x18000c90c  lea     r10, __ImageBase
0x18000c913  jb      loc_18000C6C0
0x18000c919  mov     rcx, [rsp+300h+var_2E0]
0x18000c91e  mov     rdi, [rsp+300h+var_298]
0x18000c923  mov     r13, [rsp+300h+var_290]
0x18000c928  mov     r12, [rsp+300h+var_288]
0x18000c92d  mov     rax, [rsp+300h+var_2A8]
0x18000c932  lea     r10, __ImageBase
0x18000c939  mov     r9, 8000000000000000h
0x18000c943  or      rcx, r9
0x18000c946  or      rax, r9
0x18000c949  cmp     rcx, rax
0x18000c94c  jz      short loc_18000C958
0x18000c94e  call    ?TrashStack@CTermination@WarbirdRuntime@@SAXXZ; WarbirdRuntime::CTermination::TrashStack(void)
0x18000c953  jmp     loc_18000CA1B
0x18000c958  test    r8d, r8d
0x18000c95b  jz      loc_18000CA1B
0x18000c961  mov     rcx, r14
0x18000c964  mov     [rsp+300h+var_2E0], rcx
0x18000c969  mov     r15d, r14d
0x18000c96c  test    edx, 3FFFFFFFh
0x18000c972  jbe     loc_18000C9FB
0x18000c978  nop     dword ptr [rax+rax+00000000h]
0x18000c980  mov     eax, r15d
0x18000c983  mov     rsi, ds:rva qword_1800A4A30[r10+rax*8]
0x18000c98b  mov     r14, rsi
0x18000c98e  shr     r14, 24h
0x18000c992  shr     rsi, 5
0x18000c996  and     esi, 0FFFFFFFh
0x18000c99c  add     rsi, r10
0x18000c99f  xor     ebx, ebx
0x18000c9a1  test    r14d, r14d
0x18000c9a4  jz      short loc_18000C9E3
0x18000c9a6  nop     word ptr [rax+rax+00000000h]
0x18000c9b0  mov     rax, [rsp+300h+var_2D8]
0x18000c9b5  movzx   r8d, byte ptr [rbx+rsi]
0x18000c9ba  lea     rdx, [rsp+300h+var_2E0]
0x18000c9bf  lea     rcx, [rsp+300h+var_2D8]
0x18000c9c4  mov     rax, [rax+8]
0x18000c9c8  call    cs:__guard_dispatch_icall_fptr
0x18000c9ce  inc     ebx
0x18000c9d0  cmp     ebx, r14d
0x18000c9d3  jb      short loc_18000C9B0
0x18000c9d5  mov     rdx, cs:?g_VerifiedSegmentData_1@WarbirdRuntime@@3UVERIFIED_SEGMENT_DATA_CONST_2@1@A; WarbirdRuntime::VERIFIED_SEGMENT_DATA_CONST_2 WarbirdRuntime::g_VerifiedSegmentData_1
0x18000c9dc  lea     r10, __ImageBase
0x18000c9e3  inc     r15d
0x18000c9e6  mov     ecx, edx
0x18000c9e8  and     ecx, 3FFFFFFFh
0x18000c9ee  cmp     r15d, ecx
0x18000c9f1  jb      short loc_18000C980
0x18000c9f3  mov     rcx, [rsp+300h+var_2E0]
0x18000c9f8  xor     r14d, r14d
0x18000c9fb  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000ca05  and     rcx, rax
0x18000ca08  mov     [rsp+300h+var_2E0], rcx
0x18000ca0d  mov     rax, [rsp+300h+var_2A8]
0x18000ca12  lock cmpxchg cs:?g_VerifiedSegmentDataReadWrite_1@WarbirdRuntime@@3UVERIFIED_SEGMENT_DATA_READ_WRITE_2@1@A, rcx; WarbirdRuntime::VERIFIED_SEGMENT_DATA_READ_WRITE_2 WarbirdRuntime::g_VerifiedSegmentDataReadWrite_1
0x18000ca1b  mov     eax, [rsp+300h+var_2C0]
0x18000ca1f  cmp     eax, 1
0x18000ca22  jnz     loc_18000CDC6
0x18000ca28  mov     [r13+4310h], r14d
0x18000ca2f  cmp     dword ptr [r13+1970h], 2
0x18000ca37  jnz     short loc_18000CA7C
0x18000ca39  mov     r8d, 10h; Size
0x18000ca3f  lea     rdx, [r13+1C8h]; Buf2
0x18000ca46  lea     rcx, _GUID_00000092_0000_0010_8000_00aa00389b71; Buf1
0x18000ca4d  call    memcmp_0
0x18000ca52  mov     ecx, r14d
0x18000ca55  test    eax, eax
0x18000ca57  setnz   cl
0x18000ca5a  mov     [r13+1970h], ecx
0x18000ca61  mov     rax, [r13+4598h]
0x18000ca68  cmp     dword ptr [rax+8], 0
0x18000ca6c  jnz     short loc_18000CA79
0x18000ca6e  test    ecx, ecx
0x18000ca70  jz      short loc_18000CA79
0x18000ca72  mov     dword ptr [rax+10h], 1
0x18000ca79  mov     [rax+8], ecx
0x18000ca7c  mov     r8d, 10h; Size
0x18000ca82  lea     rdx, [r13+1C8h]; Buf2
0x18000ca89  lea     rcx, MEDIASUBTYPE_PCM; Buf1
0x18000ca90  call    memcmp_0
0x18000ca95  test    eax, eax
0x18000ca97  jz      loc_18000CB51
0x18000ca9d  mov     r8d, 10h; Size
0x18000caa3  lea     rdx, [r13+1C8h]; Buf2
0x18000caaa  lea     rcx, MEDIASUBTYPE_IEEE_FLOAT; Buf1
0x18000cab1  call    memcmp_0
0x18000cab6  test    eax, eax
0x18000cab8  jz      loc_18000CB51
0x18000cabe  mov     r8d, 10h; Size
0x18000cac4  lea     rdx, [r13+1C8h]; Buf2
  ... truncated ...
```
