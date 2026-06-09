# StartList::CreateBreakawayATProcess(Accommodation *,int)

- ea: `0x14000d778`
- end: `0x14000dc63`
- name: `?CreateBreakawayATProcess@StartList@@AEAAJPEAVAccommodation@@H@Z`
- size: `1259`
- prototype: `__int64 __fastcall(StartList *__hidden this, struct Accommodation *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140010244`

## callees

- `0x140009aa8`
- `0x14000a7e4`
- `0x14000d778`
- `0x140011518`
- `0x140015ac2`
- `0x140015ace`
- `0x140015b00`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000dc05`
- `KERNEL32!HeapFree` at `0x14000dc05`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x14000d912`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x14000d912`
- `KERNEL32!GetLastError` at `0x14000d91c`
- `KERNEL32!GetLastError` at `0x14000d91c`
- `KERNEL32!CloseHandle` at `0x14000d8cb`
- `KERNEL32!CloseHandle` at `0x14000db7f`
- `KERNEL32!CloseHandle` at `0x14000db89`
- `KERNEL32!CloseHandle` at `0x14000d8cb`
- `KERNEL32!CloseHandle` at `0x14000db7f`
- `KERNEL32!CloseHandle` at `0x14000db89`
- `KERNEL32!HeapAlloc` at `0x14000dad3`
- `KERNEL32!HeapAlloc` at `0x14000dad3`
- `KERNEL32!GetProcessHeap` at `0x14000dac5`
- `KERNEL32!GetProcessHeap` at `0x14000dbf7`
- `KERNEL32!GetProcessHeap` at `0x14000dac5`
- `KERNEL32!GetProcessHeap` at `0x14000dbf7`
- `KERNEL32!DeleteProcThreadAttributeList` at `0x14000dbec`
- `KERNEL32!DeleteProcThreadAttributeList` at `0x14000dbec`
- `KERNEL32!CreateProcessW` at `0x14000db6d`
- `KERNEL32!CreateProcessW` at `0x14000db6d`
- `KERNEL32!UpdateProcThreadAttribute` at `0x14000db23`
- `KERNEL32!UpdateProcThreadAttribute` at `0x14000db23`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x14000daba`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x14000daf0`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x14000daba`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x14000daf0`
- `KERNEL32!OpenProcess` at `0x14000da98`
- `KERNEL32!OpenProcess` at `0x14000da98`
- `USER32!SystemParametersInfoW` at `0x14000d833`
- `USER32!SystemParametersInfoW` at `0x14000d833`
- `USER32!GetShellWindow` at `0x14000da62`
- `USER32!GetShellWindow` at `0x14000da62`
- `USER32!GetWindowThreadProcessId` at `0x14000da7e`
- `USER32!GetWindowThreadProcessId` at `0x14000da7e`
- `msvcrt!malloc` at `0x14000d8ee`
- `msvcrt!malloc` at `0x14000d990`
- `msvcrt!malloc` at `0x14000d8ee`
- `msvcrt!malloc` at `0x14000d990`
- `msvcrt!free` at `0x14000dbd2`
- `msvcrt!free` at `0x14000dc0f`
- `msvcrt!free` at `0x14000dc19`
- `msvcrt!free` at `0x14000dc26`
- `msvcrt!free` at `0x14000dc34`
- `msvcrt!free` at `0x14000dbd2`
- `msvcrt!free` at `0x14000dc0f`
- `msvcrt!free` at `0x14000dc19`
- `msvcrt!free` at `0x14000dc26`
- `msvcrt!free` at `0x14000dc34`
- `msvcrt!_wtoi` at `0x14000d7c8`
- `msvcrt!_wtoi` at `0x14000d7c8`

## string_xrefs

- `0x14000d9d6`: `/launchnarratorupdates`
- `0x14000d854`: `%SystemRoot%\System32\ATBroker.exe`
- `0x14000d90b`: `%SystemRoot%\System32\ATBroker.exe`

## pseudocode

```c
__int64 __fastcall StartList::CreateBreakawayATProcess(StartList *this, struct Accommodation *a2, int a3)
{
  int v5; // r8d
  int v6; // ebx
  unsigned int v7; // eax
  __int64 v8; // rcx
  unsigned __int16 *v9; // rax
  __int64 v10; // r9
  int v11; // r8d
  int v12; // edx
  __int64 v13; // rcx
  WCHAR *v14; // rax
  unsigned __int64 v15; // rdx
  unsigned __int64 v16; // rbx
  WCHAR *v17; // rdi
  size_t v18; // rcx
  const unsigned __int16 *v19; // rcx
  WCHAR *v21; // rax
  DWORD v22; // eax
  signed int LastError; // eax
  unsigned int v24; // ebx
  unsigned __int64 v25; // rax
  unsigned __int64 v26; // rsi
  void *v27; // rbx
  size_t v28; // rcx
  char IsEnabled; // al
  char v30; // dl
  const BYTE *v31; // rcx
  const BYTE *v32; // rax
  const BYTE *v33; // rdx
  int v34; // eax
  int v35; // r15d
  struct _PROC_THREAD_ATTRIBUTE_LIST *v36; // r14
  HWND ShellWindow; // rax
  SIZE_T v38; // rsi
  HANDLE ProcessHeap; // rax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v40; // rax
  BOOL updated; // eax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v42; // rcx
  unsigned int v43; // esi
  const BYTE *v44; // rdx
  HANDLE v45; // rax
  HANDLE hObject; // [rsp+50h] [rbp-B0h] BYREF
  ULONG_PTR Size; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE Value; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR *v49; // [rsp+68h] [rbp-98h]
  void *v50; // [rsp+70h] [rbp-90h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+78h] [rbp-88h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+90h] [rbp-70h] BYREF
  struct _PROC_THREAD_ATTRIBUTE_LIST *v53; // [rsp+F8h] [rbp-8h]
  _OWORD pvParam[4]; // [rsp+100h] [rbp+0h] BYREF

  if ( wcscmp_0(*((const wchar_t **)a2 + 5), L"SystemSetting") )
  {
    v19 = (const unsigned __int16 *)*((_QWORD *)a2 + 7);
    if ( !*((_DWORD *)v19 - 4) )
      goto LABEL_11;
    hObject = 0;
    if ( !Accommodation::FindProcess(v19, &hObject, v5) )
      goto LABEL_11;
    CloseHandle(hObject);
    return 0;
  }
  v6 = 0;
  v7 = _wtoi(*((const wchar_t **)a2 + 3));
  if ( v7 < 0x16 )
  {
    v8 = 32LL * v7;
    v9 = *(unsigned __int16 **)((char *)&SystemSettings::_systemSetting + v8);
    v10 = *(_QWORD *)a2 - (_QWORD)v9;
    do
    {
      v11 = *(unsigned __int16 *)((char *)v9 + v10);
      v12 = *v9 - v11;
      if ( v12 )
        break;
      ++v9;
    }
    while ( v11 );
    if ( !v12 && *(_DWORD *)((char *)&SystemSettings::_systemSetting + v8 + 16) == 2 )
    {
      memset(pvParam, 0, 60);
      LODWORD(pvParam[0]) = *(_DWORD *)((char *)&SystemSettings::_systemSetting + v8 + 20);
      if ( SystemParametersInfoW(*(_DWORD *)((char *)&SystemSettings::_systemSetting + v8 + 8), pvParam[0], pvParam, 0) )
        v6 = BYTE4(pvParam[0]) & 1;
    }
  }
  if ( v6 )
    return 0;
LABEL_11:
  v13 = 0x7FFFFFFF;
  v14 = StartList::_atBrokerExe;
  do
  {
    if ( !*v14 )
      break;
    ++v14;
    --v13;
  }
  while ( v13 );
  v15 = (0x7FFFFFFF - v13) & ((unsigned __int128)-(__int128)(unsigned __int64)v13 >> 64);
  if ( !v13 )
    return 2147500037LL;
  v16 = v15 + 260;
  if ( v15 + 260 < v15 )
    return 2147500037LL;
  v17 = 0;
  v49 = 0;
  if ( v15 == -260 )
  {
    v18 = 0;
  }
  else
  {
    if ( 0xFFFFFFFFFFFFFFFFuLL / v16 < 2 )
    {
LABEL_71:
      v24 = -2147024882;
      goto LABEL_72;
    }
    v18 = 2 * v16;
  }
  v21 = (WCHAR *)malloc(v18);
  v17 = v21;
  v49 = v21;
  if ( !v21 )
    goto LABEL_71;
  v22 = ExpandEnvironmentStringsW(StartList::_atBrokerExe, v21, v16);
  if ( !v22 )
  {
    LastError = GetLastError();
    v24 = LastError;
    if ( LastError > 0 )
      v24 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_72;
  }
  if ( v22 > v16 )
  {
    v24 = -2147024774;
LABEL_72:
    free(v17);
    return v24;
  }
  v25 = v16 + 22;
  if ( v16 + 22 < v16 || (v26 = v16 + 282, v16 + 282 < v16 + 22) )
  {
LABEL_63:
    v24 = -2147467259;
    goto LABEL_72;
  }
  v27 = 0;
  v50 = 0;
  if ( v25 == -260 )
  {
    v28 = 0;
  }
  else
  {
    if ( 0xFFFFFFFFFFFFFFFFuLL / v26 < 2 )
    {
LABEL_70:
      free(v27);
      goto LABEL_71;
    }
    v28 = 2 * v26;
  }
  v27 = malloc(v28);
  v50 = v27;
  if ( !v27 )
    goto LABEL_70;
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Narrator_AddUpdates>::GetImpl'::`2'::impl);
  v30 = *((_BYTE *)a2 + 85);
  v31 = (const BYTE *)L"/launchnarratorhome";
  if ( IsEnabled )
  {
    if ( !v30 )
      v31 = &Data;
    v32 = (const BYTE *)L"/launchnarratorupdates";
    if ( !*((_BYTE *)a2 + 86) )
      v32 = &Data;
    v33 = (const BYTE *)L"/hardwarebuttonlaunch";
    if ( !*((_BYTE *)a2 + 84) )
      v33 = &Data;
    v34 = StringCchPrintfW((unsigned __int16 *)v27, v26, L"%s /start %s %s %s %s", v17, *(_QWORD *)a2, v33, v32, v31);
  }
  else
  {
    if ( !v30 )
      v31 = &Data;
    v44 = (const BYTE *)L"/hardwarebuttonlaunch";
    if ( !*((_BYTE *)a2 + 84) )
      v44 = &Data;
    v34 = StringCchPrintfW((unsigned __int16 *)v27, v26, L"%s /start %s %s %s", v17, *(_QWORD *)a2, v44, v31);
  }
  if ( v34 < 0 )
  {
    free(v27);
    goto LABEL_63;
  }
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&StartupInfo.cb + 1, 0, 0x6Cu);
  StartupInfo.cb = 112;
  Value = 0;
  v35 = 0;
  v36 = 0;
  Size = 0;
  if ( a3 )
  {
    ShellWindow = GetShellWindow();
    if ( ShellWindow )
    {
      LODWORD(hObject) = 0;
      if ( GetWindowThreadProcessId(ShellWindow, (LPDWORD)&hObject) )
      {
        Value = OpenProcess(0x80u, 0, (DWORD)hObject);
        if ( Value )
        {
          InitializeProcThreadAttributeList(0, 1u, 0, &Size);
          v38 = Size;
          ProcessHeap = GetProcessHeap();
          v40 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)HeapAlloc(ProcessHeap, 0, v38);
          v36 = v40;
          if ( v40 )
          {
            if ( InitializeProcThreadAttributeList(v40, 1u, 0, &Size) )
            {
              v35 = 1;
              updated = UpdateProcThreadAttribute(v36, 0, 0x20000u, &Value, 8u, 0, 0);
              v42 = v53;
              if ( updated )
                v42 = v36;
              v53 = v42;
            }
          }
        }
      }
    }
  }
  if ( CreateProcessW(v17, (LPWSTR)v27, 0, 0, 0, 0x1080000u, 0, 0, &StartupInfo, &ProcessInformation) )
  {
    v43 = 0;
    CloseHandle(ProcessInformation.hProcess);
    CloseHandle(ProcessInformation.hThread);
  }
  else
  {
    v43 = -2147467259;
  }
  if ( v35 )
    DeleteProcThreadAttributeList(v36);
  if ( v36 )
  {
    v45 = GetProcessHeap();
    HeapFree(v45, 0, v36);
  }
  free(v27);
  free(v17);
  return v43;
}

```

## disassembly

```asm
0x14000d778  push    rbp
0x14000d77a  push    rbx
0x14000d77b  push    rsi
0x14000d77c  push    rdi
0x14000d77d  push    r12
0x14000d77f  push    r13
0x14000d781  push    r14
0x14000d783  push    r15
0x14000d785  lea     rbp, [rsp-58h]
0x14000d78a  sub     rsp, 158h
0x14000d791  mov     rax, cs:__security_cookie
0x14000d798  xor     rax, rsp
0x14000d79b  mov     [rbp+90h+var_50], rax
0x14000d79f  mov     r12d, r8d
0x14000d7a2  mov     r14, rdx
0x14000d7a5  lea     rdx, aSystemsetting; "SystemSetting"
0x14000d7ac  mov     rcx, [r14+28h]; String1
0x14000d7b0  call    wcscmp_0
0x14000d7b5  nop
0x14000d7b6  xor     r13d, r13d
0x14000d7b9  test    eax, eax
0x14000d7bb  jnz     loc_14000D8A9
0x14000d7c1  mov     ebx, r13d
0x14000d7c4  mov     rcx, [r14+18h]; String
0x14000d7c8  call    cs:__imp__wtoi
0x14000d7ce  cmp     eax, 16h
0x14000d7d1  jnb     short loc_14000D843
0x14000d7d3  mov     ecx, eax
0x14000d7d5  shl     rcx, 5
0x14000d7d9  lea     r10, ?_systemSetting@SystemSettings@@0PAUSystemSetting@@A; SystemSetting near * SystemSettings::_systemSetting
0x14000d7e0  mov     rax, [rcx+r10]
0x14000d7e4  mov     r9, [r14]
0x14000d7e7  sub     r9, rax
0x14000d7ea  movzx   edx, word ptr [rax]
0x14000d7ed  movzx   r8d, word ptr [rax+r9]
0x14000d7f2  sub     edx, r8d
0x14000d7f5  jnz     short loc_14000D800
0x14000d7f7  add     rax, 2
0x14000d7fb  test    r8d, r8d
0x14000d7fe  jnz     short loc_14000D7EA
0x14000d800  test    edx, edx
0x14000d802  jnz     short loc_14000D843
0x14000d804  cmp     dword ptr [rcx+r10+10h], 2
0x14000d80a  jnz     short loc_14000D843
0x14000d80c  xorps   xmm0, xmm0
0x14000d80f  movups  [rbp+90h+pvParam], xmm0
0x14000d813  movups  [rbp+90h+var_80], xmm0
0x14000d817  movups  xmmword ptr [rbp+90h+var_70], xmm0
0x14000d81b  movups  xmmword ptr [rbp+90h+var_70+0Ch], xmm0
0x14000d81f  mov     edx, [rcx+r10+14h]; uiParam
0x14000d824  mov     dword ptr [rbp+90h+pvParam], edx
0x14000d827  xor     r9d, r9d; fWinIni
0x14000d82a  lea     r8, [rbp+90h+pvParam]; pvParam
0x14000d82e  mov     ecx, [rcx+r10+8]; uiAction
0x14000d833  call    cs:__imp_SystemParametersInfoW
0x14000d839  test    eax, eax
0x14000d83b  jz      short loc_14000D843
0x14000d83d  mov     ebx, dword ptr [rbp+90h+pvParam+4]
0x14000d840  and     ebx, 1
0x14000d843  test    ebx, ebx
0x14000d845  jnz     loc_14000D8D1
0x14000d84b  mov     r8d, 7FFFFFFFh
0x14000d851  mov     ecx, r8d
0x14000d854  lea     rax, ?_atBrokerExe@StartList@@0PAGA; "%SystemRoot%\\System32\\ATBroker.exe"
0x14000d85b  cmp     [rax], r13w
0x14000d85f  jz      short loc_14000D86B
0x14000d861  add     rax, 2
0x14000d865  sub     rcx, 1
0x14000d869  jnz     short loc_14000D85B
0x14000d86b  mov     rax, rcx
0x14000d86e  sub     r8, rcx
0x14000d871  neg     rax
0x14000d874  sbb     rdx, rdx
0x14000d877  and     rdx, r8
0x14000d87a  test    rcx, rcx
0x14000d87d  jz      loc_14000DC3E
0x14000d883  lea     rbx, [rdx+104h]
0x14000d88a  cmp     rbx, rdx
0x14000d88d  jb      loc_14000DC3E
0x14000d893  mov     rdi, r13
0x14000d896  mov     [rsp+190h+var_128], r13
0x14000d89b  or      r15, 0FFFFFFFFFFFFFFFFh
0x14000d89f  test    rbx, rbx
0x14000d8a2  jnz     short loc_14000D8D8
0x14000d8a4  mov     rcx, r13
0x14000d8a7  jmp     short loc_14000D8EE
0x14000d8a9  mov     rcx, [r14+38h]; unsigned __int16 *
0x14000d8ad  cmp     [rcx-10h], r13d
0x14000d8b1  jz      short loc_14000D84B
0x14000d8b3  mov     [rsp+190h+hObject], r13
0x14000d8b8  lea     rdx, [rsp+190h+hObject]; void **
0x14000d8bd  call    ?FindProcess@Accommodation@@SAKPEBGPEAPEAXH@Z; Accommodation::FindProcess(ushort const *,void * *,int)
0x14000d8c2  test    eax, eax
0x14000d8c4  jz      short loc_14000D84B
0x14000d8c6  mov     rcx, [rsp+190h+hObject]; hObject
0x14000d8cb  call    cs:__imp_CloseHandle
0x14000d8d1  xor     eax, eax
0x14000d8d3  jmp     loc_14000DC43
0x14000d8d8  xor     edx, edx
0x14000d8da  mov     rax, r15
0x14000d8dd  div     rbx
0x14000d8e0  cmp     rax, 2
0x14000d8e4  jb      loc_14000DC2C
0x14000d8ea  lea     rcx, [rbx+rbx]; Size
0x14000d8ee  call    cs:__imp_malloc
0x14000d8f4  mov     rdi, rax
0x14000d8f7  mov     [rsp+190h+var_128], rax
0x14000d8fc  test    rax, rax
0x14000d8ff  jz      loc_14000DC2C
0x14000d905  mov     r8d, ebx; nSize
0x14000d908  mov     rdx, rax; lpDst
0x14000d90b  lea     rcx, ?_atBrokerExe@StartList@@0PAGA; "%SystemRoot%\\System32\\ATBroker.exe"
0x14000d912  call    cs:__imp_ExpandEnvironmentStringsW
0x14000d918  test    eax, eax
0x14000d91a  jnz     short loc_14000D93A
0x14000d91c  call    cs:__imp_GetLastError
0x14000d922  mov     ebx, eax
0x14000d924  test    eax, eax
0x14000d926  jle     loc_14000DC31
0x14000d92c  movzx   ebx, ax
0x14000d92f  or      ebx, 80070000h
0x14000d935  jmp     loc_14000DC31
0x14000d93a  mov     eax, eax
0x14000d93c  cmp     rax, rbx
0x14000d93f  jbe     short loc_14000D94B
0x14000d941  mov     ebx, 8007007Ah
0x14000d946  jmp     loc_14000DC31
0x14000d94b  lea     rax, [rbx+16h]
0x14000d94f  cmp     rax, rbx
0x14000d952  jb      loc_14000DBD8
0x14000d958  lea     rsi, [rax+104h]
0x14000d95f  cmp     rsi, rax
0x14000d962  jb      loc_14000DBD8
0x14000d968  mov     rbx, r13
0x14000d96b  mov     [rsp+190h+var_120], rbx
0x14000d970  test    rsi, rsi
0x14000d973  jnz     short loc_14000D97A
0x14000d975  mov     rcx, r13
0x14000d978  jmp     short loc_14000D990
0x14000d97a  xor     edx, edx
0x14000d97c  mov     rax, r15
0x14000d97f  div     rsi
0x14000d982  cmp     rax, 2
0x14000d986  jb      loc_14000DC23
0x14000d98c  lea     rcx, [rsi+rsi]; Size
0x14000d990  call    cs:__imp_malloc
0x14000d996  mov     rbx, rax
0x14000d999  mov     [rsp+190h+var_120], rax
0x14000d99e  test    rax, rax
0x14000d9a1  jz      loc_14000DC23
0x14000d9a7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates> `wil::Feature<__WilFeatureTraits_Feature_Narrator_AddUpdates>::GetImpl(void)'::`2'::impl
0x14000d9ae  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::__private_IsEnabled(void)
0x14000d9b3  mov     dl, [r14+55h]
0x14000d9b7  lea     r8, Data
0x14000d9be  lea     rcx, aLaunchnarrator; "/launchnarratorhome"
0x14000d9c5  mov     r9, rdi
0x14000d9c8  test    al, al
0x14000d9ca  jz      loc_14000DB91
0x14000d9d0  test    dl, dl
0x14000d9d2  cmovz   rcx, r8
0x14000d9d6  lea     rax, aLaunchnarrator_0; "/launchnarratorupdates"
0x14000d9dd  cmp     [r14+56h], r13b
0x14000d9e1  cmovz   rax, r8
0x14000d9e5  lea     rdx, aHardwarebutton; "/hardwarebuttonlaunch"
0x14000d9ec  cmp     [r14+54h], r13b
0x14000d9f0  cmovz   rdx, r8
0x14000d9f4  mov     [rsp+190h+lpCurrentDirectory], rcx
0x14000d9f9  mov     [rsp+190h+lpReturnSize], rax
0x14000d9fe  mov     [rsp+190h+lpPreviousValue], rdx
0x14000da03  mov     rax, [r14]
0x14000da06  mov     [rsp+190h+cbSize], rax
0x14000da0b  lea     r8, aSStartSSSS; "%s /start %s %s %s %s"
0x14000da12  mov     rdx, rsi; unsigned __int64
0x14000da15  mov     rcx, rbx; unsigned __int16 *
0x14000da18  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000da1d  test    eax, eax
0x14000da1f  js      loc_14000DBCF
0x14000da25  xorps   xmm0, xmm0
0x14000da28  xor     eax, eax
0x14000da2a  movups  xmmword ptr [rsp+190h+ProcessInformation.hProcess], xmm0
0x14000da2f  mov     qword ptr [rbp+90h+ProcessInformation.dwProcessId], rax
0x14000da33  xor     edx, edx; Val
0x14000da35  lea     r8d, [rax+6Ch]; Size
0x14000da39  lea     rcx, [rbp+90h+StartupInfo+4]; void *
0x14000da3d  call    memset_0
0x14000da42  mov     [rbp+90h+StartupInfo.cb], 70h ; 'p'
0x14000da49  mov     [rsp+190h+Value], r13
0x14000da4e  mov     r15d, r13d
0x14000da51  mov     r14, r13
0x14000da54  mov     [rsp+190h+Size], r13
0x14000da59  test    r12d, r12d
0x14000da5c  jz      loc_14000DB37
0x14000da62  call    cs:__imp_GetShellWindow
0x14000da68  test    rax, rax
0x14000da6b  jz      loc_14000DB37
0x14000da71  mov     dword ptr [rsp+190h+hObject], r13d
0x14000da76  lea     rdx, [rsp+190h+hObject]; lpdwProcessId
0x14000da7b  mov     rcx, rax; hWnd
0x14000da7e  call    cs:__imp_GetWindowThreadProcessId
0x14000da84  test    eax, eax
0x14000da86  jz      loc_14000DB37
0x14000da8c  mov     r8d, dword ptr [rsp+190h+hObject]; dwProcessId
0x14000da91  xor     edx, edx; bInheritHandle
0x14000da93  mov     ecx, 80h; dwDesiredAccess
0x14000da98  call    cs:__imp_OpenProcess
0x14000da9e  mov     [rsp+190h+Value], rax
0x14000daa3  test    rax, rax
0x14000daa6  jz      loc_14000DB37
0x14000daac  lea     r9, [rsp+190h+Size]; lpSize
0x14000dab1  xor     r8d, r8d; dwFlags
0x14000dab4  lea     edx, [r8+1]; dwAttributeCount
0x14000dab8  xor     ecx, ecx; lpAttributeList
0x14000daba  call    cs:__imp_InitializeProcThreadAttributeList
0x14000dac0  mov     rsi, [rsp+190h+Size]
0x14000dac5  call    cs:__imp_GetProcessHeap
0x14000dacb  mov     r8, rsi; dwBytes
0x14000dace  xor     edx, edx; dwFlags
0x14000dad0  mov     rcx, rax; hHeap
0x14000dad3  call    cs:__imp_HeapAlloc
0x14000dad9  mov     r14, rax
0x14000dadc  test    rax, rax
0x14000dadf  jz      short loc_14000DB37
0x14000dae1  lea     r9, [rsp+190h+Size]; lpSize
0x14000dae6  xor     r8d, r8d; dwFlags
0x14000dae9  lea     edx, [r8+1]; dwAttributeCount
0x14000daed  mov     rcx, rax; lpAttributeList
0x14000daf0  call    cs:__imp_InitializeProcThreadAttributeList
0x14000daf6  test    eax, eax
0x14000daf8  jz      short loc_14000DB37
0x14000dafa  mov     r15d, 1
0x14000db00  mov     [rsp+190h+lpReturnSize], r13; lpReturnSize
0x14000db05  mov     [rsp+190h+lpPreviousValue], r13; lpPreviousValue
0x14000db0a  mov     [rsp+190h+cbSize], 8; cbSize
0x14000db13  lea     r9, [rsp+190h+Value]; lpValue
0x14000db18  xor     edx, edx; dwFlags
0x14000db1a  mov     r8d, 20000h; Attribute
0x14000db20  mov     rcx, r14; lpAttributeList
0x14000db23  call    cs:__imp_UpdateProcThreadAttribute
0x14000db29  mov     rcx, [rbp+90h+var_98]
0x14000db2d  test    eax, eax
0x14000db2f  cmovnz  rcx, r14
0x14000db33  mov     [rbp+90h+var_98], rcx
0x14000db37  lea     rax, [rsp+190h+ProcessInformation]
0x14000db3c  mov     [rsp+190h+lpProcessInformation], rax; lpProcessInformation
0x14000db41  lea     rax, [rbp+90h+StartupInfo]
0x14000db45  mov     [rsp+190h+lpStartupInfo], rax; lpStartupInfo
0x14000db4a  mov     [rsp+190h+lpCurrentDirectory], r13; lpCurrentDirectory
0x14000db4f  mov     [rsp+190h+lpReturnSize], r13; lpEnvironment
0x14000db54  mov     dword ptr [rsp+190h+lpPreviousValue], 1080000h; dwCreationFlags
0x14000db5c  mov     dword ptr [rsp+190h+cbSize], r13d; bInheritHandles
0x14000db61  xor     r9d, r9d; lpThreadAttributes
0x14000db64  xor     r8d, r8d; lpProcessAttributes
0x14000db67  mov     rdx, rbx; lpCommandLine
0x14000db6a  mov     rcx, rdi; lpApplicationName
0x14000db6d  call    cs:__imp_CreateProcessW
0x14000db73  test    eax, eax
0x14000db75  jz      short loc_14000DBDF
0x14000db77  mov     esi, r13d
0x14000db7a  mov     rcx, [rsp+190h+ProcessInformation.hProcess]; hObject
0x14000db7f  call    cs:__imp_CloseHandle
0x14000db85  mov     rcx, [rbp+90h+ProcessInformation.hThread]; hObject
0x14000db89  call    cs:__imp_CloseHandle
0x14000db8f  jmp     short loc_14000DBE4
0x14000db91  test    dl, dl
0x14000db93  cmovz   rcx, r8
0x14000db97  lea     rdx, aHardwarebutton; "/hardwarebuttonlaunch"
0x14000db9e  cmp     [r14+54h], r13b
0x14000dba2  cmovz   rdx, r8
0x14000dba6  mov     [rsp+190h+lpReturnSize], rcx
0x14000dbab  mov     [rsp+190h+lpPreviousValue], rdx
0x14000dbb0  mov     rax, [r14]
0x14000dbb3  mov     [rsp+190h+cbSize], rax
0x14000dbb8  lea     r8, aSStartSSS; "%s /start %s %s %s"
0x14000dbbf  mov     rdx, rsi; unsigned __int64
0x14000dbc2  mov     rcx, rbx; unsigned __int16 *
0x14000dbc5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000dbca  jmp     loc_14000DA1D
0x14000dbcf  mov     rcx, rbx; Block
0x14000dbd2  call    cs:__imp_free
0x14000dbd8  mov     ebx, 80004005h
0x14000dbdd  jmp     short loc_14000DC31
0x14000dbdf  mov     esi, 80004005h
0x14000dbe4  test    r15d, r15d
0x14000dbe7  jz      short loc_14000DBF2
0x14000dbe9  mov     rcx, r14; lpAttributeList
0x14000dbec  call    cs:__imp_DeleteProcThreadAttributeList
0x14000dbf2  test    r14, r14
0x14000dbf5  jz      short loc_14000DC0C
0x14000dbf7  call    cs:__imp_GetProcessHeap
0x14000dbfd  mov     rcx, rax; hHeap
0x14000dc00  mov     r8, r14; lpMem
0x14000dc03  xor     edx, edx; dwFlags
0x14000dc05  call    cs:__imp_HeapFree
0x14000dc0b  nop
0x14000dc0c  mov     rcx, rbx; Block
0x14000dc0f  call    cs:__imp_free
0x14000dc15  nop
0x14000dc16  mov     rcx, rdi; Block
0x14000dc19  call    cs:__imp_free
0x14000dc1f  mov     eax, esi
  ... truncated ...
```
