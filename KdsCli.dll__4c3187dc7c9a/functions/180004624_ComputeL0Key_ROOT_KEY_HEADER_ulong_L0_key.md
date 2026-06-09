# ComputeL0Key(_ROOT_KEY_HEADER *,ulong,_L0_key * *)

- ea: `0x180004624`
- end: `0x1800049fa`
- name: `?ComputeL0Key@@YAJPEAU_ROOT_KEY_HEADER@@KPEAPEAU_L0_key@@@Z`
- size: `982`
- prototype: `int(struct _ROOT_KEY_HEADER *, unsigned int, struct _L0_key **)`
- caller_count: `3`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007d28`
- `0x180008afc`
- `0x180009a14`

## callees

- `0x180001630`
- `0x180001f7c`
- `0x180004624`
- `0x180004d5c`
- `0x180006cb8`
- `0x18000d6a0`
- `0x18000d9d0`
- `0x180010920`
- `0x180010950`
- `0x18001a450`
- `0x18001a6ac`

## string_xrefs

- `0x18000470f`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsrootkey.cxx`
- `0x180004784`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsrootkey.cxx`

## pseudocode

```c
__int64 __fastcall ComputeL0Key(struct _ROOT_KEY_HEADER *a1, unsigned int a2, struct _L0_key **a3)
{
  struct _EVENT_DATA_DESCRIPTOR *v5; // rsi
  __int64 v6; // r12
  __int64 v7; // r14
  __int64 v8; // r15
  struct _GUID v9; // xmm0
  int v10; // eax
  void *v11; // r13
  DWORD v12; // ebx
  unsigned int v13; // r9d
  unsigned int v14; // ecx
  HRESULT DerivedKey; // eax
  __int64 v16; // rcx
  __int64 v17; // r8
  struct _EVENT_DATA_DESCRIPTOR *v18; // rax
  unsigned __int64 v19; // r12
  struct _EVENT_DATA_DESCRIPTOR v20; // xmm1
  struct _EVENT_DATA_DESCRIPTOR v21; // xmm0
  unsigned int v22; // eax
  struct _EVENT_DATA_DESCRIPTOR v23; // xmm1
  void *v24; // rax
  unsigned __int64 v25; // r14
  void *v26; // rax
  unsigned __int64 v27; // r15
  void *v28; // rax
  size_t v29; // r14
  void *v30; // rax
  size_t v31; // r14
  void *v32; // rax
  BYTE *pNonce; // [rsp+20h] [rbp-B9h]
  PBYTE *ppKey; // [rsp+48h] [rbp-91h]
  DWORD offset; // [rsp+70h] [rbp-69h] BYREF
  unsigned int v37; // [rsp+78h] [rbp-61h]
  unsigned int Size; // [rsp+7Ch] [rbp-5Dh]
  unsigned int Size_4; // [rsp+80h] [rbp-59h]
  DWORD derivedKeyLength[2]; // [rsp+88h] [rbp-51h] BYREF
  char *v41; // [rsp+90h] [rbp-49h]
  struct _L0_key **v42; // [rsp+98h] [rbp-41h]
  struct _GUID v43; // [rsp+A0h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v44; // [rsp+B0h] [rbp-29h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v45; // [rsp+C0h] [rbp-19h]
  struct _EVENT_DATA_DESCRIPTOR v46; // [rsp+D0h] [rbp-9h]
  struct _EVENT_DATA_DESCRIPTOR v47; // [rsp+E0h] [rbp+7h]

  v42 = a3;
  v37 = a2;
  v5 = 0;
  memset_0(&v44, 0, 0x40u);
  v6 = -1;
  do
    ++v6;
  while ( *(_WORD *)(*((_QWORD *)a1 + 15) + 2 * v6) );
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)(*((_QWORD *)a1 + 4) + 2 * v7) );
  v8 = -1;
  do
    ++v8;
  while ( *(_WORD *)(*((_QWORD *)a1 + 7) + 2 * v8) );
  Size = *((_DWORD *)a1 + 12);
  Size_4 = *((_DWORD *)a1 + 18);
  v9 = *(struct _GUID *)((char *)a1 + 4);
  v41 = (char *)a1 + 4;
  *(_QWORD *)derivedKeyLength = 0;
  offset = 0;
  v43 = v9;
  v10 = GenerateKDFContext(&v43, a2, -1, -1, 0, (unsigned __int8 **)derivedKeyLength, &offset, 0);
  v11 = *(void **)derivedKeyLength;
  v12 = v10;
  if ( v10 < 0 )
  {
    v13 = 1653;
    v14 = v10;
LABEL_9:
    SidKeyDebugTraceError(v14, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsrootkey.cxx", v13);
    goto LABEL_31;
  }
  LODWORD(ppKey) = 0;
  LODWORD(pNonce) = 64;
  DerivedKey = GenerateDerivedKey(
                 *((PINFORMATIONCARD_CRYPTO_HANDLE *)a1 + 4),
                 *((_QWORD *)a1 + 5),
                 (PBYTE)*((unsigned int *)a1 + 12),
                 (_DWORD)a1 + 160,
                 pNonce,
                 derivedKeyLength[0],
                 offset,
                 0,
                 0,
                 ppKey);
  v12 = DerivedKey;
  if ( DerivedKey >= 0 )
  {
    v18 = (struct _EVENT_DATA_DESCRIPTOR *)SIDKeyProvAlloc(0xF0u);
    v5 = v18;
    if ( v18 )
    {
      v19 = 2 * v6 + 2;
      v20 = v45;
      v18[11] = v44;
      v18[10].Size = 64;
      v21 = v46;
      v22 = v37;
      v5[12] = v20;
      LODWORD(v5->Ptr) = v22;
      v23 = v47;
      v5[13] = v21;
      v5[14] = v23;
      *(struct _EVENT_DATA_DESCRIPTOR *)&v5->Size = *(struct _EVENT_DATA_DESCRIPTOR *)a1;
      *(struct _EVENT_DATA_DESCRIPTOR *)((char *)v5 + 24) = *((struct _EVENT_DATA_DESCRIPTOR *)a1 + 1);
      *(struct _EVENT_DATA_DESCRIPTOR *)((char *)v5 + 40) = *((struct _EVENT_DATA_DESCRIPTOR *)a1 + 2);
      *(struct _EVENT_DATA_DESCRIPTOR *)((char *)v5 + 56) = *((struct _EVENT_DATA_DESCRIPTOR *)a1 + 3);
      *(struct _EVENT_DATA_DESCRIPTOR *)((char *)v5 + 72) = *((struct _EVENT_DATA_DESCRIPTOR *)a1 + 4);
      *(struct _EVENT_DATA_DESCRIPTOR *)((char *)v5 + 88) = *((struct _EVENT_DATA_DESCRIPTOR *)a1 + 5);
      *(struct _EVENT_DATA_DESCRIPTOR *)((char *)v5 + 104) = *((struct _EVENT_DATA_DESCRIPTOR *)a1 + 6);
      *(struct _EVENT_DATA_DESCRIPTOR *)((char *)v5 + 120) = *((struct _EVENT_DATA_DESCRIPTOR *)a1 + 7);
      *(struct _EVENT_DATA_DESCRIPTOR *)((char *)v5 + 136) = *((struct _EVENT_DATA_DESCRIPTOR *)a1 + 8);
      *(struct _EVENT_DATA_DESCRIPTOR *)((char *)v5 + 152) = *((struct _EVENT_DATA_DESCRIPTOR *)a1 + 9);
      v24 = SIDKeyProvAlloc(v19);
      v5[8].Ptr = (ULONGLONG)v24;
      if ( v24 )
      {
        v25 = 2 * v7 + 2;
        memcpy_0(v24, *((const void **)a1 + 15), v19);
        v26 = SIDKeyProvAlloc(v25);
        *(_QWORD *)&v5[2].Size = v26;
        if ( v26 )
        {
          v27 = 2 * v8 + 2;
          memcpy_0(v26, *((const void **)a1 + 4), v25);
          v28 = SIDKeyProvAlloc(v27);
          v5[4].Ptr = (ULONGLONG)v28;
          if ( v28 )
          {
            memcpy_0(v28, *((const void **)a1 + 7), v27);
            if ( *((_QWORD *)a1 + 5) )
            {
              v29 = Size;
              v30 = SIDKeyProvAlloc(Size);
              v5[3].Ptr = (ULONGLONG)v30;
              if ( !v30 )
              {
                v13 = 1727;
                goto LABEL_15;
              }
              memcpy_0(v30, *((const void **)a1 + 5), v29);
            }
            if ( *((_QWORD *)a1 + 8) )
            {
              v31 = Size_4;
              v32 = SIDKeyProvAlloc(Size_4);
              *(_QWORD *)&v5[4].Size = v32;
              if ( !v32 )
              {
                v13 = 1739;
                goto LABEL_15;
              }
              memcpy_0(v32, *((const void **)a1 + 8), v31);
            }
            *v42 = (struct _L0_key *)v5;
            v5 = 0;
            goto LABEL_31;
          }
          v13 = 1716;
        }
        else
        {
          v13 = 1707;
        }
      }
      else
      {
        v13 = 1698;
      }
    }
    else
    {
      v13 = 1683;
    }
LABEL_15:
    v12 = -2147024882;
    v14 = -2147024882;
    goto LABEL_9;
  }
  SidKeyDebugTraceError(DerivedKey, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsrootkey.cxx", 0x68Au);
  if ( (Microsoft_Windows_KdsSvcEnableBits & 1) != 0 )
  {
    v45.Ptr = (ULONGLONG)v41;
    offset = v12;
    v46.Ptr = (ULONGLONG)&offset;
    *(_QWORD *)&v45.Size = 16;
    *(_QWORD *)&v46.Size = 4;
    McGenEventWrite_EventWriteTransfer(v16, (const EVENT_DESCRIPTOR *)KdsKeyGenerationFailure, v17, 3u, &v44);
  }
LABEL_31:
  if ( v11 )
    SIDKeyProvFree(v11);
  if ( v5 )
    FreeL0Key((struct _L0_key *)v5);
  return v12;
}

```

## disassembly

```asm
0x180004624  mov     [rsp-8+arg_8], rbx
0x180004629  push    rbp
0x18000462a  push    rsi
0x18000462b  push    rdi
0x18000462c  push    r12
0x18000462e  push    r13
0x180004630  push    r14
0x180004632  push    r15
0x180004634  lea     rbp, [rsp-27h]
0x180004639  sub     rsp, 100h
0x180004640  mov     rax, cs:__security_cookie
0x180004647  xor     rax, rsp
0x18000464a  mov     [rbp+57h+var_40], rax
0x18000464e  xor     r13d, r13d
0x180004651  mov     [rbp+57h+var_98], r8
0x180004655  mov     ebx, edx
0x180004657  mov     [rbp+57h+var_B8], edx
0x18000465a  mov     rdi, rcx
0x18000465d  xor     edx, edx; Val
0x18000465f  lea     rcx, [rbp+57h+var_80]; void *
0x180004663  mov     esi, r13d
0x180004666  lea     r8d, [r13+40h]; Size
0x18000466a  call    memset_0
0x18000466f  mov     rax, [rdi+78h]
0x180004673  or      r8, 0FFFFFFFFFFFFFFFFh; int
0x180004677  mov     r12, r8
0x18000467a  inc     r12
0x18000467d  cmp     [rax+r12*2], r13w
0x180004682  jnz     short loc_18000467A
0x180004684  mov     rax, [rdi+20h]
0x180004688  mov     r14, r8
0x18000468b  inc     r14
0x18000468e  cmp     [rax+r14*2], r13w
0x180004693  jnz     short loc_18000468B
0x180004695  mov     rax, [rdi+38h]
0x180004699  mov     r15, r8
0x18000469c  inc     r15
0x18000469f  cmp     [rax+r15*2], r13w
0x1800046a4  jnz     short loc_18000469C
0x1800046a6  mov     eax, [rdi+30h]
0x1800046a9  lea     rcx, [rbp+57h+var_90]; struct _GUID *
0x1800046ad  mov     dword ptr [rbp+57h+Size], eax
0x1800046b0  mov     r9d, r8d; int
0x1800046b3  mov     eax, [rdi+48h]
0x1800046b6  mov     edx, ebx; unsigned int
0x1800046b8  mov     dword ptr [rbp+57h+Size+4], eax
0x1800046bb  lea     rax, [rdi+4]
0x1800046bf  movups  xmm0, xmmword ptr [rax]
0x1800046c2  mov     [rbp+57h+var_A0], rax
0x1800046c6  lea     rax, [rbp+57h+var_C0]
0x1800046ca  mov     [rsp+130h+algId], r13; unsigned int *
0x1800046cf  mov     qword ptr [rsp+130h+offset], rax; unsigned int *
0x1800046d4  lea     rax, [rbp+57h+var_A8]
0x1800046d8  mov     qword ptr [rsp+130h+derivedKeyLength], rax; unsigned __int8 **
0x1800046dd  mov     dword ptr [rsp+130h+pNonce], r13d; unsigned int
0x1800046e2  mov     qword ptr [rbp+57h+var_A8], r13
0x1800046e6  mov     [rbp+57h+var_C0], r13d
0x1800046ea  movdqu  xmmword ptr [rbp+57h+var_90.Data1], xmm0
0x1800046ef  call    ?GenerateKDFContext@@YAJU_GUID@@KJJKPEAPEAEPEAK2@Z; GenerateKDFContext(_GUID,ulong,long,long,ulong,uchar * *,ulong *,ulong *)
0x1800046f4  mov     r13, qword ptr [rbp+57h+var_A8]
0x1800046f8  xor     ecx, ecx
0x1800046fa  mov     ebx, eax
0x1800046fc  test    eax, eax
0x1800046fe  jns     short loc_180004720
0x180004700  mov     r9d, 675h; unsigned int
0x180004706  mov     ecx, eax; unsigned int
0x180004708  lea     rdx, aHr; "hr"
0x18000470f  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180004716  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000471b  jmp     loc_1800049B7
0x180004720  mov     r8d, [rdi+30h]; pLabel
0x180004724  lea     rax, [rbp+57h+var_80]
0x180004728  mov     rdx, [rdi+28h]; cbLabel
0x18000472c  lea     r9, [rdi+0A0h]; cbNonce
0x180004733  mov     [rsp+130h+var_C8], rcx
0x180004738  mov     [rsp+130h+var_D0], 40h ; '@'
0x180004740  mov     [rsp+130h+var_D8], rax
0x180004745  mov     eax, [rbp+57h+var_C0]
0x180004748  mov     [rsp+130h+var_E0], 1
0x180004750  mov     dword ptr [rsp+130h+ppKey], ecx; ppKey
0x180004754  mov     [rsp+130h+pcbKey], rcx; pcbKey
0x180004759  mov     [rsp+130h+algId], rcx; algId
0x18000475e  mov     rcx, [rdi+20h]; hCrypto
0x180004762  mov     [rsp+130h+offset], eax; offset
0x180004766  mov     qword ptr [rsp+130h+derivedKeyLength], r13; derivedKeyLength
0x18000476b  mov     dword ptr [rsp+130h+pNonce], 40h ; '@'; pNonce
0x180004773  call    ?GenerateDerivedKey@@YAJPEBGPEAEK1K1KPEAK1KK1KPEAPEAG@Z; GenerateDerivedKey(ushort const *,uchar *,ulong,uchar *,ulong,uchar *,ulong,ulong *,uchar *,ulong,ulong,uchar *,ulong,ushort * *)
0x180004778  mov     ebx, eax
0x18000477a  test    eax, eax
0x18000477c  jns     short loc_1800047E9
0x18000477e  mov     r9d, 68Ah; unsigned int
0x180004784  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000478b  lea     rdx, aHr; "hr"
0x180004792  mov     ecx, eax; unsigned int
0x180004794  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180004799  test    cs:Microsoft_Windows_KdsSvcEnableBits, 1
0x1800047a0  jz      loc_1800049B7
0x1800047a6  mov     rax, [rbp+57h+var_A0]
0x1800047aa  lea     rdx, KdsKeyGenerationFailure
0x1800047b1  mov     qword ptr [rbp+57h+var_70], rax
0x1800047b5  mov     r9d, 3
0x1800047bb  lea     rax, [rbp+57h+var_C0]
0x1800047bf  mov     [rbp+57h+var_C0], ebx
0x1800047c2  mov     qword ptr [rbp+57h+var_60], rax
0x1800047c6  lea     rax, [rbp+57h+var_80]
0x1800047ca  mov     [rsp+130h+pNonce], rax
0x1800047cf  mov     qword ptr [rbp+57h+var_70+8], 10h
0x1800047d7  mov     qword ptr [rbp+57h+var_60+8], 4
0x1800047df  call    McGenEventWrite_EventWriteTransfer
0x1800047e4  jmp     loc_1800049B7
0x1800047e9  mov     ecx, 0F0h; unsigned __int64
0x1800047ee  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x1800047f3  mov     rsi, rax
0x1800047f6  test    rax, rax
0x1800047f9  jnz     short loc_180004810
0x1800047fb  mov     r9d, 693h
0x180004801  mov     ebx, 8007000Eh
0x180004806  mov     ecx, 8007000Eh
0x18000480b  jmp     loc_180004708
0x180004810  movaps  xmm0, [rbp+57h+var_80]
0x180004814  lea     r12, ds:2[r12*2]
0x18000481c  movaps  xmm1, [rbp+57h+var_70]
0x180004820  mov     rcx, r12; unsigned __int64
0x180004823  movups  xmmword ptr [rsi+0B0h], xmm0
0x18000482a  mov     dword ptr [rax+0A8h], 40h ; '@'
0x180004834  movaps  xmm0, [rbp+57h+var_60]
0x180004838  mov     eax, [rbp+57h+var_B8]
0x18000483b  movups  xmmword ptr [rsi+0C0h], xmm1
0x180004842  mov     [rsi], eax
0x180004844  movaps  xmm1, [rbp+57h+var_50]
0x180004848  movups  xmmword ptr [rsi+0D0h], xmm0
0x18000484f  movups  xmmword ptr [rsi+0E0h], xmm1
0x180004856  movups  xmm0, xmmword ptr [rdi]
0x180004859  movups  xmmword ptr [rsi+8], xmm0
0x18000485d  movups  xmm1, xmmword ptr [rdi+10h]
0x180004861  movups  xmmword ptr [rsi+18h], xmm1
0x180004865  movups  xmm0, xmmword ptr [rdi+20h]
0x180004869  movups  xmmword ptr [rsi+28h], xmm0
0x18000486d  movups  xmm1, xmmword ptr [rdi+30h]
0x180004871  movups  xmmword ptr [rsi+38h], xmm1
0x180004875  movups  xmm0, xmmword ptr [rdi+40h]
0x180004879  movups  xmmword ptr [rsi+48h], xmm0
0x18000487d  movups  xmm1, xmmword ptr [rdi+50h]
0x180004881  movups  xmmword ptr [rsi+58h], xmm1
0x180004885  movups  xmm0, xmmword ptr [rdi+60h]
0x180004889  movups  xmmword ptr [rsi+68h], xmm0
0x18000488d  movups  xmm1, xmmword ptr [rdi+70h]
0x180004891  movups  xmmword ptr [rsi+78h], xmm1
0x180004895  movups  xmm0, xmmword ptr [rdi+80h]
0x18000489c  movups  xmmword ptr [rsi+88h], xmm0
0x1800048a3  movups  xmm1, xmmword ptr [rdi+90h]
0x1800048aa  movups  xmmword ptr [rsi+98h], xmm1
0x1800048b1  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x1800048b6  mov     [rsi+80h], rax
0x1800048bd  test    rax, rax
0x1800048c0  jnz     short loc_1800048CD
0x1800048c2  mov     r9d, 6A2h
0x1800048c8  jmp     loc_180004801
0x1800048cd  mov     rdx, [rdi+78h]; Src
0x1800048d1  lea     r14, ds:2[r14*2]
0x1800048d9  mov     r8, r12; Size
0x1800048dc  mov     rcx, rax; void *
0x1800048df  call    memcpy_0
0x1800048e4  mov     rcx, r14; unsigned __int64
0x1800048e7  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x1800048ec  mov     [rsi+28h], rax
0x1800048f0  test    rax, rax
0x1800048f3  jnz     short loc_180004900
0x1800048f5  mov     r9d, 6ABh
0x1800048fb  jmp     loc_180004801
0x180004900  mov     rdx, [rdi+20h]; Src
0x180004904  lea     r15, ds:2[r15*2]
0x18000490c  mov     r8, r14; Size
0x18000490f  mov     rcx, rax; void *
0x180004912  call    memcpy_0
0x180004917  mov     rcx, r15; unsigned __int64
0x18000491a  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18000491f  mov     [rsi+40h], rax
0x180004923  test    rax, rax
0x180004926  jnz     short loc_180004933
0x180004928  mov     r9d, 6B4h
0x18000492e  jmp     loc_180004801
0x180004933  mov     rdx, [rdi+38h]; Src
0x180004937  mov     r8, r15; Size
0x18000493a  mov     rcx, rax; void *
0x18000493d  call    memcpy_0
0x180004942  cmp     qword ptr [rdi+28h], 0
0x180004947  jz      short loc_180004978
0x180004949  mov     r14d, dword ptr [rbp+57h+Size]
0x18000494d  mov     ecx, r14d; unsigned __int64
0x180004950  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x180004955  mov     [rsi+30h], rax
0x180004959  test    rax, rax
0x18000495c  jnz     short loc_180004969
0x18000495e  mov     r9d, 6BFh
0x180004964  jmp     loc_180004801
0x180004969  mov     rdx, [rdi+28h]; Src
0x18000496d  mov     r8, r14; Size
0x180004970  mov     rcx, rax; void *
0x180004973  call    memcpy_0
0x180004978  cmp     qword ptr [rdi+40h], 0
0x18000497d  jz      short loc_1800049AE
0x18000497f  mov     r14d, dword ptr [rbp+57h+Size+4]
0x180004983  mov     ecx, r14d; unsigned __int64
0x180004986  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18000498b  mov     [rsi+48h], rax
0x18000498f  test    rax, rax
0x180004992  jnz     short loc_18000499F
0x180004994  mov     r9d, 6CBh
0x18000499a  jmp     loc_180004801
0x18000499f  mov     rdx, [rdi+40h]; Src
0x1800049a3  mov     r8, r14; Size
0x1800049a6  mov     rcx, rax; void *
0x1800049a9  call    memcpy_0
0x1800049ae  mov     rax, [rbp+57h+var_98]
0x1800049b2  mov     [rax], rsi
0x1800049b5  xor     esi, esi
0x1800049b7  test    r13, r13
0x1800049ba  jz      short loc_1800049C4
0x1800049bc  mov     rcx, r13; lpMem
0x1800049bf  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x1800049c4  test    rsi, rsi
0x1800049c7  jz      short loc_1800049D1
0x1800049c9  mov     rcx, rsi; lpMem
0x1800049cc  call    ?FreeL0Key@@YAXPEAU_L0_key@@@Z; FreeL0Key(_L0_key *)
0x1800049d1  mov     eax, ebx
0x1800049d3  mov     rcx, [rbp+57h+var_40]
0x1800049d7  xor     rcx, rsp; StackCookie
0x1800049da  call    __security_check_cookie
0x1800049df  mov     rbx, [rsp+130h+arg_8]
0x1800049e7  add     rsp, 100h
0x1800049ee  pop     r15
0x1800049f0  pop     r14
0x1800049f2  pop     r13
0x1800049f4  pop     r12
0x1800049f6  pop     rdi
0x1800049f7  pop     rsi
0x1800049f8  pop     rbp
0x1800049f9  retn
```
