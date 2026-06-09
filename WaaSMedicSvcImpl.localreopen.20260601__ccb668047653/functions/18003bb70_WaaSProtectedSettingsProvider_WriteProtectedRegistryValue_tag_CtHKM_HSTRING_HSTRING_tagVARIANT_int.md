# WaaSProtectedSettingsProvider::WriteProtectedRegistryValue(tag_CtHKM,HSTRING__ *,HSTRING__ *,tagVARIANT,int)

- ea: `0x18003bb70`
- end: `0x18003bc7f`
- name: `?WriteProtectedRegistryValue@WaaSProtectedSettingsProvider@@UEAAJW4tag_CtHKM@@PEAUHSTRING__@@1UtagVARIANT@@H@Z`
- size: `271`
- prototype: `__int64 __fastcall(__int64, int, HSTRING, HSTRING, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callees

- `0x1800271a4`
- `0x18002e81c`
- `0x180034c28`
- `0x18003bb70`
- `0x180068b78`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003bb88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003bb96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003bb88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003bb96`

## string_xrefs

- `0x18003bc02`: `Caller is not granted access to write protected keys under this path. Will return: 0x%08x`
- `0x18003bc49`: `Error while attempting to determine base regkey name by index. Error code: 0x%08x.`
- `0x18003bbe0`: `Could not verify access to registry path: %s. Error code: 0x%08x.`
- `0x18003bc39`: `Caller was allowed to write under this path of registry but the write operation failed. Error code: 0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WaaSProtectedSettingsProvider::WriteProtectedRegistryValue(
        __int64 a1,
        int a2,
        HSTRING a3,
        HSTRING a4,
        unsigned __int16 *a5)
{
  __int64 v5; // rsi
  unsigned __int16 *StringRawBuffer; // rdi
  const unsigned __int16 *v8; // rbp
  bool *v9; // r9
  __int64 v10; // r14
  WaasMedic::ProtectedSettingsNamespaceMapper *v11; // rsi
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // eax
  struct tagVARIANT *v16; // [rsp+20h] [rbp-48h]
  bool v17; // [rsp+28h] [rbp-40h]
  unsigned __int16 v18; // [rsp+78h] [rbp+10h] BYREF

  v5 = a2;
  StringRawBuffer = (unsigned __int16 *)WindowsGetStringRawBuffer(a3, 0);
  v8 = WindowsGetStringRawBuffer(a4, 0);
  if ( (unsigned int)v5 > 6 )
  {
    v11 = 0;
    v13 = -2147483637;
    LogLevelW(2u, L"Error while attempting to determine base regkey name by index. Error code: 0x%08x.", 2147483659LL);
  }
  else
  {
    LOBYTE(v18) = 0;
    v10 = v5;
    v11 = (WaasMedic::ProtectedSettingsNamespaceMapper *)off_180070EA0[v5];
    v12 = WaasMedic::ProtectedSettingsNamespaceMapper::IsCallerAllowedToWriteToRegistryPath(
            v11,
            StringRawBuffer,
            &v18,
            v9);
    v13 = v12;
    if ( v12 >= 0 )
    {
      if ( (_BYTE)v18 )
      {
        LOBYTE(v16) = 1;
        v14 = WaasMedic::RegSetValueFromVariant(
                (WaasMedic *)qword_180085718[v10],
                (HKEY)StringRawBuffer,
                v8,
                a5,
                v16,
                v17);
        v13 = v14;
        if ( v14 < 0 )
          LogLevelW(
            3u,
            L"Caller was allowed to write under this path of registry but the write operation failed. Error code: 0x%08x",
            (unsigned int)v14);
      }
      else
      {
        v13 = -2147024891;
        LogLevelW(
          3u,
          L"Caller is not granted access to write protected keys under this path. Will return: 0x%08x",
          2147942405LL);
      }
    }
    else
    {
      LogLevelW(
        2u,
        L"Could not verify access to registry path: %s. Error code: 0x%08x.",
        StringRawBuffer,
        (unsigned int)v12);
    }
  }
  WaasMedic::TelemetryProvider::ReportRegistryValueProtectionResult(
    v13,
    (const unsigned __int16 *)v11,
    StringRawBuffer,
    v8,
    (bool)v16);
  return v13;
}

```

## disassembly

```asm
0x18003bb70  push    rbx
0x18003bb72  push    rbp
0x18003bb73  push    rsi
0x18003bb74  push    rdi
0x18003bb75  push    r14
0x18003bb77  push    r15
0x18003bb79  sub     rsp, 38h
0x18003bb7d  movsxd  rsi, edx
0x18003bb80  mov     rcx, r8; string
0x18003bb83  xor     edx, edx; length
0x18003bb85  mov     rbx, r9
0x18003bb88  call    cs:__imp_WindowsGetStringRawBuffer
0x18003bb8e  xor     edx, edx; length
0x18003bb90  mov     rcx, rbx; string
0x18003bb93  mov     rdi, rax
0x18003bb96  call    cs:__imp_WindowsGetStringRawBuffer
0x18003bb9c  mov     rbp, rax
0x18003bb9f  test    esi, esi
0x18003bba1  js      loc_18003BC47
0x18003bba7  cmp     esi, 7
0x18003bbaa  jnb     loc_18003BC47
0x18003bbb0  lea     r15, __ImageBase
0x18003bbb7  mov     byte ptr [rsp+68h+arg_8], 0
0x18003bbbc  mov     r14, rsi
0x18003bbbf  lea     r8, [rsp+68h+arg_8]; unsigned __int16 *
0x18003bbc4  mov     rsi, ds:rva off_180070EA0[r15+rsi*8]; "HKEY_CLASSES_ROOT\\" ...
0x18003bbcc  mov     rdx, rdi; unsigned __int16 *
0x18003bbcf  mov     rcx, rsi; this
0x18003bbd2  call    ?IsCallerAllowedToWriteToRegistryPath@ProtectedSettingsNamespaceMapper@WaasMedic@@YAJPEBG0AEA_N@Z; WaasMedic::ProtectedSettingsNamespaceMapper::IsCallerAllowedToWriteToRegistryPath(ushort const *,ushort const *,bool &)
0x18003bbd7  mov     ebx, eax
0x18003bbd9  test    eax, eax
0x18003bbdb  jns     short loc_18003BBF6
0x18003bbdd  mov     r9d, eax
0x18003bbe0  lea     rdx, aCouldNotVerify_0; "Could not verify access to registry pat"...
0x18003bbe7  mov     r8, rdi
0x18003bbea  mov     ecx, 2; unsigned __int8
0x18003bbef  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003bbf4  jmp     short loc_18003BC60
0x18003bbf6  cmp     byte ptr [rsp+68h+arg_8], 0
0x18003bbfb  jnz     short loc_18003BC10
0x18003bbfd  mov     ebx, 80070005h
0x18003bc02  lea     rdx, aCallerIsNotGra; "Caller is not granted access to write p"...
0x18003bc09  mov     ecx, 3
0x18003bc0e  jmp     short loc_18003BC58
0x18003bc10  mov     r9, [rsp+68h+arg_20]; unsigned __int16 *
0x18003bc18  mov     r8, rbp; unsigned __int16 *
0x18003bc1b  mov     rcx, ds:rva qword_180085718[r15+r14*8]; this
0x18003bc23  mov     rdx, rdi; HKEY
0x18003bc26  mov     byte ptr [rsp+68h+var_48], 1; struct tagVARIANT *
0x18003bc2b  call    ?RegSetValueFromVariant@WaasMedic@@YAJPEAUHKEY__@@PEBG1PEAUtagVARIANT@@_N@Z; WaasMedic::RegSetValueFromVariant(HKEY__ *,ushort const *,ushort const *,tagVARIANT *,bool)
0x18003bc30  mov     ebx, eax
0x18003bc32  test    eax, eax
0x18003bc34  jns     short loc_18003BC60
0x18003bc36  mov     r8d, eax
0x18003bc39  lea     rdx, aCallerWasAllow_0; "Caller was allowed to write under this "...
0x18003bc40  mov     ecx, 3
0x18003bc45  jmp     short loc_18003BC5B
0x18003bc47  xor     esi, esi
0x18003bc49  lea     rdx, aErrorWhileAtte_0; "Error while attempting to determine bas"...
0x18003bc50  mov     ebx, 8000000Bh
0x18003bc55  lea     ecx, [rsi+2]; unsigned __int8
0x18003bc58  mov     r8d, ebx
0x18003bc5b  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003bc60  mov     r9, rbp; unsigned __int16 *
0x18003bc63  mov     r8, rdi; unsigned __int16 *
0x18003bc66  mov     rdx, rsi; unsigned __int16 *
0x18003bc69  mov     ecx, ebx; int
0x18003bc6b  call    ?ReportRegistryValueProtectionResult@TelemetryProvider@WaasMedic@@SAXJPEBG00_N@Z; WaasMedic::TelemetryProvider::ReportRegistryValueProtectionResult(long,ushort const *,ushort const *,ushort const *,bool)
0x18003bc70  mov     eax, ebx
0x18003bc72  add     rsp, 38h
0x18003bc76  pop     r15
0x18003bc78  pop     r14
0x18003bc7a  pop     rdi
0x18003bc7b  pop     rsi
0x18003bc7c  pop     rbp
0x18003bc7d  pop     rbx
0x18003bc7e  retn
```
