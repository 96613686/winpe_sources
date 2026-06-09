# av_content_light_metadata_create_side_data

- ea: `0x1800439c0`
- end: `0x1800439f5`
- name: `av_content_light_metadata_create_side_data`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x18003b750`
- `0x1800439c0`
- `0x18007b020`

## pseudocode

```c
__int64 __fastcall av_content_light_metadata_create_side_data(__int64 a1)
{
  __int64 result; // rax
  __int64 v2; // rbx

  result = av_frame_new_side_data(a1, 0xEu, 8);
  v2 = result;
  if ( result )
  {
    sub_18007B020(*(__m128i **)(result + 8), 0, 8u);
    return *(_QWORD *)(v2 + 8);
  }
  return result;
}

```

## disassembly

```asm
0x1800439c0  push    rbx
0x1800439c2  sub     rsp, 20h
0x1800439c6  mov     edx, 0Eh
0x1800439cb  lea     r8d, [rdx-6]
0x1800439cf  call    av_frame_new_side_data
0x1800439d4  mov     rbx, rax
0x1800439d7  test    rax, rax
0x1800439da  jz      short loc_1800439EF
0x1800439dc  mov     rcx, [rax+8]
0x1800439e0  xor     edx, edx
0x1800439e2  lea     r8d, [rdx+8]
0x1800439e6  call    sub_18007B020
0x1800439eb  mov     rax, [rbx+8]
0x1800439ef  add     rsp, 20h
0x1800439f3  pop     rbx
0x1800439f4  retn
```
