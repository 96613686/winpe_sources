# av_stereo3d_create_side_data

- ea: `0x1800515a0`
- end: `0x180051608`
- name: `av_stereo3d_create_side_data`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x18003b750`
- `0x1800515a0`
- `0x18007b020`

## pseudocode

```c
__int64 __fastcall av_stereo3d_create_side_data(__int64 a1)
{
  __int64 result; // rax
  __int64 v2; // rbx
  __int64 v3; // rcx

  result = av_frame_new_side_data(a1, 2u, 36);
  v2 = result;
  if ( result )
  {
    sub_18007B020(*(__m128i **)(result + 8), 0, 0x24u);
    v3 = *(_QWORD *)(v2 + 8);
    *(_QWORD *)(v3 + 20) = 0x100000000LL;
    *(_QWORD *)(v3 + 28) = 0x100000000LL;
    return *(_QWORD *)(v2 + 8);
  }
  return result;
}

```

## disassembly

```asm
0x1800515a0  push    rbx
0x1800515a2  sub     rsp, 20h
0x1800515a6  mov     edx, 2
0x1800515ab  lea     r8d, [rdx+22h]
0x1800515af  call    av_frame_new_side_data
0x1800515b4  mov     rbx, rax
0x1800515b7  test    rax, rax
0x1800515ba  jz      short loc_180051602
0x1800515bc  mov     rcx, [rax+8]
0x1800515c0  xor     edx, edx
0x1800515c2  lea     r8d, [rdx+24h]
0x1800515c6  call    sub_18007B020
0x1800515cb  mov     rcx, [rbx+8]
0x1800515cf  mov     edx, 1
0x1800515d4  mov     dword ptr [rsp+28h+arg_8+4], edx
0x1800515d8  mov     dword ptr [rsp+28h+arg_8], 0
0x1800515e0  mov     rax, [rsp+28h+arg_8]
0x1800515e5  mov     [rcx+14h], rax
0x1800515e9  mov     dword ptr [rsp+28h+arg_8], 0
0x1800515f1  mov     dword ptr [rsp+28h+arg_8+4], edx
0x1800515f5  mov     rax, [rsp+28h+arg_8]
0x1800515fa  mov     [rcx+1Ch], rax
0x1800515fe  mov     rax, [rbx+8]
0x180051602  add     rsp, 20h
0x180051606  pop     rbx
0x180051607  retn
```
