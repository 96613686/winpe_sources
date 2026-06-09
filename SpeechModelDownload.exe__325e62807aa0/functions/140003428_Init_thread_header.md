# _Init_thread_header

- ea: `0x140003428`
- end: `0x14000348d`
- name: `_Init_thread_header`
- size: `101`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000985c`

## callees

- `0x140003428`
- `0x1400034dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140003438`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140003438`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140003486`

## pseudocode

```c
void __fastcall Init_thread_header(_DWORD *a1)
{
  EnterCriticalSection(&stru_140030548);
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
  LeaveCriticalSection(&stru_140030548);
}

```

## disassembly

```asm
0x140003428  push    rbx
0x14000342a  sub     rsp, 20h
0x14000342e  mov     rbx, rcx
0x140003431  lea     rcx, stru_140030548; lpCriticalSection
0x140003438  call    cs:__imp_EnterCriticalSection
0x14000343e  cmp     dword ptr [rbx], 0
0x140003441  jnz     short loc_140003452
0x140003443  mov     dword ptr [rbx], 0FFFFFFFFh
0x140003449  jmp     short loc_14000347A
0x14000344b  call    _Init_thread_wait_v2
0x140003450  jmp     short loc_14000343E
0x140003452  cmp     dword ptr [rbx], 0FFFFFFFFh
0x140003455  jz      short loc_14000344B
0x140003457  mov     rax, gs:58h
0x140003460  mov     ecx, cs:_tls_index
0x140003466  mov     r8d, 4
0x14000346c  mov     rdx, [rax+rcx*8]
0x140003470  mov     eax, cs:_Init_global_epoch
0x140003476  mov     [r8+rdx], eax
0x14000347a  lea     rcx, stru_140030548
0x140003481  add     rsp, 20h
0x140003485  pop     rbx
0x140003486  jmp     cs:__imp_LeaveCriticalSection
```
