# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`scalar deleting destructor'(uint)

- ea: `0x180009424`
- end: `0x180009458`
- name: `??_G?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAPEAXI@Z`
- size: `52`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180007fb8`
- `0x1800086d8`
- `0x180008708`
- `0x180009b10`
- `0x180009b40`

## callees

- `0x1800019f0`
- `0x180006408`
- `0x180009424`

## pseudocode

```c
void *__fastcall std::wstring::`scalar deleting destructor'(void *a1, char a2)
{
  std::wstring::~wstring((__int64)a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180009424  mov     [rsp+arg_0], rbx
0x180009429  push    rdi
0x18000942a  sub     rsp, 20h
0x18000942e  mov     ebx, edx
0x180009430  mov     rdi, rcx
0x180009433  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180009438  test    bl, 1
0x18000943b  jz      short loc_18000944A
0x18000943d  mov     edx, 20h ; ' '; unsigned __int64
0x180009442  mov     rcx, rdi; void *
0x180009445  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000944a  mov     rbx, [rsp+28h+arg_0]
0x18000944f  mov     rax, rdi
0x180009452  add     rsp, 20h
0x180009456  pop     rdi
0x180009457  retn
```
