# common_lseek_nolock_long_

- ea: `0x18001acc0`
- end: `0x18001ad4b`
- name: `common_lseek_nolock_long_`
- size: `139`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001aa84`
- `0x18001afa4`
- `0x18001b03c`

## callees

- `0x180014618`
- `0x18001acc0`
- `0x18001adfc`

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
0x18001acc0  mov     [rsp+arg_0], rbx
0x18001acc5  mov     [rsp+arg_8], rbp
0x18001acca  mov     [rsp+arg_10], rsi
0x18001accf  push    rdi
0x18001acd0  sub     rsp, 20h
0x18001acd4  movsxd  rdi, ecx
0x18001acd7  mov     rbx, r9
0x18001acda  mov     ecx, edi; FileHandle
0x18001acdc  mov     esi, r8d
0x18001acdf  mov     ebp, edx
0x18001ace1  call    _get_osfhandle
0x18001ace6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001acea  jnz     short loc_18001ACFC
0x18001acec  mov     byte ptr [rbx+30h], 1
0x18001acf0  mov     dword ptr [rbx+2Ch], 9
0x18001acf7  or      eax, 0FFFFFFFFh
0x18001acfa  jmp     short loc_18001AD36
0x18001acfc  mov     r9, rbx
0x18001acff  mov     r8d, esi
0x18001ad02  mov     edx, ebp
0x18001ad04  mov     rcx, rax; hFile
0x18001ad07  call    common_lseek_do_seek_nolock
0x18001ad0c  mov     edx, eax
0x18001ad0e  cmp     eax, 0FFFFFFFFh
0x18001ad11  jz      short loc_18001ACF7
0x18001ad13  mov     rcx, rdi
0x18001ad16  lea     r8, __pioinfo
0x18001ad1d  and     ecx, 3Fh
0x18001ad20  mov     rax, rdi
0x18001ad23  sar     rax, 6
0x18001ad27  lea     rcx, [rcx+rcx*8]
0x18001ad2b  mov     rax, [r8+rax*8]
0x18001ad2f  and     byte ptr [rax+rcx*8+38h], 0FDh
0x18001ad34  mov     eax, edx
0x18001ad36  mov     rbx, [rsp+28h+arg_0]
0x18001ad3b  mov     rbp, [rsp+28h+arg_8]
0x18001ad40  mov     rsi, [rsp+28h+arg_10]
0x18001ad45  add     rsp, 20h
0x18001ad49  pop     rdi
0x18001ad4a  retn
```
