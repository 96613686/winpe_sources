# BthUsb_ScoAllocTransferContextImpl(_DEVICE_EXTENSION *,ulong,ulong,_RESOURCE_QUEUE *)

- ea: `0x140004088`
- end: `0x1400045de`
- name: `?BthUsb_ScoAllocTransferContextImpl@@YAPEAU_SCO_USB_TRANSFER_CTX@@PEAU_DEVICE_EXTENSION@@KKPEAU_RESOURCE_QUEUE@@@Z`
- size: `1366`
- prototype: `struct _SCO_USB_TRANSFER_CTX *__fastcall(struct _DEVICE_EXTENSION *, unsigned int, unsigned int, struct _RESOURCE_QUEUE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1400045e4`

## callees

- `0x14000175c`
- `0x1400017d4`
- `0x140004088`
- `0x140006580`

## import_xrefs

- `ntoskrnl!IoAllocateIrp` at `0x140004192`
- `ntoskrnl!IoAllocateIrp` at `0x140004192`
- `ntoskrnl!IoAllocateMdl` at `0x140004385`
- `ntoskrnl!IoAllocateMdl` at `0x140004385`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400043e6`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400043e6`
- `ntoskrnl!IoFreeMdl` at `0x14000446e`
- `ntoskrnl!IoFreeMdl` at `0x14000446e`
- `ntoskrnl!IoFreeIrp` at `0x14000450d`
- `ntoskrnl!IoFreeIrp` at `0x14000450d`
- `ntoskrnl!ExAllocatePool2` at `0x140004135`
- `ntoskrnl!ExAllocatePool2` at `0x14000420f`
- `ntoskrnl!ExAllocatePool2` at `0x1400042c8`
- `ntoskrnl!ExAllocatePool2` at `0x140004415`
- `ntoskrnl!ExAllocatePool2` at `0x140004135`
- `ntoskrnl!ExAllocatePool2` at `0x14000420f`
- `ntoskrnl!ExAllocatePool2` at `0x1400042c8`
- `ntoskrnl!ExAllocatePool2` at `0x140004415`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000447f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400044f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004520`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000447f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400044f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004520`

## pseudocode

```c
struct _SCO_USB_TRANSFER_CTX *__fastcall BthUsb_ScoAllocTransferContextImpl(
        struct _DEVICE_EXTENSION *a1,
        unsigned int a2,
        unsigned int a3,
        struct _RESOURCE_QUEUE *a4)
{
  unsigned int v4; // ebp
  __int64 v6; // r14
  __int64 v7; // r15
  __int64 v8; // rsi
  unsigned __int64 v10; // rax
  unsigned int v11; // ebx
  char v12; // bl
  char v13; // di
  int v14; // edx
  int v15; // r8d
  int v16; // edx
  int v17; // r8d
  int v18; // edx
  int v19; // r8d
  __int64 Pool2; // rax
  int v21; // edx
  int v22; // r8d
  unsigned __int64 v23; // rax
  ULONG v24; // ebx
  int v25; // edx
  int v26; // r8d
  void *v27; // r12
  __int16 DeviceType; // ax
  struct _MDL *Mdl; // rax
  int v30; // edx
  int v31; // r8d
  struct _MDL *v32; // rbp
  __int64 v33; // rax
  int v34; // edx
  int v35; // r8d
  IRP *Irp; // [rsp+50h] [rbp-58h]
  PVOID P; // [rsp+58h] [rbp-50h]

  v4 = a2;
  v6 = 0;
  v7 = a3;
  v8 = a2;
  v10 = 12LL * a2;
  if ( v10 > 0xFFFFFFFF )
  {
    v12 = -107;
    v13 = 1;
    LOBYTE(a2) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      a2,
      a3,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      4,
      15,
      (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids);
  }
  else
  {
    v11 = v10 + 152;
    if ( (int)v10 + 152 >= (unsigned int)v10 )
    {
      P = (PVOID)ExAllocatePool2(64, v11, 1111642965);
      if ( P )
      {
        v13 = 1;
        Irp = IoAllocateIrp(a1->TopOfStack->StackSize + 1, 0);
        if ( Irp )
        {
          Pool2 = ExAllocatePool2(64, 168, 1111642965);
          v6 = Pool2;
          if ( Pool2 )
          {
            *(_DWORD *)Pool2 = 1129600339;
            *(_QWORD *)(Pool2 + 32) = a4;
            *(_QWORD *)(Pool2 + 64) = Irp;
            *(_QWORD *)(Pool2 + 72) = P;
            v23 = v8 * a1->Sco.MaxFrameSize;
            *(_DWORD *)(v6 + 84) = v11;
            *(_DWORD *)(v6 + 80) = v4;
            if ( v23 > 0xFFFFFFFF )
            {
              v12 = -107;
              LOBYTE(v21) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
              WPP_RECORDER_AND_TRACE_SF_(
                WPP_GLOBAL_Control->AttachedDevice,
                v21,
                v22,
                WPP_GLOBAL_Control->DeviceExtension,
                2,
                4,
                20,
                (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids);
            }
            else
            {
              v24 = v23;
              v27 = (void *)ExAllocatePool2(64, (unsigned int)v23, 1111642965);
              if ( v27 )
              {
                if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
                  || (LOBYTE(v25) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
                {
                  LOBYTE(v25) = 0;
                }
                DeviceType = WPP_GLOBAL_Control->DeviceType;
                if ( (_BYTE)v25 || DeviceType )
                {
                  LOBYTE(v26) = DeviceType != 0;
                  WPP_RECORDER_AND_TRACE_SF_L(
                    WPP_GLOBAL_Control->AttachedDevice,
                    v25,
                    v26,
                    WPP_GLOBAL_Control->DeviceExtension,
                    5,
                    4,
                    22,
                    (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids,
                    v24);
                }
                Mdl = IoAllocateMdl(v27, v24, 0, 0, 0);
                v32 = Mdl;
                if ( Mdl )
                {
                  MmBuildMdlForNonPagedPool(Mdl);
                  *(_QWORD *)(v6 + 104) = v27;
                  *(_QWORD *)(v6 + 112) = v32;
                  *(_DWORD *)(v6 + 120) = v24;
                  if ( !(_DWORD)v7 )
                    return (struct _SCO_USB_TRANSFER_CTX *)v6;
                  v33 = ExAllocatePool2(64, v7, 1111642965);
                  if ( v33 )
                  {
                    *(_QWORD *)(v6 + 128) = v33;
                    *(_DWORD *)(v6 + 136) = v7;
                    return (struct _SCO_USB_TRANSFER_CTX *)v6;
                  }
                  v12 = -102;
                  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
                    || (LOBYTE(v34) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
                  {
                    LOBYTE(v34) = 0;
                  }
                  WPP_RECORDER_AND_TRACE_SF_(
                    WPP_GLOBAL_Control->AttachedDevice,
                    v34,
                    v35,
                    WPP_GLOBAL_Control->DeviceExtension,
                    2,
                    4,
                    24,
                    (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids);
                  IoFreeMdl(v32);
                }
                else
                {
                  v12 = -102;
                  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
                    || (LOBYTE(v30) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
                  {
                    LOBYTE(v30) = 0;
                  }
                  WPP_RECORDER_AND_TRACE_SF_(
                    WPP_GLOBAL_Control->AttachedDevice,
                    v30,
                    v31,
                    WPP_GLOBAL_Control->DeviceExtension,
                    2,
                    4,
                    23,
                    (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids);
                }
                ExFreePoolWithTag(v27, 0);
              }
              else
              {
                v12 = -102;
                if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
                  || (LOBYTE(v25) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
                {
                  LOBYTE(v25) = 0;
                }
                WPP_RECORDER_AND_TRACE_SF_(
                  WPP_GLOBAL_Control->AttachedDevice,
                  v25,
                  v26,
                  WPP_GLOBAL_Control->DeviceExtension,
                  2,
                  4,
                  21,
                  (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids);
              }
            }
            ExFreePoolWithTag((PVOID)v6, 0);
            v6 = 0;
          }
          else
          {
            v12 = -102;
            LOBYTE(v21) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
            WPP_RECORDER_AND_TRACE_SF_(
              WPP_GLOBAL_Control->AttachedDevice,
              v21,
              v22,
              WPP_GLOBAL_Control->DeviceExtension,
              2,
              4,
              19,
              (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids);
          }
          IoFreeIrp(Irp);
        }
        else
        {
          v12 = -102;
          LOBYTE(v18) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
          WPP_RECORDER_AND_TRACE_SF_(
            WPP_GLOBAL_Control->AttachedDevice,
            v18,
            v19,
            WPP_GLOBAL_Control->DeviceExtension,
            2,
            4,
            18,
            (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids);
        }
        ExFreePoolWithTag(P, 0);
      }
      else
      {
        v12 = -102;
        v13 = 1;
        LOBYTE(v16) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
        WPP_RECORDER_AND_TRACE_SF_(
          WPP_GLOBAL_Control->AttachedDevice,
          v16,
          v17,
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          4,
          17,
          (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids);
      }
    }
    else
    {
      v12 = -107;
      v13 = 1;
      LOBYTE(a2) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        a2,
        a3,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        4,
        16,
        (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids);
    }
  }
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    v13 = 0;
  LOBYTE(v14) = v13;
  WPP_RECORDER_AND_TRACE_SF_D(
    WPP_GLOBAL_Control->AttachedDevice,
    v14,
    v15,
    WPP_GLOBAL_Control->DeviceExtension,
    2,
    4,
    25,
    (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids,
    v12);
  return (struct _SCO_USB_TRANSFER_CTX *)v6;
}

```

## disassembly

```asm
0x140004088  push    rbx
0x14000408a  push    rbp
0x14000408b  push    rsi
0x14000408c  push    rdi
0x14000408d  push    r12
0x14000408f  push    r13
0x140004091  push    r14
0x140004093  push    r15
0x140004095  sub     rsp, 68h
0x140004099  mov     ebp, edx
0x14000409b  mov     r13, rcx
0x14000409e  xor     r14d, r14d
0x1400040a1  mov     r15d, r8d
0x1400040a4  mov     ecx, 0FFFFFFFFh
0x1400040a9  mov     esi, edx
0x1400040ab  mov     r12, r9
0x1400040ae  lea     rax, ds:0[rbp*2]
0x1400040b6  add     rax, rbp
0x1400040b9  shl     rax, 2
0x1400040bd  cmp     rax, rcx
0x1400040c0  ja      loc_14000452E
0x1400040c6  lea     ebx, [rax+98h]
0x1400040cc  cmp     ebx, eax
0x1400040ce  jnb     short loc_140004128
0x1400040d0  mov     ebx, 0C0000095h
0x1400040d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400040dc  mov     dil, 1
0x1400040df  mov     eax, [rcx+2Ch]
0x1400040e2  test    al, 8
0x1400040e4  jz      short loc_1400040F1
0x1400040e6  cmp     byte ptr [rcx+29h], 2
0x1400040ea  jb      short loc_1400040F1
0x1400040ec  mov     dl, dil
0x1400040ef  jmp     short loc_1400040F3
0x1400040f1  xor     dl, dl
0x1400040f3  lea     rsi, WPP_89eaa7be148f36a90e353489c15db76f_Traceguids
0x1400040fa  mov     [rsp+0A8h+var_70], rsi
0x1400040ff  mov     [rsp+0A8h+var_78], 10h
0x140004106  mov     r9, [rcx+40h]
0x14000410a  mov     rcx, [rcx+18h]
0x14000410e  mov     [rsp+0A8h+var_80], 4
0x140004116  mov     byte ptr [rsp+0A8h+Irp], 2
0x14000411b  call    WPP_RECORDER_AND_TRACE_SF_
0x140004120  xor     r13d, r13d
0x140004123  jmp     loc_140004585
0x140004128  mov     edx, ebx
0x14000412a  mov     ecx, 40h ; '@'
0x14000412f  mov     r8d, 42425355h
0x140004135  call    cs:__imp_ExAllocatePool2
0x14000413c  nop     dword ptr [rax+rax+00h]
0x140004141  mov     [rsp+0A8h+P], rax
0x140004146  test    rax, rax
0x140004149  jnz     short loc_140004183
0x14000414b  mov     ebx, 0C000009Ah
0x140004150  mov     rcx, cs:WPP_GLOBAL_Control
0x140004157  mov     dil, 1
0x14000415a  mov     eax, [rcx+2Ch]
0x14000415d  test    al, 8
0x14000415f  jz      short loc_14000416C
0x140004161  cmp     byte ptr [rcx+29h], 2
0x140004165  jb      short loc_14000416C
0x140004167  mov     dl, dil
0x14000416a  jmp     short loc_14000416E
0x14000416c  xor     dl, dl
0x14000416e  lea     rsi, WPP_89eaa7be148f36a90e353489c15db76f_Traceguids
0x140004175  mov     [rsp+0A8h+var_70], rsi
0x14000417a  mov     [rsp+0A8h+var_78], 11h
0x140004181  jmp     short loc_140004106
0x140004183  mov     rax, [r13+28h]
0x140004187  mov     dil, 1
0x14000418a  xor     edx, edx; ChargeQuota
0x14000418c  mov     cl, [rax+4Ch]
0x14000418f  add     cl, dil; StackSize
0x140004192  call    cs:__imp_IoAllocateIrp
0x140004199  nop     dword ptr [rax+rax+00h]
0x14000419e  mov     [rsp+0A8h+var_58], rax
0x1400041a3  test    rax, rax
0x1400041a6  jnz     short loc_140004201
0x1400041a8  mov     ebx, 0C000009Ah
0x1400041ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400041b4  mov     eax, [rcx+2Ch]
0x1400041b7  test    al, 8
0x1400041b9  jz      short loc_1400041C9
0x1400041bb  cmp     byte ptr [rcx+29h], 2
0x1400041bf  jb      short loc_1400041C9
0x1400041c1  mov     dl, dil
0x1400041c4  xor     r13d, r13d
0x1400041c7  jmp     short loc_1400041CF
0x1400041c9  xor     r13d, r13d
0x1400041cc  mov     dl, r13b
0x1400041cf  mov     r9, [rcx+40h]
0x1400041d3  lea     rsi, WPP_89eaa7be148f36a90e353489c15db76f_Traceguids
0x1400041da  mov     rcx, [rcx+18h]
0x1400041de  mov     [rsp+0A8h+var_70], rsi
0x1400041e3  mov     [rsp+0A8h+var_78], 12h
0x1400041ea  mov     [rsp+0A8h+var_80], 4
0x1400041f2  mov     byte ptr [rsp+0A8h+Irp], 2
0x1400041f7  call    WPP_RECORDER_AND_TRACE_SF_
0x1400041fc  jmp     loc_140004519
0x140004201  mov     edx, 0A8h
0x140004206  mov     r8d, 42425355h
0x14000420c  lea     ecx, [rdx-68h]
0x14000420f  call    cs:__imp_ExAllocatePool2
0x140004216  nop     dword ptr [rax+rax+00h]
0x14000421b  mov     r14, rax
0x14000421e  test    rax, rax
0x140004221  jnz     short loc_14000427C
0x140004223  mov     ebx, 0C000009Ah
0x140004228  mov     rcx, cs:WPP_GLOBAL_Control
0x14000422f  mov     eax, [rcx+2Ch]
0x140004232  test    al, 8
0x140004234  jz      short loc_140004244
0x140004236  cmp     byte ptr [rcx+29h], 2
0x14000423a  jb      short loc_140004244
0x14000423c  mov     dl, dil
0x14000423f  xor     r13d, r13d
0x140004242  jmp     short loc_14000424A
0x140004244  xor     r13d, r13d
0x140004247  mov     dl, r13b
0x14000424a  mov     r9, [rcx+40h]
0x14000424e  lea     rsi, WPP_89eaa7be148f36a90e353489c15db76f_Traceguids
0x140004255  mov     rcx, [rcx+18h]
0x140004259  mov     [rsp+0A8h+var_70], rsi
0x14000425e  mov     [rsp+0A8h+var_78], 13h
0x140004265  mov     [rsp+0A8h+var_80], 4
0x14000426d  mov     byte ptr [rsp+0A8h+Irp], 2
0x140004272  call    WPP_RECORDER_AND_TRACE_SF_
0x140004277  jmp     loc_140004508
0x14000427c  mov     dword ptr [rax], 43545553h
0x140004282  mov     ecx, 0FFFFFFFFh
0x140004287  mov     [rax+20h], r12
0x14000428b  mov     rax, [rsp+0A8h+var_58]
0x140004290  mov     [r14+40h], rax
0x140004294  mov     rax, [rsp+0A8h+P]
0x140004299  mov     [r14+48h], rax
0x14000429d  mov     eax, [r13+2A0h]
0x1400042a4  imul    rax, rsi
0x1400042a8  mov     [r14+54h], ebx
0x1400042ac  mov     [r14+50h], ebp
0x1400042b0  cmp     rax, rcx
0x1400042b3  ja      loc_1400044A0
0x1400042b9  mov     edx, eax
0x1400042bb  mov     ecx, 40h ; '@'
0x1400042c0  mov     r8d, 42425355h
0x1400042c6  mov     ebx, eax
0x1400042c8  call    cs:__imp_ExAllocatePool2
0x1400042cf  nop     dword ptr [rax+rax+00h]
0x1400042d4  xor     r13d, r13d
0x1400042d7  mov     r12, rax
0x1400042da  test    rax, rax
0x1400042dd  jnz     short loc_140004316
0x1400042df  mov     ebx, 0C000009Ah
0x1400042e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400042eb  mov     eax, [rcx+2Ch]
0x1400042ee  test    al, 8
0x1400042f0  jz      short loc_1400042FB
0x1400042f2  cmp     byte ptr [rcx+29h], 2
0x1400042f6  mov     dl, dil
0x1400042f9  jnb     short loc_1400042FE
0x1400042fb  mov     dl, r13b
0x1400042fe  lea     rsi, WPP_89eaa7be148f36a90e353489c15db76f_Traceguids
0x140004305  mov     [rsp+0A8h+var_70], rsi
0x14000430a  mov     [rsp+0A8h+var_78], 15h
0x140004311  jmp     loc_1400044DA
0x140004316  mov     rcx, cs:WPP_GLOBAL_Control
0x14000431d  mov     eax, [rcx+2Ch]
0x140004320  test    al, 8
0x140004322  jz      short loc_14000432D
0x140004324  cmp     byte ptr [rcx+29h], 5
0x140004328  mov     dl, dil
0x14000432b  jnb     short loc_140004330
0x14000432d  mov     dl, r13b
0x140004330  movzx   eax, word ptr [rcx+48h]
0x140004334  lea     rsi, WPP_89eaa7be148f36a90e353489c15db76f_Traceguids
0x14000433b  test    ax, ax
0x14000433e  setnz   r8b
0x140004342  test    dl, dl
0x140004344  jnz     short loc_14000434B
0x140004346  test    ax, ax
0x140004349  jz      short loc_140004375
0x14000434b  mov     r9, [rcx+40h]
0x14000434f  mov     rcx, [rcx+18h]
0x140004353  mov     [rsp+0A8h+var_68], ebx
0x140004357  mov     [rsp+0A8h+var_70], rsi
0x14000435c  mov     [rsp+0A8h+var_78], 16h
0x140004363  mov     [rsp+0A8h+var_80], 4
0x14000436b  mov     byte ptr [rsp+0A8h+Irp], 5
0x140004370  call    WPP_RECORDER_AND_TRACE_SF_L
0x140004375  xor     r9d, r9d; ChargeQuota
0x140004378  mov     [rsp+0A8h+Irp], r13; Irp
0x14000437d  xor     r8d, r8d; SecondaryBuffer
0x140004380  mov     edx, ebx; Length
0x140004382  mov     rcx, r12; VirtualAddress
0x140004385  call    cs:__imp_IoAllocateMdl
0x14000438c  nop     dword ptr [rax+rax+00h]
0x140004391  mov     rbp, rax
0x140004394  test    rax, rax
0x140004397  jnz     short loc_1400043E3
0x140004399  mov     ebx, 0C000009Ah
0x14000439e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400043a5  mov     eax, [rcx+2Ch]
0x1400043a8  test    al, 8
0x1400043aa  jz      short loc_1400043B5
0x1400043ac  cmp     byte ptr [rcx+29h], 2
0x1400043b0  mov     dl, dil
0x1400043b3  jnb     short loc_1400043B8
0x1400043b5  mov     dl, r13b
0x1400043b8  mov     r9, [rcx+40h]
0x1400043bc  mov     rcx, [rcx+18h]
0x1400043c0  mov     [rsp+0A8h+var_70], rsi
0x1400043c5  mov     [rsp+0A8h+var_78], 17h
0x1400043cc  mov     [rsp+0A8h+var_80], 4
0x1400043d4  mov     byte ptr [rsp+0A8h+Irp], 2
0x1400043d9  call    WPP_RECORDER_AND_TRACE_SF_
0x1400043de  jmp     loc_14000447A
0x1400043e3  mov     rcx, rbp; MemoryDescriptorList
0x1400043e6  call    cs:__imp_MmBuildMdlForNonPagedPool
0x1400043ed  nop     dword ptr [rax+rax+00h]
0x1400043f2  mov     [r14+68h], r12
0x1400043f6  mov     [r14+70h], rbp
0x1400043fa  mov     [r14+78h], ebx
0x1400043fe  test    r15d, r15d
0x140004401  jz      loc_1400045C9
0x140004407  mov     rdx, r15
0x14000440a  mov     ecx, 40h ; '@'
0x14000440f  mov     r8d, 42425355h
0x140004415  call    cs:__imp_ExAllocatePool2
0x14000441c  nop     dword ptr [rax+rax+00h]
0x140004421  test    rax, rax
0x140004424  jnz     short loc_14000448D
0x140004426  mov     ebx, 0C000009Ah
0x14000442b  mov     rcx, cs:WPP_GLOBAL_Control
0x140004432  mov     eax, [rcx+2Ch]
0x140004435  test    al, 8
0x140004437  jz      short loc_140004442
0x140004439  cmp     byte ptr [rcx+29h], 2
0x14000443d  mov     dl, dil
0x140004440  jnb     short loc_140004445
0x140004442  mov     dl, r13b
0x140004445  mov     r9, [rcx+40h]
0x140004449  mov     rcx, [rcx+18h]
0x14000444d  mov     [rsp+0A8h+var_70], rsi
0x140004452  mov     [rsp+0A8h+var_78], 18h
0x140004459  mov     [rsp+0A8h+var_80], 4
0x140004461  mov     byte ptr [rsp+0A8h+Irp], 2
0x140004466  call    WPP_RECORDER_AND_TRACE_SF_
0x14000446b  mov     rcx, rbp; Mdl
0x14000446e  call    cs:__imp_IoFreeMdl
0x140004475  nop     dword ptr [rax+rax+00h]
0x14000447a  xor     edx, edx; Tag
0x14000447c  mov     rcx, r12; P
0x14000447f  call    cs:__imp_ExFreePoolWithTag
0x140004486  nop     dword ptr [rax+rax+00h]
0x14000448b  jmp     short loc_1400044F4
0x14000448d  mov     [r14+80h], rax
0x140004494  mov     [r14+88h], r15d
0x14000449b  jmp     loc_1400045C9
0x1400044a0  mov     ebx, 0C0000095h
0x1400044a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400044ac  mov     eax, [rcx+2Ch]
0x1400044af  test    al, 8
0x1400044b1  jz      short loc_1400044C1
0x1400044b3  cmp     byte ptr [rcx+29h], 2
0x1400044b7  jb      short loc_1400044C1
0x1400044b9  mov     dl, dil
0x1400044bc  xor     r13d, r13d
0x1400044bf  jmp     short loc_1400044C7
0x1400044c1  xor     r13d, r13d
0x1400044c4  mov     dl, r13b
0x1400044c7  lea     rsi, WPP_89eaa7be148f36a90e353489c15db76f_Traceguids
0x1400044ce  mov     [rsp+0A8h+var_70], rsi
0x1400044d3  mov     [rsp+0A8h+var_78], 14h
0x1400044da  mov     r9, [rcx+40h]
0x1400044de  mov     rcx, [rcx+18h]
0x1400044e2  mov     [rsp+0A8h+var_80], 4
0x1400044ea  mov     byte ptr [rsp+0A8h+Irp], 2
0x1400044ef  call    WPP_RECORDER_AND_TRACE_SF_
0x1400044f4  xor     edx, edx; Tag
0x1400044f6  mov     rcx, r14; P
0x1400044f9  call    cs:__imp_ExFreePoolWithTag
0x140004500  nop     dword ptr [rax+rax+00h]
0x140004505  mov     r14, r13
0x140004508  mov     rcx, [rsp+0A8h+var_58]; Irp
0x14000450d  call    cs:__imp_IoFreeIrp
0x140004514  nop     dword ptr [rax+rax+00h]
0x140004519  mov     rcx, [rsp+0A8h+P]; P
0x14000451e  xor     edx, edx; Tag
0x140004520  call    cs:__imp_ExFreePoolWithTag
0x140004527  nop     dword ptr [rax+rax+00h]
0x14000452c  jmp     short loc_140004585
0x14000452e  mov     ebx, 0C0000095h
0x140004533  mov     rcx, cs:WPP_GLOBAL_Control
0x14000453a  mov     dil, 1
0x14000453d  mov     eax, [rcx+2Ch]
0x140004540  test    al, 8
0x140004542  jz      short loc_140004552
0x140004544  cmp     byte ptr [rcx+29h], 2
0x140004548  jb      short loc_140004552
0x14000454a  mov     dl, dil
0x14000454d  xor     r13d, r13d
  ... truncated ...
```
