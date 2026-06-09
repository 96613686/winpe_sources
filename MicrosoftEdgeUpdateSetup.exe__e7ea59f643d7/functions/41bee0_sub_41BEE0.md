# sub_41BEE0

- ea: `0x41bee0`
- end: `0x41beea`
- name: `sub_41BEE0`
- size: `10`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x40c28b`
- `0x41bee0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x418f40`
- `KERNEL32!DeleteCriticalSection` at `0x418f40`

## pseudocode

```c
void __cdecl sub_41BEE0()
{
  DeleteCriticalSection((LPCRITICAL_SECTION)&dword_427344[5]);
  if ( dword_427344[11] )
  {
    free((void *)dword_427344[11]);
    dword_427344[11] = 0;
  }
  dword_427344[12] = 0;
  dword_427344[13] = 0;
}

```

## disassembly

```asm
0x41bee0  mov     ecx, offset dword_427344
0x41bee5  jmp     loc_418F39
0x418f39  push    esi
0x418f3a  mov     esi, ecx
0x418f3c  lea     eax, [esi+14h]
0x418f3f  push    eax; lpCriticalSection
0x418f40  call    ds:DeleteCriticalSection
0x418f46  lea     ecx, [esi+2Ch]
0x418f49  pop     esi
0x418f4a  jmp     loc_418FBF
0x418fbf  push    esi
0x418fc0  mov     esi, ecx
0x418fc2  cmp     dword ptr [esi], 0
0x418fc5  jz      short loc_418FD2
0x418fc7  push    dword ptr [esi]; Block
0x418fc9  call    _free
0x418fce  and     dword ptr [esi], 0
0x418fd1  pop     ecx
0x418fd2  and     dword ptr [esi+4], 0
0x418fd6  and     dword ptr [esi+8], 0
0x418fda  pop     esi
0x418fdb  retn
```
