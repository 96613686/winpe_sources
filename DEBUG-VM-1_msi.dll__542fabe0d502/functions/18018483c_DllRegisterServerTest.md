# DllRegisterServerTest

- ea: `0x18018483c`
- end: `0x180184a8f`
- name: `DllRegisterServerTest`
- size: `595`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18018e130`

## callees

- `0x180022120`
- `0x180025560`
- `0x18018483c`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180184a56`
- `ADVAPI32!RegCloseKey` at `0x180184a56`
- `ADVAPI32!RegSetValueExW` at `0x1801849fc`
- `ADVAPI32!RegSetValueExW` at `0x180184a41`
- `ADVAPI32!RegSetValueExW` at `0x1801849fc`
- `ADVAPI32!RegSetValueExW` at `0x180184a41`
- `KERNEL32!GetLastError` at `0x18018489d`
- `KERNEL32!GetLastError` at `0x18018489d`
- `KERNEL32!GetModuleFileNameW` at `0x180184893`
- `KERNEL32!GetModuleFileNameW` at `0x180184893`
- `KERNEL32!lstrlenW` at `0x1801849d2`
- `KERNEL32!lstrlenW` at `0x180184a15`
- `KERNEL32!lstrlenW` at `0x1801849d2`
- `KERNEL32!lstrlenW` at `0x180184a15`
- `RPCRT4!NdrDllRegisterProxy` at `0x180184871`
- `RPCRT4!NdrDllRegisterProxy` at `0x180184871`

## pseudocode

```c
HRESULT DllRegisterServerTest()
{
  HRESULT result; // eax
  int v1; // ebx
  int i; // esi
  const unsigned __int16 *v3; // r8
  const unsigned __int16 * near **v4; // rdi
  int v5; // eax
  const unsigned __int16 * near *v6; // rcx
  int v7; // eax
  HKEY hKey[2]; // [rsp+50h] [rbp-E8h] BYREF
  unsigned __int16 v9[80]; // [rsp+60h] [rbp-D8h] BYREF

  result = NdrDllRegisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, &CLSID_PSFactoryBuffer);
  if ( !result )
  {
    if ( GetModuleFileNameW(g_hInstance, &szRegFilePath, 0x103u) )
    {
      v1 = 0;
      word_180307DD6 = 0;
      for ( i = 0; i < 10; ++i )
      {
        result = StringCchPrintfW(&szRegCLSID, 0x28u, L"{%08lX-0000-0000-C000-000000000046}", *(&rgCLSID.Data1 + 4 * i));
        if ( result < 0 )
          return result;
        v3 = (const unsigned __int16 *)(&rgszProgId)[i];
        if ( v3 )
        {
          result = StringCchCopyW(&szRegProgId, 0x28u, v3);
          if ( result < 0 )
            return result;
        }
        v4 = &rgszRegData;
        result = StringCchCopyW(&szRegDescription, 0x64u, (const unsigned __int16 *)(&rgszDescription)[i]);
        if ( result < 0 )
          return result;
        while ( *v4 )
        {
          if ( v4[1] && v4[2] )
          {
            result = StringCchPrintfW(v9, 0x50u, (const unsigned __int16 *)*v4);
            if ( result < 0 )
              return result;
            hKey[0] = 0;
            if ( (unsigned int)((__int64 (__fastcall *)(unsigned __int64, unsigned __int16 *, _QWORD, _QWORD, _DWORD, int, _QWORD, HKEY *, _QWORD))RegCreateKeyAPI)(
                                 0xFFFFFFFF80000000uLL,
                                 v9,
                                 0,
                                 0,
                                 0,
                                 131103,
                                 0,
                                 hKey,
                                 0)
              || (v5 = lstrlenW((LPCWSTR)v4[2]), RegSetValueExW(hKey[0], 0, 0, 1u, (const BYTE *)v4[2], 2 * v5 + 2)) )
            {
              ++v1;
            }
            v6 = v4[3];
            if ( v6 )
            {
              v7 = lstrlenW((LPCWSTR)v6 + 1);
              if ( RegSetValueExW(hKey[0], (LPCWSTR)v4[3], 0, 1u, (const BYTE *)v4[4], 2 * v7 + 2) )
                ++v1;
            }
            v4 += 5;
            RegCloseKey(hKey[0]);
          }
        }
      }
      return v1 != 0 ? 0x80040201 : 0;
    }
    else
    {
      return GetLastError();
    }
  }
  return result;
}

```

## disassembly

```asm
0x18018483c  push    rbx
0x18018483e  push    rbp
0x18018483f  push    rsi
0x180184840  push    rdi
0x180184841  push    r12
0x180184843  sub     rsp, 110h
0x18018484a  mov     rax, cs:__security_cookie
0x180184851  xor     rax, rsp
0x180184854  mov     [rsp+138h+var_38], rax
0x18018485c  mov     rcx, cs:hProxyDll; hDll
0x180184863  lea     r8, CLSID_PSFactoryBuffer; pclsid
0x18018486a  lea     rdx, aProxyFileList; pProxyFileList
0x180184871  call    cs:__imp_NdrDllRegisterProxy
0x180184877  test    eax, eax
0x180184879  jnz     loc_180184A71
0x18018487f  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hModule
0x180184886  lea     rdx, ?szRegFilePath@@3PAGA; lpFilename
0x18018488d  mov     r8d, 103h; nSize
0x180184893  call    cs:__imp_GetModuleFileNameW
0x180184899  test    eax, eax
0x18018489b  jnz     short loc_1801848A8
0x18018489d  call    cs:__imp_GetLastError
0x1801848a3  jmp     loc_180184A71
0x1801848a8  xor     eax, eax
0x1801848aa  lea     r12, cs:180000000h
0x1801848b1  xor     ebx, ebx
0x1801848b3  mov     cs:word_180307DD6, ax
0x1801848ba  xor     esi, esi
0x1801848bc  cmp     esi, 0Ah
0x1801848bf  jge     loc_180184A68
0x1801848c5  movsxd  rbp, esi
0x1801848c8  lea     r8, a08lx00000000C0; "{%08lX-0000-0000-C000-000000000046}"
0x1801848cf  mov     r9, rbp
0x1801848d2  lea     rcx, ?szRegCLSID@@3PAGA; unsigned __int16 *
0x1801848d9  add     r9, r9
0x1801848dc  mov     edx, 28h ; '('; unsigned __int64
0x1801848e1  mov     r9d, dword ptr ds:rva ?rgCLSID@@3QBU_GUID@@B.Data1[r12+r9*8]; _GUID const near * const rgCLSID ...
0x1801848e9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801848ee  test    eax, eax
0x1801848f0  js      loc_180184A71
0x1801848f6  mov     r8, ds:rva ?rgszProgId@@3QBQEBGB[r12+rbp*8]; unsigned __int16 *
0x1801848fe  test    r8, r8
0x180184901  jz      short loc_18018491C
0x180184903  mov     edx, 28h ; '('; unsigned __int64
0x180184908  lea     rcx, ?szRegProgId@@3PAGA; unsigned __int16 *
0x18018490f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180184914  test    eax, eax
0x180184916  js      loc_180184A71
0x18018491c  mov     r8, ds:rva ?rgszDescription@@3QBQEBGB[r12+rbp*8]; unsigned __int16 *
0x180184924  lea     rcx, ?szRegDescription@@3PAGA; unsigned __int16 *
0x18018492b  mov     edx, 64h ; 'd'; unsigned __int64
0x180184930  lea     rdi, ?rgszRegData@@3PAPEBGA; ushort const * near * rgszRegData
0x180184937  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18018493c  test    eax, eax
0x18018493e  js      loc_180184A71
0x180184944  mov     r8, [rdi]; unsigned __int16 *
0x180184947  test    r8, r8
0x18018494a  jz      loc_180184A61
0x180184950  mov     r9, [rdi+8]
0x180184954  test    r9, r9
0x180184957  jz      short loc_180184944
0x180184959  cmp     qword ptr [rdi+10h], 0
0x18018495e  jz      short loc_180184944
0x180184960  mov     edx, 50h ; 'P'; unsigned __int64
0x180184965  lea     rcx, [rsp+138h+var_D8]; unsigned __int16 *
0x18018496a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18018496f  test    eax, eax
0x180184971  js      loc_180184A71
0x180184977  mov     [rsp+138h+var_F8], 0
0x180184980  lea     rax, [rsp+138h+hKey]
0x180184985  mov     [rsp+138h+var_100], rax
0x18018498a  lea     rdx, [rsp+138h+var_D8]
0x18018498f  mov     rax, cs:?RegCreateKeyAPI@@3P6AJPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@ZEA; long (*RegCreateKeyAPI)(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x180184996  xor     r9d, r9d
0x180184999  mov     [rsp+138h+var_108], 0
0x1801849a2  xor     r8d, r8d
0x1801849a5  mov     [rsp+138h+cbData], 2001Fh
0x1801849ad  mov     rcx, 0FFFFFFFF80000000h
0x1801849b4  mov     dword ptr [rsp+138h+lpData], 0
0x1801849bc  mov     [rsp+138h+hKey], 0
0x1801849c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801849ca  test    eax, eax
0x1801849cc  jnz     short loc_180184A06
0x1801849ce  mov     rcx, [rdi+10h]; lpString
0x1801849d2  call    cs:__imp_lstrlenW
0x1801849d8  mov     rcx, [rsp+138h+hKey]; hKey
0x1801849dd  mov     r9d, 1; dwType
0x1801849e3  xor     r8d, r8d; Reserved
0x1801849e6  xor     edx, edx; lpValueName
0x1801849e8  lea     eax, ds:2[rax*2]
0x1801849ef  mov     [rsp+138h+cbData], eax; cbData
0x1801849f3  mov     rax, [rdi+10h]
0x1801849f7  mov     [rsp+138h+lpData], rax; lpData
0x1801849fc  call    cs:__imp_RegSetValueExW
0x180184a02  test    eax, eax
0x180184a04  jz      short loc_180184A08
0x180184a06  inc     ebx
0x180184a08  mov     rcx, [rdi+18h]
0x180184a0c  test    rcx, rcx
0x180184a0f  jz      short loc_180184A4D
0x180184a11  add     rcx, 2; lpString
0x180184a15  call    cs:__imp_lstrlenW
0x180184a1b  mov     rdx, [rdi+18h]; lpValueName
0x180184a1f  mov     r9d, 1; dwType
0x180184a25  mov     rcx, [rsp+138h+hKey]; hKey
0x180184a2a  xor     r8d, r8d; Reserved
0x180184a2d  lea     eax, ds:2[rax*2]
0x180184a34  mov     [rsp+138h+cbData], eax; cbData
0x180184a38  mov     rax, [rdi+20h]
0x180184a3c  mov     [rsp+138h+lpData], rax; lpData
0x180184a41  call    cs:__imp_RegSetValueExW
0x180184a47  test    eax, eax
0x180184a49  jz      short loc_180184A4D
0x180184a4b  inc     ebx
0x180184a4d  mov     rcx, [rsp+138h+hKey]; hKey
0x180184a52  add     rdi, 28h ; '('
0x180184a56  call    cs:__imp_RegCloseKey
0x180184a5c  jmp     loc_180184944
0x180184a61  inc     esi
0x180184a63  jmp     loc_1801848BC
0x180184a68  neg     ebx
0x180184a6a  sbb     eax, eax
0x180184a6c  and     eax, 80040201h
0x180184a71  mov     rcx, [rsp+138h+var_38]
0x180184a79  xor     rcx, rsp; StackCookie
0x180184a7c  call    __security_check_cookie
0x180184a81  add     rsp, 110h
0x180184a88  pop     r12
0x180184a8a  pop     rdi
0x180184a8b  pop     rsi
0x180184a8c  pop     rbp
0x180184a8d  pop     rbx
0x180184a8e  retn
```
