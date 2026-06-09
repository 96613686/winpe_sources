# std::_Uninit_move<APPID_PLUGIN_ *,APPID_PLUGIN_ *,std::allocator<APPID_PLUGIN_>,APPID_PLUGIN_>(APPID_PLUGIN_ *,APPID_PLUGIN_ *,APPID_PLUGIN_ *,std::_Wrap_alloc<std::allocator<APPID_PLUGIN_>> &,APPID_PLUGIN_ *,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x140002644`
- end: `0x140002680`
- name: `??$_Uninit_move@PEAUAPPID_PLUGIN_@@PEAU1@V?$allocator@UAPPID_PLUGIN_@@@std@@U1@@std@@YAPEAUAPPID_PLUGIN_@@PEAU1@00AEAU?$_Wrap_alloc@V?$allocator@UAPPID_PLUGIN_@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `60`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14000696c`

## callees

- `0x140002644`

## pseudocode

```c
__int64 __fastcall std::_Uninit_move<APPID_PLUGIN_ *,APPID_PLUGIN_ *,std::allocator<APPID_PLUGIN_>,APPID_PLUGIN_>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  try
  {
    while ( a1 != a2 )
    {
      *(_OWORD *)a3 = *(_OWORD *)a1;
      *(_OWORD *)(a3 + 16) = *(_OWORD *)(a1 + 16);
      *(_DWORD *)(a3 + 32) = *(_DWORD *)(a1 + 32);
      a3 += 36;
      a1 += 36;
    }
  }
  catch ( ... )
  {
    throw;
  }
  return a3;
}

```

## disassembly

```asm
0x140002644  sub     rsp, 28h
0x140002648  cmp     rcx, rdx
0x14000264b  jz      short loc_140002678
0x14000264d  movups  xmm0, xmmword ptr [rcx]
0x140002650  movups  xmmword ptr [r8], xmm0
0x140002654  movups  xmm1, xmmword ptr [rcx+10h]
0x140002658  movups  xmmword ptr [r8+10h], xmm1
0x14000265d  mov     eax, [rcx+20h]
0x140002660  mov     [r8+20h], eax
0x140002664  add     r8, 24h ; '$'
0x140002668  mov     [rsp+28h+arg_10], r8
0x14000266d  add     rcx, 24h ; '$'
0x140002671  mov     [rsp+28h+arg_0], rcx
0x140002676  jmp     short loc_140002648
0x140002678  mov     rax, r8
0x14000267b  add     rsp, 28h
0x14000267f  retn
```
