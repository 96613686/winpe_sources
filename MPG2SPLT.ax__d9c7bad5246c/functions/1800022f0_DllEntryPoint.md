# _DllEntryPoint

- ea: `0x1800022f0`
- end: `0x180002328`
- name: `_DllEntryPoint`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001f74`

## callees

- `0x1800020ac`
- `0x1800022f0`

## import_xrefs

- `KERNEL32!DisableThreadLibraryCalls` at `0x180002302`
- `KERNEL32!DisableThreadLibraryCalls` at `0x180002302`

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
0x1800022f0  push    rbx
0x1800022f2  sub     rsp, 20h
0x1800022f6  mov     rbx, rcx
0x1800022f9  test    edx, edx
0x1800022fb  jz      short loc_180002316
0x1800022fd  cmp     edx, 1
0x180002300  jnz     short loc_18000231D
0x180002302  call    cs:__imp_DisableThreadLibraryCalls
0x180002308  mov     ecx, 1
0x18000230d  mov     cs:?g_hInst@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hInst
0x180002314  jmp     short loc_180002318
0x180002316  xor     ecx, ecx; int
0x180002318  call    ?DllInitClasses@@YAXH@Z; DllInitClasses(int)
0x18000231d  mov     eax, 1
0x180002322  add     rsp, 20h
0x180002326  pop     rbx
0x180002327  retn
```
