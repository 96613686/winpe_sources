# A2dpSidebandAudioWdmEndpoint::GetSiopUpdate(_IRP *)

- ea: `0x140080150`
- end: `0x140080396`
- name: `?GetSiopUpdate@A2dpSidebandAudioWdmEndpoint@@AEAAJPEAU_IRP@@@Z`
- size: `582`
- prototype: `__int64 __fastcall(A2dpSidebandAudioWdmEndpoint *__hidden this, struct _IRP *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140080730`

## callees

- `0x140003530`
- `0x14000e690`
- `0x1400202e8`
- `0x1400366ac`
- `0x14003674c`
- `0x140058390`
- `0x140080150`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140080324`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140080324`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140080333`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140080333`

## pseudocode

```c
__int64 __fastcall A2dpSidebandAudioWdmEndpoint::GetSiopUpdate(A2dpSidebandAudioWdmEndpoint *this, struct _IRP *a2)
{
  struct _IRP *v2; // rsi
  char v4; // di
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  unsigned int v6; // ebx
  PDEVICE_OBJECT v7; // rcx
  bool v8; // r8
  PNAMED_PIPE_CREATE_PARAMETERS Parameters; // rcx
  __int64 v10; // rax
  int v11; // ecx
  int v12; // ecx
  __int64 v13; // rdi
  struct _IRP *v14; // rax
  __int16 v16; // [rsp+30h] [rbp-68h]
  int v17; // [rsp+50h] [rbp-48h] BYREF
  __int64 v18; // [rsp+58h] [rbp-40h]
  struct _IRP *v19; // [rsp+60h] [rbp-38h]
  char *v20; // [rsp+A8h] [rbp+10h] BYREF

  v2 = a2;
  v4 = 1;
  LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)a2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      19,
      101,
      (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
      (char)this);
  CurrentStackLocation = v2->Tail.Overlay.CurrentStackLocation;
  v17 = 0;
  v18 = 0;
  v19 = v2;
  if ( CurrentStackLocation->Parameters.Create.Options == 32 )
  {
    Parameters = CurrentStackLocation->Parameters.CreatePipe.Parameters;
    v10 = *(_QWORD *)&Parameters->CompletionMode - SIDEBANDAUDIO_PARAMS_SET_A2DP;
    if ( !v10 )
      v10 = *(_QWORD *)&Parameters->InboundQuota - *((_QWORD *)&SIDEBANDAUDIO_PARAMS_SET_A2DP + 1);
    if ( !v10 )
    {
      v11 = Parameters->DefaultTimeout.LowPart - 2;
      if ( v11 )
      {
        v12 = v11 - 1;
        if ( v12 )
        {
          if ( v12 != 1 )
          {
            v6 = -1073741811;
            v17 = -1073741811;
            goto LABEL_36;
          }
          v13 = 968;
        }
        else
        {
          v13 = 888;
        }
      }
      else
      {
        v13 = 808;
      }
      KeEnterCriticalRegion();
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)((char *)this + 680));
      v20 = (char *)this + 680;
      v14 = CompletableIrp::Detach((CompletableIrp *)&v17);
      IoQueue_AddEx((char *)this + v13, v14);
      v2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = (struct _LIST_ENTRY *)this;
      __1__unique_storage_U__resource_policy_PEAU_FAST_MUTEX____A6AXPEAU1___E_1_release_fast_mutex_with_critical_region_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&v20);
      v6 = 0;
      goto LABEL_36;
    }
    v6 = -1073741811;
    v17 = -1073741811;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v4 = 0;
    }
    v8 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v16 = 103;
      goto LABEL_27;
    }
  }
  else
  {
    v6 = -1073741811;
    v17 = -1073741811;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v4 = 0;
    }
    v8 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v16 = 102;
LABEL_27:
      LOBYTE(a2) = v4;
      WPP_RECORDER_AND_TRACE_SF_d(
        v7->AttachedDevice,
        (_DWORD)a2,
        v8,
        v7->DeviceExtension,
        2,
        18,
        v16,
        (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
        13);
    }
  }
LABEL_36:
  CompletableIrp::~CompletableIrp((CompletableIrp *)&v17);
  return v6;
}

```

## disassembly

```asm
0x140080150  mov     [rsp+arg_0], rbx
0x140080155  mov     [rsp+arg_10], rbp
0x14008015a  push    rsi
0x14008015b  push    rdi
0x14008015c  push    r12
0x14008015e  push    r14
0x140080160  push    r15
0x140080162  sub     rsp, 70h
0x140080166  mov     rsi, rdx
0x140080169  mov     rbp, rcx
0x14008016c  mov     rcx, cs:WPP_GLOBAL_Control
0x140080173  lea     r14, WPP_GLOBAL_Control
0x14008017a  mov     dil, 1
0x14008017d  cmp     rcx, r14
0x140080180  jz      short loc_140080196
0x140080182  test    dword ptr [rcx+2Ch], 40000h
0x140080189  jz      short loc_140080196
0x14008018b  cmp     byte ptr [rcx+29h], 4
0x14008018f  jb      short loc_140080196
0x140080191  mov     dl, dil
0x140080194  jmp     short loc_140080198
0x140080196  xor     dl, dl
0x140080198  lea     r15, WPP_RECORDER_INITIALIZED
0x14008019f  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400801a6  lea     r12, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x1400801ad  setnz   r8b
0x1400801b1  test    dl, dl
0x1400801b3  jnz     short loc_1400801BA
0x1400801b5  test    r8b, r8b
0x1400801b8  jz      short loc_1400801E5
0x1400801ba  mov     r9, [rcx+40h]
0x1400801be  mov     rcx, [rcx+18h]
0x1400801c2  mov     [rsp+98h+var_58], rbp
0x1400801c7  mov     [rsp+98h+var_60], r12
0x1400801cc  mov     [rsp+98h+var_68], 65h ; 'e'
0x1400801d3  mov     [rsp+98h+var_70], 13h
0x1400801db  mov     [rsp+98h+var_78], 4
0x1400801e0  call    WPP_RECORDER_AND_TRACE_SF_q
0x1400801e5  mov     rcx, [rsi+0B8h]
0x1400801ec  mov     [rsp+98h+var_48], 0
0x1400801f4  mov     [rsp+98h+var_40], 0
0x1400801fd  mov     [rsp+98h+var_38], rsi
0x140080202  cmp     dword ptr [rcx+10h], 20h ; ' '
0x140080206  jz      short loc_14008025A
0x140080208  mov     ebx, 0C000000Dh
0x14008020d  mov     [rsp+98h+var_48], ebx
0x140080211  mov     rcx, cs:WPP_GLOBAL_Control
0x140080218  cmp     rcx, r14
0x14008021b  jz      short loc_14008022C
0x14008021d  test    dword ptr [rcx+2Ch], 20000h
0x140080224  jz      short loc_14008022C
0x140080226  cmp     byte ptr [rcx+29h], 2
0x14008022a  jnb     short loc_14008022F
0x14008022c  xor     dil, dil
0x14008022f  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140080236  setnz   r8b
0x14008023a  test    dil, dil
0x14008023d  jnz     short loc_140080248
0x14008023f  test    r8b, r8b
0x140080242  jz      loc_140080370
0x140080248  mov     dword ptr [rsp+98h+var_58], ebx
0x14008024c  mov     [rsp+98h+var_60], r12
0x140080251  mov     [rsp+98h+var_68], 66h ; 'f'
0x140080258  jmp     short loc_1400802CB
0x14008025a  mov     rcx, [rcx+20h]
0x14008025e  mov     rax, [rcx+8]
0x140080262  sub     rax, qword ptr cs:SIDEBANDAUDIO_PARAMS_SET_A2DP
0x140080269  jnz     short loc_140080276
0x14008026b  mov     rax, [rcx+10h]
0x14008026f  sub     rax, qword ptr cs:SIDEBANDAUDIO_PARAMS_SET_A2DP+8
0x140080276  test    rax, rax
0x140080279  jz      short loc_1400802ED
0x14008027b  mov     ebx, 0C000000Dh
0x140080280  mov     [rsp+98h+var_48], ebx
0x140080284  mov     rcx, cs:WPP_GLOBAL_Control
0x14008028b  cmp     rcx, r14
0x14008028e  jz      short loc_14008029F
0x140080290  test    dword ptr [rcx+2Ch], 20000h
0x140080297  jz      short loc_14008029F
0x140080299  cmp     byte ptr [rcx+29h], 2
0x14008029d  jnb     short loc_1400802A2
0x14008029f  xor     dil, dil
0x1400802a2  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400802a9  setnz   r8b
0x1400802ad  test    dil, dil
0x1400802b0  jnz     short loc_1400802BB
0x1400802b2  test    r8b, r8b
0x1400802b5  jz      loc_140080370
0x1400802bb  mov     dword ptr [rsp+98h+var_58], ebx
0x1400802bf  mov     [rsp+98h+var_60], r12
0x1400802c4  mov     [rsp+98h+var_68], 67h ; 'g'
0x1400802cb  mov     r9, [rcx+40h]
0x1400802cf  mov     dl, dil
0x1400802d2  mov     rcx, [rcx+18h]
0x1400802d6  mov     [rsp+98h+var_70], 12h
0x1400802de  mov     [rsp+98h+var_78], 2
0x1400802e3  call    WPP_RECORDER_AND_TRACE_SF_d
0x1400802e8  jmp     loc_140080370
0x1400802ed  mov     ecx, [rcx+18h]
0x1400802f0  sub     ecx, 2
0x1400802f3  jz      short loc_140080318
0x1400802f5  sub     ecx, 1
0x1400802f8  jz      short loc_140080311
0x1400802fa  cmp     ecx, 1
0x1400802fd  jz      short loc_14008030A
0x1400802ff  mov     ebx, 0C000000Dh
0x140080304  mov     [rsp+98h+var_48], ebx
0x140080308  jmp     short loc_140080370
0x14008030a  mov     edi, 3C8h
0x14008030f  jmp     short loc_14008031D
0x140080311  mov     edi, 378h
0x140080316  jmp     short loc_14008031D
0x140080318  mov     edi, 328h
0x14008031d  lea     rbx, [rbp+2A8h]
0x140080324  call    cs:__imp_KeEnterCriticalRegion
0x14008032b  nop     dword ptr [rax+rax+00h]
0x140080330  mov     rcx, rbx; FastMutex
0x140080333  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14008033a  nop     dword ptr [rax+rax+00h]
0x14008033f  lea     rcx, [rsp+98h+var_48]; this
0x140080344  mov     [rsp+98h+arg_8], rbx
0x14008034c  call    ?Detach@CompletableIrp@@QEAAPEAU_IRP@@XZ; CompletableIrp::Detach(void)
0x140080351  mov     rdx, rax
0x140080354  lea     rcx, [rdi+rbp]
0x140080358  call    IoQueue_AddEx
0x14008035d  lea     rcx, [rsp+98h+arg_8]
0x140080365  mov     [rsi+78h], rbp
0x140080369  call    ??1?$unique_storage@U?$resource_policy@PEAU_FAST_MUTEX@@$$A6AXPEAU1@@_E$1?release_fast_mutex_with_critical_region@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14008036e  xor     ebx, ebx
0x140080370  lea     rcx, [rsp+98h+var_48]; this
0x140080375  call    ??1CompletableIrp@@QEAA@XZ; CompletableIrp::~CompletableIrp(void)
0x14008037a  lea     r11, [rsp+98h+var_28]
0x14008037f  mov     eax, ebx
0x140080381  mov     rbx, [r11+30h]
0x140080385  mov     rbp, [r11+40h]
0x140080389  mov     rsp, r11
0x14008038c  pop     r15
0x14008038e  pop     r14
0x140080390  pop     r12
0x140080392  pop     rdi
0x140080393  pop     rsi
0x140080394  retn
```
