# __Init_thread_header

- ea: `0x419616`
- end: `0x419668`
- name: `__Init_thread_header`
- size: `82`
- prototype: `void __cdecl(_DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x40132b`

## callees

- `0x419616`
- `0x41969e`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x41965e`
- `KERNEL32!LeaveCriticalSection` at `0x41965e`
- `KERNEL32!EnterCriticalSection` at `0x419621`
- `KERNEL32!EnterCriticalSection` at `0x419621`

## pseudocode

```c
void __cdecl _Init_thread_header(_DWORD *a1)
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
    _Init_thread_wait(0x64u);
  }
  *(_DWORD *)(*((_DWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + TlsIndex) + 4) = dword_426880;
LABEL_7:
  LeaveCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x419616  push    ebp
0x419617  mov     ebp, esp
0x419619  push    esi
0x41961a  push    edi
0x41961b  mov     edi, offset CriticalSection
0x419620  push    edi; lpCriticalSection
0x419621  call    ds:EnterCriticalSection
0x419627  mov     esi, [ebp+arg_0]
0x41962a  cmp     dword ptr [esi], 0
0x41962d  jnz     short loc_41963E
0x41962f  or      dword ptr [esi], 0FFFFFFFFh
0x419632  jmp     short loc_41965D
0x419634  push    64h ; 'd'; dwMilliseconds
0x419636  call    __Init_thread_wait
0x41963b  pop     ecx
0x41963c  jmp     short loc_41962A
0x41963e  cmp     dword ptr [esi], 0FFFFFFFFh
0x419641  jz      short loc_419634
0x419643  mov     eax, large fs:2Ch
0x419649  mov     ecx, TlsIndex
0x41964f  mov     ecx, [eax+ecx*4]
0x419652  mov     eax, dword_426880
0x419657  mov     [ecx+4], eax
0x41965d  push    edi; lpCriticalSection
0x41965e  call    ds:LeaveCriticalSection
0x419664  pop     edi
0x419665  pop     esi
0x419666  pop     ebp
0x419667  retn
```
