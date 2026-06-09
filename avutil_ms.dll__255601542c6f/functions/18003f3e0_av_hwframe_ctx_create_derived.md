# av_hwframe_ctx_create_derived

- ea: `0x18003f3e0`
- end: `0x18003f516`
- name: `av_hwframe_ctx_create_derived`
- size: `310`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18002f150`
- `0x18002f210`
- `0x18003f2d0`
- `0x18003f3e0`
- `0x18007a900`

## pseudocode

```c
__int64 __fastcall av_hwframe_ctx_create_derived(__int64 *a1, int a2, __int64 a3, __int64 a4, unsigned int a5)
{
  __int64 v5; // rdi
  __int64 v9; // rcx
  __int64 v10; // rax
  unsigned int v11; // ebx
  __int64 v12; // rax
  __int64 v13; // rbx
  __int64 v14; // rax
  __int64 v15; // r14
  unsigned int v16; // ebp
  int v17; // ecx
  __int64 (__fastcall *v18)(__int64, __int64, _QWORD); // rax
  __int64 (__fastcall *v19)(__int64, __int64, _QWORD); // rax
  __int64 v21; // [rsp+58h] [rbp+20h] BYREF

  v5 = *(_QWORD *)(a4 + 8);
  v21 = 0;
  v9 = *(_QWORD *)(v5 + 96);
  if ( !v9 || *(_QWORD *)(*(_QWORD *)(v9 + 8) + 16LL) != *(_QWORD *)(a3 + 8) )
  {
    v12 = av_hwframe_ctx_alloc(a3);
    v21 = v12;
    if ( !v12 )
      goto LABEL_4;
    v13 = *(_QWORD *)(v12 + 8);
    *(_DWORD *)(v13 + 60) = a2;
    *(_DWORD *)(v13 + 64) = *(_DWORD *)(v5 + 64);
    *(_DWORD *)(v13 + 68) = *(_DWORD *)(v5 + 68);
    *(_DWORD *)(v13 + 72) = *(_DWORD *)(v5 + 72);
    v14 = av_buffer_ref(a4);
    v15 = v13 + 96;
    *(_QWORD *)(v13 + 96) = v14;
    if ( v14 )
    {
      v16 = a5;
      v17 = -40;
      *(_DWORD *)(v13 + 104) = a5 & 0xF;
      v18 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)(v5 + 80) + 160LL);
      if ( !v18 || (v17 = v18(v13, v5, v16), v17 == -40) )
      {
        v19 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)(v13 + 80) + 152LL);
        if ( v19 )
          v17 = v19(v13, v5, v16);
      }
      v11 = 0;
      if ( v17 != -40 )
        v11 = v17;
      if ( !v11 )
      {
        *a1 = v21;
        return 0;
      }
    }
    else
    {
      v11 = -12;
    }
    av_buffer_unref(v15);
    goto LABEL_16;
  }
  v10 = av_buffer_ref(v9);
  *a1 = v10;
  if ( !v10 )
  {
LABEL_4:
    v11 = -12;
LABEL_16:
    av_buffer_unref(&v21);
    return v11;
  }
  return 0;
}

```

## disassembly

```asm
0x18003f3e0  mov     [rsp+arg_0], rbx
0x18003f3e5  mov     [rsp+arg_8], rbp
0x18003f3ea  push    rsi
0x18003f3eb  push    rdi
0x18003f3ec  push    r14
0x18003f3ee  sub     rsp, 20h
0x18003f3f2  mov     rdi, [r9+8]
0x18003f3f6  mov     rsi, rcx
0x18003f3f9  mov     [rsp+38h+arg_18], 0
0x18003f402  mov     rbp, r9
0x18003f405  mov     r14d, edx
0x18003f408  mov     rcx, [rdi+60h]
0x18003f40c  test    rcx, rcx
0x18003f40f  jz      short loc_18003F43A
0x18003f411  mov     r10, [rcx+8]
0x18003f415  mov     rax, [r8+8]
0x18003f419  cmp     [r10+10h], rax
0x18003f41d  jnz     short loc_18003F43A
0x18003f41f  call    av_buffer_ref
0x18003f424  mov     [rsi], rax
0x18003f427  test    rax, rax
0x18003f42a  jnz     loc_18003F501
0x18003f430  mov     ebx, 0FFFFFFF4h
0x18003f435  jmp     loc_18003F4EB
0x18003f43a  mov     rcx, r8
0x18003f43d  call    av_hwframe_ctx_alloc
0x18003f442  mov     [rsp+38h+arg_18], rax
0x18003f447  test    rax, rax
0x18003f44a  jz      short loc_18003F430
0x18003f44c  mov     rbx, [rax+8]
0x18003f450  mov     rcx, rbp
0x18003f453  mov     [rbx+3Ch], r14d
0x18003f457  mov     eax, [rdi+40h]
0x18003f45a  mov     [rbx+40h], eax
0x18003f45d  mov     eax, [rdi+44h]
0x18003f460  mov     [rbx+44h], eax
0x18003f463  mov     eax, [rdi+48h]
0x18003f466  mov     [rbx+48h], eax
0x18003f469  call    av_buffer_ref
0x18003f46e  lea     r14, [rbx+60h]
0x18003f472  mov     [r14], rax
0x18003f475  test    rax, rax
0x18003f478  jnz     short loc_18003F47F
0x18003f47a  lea     ebx, [rax-0Ch]
0x18003f47d  jmp     short loc_18003F4E3
0x18003f47f  mov     ebp, [rsp+38h+arg_20]
0x18003f483  mov     ecx, 0FFFFFFD8h
0x18003f488  mov     eax, ebp
0x18003f48a  and     eax, 0Fh
0x18003f48d  mov     [rbx+68h], eax
0x18003f490  mov     rax, [rdi+50h]
0x18003f494  mov     rax, [rax+0A0h]
0x18003f49b  test    rax, rax
0x18003f49e  jz      short loc_18003F4B6
0x18003f4a0  mov     r8d, ebp
0x18003f4a3  mov     rdx, rdi
0x18003f4a6  mov     rcx, rbx
0x18003f4a9  call    cs:__guard_dispatch_icall_fptr
0x18003f4af  mov     ecx, eax
0x18003f4b1  cmp     eax, 0FFFFFFD8h
0x18003f4b4  jnz     short loc_18003F4D7
0x18003f4b6  mov     r9, [rbx+50h]
0x18003f4ba  mov     rax, [r9+98h]
0x18003f4c1  test    rax, rax
0x18003f4c4  jz      short loc_18003F4D7
0x18003f4c6  mov     r8d, ebp
0x18003f4c9  mov     rdx, rdi
0x18003f4cc  mov     rcx, rbx
0x18003f4cf  call    cs:__guard_dispatch_icall_fptr
0x18003f4d5  mov     ecx, eax
0x18003f4d7  xor     ebx, ebx
0x18003f4d9  cmp     ecx, 0FFFFFFD8h
0x18003f4dc  cmovnz  ebx, ecx
0x18003f4df  test    ebx, ebx
0x18003f4e1  jz      short loc_18003F4F9
0x18003f4e3  mov     rcx, r14
0x18003f4e6  call    av_buffer_unref
0x18003f4eb  lea     rcx, [rsp+38h+arg_18]
0x18003f4f0  call    av_buffer_unref
0x18003f4f5  mov     eax, ebx
0x18003f4f7  jmp     short loc_18003F503
0x18003f4f9  mov     rax, [rsp+38h+arg_18]
0x18003f4fe  mov     [rsi], rax
0x18003f501  xor     eax, eax
0x18003f503  mov     rbx, [rsp+38h+arg_0]
0x18003f508  mov     rbp, [rsp+38h+arg_8]
0x18003f50d  add     rsp, 20h
0x18003f511  pop     r14
0x18003f513  pop     rdi
0x18003f514  pop     rsi
0x18003f515  retn
```
