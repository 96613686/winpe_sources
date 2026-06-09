# __Init_thread_header

- ea: `0x40d1b6`
- end: `0x40d208`
- name: `__Init_thread_header`
- size: `82`
- prototype: `void __cdecl(_DWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x4015fb`
- `0x4046bf`

## callees

- `0x40d1b6`
- `0x40d23e`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x40d1c1`
- `KERNEL32!EnterCriticalSection` at `0x40d1c1`
- `KERNEL32!LeaveCriticalSection` at `0x40d1fe`
- `KERNEL32!LeaveCriticalSection` at `0x40d1fe`

## pseudocode

```c
void __cdecl _Init_thread_header(_DWORD *a1)
{
  EnterCriticalSection(&stru_43DCA4);
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
  *(_DWORD *)(*((_DWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + TlsIndex) + 4) = dword_43D000;
LABEL_7:
  LeaveCriticalSection(&stru_43DCA4);
}

```

## disassembly

```asm
0x40d1b6  push    ebp
0x40d1b7  mov     ebp, esp
0x40d1b9  push    esi
0x40d1ba  push    edi
0x40d1bb  mov     edi, offset stru_43DCA4
0x40d1c0  push    edi; lpCriticalSection
0x40d1c1  call    ds:EnterCriticalSection
0x40d1c7  mov     esi, [ebp+arg_0]
0x40d1ca  cmp     dword ptr [esi], 0
0x40d1cd  jnz     short loc_40D1DE
0x40d1cf  or      dword ptr [esi], 0FFFFFFFFh
0x40d1d2  jmp     short loc_40D1FD
0x40d1d4  push    64h ; 'd'; dwMilliseconds
0x40d1d6  call    __Init_thread_wait
0x40d1db  pop     ecx
0x40d1dc  jmp     short loc_40D1CA
0x40d1de  cmp     dword ptr [esi], 0FFFFFFFFh
0x40d1e1  jz      short loc_40D1D4
0x40d1e3  mov     eax, large fs:2Ch
0x40d1e9  mov     ecx, TlsIndex
0x40d1ef  mov     ecx, [eax+ecx*4]
0x40d1f2  mov     eax, dword_43D000
0x40d1f7  mov     [ecx+4], eax
0x40d1fd  push    edi; lpCriticalSection
0x40d1fe  call    ds:LeaveCriticalSection
0x40d204  pop     edi
0x40d205  pop     esi
0x40d206  pop     ebp
0x40d207  retn
```
