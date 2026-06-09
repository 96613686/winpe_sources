# CClassContainer::UnregisterAppCategory(_GUID *)

- ea: `0x180023330`
- end: `0x180023441`
- name: `?UnregisterAppCategory@CClassContainer@@UEAAJPEAU_GUID@@@Z`
- size: `273`
- prototype: `__int64 __fastcall(const unsigned __int16 **this, struct _GUID *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config`

## callees

- `0x1800016d0`
- `0x180008f58`
- `0x18001d130`
- `0x180023330`
- `0x18002350c`
- `0x180023cdc`
- `0x180024458`
- `0x180024d94`

## import_xrefs

- `adsldpc!ADSICloseDSObject` at `0x18002340f`
- `adsldpc!ADSICloseDSObject` at `0x18002340f`
- `adsldpc!ADSIDeleteDSObject` at `0x180023402`
- `adsldpc!ADSIDeleteDSObject` at `0x180023402`

## pseudocode

```c
__int64 __fastcall CClassContainer::UnregisterAppCategory(const unsigned __int16 **this, struct _GUID *a2)
{
  const unsigned __int16 *v4; // rdx
  int v5; // ebx
  unsigned int v6; // eax
  __int64 v7; // rdx
  void *v9; // [rsp+30h] [rbp-658h] BYREF
  unsigned __int16 v10[7]; // [rsp+40h] [rbp-648h] BYREF
  _BYTE v11[514]; // [rsp+4Eh] [rbp-63Ah] BYREF
  unsigned __int16 v12[264]; // [rsp+250h] [rbp-438h] BYREF
  unsigned __int16 v13[264]; // [rsp+460h] [rbp-228h] BYREF

  v9 = 0;
  GetRootPath(0, v10);
  v5 = StringCchPrintfW(
         v12,
         0x104u,
         L"%s%s%s",
         L"LDAP://",
         L"CN=AppCategories,CN=Default Domain Policy,CN=System,",
         v11);
  if ( v5 >= 0 )
  {
    if ( (gCsOptions & 1) != 0 )
      v6 = GetADsOpenObjectFlags() | 0x21;
    else
      v6 = 101;
    v5 = DSServerOpenDSObject(this + 74, v12, v6, &v9);
    if ( v5 >= 0 )
    {
      RDNFromGUID(a2, v13);
      v5 = ADSIDeleteDSObject(v9, v13);
      ADSICloseDSObject(v9, v7);
    }
  }
  return RemapErrorCode(v5, v4);
}

```

## disassembly

```asm
0x180023330  mov     [rsp+arg_10], rbx
0x180023335  mov     [rsp+arg_18], rsi
0x18002333a  push    rdi
0x18002333b  sub     rsp, 680h
0x180023342  mov     rax, cs:__security_cookie
0x180023349  xor     rax, rsp
0x18002334c  mov     [rsp+688h+var_18], rax
0x180023354  mov     rdi, rdx
0x180023357  mov     [rsp+688h+var_658], 0
0x180023360  mov     rsi, rcx
0x180023363  lea     rdx, [rsp+688h+var_648]; unsigned __int16 *
0x180023368  xor     ecx, ecx; struct CServerContext *
0x18002336a  call    ?GetRootPath@@YAJPEAVCServerContext@@PEAGK@Z; GetRootPath(CServerContext *,ushort *,ulong)
0x18002336f  lea     rax, [rsp+688h+var_63A]
0x180023374  mov     edx, 104h; unsigned __int64
0x180023379  mov     [rsp+688h+var_660], rax
0x18002337e  lea     r9, aLdap; "LDAP://"
0x180023385  lea     rax, aCnAppcategorie; "CN=AppCategories,CN=Default Domain Poli"...
0x18002338c  lea     r8, aSSS; "%s%s%s"
0x180023393  mov     [rsp+688h+var_668], rax
0x180023398  lea     rcx, [rsp+688h+var_438]; unsigned __int16 *
0x1800233a0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800233a5  mov     ebx, eax
0x1800233a7  test    eax, eax
0x1800233a9  js      short loc_180023415
0x1800233ab  test    byte ptr cs:?gCsOptions@@3KA, 1; ulong gCsOptions
0x1800233b2  jz      short loc_1800233BE
0x1800233b4  call    ?GetADsOpenObjectFlags@@YAKXZ; GetADsOpenObjectFlags(void)
0x1800233b9  or      eax, 21h
0x1800233bc  jmp     short loc_1800233C3
0x1800233be  mov     eax, 65h ; 'e'
0x1800233c3  lea     rcx, [rsi+250h]; struct CServerContext *
0x1800233ca  mov     r8d, eax; int
0x1800233cd  lea     r9, [rsp+688h+var_658]; void **
0x1800233d2  lea     rdx, [rsp+688h+var_438]; unsigned __int16 *
0x1800233da  call    ?DSServerOpenDSObject@@YAJPEAVCServerContext@@PEBGJPEAPEAX@Z; DSServerOpenDSObject(CServerContext *,ushort const *,long,void * *)
0x1800233df  mov     ebx, eax
0x1800233e1  test    eax, eax
0x1800233e3  js      short loc_180023415
0x1800233e5  lea     rdx, [rsp+688h+var_228]; unsigned __int16 *
0x1800233ed  mov     rcx, rdi; struct _GUID *
0x1800233f0  call    ?RDNFromGUID@@YAHAEBU_GUID@@PEAG@Z; RDNFromGUID(_GUID const &,ushort *)
0x1800233f5  mov     rcx, [rsp+688h+var_658]
0x1800233fa  lea     rdx, [rsp+688h+var_228]
0x180023402  call    cs:__imp_ADSIDeleteDSObject
0x180023408  mov     rcx, [rsp+688h+var_658]
0x18002340d  mov     ebx, eax
0x18002340f  call    cs:__imp_ADSICloseDSObject
0x180023415  mov     ecx, ebx; int
0x180023417  call    ?RemapErrorCode@@YAJJPEBG@Z; RemapErrorCode(long,ushort const *)
0x18002341c  mov     rcx, [rsp+688h+var_18]
0x180023424  xor     rcx, rsp; StackCookie
0x180023427  call    __security_check_cookie
0x18002342c  lea     r11, [rsp+688h+var_8]
0x180023434  mov     rbx, [r11+20h]
0x180023438  mov     rsi, [r11+28h]
0x18002343c  mov     rsp, r11
0x18002343f  pop     rdi
0x180023440  retn
```
