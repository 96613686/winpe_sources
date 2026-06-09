# WinSqmAddToStream(_GUID *,ulong,ulong,_SQM_STREAM_ENTRY *)

- ea: `0x180006d68`
- end: `0x180006e16`
- name: `?WinSqmAddToStream@@YAXPEAU_GUID@@KKPEAU_SQM_STREAM_ENTRY@@@Z`
- size: `174`
- prototype: `void __fastcall(struct _GUID *, unsigned int, unsigned int, struct _SQM_STREAM_ENTRY *)`
- caller_count: `7`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800031a4`
- `0x1800031d8`
- `0x180003218`
- `0x180003284`
- `0x1800032d0`
- `0x180005534`
- `0x18000558c`

## callees

- `0x180006d68`
- `0x180006fc4`
- `0x180008010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180006dcb`
- `KERNEL32!GetProcAddress` at `0x180006dcb`
- `KERNEL32!FreeLibrary` at `0x180006db7`
- `KERNEL32!FreeLibrary` at `0x180006db7`

## pseudocode

```c
void __fastcall WinSqmAddToStream(struct _GUID *a1, unsigned int a2, unsigned int a3, struct _SQM_STREAM_ENTRY *a4)
{
  void (__fastcall *v7)(_QWORD, _QWORD, _QWORD, struct _SQM_STREAM_ENTRY *); // rax
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax

  if ( dword_18000D1C0 )
  {
    v7 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, struct _SQM_STREAM_ENTRY *))qword_18000D2C0;
    if ( !qword_18000D2C0 )
    {
      if ( !hModule )
      {
        LibraryW = IsolationAwareLoadLibraryW();
        if ( !LibraryW )
        {
LABEL_8:
          dword_18000D1C0 = 0;
          return;
        }
        if ( _InterlockedCompareExchange64((volatile signed __int64 *)&hModule, (signed __int64)LibraryW, 0) )
          FreeLibrary(LibraryW);
      }
      ProcAddress = GetProcAddress(hModule, "WinSqmAddToStream");
      if ( !ProcAddress )
        goto LABEL_8;
      _InterlockedCompareExchange64(&qword_18000D2C0, (signed __int64)ProcAddress, 0);
      v7 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, struct _SQM_STREAM_ENTRY *))qword_18000D2C0;
    }
    v7(0, a2, a3, a4);
  }
}

```

## disassembly

```asm
0x180006d68  mov     [rsp+arg_0], rbx
0x180006d6d  mov     [rsp+arg_8], rsi
0x180006d72  push    rdi
0x180006d73  sub     rsp, 30h
0x180006d77  cmp     cs:dword_18000D1C0, 0
0x180006d7e  mov     rbx, r9
0x180006d81  mov     edi, r8d
0x180006d84  mov     esi, edx
0x180006d86  jz      short loc_180006E06
0x180006d88  mov     rax, cs:qword_18000D2C0
0x180006d8f  test    rax, rax
0x180006d92  jnz     short loc_180006DF7
0x180006d94  cmp     cs:hModule, rax
0x180006d9b  jnz     short loc_180006DBD
0x180006d9d  call    IsolationAwareLoadLibraryW
0x180006da2  mov     rcx, rax; hLibModule
0x180006da5  test    rax, rax
0x180006da8  jz      short loc_180006DD9
0x180006daa  xor     eax, eax
0x180006dac  lock cmpxchg cs:hModule, rcx
0x180006db5  jz      short loc_180006DBD
0x180006db7  call    cs:__imp_FreeLibrary
0x180006dbd  mov     rcx, cs:hModule; hModule
0x180006dc4  lea     rdx, aWinsqmaddtostr; "WinSqmAddToStream"
0x180006dcb  call    cs:__imp_GetProcAddress
0x180006dd1  mov     rcx, rax
0x180006dd4  test    rax, rax
0x180006dd7  jnz     short loc_180006DE5
0x180006dd9  mov     cs:dword_18000D1C0, 0
0x180006de3  jmp     short loc_180006E06
0x180006de5  xor     eax, eax
0x180006de7  lock cmpxchg cs:qword_18000D2C0, rcx
0x180006df0  mov     rax, cs:qword_18000D2C0
0x180006df7  mov     r9, rbx
0x180006dfa  mov     r8d, edi
0x180006dfd  mov     edx, esi
0x180006dff  xor     ecx, ecx
0x180006e01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e06  mov     rbx, [rsp+38h+arg_0]
0x180006e0b  mov     rsi, [rsp+38h+arg_8]
0x180006e10  add     rsp, 30h
0x180006e14  pop     rdi
0x180006e15  retn
```
