# av_ambient_viewing_environment_create_side_data

- ea: `0x18002a730`
- end: `0x18002a789`
- name: `av_ambient_viewing_environment_create_side_data`
- size: `89`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x18002a730`
- `0x18003b750`
- `0x18007b020`

## pseudocode

```c
__int64 __fastcall av_ambient_viewing_environment_create_side_data(__int64 a1)
{
  __int64 result; // rax
  __int64 v2; // rbx
  _QWORD *v3; // rcx

  result = av_frame_new_side_data(a1, 0x1Au, 24);
  v2 = result;
  if ( result )
  {
    sub_18007B020(*(__m128i **)(result + 8), 0, *(_QWORD *)(result + 16));
    v3 = *(_QWORD **)(v2 + 8);
    v3[2] = 0x100000000LL;
    v3[1] = 0x100000000LL;
    *v3 = 0x100000000LL;
    return *(_QWORD *)(v2 + 8);
  }
  return result;
}

```

## disassembly

```asm
0x18002a730  push    rbx
0x18002a732  sub     rsp, 20h
0x18002a736  mov     edx, 1Ah
0x18002a73b  lea     r8d, [rdx-2]
0x18002a73f  call    av_frame_new_side_data
0x18002a744  mov     rbx, rax
0x18002a747  test    rax, rax
0x18002a74a  jz      short loc_18002A783
0x18002a74c  mov     r8, [rax+10h]
0x18002a750  xor     edx, edx
0x18002a752  mov     rcx, [rax+8]
0x18002a756  call    sub_18007B020
0x18002a75b  mov     rcx, [rbx+8]
0x18002a75f  mov     dword ptr [rsp+28h+arg_8], 0
0x18002a767  mov     dword ptr [rsp+28h+arg_8+4], 1
0x18002a76f  mov     rax, [rsp+28h+arg_8]
0x18002a774  mov     [rcx+10h], rax
0x18002a778  mov     [rcx+8], rax
0x18002a77c  mov     [rcx], rax
0x18002a77f  mov     rax, [rbx+8]
0x18002a783  add     rsp, 20h
0x18002a787  pop     rbx
0x18002a788  retn
```
