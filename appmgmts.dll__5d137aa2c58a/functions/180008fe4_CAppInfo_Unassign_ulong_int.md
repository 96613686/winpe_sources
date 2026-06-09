# CAppInfo::Unassign(ulong,int)

- ea: `0x180008fe4`
- end: `0x1800093a6`
- name: `?Unassign@CAppInfo@@QEAAKKH@Z`
- size: `962`
- prototype: `__int64 __fastcall(CAppInfo *this, int, int)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000239c`
- `0x1800049d0`
- `0x180007410`
- `0x1800079b0`

## callees

- `0x1800016d0`
- `0x180005a48`
- `0x180008fe4`
- `0x18000d524`
- `0x180012fbc`
- `0x18001b1a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009304`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000931c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009304`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000931c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009209`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009209`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800092b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800092b2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000924f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000927f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800092a6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000924f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000927f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800092a6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000916f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000916f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000913a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000913a`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800092f1`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800092f1`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180009144`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180009144`
- `ADVAPI32!RegDeleteKeyW` at `0x1800092ce`
- `ADVAPI32!RegDeleteKeyW` at `0x1800092ce`

## string_xrefs

- `0x18000923d`: `RemovedAppState`

## pseudocode

```c
__int64 __fastcall CAppInfo::Unassign(CAppInfo *this, int a2, int a3)
{
  __int64 v3; // rax
  unsigned int v7; // edi
  int v8; // edi
  unsigned int v9; // eax
  __int64 v10; // rax
  int v11; // eax
  int v12; // eax
  int v13; // r14d
  __int64 v14; // rcx
  DWORD LastError; // eax
  DWORD v16; // eax
  BYTE v18[8]; // [rsp+30h] [rbp-49h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-41h] BYREF
  BYTE Data[16]; // [rsp+40h] [rbp-39h] BYREF
  WCHAR SubKey[40]; // [rsp+50h] [rbp-29h] BYREF

  v3 = *((_QWORD *)this + 2);
  hKey = 0;
  *(_DWORD *)v18 = 0;
  if ( !*(_DWORD *)(v3 + 304) && !*(_DWORD *)(v3 + 336)
    || *((_DWORD *)this + 57) != 4 && (*(_WORD *)&gDebugLevel & 0x100) == 0 )
  {
    GuidToString((struct _GUID *)((char *)this + 24), SubKey);
    if ( a3 && *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xBE7u, *((_QWORD *)this + 5));
    v7 = 0;
    if ( a2 )
    {
      v8 = a2 | 8;
      if ( *(_DWORD *)(*((_QWORD *)this + 2) + 296LL) )
        v8 = a2;
      if ( *(_DWORD *)&gDebugLevel )
        _DebugMsg(4, 0xBE5u, *((_QWORD *)this + 5), *((_QWORD *)this + 11));
      v9 = CallMsiAdvertiseScript(*((const unsigned __int16 **)this + 11), v8, 0, 1);
      v7 = 0;
      if ( v9 != 1605 )
        v7 = v9;
      if ( v7 )
      {
        if ( *(_DWORD *)&gDebugLevel )
          _DebugMsg(2, 0xBE6u, *((_QWORD *)this + 5), *((_QWORD *)this + 11), v7);
        if ( !a3 )
          return v7;
        goto LABEL_55;
      }
      v7 = 0;
    }
    if ( !a3 )
      return v7;
    v10 = *((_QWORD *)this + 2);
    if ( *(_DWORD *)(v10 + 396) != 1 && *(_DWORD *)(v10 + 296) )
      RevertToSelf();
    DeleteFileW(*((LPCWSTR *)this + 11));
    v11 = *((_DWORD *)this + 96);
    *((_DWORD *)this + 56) &= ~0x400u;
    if ( (unsigned int)(v11 - 6) > 1 )
      RegDeleteValueW(*(HKEY *)(*((_QWORD *)this + 2) + 288LL), *((LPCWSTR *)this + 10));
    if ( (int)--*((_DWORD *)this + 47) <= 0 )
      goto LABEL_47;
    v12 = *((_DWORD *)this + 57);
    v13 = 1;
    if ( v12 == 5 )
    {
      if ( *(_DWORD *)&gDebugLevel )
        _DebugMsg(4, 0xBE0u, *((_QWORD *)this + 5));
      *(_DWORD *)v18 = 32;
    }
    else if ( (v12 & 0xFFFFFFFB) != 0 )
    {
      v13 = 0;
    }
    else
    {
      if ( *(_DWORD *)&gDebugLevel )
        _DebugMsg(4, 0xBE4u, *((_QWORD *)this + 5));
      *(_DWORD *)v18 = 64;
    }
    v7 = RegOpenKeyExW(*(HKEY *)(*((_QWORD *)this + 2) + 288LL), SubKey, 0, 0xF003Fu, &hKey);
    if ( v7 )
    {
LABEL_46:
      v7 = 0;
LABEL_47:
      RegDeleteKeyW(*(HKEY *)(*((_QWORD *)this + 2) + 288LL), SubKey);
      goto LABEL_48;
    }
    *(_DWORD *)Data = *((unsigned __int8 *)this + 224);
    if ( *(_DWORD *)(*((_QWORD *)this + 2) + 328LL) )
      v7 = RegSetValueExW(hKey, L"RemovedAppState", 0, 4u, Data, 4u);
    if ( v13 )
    {
      if ( v7 )
        goto LABEL_45;
      v7 = RegSetValueExW(hKey, L"AppState", 0, 4u, v18, 4u);
    }
    if ( !v7 )
      v7 = RegSetValueExW(hKey, L"AssignCount", 0, 4u, (const BYTE *)this + 188, 4u);
LABEL_45:
    RegCloseKey(hKey);
    if ( !v7 )
    {
LABEL_48:
      v14 = *((_QWORD *)this + 2);
      if ( *(_DWORD *)(v14 + 396) != 1 && *(_DWORD *)(v14 + 296) && !ImpersonateLoggedOnUser(*(HANDLE *)(v14 + 264)) )
      {
        if ( *(_DWORD *)&gDebugLevel )
        {
          LastError = GetLastError();
          _DebugMsg(2, 0xBC4u, LastError);
        }
        v16 = GetLastError();
        if ( v16 )
          v7 = v16;
      }
LABEL_55:
      CEvents::Unassign((CEvents *)(*((_QWORD *)this + 2) + 344LL), v7, this);
      return v7;
    }
    goto LABEL_46;
  }
  if ( *(_DWORD *)&gDebugLevel )
    _DebugMsg(4, 0xCAAu);
  *((_DWORD *)this + 58) = 1274;
  if ( a3 )
    CEvents::Unassign((CEvents *)(*((_QWORD *)this + 2) + 344LL), 0x4FAu, this);
  return *((unsigned int *)this + 58);
}

```

## disassembly

```asm
0x180008fe4  mov     [rsp-8+arg_10], rbx
0x180008fe9  mov     [rsp-8+arg_18], rsi
0x180008fee  push    rbp
0x180008fef  push    rdi
0x180008ff0  push    r12
0x180008ff2  push    r14
0x180008ff4  push    r15
0x180008ff6  lea     rbp, [rsp-37h]
0x180008ffb  sub     rsp, 0B0h
0x180009002  mov     rax, cs:__security_cookie
0x180009009  xor     rax, rsp
0x18000900c  mov     [rbp+57h+var_30], rax
0x180009010  mov     rax, [rcx+10h]
0x180009014  xor     r15d, r15d
0x180009017  mov     [rbp+57h+hKey], r15
0x18000901b  mov     esi, r8d
0x18000901e  mov     dword ptr [rbp+57h+var_A0], r15d
0x180009022  mov     r14d, edx
0x180009025  mov     rbx, rcx
0x180009028  lea     r12d, [r15+4]
0x18000902c  cmp     [rax+130h], r15d
0x180009033  jnz     short loc_18000903E
0x180009035  cmp     [rax+150h], r15d
0x18000903c  jz      short loc_18000905B
0x18000903e  mov     eax, cs:?gDebugLevel@@3KA; ulong gDebugLevel
0x180009044  cmp     [rcx+0E4h], r12d
0x18000904b  jz      loc_180009345
0x180009051  bt      eax, 8
0x180009055  jb      loc_180009345
0x18000905b  add     rcx, 18h; struct _GUID *
0x18000905f  lea     rdx, [rbp+57h+SubKey]; unsigned __int16 *
0x180009063  call    ?GuidToString@@YAXAEAU_GUID@@PEAG@Z; GuidToString(_GUID &,ushort *)
0x180009068  test    esi, esi
0x18000906a  jz      short loc_180009086
0x18000906c  cmp     cs:?gDebugLevel@@3KA, r15d; ulong gDebugLevel
0x180009073  jz      short loc_180009086
0x180009075  mov     r8, [rbx+28h]
0x180009079  mov     edx, 0BE7h; unsigned int
0x18000907e  mov     ecx, r12d; unsigned int
0x180009081  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180009086  mov     edi, r15d
0x180009089  test    r14d, r14d
0x18000908c  jz      loc_18000911C
0x180009092  mov     rax, [rbx+10h]
0x180009096  mov     edi, r14d
0x180009099  or      edi, 8
0x18000909c  cmp     [rax+128h], r15d
0x1800090a3  cmovnz  edi, r14d
0x1800090a7  cmp     cs:?gDebugLevel@@3KA, r15d; ulong gDebugLevel
0x1800090ae  jz      short loc_1800090C5
0x1800090b0  mov     r9, [rbx+58h]
0x1800090b4  mov     edx, 0BE5h; unsigned int
0x1800090b9  mov     r8, [rbx+28h]
0x1800090bd  mov     ecx, r12d; unsigned int
0x1800090c0  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x1800090c5  mov     rcx, [rbx+58h]; unsigned __int16 *
0x1800090c9  mov     r9d, 1; int
0x1800090cf  xor     r8d, r8d; HKEY *
0x1800090d2  mov     edx, edi; unsigned int
0x1800090d4  call    ?CallMsiAdvertiseScript@@YAKPEBGKPEAPEAUHKEY__@@H@Z; CallMsiAdvertiseScript(ushort const *,ulong,HKEY__ * *,int)
0x1800090d9  cmp     eax, 645h
0x1800090de  mov     edi, r15d
0x1800090e1  cmovnz  edi, eax
0x1800090e4  test    edi, edi
0x1800090e6  jz      short loc_180009119
0x1800090e8  cmp     cs:?gDebugLevel@@3KA, r15d; ulong gDebugLevel
0x1800090ef  jz      short loc_18000910C
0x1800090f1  mov     r9, [rbx+58h]
0x1800090f5  mov     edx, 0BE6h; unsigned int
0x1800090fa  mov     r8, [rbx+28h]
0x1800090fe  mov     ecx, 2; unsigned int
0x180009103  mov     dword ptr [rsp+0D0h+phkResult], edi
0x180009107  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000910c  test    esi, esi
0x18000910e  jz      loc_180009341
0x180009114  jmp     loc_18000932C
0x180009119  mov     edi, r15d
0x18000911c  test    esi, esi
0x18000911e  jz      loc_180009341
0x180009124  mov     rax, [rbx+10h]
0x180009128  cmp     dword ptr [rax+18Ch], 1
0x18000912f  jz      short loc_180009140
0x180009131  cmp     [rax+128h], r15d
0x180009138  jz      short loc_180009140
0x18000913a  call    cs:__imp_RevertToSelf
0x180009140  mov     rcx, [rbx+58h]; lpFileName
0x180009144  call    cs:__imp_DeleteFileW
0x18000914a  mov     eax, [rbx+180h]
0x180009150  btr     dword ptr [rbx+0E0h], 0Ah
0x180009158  sub     eax, 6
0x18000915b  cmp     eax, 1
0x18000915e  jbe     short loc_180009175
0x180009160  mov     rcx, [rbx+10h]
0x180009164  mov     rdx, [rbx+50h]; lpValueName
0x180009168  mov     rcx, [rcx+120h]; hKey
0x18000916f  call    cs:__imp_RegDeleteValueW
0x180009175  lea     rsi, [rbx+0BCh]
0x18000917c  dec     dword ptr [rsi]
0x18000917e  cmp     [rsi], r15d
0x180009181  jle     loc_1800092BF
0x180009187  mov     eax, [rbx+0E4h]
0x18000918d  mov     r14d, 1
0x180009193  cmp     eax, 5
0x180009196  jnz     short loc_1800091BB
0x180009198  cmp     cs:?gDebugLevel@@3KA, r15d; ulong gDebugLevel
0x18000919f  jz      short loc_1800091B2
0x1800091a1  mov     r8, [rbx+28h]
0x1800091a5  mov     edx, 0BE0h; unsigned int
0x1800091aa  mov     ecx, r12d; unsigned int
0x1800091ad  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x1800091b2  mov     dword ptr [rbp+57h+var_A0], 20h ; ' '
0x1800091b9  jmp     short loc_1800091E8
0x1800091bb  test    eax, 0FFFFFFFBh
0x1800091c0  jz      short loc_1800091C7
0x1800091c2  mov     r14d, r15d
0x1800091c5  jmp     short loc_1800091E8
0x1800091c7  cmp     cs:?gDebugLevel@@3KA, r15d; ulong gDebugLevel
0x1800091ce  jz      short loc_1800091E1
0x1800091d0  mov     r8, [rbx+28h]
0x1800091d4  mov     edx, 0BE4h; unsigned int
0x1800091d9  mov     ecx, r12d; unsigned int
0x1800091dc  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x1800091e1  mov     dword ptr [rbp+57h+var_A0], 40h ; '@'
0x1800091e8  mov     rcx, [rbx+10h]
0x1800091ec  lea     rax, [rbp+57h+hKey]
0x1800091f0  mov     r9d, 0F003Fh; samDesired
0x1800091f6  mov     [rsp+0D0h+phkResult], rax; phkResult
0x1800091fb  xor     r8d, r8d; ulOptions
0x1800091fe  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x180009202  mov     rcx, [rcx+120h]; hKey
0x180009209  call    cs:__imp_RegOpenKeyExW
0x18000920f  mov     edi, eax
0x180009211  test    eax, eax
0x180009213  jnz     loc_1800092BC
0x180009219  movzx   ecx, byte ptr [rbx+0E0h]
0x180009220  mov     dword ptr [rbp+57h+Data], ecx
0x180009223  mov     rcx, [rbx+10h]
0x180009227  cmp     [rcx+148h], r15d
0x18000922e  jz      short loc_180009257
0x180009230  mov     rcx, [rbp+57h+hKey]; hKey
0x180009234  lea     rax, [rbp+57h+Data]
0x180009238  mov     [rsp+0D0h+cbData], r12d; cbData
0x18000923d  lea     rdx, aRemovedappstat; "RemovedAppState"
0x180009244  mov     r9d, r12d; dwType
0x180009247  mov     [rsp+0D0h+phkResult], rax; lpData
0x18000924c  xor     r8d, r8d; Reserved
0x18000924f  call    cs:__imp_RegSetValueExW
0x180009255  mov     edi, eax
0x180009257  test    r14d, r14d
0x18000925a  jz      short loc_180009287
0x18000925c  test    edi, edi
0x18000925e  jnz     short loc_1800092AE
0x180009260  mov     rcx, [rbp+57h+hKey]; hKey
0x180009264  lea     rax, [rbp+57h+var_A0]
0x180009268  mov     [rsp+0D0h+cbData], r12d; cbData
0x18000926d  lea     rdx, aAppstate; "AppState"
0x180009274  mov     r9d, r12d; dwType
0x180009277  mov     [rsp+0D0h+phkResult], rax; lpData
0x18000927c  xor     r8d, r8d; Reserved
0x18000927f  call    cs:__imp_RegSetValueExW
0x180009285  mov     edi, eax
0x180009287  test    edi, edi
0x180009289  jnz     short loc_1800092AE
0x18000928b  mov     rcx, [rbp+57h+hKey]; hKey
0x18000928f  lea     rdx, aAssigncount; "AssignCount"
0x180009296  mov     [rsp+0D0h+cbData], r12d; cbData
0x18000929b  mov     r9d, r12d; dwType
0x18000929e  xor     r8d, r8d; Reserved
0x1800092a1  mov     [rsp+0D0h+phkResult], rsi; lpData
0x1800092a6  call    cs:__imp_RegSetValueExW
0x1800092ac  mov     edi, eax
0x1800092ae  mov     rcx, [rbp+57h+hKey]; hKey
0x1800092b2  call    cs:__imp_RegCloseKey
0x1800092b8  test    edi, edi
0x1800092ba  jz      short loc_1800092D4
0x1800092bc  mov     edi, r15d
0x1800092bf  mov     rcx, [rbx+10h]
0x1800092c3  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x1800092c7  mov     rcx, [rcx+120h]; hKey
0x1800092ce  call    cs:__imp_RegDeleteKeyW
0x1800092d4  mov     rcx, [rbx+10h]
0x1800092d8  cmp     dword ptr [rcx+18Ch], 1
0x1800092df  jz      short loc_18000932C
0x1800092e1  cmp     [rcx+128h], r15d
0x1800092e8  jz      short loc_18000932C
0x1800092ea  mov     rcx, [rcx+108h]; hToken
0x1800092f1  call    cs:__imp_ImpersonateLoggedOnUser
0x1800092f7  test    eax, eax
0x1800092f9  jnz     short loc_18000932C
0x1800092fb  cmp     cs:?gDebugLevel@@3KA, r15d; ulong gDebugLevel
0x180009302  jz      short loc_18000931C
0x180009304  call    cs:__imp_GetLastError
0x18000930a  mov     edx, 0BC4h; unsigned int
0x18000930f  mov     ecx, 2; unsigned int
0x180009314  mov     r8d, eax
0x180009317  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000931c  call    cs:__imp_GetLastError
0x180009322  test    eax, eax
0x180009324  jz      short loc_18000932C
0x180009326  test    edi, edi
0x180009328  jnz     short loc_18000932C
0x18000932a  mov     edi, eax
0x18000932c  mov     rcx, [rbx+10h]
0x180009330  mov     r8, rbx; struct CAppInfo *
0x180009333  add     rcx, 158h; this
0x18000933a  mov     edx, edi; unsigned int
0x18000933c  call    ?Unassign@CEvents@@QEAAXKPEAVCAppInfo@@@Z; CEvents::Unassign(ulong,CAppInfo *)
0x180009341  mov     eax, edi
0x180009343  jmp     short loc_18000937E
0x180009345  test    eax, eax
0x180009347  jz      short loc_180009356
0x180009349  mov     edx, 0CAAh; unsigned int
0x18000934e  mov     ecx, r12d; unsigned int
0x180009351  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180009356  mov     edx, 4FAh; unsigned int
0x18000935b  mov     [rbx+0E8h], edx
0x180009361  test    esi, esi
0x180009363  jz      short loc_180009378
0x180009365  mov     rcx, [rbx+10h]
0x180009369  mov     r8, rbx; struct CAppInfo *
0x18000936c  add     rcx, 158h; this
0x180009373  call    ?Unassign@CEvents@@QEAAXKPEAVCAppInfo@@@Z; CEvents::Unassign(ulong,CAppInfo *)
0x180009378  mov     eax, [rbx+0E8h]
0x18000937e  mov     rcx, [rbp+57h+var_30]
0x180009382  xor     rcx, rsp; StackCookie
0x180009385  call    __security_check_cookie
0x18000938a  lea     r11, [rsp+0D0h+var_20]
0x180009392  mov     rbx, [r11+40h]
0x180009396  mov     rsi, [r11+48h]
0x18000939a  mov     rsp, r11
0x18000939d  pop     r15
0x18000939f  pop     r14
0x1800093a1  pop     r12
0x1800093a3  pop     rdi
0x1800093a4  pop     rbp
0x1800093a5  retn
```
