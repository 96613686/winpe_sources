# SidebandAudioWdmEndpoint::SignalStatusUpdate(StatusUpdateType)

- ea: `0x140088f60`
- end: `0x1400891e3`
- name: `?SignalStatusUpdate@SidebandAudioWdmEndpoint@@UEAAJW4StatusUpdateType@@@Z`
- size: `643`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x14000e690`
- `0x1400202e8`
- `0x1400366ac`
- `0x140037ee4`
- `0x140058410`
- `0x140087200`
- `0x1400874e0`
- `0x140088f60`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140089034`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140089034`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140089043`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140089043`

## pseudocode

```c
__int64 __fastcall SidebandAudioWdmEndpoint::SignalStatusUpdate(__int64 a1, unsigned int a2)
{
  int v2; // r14d
  bool v3; // bl
  __int64 v5; // r12
  __int64 v6; // rdi
  struct _FAST_MUTEX *v7; // rbx
  __int64 v8; // rcx
  __int64 Next; // rbp
  char v10; // bl
  int v11; // edx
  int v12; // r8d
  __int64 v13; // r8
  int ImmediateStatusUpdate; // eax
  int v15; // edx
  unsigned int v16; // ebp
  _BYTE v17[16]; // [rsp+60h] [rbp-58h] BYREF
  int v18; // [rsp+70h] [rbp-48h] BYREF
  __int64 v19; // [rsp+78h] [rbp-40h]
  __int64 v20; // [rsp+80h] [rbp-38h]
  __int16 v21; // [rsp+C8h] [rbp+10h] BYREF
  struct _FAST_MUTEX *v22; // [rsp+D0h] [rbp+18h] BYREF

  v2 = a2;
  if ( a2 > 5 )
  {
    v3 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = v3;
      WPP_RECORDER_AND_TRACE_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        a2,
        WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        2,
        68,
        (__int64)WPP_82bfadf91fc73c4f22c211ed6841aba6_Traceguids,
        13);
    }
    return 3221225485LL;
  }
  v5 = a1 - 16;
  v21 = a2;
  v6 = lambda_4013a6fef28567ded211aa9527d19120_::_lambda_4013a6fef28567ded211aa9527d19120_(v17, a1 - 16, &v21);
  v7 = (struct _FAST_MUTEX *)(*(_QWORD *)v6 + 64LL);
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe(v7);
  v8 = *(unsigned __int16 *)(v6 + 8);
  v22 = v7;
  Next = IoQueue_GetNext(80 * v8 + 120 + *(_QWORD *)v6);
  v10 = 1;
  if ( !Next )
    *(_BYTE *)(*(unsigned __int16 *)(v6 + 8) + *(_QWORD *)v6 + 600LL) = 1;
  __1__unique_storage_U__resource_policy_PEAU_FAST_MUTEX____A6AXPEAU1___E_1_release_fast_mutex_with_critical_region_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&v22);
  LOBYTE(v11) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)v11 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_Llq(WPP_GLOBAL_Control->AttachedDevice, v11, v12, WPP_GLOBAL_Control->DeviceExtension);
  }
  if ( !Next )
    return 0;
  v13 = *(_QWORD *)(Next + 112);
  v19 = *(_QWORD *)(Next + 56);
  v20 = Next;
  ImmediateStatusUpdate = SidebandAudioWdmEndpoint::GetImmediateStatusUpdate(v5, v2, v13);
  v18 = ImmediateStatusUpdate;
  v16 = ImmediateStatusUpdate;
  if ( ImmediateStatusUpdate >= 0 )
  {
    CompletableIrp::~CompletableIrp((CompletableIrp *)&v18);
    return 0;
  }
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
  {
    v10 = 0;
  }
  if ( v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v15) = v10;
    WPP_RECORDER_AND_TRACE_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      v15,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      2,
      70,
      (__int64)WPP_82bfadf91fc73c4f22c211ed6841aba6_Traceguids,
      ImmediateStatusUpdate);
  }
  CompletableIrp::~CompletableIrp((CompletableIrp *)&v18);
  return v16;
}

```

## disassembly

```asm
0x140088f60  mov     [rsp+arg_0], rbx
0x140088f65  mov     [rsp+arg_18], rbp
0x140088f6a  push    rsi
0x140088f6b  push    rdi
0x140088f6c  push    r12
0x140088f6e  push    r14
0x140088f70  push    r15
0x140088f72  sub     rsp, 90h
0x140088f79  mov     r14d, edx
0x140088f7c  cmp     edx, 5
0x140088f7f  jbe     loc_140089008
0x140088f85  mov     rcx, cs:WPP_GLOBAL_Control
0x140088f8c  lea     rdi, WPP_GLOBAL_Control
0x140088f93  cmp     rcx, rdi
0x140088f96  jz      short loc_140088FAC
0x140088f98  mov     eax, [rcx+2Ch]
0x140088f9b  test    al, 2
0x140088f9d  jz      short loc_140088FAC
0x140088f9f  cmp     byte ptr [rcx+29h], 2
0x140088fa3  jb      short loc_140088FAC
0x140088fa5  mov     ebx, 1
0x140088faa  jmp     short loc_140088FAE
0x140088fac  xor     bl, bl
0x140088fae  lea     rsi, WPP_RECORDER_INITIALIZED
0x140088fb5  mov     edi, 0C000000Dh
0x140088fba  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140088fc1  setnz   r8b
0x140088fc5  test    bl, bl
0x140088fc7  jnz     short loc_140088FCE
0x140088fc9  test    r8b, r8b
0x140088fcc  jz      short loc_140089001
0x140088fce  mov     r9, [rcx+40h]
0x140088fd2  lea     r15, WPP_82bfadf91fc73c4f22c211ed6841aba6_Traceguids
0x140088fd9  mov     rcx, [rcx+18h]
0x140088fdd  mov     dl, bl
0x140088fdf  mov     [rsp+0B8h+var_78], edi
0x140088fe3  mov     [rsp+0B8h+var_80], r15
0x140088fe8  mov     [rsp+0B8h+var_88], 44h ; 'D'
0x140088fef  mov     [rsp+0B8h+var_90], 2
0x140088ff7  mov     [rsp+0B8h+var_98], 2
0x140088ffc  call    WPP_RECORDER_AND_TRACE_SF_d
0x140089001  mov     eax, edi
0x140089003  jmp     loc_1400891C6
0x140089008  lea     r12, [rcx-10h]
0x14008900c  mov     [rsp+0B8h+arg_8], r14w
0x140089015  mov     rdx, r12
0x140089018  lea     r8, [rsp+0B8h+arg_8]
0x140089020  lea     rcx, [rsp+0B8h+var_58]
0x140089025  call    _lambda_4013a6fef28567ded211aa9527d19120____lambda_4013a6fef28567ded211aa9527d19120_
0x14008902a  mov     rdi, rax
0x14008902d  mov     rbx, [rax]
0x140089030  add     rbx, 40h ; '@'
0x140089034  call    cs:__imp_KeEnterCriticalRegion
0x14008903b  nop     dword ptr [rax+rax+00h]
0x140089040  mov     rcx, rbx; FastMutex
0x140089043  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14008904a  nop     dword ptr [rax+rax+00h]
0x14008904f  movzx   ecx, word ptr [rdi+8]
0x140089053  mov     [rsp+0B8h+arg_10], rbx
0x14008905b  lea     rdx, [rcx+rcx*4]
0x14008905f  mov     rcx, [rdi]
0x140089062  shl     rdx, 4
0x140089066  add     rdx, 78h ; 'x'
0x14008906a  add     rcx, rdx
0x14008906d  call    IoQueue_GetNext
0x140089072  mov     rbp, rax
0x140089075  mov     ebx, 1
0x14008907a  test    rax, rax
0x14008907d  jnz     short loc_14008908D
0x14008907f  movzx   edx, word ptr [rdi+8]
0x140089083  mov     rcx, [rdi]
0x140089086  mov     [rdx+rcx+258h], bl
0x14008908d  lea     rcx, [rsp+0B8h+arg_10]
0x140089095  call    ??1?$unique_storage@U?$resource_policy@PEAU_FAST_MUTEX@@$$A6AXPEAU1@@_E$1?release_fast_mutex_with_critical_region@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14008909a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400890a1  lea     rdi, WPP_GLOBAL_Control
0x1400890a8  cmp     rcx, rdi
0x1400890ab  jz      short loc_1400890BE
0x1400890ad  mov     eax, [rcx+2Ch]
0x1400890b0  test    bl, al
0x1400890b2  jz      short loc_1400890BE
0x1400890b4  cmp     byte ptr [rcx+29h], 4
0x1400890b8  jb      short loc_1400890BE
0x1400890ba  mov     dl, bl
0x1400890bc  jmp     short loc_1400890C0
0x1400890be  xor     dl, dl
0x1400890c0  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400890c7  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400890ce  lea     r15, WPP_82bfadf91fc73c4f22c211ed6841aba6_Traceguids
0x1400890d5  setnz   r8b
0x1400890d9  test    dl, dl
0x1400890db  jnz     short loc_1400890E2
0x1400890dd  test    r8b, r8b
0x1400890e0  jz      short loc_14008911B
0x1400890e2  xor     r9d, r9d
0x1400890e5  mov     [rsp+0B8h+var_68], r12
0x1400890ea  test    rbp, rbp
0x1400890ed  movzx   eax, r14w
0x1400890f1  setnz   r9b
0x1400890f5  mov     [rsp+0B8h+var_70], r9d
0x1400890fa  mov     r9, [rcx+40h]
0x1400890fe  mov     rcx, [rcx+18h]
0x140089102  mov     [rsp+0B8h+var_78], eax
0x140089106  mov     [rsp+0B8h+var_80], r15
0x14008910b  mov     [rsp+0B8h+var_88], 45h ; 'E'
0x140089112  mov     [rsp+0B8h+var_90], ebx
0x140089116  call    WPP_RECORDER_AND_TRACE_SF_Llq
0x14008911b  test    rbp, rbp
0x14008911e  jz      loc_1400891C4
0x140089124  mov     rax, [rbp+38h]
0x140089128  mov     edx, r14d
0x14008912b  mov     r8, [rbp+70h]
0x14008912f  mov     rcx, r12
0x140089132  mov     [rsp+0B8h+var_40], rax
0x140089137  mov     [rsp+0B8h+var_38], rbp
0x14008913f  call    ?GetImmediateStatusUpdate@SidebandAudioWdmEndpoint@@AEAAJW4StatusUpdateType@@PEAU_SIDEBANDAUDIO_STATUS_PARAMS_HEADER@@@Z; SidebandAudioWdmEndpoint::GetImmediateStatusUpdate(StatusUpdateType,_SIDEBANDAUDIO_STATUS_PARAMS_HEADER *)
0x140089144  mov     [rsp+0B8h+var_48], eax
0x140089148  mov     ebp, eax
0x14008914a  test    eax, eax
0x14008914c  jns     short loc_1400891BA
0x14008914e  mov     r10, cs:WPP_GLOBAL_Control
0x140089155  cmp     r10, rdi
0x140089158  jz      short loc_14008916A
0x14008915a  mov     ecx, [r10+2Ch]
0x14008915e  test    cl, 2
0x140089161  jz      short loc_14008916A
0x140089163  cmp     byte ptr [r10+29h], 2
0x140089168  jnb     short loc_14008916C
0x14008916a  xor     bl, bl
0x14008916c  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140089173  setnz   r8b
0x140089177  test    bl, bl
0x140089179  jnz     short loc_140089180
0x14008917b  test    r8b, r8b
0x14008917e  jz      short loc_1400891AC
0x140089180  mov     r9, [r10+40h]
0x140089184  mov     dl, bl
0x140089186  mov     rcx, [r10+18h]
0x14008918a  mov     [rsp+0B8h+var_78], ebp
0x14008918e  mov     [rsp+0B8h+var_80], r15
0x140089193  mov     [rsp+0B8h+var_88], 46h ; 'F'
0x14008919a  mov     [rsp+0B8h+var_90], 2
0x1400891a2  mov     [rsp+0B8h+var_98], 2
0x1400891a7  call    WPP_RECORDER_AND_TRACE_SF_d
0x1400891ac  lea     rcx, [rsp+0B8h+var_48]; this
0x1400891b1  call    ??1CompletableIrp@@QEAA@XZ; CompletableIrp::~CompletableIrp(void)
0x1400891b6  mov     eax, ebp
0x1400891b8  jmp     short loc_1400891C6
0x1400891ba  lea     rcx, [rsp+0B8h+var_48]; this
0x1400891bf  call    ??1CompletableIrp@@QEAA@XZ; CompletableIrp::~CompletableIrp(void)
0x1400891c4  xor     eax, eax
0x1400891c6  lea     r11, [rsp+0B8h+var_28]
0x1400891ce  mov     rbx, [r11+30h]
0x1400891d2  mov     rbp, [r11+48h]
0x1400891d6  mov     rsp, r11
0x1400891d9  pop     r15
0x1400891db  pop     r14
0x1400891dd  pop     r12
0x1400891df  pop     rdi
0x1400891e0  pop     rsi
0x1400891e1  retn
```
