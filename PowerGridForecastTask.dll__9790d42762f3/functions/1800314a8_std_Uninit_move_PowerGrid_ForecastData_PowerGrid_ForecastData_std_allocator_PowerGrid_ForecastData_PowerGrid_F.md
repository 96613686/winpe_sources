# std::_Uninit_move<PowerGrid::ForecastData *,PowerGrid::ForecastData *,std::allocator<PowerGrid::ForecastData>,PowerGrid::ForecastData>(PowerGrid::ForecastData *,PowerGrid::ForecastData *,PowerGrid::ForecastData *,std::_Wrap_alloc<std::allocator<PowerGrid::ForecastData>> &,PowerGrid::ForecastData *,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x1800314a8`
- end: `0x1800314cb`
- name: `??$_Uninit_move@PEAUForecastData@PowerGrid@@PEAU12@V?$allocator@UForecastData@PowerGrid@@@std@@U12@@std@@YAPEAUForecastData@PowerGrid@@PEAU12@00AEAU?$_Wrap_alloc@V?$allocator@UForecastData@PowerGrid@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `35`
- prototype: `_OWORD *__fastcall(_OWORD *, _OWORD *, _OWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180033f1c`

## callees

- `0x1800314a8`

## pseudocode

```c
_OWORD *__fastcall std::_Uninit_move<PowerGrid::ForecastData *,PowerGrid::ForecastData *,std::allocator<PowerGrid::ForecastData>,PowerGrid::ForecastData>(
        _OWORD *a1,
        _OWORD *a2,
        _OWORD *a3)
{
  while ( a1 != a2 )
    *a3++ = *a1++;
  return a3;
}

```

## disassembly

```asm
0x1800314a8  sub     rsp, 28h
0x1800314ac  jmp     short loc_1800314BE
0x1800314ae  movups  xmm0, xmmword ptr [rcx]
0x1800314b1  movdqu  xmmword ptr [r8], xmm0
0x1800314b6  add     r8, 10h
0x1800314ba  add     rcx, 10h
0x1800314be  cmp     rcx, rdx
0x1800314c1  jnz     short loc_1800314AE
0x1800314c3  mov     rax, r8
0x1800314c6  add     rsp, 28h
0x1800314ca  retn
```
