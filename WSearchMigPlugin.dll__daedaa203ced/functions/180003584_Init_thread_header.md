# _Init_thread_header

- ea: `0x180003584`
- end: `0x1800035e9`
- name: `_Init_thread_header`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800156a4`

## callees

- `0x180003584`
- `0x180003638`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003594`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003594`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800035e2`

## pseudocode

```c
void __fastcall Init_thread_header(_DWORD *a1)
{
  EnterCriticalSection(&stru_180025C90);
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
  LeaveCriticalSection(&stru_180025C90);
}

```

## disassembly

```asm
0x180003584  push    rbx
0x180003586  sub     rsp, 20h
0x18000358a  mov     rbx, rcx
0x18000358d  lea     rcx, stru_180025C90; lpCriticalSection
0x180003594  call    cs:__imp_EnterCriticalSection
0x18000359a  cmp     dword ptr [rbx], 0
0x18000359d  jnz     short loc_1800035AE
0x18000359f  mov     dword ptr [rbx], 0FFFFFFFFh
0x1800035a5  jmp     short loc_1800035D6
0x1800035a7  call    _Init_thread_wait_v2
0x1800035ac  jmp     short loc_18000359A
0x1800035ae  cmp     dword ptr [rbx], 0FFFFFFFFh
0x1800035b1  jz      short loc_1800035A7
0x1800035b3  mov     rax, gs:58h
0x1800035bc  mov     ecx, cs:_tls_index
0x1800035c2  mov     r8d, 4
0x1800035c8  mov     rdx, [rax+rcx*8]
0x1800035cc  mov     eax, cs:_Init_global_epoch
0x1800035d2  mov     [r8+rdx], eax
0x1800035d6  lea     rcx, stru_180025C90
0x1800035dd  add     rsp, 20h
0x1800035e1  pop     rbx
0x1800035e2  jmp     cs:__imp_LeaveCriticalSection
```
