# Avdtp_impl::impl_Create(_DEVICE_OBJECT *,_DEVICE_OBJECT *,_IO_REMOVE_LOCK *,ushort,void *,unsigned __int64,AVDTPCallbackTable const *,unsigned __int64,tagAVDTPFunctionTable *)

- ea: `0x14001fa80`
- end: `0x14001fd01`
- name: `?impl_Create@Avdtp_impl@@SAPEAXPEAU_DEVICE_OBJECT@@0PEAU_IO_REMOVE_LOCK@@GPEAX_KPEBUAVDTPCallbackTable@@3PEAUtagAVDTPFunctionTable@@@Z`
- size: `641`
- prototype: `void *__fastcall(struct _DEVICE_OBJECT *, struct _DEVICE_OBJECT *, struct _IO_REMOVE_LOCK *, unsigned __int16, void *, size_t Size, const struct AVDTPCallbackTable *Src, size_t, struct tagAVDTPFunctionTable *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x14001fa20`

## callees

- `0x14000f570`
- `0x14001c948`
- `0x14001fa80`
- `0x14004a06c`
- `0x14004cc74`
- `0x140058848`
- `0x14005c870`
- `0x14005c8c0`
- `0x14005ce00`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001fb9a`
- `ntoskrnl!ExAllocatePool2` at `0x14001fb9a`
- `ntoskrnl!KeInitializeEvent` at `0x14001fbca`
- `ntoskrnl!KeInitializeEvent` at `0x14001fbca`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001fc1b`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001fc3d`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001fc1b`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001fc3d`

## pseudocode

```c
__int64 __fastcall Avdtp_impl::impl_Create(
        struct _DEVICE_OBJECT *a1,
        struct _DEVICE_OBJECT *a2,
        struct _IO_REMOVE_LOCK *a3,
        __int16 a4,
        void *a5,
        size_t Size,
        void (__fastcall **Src)(void *, struct _DEVICE_OBJECT *, struct _IO_REMOVE_LOCK *),
        size_t a8,
        struct tagAVDTPFunctionTable *a9)
{
  struct _DEVICE_OBJECT *v10; // r12
  bool v12; // al
  bool v13; // cl
  __int64 Pool2; // rax
  __int64 v15; // rbx
  __int64 v16; // rcx
  __int64 v17; // rax
  struct _IO_REMOVE_LOCK *v19; // [rsp+90h] [rbp+18h]

  v19 = a3;
  v10 = a2;
  if ( !a2 || !a1 )
    return 0;
  LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)a2,
      (_DWORD)a3,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      4,
      12,
      (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids);
  v12 = Size == 280 && Src;
  v13 = a8 == 288 && a9;
  if ( !a5 || !v12 || !v13 )
    return 0;
  Src[2](a5, a2, a3);
  Pool2 = ExAllocatePool2(64, 1808, 1096172628);
  v15 = Pool2;
  if ( Pool2 )
  {
    RefObj_InitEx(Pool2 + 152);
    KeInitializeEvent((PRKEVENT)(v15 + 176), NotificationEvent, 0);
    *(_QWORD *)(v15 + 1096) = a1;
    *(_QWORD *)(v15 + 1088) = v10;
    *(_QWORD *)(v15 + 1144) = a5;
    *(_WORD *)(v15 + 1112) = a4;
    Avdtp_impl::SetAvdtpState_NoLock(v15, 0);
    memmove((void *)(v15 + 1152), Src, Size);
    KeInitializeSpinLock((PKSPIN_LOCK)(v15 + 1600));
    *(_QWORD *)(v15 + 1792) = v19;
    KeInitializeSpinLock((PKSPIN_LOCK)(v15 + 1776));
    *(_QWORD *)(v15 + 1768) = v15 + 1760;
    *(_QWORD *)(v15 + 1760) = v15 + 1760;
    *(_DWORD *)(v15 + 1784) = 0;
    Avdtp_impl::InitializeCmdInfoTables((Avdtp_impl *)v15);
    v16 = 0;
    v17 = 0;
    do
    {
      ++v16;
      *(_WORD *)(v17 + v15 + 224) = 128;
      *(_BYTE *)(v17 + v15 + 228) = 0;
      *(_DWORD *)(v17 + v15 + 232) = 0;
      *(_BYTE *)(v17 + v15 + 236) = 0x80;
      *(_QWORD *)(v17 + v15 + 216) = 0;
      v17 += 200;
    }
    while ( v16 != 4 );
    Avdtp_impl::GetFnTable(a9, a8, (void *)v15);
    *(_DWORD *)(v15 + 1800) = 1;
  }
  else if ( a9 )
  {
    memset(a9, 0, a8);
  }
  return v15;
}

```

## disassembly

```asm
0x14001fa80  mov     [rsp+arg_10], r8
0x14001fa85  push    rbx
0x14001fa86  push    rbp
0x14001fa87  push    r12
0x14001fa89  push    r13
0x14001fa8b  push    r14
0x14001fa8d  push    r15
0x14001fa8f  sub     rsp, 48h
0x14001fa93  movzx   r13d, r9w
0x14001fa97  mov     r12, rdx
0x14001fa9a  mov     r15, rcx
0x14001fa9d  test    rdx, rdx
0x14001faa0  jz      loc_14001FCEF
0x14001faa6  test    rcx, rcx
0x14001faa9  jz      loc_14001FCEF
0x14001faaf  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fab6  lea     rax, WPP_GLOBAL_Control
0x14001fabd  cmp     rcx, rax
0x14001fac0  jz      short loc_14001FAD3
0x14001fac2  mov     eax, [rcx+2Ch]
0x14001fac5  test    al, 8
0x14001fac7  jz      short loc_14001FAD3
0x14001fac9  cmp     byte ptr [rcx+29h], 4
0x14001facd  jb      short loc_14001FAD3
0x14001facf  mov     dl, 1
0x14001fad1  jmp     short loc_14001FAD5
0x14001fad3  xor     dl, dl
0x14001fad5  lea     rax, WPP_RECORDER_INITIALIZED
0x14001fadc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001fae3  setnz   r8b
0x14001fae7  test    dl, dl
0x14001fae9  jnz     short loc_14001FAF0
0x14001faeb  test    r8b, r8b
0x14001faee  jz      short loc_14001FB1D
0x14001faf0  mov     r9, [rcx+40h]
0x14001faf4  lea     rax, WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids
0x14001fafb  mov     rcx, [rcx+18h]
0x14001faff  mov     [rsp+78h+var_40], rax
0x14001fb04  mov     [rsp+78h+var_48], 0Ch
0x14001fb0b  mov     [rsp+78h+var_50], 4
0x14001fb13  mov     [rsp+78h+var_58], 4
0x14001fb18  call    WPP_RECORDER_AND_TRACE_SF_
0x14001fb1d  cmp     [rsp+78h+Size], 118h
0x14001fb29  mov     r14, [rsp+78h+Src]
0x14001fb31  jnz     short loc_14001FB3C
0x14001fb33  test    r14, r14
0x14001fb36  jz      short loc_14001FB3C
0x14001fb38  mov     al, 1
0x14001fb3a  jmp     short loc_14001FB3E
0x14001fb3c  xor     al, al
0x14001fb3e  cmp     [rsp+78h+arg_38], 120h
0x14001fb4a  jnz     short loc_14001FB5B
0x14001fb4c  cmp     [rsp+78h+arg_40], 0
0x14001fb55  jz      short loc_14001FB5B
0x14001fb57  mov     cl, 1
0x14001fb59  jmp     short loc_14001FB5D
0x14001fb5b  xor     cl, cl
0x14001fb5d  mov     rbp, [rsp+78h+arg_20]
0x14001fb65  test    rbp, rbp
0x14001fb68  jz      loc_14001FCEF
0x14001fb6e  test    al, al
0x14001fb70  jz      loc_14001FCEF
0x14001fb76  test    cl, cl
0x14001fb78  jz      loc_14001FCEF
0x14001fb7e  mov     rax, [r14+10h]
0x14001fb82  mov     rcx, rbp
0x14001fb85  call    _guard_dispatch_icall
0x14001fb8a  mov     edx, 710h
0x14001fb8f  mov     ecx, 40h ; '@'
0x14001fb94  mov     r8d, 41564454h
0x14001fb9a  call    cs:__imp_ExAllocatePool2
0x14001fba1  nop     dword ptr [rax+rax+00h]
0x14001fba6  mov     rbx, rax
0x14001fba9  test    rax, rax
0x14001fbac  jz      loc_14001FCC8
0x14001fbb2  lea     rcx, [rax+98h]
0x14001fbb9  call    RefObj_InitEx
0x14001fbbe  lea     rcx, [rbx+0B0h]; Event
0x14001fbc5  xor     r8d, r8d; State
0x14001fbc8  xor     edx, edx; Type
0x14001fbca  call    cs:__imp_KeInitializeEvent
0x14001fbd1  nop     dword ptr [rax+rax+00h]
0x14001fbd6  xor     edx, edx
0x14001fbd8  mov     [rbx+448h], r15
0x14001fbdf  mov     rcx, rbx
0x14001fbe2  mov     [rbx+440h], r12
0x14001fbe9  mov     [rbx+478h], rbp
0x14001fbf0  mov     [rbx+458h], r13w
0x14001fbf8  call    ?SetAvdtpState_NoLock@Avdtp_impl@@AEAA?AW4TAG_AvdtpState@@W42@@Z; Avdtp_impl::SetAvdtpState_NoLock(TAG_AvdtpState)
0x14001fbfd  mov     r8, [rsp+78h+Size]; Size
0x14001fc05  lea     rcx, [rbx+480h]; void *
0x14001fc0c  mov     rdx, r14; Src
0x14001fc0f  call    memmove
0x14001fc14  lea     rcx, [rbx+640h]; SpinLock
0x14001fc1b  call    cs:__imp_KeInitializeSpinLock
0x14001fc22  nop     dword ptr [rax+rax+00h]
0x14001fc27  mov     rax, [rsp+78h+arg_10]
0x14001fc2f  lea     rcx, [rbx+6F0h]; SpinLock
0x14001fc36  mov     [rbx+700h], rax
0x14001fc3d  call    cs:__imp_KeInitializeSpinLock
0x14001fc44  nop     dword ptr [rax+rax+00h]
0x14001fc49  lea     rax, [rbx+6E0h]
0x14001fc50  xor     ebp, ebp
0x14001fc52  mov     rcx, rbx; this
0x14001fc55  mov     [rax+8], rax
0x14001fc59  mov     [rax], rax
0x14001fc5c  mov     [rbx+6F8h], ebp
0x14001fc62  call    ?InitializeCmdInfoTables@Avdtp_impl@@AEAAXXZ; Avdtp_impl::InitializeCmdInfoTables(void)
0x14001fc67  mov     ecx, ebp
0x14001fc69  mov     eax, ebp
0x14001fc6b  inc     rcx
0x14001fc6e  mov     word ptr [rax+rbx+0E0h], 80h
0x14001fc78  mov     [rax+rbx+0E4h], bpl
0x14001fc80  mov     [rax+rbx+0E8h], ebp
0x14001fc87  mov     byte ptr [rax+rbx+0ECh], 80h
0x14001fc8f  mov     [rax+rbx+0D8h], rbp
0x14001fc97  lea     rax, [rax+0C8h]
0x14001fc9e  cmp     rcx, 4
0x14001fca2  jnz     short loc_14001FC6B
0x14001fca4  mov     rdx, [rsp+78h+arg_38]; unsigned __int64
0x14001fcac  mov     r8, rbx; void *
0x14001fcaf  mov     rcx, [rsp+78h+arg_40]; struct tagAVDTPFunctionTable *
0x14001fcb7  call    ?GetFnTable@Avdtp_impl@@CAJPEAUtagAVDTPFunctionTable@@_KPEAX@Z; Avdtp_impl::GetFnTable(tagAVDTPFunctionTable *,unsigned __int64,void *)
0x14001fcbc  mov     dword ptr [rbx+708h], 1
0x14001fcc6  jmp     short loc_14001FCEA
0x14001fcc8  cmp     [rsp+78h+arg_40], 0
0x14001fcd1  jz      short loc_14001FCEA
0x14001fcd3  mov     r8, [rsp+78h+arg_38]; Size
0x14001fcdb  xor     edx, edx; Val
0x14001fcdd  mov     rcx, [rsp+78h+arg_40]; void *
0x14001fce5  call    memset
0x14001fcea  mov     rax, rbx
0x14001fced  jmp     short loc_14001FCF1
0x14001fcef  xor     eax, eax
0x14001fcf1  add     rsp, 48h
0x14001fcf5  pop     r15
0x14001fcf7  pop     r14
0x14001fcf9  pop     r13
0x14001fcfb  pop     r12
0x14001fcfd  pop     rbp
0x14001fcfe  pop     rbx
0x14001fcff  retn
```
