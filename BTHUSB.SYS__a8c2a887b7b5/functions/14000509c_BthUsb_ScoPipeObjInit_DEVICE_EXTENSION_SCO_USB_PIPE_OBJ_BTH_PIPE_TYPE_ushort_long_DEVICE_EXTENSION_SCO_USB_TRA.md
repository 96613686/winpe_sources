# BthUsb_ScoPipeObjInit(_DEVICE_EXTENSION *,_SCO_USB_PIPE_OBJ *,_BTH_PIPE_TYPE,ushort,long (*)(_DEVICE_EXTENSION *,_SCO_USB_TRANSFER_CTX *),long (*)(_DEVICE_EXTENSION *,_SCO_USB_TRANSFER_CTX *),ulong (*)(_DEVICE_EXTENSION *,_SCO_USB_TRANSFER_CTX *,ushort,ulong),ulong (*)(_DEVICE_EXTENSION *,_SCO_USB_TRANSFER_CTX *,ushort,ulong))

- ea: `0x14000509c`
- end: `0x140005171`
- name: `?BthUsb_ScoPipeObjInit@@YAXPEAU_DEVICE_EXTENSION@@PEAU_SCO_USB_PIPE_OBJ@@W4_BTH_PIPE_TYPE@@GP6AJ0PEAU_SCO_USB_TRANSFER_CTX@@@Z4P6AK03GK@Z5@Z`
- size: `213`
- prototype: `void(struct _DEVICE_EXTENSION *, struct _SCO_USB_PIPE_OBJ *, enum _BTH_PIPE_TYPE, unsigned __int16, int (*)(struct _DEVICE_EXTENSION *, struct _SCO_USB_TRANSFER_CTX *), int (*)(struct _DEVICE_EXTENSION *, struct _SCO_USB_TRANSFER_CTX *), unsigned int (*)(struct _DEVICE_EXTENSION *, struct _SCO_USB_TRANSFER_CTX *, unsigned __int16, unsigned int), unsigned int (*)(struct _DEVICE_EXTENSION *, struct _SCO_USB_TRANSFER_CTX *, unsigned __int16, unsigned int))`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400078a0`
- `0x140009340`

## callees

- `0x14000187c`
- `0x14000509c`
- `0x14000e1c0`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x140005149`
- `ntoskrnl!KeInitializeSpinLock` at `0x140005149`

## pseudocode

```c
void __fastcall BthUsb_ScoPipeObjInit(
        struct _DEVICE_EXTENSION *a1,
        struct _SCO_USB_PIPE_OBJ *a2,
        enum _BTH_PIPE_TYPE a3,
        unsigned __int16 a4,
        int (*a5)(struct _DEVICE_EXTENSION *, struct _SCO_USB_TRANSFER_CTX *),
        int (*a6)(struct _DEVICE_EXTENSION *, struct _SCO_USB_TRANSFER_CTX *),
        unsigned int (*a7)(struct _DEVICE_EXTENSION *, struct _SCO_USB_TRANSFER_CTX *, unsigned __int16, unsigned int),
        unsigned int (*a8)(struct _DEVICE_EXTENSION *, struct _SCO_USB_TRANSFER_CTX *, unsigned __int16, unsigned int))
{
  struct _SCO_USB_PIPE_OBJ *v10; // rbx

  v10 = a2;
  LOBYTE(a2) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_q(
    WPP_GLOBAL_Control->AttachedDevice,
    (_DWORD)a2,
    a3,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    4,
    95,
    (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids,
    (char)v10);
  memset(v10, 0, sizeof(struct _SCO_USB_PIPE_OBJ));
  v10->FnCompleteUrb = (int (__fastcall *)(_DEVICE_EXTENSION *, _SCO_USB_TRANSFER_CTX *))a6;
  v10->FnSendUrb = (int (__fastcall *)(_DEVICE_EXTENSION *, _SCO_USB_TRANSFER_CTX *))a5;
  v10->FnAlignFrame = (unsigned int (__fastcall *)(_DEVICE_EXTENSION *, _SCO_USB_TRANSFER_CTX *, unsigned __int16, unsigned int))a7;
  v10->FnGetNextFrame = (unsigned int (__fastcall *)(_DEVICE_EXTENSION *, _SCO_USB_TRANSFER_CTX *, unsigned __int16, unsigned int))a8;
  v10->PipeType = a3;
  v10->Id = a4;
  KeInitializeSpinLock(&v10->Lock);
  v10->InProgressUrbsHead.Blink = &v10->InProgressUrbsHead;
  v10->InProgressUrbsHead.Flink = &v10->InProgressUrbsHead;
}

```

## disassembly

```asm
0x14000509c  mov     [rsp+arg_0], rbx
0x1400050a1  mov     [rsp+arg_8], rsi
0x1400050a6  push    rdi
0x1400050a7  sub     rsp, 50h
0x1400050ab  movzx   edi, r9w
0x1400050af  mov     esi, r8d
0x1400050b2  mov     rbx, rdx
0x1400050b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400050bc  mov     eax, [rcx+2Ch]
0x1400050bf  test    al, 8
0x1400050c1  jz      short loc_1400050CD
0x1400050c3  cmp     byte ptr [rcx+29h], 4
0x1400050c7  jb      short loc_1400050CD
0x1400050c9  mov     dl, 1
0x1400050cb  jmp     short loc_1400050CF
0x1400050cd  xor     dl, dl
0x1400050cf  mov     r9, [rcx+40h]
0x1400050d3  lea     rax, WPP_89eaa7be148f36a90e353489c15db76f_Traceguids
0x1400050da  mov     rcx, [rcx+18h]
0x1400050de  mov     [rsp+58h+var_18], rbx
0x1400050e3  mov     [rsp+58h+var_20], rax
0x1400050e8  mov     [rsp+58h+var_28], 5Fh ; '_'
0x1400050ef  mov     [rsp+58h+var_30], 4
0x1400050f7  mov     [rsp+58h+var_38], 4
0x1400050fc  call    WPP_RECORDER_AND_TRACE_SF_q
0x140005101  xor     edx, edx; Val
0x140005103  mov     rcx, rbx; void *
0x140005106  lea     r8d, [rdx+50h]; Size
0x14000510a  call    memset
0x14000510f  mov     rax, [rsp+58h+arg_28]
0x140005117  lea     rcx, [rbx+28h]; SpinLock
0x14000511b  mov     [rbx+8], rax
0x14000511f  mov     rax, [rsp+58h+arg_20]
0x140005127  mov     [rbx], rax
0x14000512a  mov     rax, [rsp+58h+arg_30]
0x140005132  mov     [rbx+10h], rax
0x140005136  mov     rax, [rsp+58h+arg_38]
0x14000513e  mov     [rbx+18h], rax
0x140005142  mov     [rbx+20h], esi
0x140005145  mov     [rbx+24h], di
0x140005149  call    cs:__imp_KeInitializeSpinLock
0x140005150  nop     dword ptr [rax+rax+00h]
0x140005155  mov     rsi, [rsp+58h+arg_8]
0x14000515a  lea     rax, [rbx+38h]
0x14000515e  mov     rbx, [rsp+58h+arg_0]
0x140005163  mov     [rax+8], rax
0x140005167  mov     [rax], rax
0x14000516a  add     rsp, 50h
0x14000516e  pop     rdi
0x14000516f  retn
```
