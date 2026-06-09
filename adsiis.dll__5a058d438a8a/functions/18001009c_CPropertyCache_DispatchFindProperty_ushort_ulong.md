# CPropertyCache::DispatchFindProperty(ushort *,ulong *)

- ea: `0x18001009c`
- end: `0x1800100fe`
- name: `?DispatchFindProperty@CPropertyCache@@IEAAJPEAGPEAK@Z`
- size: `98`
- prototype: `int(CPropertyCache *__hidden this, unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18000ffe8`
- `0x1800102e0`

## callees

- `0x18001009c`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800100cf`
- `msvcrt!_wcsicmp` at `0x1800100cf`

## pseudocode

```c
__int64 __fastcall CPropertyCache::DispatchFindProperty(CPropertyCache *this, unsigned __int16 *a2, unsigned int *a3)
{
  unsigned int i; // ebx

  if ( !a3 || !a2 )
    return 2147504136LL;
  for ( i = 0; i < *((_DWORD *)this + 25); ++i )
  {
    if ( !_wcsicmp((const wchar_t *)(*((_QWORD *)this + 11) + 520LL * i), a2) )
    {
      *a3 = i;
      return 0;
    }
  }
  *a3 = -1;
  return 2147504141LL;
}

```

## disassembly

```asm
0x18001009c  push    rbx
0x18001009e  push    rbp
0x18001009f  push    rsi
0x1800100a0  push    rdi
0x1800100a1  sub     rsp, 28h
0x1800100a5  mov     rdi, r8
0x1800100a8  mov     rsi, rdx
0x1800100ab  mov     rbp, rcx
0x1800100ae  test    r8, r8
0x1800100b1  jz      short loc_1800100F0
0x1800100b3  test    rdx, rdx
0x1800100b6  jz      short loc_1800100F0
0x1800100b8  xor     ebx, ebx
0x1800100ba  cmp     ebx, [rbp+64h]
0x1800100bd  jnb     short loc_1800100E3
0x1800100bf  mov     eax, ebx
0x1800100c1  mov     rdx, rsi; String2
0x1800100c4  imul    rcx, rax, 208h
0x1800100cb  add     rcx, [rbp+58h]; String1
0x1800100cf  call    cs:__imp__wcsicmp
0x1800100d5  test    eax, eax
0x1800100d7  jz      short loc_1800100DD
0x1800100d9  inc     ebx
0x1800100db  jmp     short loc_1800100BA
0x1800100dd  mov     [rdi], ebx
0x1800100df  xor     eax, eax
0x1800100e1  jmp     short loc_1800100F5
0x1800100e3  mov     dword ptr [rdi], 0FFFFFFFFh
0x1800100e9  mov     eax, 8000500Dh
0x1800100ee  jmp     short loc_1800100F5
0x1800100f0  mov     eax, 80005008h
0x1800100f5  add     rsp, 28h
0x1800100f9  pop     rdi
0x1800100fa  pop     rsi
0x1800100fb  pop     rbp
0x1800100fc  pop     rbx
0x1800100fd  retn
```
