# ApplicationMemory::UpdateVariable(ushort,void *,uint)

- ea: `0x180020718`
- end: `0x1800207a9`
- name: `?UpdateVariable@ApplicationMemory@@QEAAJGPEAXI@Z`
- size: `145`
- prototype: `__int64 __fastcall(ApplicationMemory *__hidden this, unsigned __int16, void *, unsigned int)`
- caller_count: `7`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18001e93c`
- `0x18001eac4`
- `0x18001f948`
- `0x18001fa3c`
- `0x180021684`
- `0x180021a30`
- `0x180021d80`

## callees

- `0x180020718`
- `0x180023054`

## pseudocode

```c
__int64 __fastcall ApplicationMemory::UpdateVariable(ApplicationMemory *this, unsigned __int16 a2, void *a3, int a4)
{
  __int64 *v7; // rcx
  __int64 i; // rax
  __int64 v9; // rbx
  void *v10; // [rsp+40h] [rbp+18h] BYREF

  v10 = a3;
  if ( a2 >= 0x100u )
    return 2147942487LL;
  v7 = (__int64 *)((char *)this + 4120);
  for ( i = *v7; i != v7[1] && *(_WORD *)i != a2; i += 8 )
    ;
  v9 = 16LL * a2;
  if ( i != v7[1] )
  {
    *(_DWORD *)(i + 4) = a4;
LABEL_9:
    *(_DWORD *)((char *)this + v9 + 8) = a4;
    return 0;
  }
  if ( *(_DWORD *)((char *)this + v9 + 8) == a4 )
    goto LABEL_9;
  LOWORD(v10) = a2;
  HIDWORD(v10) = a4;
  if ( (unsigned __int8)utl::vector<utl::pair<unsigned short,unsigned int>,utl::allocator<utl::pair<unsigned short,unsigned int>>>::push_back(
                          v7,
                          &v10) )
    goto LABEL_9;
  return 2147942414LL;
}

```

## disassembly

```asm
0x180020718  mov     [rsp+arg_0], rbx
0x18002071d  mov     [rsp+arg_8], rsi
0x180020722  mov     [rsp+arg_10], r8
0x180020727  push    rdi
0x180020728  sub     rsp, 20h
0x18002072c  mov     eax, 100h
0x180020731  mov     edi, r9d
0x180020734  mov     rsi, rcx
0x180020737  cmp     dx, ax
0x18002073a  jb      short loc_180020743
0x18002073c  mov     eax, 80070057h
0x180020741  jmp     short loc_180020774
0x180020743  add     rcx, 1018h
0x18002074a  mov     rax, [rcx]
0x18002074d  cmp     rax, [rcx+8]
0x180020751  jz      short loc_18002075E
0x180020753  cmp     [rax], dx
0x180020756  jz      short loc_18002075E
0x180020758  add     rax, 8
0x18002075c  jmp     short loc_18002074D
0x18002075e  movzx   ebx, dx
0x180020761  shl     rbx, 4
0x180020765  cmp     rax, [rcx+8]
0x180020769  jz      short loc_180020785
0x18002076b  mov     [rax+4], edi
0x18002076e  mov     [rbx+rsi+8], edi
0x180020772  xor     eax, eax
0x180020774  mov     rbx, [rsp+28h+arg_0]
0x180020779  mov     rsi, [rsp+28h+arg_8]
0x18002077e  add     rsp, 20h
0x180020782  pop     rdi
0x180020783  retn
0x180020785  cmp     [rbx+rsi+8], edi
0x180020789  jz      short loc_18002076E
0x18002078b  mov     word ptr [rsp+28h+arg_10], dx
0x180020790  lea     rdx, [rsp+28h+arg_10]
0x180020795  mov     dword ptr [rsp+28h+arg_10+4], edi
0x180020799  call    ?push_back@?$vector@U?$pair@GI@utl@@V?$allocator@U?$pair@GI@utl@@@2@@utl@@QEAA_N$$QEAU?$pair@GI@2@@Z; utl::vector<utl::pair<ushort,uint>,utl::allocator<utl::pair<ushort,uint>>>::push_back(utl::pair<ushort,uint> &&)
0x18002079e  test    al, al
0x1800207a0  jnz     short loc_18002076E
0x1800207a2  mov     eax, 8007000Eh
0x1800207a7  jmp     short loc_180020774
```
