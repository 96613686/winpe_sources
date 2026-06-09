# CServicesManager::UpdateBackgroundDeviceIndicatedByDriver(ulong *,uchar *,uchar (*)[6],_BSS_ENTRY_WFD_SERVICES_INFO *,_BSS_ENTRY_WFD_SERVICES_INFO *)

- ea: `0x140097ebc`
- end: `0x1400980f2`
- name: `?UpdateBackgroundDeviceIndicatedByDriver@CServicesManager@@QEAAHPEAKPEAEPEAY05EPEAU_BSS_ENTRY_WFD_SERVICES_INFO@@3@Z`
- size: `566`
- prototype: `__int64 __usercall@<rax>(CServicesManager *__hidden this@<rcx>, unsigned int *@<rdx>, unsigned __int8 *@<r8>, unsigned __int8 (*)[6]@<r9>, struct _BSS_ENTRY_WFD_SERVICES_INFO *, struct _BSS_ENTRY_WFD_SERVICES_INFO *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x140097e70`

## callees

- `0x14000c778`
- `0x14000d054`
- `0x14002ed50`
- `0x140030fb8`
- `0x1400940c0`
- `0x140094290`
- `0x140094344`
- `0x140097ebc`
- `0x140099160`

## pseudocode

```c
__int64 __fastcall CServicesManager::UpdateBackgroundDeviceIndicatedByDriver(
        CServicesManager *this,
        unsigned int *a2,
        char *a3,
        unsigned __int8 (*a4)[6],
        struct _BSS_ENTRY_WFD_SERVICES_INFO *a5,
        struct _BSS_ENTRY_WFD_SERVICES_INFO *a6)
{
  int v6; // ebp
  unsigned int v7; // r13d
  char v8; // si
  unsigned int v9; // r14d
  int v13; // edx
  int v14; // r9d
  unsigned __int64 CurrentTime; // r12
  int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // r13d
  int v20; // [rsp+20h] [rbp-98h]
  __int64 v21; // [rsp+28h] [rbp-90h]
  unsigned int v22; // [rsp+C0h] [rbp+8h]

  v6 = *a2;
  v7 = 0;
  v8 = *a3;
  v9 = 0;
  v22 = 0;
  CurrentTime = CSystem::get_CurrentTime();
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v13 = 0;
  }
  else if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || (v13 = 0, LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v13) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v13,
      1,
      245,
      (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids);
    v13 = 0;
  }
  v16 = *((unsigned __int8 *)this + 52);
  if ( (_BYTE)v16 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      WPP_RECORDER_SF__MAC_DddDdddddd(
        WPP_GLOBAL_Control->DeviceExtension,
        0,
        v16,
        v14,
        v20,
        (__int64)a4,
        v16,
        v6,
        *((_DWORD *)this + 30),
        v8,
        *((_DWORD *)this + 24),
        *((_DWORD *)this + 25),
        *((_DWORD *)this + 26),
        *((_DWORD *)this + 27),
        *((_DWORD *)this + 28),
        *((_DWORD *)this + 29));
      v13 = 0;
    }
    v17 = *((_DWORD *)this + 30);
    if ( v6 == v17 )
    {
      if ( !v8 )
      {
        if ( !*((_BYTE *)this + 53) && !*((_BYTE *)this + 132) )
        {
          v9 = CServicesManager::CheckForExpiredDevicesAndServices(this, CurrentTime);
LABEL_20:
          v13 = 0;
          goto LABEL_21;
        }
        goto LABEL_21;
      }
    }
    else
    {
      ++*((_DWORD *)this + 24);
      ++*((_DWORD *)this + 25);
      *a2 = v17;
      if ( !v8 )
        goto LABEL_18;
    }
    ++*((_DWORD *)this + 27);
    *a3 = 0;
LABEL_18:
    if ( !*((_BYTE *)this + 53) )
    {
      v22 = CServicesManager::CheckForNewDevices(this, CurrentTime, a4);
      v18 = CServicesManager::CheckForNewServices(this, CurrentTime, a5);
      v7 = CServicesManager::CheckForNewServices(this, CurrentTime, a6) + v18;
      goto LABEL_20;
    }
LABEL_21:
    if ( v6 != *((_DWORD *)this + 30) || v8 || v9 )
    {
      CServicesManager::CheckStartDeviceUpdateNotificationTimer(this);
      v13 = 0;
    }
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v21) = v22 + v9 + v7;
    LOBYTE(v13) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v13,
      1,
      247,
      (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids,
      v21);
  }
  return 0;
}

```

## disassembly

```asm
0x140097ebc  mov     [rsp+arg_8], rbx
0x140097ec1  mov     [rsp+arg_18], r9
0x140097ec6  push    rbp
0x140097ec7  push    rsi
0x140097ec8  push    rdi
0x140097ec9  push    r12
0x140097ecb  push    r13
0x140097ecd  push    r14
0x140097ecf  push    r15
0x140097ed1  sub     rsp, 80h
0x140097ed8  mov     ebp, [rdx]
0x140097eda  xor     r13d, r13d
0x140097edd  movzx   esi, byte ptr [r8]
0x140097ee1  xor     r14d, r14d
0x140097ee4  mov     r15, r8
0x140097ee7  mov     [rsp+0B8h+arg_0], 0
0x140097ef2  mov     rbx, rdx
0x140097ef5  mov     rdi, rcx
0x140097ef8  call    ?get_CurrentTime@CSystem@@SA_KXZ; CSystem::get_CurrentTime(void)
0x140097efd  mov     r12, rax
0x140097f00  lea     rcx, WPP_RECORDER_INITIALIZED
0x140097f07  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140097f0e  lea     rax, WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids
0x140097f15  jz      loc_140097FFF
0x140097f1b  mov     rcx, cs:WPP_GLOBAL_Control
0x140097f22  cmp     byte ptr [rcx+29h], 5
0x140097f26  jnb     short loc_140097F30
0x140097f28  xor     edx, edx
0x140097f2a  cmp     [rcx+48h], dx
0x140097f2e  jz      short loc_140097F4E
0x140097f30  mov     rcx, [rcx+40h]
0x140097f34  mov     r9d, 0F5h
0x140097f3a  mov     r8d, 1
0x140097f40  mov     [rsp+0B8h+var_98], rax
0x140097f45  mov     dl, 5
0x140097f47  call    WPP_RECORDER_SF_
0x140097f4c  xor     edx, edx
0x140097f4e  lea     rcx, WPP_RECORDER_INITIALIZED
0x140097f55  movzx   eax, byte ptr [rdi+34h]
0x140097f59  test    al, al
0x140097f5b  jz      loc_14009807F
0x140097f61  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140097f68  jz      short loc_140097FD6
0x140097f6a  mov     rcx, cs:WPP_GLOBAL_Control
0x140097f71  cmp     byte ptr [rcx+29h], 5
0x140097f75  jnb     short loc_140097F7D
0x140097f77  cmp     [rcx+48h], dx
0x140097f7b  jz      short loc_140097FD6
0x140097f7d  mov     rcx, [rcx+40h]
0x140097f81  mov     r8d, eax
0x140097f84  mov     eax, [rdi+74h]
0x140097f87  mov     [rsp+0B8h+var_40], eax
0x140097f8b  mov     eax, [rdi+70h]
0x140097f8e  mov     [rsp+0B8h+var_48], eax
0x140097f92  mov     eax, [rdi+6Ch]
0x140097f95  mov     [rsp+0B8h+var_50], eax
0x140097f99  mov     eax, [rdi+68h]
0x140097f9c  mov     [rsp+0B8h+var_58], eax
0x140097fa0  mov     eax, [rdi+64h]
0x140097fa3  mov     [rsp+0B8h+var_60], eax
0x140097fa7  mov     eax, [rdi+60h]
0x140097faa  mov     [rsp+0B8h+var_68], eax
0x140097fae  mov     eax, [rdi+78h]
0x140097fb1  mov     [rsp+0B8h+var_70], esi
0x140097fb5  mov     [rsp+0B8h+var_78], eax
0x140097fb9  mov     rax, [rsp+0B8h+arg_18]
0x140097fc1  mov     [rsp+0B8h+var_80], ebp
0x140097fc5  mov     [rsp+0B8h+var_88], r8d
0x140097fca  mov     [rsp+0B8h+var_90], rax
0x140097fcf  call    WPP_RECORDER_SF__MAC_DddDdddddd
0x140097fd4  xor     edx, edx
0x140097fd6  mov     eax, [rdi+78h]
0x140097fd9  cmp     ebp, eax
0x140097fdb  jnz     short loc_140098006
0x140097fdd  test    sil, sil
0x140097fe0  jnz     short loc_140098013
0x140097fe2  cmp     [rdi+35h], dl
0x140097fe5  jnz     short loc_140098066
0x140097fe7  cmp     [rdi+84h], dl
0x140097fed  jnz     short loc_140098066
0x140097fef  mov     rdx, r12; unsigned __int64
0x140097ff2  mov     rcx, rdi; this
0x140097ff5  call    ?CheckForExpiredDevicesAndServices@CServicesManager@@QEAAK_K@Z; CServicesManager::CheckForExpiredDevicesAndServices(unsigned __int64)
0x140097ffa  mov     r14d, eax
0x140097ffd  jmp     short loc_140098064
0x140097fff  xor     edx, edx
0x140098001  jmp     loc_140097F55
0x140098006  inc     dword ptr [rdi+60h]
0x140098009  inc     dword ptr [rdi+64h]
0x14009800c  mov     [rbx], eax
0x14009800e  test    sil, sil
0x140098011  jz      short loc_140098019
0x140098013  inc     dword ptr [rdi+6Ch]
0x140098016  mov     [r15], dl
0x140098019  cmp     [rdi+35h], dl
0x14009801c  jnz     short loc_140098066
0x14009801e  mov     r8, [rsp+0B8h+arg_18]; unsigned __int8 (*)[6]
0x140098026  mov     rdx, r12; unsigned __int64
0x140098029  mov     rcx, rdi; this
0x14009802c  call    ?CheckForNewDevices@CServicesManager@@QEAAK_KPEAY05E@Z; CServicesManager::CheckForNewDevices(unsigned __int64,uchar (*)[6])
0x140098031  mov     r8, [rsp+0B8h+arg_20]; struct _BSS_ENTRY_WFD_SERVICES_INFO *
0x140098039  mov     rdx, r12; unsigned __int64
0x14009803c  mov     rcx, rdi; this
0x14009803f  mov     [rsp+0B8h+arg_0], eax
0x140098046  call    ?CheckForNewServices@CServicesManager@@QEAAK_KPEAU_BSS_ENTRY_WFD_SERVICES_INFO@@@Z; CServicesManager::CheckForNewServices(unsigned __int64,_BSS_ENTRY_WFD_SERVICES_INFO *)
0x14009804b  mov     r8, [rsp+0B8h+arg_28]; struct _BSS_ENTRY_WFD_SERVICES_INFO *
0x140098053  mov     rdx, r12; unsigned __int64
0x140098056  mov     rcx, rdi; this
0x140098059  mov     r13d, eax
0x14009805c  call    ?CheckForNewServices@CServicesManager@@QEAAK_KPEAU_BSS_ENTRY_WFD_SERVICES_INFO@@@Z; CServicesManager::CheckForNewServices(unsigned __int64,_BSS_ENTRY_WFD_SERVICES_INFO *)
0x140098061  add     r13d, eax
0x140098064  xor     edx, edx
0x140098066  cmp     ebp, [rdi+78h]
0x140098069  jnz     short loc_140098075
0x14009806b  test    sil, sil
0x14009806e  jnz     short loc_140098075
0x140098070  test    r14d, r14d
0x140098073  jz      short loc_14009807F
0x140098075  mov     rcx, rdi; this
0x140098078  call    ?CheckStartDeviceUpdateNotificationTimer@CServicesManager@@QEAAXXZ; CServicesManager::CheckStartDeviceUpdateNotificationTimer(void)
0x14009807d  xor     edx, edx
0x14009807f  lea     rax, WPP_RECORDER_INITIALIZED
0x140098086  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14009808d  jz      short loc_1400980D4
0x14009808f  mov     rcx, cs:WPP_GLOBAL_Control
0x140098096  cmp     byte ptr [rcx+29h], 5
0x14009809a  jnb     short loc_1400980A2
0x14009809c  cmp     [rcx+48h], dx
0x1400980a0  jz      short loc_1400980D4
0x1400980a2  mov     rcx, [rcx+40h]
0x1400980a6  lea     eax, [r14+r13]
0x1400980aa  add     eax, [rsp+0B8h+arg_0]
0x1400980b1  mov     r9d, 0F7h
0x1400980b7  mov     dword ptr [rsp+0B8h+var_90], eax
0x1400980bb  mov     r8d, 1
0x1400980c1  lea     rax, WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids
0x1400980c8  mov     dl, 5
0x1400980ca  mov     [rsp+0B8h+var_98], rax
0x1400980cf  call    WPP_RECORDER_SF_d
0x1400980d4  mov     rbx, [rsp+0B8h+arg_8]
0x1400980dc  xor     eax, eax
0x1400980de  add     rsp, 80h
0x1400980e5  pop     r15
0x1400980e7  pop     r14
0x1400980e9  pop     r13
0x1400980eb  pop     r12
0x1400980ed  pop     rdi
0x1400980ee  pop     rsi
0x1400980ef  pop     rbp
0x1400980f0  retn
```
