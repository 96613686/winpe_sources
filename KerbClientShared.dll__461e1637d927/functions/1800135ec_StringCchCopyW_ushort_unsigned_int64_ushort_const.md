# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1800135ec`
- end: `0x18001361b`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `47`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180010a54`
- `0x180013ae8`

## callees

- `0x1800135ec`
- `0x180013670`
- `0x180013764`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, __int64 a2, const unsigned __int16 *a3)
{
  size_t v3; // rdx
  wchar_t *v4; // rcx
  size_t *v5; // r8
  HRESULT v6; // r9d
  size_t v8; // [rsp+20h] [rbp-18h]

  v6 = StringValidateDestW(a1, 0x104u, (const size_t)a3);
  if ( v6 < 0 )
    *v4 = 0;
  else
    return (unsigned int)StringCopyWorkerW(v4, v3, v5, (STRSAFE_PCNZWCH)v5, v8);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800135ec  sub     rsp, 38h
0x1800135f0  mov     edx, 104h; cchDest
0x1800135f5  call    StringValidateDestW
0x1800135fa  mov     r9d, eax
0x1800135fd  test    eax, eax
0x1800135ff  js      short loc_18001360E
0x180013601  mov     r9, r8; pszSrc
0x180013604  call    StringCopyWorkerW
0x180013609  mov     r9d, eax
0x18001360c  jmp     short loc_180013613
0x18001360e  xor     eax, eax
0x180013610  mov     [rcx], ax
0x180013613  mov     eax, r9d
0x180013616  add     rsp, 38h
0x18001361a  retn
```
