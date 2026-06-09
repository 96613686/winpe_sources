# DllMain2

- ea: `0x18001a24c`
- end: `0x18001a2c2`
- name: `DllMain2`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001040`

## callees

- `0x180001dd8`
- `0x1800191c0`
- `0x18001a24c`
- `0x180030010`

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x18001a282`
- `MSDART!MPDeleteCriticalSection` at `0x18001a282`

## pseudocode

```c
__int64 __fastcall DllMain2(HMODULE a1, int a2)
{
  unsigned int v2; // ebx
  unsigned __int8 *v3; // rdi

  v2 = 1;
  if ( a2 )
  {
    if ( a2 == 1 )
    {
      g_hInstancePersistMain = a1;
      return (unsigned int)MSPersistInit();
    }
  }
  else
  {
    v3 = g_pcsDataConvert;
    if ( g_pcsDataConvert )
    {
      MPDeleteCriticalSection(g_pcsDataConvert);
      MMMFree(v3);
    }
    try
    {
      g_pcsDataConvert = 0;
      ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
    }
    catch ( ... )
    {
      return 0;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18001a24c  mov     [rsp+arg_0], rbx
0x18001a251  push    rdi
0x18001a252  sub     rsp, 20h
0x18001a256  mov     ebx, 1
0x18001a25b  test    edx, edx
0x18001a25d  jz      short loc_18001A273
0x18001a25f  cmp     edx, ebx
0x18001a261  jnz     short loc_18001A2B5
0x18001a263  mov     cs:?g_hInstancePersistMain@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * g_hInstancePersistMain
0x18001a26a  call    ?MSPersistInit@@YAHXZ; MSPersistInit(void)
0x18001a26f  mov     ebx, eax
0x18001a271  jmp     short loc_18001A2B5
0x18001a273  mov     rdi, cs:?g_pcsDataConvert@@3PEAVCFoxCriticalSection@@EA; CFoxCriticalSection * g_pcsDataConvert
0x18001a27a  test    rdi, rdi
0x18001a27d  jz      short loc_18001A290
0x18001a27f  mov     rcx, rdi
0x18001a282  call    cs:__imp_MPDeleteCriticalSection
0x18001a288  mov     rcx, rdi; unsigned __int8 *
0x18001a28b  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x18001a290  mov     cs:?g_pcsDataConvert@@3PEAVCFoxCriticalSection@@EA, 0; CFoxCriticalSection * g_pcsDataConvert
0x18001a29b  mov     rcx, cs:ppMalloc
0x18001a2a2  mov     rax, [rcx]
0x18001a2a5  mov     rax, [rax+10h]
0x18001a2a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a2ae  nop
0x18001a2af  jmp     short loc_18001A2B5
0x18001a2b1  mov     ebx, [rsp+28h+arg_8]
0x18001a2b5  mov     eax, ebx
0x18001a2b7  mov     rbx, [rsp+28h+arg_0]
0x18001a2bc  add     rsp, 20h
0x18001a2c0  pop     rdi
0x18001a2c1  retn
```
