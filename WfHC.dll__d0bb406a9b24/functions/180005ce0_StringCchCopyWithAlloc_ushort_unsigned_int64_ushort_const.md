# StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)

- ea: `0x180005ce0`
- end: `0x180005db0`
- name: `?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z`
- size: `208`
- prototype: `__int64 __fastcall(unsigned __int16 **, __int64, unsigned __int16 *)`
- caller_count: `5`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800031e0`
- `0x1800033a0`
- `0x180003d20`
- `0x180005bd0`
- `0x180006ebc`

## callees

- `0x180005c60`
- `0x180005ce0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005d43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005d43`

## pseudocode

```c
__int64 __fastcall StringCchCopyWithAlloc(unsigned __int16 **a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 v5; // rbx
  __int64 v6; // rdx
  unsigned __int16 *v7; // rax
  __int64 result; // rax
  __int64 v9; // rbx
  unsigned __int16 *v10; // rax

  if ( !a1 || !a3 )
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
0x180005ce0  mov     [rsp+arg_8], rsi
0x180005ce5  push    rdi
0x180005ce6  sub     rsp, 20h
0x180005cea  mov     rdi, r8
0x180005ced  mov     rsi, rcx
0x180005cf0  test    rcx, rcx
0x180005cf3  jz      loc_180005DA0
0x180005cf9  test    r8, r8
0x180005cfc  jz      loc_180005DA0
0x180005d02  mov     [rsp+28h+arg_0], rbx
0x180005d07  lea     rbx, [rdx-1]
0x180005d0b  cmp     rbx, 7FFFFFFFh
0x180005d12  ja      short loc_180005D8B
0x180005d14  mov     rdx, rbx
0x180005d17  mov     rax, r8
0x180005d1a  test    rbx, rbx
0x180005d1d  jz      short loc_180005D30
0x180005d1f  nop
0x180005d20  cmp     word ptr [rax], 0
0x180005d24  jz      short loc_180005D66
0x180005d26  add     rax, 2
0x180005d2a  sub     rdx, 1
0x180005d2e  jnz     short loc_180005D20
0x180005d30  mov     eax, 80070057h
0x180005d35  xor     ebx, ebx
0x180005d37  test    eax, eax
0x180005d39  js      short loc_180005D56
0x180005d3b  lea     rcx, ds:2[rbx*2]; cb
0x180005d43  call    cs:__imp_CoTaskMemAlloc
0x180005d49  mov     [rsi], rax
0x180005d4c  test    rax, rax
0x180005d4f  jnz     short loc_180005D6D
0x180005d51  mov     eax, 8007000Eh
0x180005d56  mov     rbx, [rsp+28h+arg_0]
0x180005d5b  mov     rsi, [rsp+28h+arg_8]
0x180005d60  add     rsp, 20h
0x180005d64  pop     rdi
0x180005d65  retn
0x180005d66  xor     eax, eax
0x180005d68  sub     rbx, rdx
0x180005d6b  jmp     short loc_180005D37
0x180005d6d  lea     rdx, [rbx+1]; unsigned __int64
0x180005d71  mov     r8, rdi; unsigned __int16 *
0x180005d74  mov     rcx, rax; unsigned __int16 *
0x180005d77  mov     rbx, [rsp+28h+arg_0]
0x180005d7c  mov     rsi, [rsp+28h+arg_8]
0x180005d81  add     rsp, 20h
0x180005d85  pop     rdi
0x180005d86  jmp     ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180005d8b  mov     rbx, [rsp+28h+arg_0]
0x180005d90  mov     eax, 80070057h
0x180005d95  mov     rsi, [rsp+28h+arg_8]
0x180005d9a  add     rsp, 20h
0x180005d9e  pop     rdi
0x180005d9f  retn
0x180005da0  mov     rsi, [rsp+28h+arg_8]
0x180005da5  mov     eax, 80070057h
0x180005daa  add     rsp, 20h
0x180005dae  pop     rdi
0x180005daf  retn
```
