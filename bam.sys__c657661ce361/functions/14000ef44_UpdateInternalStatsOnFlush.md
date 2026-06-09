# UpdateInternalStatsOnFlush

- ea: `0x14000ef44`
- end: `0x14000ef86`
- name: `UpdateInternalStatsOnFlush`
- size: `66`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1400132ac`
- `0x1400136dc`

## callees

- `0x14000ef44`

## pseudocode

```c
void __fastcall UpdateInternalStatsOnFlush(__int64 a1, unsigned int a2)
{
  __int64 *v2; // r8
  __int64 v3; // rax

  if ( a2 )
  {
    v2 = (__int64 *)(a1 + 296);
    if ( *(_DWORD *)(a1 + 312) > a2 || (v3 = *v2) == 0 )
    {
      v3 = *v2;
      *(_DWORD *)(a1 + 312) = a2;
    }
    if ( *(_DWORD *)(a1 + 308) < a2 )
      *(_DWORD *)(a1 + 308) = a2;
    *v2 = v3 + 1;
    *(_QWORD *)(a1 + 288) += a2;
  }
}

```

## disassembly

```asm
0x14000ef44  test    edx, edx
0x14000ef46  jz      short locret_14000EF85
0x14000ef48  lea     r8, [rcx+128h]
0x14000ef4f  cmp     [rcx+138h], edx
0x14000ef55  ja      short loc_14000EF5F
0x14000ef57  mov     rax, [r8]
0x14000ef5a  test    rax, rax
0x14000ef5d  jnz     short loc_14000EF68
0x14000ef5f  mov     rax, [r8]
0x14000ef62  mov     [rcx+138h], edx
0x14000ef68  cmp     [rcx+134h], edx
0x14000ef6e  jnb     short loc_14000EF76
0x14000ef70  mov     [rcx+134h], edx
0x14000ef76  inc     rax
0x14000ef79  mov     [r8], rax
0x14000ef7c  mov     eax, edx
0x14000ef7e  add     [rcx+120h], rax
0x14000ef85  retn
```
