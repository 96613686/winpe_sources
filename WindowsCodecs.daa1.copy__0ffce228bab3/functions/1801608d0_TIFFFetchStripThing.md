# TIFFFetchStripThing

- ea: `0x1801608d0`
- end: `0x180160b24`
- name: `TIFFFetchStripThing`
- size: `596`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180164d70`
- `0x180166a50`

## callees

- `0x180150e00`
- `0x1801565f0`
- `0x18015d110`
- `0x18015d120`
- `0x18015d220`
- `0x18015d4e0`
- `0x1801608d0`
- `0x180162bc0`
- `0x180167290`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_atoi` at `0x1801609c7`
- `api-ms-win-crt-private-l1-1-0!_o_atoi` at `0x1801609c7`
- `api-ms-win-crt-private-l1-1-0!_o_getenv` at `0x1801609b4`
- `api-ms-win-crt-private-l1-1-0!_o_getenv` at `0x1801609b4`

## string_xrefs

- `0x180160943`: `Incompatible type for "%s"`
- `0x18016094c`: `IO error during reading of "%s"`
- `0x180160970`: `Out of memory reading of "%s"`

## pseudocode

```c
__int64 __fastcall TIFFFetchStripThing(__int64 a1, unsigned __int16 *a2, unsigned int a3, _QWORD *a4)
{
  unsigned __int64 v5; // r14
  int v8; // edi
  __int64 v9; // rax
  const char *v10; // r9
  const char *v11; // r8
  __int64 v13; // rdi
  char *v14; // rcx
  unsigned int v15; // eax
  const char *v16; // r9
  unsigned __int64 v17; // rax
  char *v18; // rdi
  __int64 v19; // rax
  void *v20; // rbp
  void *Src; // [rsp+30h] [rbp-48h] BYREF

  v5 = a3;
  v8 = TIFFReadDirEntryLong8ArrayWithLimit(a1, a2, &Src, a3);
  if ( !v8 )
  {
    if ( *((_QWORD *)a2 + 1) >= v5 )
    {
      v18 = (char *)Src;
    }
    else
    {
      v13 = TIFFFieldWithTag(a1, *a2);
      v14 = getenv("LIBTIFF_STRILE_ARRAY_MAX_RESIZE_COUNT");
      v15 = 1000000;
      if ( v14 )
        v15 = atoi(v14);
      if ( v13 )
        v16 = *(const char **)(v13 + 32);
      else
        v16 = "unknown tagname";
      if ( (unsigned int)v5 > v15 )
      {
        TIFFErrorExtR(a1, "TIFFFetchStripThing", "Incorrect count for \"%s\"", v16);
        goto LABEL_23;
      }
      TIFFWarningExtR(a1, "TIFFFetchStripThing", "Incorrect count for \"%s\"; tag ignored", v16);
      if ( 8 * v5 > 0x6400000 )
      {
        v17 = (*(__int64 (__fastcall **)(_QWORD))(a1 + 1216))(*(_QWORD *)(a1 + 1176));
        if ( 8 * v5 > v17 )
        {
          TIFFWarningExtR(
            a1,
            "TIFFFetchStripThing",
            "Requested memory size for StripArray of %llu is greater than filesize %llu. Memory not allocated",
            8 * v5,
            v17);
          TIFFfreeExt(a1, Src);
          return 0;
        }
      }
      v18 = (char *)TIFFCheckMalloc(a1, v5, 8, "for strip array");
      if ( !v18 )
      {
LABEL_23:
        TIFFfreeExt(a1, Src);
        return 0;
      }
      v19 = *((_QWORD *)a2 + 1);
      v20 = Src;
      if ( v19 )
        TIFFmemcpy(v18, Src, 8LL * (unsigned int)v19);
      TIFFmemset(&v18[8 * *((unsigned int *)a2 + 2)], 0, 8LL * (unsigned int)(v5 - *((_DWORD *)a2 + 2)));
      TIFFfreeExt(a1, v20);
    }
    *a4 = v18;
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
      v11 = "Incorrect count for \"%s\"";
      goto LABEL_13;
    case 2:
      v11 = "Incompatible type for \"%s\"";
      goto LABEL_13;
    case 3:
      v11 = "IO error during reading of \"%s\"";
      goto LABEL_13;
    case 4:
      v11 = "Incorrect value for \"%s\"";
      goto LABEL_13;
    case 5:
      v11 = "Cannot handle different values per sample for \"%s\"";
      goto LABEL_13;
    case 6:
      v11 = "Sanity check on size of \"%s\" value failed";
      goto LABEL_13;
    case 7:
      v11 = "Out of memory reading of \"%s\"";
LABEL_13:
      TIFFErrorExtR(a1, "TIFFFetchStripThing", v11, v10);
      break;
    default:
      return 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1801608d0  push    rbx
0x1801608d2  push    rbp
0x1801608d3  push    rsi
0x1801608d4  push    rdi
0x1801608d5  push    r14
0x1801608d7  push    r15
0x1801608d9  sub     rsp, 48h
0x1801608dd  mov     r15, r9
0x1801608e0  mov     r14d, r8d
0x1801608e3  mov     r9d, r8d
0x1801608e6  mov     rsi, rdx
0x1801608e9  lea     r8, [rsp+78h+Src]
0x1801608ee  mov     rbx, rcx
0x1801608f1  call    TIFFReadDirEntryLong8ArrayWithLimit
0x1801608f6  mov     edi, eax
0x1801608f8  test    eax, eax
0x1801608fa  jz      loc_180160995
0x180160900  movzx   edx, word ptr [rsi]
0x180160903  mov     rcx, rbx
0x180160906  call    TIFFFieldWithTag
0x18016090b  test    rax, rax
0x18016090e  jz      short loc_180160916
0x180160910  mov     r9, [rax+20h]
0x180160914  jmp     short loc_18016091D
0x180160916  lea     r9, aUnknownTagname; "unknown tagname"
0x18016091d  lea     eax, [rdi-1]; switch 7 cases
0x180160920  cmp     eax, 6
0x180160923  ja      short def_180160938; jumptable 0000000180160938 default case
0x180160925  lea     rdx, __ImageBase
0x18016092c  cdqe
0x18016092e  mov     ecx, ds:(jpt_180160938 - 180000000h)[rdx+rax*4]
0x180160935  add     rcx, rdx
0x180160938  jmp     rcx; switch jump
0x18016093a  lea     r8, aIncorrectCount_1; jumptable 0000000180160938 case 1
0x180160941  jmp     short loc_180160977
0x180160943  lea     r8, aIncompatibleTy_0; jumptable 0000000180160938 case 2
0x18016094a  jmp     short loc_180160977
0x18016094c  lea     r8, aIoErrorDuringR_0; jumptable 0000000180160938 case 3
0x180160953  jmp     short loc_180160977
0x180160955  lea     r8, aIncorrectValue; jumptable 0000000180160938 case 4
0x18016095c  jmp     short loc_180160977
0x18016095e  lea     r8, aCannotHandleDi; jumptable 0000000180160938 case 5
0x180160965  jmp     short loc_180160977
0x180160967  lea     r8, aSanityCheckOnS; jumptable 0000000180160938 case 6
0x18016096e  jmp     short loc_180160977
0x180160970  lea     r8, aOutOfMemoryRea; jumptable 0000000180160938 case 7
0x180160977  lea     rdx, aTifffetchstrip; "TIFFFetchStripThing"
0x18016097e  mov     rcx, rbx
0x180160981  call    TIFFErrorExtR
0x180160986  xor     eax, eax; jumptable 0000000180160938 default case
0x180160988  add     rsp, 48h
0x18016098c  pop     r15
0x18016098e  pop     r14
0x180160990  pop     rdi
0x180160991  pop     rsi
0x180160992  pop     rbp
0x180160993  pop     rbx
0x180160994  retn
0x180160995  cmp     [rsi+8], r14
0x180160999  jnb     loc_180160AEE
0x18016099f  movzx   edx, word ptr [rsi]
0x1801609a2  mov     rcx, rbx
0x1801609a5  call    TIFFFieldWithTag
0x1801609aa  lea     rcx, VarName; "LIBTIFF_STRILE_ARRAY_MAX_RESIZE_COUNT"
0x1801609b1  mov     rdi, rax
0x1801609b4  call    cs:__imp_getenv
0x1801609ba  mov     rcx, rax; String
0x1801609bd  mov     eax, 0F4240h
0x1801609c2  test    rcx, rcx
0x1801609c5  jz      short loc_1801609CD
0x1801609c7  call    cs:__imp_atoi
0x1801609cd  test    rdi, rdi
0x1801609d0  jz      short loc_1801609D8
0x1801609d2  mov     r9, [rdi+20h]
0x1801609d6  jmp     short loc_1801609DF
0x1801609d8  lea     r9, aUnknownTagname; "unknown tagname"
0x1801609df  lea     rdx, aTifffetchstrip; "TIFFFetchStripThing"
0x1801609e6  mov     rcx, rbx
0x1801609e9  cmp     r14d, eax
0x1801609ec  jbe     short loc_180160A16
0x1801609ee  lea     r8, aIncorrectCount_1; "Incorrect count for \"%s\""
0x1801609f5  call    TIFFErrorExtR
0x1801609fa  mov     rdx, [rsp+78h+Src]
0x1801609ff  mov     rcx, rbx
0x180160a02  call    _TIFFfreeExt
0x180160a07  xor     eax, eax
0x180160a09  add     rsp, 48h
0x180160a0d  pop     r15
0x180160a0f  pop     r14
0x180160a11  pop     rdi
0x180160a12  pop     rsi
0x180160a13  pop     rbp
0x180160a14  pop     rbx
0x180160a15  retn
0x180160a16  lea     r8, aIncorrectCount_0; "Incorrect count for \"%s\"; tag ignored"
0x180160a1d  call    TIFFWarningExtR
0x180160a22  lea     rdi, ds:0[r14*8]
0x180160a2a  cmp     rdi, 6400000h
0x180160a31  jbe     short loc_180160A85
0x180160a33  mov     rcx, [rbx+498h]
0x180160a3a  mov     rax, [rbx+4C0h]
0x180160a41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180160a46  cmp     rdi, rax
0x180160a49  jbe     short loc_180160A85
0x180160a4b  mov     r9, rdi
0x180160a4e  mov     [rsp+78h+var_58], rax
0x180160a53  lea     r8, aRequestedMemor_2; "Requested memory size for StripArray of"...
0x180160a5a  mov     rcx, rbx
0x180160a5d  lea     rdx, aTifffetchstrip; "TIFFFetchStripThing"
0x180160a64  call    TIFFWarningExtR
0x180160a69  mov     rdx, [rsp+78h+Src]
0x180160a6e  mov     rcx, rbx
0x180160a71  call    _TIFFfreeExt
0x180160a76  xor     eax, eax
0x180160a78  add     rsp, 48h
0x180160a7c  pop     r15
0x180160a7e  pop     r14
0x180160a80  pop     rdi
0x180160a81  pop     rsi
0x180160a82  pop     rbp
0x180160a83  pop     rbx
0x180160a84  retn
0x180160a85  lea     r9, aForStripArray; "for strip array"
0x180160a8c  mov     r8d, 8
0x180160a92  mov     rdx, r14
0x180160a95  mov     rcx, rbx
0x180160a98  call    _TIFFCheckMalloc
0x180160a9d  mov     rdi, rax
0x180160aa0  test    rax, rax
0x180160aa3  jz      loc_1801609FA
0x180160aa9  mov     rax, [rsi+8]
0x180160aad  mov     rbp, [rsp+78h+Src]
0x180160ab2  test    rax, rax
0x180160ab5  jz      short loc_180160AC9
0x180160ab7  mov     r8d, eax
0x180160aba  mov     rdx, rbp; Src
0x180160abd  shl     r8, 3; Size
0x180160ac1  mov     rcx, rdi; void *
0x180160ac4  call    _TIFFmemcpy
0x180160ac9  mov     eax, [rsi+8]
0x180160acc  xor     edx, edx; Val
0x180160ace  sub     r14d, eax
0x180160ad1  mov     r8d, r14d
0x180160ad4  shl     r8, 3; Size
0x180160ad8  lea     rcx, [rdi+rax*8]; void *
0x180160adc  call    _TIFFmemset
0x180160ae1  mov     rdx, rbp
0x180160ae4  mov     rcx, rbx
0x180160ae7  call    _TIFFfreeExt
0x180160aec  jmp     short loc_180160AF3
0x180160aee  mov     rdi, [rsp+78h+Src]
0x180160af3  mov     [r15], rdi
0x180160af6  mov     eax, 1
0x180160afb  add     rsp, 48h
0x180160aff  pop     r15
0x180160b01  pop     r14
0x180160b03  pop     rdi
0x180160b04  pop     rsi
0x180160b05  pop     rbp
0x180160b06  pop     rbx
0x180160b07  retn
```
