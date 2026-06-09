# VidHypercallDoorbellIoctlMap

- ea: `0x1400f7ef8`
- end: `0x1400f8220`
- name: `VidHypercallDoorbellIoctlMap`
- size: `808`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x140035708`

## callees

- `0x140021db0`
- `0x1400248f4`
- `0x140030990`
- `0x1400309d0`
- `0x1400386a0`
- `0x14008b65c`
- `0x1400f7ef8`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x1400f7fbf`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400f7fbf`
- `ntoskrnl!PsProcessType` at `0x1400f7fa9`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x1400f8060`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x1400f8060`
- `ntoskrnl!ZwClose` at `0x1400f81c9`
- `ntoskrnl!ZwClose` at `0x1400f81c9`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400f7f83`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400f7f83`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f81e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f81e2`
- `ntoskrnl!ExAllocatePool2` at `0x1400f7f6b`
- `ntoskrnl!ExAllocatePool2` at `0x1400f7f6b`
- `winhvr!WinHvGetPartitionProperty` at `0x1400f812b`
- `winhvr!WinHvGetPartitionProperty` at `0x1400f812b`

## pseudocode

```c
__int64 __fastcall VidHypercallDoorbellIoctlMap(__int64 a1, void *a2, _QWORD *a3)
{
  __int64 v3; // r13
  _QWORD *Pool2; // rdi
  _QWORD *v7; // rsi
  _QWORD *i; // rax
  void *CurrentProcess; // r12
  NTSTATUS PartitionProperty; // ebx
  _QWORD *v12; // rcx
  _QWORD *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // [rsp+40h] [rbp-10h] BYREF
  __int64 v16; // [rsp+90h] [rbp+40h] BYREF
  _QWORD *v17; // [rsp+A0h] [rbp+50h]
  HANDLE Handle; // [rsp+A8h] [rbp+58h] BYREF

  v17 = a3;
  v3 = a1 + 10864;
  v15 = 0;
  v16 = 0;
  Handle = 0;
  Pool2 = 0;
  VidLockAcquireExclusive(a1 + 10864);
  if ( (*(_DWORD *)(a1 + 32) & 0x800LL) != 0 )
  {
    v7 = (_QWORD *)(a1 + 10872);
    for ( i = *(_QWORD **)(a1 + 10872); i != v7; i = (_QWORD *)*i )
    {
      if ( (void *)i[2] == a2 )
      {
        if ( i )
        {
          VidTraceErrorInternal0(
            "VidHypercallDoorbellIoctlMap",
            "onecore\\vm\\vid\\sys\\driver\\vidhypercalldoorbell.c",
            293);
          PartitionProperty = -1073741436;
          goto LABEL_7;
        }
        break;
      }
    }
    Pool2 = (_QWORD *)ExAllocatePool2(256, 48, 1917084758);
    if ( Pool2 )
    {
      CurrentProcess = (void *)PsGetCurrentProcess();
      PartitionProperty = ObOpenObjectByPointer(
                            CurrentProcess,
                            0x200u,
                            0,
                            0x1FFFFFu,
                            (POBJECT_TYPE)PsProcessType,
                            0,
                            &Handle);
      if ( PartitionProperty >= 0 )
      {
        PartitionProperty = WinHvGetPartitionProperty(*(_QWORD *)(a1 + 648), 327698, &v15);
        if ( PartitionProperty >= 0 )
        {
          if ( (*(_DWORD *)(a1 + 16) & 0x8000LL) != 0 && (*((_DWORD *)VidDeviceExtension + 162) & 0x20) != 0 )
            (*((void (__fastcall **)(void *))VidDeviceExtension + 255))(CurrentProcess);
          PartitionProperty = VidHypercallDoorbellpMapPhysicalPagesToUserModeForExecute(v15, v14, &v16);
          if ( PartitionProperty >= 0 )
          {
            ObfReferenceObjectWithTag(a2, 0x72446456u);
            v12 = v17;
            Pool2[2] = a2;
            Pool2[4] = Handle;
            Handle = 0;
            Pool2[5] = CurrentProcess;
            Pool2[3] = v16;
            *v12 = v16;
            v13 = *(_QWORD **)(a1 + 10880);
            v16 = 0;
            if ( (_QWORD *)*v13 != v7 )
              __fastfail(3u);
            *Pool2 = v7;
            Pool2[1] = v13;
            *v13 = Pool2;
            *(_QWORD *)(a1 + 10880) = Pool2;
            Pool2 = 0;
            PartitionProperty = 0;
          }
          else
          {
            VidTraceErrorInternal0(
              "VidHypercallDoorbellIoctlMap",
              "onecore\\vm\\vid\\sys\\driver\\vidhypercalldoorbell.c",
              363);
          }
        }
        else
        {
          VidTraceErrorInternal0(
            "VidHypercallDoorbellIoctlMap",
            "onecore\\vm\\vid\\sys\\driver\\vidhypercalldoorbell.c",
            334);
        }
      }
      else
      {
        VidTraceErrorInternal0(
          "VidHypercallDoorbellIoctlMap",
          "onecore\\vm\\vid\\sys\\driver\\vidhypercalldoorbell.c",
          321);
      }
    }
    else
    {
      VidTraceErrorInternal0(
        "VidHypercallDoorbellIoctlMap",
        "onecore\\vm\\vid\\sys\\driver\\vidhypercalldoorbell.c",
        301);
      PartitionProperty = -1073741670;
    }
  }
  else
  {
    VidTraceErrorInternal0("VidHypercallDoorbellIoctlMap", "onecore\\vm\\vid\\sys\\driver\\vidhypercalldoorbell.c", 283);
    PartitionProperty = -1073741811;
  }
LABEL_7:
  if ( Handle )
    ZwClose(Handle);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x72446456u);
  VidLockRelease(v3);
  if ( PartitionProperty < 0 )
    VidTraceErrorStatusPartitionInternal0(
      (unsigned int)"VidHypercallDoorbellIoctlMap",
      (unsigned int)"onecore\\vm\\vid\\sys\\driver\\vidhypercalldoorbell.c",
      394,
      PartitionProperty,
      a1 + 656);
  return (unsigned int)PartitionProperty;
}

```

## disassembly

```asm
0x1400f7ef8  mov     [rsp-38h+arg_8], rbx
0x1400f7efd  mov     [rsp-38h+arg_10], r8
0x1400f7f02  push    rbp
0x1400f7f03  push    rsi
0x1400f7f04  push    rdi
0x1400f7f05  push    r12
0x1400f7f07  push    r13
0x1400f7f09  push    r14
0x1400f7f0b  push    r15
0x1400f7f0d  mov     rbp, rsp
0x1400f7f10  sub     rsp, 50h
0x1400f7f14  xor     ebx, ebx
0x1400f7f16  lea     r13, [rcx+2A70h]
0x1400f7f1d  mov     r14, rcx
0x1400f7f20  mov     [rbp+var_10], rbx
0x1400f7f24  mov     rcx, r13
0x1400f7f27  mov     [rbp+arg_0], rbx
0x1400f7f2b  mov     r15, rdx
0x1400f7f2e  mov     [rbp+arg_18], rbx
0x1400f7f32  mov     edi, ebx
0x1400f7f34  call    VidLockAcquireExclusive
0x1400f7f39  mov     eax, [r14+20h]
0x1400f7f3d  bt      rax, 0Bh
0x1400f7f42  jnb     loc_1400F80C3
0x1400f7f48  lea     rsi, [r14+2A78h]
0x1400f7f4f  mov     rax, [rsi]
0x1400f7f52  cmp     rax, rsi
0x1400f7f55  jnz     loc_1400F80E6
0x1400f7f5b  mov     edx, 30h ; '0'
0x1400f7f60  mov     ecx, 100h
0x1400f7f65  mov     r8d, 72446456h
0x1400f7f6b  call    cs:__imp_ExAllocatePool2
0x1400f7f72  nop     dword ptr [rax+rax+00h]
0x1400f7f77  mov     rdi, rax
0x1400f7f7a  test    rax, rax
0x1400f7f7d  jz      loc_1400F80F8
0x1400f7f83  call    cs:__imp_PsGetCurrentProcess
0x1400f7f8a  nop     dword ptr [rax+rax+00h]
0x1400f7f8f  mov     r9d, 1FFFFFh; DesiredAccess
0x1400f7f95  xor     r8d, r8d; PassedAccessState
0x1400f7f98  mov     r12, rax
0x1400f7f9b  mov     edx, 200h; HandleAttributes
0x1400f7fa0  lea     rax, [rbp+arg_18]
0x1400f7fa4  mov     [rsp+50h+Handle], rax; Handle
0x1400f7fa9  mov     rax, cs:__imp_PsProcessType
0x1400f7fb0  mov     [rsp+50h+AccessMode], bl; AccessMode
0x1400f7fb4  mov     rcx, [rax]
0x1400f7fb7  mov     [rsp+50h+ObjectType], rcx; ObjectType
0x1400f7fbc  mov     rcx, r12; Object
0x1400f7fbf  call    cs:__imp_ObOpenObjectByPointer
0x1400f7fc6  nop     dword ptr [rax+rax+00h]
0x1400f7fcb  mov     ebx, eax
0x1400f7fcd  test    eax, eax
0x1400f7fcf  jns     loc_1400F811B
0x1400f7fd5  mov     r8d, 141h
0x1400f7fdb  lea     rdx, aOnecoreVmVidSy_19; "onecore\\vm\\vid\\sys\\driver\\vidhyper"...
0x1400f7fe2  lea     rcx, aVidhypercalldo; "VidHypercallDoorbellIoctlMap"
0x1400f7fe9  call    VidTraceErrorInternal0
0x1400f7fee  mov     rcx, [rbp+arg_18]; Handle
0x1400f7ff2  test    rcx, rcx
0x1400f7ff5  jnz     loc_1400F81C9
0x1400f7ffb  test    rdi, rdi
0x1400f7ffe  jnz     loc_1400F81DA
0x1400f8004  mov     rcx, r13
0x1400f8007  call    VidLockRelease
0x1400f800c  test    ebx, ebx
0x1400f800e  js      loc_1400F81F3
0x1400f8014  mov     eax, ebx
0x1400f8016  mov     rbx, [rsp+50h+arg_8]
0x1400f801e  add     rsp, 50h
0x1400f8022  pop     r15
0x1400f8024  pop     r14
0x1400f8026  pop     r13
0x1400f8028  pop     r12
0x1400f802a  pop     rdi
0x1400f802b  pop     rsi
0x1400f802c  pop     rbp
0x1400f802d  retn
0x1400f802f  test    rax, rax
0x1400f8032  jz      loc_1400F7F5B
0x1400f8038  mov     r8d, 125h
0x1400f803e  lea     rdx, aOnecoreVmVidSy_19; "onecore\\vm\\vid\\sys\\driver\\vidhyper"...
0x1400f8045  lea     rcx, aVidhypercalldo; "VidHypercallDoorbellIoctlMap"
0x1400f804c  call    VidTraceErrorInternal0
0x1400f8051  mov     ebx, 0C0000184h
0x1400f8056  jmp     short loc_1400F7FEE
0x1400f8058  mov     edx, 72446456h; Tag
0x1400f805d  mov     rcx, r15; Object
0x1400f8060  call    cs:__imp_ObfReferenceObjectWithTag
0x1400f8067  nop     dword ptr [rax+rax+00h]
0x1400f806c  mov     rcx, [rbp+arg_10]
0x1400f8070  mov     [rdi+10h], r15
0x1400f8074  mov     rax, [rbp+arg_18]
0x1400f8078  mov     [rdi+20h], rax
0x1400f807c  mov     [rbp+arg_18], 0
0x1400f8084  mov     [rdi+28h], r12
0x1400f8088  mov     rax, [rbp+arg_0]
0x1400f808c  mov     [rdi+18h], rax
0x1400f8090  mov     rax, [rbp+arg_0]
0x1400f8094  mov     [rcx], rax
0x1400f8097  mov     rax, [rsi+8]
0x1400f809b  mov     [rbp+arg_0], 0
0x1400f80a3  cmp     [rax], rsi
0x1400f80a6  jnz     loc_1400F81C2
0x1400f80ac  mov     [rdi], rsi
0x1400f80af  mov     [rdi+8], rax
0x1400f80b3  mov     [rax], rdi
0x1400f80b6  mov     [rsi+8], rdi
0x1400f80ba  xor     edi, edi
0x1400f80bc  xor     ebx, ebx
0x1400f80be  jmp     loc_1400F7FEE
0x1400f80c3  mov     r8d, 11Bh
0x1400f80c9  lea     rdx, aOnecoreVmVidSy_19; "onecore\\vm\\vid\\sys\\driver\\vidhyper"...
0x1400f80d0  lea     rcx, aVidhypercalldo; "VidHypercallDoorbellIoctlMap"
0x1400f80d7  call    VidTraceErrorInternal0
0x1400f80dc  mov     ebx, 0C000000Dh
0x1400f80e1  jmp     loc_1400F7FEE
0x1400f80e6  cmp     [rax+10h], r15
0x1400f80ea  jz      loc_1400F802F
0x1400f80f0  mov     rax, [rax]
0x1400f80f3  jmp     loc_1400F7F52
0x1400f80f8  mov     r8d, 12Dh
0x1400f80fe  lea     rdx, aOnecoreVmVidSy_19; "onecore\\vm\\vid\\sys\\driver\\vidhyper"...
0x1400f8105  lea     rcx, aVidhypercalldo; "VidHypercallDoorbellIoctlMap"
0x1400f810c  call    VidTraceErrorInternal0
0x1400f8111  mov     ebx, 0C000009Ah
0x1400f8116  jmp     loc_1400F7FEE
0x1400f811b  mov     rcx, [r14+288h]
0x1400f8122  lea     r8, [rbp+var_10]
0x1400f8126  mov     edx, 50012h
0x1400f812b  call    cs:__imp_WinHvGetPartitionProperty
0x1400f8132  nop     dword ptr [rax+rax+00h]
0x1400f8137  mov     ebx, eax
0x1400f8139  test    eax, eax
0x1400f813b  jns     short loc_1400F815B
0x1400f813d  mov     r8d, 14Eh
0x1400f8143  lea     rdx, aOnecoreVmVidSy_19; "onecore\\vm\\vid\\sys\\driver\\vidhyper"...
0x1400f814a  lea     rcx, aVidhypercalldo; "VidHypercallDoorbellIoctlMap"
0x1400f8151  call    VidTraceErrorInternal0
0x1400f8156  jmp     loc_1400F7FEE
0x1400f815b  mov     eax, [r14+10h]
0x1400f815f  bt      rax, 0Fh
0x1400f8164  jnb     short loc_1400F818D
0x1400f8166  mov     rax, cs:VidDeviceExtension
0x1400f816d  mov     eax, [rax+288h]
0x1400f8173  test    al, 20h
0x1400f8175  jz      short loc_1400F818D
0x1400f8177  mov     rax, cs:VidDeviceExtension
0x1400f817e  mov     rcx, r12
0x1400f8181  mov     rax, [rax+7F8h]
0x1400f8188  call    _guard_dispatch_icall
0x1400f818d  mov     rcx, [rbp+var_10]
0x1400f8191  lea     r8, [rbp+arg_0]
0x1400f8195  call    VidHypercallDoorbellpMapPhysicalPagesToUserModeForExecute
0x1400f819a  mov     ebx, eax
0x1400f819c  test    eax, eax
0x1400f819e  jns     loc_1400F8058
0x1400f81a4  mov     r8d, 16Bh
0x1400f81aa  lea     rdx, aOnecoreVmVidSy_19; "onecore\\vm\\vid\\sys\\driver\\vidhyper"...
0x1400f81b1  lea     rcx, aVidhypercalldo; "VidHypercallDoorbellIoctlMap"
0x1400f81b8  call    VidTraceErrorInternal0
0x1400f81bd  jmp     loc_1400F7FEE
0x1400f81c2  mov     ecx, 3
0x1400f81c7  int     29h; Win8: RtlFailFast(ecx)
0x1400f81c9  call    cs:__imp_ZwClose
0x1400f81d0  nop     dword ptr [rax+rax+00h]
0x1400f81d5  jmp     loc_1400F7FFB
0x1400f81da  mov     edx, 72446456h; Tag
0x1400f81df  mov     rcx, rdi; P
0x1400f81e2  call    cs:__imp_ExFreePoolWithTag
0x1400f81e9  nop     dword ptr [rax+rax+00h]
0x1400f81ee  jmp     loc_1400F8004
0x1400f81f3  lea     rax, [r14+290h]
0x1400f81fa  mov     r9d, ebx
0x1400f81fd  mov     r8d, 18Ah
0x1400f8203  mov     [rsp+50h+ObjectType], rax
0x1400f8208  lea     rdx, aOnecoreVmVidSy_19; "onecore\\vm\\vid\\sys\\driver\\vidhyper"...
0x1400f820f  lea     rcx, aVidhypercalldo; "VidHypercallDoorbellIoctlMap"
0x1400f8216  call    VidTraceErrorStatusPartitionInternal0
0x1400f821b  jmp     loc_1400F8014
```
