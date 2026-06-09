# DepFSPostVolumeMount

- ea: `0x180001610`
- end: `0x180001a01`
- name: `DepFSPostVolumeMount`
- size: `1009`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800010fc`
- `0x180001150`
- `0x1800015a8`
- `0x180001610`
- `0x180001ad0`
- `0x180001ba4`
- `0x18000bb48`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x180001814`
- `ntoskrnl!KeGetCurrentIrql` at `0x180001814`
- `ntoskrnl!KeSetEvent` at `0x18000199d`
- `ntoskrnl!KeSetEvent` at `0x18000199d`
- `ntoskrnl!ObfDereferenceObject` at `0x180001928`
- `ntoskrnl!ObfDereferenceObject` at `0x18000193e`
- `ntoskrnl!ObfDereferenceObject` at `0x180001928`
- `ntoskrnl!ObfDereferenceObject` at `0x18000193e`
- `FLTMGR!FltFreeGenericWorkItem` at `0x180001912`
- `FLTMGR!FltFreeGenericWorkItem` at `0x180001912`
- `FLTMGR!FltQueueGenericWorkItem` at `0x180001849`
- `FLTMGR!FltQueueGenericWorkItem` at `0x180001849`
- `FLTMGR!FltGetDiskDeviceObject` at `0x1800017cb`
- `FLTMGR!FltGetDiskDeviceObject` at `0x1800017cb`
- `FLTMGR!FltGetDeviceObject` at `0x1800016f8`
- `FLTMGR!FltGetDeviceObject` at `0x1800016f8`

## pseudocode

```c
__int64 __fastcall DepFSPostVolumeMount(__int64 a1, __int64 Timer_high, struct _FLT_GENERIC_WORKITEM *a3)
{
  __int64 v4; // rbx
  NTSTATUS v6; // edi
  char v7; // si
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  ULONG DeviceType; // ecx
  PDEVICE_OBJECT DiskDeviceObject; // [rsp+60h] [rbp+8h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+70h] [rbp+18h] BYREF

  DiskDeviceObject = 0;
  v4 = Timer_high;
  DeviceObject = 0;
  v6 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqq(
      WPP_GLOBAL_Control->AttachedDevice,
      42,
      WPP_bc64936b77293105c4440102cf4189d6_Traceguids,
      a1,
      *(_QWORD *)(Timer_high + 32),
      *(_QWORD *)(Timer_high + 16));
  }
  if ( *(int *)(a1 + 24) >= 0 )
    goto LABEL_6;
  v7 = 1;
  if ( byte_180005194 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_45;
    }
    v9 = 43;
    goto LABEL_44;
  }
  if ( byte_180005195 || byte_180005196 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_45;
    }
    v9 = 44;
LABEL_44:
    WPP_SF_qq(
      v8->AttachedDevice,
      v9,
      WPP_bc64936b77293105c4440102cf4189d6_Traceguids,
      *(_QWORD *)(v4 + 16),
      *(_QWORD *)(v4 + 24));
    goto LABEL_45;
  }
  v6 = FltGetDeviceObject(*(PFLT_VOLUME *)(v4 + 16), &DeviceObject);
  if ( v6 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_45;
    Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (Timer_high & 1) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_45;
    v11 = 45;
    goto LABEL_19;
  }
  DeviceType = DeviceObject->DeviceType;
  if ( DeviceType - 7 > 1 && DeviceType != 36 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qq(
        WPP_GLOBAL_Control->AttachedDevice,
        46,
        WPP_bc64936b77293105c4440102cf4189d6_Traceguids,
        *(_QWORD *)(v4 + 16),
        *(_QWORD *)(v4 + 24));
    }
LABEL_6:
    v7 = 0;
    goto LABEL_45;
  }
  v6 = FltGetDiskDeviceObject(*(PFLT_VOLUME *)(v4 + 16), &DiskDeviceObject);
  if ( v6 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_45;
    }
    v11 = 47;
LABEL_19:
    WPP_SF_qD(v10->AttachedDevice, v11, WPP_bc64936b77293105c4440102cf4189d6_Traceguids, *(_QWORD *)(v4 + 16), v6);
    goto LABEL_45;
  }
  if ( KeGetCurrentIrql() != 2 )
  {
    v6 = DepFSForEachDependency(DiskDeviceObject);
    if ( v6 < 0 )
      goto LABEL_45;
    goto LABEL_6;
  }
  v6 = FltQueueGenericWorkItem(a3, Filter, DepFSDecrementActiveMountCountForVolume, DelayedWorkQueue, DiskDeviceObject);
  if ( v6 >= 0 )
  {
    DiskDeviceObject = 0;
    v7 = 0;
    goto LABEL_49;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qqD(
      WPP_GLOBAL_Control->AttachedDevice,
      48,
      WPP_bc64936b77293105c4440102cf4189d6_Traceguids,
      *(_QWORD *)(v4 + 16),
      *(_QWORD *)(v4 + 24),
      v6);
  }
LABEL_45:
  if ( a3 )
    FltFreeGenericWorkItem(a3);
  if ( DiskDeviceObject )
    ObfDereferenceObject(DiskDeviceObject);
LABEL_49:
  if ( DeviceObject )
    ObfDereferenceObject(DeviceObject);
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qq(
        WPP_GLOBAL_Control->AttachedDevice,
        49,
        WPP_bc64936b77293105c4440102cf4189d6_Traceguids,
        *(_QWORD *)(v4 + 16),
        *(_QWORD *)(v4 + 24));
    }
    KeSetEvent(&Event, 0, 0);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqqDD(WPP_GLOBAL_Control->AttachedDevice, Timer_high, a3, a1, *(_QWORD *)(v4 + 32), *(_QWORD *)(v4 + 16), v6);
  }
  return 0;
}

```

## disassembly

```asm
0x180001610  mov     r11, rsp
0x180001613  mov     [r11+10h], rbx
0x180001617  mov     [r11+20h], rbp
0x18000161b  push    rsi
0x18000161c  push    rdi
0x18000161d  push    r14
0x18000161f  sub     rsp, 40h
0x180001623  mov     rbp, r8
0x180001626  mov     qword ptr [r11+8], 0
0x18000162e  mov     rbx, rdx
0x180001631  mov     qword ptr [r11+18h], 0
0x180001639  mov     r14, rcx
0x18000163c  xor     edi, edi
0x18000163e  mov     rcx, cs:WPP_GLOBAL_Control
0x180001645  lea     rax, WPP_GLOBAL_Control
0x18000164c  cmp     rcx, rax
0x18000164f  jz      short loc_18000168B
0x180001651  mov     eax, [rcx+2Ch]
0x180001654  test    al, 10h
0x180001656  jz      short loc_180001684
0x180001658  cmp     byte ptr [rcx+29h], 4
0x18000165c  jb      short loc_180001684
0x18000165e  mov     rax, [rbx+10h]
0x180001662  lea     edx, [rdi+2Ah]
0x180001665  mov     rcx, [rcx+18h]
0x180001669  lea     r8, WPP_bc64936b77293105c4440102cf4189d6_Traceguids
0x180001670  mov     [r11-30h], rax
0x180001674  mov     r9, r14
0x180001677  mov     rax, [rbx+20h]
0x18000167b  mov     [r11-38h], rax
0x18000167f  call    WPP_SF_qqq
0x180001684  lea     rax, WPP_GLOBAL_Control
0x18000168b  cmp     [r14+18h], edi
0x18000168f  jl      short loc_180001699
0x180001691  xor     sil, sil
0x180001694  jmp     loc_18000190A
0x180001699  cmp     cs:byte_180005194, dil
0x1800016a0  mov     sil, 1
0x1800016a3  jz      short loc_1800016D5
0x1800016a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800016ac  cmp     rcx, rax
0x1800016af  jz      loc_18000190A
0x1800016b5  mov     eax, [rcx+2Ch]
0x1800016b8  test    sil, al
0x1800016bb  jz      loc_18000190A
0x1800016c1  cmp     byte ptr [rcx+29h], 2
0x1800016c5  jb      loc_18000190A
0x1800016cb  mov     edx, 2Bh ; '+'
0x1800016d0  jmp     loc_1800018ED
0x1800016d5  cmp     cs:byte_180005195, dil
0x1800016dc  jnz     loc_1800018CE
0x1800016e2  cmp     cs:byte_180005196, dil
0x1800016e9  jnz     loc_1800018CE
0x1800016ef  mov     rcx, [rbx+10h]; Volume
0x1800016f3  lea     rdx, [rsp+58h+DeviceObject]; DeviceObject
0x1800016f8  call    cs:__imp_FltGetDeviceObject
0x1800016ff  nop     dword ptr [rax+rax+00h]
0x180001704  mov     edi, eax
0x180001706  test    eax, eax
0x180001708  jns     short loc_180001759
0x18000170a  mov     rcx, cs:WPP_GLOBAL_Control
0x180001711  lea     rax, WPP_GLOBAL_Control
0x180001718  cmp     rcx, rax
0x18000171b  jz      loc_18000190A
0x180001721  mov     edx, [rcx+2Ch]
0x180001724  test    sil, dl
0x180001727  jz      loc_18000190A
0x18000172d  cmp     byte ptr [rcx+29h], 2
0x180001731  jb      loc_18000190A
0x180001737  mov     edx, 2Dh ; '-'
0x18000173c  mov     r9, [rbx+10h]
0x180001740  lea     r8, WPP_bc64936b77293105c4440102cf4189d6_Traceguids
0x180001747  mov     rcx, [rcx+18h]
0x18000174b  mov     dword ptr [rsp+58h+Context], edi
0x18000174f  call    WPP_SF_qD
0x180001754  jmp     loc_18000190A
0x180001759  mov     rax, [rsp+58h+DeviceObject]
0x18000175e  mov     ecx, [rax+48h]
0x180001761  lea     eax, [rcx-7]
0x180001764  cmp     eax, 1
0x180001767  jbe     short loc_1800017C2
0x180001769  cmp     ecx, 24h ; '$'
0x18000176c  jz      short loc_1800017C2
0x18000176e  mov     rcx, cs:WPP_GLOBAL_Control
0x180001775  lea     rax, WPP_GLOBAL_Control
0x18000177c  cmp     rcx, rax
0x18000177f  jz      loc_180001691
0x180001785  mov     eax, [rcx+2Ch]
0x180001788  test    sil, al
0x18000178b  jz      loc_180001691
0x180001791  cmp     byte ptr [rcx+29h], 2
0x180001795  jb      loc_180001691
0x18000179b  mov     rax, [rbx+18h]
0x18000179f  lea     r8, WPP_bc64936b77293105c4440102cf4189d6_Traceguids
0x1800017a6  mov     r9, [rbx+10h]
0x1800017aa  mov     edx, 2Eh ; '.'
0x1800017af  mov     rcx, [rcx+18h]
0x1800017b3  mov     [rsp+58h+Context], rax
0x1800017b8  call    WPP_SF_qq
0x1800017bd  jmp     loc_180001691
0x1800017c2  mov     rcx, [rbx+10h]; Volume
0x1800017c6  lea     rdx, [rsp+58h+DiskDeviceObject]; DiskDeviceObject
0x1800017cb  call    cs:__imp_FltGetDiskDeviceObject
0x1800017d2  nop     dword ptr [rax+rax+00h]
0x1800017d7  mov     edi, eax
0x1800017d9  test    eax, eax
0x1800017db  jns     short loc_180001814
0x1800017dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800017e4  lea     rax, WPP_GLOBAL_Control
0x1800017eb  cmp     rcx, rax
0x1800017ee  jz      loc_18000190A
0x1800017f4  mov     eax, [rcx+2Ch]
0x1800017f7  test    sil, al
0x1800017fa  jz      loc_18000190A
0x180001800  cmp     byte ptr [rcx+29h], 2
0x180001804  jb      loc_18000190A
0x18000180a  mov     edx, 2Fh ; '/'
0x18000180f  jmp     loc_18000173C
0x180001814  call    cs:__imp_KeGetCurrentIrql
0x18000181b  nop     dword ptr [rax+rax+00h]
0x180001820  cmp     al, 2
0x180001822  jnz     loc_1800018B9
0x180001828  mov     rax, [rsp+58h+DiskDeviceObject]
0x18000182d  lea     r8, DepFSDecrementActiveMountCountForVolume; WorkerRoutine
0x180001834  mov     rdx, cs:Filter; FltObject
0x18000183b  mov     r9d, 1; QueueType
0x180001841  mov     rcx, rbp; FltWorkItem
0x180001844  mov     [rsp+58h+Context], rax; Context
0x180001849  call    cs:__imp_FltQueueGenericWorkItem
0x180001850  nop     dword ptr [rax+rax+00h]
0x180001855  mov     edi, eax
0x180001857  test    eax, eax
0x180001859  js      short loc_18000186C
0x18000185b  mov     [rsp+58h+DiskDeviceObject], 0
0x180001864  xor     sil, sil
0x180001867  jmp     loc_180001934
0x18000186c  mov     rcx, cs:WPP_GLOBAL_Control
0x180001873  lea     rax, WPP_GLOBAL_Control
0x18000187a  cmp     rcx, rax
0x18000187d  jz      loc_18000190A
0x180001883  mov     eax, [rcx+2Ch]
0x180001886  test    sil, al
0x180001889  jz      short loc_18000190A
0x18000188b  cmp     byte ptr [rcx+29h], 2
0x18000188f  jb      short loc_18000190A
0x180001891  mov     rax, [rbx+18h]
0x180001895  lea     r8, WPP_bc64936b77293105c4440102cf4189d6_Traceguids
0x18000189c  mov     r9, [rbx+10h]
0x1800018a0  mov     edx, 30h ; '0'
0x1800018a5  mov     rcx, [rcx+18h]
0x1800018a9  mov     dword ptr [rsp+58h+var_30], edi
0x1800018ad  mov     [rsp+58h+Context], rax
0x1800018b2  call    WPP_SF_qqD
0x1800018b7  jmp     short loc_18000190A
0x1800018b9  mov     rcx, [rsp+58h+DiskDeviceObject]
0x1800018be  call    DepFSForEachDependency
0x1800018c3  mov     edi, eax
0x1800018c5  test    eax, eax
0x1800018c7  js      short loc_18000190A
0x1800018c9  jmp     loc_180001691
0x1800018ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800018d5  cmp     rcx, rax
0x1800018d8  jz      short loc_18000190A
0x1800018da  mov     eax, [rcx+2Ch]
0x1800018dd  test    sil, al
0x1800018e0  jz      short loc_18000190A
0x1800018e2  cmp     byte ptr [rcx+29h], 2
0x1800018e6  jb      short loc_18000190A
0x1800018e8  mov     edx, 2Ch ; ','
0x1800018ed  mov     rax, [rbx+18h]
0x1800018f1  lea     r8, WPP_bc64936b77293105c4440102cf4189d6_Traceguids
0x1800018f8  mov     r9, [rbx+10h]
0x1800018fc  mov     rcx, [rcx+18h]
0x180001900  mov     [rsp+58h+Context], rax
0x180001905  call    WPP_SF_qq
0x18000190a  test    rbp, rbp
0x18000190d  jz      short loc_18000191E
0x18000190f  mov     rcx, rbp; FltWorkItem
0x180001912  call    cs:__imp_FltFreeGenericWorkItem
0x180001919  nop     dword ptr [rax+rax+00h]
0x18000191e  mov     rcx, [rsp+58h+DiskDeviceObject]; Object
0x180001923  test    rcx, rcx
0x180001926  jz      short loc_180001934
0x180001928  call    cs:__imp_ObfDereferenceObject
0x18000192f  nop     dword ptr [rax+rax+00h]
0x180001934  mov     rcx, [rsp+58h+DeviceObject]; Object
0x180001939  test    rcx, rcx
0x18000193c  jz      short loc_18000194A
0x18000193e  call    cs:__imp_ObfDereferenceObject
0x180001945  nop     dword ptr [rax+rax+00h]
0x18000194a  test    sil, sil
0x18000194d  jz      short loc_1800019A9
0x18000194f  mov     rcx, cs:WPP_GLOBAL_Control
0x180001956  lea     rax, WPP_GLOBAL_Control
0x18000195d  cmp     rcx, rax
0x180001960  jz      short loc_180001991
0x180001962  mov     eax, [rcx+2Ch]
0x180001965  test    al, 1
0x180001967  jz      short loc_180001991
0x180001969  cmp     byte ptr [rcx+29h], 2
0x18000196d  jb      short loc_180001991
0x18000196f  mov     rax, [rbx+18h]
0x180001973  lea     r8, WPP_bc64936b77293105c4440102cf4189d6_Traceguids
0x18000197a  mov     r9, [rbx+10h]
0x18000197e  mov     edx, 31h ; '1'
0x180001983  mov     rcx, [rcx+18h]
0x180001987  mov     [rsp+58h+Context], rax
0x18000198c  call    WPP_SF_qq
0x180001991  xor     r8d, r8d; Wait
0x180001994  lea     rcx, Event; Event
0x18000199b  xor     edx, edx; Increment
0x18000199d  call    cs:__imp_KeSetEvent
0x1800019a4  nop     dword ptr [rax+rax+00h]
0x1800019a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800019b0  lea     rax, WPP_GLOBAL_Control
0x1800019b7  cmp     rcx, rax
0x1800019ba  jz      short loc_1800019EB
0x1800019bc  mov     eax, [rcx+2Ch]
0x1800019bf  test    al, 10h
0x1800019c1  jz      short loc_1800019EB
0x1800019c3  cmp     byte ptr [rcx+29h], 4
0x1800019c7  jb      short loc_1800019EB
0x1800019c9  mov     rax, [rbx+10h]
0x1800019cd  mov     r9, r14
0x1800019d0  mov     rcx, [rcx+18h]
0x1800019d4  mov     [rsp+58h+var_28], edi
0x1800019d8  mov     [rsp+58h+var_30], rax
0x1800019dd  mov     rax, [rbx+20h]
0x1800019e1  mov     [rsp+58h+Context], rax
0x1800019e6  call    WPP_SF_qqqDD
0x1800019eb  mov     rbx, [rsp+58h+arg_8]
0x1800019f0  xor     eax, eax
0x1800019f2  mov     rbp, [rsp+58h+arg_18]
0x1800019f7  add     rsp, 40h
0x1800019fb  pop     r14
0x1800019fd  pop     rdi
0x1800019fe  pop     rsi
0x1800019ff  retn
```
