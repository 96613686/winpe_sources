# TIFFFetchStripThing

- ea: `0x18015d9d0`
- end: `0x18015dc24`
- name: `TIFFFetchStripThing`
- size: `596`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180161e70`
- `0x180163b50`

## callees

- `0x18014df00`
- `0x1801536f0`
- `0x18015a210`
- `0x18015a220`
- `0x18015a320`
- `0x18015a5e0`
- `0x18015d9d0`
- `0x18015fcc0`
- `0x180164390`
- `0x1801ca010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_atoi` at `0x18015dac7`
- `api-ms-win-crt-private-l1-1-0!_o_atoi` at `0x18015dac7`
- `api-ms-win-crt-private-l1-1-0!_o_getenv` at `0x18015dab4`
- `api-ms-win-crt-private-l1-1-0!_o_getenv` at `0x18015dab4`

## string_xrefs

- `0x18015da43`: `Incompatible type for "%s"`
- `0x18015da4c`: `IO error during reading of "%s"`
- `0x18015da70`: `Out of memory reading of "%s"`

## pseudocode

```c
__int64 __fastcall TIFFFetchStripThing(__int64 a1, unsigned __int16 *a2, unsigned int a3, _QWORD *a4)
{
  unsigned __int64 v5; // r14
  int v8; // edi
  __int64 v9; // rax
  const char *v10; // r9
  __int64 v12; // rdi
  char *v13; // rcx
  unsigned int v14; // eax
  const char *v15; // r9
  unsigned __int64 v16; // rax
  char *v17; // rdi
  __int64 v18; // rax
  void *Src; // [rsp+30h] [rbp-48h] BYREF

  v5 = a3;
  v8 = TIFFReadDirEntryLong8ArrayWithLimit(a1, a2, &Src, a3);
  if ( !v8 )
  {
    if ( *((_QWORD *)a2 + 1) >= v5 )
    {
      v17 = (char *)Src;
    }
    else
    {
      v12 = TIFFFieldWithTag(a1, *a2);
      v13 = getenv("LIBTIFF_STRILE_ARRAY_MAX_RESIZE_COUNT");
      v14 = 1000000;
      if ( v13 )
        v14 = atoi(v13);
      if ( v12 )
        v15 = *(const char **)(v12 + 32);
      else
        v15 = "unknown tagname";
      if ( (unsigned int)v5 > v14 )
      {
        TIFFErrorExtR(a1, "TIFFFetchStripThing", "Incorrect count for \"%s\"", v15);
        goto LABEL_22;
      }
      TIFFWarningExtR(a1, "TIFFFetchStripThing", "Incorrect count for \"%s\"; tag ignored", v15);
      if ( 8 * v5 > 0x6400000 )
      {
        v16 = (*(__int64 (__fastcall **)(_QWORD))(a1 + 1216))(*(_QWORD *)(a1 + 1176));
        if ( 8 * v5 > v16 )
        {
          TIFFWarningExtR(
            a1,
            "TIFFFetchStripThing",
            "Requested memory size for StripArray of %llu is greater than filesize %llu. Memory not allocated",
            8 * v5,
            v16);
          TIFFfreeExt(a1);
          return 0;
        }
      }
      v17 = (char *)TIFFCheckMalloc(a1, v5, 8, "for strip array");
      if ( !v17 )
      {
LABEL_22:
        TIFFfreeExt(a1);
        return 0;
      }
      v18 = *((_QWORD *)a2 + 1);
      if ( v18 )
        TIFFmemcpy(v17, Src, 8LL * (unsigned int)v18);
      TIFFmemset(&v17[8 * *((unsigned int *)a2 + 2)], 0, 8LL * (unsigned int)(v5 - *((_DWORD *)a2 + 2)));
      TIFFfreeExt(a1);
    }
    *a4 = v17;
    return 1;
  }
  v9 = TIFFFieldWithTag(a1, *a2);
  if ( v9 )
    v10 = *(const char **)(v9 + 32);
  else
    v10 = "unknown tagname";
  switch ( v8 )
  {
    case 1:
      TIFFErrorExtR(a1, "TIFFFetchStripThing", "Incorrect count for \"%s\"", v10);
      break;
    case 2:
      TIFFErrorExtR(a1, "TIFFFetchStripThing", "Incompatible type for \"%s\"", v10);
      break;
    case 3:
      TIFFErrorExtR(a1, "TIFFFetchStripThing", "IO error during reading of \"%s\"", v10);
      break;
    case 4:
      TIFFErrorExtR(a1, "TIFFFetchStripThing", "Incorrect value for \"%s\"", v10);
      break;
    case 5:
      TIFFErrorExtR(a1, "TIFFFetchStripThing", "Cannot handle different values per sample for \"%s\"", v10);
      break;
    case 6:
      TIFFErrorExtR(a1, "TIFFFetchStripThing", "Sanity check on size of \"%s\" value failed", v10);
      break;
    case 7:
      TIFFErrorExtR(a1, "TIFFFetchStripThing", "Out of memory reading of \"%s\"", v10);
      break;
    default:
      return 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18015d9d0  push    rbx
0x18015d9d2  push    rbp
0x18015d9d3  push    rsi
0x18015d9d4  push    rdi
0x18015d9d5  push    r14
0x18015d9d7  push    r15
0x18015d9d9  sub     rsp, 48h
0x18015d9dd  mov     r15, r9
0x18015d9e0  mov     r14d, r8d
0x18015d9e3  mov     r9d, r8d
0x18015d9e6  mov     rsi, rdx
0x18015d9e9  lea     r8, [rsp+78h+Src]
0x18015d9ee  mov     rbx, rcx
0x18015d9f1  call    TIFFReadDirEntryLong8ArrayWithLimit
0x18015d9f6  mov     edi, eax
0x18015d9f8  test    eax, eax
0x18015d9fa  jz      loc_18015DA95
0x18015da00  movzx   edx, word ptr [rsi]
0x18015da03  mov     rcx, rbx
0x18015da06  call    TIFFFieldWithTag
0x18015da0b  test    rax, rax
0x18015da0e  jz      short loc_18015DA16
0x18015da10  mov     r9, [rax+20h]
0x18015da14  jmp     short loc_18015DA1D
0x18015da16  lea     r9, aUnknownTagname; "unknown tagname"
0x18015da1d  lea     eax, [rdi-1]; switch 7 cases
0x18015da20  cmp     eax, 6
0x18015da23  ja      short def_18015DA38; jumptable 000000018015DA38 default case
0x18015da25  lea     rdx, __ImageBase
0x18015da2c  cdqe
0x18015da2e  mov     ecx, ds:(jpt_18015DA38 - 180000000h)[rdx+rax*4]
0x18015da35  add     rcx, rdx
0x18015da38  jmp     rcx; switch jump
0x18015da3a  lea     r8, aIncorrectCount_1; jumptable 000000018015DA38 case 1
0x18015da41  jmp     short loc_18015DA77
0x18015da43  lea     r8, aIncompatibleTy_0; jumptable 000000018015DA38 case 2
0x18015da4a  jmp     short loc_18015DA77
0x18015da4c  lea     r8, aIoErrorDuringR_0; jumptable 000000018015DA38 case 3
0x18015da53  jmp     short loc_18015DA77
0x18015da55  lea     r8, aIncorrectValue; jumptable 000000018015DA38 case 4
0x18015da5c  jmp     short loc_18015DA77
0x18015da5e  lea     r8, aCannotHandleDi; jumptable 000000018015DA38 case 5
0x18015da65  jmp     short loc_18015DA77
0x18015da67  lea     r8, aSanityCheckOnS; jumptable 000000018015DA38 case 6
0x18015da6e  jmp     short loc_18015DA77
0x18015da70  lea     r8, aOutOfMemoryRea; jumptable 000000018015DA38 case 7
0x18015da77  lea     rdx, aTifffetchstrip; "TIFFFetchStripThing"
0x18015da7e  mov     rcx, rbx
0x18015da81  call    TIFFErrorExtR
0x18015da86  xor     eax, eax; jumptable 000000018015DA38 default case
0x18015da88  add     rsp, 48h
0x18015da8c  pop     r15
0x18015da8e  pop     r14
0x18015da90  pop     rdi
0x18015da91  pop     rsi
0x18015da92  pop     rbp
0x18015da93  pop     rbx
0x18015da94  retn
0x18015da95  cmp     [rsi+8], r14
0x18015da99  jnb     loc_18015DBEE
0x18015da9f  movzx   edx, word ptr [rsi]
0x18015daa2  mov     rcx, rbx
0x18015daa5  call    TIFFFieldWithTag
0x18015daaa  lea     rcx, VarName; "LIBTIFF_STRILE_ARRAY_MAX_RESIZE_COUNT"
0x18015dab1  mov     rdi, rax
0x18015dab4  call    cs:__imp_getenv
0x18015daba  mov     rcx, rax; String
0x18015dabd  mov     eax, 0F4240h
0x18015dac2  test    rcx, rcx
0x18015dac5  jz      short loc_18015DACD
0x18015dac7  call    cs:__imp_atoi
0x18015dacd  test    rdi, rdi
0x18015dad0  jz      short loc_18015DAD8
0x18015dad2  mov     r9, [rdi+20h]
0x18015dad6  jmp     short loc_18015DADF
0x18015dad8  lea     r9, aUnknownTagname; "unknown tagname"
0x18015dadf  lea     rdx, aTifffetchstrip; "TIFFFetchStripThing"
0x18015dae6  mov     rcx, rbx
0x18015dae9  cmp     r14d, eax
0x18015daec  jbe     short loc_18015DB16
0x18015daee  lea     r8, aIncorrectCount_1; "Incorrect count for \"%s\""
0x18015daf5  call    TIFFErrorExtR
0x18015dafa  mov     rdx, [rsp+78h+Src]
0x18015daff  mov     rcx, rbx
0x18015db02  call    _TIFFfreeExt
0x18015db07  xor     eax, eax
0x18015db09  add     rsp, 48h
0x18015db0d  pop     r15
0x18015db0f  pop     r14
0x18015db11  pop     rdi
0x18015db12  pop     rsi
0x18015db13  pop     rbp
0x18015db14  pop     rbx
0x18015db15  retn
0x18015db16  lea     r8, aIncorrectCount_0; "Incorrect count for \"%s\"; tag ignored"
0x18015db1d  call    TIFFWarningExtR
0x18015db22  lea     rdi, ds:0[r14*8]
0x18015db2a  cmp     rdi, 6400000h
0x18015db31  jbe     short loc_18015DB85
0x18015db33  mov     rcx, [rbx+498h]
0x18015db3a  mov     rax, [rbx+4C0h]
0x18015db41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015db46  cmp     rdi, rax
0x18015db49  jbe     short loc_18015DB85
0x18015db4b  mov     r9, rdi
0x18015db4e  mov     [rsp+78h+var_58], rax
0x18015db53  lea     r8, aRequestedMemor_2; "Requested memory size for StripArray of"...
0x18015db5a  mov     rcx, rbx
0x18015db5d  lea     rdx, aTifffetchstrip; "TIFFFetchStripThing"
0x18015db64  call    TIFFWarningExtR
0x18015db69  mov     rdx, [rsp+78h+Src]
0x18015db6e  mov     rcx, rbx
0x18015db71  call    _TIFFfreeExt
0x18015db76  xor     eax, eax
0x18015db78  add     rsp, 48h
0x18015db7c  pop     r15
0x18015db7e  pop     r14
0x18015db80  pop     rdi
0x18015db81  pop     rsi
0x18015db82  pop     rbp
0x18015db83  pop     rbx
0x18015db84  retn
0x18015db85  lea     r9, aForStripArray; "for strip array"
0x18015db8c  mov     r8d, 8
0x18015db92  mov     rdx, r14
0x18015db95  mov     rcx, rbx
0x18015db98  call    _TIFFCheckMalloc
0x18015db9d  mov     rdi, rax
0x18015dba0  test    rax, rax
0x18015dba3  jz      loc_18015DAFA
0x18015dba9  mov     rax, [rsi+8]
0x18015dbad  mov     rbp, [rsp+78h+Src]
0x18015dbb2  test    rax, rax
0x18015dbb5  jz      short loc_18015DBC9
0x18015dbb7  mov     r8d, eax
0x18015dbba  mov     rdx, rbp; Src
0x18015dbbd  shl     r8, 3; Size
0x18015dbc1  mov     rcx, rdi; void *
0x18015dbc4  call    _TIFFmemcpy
0x18015dbc9  mov     eax, [rsi+8]
0x18015dbcc  xor     edx, edx; Val
0x18015dbce  sub     r14d, eax
0x18015dbd1  mov     r8d, r14d
0x18015dbd4  shl     r8, 3; Size
0x18015dbd8  lea     rcx, [rdi+rax*8]; void *
0x18015dbdc  call    _TIFFmemset
0x18015dbe1  mov     rdx, rbp
0x18015dbe4  mov     rcx, rbx
0x18015dbe7  call    _TIFFfreeExt
0x18015dbec  jmp     short loc_18015DBF3
0x18015dbee  mov     rdi, [rsp+78h+Src]
0x18015dbf3  mov     [r15], rdi
0x18015dbf6  mov     eax, 1
0x18015dbfb  add     rsp, 48h
0x18015dbff  pop     r15
0x18015dc01  pop     r14
0x18015dc03  pop     rdi
0x18015dc04  pop     rsi
0x18015dc05  pop     rbp
0x18015dc06  pop     rbx
0x18015dc07  retn
```
