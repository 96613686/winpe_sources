# MSCryptGetRngProperty

- ea: `0x180065540`
- end: `0x180065634`
- name: `MSCryptGetRngProperty`
- size: `244`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000ecb0`
- `0x1800496a0`
- `0x180065540`
- `0x18007f765`

## import_xrefs

- `ntdll!wcscpy_s` at `0x180065615`
- `ntdll!wcscpy_s` at `0x180065615`

## string_xrefs

- `0x18006555d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\rng.c`

## pseudocode

```c
__int64 __fastcall MSCryptGetRngProperty(
        __int64 a1,
        __int64 a2,
        wchar_t *a3,
        unsigned int a4,
        unsigned int *a5,
        int a6)
{
  unsigned __int64 v6; // rdi
  unsigned int v8; // ebx
  const wchar_t *v9; // rdx
  __int64 v10; // rbx
  const wchar_t *v11; // r8
  __int64 v12; // rax
  unsigned int v13; // ecx

  v6 = a4;
  if ( a6 )
  {
    v8 = -1073741811;
    DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\rng.c", 275);
  }
  else
  {
    v10 = validateMSCryptRngHandle();
    if ( v10 )
    {
      if ( wcscmp_0(L"AlgorithmName", v9) )
        return (unsigned int)-1073741637;
      if ( *(_DWORD *)(v10 + 8) == 327681 )
      {
        v11 = L"RNG";
      }
      else if ( *(_DWORD *)(v10 + 8) == 327682 )
      {
        v11 = L"FIPS186DSARNG";
      }
      else
      {
        v11 = L"DUALECRNG";
        if ( *(_DWORD *)(v10 + 8) != 327683 )
          v11 = 0;
      }
      v12 = -1;
      do
        ++v12;
      while ( v11[v12] );
      v13 = 2 * v12 + 2;
      *a5 = v13;
      if ( a3 )
      {
        if ( (unsigned int)v6 < v13 )
          return (unsigned int)-1073741789;
        wcscpy_s(a3, v6 >> 1, v11);
      }
      return 0;
    }
    else
    {
      return (unsigned int)-1073741816;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180065540  push    rbx
0x180065542  push    rbp
0x180065543  push    rsi
0x180065544  push    rdi
0x180065545  sub     rsp, 28h
0x180065549  xor     ebp, ebp
0x18006554b  mov     edi, r9d
0x18006554e  mov     rsi, r8
0x180065551  cmp     [rsp+48h+arg_28], ebp
0x180065555  jz      short loc_18006557F
0x180065557  mov     r9d, 113h
0x18006555d  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180065564  lea     rdx, aStatus; "Status"
0x18006556b  mov     ecx, 0C000000Dh
0x180065570  mov     ebx, 0C000000Dh
0x180065575  call    DebugTraceError
0x18006557a  jmp     loc_180065628
0x18006557f  call    validateMSCryptRngHandle
0x180065584  mov     rbx, rax
0x180065587  test    rax, rax
0x18006558a  jnz     short loc_180065596
0x18006558c  mov     ebx, 0C0000008h
0x180065591  jmp     loc_180065628
0x180065596  lea     rcx, aAlgorithmname; "AlgorithmName"
0x18006559d  call    wcscmp_0
0x1800655a2  test    eax, eax
0x1800655a4  jnz     short loc_180065623
0x1800655a6  cmp     dword ptr [rbx+8], 50001h
0x1800655ad  jnz     short loc_1800655B8
0x1800655af  lea     r8, aRng; "RNG"
0x1800655b6  jmp     short loc_1800655DC
0x1800655b8  cmp     dword ptr [rbx+8], 50002h
0x1800655bf  jnz     short loc_1800655CA
0x1800655c1  lea     r8, aFips186dsarng; "FIPS186DSARNG"
0x1800655c8  jmp     short loc_1800655DC
0x1800655ca  cmp     dword ptr [rbx+8], 50003h
0x1800655d1  lea     r8, aDualecrng; "DUALECRNG"
0x1800655d8  cmovnz  r8, rbp; Source
0x1800655dc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800655e0  inc     rax
0x1800655e3  cmp     [r8+rax*2], bp
0x1800655e8  jnz     short loc_1800655E0
0x1800655ea  lea     ecx, ds:2[rax*2]
0x1800655f1  mov     rax, [rsp+48h+arg_20]
0x1800655f6  mov     [rax], ecx
0x1800655f8  test    rsi, rsi
0x1800655fb  jnz     short loc_180065601
0x1800655fd  mov     ebx, ebp
0x1800655ff  jmp     short loc_180065628
0x180065601  cmp     edi, ecx
0x180065603  jnb     short loc_18006560C
0x180065605  mov     ebx, 0C0000023h
0x18006560a  jmp     short loc_180065628
0x18006560c  mov     rdx, rdi
0x18006560f  mov     rcx, rsi; Destination
0x180065612  shr     rdx, 1; SizeInWords
0x180065615  call    cs:__imp_wcscpy_s
0x18006561c  nop     dword ptr [rax+rax+00h]
0x180065621  jmp     short loc_1800655FD
0x180065623  mov     ebx, 0C00000BBh
0x180065628  mov     eax, ebx
0x18006562a  add     rsp, 28h
0x18006562e  pop     rdi
0x18006562f  pop     rsi
0x180065630  pop     rbp
0x180065631  pop     rbx
0x180065632  retn
```
