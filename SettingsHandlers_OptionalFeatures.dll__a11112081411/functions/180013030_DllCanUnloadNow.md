# DllCanUnloadNow

- ea: `0x180013030`
- end: `0x180013065`
- name: `DllCanUnloadNow`
- size: `53`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800126bc`
- `0x180012e34`
- `0x180013030`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x18001303b`
- `RPCRT4!NdrDllCanUnloadNow` at `0x18001303b`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT CanUnloadNow; // ecx
  __int64 *v1; // rax
  RTL_SRWLOCK *v2; // rdx

  CanUnloadNow = NdrDllCanUnloadNow(&pPSFactoryBuffer);
  if ( !CanUnloadNow )
  {
    v1 = sub_1800126BC();
    return !sub_180012E34((__int64)v1, v2, 0);
  }
  return CanUnloadNow;
}

```

## disassembly

```asm
0x180013030  sub     rsp, 28h
0x180013034  lea     rcx, pPSFactoryBuffer; pPSFactoryBuffer
0x18001303b  call    cs:NdrDllCanUnloadNow
0x180013041  mov     ecx, eax
0x180013043  test    eax, eax
0x180013045  jnz     short loc_18001305E
0x180013047  call    sub_1800126BC
0x18001304c  xor     r8d, r8d
0x18001304f  mov     rcx, rax
0x180013052  call    sub_180012E34
0x180013057  xor     ecx, ecx
0x180013059  test    al, al
0x18001305b  setz    cl
0x18001305e  mov     eax, ecx
0x180013060  add     rsp, 28h
0x180013064  retn
```
