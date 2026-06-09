# EnsureCoInitialized(int *)

- ea: `0x180003238`
- end: `0x180003281`
- name: `?EnsureCoInitialized@@YAJPEAH@Z`
- size: `73`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800016f4`
- `0x1800022a0`

## callees

- `0x180003238`

## import_xrefs

- `ole32!CoInitializeEx` at `0x180003249`
- `ole32!CoInitializeEx` at `0x180003249`
- `ole32!CoUninitialize` at `0x180003264`
- `ole32!CoUninitialize` at `0x180003264`

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
0x180003238  mov     [rsp+arg_0], rbx
0x18000323d  push    rdi
0x18000323e  sub     rsp, 20h
0x180003242  mov     rbx, rcx
0x180003245  xor     edx, edx; dwCoInit
0x180003247  xor     ecx, ecx; pvReserved
0x180003249  call    cs:__imp_CoInitializeEx
0x18000324f  xor     edi, edi
0x180003251  test    eax, eax
0x180003253  jnz     short loc_18000325D
0x180003255  mov     dword ptr [rbx], 1
0x18000325b  jmp     short loc_180003276
0x18000325d  mov     [rbx], edi
0x18000325f  cmp     eax, 1
0x180003262  jnz     short loc_18000326E
0x180003264  call    cs:__imp_CoUninitialize
0x18000326a  mov     eax, edi
0x18000326c  jmp     short loc_180003276
0x18000326e  cmp     eax, 80010106h
0x180003273  cmovz   eax, edi
0x180003276  mov     rbx, [rsp+28h+arg_0]
0x18000327b  add     rsp, 20h
0x18000327f  pop     rdi
0x180003280  retn
```
