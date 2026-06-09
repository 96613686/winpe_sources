# CPolicyChannel::RegisterChannel(ushort const *)

- ea: `0x180013ab4`
- end: `0x180013cca`
- name: `?RegisterChannel@CPolicyChannel@@SAJPEBG@Z`
- size: `534`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000c4a0`

## callees

- `0x1800011ac`
- `0x180001b90`
- `0x180006498`
- `0x180011670`
- `0x180011930`
- `0x180013ab4`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x180013b12`
- `ntdll!RtlGetPersistedStateLocation` at `0x180013b12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013c48`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013c5e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013c48`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013c5e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180013c0b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180013c0b`

## pseudocode

```c
__int64 __fastcall CPolicyChannel::RegisterChannel(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3, int a4)
{
  const unsigned __int16 *v4; // rdi
  signed int Key; // ebx
  __int64 v6; // rax
  const wchar_t *v7; // rcx
  __int64 v8; // rdx
  signed int v10; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult[3]; // [rsp+58h] [rbp-A8h] BYREF
  const unsigned __int16 *v12; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey[3]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v14[1024]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR SubKey[512]; // [rsp+490h] [rbp+390h] BYREF

  v4 = a1;
  if ( a1 )
  {
    if ( (int)RtlGetPersistedStateLocation(L"WINEVT", 0, 0, 0, v14, 1024, 0) >= 0 )
      goto LABEL_11;
    v6 = 2147483646;
    v7 = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WINEVT";
    v8 = 512;
    a3 = (unsigned __int16 *)v14;
    do
    {
      if ( !v6 )
        break;
      a4 = *v7;
      if ( !(_WORD)a4 )
        break;
      *a3 = a4;
      ++v7;
      ++a3;
      --v6;
      --v8;
    }
    while ( v8 );
    a1 = a3 - 1;
    Key = v8 == 0 ? 0x8007007A : 0;
    if ( v8 )
      a1 = a3;
    *a1 = 0;
    if ( v8 )
    {
LABEL_11:
      Key = StringCchPrintfW(SubKey, 0x200u, L"%s\\%s", v14, L"Policies");
      if ( Key >= 0 )
      {
        memset(phkResult, 0, sizeof(phkResult));
        if ( !(unsigned int)CRegUtils::OpenKey(SubKey, phkResult)
          || (Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20006u, 0, phkResult, 0), Key >= 0) )
        {
          memset(hKey, 0, sizeof(hKey));
          Key = CRegUtils::CreateKey(phkResult, hKey, v4);
          if ( hKey[0] )
            RegCloseKey(hKey[0]);
        }
        LODWORD(a1) = phkResult[0];
        if ( phkResult[0] )
          RegCloseKey(phkResult[0]);
      }
    }
  }
  else
  {
    Key = -2147024809;
  }
  if ( (unsigned int)dword_18004AE90 > 5 )
  {
    v10 = Key;
    if ( !v4 )
      v4 = &String2;
    v12 = v4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (_DWORD)a1,
      (unsigned int)&byte_180041F8F,
      (_DWORD)a3,
      a4,
      (__int64)&v12,
      (__int64)&v10);
  }
  return (unsigned int)Key;
}

```

## disassembly

```asm
0x180013ab4  push    rbp
0x180013ab6  push    rbx
0x180013ab7  push    rsi
0x180013ab8  push    rdi
0x180013ab9  lea     rbp, [rsp-7A8h]
0x180013ac1  sub     rsp, 8A8h
0x180013ac8  mov     rax, cs:__security_cookie
0x180013acf  xor     rax, rsp
0x180013ad2  mov     [rbp+7C0h+var_30], rax
0x180013ad9  xor     esi, esi
0x180013adb  mov     rdi, rcx
0x180013ade  test    rcx, rcx
0x180013ae1  jnz     short loc_180013AED
0x180013ae3  mov     ebx, 80070057h
0x180013ae8  jmp     loc_180013C6A
0x180013aed  mov     [rsp+8C0h+lpSecurityAttributes], rsi
0x180013af2  lea     rax, [rbp+7C0h+var_830]
0x180013af6  mov     [rsp+8C0h+samDesired], 400h
0x180013afe  lea     rcx, aWinevt; "WINEVT"
0x180013b05  xor     r9d, r9d
0x180013b08  mov     qword ptr [rsp+8C0h+dwOptions], rax
0x180013b0d  xor     r8d, r8d
0x180013b10  xor     edx, edx
0x180013b12  call    cs:__imp_RtlGetPersistedStateLocation
0x180013b19  nop     dword ptr [rax+rax+00h]
0x180013b1e  mov     r10d, 200h
0x180013b24  test    eax, eax
0x180013b26  jns     short loc_180013B83
0x180013b28  mov     eax, 7FFFFFFEh
0x180013b2d  lea     rcx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180013b34  mov     edx, r10d
0x180013b37  lea     r8, [rbp+7C0h+var_830]
0x180013b3b  test    rax, rax
0x180013b3e  jz      short loc_180013B5F
0x180013b40  movzx   r9d, word ptr [rcx]
0x180013b44  test    r9w, r9w
0x180013b48  jz      short loc_180013B5F
0x180013b4a  mov     [r8], r9w
0x180013b4e  add     rcx, 2
0x180013b52  add     r8, 2
0x180013b56  dec     rax
0x180013b59  sub     rdx, 1
0x180013b5d  jnz     short loc_180013B3B
0x180013b5f  mov     rax, rdx
0x180013b62  lea     rcx, [r8-2]
0x180013b66  neg     rax
0x180013b69  sbb     ebx, ebx
0x180013b6b  not     ebx
0x180013b6d  and     ebx, 8007007Ah
0x180013b73  test    rdx, rdx
0x180013b76  cmovnz  rcx, r8
0x180013b7a  mov     [rcx], si
0x180013b7d  jz      loc_180013C6A
0x180013b83  lea     rax, aPolicies; "Policies"
0x180013b8a  mov     rdx, r10; unsigned __int64
0x180013b8d  lea     r9, [rbp+7C0h+var_830]
0x180013b91  mov     qword ptr [rsp+8C0h+dwOptions], rax
0x180013b96  lea     r8, aSS_0; "%s\\%s"
0x180013b9d  lea     rcx, [rbp+7C0h+SubKey]; unsigned __int16 *
0x180013ba4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013ba9  mov     ebx, eax
0x180013bab  test    eax, eax
0x180013bad  js      loc_180013C6A
0x180013bb3  lea     rdx, [rsp+8C0h+var_868]; struct ATL::CRegKey *
0x180013bb8  mov     [rsp+8C0h+var_868], rsi
0x180013bbd  lea     rcx, [rbp+7C0h+SubKey]; lpSubKey
0x180013bc4  mov     [rsp+8C0h+var_860], rsi
0x180013bc9  mov     [rsp+8C0h+var_858], rsi
0x180013bce  call    ?OpenKey@CRegUtils@@SAJPEBGAEAVCRegKey@ATL@@@Z; CRegUtils::OpenKey(ushort const *,ATL::CRegKey &)
0x180013bd3  test    eax, eax
0x180013bd5  jz      short loc_180013C1D
0x180013bd7  mov     [rsp+8C0h+lpdwDisposition], rsi; lpdwDisposition
0x180013bdc  lea     rax, [rsp+8C0h+var_868]
0x180013be1  mov     [rsp+8C0h+phkResult], rax; phkResult
0x180013be6  lea     rdx, [rbp+7C0h+SubKey]; lpSubKey
0x180013bed  mov     [rsp+8C0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180013bf2  xor     r9d, r9d; lpClass
0x180013bf5  mov     [rsp+8C0h+samDesired], 20006h; samDesired
0x180013bfd  xor     r8d, r8d; Reserved
0x180013c00  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180013c07  mov     [rsp+8C0h+dwOptions], esi; dwOptions
0x180013c0b  call    cs:__imp_RegCreateKeyExW
0x180013c12  nop     dword ptr [rax+rax+00h]
0x180013c17  mov     ebx, eax
0x180013c19  test    eax, eax
0x180013c1b  js      short loc_180013C54
0x180013c1d  mov     r8, rdi; unsigned __int16 *
0x180013c20  mov     [rsp+8C0h+hKey], rsi
0x180013c25  lea     rdx, [rsp+8C0h+hKey]; struct ATL::CRegKey *
0x180013c2a  mov     [rbp+7C0h+var_840], rsi
0x180013c2e  lea     rcx, [rsp+8C0h+var_868]; struct ATL::CRegKey *
0x180013c33  mov     [rbp+7C0h+var_838], rsi
0x180013c37  call    ?CreateKey@CRegUtils@@SAJAEAVCRegKey@ATL@@0PEBG@Z; CRegUtils::CreateKey(ATL::CRegKey &,ATL::CRegKey &,ushort const *)
0x180013c3c  mov     rcx, [rsp+8C0h+hKey]; hKey
0x180013c41  mov     ebx, eax
0x180013c43  test    rcx, rcx
0x180013c46  jz      short loc_180013C54
0x180013c48  call    cs:__imp_RegCloseKey
0x180013c4f  nop     dword ptr [rax+rax+00h]
0x180013c54  mov     rcx, [rsp+8C0h+var_868]; hKey
0x180013c59  test    rcx, rcx
0x180013c5c  jz      short loc_180013C6A
0x180013c5e  call    cs:__imp_RegCloseKey
0x180013c65  nop     dword ptr [rax+rax+00h]
0x180013c6a  mov     eax, cs:dword_18004AE90
0x180013c70  cmp     eax, 5
0x180013c73  jbe     short loc_180013CAC
0x180013c75  test    rdi, rdi
0x180013c78  mov     [rsp+8C0h+var_870], ebx
0x180013c7c  lea     rax, String2
0x180013c83  cmovz   rdi, rax
0x180013c87  lea     rdx, byte_180041F8F
0x180013c8e  lea     rax, [rsp+8C0h+var_870]
0x180013c93  mov     [rsp+8C0h+var_850], rdi
0x180013c98  mov     qword ptr [rsp+8C0h+samDesired], rax
0x180013c9d  lea     rax, [rsp+8C0h+var_850]
0x180013ca2  mov     qword ptr [rsp+8C0h+dwOptions], rax
0x180013ca7  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180013cac  mov     eax, ebx
0x180013cae  mov     rcx, [rbp+7C0h+var_30]
0x180013cb5  xor     rcx, rsp; StackCookie
0x180013cb8  call    __security_check_cookie
0x180013cbd  add     rsp, 8A8h
0x180013cc4  pop     rdi
0x180013cc5  pop     rsi
0x180013cc6  pop     rbx
0x180013cc7  pop     rbp
0x180013cc8  retn
```
