# CW32System::ImmSetCompositionStringW(ulong,ulong,void *,ulong,void *,ulong)

- ea: `0x18008ecc8`
- end: `0x18008ed2c`
- name: `?ImmSetCompositionStringW@CW32System@@SAHKKPEAXK0K@Z`
- size: `100`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, void *, unsigned int, void *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180051f20`

## callees

- `0x18008ecc8`
- `0x1800905e8`
- `0x180092010`

## string_xrefs

- `0x18008ece7`: `ImmSetCompositionStringW`

## pseudocode

```c
__int64 __fastcall CW32System::ImmSetCompositionStringW(unsigned int a1, unsigned int a2, void *a3, unsigned int a4)
{
  __int64 (__fastcall *v4)(_QWORD, _QWORD, void *, _QWORD, _QWORD, _DWORD); // rax

  v4 = (__int64 (__fastcall *)(_QWORD, _QWORD, void *, _QWORD, _QWORD, _DWORD))qword_1800A4188;
  if ( !qword_1800A4188 )
  {
    SetIMEProcAddr(&qword_1800A4188, 0, "ImmSetCompositionStringW");
    v4 = (__int64 (__fastcall *)(_QWORD, _QWORD, void *, _QWORD, _QWORD, _DWORD))qword_1800A4188;
  }
  return v4(a1, a2, a3, a4, 0, 0);
}

```

## disassembly

```asm
0x18008ecc8  push    rbx
0x18008ecca  push    rbp
0x18008eccb  push    rsi
0x18008eccc  push    rdi
0x18008eccd  sub     rsp, 48h
0x18008ecd1  mov     rax, cs:qword_1800A4188
0x18008ecd8  mov     ebx, r9d
0x18008ecdb  mov     rdi, r8
0x18008ecde  mov     esi, edx
0x18008ece0  mov     ebp, ecx
0x18008ece2  test    rax, rax
0x18008ece5  jnz     short loc_18008ED03
0x18008ece7  lea     r8, aImmsetcomposit; "ImmSetCompositionStringW"
0x18008ecee  xor     edx, edx
0x18008ecf0  lea     rcx, qword_1800A4188
0x18008ecf7  call    SetIMEProcAddr
0x18008ecfc  mov     rax, cs:qword_1800A4188
0x18008ed03  mov     [rsp+68h+var_40], 0
0x18008ed0b  mov     r9d, ebx
0x18008ed0e  mov     r8, rdi
0x18008ed11  mov     [rsp+68h+var_48], 0
0x18008ed1a  mov     edx, esi
0x18008ed1c  mov     ecx, ebp
0x18008ed1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ed23  add     rsp, 48h
0x18008ed27  pop     rdi
0x18008ed28  pop     rsi
0x18008ed29  pop     rbp
0x18008ed2a  pop     rbx
0x18008ed2b  retn
```
