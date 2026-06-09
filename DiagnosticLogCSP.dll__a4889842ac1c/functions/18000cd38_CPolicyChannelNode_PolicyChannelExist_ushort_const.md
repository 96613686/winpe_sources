# CPolicyChannelNode::PolicyChannelExist(ushort const *)

- ea: `0x18000cd38`
- end: `0x18000cebf`
- name: `?PolicyChannelExist@CPolicyChannelNode@@CA_NPEBG@Z`
- size: `391`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000bf50`

## callees

- `0x1800011a4`
- `0x180001b60`
- `0x180006518`
- `0x18000cd38`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x18000cd8f`
- `ntdll!RtlGetPersistedStateLocation` at `0x18000cd8f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ce56`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ce56`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ce47`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ce47`

## pseudocode

```c
char __fastcall CPolicyChannelNode::PolicyChannelExist(const unsigned __int16 *a1)
{
  unsigned int v2; // ebx
  __int64 v3; // r9
  __int64 v4; // rcx
  const wchar_t *v5; // rdx
  __int64 v6; // r8
  _WORD *v7; // rax
  _WORD *v8; // rcx
  unsigned int v10; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  const WCHAR *v12; // [rsp+50h] [rbp-B0h] BYREF
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
    if ( (unsigned int)dword_180048E90 > 5 )
    {
      v10 = v2;
      if ( !a1 )
        a1 = &String2;
      v12 = a1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (__int64)v8,
        (__int64)&byte_18003F047,
        v6,
        v3,
        &v12,
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
0x18000cd38  push    rbp
0x18000cd3a  push    rbx
0x18000cd3b  push    rsi
0x18000cd3c  push    rdi
0x18000cd3d  lea     rbp, [rsp-778h]
0x18000cd45  sub     rsp, 878h
0x18000cd4c  mov     rax, cs:__security_cookie
0x18000cd53  xor     rax, rsp
0x18000cd56  mov     [rbp+790h+var_30], rax
0x18000cd5d  xor     esi, esi
0x18000cd5f  lea     rax, [rsp+890h+var_830]
0x18000cd64  mov     [rsp+890h+var_860], rsi
0x18000cd69  mov     rdi, rcx
0x18000cd6c  mov     dword ptr [rsp+890h+var_868], 400h
0x18000cd74  lea     rcx, aWinevt; "WINEVT"
0x18000cd7b  xor     r9d, r9d
0x18000cd7e  mov     [rsp+890h+phkResult], rax
0x18000cd83  xor     r8d, r8d
0x18000cd86  mov     [rsp+890h+hKey], rsi
0x18000cd8b  xor     edx, edx
0x18000cd8d  mov     ebx, esi
0x18000cd8f  call    cs:__imp_RtlGetPersistedStateLocation
0x18000cd95  mov     r10d, 200h
0x18000cd9b  test    eax, eax
0x18000cd9d  jns     short loc_18000CDFA
0x18000cd9f  mov     ecx, 7FFFFFFEh
0x18000cda4  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000cdab  mov     r8d, r10d
0x18000cdae  lea     rax, [rsp+890h+var_830]
0x18000cdb3  test    rcx, rcx
0x18000cdb6  jz      short loc_18000CDD7
0x18000cdb8  movzx   r9d, word ptr [rdx]
0x18000cdbc  test    r9w, r9w
0x18000cdc0  jz      short loc_18000CDD7
0x18000cdc2  mov     [rax], r9w
0x18000cdc6  add     rdx, 2
0x18000cdca  add     rax, 2
0x18000cdce  dec     rcx
0x18000cdd1  sub     r8, 1
0x18000cdd5  jnz     short loc_18000CDB3
0x18000cdd7  test    r8, r8
0x18000cdda  lea     rcx, [rax-2]
0x18000cdde  cmovnz  rcx, rax
0x18000cde2  mov     rax, r8
0x18000cde5  neg     rax
0x18000cde8  sbb     ebx, ebx
0x18000cdea  not     ebx
0x18000cdec  mov     [rcx], si
0x18000cdef  and     ebx, 8007007Ah
0x18000cdf5  test    r8, r8
0x18000cdf8  jz      short loc_18000CE60
0x18000cdfa  lea     rax, aPolicies; "Policies"
0x18000ce01  mov     [rsp+890h+var_868], rdi
0x18000ce06  lea     r9, [rsp+890h+var_830]
0x18000ce0b  mov     [rsp+890h+phkResult], rax
0x18000ce10  lea     r8, aSSS; "%s\\%s\\%s"
0x18000ce17  mov     rdx, r10; unsigned __int64
0x18000ce1a  lea     rcx, [rbp+790h+SubKey]; unsigned __int16 *
0x18000ce21  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ce26  lea     rcx, [rsp+890h+hKey]
0x18000ce2b  mov     r9d, 20019h; samDesired
0x18000ce31  mov     [rsp+890h+phkResult], rcx; phkResult
0x18000ce36  lea     rdx, [rbp+790h+SubKey]; lpSubKey
0x18000ce3d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ce44  xor     r8d, r8d; ulOptions
0x18000ce47  call    cs:__imp_RegOpenKeyExW
0x18000ce4d  test    eax, eax
0x18000ce4f  jnz     short loc_18000CE60
0x18000ce51  mov     rcx, [rsp+890h+hKey]; hKey
0x18000ce56  call    cs:__imp_RegCloseKey
0x18000ce5c  mov     al, 1
0x18000ce5e  jmp     short loc_18000CEA4
0x18000ce60  mov     eax, cs:dword_180048E90
0x18000ce66  cmp     eax, 5
0x18000ce69  jbe     short loc_18000CEA2
0x18000ce6b  test    rdi, rdi
0x18000ce6e  mov     [rsp+890h+var_850], ebx
0x18000ce72  lea     rax, String2
0x18000ce79  cmovz   rdi, rax
0x18000ce7d  lea     rdx, byte_18003F047
0x18000ce84  lea     rax, [rsp+890h+var_850]
0x18000ce89  mov     [rsp+890h+var_840], rdi
0x18000ce8e  mov     [rsp+890h+var_868], rax
0x18000ce93  lea     rax, [rsp+890h+var_840]
0x18000ce98  mov     [rsp+890h+phkResult], rax
0x18000ce9d  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000cea2  xor     al, al
0x18000cea4  mov     rcx, [rbp+790h+var_30]
0x18000ceab  xor     rcx, rsp; StackCookie
0x18000ceae  call    __security_check_cookie
0x18000ceb3  add     rsp, 878h
0x18000ceba  pop     rdi
0x18000cebb  pop     rsi
0x18000cebc  pop     rbx
0x18000cebd  pop     rbp
0x18000cebe  retn
```
