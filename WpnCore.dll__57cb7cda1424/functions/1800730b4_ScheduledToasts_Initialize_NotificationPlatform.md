# ScheduledToasts::Initialize(NotificationPlatform *)

- ea: `0x1800730b4`
- end: `0x18007341c`
- name: `?Initialize@ScheduledToasts@@QEAAJPEAVNotificationPlatform@@@Z`
- size: `872`
- prototype: `__int64 __fastcall(ScheduledToasts *__hidden this, struct NotificationPlatform *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180035508`

## callees

- `0x180024640`
- `0x18002e5d0`
- `0x18002ff5c`
- `0x1800730b4`
- `0x180073424`
- `0x1800734c0`
- `0x1800a61dc`
- `0x1800af0a4`
- `0x1800b99f0`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800731cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800733df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800731cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800733df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800731db`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800733ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800731db`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800733ed`
- `ntdll!RtlNtStatusToDosError` at `0x180073137`
- `ntdll!RtlNtStatusToDosError` at `0x180073137`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtFreeMemory` at `0x1800733cb`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtFreeMemory` at `0x1800733cb`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtDeleteEvent` at `0x1800732f8`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtDeleteEvent` at `0x1800732f8`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtEnumerateBrokeredEvents` at `0x180073127`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtEnumerateBrokeredEvents` at `0x180073127`
- `TimeBrokerClient!TbDeleteEvent` at `0x1800732ea`
- `TimeBrokerClient!TbDeleteEvent` at `0x1800732ea`

## string_xrefs

- `0x1800731a2`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtoasts.cpp`
- `0x1800733ae`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtoasts.cpp`
- `0x18007319b`: `ScheduledToasts::Initialize`
- `0x1800733a7`: `ScheduledToasts::Initialize`

## pseudocode

```c
__int64 __fastcall ScheduledToasts::Initialize(ScheduledToasts *this, struct NotificationPlatform *a2)
{
  struct ScheduledToasts::_PERSISTEDTOAST *v2; // rdi
  __int64 (__fastcall ***v3)(_QWORD, char *, int *); // r12
  NTSTATUS v5; // eax
  unsigned int v6; // edx
  int v7; // ecx
  signed int IsExpired; // ebx
  signed int v9; // eax
  unsigned int v10; // eax
  int UserSid; // eax
  unsigned int v12; // ecx
  unsigned int v13; // esi
  HANDLE ProcessHeap; // rax
  __int64 v15; // r14
  int v16; // eax
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  int v19; // eax
  unsigned __int16 *v20; // rcx
  struct _WNF_STATE_NAME v21; // rdx
  struct _GUID v22; // xmm0
  HANDLE v23; // rax
  unsigned int v25; // [rsp+40h] [rbp-89h] BYREF
  __int64 v26; // [rsp+48h] [rbp-81h] BYREF
  int v27; // [rsp+50h] [rbp-79h] BYREF
  int v28; // [rsp+54h] [rbp-75h] BYREF
  int v29; // [rsp+58h] [rbp-71h] BYREF
  struct ScheduledToasts::_PERSISTEDTOAST *v30; // [rsp+60h] [rbp-69h] BYREF
  struct _GUID v31; // [rsp+70h] [rbp-59h] BYREF
  struct _GUID v32; // [rsp+80h] [rbp-49h] BYREF
  _BYTE v33[80]; // [rsp+90h] [rbp-39h] BYREF

  v2 = 0;
  *((_QWORD *)this + 5) = a2;
  v3 = (__int64 (__fastcall ***)(_QWORD, char *, int *))*((_QWORD *)a2 + 23);
  v26 = 0;
  v25 = 0;
  v27 = 0;
  v30 = 0;
  v29 = 0;
  if ( v3 )
  {
    v5 = BiPtEnumerateBrokeredEvents(qword_1801278D0, &v25, &v26);
    if ( v5 < 0 )
    {
      v9 = RtlNtStatusToDosError(v5);
      IsExpired = v9;
      if ( v9 > 0 )
        IsExpired = (unsigned __int16)v9 | 0x80070000;
    }
    else
    {
      IsExpired = 0;
    }
    if ( IsExpired < 0 )
    {
      if ( (Microsoft_Windows_PushNotifications_PlatformEnableBits & 0x20) != 0 )
        McTemplateU0zzdqz_EventWriteTransfer(
          v7,
          (unsigned int)WPNCORE_EVENT_DEBUG_INIT,
          (unsigned int)L"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtoasts.cpp",
          (unsigned int)L"ScheduledToasts::Initialize",
          110,
          IsExpired,
          (__int64)&word_180124798);
      goto LABEL_45;
    }
    v10 = v25;
    if ( v25 )
    {
      UserSid = WpnGetUserSid(v33, v6);
      IsExpired = UserSid;
      if ( UserSid < 0 )
      {
        WpnDebugInitTrace(
          v12,
          L"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtoasts.cpp",
          L"ScheduledToasts::Initialize",
          114,
          UserSid);
        goto LABEL_45;
      }
      v10 = v25;
    }
    v13 = 0;
    if ( !v10 )
      goto LABEL_45;
    while ( 1 )
    {
      if ( v2 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v2);
        v30 = 0;
      }
      v15 = 16LL * v13;
      v28 = 0;
      v31 = *(struct _GUID *)(v15 + v26);
      v16 = ScheduledToasts::UnpackPersistedEvent(&v31, v33, &v30, &v27);
      v2 = v30;
      IsExpired = v16;
      if ( v16 >= 0 )
      {
        if ( !v27 )
          goto LABEL_37;
        v16 = (**v3)(v3, (char *)v30 + 92, &v29);
        if ( v16 == -2147023728 )
        {
          v19 = 1;
          IsExpired = 0;
        }
        else
        {
          if ( v16 < 0 )
          {
            v17 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
              goto LABEL_21;
            v18 = 15;
            goto LABEL_20;
          }
          IsExpired = ScheduledToasts::TimerIsExpired(v2, 0, &v28);
          if ( IsExpired < 0 )
            IsExpired = 0;
          v19 = v28;
        }
        if ( *((_DWORD *)v2 + 13) )
          v20 = (unsigned __int16 *)((char *)v2 + 352);
        else
          v20 = 0;
        if ( v19 )
        {
          v31 = *(struct _GUID *)((char *)v2 + 4);
          TbDeleteEvent(v20, &v31);
          BiPtDeleteEvent(v15 + v26);
          goto LABEL_37;
        }
        v21 = *(struct _WNF_STATE_NAME *)((char *)v2 + 20);
        v22 = *(struct _GUID *)(v15 + v26);
        v32 = *(struct _GUID *)((char *)v2 + 4);
        v31 = v22;
        v16 = ScheduledToasts::SubscribeAndAddToList(this, v21, &v32, &v31, (const unsigned __int16 *)v2 + 46, v20);
        IsExpired = v16;
        if ( v16 >= 0 )
          goto LABEL_37;
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
          goto LABEL_21;
        v18 = 17;
      }
      else
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
          goto LABEL_21;
        v18 = 13;
      }
LABEL_20:
      WPP_SF_d(v17[2], v18, WPP_7a7099aae5df3fa656003ab1196d31fe_Traceguids, (unsigned int)v16);
LABEL_21:
      IsExpired = 0;
LABEL_37:
      if ( ++v13 >= v25 )
        goto LABEL_45;
    }
  }
  IsExpired = -2143420155;
  if ( (Microsoft_Windows_PushNotifications_PlatformEnableBits & 0x20) == 0 )
    return (unsigned int)IsExpired;
  McTemplateU0zzdqz_EventWriteTransfer(
    (_DWORD)this,
    (unsigned int)WPNCORE_EVENT_DEBUG_INIT,
    (unsigned int)L"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtoasts.cpp",
    (unsigned int)L"ScheduledToasts::Initialize",
    101,
    5,
    (__int64)&word_180124798);
LABEL_45:
  if ( v26 )
  {
    BiPtFreeMemory();
    v26 = 0;
  }
  if ( v2 )
  {
    v23 = GetProcessHeap();
    HeapFree(v23, 0, v2);
  }
  return (unsigned int)IsExpired;
}

```

## disassembly

```asm
0x1800730b4  mov     [rsp-8+arg_10], rbx
0x1800730b9  push    rbp
0x1800730ba  push    rsi
0x1800730bb  push    rdi
0x1800730bc  push    r12
0x1800730be  push    r13
0x1800730c0  push    r14
0x1800730c2  push    r15
0x1800730c4  lea     rbp, [rsp-27h]
0x1800730c9  sub     rsp, 0F0h
0x1800730d0  mov     rax, cs:__security_cookie
0x1800730d7  xor     rax, rsp
0x1800730da  mov     [rbp+57h+var_40], rax
0x1800730de  xor     edi, edi
0x1800730e0  mov     [rcx+28h], rdx
0x1800730e4  mov     r12, [rdx+0B8h]
0x1800730eb  mov     r13, rcx
0x1800730ee  mov     [rsp+120h+var_D8], 0
0x1800730f7  mov     [rsp+120h+var_E0], 0
0x1800730ff  mov     [rbp+57h+var_D0], 0
0x180073106  mov     [rbp+57h+var_C0], rdi
0x18007310a  mov     [rbp+57h+var_C8], edi
0x18007310d  test    r12, r12
0x180073110  jz      loc_18007337D
0x180073116  lea     r8, [rsp+120h+var_D8]
0x18007311b  lea     rdx, [rsp+120h+var_E0]
0x180073120  lea     rcx, qword_1801278D0
0x180073127  call    cs:__imp_BiPtEnumerateBrokeredEvents
0x18007312d  test    eax, eax
0x18007312f  js      short loc_180073135
0x180073131  xor     ebx, ebx
0x180073133  jmp     short loc_18007314C
0x180073135  mov     ecx, eax; Status
0x180073137  call    cs:__imp_RtlNtStatusToDosError
0x18007313d  mov     ebx, eax
0x18007313f  test    eax, eax
0x180073141  jle     short loc_18007314C
0x180073143  movzx   ebx, ax
0x180073146  or      ebx, 80070000h
0x18007314c  test    ebx, ebx
0x18007314e  jns     short loc_18007317A
0x180073150  test    cs:Microsoft_Windows_PushNotifications_PlatformEnableBits, 20h
0x180073157  jz      loc_1800733C1
0x18007315d  lea     rax, word_180124798
0x180073164  mov     [rsp+120h+var_F0], rax
0x180073169  mov     dword ptr [rsp+120h+var_F8], ebx
0x18007316d  mov     dword ptr [rsp+120h+var_100], 6Eh ; 'n'
0x180073175  jmp     loc_1800733A7
0x18007317a  mov     eax, [rsp+120h+var_E0]
0x18007317e  test    eax, eax
0x180073180  jz      short loc_1800731B7
0x180073182  lea     rcx, [rbp+57h+var_90]; void *
0x180073186  call    ?WpnGetUserSid@@YAJPEAXK@Z; WpnGetUserSid(void *,ulong)
0x18007318b  mov     ebx, eax
0x18007318d  test    eax, eax
0x18007318f  jns     short loc_1800731B3
0x180073191  mov     r9d, 72h ; 'r'; int
0x180073197  mov     dword ptr [rsp+120h+var_100], eax; int
0x18007319b  lea     r8, aScheduledtoast; "ScheduledToasts::Initialize"
0x1800731a2  lea     rdx, aOnecoreuapBase_72; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800731a9  call    ?WpnDebugInitTrace@@YAXKPEBG0HJ@Z; WpnDebugInitTrace(ulong,ushort const *,ushort const *,int,long)
0x1800731ae  jmp     loc_1800733C1
0x1800731b3  mov     eax, [rsp+120h+var_E0]
0x1800731b7  xor     esi, esi
0x1800731b9  test    eax, eax
0x1800731bb  jz      loc_1800733C1
0x1800731c1  lea     r15, WPP_GLOBAL_Control
0x1800731c8  test    rdi, rdi
0x1800731cb  jz      short loc_1800731E9
0x1800731cd  call    cs:__imp_GetProcessHeap
0x1800731d3  mov     r8, rdi; lpMem
0x1800731d6  xor     edx, edx; dwFlags
0x1800731d8  mov     rcx, rax; hHeap
0x1800731db  call    cs:__imp_HeapFree
0x1800731e1  mov     [rbp+57h+var_C0], 0
0x1800731e9  mov     rax, [rsp+120h+var_D8]
0x1800731ee  lea     r9, [rbp+57h+var_D0]; int *
0x1800731f2  mov     r14d, esi
0x1800731f5  lea     r8, [rbp+57h+var_C0]; struct ScheduledToasts::_PERSISTEDTOAST **
0x1800731f9  shl     r14, 4
0x1800731fd  lea     rdx, [rbp+57h+var_90]; void *
0x180073201  lea     rcx, [rbp+57h+var_B0]; struct _GUID
0x180073205  mov     [rbp+57h+var_CC], 0
0x18007320c  movups  xmm0, xmmword ptr [r14+rax]
0x180073211  movdqu  xmmword ptr [rbp+57h+var_B0.Data1], xmm0
0x180073216  call    ?UnpackPersistedEvent@ScheduledToasts@@CAJU_GUID@@PEAXPEAPEAU_PERSISTEDTOAST@1@PEAH@Z; ScheduledToasts::UnpackPersistedEvent(_GUID,void *,ScheduledToasts::_PERSISTEDTOAST * *,int *)
0x18007321b  mov     rdi, [rbp+57h+var_C0]
0x18007321f  mov     ebx, eax
0x180073221  test    eax, eax
0x180073223  jns     short loc_180073256
0x180073225  mov     rcx, cs:WPP_GLOBAL_Control
0x18007322c  cmp     rcx, r15
0x18007322f  jz      short loc_18007324F
0x180073231  test    byte ptr [rcx+1Ch], 80h
0x180073235  jz      short loc_18007324F
0x180073237  mov     edx, 0Dh
0x18007323c  mov     rcx, [rcx+10h]
0x180073240  lea     r8, WPP_7a7099aae5df3fa656003ab1196d31fe_Traceguids
0x180073247  mov     r9d, eax
0x18007324a  call    WPP_SF_d
0x18007324f  xor     ebx, ebx
0x180073251  jmp     loc_180073305
0x180073256  cmp     [rbp+57h+var_D0], 0
0x18007325a  jz      loc_180073305
0x180073260  mov     rax, [r12]
0x180073264  lea     r15, [rdi+5Ch]
0x180073268  lea     r8, [rbp+57h+var_C8]
0x18007326c  mov     rdx, r15
0x18007326f  mov     rcx, r12
0x180073272  mov     rax, [rax]
0x180073275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007327a  cmp     eax, 80070490h
0x18007327f  jnz     short loc_18007328A
0x180073281  mov     eax, 1
0x180073286  xor     ebx, ebx
0x180073288  jmp     short loc_1800732C8
0x18007328a  test    eax, eax
0x18007328c  jns     short loc_1800732AE
0x18007328e  mov     rcx, cs:WPP_GLOBAL_Control
0x180073295  lea     r15, WPP_GLOBAL_Control
0x18007329c  cmp     rcx, r15
0x18007329f  jz      short loc_18007324F
0x1800732a1  test    byte ptr [rcx+1Ch], 80h
0x1800732a5  jz      short loc_18007324F
0x1800732a7  mov     edx, 0Fh
0x1800732ac  jmp     short loc_18007323C
0x1800732ae  lea     r8, [rbp+57h+var_CC]; int *
0x1800732b2  xor     edx, edx; int
0x1800732b4  mov     rcx, rdi; struct ScheduledToasts::_PERSISTEDTOAST *
0x1800732b7  call    ?TimerIsExpired@ScheduledToasts@@CAJPEAU_PERSISTEDTOAST@1@HPEAH@Z; ScheduledToasts::TimerIsExpired(ScheduledToasts::_PERSISTEDTOAST *,int,int *)
0x1800732bc  mov     ebx, eax
0x1800732be  xor     eax, eax
0x1800732c0  test    ebx, ebx
0x1800732c2  cmovs   ebx, eax
0x1800732c5  mov     eax, [rbp+57h+var_CC]
0x1800732c8  cmp     dword ptr [rdi+34h], 0
0x1800732cc  jz      short loc_1800732D7
0x1800732ce  lea     rcx, [rdi+160h]
0x1800732d5  jmp     short loc_1800732D9
0x1800732d7  xor     ecx, ecx
0x1800732d9  test    eax, eax
0x1800732db  jz      short loc_180073316
0x1800732dd  movups  xmm0, xmmword ptr [rdi+4]
0x1800732e1  lea     rdx, [rbp+57h+var_B0]
0x1800732e5  movdqu  xmmword ptr [rbp+57h+var_B0.Data1], xmm0
0x1800732ea  call    cs:__imp_TbDeleteEvent
0x1800732f0  mov     rcx, [rsp+120h+var_D8]
0x1800732f5  add     rcx, r14
0x1800732f8  call    cs:__imp_BiPtDeleteEvent
0x1800732fe  lea     r15, WPP_GLOBAL_Control
0x180073305  inc     esi
0x180073307  cmp     esi, [rsp+120h+var_E0]
0x18007330b  jb      loc_1800731C8
0x180073311  jmp     loc_1800733C1
0x180073316  mov     rax, [rsp+120h+var_D8]
0x18007331b  lea     r9, [rbp+57h+var_B0]; struct _GUID
0x18007331f  movups  xmm1, xmmword ptr [rdi+4]
0x180073323  mov     rdx, [rdi+14h]; struct _WNF_STATE_NAME
0x180073327  lea     r8, [rbp+57h+var_A0]; struct _GUID
0x18007332b  mov     [rsp+120h+var_F8], rcx; unsigned __int16 *
0x180073330  mov     rcx, r13; this
0x180073333  movups  xmm0, xmmword ptr [r14+rax]
0x180073338  mov     [rsp+120h+var_100], r15; unsigned __int16 *
0x18007333d  movdqu  xmmword ptr [rbp+57h+var_A0.Data1], xmm1
0x180073342  movdqu  xmmword ptr [rbp+57h+var_B0.Data1], xmm0
0x180073347  call    ?SubscribeAndAddToList@ScheduledToasts@@AEAAJU_WNF_STATE_NAME@@U_GUID@@1PEBGPEAG@Z; ScheduledToasts::SubscribeAndAddToList(_WNF_STATE_NAME,_GUID,_GUID,ushort const *,ushort *)
0x18007334c  mov     ebx, eax
0x18007334e  test    eax, eax
0x180073350  jns     short loc_1800732FE
0x180073352  mov     rcx, cs:WPP_GLOBAL_Control
0x180073359  lea     r15, WPP_GLOBAL_Control
0x180073360  cmp     rcx, r15
0x180073363  jz      loc_18007324F
0x180073369  test    byte ptr [rcx+1Ch], 80h
0x18007336d  jz      loc_18007324F
0x180073373  mov     edx, 11h
0x180073378  jmp     loc_18007323C
0x18007337d  test    cs:Microsoft_Windows_PushNotifications_PlatformEnableBits, 20h
0x180073384  mov     ebx, 803E0105h
0x180073389  jz      short loc_1800733F3
0x18007338b  lea     rax, word_180124798
0x180073392  mov     [rsp+120h+var_F0], rax
0x180073397  mov     dword ptr [rsp+120h+var_F8], 803E0105h
0x18007339f  mov     dword ptr [rsp+120h+var_100], 65h ; 'e'
0x1800733a7  lea     r9, aScheduledtoast; "ScheduledToasts::Initialize"
0x1800733ae  lea     r8, aOnecoreuapBase_72; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800733b5  lea     rdx, WPNCORE_EVENT_DEBUG_INIT
0x1800733bc  call    McTemplateU0zzdqz_EventWriteTransfer
0x1800733c1  mov     rcx, [rsp+120h+var_D8]
0x1800733c6  test    rcx, rcx
0x1800733c9  jz      short loc_1800733DA
0x1800733cb  call    cs:__imp_BiPtFreeMemory
0x1800733d1  mov     [rsp+120h+var_D8], 0
0x1800733da  test    rdi, rdi
0x1800733dd  jz      short loc_1800733F3
0x1800733df  call    cs:__imp_GetProcessHeap
0x1800733e5  mov     r8, rdi; lpMem
0x1800733e8  xor     edx, edx; dwFlags
0x1800733ea  mov     rcx, rax; hHeap
0x1800733ed  call    cs:__imp_HeapFree
0x1800733f3  mov     eax, ebx
0x1800733f5  mov     rcx, [rbp+57h+var_40]
0x1800733f9  xor     rcx, rsp; StackCookie
0x1800733fc  call    __security_check_cookie
0x180073401  mov     rbx, [rsp+120h+arg_10]
0x180073409  add     rsp, 0F0h
0x180073410  pop     r15
0x180073412  pop     r14
0x180073414  pop     r13
0x180073416  pop     r12
0x180073418  pop     rdi
0x180073419  pop     rsi
0x18007341a  pop     rbp
0x18007341b  retn
```
