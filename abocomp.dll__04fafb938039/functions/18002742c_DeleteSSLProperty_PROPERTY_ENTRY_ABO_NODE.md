# DeleteSSLProperty(PROPERTY_ENTRY *,ABO_NODE *)

- ea: `0x18002742c`
- end: `0x180027874`
- name: `?DeleteSSLProperty@@YAJPEAVPROPERTY_ENTRY@@PEAVABO_NODE@@@Z`
- size: `1096`
- prototype: `__int64 __fastcall(struct PROPERTY_ENTRY *, struct ABO_NODE *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task`

## callers

- `0x180015500`

## callees

- `0x180001f90`
- `0x180002990`
- `0x18000341a`
- `0x180003460`
- `0x18002735c`
- `0x1800273c4`
- `0x180027404`
- `0x18002742c`
- `0x18002787c`
- `0x180028654`
- `0x180028ab4`

## import_xrefs

- `HTTPAPI!HttpTerminate` at `0x180027839`
- `HTTPAPI!HttpTerminate` at `0x180027839`
- `HTTPAPI!HttpSetServiceConfiguration` at `0x180027786`
- `HTTPAPI!HttpSetServiceConfiguration` at `0x180027786`
- `HTTPAPI!HttpInitialize` at `0x1800274dc`
- `HTTPAPI!HttpInitialize` at `0x1800274dc`
- `HTTPAPI!HttpDeleteServiceConfiguration` at `0x180027765`
- `HTTPAPI!HttpDeleteServiceConfiguration` at `0x180027765`
- `HTTPAPI!HttpQueryServiceConfiguration` at `0x1800275a7`
- `HTTPAPI!HttpQueryServiceConfiguration` at `0x180027628`
- `HTTPAPI!HttpQueryServiceConfiguration` at `0x1800275a7`
- `HTTPAPI!HttpQueryServiceConfiguration` at `0x180027628`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800275df`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800275df`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800275f5`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180027639`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800276a4`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800275f5`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180027639`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800276a4`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x1800275c6`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x1800275c6`

## string_xrefs

- `0x1800277d3`: `HttpDeleteServiceConfiguration failed err=%X\n`
- `0x1800277e6`: `HttpQueryServiceConfiguration failed err=%X\n`
- `0x1800277c0`: `HttpSetServiceConfiguration failed err=%X\n`

## pseudocode

```c
__int64 __fastcall DeleteSSLProperty(struct PROPERTY_ENTRY *a1, struct ABO_NODE *a2)
{
  struct addrinfoW **v3; // rsi
  unsigned int v4; // r12d
  BUFFER *v6; // rdi
  unsigned int v7; // edx
  signed int v8; // eax
  signed int SecureBindings; // ebx
  int v10; // r15d
  ULONG OutputLength; // r13d
  __int64 v12; // r14
  signed int v13; // eax
  BUFFER *v14; // rax
  BUFFER *v15; // rax
  void *pOutput; // rax
  _DWORD *Ptr; // rax
  _DWORD *v18; // rax
  signed int v19; // eax
  signed int v20; // eax
  ULONG pReturnLength; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v23; // [rsp+44h] [rbp-BCh] BYREF
  struct addrinfoW **Block; // [rsp+48h] [rbp-B8h] BYREF
  __int128 pInput; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v26; // [rsp+60h] [rbp-A0h]
  struct PROPERTY_ENTRY *v27; // [rsp+68h] [rbp-98h]
  struct addrinfoW *v28; // [rsp+70h] [rbp-90h] BYREF
  int v29; // [rsp+78h] [rbp-88h] BYREF
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  int v33; // [rsp+A0h] [rbp-60h]
  int v34; // [rsp+A4h] [rbp-5Ch]
  int v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  __int64 v37; // [rsp+B8h] [rbp-48h]
  int v38; // [rsp+C0h] [rbp-40h]
  struct addrinfoW *pConfigInformation; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v40[16]; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v41; // [rsp+E8h] [rbp-18h]
  _BYTE v42[240]; // [rsp+130h] [rbp+30h] BYREF

  v27 = a1;
  v3 = 0;
  v4 = 0;
  Block = 0;
  v23 = 0;
  SSL_DATA::SSL_DATA((SSL_DATA *)v42);
  v26 = 0;
  pReturnLength = 0;
  pConfigInformation = 0;
  v6 = 0;
  pInput = 0;
  memset_0(v40, 0, 0x50u);
  v28 = 0;
  memset_0(&v29, 0, 0x50u);
  if ( a1 && a2 )
  {
    v8 = HttpInitialize(g_Version, 2u, 0);
    SecureBindings = v8;
    if ( v8 > 0 )
      SecureBindings = (unsigned __int16)v8 | 0x80070000;
    if ( SecureBindings < 0 )
    {
      ABO_MAPPER_LOG::WriteLogEntry(g_pAboLog, L"HttpInitialize failed err=%X\n", (unsigned int)SecureBindings);
      goto LABEL_60;
    }
    v10 = 1;
    SecureBindings = GetSecureBindings(a2, &Block, &v23);
    if ( SecureBindings < 0 || (SecureBindings = GetSSLProperties(a2, (struct SSL_DATA *)v42), SecureBindings < 0) )
    {
      v3 = Block;
      v4 = v23;
    }
    else
    {
      v4 = v23;
      OutputLength = 0;
      v3 = Block;
      v12 = 0;
      if ( v23 )
      {
        while ( 1 )
        {
          Block = (struct addrinfoW **)v3[v12];
          pInput = 0;
          v26 = 0;
          *((_QWORD *)&pInput + 1) = Block[4];
          v13 = HttpQueryServiceConfiguration(
                  0,
                  HttpServiceConfigSSLCertInfo,
                  &pInput,
                  0x18u,
                  0,
                  OutputLength,
                  &pReturnLength,
                  0);
          if ( v13 == 122 )
          {
            v14 = (BUFFER *)operator new(0x30u);
            if ( !v14 )
            {
              v6 = 0;
LABEL_41:
              SecureBindings = -2147024888;
              goto LABEL_54;
            }
            v15 = BUFFER::BUFFER(v14);
            v6 = v15;
            if ( !v15 || !BUFFER::Resize(v15, pReturnLength) )
              goto LABEL_41;
            OutputLength = pReturnLength;
            pOutput = BUFFER::QueryPtr(v6);
            v13 = HttpQueryServiceConfiguration(
                    0,
                    HttpServiceConfigSSLCertInfo,
                    &pInput,
                    0x18u,
                    pOutput,
                    OutputLength,
                    &pReturnLength,
                    0);
          }
          if ( v13 )
            break;
          Ptr = BUFFER::QueryPtr(v6);
          v28 = Block[4];
          v31 = xmmword_180034F38;
          v29 = Ptr[2];
          v30 = *((_QWORD *)Ptr + 2);
          v32 = *((_QWORD *)Ptr + 5);
          v33 = Ptr[12];
          v34 = Ptr[13];
          v35 = Ptr[14];
          v36 = *((_QWORD *)Ptr + 8);
          v37 = *((_QWORD *)Ptr + 9);
          v38 = Ptr[20];
          v18 = BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)v27 + 16));
          switch ( *v18 )
          {
            case 0x870:
              v33 = 0;
              break;
            case 0x871:
              v34 = 0;
              break;
            case 0x872:
              v35 = 0;
              break;
            case 0x1582:
              v30 = 0;
              v29 = 0;
              break;
            case 0x1587:
              v32 = 0;
              break;
            case 0x1588:
              v36 = 0;
              break;
            case 0x158D:
              v37 = 0;
              break;
            case 0x158F:
              v38 &= ~1u;
              break;
            case 0x1591:
              v38 &= ~2u;
              break;
          }
          pConfigInformation = Block[4];
          v41 = xmmword_180034F38;
          v19 = HttpDeleteServiceConfiguration(0, HttpServiceConfigSSLCertInfo, &pConfigInformation, 0x58u, 0);
          if ( v19 )
          {
            if ( v19 > 0 )
              v19 = (unsigned __int16)v19 | 0x80070000;
            ABO_MAPPER_LOG::WriteLogEntry(
              g_pAboLog,
              L"HttpDeleteServiceConfiguration failed err=%X\n",
              (unsigned int)v19);
            goto LABEL_54;
          }
          v20 = HttpSetServiceConfiguration(0, HttpServiceConfigSSLCertInfo, &v28, 0x58u, 0);
          if ( v20 )
          {
            if ( v20 > 0 )
              v20 = (unsigned __int16)v20 | 0x80070000;
            ABO_MAPPER_LOG::WriteLogEntry(g_pAboLog, L"HttpSetServiceConfiguration failed err=%X\n", (unsigned int)v20);
            goto LABEL_54;
          }
          if ( v6 )
          {
            BUFFER::`scalar deleting destructor'(v6, v7);
            v6 = 0;
          }
          v12 = (unsigned int)(v12 + 1);
          if ( (unsigned int)v12 >= v4 )
            goto LABEL_54;
        }
        if ( v13 > 0 )
          v13 = (unsigned __int16)v13 | 0x80070000;
        ABO_MAPPER_LOG::WriteLogEntry(g_pAboLog, L"HttpQueryServiceConfiguration failed err=%X\n", (unsigned int)v13);
      }
    }
  }
  else
  {
    v10 = 0;
    SecureBindings = -2147024809;
  }
LABEL_54:
  if ( v3 )
    FreeSecureBindings(v3, v4);
  if ( v6 )
    BUFFER::`scalar deleting destructor'(v6, v7);
  if ( v10 )
    HttpTerminate(2u, 0);
LABEL_60:
  SSL_DATA::~SSL_DATA((SSL_DATA *)v42);
  return (unsigned int)SecureBindings;
}

```

## disassembly

```asm
0x18002742c  mov     [rsp-8+arg_10], rbx
0x180027431  push    rbp
0x180027432  push    rsi
0x180027433  push    rdi
0x180027434  push    r12
0x180027436  push    r13
0x180027438  push    r14
0x18002743a  push    r15
0x18002743c  lea     rbp, [rsp-130h]
0x180027444  sub     rsp, 230h
0x18002744b  mov     rax, cs:__security_cookie
0x180027452  xor     rax, rsp
0x180027455  mov     [rbp+160h+var_40], rax
0x18002745c  mov     rbx, rcx
0x18002745f  mov     [rsp+260h+var_1F8], rcx
0x180027464  xor     esi, esi
0x180027466  lea     rcx, [rbp+160h+var_130]; this
0x18002746a  xor     r12d, r12d
0x18002746d  mov     [rsp+260h+Block], rsi
0x180027472  mov     [rsp+260h+var_21C], r12d
0x180027477  mov     r14, rdx
0x18002747a  call    ??0SSL_DATA@@QEAA@XZ; SSL_DATA::SSL_DATA(void)
0x18002747f  xor     eax, eax
0x180027481  lea     r15d, [rsi+50h]
0x180027485  xorps   xmm0, xmm0
0x180027488  mov     [rsp+260h+var_200], rax
0x18002748d  mov     r8d, r15d; Size
0x180027490  mov     [rsp+260h+var_220], eax
0x180027494  xor     edx, edx; Val
0x180027496  mov     [rbp+160h+pConfigInformation], rax
0x18002749a  lea     rcx, [rbp+160h+var_188]; void *
0x18002749e  xor     edi, edi
0x1800274a0  movups  [rsp+260h+pInput], xmm0
0x1800274a5  call    memset_0
0x1800274aa  mov     r8d, r15d; Size
0x1800274ad  mov     [rsp+260h+var_1F0], rsi
0x1800274b2  xor     edx, edx; Val
0x1800274b4  lea     rcx, [rsp+260h+var_1E8]; void *
0x1800274b9  call    memset_0
0x1800274be  test    rbx, rbx
0x1800274c1  jz      loc_18002780A
0x1800274c7  test    r14, r14
0x1800274ca  jz      loc_18002780A
0x1800274d0  mov     ecx, dword ptr cs:?g_Version@@3U_HTTPAPI_VERSION@@A.HttpApiMajorVersion; Version
0x1800274d6  lea     edx, [rsi+2]; Flags
0x1800274d9  xor     r8d, r8d; pReserved
0x1800274dc  call    cs:__imp_HttpInitialize
0x1800274e2  mov     ebx, eax
0x1800274e4  test    eax, eax
0x1800274e6  jle     short loc_1800274F1
0x1800274e8  movzx   ebx, ax
0x1800274eb  or      ebx, 80070000h
0x1800274f1  test    ebx, ebx
0x1800274f3  jns     short loc_180027510
0x1800274f5  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x1800274fc  lea     rdx, aHttpinitialize; "HttpInitialize failed err=%X\n"
0x180027503  mov     r8d, ebx
0x180027506  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x18002750b  jmp     loc_18002783F
0x180027510  lea     r8, [rsp+260h+var_21C]; unsigned int *
0x180027515  mov     rcx, r14; struct ABO_NODE *
0x180027518  lea     rdx, [rsp+260h+Block]; struct addrinfoW ***
0x18002751d  mov     r15d, 1
0x180027523  call    ?GetSecureBindings@@YAJPEAVABO_NODE@@PEAPEAPEAUaddrinfoW@@PEAK@Z; GetSecureBindings(ABO_NODE *,addrinfoW * * *,ulong *)
0x180027528  mov     ebx, eax
0x18002752a  test    eax, eax
0x18002752c  js      loc_1800277FE
0x180027532  lea     rdx, [rbp+160h+var_130]; struct SSL_DATA *
0x180027536  mov     rcx, r14; struct ABO_NODE *
0x180027539  call    ?GetSSLProperties@@YAJPEAVABO_NODE@@PEAUSSL_DATA@@@Z; GetSSLProperties(ABO_NODE *,SSL_DATA *)
0x18002753e  mov     ebx, eax
0x180027540  test    eax, eax
0x180027542  js      loc_1800277FE
0x180027548  mov     r12d, [rsp+260h+var_21C]
0x18002754d  xor     r13d, r13d
0x180027550  mov     rsi, [rsp+260h+Block]
0x180027555  xor     r14d, r14d
0x180027558  test    r12d, r12d
0x18002755b  jz      loc_180027812
0x180027561  mov     rax, [rsi+r14*8]
0x180027565  lea     r8, [rsp+260h+pInput]; pInput
0x18002756a  xor     ecx, ecx; ServiceHandle
0x18002756c  mov     [rsp+260h+Block], rax
0x180027571  mov     [rsp+260h+pOverlapped], rcx; pOverlapped
0x180027576  xorps   xmm0, xmm0
0x180027579  movups  [rsp+260h+pInput], xmm0
0x18002757e  mov     [rsp+260h+var_200], rcx
0x180027583  mov     edx, r15d; ConfigId
0x180027586  mov     rax, [rax+20h]
0x18002758a  lea     r9d, [rcx+18h]; InputLength
0x18002758e  mov     qword ptr [rsp+260h+pInput+8], rax
0x180027593  lea     rax, [rsp+260h+var_220]
0x180027598  mov     [rsp+260h+pReturnLength], rax; pReturnLength
0x18002759d  mov     [rsp+260h+OutputLength], r13d; OutputLength
0x1800275a2  mov     [rsp+260h+pOutput], rcx; pOutput
0x1800275a7  call    cs:__imp_HttpQueryServiceConfiguration
0x1800275ad  cmp     eax, 7Ah ; 'z'
0x1800275b0  jnz     short loc_18002762E
0x1800275b2  lea     ecx, [rax-4Ah]; Size
0x1800275b5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800275ba  test    rax, rax
0x1800275bd  jz      loc_1800277AD
0x1800275c3  mov     rcx, rax
0x1800275c6  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x1800275cc  mov     rdi, rax
0x1800275cf  test    rax, rax
0x1800275d2  jz      loc_1800277AF
0x1800275d8  mov     edx, [rsp+260h+var_220]
0x1800275dc  mov     rcx, rax
0x1800275df  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800275e5  test    al, al
0x1800275e7  jz      loc_1800277AF
0x1800275ed  mov     r13d, [rsp+260h+var_220]
0x1800275f2  mov     rcx, rdi
0x1800275f5  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800275fb  mov     [rsp+260h+pOverlapped], 0; pOverlapped
0x180027604  lea     rcx, [rsp+260h+var_220]
0x180027609  mov     [rsp+260h+pReturnLength], rcx; pReturnLength
0x18002760e  lea     r8, [rsp+260h+pInput]; pInput
0x180027613  mov     [rsp+260h+OutputLength], r13d; OutputLength
0x180027618  xor     ecx, ecx; ServiceHandle
0x18002761a  mov     r9d, 18h; InputLength
0x180027620  mov     [rsp+260h+pOutput], rax; pOutput
0x180027625  mov     edx, r15d; ConfigId
0x180027628  call    cs:__imp_HttpQueryServiceConfiguration
0x18002762e  test    eax, eax
0x180027630  jnz     loc_1800277DC
0x180027636  mov     rcx, rdi
0x180027639  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002763f  movups  xmm0, cs:xmmword_180034F38
0x180027646  mov     rcx, [rsp+260h+Block]
0x18002764b  mov     rdx, rax
0x18002764e  mov     rcx, [rcx+20h]
0x180027652  mov     [rsp+260h+var_1F0], rcx
0x180027657  movdqu  [rbp+160h+var_1D8], xmm0
0x18002765c  mov     ecx, [rax+8]
0x18002765f  mov     [rsp+260h+var_1E8], ecx
0x180027663  mov     rcx, [rax+10h]
0x180027667  mov     [rbp+160h+var_1E0], rcx
0x18002766b  mov     rcx, [rax+28h]
0x18002766f  mov     [rbp+160h+var_1C8], rcx
0x180027673  mov     ecx, [rax+30h]
0x180027676  mov     [rbp+160h+var_1C0], ecx
0x180027679  mov     ecx, [rax+34h]
0x18002767c  mov     [rbp+160h+var_1BC], ecx
0x18002767f  mov     eax, [rax+38h]
0x180027682  mov     rcx, [rsp+260h+var_1F8]
0x180027687  mov     [rbp+160h+var_1B8], eax
0x18002768a  add     rcx, 10h
0x18002768e  mov     rax, [rdx+40h]
0x180027692  mov     [rbp+160h+var_1B0], rax
0x180027696  mov     rax, [rdx+48h]
0x18002769a  mov     [rbp+160h+var_1A8], rax
0x18002769e  mov     eax, [rdx+50h]
0x1800276a1  mov     [rbp+160h+var_1A0], eax
0x1800276a4  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800276aa  mov     edx, [rax]
0x1800276ac  sub     edx, 870h
0x1800276b2  jz      short loc_18002772D
0x1800276b4  sub     edx, r15d
0x1800276b7  jz      short loc_180027724
0x1800276b9  sub     edx, r15d
0x1800276bc  jz      short loc_18002771B
0x1800276be  sub     edx, 0D10h
0x1800276c4  jz      short loc_180027709
0x1800276c6  sub     edx, 5
0x1800276c9  jz      short loc_1800276FF
0x1800276cb  sub     edx, r15d
0x1800276ce  jz      short loc_1800276F5
0x1800276d0  sub     edx, 5
0x1800276d3  jz      short loc_1800276EB
0x1800276d5  sub     edx, 2
0x1800276d8  jz      short loc_1800276E5
0x1800276da  cmp     edx, 2
0x1800276dd  jnz     short loc_180027734
0x1800276df  and     [rbp+160h+var_1A0], 0FFFFFFFDh
0x1800276e3  jmp     short loc_180027734
0x1800276e5  and     [rbp+160h+var_1A0], 0FFFFFFFEh
0x1800276e9  jmp     short loc_180027734
0x1800276eb  mov     [rbp+160h+var_1A8], 0
0x1800276f3  jmp     short loc_180027734
0x1800276f5  mov     [rbp+160h+var_1B0], 0
0x1800276fd  jmp     short loc_180027734
0x1800276ff  mov     [rbp+160h+var_1C8], 0
0x180027707  jmp     short loc_180027734
0x180027709  mov     [rbp+160h+var_1E0], 0
0x180027711  mov     [rsp+260h+var_1E8], 0
0x180027719  jmp     short loc_180027734
0x18002771b  mov     [rbp+160h+var_1B8], 0
0x180027722  jmp     short loc_180027734
0x180027724  mov     [rbp+160h+var_1BC], 0
0x18002772b  jmp     short loc_180027734
0x18002772d  mov     [rbp+160h+var_1C0], 0
0x180027734  movups  xmm0, cs:xmmword_180034F38
0x18002773b  mov     rax, [rsp+260h+Block]
0x180027740  lea     r8, [rbp+160h+pConfigInformation]; pConfigInformation
0x180027744  mov     r9d, 58h ; 'X'; ConfigInformationLength
0x18002774a  mov     [rsp+260h+pOutput], 0; pOverlapped
0x180027753  mov     edx, r15d; ConfigId
0x180027756  xor     ecx, ecx; ServiceHandle
0x180027758  mov     rax, [rax+20h]
0x18002775c  mov     [rbp+160h+pConfigInformation], rax
0x180027760  movdqu  [rbp+160h+var_178], xmm0
0x180027765  call    cs:__imp_HttpDeleteServiceConfiguration
0x18002776b  test    eax, eax
0x18002776d  jnz     short loc_1800277C9
0x18002776f  lea     r9d, [rax+58h]; ConfigInformationLength
0x180027773  mov     [rsp+260h+pOutput], 0; pOverlapped
0x18002777c  lea     r8, [rsp+260h+var_1F0]; pConfigInformation
0x180027781  mov     edx, r15d; ConfigId
0x180027784  xor     ecx, ecx; ServiceHandle
0x180027786  call    cs:__imp_HttpSetServiceConfiguration
0x18002778c  test    eax, eax
0x18002778e  jnz     short loc_1800277B6
0x180027790  test    rdi, rdi
0x180027793  jz      short loc_18002779F
0x180027795  mov     rcx, rdi; this
0x180027798  call    ??_GBUFFER@@QEAAPEAXI@Z; BUFFER::`scalar deleting destructor'(uint)
0x18002779d  xor     edi, edi
0x18002779f  add     r14d, r15d
0x1800277a2  cmp     r14d, r12d
0x1800277a5  jb      loc_180027561
0x1800277ab  jmp     short loc_180027812
0x1800277ad  xor     edi, edi
0x1800277af  mov     ebx, 80070008h
0x1800277b4  jmp     short loc_180027812
0x1800277b6  jle     short loc_1800277C0
0x1800277b8  movzx   eax, ax
0x1800277bb  or      eax, 80070000h
0x1800277c0  lea     rdx, aHttpsetservice; "HttpSetServiceConfiguration failed err="...
0x1800277c7  jmp     short loc_1800277ED
0x1800277c9  jle     short loc_1800277D3
0x1800277cb  movzx   eax, ax
0x1800277ce  or      eax, 80070000h
0x1800277d3  lea     rdx, aHttpdeleteserv; "HttpDeleteServiceConfiguration failed e"...
0x1800277da  jmp     short loc_1800277ED
0x1800277dc  jle     short loc_1800277E6
0x1800277de  movzx   eax, ax
0x1800277e1  or      eax, 80070000h
0x1800277e6  lea     rdx, aHttpqueryservi; "HttpQueryServiceConfiguration failed er"...
0x1800277ed  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x1800277f4  mov     r8d, eax
0x1800277f7  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x1800277fc  jmp     short loc_180027812
0x1800277fe  mov     rsi, [rsp+260h+Block]
0x180027803  mov     r12d, [rsp+260h+var_21C]
0x180027808  jmp     short loc_180027812
0x18002780a  xor     r15d, r15d
0x18002780d  mov     ebx, 80070057h
0x180027812  test    rsi, rsi
0x180027815  jz      short loc_180027822
0x180027817  mov     edx, r12d; unsigned int
0x18002781a  mov     rcx, rsi; Block
0x18002781d  call    ?FreeSecureBindings@@YAJPEAPEAUaddrinfoW@@K@Z; FreeSecureBindings(addrinfoW * *,ulong)
0x180027822  test    rdi, rdi
0x180027825  jz      short loc_18002782F
0x180027827  mov     rcx, rdi; this
0x18002782a  call    ??_GBUFFER@@QEAAPEAXI@Z; BUFFER::`scalar deleting destructor'(uint)
0x18002782f  test    r15d, r15d
0x180027832  jz      short loc_18002783F
0x180027834  xor     edx, edx; pReserved
0x180027836  lea     ecx, [rdx+2]; Flags
0x180027839  call    cs:__imp_HttpTerminate
0x18002783f  lea     rcx, [rbp+160h+var_130]; this
0x180027843  call    ??1SSL_DATA@@QEAA@XZ; SSL_DATA::~SSL_DATA(void)
0x180027848  mov     eax, ebx
0x18002784a  mov     rcx, [rbp+160h+var_40]
0x180027851  xor     rcx, rsp; StackCookie
0x180027854  call    __security_check_cookie
0x180027859  mov     rbx, [rsp+260h+arg_10]
0x180027861  add     rsp, 230h
0x180027868  pop     r15
0x18002786a  pop     r14
0x18002786c  pop     r13
0x18002786e  pop     r12
0x180027870  pop     rdi
0x180027871  pop     rsi
0x180027872  pop     rbp
0x180027873  retn
```
