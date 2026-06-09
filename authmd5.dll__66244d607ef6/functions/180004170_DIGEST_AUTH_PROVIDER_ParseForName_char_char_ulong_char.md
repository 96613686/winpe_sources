# DIGEST_AUTH_PROVIDER::ParseForName(char *,char * *,ulong,char * *)

- ea: `0x180004170`
- end: `0x180004296`
- name: `?ParseForName@DIGEST_AUTH_PROVIDER@@QEAAJPEADPEAPEADK1@Z`
- size: `294`
- prototype: `__int64 __fastcall(DIGEST_AUTH_PROVIDER *this, char *, char **, __int64, char **)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001e00`

## callees

- `0x180004170`

## import_xrefs

- `msvcrt!_stricmp` at `0x18000424c`
- `msvcrt!_stricmp` at `0x18000424c`
- `msvcrt!isspace` at `0x1800041a1`
- `msvcrt!isspace` at `0x1800041a1`

## pseudocode

```c
__int64 __fastcall DIGEST_AUTH_PROVIDER::ParseForName(
        DIGEST_AUTH_PROVIDER *this,
        char *a2,
        char **a3,
        __int64 a4,
        char **a5)
{
  bool v5; // zf
  char *v6; // r14
  int v7; // edi
  unsigned __int64 v8; // rax
  char *v9; // rsi
  char *i; // rsi
  char v11; // al
  char *k; // rbx
  char j; // al
  __int64 v14; // rcx
  __int64 v15; // rbp

  v5 = *a2 == 0;
  v6 = a2;
  v7 = 1;
  *a5 = 0;
  if ( !v5 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        if ( !isspace((unsigned __int8)*v6) )
        {
          LODWORD(v8) = (unsigned __int8)*v6;
          if ( *v6 != 44 )
            break;
        }
        ++v6;
      }
      v9 = v6;
      while ( (_BYTE)v8 && (_BYTE)v8 != 61 && (_BYTE)v8 != 32 )
        LOBYTE(v8) = *++v9;
      if ( !*v9 )
        break;
      *v9 = 0;
      for ( i = v9 + 1; ; ++i )
      {
        v11 = *i;
        if ( !*i || v11 != 61 && v11 != 32 )
          break;
      }
      LOBYTE(v8) = *i;
      if ( *i == 34 )
      {
        k = ++i;
        for ( j = *i; j && j != 34; j = *k )
          ++k;
        if ( *k != 34 )
          k = 0;
      }
      else
      {
        for ( k = i; (_BYTE)v8; LOBYTE(v8) = *k )
        {
          if ( (unsigned __int8)v8 <= 0x2Cu )
          {
            v14 = 0x100500000000LL;
            if ( _bittest64(&v14, v8) )
              break;
          }
          ++k;
        }
      }
      if ( k )
      {
        v15 = 0;
        while ( _stricmp((const char *)(&SSPI_DIGEST_AUTH_NAMES)[v15], v6) )
        {
          v15 = (unsigned int)(v15 + 1);
          if ( (_DWORD)v15 )
            goto LABEL_34;
        }
        a5[v15] = i;
LABEL_34:
        if ( *k )
          *k++ = 0;
        v6 = k;
      }
      if ( !*v6 )
        return v7 == 0 ? 0x80070490 : 0;
    }
    v7 = 0;
  }
  return v7 == 0 ? 0x80070490 : 0;
}

```

## disassembly

```asm
0x180004170  push    rbx
0x180004172  push    rbp
0x180004173  push    rsi
0x180004174  push    rdi
0x180004175  push    r14
0x180004177  push    r15
0x180004179  sub     rsp, 28h
0x18000417d  cmp     byte ptr [rdx], 0
0x180004180  mov     r14, rdx
0x180004183  mov     r15, [rsp+58h+arg_20]
0x18000418b  mov     edi, 1
0x180004190  mov     qword ptr [r15], 0
0x180004197  jz      loc_18000427E
0x18000419d  movzx   ecx, byte ptr [r14]; C
0x1800041a1  call    cs:__imp_isspace
0x1800041a7  test    eax, eax
0x1800041a9  jnz     short loc_1800041B2
0x1800041ab  mov     al, [r14]
0x1800041ae  cmp     al, 2Ch ; ','
0x1800041b0  jnz     short loc_1800041B7
0x1800041b2  add     r14, rdi
0x1800041b5  jmp     short loc_18000419D
0x1800041b7  mov     rsi, r14
0x1800041ba  jmp     short loc_1800041C9
0x1800041bc  cmp     al, 3Dh ; '='
0x1800041be  jz      short loc_1800041CD
0x1800041c0  cmp     al, 20h ; ' '
0x1800041c2  jz      short loc_1800041CD
0x1800041c4  add     rsi, rdi
0x1800041c7  mov     al, [rsi]
0x1800041c9  test    al, al
0x1800041cb  jnz     short loc_1800041BC
0x1800041cd  cmp     byte ptr [rsi], 0
0x1800041d0  jz      loc_18000427C
0x1800041d6  mov     byte ptr [rsi], 0
0x1800041d9  inc     rsi
0x1800041dc  jmp     short loc_1800041E9
0x1800041de  cmp     al, 3Dh ; '='
0x1800041e0  jz      short loc_1800041E6
0x1800041e2  cmp     al, 20h ; ' '
0x1800041e4  jnz     short loc_1800041EF
0x1800041e6  add     rsi, rdi
0x1800041e9  mov     al, [rsi]
0x1800041eb  test    al, al
0x1800041ed  jnz     short loc_1800041DE
0x1800041ef  mov     al, [rsi]
0x1800041f1  cmp     al, 22h ; '"'
0x1800041f3  jnz     short loc_180004215
0x1800041f5  add     rsi, rdi
0x1800041f8  mov     rbx, rsi
0x1800041fb  mov     al, [rsi]
0x1800041fd  jmp     short loc_180004208
0x1800041ff  cmp     al, 22h ; '"'
0x180004201  jz      short loc_18000420C
0x180004203  add     rbx, rdi
0x180004206  mov     al, [rbx]
0x180004208  test    al, al
0x18000420a  jnz     short loc_1800041FF
0x18000420c  cmp     byte ptr [rbx], 22h ; '"'
0x18000420f  jz      short loc_180004237
0x180004211  xor     ebx, ebx
0x180004213  jmp     short loc_180004237
0x180004215  mov     rbx, rsi
0x180004218  jmp     short loc_180004233
0x18000421a  cmp     al, 2Ch ; ','
0x18000421c  ja      short loc_18000422E
0x18000421e  mov     rcx, 100500000000h
0x180004228  bt      rcx, rax
0x18000422c  jb      short loc_180004237
0x18000422e  add     rbx, rdi
0x180004231  mov     al, [rbx]
0x180004233  test    al, al
0x180004235  jnz     short loc_18000421A
0x180004237  test    rbx, rbx
0x18000423a  jz      short loc_180004270
0x18000423c  xor     ebp, ebp
0x18000423e  lea     rax, ?SSPI_DIGEST_AUTH_NAMES@@3PAPEADA; char * near * SSPI_DIGEST_AUTH_NAMES
0x180004245  mov     rdx, r14; String2
0x180004248  mov     rcx, [rax+rbp*8]; String1
0x18000424c  call    cs:__imp__stricmp
0x180004252  test    eax, eax
0x180004254  jz      short loc_18000425E
0x180004256  add     ebp, edi
0x180004258  cmp     ebp, edi
0x18000425a  jb      short loc_18000423E
0x18000425c  jmp     short loc_180004262
0x18000425e  mov     [r15+rbp*8], rsi
0x180004262  cmp     byte ptr [rbx], 0
0x180004265  jz      short loc_18000426D
0x180004267  mov     byte ptr [rbx], 0
0x18000426a  add     rbx, rdi
0x18000426d  mov     r14, rbx
0x180004270  cmp     byte ptr [r14], 0
0x180004274  jnz     loc_18000419D
0x18000427a  jmp     short loc_18000427E
0x18000427c  xor     edi, edi
0x18000427e  neg     edi
0x180004280  sbb     eax, eax
0x180004282  not     eax
0x180004284  and     eax, 80070490h
0x180004289  add     rsp, 28h
0x18000428d  pop     r15
0x18000428f  pop     r14
0x180004291  pop     rdi
0x180004292  pop     rsi
0x180004293  pop     rbp
0x180004294  pop     rbx
0x180004295  retn
```
