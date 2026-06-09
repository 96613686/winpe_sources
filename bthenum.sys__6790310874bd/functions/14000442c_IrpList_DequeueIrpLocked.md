# IrpList_DequeueIrpLocked

- ea: `0x14000442c`
- end: `0x140004490`
- name: `IrpList_DequeueIrpLocked`
- size: `100`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140002b64`
- `0x140003060`

## callees

- `0x14000442c`

## pseudocode

```c
char __fastcall IrpList_DequeueIrpLocked(__int64 a1, _QWORD *a2)
{
  _QWORD *v2; // r8
  __int64 v3; // rax
  _QWORD *v4; // r9
  _QWORD *v5; // r10
  _QWORD *v6; // rax

  v2 = *(_QWORD **)a1;
  LOBYTE(v3) = 0;
  if ( *(_QWORD *)a1 != a1 )
  {
    while ( 1 )
    {
      v4 = (_QWORD *)*v2;
      v5 = v2 - 21;
      if ( v2 - 21 == a2 )
        break;
      v2 = (_QWORD *)*v2;
      if ( v4 == (_QWORD *)a1 )
        return v3;
    }
    if ( (_QWORD *)v4[1] != v2 || (v6 = (_QWORD *)v2[1], (_QWORD *)*v6 != v2) )
      __fastfail(3u);
    *v6 = v4;
    v4[1] = v6;
    --*(_DWORD *)(a1 + 32);
    v3 = _InterlockedExchange64(v5 + 13, 0);
    if ( v3 )
    {
      v5[18] = 0;
      LOBYTE(v3) = 1;
    }
    v2[1] = v2;
    *v2 = v2;
  }
  return v3;
}

```

## disassembly

```asm
0x14000442c  mov     r8, [rcx]
0x14000442f  xor     al, al
0x140004431  cmp     r8, rcx
0x140004434  jz      short locret_14000444D
0x140004436  mov     r9, [r8]
0x140004439  lea     r10, [r8-0A8h]
0x140004440  cmp     r10, rdx
0x140004443  jz      short loc_14000444F
0x140004445  mov     r8, r9
0x140004448  cmp     r9, rcx
0x14000444b  jnz     short loc_140004436
0x14000444d  retn
0x14000444f  cmp     [r9+8], r8
0x140004453  jnz     short loc_140004489
0x140004455  mov     rax, [r8+8]
0x140004459  cmp     [rax], r8
0x14000445c  jnz     short loc_140004489
0x14000445e  mov     [rax], r9
0x140004461  mov     [r9+8], rax
0x140004465  xor     eax, eax
0x140004467  dec     dword ptr [rcx+20h]
0x14000446a  xchg    rax, [r10+68h]
0x14000446e  test    rax, rax
0x140004471  jz      short loc_140004480
0x140004473  mov     qword ptr [r10+90h], 0
0x14000447e  mov     al, 1
0x140004480  mov     [r8+8], r8
0x140004484  mov     [r8], r8
0x140004487  retn
0x140004489  mov     ecx, 3
0x14000448e  int     29h; Win8: RtlFailFast(ecx)
```
