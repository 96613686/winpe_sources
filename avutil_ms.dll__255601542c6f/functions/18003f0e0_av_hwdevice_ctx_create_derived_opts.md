# av_hwdevice_ctx_create_derived_opts

- ea: `0x18003f0e0`
- end: `0x18003f137`
- name: `av_hwdevice_ctx_create_derived_opts`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18003f0c0`

## callees

- `0x18002f150`
- `0x18002f210`
- `0x18003f0e0`

## pseudocode

```c
__int64 __fastcall av_hwdevice_ctx_create_derived_opts(__int64 *a1, int a2, __int64 a3)
{
  __int64 v4; // rax
  __int64 result; // rax
  __int64 v6; // rax
  __int64 v7; // [rsp+40h] [rbp+18h] BYREF

  while ( 1 )
  {
    if ( !a3 )
    {
      v7 = 0;
LABEL_6:
      av_buffer_unref(&v7);
      result = 4294967284LL;
      *a1 = 0;
      return result;
    }
    v4 = *(_QWORD *)(a3 + 8);
    if ( *(_DWORD *)(v4 + 8) == a2 )
      break;
    a3 = *(_QWORD *)(v4 + 48);
  }
  v6 = av_buffer_ref(a3);
  v7 = v6;
  if ( !v6 )
    goto LABEL_6;
  *a1 = v6;
  return 0;
}

```

## disassembly

```asm
0x18003f0e0  push    rbx
0x18003f0e2  sub     rsp, 20h
0x18003f0e6  mov     rbx, rcx
0x18003f0e9  jmp     short loc_18003F0F8
0x18003f0eb  mov     rax, [r8+8]
0x18003f0ef  cmp     [rax+8], edx
0x18003f0f2  jz      short loc_18003F11E
0x18003f0f4  mov     r8, [rax+30h]
0x18003f0f8  test    r8, r8
0x18003f0fb  jnz     short loc_18003F0EB
0x18003f0fd  mov     [rsp+28h+arg_10], r8
0x18003f102  lea     rcx, [rsp+28h+arg_10]
0x18003f107  call    av_buffer_unref
0x18003f10c  mov     eax, 0FFFFFFF4h
0x18003f111  mov     qword ptr [rbx], 0
0x18003f118  add     rsp, 20h
0x18003f11c  pop     rbx
0x18003f11d  retn
0x18003f11e  mov     rcx, r8
0x18003f121  call    av_buffer_ref
0x18003f126  mov     [rsp+28h+arg_10], rax
0x18003f12b  test    rax, rax
0x18003f12e  jz      short loc_18003F102
0x18003f130  mov     [rbx], rax
0x18003f133  xor     eax, eax
0x18003f135  jmp     short loc_18003F118
```
