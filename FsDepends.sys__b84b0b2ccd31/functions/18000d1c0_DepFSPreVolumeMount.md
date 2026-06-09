# DepFSPreVolumeMount

- ea: `0x18000d1c0`
- end: `0x18000d506`
- name: `DepFSPreVolumeMount`
- size: `838`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800010fc`
- `0x180001150`
- `0x180001ad0`
- `0x180001b30`
- `0x18000d1c0`
- `0x18000e88c`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x18000d499`
- `ntoskrnl!ObfDereferenceObject` at `0x18000d4af`
- `ntoskrnl!ObfDereferenceObject` at `0x18000d499`
- `ntoskrnl!ObfDereferenceObject` at `0x18000d4af`
- `FLTMGR!FltFreeGenericWorkItem` at `0x18000d43b`
- `FLTMGR!FltFreeGenericWorkItem` at `0x18000d43b`
- `FLTMGR!FltGetDiskDeviceObject` at `0x18000d3a6`
- `FLTMGR!FltGetDiskDeviceObject` at `0x18000d3a6`
- `FLTMGR!FltGetDeviceObject` at `0x18000d2fa`
- `FLTMGR!FltGetDeviceObject` at `0x18000d2fa`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x18000d286`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x18000d286`

## pseudocode

```c
__int64 __fastcall DepFSPreVolumeMount(__int64 a1, __int64 a2, struct _FLT_GENERIC_WORKITEM **a3)
{
  unsigned int v6; // esi
  PDEVICE_OBJECT v7; // rcx
  __int64 v8; // rdx
  struct _FLT_GENERIC_WORKITEM *GenericWorkItem; // rdi
  NTSTATUS v10; // r8d
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  ULONG DeviceType; // ecx
  PDEVICE_OBJECT v14; // rcx
  __int64 v15; // rdx
  NTSTATUS v16; // eax
  __int64 v17; // rdx
  int v18; // eax
  PDEVICE_OBJECT DeviceObject; // [rsp+40h] [rbp-48h] BYREF
  PDEVICE_OBJECT DiskDeviceObject; // [rsp+A8h] [rbp+20h] BYREF

  DiskDeviceObject = 0;
  DeviceObject = 0;
  v6 = 1;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqq(
      WPP_GLOBAL_Control->AttachedDevice,
      28,
      WPP_bc64936b77293105c4440102cf4189d6_Traceguids,
      a1,
      *(_QWORD *)(a2 + 32),
      *(_QWORD *)(a2 + 16));
  }
  if ( byte_180005194 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v8 = 29;
LABEL_46:
      WPP_SF_qq(
        v7->AttachedDevice,
        v8,
        WPP_bc64936b77293105c4440102cf4189d6_Traceguids,
        *(_QWORD *)(a2 + 16),
        *(_QWORD *)(a2 + 24));
      goto LABEL_47;
    }
    goto LABEL_47;
  }
  if ( !byte_180005195 && !byte_180005196 )
  {
    GenericWorkItem = FltAllocateGenericWorkItem();
    if ( !GenericWorkItem )
    {
      *(_DWORD *)(a1 + 24) = -1073741670;
      v6 = 4;
      *(_QWORD *)(a1 + 32) = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          31,
          WPP_bc64936b77293105c4440102cf4189d6_Traceguids,
          *(_QWORD *)(a2 + 16),
          -1073741670);
      }
      goto LABEL_47;
    }
    v10 = FltGetDeviceObject(*(PFLT_VOLUME *)(a2 + 16), &DeviceObject);
    if ( v10 < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_40;
      }
      v12 = 32;
      goto LABEL_22;
    }
    DeviceType = DeviceObject->DeviceType;
    if ( DeviceType - 7 <= 1 || DeviceType == 36 )
    {
      v16 = FltGetDiskDeviceObject(*(PFLT_VOLUME *)(a2 + 16), &DiskDeviceObject);
      v10 = v16;
      if ( v16 < 0 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_40;
        }
        v12 = 34;
LABEL_22:
        WPP_SF_qD(v11->AttachedDevice, v12, WPP_bc64936b77293105c4440102cf4189d6_Traceguids, *(_QWORD *)(a2 + 16), v10);
        goto LABEL_40;
      }
      v18 = DepFSCheckDependencies(DiskDeviceObject, v17, (unsigned int)v16);
      if ( v18 >= 0 )
      {
        v6 = 0;
        *a3 = GenericWorkItem;
        goto LABEL_47;
      }
      *(_DWORD *)(a1 + 24) = v18;
      v6 = 4;
      *(_QWORD *)(a1 + 32) = 0;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
LABEL_40:
        FltFreeGenericWorkItem(GenericWorkItem);
        goto LABEL_47;
      }
      v15 = 35;
    }
    else
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_40;
      }
      v15 = 33;
    }
    WPP_SF_qq(
      v14->AttachedDevice,
      v15,
      WPP_bc64936b77293105c4440102cf4189d6_Traceguids,
      *(_QWORD *)(a2 + 16),
      *(_QWORD *)(a2 + 24));
    goto LABEL_40;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v8 = 30;
    goto LABEL_46;
  }
LABEL_47:
  if ( DiskDeviceObject )
    ObfDereferenceObject(DiskDeviceObject);
  if ( DeviceObject )
    ObfDereferenceObject(DeviceObject);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqqD(
      WPP_GLOBAL_Control->AttachedDevice,
      *(_QWORD *)(a2 + 32),
      a3,
      a1,
      *(_QWORD *)(a2 + 32),
      *(_QWORD *)(a2 + 16),
      v6);
  }
  return v6;
}

```

## disassembly

```asm
0x18000d1c0  mov     r11, rsp
0x18000d1c3  push    rbx
0x18000d1c4  push    rbp
0x18000d1c5  push    rsi
0x18000d1c6  push    rdi
0x18000d1c7  push    r13
0x18000d1c9  push    r14
0x18000d1cb  sub     rsp, 58h
0x18000d1cf  mov     r14, r8
0x18000d1d2  mov     qword ptr [r11+20h], 0
0x18000d1da  mov     rbx, rdx
0x18000d1dd  mov     qword ptr [r11-48h], 0
0x18000d1e5  mov     rbp, rcx
0x18000d1e8  mov     esi, 1
0x18000d1ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d1f4  lea     r13, WPP_GLOBAL_Control
0x18000d1fb  cmp     rcx, r13
0x18000d1fe  jz      short loc_18000D233
0x18000d200  mov     eax, [rcx+2Ch]
0x18000d203  test    al, 10h
0x18000d205  jz      short loc_18000D233
0x18000d207  cmp     byte ptr [rcx+29h], 4
0x18000d20b  jb      short loc_18000D233
0x18000d20d  mov     rax, [rbx+10h]
0x18000d211  lea     edx, [rsi+1Bh]
0x18000d214  mov     rcx, [rcx+18h]
0x18000d218  lea     r8, WPP_bc64936b77293105c4440102cf4189d6_Traceguids
0x18000d21f  mov     [r11-60h], rax
0x18000d223  mov     r9, rbp
0x18000d226  mov     rax, [rbx+20h]
0x18000d22a  mov     [r11-68h], rax
0x18000d22e  call    WPP_SF_qqq
0x18000d233  cmp     cs:byte_180005194, 0
0x18000d23a  jz      short loc_18000D26C
0x18000d23c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d243  cmp     rcx, r13
0x18000d246  jz      loc_18000D48C
0x18000d24c  mov     eax, [rcx+2Ch]
0x18000d24f  test    sil, al
0x18000d252  jz      loc_18000D48C
0x18000d258  cmp     byte ptr [rcx+29h], 2
0x18000d25c  jb      loc_18000D48C
0x18000d262  mov     edx, 1Dh
0x18000d267  jmp     loc_18000D46F
0x18000d26c  cmp     cs:byte_180005195, 0
0x18000d273  jnz     loc_18000D450
0x18000d279  cmp     cs:byte_180005196, 0
0x18000d280  jnz     loc_18000D450
0x18000d286  call    cs:__imp_FltAllocateGenericWorkItem
0x18000d28d  nop     dword ptr [rax+rax+00h]
0x18000d292  mov     rdi, rax
0x18000d295  test    rax, rax
0x18000d298  jnz     short loc_18000D2F1
0x18000d29a  mov     dword ptr [rbp+18h], 0C000009Ah
0x18000d2a1  lea     esi, [rax+4]
0x18000d2a4  mov     [rbp+20h], rax
0x18000d2a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d2af  cmp     rcx, r13
0x18000d2b2  jz      loc_18000D48C
0x18000d2b8  mov     eax, [rcx+2Ch]
0x18000d2bb  test    al, 1
0x18000d2bd  jz      loc_18000D48C
0x18000d2c3  cmp     byte ptr [rcx+29h], 2
0x18000d2c7  jb      loc_18000D48C
0x18000d2cd  mov     r9, [rbx+10h]
0x18000d2d1  lea     edx, [rdi+1Fh]
0x18000d2d4  mov     rcx, [rcx+18h]
0x18000d2d8  lea     r8, WPP_bc64936b77293105c4440102cf4189d6_Traceguids
0x18000d2df  mov     dword ptr [rsp+88h+var_68], 0C000009Ah
0x18000d2e7  call    WPP_SF_qD
0x18000d2ec  jmp     loc_18000D48C
0x18000d2f1  mov     rcx, [rbx+10h]; Volume
0x18000d2f5  lea     rdx, [rsp+88h+DeviceObject]; DeviceObject
0x18000d2fa  call    cs:__imp_FltGetDeviceObject
0x18000d301  nop     dword ptr [rax+rax+00h]
0x18000d306  mov     r8d, eax
0x18000d309  test    eax, eax
0x18000d30b  jns     short loc_18000D356
0x18000d30d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d314  cmp     rcx, r13
0x18000d317  jz      loc_18000D438
0x18000d31d  mov     eax, [rcx+2Ch]
0x18000d320  test    sil, al
0x18000d323  jz      loc_18000D438
0x18000d329  cmp     byte ptr [rcx+29h], 2
0x18000d32d  jb      loc_18000D438
0x18000d333  mov     edx, 20h ; ' '
0x18000d338  mov     r9, [rbx+10h]
0x18000d33c  mov     rcx, [rcx+18h]
0x18000d340  mov     dword ptr [rsp+88h+var_68], r8d
0x18000d345  lea     r8, WPP_bc64936b77293105c4440102cf4189d6_Traceguids
0x18000d34c  call    WPP_SF_qD
0x18000d351  jmp     loc_18000D438
0x18000d356  mov     rax, [rsp+88h+DeviceObject]
0x18000d35b  mov     ecx, [rax+48h]
0x18000d35e  lea     eax, [rcx-7]
0x18000d361  cmp     eax, esi
0x18000d363  jbe     short loc_18000D39A
0x18000d365  cmp     ecx, 24h ; '$'
0x18000d368  jz      short loc_18000D39A
0x18000d36a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d371  cmp     rcx, r13
0x18000d374  jz      loc_18000D438
0x18000d37a  mov     eax, [rcx+2Ch]
0x18000d37d  test    sil, al
0x18000d380  jz      loc_18000D438
0x18000d386  cmp     byte ptr [rcx+29h], 2
0x18000d38a  jb      loc_18000D438
0x18000d390  mov     edx, 21h ; '!'
0x18000d395  jmp     loc_18000D41B
0x18000d39a  mov     rcx, [rbx+10h]; Volume
0x18000d39e  lea     rdx, [rsp+88h+DiskDeviceObject]; DiskDeviceObject
0x18000d3a6  call    cs:__imp_FltGetDiskDeviceObject
0x18000d3ad  nop     dword ptr [rax+rax+00h]
0x18000d3b2  mov     r8d, eax
0x18000d3b5  test    eax, eax
0x18000d3b7  jns     short loc_18000D3DD
0x18000d3b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d3c0  cmp     rcx, r13
0x18000d3c3  jz      short loc_18000D438
0x18000d3c5  mov     eax, [rcx+2Ch]
0x18000d3c8  test    sil, al
0x18000d3cb  jz      short loc_18000D438
0x18000d3cd  cmp     byte ptr [rcx+29h], 2
0x18000d3d1  jb      short loc_18000D438
0x18000d3d3  mov     edx, 22h ; '"'
0x18000d3d8  jmp     loc_18000D338
0x18000d3dd  mov     rcx, [rsp+88h+DiskDeviceObject]
0x18000d3e5  call    DepFSCheckDependencies
0x18000d3ea  test    eax, eax
0x18000d3ec  jns     short loc_18000D449
0x18000d3ee  mov     [rbp+18h], eax
0x18000d3f1  mov     esi, 4
0x18000d3f6  mov     qword ptr [rbp+20h], 0
0x18000d3fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d405  cmp     rcx, r13
0x18000d408  jz      short loc_18000D438
0x18000d40a  mov     eax, [rcx+2Ch]
0x18000d40d  test    sil, al
0x18000d410  jz      short loc_18000D438
0x18000d412  cmp     [rcx+29h], sil
0x18000d416  jb      short loc_18000D438
0x18000d418  lea     edx, [rsi+1Fh]
0x18000d41b  mov     rax, [rbx+18h]
0x18000d41f  lea     r8, WPP_bc64936b77293105c4440102cf4189d6_Traceguids
0x18000d426  mov     r9, [rbx+10h]
0x18000d42a  mov     rcx, [rcx+18h]
0x18000d42e  mov     [rsp+88h+var_68], rax
0x18000d433  call    WPP_SF_qq
0x18000d438  mov     rcx, rdi; FltWorkItem
0x18000d43b  call    cs:__imp_FltFreeGenericWorkItem
0x18000d442  nop     dword ptr [rax+rax+00h]
0x18000d447  jmp     short loc_18000D48C
0x18000d449  xor     esi, esi
0x18000d44b  mov     [r14], rdi
0x18000d44e  jmp     short loc_18000D48C
0x18000d450  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d457  cmp     rcx, r13
0x18000d45a  jz      short loc_18000D48C
0x18000d45c  mov     eax, [rcx+2Ch]
0x18000d45f  test    sil, al
0x18000d462  jz      short loc_18000D48C
0x18000d464  cmp     byte ptr [rcx+29h], 2
0x18000d468  jb      short loc_18000D48C
0x18000d46a  mov     edx, 1Eh
0x18000d46f  mov     rax, [rbx+18h]
0x18000d473  lea     r8, WPP_bc64936b77293105c4440102cf4189d6_Traceguids
0x18000d47a  mov     r9, [rbx+10h]
0x18000d47e  mov     rcx, [rcx+18h]
0x18000d482  mov     [rsp+88h+var_68], rax
0x18000d487  call    WPP_SF_qq
0x18000d48c  mov     rcx, [rsp+88h+DiskDeviceObject]; Object
0x18000d494  test    rcx, rcx
0x18000d497  jz      short loc_18000D4A5
0x18000d499  call    cs:__imp_ObfDereferenceObject
0x18000d4a0  nop     dword ptr [rax+rax+00h]
0x18000d4a5  mov     rcx, [rsp+88h+DeviceObject]; Object
0x18000d4aa  test    rcx, rcx
0x18000d4ad  jz      short loc_18000D4BB
0x18000d4af  call    cs:__imp_ObfDereferenceObject
0x18000d4b6  nop     dword ptr [rax+rax+00h]
0x18000d4bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d4c2  cmp     rcx, r13
0x18000d4c5  jz      short loc_18000D4F6
0x18000d4c7  mov     eax, [rcx+2Ch]
0x18000d4ca  test    al, 10h
0x18000d4cc  jz      short loc_18000D4F6
0x18000d4ce  cmp     byte ptr [rcx+29h], 4
0x18000d4d2  jb      short loc_18000D4F6
0x18000d4d4  mov     rdx, [rbx+10h]
0x18000d4d8  mov     r9, rbp
0x18000d4db  mov     rcx, [rcx+18h]
0x18000d4df  mov     [rsp+88h+var_58], esi
0x18000d4e3  mov     [rsp+88h+var_60], rdx
0x18000d4e8  mov     rdx, [rbx+20h]
0x18000d4ec  mov     [rsp+88h+var_68], rdx
0x18000d4f1  call    WPP_SF_qqqD
0x18000d4f6  mov     eax, esi
0x18000d4f8  add     rsp, 58h
0x18000d4fc  pop     r14
0x18000d4fe  pop     r13
0x18000d500  pop     rdi
0x18000d501  pop     rsi
0x18000d502  pop     rbp
0x18000d503  pop     rbx
0x18000d504  retn
```
