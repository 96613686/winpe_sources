# ATL::CComObject<Windows::Globalization::Spelling::CHostSpellCheckProvider>::`scalar deleting destructor'(uint)

- ea: `0x14000fd30`
- end: `0x14000fd9d`
- name: `??_G?$CComObject@VCHostSpellCheckProvider@Spelling@Globalization@Windows@@@ATL@@UEAAPEAXI@Z`
- size: `109`
- prototype: `Windows::Globalization::Spelling::CHostSpellCheckProvider *__fastcall(Windows::Globalization::Spelling::CHostSpellCheckProvider *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x14000fcb0`
- `0x14000fd30`
- `0x140013010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000fd89`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000fd89`

## pseudocode

```c
Windows::Globalization::Spelling::CHostSpellCheckProvider *__fastcall ATL::CComObject<Windows::Globalization::Spelling::CHostSpellCheckProvider>::`scalar deleting destructor'(
        Windows::Globalization::Spelling::CHostSpellCheckProvider *this,
        char a2)
{
  *((_DWORD *)this + 6) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<Windows::Globalization::Spelling::CHostSpellCheckProvider>::`vftable'{for `ISpellCheckProvider'};
  *((_QWORD *)this + 1) = &ATL::CComObject<Windows::Globalization::Spelling::CHostSpellCheckProvider>::`vftable'{for `IComprehensiveSpellCheckProvider'};
  *((_QWORD *)this + 2) = &ATL::CComObject<Windows::Globalization::Spelling::CHostSpellCheckProvider>::`vftable'{for `IFileWordlistInitializer'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  Windows::Globalization::Spelling::CHostSpellCheckProvider::~CHostSpellCheckProvider(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x14000fd30  mov     [rsp+arg_0], rbx
0x14000fd35  push    rdi
0x14000fd36  sub     rsp, 20h
0x14000fd3a  mov     dword ptr [rcx+18h], 0C0000001h
0x14000fd41  lea     rax, ??_7?$CComObject@VCHostSpellCheckProvider@Spelling@Globalization@Windows@@@ATL@@6BISpellCheckProvider@@@; const ATL::CComObject<Windows::Globalization::Spelling::CHostSpellCheckProvider>::`vftable'{for `ISpellCheckProvider'}
0x14000fd48  mov     [rcx], rax
0x14000fd4b  mov     rdi, rcx
0x14000fd4e  lea     rax, ??_7?$CComObject@VCHostSpellCheckProvider@Spelling@Globalization@Windows@@@ATL@@6BIComprehensiveSpellCheckProvider@@@; const ATL::CComObject<Windows::Globalization::Spelling::CHostSpellCheckProvider>::`vftable'{for `IComprehensiveSpellCheckProvider'}
0x14000fd55  mov     ebx, edx
0x14000fd57  mov     [rcx+8], rax
0x14000fd5b  lea     rax, ??_7?$CComObject@VCHostSpellCheckProvider@Spelling@Globalization@Windows@@@ATL@@6BIFileWordlistInitializer@@@; const ATL::CComObject<Windows::Globalization::Spelling::CHostSpellCheckProvider>::`vftable'{for `IFileWordlistInitializer'}
0x14000fd62  mov     [rcx+10h], rax
0x14000fd66  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x14000fd6d  mov     rax, [rcx]
0x14000fd70  mov     rax, [rax+10h]
0x14000fd74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fd79  mov     rcx, rdi; this
0x14000fd7c  call    ??1CHostSpellCheckProvider@Spelling@Globalization@Windows@@QEAA@XZ; Windows::Globalization::Spelling::CHostSpellCheckProvider::~CHostSpellCheckProvider(void)
0x14000fd81  test    bl, 1
0x14000fd84  jz      short loc_14000FD8F
0x14000fd86  mov     rcx, rdi
0x14000fd89  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000fd8f  mov     rbx, [rsp+28h+arg_0]
0x14000fd94  mov     rax, rdi
0x14000fd97  add     rsp, 20h
0x14000fd9b  pop     rdi
0x14000fd9c  retn
```
