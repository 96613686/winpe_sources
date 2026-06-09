# DrvDisableDriver

- ea: `0x1800040d0`
- end: `0x180004130`
- name: `DrvDisableDriver`
- size: `96`
- prototype: `void __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800040d0`
- `0x180020a4c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180004124`

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
      NTFUnloadFile(*((_DWORD **)&gCachedNtfFiles + i));
      *((_QWORD *)&gCachedNtfFiles + i) = 0;
    }
  }
  DeleteCriticalSection(&gPSCritSection);
}

```

## disassembly

```asm
0x1800040d0  mov     [rsp+arg_0], rbx
0x1800040d5  push    rsi
0x1800040d6  sub     rsp, 20h
0x1800040da  xor     ebx, ebx
0x1800040dc  lea     rsi, gCachedNtfFiles
0x1800040e3  mov     rax, [rsi+rbx*8]
0x1800040e7  test    rax, rax
0x1800040ea  jz      short loc_18000410A
0x1800040ec  cmp     dword ptr [rax+1Ch], 0
0x1800040f0  jle     short loc_1800040F9
0x1800040f2  mov     dword ptr [rax+1Ch], 0
0x1800040f9  mov     rcx, [rsi+rbx*8]; hMem
0x1800040fd  call    NTFUnloadFile
0x180004102  mov     qword ptr [rsi+rbx*8], 0
0x18000410a  inc     rbx
0x18000410d  cmp     rbx, 4
0x180004111  jnz     short loc_1800040DC
0x180004113  lea     rcx, gPSCritSection
0x18000411a  mov     rbx, [rsp+28h+arg_0]
0x18000411f  add     rsp, 20h
0x180004123  pop     rsi
0x180004124  jmp     cs:__imp_DeleteCriticalSection
```
