# AesRNGState_select

- ea: `0x18002eb90`
- end: `0x18002ede7`
- name: `AesRNGState_select`
- size: `599`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002e680`
- `0x18002ef10`

## callees

- `0x1800102a0`
- `0x1800225a0`
- `0x18002bf08`
- `0x18002d184`
- `0x18002e23c`
- `0x18002eb90`
- `0x18002f2e0`
- `0x18002f5d0`
- `0x1800593e0`
- `0x180063180`
- `0x18007f790`

## import_xrefs

- `ntdll!RtlGetCurrentProcessorNumberEx` at `0x18002ebf4`
- `ntdll!RtlGetCurrentProcessorNumberEx` at `0x18002ebf4`
- `ntdll!RtlFreeHeap` at `0x18002ec57`
- `ntdll!RtlFreeHeap` at `0x18002ec57`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002eceb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002eceb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002eda8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002eda8`

## pseudocode

```c
__int64 __fastcall AesRNGState_select(__int128 **a1, int a2, __int64 a3)
{
  char TrustedEnvironment; // al
  __int128 *v4; // rsi
  int v6; // ebp
  char v7; // bl
  __int64 *v8; // rdi
  volatile signed __int64 v9; // rax
  volatile signed __int64 *v10; // rbx
  char *v11; // rdi
  char *v13; // rax
  __int64 v14; // rax
  void *v15; // rax
  signed __int64 v16; // r15
  __int64 v17; // rdx
  int v18; // [rsp+20h] [rbp-78h] BYREF
  __int64 v19; // [rsp+28h] [rbp-70h] BYREF
  _BYTE v20[48]; // [rsp+30h] [rbp-68h] BYREF

  TrustedEnvironment = g_TrustedEnvironment;
  v4 = &g_rootAesRngState;
  v19 = 0;
  v6 = 0;
  if ( !g_TrustedEnvironment )
    TrustedEnvironment = GetTrustedEnvironment(a1, a2, a3);
  if ( (TrustedEnvironment & 8) != 0 )
    goto LABEL_9;
  v18 = 0;
  RtlGetCurrentProcessorNumberEx(&v18);
  v7 = BYTE2(v18);
  v8 = &g_AesStatesTable[v18 & 0x3F];
  v9 = *v8;
  if ( !*v8 )
  {
    v15 = (void *)SafeAllocaAllocateFromHeap(512);
    v16 = (signed __int64)v15;
    if ( !v15 )
      goto LABEL_20;
    memset_0(v15, 0, 0x200u);
    if ( _InterlockedCompareExchange64(v8, v16, 0) )
      BCryptFree(v16, v17);
    v9 = *v8;
  }
  v10 = (volatile signed __int64 *)(v9 + 8LL * (v7 & 0x3F));
  if ( !v10 )
    goto LABEL_20;
  v11 = 0;
  if ( *v10 )
    goto LABEL_7;
  v13 = (char *)SafeAllocaAllocateFromHeap(304);
  v11 = v13;
  if ( !v13 )
  {
LABEL_20:
    v6 = -1073741801;
    goto LABEL_9;
  }
  memset_0(v13, 0, 0x130u);
  v6 = AesRNGState_generate(&g_rootAesRngState, v20, 48, &v19);
  if ( v6 < 0 )
    goto LABEL_8;
  *(_DWORD *)v11 = 304;
  InitializeCriticalSection((LPCRITICAL_SECTION)(v11 + 128));
  if ( (unsigned int)SymCryptRngAesInstantiate(v11 + 16, v20, 48) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)(v11 + 128));
    SymCryptWipeAsm(v20, 48);
    v6 = -1073741595;
    goto LABEL_8;
  }
  SymCryptRngAesGenerate(v11 + 16, v11 + 64, 16);
  v14 = v19;
  v11[88] = 1;
  *((_QWORD *)v11 + 15) = v14;
  *((_QWORD *)v11 + 14) = 0;
  SymCryptWipeAsm(v20, 48);
  if ( _InterlockedCompareExchange64(v10, (signed __int64)v11, 0) )
    AesRNGState_wipe(v11);
  else
    v11 = 0;
  v6 = 0;
LABEL_7:
  v4 = (__int128 *)*v10;
  if ( v11 )
LABEL_8:
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
LABEL_9:
  *a1 = v4;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002eb90  push    rbp
0x18002eb92  push    rsi
0x18002eb93  push    r12
0x18002eb95  push    r14
0x18002eb97  sub     rsp, 78h
0x18002eb9b  mov     rax, cs:__security_cookie
0x18002eba2  xor     rax, rsp
0x18002eba5  mov     [rsp+98h+var_38], rax
0x18002ebaa  mov     eax, cs:g_TrustedEnvironment
0x18002ebb0  lea     rsi, g_rootAesRngState
0x18002ebb7  xor     r12d, r12d
0x18002ebba  mov     r14, rcx
0x18002ebbd  mov     [rsp+98h+var_70], r12
0x18002ebc2  mov     ebp, r12d
0x18002ebc5  test    eax, eax
0x18002ebc7  jz      loc_18002EDDD
0x18002ebcd  test    al, 8
0x18002ebcf  jnz     loc_18002EC78
0x18002ebd5  mov     [rsp+98h+arg_8], rbx
0x18002ebdd  lea     rcx, [rsp+98h+var_78]
0x18002ebe2  mov     [rsp+98h+arg_10], rdi
0x18002ebea  mov     [rsp+98h+var_28], r15
0x18002ebef  mov     [rsp+98h+var_78], r12d
0x18002ebf4  call    cs:__imp_RtlGetCurrentProcessorNumberEx
0x18002ebfb  nop     dword ptr [rax+rax+00h]
0x18002ec00  movzx   eax, word ptr [rsp+98h+var_78]
0x18002ec05  lea     rcx, g_AesStatesTable
0x18002ec0c  movzx   ebx, byte ptr [rsp+98h+var_78+2]
0x18002ec11  and     eax, 3Fh
0x18002ec14  lea     rdi, [rcx+rax*8]
0x18002ec18  mov     rax, [rcx+rax*8]
0x18002ec1c  test    rax, rax
0x18002ec1f  jz      loc_18002ED5A
0x18002ec25  and     ebx, 3Fh
0x18002ec28  lea     rbx, [rax+rbx*8]
0x18002ec2c  test    rbx, rbx
0x18002ec2f  jz      loc_18002ED8D
0x18002ec35  mov     rdi, r12
0x18002ec38  cmp     [rbx], r12
0x18002ec3b  jz      short loc_18002EC96
0x18002ec3d  mov     rsi, [rbx]
0x18002ec40  test    rdi, rdi
0x18002ec43  jz      short loc_18002EC63
0x18002ec45  mov     rcx, gs:60h
0x18002ec4e  mov     r8, rdi; P
0x18002ec51  xor     edx, edx; Flags
0x18002ec53  mov     rcx, [rcx+30h]; HeapHandle
0x18002ec57  call    cs:__imp_RtlFreeHeap
0x18002ec5e  nop     dword ptr [rax+rax+00h]
0x18002ec63  mov     r15, [rsp+98h+var_28]
0x18002ec68  mov     rbx, [rsp+98h+arg_8]
0x18002ec70  mov     rdi, [rsp+98h+arg_10]
0x18002ec78  mov     [r14], rsi
0x18002ec7b  mov     eax, ebp
0x18002ec7d  mov     rcx, [rsp+98h+var_38]
0x18002ec82  xor     rcx, rsp; StackCookie
0x18002ec85  call    __security_check_cookie
0x18002ec8a  add     rsp, 78h
0x18002ec8e  pop     r14
0x18002ec90  pop     r12
0x18002ec92  pop     rsi
0x18002ec93  pop     rbp
0x18002ec94  retn
0x18002ec96  mov     ecx, 130h
0x18002ec9b  call    SafeAllocaAllocateFromHeap
0x18002eca0  mov     rdi, rax
0x18002eca3  test    rax, rax
0x18002eca6  jz      loc_18002ED8D
0x18002ecac  xor     edx, edx; Val
0x18002ecae  mov     r8d, 130h; Size
0x18002ecb4  mov     rcx, rax; void *
0x18002ecb7  call    memset_0
0x18002ecbc  lea     r9, [rsp+98h+var_70]
0x18002ecc1  mov     r8d, 30h ; '0'
0x18002ecc7  lea     rdx, [rsp+98h+var_68]
0x18002eccc  mov     rcx, rsi
0x18002eccf  call    AesRNGState_generate
0x18002ecd4  mov     ebp, eax
0x18002ecd6  test    eax, eax
0x18002ecd8  js      loc_18002EC45
0x18002ecde  lea     rcx, [rdi+80h]; lpCriticalSection
0x18002ece5  mov     dword ptr [rdi], 130h
0x18002eceb  call    cs:__imp_InitializeCriticalSection
0x18002ecf2  nop     dword ptr [rax+rax+00h]
0x18002ecf7  mov     r8d, 30h ; '0'
0x18002ecfd  lea     rdx, [rsp+98h+var_68]
0x18002ed02  lea     rcx, [rdi+10h]
0x18002ed06  call    SymCryptRngAesInstantiate
0x18002ed0b  test    eax, eax
0x18002ed0d  jnz     loc_18002EDA1
0x18002ed13  lea     rdx, [rdi+40h]
0x18002ed17  mov     r8d, 10h
0x18002ed1d  lea     rcx, [rdi+10h]
0x18002ed21  call    SymCryptRngAesGenerate
0x18002ed26  mov     rax, [rsp+98h+var_70]
0x18002ed2b  lea     rcx, [rsp+98h+var_68]
0x18002ed30  mov     byte ptr [rdi+58h], 1
0x18002ed34  mov     edx, 30h ; '0'
0x18002ed39  mov     [rdi+78h], rax
0x18002ed3d  mov     [rdi+70h], r12
0x18002ed41  call    SymCryptWipeAsm
0x18002ed46  xor     eax, eax
0x18002ed48  lock cmpxchg [rbx], rdi
0x18002ed4d  jnz     short loc_18002EDCD
0x18002ed4f  mov     rdi, r12
0x18002ed52  mov     ebp, r12d
0x18002ed55  jmp     loc_18002EC3D
0x18002ed5a  mov     ecx, 200h
0x18002ed5f  call    SafeAllocaAllocateFromHeap
0x18002ed64  mov     r15, rax
0x18002ed67  test    rax, rax
0x18002ed6a  jz      short loc_18002ED8D
0x18002ed6c  xor     edx, edx; Val
0x18002ed6e  mov     r8d, 200h; Size
0x18002ed74  mov     rcx, rax; void *
0x18002ed77  call    memset_0
0x18002ed7c  xor     eax, eax
0x18002ed7e  lock cmpxchg [rdi], r15
0x18002ed83  jnz     short loc_18002ED97
0x18002ed85  mov     rax, [rdi]
0x18002ed88  jmp     loc_18002EC25
0x18002ed8d  mov     ebp, 0C0000017h
0x18002ed92  jmp     loc_18002EC63
0x18002ed97  mov     rcx, r15
0x18002ed9a  call    BCryptFree
0x18002ed9f  jmp     short loc_18002ED85
0x18002eda1  lea     rcx, [rdi+80h]; lpCriticalSection
0x18002eda8  call    cs:__imp_DeleteCriticalSection
0x18002edaf  nop     dword ptr [rax+rax+00h]
0x18002edb4  mov     edx, 30h ; '0'
0x18002edb9  lea     rcx, [rsp+98h+var_68]
0x18002edbe  call    SymCryptWipeAsm
0x18002edc3  mov     ebp, 0C00000E5h
0x18002edc8  jmp     loc_18002EC45
0x18002edcd  mov     rcx, rdi
0x18002edd0  call    AesRNGState_wipe
0x18002edd5  mov     ebp, r12d
0x18002edd8  jmp     loc_18002EC3D
0x18002eddd  call    GetTrustedEnvironment
0x18002ede2  jmp     loc_18002EBCD
```
