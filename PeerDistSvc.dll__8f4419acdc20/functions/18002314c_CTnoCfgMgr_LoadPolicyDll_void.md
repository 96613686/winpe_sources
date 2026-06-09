# CTnoCfgMgr::LoadPolicyDll(void)

- ea: `0x18002314c`
- end: `0x1800234ac`
- name: `?LoadPolicyDll@CTnoCfgMgr@@AEAAJXZ`
- size: `864`
- prototype: `__int64 __fastcall(CTnoCfgMgr *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180026c60`

## callees

- `0x1800024f0`
- `0x180008290`
- `0x18000cf48`
- `0x180021310`
- `0x180022218`
- `0x18002314c`
- `0x180138f50`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180023444`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180023444`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800232ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023350`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800233b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800232ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023350`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800233b8`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800232d3`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800232d3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002319f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002319f`

## string_xrefs

- `0x1800231bd`: `userenv.dll`
- `0x1800231c9`: `PolicyDllName`

## pseudocode

```c
__int64 __fastcall CTnoCfgMgr::LoadPolicyDll(CTnoCfgMgr *this)
{
  LSTATUS v2; // eax
  const unsigned __int16 *v3; // rdx
  unsigned int v4; // ebx
  unsigned int RegStringValueW; // eax
  const unsigned __int16 *v6; // rdx
  CHostedCacheMsgEncoding *v7; // rcx
  __int64 v8; // rdx
  const unsigned __int16 *v9; // rdx
  __int64 v10; // r9
  HMODULE LibraryW; // rax
  DWORD LastError; // eax
  __int64 (*ProcAddressW)(void); // rax
  DWORD v14; // eax
  __int64 (*v15)(void); // rax
  DWORD v16; // eax
  HMODULE v17; // rcx
  LPCWCH lpWideCharStr; // [rsp+30h] [rbp-10h] BYREF
  HKEY hkey; // [rsp+68h] [rbp+28h] BYREF
  LPCWSTR lpLibFileName; // [rsp+70h] [rbp+30h] BYREF
  void *Block; // [rsp+78h] [rbp+38h] BYREF

  hkey = 0;
  lpLibFileName = 0;
  Block = 0;
  lpWideCharStr = 0;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\PeerDist",
         0,
         0x20119u,
         &hkey);
  v4 = 0;
  if ( v2 != 2 )
    v4 = v2;
  if ( v4 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v8 = 230;
      v10 = v4;
      goto LABEL_43;
    }
    goto LABEL_44;
  }
  RegStringValueW = GetRegStringValueW(hkey, v3, L"PolicyDllName", L"userenv.dll", (unsigned __int16 **)&lpLibFileName);
  v4 = RegStringValueW;
  if ( RegStringValueW )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v8 = 229;
LABEL_19:
      v10 = RegStringValueW;
LABEL_43:
      WPP_SF_d(*((_QWORD *)v7 + 12), v8, WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids, v10);
      goto LABEL_44;
    }
    goto LABEL_44;
  }
  RegStringValueW = GetRegStringValueW(
                      hkey,
                      v6,
                      L"RegisterNotificationProcName",
                      L"RegisterGPNotification",
                      (unsigned __int16 **)&Block);
  v4 = RegStringValueW;
  if ( RegStringValueW )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v8 = 231;
      goto LABEL_19;
    }
LABEL_44:
    v17 = (HMODULE)*((_QWORD *)this + 18);
    if ( v17 )
    {
      FreeLibrary(v17);
      *((_QWORD *)this + 18) = 0;
      *((_QWORD *)this + 19) = 0;
      *((_QWORD *)this + 20) = 0;
    }
    goto LABEL_46;
  }
  RegStringValueW = GetRegStringValueW(
                      hkey,
                      v9,
                      L"UnRegisterNotificationProcName",
                      L"UnregisterGPNotification",
                      (unsigned __int16 **)&lpWideCharStr);
  v4 = RegStringValueW;
  if ( RegStringValueW )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v8 = 232;
      goto LABEL_19;
    }
    goto LABEL_44;
  }
  LibraryW = LoadLibraryW(lpLibFileName);
  *((_QWORD *)this + 18) = LibraryW;
  if ( !LibraryW )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        233,
        (unsigned int)WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids,
        (_DWORD)lpLibFileName,
        LastError);
    }
    if ( v4 )
      goto LABEL_44;
  }
  ProcAddressW = GetProcAddressW(*((HINSTANCE *)this + 18), (LPCWCH)Block);
  *((_QWORD *)this + 19) = ProcAddressW;
  if ( !ProcAddressW )
  {
    v14 = GetLastError();
    v4 = v14;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        234,
        (unsigned int)WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids,
        (_DWORD)Block,
        v14);
    }
    if ( v4 )
      goto LABEL_44;
  }
  v15 = GetProcAddressW(*((HINSTANCE *)this + 18), lpWideCharStr);
  *((_QWORD *)this + 20) = v15;
  if ( !v15 )
  {
    v16 = GetLastError();
    v4 = v16;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        235,
        (unsigned int)WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids,
        (_DWORD)lpWideCharStr,
        v16);
    }
    if ( v4 )
      goto LABEL_44;
  }
LABEL_46:
  operator delete((void *)lpLibFileName);
  operator delete(Block);
  operator delete((void *)lpWideCharStr);
  if ( (int)v4 > 0 )
    v4 = (unsigned __int16)v4 | 0x80070000;
  AutoRegKey::Close((AutoRegKey *)&hkey);
  return v4;
}

```

## disassembly

```asm
0x18002314c  mov     [rsp-18h+arg_0], rbx
0x180023151  push    rbp
0x180023152  push    rsi
0x180023153  push    r14
0x180023155  mov     rbp, rsp
0x180023158  sub     rsp, 40h
0x18002315c  mov     r14, rcx
0x18002315f  mov     [rbp+hkey], 0
0x180023167  lea     rax, [rbp+hkey]
0x18002316b  mov     [rbp+lpLibFileName], 0
0x180023173  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002317a  mov     [rsp+40h+phkResult], rax; phkResult
0x18002317f  mov     r9d, 20119h; samDesired
0x180023185  mov     [rbp+Block], 0
0x18002318d  xor     r8d, r8d; ulOptions
0x180023190  mov     [rbp+lpWideCharStr], 0
0x180023198  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x18002319f  call    cs:__imp_RegOpenKeyExW
0x1800231a5  xor     ebx, ebx
0x1800231a7  cmp     eax, 2
0x1800231aa  cmovnz  ebx, eax
0x1800231ad  test    ebx, ebx
0x1800231af  jnz     loc_1800233FE
0x1800231b5  mov     rcx, [rbp+hkey]; hkey
0x1800231b9  lea     rax, [rbp+lpLibFileName]
0x1800231bd  lea     r9, aUserenvDll; "userenv.dll"
0x1800231c4  mov     [rsp+40h+phkResult], rax; unsigned __int16 **
0x1800231c9  lea     r8, aPolicydllname; "PolicyDllName"
0x1800231d0  call    ?GetRegStringValueW@@YAJPEAUHKEY__@@PEBG11PEAPEAG@Z; GetRegStringValueW(HKEY__ *,ushort const *,ushort const *,ushort const *,ushort * *)
0x1800231d5  mov     ebx, eax
0x1800231d7  test    eax, eax
0x1800231d9  jz      short loc_180023213
0x1800231db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800231e2  lea     rsi, WPP_GLOBAL_Control
0x1800231e9  cmp     rcx, rsi
0x1800231ec  jz      loc_180023438
0x1800231f2  test    dword ptr [rcx+6Ch], 200h
0x1800231f9  jz      loc_180023438
0x1800231ff  cmp     byte ptr [rcx+69h], 1
0x180023203  jb      loc_180023438
0x180023209  mov     edx, 0E5h
0x18002320e  jmp     loc_1800232C7
0x180023213  mov     rcx, [rbp+hkey]; hkey
0x180023217  lea     rax, [rbp+Block]
0x18002321b  lea     r9, aRegistergpnoti; "RegisterGPNotification"
0x180023222  mov     [rsp+40h+phkResult], rax; unsigned __int16 **
0x180023227  lea     r8, aRegisternotifi; "RegisterNotificationProcName"
0x18002322e  call    ?GetRegStringValueW@@YAJPEAUHKEY__@@PEBG11PEAPEAG@Z; GetRegStringValueW(HKEY__ *,ushort const *,ushort const *,ushort const *,ushort * *)
0x180023233  mov     ebx, eax
0x180023235  test    eax, eax
0x180023237  jz      short loc_18002326E
0x180023239  mov     rcx, cs:WPP_GLOBAL_Control
0x180023240  lea     rsi, WPP_GLOBAL_Control
0x180023247  cmp     rcx, rsi
0x18002324a  jz      loc_180023438
0x180023250  test    dword ptr [rcx+6Ch], 200h
0x180023257  jz      loc_180023438
0x18002325d  cmp     byte ptr [rcx+69h], 1
0x180023261  jb      loc_180023438
0x180023267  mov     edx, 0E7h
0x18002326c  jmp     short loc_1800232C7
0x18002326e  mov     rcx, [rbp+hkey]; hkey
0x180023272  lea     rax, [rbp+lpWideCharStr]
0x180023276  lea     r9, aUnregistergpno; "UnregisterGPNotification"
0x18002327d  mov     [rsp+40h+phkResult], rax; unsigned __int16 **
0x180023282  lea     r8, aUnregisternoti; "UnRegisterNotificationProcName"
0x180023289  call    ?GetRegStringValueW@@YAJPEAUHKEY__@@PEBG11PEAPEAG@Z; GetRegStringValueW(HKEY__ *,ushort const *,ushort const *,ushort const *,ushort * *)
0x18002328e  mov     ebx, eax
0x180023290  test    eax, eax
0x180023292  jz      short loc_1800232CF
0x180023294  mov     rcx, cs:WPP_GLOBAL_Control
0x18002329b  lea     rsi, WPP_GLOBAL_Control
0x1800232a2  cmp     rcx, rsi
0x1800232a5  jz      loc_180023438
0x1800232ab  test    dword ptr [rcx+6Ch], 200h
0x1800232b2  jz      loc_180023438
0x1800232b8  cmp     byte ptr [rcx+69h], 1
0x1800232bc  jb      loc_180023438
0x1800232c2  mov     edx, 0E8h
0x1800232c7  mov     r9d, eax
0x1800232ca  jmp     loc_180023428
0x1800232cf  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x1800232d3  call    cs:__imp_LoadLibraryW
0x1800232d9  mov     [r14+90h], rax
0x1800232e0  lea     rsi, WPP_GLOBAL_Control
0x1800232e7  test    rax, rax
0x1800232ea  jnz     short loc_180023334
0x1800232ec  call    cs:__imp_GetLastError
0x1800232f2  mov     ebx, eax
0x1800232f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800232fb  cmp     rcx, rsi
0x1800232fe  jz      short loc_18002332C
0x180023300  test    dword ptr [rcx+6Ch], 200h
0x180023307  jz      short loc_18002332C
0x180023309  cmp     byte ptr [rcx+69h], 1
0x18002330d  jb      short loc_18002332C
0x18002330f  mov     r9, [rbp+lpLibFileName]
0x180023313  lea     r8, WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids
0x18002331a  mov     rcx, [rcx+60h]
0x18002331e  mov     edx, 0E9h
0x180023323  mov     dword ptr [rsp+40h+phkResult], eax
0x180023327  call    WPP_SF_Sd
0x18002332c  test    ebx, ebx
0x18002332e  jnz     loc_180023438
0x180023334  mov     rdx, [rbp+Block]; lpWideCharStr
0x180023338  mov     rcx, [r14+90h]; hModule
0x18002333f  call    ?GetProcAddressW@@YAP6A_JXZPEAUHINSTANCE__@@PEBG@Z; GetProcAddressW(HINSTANCE__ *,ushort const *)
0x180023344  mov     [r14+98h], rax
0x18002334b  test    rax, rax
0x18002334e  jnz     short loc_180023398
0x180023350  call    cs:__imp_GetLastError
0x180023356  mov     ebx, eax
0x180023358  mov     rcx, cs:WPP_GLOBAL_Control
0x18002335f  cmp     rcx, rsi
0x180023362  jz      short loc_180023390
0x180023364  test    dword ptr [rcx+6Ch], 200h
0x18002336b  jz      short loc_180023390
0x18002336d  cmp     byte ptr [rcx+69h], 1
0x180023371  jb      short loc_180023390
0x180023373  mov     r9, [rbp+Block]
0x180023377  lea     r8, WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids
0x18002337e  mov     rcx, [rcx+60h]
0x180023382  mov     edx, 0EAh
0x180023387  mov     dword ptr [rsp+40h+phkResult], eax
0x18002338b  call    WPP_SF_Sd
0x180023390  test    ebx, ebx
0x180023392  jnz     loc_180023438
0x180023398  mov     rdx, [rbp+lpWideCharStr]; lpWideCharStr
0x18002339c  mov     rcx, [r14+90h]; hModule
0x1800233a3  call    ?GetProcAddressW@@YAP6A_JXZPEAUHINSTANCE__@@PEBG@Z; GetProcAddressW(HINSTANCE__ *,ushort const *)
0x1800233a8  mov     [r14+0A0h], rax
0x1800233af  test    rax, rax
0x1800233b2  jnz     loc_18002346B
0x1800233b8  call    cs:__imp_GetLastError
0x1800233be  mov     ebx, eax
0x1800233c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800233c7  cmp     rcx, rsi
0x1800233ca  jz      short loc_1800233F8
0x1800233cc  test    dword ptr [rcx+6Ch], 200h
0x1800233d3  jz      short loc_1800233F8
0x1800233d5  cmp     byte ptr [rcx+69h], 1
0x1800233d9  jb      short loc_1800233F8
0x1800233db  mov     r9, [rbp+lpWideCharStr]
0x1800233df  lea     r8, WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids
0x1800233e6  mov     rcx, [rcx+60h]
0x1800233ea  mov     edx, 0EBh
0x1800233ef  mov     dword ptr [rsp+40h+phkResult], eax
0x1800233f3  call    WPP_SF_Sd
0x1800233f8  test    ebx, ebx
0x1800233fa  jz      short loc_18002346B
0x1800233fc  jmp     short loc_180023438
0x1800233fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180023405  lea     rsi, WPP_GLOBAL_Control
0x18002340c  cmp     rcx, rsi
0x18002340f  jz      short loc_180023438
0x180023411  test    dword ptr [rcx+6Ch], 200h
0x180023418  jz      short loc_180023438
0x18002341a  cmp     byte ptr [rcx+69h], 1
0x18002341e  jb      short loc_180023438
0x180023420  mov     edx, 0E6h
0x180023425  mov     r9d, ebx
0x180023428  mov     rcx, [rcx+60h]
0x18002342c  lea     r8, WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids
0x180023433  call    WPP_SF_d
0x180023438  mov     rcx, [r14+90h]; hLibModule
0x18002343f  test    rcx, rcx
0x180023442  jz      short loc_18002346B
0x180023444  call    cs:__imp_FreeLibrary
0x18002344a  mov     qword ptr [r14+90h], 0
0x180023455  mov     qword ptr [r14+98h], 0
0x180023460  mov     qword ptr [r14+0A0h], 0
0x18002346b  mov     rcx, [rbp+lpLibFileName]; Block
0x18002346f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180023474  mov     rcx, [rbp+Block]; Block
0x180023478  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002347d  mov     rcx, [rbp+lpWideCharStr]; Block
0x180023481  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180023486  test    ebx, ebx
0x180023488  jle     short loc_180023493
0x18002348a  movzx   ebx, bx
0x18002348d  or      ebx, 80070000h
0x180023493  lea     rcx, [rbp+hkey]; this
0x180023497  call    ?Close@AutoRegKey@@QEAAXXZ; AutoRegKey::Close(void)
0x18002349c  mov     eax, ebx
0x18002349e  mov     rbx, [rsp+40h+arg_0]
0x1800234a3  add     rsp, 40h
0x1800234a7  pop     r14
0x1800234a9  pop     rsi
0x1800234aa  pop     rbp
0x1800234ab  retn
```
