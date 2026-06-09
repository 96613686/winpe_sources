# CLayerUIPropPage::Initialize(_ITEMIDLIST const *,IDataObject *,HKEY__ *)

- ea: `0x18000c630`
- end: `0x18000c8dc`
- name: `?Initialize@CLayerUIPropPage@@UEAAJPEFBU_ITEMIDLIST@@PEAUIDataObject@@PEAUHKEY__@@@Z`
- size: `684`
- prototype: `__int64 __fastcall(CLayerUIPropPage *this, const struct _ITEMIDLIST *, struct IDataObject *, HKEY)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x18000b0bc`
- `0x18000b7c8`
- `0x18000bfe8`
- `0x18000c508`
- `0x18000c630`
- `0x18000ca04`
- `0x18000e324`
- `0x18000e440`
- `0x18001623a`
- `0x180016280`
- `0x180017010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000c822`
- `msvcrt!_wcsicmp` at `0x18000c822`
- `ntdll!RtlIsPartialPlaceholder` at `0x18000c77d`
- `ntdll!RtlIsPartialPlaceholder` at `0x18000c77d`
- `KERNEL32!GetLastError` at `0x18000c755`
- `KERNEL32!GetLastError` at `0x18000c755`
- `KERNEL32!FindFirstFileW` at `0x18000c746`
- `KERNEL32!FindFirstFileW` at `0x18000c746`
- `KERNEL32!FindClose` at `0x18000c898`
- `KERNEL32!FindClose` at `0x18000c898`
- `SHLWAPI!PathFindFileNameW` at `0x18000c7a4`
- `SHLWAPI!PathFindFileNameW` at `0x18000c7a4`
- `SHLWAPI!PathFindExtensionW` at `0x18000c794`
- `SHLWAPI!PathFindExtensionW` at `0x18000c794`
- `SHELL32!SHGetItemFromDataObject` at `0x18000c702`
- `SHELL32!SHGetItemFromDataObject` at `0x18000c702`
- `sfc!SfcIsFileProtected` at `0x18000c889`
- `sfc!SfcIsFileProtected` at `0x18000c889`

## pseudocode

```c
__int64 __fastcall CLayerUIPropPage::Initialize(
        CLayerUIPropPage *this,
        const struct _ITEMIDLIST *a2,
        struct IDataObject *a3,
        HKEY a4)
{
  int v6; // ebx
  __int64 v7; // rcx
  struct IShellItem *v8; // rcx
  HANDLE FirstFileW; // r14
  signed int LastError; // eax
  const unsigned __int16 *FileNameW; // rax
  int SdbVersionForFile; // eax
  unsigned __int16 v13; // si
  int ColorManagedShimFromSdb; // eax
  bool v15; // zf
  unsigned __int16 v17[2]; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v18; // [rsp+24h] [rbp-DCh] BYREF
  void *ppv; // [rsp+28h] [rbp-D8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-D0h] BYREF

  v18 = 260;
  v17[0] = 0;
  ppv = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( !a3 )
    return (unsigned int)-2147024809;
  if ( !(unsigned int)CheckGroupPolicy() )
    goto LABEL_4;
  v6 = -2147467259;
  if ( !(unsigned int)InitAppHelpCalls() )
    goto LABEL_38;
  if ( *((struct IDataObject **)this + 3) != a3 )
  {
    ((void (__fastcall *)(struct IDataObject *))a3->lpVtbl->AddRef)(a3);
    v7 = *((_QWORD *)this + 3);
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    *((_QWORD *)this + 3) = a3;
  }
  v6 = SHGetItemFromDataObject(a3, DOGIF_ONLY_IF_ONE, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
  if ( v6 < 0 )
    goto LABEL_38;
  v8 = (struct IShellItem *)ppv;
  *((_WORD *)this + 16) = 0;
  *((_QWORD *)this + 69) = 0;
  if ( RetrieveAndValidateFile(v8, 0, (unsigned __int16 *)this + 16, &v18) )
  {
    FirstFileW = FindFirstFileW((LPCWSTR)this + 16, &FindFileData);
    if ( FirstFileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( v6 >= 0 )
        v6 = -2147467259;
    }
    else
    {
      if ( (unsigned __int8)RtlIsPartialPlaceholder(FindFileData.dwFileAttributes, FindFileData.dwReserved0) )
      {
        v6 = -2147024891;
      }
      else
      {
        *((_QWORD *)this + 69) = PathFindExtensionW((LPCWSTR)this + 16);
        FileNameW = PathFindFileNameW((LPCWSTR)this + 16);
        *((_DWORD *)this + 142) = 1;
        *((_QWORD *)this + 70) = FileNameW;
        SdbVersionForFile = GetSdbVersionForFile((LPCWSTR)this + 16, FileNameW, v17);
        v13 = v17[0];
        if ( SdbVersionForFile )
        {
          switch ( v17[0] )
          {
            case 0x8664:
              *((_DWORD *)this + 142) = 2;
              break;
            case 0xAA64:
              *((_DWORD *)this + 142) = 8;
              break;
            case 0x1C0u:
              *((_DWORD *)this + 142) = 4;
              break;
          }
        }
        if ( !_wcsicmp(*((const wchar_t **)this + 69), L".msi") )
          *((_DWORD *)this + 142) = 16;
        if ( (unsigned int)(*((_DWORD *)this + 142) - 1) <= 1 )
          GetILTypeForFile((LPCWSTR)this + 16, (unsigned int *)this + 143);
        if ( (unsigned int)IsFileKnownGood((unsigned __int16 *)this + 16, v13)
          || ((ColorManagedShimFromSdb = RetrieveColorManagedShimFromSdb((unsigned __int16 *)this + 16, v13),
               v15 = *((_WORD *)this + 16) == 92,
               *((_DWORD *)this + 166) = ColorManagedShimFromSdb,
               !v15)
           || *((_WORD *)this + 17) != 92)
          && SfcIsFileProtected(0, (LPCWSTR)this + 16) )
        {
          v6 = -2147467259;
        }
        else
        {
          v6 = 0;
        }
      }
      FindClose(FirstFileW);
    }
  }
  else
  {
LABEL_4:
    v6 = -2147024891;
  }
LABEL_38:
  if ( ppv )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000c630  mov     [rsp-8+arg_8], rbx
0x18000c635  push    rbp
0x18000c636  push    rsi
0x18000c637  push    rdi
0x18000c638  push    r14
0x18000c63a  push    r15
0x18000c63c  lea     rbp, [rsp-190h]
0x18000c644  sub     rsp, 290h
0x18000c64b  mov     rax, cs:__security_cookie
0x18000c652  xor     rax, rsp
0x18000c655  mov     [rbp+1B0h+var_30], rax
0x18000c65c  xor     eax, eax
0x18000c65e  mov     [rsp+2B0h+var_28C], 104h
0x18000c666  mov     rsi, r8
0x18000c669  mov     [rsp+2B0h+var_290], ax
0x18000c66e  mov     rdi, rcx
0x18000c671  mov     [rsp+2B0h+ppv], rax
0x18000c676  mov     r8d, 250h; Size
0x18000c67c  lea     rcx, [rsp+2B0h+FindFileData]; void *
0x18000c681  xor     edx, edx; Val
0x18000c683  call    memset_0
0x18000c688  test    rsi, rsi
0x18000c68b  jnz     short loc_18000C697
0x18000c68d  mov     ebx, 80070057h
0x18000c692  jmp     loc_18000C8B4
0x18000c697  call    ?CheckGroupPolicy@@YAHXZ; CheckGroupPolicy(void)
0x18000c69c  test    eax, eax
0x18000c69e  jnz     short loc_18000C6AA
0x18000c6a0  mov     ebx, 80070005h
0x18000c6a5  jmp     loc_18000C89E
0x18000c6aa  mov     r15d, 80004005h
0x18000c6b0  mov     ebx, r15d
0x18000c6b3  call    ?InitAppHelpCalls@@YAHXZ; InitAppHelpCalls(void)
0x18000c6b8  test    eax, eax
0x18000c6ba  jz      loc_18000C89E
0x18000c6c0  cmp     [rdi+18h], rsi
0x18000c6c4  jz      short loc_18000C6EE
0x18000c6c6  mov     rax, [rsi]
0x18000c6c9  mov     rcx, rsi
0x18000c6cc  mov     rax, [rax+8]
0x18000c6d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6d5  mov     rcx, [rdi+18h]
0x18000c6d9  test    rcx, rcx
0x18000c6dc  jz      short loc_18000C6EA
0x18000c6de  mov     rax, [rcx]
0x18000c6e1  mov     rax, [rax+10h]
0x18000c6e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6ea  mov     [rdi+18h], rsi
0x18000c6ee  lea     r9, [rsp+2B0h+ppv]; ppv
0x18000c6f3  mov     edx, 8; dwFlags
0x18000c6f8  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18000c6ff  mov     rcx, rsi; pdtobj
0x18000c702  call    cs:__imp_SHGetItemFromDataObject
0x18000c708  mov     ebx, eax
0x18000c70a  test    eax, eax
0x18000c70c  js      loc_18000C89E
0x18000c712  mov     rcx, [rsp+2B0h+ppv]; struct IShellItem *
0x18000c717  lea     rbx, [rdi+20h]
0x18000c71b  xor     eax, eax
0x18000c71d  lea     r9, [rsp+2B0h+var_28C]; unsigned int *
0x18000c722  mov     r8, rbx; unsigned __int16 *
0x18000c725  mov     [rbx], ax
0x18000c728  xor     edx, edx; struct IUnknown *
0x18000c72a  mov     [rdi+228h], rax
0x18000c731  call    ?RetrieveAndValidateFile@@YAHPEAUIShellItem@@PEAUIUnknown@@PEAGPEAK@Z; RetrieveAndValidateFile(IShellItem *,IUnknown *,ushort *,ulong *)
0x18000c736  test    eax, eax
0x18000c738  jz      loc_18000C6A0
0x18000c73e  lea     rdx, [rsp+2B0h+FindFileData]; lpFindFileData
0x18000c743  mov     rcx, rbx; lpFileName
0x18000c746  call    cs:__imp_FindFirstFileW
0x18000c74c  mov     r14, rax
0x18000c74f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000c753  jnz     short loc_18000C775
0x18000c755  call    cs:__imp_GetLastError
0x18000c75b  mov     ebx, eax
0x18000c75d  test    eax, eax
0x18000c75f  jle     short loc_18000C76A
0x18000c761  movzx   ebx, ax
0x18000c764  or      ebx, 80070000h
0x18000c76a  test    ebx, ebx
0x18000c76c  cmovns  ebx, r15d
0x18000c770  jmp     loc_18000C89E
0x18000c775  mov     edx, [rsp+2B0h+FindFileData.dwReserved0]
0x18000c779  mov     ecx, [rsp+2B0h+FindFileData.dwFileAttributes]
0x18000c77d  call    cs:__imp_RtlIsPartialPlaceholder
0x18000c783  test    al, al
0x18000c785  jz      short loc_18000C791
0x18000c787  mov     ebx, 80070005h
0x18000c78c  jmp     loc_18000C895
0x18000c791  mov     rcx, rbx; pszPath
0x18000c794  call    cs:__imp_PathFindExtensionW
0x18000c79a  mov     rcx, rbx; pszPath
0x18000c79d  mov     [rdi+228h], rax
0x18000c7a4  call    cs:__imp_PathFindFileNameW
0x18000c7aa  lea     r8, [rsp+2B0h+var_290]; unsigned __int16 *
0x18000c7af  mov     dword ptr [rdi+238h], 1
0x18000c7b9  mov     rdx, rax; unsigned __int16 *
0x18000c7bc  mov     [rdi+230h], rax
0x18000c7c3  mov     rcx, rbx; lpFileName
0x18000c7c6  call    ?GetSdbVersionForFile@@YAHPEBG0PEAG@Z; GetSdbVersionForFile(ushort const *,ushort const *,ushort *)
0x18000c7cb  movzx   esi, [rsp+2B0h+var_290]
0x18000c7d0  test    eax, eax
0x18000c7d2  jz      short loc_18000C814
0x18000c7d4  mov     eax, 8664h
0x18000c7d9  cmp     si, ax
0x18000c7dc  jnz     short loc_18000C7EA
0x18000c7de  mov     dword ptr [rdi+238h], 2
0x18000c7e8  jmp     short loc_18000C814
0x18000c7ea  mov     eax, 0AA64h
0x18000c7ef  cmp     si, ax
0x18000c7f2  jnz     short loc_18000C800
0x18000c7f4  mov     dword ptr [rdi+238h], 8
0x18000c7fe  jmp     short loc_18000C814
0x18000c800  mov     eax, 1C0h
0x18000c805  cmp     si, ax
0x18000c808  jnz     short loc_18000C814
0x18000c80a  mov     dword ptr [rdi+238h], 4
0x18000c814  mov     rcx, [rdi+228h]; String1
0x18000c81b  lea     rdx, aMsi; ".msi"
0x18000c822  call    cs:__imp__wcsicmp
0x18000c828  test    eax, eax
0x18000c82a  jnz     short loc_18000C836
0x18000c82c  mov     dword ptr [rdi+238h], 10h
0x18000c836  mov     eax, [rdi+238h]
0x18000c83c  dec     eax
0x18000c83e  cmp     eax, 1
0x18000c841  ja      short loc_18000C852
0x18000c843  lea     rdx, [rdi+23Ch]; unsigned int *
0x18000c84a  mov     rcx, rbx; lpFileName
0x18000c84d  call    ?GetILTypeForFile@@YAHPEBGPEAK@Z; GetILTypeForFile(ushort const *,ulong *)
0x18000c852  movzx   edx, si; unsigned __int16
0x18000c855  mov     rcx, rbx; unsigned __int16 *
0x18000c858  call    ?IsFileKnownGood@@YAHPEAGG@Z; IsFileKnownGood(ushort *,ushort)
0x18000c85d  test    eax, eax
0x18000c85f  jz      short loc_18000C866
0x18000c861  mov     ebx, r15d
0x18000c864  jmp     short loc_18000C895
0x18000c866  movzx   edx, si; unsigned __int16
0x18000c869  mov     rcx, rbx; unsigned __int16 *
0x18000c86c  call    ?RetrieveColorManagedShimFromSdb@@YAHPEAGG@Z; RetrieveColorManagedShimFromSdb(ushort *,ushort)
0x18000c871  cmp     word ptr [rbx], 5Ch ; '\'
0x18000c875  mov     [rdi+298h], eax
0x18000c87b  jnz     short loc_18000C884
0x18000c87d  cmp     word ptr [rdi+22h], 5Ch ; '\'
0x18000c882  jz      short loc_18000C893
0x18000c884  mov     rdx, rbx; ProtFileName
0x18000c887  xor     ecx, ecx; RpcHandle
0x18000c889  call    cs:__imp_SfcIsFileProtected
0x18000c88f  test    eax, eax
0x18000c891  jnz     short loc_18000C861
0x18000c893  xor     ebx, ebx
0x18000c895  mov     rcx, r14; hFindFile
0x18000c898  call    cs:__imp_FindClose
0x18000c89e  mov     rcx, [rsp+2B0h+ppv]
0x18000c8a3  test    rcx, rcx
0x18000c8a6  jz      short loc_18000C8B4
0x18000c8a8  mov     rax, [rcx]
0x18000c8ab  mov     rax, [rax+10h]
0x18000c8af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8b4  mov     eax, ebx
0x18000c8b6  mov     rcx, [rbp+1B0h+var_30]
0x18000c8bd  xor     rcx, rsp; StackCookie
0x18000c8c0  call    __security_check_cookie
0x18000c8c5  mov     rbx, [rsp+2B0h+arg_8]
0x18000c8cd  add     rsp, 290h
0x18000c8d4  pop     r15
0x18000c8d6  pop     r14
0x18000c8d8  pop     rdi
0x18000c8d9  pop     rsi
0x18000c8da  pop     rbp
0x18000c8db  retn
```
