# DpspGetSessionFromId

- ea: `0x180006ae8`
- end: `0x180006b6b`
- name: `DpspGetSessionFromId`
- size: `131`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180004de4`
- `0x18000c21c`
- `0x18000c784`
- `0x18000f298`
- `0x180013214`

## callees

- `0x180006ae8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006b3a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006b52`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006b3a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006b52`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006b07`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006b07`

## pseudocode

```c
struct __SESSIONINFO *__fastcall DpspGetSessionFromId(_QWORD *a1)
{
  struct __SESSIONINFO *i; // rbx
  __int64 v3; // rax

  for ( i = g_pSessionHead; i; i = (struct __SESSIONINFO *)*((_QWORD *)i + 23) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)i + 64));
    if ( *(_QWORD *)i == *a1 && *((_QWORD *)i + 1) == a1[1] )
    {
      v3 = *((_QWORD *)i + 22);
      if ( v3 )
      {
        if ( *(_DWORD *)(v3 + 120) != 3 )
        {
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)i + 64));
          return i;
        }
      }
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)i + 64));
  }
  return i;
}

```

## disassembly

```asm
0x180006ae8  mov     [rsp+arg_0], rbx
0x180006aed  mov     [rsp+arg_8], rsi
0x180006af2  push    rdi
0x180006af3  sub     rsp, 20h
0x180006af7  mov     rbx, cs:g_pSessionHead
0x180006afe  mov     rsi, rcx
0x180006b01  jmp     short loc_180006B47
0x180006b03  lea     rcx, [rbx+40h]; lpCriticalSection
0x180006b07  call    cs:__imp_EnterCriticalSection
0x180006b0d  mov     rax, [rbx]
0x180006b10  cmp     rax, [rsi]
0x180006b13  jnz     short loc_180006B31
0x180006b15  mov     rax, [rbx+8]
0x180006b19  cmp     rax, [rsi+8]
0x180006b1d  jnz     short loc_180006B31
0x180006b1f  mov     rax, [rbx+0B0h]
0x180006b26  test    rax, rax
0x180006b29  jz      short loc_180006B31
0x180006b2b  cmp     dword ptr [rax+78h], 3
0x180006b2f  jnz     short loc_180006B4E
0x180006b31  test    rbx, rbx
0x180006b34  jz      short loc_180006B40
0x180006b36  lea     rcx, [rbx+40h]; lpCriticalSection
0x180006b3a  call    cs:__imp_LeaveCriticalSection
0x180006b40  mov     rbx, [rbx+0B8h]
0x180006b47  test    rbx, rbx
0x180006b4a  jnz     short loc_180006B03
0x180006b4c  jmp     short loc_180006B58
0x180006b4e  lea     rcx, [rbx+40h]; lpCriticalSection
0x180006b52  call    cs:__imp_LeaveCriticalSection
0x180006b58  mov     rsi, [rsp+28h+arg_8]
0x180006b5d  mov     rax, rbx
0x180006b60  mov     rbx, [rsp+28h+arg_0]
0x180006b65  add     rsp, 20h
0x180006b69  pop     rdi
0x180006b6a  retn
```
