# MIMEMAP_CUSTOM_MAPPER::RemoveMimeMap(MULTISZ *,ushort const *)

- ea: `0x18001d190`
- end: `0x18001d2e1`
- name: `?RemoveMimeMap@MIMEMAP_CUSTOM_MAPPER@@AEAAJPEAVMULTISZ@@PEBG@Z`
- size: `337`
- prototype: `__int64 __fastcall(MIMEMAP_CUSTOM_MAPPER *__hidden this, struct MULTISZ *, wchar_t *String2)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180020890`

## callees

- `0x180003432`
- `0x180003460`
- `0x18001cd84`
- `0x18001d190`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d2cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d2cb`
- `iisutil!?Copy@MULTISZ@@QEAAHAEBV1@@Z` at `0x18001d26c`
- `iisutil!?Copy@MULTISZ@@QEAAHAEBV1@@Z` at `0x18001d26c`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x18001d1ec`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x18001d25e`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x18001d279`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x18001d1ec`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x18001d25e`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x18001d279`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x18001d24b`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x18001d24b`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x18001d1f7`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x18001d1f7`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18001d1c3`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18001d1c3`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x18001d235`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x18001d235`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18001d29d`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18001d29d`

## pseudocode

```c
__int64 __fastcall MIMEMAP_CUSTOM_MAPPER::RemoveMimeMap(
        MIMEMAP_CUSTOM_MAPPER *this,
        struct MULTISZ *a2,
        wchar_t *String2)
{
  int ReversedMultiSz; // ebx
  int v7; // ebp
  const wchar_t *i; // rax
  __int64 v9; // rdi
  const unsigned __int16 *v10; // rbx
  signed int LastError; // eax
  _BYTE v13[56]; // [rsp+20h] [rbp-68h] BYREF

  MULTISZ::MULTISZ((MULTISZ *)v13);
  ReversedMultiSz = MIMEMAP_CUSTOM_MAPPER::GetReversedMultiSz(this, a2, (struct MULTISZ *)v13);
  if ( ReversedMultiSz >= 0 )
  {
    v7 = 0;
    MULTISZ::Reset(a2);
    for ( i = MULTISZ::First((MULTISZ *)v13); ; i = MULTISZ::Next((MULTISZ *)v13, v10) )
    {
      v10 = i;
      if ( !i )
        break;
      if ( v7 )
        goto LABEL_9;
      v9 = -1;
      do
        ++v9;
      while ( String2[v9] );
      if ( !wcsncmp_0(i, String2, (unsigned int)v9) && v10[v9] == 44 )
      {
        v7 = 1;
      }
      else
      {
LABEL_9:
        if ( !MULTISZ::Append(a2, v10) )
          goto LABEL_16;
      }
    }
    MULTISZ::Reset((MULTISZ *)v13);
    if ( MULTISZ::Copy((MULTISZ *)v13, a2) )
    {
      MULTISZ::Reset(a2);
      ReversedMultiSz = MIMEMAP_CUSTOM_MAPPER::GetReversedMultiSz(this, (struct MULTISZ *)v13, a2);
      if ( ReversedMultiSz >= 0 )
        ReversedMultiSz = 0;
      goto LABEL_15;
    }
LABEL_16:
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    ReversedMultiSz = LastError;
  }
LABEL_15:
  MULTISZ::~MULTISZ((MULTISZ *)v13);
  return (unsigned int)ReversedMultiSz;
}

```

## disassembly

```asm
0x18001d190  mov     [rsp+arg_10], rbx
0x18001d195  mov     [rsp+arg_18], rbp
0x18001d19a  push    rsi
0x18001d19b  push    rdi
0x18001d19c  push    r12
0x18001d19e  push    r14
0x18001d1a0  push    r15
0x18001d1a2  sub     rsp, 60h
0x18001d1a6  mov     rax, cs:__security_cookie
0x18001d1ad  xor     rax, rsp
0x18001d1b0  mov     [rsp+88h+var_30], rax
0x18001d1b5  mov     r15, rcx
0x18001d1b8  mov     r14, r8
0x18001d1bb  lea     rcx, [rsp+88h+var_68]
0x18001d1c0  mov     rsi, rdx
0x18001d1c3  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x18001d1c9  lea     r8, [rsp+88h+var_68]; struct MULTISZ *
0x18001d1ce  mov     rdx, rsi; struct MULTISZ *
0x18001d1d1  mov     rcx, r15; this
0x18001d1d4  call    ?GetReversedMultiSz@MIMEMAP_CUSTOM_MAPPER@@AEAAJPEAVMULTISZ@@0@Z; MIMEMAP_CUSTOM_MAPPER::GetReversedMultiSz(MULTISZ *,MULTISZ *)
0x18001d1d9  xor     r12d, r12d
0x18001d1dc  mov     ebx, eax
0x18001d1de  test    eax, eax
0x18001d1e0  js      loc_18001D298
0x18001d1e6  mov     rcx, rsi
0x18001d1e9  mov     ebp, r12d
0x18001d1ec  call    cs:__imp_?Reset@MULTISZ@@QEAAXXZ; MULTISZ::Reset(void)
0x18001d1f2  lea     rcx, [rsp+88h+var_68]
0x18001d1f7  call    cs:__imp_?First@MULTISZ@@QEBAPEBGXZ; MULTISZ::First(void)
0x18001d1fd  jmp     short loc_18001D251
0x18001d1ff  test    ebp, ebp
0x18001d201  jnz     short loc_18001D22F
0x18001d203  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001d207  inc     rdi
0x18001d20a  cmp     [r14+rdi*2], r12w
0x18001d20f  jnz     short loc_18001D207
0x18001d211  mov     r8d, edi; MaxCount
0x18001d214  mov     rdx, r14; String2
0x18001d217  mov     rcx, rbx; String1
0x18001d21a  call    wcsncmp_0
0x18001d21f  test    eax, eax
0x18001d221  jnz     short loc_18001D22F
0x18001d223  cmp     word ptr [rbx+rdi*2], 2Ch ; ','
0x18001d228  jnz     short loc_18001D22F
0x18001d22a  lea     ebp, [rax+1]
0x18001d22d  jmp     short loc_18001D243
0x18001d22f  mov     rdx, rbx
0x18001d232  mov     rcx, rsi
0x18001d235  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x18001d23b  test    eax, eax
0x18001d23d  jz      loc_18001D2CB
0x18001d243  mov     rdx, rbx
0x18001d246  lea     rcx, [rsp+88h+var_68]
0x18001d24b  call    cs:__imp_?Next@MULTISZ@@QEBAPEBGPEBG@Z; MULTISZ::Next(ushort const *)
0x18001d251  mov     rbx, rax
0x18001d254  test    rax, rax
0x18001d257  jnz     short loc_18001D1FF
0x18001d259  lea     rcx, [rsp+88h+var_68]
0x18001d25e  call    cs:__imp_?Reset@MULTISZ@@QEAAXXZ; MULTISZ::Reset(void)
0x18001d264  mov     rdx, rsi
0x18001d267  lea     rcx, [rsp+88h+var_68]
0x18001d26c  call    cs:__imp_?Copy@MULTISZ@@QEAAHAEBV1@@Z; MULTISZ::Copy(MULTISZ const &)
0x18001d272  test    eax, eax
0x18001d274  jz      short loc_18001D2CB
0x18001d276  mov     rcx, rsi
0x18001d279  call    cs:__imp_?Reset@MULTISZ@@QEAAXXZ; MULTISZ::Reset(void)
0x18001d27f  mov     r8, rsi; struct MULTISZ *
0x18001d282  lea     rdx, [rsp+88h+var_68]; struct MULTISZ *
0x18001d287  mov     rcx, r15; this
0x18001d28a  call    ?GetReversedMultiSz@MIMEMAP_CUSTOM_MAPPER@@AEAAJPEAVMULTISZ@@0@Z; MIMEMAP_CUSTOM_MAPPER::GetReversedMultiSz(MULTISZ *,MULTISZ *)
0x18001d28f  mov     ebx, eax
0x18001d291  test    eax, eax
0x18001d293  js      short loc_18001D298
0x18001d295  mov     ebx, r12d
0x18001d298  lea     rcx, [rsp+88h+var_68]
0x18001d29d  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x18001d2a3  mov     eax, ebx
0x18001d2a5  mov     rcx, [rsp+88h+var_30]
0x18001d2aa  xor     rcx, rsp; StackCookie
0x18001d2ad  call    __security_check_cookie
0x18001d2b2  lea     r11, [rsp+88h+var_28]
0x18001d2b7  mov     rbx, [r11+40h]
0x18001d2bb  mov     rbp, [r11+48h]
0x18001d2bf  mov     rsp, r11
0x18001d2c2  pop     r15
0x18001d2c4  pop     r14
0x18001d2c6  pop     r12
0x18001d2c8  pop     rdi
0x18001d2c9  pop     rsi
0x18001d2ca  retn
0x18001d2cb  call    cs:__imp_GetLastError
0x18001d2d1  test    eax, eax
0x18001d2d3  jle     short loc_18001D2DD
0x18001d2d5  movzx   eax, ax
0x18001d2d8  or      eax, 80070000h
0x18001d2dd  mov     ebx, eax
0x18001d2df  jmp     short loc_18001D298
```
