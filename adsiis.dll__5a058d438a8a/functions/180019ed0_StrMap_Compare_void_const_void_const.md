# StrMap::Compare(void const *,void const *)

- ea: `0x180019ed0`
- end: `0x180019f0c`
- name: `?Compare@StrMap@@KAHPEBX0@Z`
- size: `60`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180019ed0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180019eff`

## pseudocode

```c
int __fastcall StrMap::Compare(const wchar_t **a1, const wchar_t **a2)
{
  const wchar_t *v3; // rcx
  const wchar_t *v4; // rdx

  if ( a1 )
  {
    if ( !a2 )
      return 1;
    v3 = *a1;
    v4 = *a2;
    if ( !v3 )
      return -(v4 != 0);
    if ( v4 )
      return _wcsicmp(v3, v4);
    else
      return 1;
  }
  else if ( a2 )
  {
    return -1;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180019ed0  test    rcx, rcx
0x180019ed3  jnz     short loc_180019EE3
0x180019ed5  test    rdx, rdx
0x180019ed8  jz      short loc_180019EDF
0x180019eda  or      eax, 0FFFFFFFFh
0x180019edd  jmp     short locret_180019F0B
0x180019edf  xor     eax, eax
0x180019ee1  jmp     short locret_180019F0B
0x180019ee3  test    rdx, rdx
0x180019ee6  jz      short loc_180019F06
0x180019ee8  mov     rcx, [rcx]
0x180019eeb  mov     rdx, [rdx]
0x180019eee  test    rcx, rcx
0x180019ef1  jnz     short loc_180019EFA
0x180019ef3  neg     rdx
0x180019ef6  sbb     eax, eax
0x180019ef8  jmp     short locret_180019F0B
0x180019efa  test    rdx, rdx
0x180019efd  jz      short loc_180019F06
0x180019eff  jmp     cs:__imp__wcsicmp
0x180019f06  mov     eax, 1
0x180019f0b  retn
```
