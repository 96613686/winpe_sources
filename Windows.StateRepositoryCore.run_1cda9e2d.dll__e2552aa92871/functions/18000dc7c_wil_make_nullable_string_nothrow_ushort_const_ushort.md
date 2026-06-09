# wil::make_nullable_string_nothrow(ushort const *,ushort * *)

- ea: `0x18000dc7c`
- end: `0x18000dd1d`
- name: `?make_nullable_string_nothrow@wil@@YAJPEBGPEAPEAG@Z`
- size: `161`
- prototype: `__int64 __fastcall(wil *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000de40`

## callees

- `0x18000940c`
- `0x180009b54`
- `0x18000bed8`
- `0x18000c928`
- `0x18000dc7c`

## string_xrefs

- `0x18000dcf0`: `onecore\base\appmodel\StateRepository\Common\Inc\SRwil.hpp`

## pseudocode

```c
__int64 __fastcall wil::make_nullable_string_nothrow(wil *this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  __int64 v6; // rax
  unsigned __int64 v7; // rsi
  unsigned int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // r9
  int v11; // eax
  __int64 v12; // r11
  int v13; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  unsigned __int16 *v15; // [rsp+50h] [rbp+8h] BYREF

  *(_QWORD *)a2 = 0;
  if ( !this )
    return 0;
  v6 = -1;
  do
    ++v6;
  while ( *((_WORD *)this + v6) );
  v7 = v6 + 1;
  wil::make_unique_nothrow<unsigned short [0]>(&v15, v6 + 1);
  if ( v15 )
  {
    v11 = StringCchCopyW(v15, v7, (const unsigned __int16 *)this);
    v8 = v11;
    if ( v11 >= 0 )
    {
      v15 = 0;
      v8 = 0;
      *(_QWORD *)a2 = v12;
      goto LABEL_11;
    }
    v10 = (unsigned int)v11;
    v9 = 27;
  }
  else
  {
    v8 = -2147024882;
    v9 = 26;
    v10 = 2147942414LL;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Common\\Inc\\SRwil.hpp",
    (const char *)v10,
    v13);
LABEL_11:
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v15);
  return v8;
}

```

## disassembly

```asm
0x18000dc7c  push    rbx
0x18000dc7e  push    rbp
0x18000dc7f  push    rsi
0x18000dc80  push    rdi
0x18000dc81  sub     rsp, 28h
0x18000dc85  xor     ebp, ebp
0x18000dc87  mov     rdi, rdx
0x18000dc8a  mov     [rdx], rbp
0x18000dc8d  mov     rbx, rcx
0x18000dc90  test    rcx, rcx
0x18000dc93  jnz     short loc_18000DC99
0x18000dc95  xor     eax, eax
0x18000dc97  jmp     short loc_18000DD14
0x18000dc99  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000dc9d  inc     rax
0x18000dca0  cmp     [rcx+rax*2], bp
0x18000dca4  jnz     short loc_18000DC9D
0x18000dca6  lea     rsi, [rax+1]
0x18000dcaa  mov     rdx, rsi
0x18000dcad  lea     rcx, [rsp+48h+arg_0]
0x18000dcb2  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x18000dcb7  mov     r11, [rsp+48h+arg_0]
0x18000dcbc  test    r11, r11
0x18000dcbf  jnz     short loc_18000DCCF
0x18000dcc1  mov     ebx, 8007000Eh
0x18000dcc6  lea     edx, [r11+1Ah]
0x18000dcca  mov     r9d, ebx
0x18000dccd  jmp     short loc_18000DCEB
0x18000dccf  mov     r8, rbx; unsigned __int16 *
0x18000dcd2  mov     rdx, rsi; unsigned __int64
0x18000dcd5  mov     rcx, r11; unsigned __int16 *
0x18000dcd8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000dcdd  mov     ebx, eax
0x18000dcdf  test    eax, eax
0x18000dce1  jns     short loc_18000DCFE
0x18000dce3  mov     r9d, eax; char *
0x18000dce6  mov     edx, 1Bh; void *
0x18000dceb  mov     rcx, [rsp+48h]; this
0x18000dcf0  lea     r8, aOnecoreBaseApp_10; "onecore\\base\\appmodel\\StateRepositor"...
0x18000dcf7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dcfc  jmp     short loc_18000DD08
0x18000dcfe  mov     [rsp+48h+arg_0], rbp
0x18000dd03  mov     ebx, ebp
0x18000dd05  mov     [rdi], r11
0x18000dd08  lea     rcx, [rsp+48h+arg_0]
0x18000dd0d  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x18000dd12  mov     eax, ebx
0x18000dd14  add     rsp, 28h
0x18000dd18  pop     rdi
0x18000dd19  pop     rsi
0x18000dd1a  pop     rbp
0x18000dd1b  pop     rbx
0x18000dd1c  retn
```
