# PackageCollector::~PackageCollector(void)

- ea: `0x14000ac60`
- end: `0x14000acd4`
- name: `??1PackageCollector@@UEAA@XZ`
- size: `116`
- prototype: `void __fastcall(PackageCollector *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140006b70`
- `0x14000ace0`
- `0x14000e3e1`

## callees

- `0x140001130`
- `0x140003a0c`
- `0x14000ac60`
- `0x14000ded0`

## pseudocode

```c
void __fastcall PackageCollector::~PackageCollector(PackageCollector *this)
{
  *(_QWORD *)this = &PackageCollector::`vftable';
  if ( (unsigned int)dword_140017048 > 5 )
    tlgWriteTransfer_EventWriteTransfer(&dword_140017048, word_1400136E2, 0, 0);
  std::vector<std::wstring>::_Tidy((char *)this + 8);
}

```

## disassembly

```asm
0x14000ac60  push    rbx
0x14000ac62  sub     rsp, 60h
0x14000ac66  mov     rax, cs:__security_cookie
0x14000ac6d  xor     rax, rsp
0x14000ac70  mov     [rsp+68h+var_18], rax
0x14000ac75  lea     rax, ??_7PackageCollector@@6B@; const PackageCollector::`vftable'
0x14000ac7c  mov     rbx, rcx
0x14000ac7f  mov     [rcx], rax
0x14000ac82  mov     eax, cs:dword_140017048
0x14000ac88  cmp     eax, 5
0x14000ac8b  jbe     short loc_14000ACB8
0x14000ac8d  lea     rax, [rsp+68h+var_38]
0x14000ac92  xor     r9d, r9d
0x14000ac95  mov     [rsp+68h+var_40], rax
0x14000ac9a  lea     rdx, word_1400136E2
0x14000aca1  xor     r8d, r8d
0x14000aca4  mov     [rsp+68h+var_48], 2
0x14000acac  lea     rcx, dword_140017048
0x14000acb3  call    _tlgWriteTransfer_EventWriteTransfer
0x14000acb8  lea     rcx, [rbx+8]
0x14000acbc  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x14000acc1  mov     rcx, [rsp+68h+var_18]
0x14000acc6  xor     rcx, rsp; StackCookie
0x14000acc9  call    __security_check_cookie
0x14000acce  add     rsp, 60h
0x14000acd2  pop     rbx
0x14000acd3  retn
```
