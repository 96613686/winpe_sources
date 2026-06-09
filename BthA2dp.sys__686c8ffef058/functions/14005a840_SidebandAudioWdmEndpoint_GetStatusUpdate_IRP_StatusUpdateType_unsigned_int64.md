# SidebandAudioWdmEndpoint::GetStatusUpdate(_IRP *,StatusUpdateType,unsigned __int64)

- ea: `0x14005a840`
- end: `0x14005ab46`
- name: `?GetStatusUpdate@SidebandAudioWdmEndpoint@@AEAAJPEAU_IRP@@W4StatusUpdateType@@_K@Z`
- size: `774`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, size_t)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140088510`

## callees

- `0x14000e690`
- `0x1400202e8`
- `0x1400366ac`
- `0x14003674c`
- `0x140058390`
- `0x14005a840`
- `0x14005ae74`
- `0x14005ce00`
- `0x1400874e0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14005a995`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005a995`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14005a9a4`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14005a9a4`

## pseudocode

```c
__int64 __fastcall SidebandAudioWdmEndpoint::GetStatusUpdate(__int64 a1, __int64 a2, unsigned int a3, size_t a4)
{
  __int64 v4; // rdi
  _QWORD *v6; // r15
  unsigned int v8; // r12d
  unsigned int v9; // edi
  PDEVICE_OBJECT v10; // rcx
  bool v11; // bl
  __int64 v12; // rdi
  int v13; // edx
  int v14; // r8d
  int v15; // r10d
  char v16; // bl
  bool v17; // di
  unsigned __int16 v18; // r13
  int v19; // edx
  int v20; // r8d
  struct _IRP *v21; // rax
  __int16 v23; // [rsp+30h] [rbp-A8h]
  int ImmediateStatusUpdate; // [rsp+70h] [rbp-68h] BYREF
  size_t v25; // [rsp+78h] [rbp-60h]
  __int64 v26; // [rsp+80h] [rbp-58h]
  __int64 v27; // [rsp+E8h] [rbp+10h] BYREF

  v4 = *(_QWORD *)(a2 + 184);
  ImmediateStatusUpdate = 0;
  v6 = (_QWORD *)a2;
  v25 = a4;
  v26 = a2;
  v8 = a3;
  if ( *(_DWORD *)(v4 + 16) == a4 )
  {
    if ( *(_DWORD *)(v4 + 8) == a4 )
    {
      memmove(*(void **)(a2 + 112), *(const void **)(v4 + 32), a4);
      v6[7] = a4;
      v12 = *(_QWORD *)(v4 + 32);
      KeEnterCriticalRegion();
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 64));
      v15 = *(_DWORD *)(v12 + 4);
      v27 = a1 + 64;
      v16 = 1;
      v17 = v15 || *(_BYTE *)((unsigned __int16)v8 + a1 + 600);
      LOBYTE(v13) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      if ( (_BYTE)v13 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v18 = v8;
        LOBYTE(v14) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_Llllq(
          WPP_GLOBAL_Control->AttachedDevice,
          v13,
          v14,
          WPP_GLOBAL_Control->DeviceExtension);
      }
      else
      {
        v18 = v8;
      }
      if ( v17 )
      {
        ImmediateStatusUpdate = SidebandAudioWdmEndpoint::GetImmediateStatusUpdate(a1, v8, v6[14]);
        v9 = ImmediateStatusUpdate;
        if ( ImmediateStatusUpdate < 0 )
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            v16 = 0;
          }
          if ( v16 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v19) = v16;
            LOBYTE(v20) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              v19,
              v20,
              WPP_GLOBAL_Control->DeviceExtension,
              2,
              2,
              53,
              (__int64)WPP_82bfadf91fc73c4f22c211ed6841aba6_Traceguids,
              ImmediateStatusUpdate);
          }
          __1__unique_storage_U__resource_policy_PEAU_FAST_MUTEX____A6AXPEAU1___E_1_release_fast_mutex_with_critical_region_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&v27);
          goto LABEL_45;
        }
      }
      else
      {
        v21 = CompletableIrp::Detach((CompletableIrp *)&ImmediateStatusUpdate);
        IoQueue_AddEx(a1 + 80LL * v18 + 120, v21);
        v6[15] = a1;
      }
      __1__unique_storage_U__resource_policy_PEAU_FAST_MUTEX____A6AXPEAU1___E_1_release_fast_mutex_with_critical_region_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&v27);
      v9 = 0;
      goto LABEL_45;
    }
    v9 = -1073741811;
    ImmediateStatusUpdate = -1073741811;
    v10 = WPP_GLOBAL_Control;
    v11 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
       && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
       && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v11 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v23 = 51;
      goto LABEL_19;
    }
  }
  else
  {
    v9 = -1073741811;
    ImmediateStatusUpdate = -1073741811;
    v10 = WPP_GLOBAL_Control;
    v11 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
       && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
       && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v11 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v23 = 50;
LABEL_19:
      LOBYTE(a2) = v11;
      WPP_RECORDER_AND_TRACE_SF_d(
        v10->AttachedDevice,
        a2,
        a3,
        v10->DeviceExtension,
        2,
        2,
        v23,
        (__int64)WPP_82bfadf91fc73c4f22c211ed6841aba6_Traceguids,
        13);
    }
  }
LABEL_45:
  CompletableIrp::~CompletableIrp((CompletableIrp *)&ImmediateStatusUpdate);
  return v9;
}

```

## disassembly

```asm
0x14005a840  mov     rax, rsp
0x14005a843  push    rbx
0x14005a844  push    rbp
0x14005a845  push    rsi
0x14005a846  push    rdi
0x14005a847  push    r12
0x14005a849  push    r13
0x14005a84b  push    r14
0x14005a84d  push    r15
0x14005a84f  sub     rsp, 98h
0x14005a856  mov     rdi, [rdx+0B8h]
0x14005a85d  mov     rbx, r9
0x14005a860  mov     dword ptr [rax-68h], 0
0x14005a867  mov     r15, rdx
0x14005a86a  mov     [rax-60h], rbx
0x14005a86e  mov     r14, rcx
0x14005a871  mov     [rax-58h], rdx
0x14005a875  mov     eax, [rdi+10h]
0x14005a878  mov     r12d, r8d
0x14005a87b  cmp     rax, r9
0x14005a87e  jz      short loc_14005A8E7
0x14005a880  mov     edi, 0C000000Dh
0x14005a885  mov     [rsp+0D8h+var_68], edi
0x14005a889  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a890  lea     rsi, WPP_GLOBAL_Control
0x14005a897  cmp     rcx, rsi
0x14005a89a  jz      short loc_14005A8AD
0x14005a89c  mov     eax, [rcx+2Ch]
0x14005a89f  test    al, 2
0x14005a8a1  jz      short loc_14005A8AD
0x14005a8a3  cmp     byte ptr [rcx+29h], 2
0x14005a8a7  jb      short loc_14005A8AD
0x14005a8a9  mov     bl, 1
0x14005a8ab  jmp     short loc_14005A8AF
0x14005a8ad  xor     bl, bl
0x14005a8af  lea     rbp, WPP_RECORDER_INITIALIZED
0x14005a8b6  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14005a8bd  setnz   r8b
0x14005a8c1  test    bl, bl
0x14005a8c3  jnz     short loc_14005A8CE
0x14005a8c5  test    r8b, r8b
0x14005a8c8  jz      loc_14005AB25
0x14005a8ce  mov     [rsp+0D8h+var_98], edi
0x14005a8d2  lea     rax, WPP_82bfadf91fc73c4f22c211ed6841aba6_Traceguids
0x14005a8d9  mov     [rsp+0D8h+var_A0], rax
0x14005a8de  mov     [rsp+0D8h+var_A8], 32h ; '2'
0x14005a8e5  jmp     short loc_14005A958
0x14005a8e7  mov     eax, [rdi+8]
0x14005a8ea  cmp     rax, rbx
0x14005a8ed  jz      loc_14005A979
0x14005a8f3  mov     edi, 0C000000Dh
0x14005a8f8  mov     [rsp+0D8h+var_68], edi
0x14005a8fc  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a903  lea     rsi, WPP_GLOBAL_Control
0x14005a90a  cmp     rcx, rsi
0x14005a90d  jz      short loc_14005A920
0x14005a90f  mov     eax, [rcx+2Ch]
0x14005a912  test    al, 2
0x14005a914  jz      short loc_14005A920
0x14005a916  cmp     byte ptr [rcx+29h], 2
0x14005a91a  jb      short loc_14005A920
0x14005a91c  mov     bl, 1
0x14005a91e  jmp     short loc_14005A922
0x14005a920  xor     bl, bl
0x14005a922  lea     rbp, WPP_RECORDER_INITIALIZED
0x14005a929  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14005a930  setnz   r8b
0x14005a934  test    bl, bl
0x14005a936  jnz     short loc_14005A941
0x14005a938  test    r8b, r8b
0x14005a93b  jz      loc_14005AB25
0x14005a941  mov     [rsp+0D8h+var_98], edi
0x14005a945  lea     rax, WPP_82bfadf91fc73c4f22c211ed6841aba6_Traceguids
0x14005a94c  mov     [rsp+0D8h+var_A0], rax
0x14005a951  mov     [rsp+0D8h+var_A8], 33h ; '3'
0x14005a958  mov     r9, [rcx+40h]
0x14005a95c  mov     dl, bl
0x14005a95e  mov     rcx, [rcx+18h]
0x14005a962  mov     [rsp+0D8h+var_B0], 2
0x14005a96a  mov     [rsp+0D8h+var_B8], 2
0x14005a96f  call    WPP_RECORDER_AND_TRACE_SF_d
0x14005a974  jmp     loc_14005AB25
0x14005a979  mov     rdx, [rdi+20h]; Src
0x14005a97d  mov     r8, rbx; Size
0x14005a980  mov     rcx, [r15+70h]; void *
0x14005a984  call    memmove
0x14005a989  mov     [r15+38h], rbx
0x14005a98d  lea     rbx, [r14+40h]
0x14005a991  mov     rdi, [rdi+20h]
0x14005a995  call    cs:__imp_KeEnterCriticalRegion
0x14005a99c  nop     dword ptr [rax+rax+00h]
0x14005a9a1  mov     rcx, rbx; FastMutex
0x14005a9a4  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14005a9ab  nop     dword ptr [rax+rax+00h]
0x14005a9b0  mov     r10d, [rdi+4]
0x14005a9b4  mov     [rsp+0D8h+arg_8], rbx
0x14005a9bc  mov     bl, 1
0x14005a9be  test    r10d, r10d
0x14005a9c1  jnz     short loc_14005A9D6
0x14005a9c3  movzx   eax, r12w
0x14005a9c7  cmp     [rax+r14+258h], r10b
0x14005a9cf  jnz     short loc_14005A9D6
0x14005a9d1  xor     dil, dil
0x14005a9d4  jmp     short loc_14005A9D9
0x14005a9d6  mov     dil, bl
0x14005a9d9  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a9e0  lea     rsi, WPP_GLOBAL_Control
0x14005a9e7  cmp     rcx, rsi
0x14005a9ea  jz      short loc_14005A9FD
0x14005a9ec  mov     eax, [rcx+2Ch]
0x14005a9ef  test    bl, al
0x14005a9f1  jz      short loc_14005A9FD
0x14005a9f3  cmp     byte ptr [rcx+29h], 4
0x14005a9f7  jb      short loc_14005A9FD
0x14005a9f9  mov     dl, bl
0x14005a9fb  jmp     short loc_14005A9FF
0x14005a9fd  xor     dl, dl
0x14005a9ff  lea     rbp, WPP_RECORDER_INITIALIZED
0x14005aa06  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14005aa0d  setnz   r8b
0x14005aa11  test    dl, dl
0x14005aa13  jnz     short loc_14005AA20
0x14005aa15  test    r8b, r8b
0x14005aa18  jnz     short loc_14005AA20
0x14005aa1a  movzx   r13d, r12w
0x14005aa1e  jmp     short loc_14005AA56
0x14005aa20  mov     [rsp+0D8h+var_78], r14
0x14005aa25  movzx   r13d, r12w
0x14005aa29  movzx   r9d, dil
0x14005aa2d  movzx   eax, byte ptr [r14+r13+258h]
0x14005aa36  mov     [rsp+0D8h+var_80], eax
0x14005aa3a  mov     [rsp+0D8h+var_88], r10d
0x14005aa3f  mov     [rsp+0D8h+var_90], r9d
0x14005aa44  mov     r9, [rcx+40h]
0x14005aa48  mov     rcx, [rcx+18h]
0x14005aa4c  mov     [rsp+0D8h+var_98], r13d
0x14005aa51  call    WPP_RECORDER_AND_TRACE_SF_Llllq
0x14005aa56  test    dil, dil
0x14005aa59  jz      loc_14005AAED
0x14005aa5f  mov     r8, [r15+70h]
0x14005aa63  mov     edx, r12d
0x14005aa66  mov     rcx, r14
0x14005aa69  call    ?GetImmediateStatusUpdate@SidebandAudioWdmEndpoint@@AEAAJW4StatusUpdateType@@PEAU_SIDEBANDAUDIO_STATUS_PARAMS_HEADER@@@Z; SidebandAudioWdmEndpoint::GetImmediateStatusUpdate(StatusUpdateType,_SIDEBANDAUDIO_STATUS_PARAMS_HEADER *)
0x14005aa6e  mov     [rsp+0D8h+var_68], eax
0x14005aa72  mov     edi, eax
0x14005aa74  test    eax, eax
0x14005aa76  jns     loc_14005AB16
0x14005aa7c  mov     rcx, cs:WPP_GLOBAL_Control
0x14005aa83  cmp     rcx, rsi
0x14005aa86  jz      short loc_14005AA95
0x14005aa88  mov     eax, [rcx+2Ch]
0x14005aa8b  test    al, 2
0x14005aa8d  jz      short loc_14005AA95
0x14005aa8f  cmp     byte ptr [rcx+29h], 2
0x14005aa93  jnb     short loc_14005AA97
0x14005aa95  xor     bl, bl
0x14005aa97  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14005aa9e  setnz   r8b
0x14005aaa2  test    bl, bl
0x14005aaa4  jnz     short loc_14005AAAB
0x14005aaa6  test    r8b, r8b
0x14005aaa9  jz      short loc_14005AADE
0x14005aaab  mov     r9, [rcx+40h]
0x14005aaaf  lea     rax, WPP_82bfadf91fc73c4f22c211ed6841aba6_Traceguids
0x14005aab6  mov     rcx, [rcx+18h]
0x14005aaba  mov     dl, bl
0x14005aabc  mov     [rsp+0D8h+var_98], edi
0x14005aac0  mov     [rsp+0D8h+var_A0], rax
0x14005aac5  mov     [rsp+0D8h+var_A8], 35h ; '5'
0x14005aacc  mov     [rsp+0D8h+var_B0], 2
0x14005aad4  mov     [rsp+0D8h+var_B8], 2
0x14005aad9  call    WPP_RECORDER_AND_TRACE_SF_d
0x14005aade  lea     rcx, [rsp+0D8h+arg_8]
0x14005aae6  call    ??1?$unique_storage@U?$resource_policy@PEAU_FAST_MUTEX@@$$A6AXPEAU1@@_E$1?release_fast_mutex_with_critical_region@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14005aaeb  jmp     short loc_14005AB25
0x14005aaed  lea     rcx, [rsp+0D8h+var_68]; this
0x14005aaf2  call    ?Detach@CompletableIrp@@QEAAPEAU_IRP@@XZ; CompletableIrp::Detach(void)
0x14005aaf7  mov     rdx, rax
0x14005aafa  movzx   eax, r13w
0x14005aafe  lea     rcx, [rax+rax*4]
0x14005ab02  shl     rcx, 4
0x14005ab06  add     rcx, 78h ; 'x'
0x14005ab0a  add     rcx, r14
0x14005ab0d  call    IoQueue_AddEx
0x14005ab12  mov     [r15+78h], r14
0x14005ab16  lea     rcx, [rsp+0D8h+arg_8]
0x14005ab1e  call    ??1?$unique_storage@U?$resource_policy@PEAU_FAST_MUTEX@@$$A6AXPEAU1@@_E$1?release_fast_mutex_with_critical_region@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14005ab23  xor     edi, edi
0x14005ab25  lea     rcx, [rsp+0D8h+var_68]; this
0x14005ab2a  call    ??1CompletableIrp@@QEAA@XZ; CompletableIrp::~CompletableIrp(void)
0x14005ab2f  mov     eax, edi
0x14005ab31  add     rsp, 98h
0x14005ab38  pop     r15
0x14005ab3a  pop     r14
0x14005ab3c  pop     r13
0x14005ab3e  pop     r12
0x14005ab40  pop     rdi
0x14005ab41  pop     rsi
0x14005ab42  pop     rbp
0x14005ab43  pop     rbx
0x14005ab44  retn
```
