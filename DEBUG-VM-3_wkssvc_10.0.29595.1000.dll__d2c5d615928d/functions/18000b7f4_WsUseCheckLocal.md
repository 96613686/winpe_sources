# WsUseCheckLocal

- ea: `0x18000b7f4`
- end: `0x18000b882`
- name: `WsUseCheckLocal`
- size: `142`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x180001710`
- `0x1800299a4`

## callees

- `0x18000b7f4`

## import_xrefs

- `netutils!NetpwPathCanonicalize` at `0x18000b857`
- `netutils!NetpwPathCanonicalize` at `0x18000b857`
- `netutils!NetpwPathType` at `0x18000b814`
- `netutils!NetpwPathType` at `0x18000b814`

## pseudocode

```c
__int64 __fastcall WsUseCheckLocal(__int64 a1, __int64 a2, _DWORD *a3)
{
  __int64 result; // rax
  __int64 v7; // rax
  int v8; // [rsp+78h] [rbp+20h] BYREF

  v8 = 0;
  result = NetpwPathType(a1, &v8, 0);
  if ( !(_DWORD)result )
  {
    if ( ((v8 - 0x4000) & 0xFFFFFFCF) != 0 || v8 == 16432 )
    {
      return 87;
    }
    else
    {
      result = NetpwPathCanonicalize(a1, a2, 162, 0, &v8, 0);
      if ( !(_DWORD)result )
      {
        v7 = -1;
        do
          ++v7;
        while ( *(_WORD *)(a2 + 2 * v7) );
        *a3 = v7;
        return 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000b7f4  push    rbx
0x18000b7f6  push    rbp
0x18000b7f7  push    rsi
0x18000b7f8  push    rdi
0x18000b7f9  sub     rsp, 38h
0x18000b7fd  mov     rsi, r8
0x18000b800  mov     rbx, rdx
0x18000b803  xor     ebp, ebp
0x18000b805  lea     rdx, [rsp+58h+arg_18]
0x18000b80a  xor     r8d, r8d
0x18000b80d  mov     [rsp+58h+arg_18], ebp
0x18000b811  mov     rdi, rcx
0x18000b814  call    cs:__imp_NetpwPathType
0x18000b81a  test    eax, eax
0x18000b81c  jnz     short loc_18000B872
0x18000b81e  mov     r9d, [rsp+58h+arg_18]
0x18000b823  lea     eax, [r9-4000h]
0x18000b82a  test    eax, 0FFFFFFCFh
0x18000b82f  jnz     short loc_18000B87B
0x18000b831  cmp     r9d, 4030h
0x18000b838  jz      short loc_18000B87B
0x18000b83a  lea     rax, [rsp+58h+arg_18]
0x18000b83f  mov     [rsp+58h+var_30], ebp
0x18000b843  xor     r9d, r9d
0x18000b846  mov     [rsp+58h+var_38], rax
0x18000b84b  mov     r8d, 0A2h
0x18000b851  mov     rdx, rbx
0x18000b854  mov     rcx, rdi
0x18000b857  call    cs:__imp_NetpwPathCanonicalize
0x18000b85d  test    eax, eax
0x18000b85f  jnz     short loc_18000B872
0x18000b861  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b865  inc     rax
0x18000b868  cmp     [rbx+rax*2], bp
0x18000b86c  jnz     short loc_18000B865
0x18000b86e  mov     [rsi], eax
0x18000b870  xor     eax, eax
0x18000b872  add     rsp, 38h
0x18000b876  pop     rdi
0x18000b877  pop     rsi
0x18000b878  pop     rbp
0x18000b879  pop     rbx
0x18000b87a  retn
0x18000b87b  mov     eax, 57h ; 'W'
0x18000b880  jmp     short loc_18000B872
```
