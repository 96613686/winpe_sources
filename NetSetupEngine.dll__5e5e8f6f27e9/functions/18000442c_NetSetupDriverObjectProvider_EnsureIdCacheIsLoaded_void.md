# NetSetupDriverObjectProvider::EnsureIdCacheIsLoaded(void)

- ea: `0x18000442c`
- end: `0x1800047d8`
- name: `?EnsureIdCacheIsLoaded@NetSetupDriverObjectProvider@@AEBAXXZ`
- size: `940`
- prototype: `void __fastcall(NetSetupDriverObjectProvider *__hidden this)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180013310`
- `0x18003fc40`

## callees

- `0x18000442c`
- `0x1800047e0`
- `0x180004f34`
- `0x180005020`
- `0x180005660`
- `0x180006eb0`
- `0x180011614`
- `0x180012108`
- `0x180029d20`
- `0x180034a80`
- `0x18003accc`
- `0x18003ad28`
- `0x18005852c`
- `0x180064704`
- `0x18006f07c`
- `0x1800810a2`
- `0x1800810d0`

## import_xrefs

- `msvcrt!swscanf_s` at `0x180004584`
- `msvcrt!swscanf_s` at `0x180004584`
- `msvcrt!swprintf_s` at `0x18000463e`
- `msvcrt!swprintf_s` at `0x18000463e`
- `msvcrt!wcscat_s` at `0x18000465c`
- `msvcrt!wcscat_s` at `0x18000465c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800044bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800044e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004697`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800044bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800044e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004697`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall NetSetupDriverObjectProvider::EnsureIdCacheIsLoaded(NetSetupDriverObjectProvider *this)
{
  _QWORD *v2; // rbx
  HKEY *StoreKey; // rax
  HKEY v4; // rcx
  unsigned int NumSubKeys; // r14d
  int i; // eax
  __int64 v7; // rcx
  const wchar_t *v8; // rcx
  unsigned int j; // edx
  _QWORD *v10; // rax
  _QWORD *v11; // rsi
  const wchar_t *SystemStorePath; // rax
  __int64 v13; // rsi
  bool v14; // al
  __int64 v15; // rcx
  __int128 v16; // xmm0
  __int64 v17; // rdx
  int v18; // eax
  unsigned __int64 v19; // rsi
  unsigned int v20; // esi
  HKEY hKey; // [rsp+58h] [rbp-B0h] BYREF
  HKEY *v22; // [rsp+60h] [rbp-A8h] BYREF
  int v23; // [rsp+68h] [rbp-A0h]
  __int64 v24; // [rsp+6Ch] [rbp-9Ch]
  __int128 v25; // [rsp+74h] [rbp-94h] BYREF
  __int64 v26; // [rsp+88h] [rbp-80h]
  __int128 v27; // [rsp+90h] [rbp-78h] BYREF
  HKEY v28; // [rsp+A0h] [rbp-68h] BYREF
  HKEY *v29; // [rsp+A8h] [rbp-60h]
  unsigned int v30; // [rsp+B0h] [rbp-58h]
  wchar_t *Buffer[3]; // [rsp+B8h] [rbp-50h] BYREF
  unsigned __int64 v32; // [rsp+D0h] [rbp-38h]
  void *Block[4]; // [rsp+D8h] [rbp-30h] BYREF
  wchar_t Destination[264]; // [rsp+F8h] [rbp-10h] BYREF

  v26 = -2;
  if ( !*((_BYTE *)this + 12) )
  {
    v2 = (_QWORD *)((char *)this + 16);
    *((_QWORD *)this + 3) = *((_QWORD *)this + 2);
    StoreKey = (HKEY *)NetSetupDriverStore::GetStoreKey((char *)this + 104, &hKey, *((unsigned int *)this + 2));
    v4 = *StoreKey;
    *StoreKey = 0;
    v28 = v4;
    v29 = &v28;
    NumSubKeys = RegistryKey::GetNumSubKeys((RegistryKey *)&v28);
    v30 = NumSubKeys;
    if ( hKey )
    {
      RegCloseKey(hKey);
      NumSubKeys = v30;
    }
    v22 = v29;
    for ( i = 0; ; i = v23 + 1 )
    {
      v23 = i;
      if ( i == NumSubKeys )
        break;
      RegistryKeyIterator::operator*((__int64)&v22, (unsigned __int64)Buffer);
      v27 = 0;
      v8 = (const wchar_t *)Buffer;
      if ( v32 >= 8 )
        v8 = Buffer[0];
      if ( swscanf_s(
             v8,
             L"{%x-%hx-%hx-%4hx-%4hx%4hx%4hx}",
             &v27,
             (char *)&v27 + 4,
             (char *)&v27 + 6,
             (char *)&v27 + 8,
             (char *)&v27 + 10,
             (char *)&v27 + 12,
             (char *)&v27 + 14) == 7 )
      {
        for ( j = 0; j < 8; j += 2 )
          *(_WORD *)((char *)&v27 + (int)j + 8) = __ROR2__(*(_WORD *)((char *)&v27 + (int)j + 8), 8);
        memset_0(Destination, 0, 0x208u);
        HIDWORD(v24) = *((_DWORD *)this + 2);
        v25 = v27;
        v10 = (_QWORD *)StringFromGuid(Block, &v25);
        v11 = v10;
        if ( v10[3] >= 8u )
          v11 = (_QWORD *)*v10;
        SystemStorePath = NetSetupDriverStore::GetSystemStorePath(HIDWORD(v24));
        swprintf_s(Destination, 0x104u, L"Control\\NetworkSetup2\\%s\\%s", SystemStorePath, v11);
        if ( Block[3] >= (void *)8 )
          operator delete(Block[0]);
        wcscat_s(Destination, 0x104u, L"\\Properties");
        v13 = *(_QWORD *)RegistryKey::TryOpenSubKey(
                           (HKEY *)(*((_QWORD *)this + 20) + 24LL),
                           (HKEY)&hKey,
                           Destination,
                           8u,
                           0);
        if ( hKey )
          RegCloseKey(hKey);
        if ( v13 )
        {
          v14 = (unsigned __int64)&v27 < v2[1] && *v2 <= (unsigned __int64)&v27;
          v15 = v2[2];
          if ( v14 )
          {
            v19 = (unsigned __int64)&v27 - *v2;
            if ( v2[1] == v15 )
              std::vector<_GUID>::_Reserve(v2);
            v16 = *(_OWORD *)(*v2 + (v19 & 0xFFFFFFFFFFFFFFF0uLL));
          }
          else
          {
            if ( v2[1] == v15 )
              std::vector<_GUID>::_Reserve(v2);
            v16 = v27;
          }
          *(_OWORD *)v2[1] = v16;
          v2[1] += 16LL;
        }
      }
      if ( v32 >= 8 )
        operator delete(Buffer[0]);
      LOWORD(Buffer[0]) = 0;
    }
    if ( v28 )
      RegCloseKey(v28);
    v7 = *((_QWORD *)this + 17);
    if ( v7 )
    {
      NetSetupDriverStore::EnumerateDriverKeys(v7, &v28, *((unsigned int *)this + 2));
      v22 = v29;
      v18 = 0;
      v20 = v30;
      while ( 1 )
      {
        v23 = v18;
        if ( v18 == v20 )
          break;
        RegistryKeyIterator::operator*((__int64)&v22, (unsigned __int64)Block);
        NetSetupDriverObjectProvider::AddIdToCache(this, Block, 1);
        LOBYTE(v17) = 1;
        std::wstring::_Tidy(Block, v17, 0);
        v18 = v23 + 1;
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v28);
      std::unique<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<_GUID>>>>(&hKey, *v2, *((_QWORD *)this + 3));
      std::vector<_GUID>::erase(v2, &hKey, hKey, *((_QWORD *)this + 3));
    }
    *((_BYTE *)this + 12) = 1;
  }
}

```

## disassembly

```asm
0x18000442c  mov     rax, rsp
0x18000442f  push    rbp
0x180004430  push    rdi
0x180004431  push    r14
0x180004433  lea     rbp, [rax-228h]
0x18000443a  sub     rsp, 310h
0x180004441  mov     [rbp+220h+var_2A0], 0FFFFFFFFFFFFFFFEh
0x180004449  mov     [rax+10h], rbx
0x18000444d  mov     [rax+18h], rsi
0x180004451  mov     rax, cs:__security_cookie
0x180004458  xor     rax, rsp
0x18000445b  mov     [rbp+220h+var_20], rax
0x180004462  mov     rdi, rcx
0x180004465  cmp     byte ptr [rcx+0Ch], 0
0x180004469  jnz     loc_1800044FD
0x18000446f  lea     rbx, [rcx+10h]
0x180004473  mov     rax, [rbx]
0x180004476  mov     [rbx+8], rax
0x18000447a  add     rcx, 68h ; 'h'
0x18000447e  mov     r8d, [rdi+8]
0x180004482  lea     rdx, [rsp+320h+hKey]
0x180004487  call    ?GetStoreKey@NetSetupDriverStore@@QEAA?AVRegistryKey@@W4_NETSETUP_OBJECT_TYPE@@K@Z; NetSetupDriverStore::GetStoreKey(_NETSETUP_OBJECT_TYPE,ulong)
0x18000448c  nop
0x18000448d  mov     rcx, [rax]
0x180004490  mov     qword ptr [rax], 0
0x180004497  mov     [rbp+220h+var_288], rcx
0x18000449b  lea     rax, [rbp+220h+var_288]
0x18000449f  mov     [rbp+220h+var_280], rax
0x1800044a3  lea     rcx, [rbp+220h+var_288]; this
0x1800044a7  call    ?GetNumSubKeys@RegistryKey@@QEBAKXZ; RegistryKey::GetNumSubKeys(void)
0x1800044ac  mov     r14d, eax
0x1800044af  mov     [rbp+220h+var_278], eax
0x1800044b2  mov     rcx, [rsp+320h+hKey]; hKey
0x1800044b7  test    rcx, rcx
0x1800044ba  jz      short loc_1800044C6
0x1800044bc  call    cs:__imp_RegCloseKey
0x1800044c2  mov     r14d, [rbp+220h+var_278]
0x1800044c6  mov     rax, [rbp+220h+var_280]
0x1800044ca  mov     [rsp+320h+var_2C8], rax
0x1800044cf  xor     eax, eax
0x1800044d1  mov     [rsp+320h+var_2C0], eax
0x1800044d5  cmp     eax, r14d
0x1800044d8  jnz     short loc_180004524
0x1800044da  mov     rcx, [rbp+220h+var_288]; hKey
0x1800044de  test    rcx, rcx
0x1800044e1  jz      short loc_1800044E9
0x1800044e3  call    cs:__imp_RegCloseKey
0x1800044e9  mov     rcx, [rdi+88h]
0x1800044f0  test    rcx, rcx
0x1800044f3  jnz     loc_1800047B6
0x1800044f9  mov     byte ptr [rdi+0Ch], 1
0x1800044fd  mov     rcx, [rbp+220h+var_20]
0x180004504  xor     rcx, rsp; StackCookie
0x180004507  call    __security_check_cookie
0x18000450c  lea     r11, [rsp+320h+var_10]
0x180004514  mov     rbx, [r11+28h]
0x180004518  mov     rsi, [r11+30h]
0x18000451c  mov     rsp, r11
0x18000451f  pop     r14
0x180004521  pop     rdi
0x180004522  pop     rbp
0x180004523  retn
0x180004524  lea     rdx, [rbp+220h+Buffer]
0x180004528  lea     rcx, [rsp+320h+var_2C8]
0x18000452d  call    ??DRegistryKeyIterator@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; RegistryKeyIterator::operator*(void)
0x180004532  nop
0x180004533  xorps   xmm0, xmm0
0x180004536  movups  [rbp+220h+var_298], xmm0
0x18000453a  lea     rcx, [rbp+220h+Buffer]
0x18000453e  cmp     [rbp+220h+var_258], 8
0x180004543  cmovnb  rcx, [rbp+220h+Buffer]; Buffer
0x180004548  lea     rax, [rbp+220h+var_298+0Eh]
0x18000454c  mov     [rsp+320h+var_2E0], rax
0x180004551  lea     rax, [rbp+220h+var_298+0Ch]
0x180004555  mov     [rsp+320h+var_2E8], rax
0x18000455a  lea     rax, [rbp+220h+var_298+0Ah]
0x18000455e  mov     [rsp+320h+var_2F0], rax
0x180004563  lea     rax, [rbp+220h+var_298+8]
0x180004567  mov     [rsp+320h+var_2F8], rax
0x18000456c  lea     rax, [rbp+220h+var_298+6]
0x180004570  mov     [rsp+320h+var_300], rax
0x180004575  lea     r9, [rbp+220h+var_298+4]
0x180004579  lea     r8, [rbp+220h+var_298]
0x18000457d  lea     rdx, aXHxHx4hx4hx4hx; "{%x-%hx-%hx-%4hx-%4hx%4hx%4hx}"
0x180004584  call    cs:__imp_swscanf_s
0x18000458a  cmp     eax, 7
0x18000458d  jnz     loc_1800046A2
0x180004593  xor     edx, edx
0x180004595  movsxd  rcx, edx
0x180004598  movzx   eax, word ptr [rbp+rcx+220h+var_298+8]
0x18000459d  ror     ax, 8
0x1800045a1  mov     word ptr [rbp+rcx+220h+var_298+8], ax
0x1800045a6  add     edx, 2
0x1800045a9  cmp     edx, 8
0x1800045ac  jb      short loc_180004595
0x1800045ae  xor     edx, edx; Val
0x1800045b0  mov     r8d, 208h; Size
0x1800045b6  lea     rcx, [rbp+220h+Destination]; void *
0x1800045ba  call    memset_0
0x1800045bf  mov     eax, [rdi+8]
0x1800045c2  mov     dword ptr [rsp+320h+var_2BC+4], eax
0x1800045c6  mov     rax, qword ptr [rbp+220h+var_298]
0x1800045ca  mov     qword ptr [rsp+320h+var_2B4], rax
0x1800045cf  movzx   eax, word ptr [rbp+220h+var_298+8]
0x1800045d3  mov     word ptr [rsp+320h+var_2B4+8], ax
0x1800045d8  mov     al, byte ptr [rbp+220h+var_298+0Ah]
0x1800045db  mov     byte ptr [rsp+320h+var_2B4+0Ah], al
0x1800045df  mov     al, byte ptr [rbp+220h+var_298+0Bh]
0x1800045e2  mov     byte ptr [rsp+320h+var_2B4+0Bh], al
0x1800045e6  mov     al, byte ptr [rbp+220h+var_298+0Ch]
0x1800045e9  mov     byte ptr [rsp+320h+var_2B4+0Ch], al
0x1800045ed  mov     al, byte ptr [rbp+220h+var_298+0Dh]
0x1800045f0  mov     byte ptr [rsp+320h+var_2B4+0Dh], al
0x1800045f4  mov     al, byte ptr [rbp+220h+var_298+0Eh]
0x1800045f7  mov     byte ptr [rsp+320h+var_2B4+0Eh], al
0x1800045fb  mov     al, byte ptr [rbp+220h+var_298+0Fh]
0x1800045fe  mov     byte ptr [rsp+320h+var_2B4+0Fh], al
0x180004602  lea     rdx, [rsp+320h+var_2B4]
0x180004607  lea     rcx, [rbp+220h+Block]
0x18000460b  call    ?StringFromGuid@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@W4GuidConvertOptions@@@Z; StringFromGuid(_GUID const &,GuidConvertOptions)
0x180004610  mov     rsi, rax
0x180004613  cmp     qword ptr [rax+18h], 8
0x180004618  jb      short loc_18000461D
0x18000461a  mov     rsi, [rax]
0x18000461d  mov     ecx, dword ptr [rsp+320h+var_2BC+4]
0x180004621  call    ?GetSystemStorePath@NetSetupDriverStore@@CAPEB_WW4_NETSETUP_OBJECT_TYPE@@@Z; NetSetupDriverStore::GetSystemStorePath(_NETSETUP_OBJECT_TYPE)
0x180004626  mov     [rsp+320h+var_300], rsi
0x18000462b  mov     r9, rax
0x18000462e  lea     r8, aControlNetwork_7; "Control\\NetworkSetup2\\%s\\%s"
0x180004635  mov     edx, 104h; BufferCount
0x18000463a  lea     rcx, [rbp+220h+Destination]; Buffer
0x18000463e  call    cs:__imp_swprintf_s
0x180004644  nop
0x180004645  cmp     [rbp+220h+var_238], 8
0x18000464a  jnb     short loc_1800046BA
0x18000464c  lea     r8, aProperties; "\\Properties"
0x180004653  mov     edx, 104h; SizeInWords
0x180004658  lea     rcx, [rbp+220h+Destination]; Destination
0x18000465c  call    cs:__imp_wcscat_s
0x180004662  mov     rcx, [rdi+0A0h]
0x180004669  add     rcx, 18h
0x18000466d  mov     [rsp+320h+var_300], 0
0x180004676  mov     r9d, 8
0x18000467c  lea     r8, [rbp+220h+Destination]
0x180004680  lea     rdx, [rsp+320h+hKey]
0x180004685  call    ?TryOpenSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAX@Z; RegistryKey::TryOpenSubKey(wchar_t const *,ulong,void *)
0x18000468a  mov     rsi, [rax]
0x18000468d  mov     rcx, [rsp+320h+hKey]; hKey
0x180004692  test    rcx, rcx
0x180004695  jz      short loc_18000469D
0x180004697  call    cs:__imp_RegCloseKey
0x18000469d  test    rsi, rsi
0x1800046a0  jnz     short loc_1800046D0
0x1800046a2  cmp     [rbp+220h+var_258], 8
0x1800046a7  jnb     short loc_1800046C5
0x1800046a9  xor     eax, eax
0x1800046ab  mov     word ptr [rbp+220h+Buffer], ax
0x1800046af  mov     eax, [rsp+320h+var_2C0]
0x1800046b3  inc     eax
0x1800046b5  jmp     loc_1800044D1
0x1800046ba  mov     rcx, [rbp+220h+Block]; Block
0x1800046be  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800046c3  jmp     short loc_18000464C
0x1800046c5  mov     rcx, [rbp+220h+Buffer]; Block
0x1800046c9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800046ce  jmp     short loc_1800046A9
0x1800046d0  lea     rax, [rbp+220h+var_298]
0x1800046d4  cmp     rax, [rbx+8]
0x1800046d8  jnb     short loc_1800046E7
0x1800046da  lea     rax, [rbp+220h+var_298]
0x1800046de  cmp     [rbx], rax
0x1800046e1  jbe     loc_18000478B
0x1800046e7  xor     al, al
0x1800046e9  mov     rcx, [rbx+10h]
0x1800046ed  test    al, al
0x1800046ef  jnz     loc_180004792
0x1800046f5  cmp     [rbx+8], rcx
0x1800046f9  jnz     short loc_180004703
0x1800046fb  mov     rcx, rbx
0x1800046fe  call    ?_Reserve@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@IEAAX_K@Z; std::vector<_GUID>::_Reserve(unsigned __int64)
0x180004703  movups  xmm0, [rbp+220h+var_298]
0x180004707  mov     rax, [rbx+8]
0x18000470b  movdqu  xmmword ptr [rax], xmm0
0x18000470f  add     qword ptr [rbx+8], 10h
0x180004714  jmp     short loc_1800046A2
0x180004716  mov     [rsp+320h+var_2C0], eax
0x18000471a  cmp     eax, esi
0x18000471c  jz      short loc_180004756
0x18000471e  lea     rdx, [rbp+220h+Block]
0x180004722  lea     rcx, [rsp+320h+var_2C8]
0x180004727  call    ??DRegistryKeyIterator@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; RegistryKeyIterator::operator*(void)
0x18000472c  nop
0x18000472d  mov     r8d, 1
0x180004733  lea     rdx, [rbp+220h+Block]
0x180004737  mov     rcx, rdi
0x18000473a  call    ?AddIdToCache@NetSetupDriverObjectProvider@@AEBAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4NetSetupStoreType@@@Z; NetSetupDriverObjectProvider::AddIdToCache(std::wstring const &,NetSetupStoreType)
0x18000473f  nop
0x180004740  xor     r8d, r8d
0x180004743  mov     dl, 1
0x180004745  lea     rcx, [rbp+220h+Block]
0x180004749  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000474e  mov     eax, [rsp+320h+var_2C0]
0x180004752  inc     eax
0x180004754  jmp     short loc_180004716
0x180004756  lea     rcx, [rbp+220h+var_288]
0x18000475a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000475f  mov     r8, [rdi+18h]
0x180004763  mov     rdx, [rbx]
0x180004766  lea     rcx, [rsp+320h+hKey]
0x18000476b  call    ??$unique@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@U_GUID@@@std@@@std@@@std@@@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@U_GUID@@@std@@@std@@@0@V10@0@Z; std::unique<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<_GUID>>>>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<_GUID>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<_GUID>>>)
0x180004770  mov     r9, [rdi+18h]
0x180004774  mov     r8, [rsp+320h+hKey]
0x180004779  lea     rdx, [rsp+320h+hKey]
0x18000477e  mov     rcx, rbx
0x180004781  call    ?erase@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@U_GUID@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@U_GUID@@@std@@@std@@@2@0@Z; std::vector<_GUID>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<_GUID>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<_GUID>>>)
0x180004786  jmp     loc_1800044F9
0x18000478b  mov     al, 1
0x18000478d  jmp     loc_1800046E9
0x180004792  lea     rsi, [rbp+220h+var_298]
0x180004796  sub     rsi, [rbx]
0x180004799  cmp     [rbx+8], rcx
0x18000479d  jnz     short loc_1800047A7
0x18000479f  mov     rcx, rbx
0x1800047a2  call    ?_Reserve@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@IEAAX_K@Z; std::vector<_GUID>::_Reserve(unsigned __int64)
0x1800047a7  and     rsi, 0FFFFFFFFFFFFFFF0h
0x1800047ab  add     rsi, [rbx]
0x1800047ae  movups  xmm0, xmmword ptr [rsi]
0x1800047b1  jmp     loc_180004707
0x1800047b6  mov     r8d, [rdi+8]
0x1800047ba  lea     rdx, [rbp+220h+var_288]
0x1800047be  call    ?EnumerateDriverKeys@NetSetupDriverStore@@QEAA?AVDriverKeyEnumerator@@W4_NETSETUP_OBJECT_TYPE@@@Z; NetSetupDriverStore::EnumerateDriverKeys(_NETSETUP_OBJECT_TYPE)
0x1800047c3  nop
0x1800047c4  mov     rax, [rbp+220h+var_280]
0x1800047c8  mov     [rsp+320h+var_2C8], rax
0x1800047cd  xor     eax, eax
0x1800047cf  mov     esi, [rbp+220h+var_278]
0x1800047d2  jmp     loc_180004716
```
