# std::vector<DISPLAYCONFIG_MODE_INFO,std::allocator<DISPLAYCONFIG_MODE_INFO>>::_Tidy(void)

- ea: `0x14000f16c`
- end: `0x14000f1aa`
- name: `?_Tidy@?$vector@UDISPLAYCONFIG_MODE_INFO@@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@AEAAXXZ`
- size: `62`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000e15c`
- `0x14000e7e4`

## callees

- `0x14000dff4`
- `0x14000f16c`

## pseudocode

```c
__int64 __fastcall std::vector<DISPLAYCONFIG_MODE_INFO>::_Tidy(__int64 *a1)
{
  __int64 v2; // rcx
  __int64 result; // rax

  v2 = *a1;
  if ( v2 )
  {
    result = std::_Deallocate<16>(v2, (a1[2] - v2) & 0xFFFFFFFFFFFFFFC0uLL);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000f16c  push    rbx
0x14000f16e  sub     rsp, 20h
0x14000f172  mov     rbx, rcx
0x14000f175  mov     rcx, [rcx]
0x14000f178  test    rcx, rcx
0x14000f17b  jz      short loc_14000F1A4
0x14000f17d  mov     rdx, [rbx+10h]
0x14000f181  sub     rdx, rcx
0x14000f184  and     rdx, 0FFFFFFFFFFFFFFC0h
0x14000f188  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x14000f18d  mov     qword ptr [rbx], 0
0x14000f194  mov     qword ptr [rbx+8], 0
0x14000f19c  mov     qword ptr [rbx+10h], 0
0x14000f1a4  add     rsp, 20h
0x14000f1a8  pop     rbx
0x14000f1a9  retn
```
