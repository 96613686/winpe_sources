# Registrar::UnregisterComClass(Registrar::ClassInfo const &)

- ea: `0x180040a54`
- end: `0x180040b70`
- name: `?UnregisterComClass@Registrar@@CAJAEBUClassInfo@1@@Z`
- size: `284`
- prototype: `__int64 __fastcall(const struct Registrar::ClassInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180040b78`

## callees

- `0x180006194`
- `0x180040a54`
- `0x180040c68`
- `0x180043510`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180040a97`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180040a97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040b47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040b47`

## string_xrefs

- `0x180040aaa`: `Software\Classes\CLSID\%s`

## pseudocode

```c
HRESULT __fastcall Registrar::UnregisterComClass(const struct Registrar::ClassInfo *a1)
{
  const IID *v2; // rcx
  int v3; // ebx
  HRESULT result; // eax
  HKEY v5; // rcx
  HKEY v6; // rcx
  HKEY v7; // rcx
  LPOLESTR lpsz; // [rsp+20h] [rbp-138h] BYREF
  unsigned __int16 v9[72]; // [rsp+30h] [rbp-128h] BYREF
  unsigned __int16 v10[64]; // [rsp+C0h] [rbp-98h] BYREF

  lpsz = 0;
  v2 = (const IID *)*((_QWORD *)a1 + 1);
  if ( v2 )
  {
    result = StringFromCLSID(v2, &lpsz);
    if ( result < 0 )
      return result;
    v3 = StringCchPrintfW(v10, 0x3Fu, L"Software\\Classes\\CLSID\\%s", lpsz);
    if ( v3 >= 0 )
    {
      v3 = recursiveDeleteKey(v5, v10);
      if ( v3 >= 0 )
      {
        if ( !*((_QWORD *)a1 + 4)
          || (v3 = StringCchPrintfW(v9, 0x45u, L"Software\\Classes\\%s"), v3 >= 0)
          && (v3 = recursiveDeleteKey(v6, v9), v3 >= 0) )
        {
          if ( *((_QWORD *)a1 + 3) )
          {
            v3 = StringCchPrintfW(v9, 0x45u, L"Software\\Classes\\%s");
            if ( v3 >= 0 )
              v3 = recursiveDeleteKey(v7, v9);
          }
        }
      }
    }
  }
  else
  {
    v3 = -2147418113;
  }
  CoTaskMemFree(lpsz);
  return v3;
}

```

## disassembly

```asm
0x180040a54  mov     [rsp+arg_8], rbx
0x180040a59  push    rdi
0x180040a5a  sub     rsp, 150h
0x180040a61  mov     rax, cs:__security_cookie
0x180040a68  xor     rax, rsp
0x180040a6b  mov     [rsp+158h+var_18], rax
0x180040a73  mov     rdi, rcx
0x180040a76  mov     [rsp+158h+lpsz], 0
0x180040a7f  mov     rcx, [rcx+8]; rclsid
0x180040a83  test    rcx, rcx
0x180040a86  jnz     short loc_180040A92
0x180040a88  mov     ebx, 8000FFFFh
0x180040a8d  jmp     loc_180040B42
0x180040a92  lea     rdx, [rsp+158h+lpsz]; lplpsz
0x180040a97  call    cs:__imp_StringFromCLSID
0x180040a9d  test    eax, eax
0x180040a9f  js      loc_180040B4F
0x180040aa5  mov     r9, [rsp+158h+lpsz]
0x180040aaa  lea     r8, aSoftwareClasse_0; "Software\\Classes\\CLSID\\%s"
0x180040ab1  mov     edx, 3Fh ; '?'; unsigned __int64
0x180040ab6  lea     rcx, [rsp+158h+var_98]; unsigned __int16 *
0x180040abe  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180040ac3  mov     ebx, eax
0x180040ac5  test    eax, eax
0x180040ac7  js      short loc_180040B42
0x180040ac9  lea     rdx, [rsp+158h+var_98]; unsigned __int16 *
0x180040ad1  call    ?recursiveDeleteKey@@YAJPEAUHKEY__@@PEBG@Z; recursiveDeleteKey(HKEY__ *,ushort const *)
0x180040ad6  mov     ebx, eax
0x180040ad8  test    eax, eax
0x180040ada  js      short loc_180040B42
0x180040adc  mov     r9, [rdi+20h]
0x180040ae0  test    r9, r9
0x180040ae3  jz      short loc_180040B11
0x180040ae5  lea     r8, aSoftwareClasse_1; "Software\\Classes\\%s"
0x180040aec  mov     edx, 45h ; 'E'; unsigned __int64
0x180040af1  lea     rcx, [rsp+158h+var_128]; unsigned __int16 *
0x180040af6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180040afb  mov     ebx, eax
0x180040afd  test    eax, eax
0x180040aff  js      short loc_180040B42
0x180040b01  lea     rdx, [rsp+158h+var_128]; unsigned __int16 *
0x180040b06  call    ?recursiveDeleteKey@@YAJPEAUHKEY__@@PEBG@Z; recursiveDeleteKey(HKEY__ *,ushort const *)
0x180040b0b  mov     ebx, eax
0x180040b0d  test    eax, eax
0x180040b0f  js      short loc_180040B42
0x180040b11  mov     r9, [rdi+18h]
0x180040b15  test    r9, r9
0x180040b18  jz      short loc_180040B42
0x180040b1a  lea     r8, aSoftwareClasse_1; "Software\\Classes\\%s"
0x180040b21  mov     edx, 45h ; 'E'; unsigned __int64
0x180040b26  lea     rcx, [rsp+158h+var_128]; unsigned __int16 *
0x180040b2b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180040b30  mov     ebx, eax
0x180040b32  test    eax, eax
0x180040b34  js      short loc_180040B42
0x180040b36  lea     rdx, [rsp+158h+var_128]; unsigned __int16 *
0x180040b3b  call    ?recursiveDeleteKey@@YAJPEAUHKEY__@@PEBG@Z; recursiveDeleteKey(HKEY__ *,ushort const *)
0x180040b40  mov     ebx, eax
0x180040b42  mov     rcx, [rsp+158h+lpsz]; pv
0x180040b47  call    cs:__imp_CoTaskMemFree
0x180040b4d  mov     eax, ebx
0x180040b4f  mov     rcx, [rsp+158h+var_18]
0x180040b57  xor     rcx, rsp; StackCookie
0x180040b5a  call    __security_check_cookie
0x180040b5f  mov     rbx, [rsp+158h+arg_8]
0x180040b67  add     rsp, 150h
0x180040b6e  pop     rdi
0x180040b6f  retn
```
