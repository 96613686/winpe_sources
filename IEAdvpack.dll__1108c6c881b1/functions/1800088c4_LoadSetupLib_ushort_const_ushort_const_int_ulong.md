# LoadSetupLib(ushort const *,ushort const *,int,ulong)

- ea: `0x1800088c4`
- end: `0x180008a2c`
- name: `?LoadSetupLib@@YAHPEBG0HK@Z`
- size: `360`
- prototype: `__int64 __fastcall(const unsigned __int16 *, PCWSTR Section, int, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180004754`

## callees

- `0x1800022bc`
- `0x180004700`
- `0x180006d24`
- `0x180007968`
- `0x1800088c4`
- `0x18000a428`
- `0x18000a918`
- `0x18001793c`
- `0x18001b980`

## import_xrefs

- `USER32!PeekMessageW` at `0x180008a1f`
- `USER32!PeekMessageW` at `0x180008a1f`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180008986`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180008986`

## string_xrefs

- `0x180008959`: `UpdateINFEngine`

## pseudocode

```c
__int64 __fastcall LoadSetupLib(const unsigned __int16 *a1, PCWSTR Section, int a3, unsigned int a4)
{
  const unsigned __int16 *v7; // r9
  const unsigned __int16 *v8; // rcx
  const unsigned __int16 *v9; // r9
  int v10; // edx
  const unsigned __int16 **v11; // rcx
  struct tagMSG Msg; // [rsp+30h] [rbp-268h] BYREF
  WCHAR pszPath[264]; // [rsp+60h] [rbp-238h] BYREF

  memset(&Msg, 0, sizeof(Msg));
  if ( !(unsigned int)SelectSetupEngine(a1, Section, a4)
    || a3
    && ctx < 3u
    && !(unsigned int)RunningOnMillennium()
    && !UpdateHelpDlls((const unsigned __int16 **)&c_szAdvDlls, 1, 0, v7, dword_1800257D4 != 0) )
  {
    return 0;
  }
  if ( (unsigned int)GetTranslatedInt(a1, Section, L"UpdateINFEngine", 0) )
  {
    StringCchCopyW(pszPath, 0x104u, a1);
    PathRemoveFileSpecW(pszPath);
    if ( dword_1800257F8 )
    {
      v10 = 1;
      v11 = (const unsigned __int16 **)&c_szSetupXDlls;
    }
    else
    {
      CommonInstallCleanup();
      v10 = 2;
      v11 = (const unsigned __int16 **)&c_szSetupAPIDlls;
    }
    if ( !UpdateHelpDlls(v11, v10, pszPath, v9, 3u) )
      return 0;
  }
  if ( dword_1800257F8 == 1 )
  {
    hLibModule = 0;
    return 0;
  }
  if ( !(unsigned int)InitializeSetupAPI(v8) )
    return 0;
  PeekMessageW(&Msg, 0, 0, 0, 0);
  return 1;
}

```

## disassembly

```asm
0x1800088c4  mov     [rsp+arg_10], rbx
0x1800088c9  push    rsi
0x1800088ca  push    rdi
0x1800088cb  push    r15
0x1800088cd  sub     rsp, 280h
0x1800088d4  mov     rax, cs:__security_cookie
0x1800088db  xor     rax, rsp
0x1800088de  mov     [rsp+298h+var_28], rax
0x1800088e6  xorps   xmm0, xmm0
0x1800088e9  mov     edi, r8d
0x1800088ec  mov     r8d, r9d; unsigned int
0x1800088ef  mov     rsi, rdx
0x1800088f2  movups  xmmword ptr [rsp+298h+Msg.hwnd], xmm0
0x1800088f7  mov     rbx, rcx
0x1800088fa  movups  xmmword ptr [rsp+298h+Msg.wParam], xmm0
0x1800088ff  movups  xmmword ptr [rsp+298h+Msg.time], xmm0
0x180008904  call    ?SelectSetupEngine@@YAHPEBG0K@Z; SelectSetupEngine(ushort const *,ushort const *,ulong)
0x180008909  test    eax, eax
0x18000890b  jz      loc_1800089DB
0x180008911  mov     r15d, 3
0x180008917  test    edi, edi
0x180008919  jz      short loc_180008956
0x18000891b  cmp     cs:?ctx@@3UADVCONTEXTW@@A, r15w; ADVCONTEXTW ctx
0x180008923  jnb     short loc_180008956
0x180008925  call    RunningOnMillennium
0x18000892a  test    eax, eax
0x18000892c  jnz     short loc_180008956
0x18000892e  cmp     cs:dword_1800257D4, eax
0x180008934  lea     edx, [r15-2]; int
0x180008938  lea     rcx, ?c_szAdvDlls@@3PAPEBGA; unsigned __int16 **
0x18000893f  setnz   al
0x180008942  xor     r8d, r8d; unsigned __int16 *
0x180008945  mov     [rsp+298h+wRemoveMsg], eax; unsigned int
0x180008949  call    ?UpdateHelpDlls@@YAHPEAPEBGHPEBG1K@Z; UpdateHelpDlls(ushort const * *,int,ushort const *,ushort const *,ulong)
0x18000894e  test    eax, eax
0x180008950  jz      loc_1800089DB
0x180008956  xor     r9d, r9d; nDefault
0x180008959  lea     r8, aUpdateinfengin; "UpdateINFEngine"
0x180008960  mov     rdx, rsi; Section
0x180008963  mov     rcx, rbx; unsigned __int16 *
0x180008966  call    ?GetTranslatedInt@@YAKPEBG00K@Z; GetTranslatedInt(ushort const *,ushort const *,ushort const *,ulong)
0x18000896b  test    eax, eax
0x18000896d  jz      short loc_1800089C7
0x18000896f  mov     r8, rbx; unsigned __int16 *
0x180008972  lea     rcx, [rsp+298h+pszPath]; unsigned __int16 *
0x180008977  mov     edx, 104h; unsigned __int64
0x18000897c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180008981  lea     rcx, [rsp+298h+pszPath]; pszPath
0x180008986  call    cs:__imp_PathRemoveFileSpecW
0x18000898c  cmp     cs:dword_1800257F8, 0
0x180008993  jnz     short loc_1800089A8
0x180008995  call    ?CommonInstallCleanup@@YAXXZ; CommonInstallCleanup(void)
0x18000899a  mov     edx, 2
0x18000899f  lea     rcx, ?c_szSetupAPIDlls@@3PAPEBGA; ushort const * near * c_szSetupAPIDlls
0x1800089a6  jmp     short loc_1800089B4
0x1800089a8  mov     edx, 1; int
0x1800089ad  lea     rcx, ?c_szSetupXDlls@@3PAPEBGA; unsigned __int16 **
0x1800089b4  lea     r8, [rsp+298h+pszPath]; unsigned __int16 *
0x1800089b9  mov     [rsp+298h+wRemoveMsg], r15d; unsigned int
0x1800089be  call    ?UpdateHelpDlls@@YAHPEAPEBGHPEBG1K@Z; UpdateHelpDlls(ushort const * *,int,ushort const *,ushort const *,ulong)
0x1800089c3  test    eax, eax
0x1800089c5  jz      short loc_1800089DB
0x1800089c7  cmp     cs:dword_1800257F8, 1
0x1800089ce  jnz     short loc_180008A01
0x1800089d0  mov     cs:hLibModule, 0
0x1800089db  xor     eax, eax
0x1800089dd  mov     rcx, [rsp+298h+var_28]
0x1800089e5  xor     rcx, rsp; StackCookie
0x1800089e8  call    __security_check_cookie
0x1800089ed  mov     rbx, [rsp+298h+arg_10]
0x1800089f5  add     rsp, 280h
0x1800089fc  pop     r15
0x1800089fe  pop     rdi
0x1800089ff  pop     rsi
0x180008a00  retn
0x180008a01  call    ?InitializeSetupAPI@@YAHXZ; InitializeSetupAPI(void)
0x180008a06  test    eax, eax
0x180008a08  jz      short loc_1800089DB
0x180008a0a  xor     r9d, r9d; wMsgFilterMax
0x180008a0d  mov     [rsp+298h+wRemoveMsg], 0; wRemoveMsg
0x180008a15  xor     r8d, r8d; wMsgFilterMin
0x180008a18  lea     rcx, [rsp+298h+Msg]; lpMsg
0x180008a1d  xor     edx, edx; hWnd
0x180008a1f  call    cs:__imp_PeekMessageW
0x180008a25  mov     eax, 1
0x180008a2a  jmp     short loc_1800089DD
```
