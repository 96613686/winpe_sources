# PortListRemoveRequest

- ea: `0x14000b060`
- end: `0x14000b0b6`
- name: `PortListRemoveRequest`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000facc`

## callees

- `0x14000b060`

## pseudocode

```c
__int64 __fastcall PortListRemoveRequest(__int64 *a1, _QWORD *a2)
{
  __int64 v2; // rax
  _QWORD *v3; // r8
  __int64 result; // rax

  if ( (_QWORD *)a1[2] == a2 )
  {
    a1[2] = *a2;
    a1[5] = a2[2] + 1LL;
  }
  v2 = *a2;
  if ( *(_QWORD **)(*a2 + 8LL) != a2 || (v3 = (_QWORD *)a2[1], (_QWORD *)*v3 != a2) )
    __fastfail(3u);
  *v3 = v2;
  *(_QWORD *)(v2 + 8) = v3;
  result = a1[4];
  --*((_DWORD *)a1 + 6);
  if ( result )
    --*(_DWORD *)(result + 4);
  if ( (__int64 *)a1[2] == a1 )
  {
    result = *a1;
    a1[2] = *a1;
  }
  return result;
}

```

## disassembly

```asm
0x14000b060  cmp     [rcx+10h], rdx
0x14000b064  jnz     short loc_14000B078
0x14000b066  mov     rax, [rdx]
0x14000b069  mov     [rcx+10h], rax
0x14000b06d  mov     rax, [rdx+10h]
0x14000b071  inc     rax
0x14000b074  mov     [rcx+28h], rax
0x14000b078  mov     rax, [rdx]
0x14000b07b  cmp     [rax+8], rdx
0x14000b07f  jnz     short loc_14000B0AF
0x14000b081  mov     r8, [rdx+8]
0x14000b085  cmp     [r8], rdx
0x14000b088  jnz     short loc_14000B0AF
0x14000b08a  mov     [r8], rax
0x14000b08d  mov     [rax+8], r8
0x14000b091  mov     rax, [rcx+20h]
0x14000b095  dec     dword ptr [rcx+18h]
0x14000b098  test    rax, rax
0x14000b09b  jz      short loc_14000B0A0
0x14000b09d  dec     dword ptr [rax+4]
0x14000b0a0  cmp     [rcx+10h], rcx
0x14000b0a4  jnz     short locret_14000B0AD
0x14000b0a6  mov     rax, [rcx]
0x14000b0a9  mov     [rcx+10h], rax
0x14000b0ad  retn
0x14000b0af  mov     ecx, 3
0x14000b0b4  int     29h; Win8: RtlFailFast(ecx)
```
