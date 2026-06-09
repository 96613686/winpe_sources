# std::unique_ptr<AppMon::AppPortEntry,std::default_delete<AppMon::AppPortEntry>>::~unique_ptr<AppMon::AppPortEntry,std::default_delete<AppMon::AppPortEntry>>(void)

- ea: `0x180008744`
- end: `0x18000875f`
- name: `??1?$unique_ptr@VAppPortEntry@AppMon@@U?$default_delete@VAppPortEntry@AppMon@@@std@@@std@@QEAA@XZ`
- size: `27`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180008d9c`
- `0x18000f70d`

## callees

- `0x180008744`
- `0x180009460`

## pseudocode

```c
void *__fastcall std::unique_ptr<AppMon::AppPortEntry>::~unique_ptr<AppMon::AppPortEntry>(AppMon::AppPortEntry **a1)
{
  AppMon::AppPortEntry *v1; // rcx
  void *result; // rax

  v1 = *a1;
  if ( v1 )
    return AppMon::AppPortEntry::`scalar deleting destructor'(v1, 1u);
  return result;
}

```

## disassembly

```asm
0x180008744  sub     rsp, 28h
0x180008748  mov     rcx, [rcx]; this
0x18000874b  test    rcx, rcx
0x18000874e  jz      short loc_18000875A
0x180008750  mov     edx, 1; unsigned int
0x180008755  call    ??_GAppPortEntry@AppMon@@QEAAPEAXI@Z; AppMon::AppPortEntry::`scalar deleting destructor'(uint)
0x18000875a  add     rsp, 28h
0x18000875e  retn
```
