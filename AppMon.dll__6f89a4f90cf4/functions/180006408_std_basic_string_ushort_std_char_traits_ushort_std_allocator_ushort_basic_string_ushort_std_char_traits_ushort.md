# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x180006408`
- end: `0x180006442`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `58`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `25`
- callee_count: `2`
- tags: ``

## callers

- `0x18000681c`
- `0x180006bb0`
- `0x1800074ac`
- `0x180008d9c`
- `0x180009424`
- `0x18000b34c`
- `0x18000b6a8`
- `0x18000bafc`
- `0x18000c234`
- `0x18000c808`
- `0x18000ca20`
- `0x18000e0e4`
- `0x18000e84c`
- `0x18000f5d5`
- `0x18000f60b`
- `0x18000f62f`
- `0x18000f767`
- `0x18000f942`
- `0x18000fa1a`
- `0x18000fa86`
- `0x18000faaa`
- `0x18000face`
- `0x18000fb0c`
- `0x18000fbb5`
- `0x18000fc10`

## callees

- `0x180006288`
- `0x180006408`

## pseudocode

```c
__int64 __fastcall std::wstring::~wstring(__int64 a1)
{
  unsigned __int64 v1; // rdx
  __int64 result; // rax

  v1 = *(_QWORD *)(a1 + 24);
  if ( v1 > 7 )
    std::_Deallocate<16>(*(void **)a1, 2 * v1 + 2);
  result = 0;
  *(_QWORD *)(a1 + 24) = 7;
  *(_QWORD *)(a1 + 16) = 0;
  *(_WORD *)a1 = 0;
  return result;
}

```

## disassembly

```asm
0x180006408  push    rbx
0x18000640a  sub     rsp, 20h
0x18000640e  mov     rdx, [rcx+18h]
0x180006412  mov     rbx, rcx
0x180006415  cmp     rdx, 7
0x180006419  jbe     short loc_18000642B
0x18000641b  mov     rcx, [rcx]
0x18000641e  lea     rdx, ds:2[rdx*2]
0x180006426  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000642b  xor     eax, eax
0x18000642d  mov     qword ptr [rbx+18h], 7
0x180006435  mov     [rbx+10h], rax
0x180006439  mov     [rbx], ax
0x18000643c  add     rsp, 20h
0x180006440  pop     rbx
0x180006441  retn
```
