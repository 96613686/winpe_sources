# CPolicyChannelNode::ValueExist(ushort const *,ushort const *)

- ea: `0x18000d6e4`
- end: `0x18000d8ef`
- name: `?ValueExist@CPolicyChannelNode@@CA_NPEBG0@Z`
- size: `523`
- prototype: `bool __fastcall(LPCWSTR lpValueName, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000c4a0`

## callees

- `0x1800011ac`
- `0x180001b90`
- `0x180006498`
- `0x18000d6e4`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x18000d742`
- `ntdll!RtlGetPersistedStateLocation` at `0x18000d742`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d848`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d848`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d860`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d8ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d860`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d8ba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d80d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d80d`

## pseudocode

```c
char __fastcall CPolicyChannelNode::ValueExist(LPCWSTR lpValueName, const unsigned __int16 *a2)
{
  DWORD v4; // edi
  int v5; // r9d
  HKEY v6; // rbx
  const wchar_t *v7; // r8
  __int64 v8; // rcx
  _WORD *v9; // rax
  __int64 v10; // rdx
  _WORD *v11; // rcx
  LSTATUS v12; // eax
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  const unsigned __int16 *v16; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v17[1024]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[512]; // [rsp+460h] [rbp+360h] BYREF

  v4 = 0;
  if ( (int)RtlGetPersistedStateLocation(L"WINEVT", 0, 0, 0, v17, 1024, 0) < 0 )
  {
    v6 = 0;
    v7 = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WINEVT";
    v8 = 2147483646;
    v9 = v17;
    v10 = 512;
    do
    {
      if ( !v8 )
        break;
      v5 = *v7;
      if ( !(_WORD)v5 )
        break;
      *v9 = v5;
      ++v7;
      ++v9;
      --v8;
      --v10;
    }
    while ( v10 );
    v11 = v9 - 1;
    if ( v10 )
      v11 = v9;
    *v11 = 0;
    v4 = v10 == 0 ? 0x8007007A : 0;
    if ( !v10 )
      goto LABEL_16;
  }
  StringCchPrintfW(SubKey, 0x200u, L"%s\\%s\\%s", v17, L"Policies", a2);
  hKey = 0;
  v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20119u, &hKey);
  if ( v12 )
  {
    v6 = 0;
    if ( v12 < 0 )
      goto LABEL_16;
  }
  else
  {
    v6 = hKey;
  }
  Type = 0;
  if ( !RegQueryValueExW(v6, lpValueName, 0, &Type, 0, 0) )
  {
    if ( v6 )
      RegCloseKey(v6);
    return 1;
  }
LABEL_16:
  if ( (unsigned int)dword_18004AE90 > 5 )
  {
    Type = v4;
    if ( !a2 )
      a2 = &String2;
    v16 = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (_DWORD)v11,
      (unsigned int)byte_180041093,
      (_DWORD)v7,
      v5,
      (__int64)&v16,
      (__int64)&Type);
  }
  if ( v6 )
    RegCloseKey(v6);
  return 0;
}

```

## disassembly

```asm
0x18000d6e4  mov     [rsp-8+arg_10], rbx
0x18000d6e9  push    rbp
0x18000d6ea  push    rsi
0x18000d6eb  push    rdi
0x18000d6ec  push    r14
0x18000d6ee  push    r15
0x18000d6f0  lea     rbp, [rsp-770h]
0x18000d6f8  sub     rsp, 870h
0x18000d6ff  mov     rax, cs:__security_cookie
0x18000d706  xor     rax, rsp
0x18000d709  mov     [rbp+790h+var_30], rax
0x18000d710  xor     r15d, r15d
0x18000d713  lea     rax, [rsp+890h+var_830]
0x18000d718  mov     [rsp+890h+var_860], r15
0x18000d71d  mov     rsi, rdx
0x18000d720  mov     r14, rcx
0x18000d723  mov     dword ptr [rsp+890h+lpcbData], 400h
0x18000d72b  xor     r9d, r9d
0x18000d72e  mov     [rsp+890h+phkResult], rax
0x18000d733  xor     r8d, r8d
0x18000d736  lea     rcx, aWinevt; "WINEVT"
0x18000d73d  xor     edx, edx
0x18000d73f  mov     edi, r15d
0x18000d742  call    cs:__imp_RtlGetPersistedStateLocation
0x18000d749  nop     dword ptr [rax+rax+00h]
0x18000d74e  mov     r10d, 200h
0x18000d754  test    eax, eax
0x18000d756  jns     short loc_18000D7BB
0x18000d758  mov     ebx, r15d
0x18000d75b  lea     r8, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000d762  mov     ecx, 7FFFFFFEh
0x18000d767  lea     rax, [rsp+890h+var_830]
0x18000d76c  mov     edx, r10d
0x18000d76f  test    rcx, rcx
0x18000d772  jz      short loc_18000D793
0x18000d774  movzx   r9d, word ptr [r8]
0x18000d778  test    r9w, r9w
0x18000d77c  jz      short loc_18000D793
0x18000d77e  mov     [rax], r9w
0x18000d782  add     r8, 2
0x18000d786  add     rax, 2
0x18000d78a  dec     rcx
0x18000d78d  sub     rdx, 1
0x18000d791  jnz     short loc_18000D76F
0x18000d793  test    rdx, rdx
0x18000d796  lea     rcx, [rax-2]
0x18000d79a  cmovnz  rcx, rax
0x18000d79e  mov     rax, rdx
0x18000d7a1  neg     rax
0x18000d7a4  sbb     edi, edi
0x18000d7a6  not     edi
0x18000d7a8  mov     [rcx], r15w
0x18000d7ac  and     edi, 8007007Ah
0x18000d7b2  test    rdx, rdx
0x18000d7b5  jz      loc_18000D870
0x18000d7bb  lea     rax, aPolicies; "Policies"
0x18000d7c2  mov     [rsp+890h+lpcbData], rsi
0x18000d7c7  lea     r9, [rsp+890h+var_830]
0x18000d7cc  mov     [rsp+890h+phkResult], rax
0x18000d7d1  lea     r8, aSSS; "%s\\%s\\%s"
0x18000d7d8  mov     rdx, r10; unsigned __int64
0x18000d7db  lea     rcx, [rbp+790h+SubKey]; unsigned __int16 *
0x18000d7e2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000d7e7  lea     rax, [rsp+890h+hKey]
0x18000d7ec  mov     [rsp+890h+hKey], r15
0x18000d7f1  mov     r9d, 20119h; samDesired
0x18000d7f7  mov     [rsp+890h+phkResult], rax; phkResult
0x18000d7fc  xor     r8d, r8d; ulOptions
0x18000d7ff  lea     rdx, [rbp+790h+SubKey]; lpSubKey
0x18000d806  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d80d  call    cs:__imp_RegOpenKeyExW
0x18000d814  nop     dword ptr [rax+rax+00h]
0x18000d819  test    eax, eax
0x18000d81b  jnz     short loc_18000D824
0x18000d81d  mov     rbx, [rsp+890h+hKey]
0x18000d822  jmp     short loc_18000D82B
0x18000d824  mov     rbx, r15
0x18000d827  test    eax, eax
0x18000d829  js      short loc_18000D870
0x18000d82b  mov     [rsp+890h+lpcbData], r15; lpcbData
0x18000d830  lea     r9, [rsp+890h+Type]; lpType
0x18000d835  xor     r8d, r8d; lpReserved
0x18000d838  mov     [rsp+890h+phkResult], r15; lpData
0x18000d83d  mov     rdx, r14; lpValueName
0x18000d840  mov     [rsp+890h+Type], r15d
0x18000d845  mov     rcx, rbx; hKey
0x18000d848  call    cs:__imp_RegQueryValueExW
0x18000d84f  nop     dword ptr [rax+rax+00h]
0x18000d854  test    eax, eax
0x18000d856  jnz     short loc_18000D870
0x18000d858  test    rbx, rbx
0x18000d85b  jz      short loc_18000D86C
0x18000d85d  mov     rcx, rbx; hKey
0x18000d860  call    cs:__imp_RegCloseKey
0x18000d867  nop     dword ptr [rax+rax+00h]
0x18000d86c  mov     al, 1
0x18000d86e  jmp     short loc_18000D8C8
0x18000d870  mov     eax, cs:dword_18004AE90
0x18000d876  cmp     eax, 5
0x18000d879  jbe     short loc_18000D8B2
0x18000d87b  test    rsi, rsi
0x18000d87e  mov     [rsp+890h+Type], edi
0x18000d882  lea     rax, String2
0x18000d889  cmovz   rsi, rax
0x18000d88d  lea     rdx, byte_180041093
0x18000d894  lea     rax, [rsp+890h+Type]
0x18000d899  mov     [rsp+890h+var_840], rsi
0x18000d89e  mov     [rsp+890h+lpcbData], rax
0x18000d8a3  lea     rax, [rsp+890h+var_840]
0x18000d8a8  mov     [rsp+890h+phkResult], rax
0x18000d8ad  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000d8b2  test    rbx, rbx
0x18000d8b5  jz      short loc_18000D8C6
0x18000d8b7  mov     rcx, rbx; hKey
0x18000d8ba  call    cs:__imp_RegCloseKey
0x18000d8c1  nop     dword ptr [rax+rax+00h]
0x18000d8c6  xor     al, al
0x18000d8c8  mov     rcx, [rbp+790h+var_30]
0x18000d8cf  xor     rcx, rsp; StackCookie
0x18000d8d2  call    __security_check_cookie
0x18000d8d7  mov     rbx, [rsp+890h+arg_10]
0x18000d8df  add     rsp, 870h
0x18000d8e6  pop     r15
0x18000d8e8  pop     r14
0x18000d8ea  pop     rdi
0x18000d8eb  pop     rsi
0x18000d8ec  pop     rbp
0x18000d8ed  retn
```
