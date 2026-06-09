# BampReferenceThrottledProcessInformation

- ea: `0x140010880`
- end: `0x1400108a0`
- name: `BampReferenceThrottledProcessInformation`
- size: `32`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14001044c`
- `0x140010684`
- `0x14001474c`

## callees

- `0x140010880`

## pseudocode

```c
__int64 __fastcall BampReferenceThrottledProcessInformation(__int64 a1)
{
  __int64 result; // rax

  result = _InterlockedIncrement64((volatile signed __int64 *)(a1 + 264));
  if ( result <= 1 )
    __fastfail(0xEu);
  return result;
}

```

## disassembly

```asm
0x140010880  mov     eax, 1
0x140010885  lock xadd [rcx+108h], rax
0x14001088e  inc     rax
0x140010891  cmp     rax, 1
0x140010895  jle     short loc_140010899
0x140010897  retn
0x140010899  mov     ecx, 0Eh
0x14001089e  int     29h; Win8: RtlFailFast(ecx)
```
