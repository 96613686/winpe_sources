# av_dynamic_hdr_plus_create_side_data

- ea: `0x18003cdd0`
- end: `0x18003ce09`
- name: `av_dynamic_hdr_plus_create_side_data`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18003b750`
- `0x18003cdd0`
- `0x18007b020`

## pseudocode

```c
__int64 __fastcall av_dynamic_hdr_plus_create_side_data(__int64 a1)
{
  __int64 result; // rax
  __int64 v2; // rbx

  result = av_frame_new_side_data(a1, 0x11u, 11304);
  v2 = result;
  if ( result )
  {
    sub_18007B020(*(__m128i **)(result + 8), 0, 0x2C28u);
    return *(_QWORD *)(v2 + 8);
  }
  return result;
}

```

## disassembly

```asm
0x18003cdd0  push    rbx
0x18003cdd2  sub     rsp, 20h
0x18003cdd6  mov     edx, 11h
0x18003cddb  mov     r8d, 2C28h
0x18003cde1  call    av_frame_new_side_data
0x18003cde6  mov     rbx, rax
0x18003cde9  test    rax, rax
0x18003cdec  jz      short loc_18003CE03
0x18003cdee  mov     rcx, [rax+8]
0x18003cdf2  xor     edx, edx
0x18003cdf4  mov     r8d, 2C28h
0x18003cdfa  call    sub_18007B020
0x18003cdff  mov     rax, [rbx+8]
0x18003ce03  add     rsp, 20h
0x18003ce07  pop     rbx
0x18003ce08  retn
```
