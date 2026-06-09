# DrvDisableDriver

- ea: `0x180004040`
- end: `0x18000409b`
- name: `DrvDisableDriver`
- size: `91`
- prototype: `void __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180004040`
- `0x18001fe2c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180004094`

## pseudocode

```c
void __stdcall DrvDisableDriver()
{
  __int64 i; // rbx
  __int64 v1; // rax

  for ( i = 0; i != 4; ++i )
  {
    v1 = *((_QWORD *)&gCachedNtfFiles + i);
    if ( v1 )
    {
      if ( *(int *)(v1 + 28) > 0 )
        *(_DWORD *)(v1 + 28) = 0;
      NTFUnloadFile(*((HLOCAL *)&gCachedNtfFiles + i));
      *((_QWORD *)&gCachedNtfFiles + i) = 0;
    }
  }
  DeleteCriticalSection(&gPSCritSection);
}

```

## disassembly

```asm
0x180004040  mov     [rsp+arg_0], rbx
0x180004045  push    rsi
0x180004046  sub     rsp, 20h
0x18000404a  xor     ebx, ebx
0x18000404c  lea     rsi, gCachedNtfFiles
0x180004053  mov     rax, [rsi+rbx*8]
0x180004057  test    rax, rax
0x18000405a  jz      short loc_18000407A
0x18000405c  cmp     dword ptr [rax+1Ch], 0
0x180004060  jle     short loc_180004069
0x180004062  mov     dword ptr [rax+1Ch], 0
0x180004069  mov     rcx, [rsi+rbx*8]; hMem
0x18000406d  call    NTFUnloadFile
0x180004072  mov     qword ptr [rsi+rbx*8], 0
0x18000407a  inc     rbx
0x18000407d  cmp     rbx, 4
0x180004081  jnz     short loc_18000404C
0x180004083  lea     rcx, gPSCritSection
0x18000408a  mov     rbx, [rsp+28h+arg_0]
0x18000408f  add     rsp, 20h
0x180004093  pop     rsi
0x180004094  jmp     cs:__imp_DeleteCriticalSection
```
