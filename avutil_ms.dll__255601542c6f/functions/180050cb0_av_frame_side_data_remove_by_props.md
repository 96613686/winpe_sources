# av_frame_side_data_remove_by_props

- ea: `0x180050cb0`
- end: `0x180050d2a`
- name: `av_frame_side_data_remove_by_props`
- size: `122`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x180050a80`
- `0x180050cb0`
- `0x180050d58`

## pseudocode

```c
char **__fastcall av_frame_side_data_remove_by_props(_QWORD *a1, int *a2, int a3)
{
  char **result; // rax
  __int64 v6; // rbx
  unsigned int *v8; // [rsp+38h] [rbp+10h] BYREF

  result = (char **)(unsigned int)(*a2 - 1);
  v6 = (int)result;
  if ( *a2 - 1 >= 0 )
  {
    do
    {
      v8 = *(unsigned int **)(*a1 + 8 * v6);
      result = av_frame_side_data_desc(*v8);
      if ( result )
      {
        if ( (a3 & (_DWORD)result[1]) != 0 )
        {
          sub_180050D58(&v8);
          result = (char **)*a2;
          *(_QWORD *)(*a1 + 8 * v6) = *(_QWORD *)(*a1 + 8LL * (_QWORD)result - 8);
          --*a2;
        }
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
0x180050cb0  mov     [rsp+arg_0], rbx
0x180050cb5  mov     [rsp+arg_10], rbp
0x180050cba  mov     [rsp+arg_18], rsi
0x180050cbf  push    rdi
0x180050cc0  sub     rsp, 20h
0x180050cc4  mov     eax, [rdx]
0x180050cc6  mov     ebp, r8d
0x180050cc9  sub     eax, 1
0x180050ccc  mov     rdi, rdx
0x180050ccf  movsxd  rbx, eax
0x180050cd2  mov     rsi, rcx
0x180050cd5  js      short loc_180050D15
0x180050cd7  mov     rax, [rsi]
0x180050cda  mov     rcx, [rax+rbx*8]
0x180050cde  mov     [rsp+28h+arg_8], rcx
0x180050ce3  mov     ecx, [rcx]
0x180050ce5  call    av_frame_side_data_desc
0x180050cea  test    rax, rax
0x180050ced  jz      short loc_180050D0F
0x180050cef  test    [rax+8], ebp
0x180050cf2  jz      short loc_180050D0F
0x180050cf4  lea     rcx, [rsp+28h+arg_8]
0x180050cf9  call    sub_180050D58
0x180050cfe  mov     rdx, [rsi]
0x180050d01  movsxd  rax, dword ptr [rdi]
0x180050d04  mov     rcx, [rdx+rax*8-8]
0x180050d09  mov     [rdx+rbx*8], rcx
0x180050d0d  dec     dword ptr [rdi]
0x180050d0f  sub     rbx, 1
0x180050d13  jns     short loc_180050CD7
0x180050d15  mov     rbx, [rsp+28h+arg_0]
0x180050d1a  mov     rbp, [rsp+28h+arg_10]
0x180050d1f  mov     rsi, [rsp+28h+arg_18]
0x180050d24  add     rsp, 20h
0x180050d28  pop     rdi
0x180050d29  retn
```
