# StateRepository::Database::dal_function_compress(sqlite3_context *,int,sqlite3_value * *)

- ea: `0x1800fdc60`
- end: `0x1800fde96`
- name: `?dal_function_compress@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z`
- size: `566`
- prototype: `void __fastcall(struct sqlite3_context *, int, struct sqlite3_value **)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x180003060`
- `0x180003a40`
- `0x180005700`
- `0x180005980`
- `0x18000a740`
- `0x18000a7f0`
- `0x18000a9b0`
- `0x18000aaf0`
- `0x18000b5f0`
- `0x18000c150`
- `0x18000c240`
- `0x1800dd050`
- `0x1800e4dfe`
- `0x1800f7630`
- `0x1800fc60c`
- `0x1800fdc60`

## string_xrefs

- `0x1800fdd0d`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800fdcee`: `Compress(x[,level]) error: Invalid type for level (%d)`
- `0x1800fdd5c`: `Compress(x[,level]) error: Invalid level (%d)`

## pseudocode

```c
void __fastcall StateRepository::Database::dal_function_compress(
        struct sqlite3_context *a1,
        int a2,
        struct sqlite3_value **a3)
{
  unsigned int v6; // r15d
  int v7; // edi
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  unsigned int v13; // r13d
  char *v14; // rdi
  int i; // r8d
  __int64 v16; // rax
  char v17; // dl
  __int64 v18; // rbx
  int v19; // r14d
  int v20; // r8d
  _DWORD v21[4]; // [rsp+30h] [rbp-79h] BYREF
  __int64 v22; // [rsp+40h] [rbp-69h]
  char v23[112]; // [rsp+50h] [rbp-59h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  if ( (unsigned int)(a2 - 1) > 1 )
  {
    sqlite3_result_error_code(a1, 21);
  }
  else
  {
    if ( (unsigned int)sqlite3_value_type(*a3) == 5 )
      return;
    v6 = -1;
    if ( a2 >= 2 )
    {
      v7 = sqlite3_value_type(a3[1]);
      if ( v7 != 1 )
      {
        memset_0(v23, 0, 0x64u);
        v8 = StringCchPrintfA(v23, 0x64u, "Compress(x[,level]) error: Invalid type for level (%d)", v7);
        if ( v8 < 0 )
        {
          v9 = 3592;
LABEL_7:
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)v9,
            (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
            (const char *)(unsigned int)v8);
          return;
        }
LABEL_8:
        sqlite3_result_error(a1, v23, 0xFFFFFFFFLL);
        return;
      }
      v6 = sqlite3_value_int64(a3[1]);
      if ( v6 > 9 )
      {
        memset_0(v23, 0, 0x64u);
        v8 = StringCchPrintfA(v23, 0x64u, "Compress(x[,level]) error: Invalid level (%d)", 1);
        if ( v8 < 0 )
        {
          v9 = 3602;
          goto LABEL_7;
        }
        goto LABEL_8;
      }
    }
    v10 = (__int64)*a3;
    v21[0] = 0;
    v11 = sqlite3_value_blob(v10);
    v12 = (__int64)*a3;
    v22 = v11;
    v13 = sqlite3_value_bytes(v12);
    v21[0] = v13 + (v13 + 999) / 0x3E8 + 13;
    v14 = (char *)sqlite3_malloc((unsigned int)(v21[0] + 5));
    for ( i = 4; i >= 0; --i )
    {
      v16 = (unsigned int)i;
      v17 = (v13 >> (7 * (4 - i))) & 0x7F;
      *((_BYTE *)&v21[2] + v16) = v17;
    }
    v18 = 0;
    do
    {
      if ( *((_BYTE *)&v21[2] + v18) )
        break;
      v18 = (unsigned int)(v18 + 1);
    }
    while ( (int)v18 < 4 );
    v19 = 0;
    if ( (unsigned int)v18 <= 4 )
    {
      memcpy_0(v14, (char *)&v21[2] + (unsigned int)v18, 5 - (int)v18);
      do
      {
        LODWORD(v18) = v18 + 1;
        ++v19;
      }
      while ( (int)v18 <= 4 );
    }
    v20 = v22;
    v14[v19 - 1] |= 0x80u;
    if ( (unsigned int)compress2(v19 + (int)v14, (unsigned int)v21, v20, v13, v6) )
      sqlite3_free(v14);
    else
      sqlite3_result_blob(a1, v14, (unsigned int)(v19 + v21[0]), sqlite3_free);
  }
}

```

## disassembly

```asm
0x1800fdc60  mov     [rsp-8+arg_8], rbx
0x1800fdc65  push    rbp
0x1800fdc66  push    rsi
0x1800fdc67  push    rdi
0x1800fdc68  push    r12
0x1800fdc6a  push    r13
0x1800fdc6c  push    r14
0x1800fdc6e  push    r15
0x1800fdc70  lea     rbp, [rsp-27h]
0x1800fdc75  sub     rsp, 0D0h
0x1800fdc7c  mov     rax, cs:__security_cookie
0x1800fdc83  xor     rax, rsp
0x1800fdc86  mov     [rbp+57h+var_40], rax
0x1800fdc8a  lea     eax, [rdx-1]
0x1800fdc8d  mov     r14d, 1
0x1800fdc93  mov     rbx, r8
0x1800fdc96  mov     edi, edx
0x1800fdc98  mov     rsi, rcx
0x1800fdc9b  cmp     eax, r14d
0x1800fdc9e  ja      loc_1800FDE65
0x1800fdca4  mov     rcx, [r8]
0x1800fdca7  call    sqlite3_value_type
0x1800fdcac  lea     r12d, [r14+4]
0x1800fdcb0  cmp     eax, r12d
0x1800fdcb3  jz      loc_1800FDE6F
0x1800fdcb9  or      r13d, 0FFFFFFFFh
0x1800fdcbd  mov     r15d, r13d
0x1800fdcc0  cmp     edi, 2
0x1800fdcc3  jl      loc_1800FDD79
0x1800fdcc9  mov     rcx, [rbx+8]
0x1800fdccd  call    sqlite3_value_type
0x1800fdcd2  mov     edi, eax
0x1800fdcd4  cmp     eax, r14d
0x1800fdcd7  jz      short loc_1800FDD35
0x1800fdcd9  lea     ebx, [r14+63h]
0x1800fdcdd  xor     edx, edx; Val
0x1800fdcdf  mov     r8d, ebx; Size
0x1800fdce2  lea     rcx, [rbp+57h+var_B0]; void *
0x1800fdce6  call    memset_0
0x1800fdceb  mov     r9d, edi
0x1800fdcee  lea     r8, aCompressXLevel_0; "Compress(x[,level]) error: Invalid type"...
0x1800fdcf5  mov     edx, ebx; unsigned __int64
0x1800fdcf7  lea     rcx, [rbp+57h+var_B0]; char *
0x1800fdcfb  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800fdd00  test    eax, eax
0x1800fdd02  jns     short loc_1800FDD21
0x1800fdd04  mov     edx, 0E08h; void *
0x1800fdd09  mov     rcx, [rbp+5Fh]; this
0x1800fdd0d  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800fdd14  mov     r9d, eax; char *
0x1800fdd17  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800fdd1c  jmp     loc_1800FDE6F
0x1800fdd21  mov     r8d, r13d
0x1800fdd24  lea     rdx, [rbp+57h+var_B0]
0x1800fdd28  mov     rcx, rsi
0x1800fdd2b  call    sqlite3_result_error
0x1800fdd30  jmp     loc_1800FDE6F
0x1800fdd35  mov     rcx, [rbx+8]
0x1800fdd39  call    sqlite3_value_int64
0x1800fdd3e  mov     r15d, eax
0x1800fdd41  cmp     eax, 9
0x1800fdd44  jbe     short loc_1800FDD79
0x1800fdd46  mov     ebx, 64h ; 'd'
0x1800fdd4b  lea     rcx, [rbp+57h+var_B0]; void *
0x1800fdd4f  mov     r8d, ebx; Size
0x1800fdd52  xor     edx, edx; Val
0x1800fdd54  call    memset_0
0x1800fdd59  mov     r9d, r14d
0x1800fdd5c  lea     r8, aCompressXLevel; "Compress(x[,level]) error: Invalid leve"...
0x1800fdd63  mov     edx, ebx; unsigned __int64
0x1800fdd65  lea     rcx, [rbp+57h+var_B0]; char *
0x1800fdd69  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800fdd6e  test    eax, eax
0x1800fdd70  jns     short loc_1800FDD21
0x1800fdd72  mov     edx, 0E12h
0x1800fdd77  jmp     short loc_1800FDD09
0x1800fdd79  mov     rcx, [rbx]
0x1800fdd7c  mov     [rbp+57h+var_D0], 0
0x1800fdd83  call    sqlite3_value_blob
0x1800fdd88  mov     rcx, [rbx]
0x1800fdd8b  mov     [rbp+57h+var_C0], rax
0x1800fdd8f  call    sqlite3_value_bytes
0x1800fdd94  mov     r13d, eax
0x1800fdd97  lea     ecx, [rax+3E7h]
0x1800fdd9d  mov     eax, 10624DD3h
0x1800fdda2  mul     ecx
0x1800fdda4  shr     edx, 6
0x1800fdda7  lea     ecx, [rdx+0Dh]
0x1800fddaa  add     ecx, r13d
0x1800fddad  mov     [rbp+57h+var_D0], ecx
0x1800fddb0  add     ecx, r12d
0x1800fddb3  call    sqlite3_malloc
0x1800fddb8  mov     r9d, 4
0x1800fddbe  mov     rdi, rax
0x1800fddc1  mov     r8d, r9d
0x1800fddc4  mov     eax, r9d
0x1800fddc7  mov     edx, r13d
0x1800fddca  sub     eax, r8d
0x1800fddcd  imul    ecx, eax, 7
0x1800fddd0  mov     eax, r8d
0x1800fddd3  shr     edx, cl
0x1800fddd5  and     dl, 7Fh
0x1800fddd8  sub     r8d, r14d
0x1800fdddb  mov     [rbp+rax+57h+var_C8], dl
0x1800fdddf  jns     short loc_1800FDDC4
0x1800fdde1  xor     ebx, ebx
0x1800fdde3  cmp     [rbp+rbx+57h+var_C8], 0
0x1800fdde8  jnz     short loc_1800FDDF2
0x1800fddea  add     ebx, r14d
0x1800fdded  cmp     ebx, r9d
0x1800fddf0  jl      short loc_1800FDDE3
0x1800fddf2  xor     r14d, r14d
0x1800fddf5  cmp     ebx, r9d
0x1800fddf8  ja      short loc_1800FDE1B
0x1800fddfa  sub     r12d, ebx
0x1800fddfd  mov     eax, ebx
0x1800fddff  lea     rdx, [rbp+57h+var_C8]
0x1800fde03  movsxd  r8, r12d; Size
0x1800fde06  add     rdx, rax; Src
0x1800fde09  mov     rcx, rdi; void *
0x1800fde0c  call    memcpy_0
0x1800fde11  inc     ebx
0x1800fde13  inc     r14d
0x1800fde16  cmp     ebx, 4
0x1800fde19  jle     short loc_1800FDE11
0x1800fde1b  mov     r8, [rbp+57h+var_C0]
0x1800fde1f  lea     rdx, [rbp+57h+var_D0]
0x1800fde23  movsxd  rax, r14d
0x1800fde26  mov     r9d, r13d
0x1800fde29  mov     [rsp+100h+var_E0], r15d
0x1800fde2e  or      byte ptr [rax+rdi-1], 80h
0x1800fde33  lea     rcx, [rax+rdi]
0x1800fde37  call    compress2
0x1800fde3c  test    eax, eax
0x1800fde3e  jnz     short loc_1800FDE5B
0x1800fde40  mov     r8d, [rbp+57h+var_D0]
0x1800fde44  lea     r9, sqlite3_free
0x1800fde4b  add     r8d, r14d
0x1800fde4e  mov     rdx, rdi
0x1800fde51  mov     rcx, rsi
0x1800fde54  call    sqlite3_result_blob
0x1800fde59  jmp     short loc_1800FDE6F
0x1800fde5b  mov     rcx, rdi
0x1800fde5e  call    sqlite3_free
0x1800fde63  jmp     short loc_1800FDE6F
0x1800fde65  mov     edx, 15h
0x1800fde6a  call    sqlite3_result_error_code
0x1800fde6f  mov     rcx, [rbp+57h+var_40]
0x1800fde73  xor     rcx, rsp; StackCookie
0x1800fde76  call    __security_check_cookie
0x1800fde7b  mov     rbx, [rsp+100h+arg_8]
0x1800fde83  add     rsp, 0D0h
0x1800fde8a  pop     r15
0x1800fde8c  pop     r14
0x1800fde8e  pop     r13
0x1800fde90  pop     r12
0x1800fde92  pop     rdi
0x1800fde93  pop     rsi
0x1800fde94  pop     rbp
0x1800fde95  retn
```
