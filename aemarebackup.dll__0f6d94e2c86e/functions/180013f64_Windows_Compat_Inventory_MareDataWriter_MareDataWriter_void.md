# Windows::Compat::Inventory::MareDataWriter::~MareDataWriter(void)

- ea: `0x180013f64`
- end: `0x180014132`
- name: `??1MareDataWriter@Inventory@Compat@Windows@@QEAA@XZ`
- size: `462`
- prototype: `void __fastcall(Windows::Compat::Inventory::MareDataWriter *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800172a0`
- `0x1800e712e`

## callees

- `0x180004ea0`
- `0x18000fb60`
- `0x18001331c`
- `0x1800134b8`
- `0x1800138d0`
- `0x180013f64`
- `0x18001459c`
- `0x180027cb0`
- `0x18004c020`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x180013fae`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x180013fae`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180013fc0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180013fc0`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180014032`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180014032`

## string_xrefs

- `0x180013fe3`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Backup\`
- `0x180014024`: `writeTime`
- `0x180014040`: `RegSetKeyValueW failed [%d]`
- `0x18001404d`: `Windows::Compat::Inventory::MareDataWriter::~MareDataWriter`

## pseudocode

```c
void __fastcall Windows::Compat::Inventory::MareDataWriter::~MareDataWriter(
        Windows::Compat::Inventory::MareDataWriter *this)
{
  char *v2; // r14
  __int64 i; // rbx
  FILE *v4; // rcx
  const WCHAR *v5; // rdx
  LSTATUS v6; // eax
  _QWORD *v7; // rbx
  void (__fastcall ***v8)(_QWORD, __int64); // rcx
  __int64 **v9; // rcx
  __int64 j; // rax
  __int64 *k; // rcx
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp-40h] BYREF
  struct _FILETIME Data; // [rsp+38h] [rbp-38h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+40h] [rbp-30h] BYREF
  __int128 v15; // [rsp+50h] [rbp-20h]

  v2 = (char *)this + 304;
  for ( i = *((_QWORD *)this + 38); i != *((_QWORD *)this + 39); i += 40 )
  {
    v4 = *(FILE **)(i + 32);
    if ( v4 )
    {
      fclose(v4);
      SystemTimeAsFileTime = 0;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      Data = SystemTimeAsFileTime;
      *(_OWORD *)lpSubKey = 0;
      v15 = 0;
      std::wstring::_Construct<1,unsigned short const *>(
        (char **)lpSubKey,
        L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\Backup\\",
        0x43u);
      std::wstring::append(lpSubKey);
      v5 = (const WCHAR *)lpSubKey;
      if ( *((_QWORD *)&v15 + 1) > 7u )
        v5 = lpSubKey[0];
      v6 = RegSetKeyValueW(HKEY_LOCAL_MACHINE, v5, L"writeTime", 0xBu, &Data, 8u);
      if ( v6 )
        AslLogCallPrintf(
          1,
          "Windows::Compat::Inventory::MareDataWriter::~MareDataWriter",
          219,
          "RegSetKeyValueW failed [%d]",
          v6);
      std::wstring::~wstring((char **)lpSubKey);
    }
  }
  v7 = (_QWORD *)**((_QWORD **)this + 36);
  while ( v7 != *((_QWORD **)this + 36) )
  {
    v8 = (void (__fastcall ***)(_QWORD, __int64))v7[8];
    if ( v8 )
      (**v8)(v8, 1);
    v9 = (__int64 **)v7[2];
    if ( *((_BYTE *)v9 + 25) )
    {
      for ( j = v7[1]; !*(_BYTE *)(j + 25) && v7 == *(_QWORD **)(j + 16); j = *(_QWORD *)(j + 8) )
        v7 = (_QWORD *)j;
      v7 = (_QWORD *)j;
    }
    else
    {
      v7 = (_QWORD *)v7[2];
      for ( k = *v9; !*((_BYTE *)k + 25); k = (__int64 *)*k )
        v7 = k;
    }
  }
  std::wstring::~wstring((char **)this + 41);
  std::vector<std::pair<std::wstring,_iobuf *>>::~vector<std::pair<std::wstring,_iobuf *>>(v2);
  std::_Tree<std::_Tmap_traits<std::wstring const,Windows::Compat::Inventory::MareApplication *,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,Windows::Compat::Inventory::MareApplication *>>,0>>::~_Tree<std::_Tmap_traits<std::wstring const,Windows::Compat::Inventory::MareApplication *,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,Windows::Compat::Inventory::MareApplication *>>,0>>((void **)this + 36);
  TelCacheProvider::~TelCacheProvider((Windows::Compat::Inventory::MareDataWriter *)((char *)this + 144));
  TelCacheProvider::~TelCacheProvider(this);
}

```

## disassembly

```asm
0x180013f64  mov     [rsp-18h+arg_8], rbx
0x180013f69  mov     [rsp-18h+arg_10], rsi
0x180013f6e  push    rbp
0x180013f6f  push    rdi
0x180013f70  push    r14
0x180013f72  mov     rbp, rsp
0x180013f75  sub     rsp, 70h
0x180013f79  mov     rax, cs:__security_cookie
0x180013f80  xor     rax, rsp
0x180013f83  mov     [rbp+var_10], rax
0x180013f87  mov     rdi, rcx
0x180013f8a  lea     r14, [rcx+130h]
0x180013f91  mov     rbx, [r14]
0x180013f94  cmp     rbx, [rdi+138h]
0x180013f9b  jz      loc_180014070
0x180013fa1  mov     rcx, [rbx+20h]; Stream
0x180013fa5  test    rcx, rcx
0x180013fa8  jz      loc_180014067
0x180013fae  call    cs:__imp_fclose
0x180013fb4  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180013fbc  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180013fc0  call    cs:__imp_GetSystemTimeAsFileTime
0x180013fc6  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180013fca  mov     [rbp+Data], rax
0x180013fce  xorps   xmm0, xmm0
0x180013fd1  movups  xmmword ptr [rbp+lpSubKey], xmm0
0x180013fd5  xorps   xmm1, xmm1
0x180013fd8  movdqu  [rbp+var_20], xmm1
0x180013fdd  mov     r8d, 43h ; 'C'
0x180013fe3  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180013fea  lea     rcx, [rbp+lpSubKey]
0x180013fee  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180013ff3  mov     rdx, rbx
0x180013ff6  lea     rcx, [rbp+lpSubKey]; Src
0x180013ffa  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180013fff  lea     rdx, [rbp+lpSubKey]
0x180014003  cmp     qword ptr [rbp+var_20+8], 7
0x180014008  cmova   rdx, [rbp+lpSubKey]; lpSubKey
0x18001400d  mov     [rsp+70h+cbData], 8; cbData
0x180014015  lea     rax, [rbp+Data]
0x180014019  mov     [rsp+70h+lpData], rax; lpData
0x18001401e  mov     r9d, 0Bh; dwType
0x180014024  lea     r8, ValueName; "writeTime"
0x18001402b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014032  call    cs:__imp_RegSetKeyValueW
0x180014038  test    eax, eax
0x18001403a  jz      short loc_18001405E
0x18001403c  mov     dword ptr [rsp+70h+lpData], eax
0x180014040  lea     r9, aRegsetkeyvalue; "RegSetKeyValueW failed [%d]"
0x180014047  mov     r8d, 0DBh
0x18001404d  lea     rdx, aWindowsCompatI_12; "Windows::Compat::Inventory::MareDataWri"...
0x180014054  mov     ecx, 1
0x180014059  call    AslLogCallPrintf
0x18001405e  lea     rcx, [rbp+lpSubKey]
0x180014062  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014067  add     rbx, 28h ; '('
0x18001406b  jmp     loc_180013F94
0x180014070  lea     rsi, [rdi+120h]
0x180014077  mov     rbx, [rsi]
0x18001407a  mov     rbx, [rbx]
0x18001407d  cmp     rbx, [rsi]
0x180014080  jz      short loc_1800140E0
0x180014082  mov     rcx, [rbx+40h]
0x180014086  test    rcx, rcx
0x180014089  jz      short loc_18001409B
0x18001408b  mov     rax, [rcx]
0x18001408e  mov     edx, 1
0x180014093  mov     rax, [rax]
0x180014096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001409b  mov     rcx, [rbx+10h]
0x18001409f  cmp     byte ptr [rcx+19h], 0
0x1800140a3  jz      short loc_1800140C3
0x1800140a5  mov     rax, [rbx+8]
0x1800140a9  jmp     short loc_1800140B8
0x1800140ab  cmp     rbx, [rax+10h]
0x1800140af  jnz     short loc_1800140BE
0x1800140b1  mov     rbx, rax
0x1800140b4  mov     rax, [rax+8]
0x1800140b8  cmp     byte ptr [rax+19h], 0
0x1800140bc  jz      short loc_1800140AB
0x1800140be  mov     rbx, rax
0x1800140c1  jmp     short loc_18001407D
0x1800140c3  mov     rbx, rcx
0x1800140c6  mov     rcx, [rcx]
0x1800140c9  cmp     byte ptr [rcx+19h], 0
0x1800140cd  jnz     short loc_18001407D
0x1800140cf  mov     rbx, rcx
0x1800140d2  mov     rax, [rcx]
0x1800140d5  mov     rcx, rax
0x1800140d8  cmp     byte ptr [rax+19h], 0
0x1800140dc  jz      short loc_1800140CF
0x1800140de  jmp     short loc_18001407D
0x1800140e0  lea     rcx, [rdi+148h]
0x1800140e7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800140ec  mov     rcx, r14
0x1800140ef  call    ??1?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_iobuf@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_iobuf@@@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<std::wstring,_iobuf *>>::~vector<std::pair<std::wstring,_iobuf *>>(void)
0x1800140f4  mov     rcx, rsi
0x1800140f7  call    ??1?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVMareApplication@Inventory@Compat@Windows@@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVMareApplication@Inventory@Compat@Windows@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring const,Windows::Compat::Inventory::MareApplication *,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,Windows::Compat::Inventory::MareApplication *>>,0>>::~_Tree<std::_Tmap_traits<std::wstring const,Windows::Compat::Inventory::MareApplication *,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,Windows::Compat::Inventory::MareApplication *>>,0>>(void)
0x1800140fc  lea     rcx, [rdi+90h]; this
0x180014103  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x180014108  mov     rcx, rdi; this
0x18001410b  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x180014110  nop
0x180014111  mov     rcx, [rbp+var_10]
0x180014115  xor     rcx, rsp; StackCookie
0x180014118  call    __security_check_cookie
0x18001411d  lea     r11, [rsp+70h+var_s0]
0x180014122  mov     rbx, [r11+28h]
0x180014126  mov     rsi, [r11+30h]
0x18001412a  mov     rsp, r11
0x18001412d  pop     r14
0x18001412f  pop     rdi
0x180014130  pop     rbp
0x180014131  retn
```
