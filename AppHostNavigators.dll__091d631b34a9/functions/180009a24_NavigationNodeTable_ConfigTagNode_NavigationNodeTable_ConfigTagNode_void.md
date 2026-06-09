# NavigationNodeTable<ConfigTagNode>::~NavigationNodeTable<ConfigTagNode>(void)

- ea: `0x180009a24`
- end: `0x180009a9b`
- name: `??1?$NavigationNodeTable@VConfigTagNode@@@@UEAA@XZ`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180009bc0`

## callees

- `0x180004370`
- `0x180004d20`
- `0x180009a24`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x180009a85`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180009a85`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180009a3e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180009a3e`

## pseudocode

```c
__int64 __fastcall NavigationNodeTable<ConfigTagNode>::~NavigationNodeTable<ConfigTagNode>(__int64 a1)
{
  __int64 i; // rsi
  __int64 v3; // rax
  _QWORD *v4; // rdx
  _QWORD *v5; // rbx

  *(_QWORD *)a1 = &NavigationNodeTable<ConfigPathTagNode>::`vftable';
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 24));
  for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 16); i = (unsigned int)(i + 1) )
  {
    v3 = *(_QWORD *)(a1 + 8);
    v4 = *(_QWORD **)(v3 + 8 * i);
    *(_QWORD *)(v3 + 8 * i) = 0;
    if ( v4 )
    {
      do
      {
        v5 = (_QWORD *)*v4;
        HASH_TABLE<FileSystemTagNode,unsigned short const *>::DeleteNode(a1, v4);
        v4 = v5;
      }
      while ( v5 );
    }
  }
  *(_DWORD *)(a1 + 20) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 24));
  return HASH_TABLE<unsigned short const,unsigned short const *>::~HASH_TABLE<unsigned short const,unsigned short const *>(a1);
}

```

## disassembly

```asm
0x180009a24  push    rbx
0x180009a26  push    rbp
0x180009a27  push    rsi
0x180009a28  push    rdi
0x180009a29  sub     rsp, 28h
0x180009a2d  mov     rdi, rcx
0x180009a30  lea     rax, ??_7?$NavigationNodeTable@VConfigPathTagNode@@@@6B@; const NavigationNodeTable<ConfigPathTagNode>::`vftable'
0x180009a37  mov     [rcx], rax
0x180009a3a  add     rcx, 18h; SRWLock
0x180009a3e  call    cs:__imp_AcquireSRWLockExclusive
0x180009a44  xor     esi, esi
0x180009a46  cmp     [rdi+10h], esi
0x180009a49  jbe     short loc_180009A7A
0x180009a4b  mov     rax, [rdi+8]
0x180009a4f  mov     rdx, [rax+rsi*8]
0x180009a53  mov     qword ptr [rax+rsi*8], 0
0x180009a5b  test    rdx, rdx
0x180009a5e  jz      short loc_180009A73
0x180009a60  mov     rbx, [rdx]
0x180009a63  mov     rcx, rdi
0x180009a66  call    ?DeleteNode@?$HASH_TABLE@VFileSystemTagNode@@PEBG@@AEAAXPEAV?$HASH_NODE@VFileSystemTagNode@@@@@Z; HASH_TABLE<FileSystemTagNode,ushort const *>::DeleteNode(HASH_NODE<FileSystemTagNode> *)
0x180009a6b  mov     rdx, rbx
0x180009a6e  test    rbx, rbx
0x180009a71  jnz     short loc_180009A60
0x180009a73  inc     esi
0x180009a75  cmp     esi, [rdi+10h]
0x180009a78  jb      short loc_180009A4B
0x180009a7a  mov     dword ptr [rdi+14h], 0
0x180009a81  lea     rcx, [rdi+18h]; SRWLock
0x180009a85  call    cs:__imp_ReleaseSRWLockExclusive
0x180009a8b  mov     rcx, rdi
0x180009a8e  add     rsp, 28h
0x180009a92  pop     rdi
0x180009a93  pop     rsi
0x180009a94  pop     rbp
0x180009a95  pop     rbx
0x180009a96  jmp     ??1?$HASH_TABLE@$$CBGPEBG@@UEAA@XZ; HASH_TABLE<ushort const,ushort const *>::~HASH_TABLE<ushort const,ushort const *>(void)
```
