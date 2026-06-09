# av_dynamic_hdr_vivid_create_side_data

- ea: `0x18003eb60`
- end: `0x18003eb99`
- name: `av_dynamic_hdr_vivid_create_side_data`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18003b750`
- `0x18003eb60`
- `0x18007b020`

## pseudocode

```c
__int64 __fastcall av_dynamic_hdr_vivid_create_side_data(__int64 a1)
{
  __int64 result; // rax
  __int64 v2; // rbx

  result = av_frame_new_side_data(a1, 0x19u, 1372);
  v2 = result;
  if ( result )
  {
    sub_18007B020(*(__m128i **)(result + 8), 0, 0x55Cu);
    return *(_QWORD *)(v2 + 8);
  }
  return result;
}

```

## disassembly

```asm
0x18003eb60  push    rbx
0x18003eb62  sub     rsp, 20h
0x18003eb66  mov     edx, 19h
0x18003eb6b  mov     r8d, 55Ch
0x18003eb71  call    av_frame_new_side_data
0x18003eb76  mov     rbx, rax
0x18003eb79  test    rax, rax
0x18003eb7c  jz      short loc_18003EB93
0x18003eb7e  mov     rcx, [rax+8]
0x18003eb82  xor     edx, edx
0x18003eb84  mov     r8d, 55Ch
0x18003eb8a  call    sub_18007B020
0x18003eb8f  mov     rax, [rbx+8]
0x18003eb93  add     rsp, 20h
0x18003eb97  pop     rbx
0x18003eb98  retn
```
