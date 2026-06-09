# ShieldProvider::WscManager::Initialize(void)

- ea: `0x180044fd0`
- end: `0x1800451b0`
- name: `?Initialize@WscManager@ShieldProvider@@QEAAJXZ`
- size: `480`
- prototype: `__int64 __fastcall(ShieldProvider::WscManager *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180037cd4`

## callees

- `0x18000d7fc`
- `0x180044fd0`
- `0x1800451b8`
- `0x1800da58c`
- `0x1800da824`
- `0x1800e1a1c`
- `0x1800e1a88`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800450d0`
- `KERNEL32!CloseHandle` at `0x180045126`
- `KERNEL32!CloseHandle` at `0x1800450d0`
- `KERNEL32!CloseHandle` at `0x180045126`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180045035`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180045053`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800450b7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180045186`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180045198`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180045035`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180045053`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800450b7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180045186`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180045198`

## pseudocode

```c
__int64 __fastcall ShieldProvider::WscManager::Initialize(
        ShieldProvider::WscManager *this,
        struct SC_HANDLE__ **a2,
        unsigned int a3,
        const unsigned __int16 *a4)
{
  int v5; // eax
  unsigned int v6; // ebx
  SC_HANDLE v8; // rbx
  SC_HANDLE v9; // rcx
  int Event; // esi
  int v11; // r9d
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  void *v14; // rcx
  void **v15; // rdx
  struct _SECURITY_ATTRIBUTES *v16; // r8
  void *v17; // rcx
  int Thread; // eax
  unsigned int v19; // edi
  unsigned int (*v20)(void *); // [rsp+20h] [rbp-28h]
  unsigned int v21; // [rsp+20h] [rbp-28h]
  unsigned int (*v22)(void *); // [rsp+20h] [rbp-28h]
  const struct _SECURITY_ATTRIBUTES *v23; // [rsp+28h] [rbp-20h]
  void *v24; // [rsp+28h] [rbp-20h]
  unsigned int v25; // [rsp+30h] [rbp-18h]
  unsigned int *v26; // [rsp+38h] [rbp-10h]
  SC_HANDLE hSCObject; // [rsp+58h] [rbp+10h] BYREF

  hSCObject = 0;
  v5 = CommonUtil::HrOpenSCManager((CommonUtil *)&hSCObject, a2, a3, a4, (const unsigned __int16 *)v20);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_77b5160c59d63e5186f33de3a862ec2c_Traceguids,
        (unsigned int)v5);
    if ( hSCObject )
      CloseServiceHandle(hSCObject);
    return v6;
  }
  v8 = hSCObject;
  v9 = (SC_HANDLE)*((_QWORD *)this + 8);
  if ( v9 )
  {
    CloseServiceHandle(v9);
    *((_QWORD *)this + 8) = 0;
  }
  Event = CommonUtil::HrOpenService(
            (ShieldProvider::WscManager *)((char *)this + 64),
            (struct SC_HANDLE__ **)v8,
            (struct SC_HANDLE__ *)&stru_1800F5328,
            (const unsigned __int16 *)4,
            v21);
  if ( Event < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_15;
    v13 = 12;
LABEL_14:
    WPP_SF_d(v12[2], v13, WPP_77b5160c59d63e5186f33de3a862ec2c_Traceguids, (unsigned int)Event);
LABEL_15:
    if ( v8 )
      CloseServiceHandle(v8);
    return (unsigned int)Event;
  }
  v14 = (void *)*((_QWORD *)this + 12);
  if ( v14 )
  {
    CloseHandle(v14);
    *((_QWORD *)this + 12) = 0;
  }
  Event = CommonUtil::UtilCreateEvent(
            (ShieldProvider::WscManager *)((char *)this + 96),
            (void **)1,
            0,
            v11,
            (const unsigned __int16 *)v22,
            v23);
  if ( Event < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_15;
    v13 = 13;
    goto LABEL_14;
  }
  ShieldProvider::WscManager::OnWscNotification(this);
  v17 = (void *)*((_QWORD *)this + 7);
  if ( v17 )
  {
    CloseHandle(v17);
    *((_QWORD *)this + 7) = 0;
  }
  Thread = CommonUtil::UtilCreateThread(
             (ShieldProvider::WscManager *)((char *)this + 56),
             v15,
             v16,
             (unsigned int)ShieldProvider::WscManager::WorkerThreadFunc,
             (unsigned int (*)(void *))this,
             v24,
             v25,
             v26);
  v19 = Thread;
  if ( Thread >= 0 )
  {
    if ( v8 )
      CloseServiceHandle(v8);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        WPP_77b5160c59d63e5186f33de3a862ec2c_Traceguids,
        (unsigned int)Thread);
    if ( v8 )
      CloseServiceHandle(v8);
    return v19;
  }
}

```

## disassembly

```asm
0x180044fd0  mov     rax, rsp
0x180044fd3  mov     [rax+8], rbx
0x180044fd7  mov     [rax+18h], rsi
0x180044fdb  push    rdi
0x180044fdc  sub     rsp, 40h
0x180044fe0  mov     rdi, rcx
0x180044fe3  mov     qword ptr [rax+10h], 0
0x180044feb  lea     rcx, [rax+10h]; this
0x180044fef  call    ?HrOpenSCManager@CommonUtil@@YAJPEAPEAUSC_HANDLE__@@KPEBG1@Z; CommonUtil::HrOpenSCManager(SC_HANDLE__ * *,ulong,ushort const *,ushort const *)
0x180044ff4  mov     ebx, eax
0x180044ff6  test    eax, eax
0x180044ff8  jns     short loc_180045042
0x180044ffa  mov     rcx, cs:WPP_GLOBAL_Control
0x180045001  lea     rdx, WPP_GLOBAL_Control
0x180045008  cmp     rcx, rdx
0x18004500b  jz      short loc_18004502B
0x18004500d  test    byte ptr [rcx+1Ch], 1
0x180045011  jz      short loc_18004502B
0x180045013  mov     rcx, [rcx+10h]
0x180045017  lea     r8, WPP_77b5160c59d63e5186f33de3a862ec2c_Traceguids
0x18004501e  mov     edx, 0Bh
0x180045023  mov     r9d, eax
0x180045026  call    WPP_SF_d
0x18004502b  mov     rcx, [rsp+48h+hSCObject]; hSCObject
0x180045030  test    rcx, rcx
0x180045033  jz      short loc_18004503B
0x180045035  call    cs:__imp_CloseServiceHandle
0x18004503b  mov     eax, ebx
0x18004503d  jmp     loc_1800451A0
0x180045042  mov     rbx, [rsp+48h+hSCObject]
0x180045047  lea     rsi, [rdi+40h]
0x18004504b  mov     rcx, [rsi]; hSCObject
0x18004504e  test    rcx, rcx
0x180045051  jz      short loc_180045060
0x180045053  call    cs:__imp_CloseServiceHandle
0x180045059  mov     qword ptr [rsi], 0
0x180045060  mov     r9d, 4; unsigned __int16 *
0x180045066  lea     r8, stru_1800F5328; struct SC_HANDLE__ *
0x18004506d  mov     rdx, rbx; struct SC_HANDLE__ **
0x180045070  mov     rcx, rsi; this
0x180045073  call    ?HrOpenService@CommonUtil@@YAJPEAPEAUSC_HANDLE__@@PEAU2@PEBGK@Z; CommonUtil::HrOpenService(SC_HANDLE__ * *,SC_HANDLE__ *,ushort const *,ulong)
0x180045078  mov     esi, eax
0x18004507a  test    eax, eax
0x18004507c  jns     short loc_1800450C4
0x18004507e  mov     rcx, cs:WPP_GLOBAL_Control
0x180045085  lea     rdx, WPP_GLOBAL_Control
0x18004508c  cmp     rcx, rdx
0x18004508f  jz      short loc_1800450AF
0x180045091  test    byte ptr [rcx+1Ch], 1
0x180045095  jz      short loc_1800450AF
0x180045097  mov     edx, 0Ch
0x18004509c  mov     rcx, [rcx+10h]
0x1800450a0  lea     r8, WPP_77b5160c59d63e5186f33de3a862ec2c_Traceguids
0x1800450a7  mov     r9d, esi
0x1800450aa  call    WPP_SF_d
0x1800450af  test    rbx, rbx
0x1800450b2  jz      short loc_1800450BD
0x1800450b4  mov     rcx, rbx; hSCObject
0x1800450b7  call    cs:__imp_CloseServiceHandle
0x1800450bd  mov     eax, esi
0x1800450bf  jmp     loc_1800451A0
0x1800450c4  lea     rsi, [rdi+60h]
0x1800450c8  mov     rcx, [rsi]; hObject
0x1800450cb  test    rcx, rcx
0x1800450ce  jz      short loc_1800450DD
0x1800450d0  call    cs:__imp_CloseHandle
0x1800450d6  mov     qword ptr [rsi], 0
0x1800450dd  xor     r8d, r8d; int
0x1800450e0  mov     rcx, rsi; this
0x1800450e3  lea     edx, [r8+1]; void **
0x1800450e7  call    ?UtilCreateEvent@CommonUtil@@YAJPEAPEAXHHPEBGPEBU_SECURITY_ATTRIBUTES@@@Z; CommonUtil::UtilCreateEvent(void * *,int,int,ushort const *,_SECURITY_ATTRIBUTES const *)
0x1800450ec  mov     esi, eax
0x1800450ee  test    eax, eax
0x1800450f0  jns     short loc_180045112
0x1800450f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800450f9  lea     rdx, WPP_GLOBAL_Control
0x180045100  cmp     rcx, rdx
0x180045103  jz      short loc_1800450AF
0x180045105  test    byte ptr [rcx+1Ch], 1
0x180045109  jz      short loc_1800450AF
0x18004510b  mov     edx, 0Dh
0x180045110  jmp     short loc_18004509C
0x180045112  mov     rcx, rdi
0x180045115  call    ?OnWscNotification@WscManager@ShieldProvider@@AEAAJW4THREAT_PROTECTION_NOTIFICATION_STATE@@@Z; ShieldProvider::WscManager::OnWscNotification(THREAT_PROTECTION_NOTIFICATION_STATE)
0x18004511a  lea     rsi, [rdi+38h]
0x18004511e  mov     rcx, [rsi]; hObject
0x180045121  test    rcx, rcx
0x180045124  jz      short loc_180045133
0x180045126  call    cs:__imp_CloseHandle
0x18004512c  mov     qword ptr [rsi], 0
0x180045133  lea     r9, ?WorkerThreadFunc@WscManager@ShieldProvider@@CAIPEAX@Z; unsigned int
0x18004513a  mov     [rsp+48h+var_28], rdi; unsigned int (*)(void *)
0x18004513f  mov     rcx, rsi; this
0x180045142  call    ?UtilCreateThread@CommonUtil@@YAJPEAPEAXPEAU_SECURITY_ATTRIBUTES@@KP6AIPEAX@Z2KPEAK@Z; CommonUtil::UtilCreateThread(void * *,_SECURITY_ATTRIBUTES *,ulong,uint (*)(void *),void *,ulong,ulong *)
0x180045147  mov     edi, eax
0x180045149  test    eax, eax
0x18004514b  jns     short loc_180045190
0x18004514d  mov     rcx, cs:WPP_GLOBAL_Control
0x180045154  lea     rdx, WPP_GLOBAL_Control
0x18004515b  cmp     rcx, rdx
0x18004515e  jz      short loc_18004517E
0x180045160  test    byte ptr [rcx+1Ch], 1
0x180045164  jz      short loc_18004517E
0x180045166  mov     rcx, [rcx+10h]
0x18004516a  lea     r8, WPP_77b5160c59d63e5186f33de3a862ec2c_Traceguids
0x180045171  mov     edx, 0Eh
0x180045176  mov     r9d, eax
0x180045179  call    WPP_SF_d
0x18004517e  test    rbx, rbx
0x180045181  jz      short loc_18004518C
0x180045183  mov     rcx, rbx; hSCObject
0x180045186  call    cs:__imp_CloseServiceHandle
0x18004518c  mov     eax, edi
0x18004518e  jmp     short loc_1800451A0
0x180045190  test    rbx, rbx
0x180045193  jz      short loc_18004519E
0x180045195  mov     rcx, rbx; hSCObject
0x180045198  call    cs:__imp_CloseServiceHandle
0x18004519e  xor     eax, eax
0x1800451a0  mov     rbx, [rsp+48h+arg_0]
0x1800451a5  mov     rsi, [rsp+48h+arg_10]
0x1800451aa  add     rsp, 40h
0x1800451ae  pop     rdi
0x1800451af  retn
```
