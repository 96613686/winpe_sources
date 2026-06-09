# StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)

- ea: `0x18000c244`
- end: `0x18000c2d5`
- name: `?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z`
- size: `145`
- prototype: `int(unsigned __int16 **, unsigned __int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b8ac`
- `0x18000bb08`

## callees

- `0x18000a320`
- `0x18000c244`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c29a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c29a`

## pseudocode

```c
__int64 __fastcall StringCchCopyWithAlloc(unsigned __int16 **a1, __int64 a2, const unsigned __int16 *a3)
{
  __int64 v5; // rbx
  __int64 v6; // rdx
  const unsigned __int16 *v7; // rax
  __int64 result; // rax
  __int64 v9; // rbx
  unsigned __int16 *v10; // rax

  if ( !a1 )
    return 2147942487LL;
  if ( !a3 )
    return 2147942487LL;
  v5 = a2 - 1;
  if ( (unsigned __int64)(a2 - 1) > 0x7FFFFFFF )
    return 2147942487LL;
  v6 = a2 - 1;
  v7 = a3;
  if ( v5 )
  {
    while ( *v7 )
    {
      ++v7;
      if ( !--v6 )
        goto LABEL_7;
    }
    result = 0;
    v9 = v5 - v6;
  }
  else
  {
LABEL_7:
    result = 2147942487LL;
    v9 = 0;
  }
  if ( (int)result >= 0 )
  {
    v10 = (unsigned __int16 *)CoTaskMemAlloc(2 * v9 + 2);
    *a1 = v10;
    if ( v10 )
      return StringCchCopyW(v10, v9 + 1, a3);
    else
      return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x18000c244  push    rbx
0x18000c246  push    rbp
0x18000c247  push    rsi
0x18000c248  push    rdi
0x18000c249  sub     rsp, 28h
0x18000c24d  xor     ebp, ebp
0x18000c24f  mov     rdi, r8
0x18000c252  mov     rsi, rcx
0x18000c255  test    rcx, rcx
0x18000c258  jz      short loc_18000C2C7
0x18000c25a  test    r8, r8
0x18000c25d  jz      short loc_18000C2C7
0x18000c25f  lea     rbx, [rdx-1]
0x18000c263  cmp     rbx, 7FFFFFFFh
0x18000c26a  ja      short loc_18000C2C7
0x18000c26c  mov     rdx, rbx
0x18000c26f  mov     rax, r8
0x18000c272  test    rbx, rbx
0x18000c275  jz      short loc_18000C286
0x18000c277  cmp     [rax], bp
0x18000c27a  jz      short loc_18000C2AF
0x18000c27c  add     rax, 2
0x18000c280  sub     rdx, 1
0x18000c284  jnz     short loc_18000C277
0x18000c286  mov     eax, 80070057h
0x18000c28b  mov     rbx, rbp
0x18000c28e  test    eax, eax
0x18000c290  js      short loc_18000C2CC
0x18000c292  lea     rcx, ds:2[rbx*2]; cb
0x18000c29a  call    cs:__imp_CoTaskMemAlloc
0x18000c2a0  mov     [rsi], rax
0x18000c2a3  test    rax, rax
0x18000c2a6  jnz     short loc_18000C2B6
0x18000c2a8  mov     eax, 8007000Eh
0x18000c2ad  jmp     short loc_18000C2CC
0x18000c2af  mov     eax, ebp
0x18000c2b1  sub     rbx, rdx
0x18000c2b4  jmp     short loc_18000C28E
0x18000c2b6  lea     rdx, [rbx+1]; unsigned __int64
0x18000c2ba  mov     r8, rdi; unsigned __int16 *
0x18000c2bd  mov     rcx, rax; unsigned __int16 *
0x18000c2c0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000c2c5  jmp     short loc_18000C2CC
0x18000c2c7  mov     eax, 80070057h
0x18000c2cc  add     rsp, 28h
0x18000c2d0  pop     rdi
0x18000c2d1  pop     rsi
0x18000c2d2  pop     rbp
0x18000c2d3  pop     rbx
0x18000c2d4  retn
```
