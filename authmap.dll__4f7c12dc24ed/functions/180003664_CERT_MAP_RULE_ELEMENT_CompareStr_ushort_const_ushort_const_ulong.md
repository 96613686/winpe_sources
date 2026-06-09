# CERT_MAP_RULE_ELEMENT::CompareStr(ushort const *,ushort const *,ulong)

- ea: `0x180003664`
- end: `0x1800036a9`
- name: `?CompareStr@CERT_MAP_RULE_ELEMENT@@QEAAHPEBG0K@Z`
- size: `69`
- prototype: `_BOOL8 __fastcall(CERT_MAP_RULE_ELEMENT *this, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800039e4`

## callees

- `0x180003664`
- `0x180006daa`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180003695`
- `msvcrt!_wcsnicmp` at `0x180003695`

## pseudocode

```c
_BOOL8 __fastcall CERT_MAP_RULE_ELEMENT::CompareStr(
        CERT_MAP_RULE_ELEMENT *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4)
{
  int v5; // eax

  if ( !a4 )
    return 1;
  if ( *((_DWORD *)this + 55) )
    v5 = wcsncmp_0(a2, a3, a4);
  else
    v5 = _wcsnicmp(a2, a3, a4);
  return v5 == 0;
}

```

## disassembly

```asm
0x180003664  sub     rsp, 28h
0x180003668  mov     rax, r8
0x18000366b  mov     r10, rdx
0x18000366e  test    r9d, r9d
0x180003671  jnz     short loc_180003679
0x180003673  lea     eax, [r9+1]
0x180003677  jmp     short loc_1800036A4
0x180003679  cmp     dword ptr [rcx+0DCh], 0
0x180003680  mov     rdx, rax; String2
0x180003683  mov     rcx, r10; String1
0x180003686  jz      short loc_180003692
0x180003688  mov     r8d, r9d; MaxCount
0x18000368b  call    wcsncmp_0
0x180003690  jmp     short loc_18000369B
0x180003692  mov     r8d, r9d; MaxCount
0x180003695  call    cs:__imp__wcsnicmp
0x18000369b  xor     ecx, ecx
0x18000369d  test    eax, eax
0x18000369f  setz    cl
0x1800036a2  mov     eax, ecx
0x1800036a4  add     rsp, 28h
0x1800036a8  retn
```
