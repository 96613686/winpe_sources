# WriteRegSZValue(HKEY__ *,ushort const *,ushort const *,ushort const *,_SECURITY_ATTRIBUTES *,int)

- ea: `0x140018520`
- end: `0x140018662`
- name: `?WriteRegSZValue@@YAJPEAUHKEY__@@PEBG11PEAU_SECURITY_ATTRIBUTES@@H@Z`
- size: `322`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, const BYTE *)`
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140018b40`
- `0x140019c6c`
- `0x140019d68`
- `0x140019e94`
- `0x140019fcc`
- `0x14001a550`

## callees

- `0x14000740c`
- `0x1400074d4`
- `0x140018520`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14001864d`
- `ADVAPI32!RegCloseKey` at `0x14001864d`
- `ADVAPI32!RegCreateKeyExW` at `0x14001859b`
- `ADVAPI32!RegCreateKeyExW` at `0x14001859b`
- `ADVAPI32!RegSetValueExW` at `0x1400185f9`
- `ADVAPI32!RegSetValueExW` at `0x1400185f9`
- `KERNEL32!GetLastError` at `0x1400185b8`
- `KERNEL32!GetLastError` at `0x140018616`
- `KERNEL32!GetLastError` at `0x1400185b8`
- `KERNEL32!GetLastError` at `0x140018616`

## string_xrefs

- `0x1400185c1`: `RegCreateKeyEx for subkey %1 failed  with Status = %2!d!. GetLastError is 0x%3!x!`
- `0x14001861f`: `RegSetValueEx for value %1 failed  with Status = %2!d!. GetLastError is 0x%3!x!`
- `0x14001862b`: `Setting the value of the registry key %1\%2 to %3.`

## pseudocode

```c
__int64 __fastcall WriteRegSZValue(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3, const BYTE *a4)
{
  unsigned int v7; // ebx
  __int64 v8; // rbx
  LSTATUS v9; // eax
  unsigned int v10; // edi
  DWORD LastError; // eax
  LSTATUS v12; // eax
  unsigned int v13; // edi
  DWORD v14; // eax
  HKEY hKey; // [rsp+90h] [rbp+8h] BYREF

  hKey = 0;
  if ( a4 && a2 && a3 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)&a4[2 * v8] );
    v9 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0, 0, 0xF013Fu, 0, &hKey, 0);
    v10 = v9;
    if ( v9 )
    {
      if ( v9 > 0 )
        v7 = (unsigned __int16)v9 | 0x80070000;
      else
        v7 = v9;
      LastError = GetLastError();
      LogError(L"RegCreateKeyEx for subkey %1 failed  with Status = %2!d!. GetLastError is 0x%3!x!", a2, v10, LastError);
    }
    else
    {
      v12 = RegSetValueExW(hKey, a3, 0, 1u, a4, 2 * v8 + 2);
      v13 = v12;
      if ( v12 )
      {
        if ( v12 > 0 )
          v7 = (unsigned __int16)v12 | 0x80070000;
        else
          v7 = v12;
        v14 = GetLastError();
        LogError(L"RegSetValueEx for value %1 failed  with Status = %2!d!. GetLastError is 0x%3!x!", a3, v13, v14);
      }
      else
      {
        v7 = 0;
        LogInfo(L"Setting the value of the registry key %1\\%2 to %3.", a2, a3, a4);
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v7;
}

```

## disassembly

```asm
0x140018520  mov     rax, rsp
0x140018523  mov     [rax+8], rcx
0x140018527  push    rbx
0x140018528  push    rbp
0x140018529  push    rsi
0x14001852a  push    rdi
0x14001852b  push    r14
0x14001852d  push    r15
0x14001852f  sub     rsp, 58h
0x140018533  xor     r15d, r15d
0x140018536  mov     rsi, r9
0x140018539  mov     [rax+8], r15
0x14001853d  mov     rbp, r8
0x140018540  mov     r14, rdx
0x140018543  test    r9, r9
0x140018546  jnz     short loc_140018552
0x140018548  mov     ebx, 80070057h
0x14001854d  jmp     loc_140018653
0x140018552  test    r14, r14
0x140018555  jz      short loc_140018548
0x140018557  test    rbp, rbp
0x14001855a  jz      short loc_140018548
0x14001855c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140018560  inc     rbx
0x140018563  cmp     [r9+rbx*2], r15w
0x140018568  jnz     short loc_140018560
0x14001856a  mov     [rsp+88h+lpdwDisposition], r15; lpdwDisposition
0x14001856f  lea     rax, [rsp+88h+hKey]
0x140018577  mov     [rsp+88h+phkResult], rax; phkResult
0x14001857c  xor     r9d, r9d; lpClass
0x14001857f  mov     [rsp+88h+lpSecurityAttributes], r15; lpSecurityAttributes
0x140018584  xor     r8d, r8d; Reserved
0x140018587  mov     [rsp+88h+samDesired], 0F013Fh; samDesired
0x14001858f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140018596  mov     [rsp+88h+dwOptions], r15d; dwOptions
0x14001859b  call    cs:__imp_RegCreateKeyExW
0x1400185a1  mov     edi, eax
0x1400185a3  test    eax, eax
0x1400185a5  jz      short loc_1400185D5
0x1400185a7  test    eax, eax
0x1400185a9  jg      short loc_1400185AF
0x1400185ab  mov     ebx, eax
0x1400185ad  jmp     short loc_1400185B8
0x1400185af  movzx   ebx, di
0x1400185b2  or      ebx, 80070000h
0x1400185b8  call    cs:__imp_GetLastError
0x1400185be  mov     rdx, r14
0x1400185c1  lea     rcx, aRegcreatekeyex_0; "RegCreateKeyEx for subkey %1 failed  wi"...
0x1400185c8  mov     r8d, edi
0x1400185cb  mov     r9d, eax
0x1400185ce  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x1400185d3  jmp     short loc_140018640
0x1400185d5  mov     rcx, [rsp+88h+hKey]; hKey
0x1400185dd  lea     eax, ds:2[rbx*2]
0x1400185e4  mov     [rsp+88h+samDesired], eax; cbData
0x1400185e8  mov     r9d, 1; dwType
0x1400185ee  xor     r8d, r8d; Reserved
0x1400185f1  mov     qword ptr [rsp+88h+dwOptions], rsi; lpData
0x1400185f6  mov     rdx, rbp; lpValueName
0x1400185f9  call    cs:__imp_RegSetValueExW
0x1400185ff  mov     edi, eax
0x140018601  test    eax, eax
0x140018603  jz      short loc_140018628
0x140018605  test    eax, eax
0x140018607  jg      short loc_14001860D
0x140018609  mov     ebx, eax
0x14001860b  jmp     short loc_140018616
0x14001860d  movzx   ebx, di
0x140018610  or      ebx, 80070000h
0x140018616  call    cs:__imp_GetLastError
0x14001861c  mov     rdx, rbp
0x14001861f  lea     rcx, aRegsetvalueexF; "RegSetValueEx for value %1 failed  with"...
0x140018626  jmp     short loc_1400185C8
0x140018628  mov     r9, rsi
0x14001862b  lea     rcx, aSettingTheValu; "Setting the value of the registry key %"...
0x140018632  mov     r8, rbp
0x140018635  mov     rdx, r14
0x140018638  mov     ebx, r15d
0x14001863b  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x140018640  mov     rcx, [rsp+88h+hKey]; hKey
0x140018648  test    rcx, rcx
0x14001864b  jz      short loc_140018653
0x14001864d  call    cs:__imp_RegCloseKey
0x140018653  mov     eax, ebx
0x140018655  add     rsp, 58h
0x140018659  pop     r15
0x14001865b  pop     r14
0x14001865d  pop     rdi
0x14001865e  pop     rsi
0x14001865f  pop     rbp
0x140018660  pop     rbx
0x140018661  retn
```
