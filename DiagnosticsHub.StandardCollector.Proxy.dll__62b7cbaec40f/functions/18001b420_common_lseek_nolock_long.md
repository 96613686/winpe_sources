# common_lseek_nolock_long_

- ea: `0x18001b420`
- end: `0x18001b4ab`
- name: `common_lseek_nolock_long_`
- size: `139`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001b1e4`
- `0x18001b704`
- `0x18001b79c`

## callees

- `0x180014d78`
- `0x18001b420`
- `0x18001b55c`

## pseudocode

```c
__int64 __fastcall common_lseek_nolock_long_(int a1, int a2, DWORD a3, __int64 a4)
{
  __int64 v4; // rdi
  void *osfhandle; // rax
  unsigned int v10; // edx

  v4 = a1;
  osfhandle = (void *)get_osfhandle(a1);
  if ( osfhandle == (void *)-1LL )
  {
    *(_BYTE *)(a4 + 48) = 1;
    *(_DWORD *)(a4 + 44) = 9;
    return 0xFFFFFFFFLL;
  }
  v10 = common_lseek_do_seek_nolock(osfhandle, a2, a3, a4);
  if ( v10 == -1 )
    return 0xFFFFFFFFLL;
  *(_BYTE *)(_pioinfo[v4 >> 6] + 72 * (v4 & 0x3F) + 56) &= ~2u;
  return v10;
}

```

## disassembly

```asm
0x18001b420  mov     [rsp+arg_0], rbx
0x18001b425  mov     [rsp+arg_8], rbp
0x18001b42a  mov     [rsp+arg_10], rsi
0x18001b42f  push    rdi
0x18001b430  sub     rsp, 20h
0x18001b434  movsxd  rdi, ecx
0x18001b437  mov     rbx, r9
0x18001b43a  mov     ecx, edi; FileHandle
0x18001b43c  mov     esi, r8d
0x18001b43f  mov     ebp, edx
0x18001b441  call    _get_osfhandle
0x18001b446  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001b44a  jnz     short loc_18001B45C
0x18001b44c  mov     byte ptr [rbx+30h], 1
0x18001b450  mov     dword ptr [rbx+2Ch], 9
0x18001b457  or      eax, 0FFFFFFFFh
0x18001b45a  jmp     short loc_18001B496
0x18001b45c  mov     r9, rbx
0x18001b45f  mov     r8d, esi
0x18001b462  mov     edx, ebp
0x18001b464  mov     rcx, rax; hFile
0x18001b467  call    common_lseek_do_seek_nolock
0x18001b46c  mov     edx, eax
0x18001b46e  cmp     eax, 0FFFFFFFFh
0x18001b471  jz      short loc_18001B457
0x18001b473  mov     rcx, rdi
0x18001b476  lea     r8, __pioinfo
0x18001b47d  and     ecx, 3Fh
0x18001b480  mov     rax, rdi
0x18001b483  sar     rax, 6
0x18001b487  lea     rcx, [rcx+rcx*8]
0x18001b48b  mov     rax, [r8+rax*8]
0x18001b48f  and     byte ptr [rax+rcx*8+38h], 0FDh
0x18001b494  mov     eax, edx
0x18001b496  mov     rbx, [rsp+28h+arg_0]
0x18001b49b  mov     rbp, [rsp+28h+arg_8]
0x18001b4a0  mov     rsi, [rsp+28h+arg_10]
0x18001b4a5  add     rsp, 20h
0x18001b4a9  pop     rdi
0x18001b4aa  retn
```
