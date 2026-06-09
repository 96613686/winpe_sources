# SystemSettings::PointInTimeRestore::CPointInTimeRestoreDialog::SetProperty(HSTRING__ *,IInspectable *)

- ea: `0x18001f470`
- end: `0x18001f70c`
- name: `?SetProperty@CPointInTimeRestoreDialog@PointInTimeRestore@SystemSettings@@MEAAJPEAUHSTRING__@@PEAUIInspectable@@@Z`
- size: `668`
- prototype: `__int64 __fastcall(SystemSettings::PointInTimeRestore::CPointInTimeRestoreDialog *__hidden this, HSTRING, struct IInspectable *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000bef4`
- `0x18001c1f8`
- `0x18001f470`
- `0x18001f720`
- `0x1800215bc`
- `0x18002548c`
- `0x180025920`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f4b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f4b2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001f4a3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001f4a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001f487`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001f487`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001f515`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001f515`
- `WDSCORE!CurrentIP` at `0x18001f4ba`
- `WDSCORE!CurrentIP` at `0x18001f4ba`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::PointInTimeRestore::CPointInTimeRestoreDialog::SetProperty(
        SystemSettings::PointInTimeRestore::CPointInTimeRestoreDialog *this,
        HSTRING a2,
        struct IInspectable *a3)
{
  const WCHAR *StringRawBuffer; // rax
  DWORD LastError; // edi
  __int64 v8; // rbx
  struct tagLOG_PARTIAL_MSG *v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  struct SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton *Current; // rax
  SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton *v23; // rax
  unsigned int v24; // r8d

  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  if ( CompareStringOrdinal(StringRawBuffer, -1, L"TriggerCancel", -1, 0) != 2 )
    return SystemSettings::DataModel::CSettingBase::SetProperty(this, a2, a3);
  LastError = GetLastError();
  v8 = CurrentIP();
  v9 = ConstructPartialMsgW(
         0x4000000u,
         "SystemSettings::PointInTimeRestore::CPointInTimeRestoreDialog::SetProperty: Close was triggered, resetting state");
  WdsSetupLogMessageW(
    v9,
    0,
    L"D",
    0,
    199,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
    L"SystemSettings::PointInTimeRestore::CPointInTimeRestoreDialog::SetProperty",
    v8,
    LastError,
    0,
    0);
  v10 = *((_QWORD *)this + 35);
  if ( v10 )
  {
    *((_QWORD *)this + 35) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    v11 = *((_QWORD *)this + 35);
    if ( v11 )
    {
      *((_QWORD *)this + 35) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
  }
  v12 = *((_QWORD *)this + 36);
  if ( v12 )
  {
    *((_QWORD *)this + 36) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v13 = *((_QWORD *)this + 36);
    if ( v13 )
    {
      *((_QWORD *)this + 36) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
  }
  v14 = *((_QWORD *)this + 37);
  if ( v14 )
  {
    *((_QWORD *)this + 37) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v15 = *((_QWORD *)this + 37);
    if ( v15 )
    {
      *((_QWORD *)this + 37) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
  }
  v16 = *((_QWORD *)this + 38);
  if ( v16 )
  {
    *((_QWORD *)this + 38) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v17 = *((_QWORD *)this + 38);
    if ( v17 )
    {
      *((_QWORD *)this + 38) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
  }
  v18 = *((_QWORD *)this + 39);
  if ( v18 )
  {
    *((_QWORD *)this + 39) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v19 = *((_QWORD *)this + 39);
    if ( v19 )
    {
      *((_QWORD *)this + 39) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
  }
  v20 = *((_QWORD *)this + 40);
  if ( v20 )
  {
    *((_QWORD *)this + 40) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v21 = *((_QWORD *)this + 40);
    if ( v21 )
    {
      *((_QWORD *)this + 40) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
  }
  Current = SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent();
  SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::Unregister(
    (__int64)Current,
    (RTL_SRWLOCK *)(((unsigned __int64)this + 240) & -(__int64)(this != 0)),
    (__int64)this + 240);
  v23 = SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent();
  SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::CleanState(v23);
  *((_DWORD *)this + 82) = 0;
  SystemSettings::DataModel::CSettingBase::OnValueChanged(this, L"IsPrimaryButtonEnabled", v24);
  (*(void (__fastcall **)(SystemSettings::PointInTimeRestore::CPointInTimeRestoreDialog *, _QWORD))(*(_QWORD *)this
                                                                                                  + 168LL))(
    this,
    0);
  return 0;
}

```

## disassembly

```asm
0x18001f470  push    rbx
0x18001f472  push    rbp
0x18001f473  push    rsi
0x18001f474  push    rdi
0x18001f475  sub     rsp, 68h
0x18001f479  mov     rdi, r8
0x18001f47c  mov     rbx, rdx
0x18001f47f  mov     rsi, rcx
0x18001f482  xor     edx, edx; length
0x18001f484  mov     rcx, rbx; string
0x18001f487  call    cs:__imp_WindowsGetStringRawBuffer
0x18001f48d  mov     rcx, rax; lpString1
0x18001f490  xor     ebp, ebp
0x18001f492  mov     [rsp+88h+bIgnoreCase], ebp; bIgnoreCase
0x18001f496  or      edx, 0FFFFFFFFh; cchCount1
0x18001f499  mov     r9d, edx; cchCount2
0x18001f49c  lea     r8, aTriggercancel; "TriggerCancel"
0x18001f4a3  call    cs:__imp_CompareStringOrdinal
0x18001f4a9  cmp     eax, 2
0x18001f4ac  jnz     loc_18001F6F5
0x18001f4b2  call    cs:__imp_GetLastError
0x18001f4b8  mov     edi, eax
0x18001f4ba  call    cs:__imp_CurrentIP
0x18001f4c0  mov     rbx, rax
0x18001f4c3  lea     rdx, aSystemsettings_103; "SystemSettings::PointInTimeRestore::CPo"...
0x18001f4ca  mov     ecx, 4000000h; unsigned int
0x18001f4cf  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18001f4d4  mov     [rsp+88h+var_38], ebp
0x18001f4d8  mov     [rsp+88h+var_40], rbp
0x18001f4dd  mov     [rsp+88h+var_48], edi
0x18001f4e1  mov     [rsp+88h+var_50], rbx
0x18001f4e6  lea     rcx, aSystemsettings_138; "SystemSettings::PointInTimeRestore::CPo"...
0x18001f4ed  mov     [rsp+88h+var_58], rcx
0x18001f4f2  lea     rcx, aPcshellShellSy_1; "pcshell\\shell\\systemsettings\\recover"...
0x18001f4f9  mov     [rsp+88h+var_60], rcx
0x18001f4fe  mov     [rsp+88h+bIgnoreCase], 0C7h
0x18001f506  xor     r9d, r9d
0x18001f509  lea     r8, aD; "D"
0x18001f510  xor     edx, edx
0x18001f512  mov     rcx, rax
0x18001f515  call    cs:__imp_WdsSetupLogMessageW
0x18001f51b  mov     rcx, [rsi+118h]
0x18001f522  test    rcx, rcx
0x18001f525  jz      short loc_18001F55B
0x18001f527  mov     [rsi+118h], rbp
0x18001f52e  mov     rax, [rcx]
0x18001f531  mov     rax, [rax+10h]
0x18001f535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f53a  nop
0x18001f53b  mov     rcx, [rsi+118h]
0x18001f542  test    rcx, rcx
0x18001f545  jz      short loc_18001F55B
0x18001f547  mov     [rsi+118h], rbp
0x18001f54e  mov     rax, [rcx]
0x18001f551  mov     rax, [rax+10h]
0x18001f555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f55a  nop
0x18001f55b  mov     rcx, [rsi+120h]
0x18001f562  test    rcx, rcx
0x18001f565  jz      short loc_18001F59B
0x18001f567  mov     [rsi+120h], rbp
0x18001f56e  mov     rax, [rcx]
0x18001f571  mov     rax, [rax+10h]
0x18001f575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f57a  nop
0x18001f57b  mov     rcx, [rsi+120h]
0x18001f582  test    rcx, rcx
0x18001f585  jz      short loc_18001F59B
0x18001f587  mov     [rsi+120h], rbp
0x18001f58e  mov     rax, [rcx]
0x18001f591  mov     rax, [rax+10h]
0x18001f595  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f59a  nop
0x18001f59b  mov     rcx, [rsi+128h]
0x18001f5a2  test    rcx, rcx
0x18001f5a5  jz      short loc_18001F5DB
0x18001f5a7  mov     [rsi+128h], rbp
0x18001f5ae  mov     rax, [rcx]
0x18001f5b1  mov     rax, [rax+10h]
0x18001f5b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f5ba  nop
0x18001f5bb  mov     rcx, [rsi+128h]
0x18001f5c2  test    rcx, rcx
0x18001f5c5  jz      short loc_18001F5DB
0x18001f5c7  mov     [rsi+128h], rbp
0x18001f5ce  mov     rax, [rcx]
0x18001f5d1  mov     rax, [rax+10h]
0x18001f5d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f5da  nop
0x18001f5db  mov     rcx, [rsi+130h]
0x18001f5e2  test    rcx, rcx
0x18001f5e5  jz      short loc_18001F61B
0x18001f5e7  mov     [rsi+130h], rbp
0x18001f5ee  mov     rax, [rcx]
0x18001f5f1  mov     rax, [rax+10h]
0x18001f5f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f5fa  nop
0x18001f5fb  mov     rcx, [rsi+130h]
0x18001f602  test    rcx, rcx
0x18001f605  jz      short loc_18001F61B
0x18001f607  mov     [rsi+130h], rbp
0x18001f60e  mov     rax, [rcx]
0x18001f611  mov     rax, [rax+10h]
0x18001f615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f61a  nop
0x18001f61b  mov     rcx, [rsi+138h]
0x18001f622  test    rcx, rcx
0x18001f625  jz      short loc_18001F65B
0x18001f627  mov     [rsi+138h], rbp
0x18001f62e  mov     rax, [rcx]
0x18001f631  mov     rax, [rax+10h]
0x18001f635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f63a  nop
0x18001f63b  mov     rcx, [rsi+138h]
0x18001f642  test    rcx, rcx
0x18001f645  jz      short loc_18001F65B
0x18001f647  mov     [rsi+138h], rbp
0x18001f64e  mov     rax, [rcx]
0x18001f651  mov     rax, [rax+10h]
0x18001f655  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f65a  nop
0x18001f65b  mov     rcx, [rsi+140h]
0x18001f662  test    rcx, rcx
0x18001f665  jz      short loc_18001F69B
0x18001f667  mov     [rsi+140h], rbp
0x18001f66e  mov     rax, [rcx]
0x18001f671  mov     rax, [rax+10h]
0x18001f675  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f67a  nop
0x18001f67b  mov     rcx, [rsi+140h]
0x18001f682  test    rcx, rcx
0x18001f685  jz      short loc_18001F69B
0x18001f687  mov     [rsi+140h], rbp
0x18001f68e  mov     rax, [rcx]
0x18001f691  mov     rax, [rax+10h]
0x18001f695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f69a  nop
0x18001f69b  call    ?GetCurrent@CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@SAPEAV123@XZ; SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent(void)
0x18001f6a0  mov     rcx, rsi
0x18001f6a3  lea     r8, [rsi+0F0h]
0x18001f6aa  neg     rcx
0x18001f6ad  sbb     rdx, rdx
0x18001f6b0  and     rdx, r8
0x18001f6b3  mov     rcx, rax
0x18001f6b6  call    ?Unregister@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z; SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::Unregister(SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *)
0x18001f6bb  call    ?GetCurrent@CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@SAPEAV123@XZ; SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent(void)
0x18001f6c0  mov     rcx, rax; this
0x18001f6c3  call    ?CleanState@CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@QEAAXXZ; SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::CleanState(void)
0x18001f6c8  mov     [rsi+148h], ebp
0x18001f6ce  lea     rdx, aIsprimarybutto; "IsPrimaryButtonEnabled"
0x18001f6d5  mov     rcx, rsi; this
0x18001f6d8  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x18001f6dd  mov     rax, [rsi]
0x18001f6e0  xor     edx, edx
0x18001f6e2  mov     rcx, rsi
0x18001f6e5  mov     rax, [rax+0A8h]
0x18001f6ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f6f1  xor     eax, eax
0x18001f6f3  jmp     short loc_18001F703
0x18001f6f5  mov     r8, rdi; struct IInspectable *
0x18001f6f8  mov     rdx, rbx; HSTRING
0x18001f6fb  mov     rcx, rsi; this
0x18001f6fe  call    ?SetProperty@CSettingBase@DataModel@SystemSettings@@UEAAJPEAUHSTRING__@@PEAUIInspectable@@@Z; SystemSettings::DataModel::CSettingBase::SetProperty(HSTRING__ *,IInspectable *)
0x18001f703  add     rsp, 68h
0x18001f707  pop     rdi
0x18001f708  pop     rsi
0x18001f709  pop     rbp
0x18001f70a  pop     rbx
0x18001f70b  retn
```
