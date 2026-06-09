# std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(std::shared_ptr<IWICImagingFactory> const &)

- ea: `0x18000da08`
- end: `0x18000da24`
- name: `??$_Copy_construct_from@UIWICImagingFactory@@@?$_Ptr_base@UIWICImagingFactory@@@std@@IEAAXAEBV?$shared_ptr@UIWICImagingFactory@@@1@@Z`
- size: `28`
- prototype: ``
- caller_count: `32`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e1f8`
- `0x180012254`
- `0x180014568`
- `0x180018414`
- `0x1800184e8`
- `0x180019a94`
- `0x180028680`
- `0x180028810`
- `0x180028acc`
- `0x180029538`
- `0x18002969c`
- `0x18002976c`
- `0x18002990c`
- `0x18002a000`
- `0x18002a684`
- `0x18002b6f4`
- `0x18002bcf0`
- `0x180033d5c`
- `0x18003426c`
- `0x180037c20`
- `0x180038e80`
- `0x180039984`
- `0x180039cd4`
- `0x18003a18c`
- `0x18003c42c`
- `0x18003eb20`
- `0x18003edd0`
- `0x18003fcc8`
- `0x1800427b0`
- `0x1800432dc`
- `0x180043d74`
- `0x180045b18`

## callees

- `0x18000da08`

## pseudocode

```c
__int64 __fastcall std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(_QWORD *a1, _QWORD *a2)
{
  __int64 v2; // rax
  __int64 result; // rax

  v2 = a2[1];
  if ( v2 )
    _InterlockedIncrement((volatile signed __int32 *)(v2 + 8));
  *a1 = *a2;
  result = a2[1];
  a1[1] = result;
  return result;
}

```

## disassembly

```asm
0x18000da08  mov     rax, [rdx+8]
0x18000da0c  test    rax, rax
0x18000da0f  jz      short loc_18000DA15
0x18000da11  lock inc dword ptr [rax+8]
0x18000da15  mov     rax, [rdx]
0x18000da18  mov     [rcx], rax
0x18000da1b  mov     rax, [rdx+8]
0x18000da1f  mov     [rcx+8], rax
0x18000da23  retn
```
