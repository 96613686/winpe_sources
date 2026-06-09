# OnDemandBrokerClient::LaunchBackgroundTask(void *,void *,ulong,ushort const *,ushort const *,_GUID *,uchar *,ulong,_OdbLaunchInfo *,_GUID *,_GUID *)

- ea: `0x180002460`
- end: `0x180002700`
- name: `?LaunchBackgroundTask@OnDemandBrokerClient@@UEAAJPEAX0KPEBG1PEAU_GUID@@PEAEKPEAU_OdbLaunchInfo@@22@Z`
- size: `672`
- prototype: `__int64 __fastcall(OnDemandBrokerClient *__hidden this, void *, void *, unsigned int, const unsigned __int16 *, const unsigned __int16 *, struct _GUID *, unsigned __int8 *, unsigned int, struct _OdbLaunchInfo *, struct _GUID *, struct _GUID *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002460`
- `0x18000634c`
- `0x180006570`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000263b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000263b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000250f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000250f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000258a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000258a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800026c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800026c7`

## pseudocode

```c
__int64 __fastcall OnDemandBrokerClient::LaunchBackgroundTask(
        OnDemandBrokerClient *this,
        void *a2,
        void *a3,
        unsigned int a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        struct _GUID *a7,
        unsigned __int8 *a8,
        unsigned int a9,
        struct _OdbLaunchInfo *a10,
        struct _GUID *a11,
        struct _GUID *a12)
{
  __int128 *v13; // rdi
  _DWORD *v17; // rax
  __int128 v18; // xmm0
  void *v19; // rdx
  __int64 *v20; // rax
  __int64 v21; // r11
  int v22; // eax
  unsigned int v23; // ebx
  HANDLE TargetHandle; // [rsp+70h] [rbp-A8h] BYREF
  struct _GUID *v26; // [rsp+78h] [rbp-A0h]
  unsigned __int8 *v27; // [rsp+80h] [rbp-98h]
  struct _GUID *v28; // [rsp+88h] [rbp-90h]
  const unsigned __int16 *v29; // [rsp+90h] [rbp-88h]
  struct _GUID *v30; // [rsp+98h] [rbp-80h]
  struct _GUID v31; // [rsp+A0h] [rbp-78h] BYREF
  __int128 v32; // [rsp+B0h] [rbp-68h] BYREF
  __int64 v33; // [rsp+C0h] [rbp-58h]

  v13 = 0;
  v29 = a6;
  v28 = a7;
  v27 = a8;
  v26 = a11;
  v30 = a12;
  v33 = 0;
  v31 = 0;
  TargetHandle = 0;
  v32 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v17 = (_DWORD *)*((_QWORD *)this + 11);
  TargetHandle = 0;
  while ( 1 )
  {
    if ( v17 == (_DWORD *)((char *)this + 88) )
    {
      v23 = -2147023728;
      goto LABEL_15;
    }
    if ( a4 == v17[4] )
      break;
    v17 = *(_DWORD **)v17;
  }
  if ( a10 )
  {
    v18 = *(_OWORD *)a10;
    v19 = *(void **)a10;
    v13 = &v32;
    v33 = *((_QWORD *)a10 + 2);
    v32 = v18;
    if ( v19 )
    {
      if ( DuplicateHandle((HANDLE)0xFFFFFFFFFFFFFFFFLL, v19, (HANDLE)0xFFFFFFFFFFFFFFFFLL, &TargetHandle, 0, 0, 2u) )
        *(_QWORD *)&v32 = TargetHandle;
      else
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
  }
  v20 = (__int64 *)*((_QWORD *)this + 10);
  v21 = *v20;
  if ( a2 )
    v22 = (*(__int64 (__fastcall **)(__int64 *, void *, void *, _QWORD, const unsigned __int16 *, const unsigned __int16 *, struct _GUID *, unsigned __int8 *, unsigned int, __int128 *, struct _GUID *, struct _GUID *))(v21 + 64))(
            v20,
            a2,
            a3,
            a4,
            a5,
            v29,
            v28,
            v27,
            a9,
            v13,
            v26,
            &v31);
  else
    v22 = (*(__int64 (__fastcall **)(__int64 *, void *, _QWORD, const unsigned __int16 *, const unsigned __int16 *, struct _GUID *, unsigned __int8 *, unsigned int, __int128 *, struct _GUID *, struct _GUID *))(v21 + 56))(
            v20,
            a3,
            a4,
            a5,
            v29,
            v28,
            v27,
            a9,
            v13,
            v26,
            &v31);
  v23 = v22;
  if ( v22 >= 0 )
  {
    v23 = 0;
    *v30 = v31;
  }
  if ( TargetHandle )
    CloseHandle(TargetHandle);
LABEL_15:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  return v23;
}

```

## disassembly

```asm
0x180002460  mov     r11, rsp
0x180002463  push    rbx
0x180002464  push    rbp
0x180002465  push    rsi
0x180002466  push    rdi
0x180002467  push    r12
0x180002469  push    r13
0x18000246b  push    r14
0x18000246d  push    r15
0x18000246f  sub     rsp, 0D8h
0x180002476  mov     rax, cs:__security_cookie
0x18000247d  xor     rax, rsp
0x180002480  mov     [rsp+118h+var_50], rax
0x180002488  mov     rax, [rsp+118h+arg_28]
0x180002490  xorps   xmm0, xmm0
0x180002493  mov     rsi, [rsp+118h+arg_48]
0x18000249b  mov     r15, rcx
0x18000249e  mov     r13, [rsp+118h+arg_20]
0x1800024a6  xor     edi, edi
0x1800024a8  mov     [rsp+118h+var_88], rax
0x1800024b0  add     rcx, 18h; lpCriticalSection
0x1800024b4  mov     rax, [rsp+118h+arg_30]
0x1800024bc  mov     ebx, r9d
0x1800024bf  mov     [rsp+118h+var_90], rax
0x1800024c7  mov     r12, r8
0x1800024ca  mov     rax, [rsp+118h+arg_38]
0x1800024d2  mov     rbp, rdx
0x1800024d5  mov     [rsp+118h+var_98], rax
0x1800024dd  mov     rax, [rsp+118h+arg_50]
0x1800024e5  mov     [rsp+118h+var_A0], rax
0x1800024ea  mov     rax, [rsp+118h+arg_58]
0x1800024f2  mov     [rsp+118h+var_80], rax
0x1800024fa  xor     eax, eax
0x1800024fc  mov     [r11-58h], rax
0x180002500  movups  xmmword ptr [r11-78h], xmm0
0x180002505  mov     [rsp+118h+TargetHandle], rdi
0x18000250a  movups  xmmword ptr [r11-68h], xmm0
0x18000250f  call    cs:__imp_EnterCriticalSection
0x180002515  mov     rax, [r15+58h]
0x180002519  lea     rcx, [r15+58h]
0x18000251d  mov     [rsp+118h+TargetHandle], rdi
0x180002522  cmp     rax, rcx
0x180002525  jz      loc_1800026EC
0x18000252b  cmp     ebx, [rax+10h]
0x18000252e  jz      short loc_180002535
0x180002530  mov     rax, [rax]
0x180002533  jmp     short loc_180002522
0x180002535  test    rsi, rsi
0x180002538  jz      short loc_1800025A5
0x18000253a  movups  xmm0, xmmword ptr [rsi]
0x18000253d  mov     rdx, [rsi]; hSourceHandle
0x180002540  lea     rdi, [rsp+118h+var_68]
0x180002548  movsd   xmm1, qword ptr [rsi+10h]
0x18000254d  movsd   [rsp+118h+var_58], xmm1
0x180002556  movups  [rsp+118h+var_68], xmm0
0x18000255e  test    rdx, rdx
0x180002561  jz      short loc_1800025A5
0x180002563  mov     rcx, 0FFFFFFFFFFFFFFFFh; hSourceProcessHandle
0x18000256a  mov     [rsp+118h+dwOptions], 2; dwOptions
0x180002572  mov     r8, rcx; hTargetProcessHandle
0x180002575  mov     [rsp+118h+bInheritHandle], 0; bInheritHandle
0x18000257d  lea     r9, [rsp+118h+TargetHandle]; lpTargetHandle
0x180002582  mov     [rsp+118h+dwDesiredAccess], 0; dwDesiredAccess
0x18000258a  call    cs:__imp_DuplicateHandle
0x180002590  test    eax, eax
0x180002592  jz      loc_1800026F6
0x180002598  mov     rax, [rsp+118h+TargetHandle]
0x18000259d  mov     qword ptr [rsp+118h+var_68], rax
0x1800025a5  mov     rax, [r15+50h]
0x1800025a9  lea     rcx, [rsp+118h+var_78]
0x1800025b1  mov     r11, [rax]
0x1800025b4  test    rbp, rbp
0x1800025b7  jz      loc_180002667
0x1800025bd  mov     r10d, [rsp+118h+arg_40]
0x1800025c5  mov     r9d, ebx
0x1800025c8  mov     [rsp+118h+var_C0], rcx
0x1800025cd  mov     r8, r12
0x1800025d0  mov     rcx, [rsp+118h+var_A0]
0x1800025d5  mov     rdx, rbp
0x1800025d8  mov     [rsp+118h+var_C8], rcx
0x1800025dd  mov     rcx, [rsp+118h+var_98]
0x1800025e5  mov     [rsp+118h+var_D0], rdi
0x1800025ea  mov     dword ptr [rsp+118h+var_D8], r10d
0x1800025ef  mov     [rsp+118h+var_E0], rcx
0x1800025f4  mov     rcx, [rsp+118h+var_90]
0x1800025fc  mov     qword ptr [rsp+118h+dwOptions], rcx
0x180002601  mov     rcx, [rsp+118h+var_88]
0x180002609  mov     qword ptr [rsp+118h+bInheritHandle], rcx
0x18000260e  mov     rcx, rax
0x180002611  mov     rax, [r11+40h]
0x180002615  mov     qword ptr [rsp+118h+dwDesiredAccess], r13
0x18000261a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000261f  mov     ebx, eax
0x180002621  test    eax, eax
0x180002623  jns     loc_1800026D2
0x180002629  mov     rcx, [rsp+118h+TargetHandle]; hObject
0x18000262e  test    rcx, rcx
0x180002631  jnz     loc_1800026C7
0x180002637  lea     rcx, [r15+18h]; lpCriticalSection
0x18000263b  call    cs:__imp_LeaveCriticalSection
0x180002641  mov     eax, ebx
0x180002643  mov     rcx, [rsp+118h+var_50]
0x18000264b  xor     rcx, rsp; StackCookie
0x18000264e  call    __security_check_cookie
0x180002653  add     rsp, 0D8h
0x18000265a  pop     r15
0x18000265c  pop     r14
0x18000265e  pop     r13
0x180002660  pop     r12
0x180002662  pop     rdi
0x180002663  pop     rsi
0x180002664  pop     rbp
0x180002665  pop     rbx
0x180002666  retn
0x180002667  mov     [rsp+118h+var_C8], rcx
0x18000266c  mov     r9, r13
0x18000266f  mov     rcx, [rsp+118h+var_A0]
0x180002674  mov     r8d, ebx
0x180002677  mov     [rsp+118h+var_D0], rcx
0x18000267c  mov     rdx, r12
0x18000267f  mov     ecx, [rsp+118h+arg_40]
0x180002686  mov     [rsp+118h+var_D8], rdi
0x18000268b  mov     dword ptr [rsp+118h+var_E0], ecx
0x18000268f  mov     rcx, [rsp+118h+var_98]
0x180002697  mov     qword ptr [rsp+118h+dwOptions], rcx
0x18000269c  mov     rcx, [rsp+118h+var_90]
0x1800026a4  mov     qword ptr [rsp+118h+bInheritHandle], rcx
0x1800026a9  mov     rcx, [rsp+118h+var_88]
0x1800026b1  mov     qword ptr [rsp+118h+dwDesiredAccess], rcx
0x1800026b6  mov     rcx, rax
0x1800026b9  mov     rax, [r11+38h]
0x1800026bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026c2  jmp     loc_18000261F
0x1800026c7  call    cs:__imp_CloseHandle
0x1800026cd  jmp     loc_180002637
0x1800026d2  mov     rax, [rsp+118h+var_80]
0x1800026da  xor     ebx, ebx
0x1800026dc  movups  xmm0, [rsp+118h+var_78]
0x1800026e4  movups  xmmword ptr [rax], xmm0
0x1800026e7  jmp     loc_180002629
0x1800026ec  mov     ebx, 80070490h
0x1800026f1  jmp     loc_180002637
0x1800026f6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800026fb  jmp     loc_1800025A5
```
