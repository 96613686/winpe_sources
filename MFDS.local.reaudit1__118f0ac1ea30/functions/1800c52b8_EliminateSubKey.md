# EliminateSubKey

- ea: `0x1800c52b8`
- end: `0x1800c5413`
- name: `EliminateSubKey`
- size: `347`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800c5228`
- `0x1800c52b8`

## callees

- `0x1800429e4`
- `0x180074160`
- `0x1800c52b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800c5395`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800c5395`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c533a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c533a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c53bd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c53bd`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800c53cf`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800c53cf`

## pseudocode

```c
LSTATUS __fastcall EliminateSubKey(HKEY a1, const unsigned __int16 *a2)
{
  LSTATUS result; // eax
  bool v5; // cc
  DWORD cchName[2]; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  *(_QWORD *)cchName = 0;
  if ( (int)StringCchLengthW(a2, 0x7FFFFFFFu, (unsigned __int64 *)cchName) < 0 || !*(_QWORD *)cchName )
    return -2147467259;
  result = RegOpenKeyExW(a1, a2, 0, 0x2000000u, &hKey);
  v5 = result <= 0;
  if ( !result )
  {
    do
    {
      cchName[0] = 260;
      ftLastWriteTime = 0;
    }
    while ( !RegEnumKeyExW(hKey, 0, SubKey, cchName, 0, 0, 0, &ftLastWriteTime)
         && !(unsigned int)EliminateSubKey(hKey, SubKey) );
    RegCloseKey(hKey);
    result = RegDeleteKeyW(a1, a2);
    v5 = result <= 0;
  }
  if ( !v5 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800c52b8  mov     [rsp-8+arg_10], rbx
0x1800c52bd  mov     [rsp-8+arg_18], rdi
0x1800c52c2  push    rbp
0x1800c52c3  lea     rbp, [rsp-180h]
0x1800c52cb  sub     rsp, 280h
0x1800c52d2  mov     rax, cs:__security_cookie
0x1800c52d9  xor     rax, rsp
0x1800c52dc  mov     [rbp+180h+var_10], rax
0x1800c52e3  mov     rbx, rdx
0x1800c52e6  mov     [rsp+280h+hKey], 0
0x1800c52ef  mov     rdi, rcx
0x1800c52f2  mov     qword ptr [rsp+280h+cchName], 0
0x1800c52fb  mov     rcx, rbx; unsigned __int16 *
0x1800c52fe  lea     r8, [rsp+280h+cchName]; unsigned __int64 *
0x1800c5303  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800c5308  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800c530d  test    eax, eax
0x1800c530f  js      loc_1800C53E9
0x1800c5315  cmp     qword ptr [rsp+280h+cchName], 0
0x1800c531b  jz      loc_1800C53E9
0x1800c5321  lea     rax, [rsp+280h+hKey]
0x1800c5326  mov     r9d, 2000000h; samDesired
0x1800c532c  xor     r8d, r8d; ulOptions
0x1800c532f  mov     [rsp+280h+phkResult], rax; phkResult
0x1800c5334  mov     rdx, rbx; lpSubKey
0x1800c5337  mov     rcx, rdi; hKey
0x1800c533a  call    cs:__imp_RegOpenKeyExW
0x1800c5341  nop     dword ptr [rax+rax+00h]
0x1800c5346  test    eax, eax
0x1800c5348  jnz     loc_1800C53DD
0x1800c534e  mov     rcx, [rsp+280h+hKey]; hKey
0x1800c5353  lea     rax, [rsp+280h+ftLastWriteTime]
0x1800c5358  mov     [rsp+280h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800c535d  lea     r9, [rsp+280h+cchName]; lpcchName
0x1800c5362  mov     [rsp+280h+lpcchClass], 0; lpcchClass
0x1800c536b  lea     r8, [rsp+280h+SubKey]; lpName
0x1800c5370  mov     [rsp+280h+lpClass], 0; lpClass
0x1800c5379  xor     edx, edx; dwIndex
0x1800c537b  mov     [rsp+280h+phkResult], 0; lpReserved
0x1800c5384  mov     [rsp+280h+cchName], 104h
0x1800c538c  mov     qword ptr [rsp+280h+ftLastWriteTime.dwLowDateTime], 0
0x1800c5395  call    cs:__imp_RegEnumKeyExW
0x1800c539c  nop     dword ptr [rax+rax+00h]
0x1800c53a1  test    eax, eax
0x1800c53a3  jnz     short loc_1800C53B8
0x1800c53a5  mov     rcx, [rsp+280h+hKey]
0x1800c53aa  lea     rdx, [rsp+280h+SubKey]
0x1800c53af  call    EliminateSubKey
0x1800c53b4  test    eax, eax
0x1800c53b6  jz      short loc_1800C534E
0x1800c53b8  mov     rcx, [rsp+280h+hKey]; hKey
0x1800c53bd  call    cs:__imp_RegCloseKey
0x1800c53c4  nop     dword ptr [rax+rax+00h]
0x1800c53c9  mov     rdx, rbx; lpSubKey
0x1800c53cc  mov     rcx, rdi; hKey
0x1800c53cf  call    cs:__imp_RegDeleteKeyW
0x1800c53d6  nop     dword ptr [rax+rax+00h]
0x1800c53db  test    eax, eax
0x1800c53dd  jle     short loc_1800C53EE
0x1800c53df  movzx   eax, ax
0x1800c53e2  or      eax, 80070000h
0x1800c53e7  jmp     short loc_1800C53EE
0x1800c53e9  mov     eax, 80004005h
0x1800c53ee  mov     rcx, [rbp+180h+var_10]
0x1800c53f5  xor     rcx, rsp; StackCookie
0x1800c53f8  call    __security_check_cookie
0x1800c53fd  lea     r11, [rsp+280h+var_s0]
0x1800c5405  mov     rbx, [r11+20h]
0x1800c5409  mov     rdi, [r11+28h]
0x1800c540d  mov     rsp, r11
0x1800c5410  pop     rbp
0x1800c5411  retn
```
