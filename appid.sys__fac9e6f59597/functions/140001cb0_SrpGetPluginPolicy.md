# SrpGetPluginPolicy

- ea: `0x140001cb0`
- end: `0x140001d28`
- name: `SrpGetPluginPolicy`
- size: `120`
- prototype: `__int64 __fastcall(__int64, int, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x14002c9c4`

## callees

- `0x140001cb0`
- `0x140001d30`

## pseudocode

```c
__int64 __fastcall SrpGetPluginPolicy(__int64 a1, int a2, __int64 a3, int a4, __int64 a5)
{
  __int64 v7; // rax
  unsigned int v8; // edx
  _QWORD *v9; // r8
  unsigned int i; // r9d
  __int64 v11; // rax

  if ( *(int *)(a1 + 208) >= 0 )
  {
    v7 = *(_QWORD *)(a1 + 216);
    if ( v7 )
    {
      v8 = *(_DWORD *)(v7 + 12);
      v9 = (_QWORD *)(v7 + *(unsigned int *)(v7 + 8));
      for ( i = 0; i < v8; ++i )
      {
        v11 = *v9 - EdpPluginGuid;
        if ( *v9 == EdpPluginGuid )
          v11 = v9[1] - 0x36F6D035FB531A99LL;
        if ( !v11 )
          return SrppGetPluginPolicy(a1, a2, (_DWORD)v9, a4, a5);
        v9 = (_QWORD *)((char *)v9 + 36);
      }
    }
  }
  return 3221226021LL;
}

```

## disassembly

```asm
0x140001cb0  sub     rsp, 38h
0x140001cb4  cmp     dword ptr [rcx+0D0h], 0
0x140001cbb  mov     r10, r9
0x140001cbe  mov     r11, rdx
0x140001cc1  jl      short loc_140001D1D
0x140001cc3  mov     rax, [rcx+0D8h]
0x140001cca  test    rax, rax
0x140001ccd  jz      short loc_140001D1D
0x140001ccf  mov     r8d, [rax+8]
0x140001cd3  mov     edx, [rax+0Ch]
0x140001cd6  add     r8, rax
0x140001cd9  xor     r9d, r9d
0x140001cdc  cmp     r9d, edx
0x140001cdf  jnb     short loc_140001D1D
0x140001ce1  mov     rax, [r8]
0x140001ce4  sub     rax, cs:EdpPluginGuid
0x140001ceb  jnz     short loc_140001CF8
0x140001ced  mov     rax, [r8+8]
0x140001cf1  sub     rax, cs:qword_14000DD38
0x140001cf8  test    rax, rax
0x140001cfb  jz      short loc_140001D06
0x140001cfd  inc     r9d
0x140001d00  add     r8, 24h ; '$'
0x140001d04  jmp     short loc_140001CDC
0x140001d06  mov     rax, [rsp+38h+arg_20]
0x140001d0b  mov     r9, r10
0x140001d0e  mov     rdx, r11
0x140001d11  mov     [rsp+38h+var_18], rax
0x140001d16  call    SrppGetPluginPolicy
0x140001d1b  jmp     short loc_140001D22
0x140001d1d  mov     eax, 0C0000225h
0x140001d22  add     rsp, 38h
0x140001d26  retn
```
