# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(ushort const *)

- ea: `0x18000f77c`
- end: `0x18000f7b5`
- name: `??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z`
- size: `57`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f234`
- `0x1800103e8`
- `0x1800132c0`
- `0x180013464`
- `0x1800138c0`
- `0x180014170`
- `0x180014490`

## callees

- `0x18000f77c`
- `0x1800126f4`

## pseudocode

```c
__int64 __fastcall std::wstring::wstring(__int64 a1, __int64 a2)
{
  __int64 v3; // r8

  *(_QWORD *)(a1 + 24) = 7;
  v3 = -1;
  *(_QWORD *)(a1 + 16) = 0;
  *(_WORD *)a1 = 0;
  do
    ++v3;
  while ( *(_WORD *)(a2 + 2 * v3) );
  std::wstring::assign(a1);
  return a1;
}

```

## disassembly

```asm
0x18000f77c  push    rbx
0x18000f77e  sub     rsp, 20h
0x18000f782  mov     rbx, rcx
0x18000f785  mov     qword ptr [rcx+18h], 7
0x18000f78d  xor     ecx, ecx
0x18000f78f  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000f793  mov     [rbx+10h], rcx
0x18000f797  mov     [rbx], cx
0x18000f79a  inc     r8
0x18000f79d  cmp     [rdx+r8*2], cx
0x18000f7a2  jnz     short loc_18000F79A
0x18000f7a4  mov     rcx, rbx
0x18000f7a7  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18000f7ac  mov     rax, rbx
0x18000f7af  add     rsp, 20h
0x18000f7b3  pop     rbx
0x18000f7b4  retn
```
