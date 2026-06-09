# KeyAtt_StartOIAPSession(void *,uint *,uchar *,uchar *)

- ea: `0x1800942e8`
- end: `0x180094604`
- name: `?KeyAtt_StartOIAPSession@@YAJPEAXPEAIPEAE2@Z`
- size: `796`
- prototype: `__int64 __fastcall(TBS_HCONTEXT hContext, unsigned int *, unsigned __int8 *Destination, PUCHAR pbBuffer)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18009366c`

## callees

- `0x180015660`
- `0x1800157c0`
- `0x180029260`
- `0x1800764d0`
- `0x18007704c`
- `0x1800942e8`
- `0x1800946d4`
- `0x180094714`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800945c1`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800945c1`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800944f0`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800944f0`
- `bcrypt!BCryptGenRandom` at `0x18009455e`
- `bcrypt!BCryptGenRandom` at `0x18009455e`
- `tbs!Tbsip_Submit_Command` at `0x1800943d3`
- `tbs!Tbsip_Submit_Command` at `0x1800943d3`

## pseudocode

```c
__int64 __fastcall KeyAtt_StartOIAPSession(
        TBS_HCONTEXT hContext,
        unsigned int *a2,
        unsigned __int8 *Destination,
        UCHAR *pbBuffer)
{
  int v8; // ebx
  unsigned int v9; // edi
  NTSTATUS v10; // eax
  NTSTATUS v11; // eax
  int v13; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v14; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int pcbResult; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v16; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v17; // [rsp+50h] [rbp-B0h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+58h] [rbp-A8h] BYREF
  void *Source; // [rsp+60h] [rbp-A0h] BYREF
  BYTE v20[24]; // [rsp+68h] [rbp-98h] BYREF
  BYTE pabCommand[4]; // [rsp+80h] [rbp-80h] BYREF
  int v22; // [rsp+84h] [rbp-7Ch]
  __int16 v23; // [rsp+88h] [rbp-78h]
  BYTE pabResult[512]; // [rsp+90h] [rbp-70h] BYREF

  v13 = 0;
  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v20, L"KeyAtt_StartOIAPSession", &v13);
  *(_DWORD *)pabCommand = 49408;
  v22 = 2560;
  v23 = 2560;
  memset_0(pabResult, 0, sizeof(pabResult));
  pcbResult = 512;
  v14 = 0;
  v16 = 0;
  v17 = 0;
  Source = 0;
  phAlgorithm = 0;
  if ( !a2 || !Destination || !pbBuffer )
    goto LABEL_33;
  *(_OWORD *)pbBuffer = 0;
  *((_DWORD *)pbBuffer + 4) = 0;
  v13 = Tbsip_Submit_Command(hContext, 0, 0xC8u, pabCommand, 0xAu, pabResult, &pcbResult);
  v8 = v13;
  if ( v13 < 0 )
    goto LABEL_35;
  v9 = pcbResult;
  if ( pcbResult < 2 )
  {
LABEL_33:
    v8 = -2147024809;
    goto LABEL_34;
  }
  v14 = 2;
  v13 = 0;
  v13 = ReadBigEndian(pabResult, pcbResult, &v14, &v16);
  v8 = v13;
  if ( v13 < 0 )
    goto LABEL_35;
  if ( v16 != v9 )
    goto LABEL_11;
  v13 = ReadBigEndian(pabResult, v9, &v14, &v17);
  v8 = v13;
  if ( v13 < 0 )
    goto LABEL_35;
  if ( v17 )
  {
    if ( (v17 & 0xFFFF0000) == 0 )
    {
      v8 = v17 | 0x80280000;
      goto LABEL_34;
    }
LABEL_11:
    v8 = -2147467259;
LABEL_34:
    v13 = v8;
    goto LABEL_35;
  }
  v13 = ReadBigEndian(pabResult, v9, &v14, a2);
  v8 = v13;
  if ( v13 >= 0 )
  {
    v13 = ReadBigEndian(pabResult, v9, &v14, (unsigned __int8 **)&Source, 0x14u);
    v8 = v13;
    if ( v13 >= 0 )
    {
      if ( memcpy_s(Destination, 0x14u, Source, 0x14u) )
        goto LABEL_11;
      v10 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"RNG", 0, 0);
      if ( !v10 )
      {
        v13 = 0;
LABEL_25:
        v11 = BCryptGenRandom(phAlgorithm, pbBuffer, 0x14u, 0);
        if ( v11 )
        {
          if ( (v11 & 0xFFFF000) == 0x290000 )
          {
            v8 = v11 & 0xFFF | 0x80280000;
          }
          else if ( (v11 & 0xFFF0000) == 0x70000 )
          {
            v8 = (unsigned __int16)v11;
            if ( (_WORD)v11 )
              v8 = (unsigned __int16)v11 | 0x80070000;
          }
          else
          {
            v8 = v11 | 0x10000000;
          }
        }
        else
        {
          v8 = 0;
        }
        goto LABEL_34;
      }
      if ( (v10 & 0xFFFF000) == 0x290000 )
      {
        v8 = v10 & 0xFFF | 0x80280000;
      }
      else if ( (v10 & 0xFFF0000) == 0x70000 )
      {
        v8 = (unsigned __int16)v10;
        if ( (_WORD)v10 )
          v8 = (unsigned __int16)v10 | 0x80070000;
      }
      else
      {
        v8 = v10 | 0x10000000;
      }
      v13 = v8;
      if ( v8 >= 0 )
        goto LABEL_25;
    }
  }
LABEL_35:
  if ( phAlgorithm )
  {
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    v8 = v13;
    phAlgorithm = 0;
  }
  KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v20);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800942e8  push    rbp
0x1800942ea  push    rbx
0x1800942eb  push    rsi
0x1800942ec  push    rdi
0x1800942ed  push    r12
0x1800942ef  push    r14
0x1800942f1  push    r15
0x1800942f3  lea     rbp, [rsp-1A0h]
0x1800942fb  sub     rsp, 2A0h
0x180094302  mov     rax, cs:__security_cookie
0x180094309  xor     rax, rsp
0x18009430c  mov     [rbp+1D0h+var_40], rax
0x180094313  mov     rsi, r8
0x180094316  mov     r15, rdx
0x180094319  mov     rbx, rcx
0x18009431c  lea     r8, [rsp+2D0h+var_290]; int *
0x180094321  xor     r12d, r12d
0x180094324  lea     rdx, aKeyattStartoia; "KeyAtt_StartOIAPSession"
0x18009432b  lea     rcx, [rsp+2D0h+var_268]; this
0x180094330  mov     [rsp+2D0h+var_290], r12d
0x180094335  mov     r14, r9
0x180094338  call    ??0KspFunctionLogger@@QEAA@QEBGAEBJ@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,long const &)
0x18009433d  mov     edi, 200h
0x180094342  mov     dword ptr [rbp+1D0h+pabCommand], 0C100h
0x180094349  mov     r8d, edi; Size
0x18009434c  mov     [rbp+1D0h+var_24C], 0A00h
0x180094353  xor     edx, edx; Val
0x180094355  mov     [rbp+1D0h+var_248], 0A00h
0x18009435b  lea     rcx, [rbp+1D0h+var_240]; void *
0x18009435f  call    memset_0
0x180094364  mov     [rsp+2D0h+var_288], edi
0x180094368  mov     [rsp+2D0h+var_28C], r12d
0x18009436d  mov     [rsp+2D0h+var_284], r12d
0x180094372  mov     [rsp+2D0h+var_280], r12d
0x180094377  mov     [rsp+2D0h+Source], r12
0x18009437c  mov     [rsp+2D0h+phAlgorithm], r12
0x180094381  test    r15, r15
0x180094384  jz      loc_1800945AC
0x18009438a  test    rsi, rsi
0x18009438d  jz      loc_1800945AC
0x180094393  test    r14, r14
0x180094396  jz      loc_1800945AC
0x18009439c  xor     eax, eax
0x18009439e  lea     r9, [rbp+1D0h+pabCommand]; pabCommand
0x1800943a2  xorps   xmm0, xmm0
0x1800943a5  xor     edx, edx; Locality
0x1800943a7  movups  xmmword ptr [r14], xmm0
0x1800943ab  mov     [r14+10h], eax
0x1800943af  mov     r8d, 0C8h; Priority
0x1800943b5  lea     rax, [rsp+2D0h+var_288]
0x1800943ba  mov     rcx, rbx; hContext
0x1800943bd  mov     [rsp+2D0h+pcbResult], rax; pcbResult
0x1800943c2  lea     rax, [rbp+1D0h+var_240]
0x1800943c6  mov     [rsp+2D0h+pabResult], rax; pabResult
0x1800943cb  mov     [rsp+2D0h+cbCommand], 0Ah; cbCommand
0x1800943d3  call    cs:__imp_Tbsip_Submit_Command
0x1800943da  nop     dword ptr [rax+rax+00h]
0x1800943df  mov     [rsp+2D0h+var_290], eax
0x1800943e3  mov     ebx, eax
0x1800943e5  test    eax, eax
0x1800943e7  js      loc_1800945B5
0x1800943ed  mov     edi, [rsp+2D0h+var_288]
0x1800943f1  cmp     edi, 2
0x1800943f4  jb      loc_1800945AC
0x1800943fa  lea     r9, [rsp+2D0h+var_284]; unsigned int *
0x1800943ff  mov     [rsp+2D0h+var_28C], 2
0x180094407  lea     r8, [rsp+2D0h+var_28C]; unsigned int *
0x18009440c  mov     [rsp+2D0h+var_290], r12d
0x180094411  mov     edx, edi; unsigned int
0x180094413  lea     rcx, [rbp+1D0h+var_240]; unsigned __int8 *
0x180094417  call    ?ReadBigEndian@@YAJPEBEIPEAI1@Z; ReadBigEndian(uchar const *,uint,uint *,uint *)
0x18009441c  mov     [rsp+2D0h+var_290], eax
0x180094420  mov     ebx, eax
0x180094422  test    eax, eax
0x180094424  js      loc_1800945B5
0x18009442a  cmp     [rsp+2D0h+var_284], edi
0x18009442e  jnz     short loc_180094463
0x180094430  lea     r9, [rsp+2D0h+var_280]; unsigned int *
0x180094435  mov     edx, edi; unsigned int
0x180094437  lea     r8, [rsp+2D0h+var_28C]; unsigned int *
0x18009443c  lea     rcx, [rbp+1D0h+var_240]; unsigned __int8 *
0x180094440  call    ?ReadBigEndian@@YAJPEBEIPEAI1@Z; ReadBigEndian(uchar const *,uint,uint *,uint *)
0x180094445  mov     [rsp+2D0h+var_290], eax
0x180094449  mov     ebx, eax
0x18009444b  test    eax, eax
0x18009444d  js      loc_1800945B5
0x180094453  mov     ebx, [rsp+2D0h+var_280]
0x180094457  test    ebx, ebx
0x180094459  jz      short loc_180094478
0x18009445b  test    ebx, 0FFFF0000h
0x180094461  jz      short loc_18009446D
0x180094463  mov     ebx, 80004005h
0x180094468  jmp     loc_1800945B1
0x18009446d  or      ebx, 80280000h
0x180094473  jmp     loc_1800945B1
0x180094478  mov     r9, r15; unsigned int *
0x18009447b  lea     r8, [rsp+2D0h+var_28C]; unsigned int *
0x180094480  mov     edx, edi; unsigned int
0x180094482  lea     rcx, [rbp+1D0h+var_240]; unsigned __int8 *
0x180094486  call    ?ReadBigEndian@@YAJPEBEIPEAI1@Z; ReadBigEndian(uchar const *,uint,uint *,uint *)
0x18009448b  mov     [rsp+2D0h+var_290], eax
0x18009448f  mov     ebx, eax
0x180094491  test    eax, eax
0x180094493  js      loc_1800945B5
0x180094499  mov     r15d, 14h
0x18009449f  lea     r9, [rsp+2D0h+Source]; unsigned __int8 **
0x1800944a4  lea     r8, [rsp+2D0h+var_28C]; unsigned int *
0x1800944a9  mov     [rsp+2D0h+cbCommand], r15d; unsigned int
0x1800944ae  mov     edx, edi; unsigned int
0x1800944b0  lea     rcx, [rbp+1D0h+var_240]; unsigned __int8 *
0x1800944b4  call    ?ReadBigEndian@@YAJPEAEIPEAIPEAPEAEI@Z; ReadBigEndian(uchar *,uint,uint *,uchar * *,uint)
0x1800944b9  mov     [rsp+2D0h+var_290], eax
0x1800944bd  mov     ebx, eax
0x1800944bf  test    eax, eax
0x1800944c1  js      loc_1800945B5
0x1800944c7  mov     r8, [rsp+2D0h+Source]; Source
0x1800944cc  mov     r9d, r15d; SourceSize
0x1800944cf  mov     edx, r15d; DestinationSize
0x1800944d2  mov     rcx, rsi; Destination
0x1800944d5  call    memcpy_s
0x1800944da  test    eax, eax
0x1800944dc  jnz     short loc_180094463
0x1800944de  xor     r9d, r9d; dwFlags
0x1800944e1  lea     rdx, aRng; "RNG"
0x1800944e8  xor     r8d, r8d; pszImplementation
0x1800944eb  lea     rcx, [rsp+2D0h+phAlgorithm]; phAlgorithm
0x1800944f0  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800944f7  nop     dword ptr [rax+rax+00h]
0x1800944fc  mov     edi, 80280000h
0x180094501  mov     esi, 10000000h
0x180094506  mov     ebx, eax
0x180094508  test    eax, eax
0x18009450a  jnz     short loc_180094513
0x18009450c  mov     [rsp+2D0h+var_290], r12d
0x180094511  jmp     short loc_180094550
0x180094513  and     eax, 0FFFF000h
0x180094518  cmp     eax, 290000h
0x18009451d  jnz     short loc_180094529
0x18009451f  and     ebx, 0FFFh
0x180094525  or      ebx, edi
0x180094527  jmp     short loc_180094548
0x180094529  mov     eax, ebx
0x18009452b  and     eax, 0FFF0000h
0x180094530  cmp     eax, 70000h
0x180094535  jnz     short loc_180094546
0x180094537  movzx   ebx, bx
0x18009453a  test    ebx, ebx
0x18009453c  jz      short loc_180094548
0x18009453e  or      ebx, 80070000h
0x180094544  jmp     short loc_180094548
0x180094546  or      ebx, esi
0x180094548  mov     [rsp+2D0h+var_290], ebx
0x18009454c  test    ebx, ebx
0x18009454e  js      short loc_1800945B5
0x180094550  mov     rcx, [rsp+2D0h+phAlgorithm]; hAlgorithm
0x180094555  xor     r9d, r9d; dwFlags
0x180094558  mov     r8d, r15d; cbBuffer
0x18009455b  mov     rdx, r14; pbBuffer
0x18009455e  call    cs:__imp_BCryptGenRandom
0x180094565  nop     dword ptr [rax+rax+00h]
0x18009456a  mov     ebx, eax
0x18009456c  test    eax, eax
0x18009456e  jnz     short loc_180094575
0x180094570  mov     ebx, r12d
0x180094573  jmp     short loc_1800945B1
0x180094575  and     eax, 0FFFF000h
0x18009457a  cmp     eax, 290000h
0x18009457f  jnz     short loc_18009458B
0x180094581  and     ebx, 0FFFh
0x180094587  or      ebx, edi
0x180094589  jmp     short loc_1800945B1
0x18009458b  mov     eax, ebx
0x18009458d  and     eax, 0FFF0000h
0x180094592  cmp     eax, 70000h
0x180094597  jnz     short loc_1800945A8
0x180094599  movzx   ebx, bx
0x18009459c  test    ebx, ebx
0x18009459e  jz      short loc_1800945B1
0x1800945a0  or      ebx, 80070000h
0x1800945a6  jmp     short loc_1800945B1
0x1800945a8  or      ebx, esi
0x1800945aa  jmp     short loc_1800945B1
0x1800945ac  mov     ebx, 80070057h
0x1800945b1  mov     [rsp+2D0h+var_290], ebx
0x1800945b5  mov     rcx, [rsp+2D0h+phAlgorithm]; hAlgorithm
0x1800945ba  test    rcx, rcx
0x1800945bd  jz      short loc_1800945D6
0x1800945bf  xor     edx, edx; dwFlags
0x1800945c1  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800945c8  nop     dword ptr [rax+rax+00h]
0x1800945cd  mov     ebx, [rsp+2D0h+var_290]
0x1800945d1  mov     [rsp+2D0h+phAlgorithm], r12
0x1800945d6  lea     rcx, [rsp+2D0h+var_268]; this
0x1800945db  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x1800945e0  mov     eax, ebx
0x1800945e2  mov     rcx, [rbp+1D0h+var_40]
0x1800945e9  xor     rcx, rsp; StackCookie
0x1800945ec  call    __security_check_cookie
0x1800945f1  add     rsp, 2A0h
0x1800945f8  pop     r15
0x1800945fa  pop     r14
0x1800945fc  pop     r12
0x1800945fe  pop     rdi
0x1800945ff  pop     rsi
0x180094600  pop     rbx
0x180094601  pop     rbp
0x180094602  retn
```
