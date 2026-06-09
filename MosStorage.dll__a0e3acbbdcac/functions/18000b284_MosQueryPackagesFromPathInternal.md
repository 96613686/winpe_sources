# MosQueryPackagesFromPathInternal

- ea: `0x18000b284`
- end: `0x18000b2d4`
- name: `MosQueryPackagesFromPathInternal`
- size: `80`
- prototype: `int __fastcall(__int64, __int64, __int64, int)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000aee0`
- `0x18000b1d0`
- `0x18000b270`

## callees

- `0x18000b284`
- `0x18000b2dc`
- `0x18000b5a4`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000b2b5`

## string_xrefs

- `0x18000b2a8`: `MosQueryPackagesFromPathInternal`

## pseudocode

```c
int __fastcall MosQueryPackagesFromPathInternal(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  int v4; // eax
  int PackagesFromPathInternal_Unified; // eax
  int v6; // r8d

  v4 = 3;
  if ( a4 )
    v4 = a4;
  if ( v4 == 3 )
  {
    PackagesFromPathInternal_Unified = MosQueryPackagesFromPathInternal_Unified();
    if ( PackagesFromPathInternal_Unified < 0 )
    {
      v6 = 95;
      return ZTraceReportPropagationNoThis(PackagesFromPathInternal_Unified, "MosQueryPackagesFromPathInternal", v6);
    }
  }
  else
  {
    PackagesFromPathInternal_Unified = MosQueryPackagesFromPathInternal_Mos();
    if ( PackagesFromPathInternal_Unified < 0 )
    {
      v6 = 99;
      return ZTraceReportPropagationNoThis(PackagesFromPathInternal_Unified, "MosQueryPackagesFromPathInternal", v6);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000b284  sub     rsp, 28h
0x18000b288  test    r9d, r9d
0x18000b28b  mov     eax, 3
0x18000b290  cmovnz  eax, r9d
0x18000b294  cmp     eax, 3
0x18000b297  jnz     short loc_18000B2BC
0x18000b299  call    MosQueryPackagesFromPathInternal_Unified
0x18000b29e  test    eax, eax
0x18000b2a0  jns     short loc_18000B2CD
0x18000b2a2  mov     r8d, 5Fh ; '_'
0x18000b2a8  lea     rdx, aMosquerypackag_3; "MosQueryPackagesFromPathInternal"
0x18000b2af  mov     ecx, eax
0x18000b2b1  add     rsp, 28h
0x18000b2b5  jmp     cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000b2bc  call    MosQueryPackagesFromPathInternal_Mos
0x18000b2c1  test    eax, eax
0x18000b2c3  jns     short loc_18000B2CD
0x18000b2c5  mov     r8d, 63h ; 'c'
0x18000b2cb  jmp     short loc_18000B2A8
0x18000b2cd  xor     eax, eax
0x18000b2cf  add     rsp, 28h
0x18000b2d3  retn
```
