# DetourUpdateThread(x)

- ea: `0x40e280`
- end: `0x40e301`
- name: `_DetourUpdateThread@4`
- size: `129`
- prototype: `DWORD __stdcall(HANDLE hThread)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callers

- `0x409e9d`
- `0x409f13`

## callees

- `0x4026e7`
- `0x40e280`
- `0x40eb05`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x40e28a`
- `KERNEL32!GetCurrentThread` at `0x40e28a`
- `KERNEL32!SuspendThread` at `0x40e2b5`
- `KERNEL32!SuspendThread` at `0x40e2b5`
- `KERNEL32!GetLastError` at `0x40e2c0`
- `KERNEL32!GetLastError` at `0x40e2c0`

## pseudocode

```c
DWORD __stdcall DetourUpdateThread(HANDLE hThread)
{
  DWORD result; // eax
  _DWORD *v2; // esi
  DWORD LastError; // edi
  void *v4; // eax

  result = dword_40F480;
  if ( !dword_40F480 )
  {
    if ( hThread == GetCurrentThread() )
      return 0;
    v2 = operator new(8u);
    if ( !v2 )
    {
      LastError = 8;
LABEL_8:
      dword_40F480 = LastError;
      result = LastError;
      dword_40F484 = 0;
      return result;
    }
    if ( SuspendThread(hThread) == -1 )
    {
      LastError = GetLastError();
      operator delete(v2);
      goto LABEL_8;
    }
    v4 = dword_40F488;
    v2[1] = hThread;
    *v2 = v4;
    result = 0;
    dword_40F488 = v2;
  }
  return result;
}

```

## disassembly

```asm
0x40e280  mov     eax, dword_40F480
0x40e285  test    eax, eax
0x40e287  jnz     short locret_40E2FE
0x40e289  push    edi
0x40e28a  call    ds:__imp__GetCurrentThread@0; GetCurrentThread()
0x40e290  mov     edi, [esp+4+hThread]
0x40e294  cmp     edi, eax
0x40e296  jnz     short loc_40E29E
0x40e298  xor     eax, eax
0x40e29a  pop     edi
0x40e29b  retn    4
0x40e29e  push    esi
0x40e29f  push    8; dwBytes
0x40e2a1  call    ??2@YAPAXI@Z; operator new(uint)
0x40e2a6  mov     esi, eax
0x40e2a8  add     esp, 4
0x40e2ab  test    esi, esi
0x40e2ad  jnz     short loc_40E2B4
0x40e2af  lea     edi, [eax+8]
0x40e2b2  jmp     short loc_40E2D3
0x40e2b4  push    edi; hThread
0x40e2b5  call    ds:__imp__SuspendThread@4; SuspendThread(x)
0x40e2bb  cmp     eax, 0FFFFFFFFh
0x40e2be  jnz     short loc_40E2EA
0x40e2c0  call    ds:__imp__GetLastError@0; GetLastError()
0x40e2c6  mov     edi, eax
0x40e2c8  push    8; unsigned int
0x40e2ca  push    esi; lpMem
0x40e2cb  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x40e2d0  add     esp, 8
0x40e2d3  pop     esi
0x40e2d4  mov     dword_40F480, edi
0x40e2da  mov     eax, edi
0x40e2dc  mov     dword_40F484, 0
0x40e2e6  pop     edi
0x40e2e7  retn    4
0x40e2ea  mov     eax, dword_40F488
0x40e2ef  mov     [esi+4], edi
0x40e2f2  mov     [esi], eax
0x40e2f4  xor     eax, eax
0x40e2f6  mov     dword_40F488, esi
0x40e2fc  pop     esi
0x40e2fd  pop     edi
0x40e2fe  retn    4
```
