# StringCchLengthW

- ea: `0x18000c964`
- end: `0x18000c9a9`
- name: `StringCchLengthW`
- size: `69`
- prototype: `HRESULT __stdcall(STRSAFE_PCNZWCH psz, size_t cchMax, size_t *pcchLength)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180002e30`

## callees

- `0x18000c964`

## string_xrefs

- `0x18000c969`: `WSLicensingService-AllowDisablingStoreApps`

## pseudocode

```c
HRESULT __stdcall StringCchLengthW(STRSAFE_PCNZWCH psz, size_t cchMax, size_t *pcchLength)
{
  const wchar_t *v3; // rax
  __int64 v4; // rcx
  HRESULT result; // eax

  v3 = L"WSLicensingService-AllowDisablingStoreApps";
  v4 = 0x7FFFFFFF;
  do
  {
    if ( !*v3 )
      break;
    ++v3;
    --v4;
  }
  while ( v4 );
  result = v4 == 0 ? 0x80070057 : 0;
  if ( pcchLength )
  {
    if ( v4 )
      *pcchLength = 0x7FFFFFFF - v4;
    else
      *pcchLength = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000c964  mov     edx, 7FFFFFFFh
0x18000c969  lea     rax, aWslicensingser; "WSLicensingService-AllowDisablingStoreA"...
0x18000c970  mov     ecx, edx
0x18000c972  xor     r9d, r9d
0x18000c975  cmp     [rax], r9w
0x18000c979  jz      short loc_18000C985
0x18000c97b  add     rax, 2
0x18000c97f  sub     rcx, 1
0x18000c983  jnz     short loc_18000C975
0x18000c985  mov     rax, rcx
0x18000c988  neg     rax
0x18000c98b  sbb     eax, eax
0x18000c98d  not     eax
0x18000c98f  and     eax, 80070057h
0x18000c994  test    r8, r8
0x18000c997  jz      short locret_18000C9A8
0x18000c999  test    rcx, rcx
0x18000c99c  jz      short loc_18000C9A5
0x18000c99e  sub     rdx, rcx
0x18000c9a1  mov     [r8], rdx
0x18000c9a4  retn
0x18000c9a5  mov     [r8], r9
0x18000c9a8  retn
```
