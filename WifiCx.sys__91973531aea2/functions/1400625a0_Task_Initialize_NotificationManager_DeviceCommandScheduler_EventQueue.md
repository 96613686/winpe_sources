# Task::Initialize(NotificationManager *,DeviceCommandScheduler *,EventQueue *)

- ea: `0x1400625a0`
- end: `0x140062760`
- name: `?Initialize@Task@@QEAAHPEAVNotificationManager@@PEAVDeviceCommandScheduler@@PEAVEventQueue@@@Z`
- size: `448`
- prototype: `__int64 __fastcall(enum _WDF_EXECUTION_LEVEL this, struct NotificationManager *, struct DeviceCommandScheduler *, struct EventQueue *)`
- caller_count: `12`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140063764`
- `0x14006b410`
- `0x140071c10`
- `0x14007bbd0`
- `0x14007f3bc`
- `0x140081588`
- `0x14009292c`
- `0x1400ad300`
- `0x1400b511c`
- `0x1400ba93c`
- `0x1400bad7c`
- `0x1400c5aa0`

## callees

- `0x140016d00`
- `0x14001e2c0`
- `0x14001eed0`
- `0x14002bd34`
- `0x1400625a0`
- `0x140062768`
- `0x1400dfd40`

## pseudocode

```c
__int64 __fastcall Task::Initialize(
        __int64 this,
        struct NotificationManager *a2,
        struct DeviceCommandScheduler *a3,
        struct EventQueue *a4)
{
  unsigned int v4; // edi
  __int64 *v9; // rdx
  CPropertyCache *v10; // rax
  int PropertyULong; // eax
  int v12; // edx
  int v13; // r8d
  int v14; // edx
  unsigned int v15; // edi
  int v16; // r8d
  __int64 v18; // [rsp+38h] [rbp-40h]
  unsigned int v19; // [rsp+90h] [rbp+18h] BYREF

  v4 = 30000;
  v19 = 30000;
  v9 = WPP_a1b4414c73513c72229efa91c05f01c7_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v9) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v9,
      (_DWORD)a3,
      15,
      (__int64)WPP_a1b4414c73513c72229efa91c05f01c7_Traceguids,
      this,
      *(_DWORD *)(this + 32));
  }
  v10 = (CPropertyCache *)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)(*((_QWORD *)a3 + 22) + 8LL) + 8LL))(
                            *((_QWORD *)a3 + 22) + 8LL,
                            v9);
  PropertyULong = CPropertyCache::GetPropertyULong(v10, 0x16u, &v19);
  if ( PropertyULong )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_13;
    LOBYTE(v12) = 2;
    WPP_RECORDER_SF_qDdd(
      WPP_GLOBAL_Control->DeviceExtension,
      v12,
      v13,
      16,
      (__int64)WPP_a1b4414c73513c72229efa91c05f01c7_Traceguids,
      this,
      *(_DWORD *)(this + 32),
      PropertyULong,
      30000);
  }
  else
  {
    v4 = v19;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v12) = 5;
    LODWORD(v18) = v4;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v12,
      v13,
      17,
      (__int64)WPP_a1b4414c73513c72229efa91c05f01c7_Traceguids,
      this,
      *(_DWORD *)(this + 32),
      v18);
  }
LABEL_13:
  v15 = Task::Initialize((enum _WDF_EXECUTION_LEVEL)this, a2, a3, a4, v4);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v14) = 5;
    LODWORD(v18) = v15;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v14,
      v16,
      18,
      (__int64)WPP_a1b4414c73513c72229efa91c05f01c7_Traceguids,
      this,
      *(_DWORD *)(this + 32),
      v18);
  }
  return v15;
}

```

## disassembly

```asm
0x1400625a0  mov     rax, rsp
0x1400625a3  mov     [rax+8], rbx
0x1400625a7  mov     [rax+10h], rbp
0x1400625ab  push    rsi
0x1400625ac  push    rdi
0x1400625ad  push    r12
0x1400625af  push    r13
0x1400625b1  push    r14
0x1400625b3  sub     rsp, 50h
0x1400625b7  mov     edi, 7530h
0x1400625bc  mov     rbp, r9
0x1400625bf  mov     [rax+18h], edi
0x1400625c2  mov     rsi, r8
0x1400625c5  mov     r14, rdx
0x1400625c8  mov     rbx, rcx
0x1400625cb  lea     r13, WPP_RECORDER_INITIALIZED
0x1400625d2  xor     r12d, r12d
0x1400625d5  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400625dc  lea     rdx, WPP_a1b4414c73513c72229efa91c05f01c7_Traceguids
0x1400625e3  jz      short loc_14006261B
0x1400625e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400625ec  cmp     byte ptr [rcx+29h], 5
0x1400625f0  jnb     short loc_1400625F9
0x1400625f2  cmp     [rcx+48h], r12w
0x1400625f7  jz      short loc_14006261B
0x1400625f9  mov     eax, [rbx+20h]
0x1400625fc  mov     r9d, 0Fh
0x140062602  mov     rcx, [rcx+40h]
0x140062606  mov     [rsp+78h+var_48], eax
0x14006260a  mov     [rsp+78h+var_50], rbx
0x14006260f  mov     qword ptr [rsp+78h+var_58], rdx
0x140062614  mov     dl, 5
0x140062616  call    WPP_RECORDER_SF_qD
0x14006261b  mov     rcx, [rsi+0B0h]
0x140062622  add     rcx, 8
0x140062626  mov     rax, [rcx]
0x140062629  mov     rax, [rax+8]
0x14006262d  call    _guard_dispatch_icall
0x140062632  lea     r8, [rsp+78h+arg_10]; unsigned int *
0x14006263a  mov     edx, 16h; unsigned int
0x14006263f  mov     rcx, rax; this
0x140062642  call    ?GetPropertyULong@CPropertyCache@@QEAAHKPEAK@Z; CPropertyCache::GetPropertyULong(ulong,ulong *)
0x140062647  test    eax, eax
0x140062649  jz      short loc_140062692
0x14006264b  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140062652  jz      loc_1400626E3
0x140062658  mov     rcx, cs:WPP_GLOBAL_Control
0x14006265f  mov     r9d, 10h
0x140062665  mov     [rsp+78h+var_38], edi
0x140062669  mov     dl, 2
0x14006266b  mov     dword ptr [rsp+78h+var_40], eax
0x14006266f  mov     eax, [rbx+20h]
0x140062672  mov     rcx, [rcx+40h]
0x140062676  mov     [rsp+78h+var_48], eax
0x14006267a  lea     rax, WPP_a1b4414c73513c72229efa91c05f01c7_Traceguids
0x140062681  mov     [rsp+78h+var_50], rbx
0x140062686  mov     qword ptr [rsp+78h+var_58], rax
0x14006268b  call    WPP_RECORDER_SF_qDdd
0x140062690  jmp     short loc_140062699
0x140062692  mov     edi, [rsp+78h+arg_10]
0x140062699  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400626a0  jz      short loc_1400626E3
0x1400626a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400626a9  cmp     byte ptr [rcx+29h], 5
0x1400626ad  jnb     short loc_1400626B6
0x1400626af  cmp     [rcx+48h], r12w
0x1400626b4  jz      short loc_1400626E3
0x1400626b6  mov     eax, [rbx+20h]
0x1400626b9  mov     r9d, 11h
0x1400626bf  mov     rcx, [rcx+40h]
0x1400626c3  mov     dl, 5
0x1400626c5  mov     dword ptr [rsp+78h+var_40], edi
0x1400626c9  mov     [rsp+78h+var_48], eax
0x1400626cd  lea     rax, WPP_a1b4414c73513c72229efa91c05f01c7_Traceguids
0x1400626d4  mov     [rsp+78h+var_50], rbx
0x1400626d9  mov     qword ptr [rsp+78h+var_58], rax
0x1400626de  call    WPP_RECORDER_SF_qDD
0x1400626e3  mov     r9, rbp; struct EventQueue *
0x1400626e6  mov     [rsp+78h+var_58], edi; unsigned int
0x1400626ea  mov     r8, rsi; struct DeviceCommandScheduler *
0x1400626ed  mov     rdx, r14; struct NotificationManager *
0x1400626f0  mov     rcx, rbx; this
0x1400626f3  call    ?Initialize@Task@@QEAAHPEAVNotificationManager@@PEAVDeviceCommandScheduler@@PEAVEventQueue@@K@Z; Task::Initialize(NotificationManager *,DeviceCommandScheduler *,EventQueue *,ulong)
0x1400626f8  mov     edi, eax
0x1400626fa  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140062701  jz      short loc_140062744
0x140062703  mov     rcx, cs:WPP_GLOBAL_Control
0x14006270a  cmp     byte ptr [rcx+29h], 5
0x14006270e  jnb     short loc_140062717
0x140062710  cmp     [rcx+48h], r12w
0x140062715  jz      short loc_140062744
0x140062717  mov     eax, [rbx+20h]
0x14006271a  mov     r9d, 12h
0x140062720  mov     rcx, [rcx+40h]
0x140062724  mov     dl, 5
0x140062726  mov     dword ptr [rsp+78h+var_40], edi
0x14006272a  mov     [rsp+78h+var_48], eax
0x14006272e  lea     rax, WPP_a1b4414c73513c72229efa91c05f01c7_Traceguids
0x140062735  mov     [rsp+78h+var_50], rbx
0x14006273a  mov     qword ptr [rsp+78h+var_58], rax
0x14006273f  call    WPP_RECORDER_SF_qDD
0x140062744  lea     r11, [rsp+78h+var_28]
0x140062749  mov     eax, edi
0x14006274b  mov     rbx, [r11+30h]
0x14006274f  mov     rbp, [r11+38h]
0x140062753  mov     rsp, r11
0x140062756  pop     r14
0x140062758  pop     r13
0x14006275a  pop     r12
0x14006275c  pop     rdi
0x14006275d  pop     rsi
0x14006275e  retn
```
