# OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)

- ea: `0x1800617f0`
- end: `0x1800618c9`
- name: `?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z`
- size: `217`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18005f930`
- `0x180064f90`

## callees

- `0x1800617f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180061836`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180061836`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006187c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006187c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800618aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800618aa`

## pseudocode

```c
__int64 __fastcall OmaDmRegistrySetDWORD(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3, int a4)
{
  unsigned int v6; // ebx
  LSTATUS v7; // eax
  LSTATUS v8; // eax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF
  int Data; // [rsp+58h] [rbp+20h] BYREF

  Data = a4;
  hKey = 0;
  if ( !a1 )
  {
    v6 = -2147024809;
    goto LABEL_13;
  }
  if ( !a2 )
  {
    hKey = a1;
LABEL_9:
    v6 = 0;
    v8 = RegSetValueExW(a1, a3, 0, 4u, (const BYTE *)&Data, 4u);
    if ( v8 )
    {
      if ( v8 > 0 )
        v6 = (unsigned __int16)v8 | 0x80070000;
      else
        v6 = v8;
    }
LABEL_13:
    if ( !a2 )
      return v6;
    goto LABEL_14;
  }
  v7 = RegOpenKeyExW(a1, a2, 0, 0x20106u, &hKey);
  v6 = v7;
  if ( !v7 )
  {
    a1 = hKey;
    goto LABEL_9;
  }
  if ( v7 > 0 )
    v6 = (unsigned __int16)v7 | 0x80070000;
LABEL_14:
  if ( hKey )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x1800617f0  mov     rax, rsp
0x1800617f3  mov     [rax+10h], rbx
0x1800617f7  mov     [rax+18h], rsi
0x1800617fb  mov     [rax+20h], r9d
0x1800617ff  push    rdi
0x180061800  sub     rsp, 30h
0x180061804  mov     qword ptr [rax+8], 0
0x18006180c  mov     rsi, r8
0x18006180f  mov     rdi, rdx
0x180061812  test    rcx, rcx
0x180061815  jnz     short loc_18006181E
0x180061817  mov     ebx, 80070057h
0x18006181c  jmp     short loc_18006189B
0x18006181e  test    rdi, rdi
0x180061821  jz      short loc_18006185C
0x180061823  lea     rax, [rsp+38h+hKey]
0x180061828  mov     r9d, 20106h; samDesired
0x18006182e  xor     r8d, r8d; ulOptions
0x180061831  mov     [rsp+38h+phkResult], rax; phkResult
0x180061836  call    cs:__imp_RegOpenKeyExW
0x18006183d  nop     dword ptr [rax+rax+00h]
0x180061842  mov     ebx, eax
0x180061844  test    eax, eax
0x180061846  jz      short loc_180061855
0x180061848  jle     short loc_1800618A0
0x18006184a  movzx   ebx, ax
0x18006184d  or      ebx, 80070000h
0x180061853  jmp     short loc_1800618A0
0x180061855  mov     rcx, [rsp+38h+hKey]; hKey
0x18006185a  jmp     short loc_180061861
0x18006185c  mov     [rsp+38h+hKey], rcx
0x180061861  lea     rax, [rsp+38h+Data]
0x180061866  xor     ebx, ebx
0x180061868  xor     r8d, r8d; Reserved
0x18006186b  mov     rdx, rsi; lpValueName
0x18006186e  lea     r9d, [rbx+4]; dwType
0x180061872  mov     [rsp+38h+cbData], r9d; cbData
0x180061877  mov     [rsp+38h+phkResult], rax; lpData
0x18006187c  call    cs:__imp_RegSetValueExW
0x180061883  nop     dword ptr [rax+rax+00h]
0x180061888  test    eax, eax
0x18006188a  jz      short loc_18006189B
0x18006188c  jg      short loc_180061892
0x18006188e  mov     ebx, eax
0x180061890  jmp     short loc_18006189B
0x180061892  movzx   ebx, ax
0x180061895  or      ebx, 80070000h
0x18006189b  test    rdi, rdi
0x18006189e  jz      short loc_1800618B6
0x1800618a0  mov     rcx, [rsp+38h+hKey]; hKey
0x1800618a5  test    rcx, rcx
0x1800618a8  jz      short loc_1800618B6
0x1800618aa  call    cs:__imp_RegCloseKey
0x1800618b1  nop     dword ptr [rax+rax+00h]
0x1800618b6  mov     rsi, [rsp+38h+arg_10]
0x1800618bb  mov     eax, ebx
0x1800618bd  mov     rbx, [rsp+38h+arg_8]
0x1800618c2  add     rsp, 30h
0x1800618c6  pop     rdi
0x1800618c7  retn
```
