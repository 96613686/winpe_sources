# ConfigSet::Initialize(int)

- ea: `0x18001e2ac`
- end: `0x18001e4a7`
- name: `?Initialize@ConfigSet@@QEAAJH@Z`
- size: `507`
- prototype: `__int64 __fastcall(ConfigSet *__hidden this, int)`
- caller_count: `6`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800209e0`
- `0x1800519bc`
- `0x180078550`
- `0x18007d30c`
- `0x180081440`
- `0x18008e1d0`

## callees

- `0x180018614`
- `0x18001e2ac`
- `0x18001e4b0`
- `0x18001e4e8`
- `0x18001ee54`
- `0x18001efb4`
- `0x18001f188`
- `0x18002416c`
- `0x1800c50ec`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001e336`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001e336`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e353`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e449`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e353`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e449`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18001e3f1`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18001e3f1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18001e43f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18001e43f`

## string_xrefs

- `0x18001e2be`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`

## pseudocode

```c
__int64 __fastcall ConfigSet::Initialize(ConfigSet *this, int a2)
{
  int v4; // ecx
  __int64 v5; // rcx
  HANDLE EventW; // rax
  signed int LastError; // eax
  int OnlyFailIfKeyAbsent; // ebx
  HKEY v10; // rcx
  LSTATUS v11; // eax
  void *v12; // rbx
  void **v13; // rax
  signed int v14; // eax

  if ( (unsigned __int64)(*((_QWORD *)this + 13) + 0x80000000LL) > 3 )
  {
    Log_AssertionEvent_5(this, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 936);
    if ( (unsigned __int64)(*((_QWORD *)this + 13) + 0x80000000LL) > 3 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v4 = *((_DWORD *)this + 36);
  if ( v4 )
  {
    v5 = (unsigned int)(v4 - 1);
    if ( (_DWORD)v5 )
    {
      if ( (_DWORD)v5 == 1 )
      {
        OnlyFailIfKeyAbsent = ConfigSet::ReadOnlyFailIfKeyAbsent((HKEY *)this);
        if ( OnlyFailIfKeyAbsent < 0 )
          goto LABEL_18;
      }
      else
      {
        Log_AssertionEvent_5(v5, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 953);
        MicrosoftTelemetryAssertTriggeredNoArgs();
      }
    }
    else
    {
      OnlyFailIfKeyAbsent = ConfigSet::ReadWriteFailIfKeyAbsent((HKEY *)this);
      if ( OnlyFailIfKeyAbsent < 0 )
        goto LABEL_18;
    }
  }
  else
  {
    OnlyFailIfKeyAbsent = ConfigSet::ReadWriteCreateKey(this);
    if ( OnlyFailIfKeyAbsent < 0 )
    {
LABEL_18:
      Log_HREvent_5(OnlyFailIfKeyAbsent);
      return (unsigned int)OnlyFailIfKeyAbsent;
    }
  }
  if ( a2 )
    goto LABEL_28;
  EventW = CreateEventW(0, 0, 0, 0);
  tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::reset((char *)this + 72, EventW);
  if ( !*((_QWORD *)this + 9) )
  {
    LastError = GetLastError();
    OnlyFailIfKeyAbsent = LastError;
    if ( LastError > 0 )
      OnlyFailIfKeyAbsent = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_18;
  }
  v10 = (HKEY)*((_QWORD *)this + 10);
  if ( (unsigned __int64)(v10 + 0x20000000) <= 3 )
  {
    OnlyFailIfKeyAbsent = -2147418113;
    goto LABEL_18;
  }
  v11 = RegNotifyChangeKeyValue(v10, 1, 0x10000004u, *((HANDLE *)this + 9), 1);
  OnlyFailIfKeyAbsent = v11;
  if ( v11 > 0 )
    OnlyFailIfKeyAbsent = (unsigned __int16)v11 | 0x80070000;
  if ( OnlyFailIfKeyAbsent < 0 )
    goto LABEL_18;
  v12 = (void *)*((_QWORD *)this + 9);
  v13 = tlx::replace<void *,unsigned long (*)(void *),&private: static unsigned long ConfigSet::UnregisterWaitAndBlock(void *),0>((void **)this + 12);
  if ( !RegisterWaitForSingleObject(v13, v12, ConfigSet::RegistryNotificationCallback, this, 0xFFFFFFFF, 0) )
  {
    v14 = GetLastError();
    OnlyFailIfKeyAbsent = v14;
    if ( v14 > 0 )
      OnlyFailIfKeyAbsent = (unsigned __int16)v14 | 0x80070000;
    goto LABEL_18;
  }
LABEL_28:
  OnlyFailIfKeyAbsent = (*(__int64 (__fastcall **)(ConfigSet *))(*(_QWORD *)this + 8LL))(this);
  if ( OnlyFailIfKeyAbsent < 0 )
    goto LABEL_18;
  return 0;
}

```

## disassembly

```asm
0x18001e2ac  push    rbx
0x18001e2ae  push    rbp
0x18001e2af  push    rsi
0x18001e2b0  push    r12
0x18001e2b2  push    r14
0x18001e2b4  push    r15
0x18001e2b6  sub     rsp, 38h
0x18001e2ba  mov     rax, [rcx+68h]
0x18001e2be  lea     r15, aOnecoreuapInte_2; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18001e2c5  mov     r12d, 80000000h
0x18001e2cb  mov     ebp, edx
0x18001e2cd  add     rax, r12
0x18001e2d0  mov     rsi, rcx
0x18001e2d3  cmp     rax, 3
0x18001e2d7  jbe     short loc_18001E2F9
0x18001e2d9  mov     r8d, 3A8h
0x18001e2df  mov     rdx, r15
0x18001e2e2  call    Log_AssertionEvent_5
0x18001e2e7  mov     rax, [rsi+68h]
0x18001e2eb  add     rax, r12
0x18001e2ee  cmp     rax, 3
0x18001e2f2  jbe     short loc_18001E2F9
0x18001e2f4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001e2f9  mov     ecx, [rsi+90h]
0x18001e2ff  test    ecx, ecx
0x18001e301  jz      loc_18001E39E
0x18001e307  sub     ecx, 1
0x18001e30a  jz      short loc_18001E388
0x18001e30c  cmp     ecx, 1
0x18001e30f  jz      short loc_18001E372
0x18001e311  mov     r8d, 3B9h
0x18001e317  mov     rdx, r15
0x18001e31a  call    Log_AssertionEvent_5
0x18001e31f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001e324  test    ebp, ebp
0x18001e326  jnz     loc_18001E477
0x18001e32c  xor     r9d, r9d; lpName
0x18001e32f  xor     r8d, r8d; bInitialState
0x18001e332  xor     edx, edx; bManualReset
0x18001e334  xor     ecx, ecx; lpEventAttributes
0x18001e336  call    cs:__imp_CreateEventW
0x18001e33c  lea     r14, [rsi+48h]
0x18001e340  mov     rdx, rax
0x18001e343  mov     rcx, r14
0x18001e346  call    ?reset@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@QEAAXPEAX@Z; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::reset(void *)
0x18001e34b  mov     r9, [r14]; hEvent
0x18001e34e  test    r9, r9
0x18001e351  jnz     short loc_18001E3CC
0x18001e353  call    cs:__imp_GetLastError
0x18001e359  mov     ebx, eax
0x18001e35b  test    eax, eax
0x18001e35d  jle     short loc_18001E368
0x18001e35f  movzx   ebx, ax
0x18001e362  or      ebx, 80070000h
0x18001e368  mov     r9d, 3C1h
0x18001e36e  xor     edx, edx
0x18001e370  jmp     short loc_18001E3BB
0x18001e372  mov     rcx, rsi; this
0x18001e375  call    ?ReadOnlyFailIfKeyAbsent@ConfigSet@@QEAAJXZ; ConfigSet::ReadOnlyFailIfKeyAbsent(void)
0x18001e37a  mov     ebx, eax
0x18001e37c  test    eax, eax
0x18001e37e  jns     short loc_18001E324
0x18001e380  mov     r9d, 3B5h
0x18001e386  jmp     short loc_18001E3B6
0x18001e388  mov     rcx, rsi; this
0x18001e38b  call    ?ReadWriteFailIfKeyAbsent@ConfigSet@@QEAAJXZ; ConfigSet::ReadWriteFailIfKeyAbsent(void)
0x18001e390  mov     ebx, eax
0x18001e392  test    eax, eax
0x18001e394  jns     short loc_18001E324
0x18001e396  mov     r9d, 3B1h
0x18001e39c  jmp     short loc_18001E3B6
0x18001e39e  mov     rcx, rsi; this
0x18001e3a1  call    ?ReadWriteCreateKey@ConfigSet@@QEAAJXZ; ConfigSet::ReadWriteCreateKey(void)
0x18001e3a6  mov     ebx, eax
0x18001e3a8  test    eax, eax
0x18001e3aa  jns     loc_18001E324
0x18001e3b0  mov     r9d, 3ADh
0x18001e3b6  mov     edx, 1
0x18001e3bb  mov     r8, r15
0x18001e3be  mov     ecx, ebx; int
0x18001e3c0  call    Log_HREvent_5
0x18001e3c5  mov     eax, ebx
0x18001e3c7  jmp     loc_18001E499
0x18001e3cc  mov     rcx, [rsi+50h]; hKey
0x18001e3d0  lea     rax, [rcx+r12]
0x18001e3d4  cmp     rax, 3
0x18001e3d8  jbe     loc_18001E465
0x18001e3de  mov     edx, 1; bWatchSubtree
0x18001e3e3  mov     [rsp+68h+fAsynchronous], 1; fAsynchronous
0x18001e3eb  mov     r8d, 10000004h; dwNotifyFilter
0x18001e3f1  call    cs:__imp_RegNotifyChangeKeyValue
0x18001e3f7  mov     ebx, eax
0x18001e3f9  mov     ebp, 80070000h
0x18001e3fe  test    eax, eax
0x18001e400  jle     short loc_18001E407
0x18001e402  movzx   ebx, ax
0x18001e405  or      ebx, ebp
0x18001e407  test    ebx, ebx
0x18001e409  jns     short loc_18001E413
0x18001e40b  mov     r9d, 3CCh
0x18001e411  jmp     short loc_18001E3B6
0x18001e413  mov     rbx, [r14]
0x18001e416  lea     rcx, [rsi+60h]
0x18001e41a  call    ??$replace@PEAXP6AKPEAX@Z$1?UnregisterWaitAndBlock@ConfigSet@@CAK0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AKPEAX@Z$1?UnregisterWaitAndBlock@ConfigSet@@CAK0@Z$0A@@0@@Z; tlx::replace<void *,ulong (*)(void *),&ConfigSet::UnregisterWaitAndBlock(void *),0>(tlx::auto_xxx<void *,ulong (*)(void *),&ConfigSet::UnregisterWaitAndBlock(void *),0> &)
0x18001e41f  mov     r9, rsi; Context
0x18001e422  mov     [rsp+68h+dwFlags], 0; dwFlags
0x18001e42a  lea     r8, ?RegistryNotificationCallback@ConfigSet@@CAXPEAXE@Z; Callback
0x18001e431  mov     [rsp+68h+fAsynchronous], 0FFFFFFFFh; dwMilliseconds
0x18001e439  mov     rdx, rbx; hObject
0x18001e43c  mov     rcx, rax; phNewWaitObject
0x18001e43f  call    cs:__imp_RegisterWaitForSingleObject
0x18001e445  test    eax, eax
0x18001e447  jnz     short loc_18001E477
0x18001e449  call    cs:__imp_GetLastError
0x18001e44f  mov     ebx, eax
0x18001e451  test    eax, eax
0x18001e453  jle     short loc_18001E45A
0x18001e455  movzx   ebx, ax
0x18001e458  or      ebx, ebp
0x18001e45a  mov     r9d, 3CFh
0x18001e460  jmp     loc_18001E36E
0x18001e465  mov     r9d, 3C8h
0x18001e46b  xor     edx, edx
0x18001e46d  mov     ebx, 8000FFFFh
0x18001e472  jmp     loc_18001E3BB
0x18001e477  mov     rax, [rsi]
0x18001e47a  mov     rcx, rsi
0x18001e47d  mov     rax, [rax+8]
0x18001e481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e486  mov     ebx, eax
0x18001e488  test    eax, eax
0x18001e48a  jns     short loc_18001E497
0x18001e48c  mov     r9d, 3D2h
0x18001e492  jmp     loc_18001E3B6
0x18001e497  xor     eax, eax
0x18001e499  add     rsp, 38h
0x18001e49d  pop     r15
0x18001e49f  pop     r14
0x18001e4a1  pop     r12
0x18001e4a3  pop     rsi
0x18001e4a4  pop     rbp
0x18001e4a5  pop     rbx
0x18001e4a6  retn
```
