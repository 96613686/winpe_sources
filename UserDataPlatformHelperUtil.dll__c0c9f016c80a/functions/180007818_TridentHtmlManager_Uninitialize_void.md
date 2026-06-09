# TridentHtmlManager::Uninitialize(void)

- ea: `0x180007818`
- end: `0x1800078aa`
- name: `?Uninitialize@TridentHtmlManager@@QEAAXXZ`
- size: `146`
- prototype: `void __fastcall(TridentHtmlManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800075f4`
- `0x180007a20`

## callees

- `0x180007818`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007829`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007829`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800078a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007863`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007863`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180007881`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180007881`

## pseudocode

```c
void __fastcall TridentHtmlManager::Uninitialize(TridentHtmlManager *this)
{
  void (*ProcAddress)(void); // rax

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( *(_BYTE *)this )
  {
    if ( _InterlockedExchangeAdd(&dword_180011934, 0xFFFFFFFF) == 1 && hLibModule )
    {
      ProcAddress = (void (*)(void))qword_180011950;
      if ( qword_180011950
        || (ProcAddress = (void (*)(void))GetProcAddress(hLibModule, "UninitializeLocalHtmlEngine"),
            (qword_180011950 = (__int64)ProcAddress) != 0) )
      {
        ProcAddress();
      }
      FreeLibrary(hLibModule);
      hLibModule = 0;
    }
    *(_BYTE *)this = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x180007818  mov     [rsp+arg_0], rbx
0x18000781d  push    rdi
0x18000781e  sub     rsp, 20h
0x180007822  mov     rbx, rcx
0x180007825  add     rcx, 8; lpCriticalSection
0x180007829  call    cs:__imp_EnterCriticalSection
0x18000782f  cmp     byte ptr [rbx], 0
0x180007832  jz      short loc_180007895
0x180007834  or      eax, 0FFFFFFFFh
0x180007837  lock xadd cs:dword_180011934, eax
0x18000783f  cmp     eax, 1
0x180007842  jnz     short loc_180007892
0x180007844  mov     rcx, cs:hLibModule; hModule
0x18000784b  test    rcx, rcx
0x18000784e  jz      short loc_180007892
0x180007850  mov     rax, cs:qword_180011950
0x180007857  test    rax, rax
0x18000785a  jnz     short loc_180007875
0x18000785c  lea     rdx, aUninitializelo; "UninitializeLocalHtmlEngine"
0x180007863  call    cs:__imp_GetProcAddress
0x180007869  mov     cs:qword_180011950, rax
0x180007870  test    rax, rax
0x180007873  jz      short loc_18000787A
0x180007875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000787a  mov     rcx, cs:hLibModule; hLibModule
0x180007881  call    cs:__imp_FreeLibrary
0x180007887  mov     cs:hLibModule, 0
0x180007892  mov     byte ptr [rbx], 0
0x180007895  lea     rcx, [rbx+8]
0x180007899  mov     rbx, [rsp+28h+arg_0]
0x18000789e  add     rsp, 20h
0x1800078a2  pop     rdi
0x1800078a3  jmp     cs:__imp_LeaveCriticalSection
```
