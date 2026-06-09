# HASH_TABLE<ConfigPathTagNode,ushort const *>::FindNodeInternal(ushort const *,ulong,HASH_NODE<ConfigPathTagNode> * *,HASH_NODE<ConfigPathTagNode> * * *)

- ea: `0x180004e08`
- end: `0x180004ea6`
- name: `?FindNodeInternal@?$HASH_TABLE@VConfigPathTagNode@@PEBG@@AEAAHPEBGKPEAPEAV?$HASH_NODE@VConfigPathTagNode@@@@PEAPEAPEAV2@@Z`
- size: `158`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180004d5c`
- `0x18000a2fc`
- `0x180012c1c`
- `0x180012cc8`

## callees

- `0x180004e08`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall HASH_TABLE<ConfigPathTagNode,unsigned short const *>::FindNodeInternal(
        __int64 *a1,
        __int64 a2,
        unsigned int a3,
        _QWORD *a4,
        __int64 ***a5)
{
  unsigned int v6; // r14d
  __int64 **v10; // rsi
  __int64 *i; // rdi
  __int64 v12; // rbx
  __int64 v13; // rax

  v6 = 0;
  v10 = (__int64 **)(a1[1] + 8LL * (a3 % *((_DWORD *)a1 + 4)));
  for ( i = *v10; i; i = (__int64 *)*i )
  {
    if ( *((_DWORD *)i + 4) == a3 )
    {
      v12 = *a1;
      v13 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*a1 + 24))(a1, i[1]);
      if ( (*(unsigned int (__fastcall **)(__int64 *, __int64, __int64))(v12 + 40))(a1, a2, v13) )
      {
        v6 = 1;
        break;
      }
    }
    else if ( *((_DWORD *)i + 4) > a3 )
    {
      break;
    }
    v10 = (__int64 **)i;
  }
  *a4 = i;
  if ( a5 )
    *a5 = v10;
  return v6;
}

```

## disassembly

```asm
0x180004e08  push    rbx
0x180004e0a  push    rbp
0x180004e0b  push    rsi
0x180004e0c  push    rdi
0x180004e0d  push    r12
0x180004e0f  push    r13
0x180004e11  push    r14
0x180004e13  push    r15
0x180004e15  sub     rsp, 28h
0x180004e19  mov     r13, rdx
0x180004e1c  mov     eax, r8d
0x180004e1f  xor     edx, edx
0x180004e21  xor     r14d, r14d
0x180004e24  div     dword ptr [rcx+10h]
0x180004e27  mov     rax, [rcx+8]
0x180004e2b  mov     r12, r9
0x180004e2e  mov     ebp, r8d
0x180004e31  mov     r15, rcx
0x180004e34  lea     rsi, [rax+rdx*8]
0x180004e38  mov     rdi, [rsi]
0x180004e3b  test    rdi, rdi
0x180004e3e  jz      short loc_180004E74
0x180004e40  cmp     [rdi+10h], ebp
0x180004e43  jnz     short loc_180004E9C
0x180004e45  mov     rbx, [r15]
0x180004e48  mov     rcx, r15
0x180004e4b  mov     rdx, [rdi+8]
0x180004e4f  mov     rax, [rbx+18h]
0x180004e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e58  mov     r8, rax
0x180004e5b  mov     rdx, r13
0x180004e5e  mov     rax, [rbx+28h]
0x180004e62  mov     rcx, r15
0x180004e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e6a  test    eax, eax
0x180004e6c  jz      short loc_180004E9E
0x180004e6e  mov     r14d, 1
0x180004e74  mov     rcx, [rsp+68h+arg_20]
0x180004e7c  mov     [r12], rdi
0x180004e80  test    rcx, rcx
0x180004e83  jz      short loc_180004E88
0x180004e85  mov     [rcx], rsi
0x180004e88  mov     eax, r14d
0x180004e8b  add     rsp, 28h
0x180004e8f  pop     r15
0x180004e91  pop     r14
0x180004e93  pop     r13
0x180004e95  pop     r12
0x180004e97  pop     rdi
0x180004e98  pop     rsi
0x180004e99  pop     rbp
0x180004e9a  pop     rbx
0x180004e9b  retn
0x180004e9c  ja      short loc_180004E74
0x180004e9e  mov     rsi, rdi
0x180004ea1  mov     rdi, [rdi]
0x180004ea4  jmp     short loc_180004E3B
```
