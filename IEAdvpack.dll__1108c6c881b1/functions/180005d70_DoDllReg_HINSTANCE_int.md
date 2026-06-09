# DoDllReg(HINSTANCE__ *,int)

- ea: `0x180005d70`
- end: `0x180005dae`
- name: `?DoDllReg@@YAHPEAUHINSTANCE__@@H@Z`
- size: `62`
- prototype: `__int64 __fastcall(HINSTANCE, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800079c0`

## callees

- `0x180005d70`
- `0x18001c010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180005d8e`
- `KERNEL32!GetProcAddress` at `0x180005d8e`

## string_xrefs

- `0x180005d81`: `DllRegisterServer`
- `0x180005d78`: `DllUnregisterServer`

## pseudocode

```c
__int64 __fastcall DoDllReg(HINSTANCE a1, int a2)
{
  unsigned int v3; // ebx
  const CHAR *v4; // rdx
  int (*ProcAddress)(void); // rax

  v3 = 0;
  v4 = "DllRegisterServer";
  if ( !a2 )
    v4 = "DllUnregisterServer";
  ProcAddress = (int (*)(void))GetProcAddress(a1, v4);
  if ( ProcAddress && ProcAddress() >= 0 )
    return 1;
  return v3;
}

```

## disassembly

```asm
0x180005d70  push    rbx
0x180005d72  sub     rsp, 20h
0x180005d76  mov     eax, edx
0x180005d78  lea     r8, aDllunregisters_0; "DllUnregisterServer"
0x180005d7f  xor     ebx, ebx
0x180005d81  lea     rdx, aDllregisterser_0; "DllRegisterServer"
0x180005d88  test    eax, eax
0x180005d8a  cmovz   rdx, r8; lpProcName
0x180005d8e  call    cs:__imp_GetProcAddress
0x180005d94  test    rax, rax
0x180005d97  jz      short loc_180005DA6
0x180005d99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d9e  test    eax, eax
0x180005da0  lea     ecx, [rbx+1]
0x180005da3  cmovns  ebx, ecx
0x180005da6  mov     eax, ebx
0x180005da8  add     rsp, 20h
0x180005dac  pop     rbx
0x180005dad  retn
```
