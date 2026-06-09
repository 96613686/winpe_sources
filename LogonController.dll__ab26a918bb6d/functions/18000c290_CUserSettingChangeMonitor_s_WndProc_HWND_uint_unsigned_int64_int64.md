# CUserSettingChangeMonitor::s_WndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18000c290`
- end: `0x18000c7c2`
- name: `?s_WndProc@CUserSettingChangeMonitor@@CA_JPEAUHWND__@@I_K_J@Z`
- size: `1330`
- prototype: `static __int64(HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation`

## callees

- `0x18000bda4`
- `0x18000c290`
- `0x18000c7c8`
- `0x18000c894`
- `0x18000c918`
- `0x18000c970`
- `0x18000c9dc`
- `0x18000ca90`
- `0x18000cb1c`
- `0x1800852e4`
- `0x18008536c`
- `0x1800853c4`
- `0x18009d010`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x18000c648`
- `KERNEL32!GetTickCount64` at `0x18000c648`
- `KERNEL32!GetCurrentProcessId` at `0x18000c5ca`
- `KERNEL32!GetCurrentProcessId` at `0x18000c5ca`
- `KERNEL32!ReleaseSRWLockShared` at `0x18000c330`
- `KERNEL32!ReleaseSRWLockShared` at `0x18000c3da`
- `KERNEL32!ReleaseSRWLockShared` at `0x18000c4c9`
- `KERNEL32!ReleaseSRWLockShared` at `0x18000c5a5`
- `KERNEL32!ReleaseSRWLockShared` at `0x18000c617`
- `KERNEL32!ReleaseSRWLockShared` at `0x18000c330`
- `KERNEL32!ReleaseSRWLockShared` at `0x18000c3da`
- `KERNEL32!ReleaseSRWLockShared` at `0x18000c4c9`
- `KERNEL32!ReleaseSRWLockShared` at `0x18000c5a5`
- `KERNEL32!ReleaseSRWLockShared` at `0x18000c617`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000c55d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000c55d`
- `KERNEL32!AcquireSRWLockShared` at `0x18000c31d`
- `KERNEL32!AcquireSRWLockShared` at `0x18000c3ab`
- `KERNEL32!AcquireSRWLockShared` at `0x18000c49a`
- `KERNEL32!AcquireSRWLockShared` at `0x18000c576`
- `KERNEL32!AcquireSRWLockShared` at `0x18000c5e4`
- `KERNEL32!AcquireSRWLockShared` at `0x18000c31d`
- `KERNEL32!AcquireSRWLockShared` at `0x18000c3ab`
- `KERNEL32!AcquireSRWLockShared` at `0x18000c49a`
- `KERNEL32!AcquireSRWLockShared` at `0x18000c576`
- `KERNEL32!AcquireSRWLockShared` at `0x18000c5e4`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000c532`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000c532`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18000c5c4`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18000c5c4`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongPtrW` at `0x18000c2af`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongPtrW` at `0x18000c2af`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DefWindowProcW` at `0x18000c306`
- `USER32!RegisterBSDRWindow` at `0x18000c54b`
- `USER32!RegisterBSDRWindow` at `0x18000c54b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
LRESULT __fastcall CUserSettingChangeMonitor::s_WndProc(HWND a1, UINT a2, WPARAM a3, LPARAM a4)
{
  RTL_SRWLOCK *WindowLongPtrW; // rax
  RTL_SRWLOCK *v9; // r13
  struct tagSHUTDOWN_BLOCK_DESCRIPTION *v11; // rdi
  RTL_SRWLOCK *v12; // rsi
  char v13; // bl
  HWND v14; // rcx
  __int64 *v15; // rbx
  RTL_SRWLOCK *v16; // rdi
  __int64 *v17; // rsi
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  unsigned __int8 v22; // di
  RTL_SRWLOCK *v23; // rdi
  unsigned int v24; // ecx
  __int64 *Ptr; // rsi
  unsigned int v26; // edi
  __int64 v27; // rax
  __int64 *v28; // rcx
  RTL_SRWLOCK *v29; // rdi
  __int64 *v30; // rsi
  __int64 *v31; // rdi
  __int64 v32; // r8
  __int64 *v33; // rcx
  int v34; // esi
  unsigned __int8 v35; // di
  unsigned int v36; // edi
  struct _PEB *v37; // rax
  _BYTE v38[4]; // [rsp+20h] [rbp-68h] BYREF
  DWORD dwProcessId; // [rsp+24h] [rbp-64h] BYREF
  __int64 *v40; // [rsp+28h] [rbp-60h] BYREF
  struct tagSHUTDOWN_BLOCK_DESCRIPTION *v41; // [rsp+30h] [rbp-58h] BYREF
  __int64 *v42; // [rsp+38h] [rbp-50h]

  WindowLongPtrW = (RTL_SRWLOCK *)GetWindowLongPtrW(a1, 0);
  v9 = WindowLongPtrW;
  if ( !WindowLongPtrW )
    return DefWindowProcW(a1, a2, a3, a4);
  switch ( a2 )
  {
    case 0x1Au:
      v15 = 0;
      v42 = 0;
      v23 = WindowLongPtrW + 7;
      AcquireSRWLockShared(WindowLongPtrW + 7);
      Ptr = (__int64 *)v9[6].Ptr;
      if ( Ptr )
      {
        (*(void (__fastcall **)(PVOID))(*Ptr + 8))(v9[6].Ptr);
        v15 = Ptr;
        v42 = Ptr;
      }
      if ( v23 )
        ReleaseSRWLockShared(v23);
      if ( v15 )
      {
        if ( a3 == 67 )
        {
          (*(void (__fastcall **)(__int64 *))(*v15 + 24))(v15);
        }
        else if ( CImmersiveColor::IsColorSchemeChangeMessage(v24, a4) )
        {
          (*(void (__fastcall **)(__int64 *))(*v15 + 40))(v15);
          (*(void (__fastcall **)(__int64 *))(*v15 + 32))(v15);
        }
      }
      goto LABEL_46;
    case 0x218u:
      if ( (_DWORD)a3 != 32787 || !a4 )
        return DefWindowProcW(a1, a2, a3, a4);
      v15 = 0;
      v42 = 0;
      v16 = WindowLongPtrW + 7;
      AcquireSRWLockShared(WindowLongPtrW + 7);
      v17 = (__int64 *)v9[6].Ptr;
      if ( v17 )
      {
        (*(void (__fastcall **)(PVOID))(*v17 + 8))(v9[6].Ptr);
        v15 = v17;
        v42 = v17;
      }
      if ( v16 )
        ReleaseSRWLockShared(v16);
      if ( v15 )
      {
        v18 = *(_QWORD *)a4 - *(_QWORD *)&GUID_CONSOLE_DISPLAY_STATE.Data1;
        if ( *(_QWORD *)a4 == *(_QWORD *)&GUID_CONSOLE_DISPLAY_STATE.Data1 )
          v18 = *(_QWORD *)(a4 + 8) - *(_QWORD *)GUID_CONSOLE_DISPLAY_STATE.Data4;
        if ( v18 )
        {
          v19 = *(_QWORD *)a4 - *(_QWORD *)&GUID_LIDSWITCH_STATE_CHANGE.Data1;
          if ( *(_QWORD *)a4 == *(_QWORD *)&GUID_LIDSWITCH_STATE_CHANGE.Data1 )
            v19 = *(_QWORD *)(a4 + 8) - *(_QWORD *)GUID_LIDSWITCH_STATE_CHANGE.Data4;
          if ( v19 )
          {
            v20 = *(_QWORD *)a4 - *(_QWORD *)&GUID_SESSION_USER_PRESENCE.Data1;
            if ( *(_QWORD *)a4 == *(_QWORD *)&GUID_SESSION_USER_PRESENCE.Data1 )
              v20 = *(_QWORD *)(a4 + 8) - *(_QWORD *)GUID_SESSION_USER_PRESENCE.Data4;
            if ( v20 )
            {
              v21 = *(_QWORD *)a4 - *(_QWORD *)&GUID_LOW_POWER_EPOCH.Data1;
              if ( *(_QWORD *)a4 == *(_QWORD *)&GUID_LOW_POWER_EPOCH.Data1 )
                v21 = *(_QWORD *)(a4 + 8) - *(_QWORD *)GUID_LOW_POWER_EPOCH.Data4;
              if ( !v21 )
              {
                v38[0] = *(_DWORD *)(a4 + 20) != 0;
                v22 = v38[0];
                LogonControllerTelemetry::LowPowerStateChanged<bool const &>(v38);
                (*(void (__fastcall **)(__int64 *, _QWORD))(*v15 + 112))(v15, v22);
              }
            }
            else
            {
              v36 = *(unsigned __int8 *)(a4 + 20);
              LODWORD(v41) = v36;
              LogonControllerTelemetry::UserPresenceStateChanged<enum _USER_ACTIVITY_PRESENCE const &>(&v41);
              (*(void (__fastcall **)(__int64 *, _QWORD))(*v15 + 80))(v15, v36);
            }
          }
          else
          {
            v38[0] = *(_DWORD *)(a4 + 20) != 0;
            v35 = v38[0];
            LogonControllerTelemetry::LidStateChanged<bool const &>(v38);
            (*(void (__fastcall **)(__int64 *, _QWORD))(*v15 + 88))(v15, v35);
          }
        }
        else
        {
          v26 = *(unsigned __int8 *)(a4 + 20);
          LODWORD(v41) = v26;
          LogonControllerTelemetry::DisplayStateChanged<enum _MONITOR_DISPLAY_STATE const &>(&v41);
          (*(void (__fastcall **)(__int64 *, _QWORD))(*v15 + 72))(v15, v26);
        }
      }
LABEL_46:
      if ( !v15 )
        return DefWindowProcW(a1, a2, a3, a4);
      v27 = *v15;
      v28 = v15;
LABEL_48:
      (*(void (__fastcall **)(__int64 *))(v27 + 16))(v28);
      return DefWindowProcW(a1, a2, a3, a4);
    case 0x2B1u:
      v15 = 0;
      v42 = 0;
      v29 = WindowLongPtrW + 7;
      AcquireSRWLockShared(WindowLongPtrW + 7);
      v30 = (__int64 *)v9[6].Ptr;
      if ( v30 )
      {
        (*(void (__fastcall **)(PVOID))(*v30 + 8))(v9[6].Ptr);
        v15 = v30;
        v42 = v30;
      }
      if ( v29 )
        ReleaseSRWLockShared(v29);
      if ( v15 )
      {
        v37 = NtCurrentPeb();
        if ( a3 == 2 && v37->SessionId == (_DWORD)a4 )
          (*(void (__fastcall **)(__int64 *))(*v15 + 48))(v15);
      }
      goto LABEL_46;
  }
  if ( a2 != 809 )
    return DefWindowProcW(a1, a2, a3, a4);
  v11 = *(struct tagSHUTDOWN_BLOCK_DESCRIPTION **)(a4 + 16);
  v41 = v11;
  v12 = WindowLongPtrW + 7;
  AcquireSRWLockShared(WindowLongPtrW + 7);
  v13 = BYTE1(v9[10].Ptr);
  if ( v12 )
    ReleaseSRWLockShared(v12);
  if ( v13 )
  {
    AcquireSRWLockExclusive(v12);
    if ( !BYTE1(v9[10].Ptr) )
    {
      BYTE1(v9[10].Ptr) = 1;
      HIDWORD(v9[10].Ptr) = 4;
    }
    RegisterBSDRWindow(v9[11].Ptr, HIDWORD(v9[10].Ptr));
    if ( v12 )
      ReleaseSRWLockExclusive(v12);
  }
  else if ( v11 )
  {
    v14 = *(HWND *)v11;
    if ( *(_QWORD *)v11 == 0xFFFF )
    {
      if ( !a3 )
        goto LABEL_15;
      if ( (unsigned int)GetSharedModeType() != 1 )
        return DefWindowProcW(a1, a2, a3, a4);
      if ( (unsigned int)GetSharedModeType() == 1 )
        LogonControllerTelemetry::BlockedShutdown_ForcedBySharedCart();
      else
LABEL_15:
        LogonControllerTelemetry::BlockedShutdown_ForcedByShellShutdown();
      CUserSettingChangeMonitor::ResolveBlockedShutdown(v9, 1);
      return DefWindowProcW(a1, a2, a3, a4);
    }
    dwProcessId = 0;
    GetWindowThreadProcessId(v14, &dwProcessId);
    if ( dwProcessId != GetCurrentProcessId() )
    {
      v31 = 0;
      v42 = 0;
      AcquireSRWLockShared(v12);
      v33 = (__int64 *)v9[6].Ptr;
      v40 = v33;
      if ( v33 )
      {
        (*(void (__fastcall **)(__int64 *))(*v33 + 8))(v33);
        v31 = v40;
        v42 = v40;
      }
      if ( v12 )
        ReleaseSRWLockShared(v12);
      if ( a3 )
      {
        if ( a3 == 1 )
        {
          (*(void (__fastcall **)(__int64 *, struct tagSHUTDOWN_BLOCK_DESCRIPTION *, _QWORD))(*v31 + 56))(v31, v41, 0);
          CUserSettingChangeMonitor::_LogBSDRAppAddedTelemetry((CUserSettingChangeMonitor *)v9, v41, 0);
        }
        else if ( a3 == 2 )
        {
          LOBYTE(v32) = 1;
          (*(void (__fastcall **)(__int64 *, struct tagSHUTDOWN_BLOCK_DESCRIPTION *, __int64))(*v31 + 56))(
            v31,
            v41,
            v32);
          CUserSettingChangeMonitor::_LogBSDRAppAddedTelemetry((CUserSettingChangeMonitor *)v9, v41, 1);
        }
      }
      else
      {
        v34 = *(_DWORD *)v41;
        (*(void (__fastcall **)(__int64 *, _QWORD))(*v31 + 64))(v31, *(unsigned int *)v41);
        LODWORD(v41) = v34;
        if ( LODWORD(v9[8].Ptr) == v34 )
        {
          LODWORD(v40) = GetTickCount64() - LODWORD(v9[9].Ptr);
          LogonControllerTelemetry::BlockedShutdown_BlockingAppRemoved<unsigned int &,unsigned int const &>(&v41, &v40);
          LODWORD(v9[8].Ptr) = 0;
          v9[9].Ptr = 0;
        }
      }
      if ( v31 )
      {
        v27 = *v31;
        v28 = v31;
        goto LABEL_48;
      }
    }
  }
  return DefWindowProcW(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000c290  push    rbx
0x18000c292  push    rbp
0x18000c293  push    rsi
0x18000c294  push    rdi
0x18000c295  push    r12
0x18000c297  push    r13
0x18000c299  push    r14
0x18000c29b  push    r15
0x18000c29d  sub     rsp, 48h
0x18000c2a1  mov     r15, r9
0x18000c2a4  mov     r12, r8
0x18000c2a7  mov     r14d, edx
0x18000c2aa  mov     rbp, rcx
0x18000c2ad  xor     edx, edx; nIndex
0x18000c2af  call    cs:__imp_GetWindowLongPtrW
0x18000c2b5  mov     r13, rax
0x18000c2b8  test    rax, rax
0x18000c2bb  jz      short loc_18000C2EA
0x18000c2bd  mov     r10d, r14d
0x18000c2c0  sub     r10d, 1Ah
0x18000c2c4  jz      loc_18000C48C
0x18000c2ca  sub     r10d, 1FEh
0x18000c2d1  jz      loc_18000C387
0x18000c2d7  sub     r10d, 99h
0x18000c2de  jz      loc_18000C568
0x18000c2e4  cmp     r10d, 78h ; 'x'
0x18000c2e8  jz      short loc_18000C30D
0x18000c2ea  mov     r9, r15
0x18000c2ed  mov     r8, r12
0x18000c2f0  mov     edx, r14d
0x18000c2f3  mov     rcx, rbp
0x18000c2f6  add     rsp, 48h
0x18000c2fa  pop     r15
0x18000c2fc  pop     r14
0x18000c2fe  pop     r13
0x18000c300  pop     r12
0x18000c302  pop     rdi
0x18000c303  pop     rsi
0x18000c304  pop     rbp
0x18000c305  pop     rbx
0x18000c306  jmp     cs:__imp_DefWindowProcW
0x18000c30d  mov     rdi, [r15+10h]
0x18000c311  mov     [rsp+88h+var_58], rdi
0x18000c316  lea     rsi, [rax+38h]
0x18000c31a  mov     rcx, rsi; SRWLock
0x18000c31d  call    cs:__imp_AcquireSRWLockShared
0x18000c323  movzx   ebx, byte ptr [r13+51h]
0x18000c328  test    rsi, rsi
0x18000c32b  jz      short loc_18000C336
0x18000c32d  mov     rcx, rsi; SRWLock
0x18000c330  call    cs:__imp_ReleaseSRWLockShared
0x18000c336  test    bl, bl
0x18000c338  jnz     loc_18000C52F
0x18000c33e  test    rdi, rdi
0x18000c341  jz      short loc_18000C2EA
0x18000c343  mov     rcx, [rdi]; hWnd
0x18000c346  cmp     rcx, 0FFFFh
0x18000c34d  jnz     loc_18000C5B9
0x18000c353  test    r12, r12
0x18000c356  jz      short loc_18000C370
0x18000c358  call    ?GetSharedModeType@@YA?AW4SharedModeType@@XZ; GetSharedModeType(void)
0x18000c35d  cmp     eax, 1
0x18000c360  jnz     short loc_18000C2EA
0x18000c362  call    ?GetSharedModeType@@YA?AW4SharedModeType@@XZ; GetSharedModeType(void)
0x18000c367  cmp     eax, 1
0x18000c36a  jz      loc_18000C79C
0x18000c370  call    ?BlockedShutdown_ForcedByShellShutdown@LogonControllerTelemetry@@SAXXZ; LogonControllerTelemetry::BlockedShutdown_ForcedByShellShutdown(void)
0x18000c375  mov     edx, 1
0x18000c37a  mov     rcx, r13
0x18000c37d  call    ?ResolveBlockedShutdown@CUserSettingChangeMonitor@@QEAAXW4BlockedShutdownResolution@Controller@Logon@UI@Internal@Windows@@@Z; CUserSettingChangeMonitor::ResolveBlockedShutdown(Windows::Internal::UI::Logon::Controller::BlockedShutdownResolution)
0x18000c382  jmp     loc_18000C2EA
0x18000c387  cmp     r12d, 8013h
0x18000c38e  jnz     loc_18000C2EA
0x18000c394  test    r15, r15
0x18000c397  jz      loc_18000C2EA
0x18000c39d  xor     ebx, ebx
0x18000c39f  mov     [rsp+88h+var_50], rbx
0x18000c3a4  lea     rdi, [rax+38h]
0x18000c3a8  mov     rcx, rdi; SRWLock
0x18000c3ab  call    cs:__imp_AcquireSRWLockShared
0x18000c3b1  mov     rsi, [r13+30h]
0x18000c3b5  test    rsi, rsi
0x18000c3b8  jz      short loc_18000C3D2
0x18000c3ba  mov     rax, [rsi]
0x18000c3bd  mov     rcx, rsi
0x18000c3c0  mov     rax, [rax+8]
0x18000c3c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3c9  nop
0x18000c3ca  mov     rbx, rsi
0x18000c3cd  mov     [rsp+88h+var_50], rbx
0x18000c3d2  test    rdi, rdi
0x18000c3d5  jz      short loc_18000C3E0
0x18000c3d7  mov     rcx, rdi; SRWLock
0x18000c3da  call    cs:__imp_ReleaseSRWLockShared
0x18000c3e0  test    rbx, rbx
0x18000c3e3  jz      loc_18000C515
0x18000c3e9  mov     rax, [r15]
0x18000c3ec  sub     rax, qword ptr cs:GUID_CONSOLE_DISPLAY_STATE.Data1
0x18000c3f3  jnz     short loc_18000C400
0x18000c3f5  mov     rax, [r15+8]
0x18000c3f9  sub     rax, qword ptr cs:GUID_CONSOLE_DISPLAY_STATE.Data4
0x18000c400  test    rax, rax
0x18000c403  jz      loc_18000C4F0
0x18000c409  mov     rax, [r15]
0x18000c40c  sub     rax, qword ptr cs:GUID_LIDSWITCH_STATE_CHANGE.Data1
0x18000c413  jnz     short loc_18000C420
0x18000c415  mov     rax, [r15+8]
0x18000c419  sub     rax, qword ptr cs:GUID_LIDSWITCH_STATE_CHANGE.Data4
0x18000c420  test    rax, rax
0x18000c423  jz      loc_18000C681
0x18000c429  mov     rax, [r15]
0x18000c42c  sub     rax, qword ptr cs:GUID_SESSION_USER_PRESENCE.Data1
0x18000c433  jnz     short loc_18000C440
0x18000c435  mov     rax, [r15+8]
0x18000c439  sub     rax, qword ptr cs:GUID_SESSION_USER_PRESENCE.Data4
0x18000c440  test    rax, rax
0x18000c443  jz      loc_18000C6B1
0x18000c449  mov     rax, [r15]
0x18000c44c  sub     rax, qword ptr cs:GUID_LOW_POWER_EPOCH.Data1
0x18000c453  jnz     short loc_18000C460
0x18000c455  mov     rax, [r15+8]
0x18000c459  sub     rax, qword ptr cs:GUID_LOW_POWER_EPOCH.Data4
0x18000c460  test    rax, rax
0x18000c463  jnz     loc_18000C515
0x18000c469  cmp     [r15+14h], eax
0x18000c46d  setnz   dil
0x18000c471  mov     [rsp+88h+var_68], dil
0x18000c476  lea     rcx, [rsp+88h+var_68]
0x18000c47b  call    ??$LowPowerStateChanged@AEB_N@LogonControllerTelemetry@@SAXAEB_N@Z; LogonControllerTelemetry::LowPowerStateChanged<bool const &>(bool const &)
0x18000c480  mov     rax, [rbx]
0x18000c483  mov     rax, [rax+70h]
0x18000c487  jmp     loc_18000C6A0
0x18000c48c  xor     ebx, ebx
0x18000c48e  mov     [rsp+88h+var_50], rbx
0x18000c493  lea     rdi, [rax+38h]
0x18000c497  mov     rcx, rdi; SRWLock
0x18000c49a  call    cs:__imp_AcquireSRWLockShared
0x18000c4a0  mov     rsi, [r13+30h]
0x18000c4a4  test    rsi, rsi
0x18000c4a7  jz      short loc_18000C4C1
0x18000c4a9  mov     rax, [rsi]
0x18000c4ac  mov     rcx, rsi
0x18000c4af  mov     rax, [rax+8]
0x18000c4b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4b8  nop
0x18000c4b9  mov     rbx, rsi
0x18000c4bc  mov     [rsp+88h+var_50], rbx
0x18000c4c1  test    rdi, rdi
0x18000c4c4  jz      short loc_18000C4CF
0x18000c4c6  mov     rcx, rdi; SRWLock
0x18000c4c9  call    cs:__imp_ReleaseSRWLockShared
0x18000c4cf  test    rbx, rbx
0x18000c4d2  jz      short loc_18000C4EE
0x18000c4d4  cmp     r12, 43h ; 'C'
0x18000c4d8  jz      loc_18000C7B8
0x18000c4de  mov     rdx, r15; __int64
0x18000c4e1  call    ?IsColorSchemeChangeMessage@CImmersiveColor@@SA_NI_J@Z; CImmersiveColor::IsColorSchemeChangeMessage(uint,__int64)
0x18000c4e6  test    al, al
0x18000c4e8  jnz     loc_18000C743
0x18000c4ee  jmp     short loc_18000C515
0x18000c4f0  movzx   edi, byte ptr [r15+14h]
0x18000c4f5  mov     dword ptr [rsp+88h+var_58], edi
0x18000c4f9  lea     rcx, [rsp+88h+var_58]
0x18000c4fe  call    ??$DisplayStateChanged@AEBW4_MONITOR_DISPLAY_STATE@@@LogonControllerTelemetry@@SAXAEBW4_MONITOR_DISPLAY_STATE@@@Z; LogonControllerTelemetry::DisplayStateChanged<_MONITOR_DISPLAY_STATE const &>(_MONITOR_DISPLAY_STATE const &)
0x18000c503  mov     rax, [rbx]
0x18000c506  mov     edx, edi
0x18000c508  mov     rcx, rbx
0x18000c50b  mov     rax, [rax+48h]
0x18000c50f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c514  nop
0x18000c515  test    rbx, rbx
0x18000c518  jz      short loc_18000C52A
0x18000c51a  mov     rax, [rbx]
0x18000c51d  mov     rcx, rbx
0x18000c520  mov     rax, [rax+10h]
0x18000c524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c529  nop
0x18000c52a  jmp     loc_18000C2EA
0x18000c52f  mov     rcx, rsi; SRWLock
0x18000c532  call    cs:__imp_AcquireSRWLockExclusive
0x18000c538  cmp     byte ptr [r13+51h], 0
0x18000c53d  jz      loc_18000C7A6
0x18000c543  mov     edx, [r13+54h]
0x18000c547  mov     rcx, [r13+58h]
0x18000c54b  call    cs:__imp_RegisterBSDRWindow
0x18000c551  test    rsi, rsi
0x18000c554  jz      loc_18000C2EA
0x18000c55a  mov     rcx, rsi; SRWLock
0x18000c55d  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c563  jmp     loc_18000C2EA
0x18000c568  xor     ebx, ebx
0x18000c56a  mov     [rsp+88h+var_50], rbx
0x18000c56f  lea     rdi, [rax+38h]
0x18000c573  mov     rcx, rdi; SRWLock
0x18000c576  call    cs:__imp_AcquireSRWLockShared
0x18000c57c  mov     rsi, [r13+30h]
0x18000c580  test    rsi, rsi
0x18000c583  jz      short loc_18000C59D
0x18000c585  mov     rax, [rsi]
0x18000c588  mov     rcx, rsi
0x18000c58b  mov     rax, [rax+8]
0x18000c58f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c594  nop
0x18000c595  mov     rbx, rsi
0x18000c598  mov     [rsp+88h+var_50], rbx
0x18000c59d  test    rdi, rdi
0x18000c5a0  jz      short loc_18000C5AB
0x18000c5a2  mov     rcx, rdi; SRWLock
0x18000c5a5  call    cs:__imp_ReleaseSRWLockShared
0x18000c5ab  test    rbx, rbx
0x18000c5ae  jnz     loc_18000C6DA
0x18000c5b4  jmp     loc_18000C515
0x18000c5b9  xor     ebx, ebx
0x18000c5bb  mov     [rsp+88h+dwProcessId], ebx
0x18000c5bf  lea     rdx, [rsp+88h+dwProcessId]; lpdwProcessId
0x18000c5c4  call    cs:__imp_GetWindowThreadProcessId
0x18000c5ca  call    cs:__imp_GetCurrentProcessId
0x18000c5d0  cmp     [rsp+88h+dwProcessId], eax
0x18000c5d4  jz      loc_18000C2EA
0x18000c5da  mov     edi, ebx
0x18000c5dc  mov     [rsp+88h+var_50], rbx
0x18000c5e1  mov     rcx, rsi; SRWLock
0x18000c5e4  call    cs:__imp_AcquireSRWLockShared
0x18000c5ea  mov     rcx, [r13+30h]
0x18000c5ee  mov     [rsp+88h+var_60], rcx
0x18000c5f3  test    rcx, rcx
0x18000c5f6  jz      short loc_18000C60F
0x18000c5f8  mov     rax, [rcx]
0x18000c5fb  mov     rax, [rax+8]
0x18000c5ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c604  nop
0x18000c605  mov     rdi, [rsp+88h+var_60]
0x18000c60a  mov     [rsp+88h+var_50], rdi
0x18000c60f  test    rsi, rsi
0x18000c612  jz      short loc_18000C61D
0x18000c614  mov     rcx, rsi; SRWLock
0x18000c617  call    cs:__imp_ReleaseSRWLockShared
0x18000c61d  test    r12, r12
0x18000c620  jnz     loc_18000C70E
0x18000c626  mov     rsi, [rsp+88h+var_58]
0x18000c62b  mov     esi, [rsi]
0x18000c62d  mov     rax, [rdi]
0x18000c630  mov     edx, esi
0x18000c632  mov     rcx, rdi
0x18000c635  mov     rax, [rax+40h]
0x18000c639  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c63e  mov     dword ptr [rsp+88h+var_58], esi
0x18000c642  cmp     [r13+40h], esi
0x18000c646  jnz     short loc_18000C66D
0x18000c648  call    cs:__imp_GetTickCount64
0x18000c64e  sub     eax, [r13+48h]
0x18000c652  mov     dword ptr [rsp+88h+var_60], eax
0x18000c656  lea     rdx, [rsp+88h+var_60]
0x18000c65b  lea     rcx, [rsp+88h+var_58]
0x18000c660  call    ??$BlockedShutdown_BlockingAppRemoved@AEAIAEBI@LogonControllerTelemetry@@SAXAEAIAEBI@Z; LogonControllerTelemetry::BlockedShutdown_BlockingAppRemoved<uint &,uint const &>(uint &,uint const &)
0x18000c665  mov     [r13+40h], ebx
0x18000c669  mov     [r13+48h], rbx
0x18000c66d  test    rdi, rdi
0x18000c670  jz      loc_18000C52A
0x18000c676  mov     rax, [rdi]
0x18000c679  mov     rcx, rdi
0x18000c67c  jmp     loc_18000C520
0x18000c681  cmp     dword ptr [r15+14h], 0
0x18000c686  setnz   dil
0x18000c68a  mov     [rsp+88h+var_68], dil
0x18000c68f  lea     rcx, [rsp+88h+var_68]
0x18000c694  call    ??$LidStateChanged@AEB_N@LogonControllerTelemetry@@SAXAEB_N@Z; LogonControllerTelemetry::LidStateChanged<bool const &>(bool const &)
0x18000c699  mov     rax, [rbx]
0x18000c69c  mov     rax, [rax+58h]
0x18000c6a0  movzx   edx, dil
0x18000c6a4  mov     rcx, rbx
0x18000c6a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6ac  jmp     loc_18000C515
0x18000c6b1  movzx   edi, byte ptr [r15+14h]
0x18000c6b6  mov     dword ptr [rsp+88h+var_58], edi
0x18000c6ba  lea     rcx, [rsp+88h+var_58]
0x18000c6bf  call    ??$UserPresenceStateChanged@AEBW4_USER_ACTIVITY_PRESENCE@@@LogonControllerTelemetry@@SAXAEBW4_USER_ACTIVITY_PRESENCE@@@Z; LogonControllerTelemetry::UserPresenceStateChanged<_USER_ACTIVITY_PRESENCE const &>(_USER_ACTIVITY_PRESENCE const &)
0x18000c6c4  mov     rax, [rbx]
0x18000c6c7  mov     edx, edi
0x18000c6c9  mov     rcx, rbx
0x18000c6cc  mov     rax, [rax+50h]
0x18000c6d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6d5  jmp     loc_18000C515
0x18000c6da  mov     rax, gs:60h
0x18000c6e3  cmp     r12, 2
0x18000c6e7  jnz     loc_18000C5B4
0x18000c6ed  cmp     [rax+2C0h], r15d
0x18000c6f4  jnz     loc_18000C5B4
0x18000c6fa  mov     rax, [rbx]
0x18000c6fd  mov     rcx, rbx
0x18000c700  mov     rax, [rax+30h]
0x18000c704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c709  jmp     loc_18000C5B4
0x18000c70e  mov     rax, r12
0x18000c711  sub     rax, 1
0x18000c715  jnz     short loc_18000C766
0x18000c717  mov     rax, [rdi]
0x18000c71a  xor     r8d, r8d
0x18000c71d  mov     rdx, [rsp+88h+var_58]
0x18000c722  mov     rcx, rdi
  ... truncated ...
```
