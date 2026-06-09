# _Init_thread_header

- ea: `0x180003748`
- end: `0x1800037af`
- name: `_Init_thread_header`
- size: `103`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800014a0`

## callees

- `0x180003748`
- `0x1800037f4`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800037a8`
- `KERNEL32!EnterCriticalSection` at `0x180003758`
- `KERNEL32!EnterCriticalSection` at `0x180003758`

## pseudocode

```c
void __fastcall Init_thread_header(_DWORD *a1)
{
  EnterCriticalSection(&CriticalSection);
  while ( 1 )
  {
    if ( !*a1 )
    {
      *a1 = -1;
      goto LABEL_7;
    }
    if ( *a1 != -1 )
      break;
    Init_thread_wait(0x64u);
  }
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL) = Init_global_epoch;
LABEL_7:
  LeaveCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x180003748  push    rbx
0x18000374a  sub     rsp, 20h
0x18000374e  mov     rbx, rcx
0x180003751  lea     rcx, CriticalSection; lpCriticalSection
0x180003758  call    cs:__imp_EnterCriticalSection
0x18000375e  cmp     dword ptr [rbx], 0
0x180003761  jnz     short loc_180003774
0x180003763  or      dword ptr [rbx], 0FFFFFFFFh
0x180003766  jmp     short loc_18000379C
0x180003768  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18000376d  call    _Init_thread_wait
0x180003772  jmp     short loc_18000375E
0x180003774  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180003777  jz      short loc_180003768
0x180003779  mov     rax, gs:58h
0x180003782  mov     ecx, cs:_tls_index
0x180003788  mov     r8d, 4
0x18000378e  mov     rdx, [rax+rcx*8]
0x180003792  mov     eax, cs:_Init_global_epoch
0x180003798  mov     [r8+rdx], eax
0x18000379c  lea     rcx, CriticalSection
0x1800037a3  add     rsp, 20h
0x1800037a7  pop     rbx
0x1800037a8  jmp     cs:__imp_LeaveCriticalSection
```
