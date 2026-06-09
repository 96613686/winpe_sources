# CMsMpSimpleConfig::DeleteValue(ushort *,ushort *)

- ea: `0x180004c90`
- end: `0x180004cc3`
- name: `?DeleteValue@CMsMpSimpleConfig@@UEAAJPEAG0@Z`
- size: `51`
- prototype: `__int64 __fastcall(CMsMpSimpleConfig *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180004c90`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall CMsMpSimpleConfig::DeleteValue(CMsMpSimpleConfig *this, unsigned __int16 *a2, unsigned __int16 *a3)
{
  int v3; // eax
  unsigned int v4; // ecx

  if ( !a2 || !a3 )
    return 2147500035LL;
  v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 24LL))(*((_QWORD *)this + 2));
  v4 = 0;
  if ( v3 < 0 )
    return (unsigned int)v3;
  return v4;
}

```

## disassembly

```asm
0x180004c90  sub     rsp, 28h
0x180004c94  test    rdx, rdx
0x180004c97  jz      short loc_180004CB9
0x180004c99  test    r8, r8
0x180004c9c  jz      short loc_180004CB9
0x180004c9e  mov     rcx, [rcx+10h]
0x180004ca2  mov     rax, [rcx]
0x180004ca5  mov     rax, [rax+18h]
0x180004ca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cae  xor     ecx, ecx
0x180004cb0  test    eax, eax
0x180004cb2  cmovs   ecx, eax
0x180004cb5  mov     eax, ecx
0x180004cb7  jmp     short loc_180004CBE
0x180004cb9  mov     eax, 80004003h
0x180004cbe  add     rsp, 28h
0x180004cc2  retn
```
