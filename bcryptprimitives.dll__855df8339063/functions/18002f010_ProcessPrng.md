# ProcessPrng

- ea: `0x18002f010`
- end: `0x18002f2d5`
- name: `ProcessPrng`
- size: `709`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180020d08`
- `0x18002df30`
- `0x18002e290`
- `0x18002e2b0`
- `0x18003e750`

## callees

- `0x1800102a0`
- `0x1800225a0`
- `0x18002bf08`
- `0x18002d184`
- `0x18002e23c`
- `0x18002f010`
- `0x18002f2e0`
- `0x18002f5d0`
- `0x1800593e0`
- `0x180063180`
- `0x18006370c`
- `0x18007f790`

## import_xrefs

- `ntdll!RtlGetCurrentProcessorNumberEx` at `0x18002f08e`
- `ntdll!RtlGetCurrentProcessorNumberEx` at `0x18002f08e`
- `ntdll!RtlFreeHeap` at `0x18002f0f9`
- `ntdll!RtlFreeHeap` at `0x18002f0f9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002f1d1`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002f1d1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002f289`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002f289`

## pseudocode

```c
_BOOL8 __fastcall ProcessPrng(__int64 a1, unsigned __int64 a2, __int64 a3)
{
  unsigned __int64 v3; // rbx
  __int64 v4; // rbp
  char TrustedEnvironment; // al
  int v6; // esi
  __int128 *v7; // r14
  char v8; // di
  __int64 *v9; // r15
  volatile signed __int64 v10; // rax
  volatile signed __int64 *v11; // rdi
  _DWORD *v12; // r15
  __int64 v13; // rdi
  __int64 v14; // rdx
  _DWORD *v16; // rax
  __int64 v17; // rax
  void *v18; // rax
  signed __int64 v19; // r12
  __int64 v20; // rdx
  int v21; // [rsp+20h] [rbp-88h] BYREF
  __int64 v22; // [rsp+28h] [rbp-80h] BYREF
  __int64 v23; // [rsp+30h] [rbp-78h] BYREF
  _BYTE v24[48]; // [rsp+38h] [rbp-70h] BYREF

  v3 = a2;
  v4 = a1;
  if ( g_rngState == 1 )
  {
    TrustedEnvironment = g_TrustedEnvironment;
    v6 = 0;
    v23 = 0;
    v7 = &g_rootAesRngState;
    v22 = 0;
    if ( !g_TrustedEnvironment )
      TrustedEnvironment = GetTrustedEnvironment(a1, a2, a3);
    if ( (TrustedEnvironment & 8) != 0 )
      goto LABEL_11;
    v21 = 0;
    RtlGetCurrentProcessorNumberEx(&v21);
    v8 = BYTE2(v21);
    v9 = &g_AesStatesTable[v21 & 0x3F];
    v10 = *v9;
    if ( !*v9 )
    {
      v18 = (void *)SafeAllocaAllocateFromHeap(512);
      v19 = (signed __int64)v18;
      if ( !v18 )
        goto LABEL_11;
      memset_0(v18, 0, 0x200u);
      if ( _InterlockedCompareExchange64(v9, v19, 0) )
        BCryptFree(v19, v20);
      v10 = *v9;
    }
    v11 = (volatile signed __int64 *)(v10 + 8LL * (v8 & 0x3F));
    if ( !v11 )
      goto LABEL_11;
    v12 = 0;
    if ( !*v11 )
    {
      v16 = (_DWORD *)SafeAllocaAllocateFromHeap(304);
      v12 = v16;
      if ( !v16 )
      {
LABEL_9:
        if ( v12 )
LABEL_10:
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
LABEL_11:
        while ( v3 )
        {
          v13 = 0x10000;
          v14 = v4;
          if ( v3 < 0x10000 )
            v13 = v3;
          v4 += v13;
          v6 = AesRNGState_generate(v7, v14, v13, &v23);
          v3 -= v13;
        }
        return v6 >= 0;
      }
      memset_0(v16, 0, 0x130u);
      if ( (int)AesRNGState_generate(&g_rootAesRngState, v24, 48, &v22) < 0 )
        goto LABEL_10;
      *v12 = 304;
      InitializeCriticalSection((LPCRITICAL_SECTION)(v12 + 32));
      if ( (unsigned int)SymCryptRngAesInstantiate(v12 + 4, v24, 48) )
      {
        DeleteCriticalSection((LPCRITICAL_SECTION)(v12 + 32));
        SymCryptWipeAsm(v24, 48);
        goto LABEL_10;
      }
      SymCryptRngAesGenerate(v12 + 4, v12 + 16, 16);
      v17 = v22;
      *((_BYTE *)v12 + 88) = 1;
      *((_QWORD *)v12 + 15) = v17;
      *((_QWORD *)v12 + 14) = 0;
      SymCryptWipeAsm(v24, 48);
      if ( _InterlockedCompareExchange64(v11, (signed __int64)v12, 0) )
        AesRNGState_wipe(v12);
      else
        v12 = 0;
    }
    v7 = (__int128 *)*v11;
    goto LABEL_9;
  }
  if ( g_rngState != 2 )
  {
    MEMORY[0] = 2020044402;
    while ( 1 )
      ;
  }
  EmergencyRng();
  return 1;
}

```

## disassembly

```asm
0x18002f010  mov     r11, rsp
0x18002f013  push    rbx
0x18002f014  push    rbp
0x18002f015  sub     rsp, 98h
0x18002f01c  mov     rax, cs:__security_cookie
0x18002f023  xor     rax, rsp
0x18002f026  mov     [rsp+0A8h+var_40], rax
0x18002f02b  movzx   eax, cs:g_rngState
0x18002f032  mov     rbx, rdx
0x18002f035  mov     rbp, rcx
0x18002f038  cmp     al, 1
0x18002f03a  jnz     loc_18002F2C0
0x18002f040  mov     eax, cs:g_TrustedEnvironment
0x18002f046  mov     [r11+18h], rsi
0x18002f04a  mov     [r11-20h], r12
0x18002f04e  xor     r12d, r12d
0x18002f051  mov     [r11-30h], r14
0x18002f055  mov     esi, r12d
0x18002f058  mov     [r11-78h], r12
0x18002f05c  lea     r14, g_rootAesRngState
0x18002f063  mov     [r11-80h], r12
0x18002f067  test    eax, eax
0x18002f069  jz      loc_18002F2B6
0x18002f06f  mov     [rsp+0A8h+var_18], rdi
0x18002f077  test    al, 8
0x18002f079  jnz     loc_18002F112
0x18002f07f  lea     rcx, [rsp+0A8h+var_88]
0x18002f084  mov     [rsp+0A8h+var_38], r15
0x18002f089  mov     [rsp+0A8h+var_88], r12d
0x18002f08e  call    cs:__imp_RtlGetCurrentProcessorNumberEx
0x18002f095  nop     dword ptr [rax+rax+00h]
0x18002f09a  movzx   eax, word ptr [rsp+0A8h+var_88]
0x18002f09f  lea     rcx, g_AesStatesTable
0x18002f0a6  movzx   edi, byte ptr [rsp+0A8h+var_88+2]
0x18002f0ab  and     eax, 3Fh
0x18002f0ae  lea     r15, [rcx+rax*8]
0x18002f0b2  mov     rax, [rcx+rax*8]
0x18002f0b6  test    rax, rax
0x18002f0b9  jz      loc_18002F23E
0x18002f0bf  and     edi, 3Fh
0x18002f0c2  lea     rdi, [rax+rdi*8]
0x18002f0c6  test    rdi, rdi
0x18002f0c9  jz      short loc_18002F10D
0x18002f0cb  mov     r15, r12
0x18002f0ce  mov     [rsp+0A8h+var_28], r13
0x18002f0d6  cmp     [rdi], rsi
0x18002f0d9  jz      loc_18002F17D
0x18002f0df  mov     r14, [rdi]
0x18002f0e2  test    r15, r15
0x18002f0e5  jz      short loc_18002F105
0x18002f0e7  mov     rcx, gs:60h
0x18002f0f0  mov     r8, r15; P
0x18002f0f3  xor     edx, edx; Flags
0x18002f0f5  mov     rcx, [rcx+30h]; HeapHandle
0x18002f0f9  call    cs:__imp_RtlFreeHeap
0x18002f100  nop     dword ptr [rax+rax+00h]
0x18002f105  mov     r13, [rsp+0A8h+var_28]
0x18002f10d  mov     r15, [rsp+0A8h+var_38]
0x18002f112  mov     r12, [rsp+0A8h+var_20]
0x18002f11a  test    rbx, rbx
0x18002f11d  jz      short loc_18002F149
0x18002f11f  nop
0x18002f120  mov     edi, 10000h
0x18002f125  lea     r9, [rsp+0A8h+var_78]
0x18002f12a  cmp     rbx, rdi
0x18002f12d  mov     rdx, rbp
0x18002f130  mov     rcx, r14
0x18002f133  cmovb   rdi, rbx
0x18002f137  mov     r8, rdi
0x18002f13a  call    AesRNGState_generate
0x18002f13f  add     rbp, rdi
0x18002f142  mov     esi, eax
0x18002f144  sub     rbx, rdi
0x18002f147  jnz     short loc_18002F120
0x18002f149  mov     r14, [rsp+0A8h+var_30]
0x18002f14e  not     esi
0x18002f150  mov     rdi, [rsp+0A8h+var_18]
0x18002f158  shr     esi, 1Fh
0x18002f15b  mov     eax, esi
0x18002f15d  mov     rsi, [rsp+0A8h+arg_10]
0x18002f165  mov     rcx, [rsp+0A8h+var_40]
0x18002f16a  xor     rcx, rsp; StackCookie
0x18002f16d  call    __security_check_cookie
0x18002f172  add     rsp, 98h
0x18002f179  pop     rbp
0x18002f17a  pop     rbx
0x18002f17b  retn
0x18002f17d  mov     ecx, 130h
0x18002f182  call    SafeAllocaAllocateFromHeap
0x18002f187  mov     r15, rax
0x18002f18a  test    rax, rax
0x18002f18d  jz      loc_18002F0E2
0x18002f193  xor     edx, edx; Val
0x18002f195  mov     r8d, 130h; Size
0x18002f19b  mov     rcx, rax; void *
0x18002f19e  call    memset_0
0x18002f1a3  lea     r9, [rsp+0A8h+var_80]
0x18002f1a8  mov     r8d, 30h ; '0'
0x18002f1ae  lea     rdx, [rsp+0A8h+var_70]
0x18002f1b3  mov     rcx, r14
0x18002f1b6  call    AesRNGState_generate
0x18002f1bb  test    eax, eax
0x18002f1bd  js      loc_18002F0E7
0x18002f1c3  lea     rcx, [r15+80h]; lpCriticalSection
0x18002f1ca  mov     dword ptr [r15], 130h
0x18002f1d1  call    cs:__imp_InitializeCriticalSection
0x18002f1d8  nop     dword ptr [rax+rax+00h]
0x18002f1dd  mov     r8d, 30h ; '0'
0x18002f1e3  lea     rdx, [rsp+0A8h+var_70]
0x18002f1e8  lea     rcx, [r15+10h]
0x18002f1ec  call    SymCryptRngAesInstantiate
0x18002f1f1  test    eax, eax
0x18002f1f3  jnz     loc_18002F282
0x18002f1f9  lea     rdx, [r15+40h]
0x18002f1fd  mov     r8d, 10h
0x18002f203  lea     rcx, [r15+10h]
0x18002f207  call    SymCryptRngAesGenerate
0x18002f20c  mov     rax, [rsp+0A8h+var_80]
0x18002f211  lea     rcx, [rsp+0A8h+var_70]
0x18002f216  mov     byte ptr [r15+58h], 1
0x18002f21b  mov     edx, 30h ; '0'
0x18002f220  mov     [r15+78h], rax
0x18002f224  mov     [r15+70h], rsi
0x18002f228  call    SymCryptWipeAsm
0x18002f22d  xor     eax, eax
0x18002f22f  lock cmpxchg [rdi], r15
0x18002f234  jnz     short loc_18002F2A9
0x18002f236  xor     r15d, r15d
0x18002f239  jmp     loc_18002F0DF
0x18002f23e  mov     ecx, 200h
0x18002f243  call    SafeAllocaAllocateFromHeap
0x18002f248  mov     r12, rax
0x18002f24b  test    rax, rax
0x18002f24e  jz      loc_18002F10D
0x18002f254  xor     edx, edx; Val
0x18002f256  mov     r8d, 200h; Size
0x18002f25c  mov     rcx, rax; void *
0x18002f25f  call    memset_0
0x18002f264  xor     eax, eax
0x18002f266  lock cmpxchg [r15], r12
0x18002f26b  jnz     short loc_18002F278
0x18002f26d  mov     rax, [r15]
0x18002f270  xor     r12d, r12d
0x18002f273  jmp     loc_18002F0BF
0x18002f278  mov     rcx, r12
0x18002f27b  call    BCryptFree
0x18002f280  jmp     short loc_18002F26D
0x18002f282  lea     rcx, [r15+80h]; lpCriticalSection
0x18002f289  call    cs:__imp_DeleteCriticalSection
0x18002f290  nop     dword ptr [rax+rax+00h]
0x18002f295  mov     edx, 30h ; '0'
0x18002f29a  lea     rcx, [rsp+0A8h+var_70]
0x18002f29f  call    SymCryptWipeAsm
0x18002f2a4  jmp     loc_18002F0E7
0x18002f2a9  mov     rcx, r15
0x18002f2ac  call    AesRNGState_wipe
0x18002f2b1  jmp     loc_18002F0DF
0x18002f2b6  call    GetTrustedEnvironment
0x18002f2bb  jmp     loc_18002F06F
0x18002f2c0  cmp     al, 2
0x18002f2c2  jz      loc_180081E68
0x18002f2c8  mov     dword ptr ds:0, 78676E72h
0x18002f2d3  jmp     short loc_18002F2D3
0x180081e68  call    EmergencyRng
0x180081e6d  mov     eax, 1
0x180081e72  jmp     loc_18002F165
```
