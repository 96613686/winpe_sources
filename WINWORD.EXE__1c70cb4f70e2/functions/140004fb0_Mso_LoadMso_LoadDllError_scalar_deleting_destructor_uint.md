# Mso::LoadMso::LoadDllError::`scalar deleting destructor'(uint)

- ea: `0x140004fb0`
- end: `0x140004fde`
- name: `??_GLoadDllError@LoadMso@Mso@@QEAAPEAXI@Z`
- size: `46`
- prototype: `void *__fastcall(Mso::LoadMso::LoadDllError *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140004e04`
- `0x140004fe0`

## callees

- `0x140004c2c`

## pseudocode

```c
void *__fastcall Mso::LoadMso::LoadDllError::`scalar deleting destructor'(Mso::LoadMso::LoadDllError *this)
{
  void *result; // rax

  std::wstring::_Tidy_deallocate(this);
  result = this;
  *(_QWORD *)this = 19937;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 15;
  return result;
}

```

## disassembly

```asm
0x140004fb0  push    rbx
0x140004fb2  sub     rsp, 20h
0x140004fb6  mov     rbx, rcx
0x140004fb9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140004fbe  mov     rax, rbx
0x140004fc1  mov     qword ptr [rbx], 4DE1h
0x140004fc8  mov     qword ptr [rbx+10h], 0
0x140004fd0  mov     qword ptr [rbx+18h], 0Fh
0x140004fd8  add     rsp, 20h
0x140004fdc  pop     rbx
0x140004fdd  retn
```
