# ShieldProvider::DataProtectionShield::RuntimeClassInitialize(void)

- ea: `0x18007a894`
- end: `0x18007ab30`
- name: `?RuntimeClassInitialize@DataProtectionShield@ShieldProvider@@QEAAJXZ`
- size: `668`
- prototype: `__int64 __fastcall(ShieldProvider::DataProtectionShield *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180076544`

## callees

- `0x18000d7fc`
- `0x180010ff0`
- `0x180078600`
- `0x18007a894`
- `0x1800d5be4`
- `0x1800da58c`
- `0x1800da824`
- `0x1800de318`
- `0x1800e1a1c`
- `0x1800e1a88`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18007a8fc`
- `KERNEL32!CloseHandle` at `0x18007aa33`
- `KERNEL32!CloseHandle` at `0x18007a8fc`
- `KERNEL32!CloseHandle` at `0x18007aa33`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007a994`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007a9b3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007aa17`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007ab18`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007a994`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007a9b3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007aa17`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007ab18`

## pseudocode

```c
__int64 __fastcall ShieldProvider::DataProtectionShield::RuntimeClassInitialize(
        ShieldProvider::DataProtectionShield *this)
{
  unsigned int Event; // ebx
  int v3; // r9d
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  void *v7; // rcx
  struct SC_HANDLE__ **v8; // rdx
  unsigned int v9; // r8d
  const unsigned __int16 *v10; // r9
  int v11; // eax
  SC_HANDLE v12; // rbx
  SC_HANDLE v13; // rcx
  void **v14; // rdx
  int Thread; // esi
  struct _SECURITY_ATTRIBUTES *v16; // r8
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  void *v19; // rcx
  int *v20; // rdx
  int IsWindowsLockdownMode; // eax
  int v22; // ecx
  unsigned int (*v23)(void *); // [rsp+20h] [rbp-28h]
  unsigned int (*v24)(void *); // [rsp+20h] [rbp-28h]
  unsigned int v25; // [rsp+20h] [rbp-28h]
  const struct _SECURITY_ATTRIBUTES *v26; // [rsp+28h] [rbp-20h]
  void *v27; // [rsp+28h] [rbp-20h]
  unsigned int v28; // [rsp+30h] [rbp-18h]
  unsigned int *v29; // [rsp+38h] [rbp-10h]
  int v30; // [rsp+50h] [rbp+8h] BYREF
  SC_HANDLE hSCObject; // [rsp+58h] [rbp+10h] BYREF

  Event = CommonUtil::CMpCriticalSection::Initialize((ShieldProvider::DataProtectionShield *)((char *)this + 56));
  if ( (Event & 0x80000000) != 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return Event;
    v5 = 20;
LABEL_5:
    WPP_SF_d(v4[2], v5, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids, Event);
    return Event;
  }
  v7 = (void *)*((_QWORD *)this + 19);
  if ( v7 )
  {
    CloseHandle(v7);
    *((_QWORD *)this + 19) = 0;
  }
  Event = CommonUtil::UtilCreateEvent(
            (ShieldProvider::DataProtectionShield *)((char *)this + 152),
            0,
            0,
            v3,
            (const unsigned __int16 *)v23,
            v26);
  if ( (Event & 0x80000000) != 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return Event;
    v5 = 21;
    goto LABEL_5;
  }
  hSCObject = 0;
  v11 = CommonUtil::HrOpenSCManager((CommonUtil *)&hSCObject, v8, v9, v10, (const unsigned __int16 *)v24);
  Event = v11;
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids,
        (unsigned int)v11);
    if ( hSCObject )
      CloseServiceHandle(hSCObject);
    return Event;
  }
  v12 = hSCObject;
  v13 = (SC_HANDLE)*((_QWORD *)this + 17);
  if ( v13 )
  {
    CloseServiceHandle(v13);
    *((_QWORD *)this + 17) = 0;
  }
  Thread = CommonUtil::HrOpenService(
             (ShieldProvider::DataProtectionShield *)((char *)this + 136),
             (struct SC_HANDLE__ **)v12,
             (struct SC_HANDLE__ *)&stru_1800F5328,
             (const unsigned __int16 *)4,
             v25);
  if ( Thread < 0 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_26;
    v18 = 23;
LABEL_25:
    WPP_SF_d(v17[2], v18, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids, (unsigned int)Thread);
LABEL_26:
    if ( v12 )
      CloseServiceHandle(v12);
    return (unsigned int)Thread;
  }
  v19 = (void *)*((_QWORD *)this + 18);
  if ( v19 )
  {
    CloseHandle(v19);
    *((_QWORD *)this + 18) = 0;
  }
  Thread = CommonUtil::UtilCreateThread(
             (ShieldProvider::DataProtectionShield *)((char *)this + 144),
             v14,
             v16,
             (unsigned int)ShieldProvider::DataProtectionShield::WorkerThread,
             (unsigned int (*)(void *))this,
             v27,
             v28,
             v29);
  if ( Thread < 0 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_26;
    v18 = 24;
    goto LABEL_25;
  }
  v30 = 0;
  IsWindowsLockdownMode = ShieldProvider::MpIsWindowsLockdownMode((ShieldProvider *)&v30, v20);
  if ( IsWindowsLockdownMode < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids,
        (unsigned int)IsWindowsLockdownMode);
  }
  else
  {
    v22 = v30;
    *((_BYTE *)this + 160) = v30 != 0;
    if ( v22 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids);
  }
  ShieldProvider::IsDefenderDataProtectionEnabled((char *)this + 162);
  if ( v12 )
    CloseServiceHandle(v12);
  return 0;
}

```

## disassembly

```asm
0x18007a894  mov     [rsp+arg_10], rbx
0x18007a899  mov     [rsp+arg_18], rsi
0x18007a89e  push    rdi
0x18007a89f  sub     rsp, 40h
0x18007a8a3  mov     rdi, rcx
0x18007a8a6  add     rcx, 38h ; '8'; this
0x18007a8aa  call    ?Initialize@CMpCriticalSection@CommonUtil@@QEAAJXZ; CommonUtil::CMpCriticalSection::Initialize(void)
0x18007a8af  mov     ebx, eax
0x18007a8b1  test    eax, eax
0x18007a8b3  jns     short loc_18007A8ED
0x18007a8b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a8bc  lea     rdx, WPP_GLOBAL_Control
0x18007a8c3  cmp     rcx, rdx
0x18007a8c6  jz      short loc_18007A8E6
0x18007a8c8  test    byte ptr [rcx+1Ch], 1
0x18007a8cc  jz      short loc_18007A8E6
0x18007a8ce  mov     edx, 14h
0x18007a8d3  mov     rcx, [rcx+10h]
0x18007a8d7  lea     r8, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids
0x18007a8de  mov     r9d, ebx
0x18007a8e1  call    WPP_SF_d
0x18007a8e6  mov     eax, ebx
0x18007a8e8  jmp     loc_18007AB20
0x18007a8ed  lea     rbx, [rdi+98h]
0x18007a8f4  mov     rcx, [rbx]; hObject
0x18007a8f7  test    rcx, rcx
0x18007a8fa  jz      short loc_18007A909
0x18007a8fc  call    cs:__imp_CloseHandle
0x18007a902  mov     qword ptr [rbx], 0
0x18007a909  xor     r8d, r8d; int
0x18007a90c  xor     edx, edx; void **
0x18007a90e  mov     rcx, rbx; this
0x18007a911  call    ?UtilCreateEvent@CommonUtil@@YAJPEAPEAXHHPEBGPEBU_SECURITY_ATTRIBUTES@@@Z; CommonUtil::UtilCreateEvent(void * *,int,int,ushort const *,_SECURITY_ATTRIBUTES const *)
0x18007a916  mov     ebx, eax
0x18007a918  test    eax, eax
0x18007a91a  jns     short loc_18007A93C
0x18007a91c  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a923  lea     rdx, WPP_GLOBAL_Control
0x18007a92a  cmp     rcx, rdx
0x18007a92d  jz      short loc_18007A8E6
0x18007a92f  test    byte ptr [rcx+1Ch], 1
0x18007a933  jz      short loc_18007A8E6
0x18007a935  mov     edx, 15h
0x18007a93a  jmp     short loc_18007A8D3
0x18007a93c  lea     rcx, [rsp+48h+hSCObject]; this
0x18007a941  mov     [rsp+48h+hSCObject], 0
0x18007a94a  call    ?HrOpenSCManager@CommonUtil@@YAJPEAPEAUSC_HANDLE__@@KPEBG1@Z; CommonUtil::HrOpenSCManager(SC_HANDLE__ * *,ulong,ushort const *,ushort const *)
0x18007a94f  mov     ebx, eax
0x18007a951  test    eax, eax
0x18007a953  jns     short loc_18007A99F
0x18007a955  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a95c  lea     rdx, WPP_GLOBAL_Control
0x18007a963  cmp     rcx, rdx
0x18007a966  jz      short loc_18007A986
0x18007a968  test    byte ptr [rcx+1Ch], 1
0x18007a96c  jz      short loc_18007A986
0x18007a96e  mov     rcx, [rcx+10h]
0x18007a972  lea     r8, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids
0x18007a979  mov     edx, 16h
0x18007a97e  mov     r9d, eax
0x18007a981  call    WPP_SF_d
0x18007a986  mov     rcx, [rsp+48h+hSCObject]; hSCObject
0x18007a98b  test    rcx, rcx
0x18007a98e  jz      loc_18007A8E6
0x18007a994  call    cs:__imp_CloseServiceHandle
0x18007a99a  jmp     loc_18007A8E6
0x18007a99f  mov     rbx, [rsp+48h+hSCObject]
0x18007a9a4  lea     rsi, [rdi+88h]
0x18007a9ab  mov     rcx, [rsi]; hSCObject
0x18007a9ae  test    rcx, rcx
0x18007a9b1  jz      short loc_18007A9C0
0x18007a9b3  call    cs:__imp_CloseServiceHandle
0x18007a9b9  mov     qword ptr [rsi], 0
0x18007a9c0  mov     r9d, 4; unsigned __int16 *
0x18007a9c6  lea     r8, stru_1800F5328; struct SC_HANDLE__ *
0x18007a9cd  mov     rdx, rbx; struct SC_HANDLE__ **
0x18007a9d0  mov     rcx, rsi; this
0x18007a9d3  call    ?HrOpenService@CommonUtil@@YAJPEAPEAUSC_HANDLE__@@PEAU2@PEBGK@Z; CommonUtil::HrOpenService(SC_HANDLE__ * *,SC_HANDLE__ *,ushort const *,ulong)
0x18007a9d8  mov     esi, eax
0x18007a9da  test    eax, eax
0x18007a9dc  jns     short loc_18007AA24
0x18007a9de  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a9e5  lea     rdx, WPP_GLOBAL_Control
0x18007a9ec  cmp     rcx, rdx
0x18007a9ef  jz      short loc_18007AA0F
0x18007a9f1  test    byte ptr [rcx+1Ch], 1
0x18007a9f5  jz      short loc_18007AA0F
0x18007a9f7  mov     edx, 17h
0x18007a9fc  mov     rcx, [rcx+10h]
0x18007aa00  lea     r8, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids
0x18007aa07  mov     r9d, esi
0x18007aa0a  call    WPP_SF_d
0x18007aa0f  test    rbx, rbx
0x18007aa12  jz      short loc_18007AA1D
0x18007aa14  mov     rcx, rbx; hSCObject
0x18007aa17  call    cs:__imp_CloseServiceHandle
0x18007aa1d  mov     eax, esi
0x18007aa1f  jmp     loc_18007AB20
0x18007aa24  lea     rsi, [rdi+90h]
0x18007aa2b  mov     rcx, [rsi]; hObject
0x18007aa2e  test    rcx, rcx
0x18007aa31  jz      short loc_18007AA40
0x18007aa33  call    cs:__imp_CloseHandle
0x18007aa39  mov     qword ptr [rsi], 0
0x18007aa40  lea     r9, ?WorkerThread@DataProtectionShield@ShieldProvider@@CAIPEAX@Z; unsigned int
0x18007aa47  mov     [rsp+48h+var_28], rdi; unsigned int (*)(void *)
0x18007aa4c  mov     rcx, rsi; this
0x18007aa4f  call    ?UtilCreateThread@CommonUtil@@YAJPEAPEAXPEAU_SECURITY_ATTRIBUTES@@KP6AIPEAX@Z2KPEAK@Z; CommonUtil::UtilCreateThread(void * *,_SECURITY_ATTRIBUTES *,ulong,uint (*)(void *),void *,ulong,ulong *)
0x18007aa54  mov     esi, eax
0x18007aa56  test    eax, eax
0x18007aa58  jns     short loc_18007AA7A
0x18007aa5a  mov     rcx, cs:WPP_GLOBAL_Control
0x18007aa61  lea     rdx, WPP_GLOBAL_Control
0x18007aa68  cmp     rcx, rdx
0x18007aa6b  jz      short loc_18007AA0F
0x18007aa6d  test    byte ptr [rcx+1Ch], 1
0x18007aa71  jz      short loc_18007AA0F
0x18007aa73  mov     edx, 18h
0x18007aa78  jmp     short loc_18007A9FC
0x18007aa7a  lea     rcx, [rsp+48h+arg_0]; this
0x18007aa7f  mov     [rsp+48h+arg_0], 0
0x18007aa87  call    ?MpIsWindowsLockdownMode@ShieldProvider@@YAJPEAH@Z; ShieldProvider::MpIsWindowsLockdownMode(int *)
0x18007aa8c  test    eax, eax
0x18007aa8e  js      short loc_18007AAD3
0x18007aa90  mov     ecx, [rsp+48h+arg_0]
0x18007aa94  test    ecx, ecx
0x18007aa96  setnz   al
0x18007aa99  mov     [rdi+0A0h], al
0x18007aa9f  test    ecx, ecx
0x18007aaa1  jz      short loc_18007AB04
0x18007aaa3  mov     rcx, cs:WPP_GLOBAL_Control
0x18007aaaa  lea     rdx, WPP_GLOBAL_Control
0x18007aab1  cmp     rcx, rdx
0x18007aab4  jz      short loc_18007AB04
0x18007aab6  test    byte ptr [rcx+1Ch], 4
0x18007aaba  jz      short loc_18007AB04
0x18007aabc  mov     rcx, [rcx+10h]
0x18007aac0  lea     r8, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids
0x18007aac7  mov     edx, 19h
0x18007aacc  call    WPP_SF_
0x18007aad1  jmp     short loc_18007AB04
0x18007aad3  mov     rcx, cs:WPP_GLOBAL_Control
0x18007aada  lea     rdx, WPP_GLOBAL_Control
0x18007aae1  cmp     rcx, rdx
0x18007aae4  jz      short loc_18007AB04
0x18007aae6  test    byte ptr [rcx+1Ch], 1
0x18007aaea  jz      short loc_18007AB04
0x18007aaec  mov     rcx, [rcx+10h]
0x18007aaf0  lea     r8, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids
0x18007aaf7  mov     edx, 1Ah
0x18007aafc  mov     r9d, eax
0x18007aaff  call    WPP_SF_d
0x18007ab04  lea     rcx, [rdi+0A2h]
0x18007ab0b  call    ShieldProvider__IsDefenderDataProtectionEnabled
0x18007ab10  test    rbx, rbx
0x18007ab13  jz      short loc_18007AB1E
0x18007ab15  mov     rcx, rbx; hSCObject
0x18007ab18  call    cs:__imp_CloseServiceHandle
0x18007ab1e  xor     eax, eax
0x18007ab20  mov     rbx, [rsp+48h+arg_10]
0x18007ab25  mov     rsi, [rsp+48h+arg_18]
0x18007ab2a  add     rsp, 40h
0x18007ab2e  pop     rdi
0x18007ab2f  retn
```
