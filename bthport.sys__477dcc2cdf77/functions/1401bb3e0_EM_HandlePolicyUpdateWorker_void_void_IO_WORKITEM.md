# EM_HandlePolicyUpdateWorker(void *,void *,_IO_WORKITEM *)

- ea: `0x1401bb3e0`
- end: `0x1401bb578`
- name: `?EM_HandlePolicyUpdateWorker@@YAXPEAX0PEAU_IO_WORKITEM@@@Z`
- size: `408`
- prototype: `IO_WORKITEM_ROUTINE_EX`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x140005608`
- `0x140005690`
- `0x14000abf4`
- `0x140028c24`
- `0x14002a2c4`
- `0x14002a354`
- `0x14002a4f4`
- `0x1400803b4`
- `0x14013006c`
- `0x140164cec`
- `0x1401bb3e0`

## import_xrefs

- `ntoskrnl!IoFreeWorkItem` at `0x1401bb55e`
- `ntoskrnl!IoFreeWorkItem` at `0x1401bb55e`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1401bb54f`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1401bb54f`

## pseudocode

```c
void __fastcall EM_HandlePolicyUpdateWorker(
        struct _DEVICE_OBJECT *IoObject,
        struct DEVICE_EXTENSION *Context,
        PIO_WORKITEM IoWorkItem)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  char v9; // bl
  __int16 DeviceType; // ax
  int v11; // eax
  int v12; // edx
  int v13; // r8d
  char v14; // si
  Fdo *v15; // rax
  RadioStateManager *RadioStateManager; // rax
  struct HCI_INTERFACE *v17; // rcx
  int v18; // edx
  int v19; // r8d
  __int16 v20; // ax

  if ( !(unsigned int)Feature_59215879__private_IsEnabledDeviceUsageNoInline() )
    Context = Fdo::GetDevExtFromWdmDevice(IoObject);
  v9 = 1;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) == 0 || (LOBYTE(v6) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    LOBYTE(v6) = 0;
  DeviceType = WPP_GLOBAL_Control->DeviceType;
  LOBYTE(v8) = DeviceType != 0;
  if ( (_BYTE)v6 || DeviceType )
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v6,
      v8,
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      12,
      33,
      (__int64)WPP_f44453fc40fe39d84113d29c29467d77_Traceguids);
  EM_PrintPolicyConfiguration(v7, v6, v8);
  v11 = BthReportPoliciesUpdated();
  v14 = v11;
  if ( v11 < 0 )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) == 0 || (LOBYTE(v12) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
      LOBYTE(v12) = 0;
    LOBYTE(v13) = 1;
    WPP_RECORDER_AND_TRACE_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      v12,
      v13,
      WPP_GLOBAL_Control->DeviceExtension,
      3,
      12,
      34,
      (__int64)WPP_f44453fc40fe39d84113d29c29467d77_Traceguids,
      v11);
  }
  v15 = Fdo::FromDevExt(Context);
  RadioStateManager = Fdo::GetRadioStateManager(v15);
  RadioStateManager::OnPotentialPolicyUpdate(RadioStateManager);
  HciLEAdv_ApplyAdvertisingPolicy(v17);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
    v9 = 0;
  v20 = WPP_GLOBAL_Control->DeviceType;
  if ( v9 || v20 )
  {
    LOBYTE(v18) = v9;
    LOBYTE(v19) = v20 != 0;
    WPP_RECORDER_AND_TRACE_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      v18,
      v19,
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      12,
      35,
      (__int64)WPP_f44453fc40fe39d84113d29c29467d77_Traceguids,
      v14);
  }
  IoReleaseRemoveLockEx(&Context->RemoveLock, EM_HandlePolicyUpdateWorker, 0x20u);
  IoFreeWorkItem(IoWorkItem);
}

```

## disassembly

```asm
0x1401bb3e0  push    rbx
0x1401bb3e2  push    rbp
0x1401bb3e3  push    rsi
0x1401bb3e4  push    rdi
0x1401bb3e5  push    r13
0x1401bb3e7  push    r14
0x1401bb3e9  sub     rsp, 58h
0x1401bb3ed  mov     rbp, r8
0x1401bb3f0  mov     rdi, rdx
0x1401bb3f3  mov     rbx, rcx
0x1401bb3f6  call    Feature_59215879__private_IsEnabledDeviceUsageNoInline
0x1401bb3fb  xor     r14d, r14d
0x1401bb3fe  test    eax, eax
0x1401bb400  jnz     short loc_1401BB40D
0x1401bb402  mov     rcx, rbx; struct _DEVICE_OBJECT *
0x1401bb405  call    ?GetDevExtFromWdmDevice@Fdo@@SAPEAUDEVICE_EXTENSION@@PEAU_DEVICE_OBJECT@@@Z; Fdo::GetDevExtFromWdmDevice(_DEVICE_OBJECT *)
0x1401bb40a  mov     rdi, rax
0x1401bb40d  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401bb414  mov     bl, 1
0x1401bb416  test    dword ptr [r10+2Ch], 800h
0x1401bb41e  jz      short loc_1401BB429
0x1401bb420  cmp     byte ptr [r10+29h], 5
0x1401bb425  mov     dl, bl
0x1401bb427  jnb     short loc_1401BB42C
0x1401bb429  mov     dl, r14b
0x1401bb42c  movzx   eax, word ptr [r10+48h]
0x1401bb431  lea     r13, WPP_f44453fc40fe39d84113d29c29467d77_Traceguids
0x1401bb438  test    ax, ax
0x1401bb43b  setnz   r8b
0x1401bb43f  test    dl, dl
0x1401bb441  jnz     short loc_1401BB448
0x1401bb443  test    ax, ax
0x1401bb446  jz      short loc_1401BB46E
0x1401bb448  mov     r9, [r10+40h]
0x1401bb44c  mov     rcx, [r10+18h]
0x1401bb450  mov     [rsp+88h+var_50], r13
0x1401bb455  mov     [rsp+88h+var_58], 21h ; '!'
0x1401bb45c  mov     [rsp+88h+var_60], 0Ch
0x1401bb464  mov     [rsp+88h+var_68], 5
0x1401bb469  call    WPP_RECORDER_AND_TRACE_SF_
0x1401bb46e  call    EM_PrintPolicyConfiguration
0x1401bb473  call    BthReportPoliciesUpdated
0x1401bb478  mov     esi, eax
0x1401bb47a  test    eax, eax
0x1401bb47c  jns     short loc_1401BB4C8
0x1401bb47e  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401bb485  test    dword ptr [r10+2Ch], 800h
0x1401bb48d  jz      short loc_1401BB498
0x1401bb48f  cmp     byte ptr [r10+29h], 3
0x1401bb494  mov     dl, bl
0x1401bb496  jnb     short loc_1401BB49B
0x1401bb498  mov     dl, r14b
0x1401bb49b  mov     r9, [r10+40h]
0x1401bb49f  mov     r8b, bl
0x1401bb4a2  mov     rcx, [r10+18h]
0x1401bb4a6  mov     [rsp+88h+var_48], esi
0x1401bb4aa  mov     [rsp+88h+var_50], r13
0x1401bb4af  mov     [rsp+88h+var_58], 22h ; '"'
0x1401bb4b6  mov     [rsp+88h+var_60], 0Ch
0x1401bb4be  mov     [rsp+88h+var_68], 3
0x1401bb4c3  call    WPP_RECORDER_AND_TRACE_SF_d
0x1401bb4c8  mov     rcx, rdi; struct DEVICE_EXTENSION *
0x1401bb4cb  call    ?FromDevExt@Fdo@@SAAEAV1@PEAUDEVICE_EXTENSION@@@Z; Fdo::FromDevExt(DEVICE_EXTENSION *)
0x1401bb4d0  mov     rcx, rax; this
0x1401bb4d3  call    ?GetRadioStateManager@Fdo@@QEAAAEAVRadioStateManager@@XZ; Fdo::GetRadioStateManager(void)
0x1401bb4d8  mov     rcx, rax; this
0x1401bb4db  call    ?OnPotentialPolicyUpdate@RadioStateManager@@QEAAXXZ; RadioStateManager::OnPotentialPolicyUpdate(void)
0x1401bb4e0  call    ?HciLEAdv_ApplyAdvertisingPolicy@@YAXPEAUHCI_INTERFACE@@@Z; HciLEAdv_ApplyAdvertisingPolicy(HCI_INTERFACE *)
0x1401bb4e5  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401bb4ec  test    dword ptr [rcx+2Ch], 800h
0x1401bb4f3  jz      short loc_1401BB4FB
0x1401bb4f5  cmp     byte ptr [rcx+29h], 5
0x1401bb4f9  jnb     short loc_1401BB4FE
0x1401bb4fb  mov     bl, r14b
0x1401bb4fe  movzx   eax, word ptr [rcx+48h]
0x1401bb502  test    ax, ax
0x1401bb505  setnz   r8b
0x1401bb509  test    bl, bl
0x1401bb50b  jnz     short loc_1401BB512
0x1401bb50d  test    ax, ax
0x1401bb510  jz      short loc_1401BB53E
0x1401bb512  mov     r9, [rcx+40h]
0x1401bb516  mov     dl, bl
0x1401bb518  mov     rcx, [rcx+18h]
0x1401bb51c  mov     [rsp+88h+var_48], esi
0x1401bb520  mov     [rsp+88h+var_50], r13
0x1401bb525  mov     [rsp+88h+var_58], 23h ; '#'
0x1401bb52c  mov     [rsp+88h+var_60], 0Ch
0x1401bb534  mov     [rsp+88h+var_68], 5
0x1401bb539  call    WPP_RECORDER_AND_TRACE_SF_d
0x1401bb53e  lea     rcx, [rdi+38h]; RemoveLock
0x1401bb542  mov     r8d, 20h ; ' '; RemlockSize
0x1401bb548  lea     rdx, ?EM_HandlePolicyUpdateWorker@@YAXPEAX0PEAU_IO_WORKITEM@@@Z; Tag
0x1401bb54f  call    cs:__imp_IoReleaseRemoveLockEx
0x1401bb556  nop     dword ptr [rax+rax+00h]
0x1401bb55b  mov     rcx, rbp; IoWorkItem
0x1401bb55e  call    cs:__imp_IoFreeWorkItem
0x1401bb565  nop     dword ptr [rax+rax+00h]
0x1401bb56a  add     rsp, 58h
0x1401bb56e  pop     r14
0x1401bb570  pop     r13
0x1401bb572  pop     rdi
0x1401bb573  pop     rsi
0x1401bb574  pop     rbp
0x1401bb575  pop     rbx
0x1401bb576  retn
```
