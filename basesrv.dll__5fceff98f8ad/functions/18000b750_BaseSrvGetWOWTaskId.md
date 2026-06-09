# BaseSrvGetWOWTaskId

- ea: `0x18000b750`
- end: `0x18000b7c6`
- name: `BaseSrvGetWOWTaskId`
- size: `118`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180008394`
- `0x1800088b0`

## callees

- `0x18000b750`

## pseudocode

```c
__int64 BaseSrvGetWOWTaskId()
{
  unsigned int v0; // edx
  int v1; // eax
  _QWORD *v2; // rcx
  __int64 i; // r8
  __int64 result; // rax

  v0 = WOWTaskIdNext;
  if ( WOWTaskIdNext == -2 )
  {
    v1 = 1;
    v0 = 1;
    dword_180013678 = 1;
  }
  else
  {
    v1 = dword_180013678;
  }
  if ( v1 )
  {
    v2 = (_QWORD *)gWowHead;
    if ( gWowHead )
    {
      do
      {
        for ( i = v2[7]; ; i = *(_QWORD *)(i + 32) )
        {
          if ( !i )
          {
            v2 = (_QWORD *)*v2;
            goto LABEL_14;
          }
          if ( *(_DWORD *)i == v0 )
            break;
        }
        if ( ++v0 == -2 )
          v0 = 1;
        v2 = (_QWORD *)gWowHead;
LABEL_14:
        ;
      }
      while ( v2 );
    }
  }
  result = v0;
  WOWTaskIdNext = v0 + 1;
  return result;
}

```

## disassembly

```asm
0x18000b750  mov     edx, cs:WOWTaskIdNext
0x18000b756  mov     r10d, 0FFFFFFFEh
0x18000b75c  mov     r9d, 1
0x18000b762  cmp     edx, r10d
0x18000b765  jnz     short loc_18000B775
0x18000b767  mov     eax, r9d
0x18000b76a  mov     edx, r9d
0x18000b76d  mov     cs:dword_180013678, eax
0x18000b773  jmp     short loc_18000B77B
0x18000b775  mov     eax, cs:dword_180013678
0x18000b77b  test    eax, eax
0x18000b77d  jz      short loc_18000B7BA
0x18000b77f  mov     rax, cs:gWowHead
0x18000b786  mov     rcx, rax
0x18000b789  test    rax, rax
0x18000b78c  jz      short loc_18000B7BA
0x18000b78e  mov     r8, [rcx+38h]
0x18000b792  test    r8, r8
0x18000b795  jz      short loc_18000B7B2
0x18000b797  cmp     [r8], edx
0x18000b79a  jz      short loc_18000B7A2
0x18000b79c  mov     r8, [r8+20h]
0x18000b7a0  jmp     short loc_18000B792
0x18000b7a2  add     edx, r9d
0x18000b7a5  cmp     edx, r10d
0x18000b7a8  jnz     short loc_18000B7AD
0x18000b7aa  mov     edx, r9d
0x18000b7ad  mov     rcx, rax
0x18000b7b0  jmp     short loc_18000B7B5
0x18000b7b2  mov     rcx, [rcx]
0x18000b7b5  test    rcx, rcx
0x18000b7b8  jnz     short loc_18000B78E
0x18000b7ba  lea     ecx, [rdx+1]
0x18000b7bd  mov     eax, edx
0x18000b7bf  mov     cs:WOWTaskIdNext, ecx
0x18000b7c5  retn
```
