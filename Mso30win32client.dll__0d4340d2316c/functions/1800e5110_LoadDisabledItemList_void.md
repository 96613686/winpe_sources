# LoadDisabledItemList(void)

- ea: `0x1800e5110`
- end: `0x1800e54cb`
- name: `?LoadDisabledItemList@@YAPEAV?$MSOTPX@PEAUMSODIPLEXNODE@@@@XZ`
- size: `955`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18018c2f0`

## callees

- `0x180020684`
- `0x18003af78`
- `0x1800648b8`
- `0x1800e5110`
- `0x1800e54d0`
- `0x180190520`
- `0x1801906b4`
- `0x180190750`
- `0x180192520`
- `0x180468798`
- `0x18054f848`

## import_xrefs

- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800e542b`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800e542b`
- `Mso20Win32Client!__imp_?MsoFIsRunningRestricted@@YAHXZ` at `0x1800e5159`
- `Mso20Win32Client!__imp_?MsoFIsRunningRestricted@@YAHXZ` at `0x1800e5159`
- `Mso20Win32Client!__imp_?MsoParseHexIntSz@@YAHPEBDPEAH@Z` at `0x1800e53fb`
- `Mso20Win32Client!__imp_?MsoParseHexIntSz@@YAHPEBDPEAH@Z` at `0x1800e53fb`
- `Mso20Win32Client!__imp_MsoFInitPxCore` at `0x1800e52e7`
- `Mso20Win32Client!__imp_MsoFInitPxCore` at `0x1800e52e7`
- `Mso20Win32Client!__imp_??IKey@Registry@Mso@@QEAAPEAPEAUHKEY__@@XZ` at `0x1800e51c5`
- `Mso20Win32Client!__imp_??IKey@Registry@Mso@@QEAAPEAPEAUHKEY__@@XZ` at `0x1800e51c5`
- `Mso20Win32Client!__imp_??1Key@Registry@Mso@@UEAA@XZ` at `0x1800e5213`
- `Mso20Win32Client!__imp_??1Key@Registry@Mso@@UEAA@XZ` at `0x1800e52b4`
- `Mso20Win32Client!__imp_??1Key@Registry@Mso@@UEAA@XZ` at `0x1800e5213`
- `Mso20Win32Client!__imp_??1Key@Registry@Mso@@UEAA@XZ` at `0x1800e52b4`
- `Mso20Win32Client!__imp_?MsoIAppendPx@@YAHPEAXPEBX@Z` at `0x1800e5418`
- `Mso20Win32Client!__imp_?MsoIAppendPx@@YAHPEAXPEBX@Z` at `0x1800e5418`
- `Mso20Win32Client!__imp_??BKey@Registry@Mso@@QEBAPEAUHKEY__@@XZ` at `0x1800e5237`
- `Mso20Win32Client!__imp_??BKey@Registry@Mso@@QEBAPEAUHKEY__@@XZ` at `0x1800e5374`
- `Mso20Win32Client!__imp_??BKey@Registry@Mso@@QEBAPEAUHKEY__@@XZ` at `0x1800e5237`
- `Mso20Win32Client!__imp_??BKey@Registry@Mso@@QEBAPEAUHKEY__@@XZ` at `0x1800e5374`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800e532e`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800e533c`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800e53b9`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800e532e`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800e533c`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800e53b9`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800e5435`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800e5447`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800e5450`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800e5485`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800e548e`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800e54b9`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800e5435`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800e5447`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800e5450`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800e5485`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800e548e`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800e54b9`
- `ADVAPI32!RegQueryInfoKeyA` at `0x1800e527c`
- `ADVAPI32!RegQueryInfoKeyA` at `0x1800e527c`
- `ADVAPI32!RegEnumValueA` at `0x1800e539f`
- `ADVAPI32!RegEnumValueA` at `0x1800e539f`

## pseudocode

```c
struct MSODISABLEDITEM *LoadDisabledItemList()
{
  struct MSODISABLEDITEM *v0; // rdi
  HKEY *v2; // rbx
  __int64 AppDisabledItemsRegPath; // rax
  int v4; // ebx
  HKEY v5; // rax
  unsigned __int64 v6; // rdx
  unsigned int v7; // r8d
  struct MSODISABLEDITEM *v8; // rax
  struct MSODISABLEDITEM *v9; // rcx
  unsigned int v10; // r8d
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rax
  Mso::Memory *v13; // rsi
  unsigned int v14; // r8d
  unsigned int *v15; // rax
  void *v16; // rdx
  unsigned int *v17; // rbx
  DWORD i; // r14d
  HKEY v19; // rax
  unsigned int v20; // r8d
  int *v21; // rax
  void *v22; // rdx
  int v23; // eax
  void *v24; // rdx
  void *v25; // rdx
  DWORD cbMaxValueLen; // [rsp+68h] [rbp-39h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+6Ch] [rbp-35h] BYREF
  DWORD cbData; // [rsp+70h] [rbp-31h] BYREF
  DWORD cValues; // [rsp+74h] [rbp-2Dh] BYREF
  DWORD cchValueName; // [rsp+78h] [rbp-29h] BYREF
  int *v31; // [rsp+80h] [rbp-21h] BYREF
  _QWORD v32[2]; // [rsp+88h] [rbp-19h] BYREF
  void **v33; // [rsp+98h] [rbp-9h] BYREF
  int v34; // [rsp+A0h] [rbp-1h]
  __int64 v35; // [rsp+A8h] [rbp+7h]
  char v36; // [rsp+B0h] [rbp+Fh]
  _BYTE v37[32]; // [rsp+B8h] [rbp+17h] BYREF

  v32[0] = &disabledItemsLock;
  v32[1] = 0;
  v0 = 0;
  Mso::TLocker<Mso::Lockable<Mso::AlwaysInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>::Lock(v32);
  if ( MsoFIsRunningRestricted() || !(_QWORD)xmmword_180F6E8F0 )
  {
    vppxpdi = 0;
LABEL_4:
    Mso::TLocker<Mso::Lockable<Mso::AlwaysInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>::~TLocker<Mso::Lockable<Mso::AlwaysInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>(v32);
    return 0;
  }
  v34 = 1;
  v33 = &Mso::Registry::Key::`vftable';
  v35 = 0;
  v36 = 1;
  v2 = (HKEY *)Mso::Registry::Key::operator&(&v33);
  AppDisabledItemsRegPath = Mso::Resiliency::GetAppDisabledItemsRegPath(v37);
  if ( *(_QWORD *)(AppDisabledItemsRegPath + 24) > 0xFu )
    AppDisabledItemsRegPath = *(_QWORD *)AppDisabledItemsRegPath;
  v4 = MsoRegOpenKeyExA(HKEY_CURRENT_USER, (LPCSTR)AppDisabledItemsRegPath, 0x20019u, v2);
  std::string::_Tidy_deallocate(v37);
  if ( !v4 )
  {
    cbMaxValueNameLen = 0;
    cbMaxValueLen = 0;
    cValues = 0;
    v5 = (HKEY)Mso::Registry::Key::operator HKEY__ *(&v33);
    RegQueryInfoKeyA(v5, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
    v8 = (struct MSODISABLEDITEM *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x20, v6, v7);
    v9 = v8;
    if ( v8 )
    {
      *(_QWORD *)v8 = 0;
      *((_WORD *)v8 + 4) = 8;
      *((_DWORD *)v8 + 2) = 65544;
      *((_QWORD *)v8 + 2) = 0;
      *((_QWORD *)v8 + 3) = 0;
    }
    else
    {
      v9 = 0;
    }
    vppxpdi = v9;
    if ( v9 && (unsigned int)MsoFInitPxCore(v9, 1, cValues) )
    {
      if ( (unsigned __int64)cbMaxValueLen + 4 > 0xFFFFFFFF
        || (cbMaxValueLen += 4, v11 = cbMaxValueNameLen + 4LL, v11 > 0xFFFFFFFF)
        || (cbMaxValueNameLen += 4, v12 = (unsigned int)v11 + 1LL, v12 > 0xFFFFFFFF) )
      {
        __fastfail(5u);
      }
      v13 = (Mso::Memory *)Mso::Memory::AllocateEx((Mso::Memory *)(unsigned int)v12, 0, v10);
      v15 = (unsigned int *)Mso::Memory::AllocateEx((Mso::Memory *)cbMaxValueLen, 0, v14);
      v17 = v15;
      if ( v13 && v15 )
      {
        for ( i = 0; ; ++i )
        {
          if ( i >= cValues )
          {
            Mso::Memory::Free(v13, v16);
            Mso::Memory::Free((Mso::Memory *)v17, v25);
            v0 = vppxpdi;
            goto LABEL_9;
          }
          cchValueName = cbMaxValueNameLen;
          cbData = cbMaxValueLen;
          v19 = (HKEY)Mso::Registry::Key::operator HKEY__ *(&v33);
          RegEnumValueA(v19, i, (LPSTR)v13, &cchValueName, 0, 0, (LPBYTE)v17, &cbData);
          if ( !(unsigned __int8)sub_180468798(v17) )
          {
            v21 = (int *)Mso::Memory::AllocateEx((Mso::Memory *)(cbData + 8LL), 0, v20);
            v31 = v21;
            if ( !v21 )
            {
              if ( vppxpdi )
                MSOTPX<MSODIPLEXNODE *>::`scalar deleting destructor'(vppxpdi);
              vppxpdi = 0;
              Mso::Memory::Free(v13, v22);
              goto LABEL_38;
            }
            if ( cbData >= 0xC && cbData == v17[1] + v17[2] + 12LL )
            {
              memcpy_0(v21 + 2, v17, cbData);
              v23 = MsoParseHexIntSz((const char *)v13, v31);
              if ( v23 != cchValueName )
                *v31 = 0;
              v31[1] = 0;
              MsoIAppendPx(vppxpdi, &v31);
            }
            else
            {
              MsoShipAssertTagProc(6920213);
              Mso::Memory::Free((Mso::Memory *)v31, v24);
            }
          }
        }
      }
      if ( vppxpdi )
        MSOTPX<MSODIPLEXNODE *>::`scalar deleting destructor'(vppxpdi);
      vppxpdi = 0;
      if ( v13 )
        Mso::Memory::Free(v13, v16);
      if ( v17 )
LABEL_38:
        Mso::Memory::Free((Mso::Memory *)v17, v16);
    }
    else
    {
      vppxpdi = 0;
    }
    Mso::Registry::Key::~Key((Mso::Registry::Key *)&v33);
    goto LABEL_4;
  }
  vppxpdi = 0;
LABEL_9:
  Mso::Registry::Key::~Key((Mso::Registry::Key *)&v33);
  Mso::TLocker<Mso::Lockable<Mso::AlwaysInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>::~TLocker<Mso::Lockable<Mso::AlwaysInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>(v32);
  return v0;
}

```

## disassembly

```asm
0x1800e5110  mov     rax, rsp
0x1800e5113  mov     [rax+8], rbx
0x1800e5117  mov     [rax+10h], rsi
0x1800e511b  mov     [rax+18h], rdi
0x1800e511f  push    rbp
0x1800e5120  push    r14
0x1800e5122  push    r15
0x1800e5124  lea     rbp, [rax-5Fh]
0x1800e5128  sub     rsp, 0E0h
0x1800e512f  mov     rax, cs:__security_cookie
0x1800e5136  xor     rax, rsp
0x1800e5139  mov     [rbp+57h+var_20], rax
0x1800e513d  lea     rax, ?disabledItemsLock@@3V?$Lockable@V?$AlwaysInit@VCritSecBase@Mso@@@Mso@@VZeroOrOneThreaded@2@@Mso@@A; Mso::Lockable<Mso::AlwaysInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded> disabledItemsLock
0x1800e5144  mov     [rbp+57h+var_70], rax
0x1800e5148  xor     eax, eax
0x1800e514a  mov     [rbp+57h+var_68], rax
0x1800e514e  xor     edi, edi
0x1800e5150  lea     rcx, [rbp+57h+var_70]
0x1800e5154  call    ?Lock@?$TLocker@V?$Lockable@V?$AlwaysInit@VCritSecBase@Mso@@@Mso@@VZeroOrOneThreaded@2@@Mso@@VZeroOrOneThreaded@2@@Mso@@QEAAXXZ; Mso::TLocker<Mso::Lockable<Mso::AlwaysInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>::Lock(void)
0x1800e5159  call    cs:__imp_?MsoFIsRunningRestricted@@YAHXZ; MsoFIsRunningRestricted(void)
0x1800e515f  test    eax, eax
0x1800e5161  jnz     short loc_1800E516C
0x1800e5163  cmp     qword ptr cs:xmmword_180F6E8F0, rdi
0x1800e516a  jnz     short loc_1800E51A7
0x1800e516c  mov     cs:?vppxpdi@@3PEAV?$MSOTPX@PEAUMSODIPLEXNODE@@@@EA, rdi; MSOTPX<MSODIPLEXNODE *> * vppxpdi
0x1800e5173  lea     rcx, [rbp+57h+var_70]
0x1800e5177  call    ??1?$TLocker@V?$Lockable@V?$AlwaysInit@VCritSecBase@Mso@@@Mso@@VZeroOrOneThreaded@2@@Mso@@VZeroOrOneThreaded@2@@Mso@@QEAA@XZ; Mso::TLocker<Mso::Lockable<Mso::AlwaysInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>::~TLocker<Mso::Lockable<Mso::AlwaysInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>(void)
0x1800e517c  xor     eax, eax
0x1800e517e  mov     rcx, [rbp+57h+var_20]
0x1800e5182  xor     rcx, rsp; StackCookie
0x1800e5185  call    __security_check_cookie
0x1800e518a  lea     r11, [rsp+0F0h+var_10]
0x1800e5192  mov     rbx, [r11+20h]
0x1800e5196  mov     rsi, [r11+28h]
0x1800e519a  mov     rdi, [r11+30h]
0x1800e519e  mov     rsp, r11
0x1800e51a1  pop     r15
0x1800e51a3  pop     r14
0x1800e51a5  pop     rbp
0x1800e51a6  retn
0x1800e51a7  mov     [rbp+57h+var_58], 1
0x1800e51ae  lea     rax, ??_7Key@Registry@Mso@@6B@; const Mso::Registry::Key::`vftable'
0x1800e51b5  mov     [rbp+57h+var_60], rax
0x1800e51b9  mov     [rbp+57h+var_50], rdi
0x1800e51bd  mov     [rbp+57h+var_48], 1
0x1800e51c1  lea     rcx, [rbp+57h+var_60]
0x1800e51c5  call    cs:__imp_??IKey@Registry@Mso@@QEAAPEAPEAUHKEY__@@XZ; Mso::Registry::Key::operator&(void)
0x1800e51cb  mov     rbx, rax
0x1800e51ce  lea     rcx, [rbp+57h+var_40]
0x1800e51d2  call    ?GetAppDisabledItemsRegPath@Resiliency@Mso@@YA?BV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; Mso::Resiliency::GetAppDisabledItemsRegPath(void)
0x1800e51d7  cmp     qword ptr [rax+18h], 0Fh
0x1800e51dc  jbe     short loc_1800E51E1
0x1800e51de  mov     rax, [rax]
0x1800e51e1  mov     r9, rbx; HKEY *
0x1800e51e4  mov     r8d, 20019h; unsigned int
0x1800e51ea  mov     rdx, rax; lpSubKey
0x1800e51ed  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800e51f4  call    ?MsoRegOpenKeyExA@@YAJPEAUHKEY__@@PEBDKPEAPEAU1@@Z; MsoRegOpenKeyExA(HKEY__ *,char const *,ulong,HKEY__ * *)
0x1800e51f9  mov     ebx, eax
0x1800e51fb  lea     rcx, [rbp+57h+var_40]
0x1800e51ff  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800e5204  test    ebx, ebx
0x1800e5206  jz      short loc_1800E522A
0x1800e5208  mov     cs:?vppxpdi@@3PEAV?$MSOTPX@PEAUMSODIPLEXNODE@@@@EA, rdi; MSOTPX<MSODIPLEXNODE *> * vppxpdi
0x1800e520f  lea     rcx, [rbp+57h+var_60]
0x1800e5213  call    cs:__imp_??1Key@Registry@Mso@@UEAA@XZ; Mso::Registry::Key::~Key(void)
0x1800e5219  lea     rcx, [rbp+57h+var_70]
0x1800e521d  call    ??1?$TLocker@V?$Lockable@V?$AlwaysInit@VCritSecBase@Mso@@@Mso@@VZeroOrOneThreaded@2@@Mso@@VZeroOrOneThreaded@2@@Mso@@QEAA@XZ; Mso::TLocker<Mso::Lockable<Mso::AlwaysInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>::~TLocker<Mso::Lockable<Mso::AlwaysInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>(void)
0x1800e5222  mov     rax, rdi
0x1800e5225  jmp     loc_1800E517E
0x1800e522a  mov     [rbp+57h+cbMaxValueNameLen], edi
0x1800e522d  mov     [rbp+57h+cbMaxValueLen], edi
0x1800e5230  mov     [rbp+57h+cValues], edi
0x1800e5233  lea     rcx, [rbp+57h+var_60]
0x1800e5237  call    cs:__imp_??BKey@Registry@Mso@@QEBAPEAUHKEY__@@XZ; Mso::Registry::Key::operator HKEY__ *(void)
0x1800e523d  mov     [rsp+0F0h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x1800e5242  mov     [rsp+0F0h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x1800e5247  lea     rcx, [rbp+57h+cbMaxValueLen]
0x1800e524b  mov     [rsp+0F0h+lpcbMaxValueLen], rcx; lpcbMaxValueLen
0x1800e5250  lea     rcx, [rbp+57h+cbMaxValueNameLen]
0x1800e5254  mov     [rsp+0F0h+lpcbMaxValueNameLen], rcx; lpcbMaxValueNameLen
0x1800e5259  lea     rcx, [rbp+57h+cValues]
0x1800e525d  mov     [rsp+0F0h+lpcValues], rcx; lpcValues
0x1800e5262  mov     [rsp+0F0h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x1800e5267  mov     [rsp+0F0h+lpcbMaxSubKeyLen], rdi; lpcbMaxSubKeyLen
0x1800e526c  mov     [rsp+0F0h+lpcSubKeys], rdi; lpcSubKeys
0x1800e5271  xor     r9d, r9d; lpReserved
0x1800e5274  xor     r8d, r8d; lpcchClass
0x1800e5277  xor     edx, edx; lpClass
0x1800e5279  mov     rcx, rax; hKey
0x1800e527c  call    cs:__imp_RegQueryInfoKeyA
0x1800e5282  mov     ecx, 20h ; ' '; this
0x1800e5287  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1800e528c  mov     rcx, rax
0x1800e528f  mov     r15d, 8
0x1800e5295  test    rax, rax
0x1800e5298  jnz     short loc_1800E52BF
0x1800e529a  mov     rcx, rdi
0x1800e529d  mov     cs:?vppxpdi@@3PEAV?$MSOTPX@PEAUMSODIPLEXNODE@@@@EA, rcx; MSOTPX<MSODIPLEXNODE *> * vppxpdi
0x1800e52a4  test    rcx, rcx
0x1800e52a7  jnz     short loc_1800E52DC
0x1800e52a9  mov     cs:?vppxpdi@@3PEAV?$MSOTPX@PEAUMSODIPLEXNODE@@@@EA, rdi; MSOTPX<MSODIPLEXNODE *> * vppxpdi
0x1800e52b0  lea     rcx, [rbp+57h+var_60]
0x1800e52b4  call    cs:__imp_??1Key@Registry@Mso@@UEAA@XZ; Mso::Registry::Key::~Key(void)
0x1800e52ba  jmp     loc_1800E5173
0x1800e52bf  mov     [rax], rdi
0x1800e52c2  mov     [rax+8], r15w
0x1800e52c7  movzx   eax, r15w
0x1800e52cb  bts     eax, 10h
0x1800e52cf  mov     [rcx+8], eax
0x1800e52d2  mov     [rcx+10h], rdi
0x1800e52d6  mov     [rcx+18h], rdi
0x1800e52da  jmp     short loc_1800E529D
0x1800e52dc  xor     r9d, r9d
0x1800e52df  mov     r8d, [rbp+57h+cValues]
0x1800e52e3  lea     edx, [r9+1]
0x1800e52e7  call    cs:__imp_MsoFInitPxCore
0x1800e52ed  test    eax, eax
0x1800e52ef  jz      short loc_1800E52A9
0x1800e52f1  mov     eax, [rbp+57h+cbMaxValueLen]
0x1800e52f4  add     rax, 4
0x1800e52f8  mov     ecx, 0FFFFFFFFh
0x1800e52fd  cmp     rax, rcx
0x1800e5300  ja      loc_1800E543D
0x1800e5306  mov     [rbp+57h+cbMaxValueLen], eax
0x1800e5309  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x1800e530c  add     rax, 4
0x1800e5310  cmp     rax, rcx
0x1800e5313  ja      loc_1800E543D
0x1800e5319  mov     eax, eax
0x1800e531b  mov     [rbp+57h+cbMaxValueNameLen], eax
0x1800e531e  inc     rax
0x1800e5321  cmp     rax, rcx
0x1800e5324  ja      loc_1800E543D
0x1800e532a  mov     ecx, eax
0x1800e532c  xor     edx, edx
0x1800e532e  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x1800e5334  mov     rsi, rax
0x1800e5337  mov     ecx, [rbp+57h+cbMaxValueLen]
0x1800e533a  xor     edx, edx
0x1800e533c  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x1800e5342  mov     rbx, rax
0x1800e5345  test    rsi, rsi
0x1800e5348  jz      loc_1800E5499
0x1800e534e  test    rax, rax
0x1800e5351  jz      loc_1800E5499
0x1800e5357  mov     r14d, edi
0x1800e535a  cmp     r14d, [rbp+57h+cValues]
0x1800e535e  jnb     loc_1800E5444
0x1800e5364  mov     ecx, [rbp+57h+cbMaxValueNameLen]
0x1800e5367  mov     [rbp+57h+cchValueName], ecx
0x1800e536a  mov     eax, [rbp+57h+cbMaxValueLen]
0x1800e536d  mov     [rbp+57h+cbData], eax
0x1800e5370  lea     rcx, [rbp+57h+var_60]
0x1800e5374  call    cs:__imp_??BKey@Registry@Mso@@QEBAPEAUHKEY__@@XZ; Mso::Registry::Key::operator HKEY__ *(void)
0x1800e537a  mov     rcx, rax; hKey
0x1800e537d  lea     rax, [rbp+57h+cbData]
0x1800e5381  mov     [rsp+0F0h+lpcValues], rax; lpcbData
0x1800e5386  mov     [rsp+0F0h+lpcbMaxClassLen], rbx; lpData
0x1800e538b  mov     [rsp+0F0h+lpcbMaxSubKeyLen], rdi; lpType
0x1800e5390  mov     [rsp+0F0h+lpcSubKeys], rdi; lpReserved
0x1800e5395  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x1800e5399  mov     r8, rsi; lpValueName
0x1800e539c  mov     edx, r14d; dwIndex
0x1800e539f  call    cs:__imp_RegEnumValueA
0x1800e53a5  mov     rcx, rbx
0x1800e53a8  call    sub_180468798
0x1800e53ad  test    al, al
0x1800e53af  jnz     short loc_1800E541E
0x1800e53b1  mov     ecx, [rbp+57h+cbData]
0x1800e53b4  add     rcx, r15
0x1800e53b7  xor     edx, edx
0x1800e53b9  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x1800e53bf  mov     [rbp+57h+var_78], rax
0x1800e53c3  test    rax, rax
0x1800e53c6  jz      loc_1800E546A
0x1800e53cc  cmp     [rbp+57h+cbData], 0Ch
0x1800e53d0  jb      short loc_1800E5426
0x1800e53d2  mov     r8d, [rbp+57h+cbData]; Size
0x1800e53d6  mov     edx, [rbx+8]
0x1800e53d9  mov     ecx, [rbx+4]
0x1800e53dc  add     rdx, 0Ch
0x1800e53e0  add     rdx, rcx
0x1800e53e3  cmp     r8, rdx
0x1800e53e6  jnz     short loc_1800E5426
0x1800e53e8  lea     rcx, [rax+8]; void *
0x1800e53ec  mov     rdx, rbx; Src
0x1800e53ef  call    memcpy_0
0x1800e53f4  mov     rdx, [rbp+57h+var_78]
0x1800e53f8  mov     rcx, rsi
0x1800e53fb  call    cs:__imp_?MsoParseHexIntSz@@YAHPEBDPEAH@Z; MsoParseHexIntSz(char const *,int *)
0x1800e5401  cmp     eax, [rbp+57h+cchValueName]
0x1800e5404  jnz     short loc_1800E5462
0x1800e5406  mov     rax, [rbp+57h+var_78]
0x1800e540a  mov     [rax+4], edi
0x1800e540d  lea     rdx, [rbp+57h+var_78]
0x1800e5411  mov     rcx, cs:?vppxpdi@@3PEAV?$MSOTPX@PEAUMSODIPLEXNODE@@@@EA; MSOTPX<MSODIPLEXNODE *> * vppxpdi
0x1800e5418  call    cs:__imp_?MsoIAppendPx@@YAHPEAXPEBX@Z; MsoIAppendPx(void *,void const *)
0x1800e541e  inc     r14d
0x1800e5421  jmp     loc_1800E535A
0x1800e5426  mov     ecx, 699815h
0x1800e542b  call    cs:__imp_MsoShipAssertTagProc
0x1800e5431  mov     rcx, [rbp+57h+var_78]
0x1800e5435  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1800e543b  jmp     short loc_1800E541E
0x1800e543d  mov     ecx, 5
0x1800e5442  int     29h; Win8: RtlFailFast(ecx)
0x1800e5444  mov     rcx, rsi
0x1800e5447  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1800e544d  mov     rcx, rbx
0x1800e5450  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1800e5456  mov     rdi, cs:?vppxpdi@@3PEAV?$MSOTPX@PEAUMSODIPLEXNODE@@@@EA; MSOTPX<MSODIPLEXNODE *> * vppxpdi
0x1800e545d  jmp     loc_1800E520F
0x1800e5462  mov     rax, [rbp+57h+var_78]
0x1800e5466  mov     [rax], edi
0x1800e5468  jmp     short loc_1800E5406
0x1800e546a  mov     rcx, cs:?vppxpdi@@3PEAV?$MSOTPX@PEAUMSODIPLEXNODE@@@@EA; struct MSODISABLEDITEM *
0x1800e5471  test    rcx, rcx
0x1800e5474  jz      short loc_1800E547B
0x1800e5476  call    ??_G?$MSOTPX@PEAUMSODIPLEXNODE@@@@QEAAPEAXI@Z; MSOTPX<MSODIPLEXNODE *>::`scalar deleting destructor'(uint)
0x1800e547b  mov     cs:?vppxpdi@@3PEAV?$MSOTPX@PEAUMSODIPLEXNODE@@@@EA, rdi; MSOTPX<MSODIPLEXNODE *> * vppxpdi
0x1800e5482  mov     rcx, rsi
0x1800e5485  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1800e548b  mov     rcx, rbx
0x1800e548e  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1800e5494  jmp     loc_1800E52B0
0x1800e5499  mov     rcx, cs:?vppxpdi@@3PEAV?$MSOTPX@PEAUMSODIPLEXNODE@@@@EA; struct MSODISABLEDITEM *
0x1800e54a0  test    rcx, rcx
0x1800e54a3  jz      short loc_1800E54AA
0x1800e54a5  call    ??_G?$MSOTPX@PEAUMSODIPLEXNODE@@@@QEAAPEAXI@Z; MSOTPX<MSODIPLEXNODE *>::`scalar deleting destructor'(uint)
0x1800e54aa  mov     cs:?vppxpdi@@3PEAV?$MSOTPX@PEAUMSODIPLEXNODE@@@@EA, rdi; MSOTPX<MSODIPLEXNODE *> * vppxpdi
0x1800e54b1  test    rsi, rsi
0x1800e54b4  jz      short loc_1800E54BF
0x1800e54b6  mov     rcx, rsi
0x1800e54b9  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1800e54bf  test    rbx, rbx
0x1800e54c2  jz      loc_1800E52B0
0x1800e54c8  jmp     short loc_1800E548B
```
