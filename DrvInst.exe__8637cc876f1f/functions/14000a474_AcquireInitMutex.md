# _AcquireInitMutex

- ea: `0x14000a474`
- end: `0x14000a51e`
- name: `_AcquireInitMutex`
- size: `170`
- prototype: `__int64 __fastcall(signed __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000a570`
- `0x14000a6bc`
- `0x14000a774`

## callees

- `0x14000a474`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000a4af`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000a4af`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14000a4e7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14000a4e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a4f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a4f6`

## pseudocode

```c
__int64 __fastcall AcquireInitMutex(signed __int64 a1)
{
  __int64 result; // rax
  signed __int64 v3; // rcx
  DWORD v4; // edi

  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)a1 = 0;
  if ( !_InterlockedCompareExchange64(&qword_140063EA0, a1, 0) )
    return 1;
  result = (__int64)CreateEventW(0, 0, 0, 0);
  *(_QWORD *)a1 = result;
  if ( result )
  {
    do
    {
      v3 = qword_140063EA0;
      *(_QWORD *)(a1 + 8) = qword_140063EA0;
    }
    while ( v3 != _InterlockedCompareExchange64(&qword_140063EA0, a1, v3) );
    if ( v3 )
      v4 = WaitForSingleObjectEx(*(HANDLE *)a1, 0xFFFFFFFF, 0);
    else
      v4 = 0;
    CloseHandle(*(HANDLE *)a1);
    *(_QWORD *)a1 = 0;
    return v4 == 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000a474  mov     [rsp+arg_0], rbx
0x14000a479  push    rdi
0x14000a47a  sub     rsp, 20h
0x14000a47e  mov     rbx, rcx
0x14000a481  mov     qword ptr [rcx+10h], 0
0x14000a489  mov     qword ptr [rcx+8], 0
0x14000a491  xor     eax, eax
0x14000a493  mov     qword ptr [rcx], 0
0x14000a49a  lock cmpxchg cs:qword_140063EA0, rbx
0x14000a4a3  jz      short loc_14000A50E
0x14000a4a5  xor     r9d, r9d; lpName
0x14000a4a8  xor     r8d, r8d; bInitialState
0x14000a4ab  xor     edx, edx; bManualReset
0x14000a4ad  xor     ecx, ecx; lpEventAttributes
0x14000a4af  call    cs:__imp_CreateEventW
0x14000a4b5  mov     [rbx], rax
0x14000a4b8  test    rax, rax
0x14000a4bb  jz      short loc_14000A50C
0x14000a4bd  mov     rcx, cs:qword_140063EA0
0x14000a4c4  mov     [rbx+8], rcx
0x14000a4c8  mov     rax, rcx
0x14000a4cb  lock cmpxchg cs:qword_140063EA0, rbx
0x14000a4d4  cmp     rcx, rax
0x14000a4d7  jnz     short loc_14000A4BD
0x14000a4d9  test    rcx, rcx
0x14000a4dc  jz      short loc_14000A4F1
0x14000a4de  mov     rcx, [rbx]; hHandle
0x14000a4e1  xor     r8d, r8d; bAlertable
0x14000a4e4  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000a4e7  call    cs:__imp_WaitForSingleObjectEx
0x14000a4ed  mov     edi, eax
0x14000a4ef  jmp     short loc_14000A4F3
0x14000a4f1  xor     edi, edi
0x14000a4f3  mov     rcx, [rbx]; hObject
0x14000a4f6  call    cs:__imp_CloseHandle
0x14000a4fc  xor     eax, eax
0x14000a4fe  mov     qword ptr [rbx], 0
0x14000a505  test    edi, edi
0x14000a507  setz    al
0x14000a50a  jmp     short loc_14000A513
0x14000a50c  jmp     short loc_14000A513
0x14000a50e  mov     eax, 1
0x14000a513  mov     rbx, [rsp+28h+arg_0]
0x14000a518  add     rsp, 20h
0x14000a51c  pop     rdi
0x14000a51d  retn
```
