# GetMlKemBlobInfo

- ea: `0x180064130`
- end: `0x1800641e0`
- name: `GetMlKemBlobInfo`
- size: `176`
- prototype: `__int64 __fastcall(char *, wchar_t ***)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180063d2c`
- `0x18006445c`

## callees

- `0x18000ecb0`
- `0x180064130`

## string_xrefs

- `0x1800641a9`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\kem.c`

## pseudocode

```c
__int64 __fastcall GetMlKemBlobInfo(char *a1, wchar_t ***a2)
{
  wchar_t **v2; // r8
  __int64 i; // r9
  __int64 v6; // rcx
  wchar_t *v7; // rdx
  char *v8; // rax
  char *v9; // rdx
  int v10; // r11d
  int v11; // r10d
  unsigned int v12; // ebx

  v2 = 0;
  for ( i = 0; i != 3; ++i )
  {
    v6 = 0;
    do
    {
      v7 = (&(&off_180087250)[4 * i])[v6];
      if ( !v7 )
        break;
      v8 = a1;
      v9 = (char *)((char *)v7 - a1);
      do
      {
        v10 = *(unsigned __int16 *)&v9[(_QWORD)v8];
        v11 = *(unsigned __int16 *)v8 - v10;
        if ( v11 )
          break;
        v8 += 2;
      }
      while ( v10 );
      if ( !v11 )
      {
        v2 = &(&off_180087250)[4 * i];
        break;
      }
      v6 = (unsigned int)(v6 + 1);
    }
    while ( (unsigned int)v6 < 2 );
  }
  if ( v2 )
  {
    v12 = 0;
    *a2 = v2;
  }
  else
  {
    v12 = -1073741637;
    DebugTraceError(3221225659LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\kem.c", 538);
  }
  return v12;
}

```

## disassembly

```asm
0x180064130  mov     [rsp+arg_0], rbx
0x180064135  mov     [rsp+arg_8], rsi
0x18006413a  push    rdi
0x18006413b  sub     rsp, 20h
0x18006413f  xor     r8d, r8d
0x180064142  mov     rdi, rdx
0x180064145  xor     r9d, r9d
0x180064148  mov     rsi, rcx
0x18006414b  lea     rcx, off_180087250; "MLKEMPRIVATESEEDBLOB"
0x180064152  mov     rbx, r9
0x180064155  shl     rbx, 5
0x180064159  add     rbx, rcx
0x18006415c  xor     ecx, ecx
0x18006415e  mov     rdx, [rbx+rcx*8]
0x180064162  test    rdx, rdx
0x180064165  jz      short loc_180064195
0x180064167  mov     rax, rsi
0x18006416a  sub     rdx, rsi
0x18006416d  movzx   r10d, word ptr [rax]
0x180064171  movzx   r11d, word ptr [rax+rdx]
0x180064176  sub     r10d, r11d
0x180064179  jnz     short loc_180064184
0x18006417b  add     rax, 2
0x18006417f  test    r11d, r11d
0x180064182  jnz     short loc_18006416D
0x180064184  test    r10d, r10d
0x180064187  jz      short loc_180064192
0x180064189  inc     ecx
0x18006418b  cmp     ecx, 2
0x18006418e  jb      short loc_18006415E
0x180064190  jmp     short loc_180064195
0x180064192  mov     r8, rbx
0x180064195  inc     r9
0x180064198  cmp     r9, 3
0x18006419c  jnz     short loc_18006414B
0x18006419e  test    r8, r8
0x1800641a1  jnz     short loc_1800641C8
0x1800641a3  mov     r9d, 21Ah
0x1800641a9  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800641b0  lea     rdx, aStatus; "Status"
0x1800641b7  mov     ecx, 0C00000BBh
0x1800641bc  mov     ebx, 0C00000BBh
0x1800641c1  call    DebugTraceError
0x1800641c6  jmp     short loc_1800641CD
0x1800641c8  xor     ebx, ebx
0x1800641ca  mov     [rdi], r8
0x1800641cd  mov     rsi, [rsp+28h+arg_8]
0x1800641d2  mov     eax, ebx
0x1800641d4  mov     rbx, [rsp+28h+arg_0]
0x1800641d9  add     rsp, 20h
0x1800641dd  pop     rdi
0x1800641de  retn
```
