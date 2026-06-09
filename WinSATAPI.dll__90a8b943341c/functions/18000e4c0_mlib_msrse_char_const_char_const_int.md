# mlib::_msrse_(char const *,char const *,int)

- ea: `0x18000e4c0`
- end: `0x18000e683`
- name: `?_msrse_@mlib@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD0H@Z`
- size: `451`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `22`
- callee_count: `7`
- tags: ``

## callers

- `0x180002390`
- `0x18000255c`
- `0x1800031a0`
- `0x180003680`
- `0x180004198`
- `0x1800043f0`
- `0x180004990`
- `0x18000aa80`
- `0x18000af20`
- `0x18000b7c0`
- `0x18000be30`
- `0x18000e124`
- `0x18000ef28`
- `0x18001012c`
- `0x18001ba74`
- `0x18001bb20`
- `0x18001c324`
- `0x18001c4b4`
- `0x18001f460`
- `0x180029bd8`
- `0x18002d9b4`
- `0x18002dbc8`

## callees

- `0x18000e4c0`
- `0x18000f9a0`
- `0x18000f9c0`
- `0x18000fe90`
- `0x180011f08`
- `0x18001a4b4`
- `0x18002fb50`

## import_xrefs

- `msvcrt!_itoa_s` at `0x18000e504`
- `msvcrt!_itoa_s` at `0x18000e504`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall mlib::_msrse_(_QWORD *a1, __int64 a2, __int64 a3, int a4)
{
  const char *v6; // rcx
  char *v7; // rdi
  unsigned __int64 v8; // rax
  __int64 v9; // rdx
  size_t v10; // r8
  __int64 v11; // rdi
  _QWORD *v12; // rax
  _QWORD *v13; // rax
  __int64 v14; // r8
  __int64 v15; // rdi
  _QWORD *v16; // rax
  _QWORD *v17; // rax
  __int64 v18; // rax
  char Buffer[16]; // [rsp+38h] [rbp-30h] BYREF

  LODWORD(v8) = _itoa_s(a4, Buffer, 0x10u, 10);
  v6 = "base\\winsat\\mlib\\mstring.h";
  v7 = "base\\winsat\\mlib\\mstring.h";
  LOBYTE(v8) = 98;
  do
  {
    LOBYTE(v8) = v8 - 47;
    if ( (unsigned __int8)v8 <= 0x2Du )
    {
      v9 = 0x200000000801LL;
      if ( _bittest64(&v9, v8) )
        v7 = (char *)(v6 + 1);
    }
    LOBYTE(v8) = *++v6;
  }
  while ( *v6 );
  a1[2] = 0;
  a1[3] = 15;
  a1[2] = 0;
  *(_BYTE *)a1 = 0;
  v10 = std::char_traits<char>::length(v7);
  std::string::assign(a1, v7, v10);
  if ( a1[2] == -1 || ~a1[2] == 1 )
    goto LABEL_29;
  v11 = a1[2] + 1LL;
  if ( (unsigned __int8)std::string::_Grow(a1, v11, 0) )
  {
    if ( a1[3] < 0x10u )
      v12 = a1;
    else
      v12 = (_QWORD *)*a1;
    *((_BYTE *)v12 + a1[2]) = 58;
    if ( a1[3] < 0x10u )
      v13 = a1;
    else
      v13 = (_QWORD *)*a1;
    a1[2] = v11;
    *((_BYTE *)v13 + v11) = 0;
  }
  if ( Buffer[0] )
  {
    v14 = -1;
    do
      ++v14;
    while ( Buffer[v14] );
  }
  else
  {
    v14 = 0;
  }
  std::string::append(a1, Buffer, v14);
  if ( a1[2] == -1 || ~a1[2] == 1 )
LABEL_29:
    std::_Xlength_error("string too long");
  v15 = a1[2] + 1LL;
  if ( (unsigned __int8)std::string::_Grow(a1, v15, 0) )
  {
    if ( a1[3] < 0x10u )
      v16 = a1;
    else
      v16 = (_QWORD *)*a1;
    *((_BYTE *)v16 + a1[2]) = 32;
    if ( a1[3] < 0x10u )
      v17 = a1;
    else
      v17 = (_QWORD *)*a1;
    a1[2] = v15;
    *((_BYTE *)v17 + v15) = 0;
  }
  v18 = std::char_traits<char>::length(a2);
  std::string::append(a1, a2, v18);
  return a1;
}

```

## disassembly

```asm
0x18000e4c0  push    rbx
0x18000e4c2  push    rsi
0x18000e4c3  push    rdi
0x18000e4c4  sub     rsp, 50h
0x18000e4c8  mov     [rsp+68h+var_40], 0FFFFFFFFFFFFFFFEh
0x18000e4d1  mov     rax, cs:__security_cookie
0x18000e4d8  xor     rax, rsp
0x18000e4db  mov     [rsp+68h+var_20], rax
0x18000e4e0  mov     eax, r9d
0x18000e4e3  mov     rsi, rdx
0x18000e4e6  mov     rbx, rcx
0x18000e4e9  mov     [rsp+68h+var_38], rcx
0x18000e4ee  and     [rsp+68h+var_48], 0
0x18000e4f3  mov     r9d, 0Ah; Radix
0x18000e4f9  lea     r8d, [r9+6]; BufferCount
0x18000e4fd  lea     rdx, [rsp+68h+Buffer]; Buffer
0x18000e502  mov     ecx, eax; Value
0x18000e504  call    cs:__imp__itoa_s
0x18000e50b  nop     dword ptr [rax+rax+00h]
0x18000e510  lea     rcx, aBaseWinsatMlib; "base\\winsat\\mlib\\mstring.h"
0x18000e517  mov     rdi, rcx
0x18000e51a  mov     al, 62h ; 'b'
0x18000e51c  sub     al, 2Fh ; '/'
0x18000e51e  cmp     al, 2Dh ; '-'
0x18000e520  ja      short loc_18000E536
0x18000e522  mov     rdx, 200000000801h
0x18000e52c  bt      rdx, rax
0x18000e530  jnb     short loc_18000E536
0x18000e532  lea     rdi, [rcx+1]
0x18000e536  inc     rcx
0x18000e539  mov     al, [rcx]
0x18000e53b  test    al, al
0x18000e53d  jnz     short loc_18000E51C
0x18000e53f  and     qword ptr [rbx+10h], 0
0x18000e544  mov     qword ptr [rbx+18h], 0Fh
0x18000e54c  and     qword ptr [rbx+10h], 0
0x18000e551  mov     [rbx], al
0x18000e553  mov     rcx, rdi
0x18000e556  call    ?length@?$char_traits@D@std@@SA_KPEBD@Z; std::char_traits<char>::length(char const *)
0x18000e55b  mov     r8, rax; Size
0x18000e55e  mov     rdx, rdi; Src
0x18000e561  mov     rcx, rbx; void *
0x18000e564  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z; std::string::assign(char const *,unsigned __int64)
0x18000e569  mov     [rsp+68h+var_48], 1
0x18000e571  mov     rdi, [rbx+10h]
0x18000e575  mov     rax, rdi
0x18000e578  not     rax
0x18000e57b  cmp     rax, 1
0x18000e57f  jbe     loc_18000E676
0x18000e585  inc     rdi
0x18000e588  xor     r8d, r8d
0x18000e58b  mov     rdx, rdi
0x18000e58e  mov     rcx, rbx
0x18000e591  call    ?_Grow@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA_N_K_N@Z; std::string::_Grow(unsigned __int64,bool)
0x18000e596  test    al, al
0x18000e598  jz      short loc_18000E5C8
0x18000e59a  mov     rcx, [rbx+10h]
0x18000e59e  cmp     qword ptr [rbx+18h], 10h
0x18000e5a3  jb      short loc_18000E5AA
0x18000e5a5  mov     rax, [rbx]
0x18000e5a8  jmp     short loc_18000E5AD
0x18000e5aa  mov     rax, rbx
0x18000e5ad  mov     byte ptr [rax+rcx], 3Ah ; ':'
0x18000e5b1  cmp     qword ptr [rbx+18h], 10h
0x18000e5b6  jb      short loc_18000E5BD
0x18000e5b8  mov     rax, [rbx]
0x18000e5bb  jmp     short loc_18000E5C0
0x18000e5bd  mov     rax, rbx
0x18000e5c0  mov     [rbx+10h], rdi
0x18000e5c4  mov     byte ptr [rax+rdi], 0
0x18000e5c8  cmp     [rsp+68h+Buffer], 0
0x18000e5cd  jnz     short loc_18000E5D4
0x18000e5cf  xor     r8d, r8d
0x18000e5d2  jmp     short loc_18000E5E7
0x18000e5d4  lea     rax, [rsp+68h+Buffer]
0x18000e5d9  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000e5dd  inc     r8
0x18000e5e0  cmp     byte ptr [rax+r8], 0
0x18000e5e5  jnz     short loc_18000E5DD
0x18000e5e7  lea     rdx, [rsp+68h+Buffer]
0x18000e5ec  mov     rcx, rbx
0x18000e5ef  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z; std::string::append(char const *,unsigned __int64)
0x18000e5f4  mov     rdi, [rbx+10h]
0x18000e5f8  mov     rax, rdi
0x18000e5fb  not     rax
0x18000e5fe  cmp     rax, 1
0x18000e602  jbe     short loc_18000E676
0x18000e604  inc     rdi
0x18000e607  xor     r8d, r8d
0x18000e60a  mov     rdx, rdi
0x18000e60d  mov     rcx, rbx
0x18000e610  call    ?_Grow@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA_N_K_N@Z; std::string::_Grow(unsigned __int64,bool)
0x18000e615  test    al, al
0x18000e617  jz      short loc_18000E647
0x18000e619  mov     rcx, [rbx+10h]
0x18000e61d  cmp     qword ptr [rbx+18h], 10h
0x18000e622  jb      short loc_18000E629
0x18000e624  mov     rax, [rbx]
0x18000e627  jmp     short loc_18000E62C
0x18000e629  mov     rax, rbx
0x18000e62c  mov     byte ptr [rax+rcx], 20h ; ' '
0x18000e630  cmp     qword ptr [rbx+18h], 10h
0x18000e635  jb      short loc_18000E63C
0x18000e637  mov     rax, [rbx]
0x18000e63a  jmp     short loc_18000E63F
0x18000e63c  mov     rax, rbx
0x18000e63f  mov     [rbx+10h], rdi
0x18000e643  mov     byte ptr [rax+rdi], 0
0x18000e647  mov     rcx, rsi
0x18000e64a  call    ?length@?$char_traits@D@std@@SA_KPEBD@Z; std::char_traits<char>::length(char const *)
0x18000e64f  mov     r8, rax
0x18000e652  mov     rdx, rsi
0x18000e655  mov     rcx, rbx
0x18000e658  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z; std::string::append(char const *,unsigned __int64)
0x18000e65d  mov     rax, rbx
0x18000e660  mov     rcx, [rsp+68h+var_20]
0x18000e665  xor     rcx, rsp; StackCookie
0x18000e668  call    __security_check_cookie
0x18000e66d  add     rsp, 50h
0x18000e671  pop     rdi
0x18000e672  pop     rsi
0x18000e673  pop     rbx
0x18000e674  retn
0x18000e676  lea     rcx, aStringTooLong; "string too long"
0x18000e67d  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
