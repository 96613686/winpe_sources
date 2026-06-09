# EliminateSubKey

- ea: `0x180056574`
- end: `0x1800566cf`
- name: `EliminateSubKey`
- size: `347`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800564e4`
- `0x180056574`

## callees

- `0x18004d320`
- `0x180056128`
- `0x180056574`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180056679`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180056679`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180056651`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180056651`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800565f6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800565f6`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18005668b`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18005668b`

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
0x180056574  mov     [rsp-8+arg_10], rbx
0x180056579  mov     [rsp-8+arg_18], rdi
0x18005657e  push    rbp
0x18005657f  lea     rbp, [rsp-180h]
0x180056587  sub     rsp, 280h
0x18005658e  mov     rax, cs:__security_cookie
0x180056595  xor     rax, rsp
0x180056598  mov     [rbp+180h+var_10], rax
0x18005659f  mov     rbx, rdx
0x1800565a2  mov     [rsp+280h+hKey], 0
0x1800565ab  mov     rdi, rcx
0x1800565ae  mov     qword ptr [rsp+280h+cchName], 0
0x1800565b7  mov     rcx, rbx; unsigned __int16 *
0x1800565ba  lea     r8, [rsp+280h+cchName]; unsigned __int64 *
0x1800565bf  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800565c4  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800565c9  test    eax, eax
0x1800565cb  js      loc_1800566A5
0x1800565d1  cmp     qword ptr [rsp+280h+cchName], 0
0x1800565d7  jz      loc_1800566A5
0x1800565dd  lea     rax, [rsp+280h+hKey]
0x1800565e2  mov     r9d, 2000000h; samDesired
0x1800565e8  xor     r8d, r8d; ulOptions
0x1800565eb  mov     [rsp+280h+phkResult], rax; phkResult
0x1800565f0  mov     rdx, rbx; lpSubKey
0x1800565f3  mov     rcx, rdi; hKey
0x1800565f6  call    cs:__imp_RegOpenKeyExW
0x1800565fd  nop     dword ptr [rax+rax+00h]
0x180056602  test    eax, eax
0x180056604  jnz     loc_180056699
0x18005660a  mov     rcx, [rsp+280h+hKey]; hKey
0x18005660f  lea     rax, [rsp+280h+ftLastWriteTime]
0x180056614  mov     [rsp+280h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180056619  lea     r9, [rsp+280h+cchName]; lpcchName
0x18005661e  mov     [rsp+280h+lpcchClass], 0; lpcchClass
0x180056627  lea     r8, [rsp+280h+SubKey]; lpName
0x18005662c  mov     [rsp+280h+lpClass], 0; lpClass
0x180056635  xor     edx, edx; dwIndex
0x180056637  mov     [rsp+280h+phkResult], 0; lpReserved
0x180056640  mov     [rsp+280h+cchName], 104h
0x180056648  mov     qword ptr [rsp+280h+ftLastWriteTime.dwLowDateTime], 0
0x180056651  call    cs:__imp_RegEnumKeyExW
0x180056658  nop     dword ptr [rax+rax+00h]
0x18005665d  test    eax, eax
0x18005665f  jnz     short loc_180056674
0x180056661  mov     rcx, [rsp+280h+hKey]
0x180056666  lea     rdx, [rsp+280h+SubKey]
0x18005666b  call    EliminateSubKey
0x180056670  test    eax, eax
0x180056672  jz      short loc_18005660A
0x180056674  mov     rcx, [rsp+280h+hKey]; hKey
0x180056679  call    cs:__imp_RegCloseKey
0x180056680  nop     dword ptr [rax+rax+00h]
0x180056685  mov     rdx, rbx; lpSubKey
0x180056688  mov     rcx, rdi; hKey
0x18005668b  call    cs:__imp_RegDeleteKeyW
0x180056692  nop     dword ptr [rax+rax+00h]
0x180056697  test    eax, eax
0x180056699  jle     short loc_1800566AA
0x18005669b  movzx   eax, ax
0x18005669e  or      eax, 80070000h
0x1800566a3  jmp     short loc_1800566AA
0x1800566a5  mov     eax, 80004005h
0x1800566aa  mov     rcx, [rbp+180h+var_10]
0x1800566b1  xor     rcx, rsp; StackCookie
0x1800566b4  call    __security_check_cookie
0x1800566b9  lea     r11, [rsp+280h+var_s0]
0x1800566c1  mov     rbx, [r11+20h]
0x1800566c5  mov     rdi, [r11+28h]
0x1800566c9  mov     rsp, r11
0x1800566cc  pop     rbp
0x1800566cd  retn
```
