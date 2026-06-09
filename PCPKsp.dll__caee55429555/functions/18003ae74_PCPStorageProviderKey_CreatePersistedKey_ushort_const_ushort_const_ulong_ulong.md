# PCPStorageProviderKey::CreatePersistedKey(ushort const *,ushort const *,ulong,ulong)

- ea: `0x18003ae74`
- end: `0x18003b383`
- name: `?CreatePersistedKey@PCPStorageProviderKey@@QEAAJPEBG0KK@Z`
- size: `1295`
- prototype: `__int64 __usercall@<rax>(PCPStorageProviderKey *__hidden this@<rcx>, wchar_t *String1@<rdx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, unsigned int)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops`

## callers

- `0x18003a340`

## callees

- `0x1800113f0`
- `0x1800138e0`
- `0x180015660`
- `0x1800157c0`
- `0x180018e20`
- `0x180021b7c`
- `0x180026b90`
- `0x1800389c0`
- `0x18003ae74`
- `0x18003bad0`
- `0x18003bbc4`
- `0x18003cce0`
- `0x18003d35c`
- `0x1800764d0`
- `0x180076998`
- `0x18007704c`
- `0x1800c2ce0`

## string_xrefs

- `0x18003aeb9`: `PCPStorageProviderKey::CreatePersistedKey`
- `0x18003b2b1`: `Key exists, OverwriteKey is FALSE.`
- `0x18003b2fb`: `Marking old container for delete.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall PCPStorageProviderKey::CreatePersistedKey(
        PCPStorageProviderKey *this,
        wchar_t *String1,
        const unsigned __int16 *a3,
        int a4,
        char a5)
{
  unsigned __int8 v9; // r12
  unsigned __int16 *v10; // rsi
  const wchar_t *v11; // rbx
  const unsigned __int16 *v12; // rdx
  int KeyContainerName; // ebx
  void **v15; // rcx
  __int64 v16; // rdx
  unsigned __int16 *v17; // rax
  int KeyPair; // eax
  const unsigned __int16 *v19; // rdx
  void **v20; // rcx
  unsigned __int64 v21; // r11
  unsigned __int64 v22; // rbx
  unsigned __int64 v23; // rcx
  unsigned __int64 v24; // rax
  void *v25; // rax
  __int64 v26; // rbx
  unsigned __int16 *v27; // rax
  int v28; // r9d
  int v29; // ecx
  unsigned __int16 *v30; // rax
  int v31; // [rsp+30h] [rbp-278h] BYREF
  unsigned __int64 v32; // [rsp+38h] [rbp-270h] BYREF
  int *v33[4]; // [rsp+40h] [rbp-268h] BYREF
  unsigned __int16 v34; // [rsp+60h] [rbp-248h] BYREF
  _BYTE v35[526]; // [rsp+62h] [rbp-246h] BYREF

  v31 = 0;
  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v33, L"PCPStorageProviderKey::CreatePersistedKey", &v31);
  v9 = (a5 & 0x20) != 0;
  v34 = 0;
  memset_0(v35, 0, 0x206u);
  v32 = 0;
  if ( a4 )
  {
    KspDebugProvider::TraceLoggingError("No support for legacy keys.");
    goto LABEL_14;
  }
  v10 = 0;
  v11 = L"RSA";
  if ( wcscmp_0(String1, L"RSA") )
  {
    if ( wcscmp_0(String1, L"RSA_SIGN") )
    {
      v11 = L"ECDSA";
      if ( wcscmp_0(String1, L"ECDSA") )
      {
        if ( wcscmp_0(String1, L"ECDH") )
        {
          if ( !wcscmp_0(String1, L"ECDSA_P256") )
          {
            v10 = L"nistP256";
            goto LABEL_19;
          }
          if ( !wcscmp_0(String1, L"ECDH_P256") )
          {
            v10 = L"nistP256";
          }
          else
          {
            if ( !wcscmp_0(String1, L"ECDSA_P384") )
            {
              v10 = L"nistP384";
              goto LABEL_19;
            }
            if ( !wcscmp_0(String1, L"ECDH_P384") )
            {
              v10 = L"nistP384";
            }
            else
            {
              if ( !wcscmp_0(String1, L"ECDSA_P521") )
              {
                v10 = L"nistP521";
                goto LABEL_19;
              }
              if ( wcscmp_0(String1, L"ECDH_P521") )
              {
                v11 = L"HMAC-SHA256";
                if ( wcscmp_0(String1, L"HMAC-SHA256") )
                {
                  KspDebugProvider::TraceLoggingError("Unknown algorithm type.");
LABEL_14:
                  KeyContainerName = -2146893783;
LABEL_15:
                  v31 = KeyContainerName;
                  goto LABEL_16;
                }
                goto LABEL_19;
              }
              v10 = L"nistP521";
            }
          }
        }
        v11 = L"ECDH";
      }
    }
  }
LABEL_19:
  *((_QWORD *)this + 89) = v11;
  *((_BYTE *)this + 652) = v9;
  if ( *(_DWORD *)(*((_QWORD *)this + 6) + 8LL) )
  {
    if ( !a3 || !*a3 )
      goto LABEL_21;
    if ( (int)StringCchLengthW(a3, 0x104u, &v32) < 0 || (v22 = v32, v23 = v32 + 1, v32 + 1 > v21) )
    {
      KspDebugProvider::TraceLoggingError("Key name too long.");
      KeyContainerName = -2146893785;
      goto LABEL_15;
    }
    v24 = 2 * v23;
    if ( !is_mul_ok(v23, 2u) )
      v24 = -1;
    v25 = operator new[](v24, (const struct std::nothrow_t *)&std::nothrow);
    *((_QWORD *)this + 10) = v25;
    if ( v25 )
    {
      v26 = 2 * v22 + 2;
      memset_0(v25, 0, v26);
      memcpy_s_1(*((void *const *)this + 10), v26, a3, v26);
      KeyContainerName = PCPStorageProviderKey::GenerateKeyContainerName(this);
      v31 = KeyContainerName;
      if ( KeyContainerName < 0 )
        goto LABEL_16;
      if ( (int)PCPStorageProvider::GetContainerNameFromKeyName(*((PCPStorageProvider **)this + 6), a3, v9, 0, &v34) < 0 )
        goto LABEL_21;
      if ( a5 >= 0 )
      {
        KspDebugProvider::TraceLoggingError("Key exists, OverwriteKey is FALSE.");
        KeyContainerName = -2146893809;
        goto LABEL_15;
      }
      v27 = &v34;
      do
      {
        v28 = *(unsigned __int16 *)((char *)v27
                                  + (PCPStorageProviderKey *)((char *)this + 88)
                                  - (PCPStorageProviderKey *)&v34);
        v29 = *v27 - v28;
        if ( v29 )
          break;
        ++v27;
      }
      while ( v28 );
      if ( !v29 )
      {
LABEL_21:
        v15 = (void **)(*((_QWORD *)this + 6) + 136LL);
        if ( *v15
          || (KeyContainerName = ProviderOpenAlgorithmProvider(v15, v12, 0),
              v31 = KeyContainerName,
              KeyContainerName >= 0) )
        {
          KeyContainerName = ProviderGenerateKeyPair(
                               *((const unsigned __int16 **)this + 89),
                               *(void **)(*((_QWORD *)this + 6) + 136LL),
                               (void **)this + 96);
          v31 = KeyContainerName;
          if ( KeyContainerName >= 0 )
          {
            if ( v10 )
            {
              v16 = 130;
              v17 = v10;
              do
              {
                if ( !*v17 )
                  break;
                ++v17;
                --v16;
              }
              while ( v16 );
              KeyContainerName = v16 == 0 ? 0x80070057 : 0;
              v31 = KeyContainerName;
              if ( v16 )
              {
                KeyPair = PCPStorageProviderKey::SetProperty(
                            (__int64)this,
                            0x20u,
                            v10,
                            v16 != 0 ? 2 * (130 - v16) + 2 : 2,
                            0);
                KeyContainerName = KeyPair;
LABEL_29:
                v31 = KeyPair;
                goto LABEL_16;
              }
            }
          }
        }
        goto LABEL_16;
      }
      KspDebugProvider::TraceLoggingInfo("Marking old container for delete.");
      v30 = (unsigned __int16 *)operator new[](0x208u, (const struct std::nothrow_t *)&std::nothrow);
      *((_QWORD *)this + 76) = v30;
      if ( v30 )
      {
        KeyContainerName = StringCchCopyW(v30, 0x104u, &v34);
        v31 = KeyContainerName;
        if ( KeyContainerName < 0 )
          goto LABEL_16;
        goto LABEL_21;
      }
    }
    KeyContainerName = -2147024888;
    goto LABEL_15;
  }
  KspDebugProvider::TraceLoggingInfo("No TPM present.");
  v20 = (void **)(*((_QWORD *)this + 6) + 136LL);
  if ( *v20
    || (KeyContainerName = ProviderOpenAlgorithmProvider(v20, v19, 0), v31 = KeyContainerName, KeyContainerName >= 0) )
  {
    KeyPair = ProviderGenerateKeyPair(
                *((const unsigned __int16 **)this + 89),
                *(void **)(*((_QWORD *)this + 6) + 136LL),
                (void **)this + 96);
    KeyContainerName = KeyPair;
    goto LABEL_29;
  }
LABEL_16:
  KspFunctionLogger::~KspFunctionLogger(v33);
  return (unsigned int)KeyContainerName;
}

```

## disassembly

```asm
0x18003ae74  mov     [rsp+arg_8], rbx
0x18003ae79  mov     [rsp+arg_18], rsi
0x18003ae7e  push    rdi
0x18003ae7f  push    r12
0x18003ae81  push    r13
0x18003ae83  push    r14
0x18003ae85  push    r15
0x18003ae87  sub     rsp, 280h
0x18003ae8e  mov     rax, cs:__security_cookie
0x18003ae95  xor     rax, rsp
0x18003ae98  mov     [rsp+2A8h+var_38], rax
0x18003aea0  mov     ebx, r9d
0x18003aea3  mov     r15, r8
0x18003aea6  mov     r14, rdx
0x18003aea9  mov     rdi, rcx
0x18003aeac  mov     [rsp+2A8h+var_278], 0
0x18003aeb4  lea     r8, [rsp+2A8h+var_278]; int *
0x18003aeb9  lea     rdx, aPcpstorageprov_1; "PCPStorageProviderKey::CreatePersistedK"...
0x18003aec0  lea     rcx, [rsp+2A8h+var_268]; this
0x18003aec5  call    ??0KspFunctionLogger@@QEAA@QEBGAEBJ@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,long const &)
0x18003aeca  nop
0x18003aecb  mov     r13d, [rsp+2A8h+arg_20]
0x18003aed3  mov     r12d, r13d
0x18003aed6  shr     r12d, 5
0x18003aeda  and     r12b, 1
0x18003aede  xor     eax, eax
0x18003aee0  mov     [rsp+2A8h+var_248], ax
0x18003aee5  xor     edx, edx; Val
0x18003aee7  mov     r8d, 206h; Size
0x18003aeed  lea     rcx, [rsp+2A8h+var_246]; void *
0x18003aef2  call    memset_0
0x18003aef7  mov     [rsp+2A8h+var_270], 0
0x18003af00  test    ebx, ebx
0x18003af02  jnz     loc_18003B19D
0x18003af08  xor     esi, esi
0x18003af0a  lea     rbx, aRsa; "RSA"
0x18003af11  mov     rdx, rbx; String2
0x18003af14  mov     rcx, r14; String1
0x18003af17  call    wcscmp_0
0x18003af1c  test    eax, eax
0x18003af1e  jz      loc_18003B06C
0x18003af24  lea     rdx, aRsaSign; "RSA_SIGN"
0x18003af2b  mov     rcx, r14; String1
0x18003af2e  call    wcscmp_0
0x18003af33  test    eax, eax
0x18003af35  jz      loc_18003B06C
0x18003af3b  lea     rbx, aEcdsa; "ECDSA"
0x18003af42  mov     rdx, rbx; String2
0x18003af45  mov     rcx, r14; String1
0x18003af48  call    wcscmp_0
0x18003af4d  test    eax, eax
0x18003af4f  jz      loc_18003B06C
0x18003af55  lea     rdx, aEcdh; "ECDH"
0x18003af5c  mov     rcx, r14; String1
0x18003af5f  call    wcscmp_0
0x18003af64  test    eax, eax
0x18003af66  jz      loc_18003B065
0x18003af6c  lea     rdx, aEcdsaP256; "ECDSA_P256"
0x18003af73  mov     rcx, r14; String1
0x18003af76  call    wcscmp_0
0x18003af7b  test    eax, eax
0x18003af7d  jz      loc_18003B1A9
0x18003af83  lea     rdx, aEcdhP256; "ECDH_P256"
0x18003af8a  mov     rcx, r14; String1
0x18003af8d  call    wcscmp_0
0x18003af92  test    eax, eax
0x18003af94  jz      loc_18003B05E
0x18003af9a  lea     rdx, aEcdsaP384; "ECDSA_P384"
0x18003afa1  mov     rcx, r14; String1
0x18003afa4  call    wcscmp_0
0x18003afa9  test    eax, eax
0x18003afab  jz      loc_18003B1B5
0x18003afb1  lea     rdx, aEcdhP384; "ECDH_P384"
0x18003afb8  mov     rcx, r14; String1
0x18003afbb  call    wcscmp_0
0x18003afc0  test    eax, eax
0x18003afc2  jz      loc_18003B1C1
0x18003afc8  lea     rdx, aEcdsaP521; "ECDSA_P521"
0x18003afcf  mov     rcx, r14; String1
0x18003afd2  call    wcscmp_0
0x18003afd7  test    eax, eax
0x18003afd9  jz      loc_18003B1CD
0x18003afdf  lea     rdx, aEcdhP521; "ECDH_P521"
0x18003afe6  mov     rcx, r14; String1
0x18003afe9  call    wcscmp_0
0x18003afee  test    eax, eax
0x18003aff0  jz      loc_18003B1D9
0x18003aff6  lea     rbx, aHmacSha256; "HMAC-SHA256"
0x18003affd  mov     rdx, rbx; String2
0x18003b000  mov     rcx, r14; String1
0x18003b003  call    wcscmp_0
0x18003b008  xor     r14d, r14d
0x18003b00b  test    eax, eax
0x18003b00d  jz      short loc_18003B06F
0x18003b00f  lea     rcx, aUnknownAlgorit_0; "Unknown algorithm type."
0x18003b016  call    ?TraceLoggingError@KspDebugProvider@@SAXPEBDZZ; KspDebugProvider::TraceLoggingError(char const *,...)
0x18003b01b  mov     ebx, 80090029h
0x18003b020  mov     [rsp+2A8h+var_278], ebx
0x18003b024  lea     rcx, [rsp+2A8h+var_268]; this
0x18003b029  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18003b02e  mov     eax, ebx
0x18003b030  mov     rcx, [rsp+2A8h+var_38]
0x18003b038  xor     rcx, rsp; StackCookie
0x18003b03b  call    __security_check_cookie
0x18003b040  lea     r11, [rsp+2A8h+var_28]
0x18003b048  mov     rbx, [r11+38h]
0x18003b04c  mov     rsi, [r11+48h]
0x18003b050  mov     rsp, r11
0x18003b053  pop     r15
0x18003b055  pop     r14
0x18003b057  pop     r13
0x18003b059  pop     r12
0x18003b05b  pop     rdi
0x18003b05c  retn
0x18003b05e  lea     rsi, aNistp256; "nistP256"
0x18003b065  lea     rbx, aEcdh; "ECDH"
0x18003b06c  xor     r14d, r14d
0x18003b06f  mov     [rdi+2C8h], rbx
0x18003b076  mov     [rdi+28Ch], r12b
0x18003b07d  mov     rax, [rdi+30h]
0x18003b081  cmp     [rax+8], r14d
0x18003b085  jz      loc_18003B149
0x18003b08b  test    r15, r15
0x18003b08e  jnz     loc_18003B1E5
0x18003b094  mov     rcx, [rdi+30h]
0x18003b098  add     rcx, 88h; void **
0x18003b09f  cmp     [rcx], r14
0x18003b0a2  jz      loc_18003B35F
0x18003b0a8  lea     r8, [rdi+300h]; void **
0x18003b0af  mov     rdx, [rdi+30h]
0x18003b0b3  mov     rdx, [rdx+88h]; void *
0x18003b0ba  mov     rcx, [rdi+2C8h]; unsigned __int16 *
0x18003b0c1  call    ?ProviderGenerateKeyPair@@YAJPEBGPEAXPEAPEAX@Z; ProviderGenerateKeyPair(ushort const *,void *,void * *)
0x18003b0c6  mov     ebx, eax
0x18003b0c8  mov     [rsp+2A8h+var_278], eax
0x18003b0cc  test    eax, eax
0x18003b0ce  js      loc_18003B024
0x18003b0d4  test    rsi, rsi
0x18003b0d7  jz      loc_18003B024
0x18003b0dd  mov     r8d, 82h
0x18003b0e3  mov     edx, r8d
0x18003b0e6  mov     rax, rsi
0x18003b0e9  cmp     [rax], r14w
0x18003b0ed  jz      short loc_18003B0F9
0x18003b0ef  add     rax, 2
0x18003b0f3  sub     rdx, 1
0x18003b0f7  jnz     short loc_18003B0E9
0x18003b0f9  mov     rax, rdx
0x18003b0fc  neg     rax
0x18003b0ff  sbb     ebx, ebx
0x18003b101  not     ebx
0x18003b103  and     ebx, 80070057h
0x18003b109  mov     [rsp+2A8h+var_278], ebx
0x18003b10d  test    rdx, rdx
0x18003b110  jz      loc_18003B024
0x18003b116  sub     r8d, edx
0x18003b119  add     r8d, r8d
0x18003b11c  neg     rdx
0x18003b11f  sbb     r9d, r9d
0x18003b122  and     r9d, r8d
0x18003b125  add     r9d, 2
0x18003b129  mov     dword ptr [rsp+2A8h+var_288], r14d
0x18003b12e  mov     r8, rsi
0x18003b131  mov     edx, 20h ; ' '
0x18003b136  mov     rcx, rdi
0x18003b139  call    ?SetProperty@PCPStorageProviderKey@@QEAAJW4KspProp@@PEAEKK@Z; PCPStorageProviderKey::SetProperty(KspProp,uchar *,ulong,ulong)
0x18003b13e  mov     ebx, eax
0x18003b140  mov     [rsp+2A8h+var_278], eax
0x18003b144  jmp     loc_18003B024
0x18003b149  lea     rcx, aNoTpmPresent; "No TPM present."
0x18003b150  call    ?TraceLoggingInfo@KspDebugProvider@@SAXPEBDZZ; KspDebugProvider::TraceLoggingInfo(char const *,...)
0x18003b155  mov     rcx, [rdi+30h]
0x18003b159  add     rcx, 88h; void **
0x18003b160  cmp     [rcx], r14
0x18003b163  jnz     short loc_18003B17B
0x18003b165  xor     r8d, r8d; unsigned int
0x18003b168  call    ?ProviderOpenAlgorithmProvider@@YAJPEAPEAXPEBGK@Z; ProviderOpenAlgorithmProvider(void * *,ushort const *,ulong)
0x18003b16d  mov     ebx, eax
0x18003b16f  mov     [rsp+2A8h+var_278], eax
0x18003b173  test    eax, eax
0x18003b175  js      loc_18003B024
0x18003b17b  lea     r8, [rdi+300h]; void **
0x18003b182  mov     rdx, [rdi+30h]
0x18003b186  mov     rdx, [rdx+88h]; void *
0x18003b18d  mov     rcx, [rdi+2C8h]; unsigned __int16 *
0x18003b194  call    ?ProviderGenerateKeyPair@@YAJPEBGPEAXPEAPEAX@Z; ProviderGenerateKeyPair(ushort const *,void *,void * *)
0x18003b199  mov     ebx, eax
0x18003b19b  jmp     short loc_18003B140
0x18003b19d  lea     rcx, aNoSupportForLe; "No support for legacy keys."
0x18003b1a4  jmp     loc_18003B016
0x18003b1a9  lea     rsi, aNistp256; "nistP256"
0x18003b1b0  jmp     loc_18003B06C
0x18003b1b5  lea     rsi, aNistp384; "nistP384"
0x18003b1bc  jmp     loc_18003B06C
0x18003b1c1  lea     rsi, aNistp384; "nistP384"
0x18003b1c8  jmp     loc_18003B065
0x18003b1cd  lea     rsi, aNistp521; "nistP521"
0x18003b1d4  jmp     loc_18003B06C
0x18003b1d9  lea     rsi, aNistp521; "nistP521"
0x18003b1e0  jmp     loc_18003B065
0x18003b1e5  cmp     [r15], r14w
0x18003b1e9  jz      loc_18003B094
0x18003b1ef  lea     r8, [rsp+2A8h+var_270]; unsigned __int64 *
0x18003b1f4  mov     r11d, 104h
0x18003b1fa  mov     edx, r11d; unsigned __int64
0x18003b1fd  mov     rcx, r15; unsigned __int16 *
0x18003b200  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18003b205  test    eax, eax
0x18003b207  js      loc_18003B349
0x18003b20d  mov     rbx, [rsp+2A8h+var_270]
0x18003b212  lea     rcx, [rbx+1]
0x18003b216  cmp     rcx, r11
0x18003b219  ja      loc_18003B349
0x18003b21f  mov     eax, 2
0x18003b224  mul     rcx
0x18003b227  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003b22e  cmovb   rax, rcx
0x18003b232  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003b239  mov     rcx, rax; unsigned __int64
0x18003b23c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003b241  mov     [rdi+50h], rax
0x18003b245  test    rax, rax
0x18003b248  jz      short loc_18003B2C7
0x18003b24a  lea     rbx, ds:2[rbx*2]
0x18003b252  mov     r8, rbx; Size
0x18003b255  xor     edx, edx; Val
0x18003b257  mov     rcx, rax; void *
0x18003b25a  call    memset_0
0x18003b25f  mov     r9, rbx; SourceSize
0x18003b262  mov     r8, r15; Source
0x18003b265  mov     rdx, rbx; DestinationSize
0x18003b268  mov     rcx, [rdi+50h]; Destination
0x18003b26c  call    memcpy_s_1
0x18003b271  mov     rcx, rdi; this
0x18003b274  call    ?GenerateKeyContainerName@PCPStorageProviderKey@@IEAAJXZ; PCPStorageProviderKey::GenerateKeyContainerName(void)
0x18003b279  mov     ebx, eax
0x18003b27b  mov     [rsp+2A8h+var_278], eax
0x18003b27f  test    eax, eax
0x18003b281  js      loc_18003B024
0x18003b287  lea     rax, [rsp+2A8h+var_248]
0x18003b28c  mov     [rsp+2A8h+var_288], rax; unsigned __int16 *
0x18003b291  xor     r9d, r9d; bool
0x18003b294  mov     r8b, r12b; unsigned __int8
0x18003b297  mov     rdx, r15; unsigned __int16 *
0x18003b29a  mov     rcx, [rdi+30h]; this
0x18003b29e  call    ?GetContainerNameFromKeyName@PCPStorageProvider@@QEAAJPEBGE_NPEAG@Z; PCPStorageProvider::GetContainerNameFromKeyName(ushort const *,uchar,bool,ushort *)
0x18003b2a3  test    eax, eax
0x18003b2a5  js      loc_18003B094
0x18003b2ab  test    r13b, 80h
0x18003b2af  jnz     short loc_18003B2D1
0x18003b2b1  lea     rcx, aKeyExistsOverw; "Key exists, OverwriteKey is FALSE."
0x18003b2b8  call    ?TraceLoggingError@KspDebugProvider@@SAXPEBDZZ; KspDebugProvider::TraceLoggingError(char const *,...)
0x18003b2bd  mov     ebx, 8009000Fh
0x18003b2c2  jmp     loc_18003B020
0x18003b2c7  mov     ebx, 80070008h
0x18003b2cc  jmp     loc_18003B020
0x18003b2d1  lea     r8, [rdi+58h]
0x18003b2d5  lea     rax, [rsp+2A8h+var_248]
0x18003b2da  sub     r8, rax
0x18003b2dd  movzx   ecx, word ptr [rax]
0x18003b2e0  movzx   r9d, word ptr [rax+r8]
0x18003b2e5  sub     ecx, r9d
0x18003b2e8  jnz     short loc_18003B2F3
0x18003b2ea  add     rax, 2
0x18003b2ee  test    r9d, r9d
0x18003b2f1  jnz     short loc_18003B2DD
0x18003b2f3  test    ecx, ecx
0x18003b2f5  jz      loc_18003B094
0x18003b2fb  lea     rcx, aMarkingOldCont; "Marking old container for delete."
0x18003b302  call    ?TraceLoggingInfo@KspDebugProvider@@SAXPEBDZZ; KspDebugProvider::TraceLoggingInfo(char const *,...)
0x18003b307  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003b30e  mov     ecx, 208h; unsigned __int64
0x18003b313  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003b318  mov     [rdi+260h], rax
0x18003b31f  test    rax, rax
0x18003b322  jz      short loc_18003B2C7
0x18003b324  lea     r8, [rsp+2A8h+var_248]; unsigned __int16 *
0x18003b329  mov     edx, 104h; unsigned __int64
0x18003b32e  mov     rcx, rax; unsigned __int16 *
0x18003b331  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003b336  mov     ebx, eax
0x18003b338  mov     [rsp+2A8h+var_278], eax
0x18003b33c  test    eax, eax
0x18003b33e  jns     loc_18003B094
0x18003b344  jmp     loc_18003B024
0x18003b349  lea     rcx, aKeyNameTooLong; "Key name too long."
0x18003b350  call    ?TraceLoggingError@KspDebugProvider@@SAXPEBDZZ; KspDebugProvider::TraceLoggingError(char const *,...)
0x18003b355  mov     ebx, 80090027h
0x18003b35a  jmp     loc_18003B020
0x18003b35f  xor     r8d, r8d; unsigned int
0x18003b362  call    ?ProviderOpenAlgorithmProvider@@YAJPEAPEAXPEBGK@Z; ProviderOpenAlgorithmProvider(void * *,ushort const *,ulong)
0x18003b367  mov     ebx, eax
0x18003b369  mov     [rsp+2A8h+var_278], eax
0x18003b36d  test    eax, eax
0x18003b36f  js      loc_18003B024
0x18003b375  jmp     loc_18003B0A8
0x18003b37a  mov     eax, [rsp+2A8h+var_278]
0x18003b37e  jmp     loc_18003B030
```
