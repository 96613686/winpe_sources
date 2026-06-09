# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(HKEY__ *,ushort const *,ulong,void *,ulong *)

- ea: `0x140016e40`
- end: `0x140016e9a`
- name: `?TryGetRegValue@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@CAJPEAUHKEY__@@PEBGKPEAXPEAK@Z`
- size: `90`
- prototype: `static int(HKEY, const unsigned __int16 *, unsigned int, void *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x14000e760`

## callees

- `0x140013720`
- `0x140016e40`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x140016e64`
- `ADVAPI32!RegGetValueW` at `0x140016e64`

## string_xrefs

- `0x140016e7e`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

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
0x140016e40  sub     rsp, 48h
0x140016e44  mov     rax, [rsp+48h+arg_20]
0x140016e49  mov     [rsp+48h+pcbData], rax; pcbData
0x140016e4e  mov     [rsp+48h+pvData], r9; pvData
0x140016e53  mov     r9d, r8d; dwFlags
0x140016e56  mov     r8, rdx; lpValue
0x140016e59  mov     [rsp+48h+pdwType], 0; pdwType
0x140016e62  xor     edx, edx; lpSubKey
0x140016e64  call    cs:__imp_RegGetValueW
0x140016e6a  xor     r9d, r9d
0x140016e6d  cmp     eax, 2
0x140016e70  cmovnz  r9d, eax; char *
0x140016e74  test    r9d, r9d
0x140016e77  jz      short loc_140016E93
0x140016e79  mov     rcx, [rsp+48h]; this
0x140016e7e  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x140016e85  mov     edx, 118h; void *
0x140016e8a  add     rsp, 48h
0x140016e8e  jmp     ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140016e93  xor     eax, eax
0x140016e95  add     rsp, 48h
0x140016e99  retn
```
