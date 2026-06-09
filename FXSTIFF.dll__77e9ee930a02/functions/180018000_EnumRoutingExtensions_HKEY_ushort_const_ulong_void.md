# EnumRoutingExtensions(HKEY__ *,ushort const *,ulong,void *)

- ea: `0x180018000`
- end: `0x18001811b`
- name: `?EnumRoutingExtensions@@YAHPEAUHKEY__@@PEBGKPEAX@Z`
- size: `283`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, unsigned int, void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callees

- `0x18000f128`
- `0x18000f1c8`
- `0x18000f20c`
- `0x18000f550`
- `0x180017098`
- `0x180018000`
- `0x180018270`

## pseudocode

```c
__int64 __fastcall EnumRoutingExtensions(HKEY hKey, unsigned __int16 *a2, unsigned int a3, _QWORD *a4)
{
  __int64 v4; // rdi
  LPVOID v7; // rax
  __int64 v9; // rbp
  const unsigned __int16 *v10; // r9
  const unsigned __int16 *v11; // r9
  BYTE *RegistryStringValue; // rax
  __int64 v13; // r8
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
        if ( *(_WORD *)RegistryStringValue == 64 )
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
                                           hKey,
                                           L"Routing Methods",
                                           v13,
                                           (unsigned int (__fastcall *)(HKEY, WCHAR *, _QWORD, __int64))EnumRoutingMethods,
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
0x180018000  push    rbx
0x180018002  push    rbp
0x180018003  push    rsi
0x180018004  push    rdi
0x180018005  push    r14
0x180018007  sub     rsp, 30h
0x18001800b  mov     edi, r8d
0x18001800e  mov     rbx, r9
0x180018011  mov     r14, rcx
0x180018014  test    rdx, rdx
0x180018017  jnz     short loc_180018052
0x180018019  test    r8d, r8d
0x18001801c  jz      short loc_180018048
0x18001801e  lea     rcx, [rdi+rdi*4]
0x180018022  mov     eax, 0FFFFFFFFh
0x180018027  shl     rcx, 3
0x18001802b  cmp     rcx, rax
0x18001802e  ja      loc_18001810D
0x180018034  mov     ecx, ecx; dwBytes
0x180018036  call    pMemAlloc
0x18001803b  mov     [rbx+10h], rax
0x18001803f  test    rax, rax
0x180018042  jz      loc_18001810D
0x180018048  mov     eax, 1
0x18001804d  jmp     loc_18001810F
0x180018052  test    rbx, rbx
0x180018055  jz      loc_18001810D
0x18001805b  cmp     qword ptr [r9+10h], 0
0x180018060  jz      loc_18001810D
0x180018066  mov     rcx, rdx; unsigned __int16 *
0x180018069  call    StringDup
0x18001806e  mov     rcx, [rbx+10h]
0x180018072  lea     rbp, [rdi+rdi*4]
0x180018076  lea     r8, aImagename; "ImageName"
0x18001807d  mov     edx, 2; dwType
0x180018082  mov     [rcx+rbp*8+10h], rax
0x180018087  mov     rcx, r14; hKey
0x18001808a  call    ?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z; GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)
0x18001808f  mov     rcx, [rbx+10h]
0x180018093  lea     r8, aFriendlyname; "FriendlyName"
0x18001809a  mov     edx, 1; dwType
0x18001809f  mov     [rcx+rbp*8+8], rax
0x1800180a4  mov     rcx, r14; hKey
0x1800180a7  call    ?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z; GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)
0x1800180ac  mov     rdi, rax
0x1800180af  test    rax, rax
0x1800180b2  jz      short loc_1800180D5
0x1800180b4  cmp     word ptr [rax], 40h ; '@'
0x1800180b8  jnz     short loc_1800180D5
0x1800180ba  mov     rcx, rax
0x1800180bd  call    TryLoadIndirectFriendlyName
0x1800180c2  mov     rsi, rax
0x1800180c5  test    rax, rax
0x1800180c8  jz      short loc_1800180D5
0x1800180ca  mov     rcx, rdi; lpMem
0x1800180cd  call    pMemFree
0x1800180d2  mov     rdi, rsi
0x1800180d5  mov     rax, [rbx+10h]
0x1800180d9  lea     r9, ?EnumRoutingMethods@@YAHPEAUHKEY__@@PEBGKPEAX@Z; EnumRoutingMethods(HKEY__ *,ushort const *,ulong,void *)
0x1800180e0  lea     rdx, aRoutingMethods; "Routing Methods"
0x1800180e7  mov     [rax+rbp*8], rdi
0x1800180eb  mov     rax, [rbx+10h]
0x1800180ef  lea     rcx, [rax+rbp*8]
0x1800180f3  mov     [rsp+58h+var_38], rcx
0x1800180f8  mov     rcx, r14
0x1800180fb  call    EnumerateRegistryKeys
0x180018100  mov     rcx, [rbx+10h]
0x180018104  mov     [rcx+rbp*8+18h], eax
0x180018108  jmp     loc_180018048
0x18001810d  xor     eax, eax
0x18001810f  add     rsp, 30h
0x180018113  pop     r14
0x180018115  pop     rdi
0x180018116  pop     rsi
0x180018117  pop     rbp
0x180018118  pop     rbx
0x180018119  retn
```
