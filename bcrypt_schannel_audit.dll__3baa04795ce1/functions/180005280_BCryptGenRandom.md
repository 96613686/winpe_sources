# BCryptGenRandom

- ea: `0x180005280`
- end: `0x180005469`
- name: `BCryptGenRandom`
- size: `489`
- prototype: `NTSTATUS __stdcall(BCRYPT_ALG_HANDLE hAlgorithm, PUCHAR pbBuffer, ULONG cbBuffer, ULONG dwFlags)`
- caller_count: `4`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005280`
- `0x180014084`
- `0x180016564`
- `0x1800168c8`

## callees

- `0x180004800`
- `0x180005060`
- `0x180005280`
- `0x180006bd0`
- `0x180007a7c`
- `0x18000b094`
- `0x1800124c4`
- `0x18001c010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180005396`
- `ntdll!RtlReleaseResource` at `0x180005396`

## string_xrefs

- `0x18000531c`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180005451`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000540b`: `onecore\ds\security\cryptoapi\ncrypt\common\syspref.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptGenRandom(BCRYPT_ALG_HANDLE hAlgorithm, PUCHAR pbBuffer, ULONG cbBuffer, ULONG dwFlags)
{
  _BYTE *v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  NTSTATUS SystemPreferredRngHandle; // ebx
  char TrustedEnvironment; // al
  int v14; // r14d
  __int64 v15; // rcx
  NTSTATUS v16; // eax
  __int64 v17; // rcx
  __int64 v18[7]; // [rsp+40h] [rbp-38h] BYREF

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_qqdD(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, cbBuffer, hAlgorithm, pbBuffer, cbBuffer, dwFlags);
    v8 = WPP_GLOBAL_Control;
  }
  if ( (dwFlags & 2) == 0 )
  {
    v9 = ValidateBaseAlgHandle(hAlgorithm);
    if ( v9 )
    {
      if ( *(_DWORD *)(v9 + 36) == 6 )
      {
        v10 = (*(__int64 (__fastcall **)(_QWORD, PUCHAR, _QWORD, _QWORD))(v9 + 88))(
                *(_QWORD *)(v9 + 24),
                pbBuffer,
                cbBuffer,
                dwFlags);
        SystemPreferredRngHandle = v10;
        if ( v10 >= 0 )
          return SystemPreferredRngHandle;
        v17 = (unsigned int)v10;
      }
      else
      {
        SystemPreferredRngHandle = -1073741816;
        v17 = 3221225480LL;
      }
    }
    else
    {
      SystemPreferredRngHandle = -1073741816;
      v17 = 3221225480LL;
    }
LABEL_29:
    DebugTraceError(v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
    return SystemPreferredRngHandle;
  }
  if ( !hAlgorithm )
  {
    TrustedEnvironment = g_TrustedEnvironment;
    v18[0] = 0;
    if ( !g_TrustedEnvironment )
      TrustedEnvironment = GetTrustedEnvironment();
    if ( (TrustedEnvironment & 1) != 0 )
    {
      SystemPreferredRngHandle = GetSystemPreferredRngHandle(v18);
      if ( SystemPreferredRngHandle < 0 )
      {
LABEL_21:
        if ( SystemPreferredRngHandle >= 0 )
          return SystemPreferredRngHandle;
        v17 = (unsigned int)SystemPreferredRngHandle;
        goto LABEL_29;
      }
      v15 = v18[0];
      v14 = 1;
    }
    else
    {
      v14 = 0;
      v15 = 129;
    }
    v16 = BCryptGenRandom((BCRYPT_ALG_HANDLE)v15, pbBuffer, cbBuffer, dwFlags & 0xFFFFFFFD);
    SystemPreferredRngHandle = v16;
    if ( v16 < 0 )
      DebugTraceError((unsigned int)v16, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\syspref.c");
    else
      SystemPreferredRngHandle = 0;
    if ( v14 )
      RtlReleaseResource(g_pCachedRngRWLock);
    goto LABEL_21;
  }
  SystemPreferredRngHandle = -1073741811;
  if ( v8 == (_BYTE *)&WPP_GLOBAL_Control || (v8[28] & 1) == 0 )
    return SystemPreferredRngHandle;
  WPP_SF_sDsd(
    *((_QWORD *)v8 + 2),
    (_DWORD)pbBuffer,
    (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
    (unsigned int)"Status",
    13,
    (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
    147);
  return -1073741811;
}

```

## disassembly

```asm
0x180005280  push    rbx
0x180005282  push    rbp
0x180005283  push    rsi
0x180005284  push    rdi
0x180005285  push    r14
0x180005287  sub     rsp, 50h
0x18000528b  mov     edi, r9d
0x18000528e  mov     esi, r8d
0x180005291  mov     rbp, rdx
0x180005294  mov     rbx, rcx
0x180005297  mov     rcx, cs:WPP_GLOBAL_Control
0x18000529e  lea     r14, WPP_GLOBAL_Control
0x1800052a5  cmp     rcx, r14
0x1800052a8  jz      short loc_1800052B4
0x1800052aa  test    byte ptr [rcx+1Ch], 4
0x1800052ae  jnz     loc_1800053DB
0x1800052b4  test    dil, 2
0x1800052b8  jnz     short loc_180005303
0x1800052ba  mov     rcx, rbx
0x1800052bd  call    ValidateBaseAlgHandle
0x1800052c2  test    rax, rax
0x1800052c5  jz      loc_180005425
0x1800052cb  cmp     dword ptr [rax+24h], 6
0x1800052cf  jnz     loc_180005437
0x1800052d5  mov     rcx, [rax+18h]
0x1800052d9  mov     r9d, edi
0x1800052dc  mov     rax, [rax+58h]
0x1800052e0  mov     r8d, esi
0x1800052e3  mov     rdx, rbp
0x1800052e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052eb  mov     ebx, eax
0x1800052ed  test    eax, eax
0x1800052ef  js      loc_180005449
0x1800052f5  mov     eax, ebx
0x1800052f7  add     rsp, 50h
0x1800052fb  pop     r14
0x1800052fd  pop     rdi
0x1800052fe  pop     rsi
0x1800052ff  pop     rbp
0x180005300  pop     rbx
0x180005301  retn
0x180005303  test    rbx, rbx
0x180005306  jz      short loc_180005352
0x180005308  mov     ebx, 0C000000Dh
0x18000530d  cmp     rcx, r14
0x180005310  jz      short loc_1800052F5
0x180005312  test    byte ptr [rcx+1Ch], 1
0x180005316  jz      short loc_1800052F5
0x180005318  mov     rcx, [rcx+10h]
0x18000531c  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005323  mov     [rsp+78h+var_48], 1B93h
0x18000532b  lea     r9, aStatus; "Status"
0x180005332  mov     [rsp+78h+var_50], r8
0x180005337  mov     dword ptr [rsp+78h+var_58], 0C000000Dh
0x18000533f  call    WPP_SF_sDsd
0x180005344  mov     eax, ebx
0x180005346  add     rsp, 50h
0x18000534a  pop     r14
0x18000534c  pop     rdi
0x18000534d  pop     rsi
0x18000534e  pop     rbp
0x18000534f  pop     rbx
0x180005350  retn
0x180005352  mov     eax, cs:g_TrustedEnvironment
0x180005358  mov     [rsp+78h+var_38], 0
0x180005361  test    eax, eax
0x180005363  jz      short loc_1800053D4
0x180005365  test    al, 1
0x180005367  jnz     short loc_1800053B7
0x180005369  xor     r14d, r14d
0x18000536c  mov     ecx, 81h; hAlgorithm
0x180005371  and     edi, 0FFFFFFFDh
0x180005374  mov     r8d, esi; cbBuffer
0x180005377  mov     r9d, edi; dwFlags
0x18000537a  mov     rdx, rbp; pbBuffer
0x18000537d  call    BCryptGenRandom
0x180005382  mov     ebx, eax
0x180005384  test    eax, eax
0x180005386  js      short loc_180005405
0x180005388  xor     ebx, ebx
0x18000538a  test    r14d, r14d
0x18000538d  jz      short loc_1800053A2
0x18000538f  mov     rcx, cs:g_pCachedRngRWLock; Resource
0x180005396  call    cs:__imp_RtlReleaseResource
0x18000539d  nop     dword ptr [rax+rax+00h]
0x1800053a2  test    ebx, ebx
0x1800053a4  jns     loc_1800052F5
0x1800053aa  mov     r9d, 1B9Dh
0x1800053b0  mov     ecx, ebx
0x1800053b2  jmp     loc_180005451
0x1800053b7  lea     rcx, [rsp+78h+var_38]
0x1800053bc  call    GetSystemPreferredRngHandle
0x1800053c1  mov     ebx, eax
0x1800053c3  test    eax, eax
0x1800053c5  js      short loc_1800053A2
0x1800053c7  mov     rcx, [rsp+78h+var_38]
0x1800053cc  mov     r14d, 1
0x1800053d2  jmp     short loc_180005371
0x1800053d4  call    GetTrustedEnvironment
0x1800053d9  jmp     short loc_180005365
0x1800053db  mov     rcx, [rcx+10h]
0x1800053df  mov     edx, 28h ; '('
0x1800053e4  mov     [rsp+78h+var_48], edi
0x1800053e8  mov     r9, rbx
0x1800053eb  mov     dword ptr [rsp+78h+var_50], esi
0x1800053ef  mov     [rsp+78h+var_58], rbp
0x1800053f4  call    WPP_SF_qqdD
0x1800053f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180005400  jmp     loc_1800052B4
0x180005405  mov     r9d, 232h
0x18000540b  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005412  lea     rdx, aStatus; "Status"
0x180005419  mov     ecx, eax
0x18000541b  call    DebugTraceError
0x180005420  jmp     loc_18000538A
0x180005425  mov     ebx, 0C0000008h
0x18000542a  mov     r9d, 1BA8h
0x180005430  mov     ecx, 0C0000008h
0x180005435  jmp     short loc_180005451
0x180005437  mov     ebx, 0C0000008h
0x18000543c  mov     r9d, 1BAFh
0x180005442  mov     ecx, 0C0000008h
0x180005447  jmp     short loc_180005451
0x180005449  mov     r9d, 1BBAh
0x18000544f  mov     ecx, eax
0x180005451  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005458  lea     rdx, aStatus; "Status"
0x18000545f  call    DebugTraceError
0x180005464  jmp     loc_1800052F5
```
