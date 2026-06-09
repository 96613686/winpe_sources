# ETWWrite

- ea: `0x180012a08`
- end: `0x180012a63`
- name: `ETWWrite`
- size: `91`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x180012114`
- `0x180012818`
- `0x180012e50`
- `0x180013704`
- `0x18001385c`
- `0x180013944`
- `0x180013a2c`
- `0x180013fa0`
- `0x180014f1c`
- `0x1800150c8`
- `0x180025294`
- `0x1800279b0`
- `0x180028c80`
- `0x18002c560`
- `0x18002df70`
- `0x18002eb20`

## callees

- `0x180012a08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012a2b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012a2b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012a4e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012a4e`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180012a42`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180012a42`

## pseudocode

```c
__int64 __fastcall ETWWrite(__int64 a1, const EVENT_DESCRIPTOR *a2, ULONG a3, struct _EVENT_DATA_DESCRIPTOR *a4)
{
  char *v4; // rsi
  ULONG v8; // ebx

  v4 = (char *)g_petwPro;
  v8 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_petwPro + 16));
  if ( !*(_DWORD *)v4 )
    v8 = EventWrite(*((_QWORD *)v4 + 1), a2, a3, a4);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 16));
  return v8;
}

```

## disassembly

```asm
0x180012a08  push    rbx
0x180012a0a  push    rbp
0x180012a0b  push    rsi
0x180012a0c  push    rdi
0x180012a0d  push    r14
0x180012a0f  push    r15
0x180012a11  sub     rsp, 28h
0x180012a15  mov     rsi, cs:g_petwPro
0x180012a1c  mov     rbp, r9
0x180012a1f  mov     r14d, r8d
0x180012a22  mov     r15, rdx
0x180012a25  xor     ebx, ebx
0x180012a27  lea     rcx, [rsi+10h]; lpCriticalSection
0x180012a2b  call    cs:__imp_EnterCriticalSection
0x180012a31  cmp     [rsi], ebx
0x180012a33  jnz     short loc_180012A4A
0x180012a35  mov     rcx, [rsi+8]; RegHandle
0x180012a39  mov     r9, rbp; UserData
0x180012a3c  mov     r8d, r14d; UserDataCount
0x180012a3f  mov     rdx, r15; EventDescriptor
0x180012a42  call    cs:__imp_EventWrite
0x180012a48  mov     ebx, eax
0x180012a4a  lea     rcx, [rsi+10h]; lpCriticalSection
0x180012a4e  call    cs:__imp_LeaveCriticalSection
0x180012a54  mov     eax, ebx
0x180012a56  add     rsp, 28h
0x180012a5a  pop     r15
0x180012a5c  pop     r14
0x180012a5e  pop     rdi
0x180012a5f  pop     rsi
0x180012a60  pop     rbp
0x180012a61  pop     rbx
0x180012a62  retn
```
