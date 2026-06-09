# Broker::ApplicationIdentity::~ApplicationIdentity(void)

- ea: `0x1800042b8`
- end: `0x1800042e0`
- name: `??1ApplicationIdentity@Broker@@QEAA@XZ`
- size: `40`
- prototype: `void __fastcall(Broker::ApplicationIdentity *__hidden this)`
- caller_count: `11`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ef50`
- `0x1800118e0`
- `0x180011c20`
- `0x1800147b0`
- `0x1800149d0`
- `0x180019ee6`
- `0x18001a02a`
- `0x18001a444`
- `0x18001acef`
- `0x18001b44b`
- `0x18001b5c9`

## callees

- `0x180004b70`
- `0x1800112d8`

## pseudocode

```c
void __fastcall Broker::ApplicationIdentity::~ApplicationIdentity(Broker::ApplicationIdentity *this)
{
  std::wstring::_Tidy_deallocate((char *)this + 56);
  std::wstring::_Tidy_deallocate((char *)this + 24);
  std::vector<unsigned char>::_Tidy(this);
}

```

## disassembly

```asm
0x1800042b8  push    rbx
0x1800042ba  sub     rsp, 20h
0x1800042be  mov     rbx, rcx
0x1800042c1  add     rcx, 38h ; '8'
0x1800042c5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800042ca  lea     rcx, [rbx+18h]
0x1800042ce  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800042d3  mov     rcx, rbx
0x1800042d6  add     rsp, 20h
0x1800042da  pop     rbx
0x1800042db  jmp     ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
```
