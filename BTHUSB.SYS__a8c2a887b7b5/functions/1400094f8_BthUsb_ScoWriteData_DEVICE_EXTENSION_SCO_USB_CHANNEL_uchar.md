# BthUsb_ScoWriteData(_DEVICE_EXTENSION *,_SCO_USB_CHANNEL *,uchar)

- ea: `0x1400094f8`
- end: `0x14000971a`
- name: `?BthUsb_ScoWriteData@@YAJPEAU_DEVICE_EXTENSION@@PEAU_SCO_USB_CHANNEL@@E@Z`
- size: `546`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _SCO_USB_CHANNEL *, unsigned __int8)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x140004840`
- `0x140009a90`

## callees

- `0x140005c8c`
- `0x1400090d8`
- `0x1400094f8`
- `0x140009e54`
- `0x140009fbc`
- `0x14000d85c`
- `0x14000da00`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000955a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009596`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400096aa`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000955a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009596`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400096aa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009527`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009581`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000967f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009527`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009581`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000967f`

## string_xrefs

- `0x14000966c`: `onecore\drivers\wdm\bluetooth\drivers\bthusb\scousbwrite.cpp`

## pseudocode

```c
__int64 __fastcall BthUsb_ScoWriteData(struct _DEVICE_EXTENSION *a1, struct _SCO_USB_CHANNEL *a2, char a3)
{
  int v4; // ebp
  char v5; // r13
  int v8; // r15d
  KIRQL v9; // dl
  char v10; // di
  unsigned int Flags; // eax
  char v12; // bl
  int v13; // edx
  int v14; // r8d
  int v15; // r14d
  unsigned __int64 *p_Lock; // rax
  KIRQL v17; // al
  int InProgressUrbs; // ebx
  int v19; // edx
  int WriteMaxPendingReq; // r8d
  const char *v21; // rax
  __int64 Item; // rax
  struct _SCO_USB_TRANSFER_CTX *v23; // rbx
  KIRQL v24; // al
  unsigned int v25; // ebx
  int v27; // [rsp+20h] [rbp-88h]
  int v28; // [rsp+28h] [rbp-80h]
  int v29; // [rsp+30h] [rbp-78h]
  int v30; // [rsp+38h] [rbp-70h]
  char v31; // [rsp+B0h] [rbp+8h]

  v4 = 0;
  v5 = 0;
  v31 = 0;
  v8 = 2;
  v9 = KeAcquireSpinLockRaiseToDpc(&a2->Lock);
  v10 = 1;
  Flags = a2->Flags;
  if ( (Flags & 1) != 0 )
  {
    if ( a3 )
      a2->Flags = Flags | 2;
    v12 = 1;
  }
  else
  {
    v12 = 0;
    a2->Flags = Flags | 1;
  }
  KeReleaseSpinLock(&a2->Lock, v9);
  if ( !v12 )
  {
    do
    {
      v15 = 0;
      if ( v8 )
      {
        p_Lock = &a2->WritePipeObj.Lock;
        do
        {
          v17 = KeAcquireSpinLockRaiseToDpc(p_Lock);
          InProgressUrbs = a2->WritePipeObj.InProgressUrbs;
          KeReleaseSpinLock(&a2->WritePipeObj.Lock, v17);
          LOBYTE(v19) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
          WriteMaxPendingReq = a1->Sco.WriteMaxPendingReq;
          v21 = "bail out";
          if ( WriteMaxPendingReq > InProgressUrbs )
            v21 = "continue";
          WPP_RECORDER_AND_TRACE_SF_llls(
            WPP_GLOBAL_Control->AttachedDevice,
            v19,
            WriteMaxPendingReq,
            WPP_GLOBAL_Control->DeviceExtension,
            v27,
            v28,
            v29,
            v30,
            v15,
            WriteMaxPendingReq,
            InProgressUrbs,
            (__int64)v21);
          if ( a1->Sco.WriteMaxPendingReq <= InProgressUrbs )
            break;
          Item = ResourceQueue_GetItem(&a1->Sco.WriteCtxQueue);
          v23 = (struct _SCO_USB_TRANSFER_CTX *)Item;
          if ( !Item )
            break;
          *(_QWORD *)(Item + 56) = a1;
          *(_DWORD *)(Item + 96) = 4;
          v4 = BthUsb_ScoInitWriteTransferUrb(a1, a2, (struct _SCO_USB_TRANSFER_CTX *)Item);
          if ( v4 < 0 )
          {
            RefObj_ReleaseEx(
              &v23->RefObj,
              v23,
              800,
              "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthusb\\scousbwrite.cpp");
            break;
          }
          ++v31;
          ++v15;
          v4 = BthUsb_ScoUrbStart(a1, &a2->WritePipeObj, v23);
          p_Lock = &a2->WritePipeObj.Lock;
        }
        while ( v15 < v8 );
      }
      v24 = KeAcquireSpinLockRaiseToDpc(&a2->Lock);
      v25 = a2->Flags & 2;
      a2->Flags &= -(v25 != 0) - 2;
      KeReleaseSpinLock(&a2->Lock, v24);
      v8 = v25 != 0 ? 2 : 0;
    }
    while ( v25 );
    v5 = v31;
  }
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    v10 = 0;
  LOBYTE(v13) = v10;
  WPP_RECORDER_AND_TRACE_SF_qLd(
    WPP_GLOBAL_Control->AttachedDevice,
    v13,
    v14,
    WPP_GLOBAL_Control->DeviceExtension,
    v27,
    v28,
    v29,
    v30,
    (char)a2,
    v5,
    v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400094f8  push    rbx
0x1400094fa  push    rbp
0x1400094fb  push    rsi
0x1400094fc  push    rdi
0x1400094fd  push    r12
0x1400094ff  push    r13
0x140009501  push    r14
0x140009503  push    r15
0x140009505  sub     rsp, 68h
0x140009509  mov     r12, rcx
0x14000950c  xor     ebp, ebp
0x14000950e  xor     r13d, r13d
0x140009511  lea     rcx, [rdx+8]; SpinLock
0x140009515  mov     bl, r8b
0x140009518  mov     [rsp+0A8h+arg_0], r13d
0x140009520  mov     rsi, rdx
0x140009523  lea     r15d, [rbp+2]
0x140009527  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000952e  nop     dword ptr [rax+rax+00h]
0x140009533  mov     dl, al; NewIrql
0x140009535  lea     edi, [rbp+1]
0x140009538  mov     eax, [rsi+10h]
0x14000953b  test    dil, al
0x14000953e  jz      short loc_14000954F
0x140009540  test    bl, bl
0x140009542  jz      short loc_14000954A
0x140009544  or      eax, r15d
0x140009547  mov     [rsi+10h], eax
0x14000954a  mov     bl, dil
0x14000954d  jmp     short loc_140009556
0x14000954f  xor     bl, bl
0x140009551  or      eax, edi
0x140009553  mov     [rsi+10h], eax
0x140009556  lea     rcx, [rsi+8]; SpinLock
0x14000955a  call    cs:__imp_KeReleaseSpinLock
0x140009561  nop     dword ptr [rax+rax+00h]
0x140009566  test    bl, bl
0x140009568  jnz     loc_1400096D1
0x14000956e  xor     r14d, r14d
0x140009571  test    r15d, r15d
0x140009574  jz      loc_14000967B
0x14000957a  lea     rax, [rsi+68h]
0x14000957e  mov     rcx, rax; SpinLock
0x140009581  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140009588  nop     dword ptr [rax+rax+00h]
0x14000958d  mov     ebx, [rsi+74h]
0x140009590  lea     rcx, [rsi+68h]; SpinLock
0x140009594  mov     dl, al; NewIrql
0x140009596  call    cs:__imp_KeReleaseSpinLock
0x14000959d  nop     dword ptr [rax+rax+00h]
0x1400095a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400095a9  mov     eax, [rcx+2Ch]
0x1400095ac  test    al, 10h
0x1400095ae  jz      short loc_1400095BB
0x1400095b0  cmp     byte ptr [rcx+29h], 4
0x1400095b4  jb      short loc_1400095BB
0x1400095b6  mov     dl, dil
0x1400095b9  jmp     short loc_1400095BD
0x1400095bb  xor     dl, dl
0x1400095bd  mov     r8d, [r12+278h]
0x1400095c5  lea     r9, aContinue; "continue"
0x1400095cc  cmp     r8d, ebx
0x1400095cf  lea     rax, aBailOut; "bail out"
0x1400095d6  cmovg   rax, r9
0x1400095da  mov     r9, [rcx+40h]
0x1400095de  mov     rcx, [rcx+18h]
0x1400095e2  mov     [rsp+0A8h+var_50], rax
0x1400095e7  mov     [rsp+0A8h+var_58], ebx
0x1400095eb  mov     [rsp+0A8h+var_60], r8d
0x1400095f0  mov     dword ptr [rsp+0A8h+var_68], r14d
0x1400095f5  call    WPP_RECORDER_AND_TRACE_SF_llls
0x1400095fa  cmp     [r12+278h], ebx
0x140009602  jle     short loc_14000967B
0x140009604  lea     rcx, [r12+138h]
0x14000960c  call    ResourceQueue_GetItem
0x140009611  mov     rbx, rax
0x140009614  test    rax, rax
0x140009617  jz      short loc_14000967B
0x140009619  mov     r8, rax; struct _SCO_USB_TRANSFER_CTX *
0x14000961c  mov     [rax+38h], r12
0x140009620  mov     rdx, rsi; struct _SCO_USB_CHANNEL *
0x140009623  mov     dword ptr [rax+60h], 4
0x14000962a  mov     rcx, r12; struct _DEVICE_EXTENSION *
0x14000962d  call    ?BthUsb_ScoInitWriteTransferUrb@@YAJPEAU_DEVICE_EXTENSION@@PEAU_SCO_USB_CHANNEL@@PEAU_SCO_USB_TRANSFER_CTX@@@Z; BthUsb_ScoInitWriteTransferUrb(_DEVICE_EXTENSION *,_SCO_USB_CHANNEL *,_SCO_USB_TRANSFER_CTX *)
0x140009632  mov     ebp, eax
0x140009634  test    eax, eax
0x140009636  js      short loc_140009662
0x140009638  mov     r8, rbx; struct _SCO_USB_TRANSFER_CTX *
0x14000963b  lea     rdx, [rsi+40h]; struct _SCO_USB_PIPE_OBJ *
0x14000963f  mov     rcx, r12; struct _DEVICE_EXTENSION *
0x140009642  call    ?BthUsb_ScoUrbStart@@YAJPEAU_DEVICE_EXTENSION@@PEAU_SCO_USB_PIPE_OBJ@@PEAU_SCO_USB_TRANSFER_CTX@@@Z; BthUsb_ScoUrbStart(_DEVICE_EXTENSION *,_SCO_USB_PIPE_OBJ *,_SCO_USB_TRANSFER_CTX *)
0x140009647  add     [rsp+0A8h+arg_0], edi
0x14000964e  add     r14d, edi
0x140009651  mov     ebp, eax
0x140009653  lea     rax, [rsi+68h]
0x140009657  cmp     r14d, r15d
0x14000965a  jl      loc_14000957E
0x140009660  jmp     short loc_14000967B
0x140009662  lea     rcx, [rbx+8]
0x140009666  mov     r8d, 320h
0x14000966c  lea     r9, aOnecoreDrivers_0; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140009673  mov     rdx, rbx
0x140009676  call    RefObj_ReleaseEx
0x14000967b  lea     rcx, [rsi+8]; SpinLock
0x14000967f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140009686  nop     dword ptr [rax+rax+00h]
0x14000968b  mov     r8d, [rsi+10h]
0x14000968f  mov     ebx, r8d
0x140009692  and     ebx, 2
0x140009695  mov     ecx, ebx
0x140009697  neg     ecx
0x140009699  lea     rcx, [rsi+8]; SpinLock
0x14000969d  sbb     edx, edx
0x14000969f  add     edx, 0FFFFFFFEh
0x1400096a2  and     edx, r8d
0x1400096a5  mov     [rsi+10h], edx
0x1400096a8  mov     dl, al; NewIrql
0x1400096aa  call    cs:__imp_KeReleaseSpinLock
0x1400096b1  nop     dword ptr [rax+rax+00h]
0x1400096b6  mov     eax, ebx
0x1400096b8  neg     eax
0x1400096ba  sbb     r15d, r15d
0x1400096bd  and     r15d, 2
0x1400096c1  test    ebx, ebx
0x1400096c3  jnz     loc_14000956E
0x1400096c9  mov     r13d, [rsp+0A8h+arg_0]
0x1400096d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400096d8  mov     eax, [rcx+2Ch]
0x1400096db  test    al, 10h
0x1400096dd  jz      short loc_1400096E5
0x1400096df  cmp     byte ptr [rcx+29h], 4
0x1400096e3  jnb     short loc_1400096E8
0x1400096e5  xor     dil, dil
0x1400096e8  mov     r9, [rcx+40h]
0x1400096ec  mov     dl, dil
0x1400096ef  mov     rcx, [rcx+18h]
0x1400096f3  mov     [rsp+0A8h+var_58], ebp
0x1400096f7  mov     [rsp+0A8h+var_60], r13d
0x1400096fc  mov     [rsp+0A8h+var_68], rsi
0x140009701  call    WPP_RECORDER_AND_TRACE_SF_qLd
0x140009706  mov     eax, ebp
0x140009708  add     rsp, 68h
0x14000970c  pop     r15
0x14000970e  pop     r14
0x140009710  pop     r13
0x140009712  pop     r12
0x140009714  pop     rdi
0x140009715  pop     rsi
0x140009716  pop     rbp
0x140009717  pop     rbx
0x140009718  retn
```
