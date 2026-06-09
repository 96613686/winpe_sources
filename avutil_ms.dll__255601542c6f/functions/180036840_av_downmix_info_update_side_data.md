# av_downmix_info_update_side_data

- ea: `0x180036840`
- end: `0x180036896`
- name: `av_downmix_info_update_side_data`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, installer_update`

## callees

- `0x180036840`
- `0x18003b460`
- `0x18003b750`
- `0x18007b020`

## pseudocode

```c
__int64 __fastcall av_downmix_info_update_side_data(__int64 a1)
{
  __int64 side_data; // rbx
  __int64 result; // rax

  side_data = av_frame_get_side_data(a1, 4);
  if ( !side_data )
  {
    result = av_frame_new_side_data(a1, 4u, 48);
    side_data = result;
    if ( !result )
      return result;
    sub_18007B020(*(__m128i **)(result + 8), 0, 0x30u);
  }
  return *(_QWORD *)(side_data + 8);
}

```

## disassembly

```asm
0x180036840  mov     [rsp+arg_0], rbx
0x180036845  push    rdi
0x180036846  sub     rsp, 20h
0x18003684a  mov     edx, 4
0x18003684f  mov     rdi, rcx
0x180036852  call    av_frame_get_side_data
0x180036857  mov     rbx, rax
0x18003685a  test    rax, rax
0x18003685d  jnz     short loc_180036885
0x18003685f  lea     edx, [rax+4]
0x180036862  mov     rcx, rdi
0x180036865  lea     r8d, [rax+30h]
0x180036869  call    av_frame_new_side_data
0x18003686e  mov     rbx, rax
0x180036871  test    rax, rax
0x180036874  jz      short loc_180036894
0x180036876  mov     rcx, [rax+8]
0x18003687a  xor     edx, edx
0x18003687c  lea     r8d, [rdx+30h]
0x180036880  call    sub_18007B020
0x180036885  mov     rax, [rbx+8]
0x180036889  mov     rbx, [rsp+28h+arg_0]
0x18003688e  add     rsp, 20h
0x180036892  pop     rdi
0x180036893  retn
0x180036894  jmp     short loc_180036889
```
