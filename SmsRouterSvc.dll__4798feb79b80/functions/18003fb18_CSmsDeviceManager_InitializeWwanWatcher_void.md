# CSmsDeviceManager::InitializeWwanWatcher(void)

- ea: `0x18003fb18`
- end: `0x18003fd51`
- name: `?InitializeWwanWatcher@CSmsDeviceManager@@AEAAJXZ`
- size: `569`
- prototype: `__int64 __fastcall(CSmsDeviceManager *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800443b0`

## callees

- `0x18003d654`
- `0x18003fb18`
- `0x18004099c`
- `0x180051420`
- `0x180051628`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003fbc3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003fbc3`
- `wwapi!WwanEnumerateInterfaces` at `0x18003fc95`
- `wwapi!WwanEnumerateInterfaces` at `0x18003fc95`
- `wwapi!WwanFreeMemory` at `0x18003fd16`
- `wwapi!WwanFreeMemory` at `0x18003fd16`
- `wwapi!WwanOpenHandle` at `0x18003fb84`
- `wwapi!WwanOpenHandle` at `0x18003fb84`
- `wwapi!WwanRegisterNotification` at `0x18003fc42`
- `wwapi!WwanRegisterNotification` at `0x18003fc42`

## string_xrefs

- `0x18003fb9f`: `WwanOpenHandle failed (attempt: %d)`
- `0x18003fc06`: `WwanOpenHandle opened (0x%p)`
- `0x18003fbd4`: `WwanOpenHandle failed and abandoned`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSmsDeviceManager::InitializeWwanWatcher(CSmsDeviceManager *this)
{
  unsigned int v2; // ebx
  char *v3; // rsi
  int v4; // edi
  const void **v5; // r14
  int v6; // eax
  int v7; // eax
  unsigned int v8; // edi
  int v10; // eax
  unsigned int v11; // edi
  unsigned int *i; // rdx
  _BYTE v13[56]; // [rsp+40h] [rbp-38h] BYREF
  int v14; // [rsp+80h] [rbp+8h] BYREF
  int v15; // [rsp+88h] [rbp+10h] BYREF
  unsigned int *v16; // [rsp+90h] [rbp+18h] BYREF

  v2 = 0;
  v15 = 0;
  v16 = 0;
  v14 = 0;
  v3 = (char *)this + 96;
  (**((void (__fastcall ***)(char *))this + 12))((char *)this + 96);
  if ( !*((_DWORD *)this + 10) )
  {
    v4 = 1;
    v5 = (const void **)((char *)this + 48);
    do
    {
      v6 = WwanOpenHandle(1, 0, &v14, (char *)this + 48);
      v2 = v6;
      if ( !v6 )
      {
        v2 = 0;
        goto LABEL_10;
      }
      if ( v6 > 0 )
        v2 = (unsigned __int16)v6 | 0x80070000;
      LogSmsRouterError(
        "CSmsDeviceManager::InitializeWwanWatcher",
        0x2C0u,
        v2,
        "WwanOpenHandle failed (attempt: %d)",
        v4);
      *v5 = 0;
      Sleep(500 * v4++);
    }
    while ( v4 <= 10 );
    if ( (v2 & 0x80000000) != 0 )
    {
      LogSmsRouterError("CSmsDeviceManager::InitializeWwanWatcher", 0x2CEu, v2, "WwanOpenHandle failed and abandoned");
      (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 8LL))(v3);
      return v2;
    }
LABEL_10:
    LogSmsRouterInfo("CSmsDeviceManager::InitializeWwanWatcher", 0x2D2u, "WwanOpenHandle opened (0x%p)", *v5);
    v7 = WwanRegisterNotification(*v5, 6, CSmsDeviceManager::s_OnWwanNotification, this, 0, &v15);
    v8 = v7;
    if ( v7 )
    {
      if ( v7 > 0 )
        v8 = (unsigned __int16)v7 | 0x80070000;
      LogSmsRouterError(
        "CSmsDeviceManager::InitializeWwanWatcher",
        0x2DBu,
        v8,
        "WwanRegisterNotification(WwanNotificationSourceMsm | WwanNotificationSourcePnp) failed");
      (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 8LL))(v3);
      return v8;
    }
    v10 = WwanEnumerateInterfaces(*v5, 0, &v16);
    v8 = v10;
    if ( v10 )
    {
      if ( v10 > 0 )
        v8 = (unsigned __int16)v10 | 0x80070000;
      LogSmsRouterError("CSmsDeviceManager::InitializeWwanWatcher", 0x2E6u, v8, "WwanEnumerateInterfaces failed");
      (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 8LL))(v3);
      return v8;
    }
    v11 = 0;
    for ( i = v16; v11 < *v16; i = v16 )
      std::_Tree<std::_Tset_traits<_GUID,CGuidLessCompare,std::allocator<_GUID>,0>>::insert<0,0>(
        (__int64 *)this + 40,
        (__int64)v13,
        &i[147 * v11++ + 1]);
    WwanFreeMemory(i);
    *((_DWORD *)this + 10) = 1;
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 8LL))(v3);
  CSmsDeviceManager::ProcessPendingSmsDevices(this);
  return v2;
}

```

## disassembly

```asm
0x18003fb18  mov     rax, rsp
0x18003fb1b  mov     [rax+20h], rbx
0x18003fb1f  push    rbp
0x18003fb20  push    rsi
0x18003fb21  push    rdi
0x18003fb22  push    r13
0x18003fb24  push    r14
0x18003fb26  sub     rsp, 50h
0x18003fb2a  mov     rbp, rcx
0x18003fb2d  xor     ebx, ebx
0x18003fb2f  mov     [rax+10h], ebx
0x18003fb32  mov     [rax+18h], rbx
0x18003fb36  mov     [rax+8], ebx
0x18003fb39  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x18003fb40  mov     [rsp+78h+var_48], rax
0x18003fb45  lea     rsi, [rcx+60h]
0x18003fb49  mov     [rsp+78h+var_40], rsi
0x18003fb4e  mov     rax, [rsi]
0x18003fb51  mov     rcx, rsi
0x18003fb54  mov     rax, [rax]
0x18003fb57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fb5c  nop
0x18003fb5d  cmp     [rbp+28h], ebx
0x18003fb60  jnz     loc_18003FD23
0x18003fb66  lea     edi, [rbx+1]
0x18003fb69  lea     r14, [rbp+30h]
0x18003fb6d  lea     r13, aCsmsdevicemana_13; "CSmsDeviceManager::InitializeWwanWatche"...
0x18003fb74  mov     r9, r14
0x18003fb77  lea     r8, [rsp+78h+arg_0]
0x18003fb7f  xor     edx, edx
0x18003fb81  lea     ecx, [rdx+1]
0x18003fb84  call    cs:__imp_WwanOpenHandle
0x18003fb8a  mov     ebx, eax
0x18003fb8c  test    eax, eax
0x18003fb8e  jz      short loc_18003FC01
0x18003fb90  jle     short loc_18003FB9B
0x18003fb92  movzx   ebx, ax
0x18003fb95  or      ebx, 80070000h
0x18003fb9b  mov     dword ptr [rsp+78h+var_58], edi
0x18003fb9f  lea     r9, aWwanopenhandle_2; "WwanOpenHandle failed (attempt: %d)"
0x18003fba6  mov     r8d, ebx; int
0x18003fba9  mov     edx, 2C0h; unsigned int
0x18003fbae  mov     rcx, r13; char *
0x18003fbb1  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18003fbb6  mov     qword ptr [r14], 0
0x18003fbbd  imul    ecx, edi, 1F4h; dwMilliseconds
0x18003fbc3  call    cs:__imp_Sleep
0x18003fbc9  inc     edi
0x18003fbcb  cmp     edi, 0Ah
0x18003fbce  jle     short loc_18003FB74
0x18003fbd0  test    ebx, ebx
0x18003fbd2  jns     short loc_18003FC03
0x18003fbd4  lea     r9, aWwanopenhandle_1; "WwanOpenHandle failed and abandoned"
0x18003fbdb  mov     r8d, ebx; int
0x18003fbde  mov     edx, 2CEh; unsigned int
0x18003fbe3  mov     rcx, r13; char *
0x18003fbe6  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18003fbeb  nop
0x18003fbec  mov     rax, [rsi]
0x18003fbef  mov     rcx, rsi
0x18003fbf2  mov     rax, [rax+8]
0x18003fbf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fbfb  nop
0x18003fbfc  jmp     loc_18003FD3B
0x18003fc01  xor     ebx, ebx
0x18003fc03  mov     r9, [r14]
0x18003fc06  lea     r8, aWwanopenhandle_0; "WwanOpenHandle opened (0x%p)"
0x18003fc0d  mov     edx, 2D2h; unsigned int
0x18003fc12  mov     rcx, r13; char *
0x18003fc15  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x18003fc1a  lea     rax, [rsp+78h+arg_8]
0x18003fc22  mov     [rsp+78h+var_50], rax
0x18003fc27  mov     [rsp+78h+var_58], 0
0x18003fc30  mov     r9, rbp
0x18003fc33  lea     r8, ?s_OnWwanNotification@CSmsDeviceManager@@CAXPEAU_L2_NOTIFICATION_DATA@@PEAX@Z; CSmsDeviceManager::s_OnWwanNotification(_L2_NOTIFICATION_DATA *,void *)
0x18003fc3a  mov     edx, 6
0x18003fc3f  mov     rcx, [r14]
0x18003fc42  call    cs:__imp_WwanRegisterNotification
0x18003fc48  mov     edi, eax
0x18003fc4a  test    eax, eax
0x18003fc4c  jz      short loc_18003FC88
0x18003fc4e  jle     short loc_18003FC59
0x18003fc50  movzx   edi, ax
0x18003fc53  or      edi, 80070000h
0x18003fc59  lea     r9, aWwanregisterno_1; "WwanRegisterNotification(WwanNotificati"...
0x18003fc60  mov     r8d, edi; int
0x18003fc63  mov     edx, 2DBh; unsigned int
0x18003fc68  mov     rcx, r13; char *
0x18003fc6b  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18003fc70  nop
0x18003fc71  mov     rax, [rsi]
0x18003fc74  mov     rcx, rsi
0x18003fc77  mov     rax, [rax+8]
0x18003fc7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fc80  nop
0x18003fc81  mov     eax, edi
0x18003fc83  jmp     loc_18003FD3D
0x18003fc88  lea     r8, [rsp+78h+arg_10]
0x18003fc90  xor     edx, edx
0x18003fc92  mov     rcx, [r14]
0x18003fc95  call    cs:__imp_WwanEnumerateInterfaces
0x18003fc9b  mov     edi, eax
0x18003fc9d  test    eax, eax
0x18003fc9f  jz      short loc_18003FCD6
0x18003fca1  jle     short loc_18003FCAC
0x18003fca3  movzx   edi, ax
0x18003fca6  or      edi, 80070000h
0x18003fcac  lea     r9, aWwanenumeratei_0; "WwanEnumerateInterfaces failed"
0x18003fcb3  mov     r8d, edi; int
0x18003fcb6  mov     edx, 2E6h; unsigned int
0x18003fcbb  mov     rcx, r13; char *
0x18003fcbe  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18003fcc3  nop
0x18003fcc4  mov     rax, [rsi]
0x18003fcc7  mov     rcx, rsi
0x18003fcca  mov     rax, [rax+8]
0x18003fcce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fcd3  nop
0x18003fcd4  jmp     short loc_18003FC81
0x18003fcd6  xor     edi, edi
0x18003fcd8  mov     rdx, [rsp+78h+arg_10]
0x18003fce0  cmp     [rdx], edi
0x18003fce2  jbe     short loc_18003FD13
0x18003fce4  mov     eax, edi
0x18003fce6  imul    rcx, rax, 24Ch
0x18003fced  lea     r8, [rdx+4]
0x18003fcf1  add     r8, rcx
0x18003fcf4  lea     rdx, [rsp+78h+var_38]
0x18003fcf9  lea     rcx, [rbp+140h]
0x18003fd00  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@U_GUID@@VCGuidLessCompare@@V?$allocator@U_GUID@@@std@@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U_GUID@@@std@@@std@@@std@@_N@1@AEBU_GUID@@@Z; std::_Tree<std::_Tset_traits<_GUID,CGuidLessCompare,std::allocator<_GUID>,0>>::insert<0,0>(_GUID const &)
0x18003fd05  inc     edi
0x18003fd07  mov     rdx, [rsp+78h+arg_10]
0x18003fd0f  cmp     edi, [rdx]
0x18003fd11  jb      short loc_18003FCE4
0x18003fd13  mov     rcx, rdx
0x18003fd16  call    cs:__imp_WwanFreeMemory
0x18003fd1c  mov     dword ptr [rbp+28h], 1
0x18003fd23  mov     rcx, [rsi]
0x18003fd26  mov     rax, [rcx+8]
0x18003fd2a  mov     rcx, rsi
0x18003fd2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fd32  nop
0x18003fd33  mov     rcx, rbp; this
0x18003fd36  call    ?ProcessPendingSmsDevices@CSmsDeviceManager@@AEAAJXZ; CSmsDeviceManager::ProcessPendingSmsDevices(void)
0x18003fd3b  mov     eax, ebx
0x18003fd3d  mov     rbx, [rsp+78h+arg_18]
0x18003fd45  add     rsp, 50h
0x18003fd49  pop     r14
0x18003fd4b  pop     r13
0x18003fd4d  pop     rdi
0x18003fd4e  pop     rsi
0x18003fd4f  pop     rbp
0x18003fd50  retn
```
