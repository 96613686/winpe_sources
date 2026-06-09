# LKRhash::CLKRHashTable::WriteUnlock(void)

- ea: `0x180008638`
- end: `0x18000868e`
- name: `?WriteUnlock@CLKRHashTable@LKRhash@@QEBAXXZ`
- size: `86`
- prototype: `void __fastcall(LKRhash::CLKRHashTable *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000488c`
- `0x180008250`

## callees

- `0x180008638`

## pseudocode

```c
void __fastcall LKRhash::CLKRHashTable::WriteUnlock(LKRhash::CLKRHashTable *this)
{
  __int64 v1; // r8
  __int64 v2; // r9
  int v3; // edx
  bool v4; // zf
  signed __int32 v5; // edx

  LODWORD(v1) = *((_DWORD *)this + 5);
  while ( (_DWORD)v1 )
  {
    v1 = (unsigned int)(v1 - 1);
    v2 = *(_QWORD *)(*((_QWORD *)this + 3) + 8 * v1);
    if ( *(_BYTE *)(v2 + 153) )
    {
      v3 = *(_DWORD *)(v2 + 28) - 1;
      v4 = (((*(_BYTE *)(v2 + 28) - 1) & 3) != 0 ? v3 : 0) == 0;
      _InterlockedExchange((volatile __int32 *)(v2 + 28), ((*(_BYTE *)(v2 + 28) - 1) & 3) != 0 ? v3 : 0);
      if ( v4 )
      {
        do
          v5 = *(_DWORD *)(v2 + 24);
        while ( v5 != _InterlockedCompareExchange((volatile signed __int32 *)(v2 + 24), (v5 - 0x10000) & 0xFFFF0000, v5) );
      }
    }
  }
}

```

## disassembly

```asm
0x180008638  mov     r8d, [rcx+14h]
0x18000863c  mov     r10, rcx
0x18000863f  jmp     short loc_180008688
0x180008641  mov     rax, [r10+18h]
0x180008645  dec     r8d
0x180008648  mov     r9, [rax+r8*8]
0x18000864c  cmp     byte ptr [r9+99h], 0
0x180008654  jz      short loc_180008688
0x180008656  mov     edx, [r9+1Ch]
0x18000865a  dec     edx
0x18000865c  mov     eax, edx
0x18000865e  and     al, 3
0x180008660  neg     al
0x180008662  sbb     ecx, ecx
0x180008664  and     ecx, edx
0x180008666  xchg    ecx, [r9+1Ch]
0x18000866a  jnz     short loc_180008688
0x18000866c  mov     edx, [r9+18h]
0x180008670  mov     eax, edx
0x180008672  lea     ecx, [rdx-10000h]
0x180008678  and     ecx, 0FFFF0000h
0x18000867e  lock cmpxchg [r9+18h], ecx
0x180008684  cmp     edx, eax
0x180008686  jnz     short loc_18000866C
0x180008688  test    r8d, r8d
0x18000868b  jnz     short loc_180008641
0x18000868d  retn
```
