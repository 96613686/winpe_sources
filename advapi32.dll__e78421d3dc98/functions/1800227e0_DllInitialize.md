# _DllInitialize

- ea: `0x1800227e0`
- end: `0x1800229a2`
- name: `_DllInitialize`
- size: `450`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180022790`

## callees

- `0x1800227e0`
- `0x1800229a8`
- `0x180022d40`
- `0x180066010`

## import_xrefs

- `ntdll!RtlInitializeCriticalSection` at `0x18002281d`
- `ntdll!RtlInitializeCriticalSection` at `0x18002281d`
- `ntdll!RtlDeleteCriticalSection` at `0x1800228e4`
- `ntdll!RtlDeleteCriticalSection` at `0x180022905`
- `ntdll!RtlDeleteCriticalSection` at `0x180022926`
- `ntdll!RtlDeleteCriticalSection` at `0x180022947`
- `ntdll!RtlDeleteCriticalSection` at `0x1800228e4`
- `ntdll!RtlDeleteCriticalSection` at `0x180022905`
- `ntdll!RtlDeleteCriticalSection` at `0x180022926`
- `ntdll!RtlDeleteCriticalSection` at `0x180022947`

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
        if ( byte_18009F008[0] && RtlDeleteCriticalSection(AdvapiCriticalSections) >= 0 )
          byte_18009F008[0] = 0;
        if ( byte_18009F018 && RtlDeleteCriticalSection(CriticalSection) >= 0 )
          byte_18009F018 = 0;
        if ( byte_18009F028 && RtlDeleteCriticalSection(off_18009F020) >= 0 )
          byte_18009F028 = 0;
        if ( byte_18009F038 && RtlDeleteCriticalSection(off_18009F030) >= 0 )
          byte_18009F038 = 0;
        return 0;
      }
      byte_18009F008[8 * v7] = 1;
    }
    fCSInitialized = 1;
  }
  v8 = 1 << a2;
  v9 = 1;
  v10 = 0;
  while ( 1 )
  {
    if ( (v8 & dword_180067838[4 * v10]) == 0
      || !a2 && ((AdvapiInitRoutinesCompletedFlags[v10] & 2) == 0 || a3 && dword_180067838[4 * v10] >= 0) )
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
0x1800227e0  mov     [rsp+arg_8], rbx
0x1800227e5  mov     [rsp+arg_10], rbp
0x1800227ea  push    rsi
0x1800227eb  push    rdi
0x1800227ec  push    r12
0x1800227ee  push    r13
0x1800227f0  push    r15
0x1800227f2  sub     rsp, 20h
0x1800227f6  mov     esi, 1
0x1800227fb  lea     r13, __ImageBase
0x180022802  mov     r15, r8
0x180022805  mov     ebp, edx
0x180022807  mov     r12, rcx
0x18002280a  cmp     edx, esi
0x18002280c  jnz     short loc_180022840
0x18002280e  xor     edi, edi
0x180022810  mov     ebx, edi
0x180022812  add     rbx, rbx
0x180022815  mov     rcx, rva AdvapiCriticalSections[r13+rbx*8]; CriticalSection
0x18002281d  call    cs:__imp_RtlInitializeCriticalSection
0x180022823  test    eax, eax
0x180022825  js      loc_1800228D4
0x18002282b  inc     edi
0x18002282d  mov     rva byte_18009F008[r13+rbx*8], sil
0x180022835  cmp     edi, 4
0x180022838  jb      short loc_180022810
0x18002283a  mov     cs:fCSInitialized, esi
0x180022840  mov     ecx, ebp
0x180022842  mov     [rsp+48h+arg_0], r14
0x180022847  shl     esi, cl
0x180022849  mov     dil, 1
0x18002284c  xor     ebx, ebx
0x18002284e  movsxd  r14, ebx
0x180022851  mov     r9, r14
0x180022854  add     r9, r9
0x180022857  test    ds:rva dword_180067838[r13+r9*8], esi
0x18002285f  jnz     short loc_180022887
0x180022861  inc     ebx
0x180022863  cmp     ebx, 8
0x180022866  jb      short loc_18002284E
0x180022868  test    dil, dil
0x18002286b  jz      loc_180022998
0x180022871  test    ebp, ebp
0x180022873  jz      loc_180022985
0x180022879  mov     r14, [rsp+48h+arg_0]
0x18002287e  movzx   eax, dil
0x180022882  jmp     loc_18002295A
0x180022887  test    ebp, ebp
0x180022889  jnz     short loc_1800228A0
0x18002288b  mov     eax, rva AdvapiInitRoutinesCompletedFlags[r13+r14*4]
0x180022893  test    al, 2
0x180022895  jz      short loc_180022861
0x180022897  test    r15, r15
0x18002289a  jnz     loc_180022971
0x1800228a0  mov     rax, ds:(AdvapiInitRoutines - 180000000h)[r13+r9*8]
0x1800228a8  mov     r8, r15
0x1800228ab  mov     edx, ebp
0x1800228ad  mov     rcx, r12
0x1800228b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800228b5  movzx   edi, al
0x1800228b8  test    al, al
0x1800228ba  jz      loc_180022998
0x1800228c0  mov     ecx, rva AdvapiInitRoutinesCompletedFlags[r13+r14*4]
0x1800228c8  or      ecx, esi
0x1800228ca  mov     rva AdvapiInitRoutinesCompletedFlags[r13+r14*4], ecx
0x1800228d2  jmp     short loc_180022861
0x1800228d4  cmp     cs:byte_18009F008, 0
0x1800228db  jz      short loc_1800228F5
0x1800228dd  mov     rcx, cs:AdvapiCriticalSections; CriticalSection
0x1800228e4  call    cs:__imp_RtlDeleteCriticalSection
0x1800228ea  test    eax, eax
0x1800228ec  js      short loc_1800228F5
0x1800228ee  mov     cs:byte_18009F008, 0
0x1800228f5  cmp     cs:byte_18009F018, 0
0x1800228fc  jz      short loc_180022916
0x1800228fe  mov     rcx, cs:CriticalSection; CriticalSection
0x180022905  call    cs:__imp_RtlDeleteCriticalSection
0x18002290b  test    eax, eax
0x18002290d  js      short loc_180022916
0x18002290f  mov     cs:byte_18009F018, 0
0x180022916  cmp     cs:byte_18009F028, 0
0x18002291d  jz      short loc_180022937
0x18002291f  mov     rcx, cs:off_18009F020; CriticalSection
0x180022926  call    cs:__imp_RtlDeleteCriticalSection
0x18002292c  test    eax, eax
0x18002292e  js      short loc_180022937
0x180022930  mov     cs:byte_18009F028, 0
0x180022937  cmp     cs:byte_18009F038, 0
0x18002293e  jz      short loc_180022958
0x180022940  mov     rcx, cs:off_18009F030; CriticalSection
0x180022947  call    cs:__imp_RtlDeleteCriticalSection
0x18002294d  test    eax, eax
0x18002294f  js      short loc_180022958
0x180022951  mov     cs:byte_18009F038, 0
0x180022958  xor     al, al
0x18002295a  mov     rbx, [rsp+48h+arg_8]
0x18002295f  mov     rbp, [rsp+48h+arg_10]
0x180022964  add     rsp, 20h
0x180022968  pop     r15
0x18002296a  pop     r13
0x18002296c  pop     r12
0x18002296e  pop     rdi
0x18002296f  pop     rsi
0x180022970  retn
0x180022971  cmp     ds:rva dword_180067838[r13+r9*8], 0
0x18002297a  jl      loc_1800228A0
0x180022980  jmp     loc_180022861
0x180022985  test    r15, r15
0x180022988  jnz     loc_180022879
0x18002298e  call    DeleteAdvapiCriticalSections
0x180022993  jmp     loc_180022879
0x180022998  cmp     ebp, 1
0x18002299b  jz      short loc_18002298E
0x18002299d  jmp     loc_180022871
```
