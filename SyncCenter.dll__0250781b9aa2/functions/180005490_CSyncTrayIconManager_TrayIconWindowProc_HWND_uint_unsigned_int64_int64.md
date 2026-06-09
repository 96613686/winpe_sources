# CSyncTrayIconManager::_TrayIconWindowProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180005490`
- end: `0x18000564e`
- name: `?_TrayIconWindowProc@CSyncTrayIconManager@@AEAA_JPEAUHWND__@@I_K_J@Z`
- size: `446`
- prototype: `LRESULT __fastcall(CSyncTrayIconManager *this, HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800053f0`

## callees

- `0x180005490`
- `0x180009940`
- `0x180023314`
- `0x180023548`
- `0x1800235e8`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005556`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005556`
- `USER32!DefWindowProcW` at `0x1800054f4`
- `USER32!DefWindowProcW` at `0x1800054f4`
- `USER32!DestroyWindow` at `0x1800055e3`
- `USER32!DestroyWindow` at `0x1800055e3`
- `USER32!PostMessageW` at `0x180005635`
- `USER32!PostMessageW` at `0x180005635`
- `USER32!KillTimer` at `0x180005611`
- `USER32!KillTimer` at `0x180005611`
- `USER32!PostQuitMessage` at `0x18000561f`
- `USER32!PostQuitMessage` at `0x18000561f`

## pseudocode

```c
LRESULT __fastcall CSyncTrayIconManager::_TrayIconWindowProc(
        CSyncTrayIconManager *this,
        HWND hWnd,
        UINT Msg,
        WPARAM wParam,
        LPARAM lParam)
{
  void *v8; // rbx
  LPVOID ppv; // [rsp+30h] [rbp-1A8h] BYREF
  _BYTE v10[404]; // [rsp+44h] [rbp-194h] BYREF

  switch ( Msg )
  {
    case 1u:
      PostMessageW(hWnd, 0x8001u, 0, 0);
      break;
    case 2u:
      CSyncTrayIconManager::_RegisterShellTrayIcon(this, (bool)hWnd, 0);
      KillTimer(hWnd, 3u);
      *((_QWORD *)this + 3) = 0;
      PostQuitMessage(0);
      break;
    case 0x113u:
      if ( wParam == 3 )
        CSyncTrayIconManager::_UpdateTrayIcon(this, hWnd, 0);
      break;
    case 0x8000u:
      DestroyWindow(hWnd);
      break;
    case 0x8001u:
      v8 = 0;
      if ( lParam )
      {
        CZeroInitNew::operator delete(0);
        v8 = (void *)lParam;
      }
      CSyncTrayIconManager::_UpdateTrayIcon(this, hWnd, v10);
      CZeroInitNew::operator delete(v8);
      break;
    case 0x8002u:
      switch ( lParam )
      {
        case 515LL:
          *((_BYTE *)this + 39) = 1;
          break;
        case 514LL:
          if ( *((_BYTE *)this + 39) == 1 )
          {
            *((_BYTE *)this + 39) = 0;
          }
          else
          {
            ppv = 0;
            if ( CoCreateInstance(&CLSID_OpenControlPanel, 0, 1u, &GUID_d11ad862_66de_4df4_bf6c_1f5621996af1, &ppv) >= 0 )
            {
              (*(void (__fastcall **)(LPVOID, const unsigned __int16 *, _QWORD, _QWORD))(*(_QWORD *)ppv + 24LL))(
                ppv,
                L"Microsoft.SyncCenter",
                0,
                0);
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
            }
          }
          break;
        case 517LL:
          CSyncTrayIconManager::_OnTrayMenu((CSyncTrayIconManager *)(Msg - 32769), hWnd);
          break;
      }
      break;
    default:
      return DefWindowProcW(hWnd, Msg, wParam, lParam);
  }
  return 0;
}

```

## disassembly

```asm
0x180005490  mov     [rsp+arg_0], rbx
0x180005495  push    rdi
0x180005496  sub     rsp, 1D0h
0x18000549d  mov     r10, r9
0x1800054a0  mov     eax, r8d
0x1800054a3  mov     rbx, rdx
0x1800054a6  mov     rdi, rcx
0x1800054a9  cmp     r8d, 1
0x1800054ad  jz      loc_180005627
0x1800054b3  mov     ecx, eax
0x1800054b5  sub     ecx, 2
0x1800054b8  jz      loc_1800055FE
0x1800054be  sub     ecx, 111h
0x1800054c4  jz      loc_1800055EB
0x1800054ca  sub     ecx, 7EEDh
0x1800054d0  jz      loc_1800055E0
0x1800054d6  sub     ecx, 1; this
0x1800054d9  jz      loc_1800055AE
0x1800054df  cmp     ecx, 1
0x1800054e2  jz      short loc_1800054FF
0x1800054e4  mov     r9, [rsp+1D8h+lParam]; lParam
0x1800054ec  mov     r8, r10; wParam
0x1800054ef  mov     edx, eax; Msg
0x1800054f1  mov     rcx, rbx; hWnd
0x1800054f4  call    cs:__imp_DefWindowProcW
0x1800054fa  jmp     loc_18000563D
0x1800054ff  mov     rax, [rsp+1D8h+lParam]
0x180005507  cmp     rax, 203h
0x18000550d  jnz     short loc_180005518
0x18000550f  mov     byte ptr [rdi+27h], 1
0x180005513  jmp     loc_18000563B
0x180005518  cmp     rax, 202h
0x18000551e  jnz     short loc_180005598
0x180005520  cmp     byte ptr [rdi+27h], 1
0x180005524  jnz     short loc_18000552F
0x180005526  mov     byte ptr [rdi+27h], 0
0x18000552a  jmp     loc_18000563B
0x18000552f  lea     rax, [rsp+1D8h+var_1A8]
0x180005534  xor     ebx, ebx
0x180005536  lea     r9, _GUID_d11ad862_66de_4df4_bf6c_1f5621996af1; riid
0x18000553d  mov     [rsp+1D8h+var_1A8], rbx
0x180005542  xor     edx, edx; pUnkOuter
0x180005544  mov     [rsp+1D8h+ppv], rax; ppv
0x180005549  mov     r8d, 1; dwClsContext
0x18000554f  lea     rcx, CLSID_OpenControlPanel; rclsid
0x180005556  call    cs:__imp_CoCreateInstance
0x18000555c  test    eax, eax
0x18000555e  js      loc_18000563B
0x180005564  mov     rcx, [rsp+1D8h+var_1A8]
0x180005569  lea     rdx, aMicrosoftSyncc; "Microsoft.SyncCenter"
0x180005570  xor     r9d, r9d
0x180005573  xor     r8d, r8d
0x180005576  mov     rax, [rcx]
0x180005579  mov     rax, [rax+18h]
0x18000557d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005582  mov     rcx, [rsp+1D8h+var_1A8]
0x180005587  mov     rax, [rcx]
0x18000558a  mov     rax, [rax+10h]
0x18000558e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005593  jmp     loc_18000563B
0x180005598  cmp     rax, 205h
0x18000559e  jnz     loc_18000563B
0x1800055a4  call    ?_OnTrayMenu@CSyncTrayIconManager@@AEAAXPEAUHWND__@@@Z; CSyncTrayIconManager::_OnTrayMenu(HWND__ *)
0x1800055a9  jmp     loc_18000563B
0x1800055ae  xor     ebx, ebx
0x1800055b0  cmp     [rsp+1D8h+lParam], rbx
0x1800055b8  jz      short loc_1800055C9
0x1800055ba  xor     ecx, ecx; lpMem
0x1800055bc  call    ??3CZeroInitNew@@SAXPEAX@Z; CZeroInitNew::operator delete(void *)
0x1800055c1  mov     rbx, [rsp+1D8h+lParam]
0x1800055c9  lea     r8, [rsp+1D8h+var_194]
0x1800055ce  mov     rcx, rdi
0x1800055d1  call    ?_UpdateTrayIcon@CSyncTrayIconManager@@AEAAXW4SYNCMGR_STATE_CHANGE_TYPE@@PEBG1@Z; CSyncTrayIconManager::_UpdateTrayIcon(SYNCMGR_STATE_CHANGE_TYPE,ushort const *,ushort const *)
0x1800055d6  mov     rcx, rbx; lpMem
0x1800055d9  call    ??3CZeroInitNew@@SAXPEAX@Z; CZeroInitNew::operator delete(void *)
0x1800055de  jmp     short loc_18000563B
0x1800055e0  mov     rcx, rbx; hWnd
0x1800055e3  call    cs:__imp_DestroyWindow
0x1800055e9  jmp     short loc_18000563B
0x1800055eb  cmp     r10, 3
0x1800055ef  jnz     short loc_18000563B
0x1800055f1  xor     r8d, r8d
0x1800055f4  mov     rcx, rdi
0x1800055f7  call    ?_UpdateTrayIcon@CSyncTrayIconManager@@AEAAXW4SYNCMGR_STATE_CHANGE_TYPE@@PEBG1@Z; CSyncTrayIconManager::_UpdateTrayIcon(SYNCMGR_STATE_CHANGE_TYPE,ushort const *,ushort const *)
0x1800055fc  jmp     short loc_18000563B
0x1800055fe  xor     r8d, r8d; bool
0x180005601  mov     rcx, rdi; this
0x180005604  call    ?_RegisterShellTrayIcon@CSyncTrayIconManager@@AEAAX_N0@Z; CSyncTrayIconManager::_RegisterShellTrayIcon(bool,bool)
0x180005609  mov     edx, 3; uIDEvent
0x18000560e  mov     rcx, rbx; hWnd
0x180005611  call    cs:__imp_KillTimer
0x180005617  xor     ebx, ebx
0x180005619  xor     ecx, ecx; nExitCode
0x18000561b  mov     [rdi+18h], rbx
0x18000561f  call    cs:__imp_PostQuitMessage
0x180005625  jmp     short loc_18000563B
0x180005627  xor     r9d, r9d; lParam
0x18000562a  xor     r8d, r8d; wParam
0x18000562d  mov     edx, 8001h; Msg
0x180005632  mov     rcx, rbx; hWnd
0x180005635  call    cs:__imp_PostMessageW
0x18000563b  xor     eax, eax
0x18000563d  mov     rbx, [rsp+1D8h+arg_0]
0x180005645  add     rsp, 1D0h
0x18000564c  pop     rdi
0x18000564d  retn
```
