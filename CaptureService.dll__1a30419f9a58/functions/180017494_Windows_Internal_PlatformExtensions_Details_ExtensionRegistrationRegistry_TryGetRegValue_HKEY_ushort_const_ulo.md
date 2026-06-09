# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(HKEY__ *,ushort const *,ulong,void *,ulong *)

- ea: `0x180017494`
- end: `0x1800174ee`
- name: `?TryGetRegValue@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@CAJPEAUHKEY__@@PEBGKPEAXPEAK@Z`
- size: `90`
- prototype: `static int(HKEY, const unsigned __int16 *, unsigned int, void *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180012134`

## callees

- `0x180014800`
- `0x180017494`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800174b8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800174b8`

## string_xrefs

- `0x1800174d2`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

## pseudocode

```c
int __fastcall Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(
        HKEY a1,
        const unsigned __int16 *a2,
        DWORD a3,
        void *pvData,
        unsigned int *pcbData)
{
  unsigned int ValueW; // eax
  const char *v6; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  ValueW = RegGetValueW(a1, 0, a2, a3, 0, pvData, pcbData);
  v6 = 0;
  if ( ValueW != 2 )
    v6 = (const char *)ValueW;
  if ( (_DWORD)v6 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x118,
             (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
             v6,
             (unsigned int)pcbData);
  else
    return 0;
}

```

## disassembly

```asm
0x180017494  sub     rsp, 48h
0x180017498  mov     rax, [rsp+48h+arg_20]
0x18001749d  mov     [rsp+48h+pcbData], rax; pcbData
0x1800174a2  mov     [rsp+48h+pvData], r9; pvData
0x1800174a7  mov     r9d, r8d; dwFlags
0x1800174aa  mov     r8, rdx; lpValue
0x1800174ad  mov     [rsp+48h+pdwType], 0; pdwType
0x1800174b6  xor     edx, edx; lpSubKey
0x1800174b8  call    cs:__imp_RegGetValueW
0x1800174be  xor     r9d, r9d
0x1800174c1  cmp     eax, 2
0x1800174c4  cmovnz  r9d, eax; char *
0x1800174c8  test    r9d, r9d
0x1800174cb  jz      short loc_1800174E7
0x1800174cd  mov     rcx, [rsp+48h]; this
0x1800174d2  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x1800174d9  mov     edx, 118h; void *
0x1800174de  add     rsp, 48h
0x1800174e2  jmp     ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800174e7  xor     eax, eax
0x1800174e9  add     rsp, 48h
0x1800174ed  retn
```
