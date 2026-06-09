# av_frame_side_data_remove

- ea: `0x180050c40`
- end: `0x180050cad`
- name: `av_frame_side_data_remove`
- size: `109`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18003b9f0`
- `0x180050760`
- `0x180050880`
- `0x180050b50`

## callees

- `0x180050c40`
- `0x180050d58`

## pseudocode

```c
__int64 __fastcall av_frame_side_data_remove(__int64 *a1, int *a2, int a3)
{
  __int64 result; // rax
  __int64 v6; // rbx
  _DWORD *v8; // [rsp+38h] [rbp+10h] BYREF

  result = (unsigned int)(*a2 - 1);
  v6 = (int)result;
  if ( *a2 - 1 >= 0 )
  {
    do
    {
      result = *a1;
      v8 = *(_DWORD **)(*a1 + 8 * v6);
      if ( *v8 == a3 )
      {
        sub_180050D58(&v8);
        result = *a2;
        *(_QWORD *)(*a1 + 8 * v6) = *(_QWORD *)(*a1 + 8 * result - 8);
        --*a2;
      }
      --v6;
    }
    while ( v6 >= 0 );
  }
  return result;
}

```

## disassembly

```asm
0x180050c40  mov     [rsp+arg_0], rbx
0x180050c45  mov     [rsp+arg_10], rbp
0x180050c4a  mov     [rsp+arg_18], rsi
0x180050c4f  push    rdi
0x180050c50  sub     rsp, 20h
0x180050c54  mov     eax, [rdx]
0x180050c56  mov     ebp, r8d
0x180050c59  sub     eax, 1
0x180050c5c  mov     rdi, rdx
0x180050c5f  movsxd  rbx, eax
0x180050c62  mov     rsi, rcx
0x180050c65  js      short loc_180050C98
0x180050c67  mov     rax, [rsi]
0x180050c6a  mov     rdx, [rax+rbx*8]
0x180050c6e  mov     [rsp+28h+arg_8], rdx
0x180050c73  cmp     [rdx], ebp
0x180050c75  jnz     short loc_180050C92
0x180050c77  lea     rcx, [rsp+28h+arg_8]
0x180050c7c  call    sub_180050D58
0x180050c81  mov     rdx, [rsi]
0x180050c84  movsxd  rax, dword ptr [rdi]
0x180050c87  mov     rcx, [rdx+rax*8-8]
0x180050c8c  mov     [rdx+rbx*8], rcx
0x180050c90  dec     dword ptr [rdi]
0x180050c92  sub     rbx, 1
0x180050c96  jns     short loc_180050C67
0x180050c98  mov     rbx, [rsp+28h+arg_0]
0x180050c9d  mov     rbp, [rsp+28h+arg_10]
0x180050ca2  mov     rsi, [rsp+28h+arg_18]
0x180050ca7  add     rsp, 20h
0x180050cab  pop     rdi
0x180050cac  retn
```
