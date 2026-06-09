# _Init_thread_header

- ea: `0x180004768`
- end: `0x1800047cd`
- name: `_Init_thread_header`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cc18`

## callees

- `0x180004768`
- `0x18000481c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800047c6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004778`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004778`

## pseudocode

```c
void __fastcall Init_thread_header(_DWORD *a1)
{
  EnterCriticalSection(&stru_18004A470);
  while ( 1 )
  {
    if ( !*a1 )
    {
      *a1 = -1;
      goto LABEL_7;
    }
    if ( *a1 != -1 )
      break;
    Init_thread_wait_v2();
  }
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL) = Init_global_epoch;
LABEL_7:
  LeaveCriticalSection(&stru_18004A470);
}

```

## disassembly

```asm
0x180004768  push    rbx
0x18000476a  sub     rsp, 20h
0x18000476e  mov     rbx, rcx
0x180004771  lea     rcx, stru_18004A470; lpCriticalSection
0x180004778  call    cs:__imp_EnterCriticalSection
0x18000477e  cmp     dword ptr [rbx], 0
0x180004781  jnz     short loc_180004792
0x180004783  mov     dword ptr [rbx], 0FFFFFFFFh
0x180004789  jmp     short loc_1800047BA
0x18000478b  call    _Init_thread_wait_v2
0x180004790  jmp     short loc_18000477E
0x180004792  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180004795  jz      short loc_18000478B
0x180004797  mov     rax, gs:58h
0x1800047a0  mov     ecx, cs:_tls_index
0x1800047a6  mov     r8d, 4
0x1800047ac  mov     rdx, [rax+rcx*8]
0x1800047b0  mov     eax, cs:_Init_global_epoch
0x1800047b6  mov     [r8+rdx], eax
0x1800047ba  lea     rcx, stru_18004A470
0x1800047c1  add     rsp, 20h
0x1800047c5  pop     rbx
0x1800047c6  jmp     cs:__imp_LeaveCriticalSection
```
