# BaseSrvGetWOWTaskId

- ea: `0x18000b4a4`
- end: `0x18000b51d`
- name: `BaseSrvGetWOWTaskId`
- size: `121`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18000806c`
- `0x1800085bc`

## callees

- `0x18000b4a4`

## pseudocode

```c
__int64 BaseSrvGetWOWTaskId()
{
  unsigned int v0; // edx
  _QWORD *v1; // rcx
  int v2; // r8d
  __int64 i; // r8
  __int64 result; // rax

  v0 = WOWTaskIdNext;
  v1 = (_QWORD *)gWowHead;
  if ( WOWTaskIdNext == -2 )
  {
    v2 = 1;
    dword_180013678 = 1;
    v0 = 1;
  }
  else
  {
    v2 = dword_180013678;
  }
  if ( v2 && gWowHead )
  {
    do
    {
      for ( i = v1[7]; ; i = *(_QWORD *)(i + 32) )
      {
        if ( !i )
        {
          v1 = (_QWORD *)*v1;
          goto LABEL_14;
        }
        if ( *(_DWORD *)i == v0 )
          break;
      }
      if ( ++v0 == -2 )
        v0 = 1;
      v1 = (_QWORD *)gWowHead;
LABEL_14:
      ;
    }
    while ( v1 );
  }
  result = v0;
  WOWTaskIdNext = v0 + 1;
  return result;
}

```

## disassembly

```asm
0x18000b4a4  mov     rax, cs:gWowHead
0x18000b4ab  mov     r10d, 0FFFFFFFEh
0x18000b4b1  mov     edx, cs:WOWTaskIdNext
0x18000b4b7  mov     rcx, rax
0x18000b4ba  mov     r9d, 1
0x18000b4c0  cmp     edx, r10d
0x18000b4c3  jnz     short loc_18000B4D4
0x18000b4c5  mov     r8d, r9d
0x18000b4c8  mov     cs:dword_180013678, r9d
0x18000b4cf  mov     edx, r9d
0x18000b4d2  jmp     short loc_18000B4DB
0x18000b4d4  mov     r8d, cs:dword_180013678
0x18000b4db  test    r8d, r8d
0x18000b4de  jz      short loc_18000B511
0x18000b4e0  test    rax, rax
0x18000b4e3  jz      short loc_18000B511
0x18000b4e5  mov     r8, [rcx+38h]
0x18000b4e9  test    r8, r8
0x18000b4ec  jz      short loc_18000B509
0x18000b4ee  cmp     [r8], edx
0x18000b4f1  jz      short loc_18000B4F9
0x18000b4f3  mov     r8, [r8+20h]
0x18000b4f7  jmp     short loc_18000B4E9
0x18000b4f9  add     edx, r9d
0x18000b4fc  cmp     edx, r10d
0x18000b4ff  jnz     short loc_18000B504
0x18000b501  mov     edx, r9d
0x18000b504  mov     rcx, rax
0x18000b507  jmp     short loc_18000B50C
0x18000b509  mov     rcx, [rcx]
0x18000b50c  test    rcx, rcx
0x18000b50f  jnz     short loc_18000B4E5
0x18000b511  lea     ecx, [rdx+1]
0x18000b514  mov     eax, edx
0x18000b516  mov     cs:WOWTaskIdNext, ecx
0x18000b51c  retn
```
