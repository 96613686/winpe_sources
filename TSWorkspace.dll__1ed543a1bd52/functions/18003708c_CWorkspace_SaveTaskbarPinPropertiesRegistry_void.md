# CWorkspace::SaveTaskbarPinPropertiesRegistry(void *)

- ea: `0x18003708c`
- end: `0x180037375`
- name: `?SaveTaskbarPinPropertiesRegistry@CWorkspace@@QEAAJPEAX@Z`
- size: `745`
- prototype: `__int64 __fastcall(CWorkspace *this, void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x180034ffc`

## callees

- `0x1800055d0`
- `0x18000b1d8`
- `0x18000d8d4`
- `0x18000ec94`
- `0x18000ece0`
- `0x18001e41c`
- `0x180025950`
- `0x18003708c`
- `0x180057d58`
- `0x18009a520`

## import_xrefs

- `ADVAPI32!RegCreateKeyTransactedW` at `0x180037164`
- `ADVAPI32!RegCreateKeyTransactedW` at `0x180037164`
- `ADVAPI32!RegCloseKey` at `0x180037349`
- `ADVAPI32!RegCloseKey` at `0x180037349`
- `KERNEL32!RegDeleteTreeW` at `0x1800371f3`
- `KERNEL32!RegDeleteTreeW` at `0x1800371f3`

## string_xrefs

- `0x1800370e7`: `TaskbarPinIdToPropertyMap`
- `0x1800372e8`: `CWorkspaceTaskbarPin::CreateTaskbarPinRegistryEntry failed`

## pseudocode

```c
__int64 __fastcall CWorkspace::SaveTaskbarPinPropertiesRegistry(CWorkspace *this, void *a2)
{
  __int64 v4; // rax
  const WCHAR *v5; // rax
  int TaskbarPinRegistryEntry; // ebx
  unsigned int v7; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v9; // edi
  unsigned int v10; // eax
  unsigned __int64 i; // rdi
  __int64 v12; // rcx
  unsigned int v13; // eax
  __int64 samDesired; // [rsp+28h] [rbp-D0h]
  HKEY hKey; // [rsp+68h] [rbp-90h] BYREF
  DWORD dwDisposition; // [rsp+70h] [rbp-88h] BYREF
  unsigned __int64 v18; // [rsp+78h] [rbp-80h]
  __int64 v19; // [rsp+80h] [rbp-78h]
  _BYTE v20[32]; // [rsp+88h] [rbp-70h] BYREF
  _BYTE v21[40]; // [rsp+A8h] [rbp-50h] BYREF

  v19 = -2;
  hKey = 0;
  dwDisposition = 0;
  v4 = std::operator+<unsigned short>(v21, (char *)this + 488, L"\\");
  std::operator+<unsigned short>(v20, v4, L"TaskbarPinIdToPropertyMap");
  std::wstring::~wstring(v21);
  v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v20);
  TaskbarPinRegistryEntry = RegCreateKeyTransactedW(
                              HKEY_CURRENT_USER,
                              v5,
                              0,
                              0,
                              0,
                              0x2001Fu,
                              0,
                              &hKey,
                              &dwDisposition,
                              a2,
                              0);
  if ( TaskbarPinRegistryEntry )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( TaskbarPinRegistryEntry > 0 )
        v7 = (unsigned __int16)TaskbarPinRegistryEntry | 0x80070000;
      else
        v7 = TaskbarPinRegistryEntry;
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        223,
        WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
        CurrentThreadActivityIdPrefix,
        v7);
    }
    if ( TaskbarPinRegistryEntry > 0 )
      TaskbarPinRegistryEntry = (unsigned __int16)TaskbarPinRegistryEntry | 0x80070000;
  }
  else
  {
    TaskbarPinRegistryEntry = RegDeleteTreeW(hKey, 0);
    if ( TaskbarPinRegistryEntry )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        if ( TaskbarPinRegistryEntry > 0 )
          v9 = (unsigned __int16)TaskbarPinRegistryEntry | 0x80070000;
        else
          v9 = TaskbarPinRegistryEntry;
        v10 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 224, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids, v10, v9);
      }
      if ( TaskbarPinRegistryEntry > 0 )
        TaskbarPinRegistryEntry = (unsigned __int16)TaskbarPinRegistryEntry | 0x80070000;
    }
    else
    {
      for ( i = 0; ; ++i )
      {
        v18 = i;
        v12 = *((_QWORD *)this + 101);
        if ( i >= (*((_QWORD *)this + 102) - v12) >> 3 )
        {
          std::wstring::~wstring(v20);
          TaskbarPinRegistryEntry = 0;
          goto LABEL_33;
        }
        TaskbarPinRegistryEntry = CWorkspaceTaskbarPin::CreateTaskbarPinRegistryEntry(
                                    *(CWorkspaceTaskbarPin **)(v12 + 8 * i),
                                    a2,
                                    hKey);
        if ( TaskbarPinRegistryEntry < 0 )
          break;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = RdpWppGetCurrentThreadActivityIdPrefix();
        LODWORD(samDesired) = TaskbarPinRegistryEntry;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          225,
          (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
          v13,
          (__int64)"CWorkspaceTaskbarPin::CreateTaskbarPinRegistryEntry failed",
          samDesired);
      }
    }
  }
  std::wstring::~wstring(v20);
LABEL_33:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)TaskbarPinRegistryEntry;
}

```

## disassembly

```asm
0x18003708c  mov     r11, rsp
0x18003708f  push    rsi
0x180037090  push    rdi
0x180037091  push    r14
0x180037093  sub     rsp, 0E0h
0x18003709a  mov     qword ptr [r11-78h], 0FFFFFFFFFFFFFFFEh
0x1800370a2  mov     [r11+18h], rbx
0x1800370a6  mov     rax, cs:__security_cookie
0x1800370ad  xor     rax, rsp
0x1800370b0  mov     [rsp+0F8h+var_28], rax
0x1800370b8  mov     r14, rdx
0x1800370bb  mov     rsi, rcx
0x1800370be  mov     [rsp+0F8h+hKey], 0
0x1800370c7  mov     [rsp+0F8h+dwDisposition], 0
0x1800370cf  lea     rdx, [rcx+1E8h]
0x1800370d6  lea     r8, SubStr; "\\"
0x1800370dd  lea     rcx, [r11-50h]
0x1800370e1  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@PEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const *)
0x1800370e6  nop
0x1800370e7  lea     r8, aTaskbarpinidto; "TaskbarPinIdToPropertyMap"
0x1800370ee  mov     rdx, rax
0x1800370f1  lea     rcx, [rsp+0F8h+var_70]
0x1800370f9  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x1800370fe  nop
0x1800370ff  lea     rcx, [rsp+0F8h+var_50]; void *
0x180037107  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003710c  lea     rcx, [rsp+0F8h+var_70]
0x180037114  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180037119  mov     rdx, rax; lpSubKey
0x18003711c  mov     [rsp+0F8h+pExtendedParemeter], 0; pExtendedParemeter
0x180037125  mov     [rsp+0F8h+hTransaction], r14; hTransaction
0x18003712a  lea     rax, [rsp+0F8h+dwDisposition]
0x18003712f  mov     [rsp+0F8h+lpdwDisposition], rax; lpdwDisposition
0x180037134  lea     rax, [rsp+0F8h+hKey]
0x180037139  mov     [rsp+0F8h+phkResult], rax; phkResult
0x18003713e  mov     [rsp+0F8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180037147  mov     dword ptr [rsp+0F8h+samDesired], 2001Fh; samDesired
0x18003714f  mov     [rsp+0F8h+dwOptions], 0; dwOptions
0x180037157  xor     r9d, r9d; lpClass
0x18003715a  xor     r8d, r8d; Reserved
0x18003715d  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180037164  call    cs:__imp_RegCreateKeyTransactedW
0x18003716a  mov     ebx, eax
0x18003716c  test    eax, eax
0x18003716e  jz      short loc_1800371EC
0x180037170  lea     rax, WPP_GLOBAL_Control
0x180037177  mov     rcx, cs:WPP_GLOBAL_Control
0x18003717e  cmp     rcx, rax
0x180037181  jz      short loc_1800371C8
0x180037183  test    byte ptr [rcx+1Ch], 8
0x180037187  jz      short loc_1800371C8
0x180037189  cmp     byte ptr [rcx+19h], 2
0x18003718d  jb      short loc_1800371C8
0x18003718f  test    ebx, ebx
0x180037191  jg      short loc_180037197
0x180037193  mov     edi, ebx
0x180037195  jmp     short loc_1800371A0
0x180037197  movzx   edi, bx
0x18003719a  or      edi, 80070000h
0x1800371a0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800371a5  mov     edx, 0DFh
0x1800371aa  mov     [rsp+0F8h+dwOptions], edi
0x1800371ae  mov     r9d, eax
0x1800371b1  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x1800371b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800371bf  mov     rcx, [rcx+10h]
0x1800371c3  call    WPP_SF_Dd
0x1800371c8  test    ebx, ebx
0x1800371ca  jle     short loc_1800371D5
0x1800371cc  movzx   ebx, bx
0x1800371cf  or      ebx, 80070000h
0x1800371d5  mov     [rsp+0F8h+var_98], ebx
0x1800371d9  lea     rcx, [rsp+0F8h+var_70]; void *
0x1800371e1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800371e6  nop
0x1800371e7  jmp     loc_18003733F
0x1800371ec  xor     edx, edx; lpSubKey
0x1800371ee  mov     rcx, [rsp+0F8h+hKey]; hKey
0x1800371f3  call    cs:__imp_RegDeleteTreeW
0x1800371f9  mov     ebx, eax
0x1800371fb  test    eax, eax
0x1800371fd  jz      short loc_18003727B
0x1800371ff  lea     rax, WPP_GLOBAL_Control
0x180037206  mov     rcx, cs:WPP_GLOBAL_Control
0x18003720d  cmp     rcx, rax
0x180037210  jz      short loc_180037257
0x180037212  test    byte ptr [rcx+1Ch], 8
0x180037216  jz      short loc_180037257
0x180037218  cmp     byte ptr [rcx+19h], 2
0x18003721c  jb      short loc_180037257
0x18003721e  test    ebx, ebx
0x180037220  jg      short loc_180037226
0x180037222  mov     edi, ebx
0x180037224  jmp     short loc_18003722F
0x180037226  movzx   edi, bx
0x180037229  or      edi, 80070000h
0x18003722f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180037234  mov     edx, 0E0h
0x180037239  mov     [rsp+0F8h+dwOptions], edi
0x18003723d  mov     r9d, eax
0x180037240  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x180037247  mov     rcx, cs:WPP_GLOBAL_Control
0x18003724e  mov     rcx, [rcx+10h]
0x180037252  call    WPP_SF_Dd
0x180037257  test    ebx, ebx
0x180037259  jle     short loc_180037264
0x18003725b  movzx   ebx, bx
0x18003725e  or      ebx, 80070000h
0x180037264  mov     [rsp+0F8h+var_98], ebx
0x180037268  lea     rcx, [rsp+0F8h+var_70]; void *
0x180037270  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180037275  nop
0x180037276  jmp     loc_18003733F
0x18003727b  xor     edi, edi
0x18003727d  mov     [rsp+0F8h+var_80], rdi
0x180037282  mov     rcx, [rsi+328h]
0x180037289  mov     rax, [rsi+330h]
0x180037290  sub     rax, rcx
0x180037293  sar     rax, 3
0x180037297  cmp     rdi, rax
0x18003729a  jnb     loc_180037327
0x1800372a0  mov     r8, [rsp+0F8h+hKey]; HKEY
0x1800372a5  mov     rdx, r14; void *
0x1800372a8  mov     rcx, [rcx+rdi*8]; this
0x1800372ac  call    ?CreateTaskbarPinRegistryEntry@CWorkspaceTaskbarPin@@QEAAJPEAXPEAUHKEY__@@@Z; CWorkspaceTaskbarPin::CreateTaskbarPinRegistryEntry(void *,HKEY__ *)
0x1800372b1  mov     ebx, eax
0x1800372b3  mov     [rsp+0F8h+var_98], eax
0x1800372b7  test    eax, eax
0x1800372b9  jns     short loc_18003731F
0x1800372bb  lea     rax, WPP_GLOBAL_Control
0x1800372c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800372c9  cmp     rcx, rax
0x1800372cc  jz      short loc_18003730F
0x1800372ce  test    byte ptr [rcx+1Ch], 8
0x1800372d2  jz      short loc_18003730F
0x1800372d4  cmp     byte ptr [rcx+19h], 2
0x1800372d8  jb      short loc_18003730F
0x1800372da  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800372df  mov     edx, 0E1h
0x1800372e4  mov     dword ptr [rsp+0F8h+samDesired], ebx
0x1800372e8  lea     rcx, aCworkspacetask; "CWorkspaceTaskbarPin::CreateTaskbarPinR"...
0x1800372ef  mov     qword ptr [rsp+0F8h+dwOptions], rcx
0x1800372f4  mov     r9d, eax
0x1800372f7  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x1800372fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180037305  mov     rcx, [rcx+10h]
0x180037309  call    WPP_SF_DsD
0x18003730e  nop
0x18003730f  lea     rcx, [rsp+0F8h+var_70]; void *
0x180037317  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003731c  nop
0x18003731d  jmp     short loc_18003733F
0x18003731f  inc     rdi
0x180037322  jmp     loc_18003727D
0x180037327  lea     rcx, [rsp+0F8h+var_70]; void *
0x18003732f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180037334  nop
0x180037335  xor     ebx, ebx
0x180037337  jmp     short loc_18003733F
0x180037339  jmp     short $+2
0x18003733b  mov     ebx, [rsp+0F8h+var_98]
0x18003733f  mov     rcx, [rsp+0F8h+hKey]; hKey
0x180037344  test    rcx, rcx
0x180037347  jz      short loc_18003734F
0x180037349  call    cs:__imp_RegCloseKey
0x18003734f  mov     eax, ebx
0x180037351  mov     rcx, [rsp+0F8h+var_28]
0x180037359  xor     rcx, rsp; StackCookie
0x18003735c  call    __security_check_cookie
0x180037361  mov     rbx, [rsp+0F8h+arg_10]
0x180037369  add     rsp, 0E0h
0x180037370  pop     r14
0x180037372  pop     rdi
0x180037373  pop     rsi
0x180037374  retn
```
