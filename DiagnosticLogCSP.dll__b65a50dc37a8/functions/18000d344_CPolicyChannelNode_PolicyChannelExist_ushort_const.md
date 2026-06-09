# CPolicyChannelNode::PolicyChannelExist(ushort const *)

- ea: `0x18000d344`
- end: `0x18000d4de`
- name: `?PolicyChannelExist@CPolicyChannelNode@@CA_NPEBG@Z`
- size: `410`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000c4a0`

## callees

- `0x1800011ac`
- `0x180001b90`
- `0x180006498`
- `0x18000d344`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x18000d39b`
- `ntdll!RtlGetPersistedStateLocation` at `0x18000d39b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d46e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d46e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d459`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d459`

## pseudocode

```c
char __fastcall CPolicyChannelNode::PolicyChannelExist(const unsigned __int16 *a1)
{
  unsigned int v2; // ebx
  int v3; // r9d
  __int64 v4; // rcx
  const wchar_t *v5; // rdx
  __int64 v6; // r8
  _WORD *v7; // rax
  _WORD *v8; // rcx
  unsigned int v10; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  const unsigned __int16 *v12; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v13[1024]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[512]; // [rsp+460h] [rbp+360h] BYREF

  hKey = 0;
  v2 = 0;
  if ( (int)RtlGetPersistedStateLocation(L"WINEVT", 0, 0, 0, v13, 1024, 0) < 0 )
  {
    v4 = 2147483646;
    v5 = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WINEVT";
    v6 = 512;
    v7 = v13;
    do
    {
      if ( !v4 )
        break;
      v3 = *v5;
      if ( !(_WORD)v3 )
        break;
      *v7 = v3;
      ++v5;
      ++v7;
      --v4;
      --v6;
    }
    while ( v6 );
    v8 = v7 - 1;
    if ( v6 )
      v8 = v7;
    *v8 = 0;
    v2 = v6 == 0 ? 0x8007007A : 0;
    if ( !v6 )
      goto LABEL_11;
  }
  StringCchPrintfW(SubKey, 0x200u, L"%s\\%s\\%s", v13, L"Policies", a1);
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey) )
  {
LABEL_11:
    if ( (unsigned int)dword_18004AE90 > 5 )
    {
      v10 = v2;
      if ( !a1 )
        a1 = &String2;
      v12 = a1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (_DWORD)v8,
        (unsigned int)&byte_180041047,
        v6,
        v3,
        (__int64)&v12,
        (__int64)&v10);
    }
    return 0;
  }
  else
  {
    RegCloseKey(hKey);
    return 1;
  }
}

```

## disassembly

```asm
0x18000d344  push    rbp
0x18000d346  push    rbx
0x18000d347  push    rsi
0x18000d348  push    rdi
0x18000d349  lea     rbp, [rsp-778h]
0x18000d351  sub     rsp, 878h
0x18000d358  mov     rax, cs:__security_cookie
0x18000d35f  xor     rax, rsp
0x18000d362  mov     [rbp+790h+var_30], rax
0x18000d369  xor     esi, esi
0x18000d36b  lea     rax, [rsp+890h+var_830]
0x18000d370  mov     [rsp+890h+var_860], rsi
0x18000d375  mov     rdi, rcx
0x18000d378  mov     dword ptr [rsp+890h+var_868], 400h
0x18000d380  lea     rcx, aWinevt; "WINEVT"
0x18000d387  xor     r9d, r9d
0x18000d38a  mov     [rsp+890h+phkResult], rax
0x18000d38f  xor     r8d, r8d
0x18000d392  mov     [rsp+890h+hKey], rsi
0x18000d397  xor     edx, edx
0x18000d399  mov     ebx, esi
0x18000d39b  call    cs:__imp_RtlGetPersistedStateLocation
0x18000d3a2  nop     dword ptr [rax+rax+00h]
0x18000d3a7  mov     r10d, 200h
0x18000d3ad  test    eax, eax
0x18000d3af  jns     short loc_18000D40C
0x18000d3b1  mov     ecx, 7FFFFFFEh
0x18000d3b6  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000d3bd  mov     r8d, r10d
0x18000d3c0  lea     rax, [rsp+890h+var_830]
0x18000d3c5  test    rcx, rcx
0x18000d3c8  jz      short loc_18000D3E9
0x18000d3ca  movzx   r9d, word ptr [rdx]
0x18000d3ce  test    r9w, r9w
0x18000d3d2  jz      short loc_18000D3E9
0x18000d3d4  mov     [rax], r9w
0x18000d3d8  add     rdx, 2
0x18000d3dc  add     rax, 2
0x18000d3e0  dec     rcx
0x18000d3e3  sub     r8, 1
0x18000d3e7  jnz     short loc_18000D3C5
0x18000d3e9  test    r8, r8
0x18000d3ec  lea     rcx, [rax-2]
0x18000d3f0  cmovnz  rcx, rax
0x18000d3f4  mov     rax, r8
0x18000d3f7  neg     rax
0x18000d3fa  sbb     ebx, ebx
0x18000d3fc  not     ebx
0x18000d3fe  mov     [rcx], si
0x18000d401  and     ebx, 8007007Ah
0x18000d407  test    r8, r8
0x18000d40a  jz      short loc_18000D47E
0x18000d40c  lea     rax, aPolicies; "Policies"
0x18000d413  mov     [rsp+890h+var_868], rdi
0x18000d418  lea     r9, [rsp+890h+var_830]
0x18000d41d  mov     [rsp+890h+phkResult], rax
0x18000d422  lea     r8, aSSS; "%s\\%s\\%s"
0x18000d429  mov     rdx, r10; unsigned __int64
0x18000d42c  lea     rcx, [rbp+790h+SubKey]; unsigned __int16 *
0x18000d433  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000d438  lea     rcx, [rsp+890h+hKey]
0x18000d43d  mov     r9d, 20019h; samDesired
0x18000d443  mov     [rsp+890h+phkResult], rcx; phkResult
0x18000d448  lea     rdx, [rbp+790h+SubKey]; lpSubKey
0x18000d44f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d456  xor     r8d, r8d; ulOptions
0x18000d459  call    cs:__imp_RegOpenKeyExW
0x18000d460  nop     dword ptr [rax+rax+00h]
0x18000d465  test    eax, eax
0x18000d467  jnz     short loc_18000D47E
0x18000d469  mov     rcx, [rsp+890h+hKey]; hKey
0x18000d46e  call    cs:__imp_RegCloseKey
0x18000d475  nop     dword ptr [rax+rax+00h]
0x18000d47a  mov     al, 1
0x18000d47c  jmp     short loc_18000D4C2
0x18000d47e  mov     eax, cs:dword_18004AE90
0x18000d484  cmp     eax, 5
0x18000d487  jbe     short loc_18000D4C0
0x18000d489  test    rdi, rdi
0x18000d48c  mov     [rsp+890h+var_850], ebx
0x18000d490  lea     rax, String2
0x18000d497  cmovz   rdi, rax
0x18000d49b  lea     rdx, byte_180041047
0x18000d4a2  lea     rax, [rsp+890h+var_850]
0x18000d4a7  mov     [rsp+890h+var_840], rdi
0x18000d4ac  mov     [rsp+890h+var_868], rax
0x18000d4b1  lea     rax, [rsp+890h+var_840]
0x18000d4b6  mov     [rsp+890h+phkResult], rax
0x18000d4bb  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000d4c0  xor     al, al
0x18000d4c2  mov     rcx, [rbp+790h+var_30]
0x18000d4c9  xor     rcx, rsp; StackCookie
0x18000d4cc  call    __security_check_cookie
0x18000d4d1  add     rsp, 878h
0x18000d4d8  pop     rdi
0x18000d4d9  pop     rsi
0x18000d4da  pop     rbx
0x18000d4db  pop     rbp
0x18000d4dc  retn
```
