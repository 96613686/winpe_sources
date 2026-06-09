# _DllInitialize

- ea: `0x180021990`
- end: `0x180021b71`
- name: `_DllInitialize`
- size: `481`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180021940`

## callees

- `0x180021990`
- `0x180021b78`
- `0x1800254c0`
- `0x180074010`

## import_xrefs

- `ntdll!RtlInitializeCriticalSection` at `0x1800219cd`
- `ntdll!RtlInitializeCriticalSection` at `0x1800219cd`
- `ntdll!RtlDeleteCriticalSection` at `0x180021a9a`
- `ntdll!RtlDeleteCriticalSection` at `0x180021ac1`
- `ntdll!RtlDeleteCriticalSection` at `0x180021ae8`
- `ntdll!RtlDeleteCriticalSection` at `0x180021b0f`
- `ntdll!RtlDeleteCriticalSection` at `0x180021a9a`
- `ntdll!RtlDeleteCriticalSection` at `0x180021ac1`
- `ntdll!RtlDeleteCriticalSection` at `0x180021ae8`
- `ntdll!RtlDeleteCriticalSection` at `0x180021b0f`

## pseudocode

```c
char __fastcall DllInitialize(__int64 a1, unsigned int a2, __int64 a3)
{
  unsigned int i; // edi
  __int64 v7; // rbx
  int v8; // esi
  char v9; // di
  int v10; // ebx

  if ( a2 == 1 )
  {
    for ( i = 0; i < 4; ++i )
    {
      v7 = 2LL * i;
      if ( RtlInitializeCriticalSection(*(&AdvapiCriticalSections + 2 * i)) < 0 )
      {
        if ( byte_1800AE008[0] && RtlDeleteCriticalSection(AdvapiCriticalSections) >= 0 )
          byte_1800AE008[0] = 0;
        if ( byte_1800AE018 && RtlDeleteCriticalSection(CriticalSection) >= 0 )
          byte_1800AE018 = 0;
        if ( byte_1800AE028 && RtlDeleteCriticalSection(off_1800AE020) >= 0 )
          byte_1800AE028 = 0;
        if ( byte_1800AE038 && RtlDeleteCriticalSection(off_1800AE030) >= 0 )
          byte_1800AE038 = 0;
        return 0;
      }
      byte_1800AE008[8 * v7] = 1;
    }
    fCSInitialized = 1;
  }
  v8 = 1 << a2;
  v9 = 1;
  v10 = 0;
  while ( 1 )
  {
    if ( (v8 & dword_180075838[4 * v10]) == 0
      || !a2 && ((AdvapiInitRoutinesCompletedFlags[v10] & 2) == 0 || a3 && dword_180075838[4 * v10] >= 0) )
    {
      goto LABEL_8;
    }
    v9 = ((__int64 (__fastcall *)(__int64, _QWORD, __int64))*(&AdvapiInitRoutines + 2 * v10))(a1, a2, a3);
    if ( !v9 )
      break;
    AdvapiInitRoutinesCompletedFlags[v10] |= v8;
LABEL_8:
    if ( (unsigned int)++v10 >= 8 )
      goto LABEL_9;
  }
  if ( a2 == 1 )
  {
LABEL_32:
    DeleteAdvapiCriticalSections();
    return v9;
  }
LABEL_9:
  if ( !a2 && !a3 )
    goto LABEL_32;
  return v9;
}

```

## disassembly

```asm
0x180021990  mov     [rsp+arg_8], rbx
0x180021995  mov     [rsp+arg_10], rbp
0x18002199a  push    rsi
0x18002199b  push    rdi
0x18002199c  push    r12
0x18002199e  push    r13
0x1800219a0  push    r15
0x1800219a2  sub     rsp, 20h
0x1800219a6  mov     esi, 1
0x1800219ab  lea     r13, __ImageBase
0x1800219b2  mov     r15, r8
0x1800219b5  mov     ebp, edx
0x1800219b7  mov     r12, rcx
0x1800219ba  cmp     edx, esi
0x1800219bc  jnz     short loc_1800219F6
0x1800219be  xor     edi, edi
0x1800219c0  mov     ebx, edi
0x1800219c2  add     rbx, rbx
0x1800219c5  mov     rcx, rva AdvapiCriticalSections[r13+rbx*8]; CriticalSection
0x1800219cd  call    cs:__imp_RtlInitializeCriticalSection
0x1800219d4  nop     dword ptr [rax+rax+00h]
0x1800219d9  test    eax, eax
0x1800219db  js      loc_180021A8A
0x1800219e1  inc     edi
0x1800219e3  mov     rva byte_1800AE008[r13+rbx*8], sil
0x1800219eb  cmp     edi, 4
0x1800219ee  jb      short loc_1800219C0
0x1800219f0  mov     cs:fCSInitialized, esi
0x1800219f6  mov     ecx, ebp
0x1800219f8  mov     [rsp+48h+arg_0], r14
0x1800219fd  shl     esi, cl
0x1800219ff  mov     dil, 1
0x180021a02  xor     ebx, ebx
0x180021a04  movsxd  r14, ebx
0x180021a07  mov     r9, r14
0x180021a0a  add     r9, r9
0x180021a0d  test    ds:rva dword_180075838[r13+r9*8], esi
0x180021a15  jnz     short loc_180021A3D
0x180021a17  inc     ebx
0x180021a19  cmp     ebx, 8
0x180021a1c  jb      short loc_180021A04
0x180021a1e  test    dil, dil
0x180021a21  jz      loc_180021B67
0x180021a27  test    ebp, ebp
0x180021a29  jz      loc_180021B54
0x180021a2f  mov     r14, [rsp+48h+arg_0]
0x180021a34  movzx   eax, dil
0x180021a38  jmp     loc_180021B28
0x180021a3d  test    ebp, ebp
0x180021a3f  jnz     short loc_180021A56
0x180021a41  mov     eax, rva AdvapiInitRoutinesCompletedFlags[r13+r14*4]
0x180021a49  test    al, 2
0x180021a4b  jz      short loc_180021A17
0x180021a4d  test    r15, r15
0x180021a50  jnz     loc_180021B40
0x180021a56  mov     rax, ds:(AdvapiInitRoutines - 180000000h)[r13+r9*8]
0x180021a5e  mov     r8, r15
0x180021a61  mov     edx, ebp
0x180021a63  mov     rcx, r12
0x180021a66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a6b  movzx   edi, al
0x180021a6e  test    al, al
0x180021a70  jz      loc_180021B67
0x180021a76  mov     ecx, rva AdvapiInitRoutinesCompletedFlags[r13+r14*4]
0x180021a7e  or      ecx, esi
0x180021a80  mov     rva AdvapiInitRoutinesCompletedFlags[r13+r14*4], ecx
0x180021a88  jmp     short loc_180021A17
0x180021a8a  cmp     cs:byte_1800AE008, 0
0x180021a91  jz      short loc_180021AB1
0x180021a93  mov     rcx, cs:AdvapiCriticalSections; CriticalSection
0x180021a9a  call    cs:__imp_RtlDeleteCriticalSection
0x180021aa1  nop     dword ptr [rax+rax+00h]
0x180021aa6  test    eax, eax
0x180021aa8  js      short loc_180021AB1
0x180021aaa  mov     cs:byte_1800AE008, 0
0x180021ab1  cmp     cs:byte_1800AE018, 0
0x180021ab8  jz      short loc_180021AD8
0x180021aba  mov     rcx, cs:CriticalSection; CriticalSection
0x180021ac1  call    cs:__imp_RtlDeleteCriticalSection
0x180021ac8  nop     dword ptr [rax+rax+00h]
0x180021acd  test    eax, eax
0x180021acf  js      short loc_180021AD8
0x180021ad1  mov     cs:byte_1800AE018, 0
0x180021ad8  cmp     cs:byte_1800AE028, 0
0x180021adf  jz      short loc_180021AFF
0x180021ae1  mov     rcx, cs:off_1800AE020; CriticalSection
0x180021ae8  call    cs:__imp_RtlDeleteCriticalSection
0x180021aef  nop     dword ptr [rax+rax+00h]
0x180021af4  test    eax, eax
0x180021af6  js      short loc_180021AFF
0x180021af8  mov     cs:byte_1800AE028, 0
0x180021aff  cmp     cs:byte_1800AE038, 0
0x180021b06  jz      short loc_180021B26
0x180021b08  mov     rcx, cs:off_1800AE030; CriticalSection
0x180021b0f  call    cs:__imp_RtlDeleteCriticalSection
0x180021b16  nop     dword ptr [rax+rax+00h]
0x180021b1b  test    eax, eax
0x180021b1d  js      short loc_180021B26
0x180021b1f  mov     cs:byte_1800AE038, 0
0x180021b26  xor     al, al
0x180021b28  mov     rbx, [rsp+48h+arg_8]
0x180021b2d  mov     rbp, [rsp+48h+arg_10]
0x180021b32  add     rsp, 20h
0x180021b36  pop     r15
0x180021b38  pop     r13
0x180021b3a  pop     r12
0x180021b3c  pop     rdi
0x180021b3d  pop     rsi
0x180021b3e  retn
0x180021b40  cmp     ds:rva dword_180075838[r13+r9*8], 0
0x180021b49  jl      loc_180021A56
0x180021b4f  jmp     loc_180021A17
0x180021b54  test    r15, r15
0x180021b57  jnz     loc_180021A2F
0x180021b5d  call    DeleteAdvapiCriticalSections
0x180021b62  jmp     loc_180021A2F
0x180021b67  cmp     ebp, 1
0x180021b6a  jz      short loc_180021B5D
0x180021b6c  jmp     loc_180021A27
```
