# CRegistry::GetValue(wchar_t const *,ulong *)

- ea: `0x140028fe4`
- end: `0x140029082`
- name: `?GetValue@CRegistry@@QEAAHPEB_WPEAK@Z`
- size: `158`
- prototype: `__int64 __fastcall(CRegistry *__hidden this, const wchar_t *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x14002290c`

## callees

- `0x140028fe4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140028ffb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002906f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140028ffb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002906f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14002904f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14002904f`

## string_xrefs

- `0x140029043`: `MaxMSinFilter`

## pseudocode

```c
__int64 __fastcall CRegistry::GetValue(CRegistry *this, const wchar_t *a2, unsigned int *a3)
{
  HKEY v5; // rcx
  DWORD v6; // ecx
  LSTATUS v7; // eax
  unsigned int Data; // [rsp+40h] [rbp+8h] BYREF
  const wchar_t *Type; // [rsp+48h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+20h] BYREF

  Type = a2;
  SetLastError(0);
  v5 = (HKEY)*((_QWORD *)this + 22);
  cbData = 4;
  LODWORD(Type) = 0;
  Data = 0;
  if ( v5 )
  {
    v7 = RegQueryValueExW(v5, L"MaxMSinFilter", 0, (LPDWORD)&Type, (LPBYTE)&Data, &cbData);
    if ( !v7 && (_DWORD)Type == 4 )
    {
      *a3 = Data;
      return 1;
    }
    v6 = v7;
  }
  else
  {
    v6 = 6;
  }
  SetLastError(v6);
  return 0;
}

```

## disassembly

```asm
0x140028fe4  mov     [rsp+arg_10], rbx
0x140028fe9  mov     [rsp+Type], rdx
0x140028fee  push    rdi
0x140028fef  sub     rsp, 30h
0x140028ff3  mov     rbx, rcx
0x140028ff6  mov     rdi, r8
0x140028ff9  xor     ecx, ecx; dwErrCode
0x140028ffb  call    cs:__imp_SetLastError
0x140029001  mov     rcx, [rbx+0B0h]; hKey
0x140029008  mov     [rsp+38h+cbData], 4
0x140029010  mov     dword ptr [rsp+38h+Type], 0
0x140029018  mov     [rsp+38h+Data], 0
0x140029020  test    rcx, rcx
0x140029023  jnz     short loc_14002902C
0x140029025  mov     ecx, 6
0x14002902a  jmp     short loc_14002906F
0x14002902c  lea     rax, [rsp+38h+cbData]
0x140029031  xor     r8d, r8d; lpReserved
0x140029034  mov     [rsp+38h+lpcbData], rax; lpcbData
0x140029039  lea     r9, [rsp+38h+Type]; lpType
0x14002903e  lea     rax, [rsp+38h+Data]
0x140029043  lea     rdx, aMaxmsinfilter; "MaxMSinFilter"
0x14002904a  mov     [rsp+38h+lpData], rax; lpData
0x14002904f  call    cs:__imp_RegQueryValueExW
0x140029055  test    eax, eax
0x140029057  jnz     short loc_14002906D
0x140029059  cmp     dword ptr [rsp+38h+Type], 4
0x14002905e  jnz     short loc_14002906D
0x140029060  mov     eax, [rsp+38h+Data]
0x140029064  mov     [rdi], eax
0x140029066  mov     eax, 1
0x14002906b  jmp     short loc_140029077
0x14002906d  mov     ecx, eax; dwErrCode
0x14002906f  call    cs:__imp_SetLastError
0x140029075  xor     eax, eax
0x140029077  mov     rbx, [rsp+38h+arg_10]
0x14002907c  add     rsp, 30h
0x140029080  pop     rdi
0x140029081  retn
```
