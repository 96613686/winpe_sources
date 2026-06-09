# Mso::LoadMso::LoadDllResults::~LoadDllResults(void)

- ea: `0x140004da8`
- end: `0x140004e02`
- name: `??1LoadDllResults@LoadMso@Mso@@QEAA@XZ`
- size: `90`
- prototype: `void __fastcall(Mso::LoadMso::LoadDllResults *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140004da0`
- `0x140004fe0`
- `0x1400055d4`

## callees

- `0x140004c2c`

## pseudocode

```c
void __fastcall Mso::LoadMso::LoadDllResults::~LoadDllResults(Mso::LoadMso::LoadDllResults *this)
{
  std::wstring::_Tidy_deallocate((char *)this + 64);
  *((_QWORD *)this + 8) = 19937;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 15;
  std::wstring::_Tidy_deallocate((char *)this + 16);
  *((_QWORD *)this + 2) = 19937;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 15;
}

```

## disassembly

```asm
0x140004da8  mov     [rsp+arg_0], rbx
0x140004dad  push    rdi
0x140004dae  sub     rsp, 20h
0x140004db2  mov     rdi, rcx
0x140004db5  add     rcx, 40h ; '@'
0x140004db9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140004dbe  lea     rcx, [rdi+10h]
0x140004dc2  mov     qword ptr [rdi+40h], 4DE1h
0x140004dca  mov     qword ptr [rdi+50h], 0
0x140004dd2  mov     qword ptr [rdi+58h], 0Fh
0x140004dda  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140004ddf  mov     rbx, [rsp+28h+arg_0]
0x140004de4  mov     qword ptr [rdi+10h], 4DE1h
0x140004dec  mov     qword ptr [rdi+20h], 0
0x140004df4  mov     qword ptr [rdi+28h], 0Fh
0x140004dfc  add     rsp, 20h
0x140004e00  pop     rdi
0x140004e01  retn
```
