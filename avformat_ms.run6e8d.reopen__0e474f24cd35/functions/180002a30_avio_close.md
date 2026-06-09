# avio_close

- ea: `0x180002a30`
- end: `0x180002b09`
- name: `avio_close`
- size: `217`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x180002bb0`
- `0x180002e8c`
- `0x180019770`

## callees

- `0x180002a30`
- `0x18000320c`
- `0x180003f70`
- `0x180003fb0`
- `0x18001bb58`
- `0x18001bba6`
- `0x18001bbbe`

## string_xrefs

- `0x180002a88`: `Statistics: %lld bytes written, %d seeks, %d writeouts\n`
- `0x180002ab1`: `Statistics: %lld bytes read, %d seeks\n`

## pseudocode

```c
__int64 __fastcall avio_close(__int64 a1)
{
  __int64 result; // rax
  __int64 v3; // rdi
  unsigned int v4; // ebx
  __int64 v5; // [rsp+40h] [rbp+8h] BYREF
  __int64 v6; // [rsp+48h] [rbp+10h] BYREF

  v5 = a1;
  if ( !a1 )
    return 0;
  avio_flush(a1);
  v3 = *(_QWORD *)(v5 + 40);
  *(_QWORD *)(v5 + 40) = 0;
  av_freep(v5 + 8);
  if ( *(_DWORD *)(v5 + 88) )
    av_log(
      v5,
      40,
      "Statistics: %lld bytes written, %d seeks, %d writeouts\n",
      *(_QWORD *)(a1 + 240),
      *(_DWORD *)(a1 + 248),
      *(_DWORD *)(a1 + 252));
  else
    av_log(v5, 40, "Statistics: %lld bytes read, %d seeks\n", *(_QWORD *)(a1 + 232), *(_DWORD *)(a1 + 248));
  av_opt_free(v5);
  v4 = *(_DWORD *)(v5 + 84);
  avio_context_free(&v5);
  v6 = v3;
  result = sub_18000320C(&v6);
  if ( (int)result >= 0 )
    return v4;
  _mm_lfence();
  return result;
}

```

## disassembly

```asm
0x180002a30  mov     [rsp+arg_10], rbx
0x180002a35  mov     [rsp+arg_0], rcx
0x180002a3a  push    rdi
0x180002a3b  sub     rsp, 30h
0x180002a3f  mov     rbx, rcx
0x180002a42  test    rcx, rcx
0x180002a45  jnz     short loc_180002A4E
0x180002a47  xor     eax, eax
0x180002a49  jmp     loc_180002AFE
0x180002a4e  call    avio_flush
0x180002a53  mov     rax, [rsp+38h+arg_0]
0x180002a58  mov     rdi, [rax+28h]
0x180002a5c  mov     qword ptr [rax+28h], 0
0x180002a64  mov     rcx, [rsp+38h+arg_0]
0x180002a69  add     rcx, 8
0x180002a6d  call    av_freep
0x180002a72  mov     rcx, [rsp+38h+arg_0]
0x180002a77  mov     edx, 28h ; '('
0x180002a7c  cmp     dword ptr [rcx+58h], 0
0x180002a80  jz      short loc_180002AAB
0x180002a82  mov     eax, [rbx+0FCh]
0x180002a88  lea     r8, aStatisticsLldB; "Statistics: %lld bytes written, %d seek"...
0x180002a8f  mov     r9, [rbx+0F0h]
0x180002a96  mov     [rsp+38h+var_10], eax
0x180002a9a  mov     eax, [rbx+0F8h]
0x180002aa0  mov     [rsp+38h+var_18], eax
0x180002aa4  call    av_log
0x180002aa9  jmp     short loc_180002AC8
0x180002aab  mov     eax, [rbx+0F8h]
0x180002ab1  lea     r8, aStatisticsLldB_0; "Statistics: %lld bytes read, %d seeks\n"
0x180002ab8  mov     r9, [rbx+0E8h]
0x180002abf  mov     [rsp+38h+var_18], eax
0x180002ac3  call    av_log
0x180002ac8  mov     rcx, [rsp+38h+arg_0]
0x180002acd  call    av_opt_free
0x180002ad2  mov     rax, [rsp+38h+arg_0]
0x180002ad7  lea     rcx, [rsp+38h+arg_0]
0x180002adc  mov     ebx, [rax+54h]
0x180002adf  call    avio_context_free
0x180002ae4  lea     rcx, [rsp+38h+arg_8]
0x180002ae9  mov     [rsp+38h+arg_8], rdi
0x180002aee  call    sub_18000320C
0x180002af3  test    eax, eax
0x180002af5  jns     short loc_180002AFC
0x180002af7  lfence
0x180002afa  jmp     short loc_180002AFE
0x180002afc  mov     eax, ebx
0x180002afe  mov     rbx, [rsp+38h+arg_10]
0x180002b03  add     rsp, 30h
0x180002b07  pop     rdi
0x180002b08  retn
```
