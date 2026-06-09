# CDownloadService::`vector deleting destructor'(uint)

- ea: `0x1800132e0`
- end: `0x18001332a`
- name: `??_ECDownloadService@@UEAAPEAXI@Z`
- size: `74`
- prototype: `void *__fastcall(CDownloadService *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task`

## callees

- `0x1800062ac`
- `0x1800132e0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001330f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001330f`

## pseudocode

```c
CDownloadService *__fastcall CDownloadService::`vector deleting destructor'(CDownloadService *this, __int64 a2)
{
  char v2; // bl

  v2 = a2;
  *(_QWORD *)this = &CDownloadService::`vftable';
  LOBYTE(a2) = 1;
  std::wstring::_Tidy((char *)this + 16, a2, 0);
  if ( (v2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800132e0  mov     [rsp+arg_0], rbx
0x1800132e5  push    rdi
0x1800132e6  sub     rsp, 20h
0x1800132ea  lea     rax, ??_7CDownloadService@@6B@; const CDownloadService::`vftable'
0x1800132f1  mov     ebx, edx
0x1800132f3  mov     [rcx], rax
0x1800132f6  mov     rdi, rcx
0x1800132f9  add     rcx, 10h
0x1800132fd  xor     r8d, r8d
0x180013300  mov     dl, 1
0x180013302  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180013307  test    bl, 1
0x18001330a  jz      short loc_18001331B
0x18001330c  mov     rcx, rdi
0x18001330f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180013316  nop     dword ptr [rax+rax+00h]
0x18001331b  mov     rbx, [rsp+28h+arg_0]
0x180013320  mov     rax, rdi
0x180013323  add     rsp, 20h
0x180013327  pop     rdi
0x180013328  retn
```
