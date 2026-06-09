# DeleteRegKeyRecursive(HKEY__ *,ushort const *)

- ea: `0x1400156e0`
- end: `0x140015843`
- name: `?DeleteRegKeyRecursive@@YAJPEAUHKEY__@@PEBG@Z`
- size: `355`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x1400156e0`
- `0x140018d08`

## callees

- `0x14000740c`
- `0x1400074d4`
- `0x1400156e0`
- `0x14001a8d0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140015741`
- `ADVAPI32!RegOpenKeyExW` at `0x140015741`
- `ADVAPI32!RegCloseKey` at `0x1400157b2`
- `ADVAPI32!RegCloseKey` at `0x1400157b2`
- `ADVAPI32!RegEnumKeyExW` at `0x140015789`
- `ADVAPI32!RegEnumKeyExW` at `0x140015789`
- `ADVAPI32!RegDeleteKeyExW` at `0x1400157c7`
- `ADVAPI32!RegDeleteKeyExW` at `0x1400157c7`
- `KERNEL32!GetLastError` at `0x1400157ff`
- `KERNEL32!GetLastError` at `0x1400157ff`

## string_xrefs

- `0x140015808`: `RegOpenKeyExW for %1 failed with Status = %2!d!. GetLastError is 0x%3!x!`
- `0x1400157ef`: `Registry %1 does not exist - nothing to delete`

## pseudocode

```c
__int64 __fastcall DeleteRegKeyRecursive(HKEY a1, const unsigned __int16 *a2)
{
  LSTATUS v4; // edi
  unsigned int v5; // ebx
  DWORD LastError; // eax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Name[256]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  cchName = 256;
  ftLastWriteTime = 0;
  v4 = RegOpenKeyExW(a1, a2, 0, 0x2011Fu, &hKey);
  if ( v4 )
    goto LABEL_7;
  v5 = 0;
  while ( !RegEnumKeyExW(hKey, 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime) )
  {
    v5 = DeleteRegKeyRecursive(hKey, Name);
    if ( (v5 & 0x80000000) != 0 )
      return v5;
    cchName = 256;
  }
  RegCloseKey(hKey);
  v4 = RegDeleteKeyExW(a1, a2, 0x100u, 0);
  if ( v4 )
  {
LABEL_7:
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    else
      v5 = v4;
    if ( v5 == -2147024894 )
    {
      LogInfo(L"Registry %1 does not exist - nothing to delete", a2);
      return 0;
    }
    else
    {
      LastError = GetLastError();
      LogError(
        L"RegOpenKeyExW for %1 failed with Status = %2!d!. GetLastError is 0x%3!x!",
        a2,
        (unsigned int)v4,
        LastError);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1400156e0  mov     [rsp-8+arg_10], rbx
0x1400156e5  mov     [rsp-8+arg_18], rsi
0x1400156ea  push    rbp
0x1400156eb  push    rdi
0x1400156ec  push    r14
0x1400156ee  lea     rbp, [rsp-170h]
0x1400156f6  sub     rsp, 270h
0x1400156fd  mov     rax, cs:__security_cookie
0x140015704  xor     rax, rsp
0x140015707  mov     [rbp+180h+var_20], rax
0x14001570e  lea     rax, [rsp+280h+hKey]
0x140015713  mov     [rsp+280h+hKey], 0
0x14001571c  mov     r9d, 2011Fh; samDesired
0x140015722  mov     [rsp+280h+phkResult], rax; phkResult
0x140015727  xor     r8d, r8d; ulOptions
0x14001572a  mov     [rsp+280h+cchName], 100h
0x140015732  mov     rsi, rdx
0x140015735  mov     qword ptr [rsp+280h+ftLastWriteTime.dwLowDateTime], 0
0x14001573e  mov     r14, rcx
0x140015741  call    cs:__imp_RegOpenKeyExW
0x140015747  mov     edi, eax
0x140015749  test    eax, eax
0x14001574b  jnz     loc_1400157D3
0x140015751  xor     ebx, ebx
0x140015753  mov     rcx, [rsp+280h+hKey]; hKey
0x140015758  lea     rax, [rsp+280h+ftLastWriteTime]
0x14001575d  mov     [rsp+280h+lpftLastWriteTime], rax; lpftLastWriteTime
0x140015762  lea     r9, [rsp+280h+cchName]; lpcchName
0x140015767  mov     [rsp+280h+lpcchClass], 0; lpcchClass
0x140015770  lea     r8, [rsp+280h+Name]; lpName
0x140015775  mov     [rsp+280h+lpClass], 0; lpClass
0x14001577e  xor     edx, edx; dwIndex
0x140015780  mov     [rsp+280h+phkResult], 0; lpReserved
0x140015789  call    cs:__imp_RegEnumKeyExW
0x14001578f  mov     rcx, [rsp+280h+hKey]; HKEY
0x140015794  test    eax, eax
0x140015796  jnz     short loc_1400157B2
0x140015798  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x14001579d  call    ?DeleteRegKeyRecursive@@YAJPEAUHKEY__@@PEBG@Z; DeleteRegKeyRecursive(HKEY__ *,ushort const *)
0x1400157a2  mov     ebx, eax
0x1400157a4  test    eax, eax
0x1400157a6  js      short loc_14001581A
0x1400157a8  mov     [rsp+280h+cchName], 100h
0x1400157b0  jmp     short loc_140015753
0x1400157b2  call    cs:__imp_RegCloseKey
0x1400157b8  xor     r9d, r9d; Reserved
0x1400157bb  mov     r8d, 100h; samDesired
0x1400157c1  mov     rdx, rsi; lpSubKey
0x1400157c4  mov     rcx, r14; hKey
0x1400157c7  call    cs:__imp_RegDeleteKeyExW
0x1400157cd  mov     edi, eax
0x1400157cf  test    eax, eax
0x1400157d1  jz      short loc_14001581A
0x1400157d3  test    edi, edi
0x1400157d5  jg      short loc_1400157DB
0x1400157d7  mov     ebx, edi
0x1400157d9  jmp     short loc_1400157E4
0x1400157db  movzx   ebx, di
0x1400157de  or      ebx, 80070000h
0x1400157e4  cmp     ebx, 80070002h
0x1400157ea  jnz     short loc_1400157FF
0x1400157ec  mov     rdx, rsi
0x1400157ef  lea     rcx, aRegistry1DoesN; "Registry %1 does not exist - nothing to"...
0x1400157f6  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x1400157fb  xor     ebx, ebx
0x1400157fd  jmp     short loc_14001581A
0x1400157ff  call    cs:__imp_GetLastError
0x140015805  mov     r8d, edi
0x140015808  lea     rcx, aRegopenkeyexwF_2; "RegOpenKeyExW for %1 failed with Status"...
0x14001580f  mov     r9d, eax
0x140015812  mov     rdx, rsi
0x140015815  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x14001581a  mov     eax, ebx
0x14001581c  mov     rcx, [rbp+180h+var_20]
0x140015823  xor     rcx, rsp; StackCookie
0x140015826  call    __security_check_cookie
0x14001582b  lea     r11, [rsp+280h+var_10]
0x140015833  mov     rbx, [r11+30h]
0x140015837  mov     rsi, [r11+38h]
0x14001583b  mov     rsp, r11
0x14001583e  pop     r14
0x140015840  pop     rdi
0x140015841  pop     rbp
0x140015842  retn
```
