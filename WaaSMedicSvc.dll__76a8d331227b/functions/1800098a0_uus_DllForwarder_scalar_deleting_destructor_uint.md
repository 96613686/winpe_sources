# uus::DllForwarder::`scalar deleting destructor'(uint)

- ea: `0x1800098a0`
- end: `0x180009914`
- name: `??_GDllForwarder@uus@@UEAAPEAXI@Z`
- size: `116`
- prototype: `char **__fastcall(char **this, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callees

- `0x1800025d0`
- `0x180008f20`
- `0x1800098a0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800098d4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800098d4`

## pseudocode

```c
char **__fastcall uus::DllForwarder::`scalar deleting destructor'(char **this, char a2)
{
  HMODULE v4; // rcx
  char *v5; // rcx

  *this = (char *)&uus::DllForwarder::`vftable';
  std::wstring::~wstring(this + 7);
  std::wstring::~wstring(this + 3);
  v4 = (HMODULE)this[2];
  if ( v4 )
    FreeLibrary(v4);
  v5 = this[1];
  if ( v5 )
    (**(void (__fastcall ***)(char *, __int64))v5)(v5, 1);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800098a0  mov     [rsp+arg_0], rbx
0x1800098a5  push    rdi
0x1800098a6  sub     rsp, 20h
0x1800098aa  lea     rax, ??_7DllForwarder@uus@@6B@; const uus::DllForwarder::`vftable'
0x1800098b1  mov     rbx, rcx
0x1800098b4  mov     [rcx], rax
0x1800098b7  mov     edi, edx
0x1800098b9  add     rcx, 38h ; '8'
0x1800098bd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800098c2  lea     rcx, [rbx+18h]
0x1800098c6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800098cb  mov     rcx, [rbx+10h]; hLibModule
0x1800098cf  test    rcx, rcx
0x1800098d2  jz      short loc_1800098DA
0x1800098d4  call    cs:__imp_FreeLibrary
0x1800098da  mov     rcx, [rbx+8]
0x1800098de  test    rcx, rcx
0x1800098e1  jz      short loc_1800098F3
0x1800098e3  mov     rax, [rcx]
0x1800098e6  mov     edx, 1
0x1800098eb  mov     rax, [rax]
0x1800098ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098f3  test    dil, 1
0x1800098f7  jz      short loc_180009906
0x1800098f9  mov     edx, 58h ; 'X'; unsigned __int64
0x1800098fe  mov     rcx, rbx; void *
0x180009901  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009906  mov     rax, rbx
0x180009909  mov     rbx, [rsp+28h+arg_0]
0x18000990e  add     rsp, 20h
0x180009912  pop     rdi
0x180009913  retn
```
