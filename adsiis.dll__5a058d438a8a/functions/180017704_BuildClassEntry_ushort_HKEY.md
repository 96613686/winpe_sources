# BuildClassEntry(ushort *,HKEY__ *)

- ea: `0x180017704`
- end: `0x18001788d`
- name: `?BuildClassEntry@@YAPEAU_class_entry@@PEAGPEAUHKEY__@@@Z`
- size: `393`
- prototype: `struct _class_entry *__fastcall(wchar_t *Source, HKEY hKey)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180017894`

## callees

- `0x180017704`
- `0x180017a2c`
- `0x18001d66a`
- `0x18001d6c0`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180017778`
- `msvcrt!wcscpy_s` at `0x18001781e`
- `msvcrt!wcscpy_s` at `0x180017778`
- `msvcrt!wcscpy_s` at `0x18001781e`
- `ADVAPI32!RegCloseKey` at `0x180017838`
- `ADVAPI32!RegCloseKey` at `0x180017838`
- `ADVAPI32!RegEnumKeyExW` at `0x1800177c9`
- `ADVAPI32!RegEnumKeyExW` at `0x1800177c9`
- `ADVAPI32!RegOpenKeyExW` at `0x1800177f2`
- `ADVAPI32!RegOpenKeyExW` at `0x1800177f2`
- `ACTIVEDS!__imp_AllocADsMem` at `0x180017752`
- `ACTIVEDS!__imp_AllocADsMem` at `0x180017752`

## pseudocode

```c
wchar_t *__fastcall BuildClassEntry(wchar_t *Source, HKEY hKey)
{
  wchar_t *v4; // rax
  wchar_t *v5; // rbx
  DWORD v6; // r14d
  wchar_t *v7; // rsi
  wchar_t *v8; // rax
  wchar_t *v9; // rdi
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF

  phkResult = 0;
  cchName = 0;
  v4 = (wchar_t *)AllocADsMem(0x218u);
  v5 = v4;
  if ( v4 )
  {
    v6 = 0;
    v7 = 0;
    wcscpy_s(v4, 0x104u, Source);
    memset_0(Name, 0, 0x208u);
    while ( 1 )
    {
      cchName = 260;
      if ( RegEnumKeyExW(hKey, v6, Name, &cchName, 0, 0, 0, 0) )
        break;
      if ( RegOpenKeyExW(hKey, Name, 0, 0x20019u, &phkResult) )
        return v5;
      v8 = (wchar_t *)BuildExtensionEntry(Name, phkResult);
      v9 = v8;
      if ( v8 )
      {
        wcscpy_s(v8, 0x104u, Name);
        *((_QWORD *)v9 + 73) = v7;
        v7 = v9;
      }
      if ( phkResult )
        RegCloseKey(phkResult);
      memset_0(Name, 0, 0x208u);
      ++v6;
    }
    *((_QWORD *)v5 + 65) = v7;
  }
  return v5;
}

```

## disassembly

```asm
0x180017704  mov     [rsp-8+arg_10], rbx
0x180017709  mov     [rsp-8+arg_18], rsi
0x18001770e  push    rbp
0x18001770f  push    rdi
0x180017710  push    r13
0x180017712  push    r14
0x180017714  push    r15
0x180017716  lea     rbp, [rsp-170h]
0x18001771e  sub     rsp, 270h
0x180017725  mov     rax, cs:__security_cookie
0x18001772c  xor     rax, rsp
0x18001772f  mov     [rbp+190h+var_30], rax
0x180017736  mov     rdi, rcx
0x180017739  mov     [rsp+290h+phkResult], 0
0x180017742  mov     ecx, 218h; cb
0x180017747  mov     [rsp+290h+cchName], 0
0x18001774f  mov     r15, rdx
0x180017752  call    cs:__imp_AllocADsMem
0x180017758  mov     rbx, rax
0x18001775b  test    rax, rax
0x18001775e  jz      loc_18001785F
0x180017764  mov     r13d, 104h
0x18001776a  mov     r8, rdi; Source
0x18001776d  mov     edx, r13d; SizeInWords
0x180017770  mov     rcx, rax; Destination
0x180017773  xor     r14d, r14d
0x180017776  xor     esi, esi
0x180017778  call    cs:__imp_wcscpy_s
0x18001777e  xor     edx, edx; Val
0x180017780  lea     rcx, [rsp+290h+Name]; void *
0x180017785  mov     r8d, 208h; Size
0x18001778b  call    memset_0
0x180017790  mov     [rsp+290h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180017799  lea     r9, [rsp+290h+cchName]; lpcchName
0x18001779e  mov     [rsp+290h+lpcchClass], 0; lpcchClass
0x1800177a7  lea     r8, [rsp+290h+Name]; lpName
0x1800177ac  mov     [rsp+290h+lpClass], 0; lpClass
0x1800177b5  mov     edx, r14d; dwIndex
0x1800177b8  mov     rcx, r15; hKey
0x1800177bb  mov     [rsp+290h+lpReserved], 0; lpReserved
0x1800177c4  mov     [rsp+290h+cchName], r13d
0x1800177c9  call    cs:__imp_RegEnumKeyExW
0x1800177cf  test    eax, eax
0x1800177d1  jnz     loc_180017858
0x1800177d7  lea     rax, [rsp+290h+phkResult]
0x1800177dc  mov     r9d, 20019h; samDesired
0x1800177e2  xor     r8d, r8d; ulOptions
0x1800177e5  mov     [rsp+290h+lpReserved], rax; phkResult
0x1800177ea  lea     rdx, [rsp+290h+Name]; lpSubKey
0x1800177ef  mov     rcx, r15; hKey
0x1800177f2  call    cs:__imp_RegOpenKeyExW
0x1800177f8  test    eax, eax
0x1800177fa  jnz     short loc_18001785F
0x1800177fc  mov     rdx, [rsp+290h+phkResult]; hKey
0x180017801  lea     rcx, [rsp+290h+Name]; lpsz
0x180017806  call    ?BuildExtensionEntry@@YAPEAU_extension_entry@@PEAGPEAUHKEY__@@@Z; BuildExtensionEntry(ushort *,HKEY__ *)
0x18001780b  mov     rdi, rax
0x18001780e  test    rax, rax
0x180017811  jz      short loc_18001782E
0x180017813  lea     r8, [rsp+290h+Name]; Source
0x180017818  mov     rdx, r13; SizeInWords
0x18001781b  mov     rcx, rax; Destination
0x18001781e  call    cs:__imp_wcscpy_s
0x180017824  mov     [rdi+248h], rsi
0x18001782b  mov     rsi, rdi
0x18001782e  mov     rcx, [rsp+290h+phkResult]; hKey
0x180017833  test    rcx, rcx
0x180017836  jz      short loc_18001783E
0x180017838  call    cs:__imp_RegCloseKey
0x18001783e  xor     edx, edx; Val
0x180017840  lea     rcx, [rsp+290h+Name]; void *
0x180017845  mov     r8d, 208h; Size
0x18001784b  call    memset_0
0x180017850  inc     r14d
0x180017853  jmp     loc_180017790
0x180017858  mov     [rbx+208h], rsi
0x18001785f  mov     rax, rbx
0x180017862  mov     rcx, [rbp+190h+var_30]
0x180017869  xor     rcx, rsp; StackCookie
0x18001786c  call    __security_check_cookie
0x180017871  lea     r11, [rsp+290h+var_20]
0x180017879  mov     rbx, [r11+40h]
0x18001787d  mov     rsi, [r11+48h]
0x180017881  mov     rsp, r11
0x180017884  pop     r15
0x180017886  pop     r14
0x180017888  pop     r13
0x18001788a  pop     rdi
0x18001788b  pop     rbp
0x18001788c  retn
```
