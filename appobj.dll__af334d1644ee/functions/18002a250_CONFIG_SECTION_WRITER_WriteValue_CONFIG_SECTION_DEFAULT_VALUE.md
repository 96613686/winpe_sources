# CONFIG_SECTION_WRITER::WriteValue(CONFIG_SECTION_DEFAULT_VALUE *)

- ea: `0x18002a250`
- end: `0x18002a415`
- name: `?WriteValue@CONFIG_SECTION_WRITER@@QEAAJPEAUCONFIG_SECTION_DEFAULT_VALUE@@@Z`
- size: `453`
- prototype: `__int64 __fastcall(CONFIG_SECTION_WRITER *__hidden this, struct CONFIG_SECTION_DEFAULT_VALUE *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x180019d30`

## callees

- `0x180001ed0`
- `0x180001fb0`
- `0x180002e90`
- `0x18002a250`
- `0x18002a41c`
- `0x180032c08`
- `0x180034cbe`
- `0x180034d00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a39f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a39f`

## pseudocode

```c
__int64 __fastcall CONFIG_SECTION_WRITER::WriteValue(
        CONFIG_SECTION_WRITER *this,
        struct CONFIG_SECTION_DEFAULT_VALUE *a2)
{
  const unsigned __int8 *v4; // rax
  int v5; // edx
  int v6; // ecx
  int v7; // ebx
  unsigned __int16 *v8; // rdx
  unsigned __int16 v9; // ax
  int v10; // ecx
  signed int LastError; // eax
  _BYTE v13[32]; // [rsp+20h] [rbp-E0h] BYREF
  __int16 *v14; // [rsp+40h] [rbp-C0h]
  int v15; // [rsp+48h] [rbp-B8h]
  __int16 v16; // [rsp+4Ch] [rbp-B4h]
  int v17; // [rsp+50h] [rbp-B0h]
  _BYTE v18[32]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *Src; // [rsp+78h] [rbp-88h]
  int v20; // [rsp+80h] [rbp-80h]
  __int16 v21; // [rsp+84h] [rbp-7Ch]
  int v22; // [rsp+88h] [rbp-78h]
  _BYTE v23[64]; // [rsp+90h] [rbp-70h] BYREF
  __int16 v24; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v25[510]; // [rsp+D2h] [rbp-2Eh] BYREF
  __int16 v26; // [rsp+2D0h] [rbp+1D0h] BYREF
  _BYTE v27[510]; // [rsp+2D2h] [rbp+1D2h] BYREF

  memset_0(v25, 0, sizeof(v25));
  v21 = 256;
  v20 = 512;
  Src = (unsigned __int16 *)&v24;
  v22 = 0;
  v24 = 0;
  memset_0(v27, 0, sizeof(v27));
  v15 = 512;
  v14 = &v26;
  v16 = 256;
  v17 = 0;
  v26 = 0;
  MULTISZ::MULTISZ((MULTISZ *)v23);
  if ( !a2 )
    goto LABEL_22;
  v4 = *(const unsigned __int8 **)a2;
  do
  {
    v5 = *(unsigned __int16 *)&v4[*((_QWORD *)this + 2) - *(_QWORD *)a2];
    v6 = *(unsigned __int16 *)v4 - v5;
    if ( v6 )
      break;
    v4 += 2;
  }
  while ( v5 );
  if ( v6 )
  {
LABEL_22:
    v7 = -2147024809;
  }
  else
  {
    v7 = STRU::Copy((STRU *)v18, *((const unsigned __int8 **)a2 + 1));
    if ( v7 >= 0 )
    {
      v8 = Src;
      v9 = *Src;
      if ( *Src )
      {
        v10 = 0;
        do
        {
          if ( v9 == 123 )
          {
            ++v10;
          }
          else if ( v9 == 125 )
          {
            if ( v10 )
              --v10;
          }
          else if ( v9 == 47 && !v10 )
          {
            *v8 = 0;
          }
          v9 = *++v8;
        }
        while ( *v8 );
      }
      if ( (unsigned int)MULTISZ::AuxAppend((MULTISZ *)v23, Src, (unsigned int)(2 * v22), 1) )
      {
        v7 = CONFIG_SECTION_WRITER::WriteValueInternal(this, (struct MULTISZ *)v23, *((unsigned __int16 **)a2 + 2));
      }
      else
      {
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
      }
    }
  }
  BUFFER::~BUFFER((BUFFER *)v23);
  BUFFER::~BUFFER((BUFFER *)v13);
  BUFFER::~BUFFER((BUFFER *)v18);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002a250  mov     [rsp-8+arg_10], rbx
0x18002a255  mov     [rsp-8+arg_18], rsi
0x18002a25a  push    rbp
0x18002a25b  push    rdi
0x18002a25c  push    r15
0x18002a25e  lea     rbp, [rsp-3E0h]
0x18002a266  sub     rsp, 4E0h
0x18002a26d  mov     rax, cs:__security_cookie
0x18002a274  xor     rax, rsp
0x18002a277  mov     [rbp+3F0h+var_20], rax
0x18002a27e  mov     rdi, rdx
0x18002a281  mov     rsi, rcx
0x18002a284  xor     edx, edx; Val
0x18002a286  lea     rcx, [rbp+3F0h+var_41E]; void *
0x18002a28a  mov     r8d, 1FEh; Size
0x18002a290  call    memset_0
0x18002a295  mov     ebx, 200h
0x18002a29a  mov     [rbp+3F0h+var_46C], 100h
0x18002a2a0  lea     rax, [rbp+3F0h+var_420]
0x18002a2a4  mov     [rbp+3F0h+var_470], ebx
0x18002a2a7  xor     r15d, r15d
0x18002a2aa  mov     [rsp+4F0h+Src], rax
0x18002a2af  xor     edx, edx; Val
0x18002a2b1  mov     [rbp+3F0h+var_468], r15d
0x18002a2b5  lea     r8d, [rbx-2]; Size
0x18002a2b9  mov     [rbp+3F0h+var_420], r15w
0x18002a2be  lea     rcx, [rbp+3F0h+var_21E]; void *
0x18002a2c5  call    memset_0
0x18002a2ca  lea     rax, [rbp+3F0h+var_220]
0x18002a2d1  mov     [rsp+4F0h+var_4A8], ebx
0x18002a2d5  lea     rcx, [rbp+3F0h+var_460]; this
0x18002a2d9  mov     [rsp+4F0h+var_4B0], rax
0x18002a2de  mov     [rsp+4F0h+var_4A4], 100h
0x18002a2e5  mov     [rsp+4F0h+var_4A0], r15d
0x18002a2ea  mov     [rbp+3F0h+var_220], r15w
0x18002a2f2  call    ??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x18002a2f7  test    rdi, rdi
0x18002a2fa  jz      loc_18002A3CA
0x18002a300  mov     rax, [rdi]
0x18002a303  mov     r8, [rsi+10h]
0x18002a307  sub     r8, rax
0x18002a30a  movzx   ecx, word ptr [rax]
0x18002a30d  movzx   edx, word ptr [rax+r8]
0x18002a312  sub     ecx, edx
0x18002a314  jnz     short loc_18002A31E
0x18002a316  add     rax, 2
0x18002a31a  test    edx, edx
0x18002a31c  jnz     short loc_18002A30A
0x18002a31e  test    ecx, ecx
0x18002a320  jnz     loc_18002A3CA
0x18002a326  mov     rdx, [rdi+8]; unsigned __int16 *
0x18002a32a  lea     rcx, [rsp+4F0h+var_498]; this
0x18002a32f  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18002a334  mov     ebx, eax
0x18002a336  test    eax, eax
0x18002a338  js      loc_18002A3CF
0x18002a33e  mov     rdx, [rsp+4F0h+Src]
0x18002a343  movzx   eax, word ptr [rdx]
0x18002a346  test    ax, ax
0x18002a349  jz      short loc_18002A380
0x18002a34b  mov     ecx, r15d
0x18002a34e  cmp     ax, 7Bh ; '{'
0x18002a352  jnz     short loc_18002A358
0x18002a354  inc     ecx
0x18002a356  jmp     short loc_18002A374
0x18002a358  cmp     ax, 7Dh ; '}'
0x18002a35c  jnz     short loc_18002A366
0x18002a35e  test    ecx, ecx
0x18002a360  jz      short loc_18002A374
0x18002a362  dec     ecx
0x18002a364  jmp     short loc_18002A374
0x18002a366  cmp     ax, 2Fh ; '/'
0x18002a36a  jnz     short loc_18002A374
0x18002a36c  test    ecx, ecx
0x18002a36e  jnz     short loc_18002A374
0x18002a370  mov     [rdx], r15w
0x18002a374  add     rdx, 2
0x18002a378  movzx   eax, word ptr [rdx]
0x18002a37b  test    ax, ax
0x18002a37e  jnz     short loc_18002A34E
0x18002a380  mov     r8d, [rbp+3F0h+var_468]
0x18002a384  lea     rcx, [rbp+3F0h+var_460]; this
0x18002a388  mov     rdx, [rsp+4F0h+Src]; Src
0x18002a38d  add     r8d, r8d; Size
0x18002a390  mov     r9d, 1; int
0x18002a396  call    ?AuxAppend@MULTISZ@@AEAAHPEBGIH@Z; MULTISZ::AuxAppend(ushort const *,uint,int)
0x18002a39b  test    eax, eax
0x18002a39d  jnz     short loc_18002A3B6
0x18002a39f  call    cs:__imp_GetLastError
0x18002a3a5  mov     ebx, eax
0x18002a3a7  test    eax, eax
0x18002a3a9  jle     short loc_18002A3CF
0x18002a3ab  movzx   ebx, ax
0x18002a3ae  or      ebx, 80070000h
0x18002a3b4  jmp     short loc_18002A3CF
0x18002a3b6  mov     r8, [rdi+10h]; unsigned __int16 *
0x18002a3ba  lea     rdx, [rbp+3F0h+var_460]; struct MULTISZ *
0x18002a3be  mov     rcx, rsi; this
0x18002a3c1  call    ?WriteValueInternal@CONFIG_SECTION_WRITER@@AEAAJPEAVMULTISZ@@PEAG@Z; CONFIG_SECTION_WRITER::WriteValueInternal(MULTISZ *,ushort *)
0x18002a3c6  mov     ebx, eax
0x18002a3c8  jmp     short loc_18002A3CF
0x18002a3ca  mov     ebx, 80070057h
0x18002a3cf  lea     rcx, [rbp+3F0h+var_460]; this
0x18002a3d3  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002a3d8  lea     rcx, [rsp+4F0h+var_4D0]; this
0x18002a3dd  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002a3e2  lea     rcx, [rsp+4F0h+var_498]; this
0x18002a3e7  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002a3ec  mov     eax, ebx
0x18002a3ee  mov     rcx, [rbp+3F0h+var_20]
0x18002a3f5  xor     rcx, rsp; StackCookie
0x18002a3f8  call    __security_check_cookie
0x18002a3fd  lea     r11, [rsp+4F0h+var_10]
0x18002a405  mov     rbx, [r11+30h]
0x18002a409  mov     rsi, [r11+38h]
0x18002a40d  mov     rsp, r11
0x18002a410  pop     r15
0x18002a412  pop     rdi
0x18002a413  pop     rbp
0x18002a414  retn
```
