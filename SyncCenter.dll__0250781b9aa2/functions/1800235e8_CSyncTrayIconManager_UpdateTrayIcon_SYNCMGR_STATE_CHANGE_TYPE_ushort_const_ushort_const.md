# CSyncTrayIconManager::_UpdateTrayIcon(SYNCMGR_STATE_CHANGE_TYPE,ushort const *,ushort const *)

- ea: `0x1800235e8`
- end: `0x180023857`
- name: `?_UpdateTrayIcon@CSyncTrayIconManager@@AEAAXW4SYNCMGR_STATE_CHANGE_TYPE@@PEBG1@Z`
- size: `623`
- prototype: `void __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180005490`

## callees

- `0x18000f784`
- `0x18002307c`
- `0x180023548`
- `0x1800235e8`
- `0x180051240`
- `0x180051fe8`
- `0x18005292a`
- `0x180052950`
- `0x180053010`

## import_xrefs

- `SHELL32!Shell_NotifyIconW` at `0x1800237c5`
- `SHELL32!Shell_NotifyIconW` at `0x1800237e0`
- `SHELL32!Shell_NotifyIconW` at `0x1800237c5`
- `SHELL32!Shell_NotifyIconW` at `0x1800237e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002378d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002378d`
- `USER32!DestroyIcon` at `0x1800236f0`
- `USER32!DestroyIcon` at `0x18002381c`
- `USER32!DestroyIcon` at `0x1800236f0`
- `USER32!DestroyIcon` at `0x18002381c`

## pseudocode

```c
void __fastcall CSyncTrayIconManager::_UpdateTrayIcon(__int64 a1, __int64 a2, __int64 a3)
{
  int v5; // r14d
  HWND v6; // rax
  HICON v7; // rdx
  DWORD v8; // edi
  HICON v9; // rcx
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  bool v14; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  HICON v16; // [rsp+40h] [rbp-C0h] BYREF
  struct _NOTIFYICONDATAW Data; // [rsp+50h] [rbp-B0h] BYREF

  LODWORD(pv) = 0;
  v16 = 0;
  v14 = 0;
  CSyncTrayIconManager::_CalcNewTrayStatus((CSyncTrayIconManager *)a1, (int *)&pv, &v16, &v14);
  if ( *(_BYTE *)(a1 + 38) == 1 )
  {
    memset_0(&Data, 0, sizeof(Data));
    v5 = (int)pv;
    v6 = *(HWND *)(a1 + 24);
    v7 = v16;
    Data.cbSize = 976;
    v8 = 1;
    Data.hWnd = v6;
    Data.uTimeout = 4;
    Data.uID = 1;
    Data.uFlags = 1;
    Data.uCallbackMessage = 32770;
    if ( (_DWORD)pv != *(_DWORD *)(a1 + 40) || v16 != *(HICON *)(a1 + 48) || v14 || a3 )
    {
      if ( !*(_DWORD *)(a1 + 40) )
        v8 = *(_QWORD *)(a1 + 48) != 0;
      if ( v16 )
      {
        v9 = *(HICON *)(a1 + 48);
        if ( v9 )
        {
          DestroyIcon(v9);
          v7 = v16;
        }
        *(_QWORD *)(a1 + 48) = v7;
        Data.hIcon = v7;
      }
      else
      {
        LoadIconMetric(g_hmodThisDll, (PCWSTR)(unsigned __int16)pv, 0, &Data.hIcon);
      }
      v10 = *(_QWORD *)(a1 + 56);
      if ( v10 )
      {
        pv = 0;
        v11 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v10 + 48LL))(v10, &pv);
        if ( v11 == -2147023174 )
        {
          CSyncTrayIconManager::_RegisterShellTrayIcon((CSyncTrayIconManager *)a1, 0, 1);
          *(_BYTE *)(a1 + 38) = 0;
        }
        else if ( v11 >= 0 )
        {
          Data.uFlags |= 4u;
          ResourceStringCopyEx(g_hmodThisDll, v12, v13, Data.szTip);
          StringCchCatW(Data.szTip, 0x80u, L"\n");
          StringCchCatW(Data.szTip, 0x80u, (const unsigned __int16 *)pv);
          CoTaskMemFree(pv);
        }
      }
    }
    if ( *(_BYTE *)(a1 + 38) == 1 )
    {
      if ( Data.uFlags != 1 )
      {
        if ( Data.hIcon || Data.hBalloonIcon )
          Data.uFlags |= 2u;
        else
          Data.uFlags &= ~2u;
        if ( Shell_NotifyIconW(v8, &Data) || Shell_NotifyIconW(v8 == 0, &Data) )
        {
          if ( *(_BYTE *)(a1 + 38) == 1 )
            *(_DWORD *)(a1 + 40) = v5;
        }
        else
        {
          *(_DWORD *)(a1 + 40) = 0;
        }
      }
      Data.uFlags |= 0x10u;
      Data.dwInfoFlags = 4;
    }
    if ( Data.hIcon )
    {
      if ( Data.hIcon != *(HICON *)(a1 + 48) )
        DestroyIcon(Data.hIcon);
    }
  }
  else if ( v14 )
  {
    CSyncTrayIconManager::_RegisterShellTrayIcon((CSyncTrayIconManager *)a1, 0, 1);
  }
}

```

## disassembly

```asm
0x1800235e8  push    rbp
0x1800235ea  push    rbx
0x1800235eb  push    rsi
0x1800235ec  push    rdi
0x1800235ed  push    r12
0x1800235ef  push    r14
0x1800235f1  lea     rbp, [rsp-338h]
0x1800235f9  sub     rsp, 438h
0x180023600  mov     rax, cs:__security_cookie
0x180023607  xor     rax, rsp
0x18002360a  mov     [rbp+360h+var_40], rax
0x180023611  mov     rsi, r8
0x180023614  mov     dword ptr [rsp+460h+pv], 0
0x18002361c  lea     r8, [rsp+460h+var_420]; HICON *
0x180023621  mov     [rsp+460h+var_420], 0
0x18002362a  lea     r9, [rsp+460h+var_430]; bool *
0x18002362f  mov     [rsp+460h+var_430], 0
0x180023634  lea     rdx, [rsp+460h+pv]; int *
0x180023639  mov     rbx, rcx
0x18002363c  call    ?_CalcNewTrayStatus@CSyncTrayIconManager@@AEAAXPEAHPEAPEAUHICON__@@PEA_N@Z; CSyncTrayIconManager::_CalcNewTrayStatus(int *,HICON__ * *,bool *)
0x180023641  mov     r12d, 1
0x180023647  cmp     [rbx+26h], r12b
0x18002364b  jnz     loc_180023824
0x180023651  mov     edi, 3D0h
0x180023656  lea     rcx, [rsp+460h+Data]; void *
0x18002365b  mov     r8d, edi; Size
0x18002365e  xor     edx, edx; Val
0x180023660  call    memset_0
0x180023665  mov     r14d, dword ptr [rsp+460h+pv]
0x18002366a  mov     rax, [rbx+18h]
0x18002366e  mov     rdx, [rsp+460h+var_420]
0x180023673  mov     [rsp+460h+Data.cbSize], edi
0x180023677  mov     edi, r12d
0x18002367a  mov     [rsp+460h+Data.hWnd], rax
0x18002367f  mov     dword ptr [rbp+360h+Data.330h], 4
0x180023689  mov     [rsp+460h+Data.uID], r12d
0x18002368e  mov     [rsp+460h+Data.uFlags], r12d
0x180023693  mov     [rsp+460h+Data.uCallbackMessage], 8002h
0x18002369b  cmp     r14d, [rbx+28h]
0x18002369f  jnz     short loc_1800236B7
0x1800236a1  cmp     rdx, [rbx+30h]
0x1800236a5  jnz     short loc_1800236B7
0x1800236a7  cmp     [rsp+460h+var_430], r12b
0x1800236ac  jz      short loc_1800236B7
0x1800236ae  test    rsi, rsi
0x1800236b1  jz      loc_180023793
0x1800236b7  cmp     dword ptr [rbx+28h], 0
0x1800236bb  jnz     short loc_1800236C8
0x1800236bd  mov     rax, [rbx+30h]
0x1800236c1  neg     rax
0x1800236c4  sbb     ecx, ecx
0x1800236c6  and     edi, ecx
0x1800236c8  test    rdx, rdx
0x1800236cb  jnz     short loc_1800236E7
0x1800236cd  mov     rcx, cs:?g_hmodThisDll@@3PEAUHINSTANCE__@@EA; hinst
0x1800236d4  lea     r9, [rsp+460h+Data.hIcon]; phico
0x1800236d9  movzx   edx, r14w; pszName
0x1800236dd  xor     r8d, r8d; lims
0x1800236e0  call    LoadIconMetric
0x1800236e5  jmp     short loc_180023704
0x1800236e7  mov     rcx, [rbx+30h]; hIcon
0x1800236eb  test    rcx, rcx
0x1800236ee  jz      short loc_1800236FB
0x1800236f0  call    cs:__imp_DestroyIcon
0x1800236f6  mov     rdx, [rsp+460h+var_420]
0x1800236fb  mov     [rbx+30h], rdx
0x1800236ff  mov     [rsp+460h+Data.hIcon], rdx
0x180023704  mov     rcx, [rbx+38h]
0x180023708  test    rcx, rcx
0x18002370b  jz      loc_180023793
0x180023711  mov     [rsp+460h+pv], 0
0x18002371a  lea     rdx, [rsp+460h+pv]
0x18002371f  mov     rax, [rcx]
0x180023722  mov     rax, [rax+30h]
0x180023726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002372b  cmp     eax, 800706BAh
0x180023730  jnz     short loc_180023745
0x180023732  mov     r8b, r12b; bool
0x180023735  xor     edx, edx; bool
0x180023737  mov     rcx, rbx; this
0x18002373a  call    ?_RegisterShellTrayIcon@CSyncTrayIconManager@@AEAAX_N0@Z; CSyncTrayIconManager::_RegisterShellTrayIcon(bool,bool)
0x18002373f  mov     byte ptr [rbx+26h], 0
0x180023743  jmp     short loc_180023793
0x180023745  test    eax, eax
0x180023747  js      short loc_180023793
0x180023749  mov     rcx, cs:?g_hmodThisDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hmodThisDll
0x180023750  lea     r9, [rsp+460h+Data.szTip]
0x180023755  or      [rsp+460h+Data.uFlags], 4
0x18002375a  call    _ResourceStringCopyEx
0x18002375f  mov     esi, 80h
0x180023764  lea     r8, asc_18005D1D8; "\n"
0x18002376b  mov     edx, esi; unsigned __int64
0x18002376d  lea     rcx, [rsp+460h+Data.szTip]; unsigned __int16 *
0x180023772  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180023777  mov     r8, [rsp+460h+pv]; unsigned __int16 *
0x18002377c  lea     rcx, [rsp+460h+Data.szTip]; unsigned __int16 *
0x180023781  mov     edx, esi; unsigned __int64
0x180023783  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180023788  mov     rcx, [rsp+460h+pv]; pv
0x18002378d  call    cs:__imp_CoTaskMemFree
0x180023793  cmp     [rbx+26h], r12b
0x180023797  jnz     short loc_18002380C
0x180023799  cmp     [rsp+460h+Data.uFlags], r12d
0x18002379e  jz      short loc_1800237FD
0x1800237a0  cmp     [rsp+460h+Data.hIcon], 0
0x1800237a6  jnz     short loc_1800237B9
0x1800237a8  cmp     [rbp+360h+Data.hBalloonIcon], 0
0x1800237b0  jnz     short loc_1800237B9
0x1800237b2  and     [rsp+460h+Data.uFlags], 0FFFFFFFDh
0x1800237b7  jmp     short loc_1800237BE
0x1800237b9  or      [rsp+460h+Data.uFlags], 2
0x1800237be  lea     rdx, [rsp+460h+Data]; lpData
0x1800237c3  mov     ecx, edi; dwMessage
0x1800237c5  call    cs:__imp_Shell_NotifyIconW
0x1800237cb  test    eax, eax
0x1800237cd  jnz     short loc_1800237F3
0x1800237cf  cmp     edi, r12d
0x1800237d2  ja      short loc_1800237EA
0x1800237d4  xor     ecx, ecx
0x1800237d6  lea     rdx, [rsp+460h+Data]; lpData
0x1800237db  test    edi, edi
0x1800237dd  setz    cl; dwMessage
0x1800237e0  call    cs:__imp_Shell_NotifyIconW
0x1800237e6  test    eax, eax
0x1800237e8  jnz     short loc_1800237F3
0x1800237ea  mov     dword ptr [rbx+28h], 0
0x1800237f1  jmp     short loc_1800237FD
0x1800237f3  cmp     [rbx+26h], r12b
0x1800237f7  jnz     short loc_1800237FD
0x1800237f9  mov     [rbx+28h], r14d
0x1800237fd  or      [rsp+460h+Data.uFlags], 10h
0x180023802  mov     [rbp+360h+Data.dwInfoFlags], 4
0x18002380c  mov     rcx, [rsp+460h+Data.hIcon]; hIcon
0x180023811  test    rcx, rcx
0x180023814  jz      short loc_180023838
0x180023816  cmp     rcx, [rbx+30h]
0x18002381a  jz      short loc_180023838
0x18002381c  call    cs:__imp_DestroyIcon
0x180023822  jmp     short loc_180023838
0x180023824  cmp     [rsp+460h+var_430], r12b
0x180023829  jnz     short loc_180023838
0x18002382b  mov     r8b, r12b; bool
0x18002382e  xor     edx, edx; bool
0x180023830  mov     rcx, rbx; this
0x180023833  call    ?_RegisterShellTrayIcon@CSyncTrayIconManager@@AEAAX_N0@Z; CSyncTrayIconManager::_RegisterShellTrayIcon(bool,bool)
0x180023838  mov     rcx, [rbp+360h+var_40]
0x18002383f  xor     rcx, rsp; StackCookie
0x180023842  call    __security_check_cookie
0x180023847  add     rsp, 438h
0x18002384e  pop     r14
0x180023850  pop     r12
0x180023852  pop     rdi
0x180023853  pop     rsi
0x180023854  pop     rbx
0x180023855  pop     rbp
0x180023856  retn
```
