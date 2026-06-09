# ETWCrimson4CPK_Write

- ea: `0x1800336dc`
- end: `0x18003374b`
- name: `ETWCrimson4CPK_Write`
- size: `111`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d580`
- `0x180011860`
- `0x180016f00`

## callees

- `0x1800336dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003372f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003372f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033700`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033700`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18003371d`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18003371d`

## pseudocode

```c
__int64 __fastcall ETWCrimson4CPK_Write(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        ULONG a3,
        struct _EVENT_DATA_DESCRIPTOR *a4)
{
  ULONG v4; // esi

  v4 = 0;
  if ( a1 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
    if ( !*(_DWORD *)a1 )
      v4 = EventWrite(*(_QWORD *)(a1 + 8), a2, a3, a4);
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  }
  return v4;
}

```

## disassembly

```asm
0x1800336dc  push    rbx
0x1800336de  push    rbp
0x1800336df  push    rsi
0x1800336e0  push    rdi
0x1800336e1  push    r14
0x1800336e3  push    r15
0x1800336e5  sub     rsp, 28h
0x1800336e9  xor     esi, esi
0x1800336eb  mov     rbp, r9
0x1800336ee  mov     r14d, r8d
0x1800336f1  mov     r15, rdx
0x1800336f4  mov     rbx, rcx
0x1800336f7  test    rcx, rcx
0x1800336fa  jz      short loc_18003373B
0x1800336fc  add     rcx, 10h; lpCriticalSection
0x180033700  call    cs:__imp_EnterCriticalSection
0x180033707  nop     dword ptr [rax+rax+00h]
0x18003370c  cmp     [rbx], esi
0x18003370e  jnz     short loc_18003372B
0x180033710  mov     rcx, [rbx+8]; RegHandle
0x180033714  mov     r9, rbp; UserData
0x180033717  mov     r8d, r14d; UserDataCount
0x18003371a  mov     rdx, r15; EventDescriptor
0x18003371d  call    cs:__imp_EventWrite
0x180033724  nop     dword ptr [rax+rax+00h]
0x180033729  mov     esi, eax
0x18003372b  lea     rcx, [rbx+10h]; lpCriticalSection
0x18003372f  call    cs:__imp_LeaveCriticalSection
0x180033736  nop     dword ptr [rax+rax+00h]
0x18003373b  mov     eax, esi
0x18003373d  add     rsp, 28h
0x180033741  pop     r15
0x180033743  pop     r14
0x180033745  pop     rdi
0x180033746  pop     rsi
0x180033747  pop     rbp
0x180033748  pop     rbx
0x180033749  retn
```
