# DllCanUnloadNow

- ea: `0x1800014f0`
- end: `0x180001536`
- name: `DllCanUnloadNow`
- size: `70`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800014f0`

## import_xrefs

- `KERNEL32!Sleep` at `0x180001525`
- `KERNEL32!Sleep` at `0x180001525`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  signed __int32 v0; // eax
  signed __int32 v1; // ecx
  signed __int32 v2; // ecx

  v0 = _InterlockedExchangeAdd(&dword_1800B20C8, 1u);
  _InterlockedDecrement(&dword_1800B20C8);
  v1 = _InterlockedExchangeAdd(&dword_1800B20CC, 1u);
  _InterlockedDecrement(&dword_1800B20CC);
  v2 = v1 + 1;
  if ( v0 != -1 || v2 )
    return 1;
  Sleep(0);
  return 0;
}

```

## disassembly

```asm
0x1800014f0  sub     rsp, 28h
0x1800014f4  mov     edx, 1
0x1800014f9  mov     eax, edx
0x1800014fb  lock xadd cs:dword_1800B20C8, eax
0x180001503  lock dec cs:dword_1800B20C8
0x18000150a  mov     ecx, edx
0x18000150c  lock xadd cs:dword_1800B20CC, ecx
0x180001514  lock dec cs:dword_1800B20CC
0x18000151b  add     ecx, edx; dwMilliseconds
0x18000151d  add     eax, edx
0x18000151f  jnz     short loc_18000152F
0x180001521  test    ecx, ecx
0x180001523  jnz     short loc_18000152F
0x180001525  call    cs:__imp_Sleep
0x18000152b  xor     eax, eax
0x18000152d  jmp     short loc_180001531
0x18000152f  mov     eax, edx
0x180001531  add     rsp, 28h
0x180001535  retn
```
