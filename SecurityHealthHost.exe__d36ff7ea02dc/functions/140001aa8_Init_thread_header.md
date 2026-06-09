# _Init_thread_header

- ea: `0x140001aa8`
- end: `0x140001b0d`
- name: `_Init_thread_header`
- size: `101`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400043d0`

## callees

- `0x140001aa8`
- `0x140001b5c`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x140001b06`
- `KERNEL32!EnterCriticalSection` at `0x140001ab8`
- `KERNEL32!EnterCriticalSection` at `0x140001ab8`

## pseudocode

```c
void __fastcall Init_thread_header(_DWORD *a1)
{
  EnterCriticalSection(&stru_140018C60);
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
  LeaveCriticalSection(&stru_140018C60);
}

```

## disassembly

```asm
0x140001aa8  push    rbx
0x140001aaa  sub     rsp, 20h
0x140001aae  mov     rbx, rcx
0x140001ab1  lea     rcx, stru_140018C60; lpCriticalSection
0x140001ab8  call    cs:__imp_EnterCriticalSection
0x140001abe  cmp     dword ptr [rbx], 0
0x140001ac1  jnz     short loc_140001AD2
0x140001ac3  mov     dword ptr [rbx], 0FFFFFFFFh
0x140001ac9  jmp     short loc_140001AFA
0x140001acb  call    _Init_thread_wait_v2
0x140001ad0  jmp     short loc_140001ABE
0x140001ad2  cmp     dword ptr [rbx], 0FFFFFFFFh
0x140001ad5  jz      short loc_140001ACB
0x140001ad7  mov     rax, gs:58h
0x140001ae0  mov     ecx, cs:_tls_index
0x140001ae6  mov     r8d, 4
0x140001aec  mov     rdx, [rax+rcx*8]
0x140001af0  mov     eax, cs:_Init_global_epoch
0x140001af6  mov     [r8+rdx], eax
0x140001afa  lea     rcx, stru_140018C60
0x140001b01  add     rsp, 20h
0x140001b05  pop     rbx
0x140001b06  jmp     cs:__imp_LeaveCriticalSection
```
