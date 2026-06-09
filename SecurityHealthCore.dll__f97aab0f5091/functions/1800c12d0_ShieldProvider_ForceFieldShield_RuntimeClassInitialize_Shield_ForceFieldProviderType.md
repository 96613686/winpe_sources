# ShieldProvider::ForceFieldShield::RuntimeClassInitialize(Shield_ForceFieldProviderType)

- ea: `0x1800c12d0`
- end: `0x1800c156e`
- name: `?RuntimeClassInitialize@ForceFieldShield@ShieldProvider@@QEAAJW4Shield_ForceFieldProviderType@@@Z`
- size: `670`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800be220`

## callees

- `0x18000d7fc`
- `0x180010ff0`
- `0x1800c12d0`
- `0x1800d5be4`
- `0x1800da58c`
- `0x1800da824`
- `0x1800de318`
- `0x1800e1a1c`
- `0x1800e1a88`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800c1346`
- `KERNEL32!CloseHandle` at `0x1800c147d`
- `KERNEL32!CloseHandle` at `0x1800c1346`
- `KERNEL32!CloseHandle` at `0x1800c147d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800c13de`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800c13fd`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800c1461`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800c1556`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800c13de`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800c13fd`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800c1461`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800c1556`

## pseudocode

```c
__int64 __fastcall ShieldProvider::ForceFieldShield::RuntimeClassInitialize(__int64 a1, int a2)
{
  unsigned int Event; // ebx
  int v5; // r9d
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  void *v9; // rcx
  struct SC_HANDLE__ **v10; // rdx
  unsigned int v11; // r8d
  const unsigned __int16 *v12; // r9
  int v13; // eax
  SC_HANDLE v14; // rbx
  SC_HANDLE v15; // rcx
  void **v16; // rdx
  int Thread; // esi
  struct _SECURITY_ATTRIBUTES *v18; // r8
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  void *v21; // rcx
  int *v22; // rdx
  int IsWindowsLockdownMode; // eax
  int v24; // ecx
  unsigned int (*v25)(void *); // [rsp+20h] [rbp-28h]
  unsigned int (*v26)(void *); // [rsp+20h] [rbp-28h]
  unsigned int v27; // [rsp+20h] [rbp-28h]
  const struct _SECURITY_ATTRIBUTES *v28; // [rsp+28h] [rbp-20h]
  void *v29; // [rsp+28h] [rbp-20h]
  unsigned int v30; // [rsp+30h] [rbp-18h]
  unsigned int *v31; // [rsp+38h] [rbp-10h]
  int v32; // [rsp+50h] [rbp+8h] BYREF
  SC_HANDLE hSCObject; // [rsp+60h] [rbp+18h] BYREF

  Event = CommonUtil::CMpCriticalSection::Initialize((CommonUtil::CMpCriticalSection *)(a1 + 56));
  if ( (Event & 0x80000000) != 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return Event;
    v7 = 18;
LABEL_5:
    WPP_SF_d(v6[2], v7, WPP_3533d4a562073f930570ad4a944aa956_Traceguids, Event);
    return Event;
  }
  *(_DWORD *)(a1 + 164) = a2;
  *(_DWORD *)(a1 + 168) = a2;
  v9 = *(void **)(a1 + 152);
  if ( v9 )
  {
    CloseHandle(v9);
    *(_QWORD *)(a1 + 152) = 0;
  }
  Event = CommonUtil::UtilCreateEvent((CommonUtil *)(a1 + 152), 0, 0, v5, (const unsigned __int16 *)v25, v28);
  if ( (Event & 0x80000000) != 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return Event;
    v7 = 19;
    goto LABEL_5;
  }
  hSCObject = 0;
  v13 = CommonUtil::HrOpenSCManager((CommonUtil *)&hSCObject, v10, v11, v12, (const unsigned __int16 *)v26);
  Event = v13;
  if ( v13 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        WPP_3533d4a562073f930570ad4a944aa956_Traceguids,
        (unsigned int)v13);
    if ( hSCObject )
      CloseServiceHandle(hSCObject);
    return Event;
  }
  v14 = hSCObject;
  v15 = *(SC_HANDLE *)(a1 + 136);
  if ( v15 )
  {
    CloseServiceHandle(v15);
    *(_QWORD *)(a1 + 136) = 0;
  }
  Thread = CommonUtil::HrOpenService(
             (CommonUtil *)(a1 + 136),
             (struct SC_HANDLE__ **)v14,
             (struct SC_HANDLE__ *)&stru_1800F5328,
             (const unsigned __int16 *)4,
             v27);
  if ( Thread < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_26;
    v20 = 21;
LABEL_25:
    WPP_SF_d(v19[2], v20, WPP_3533d4a562073f930570ad4a944aa956_Traceguids, (unsigned int)Thread);
LABEL_26:
    if ( v14 )
      CloseServiceHandle(v14);
    return (unsigned int)Thread;
  }
  v21 = *(void **)(a1 + 144);
  if ( v21 )
  {
    CloseHandle(v21);
    *(_QWORD *)(a1 + 144) = 0;
  }
  Thread = CommonUtil::UtilCreateThread(
             (CommonUtil *)(a1 + 144),
             v16,
             v18,
             (unsigned int)ShieldProvider::ForceFieldShield::WorkerThread,
             (unsigned int (*)(void *))a1,
             v29,
             v30,
             v31);
  if ( Thread < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_26;
    v20 = 22;
    goto LABEL_25;
  }
  v32 = 0;
  IsWindowsLockdownMode = ShieldProvider::MpIsWindowsLockdownMode((ShieldProvider *)&v32, v22);
  if ( IsWindowsLockdownMode < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        WPP_3533d4a562073f930570ad4a944aa956_Traceguids,
        (unsigned int)IsWindowsLockdownMode);
  }
  else
  {
    v24 = v32;
    *(_BYTE *)(a1 + 160) = v32 != 0;
    if ( v24 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_3533d4a562073f930570ad4a944aa956_Traceguids);
  }
  if ( v14 )
    CloseServiceHandle(v14);
  return 0;
}

```

## disassembly

```asm
0x1800c12d0  mov     [rsp+arg_8], rbx
0x1800c12d5  mov     [rsp+arg_18], rsi
0x1800c12da  push    rdi
0x1800c12db  sub     rsp, 40h
0x1800c12df  mov     rdi, rcx
0x1800c12e2  mov     esi, edx
0x1800c12e4  add     rcx, 38h ; '8'; this
0x1800c12e8  call    ?Initialize@CMpCriticalSection@CommonUtil@@QEAAJXZ; CommonUtil::CMpCriticalSection::Initialize(void)
0x1800c12ed  mov     ebx, eax
0x1800c12ef  test    eax, eax
0x1800c12f1  jns     short loc_1800C132B
0x1800c12f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c12fa  lea     rdx, WPP_GLOBAL_Control
0x1800c1301  cmp     rcx, rdx
0x1800c1304  jz      short loc_1800C1324
0x1800c1306  test    byte ptr [rcx+1Ch], 1
0x1800c130a  jz      short loc_1800C1324
0x1800c130c  mov     edx, 12h
0x1800c1311  mov     rcx, [rcx+10h]
0x1800c1315  lea     r8, WPP_3533d4a562073f930570ad4a944aa956_Traceguids
0x1800c131c  mov     r9d, ebx
0x1800c131f  call    WPP_SF_d
0x1800c1324  mov     eax, ebx
0x1800c1326  jmp     loc_1800C155E
0x1800c132b  lea     rbx, [rdi+98h]
0x1800c1332  mov     [rdi+0A4h], esi
0x1800c1338  mov     [rdi+0A8h], esi
0x1800c133e  mov     rcx, [rbx]; hObject
0x1800c1341  test    rcx, rcx
0x1800c1344  jz      short loc_1800C1353
0x1800c1346  call    cs:__imp_CloseHandle
0x1800c134c  mov     qword ptr [rbx], 0
0x1800c1353  xor     r8d, r8d; int
0x1800c1356  xor     edx, edx; void **
0x1800c1358  mov     rcx, rbx; this
0x1800c135b  call    ?UtilCreateEvent@CommonUtil@@YAJPEAPEAXHHPEBGPEBU_SECURITY_ATTRIBUTES@@@Z; CommonUtil::UtilCreateEvent(void * *,int,int,ushort const *,_SECURITY_ATTRIBUTES const *)
0x1800c1360  mov     ebx, eax
0x1800c1362  test    eax, eax
0x1800c1364  jns     short loc_1800C1386
0x1800c1366  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c136d  lea     rdx, WPP_GLOBAL_Control
0x1800c1374  cmp     rcx, rdx
0x1800c1377  jz      short loc_1800C1324
0x1800c1379  test    byte ptr [rcx+1Ch], 1
0x1800c137d  jz      short loc_1800C1324
0x1800c137f  mov     edx, 13h
0x1800c1384  jmp     short loc_1800C1311
0x1800c1386  lea     rcx, [rsp+48h+hSCObject]; this
0x1800c138b  mov     [rsp+48h+hSCObject], 0
0x1800c1394  call    ?HrOpenSCManager@CommonUtil@@YAJPEAPEAUSC_HANDLE__@@KPEBG1@Z; CommonUtil::HrOpenSCManager(SC_HANDLE__ * *,ulong,ushort const *,ushort const *)
0x1800c1399  mov     ebx, eax
0x1800c139b  test    eax, eax
0x1800c139d  jns     short loc_1800C13E9
0x1800c139f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c13a6  lea     rdx, WPP_GLOBAL_Control
0x1800c13ad  cmp     rcx, rdx
0x1800c13b0  jz      short loc_1800C13D0
0x1800c13b2  test    byte ptr [rcx+1Ch], 1
0x1800c13b6  jz      short loc_1800C13D0
0x1800c13b8  mov     rcx, [rcx+10h]
0x1800c13bc  lea     r8, WPP_3533d4a562073f930570ad4a944aa956_Traceguids
0x1800c13c3  mov     edx, 14h
0x1800c13c8  mov     r9d, eax
0x1800c13cb  call    WPP_SF_d
0x1800c13d0  mov     rcx, [rsp+48h+hSCObject]; hSCObject
0x1800c13d5  test    rcx, rcx
0x1800c13d8  jz      loc_1800C1324
0x1800c13de  call    cs:__imp_CloseServiceHandle
0x1800c13e4  jmp     loc_1800C1324
0x1800c13e9  mov     rbx, [rsp+48h+hSCObject]
0x1800c13ee  lea     rsi, [rdi+88h]
0x1800c13f5  mov     rcx, [rsi]; hSCObject
0x1800c13f8  test    rcx, rcx
0x1800c13fb  jz      short loc_1800C140A
0x1800c13fd  call    cs:__imp_CloseServiceHandle
0x1800c1403  mov     qword ptr [rsi], 0
0x1800c140a  mov     r9d, 4; unsigned __int16 *
0x1800c1410  lea     r8, stru_1800F5328; struct SC_HANDLE__ *
0x1800c1417  mov     rdx, rbx; struct SC_HANDLE__ **
0x1800c141a  mov     rcx, rsi; this
0x1800c141d  call    ?HrOpenService@CommonUtil@@YAJPEAPEAUSC_HANDLE__@@PEAU2@PEBGK@Z; CommonUtil::HrOpenService(SC_HANDLE__ * *,SC_HANDLE__ *,ushort const *,ulong)
0x1800c1422  mov     esi, eax
0x1800c1424  test    eax, eax
0x1800c1426  jns     short loc_1800C146E
0x1800c1428  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c142f  lea     rdx, WPP_GLOBAL_Control
0x1800c1436  cmp     rcx, rdx
0x1800c1439  jz      short loc_1800C1459
0x1800c143b  test    byte ptr [rcx+1Ch], 1
0x1800c143f  jz      short loc_1800C1459
0x1800c1441  mov     edx, 15h
0x1800c1446  mov     rcx, [rcx+10h]
0x1800c144a  lea     r8, WPP_3533d4a562073f930570ad4a944aa956_Traceguids
0x1800c1451  mov     r9d, esi
0x1800c1454  call    WPP_SF_d
0x1800c1459  test    rbx, rbx
0x1800c145c  jz      short loc_1800C1467
0x1800c145e  mov     rcx, rbx; hSCObject
0x1800c1461  call    cs:__imp_CloseServiceHandle
0x1800c1467  mov     eax, esi
0x1800c1469  jmp     loc_1800C155E
0x1800c146e  lea     rsi, [rdi+90h]
0x1800c1475  mov     rcx, [rsi]; hObject
0x1800c1478  test    rcx, rcx
0x1800c147b  jz      short loc_1800C148A
0x1800c147d  call    cs:__imp_CloseHandle
0x1800c1483  mov     qword ptr [rsi], 0
0x1800c148a  lea     r9, ?WorkerThread@ForceFieldShield@ShieldProvider@@CAIPEAX@Z; unsigned int
0x1800c1491  mov     [rsp+48h+var_28], rdi; unsigned int (*)(void *)
0x1800c1496  mov     rcx, rsi; this
0x1800c1499  call    ?UtilCreateThread@CommonUtil@@YAJPEAPEAXPEAU_SECURITY_ATTRIBUTES@@KP6AIPEAX@Z2KPEAK@Z; CommonUtil::UtilCreateThread(void * *,_SECURITY_ATTRIBUTES *,ulong,uint (*)(void *),void *,ulong,ulong *)
0x1800c149e  mov     esi, eax
0x1800c14a0  test    eax, eax
0x1800c14a2  jns     short loc_1800C14C4
0x1800c14a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c14ab  lea     rdx, WPP_GLOBAL_Control
0x1800c14b2  cmp     rcx, rdx
0x1800c14b5  jz      short loc_1800C1459
0x1800c14b7  test    byte ptr [rcx+1Ch], 1
0x1800c14bb  jz      short loc_1800C1459
0x1800c14bd  mov     edx, 16h
0x1800c14c2  jmp     short loc_1800C1446
0x1800c14c4  lea     rcx, [rsp+48h+arg_0]; this
0x1800c14c9  mov     [rsp+48h+arg_0], 0
0x1800c14d1  call    ?MpIsWindowsLockdownMode@ShieldProvider@@YAJPEAH@Z; ShieldProvider::MpIsWindowsLockdownMode(int *)
0x1800c14d6  test    eax, eax
0x1800c14d8  js      short loc_1800C151D
0x1800c14da  mov     ecx, [rsp+48h+arg_0]
0x1800c14de  test    ecx, ecx
0x1800c14e0  setnz   al
0x1800c14e3  mov     [rdi+0A0h], al
0x1800c14e9  test    ecx, ecx
0x1800c14eb  jz      short loc_1800C154E
0x1800c14ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c14f4  lea     rdx, WPP_GLOBAL_Control
0x1800c14fb  cmp     rcx, rdx
0x1800c14fe  jz      short loc_1800C154E
0x1800c1500  test    byte ptr [rcx+1Ch], 4
0x1800c1504  jz      short loc_1800C154E
0x1800c1506  mov     rcx, [rcx+10h]
0x1800c150a  lea     r8, WPP_3533d4a562073f930570ad4a944aa956_Traceguids
0x1800c1511  mov     edx, 17h
0x1800c1516  call    WPP_SF_
0x1800c151b  jmp     short loc_1800C154E
0x1800c151d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c1524  lea     rdx, WPP_GLOBAL_Control
0x1800c152b  cmp     rcx, rdx
0x1800c152e  jz      short loc_1800C154E
0x1800c1530  test    byte ptr [rcx+1Ch], 1
0x1800c1534  jz      short loc_1800C154E
0x1800c1536  mov     rcx, [rcx+10h]
0x1800c153a  lea     r8, WPP_3533d4a562073f930570ad4a944aa956_Traceguids
0x1800c1541  mov     edx, 18h
0x1800c1546  mov     r9d, eax
0x1800c1549  call    WPP_SF_d
0x1800c154e  test    rbx, rbx
0x1800c1551  jz      short loc_1800C155C
0x1800c1553  mov     rcx, rbx; hSCObject
0x1800c1556  call    cs:__imp_CloseServiceHandle
0x1800c155c  xor     eax, eax
0x1800c155e  mov     rbx, [rsp+48h+arg_8]
0x1800c1563  mov     rsi, [rsp+48h+arg_18]
0x1800c1568  add     rsp, 40h
0x1800c156c  pop     rdi
0x1800c156d  retn
```
