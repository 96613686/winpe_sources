# VfsUpdateDirQueryContext

- ea: `0x140007acc`
- end: `0x140007ba5`
- name: `VfsUpdateDirQueryContext`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140006710`

## callees

- `0x140007acc`
- `0x140013d00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140007b79`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007b79`
- `ntoskrnl!ExAllocatePool2` at `0x140007b46`
- `ntoskrnl!ExAllocatePool2` at `0x140007b46`

## pseudocode

```c
__int64 __fastcall VfsUpdateDirQueryContext(__int64 a1, __int64 a2)
{
  __int64 v2; // rax
  int v4; // edx
  __int64 *i; // rax
  unsigned int v6; // esi
  __int64 *j; // rbx
  void *Pool2; // rax
  __int64 v10; // rbp

  v2 = *(_QWORD *)(a1 + 16);
  v4 = *(_DWORD *)(v2 + 40);
  if ( (*(_BYTE *)(v2 + 6) & 1) != 0 )
  {
    *(_DWORD *)a2 |= 1u;
    *(_DWORD *)(a2 + 32) = v4;
    for ( i = *(__int64 **)(a2 + 8); i != (__int64 *)(a2 + 8); i = (__int64 *)*i )
    {
      *(__int64 *)((char *)i + 60) = 0;
      *((_DWORD *)i + 17) = 0;
    }
  }
  else if ( *(_DWORD *)(a2 + 32) != v4 )
  {
    return 3221225485LL;
  }
  v6 = (*(_DWORD *)(*(_QWORD *)(a1 + 16) + 24LL) + 7) & 0xFFFFFFF8;
  if ( *(_DWORD *)(a2 + 24) < v6 )
  {
    for ( j = *(__int64 **)(a2 + 8); j != (__int64 *)(a2 + 8); j = (__int64 *)*j )
    {
      if ( *((_DWORD *)j + 14) < v6 )
      {
        Pool2 = (void *)ExAllocatePool2(256, v6, 1648641622);
        v10 = (__int64)Pool2;
        if ( Pool2 )
        {
          if ( *((_DWORD *)j + 15) )
            memmove(Pool2, (const void *)j[6], *((unsigned int *)j + 14));
          ExFreePoolWithTag((PVOID)j[6], 0x62444656u);
          j[6] = v10;
          *((_DWORD *)j + 14) = v6;
        }
      }
    }
    *(_DWORD *)(a2 + 24) = v6;
  }
  return 0;
}

```

## disassembly

```asm
0x140007acc  push    rbx
0x140007ace  push    rbp
0x140007acf  push    rsi
0x140007ad0  push    rdi
0x140007ad1  push    r14
0x140007ad3  sub     rsp, 20h
0x140007ad7  mov     rax, [rcx+10h]
0x140007adb  mov     rdi, rdx
0x140007ade  test    byte ptr [rax+6], 1
0x140007ae2  mov     edx, [rax+28h]
0x140007ae5  jz      short loc_140007B28
0x140007ae7  or      dword ptr [rdi], 1
0x140007aea  mov     [rdi+20h], edx
0x140007aed  lea     rdx, [rdi+8]
0x140007af1  mov     rax, [rdx]
0x140007af4  jmp     short loc_140007B08
0x140007af6  mov     qword ptr [rax+3Ch], 0
0x140007afe  mov     dword ptr [rax+44h], 0
0x140007b05  mov     rax, [rax]
0x140007b08  cmp     rax, rdx
0x140007b0b  jnz     short loc_140007AF6
0x140007b0d  mov     rax, [rcx+10h]
0x140007b11  mov     esi, [rax+18h]
0x140007b14  add     esi, 7
0x140007b17  and     esi, 0FFFFFFF8h
0x140007b1a  cmp     [rdi+18h], esi
0x140007b1d  jnb     short loc_140007B97
0x140007b1f  lea     r14, [rdi+8]
0x140007b23  mov     rbx, [r14]
0x140007b26  jmp     short loc_140007B8F
0x140007b28  cmp     [rdi+20h], edx
0x140007b2b  jz      short loc_140007B0D
0x140007b2d  mov     eax, 0C000000Dh
0x140007b32  jmp     short loc_140007B99
0x140007b34  cmp     [rbx+38h], esi
0x140007b37  jnb     short loc_140007B8C
0x140007b39  mov     edx, esi
0x140007b3b  mov     ecx, 100h
0x140007b40  mov     r8d, 62444656h
0x140007b46  call    cs:__imp_ExAllocatePool2
0x140007b4d  nop     dword ptr [rax+rax+00h]
0x140007b52  mov     rbp, rax
0x140007b55  test    rax, rax
0x140007b58  jz      short loc_140007B8C
0x140007b5a  cmp     dword ptr [rbx+3Ch], 0
0x140007b5e  jbe     short loc_140007B70
0x140007b60  mov     r8d, [rbx+38h]; Size
0x140007b64  mov     rcx, rax; void *
0x140007b67  mov     rdx, [rbx+30h]; Src
0x140007b6b  call    memmove
0x140007b70  mov     rcx, [rbx+30h]; P
0x140007b74  mov     edx, 62444656h; Tag
0x140007b79  call    cs:__imp_ExFreePoolWithTag
0x140007b80  nop     dword ptr [rax+rax+00h]
0x140007b85  mov     [rbx+30h], rbp
0x140007b89  mov     [rbx+38h], esi
0x140007b8c  mov     rbx, [rbx]
0x140007b8f  cmp     rbx, r14
0x140007b92  jnz     short loc_140007B34
0x140007b94  mov     [rdi+18h], esi
0x140007b97  xor     eax, eax
0x140007b99  add     rsp, 20h
0x140007b9d  pop     r14
0x140007b9f  pop     rdi
0x140007ba0  pop     rsi
0x140007ba1  pop     rbp
0x140007ba2  pop     rbx
0x140007ba3  retn
```
