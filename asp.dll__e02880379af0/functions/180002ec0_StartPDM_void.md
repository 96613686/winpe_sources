# StartPDM(void)

- ea: `0x180002ec0`
- end: `0x180002f42`
- name: `?StartPDM@@YAJXZ`
- size: `130`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002e40`

## callees

- `0x180002ec0`

## import_xrefs

- `msvcrt!_beginthread` at `0x180002ef8`
- `msvcrt!_beginthread` at `0x180002ef8`
- `KERNEL32!CloseHandle` at `0x180002f16`
- `KERNEL32!CloseHandle` at `0x180002f16`
- `KERNEL32!CreateEventA` at `0x180002ed8`
- `KERNEL32!CreateEventA` at `0x180002ed8`
- `KERNEL32!Sleep` at `0x180002f36`
- `KERNEL32!Sleep` at `0x180002f36`

## pseudocode

```c
__int64 StartPDM(void)
{
  int ArgList; // [rsp+30h] [rbp+8h] BYREF

  ArgList = 0;
  hObject = CreateEventA(0, 1, 0, 0);
  if ( !hObject )
    return 2147500037LL;
  _beginthread(Debugger, 0, &ArgList);
  while ( !ArgList )
    Sleep(0x64u);
  if ( !g_pPDM )
  {
    CloseHandle(hObject);
    hObject = 0;
    return 2147500037LL;
  }
  return 0;
}

```

## disassembly

```asm
0x180002ec0  sub     rsp, 28h
0x180002ec4  xor     r9d, r9d; lpName
0x180002ec7  mov     [rsp+28h+ArgList], 0
0x180002ecf  xor     r8d, r8d; bInitialState
0x180002ed2  xor     ecx, ecx; lpEventAttributes
0x180002ed4  lea     edx, [r9+1]; bManualReset
0x180002ed8  call    cs:__imp_CreateEventA
0x180002ede  mov     cs:hObject, rax
0x180002ee5  test    rax, rax
0x180002ee8  jz      short loc_180002F27
0x180002eea  lea     r8, [rsp+28h+ArgList]; ArgList
0x180002eef  xor     edx, edx; StackSize
0x180002ef1  lea     rcx, ?Debugger@@YAXPEAX@Z; StartAddress
0x180002ef8  call    cs:__imp__beginthread
0x180002efe  cmp     [rsp+28h+ArgList], 0
0x180002f03  jz      short loc_180002F31
0x180002f05  cmp     cs:?g_pPDM@@3PEAUIProcessDebugManager64@@EA, 0; IProcessDebugManager64 * g_pPDM
0x180002f0d  jnz     short loc_180002F3E
0x180002f0f  mov     rcx, cs:hObject; hObject
0x180002f16  call    cs:__imp_CloseHandle
0x180002f1c  mov     cs:hObject, 0
0x180002f27  mov     eax, 80004005h
0x180002f2c  add     rsp, 28h
0x180002f30  retn
0x180002f31  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180002f36  call    cs:__imp_Sleep
0x180002f3c  jmp     short loc_180002EFE
0x180002f3e  xor     eax, eax
0x180002f40  jmp     short loc_180002F2C
```
