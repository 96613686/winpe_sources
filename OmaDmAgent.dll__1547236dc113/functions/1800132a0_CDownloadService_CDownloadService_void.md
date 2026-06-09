# CDownloadService::~CDownloadService(void)

- ea: `0x1800132a0`
- end: `0x1800132b8`
- name: `??1CDownloadService@@UEAA@XZ`
- size: `24`
- prototype: `void __fastcall(CDownloadService *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180020654`
- `0x18002068e`
- `0x1800206e8`

## callees

- `0x1800062ac`

## pseudocode

```c
void __fastcall CDownloadService::~CDownloadService(CDownloadService *this, __int64 a2)
{
  *(_QWORD *)this = &CDownloadService::`vftable';
  LOBYTE(a2) = 1;
  std::wstring::_Tidy((char *)this + 16, a2, 0);
}

```

## disassembly

```asm
0x1800132a0  lea     rax, ??_7CDownloadService@@6B@; const CDownloadService::`vftable'
0x1800132a7  xor     r8d, r8d
0x1800132aa  mov     [rcx], rax
0x1800132ad  mov     dl, 1
0x1800132af  add     rcx, 10h
0x1800132b3  jmp     ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
```
