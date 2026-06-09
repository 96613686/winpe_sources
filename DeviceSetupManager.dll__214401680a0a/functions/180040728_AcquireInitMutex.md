# _AcquireInitMutex

- ea: `0x180040728`
- end: `0x1800407d2`
- name: `_AcquireInitMutex`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18004088c`
- `0x180040944`

## callees

- `0x180040728`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180040763`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180040763`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18004079b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18004079b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800407aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800407aa`

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
  if ( !_InterlockedCompareExchange64(&qword_18005A368, a1, 0) )
    return 1;
  result = (__int64)CreateEventW(0, 0, 0, 0);
  *(_QWORD *)a1 = result;
  if ( result )
  {
    do
    {
      v3 = qword_18005A368;
      *(_QWORD *)(a1 + 8) = qword_18005A368;
    }
    while ( v3 != _InterlockedCompareExchange64(&qword_18005A368, a1, v3) );
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
0x180040728  mov     [rsp+arg_0], rbx
0x18004072d  push    rdi
0x18004072e  sub     rsp, 20h
0x180040732  mov     rbx, rcx
0x180040735  mov     qword ptr [rcx+10h], 0
0x18004073d  mov     qword ptr [rcx+8], 0
0x180040745  xor     eax, eax
0x180040747  mov     qword ptr [rcx], 0
0x18004074e  lock cmpxchg cs:qword_18005A368, rbx
0x180040757  jz      short loc_1800407C2
0x180040759  xor     r9d, r9d; lpName
0x18004075c  xor     r8d, r8d; bInitialState
0x18004075f  xor     edx, edx; bManualReset
0x180040761  xor     ecx, ecx; lpEventAttributes
0x180040763  call    cs:__imp_CreateEventW
0x180040769  mov     [rbx], rax
0x18004076c  test    rax, rax
0x18004076f  jz      short loc_1800407C0
0x180040771  mov     rcx, cs:qword_18005A368
0x180040778  mov     [rbx+8], rcx
0x18004077c  mov     rax, rcx
0x18004077f  lock cmpxchg cs:qword_18005A368, rbx
0x180040788  cmp     rcx, rax
0x18004078b  jnz     short loc_180040771
0x18004078d  test    rcx, rcx
0x180040790  jz      short loc_1800407A5
0x180040792  mov     rcx, [rbx]; hHandle
0x180040795  xor     r8d, r8d; bAlertable
0x180040798  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18004079b  call    cs:__imp_WaitForSingleObjectEx
0x1800407a1  mov     edi, eax
0x1800407a3  jmp     short loc_1800407A7
0x1800407a5  xor     edi, edi
0x1800407a7  mov     rcx, [rbx]; hObject
0x1800407aa  call    cs:__imp_CloseHandle
0x1800407b0  xor     eax, eax
0x1800407b2  mov     qword ptr [rbx], 0
0x1800407b9  test    edi, edi
0x1800407bb  setz    al
0x1800407be  jmp     short loc_1800407C7
0x1800407c0  jmp     short loc_1800407C7
0x1800407c2  mov     eax, 1
0x1800407c7  mov     rbx, [rsp+28h+arg_0]
0x1800407cc  add     rsp, 20h
0x1800407d0  pop     rdi
0x1800407d1  retn
```
