# mmInitializeMultipleCriticalSections(_RTL_CRITICAL_SECTION * *,long)

- ea: `0x18000dea4`
- end: `0x18000df02`
- name: `?mmInitializeMultipleCriticalSections@@YAHPEAPEAU_RTL_CRITICAL_SECTION@@J@Z`
- size: `94`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION **, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ddc8`

## callees

- `0x18000dea4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000dec2`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000dec2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000dedd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000dedd`

## pseudocode

```c
__int64 __fastcall mmInitializeMultipleCriticalSections(struct _RTL_CRITICAL_SECTION **a1)
{
  int v1; // edi
  __int64 v2; // rbx
  int i; // ebx

  v1 = 0;
  v2 = 0;
  do
  {
    InitializeCriticalSection((LPCRITICAL_SECTION)(&acs)[v2]);
    ++v1;
    ++v2;
  }
  while ( v1 < 7 );
  if ( v1 == 7 )
    return 1;
  for ( i = 0; i < v1; ++i )
    DeleteCriticalSection((LPCRITICAL_SECTION)(&acs)[i]);
  return 0;
}

```

## disassembly

```asm
0x18000dea4  mov     [rsp+arg_0], rbx
0x18000dea9  mov     [rsp+arg_8], rsi
0x18000deae  push    rdi
0x18000deaf  sub     rsp, 20h
0x18000deb3  xor     edi, edi
0x18000deb5  lea     rsi, ?acs@@3PAPEAU_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION * near * acs
0x18000debc  xor     ebx, ebx
0x18000debe  mov     rcx, [rsi+rbx*8]; lpCriticalSection
0x18000dec2  call    cs:__imp_InitializeCriticalSection
0x18000dec8  inc     edi
0x18000deca  inc     rbx
0x18000decd  cmp     edi, 7
0x18000ded0  jl      short loc_18000DEBE
0x18000ded2  jz      short loc_18000DEFB
0x18000ded4  xor     ebx, ebx
0x18000ded6  movsxd  rcx, ebx
0x18000ded9  mov     rcx, [rsi+rcx*8]; lpCriticalSection
0x18000dedd  call    cs:__imp_DeleteCriticalSection
0x18000dee3  inc     ebx
0x18000dee5  cmp     ebx, edi
0x18000dee7  jl      short loc_18000DED6
0x18000dee9  xor     eax, eax
0x18000deeb  mov     rbx, [rsp+28h+arg_0]
0x18000def0  mov     rsi, [rsp+28h+arg_8]
0x18000def5  add     rsp, 20h
0x18000def9  pop     rdi
0x18000defa  retn
0x18000defb  mov     eax, 1
0x18000df00  jmp     short loc_18000DEEB
```
