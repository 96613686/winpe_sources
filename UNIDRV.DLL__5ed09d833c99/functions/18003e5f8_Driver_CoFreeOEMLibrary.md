# Driver_CoFreeOEMLibrary

- ea: `0x18003e5f8`
- end: `0x18003e648`
- name: `Driver_CoFreeOEMLibrary`
- size: `80`
- prototype: `void __fastcall(HMODULE hLibModule, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18003d00c`

## callees

- `0x18003e5f8`
- `0x180077010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18003e630`
- `KERNEL32!FreeLibrary` at `0x18003e630`
- `KERNEL32!GetProcAddress` at `0x18003e613`
- `KERNEL32!GetProcAddress` at `0x18003e613`

## string_xrefs

- `0x18003e60c`: `DllCanUnloadNow`

## pseudocode

```c
void __fastcall Driver_CoFreeOEMLibrary(HMODULE hLibModule, int a2)
{
  void (*ProcAddress)(void); // rax

  if ( hLibModule )
  {
    ProcAddress = (void (*)(void))GetProcAddress(hLibModule, "DllCanUnloadNow");
    if ( ProcAddress )
    {
      if ( a2 )
        ProcAddress();
      FreeLibrary(hLibModule);
    }
  }
}

```

## disassembly

```asm
0x18003e5f8  test    rcx, rcx
0x18003e5fb  jz      short locret_18003E646
0x18003e5fd  mov     [rsp+arg_0], rbx
0x18003e602  push    rdi
0x18003e603  sub     rsp, 20h
0x18003e607  mov     edi, edx
0x18003e609  mov     rbx, rcx
0x18003e60c  lea     rdx, aDllcanunloadno; "DllCanUnloadNow"
0x18003e613  call    cs:__imp_GetProcAddress
0x18003e61a  nop     dword ptr [rax+rax+00h]
0x18003e61f  test    rax, rax
0x18003e622  jz      short loc_18003E63C
0x18003e624  test    edi, edi
0x18003e626  jz      short loc_18003E62D
0x18003e628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e62d  mov     rcx, rbx; hLibModule
0x18003e630  call    cs:__imp_FreeLibrary
0x18003e637  nop     dword ptr [rax+rax+00h]
0x18003e63c  mov     rbx, [rsp+28h+arg_0]
0x18003e641  add     rsp, 20h
0x18003e645  pop     rdi
0x18003e646  retn
```
