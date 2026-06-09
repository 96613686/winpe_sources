# EnumRoutingExtensions(HKEY__ *,ushort const *,ulong,void *)

- ea: `0x180017280`
- end: `0x18001739a`
- name: `?EnumRoutingExtensions@@YAHPEAUHKEY__@@PEBGKPEAX@Z`
- size: `282`
- prototype: `__int64 __fastcall(HKEY hKey, unsigned __int16 *, unsigned int, _QWORD *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callees

- `0x18000ea18`
- `0x18000eac0`
- `0x18000eafc`
- `0x18000ee14`
- `0x18001639c`
- `0x180017280`
- `0x1800174e0`

## pseudocode

```c
__int64 __fastcall EnumRoutingExtensions(HKEY hKey, unsigned __int16 *a2, unsigned int a3, _QWORD *a4)
{
  __int64 v4; // rdi
  LPVOID v7; // rax
  __int64 v9; // rbp
  const unsigned __int16 *v10; // r9
  const unsigned __int16 *v11; // r9
  unsigned __int16 *RegistryStringValue; // rax
  int v13; // r8d
  void *v14; // rdi
  __int64 IndirectFriendlyName; // rsi
  unsigned int *v16; // [rsp+20h] [rbp-38h]
  unsigned int *v17; // [rsp+20h] [rbp-38h]

  v4 = a3;
  if ( a2 )
  {
    if ( a4 && a4[2] )
    {
      v9 = 5LL * a3;
      *(_QWORD *)(a4[2] + 40LL * a3 + 16) = StringDup(a2);
      *(_QWORD *)(a4[2] + 40 * v4 + 8) = GetRegistryStringValue(hKey, 2u, L"ImageName", v10, v16);
      RegistryStringValue = GetRegistryStringValue(hKey, 1u, L"FriendlyName", v11, v17);
      v14 = RegistryStringValue;
      if ( RegistryStringValue )
      {
        if ( *RegistryStringValue == 64 )
        {
          IndirectFriendlyName = TryLoadIndirectFriendlyName(RegistryStringValue);
          if ( IndirectFriendlyName )
          {
            pMemFree(v14);
            v14 = (void *)IndirectFriendlyName;
          }
        }
      }
      *(_QWORD *)(a4[2] + 8 * v9) = v14;
      *(_DWORD *)(a4[2] + 8 * v9 + 24) = EnumerateRegistryKeys(
                                           (_DWORD)hKey,
                                           (unsigned int)L"Routing Methods",
                                           v13,
                                           (unsigned int)EnumRoutingMethods,
                                           a4[2] + 8 * v9);
      return 1;
    }
  }
  else
  {
    if ( !a3 )
      return 1;
    if ( 40 * (unsigned __int64)a3 <= 0xFFFFFFFF )
    {
      v7 = pMemAlloc(40 * a3);
      a4[2] = v7;
      if ( v7 )
        return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180017280  push    rbx
0x180017282  push    rbp
0x180017283  push    rsi
0x180017284  push    rdi
0x180017285  push    r14
0x180017287  sub     rsp, 30h
0x18001728b  mov     edi, r8d
0x18001728e  mov     rbx, r9
0x180017291  mov     r14, rcx
0x180017294  test    rdx, rdx
0x180017297  jnz     short loc_1800172D2
0x180017299  test    r8d, r8d
0x18001729c  jz      short loc_1800172C8
0x18001729e  lea     rcx, [rdi+rdi*4]
0x1800172a2  mov     eax, 0FFFFFFFFh
0x1800172a7  shl     rcx, 3
0x1800172ab  cmp     rcx, rax
0x1800172ae  ja      loc_18001738D
0x1800172b4  mov     ecx, ecx; dwBytes
0x1800172b6  call    pMemAlloc
0x1800172bb  mov     [rbx+10h], rax
0x1800172bf  test    rax, rax
0x1800172c2  jz      loc_18001738D
0x1800172c8  mov     eax, 1
0x1800172cd  jmp     loc_18001738F
0x1800172d2  test    rbx, rbx
0x1800172d5  jz      loc_18001738D
0x1800172db  cmp     qword ptr [r9+10h], 0
0x1800172e0  jz      loc_18001738D
0x1800172e6  mov     rcx, rdx; unsigned __int16 *
0x1800172e9  call    StringDup
0x1800172ee  mov     rcx, [rbx+10h]
0x1800172f2  lea     rbp, [rdi+rdi*4]
0x1800172f6  lea     r8, aImagename; "ImageName"
0x1800172fd  mov     edx, 2; dwType
0x180017302  mov     [rcx+rbp*8+10h], rax
0x180017307  mov     rcx, r14; hKey
0x18001730a  call    ?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z; GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)
0x18001730f  mov     rcx, [rbx+10h]
0x180017313  lea     r8, aFriendlyname; "FriendlyName"
0x18001731a  mov     edx, 1; dwType
0x18001731f  mov     [rcx+rbp*8+8], rax
0x180017324  mov     rcx, r14; hKey
0x180017327  call    ?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z; GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)
0x18001732c  mov     rdi, rax
0x18001732f  test    rax, rax
0x180017332  jz      short loc_180017355
0x180017334  cmp     word ptr [rax], 40h ; '@'
0x180017338  jnz     short loc_180017355
0x18001733a  mov     rcx, rax
0x18001733d  call    TryLoadIndirectFriendlyName
0x180017342  mov     rsi, rax
0x180017345  test    rax, rax
0x180017348  jz      short loc_180017355
0x18001734a  mov     rcx, rdi; lpMem
0x18001734d  call    pMemFree
0x180017352  mov     rdi, rsi
0x180017355  mov     rax, [rbx+10h]
0x180017359  lea     r9, ?EnumRoutingMethods@@YAHPEAUHKEY__@@PEBGKPEAX@Z; EnumRoutingMethods(HKEY__ *,ushort const *,ulong,void *)
0x180017360  lea     rdx, aRoutingMethods; "Routing Methods"
0x180017367  mov     [rax+rbp*8], rdi
0x18001736b  mov     rax, [rbx+10h]
0x18001736f  lea     rcx, [rax+rbp*8]
0x180017373  mov     [rsp+58h+var_38], rcx
0x180017378  mov     rcx, r14
0x18001737b  call    EnumerateRegistryKeys
0x180017380  mov     rcx, [rbx+10h]
0x180017384  mov     [rcx+rbp*8+18h], eax
0x180017388  jmp     loc_1800172C8
0x18001738d  xor     eax, eax
0x18001738f  add     rsp, 30h
0x180017393  pop     r14
0x180017395  pop     rdi
0x180017396  pop     rsi
0x180017397  pop     rbp
0x180017398  pop     rbx
0x180017399  retn
```
