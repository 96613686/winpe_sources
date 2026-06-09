# Windows::Compat::Inventory::MareDataWriter::UpdateCacheAfterCollection(void)

- ea: `0x1800257a8`
- end: `0x180025a1a`
- name: `?UpdateCacheAfterCollection@MareDataWriter@Inventory@Compat@Windows@@AEAAJXZ`
- size: `626`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::MareDataWriter *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800172a0`

## callees

- `0x180004ea0`
- `0x180011fcc`
- `0x1800134b8`
- `0x180013ad4`
- `0x180015b48`
- `0x180016828`
- `0x180016a3c`
- `0x18001de34`
- `0x1800241fc`
- `0x1800257a8`
- `0x18002f95c`
- `0x18004c020`

## string_xrefs

- `0x180025801`: `TelCacheProvider::BatchBegin failed [%#x]`
- `0x180025812`: `Windows::Compat::Inventory::MareDataWriter::UpdateCacheAfterCollection`
- `0x180025889`: `Windows::Compat::Inventory::MareDataWriter::UpdateCacheAfterCollection`
- `0x1800258fb`: `Windows::Compat::Inventory::MareDataWriter::UpdateCacheAfterCollection`
- `0x1800259ca`: `Windows::Compat::Inventory::MareDataWriter::UpdateCacheAfterCollection`
- `0x18002587c`: `TelCacheProvider::AddItem failed [%#x]`
- `0x1800258ee`: `%d MareApps added to cache`
- `0x18002591a`: `TelCacheProvider::BatchEnd failed [%#x]`
- `0x1800259bd`: `TelCacheProvider::SetMetadata failed [%#x]`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Windows::Compat::Inventory::MareDataWriter::UpdateCacheAfterCollection(
        Windows::Compat::Inventory::MareDataWriter *this)
{
  TelCacheProvider *v2; // r15
  int UserData; // eax
  unsigned int v4; // ebx
  const char *v5; // r9
  __int64 v6; // r8
  int v7; // esi
  _QWORD *v8; // rbx
  __int64 v9; // rcx
  int v10; // eax
  __int64 **v11; // rcx
  __int64 i; // rax
  __int64 *j; // rcx
  __int64 k; // rbx
  __int64 v15; // rsi
  __int64 UninstallDataFromCacheBySid; // rax
  const unsigned __int16 *v17; // rdx
  int v18; // r14d
  __int64 v20; // [rsp+20h] [rbp-79h]
  __int128 v21; // [rsp+30h] [rbp-69h] BYREF
  __int64 v22; // [rsp+40h] [rbp-59h]
  _BYTE v23[32]; // [rsp+50h] [rbp-49h] BYREF
  unsigned __int16 *v24[4]; // [rsp+70h] [rbp-29h] BYREF
  _BYTE Src[32]; // [rsp+90h] [rbp-9h] BYREF

  v21 = 0;
  v22 = 0;
  Windows::Compat::Inventory::MareApplication::s_updateMode = 1;
  v2 = (Windows::Compat::Inventory::MareDataWriter *)((char *)this + 144);
  UserData = TelCacheProvider::BatchBegin((Windows::Compat::Inventory::MareDataWriter *)((char *)this + 144));
  v4 = UserData;
  if ( UserData < 0 )
  {
    v5 = "TelCacheProvider::BatchBegin failed [%#x]";
    v6 = 1069;
LABEL_3:
    LODWORD(v20) = UserData;
    AslLogCallPrintf(1, "Windows::Compat::Inventory::MareDataWriter::UpdateCacheAfterCollection", v6, v5, v20);
    goto LABEL_35;
  }
  v7 = 0;
  v8 = (_QWORD *)**((_QWORD **)this + 36);
  while ( v8 != *((_QWORD **)this + 36) )
  {
    v9 = v8[8];
    if ( !*(_BYTE *)(v9 + 224) || Windows::Compat::Inventory::MareApplication::s_keepHiddenArps || *(_QWORD *)(v9 + 248) )
    {
      v10 = TelCacheProvider::AddItem(v2, (struct IAmiInventoryItem *)((v9 + 8) & -(__int64)(v9 != 0)));
      if ( v10 < 0 )
        AslLogCallPrintf(
          1,
          "Windows::Compat::Inventory::MareDataWriter::UpdateCacheAfterCollection",
          1081,
          "TelCacheProvider::AddItem failed [%#x]",
          v10);
      ++v7;
    }
    v11 = (__int64 **)v8[2];
    if ( *((_BYTE *)v11 + 25) )
    {
      for ( i = v8[1]; !*(_BYTE *)(i + 25) && v8 == *(_QWORD **)(i + 16); i = *(_QWORD *)(i + 8) )
        v8 = (_QWORD *)i;
      v8 = (_QWORD *)i;
    }
    else
    {
      v8 = (_QWORD *)v8[2];
      for ( j = *v11; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v8 = j;
    }
  }
  AslLogCallPrintf(
    3,
    "Windows::Compat::Inventory::MareDataWriter::UpdateCacheAfterCollection",
    1087,
    "%d MareApps added to cache",
    v7);
  UserData = TelCacheProvider::BatchEnd(v2);
  v4 = UserData;
  if ( UserData < 0 )
  {
    v5 = "TelCacheProvider::BatchEnd failed [%#x]";
    v6 = 1092;
    goto LABEL_3;
  }
  UserData = Windows::Compat::Inventory::MareDataWriter::GetUserData((void **)&v21, 0);
  v4 = UserData;
  if ( UserData < 0 )
  {
    v5 = "GetUserData failed [%#x]";
    v6 = 1099;
    goto LABEL_3;
  }
  v15 = *((_QWORD *)&v21 + 1);
  for ( k = v21; k != v15; k += 96 )
  {
    std::wstring::wstring(v24, k + 64);
    std::wstring::wstring(v23, v24);
    UninstallDataFromCacheBySid = Windows::Compat::Inventory::MareApplication::GetUninstallDataFromCacheBySid(Src);
    if ( *(_QWORD *)(UninstallDataFromCacheBySid + 24) > 7u )
      UninstallDataFromCacheBySid = *(_QWORD *)UninstallDataFromCacheBySid;
    v17 = (const unsigned __int16 *)v24;
    if ( v24[3] > (unsigned __int16 *)7 )
      v17 = v24[0];
    v18 = TelCacheProvider::SetMetadata(v2, v17, (const unsigned __int16 *)UninstallDataFromCacheBySid);
    std::wstring::~wstring(Src);
    if ( v18 < 0 )
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::MareDataWriter::UpdateCacheAfterCollection",
        1110,
        "TelCacheProvider::SetMetadata failed [%#x]",
        v18);
    std::wstring::~wstring(v24);
  }
  v4 = 0;
LABEL_35:
  std::vector<std::tuple<std::wstring,std::wstring,std::wstring>>::~vector<std::tuple<std::wstring,std::wstring,std::wstring>>(&v21);
  return v4;
}

```

## disassembly

```asm
0x1800257a8  push    rbp
0x1800257aa  push    rbx
0x1800257ab  push    rsi
0x1800257ac  push    r13
0x1800257ae  push    r14
0x1800257b0  push    r15
0x1800257b2  lea     rbp, [rsp-2Fh]
0x1800257b7  sub     rsp, 0C8h
0x1800257be  mov     rax, cs:__security_cookie
0x1800257c5  xor     rax, rsp
0x1800257c8  mov     [rbp+57h+var_40], rax
0x1800257cc  mov     r14, rcx
0x1800257cf  xorps   xmm0, xmm0
0x1800257d2  movdqu  [rbp+57h+var_C0], xmm0
0x1800257d7  mov     [rbp+57h+var_B0], 0
0x1800257df  mov     r13d, 1
0x1800257e5  mov     cs:?s_updateMode@MareApplication@Inventory@Compat@Windows@@0W4CacheUpdateMode@1234@A, r13d; Windows::Compat::Inventory::MareApplication::CacheUpdateMode Windows::Compat::Inventory::MareApplication::s_updateMode
0x1800257ec  lea     r15, [rcx+90h]
0x1800257f3  mov     rcx, r15; this
0x1800257f6  call    ?BatchBegin@TelCacheProvider@@QEAAJXZ; TelCacheProvider::BatchBegin(void)
0x1800257fb  mov     ebx, eax
0x1800257fd  test    eax, eax
0x1800257ff  jns     short loc_180025826
0x180025801  lea     r9, aTelcacheprovid_12; "TelCacheProvider::BatchBegin failed [%#"...
0x180025808  mov     r8d, 42Dh
0x18002580e  mov     [rsp+0F0h+var_D0], eax
0x180025812  lea     rdx, aWindowsCompatI_4; "Windows::Compat::Inventory::MareDataWri"...
0x180025819  mov     ecx, r13d
0x18002581c  call    AslLogCallPrintf
0x180025821  jmp     loc_1800259F2
0x180025826  xor     esi, esi
0x180025828  mov     rbx, [r14+120h]
0x18002582f  mov     rbx, [rbx]
0x180025832  cmp     rbx, [r14+120h]
0x180025839  jz      loc_1800258EA
0x18002583f  mov     rcx, [rbx+40h]
0x180025843  cmp     byte ptr [rcx+0E0h], 0
0x18002584a  jz      short loc_18002585F
0x18002584c  cmp     cs:?s_keepHiddenArps@MareApplication@Inventory@Compat@Windows@@0_NA, 0; bool Windows::Compat::Inventory::MareApplication::s_keepHiddenArps
0x180025853  jnz     short loc_18002585F
0x180025855  cmp     qword ptr [rcx+0F8h], 0
0x18002585d  jz      short loc_18002589B
0x18002585f  lea     rax, [rcx+8]
0x180025863  neg     rcx
0x180025866  sbb     rdx, rdx
0x180025869  and     rdx, rax; struct IAmiInventoryItem *
0x18002586c  mov     rcx, r15; this
0x18002586f  call    ?AddItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@@Z; TelCacheProvider::AddItem(IAmiInventoryItem *)
0x180025874  test    eax, eax
0x180025876  jns     short loc_180025898
0x180025878  mov     [rsp+0F0h+var_D0], eax
0x18002587c  lea     r9, aTelcacheprovid_18; "TelCacheProvider::AddItem failed [%#x]"
0x180025883  mov     r8d, 439h
0x180025889  lea     rdx, aWindowsCompatI_4; "Windows::Compat::Inventory::MareDataWri"...
0x180025890  mov     ecx, r13d
0x180025893  call    AslLogCallPrintf
0x180025898  add     esi, r13d
0x18002589b  mov     rcx, [rbx+10h]
0x18002589f  cmp     byte ptr [rcx+19h], 0
0x1800258a3  jz      short loc_1800258C6
0x1800258a5  mov     rax, [rbx+8]
0x1800258a9  jmp     short loc_1800258B8
0x1800258ab  cmp     rbx, [rax+10h]
0x1800258af  jnz     short loc_1800258BE
0x1800258b1  mov     rbx, rax
0x1800258b4  mov     rax, [rax+8]
0x1800258b8  cmp     byte ptr [rax+19h], 0
0x1800258bc  jz      short loc_1800258AB
0x1800258be  mov     rbx, rax
0x1800258c1  jmp     loc_180025832
0x1800258c6  mov     rbx, rcx
0x1800258c9  mov     rcx, [rcx]
0x1800258cc  cmp     byte ptr [rcx+19h], 0
0x1800258d0  jnz     loc_180025832
0x1800258d6  mov     rbx, rcx
0x1800258d9  mov     rax, [rcx]
0x1800258dc  mov     rcx, rax
0x1800258df  cmp     byte ptr [rax+19h], 0
0x1800258e3  jz      short loc_1800258D6
0x1800258e5  jmp     loc_180025832
0x1800258ea  mov     [rsp+0F0h+var_D0], esi
0x1800258ee  lea     r9, aDMareappsAdded; "%d MareApps added to cache"
0x1800258f5  mov     r8d, 43Fh
0x1800258fb  lea     rdx, aWindowsCompatI_4; "Windows::Compat::Inventory::MareDataWri"...
0x180025902  mov     ecx, 3
0x180025907  call    AslLogCallPrintf
0x18002590c  mov     rcx, r15; this
0x18002590f  call    ?BatchEnd@TelCacheProvider@@QEAAJXZ; TelCacheProvider::BatchEnd(void)
0x180025914  mov     ebx, eax
0x180025916  test    eax, eax
0x180025918  jns     short loc_18002592C
0x18002591a  lea     r9, aTelcacheprovid_3; "TelCacheProvider::BatchEnd failed [%#x]"
0x180025921  mov     r8d, 444h
0x180025927  jmp     loc_18002580E
0x18002592c  xor     edx, edx
0x18002592e  lea     rcx, [rbp+57h+var_C0]
0x180025932  call    ?GetUserData@MareDataWriter@Inventory@Compat@Windows@@SAJAEAV?$vector@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V12@@std@@V?$allocator@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V12@@std@@@2@@std@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@6@@Z; Windows::Compat::Inventory::MareDataWriter::GetUserData(std::vector<std::tuple<std::wstring,std::wstring,std::wstring>> &,std::wstring *)
0x180025937  mov     ebx, eax
0x180025939  test    eax, eax
0x18002593b  jns     short loc_18002594F
0x18002593d  lea     r9, aGetuserdataFai; "GetUserData failed [%#x]"
0x180025944  mov     r8d, 44Bh
0x18002594a  jmp     loc_18002580E
0x18002594f  mov     rbx, qword ptr [rbp+57h+var_C0]
0x180025953  mov     rsi, qword ptr [rbp+57h+var_C0+8]
0x180025957  jmp     loc_1800259E7
0x18002595c  lea     rdx, [rbx+40h]
0x180025960  lea     rcx, [rbp+57h+var_80]
0x180025964  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180025969  nop
0x18002596a  lea     rdx, [rbp+57h+var_80]
0x18002596e  lea     rcx, [rbp+57h+var_A0]
0x180025972  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180025977  mov     rdx, rax
0x18002597a  lea     rcx, [rbp+57h+Src]; Src
0x18002597e  call    ?GetUninstallDataFromCacheBySid@MareApplication@Inventory@Compat@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V56@@Z; Windows::Compat::Inventory::MareApplication::GetUninstallDataFromCacheBySid(std::wstring)
0x180025983  nop
0x180025984  cmp     qword ptr [rax+18h], 7
0x180025989  jbe     short loc_18002598E
0x18002598b  mov     rax, [rax]
0x18002598e  lea     rdx, [rbp+57h+var_80]
0x180025992  cmp     [rbp+57h+var_68], 7
0x180025997  cmova   rdx, [rbp+57h+var_80]; unsigned __int16 *
0x18002599c  mov     r8, rax; unsigned __int16 *
0x18002599f  mov     rcx, r15; this
0x1800259a2  call    ?SetMetadata@TelCacheProvider@@QEAAJPEBG0@Z; TelCacheProvider::SetMetadata(ushort const *,ushort const *)
0x1800259a7  mov     r14d, eax
0x1800259aa  lea     rcx, [rbp+57h+Src]
0x1800259ae  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800259b3  test    r14d, r14d
0x1800259b6  jns     short loc_1800259DA
0x1800259b8  mov     [rsp+0F0h+var_D0], r14d
0x1800259bd  lea     r9, aTelcacheprovid_15; "TelCacheProvider::SetMetadata failed [%"...
0x1800259c4  mov     r8d, 456h
0x1800259ca  lea     rdx, aWindowsCompatI_4; "Windows::Compat::Inventory::MareDataWri"...
0x1800259d1  mov     ecx, r13d
0x1800259d4  call    AslLogCallPrintf
0x1800259d9  nop
0x1800259da  lea     rcx, [rbp+57h+var_80]
0x1800259de  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800259e3  add     rbx, 60h ; '`'
0x1800259e7  cmp     rbx, rsi
0x1800259ea  jnz     loc_18002595C
0x1800259f0  xor     ebx, ebx
0x1800259f2  lea     rcx, [rbp+57h+var_C0]
0x1800259f6  call    ??1?$vector@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V12@@std@@V?$allocator@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V12@@std@@@2@@std@@QEAA@XZ; std::vector<std::tuple<std::wstring,std::wstring,std::wstring>>::~vector<std::tuple<std::wstring,std::wstring,std::wstring>>(void)
0x1800259fb  mov     eax, ebx
0x1800259fd  mov     rcx, [rbp+57h+var_40]
0x180025a01  xor     rcx, rsp; StackCookie
0x180025a04  call    __security_check_cookie
0x180025a09  add     rsp, 0C8h
0x180025a10  pop     r15
0x180025a12  pop     r14
0x180025a14  pop     r13
0x180025a16  pop     rsi
0x180025a17  pop     rbx
0x180025a18  pop     rbp
0x180025a19  retn
```
