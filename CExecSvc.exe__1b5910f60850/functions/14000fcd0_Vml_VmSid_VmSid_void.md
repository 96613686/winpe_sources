# Vml::VmSid::~VmSid(void)

- ea: `0x14000fcd0`
- end: `0x14000fcfe`
- name: `??1VmSid@Vml@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(char **this)`
- caller_count: `7`
- callee_count: `2`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14002302f`
- `0x140023041`
- `0x140023053`
- `0x1400230a3`
- `0x1400230b5`
- `0x1400230c7`
- `0x1400230d9`

## callees

- `0x140008160`
- `0x14000fcd0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000fce1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000fce1`

## pseudocode

```c
void __fastcall Vml::VmSid::~VmSid(char **this)
{
  char *v2; // rcx

  v2 = *this;
  if ( v2 )
    LocalFree(v2);
  std::wstring::~wstring(this + 6);
  std::wstring::~wstring(this + 2);
}

```

## disassembly

```asm
0x14000fcd0  push    rbx
0x14000fcd2  sub     rsp, 20h
0x14000fcd6  mov     rbx, rcx
0x14000fcd9  mov     rcx, [rcx]; hMem
0x14000fcdc  test    rcx, rcx
0x14000fcdf  jz      short loc_14000FCE7
0x14000fce1  call    cs:__imp_LocalFree
0x14000fce7  lea     rcx, [rbx+30h]
0x14000fceb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000fcf0  lea     rcx, [rbx+10h]
0x14000fcf4  add     rsp, 20h
0x14000fcf8  pop     rbx
0x14000fcf9  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
