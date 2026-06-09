# EnsureCoInitialized(int *)

- ea: `0x140005594`
- end: `0x1400055dd`
- name: `?EnsureCoInitialized@@YAJPEAH@Z`
- size: `73`
- prototype: `HRESULT __fastcall(int *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140002d20`
- `0x140002d6c`

## callees

- `0x140005594`

## import_xrefs

- `ole32!CoInitializeEx` at `0x1400055a5`
- `ole32!CoInitializeEx` at `0x1400055a5`
- `ole32!CoUninitialize` at `0x1400055c0`
- `ole32!CoUninitialize` at `0x1400055c0`

## pseudocode

```c
HRESULT __fastcall EnsureCoInitialized(int *a1)
{
  HRESULT result; // eax

  result = CoInitializeEx(0, 0);
  if ( result )
  {
    *a1 = 0;
    if ( result == 1 )
    {
      CoUninitialize();
      return 0;
    }
    else if ( result == -2147417850 )
    {
      return 0;
    }
  }
  else
  {
    *a1 = 1;
  }
  return result;
}

```

## disassembly

```asm
0x140005594  mov     [rsp+arg_0], rbx
0x140005599  push    rdi
0x14000559a  sub     rsp, 20h
0x14000559e  mov     rbx, rcx
0x1400055a1  xor     edx, edx; dwCoInit
0x1400055a3  xor     ecx, ecx; pvReserved
0x1400055a5  call    cs:__imp_CoInitializeEx
0x1400055ab  xor     edi, edi
0x1400055ad  test    eax, eax
0x1400055af  jnz     short loc_1400055B9
0x1400055b1  mov     dword ptr [rbx], 1
0x1400055b7  jmp     short loc_1400055D2
0x1400055b9  mov     [rbx], edi
0x1400055bb  cmp     eax, 1
0x1400055be  jnz     short loc_1400055CA
0x1400055c0  call    cs:__imp_CoUninitialize
0x1400055c6  mov     eax, edi
0x1400055c8  jmp     short loc_1400055D2
0x1400055ca  cmp     eax, 80010106h
0x1400055cf  cmovz   eax, edi
0x1400055d2  mov     rbx, [rsp+28h+arg_0]
0x1400055d7  add     rsp, 20h
0x1400055db  pop     rdi
0x1400055dc  retn
```
