# _GetDllForwarder_::_2_::_dynamic_atexit_destructor_for__instance__

- ea: `0x18000c710`
- end: `0x18000c76d`
- name: `_GetDllForwarder_::_2_::_dynamic_atexit_destructor_for__instance__`
- size: `93`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008f20`
- `0x18000c710`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000c746`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000c746`

## pseudocode

```c
void __fastcall GetDllForwarder_::_2_::_dynamic_atexit_destructor_for__instance__()
{
  off_180013090 = &uus::DllForwarder::`vftable';
  std::wstring::~wstring((char **)&qword_1800130C8);
  std::wstring::~wstring((char **)&lpLibFileName);
  if ( hLibModule )
    FreeLibrary(hLibModule);
  if ( qword_180013098 )
    (**(void (__fastcall ***)(__int64, __int64))qword_180013098)(qword_180013098, 1);
}

```

## disassembly

```asm
0x18000c710  sub     rsp, 28h
0x18000c714  lea     rax, ??_7DllForwarder@uus@@6B@; const uus::DllForwarder::`vftable'
0x18000c71b  lea     rcx, qword_1800130C8
0x18000c722  mov     cs:off_180013090, rax
0x18000c729  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000c72e  lea     rcx, lpLibFileName
0x18000c735  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000c73a  mov     rcx, cs:hLibModule; hLibModule
0x18000c741  test    rcx, rcx
0x18000c744  jz      short loc_18000C74C
0x18000c746  call    cs:__imp_FreeLibrary
0x18000c74c  mov     rcx, cs:qword_180013098
0x18000c753  test    rcx, rcx
0x18000c756  jz      short loc_18000C768
0x18000c758  mov     rax, [rcx]
0x18000c75b  mov     edx, 1
0x18000c760  mov     rax, [rax]
0x18000c763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c768  add     rsp, 28h
0x18000c76c  retn
```
