# StartAddress

- ea: `0x404350`
- end: `0x4043d1`
- name: `StartAddress`
- size: `129`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x404350`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x4043b8`
- `KERNEL32!TerminateProcess` at `0x4043b8`
- `KERNEL32!GetCurrentProcess` at `0x4043b0`
- `KERNEL32!GetCurrentProcess` at `0x4043b0`
- `KERNEL32!WaitForSingleObject` at `0x404379`
- `KERNEL32!WaitForSingleObject` at `0x40439d`
- `KERNEL32!WaitForSingleObject` at `0x404379`
- `KERNEL32!WaitForSingleObject` at `0x40439d`
- `KERNEL32!ReleaseMutex` at `0x4043c3`
- `KERNEL32!ReleaseMutex` at `0x4043c3`
- `KERNEL32!SetEvent` at `0x404393`
- `KERNEL32!SetEvent` at `0x404393`

## pseudocode

```c
DWORD __stdcall StartAddress(LPVOID lpThreadParameter)
{
  DWORD v1; // ecx
  DWORD v2; // edi
  DWORD v3; // eax
  UINT v4; // esi
  HANDLE CurrentProcess; // eax

  v1 = *(_DWORD *)lpThreadParameter;
  if ( *((_BYTE *)lpThreadParameter + 20) && v1 > *((_DWORD *)lpThreadParameter + 1) )
    v1 = *((_DWORD *)lpThreadParameter + 1);
  v2 = (*(_DWORD *)lpThreadParameter - v1) & ((*(_DWORD *)lpThreadParameter < v1) - 1);
  v3 = WaitForSingleObject(*((HANDLE *)lpThreadParameter + 3), v1);
  if ( v3 )
  {
    if ( v3 == 258 )
    {
      if ( !*((_DWORD *)lpThreadParameter + 6)
        || (SetEvent(*((HANDLE *)lpThreadParameter + 6)), WaitForSingleObject(*((HANDLE *)lpThreadParameter + 3), v2)) )
      {
        if ( *((_BYTE *)lpThreadParameter + 21) )
        {
          v4 = *((_DWORD *)lpThreadParameter + 2);
          CurrentProcess = GetCurrentProcess();
          TerminateProcess(CurrentProcess, v4);
        }
      }
    }
  }
  else
  {
    ReleaseMutex(*((HANDLE *)lpThreadParameter + 3));
  }
  return 0;
}

```

## disassembly

```asm
0x404350  push    ebp
0x404351  mov     ebp, esp
0x404353  push    esi
0x404354  mov     esi, [ebp+lpThreadParameter]
0x404357  push    edi
0x404358  cmp     byte ptr [esi+14h], 0
0x40435c  mov     ecx, [esi]
0x40435e  jz      short loc_404369
0x404360  mov     eax, [esi+4]
0x404363  cmp     ecx, eax
0x404365  jbe     short loc_404369
0x404367  mov     ecx, eax
0x404369  mov     eax, [esi]
0x40436b  sub     eax, ecx
0x40436d  cmp     [esi], eax
0x40436f  push    ecx; dwMilliseconds
0x404370  push    dword ptr [esi+0Ch]; hHandle
0x404373  sbb     edi, edi
0x404375  not     edi
0x404377  and     edi, eax
0x404379  call    ds:WaitForSingleObject
0x40437f  test    eax, eax
0x404381  jz      short loc_4043C0
0x404383  cmp     eax, 102h
0x404388  jnz     short loc_4043C9
0x40438a  cmp     dword ptr [esi+18h], 0
0x40438e  jz      short loc_4043A7
0x404390  push    dword ptr [esi+18h]; hEvent
0x404393  call    ds:SetEvent
0x404399  push    edi; dwMilliseconds
0x40439a  push    dword ptr [esi+0Ch]; hHandle
0x40439d  call    ds:WaitForSingleObject
0x4043a3  test    eax, eax
0x4043a5  jz      short loc_4043C9
0x4043a7  cmp     byte ptr [esi+15h], 0
0x4043ab  jz      short loc_4043C9
0x4043ad  mov     esi, [esi+8]
0x4043b0  call    ds:GetCurrentProcess
0x4043b6  push    esi; uExitCode
0x4043b7  push    eax; hProcess
0x4043b8  call    ds:TerminateProcess
0x4043be  jmp     short loc_4043C9
0x4043c0  push    dword ptr [esi+0Ch]; hMutex
0x4043c3  call    ds:ReleaseMutex
0x4043c9  pop     edi
0x4043ca  xor     eax, eax
0x4043cc  pop     esi
0x4043cd  pop     ebp
0x4043ce  retn    4
```
