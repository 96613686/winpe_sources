# CWorkspace::InitializeSSPInstalledAppsFromRegistry(void)

- ea: `0x180031f10`
- end: `0x1800321de`
- name: `?InitializeSSPInstalledAppsFromRegistry@CWorkspace@@QEAAJXZ`
- size: `718`
- prototype: `__int64 __fastcall(CWorkspace *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180030dc4`

## callees

- `0x1800055d0`
- `0x18000b1d8`
- `0x18000d8d4`
- `0x18000ec54`
- `0x18000ec94`
- `0x18001e41c`
- `0x18001e610`
- `0x180025950`
- `0x180028b64`
- `0x180031f10`
- `0x18003af88`
- `0x18009a520`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800321b8`
- `ADVAPI32!RegCloseKey` at `0x1800321b8`
- `ADVAPI32!RegEnumKeyExW` at `0x1800320f5`
- `ADVAPI32!RegEnumKeyExW` at `0x1800320f5`
- `ADVAPI32!RegOpenKeyExW` at `0x180031ff5`
- `ADVAPI32!RegOpenKeyExW` at `0x180031ff5`

## string_xrefs

- `0x180031fbb`: `SSPInstalledApps`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall CWorkspace::InitializeSSPInstalledAppsFromRegistry(CWorkspace *this)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  char *v3; // r14
  __int64 v4; // rax
  __int64 v5; // rax
  const WCHAR *v6; // rax
  int v7; // ebx
  unsigned int v8; // esi
  unsigned int v9; // eax
  DWORD i; // esi
  LSTATUS v11; // eax
  unsigned int v12; // esi
  unsigned int v13; // eax
  DWORD cchName; // [rsp+44h] [rbp-294h] BYREF
  DWORD v16; // [rsp+48h] [rbp-290h]
  HKEY hKey[2]; // [rsp+50h] [rbp-288h] BYREF
  _BYTE v18[32]; // [rsp+60h] [rbp-278h] BYREF
  _BYTE v19[32]; // [rsp+80h] [rbp-258h] BYREF
  WCHAR Name[260]; // [rsp+A0h] [rbp-238h] BYREF

  hKey[1] = HKEY_DYN_DATA|0x7FFFFFF8LL;
  hKey[0] = 0;
  cchName = 256;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      113,
      WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
      CurrentThreadActivityIdPrefix);
  }
  v3 = (char *)this + 272;
  std::_Tree<std::_Tmap_traits<std::wstring,bool,KeyCompareLessIgnoreCase,std::allocator<std::pair<std::wstring const,bool>>,0>>::clear((char *)this + 272);
  v4 = std::operator+<unsigned short>(v19, (char *)this + 488, L"\\");
  v5 = std::operator+<unsigned short>(v18, v4, L"SSPInstalledApps");
  v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v5);
  v7 = RegOpenKeyExW(HKEY_CURRENT_USER, v6, 0, 0x20019u, hKey);
  std::wstring::~wstring(v18);
  std::wstring::~wstring(v19);
  if ( !*((_DWORD *)this + 66) && v7 == 2 )
  {
    v7 = 0;
    goto LABEL_35;
  }
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( v7 > 0 )
        v8 = (unsigned __int16)v7 | 0x80070000;
      else
        v8 = v7;
      v9 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 114, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids, v9, v8);
    }
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
    goto LABEL_35;
  }
  v16 = 0;
  v7 = 0;
  for ( i = 0; ; ++i )
  {
    v16 = i;
    if ( v7 == 259 )
    {
      v7 = 0;
      goto LABEL_35;
    }
    cchName = 256;
    v11 = RegEnumKeyExW(hKey[0], i, Name, &cchName, 0, 0, 0, 0);
    v7 = v11;
    if ( v11 )
      break;
    std::wstring::wstring(v18, Name);
    *(_BYTE *)std::map<std::wstring,bool,KeyCompareLessIgnoreCase,std::allocator<std::pair<std::wstring const,bool>>>::operator[](
                v3,
                v18) = 1;
    std::wstring::~wstring(v18);
LABEL_34:
    ;
  }
  if ( v11 == 259 )
    goto LABEL_34;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    if ( v11 > 0 )
      v12 = (unsigned __int16)v11 | 0x80070000;
    else
      v12 = v11;
    v13 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 115, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids, v13, v12);
  }
  if ( v7 > 0 )
    v7 = (unsigned __int16)v7 | 0x80070000;
LABEL_35:
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180031f10  push    rbx
0x180031f12  push    rsi
0x180031f13  push    r14
0x180031f15  push    r15
0x180031f17  sub     rsp, 2B8h
0x180031f1e  mov     [rsp+2D8h+var_280], 0FFFFFFFFFFFFFFFEh
0x180031f27  mov     rax, cs:__security_cookie
0x180031f2e  xor     rax, rsp
0x180031f31  mov     [rsp+2D8h+var_30], rax
0x180031f39  mov     rsi, rcx
0x180031f3c  mov     [rsp+2D8h+hKey], 0
0x180031f45  mov     [rsp+2D8h+cchName], 100h
0x180031f4d  lea     r15, WPP_GLOBAL_Control
0x180031f54  mov     rax, cs:WPP_GLOBAL_Control
0x180031f5b  cmp     rax, r15
0x180031f5e  jz      short loc_180031F90
0x180031f60  test    byte ptr [rax+1Ch], 1
0x180031f64  jz      short loc_180031F90
0x180031f66  cmp     byte ptr [rax+19h], 4
0x180031f6a  jb      short loc_180031F90
0x180031f6c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180031f71  mov     edx, 71h ; 'q'
0x180031f76  mov     r9d, eax
0x180031f79  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x180031f80  mov     rcx, cs:WPP_GLOBAL_Control
0x180031f87  mov     rcx, [rcx+10h]
0x180031f8b  call    WPP_SF_D
0x180031f90  lea     r14, [rsi+110h]
0x180031f97  mov     rcx, r14
0x180031f9a  call    ?clear@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NUKeyCompareLessIgnoreCase@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,bool,KeyCompareLessIgnoreCase,std::allocator<std::pair<std::wstring const,bool>>,0>>::clear(void)
0x180031f9f  lea     rdx, [rsi+1E8h]
0x180031fa6  lea     r8, SubStr; "\\"
0x180031fad  lea     rcx, [rsp+2D8h+var_258]
0x180031fb5  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@PEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const *)
0x180031fba  nop
0x180031fbb  lea     r8, aSspinstalledap; "SSPInstalledApps"
0x180031fc2  mov     rdx, rax
0x180031fc5  lea     rcx, [rsp+2D8h+var_278]
0x180031fca  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x180031fcf  nop
0x180031fd0  mov     rcx, rax
0x180031fd3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180031fd8  lea     rcx, [rsp+2D8h+hKey]
0x180031fdd  mov     [rsp+2D8h+phkResult], rcx; phkResult
0x180031fe2  mov     r9d, 20019h; samDesired
0x180031fe8  xor     r8d, r8d; ulOptions
0x180031feb  mov     rdx, rax; lpSubKey
0x180031fee  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180031ff5  call    cs:__imp_RegOpenKeyExW
0x180031ffb  mov     ebx, eax
0x180031ffd  lea     rcx, [rsp+2D8h+var_278]; void *
0x180032002  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180032007  nop
0x180032008  lea     rcx, [rsp+2D8h+var_258]; void *
0x180032010  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180032015  cmp     dword ptr [rsi+108h], 0
0x18003201c  jnz     short loc_18003202E
0x18003201e  cmp     ebx, 2
0x180032021  jnz     short loc_18003202E
0x180032023  xor     ebx, ebx
0x180032025  mov     [rsp+2D8h+var_298], ebx
0x180032029  jmp     loc_1800321AE
0x18003202e  test    ebx, ebx
0x180032030  jz      short loc_180032099
0x180032032  mov     rax, cs:WPP_GLOBAL_Control
0x180032039  cmp     rax, r15
0x18003203c  jz      short loc_180032083
0x18003203e  test    byte ptr [rax+1Ch], 8
0x180032042  jz      short loc_180032083
0x180032044  cmp     byte ptr [rax+19h], 2
0x180032048  jb      short loc_180032083
0x18003204a  test    ebx, ebx
0x18003204c  jg      short loc_180032052
0x18003204e  mov     esi, ebx
0x180032050  jmp     short loc_18003205B
0x180032052  movzx   esi, bx
0x180032055  or      esi, 80070000h
0x18003205b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180032060  mov     edx, 72h ; 'r'
0x180032065  mov     dword ptr [rsp+2D8h+phkResult], esi
0x180032069  mov     r9d, eax
0x18003206c  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x180032073  mov     rcx, cs:WPP_GLOBAL_Control
0x18003207a  mov     rcx, [rcx+10h]
0x18003207e  call    WPP_SF_Dd
0x180032083  test    ebx, ebx
0x180032085  jle     short loc_180032090
0x180032087  movzx   ebx, bx
0x18003208a  or      ebx, 80070000h
0x180032090  mov     [rsp+2D8h+var_298], ebx
0x180032094  jmp     loc_1800321AE
0x180032099  mov     [rsp+2D8h+var_290], 0
0x1800320a1  xor     ebx, ebx
0x1800320a3  xor     esi, esi
0x1800320a5  mov     [rsp+2D8h+var_290], esi
0x1800320a9  cmp     ebx, 103h
0x1800320af  jz      loc_1800321A4
0x1800320b5  mov     [rsp+2D8h+cchName], 100h
0x1800320bd  mov     [rsp+2D8h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1800320c6  mov     [rsp+2D8h+lpcchClass], 0; lpcchClass
0x1800320cf  mov     [rsp+2D8h+lpClass], 0; lpClass
0x1800320d8  mov     [rsp+2D8h+phkResult], 0; lpReserved
0x1800320e1  lea     r9, [rsp+2D8h+cchName]; lpcchName
0x1800320e6  lea     r8, [rsp+2D8h+Name]; lpName
0x1800320ee  mov     edx, esi; dwIndex
0x1800320f0  mov     rcx, [rsp+2D8h+hKey]; hKey
0x1800320f5  call    cs:__imp_RegEnumKeyExW
0x1800320fb  mov     ebx, eax
0x1800320fd  test    eax, eax
0x1800320ff  jz      short loc_180032170
0x180032101  cmp     eax, 103h
0x180032106  jz      loc_18003219D
0x18003210c  mov     rax, cs:WPP_GLOBAL_Control
0x180032113  cmp     rax, r15
0x180032116  jz      short loc_18003215D
0x180032118  test    byte ptr [rax+1Ch], 8
0x18003211c  jz      short loc_18003215D
0x18003211e  cmp     byte ptr [rax+19h], 2
0x180032122  jb      short loc_18003215D
0x180032124  test    ebx, ebx
0x180032126  jg      short loc_18003212C
0x180032128  mov     esi, ebx
0x18003212a  jmp     short loc_180032135
0x18003212c  movzx   esi, bx
0x18003212f  or      esi, 80070000h
0x180032135  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003213a  mov     edx, 73h ; 's'
0x18003213f  mov     dword ptr [rsp+2D8h+phkResult], esi
0x180032143  mov     r9d, eax
0x180032146  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x18003214d  mov     rcx, cs:WPP_GLOBAL_Control
0x180032154  mov     rcx, [rcx+10h]
0x180032158  call    WPP_SF_Dd
0x18003215d  test    ebx, ebx
0x18003215f  jle     short loc_18003216A
0x180032161  movzx   ebx, bx
0x180032164  or      ebx, 80070000h
0x18003216a  mov     [rsp+2D8h+var_298], ebx
0x18003216e  jmp     short loc_1800321AE
0x180032170  lea     rdx, [rsp+2D8h+Name]
0x180032178  lea     rcx, [rsp+2D8h+var_278]
0x18003217d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180032182  nop
0x180032183  lea     rdx, [rsp+2D8h+var_278]
0x180032188  mov     rcx, r14
0x18003218b  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NUKeyCompareLessIgnoreCase@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@@std@@QEAAAEA_N$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,bool,KeyCompareLessIgnoreCase,std::allocator<std::pair<std::wstring const,bool>>>::operator[](std::wstring &&)
0x180032190  mov     byte ptr [rax], 1
0x180032193  lea     rcx, [rsp+2D8h+var_278]; void *
0x180032198  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003219d  inc     esi
0x18003219f  jmp     loc_1800320A5
0x1800321a4  xor     ebx, ebx
0x1800321a6  jmp     short loc_1800321AE
0x1800321a8  jmp     short $+2
0x1800321aa  mov     ebx, [rsp+2D8h+var_298]
0x1800321ae  mov     rcx, [rsp+2D8h+hKey]; hKey
0x1800321b3  test    rcx, rcx
0x1800321b6  jz      short loc_1800321BE
0x1800321b8  call    cs:__imp_RegCloseKey
0x1800321be  mov     eax, ebx
0x1800321c0  mov     rcx, [rsp+2D8h+var_30]
0x1800321c8  xor     rcx, rsp; StackCookie
0x1800321cb  call    __security_check_cookie
0x1800321d0  add     rsp, 2B8h
0x1800321d7  pop     r15
0x1800321d9  pop     r14
0x1800321db  pop     rsi
0x1800321dc  pop     rbx
0x1800321dd  retn
```
