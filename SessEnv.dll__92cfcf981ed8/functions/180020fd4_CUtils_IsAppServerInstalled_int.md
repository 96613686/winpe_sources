# CUtils::IsAppServerInstalled(int &)

- ea: `0x180020fd4`
- end: `0x180021182`
- name: `?IsAppServerInstalled@CUtils@@SAJAEAH@Z`
- size: `430`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180020acc`
- `0x18002fdf0`

## callees

- `0x180001090`
- `0x180001a48`
- `0x180020fd4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021012`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021012`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800210ae`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800210ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021170`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021170`

## string_xrefs

- `0x180021085`: `TSAppCompat`
- `0x180021029`: `Unable to open TS key in HKLM`
- `0x1800210da`: `Successfully read APPCOMPAT key`
- `0x18002112c`: `Unable to read APPCOMPAT key`

## pseudocode

```c
__int64 __fastcall CUtils::IsAppServerInstalled(int *a1)
{
  int v2; // ebx
  unsigned int v3; // eax
  __int64 v4; // r8
  __int64 v5; // r9
  unsigned int v6; // eax
  int v7; // ecx
  const char *v9; // [rsp+40h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-20h] BYREF
  const unsigned __int16 *v11; // [rsp+50h] [rbp-18h] BYREF
  const char *v12; // [rsp+58h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+90h] [rbp+28h] BYREF
  DWORD Type; // [rsp+98h] [rbp+30h] BYREF
  int Data; // [rsp+A0h] [rbp+38h] BYREF
  int v16; // [rsp+A8h] [rbp+40h] BYREF

  *a1 = 0;
  hKey = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Terminal Server", 0, 0x20019u, &hKey);
  if ( v2 )
  {
    if ( (unsigned int)dword_180084170 > 2 )
    {
      v16 = v2;
      v9 = "Unable to open TS key in HKLM";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (__int64)&dword_180084170,
        (__int64)word_180078DD2,
        0,
        0,
        (const unsigned __int16 **)&v9,
        (__int64)&v16);
    }
    if ( v2 > 0 )
      v2 = (unsigned __int16)v2 | 0x80070000;
  }
  else
  {
    cbData = 4;
    v2 = 0;
    Type = 0;
    Data = 0;
    v3 = RegQueryValueExW(hKey, L"TSAppCompat", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( !v3 && cbData == 4 && Type == 4 )
    {
      v6 = dword_180084170;
      v7 = Data;
      *a1 = Data;
      if ( v6 > 4 )
      {
        v16 = v7;
        v9 = "Successfully read APPCOMPAT key";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (__int64)&dword_180084170,
          (__int64)word_180078DFA,
          0,
          0,
          (const unsigned __int16 **)&v9,
          (__int64)&v16);
      }
    }
    else if ( (unsigned int)dword_180084170 > 4 )
    {
      v16 = *a1;
      v12 = "Unable to read APPCOMPAT key";
      v11 = L"TSAppCompat";
      LODWORD(v9) = v3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        v3,
        (__int64)&word_180078E26,
        v4,
        v5,
        (const unsigned __int16 **)&v12,
        (__int64)&v9,
        (__int64)&v16,
        &v11);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180020fd4  push    rbp
0x180020fd6  push    rbx
0x180020fd7  push    rdi
0x180020fd8  push    r15
0x180020fda  mov     rbp, rsp
0x180020fdd  sub     rsp, 68h
0x180020fe1  mov     rdi, rcx
0x180020fe4  mov     dword ptr [rcx], 0
0x180020fea  lea     rax, [rbp+hKey]
0x180020fee  mov     [rbp+hKey], 0
0x180020ff6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180020ffd  mov     [rsp+68h+phkResult], rax; phkResult
0x180021002  mov     r9d, 20019h; samDesired
0x180021008  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Ter"...
0x18002100f  xor     r8d, r8d; ulOptions
0x180021012  call    cs:__imp_RegOpenKeyExW
0x180021018  mov     ebx, eax
0x18002101a  test    eax, eax
0x18002101c  jz      short loc_180021078
0x18002101e  mov     eax, cs:dword_180084170
0x180021024  cmp     eax, 2
0x180021027  jbe     short loc_180021062
0x180021029  lea     rax, aUnableToOpenTs; "Unable to open TS key in HKLM"
0x180021030  mov     [rbp+arg_18], ebx
0x180021033  mov     [rbp+var_28], rax
0x180021037  lea     rdx, word_180078DD2
0x18002103e  lea     rax, [rbp+arg_18]
0x180021042  xor     r9d, r9d
0x180021045  mov     [rsp+68h+lpcbData], rax
0x18002104a  lea     rcx, dword_180084170
0x180021051  lea     rax, [rbp+var_28]
0x180021055  xor     r8d, r8d
0x180021058  mov     [rsp+68h+phkResult], rax
0x18002105d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180021062  test    ebx, ebx
0x180021064  jle     loc_180021167
0x18002106a  movzx   ebx, bx
0x18002106d  or      ebx, 80070000h
0x180021073  jmp     loc_180021167
0x180021078  mov     rcx, [rbp+hKey]; hKey
0x18002107c  lea     rax, [rbp+cbData]
0x180021080  mov     [rsp+68h+lpcbData], rax; lpcbData
0x180021085  lea     r15, aTsappcompat; "TSAppCompat"
0x18002108c  lea     rax, [rbp+Data]
0x180021090  mov     [rbp+cbData], 4
0x180021097  xor     ebx, ebx
0x180021099  mov     [rsp+68h+phkResult], rax; lpData
0x18002109e  lea     r9, [rbp+Type]; lpType
0x1800210a2  mov     [rbp+Type], ebx
0x1800210a5  xor     r8d, r8d; lpReserved
0x1800210a8  mov     [rbp+Data], ebx
0x1800210ab  mov     rdx, r15; lpValueName
0x1800210ae  call    cs:__imp_RegQueryValueExW
0x1800210b4  mov     ecx, eax
0x1800210b6  test    eax, eax
0x1800210b8  jnz     short loc_180021115
0x1800210ba  cmp     [rbp+cbData], 4
0x1800210be  jnz     short loc_180021115
0x1800210c0  cmp     [rbp+Type], 4
0x1800210c4  jnz     short loc_180021115
0x1800210c6  mov     eax, cs:dword_180084170
0x1800210cc  mov     ecx, [rbp+Data]
0x1800210cf  mov     [rdi], ecx
0x1800210d1  cmp     eax, 4
0x1800210d4  jbe     loc_180021167
0x1800210da  lea     rax, aSuccessfullyRe_0; "Successfully read APPCOMPAT key"
0x1800210e1  mov     [rbp+arg_18], ecx
0x1800210e4  mov     [rbp+var_28], rax
0x1800210e8  lea     rdx, word_180078DFA
0x1800210ef  lea     rax, [rbp+arg_18]
0x1800210f3  xor     r9d, r9d
0x1800210f6  mov     [rsp+68h+lpcbData], rax
0x1800210fb  lea     rcx, dword_180084170
0x180021102  lea     rax, [rbp+var_28]
0x180021106  xor     r8d, r8d
0x180021109  mov     [rsp+68h+phkResult], rax
0x18002110e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180021113  jmp     short loc_180021167
0x180021115  mov     eax, cs:dword_180084170
0x18002111b  cmp     eax, 4
0x18002111e  jbe     short loc_180021167
0x180021120  mov     eax, [rdi]
0x180021122  lea     rdx, word_180078E26
0x180021129  mov     [rbp+arg_18], eax
0x18002112c  lea     rax, aUnableToReadAp; "Unable to read APPCOMPAT key"
0x180021133  mov     [rbp+var_10], rax
0x180021137  lea     rax, [rbp+var_18]
0x18002113b  mov     [rsp+68h+var_30], rax
0x180021140  lea     rax, [rbp+arg_18]
0x180021144  mov     [rsp+68h+var_38], rax
0x180021149  lea     rax, [rbp+var_28]
0x18002114d  mov     [rsp+68h+lpcbData], rax
0x180021152  lea     rax, [rbp+var_10]
0x180021156  mov     [rsp+68h+phkResult], rax
0x18002115b  mov     [rbp+var_18], r15
0x18002115f  mov     dword ptr [rbp+var_28], ecx
0x180021162  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x180021167  mov     rcx, [rbp+hKey]; hKey
0x18002116b  test    rcx, rcx
0x18002116e  jz      short loc_180021176
0x180021170  call    cs:__imp_RegCloseKey
0x180021176  mov     eax, ebx
0x180021178  add     rsp, 68h
0x18002117c  pop     r15
0x18002117e  pop     rdi
0x18002117f  pop     rbx
0x180021180  pop     rbp
0x180021181  retn
```
