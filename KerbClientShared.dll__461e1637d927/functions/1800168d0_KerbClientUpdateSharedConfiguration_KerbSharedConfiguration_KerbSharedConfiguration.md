# KerbClientUpdateSharedConfiguration(_KerbSharedConfiguration *,_KerbSharedConfiguration *)

- ea: `0x1800168d0`
- end: `0x180016944`
- name: `?KerbClientUpdateSharedConfiguration@@YAJPEAU_KerbSharedConfiguration@@0@Z`
- size: `116`
- prototype: `__int64 __fastcall(struct _KerbSharedConfiguration *, struct _KerbSharedConfiguration *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x1800168d0`

## pseudocode

```c
__int64 __fastcall KerbClientUpdateSharedConfiguration(
        struct _KerbSharedConfiguration *a1,
        struct _KerbSharedConfiguration *a2)
{
  int v2; // eax
  unsigned int v3; // ecx
  unsigned int v4; // eax
  bool v5; // cc
  __int128 v6; // xmm0
  __int64 result; // rax

  if ( !a1 || !a2 )
    return 3221225485LL;
  *(_OWORD *)a2 = *(_OWORD *)a1;
  *((_DWORD *)a2 + 4) = *((_DWORD *)a1 + 4);
  if ( GlobalConfig )
  {
    v2 = 512;
    *((_DWORD *)a2 + 4) = 0;
    if ( *(_DWORD *)a2 > 0x200u )
      v2 = *(_DWORD *)a2;
    *(_DWORD *)a2 = v2;
  }
  v3 = *((_DWORD *)a2 + 2);
  v4 = *((_DWORD *)a2 + 1);
  if ( v3 <= *(_DWORD *)a2 )
    v3 = *(_DWORD *)a2;
  v5 = v4 <= *(_DWORD *)a2;
  *((_DWORD *)a2 + 2) = v3;
  if ( v5 )
    v4 = *(_DWORD *)a2;
  if ( v4 < v3 )
    v3 = v4;
  *((_DWORD *)a2 + 1) = v3;
  if ( !v3 )
    *((_DWORD *)a2 + 1) = 1;
  v6 = *(_OWORD *)a2;
  dword_180033518 = *((_DWORD *)a2 + 4);
  result = 0;
  GlobalSharedConfig = v6;
  return result;
}

```

## disassembly

```asm
0x1800168d0  test    rcx, rcx
0x1800168d3  jz      short loc_18001693E
0x1800168d5  test    rdx, rdx
0x1800168d8  jz      short loc_18001693E
0x1800168da  movups  xmm0, xmmword ptr [rcx]
0x1800168dd  movups  xmmword ptr [rdx], xmm0
0x1800168e0  mov     eax, [rcx+10h]
0x1800168e3  mov     [rdx+10h], eax
0x1800168e6  cmp     cs:?GlobalConfig@@3U_KerbClientConfiguration@@A, 0; _KerbClientConfiguration GlobalConfig
0x1800168ed  jz      short loc_180016902
0x1800168ef  mov     eax, 200h
0x1800168f4  mov     dword ptr [rdx+10h], 0
0x1800168fb  cmp     [rdx], eax
0x1800168fd  cmova   eax, [rdx]
0x180016900  mov     [rdx], eax
0x180016902  mov     ecx, [rdx+8]
0x180016905  cmp     ecx, [rdx]
0x180016907  mov     eax, [rdx+4]
0x18001690a  cmovbe  ecx, [rdx]
0x18001690d  cmp     eax, [rdx]
0x18001690f  mov     [rdx+8], ecx
0x180016912  cmovbe  eax, [rdx]
0x180016915  cmp     eax, ecx
0x180016917  cmovb   ecx, eax
0x18001691a  mov     [rdx+4], ecx
0x18001691d  test    ecx, ecx
0x18001691f  jnz     short loc_180016928
0x180016921  mov     dword ptr [rdx+4], 1
0x180016928  mov     eax, [rdx+10h]
0x18001692b  movups  xmm0, xmmword ptr [rdx]
0x18001692e  mov     cs:dword_180033518, eax
0x180016934  xor     eax, eax
0x180016936  movups  cs:?GlobalSharedConfig@@3U_KerbSharedConfiguration@@A, xmm0; _KerbSharedConfiguration GlobalSharedConfig
0x18001693d  retn
0x18001693e  mov     eax, 0C000000Dh
0x180016943  retn
```
