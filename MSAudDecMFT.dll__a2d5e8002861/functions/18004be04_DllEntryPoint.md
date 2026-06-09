# _DllEntryPoint

- ea: `0x18004be04`
- end: `0x18004be43`
- name: `_DllEntryPoint`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180041b94`

## callees

- `0x180041274`
- `0x18004be04`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18004be16`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18004be16`

## pseudocode

```c
__int64 __fastcall DllEntryPoint(HMODULE a1, int a2)
{
  int v3; // ecx

  if ( !a2 )
  {
    v3 = 0;
    goto LABEL_5;
  }
  if ( a2 == 1 )
  {
    DisableThreadLibraryCalls(a1);
    v3 = 1;
    g_hInst = a1;
LABEL_5:
    DllInitClasses(v3);
  }
  return 1;
}

```

## disassembly

```asm
0x18004be04  push    rbx
0x18004be06  sub     rsp, 20h
0x18004be0a  mov     rbx, rcx
0x18004be0d  test    edx, edx
0x18004be0f  jz      short loc_18004BE30
0x18004be11  cmp     edx, 1
0x18004be14  jnz     short loc_18004BE37
0x18004be16  call    cs:__imp_DisableThreadLibraryCalls
0x18004be1d  nop     dword ptr [rax+rax+00h]
0x18004be22  mov     ecx, 1
0x18004be27  mov     cs:?g_hInst@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hInst
0x18004be2e  jmp     short loc_18004BE32
0x18004be30  xor     ecx, ecx; int
0x18004be32  call    ?DllInitClasses@@YAXH@Z; DllInitClasses(int)
0x18004be37  mov     eax, 1
0x18004be3c  add     rsp, 20h
0x18004be40  pop     rbx
0x18004be41  retn
```
