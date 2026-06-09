# USBSTOR_SelectConfiguration

- ea: `0x1400279c0`
- end: `0x140027d17`
- name: `USBSTOR_SelectConfiguration`
- size: `855`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x140008590`

## callees

- `0x140001950`
- `0x140003630`
- `0x1400105e8`
- `0x140010664`
- `0x140010e18`
- `0x140013a40`
- `0x140013d40`
- `0x1400279c0`
- `0x140027d20`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140027a4c`
- `ntoskrnl!ExAllocatePool2` at `0x140027b2c`
- `ntoskrnl!ExAllocatePool2` at `0x140027a4c`
- `ntoskrnl!ExAllocatePool2` at `0x140027b2c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027c84`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027caa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027c84`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027caa`
- `USBD!USBD_CreateConfigurationRequestEx` at `0x140027ae2`
- `USBD!USBD_CreateConfigurationRequestEx` at `0x140027ae2`

## pseudocode

```c
__int64 __fastcall USBSTOR_SelectConfiguration(__int64 a1)
{
  __int64 v2; // rsi
  struct _USB_CONFIGURATION_DESCRIPTOR *v3; // rbx
  struct _USBD_INTERFACE_LIST_ENTRY *Pool2; // r12
  struct _USB_INTERFACE_DESCRIPTOR *v5; // rax
  PURB ConfigurationRequest; // rax
  _WORD *p_Length; // rdi
  int v8; // ebx
  _WORD *v9; // r14
  void *v10; // rax
  __int16 v11; // cx
  __int64 v12; // r8
  unsigned int i; // ebx
  int v15; // [rsp+80h] [rbp+48h] BYREF
  int v16; // [rsp+88h] [rbp+50h] BYREF
  int v17; // [rsp+90h] [rbp+58h] BYREF
  struct _USB_INTERFACE_DESCRIPTOR *v18; // [rsp+98h] [rbp+60h] BYREF

  v18 = 0;
  v16 = 0;
  v17 = 0;
  v15 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 159, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1313817427, a1, 0, 0);
  v2 = *(_QWORD *)(a1 + 64);
  v3 = *(struct _USB_CONFIGURATION_DESCRIPTOR **)(v2 + 56);
  Pool2 = (struct _USBD_INTERFACE_LIST_ENTRY *)ExAllocatePool2(256, 32, 1396788565);
  if ( Pool2 )
  {
    USBSTOR_AdjustConfigurationDescriptor(
      a1,
      *(_QWORD *)(v2 + 56),
      (unsigned int)&v18,
      (unsigned int)&v16,
      (__int64)&v17,
      (__int64)&v15);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 160, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
    }
    v5 = v18;
    *(_QWORD *)(v2 + 64) = v18;
    if ( v5 )
    {
      Pool2->InterfaceDescriptor = v5;
      Pool2[1].InterfaceDescriptor = 0;
      v3->bNumInterfaces = 1;
      ConfigurationRequest = USBD_CreateConfigurationRequestEx(v3, Pool2);
      p_Length = &ConfigurationRequest->UrbHeader.Length;
      if ( ConfigurationRequest )
      {
        v8 = USBSTOR_SyncSendUsbRequest(a1, ConfigurationRequest);
        if ( v8 >= 0 )
        {
          v9 = p_Length + 16;
          *(_QWORD *)(v2 + 80) = *((_QWORD *)p_Length + 4);
          v10 = (void *)ExAllocatePool2(64, (unsigned __int16)p_Length[20], 1396788565);
          *(_QWORD *)(v2 + 88) = v10;
          if ( v10 )
          {
            memmove(v10, p_Length + 20, (unsigned __int16)p_Length[20]);
            memset(p_Length, 0, 24LL * *(unsigned int *)(*(_QWORD *)(v2 + 88) + 16LL) + 56);
            v11 = *(_WORD *)(*(_QWORD *)(v2 + 88) + 16LL);
            p_Length[1] = 1;
            *p_Length = 24 * v11 + 56;
            *((_QWORD *)p_Length + 3) = *(_QWORD *)(v2 + 80);
            memmove(p_Length + 16, *(const void **)(v2 + 88), **(unsigned __int16 **)(v2 + 88));
            for ( i = 0; (signed int)i < *((_DWORD *)p_Length + 12); ++i )
            {
              if ( i == v16 || i == v17 )
              {
                *(_DWORD *)&v9[12 * i + 20] = 0x20000;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  WPP_SF_dD(WPP_GLOBAL_Control->AttachedDevice, 161, v12, i, 0x20000);
                }
              }
              else if ( i == v15 )
              {
                v12 = 2;
                *(_DWORD *)&v9[12 * i + 20] = 2;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  WPP_SF_dD(WPP_GLOBAL_Control->AttachedDevice, 162, 2, i, 2);
                }
              }
            }
            v8 = USBSTOR_SyncSendUsbRequest(a1, p_Length);
            if ( v8 >= 0 )
              memmove(*(void **)(v2 + 88), p_Length + 16, **(unsigned __int16 **)(v2 + 88));
          }
          else
          {
            v8 = -1073741670;
          }
        }
        ExFreePoolWithTag(p_Length, 0);
      }
      else
      {
        v8 = -1073741670;
      }
    }
    else
    {
      v8 = -1073741823;
    }
    ExFreePoolWithTag(Pool2, 0);
  }
  else
  {
    v8 = -1073741670;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 163, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1852793715, v8, 0, 0);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400279c0  push    rbp
0x1400279c2  push    rbx
0x1400279c3  push    rsi
0x1400279c4  push    rdi
0x1400279c5  push    r12
0x1400279c7  push    r13
0x1400279c9  push    r14
0x1400279cb  push    r15
0x1400279cd  mov     rbp, rsp
0x1400279d0  sub     rsp, 38h
0x1400279d4  xor     r13d, r13d
0x1400279d7  mov     r15, rcx
0x1400279da  mov     [rbp+arg_18], r13
0x1400279de  mov     [rbp+arg_8], r13d
0x1400279e2  mov     [rbp+arg_10], r13d
0x1400279e6  mov     [rbp+arg_0], r13d
0x1400279ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400279f1  lea     rdi, WPP_GLOBAL_Control
0x1400279f8  cmp     rcx, rdi
0x1400279fb  jz      short loc_140027A21
0x1400279fd  test    dword ptr [rcx+2Ch], 100h
0x140027a04  jz      short loc_140027A21
0x140027a06  cmp     byte ptr [rcx+29h], 4
0x140027a0a  jb      short loc_140027A21
0x140027a0c  mov     rcx, [rcx+18h]
0x140027a10  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140027a17  mov     edx, 9Fh
0x140027a1c  call    WPP_SF_
0x140027a21  xor     r9d, r9d
0x140027a24  xor     r8d, r8d
0x140027a27  mov     rdx, r15
0x140027a2a  mov     ecx, 4E4F4353h
0x140027a2f  call    USBSTOR_LogEntry
0x140027a34  mov     rsi, [r15+40h]
0x140027a38  mov     edx, 20h ; ' '
0x140027a3d  mov     ecx, 100h
0x140027a42  mov     r8d, 53414D55h
0x140027a48  mov     rbx, [rsi+38h]
0x140027a4c  call    cs:__imp_ExAllocatePool2
0x140027a53  nop     dword ptr [rax+rax+00h]
0x140027a58  mov     r12, rax
0x140027a5b  test    rax, rax
0x140027a5e  jz      loc_140027CB8
0x140027a64  mov     rdx, [rsi+38h]
0x140027a68  lea     rax, [rbp+arg_0]
0x140027a6c  mov     [rsp+38h+var_10], rax
0x140027a71  lea     r9, [rbp+arg_8]
0x140027a75  lea     rax, [rbp+arg_10]
0x140027a79  mov     rcx, r15
0x140027a7c  lea     r8, [rbp+arg_18]
0x140027a80  mov     [rsp+38h+var_18], rax
0x140027a85  call    USBSTOR_AdjustConfigurationDescriptor
0x140027a8a  mov     rcx, cs:WPP_GLOBAL_Control
0x140027a91  cmp     rcx, rdi
0x140027a94  jz      short loc_140027ABE
0x140027a96  test    dword ptr [rcx+2Ch], 100h
0x140027a9d  jz      short loc_140027ABE
0x140027a9f  cmp     byte ptr [rcx+29h], 2
0x140027aa3  jb      short loc_140027ABE
0x140027aa5  mov     r9d, [rbp+arg_0]
0x140027aa9  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140027ab0  mov     rcx, [rcx+18h]
0x140027ab4  mov     edx, 0A0h
0x140027ab9  call    WPP_SF_d
0x140027abe  mov     rax, [rbp+arg_18]
0x140027ac2  mov     [rsi+40h], rax
0x140027ac6  test    rax, rax
0x140027ac9  jz      loc_140027CA0
0x140027acf  mov     [r12], rax
0x140027ad3  mov     rdx, r12; InterfaceList
0x140027ad6  mov     [r12+10h], r13
0x140027adb  mov     rcx, rbx; ConfigurationDescriptor
0x140027ade  mov     byte ptr [rbx+4], 1
0x140027ae2  call    cs:__imp_USBD_CreateConfigurationRequestEx
0x140027ae9  nop     dword ptr [rax+rax+00h]
0x140027aee  mov     rdi, rax
0x140027af1  test    rax, rax
0x140027af4  jz      loc_140027C92
0x140027afa  mov     rdx, rax
0x140027afd  mov     rcx, r15
0x140027b00  call    USBSTOR_SyncSendUsbRequest
0x140027b05  mov     ebx, eax
0x140027b07  test    eax, eax
0x140027b09  js      loc_140027C7F
0x140027b0f  lea     r14, [rdi+20h]
0x140027b13  mov     ecx, 40h ; '@'
0x140027b18  mov     rax, [r14]
0x140027b1b  lea     rbx, [rdi+28h]
0x140027b1f  mov     [rsi+50h], rax
0x140027b23  mov     r8d, 53414D55h
0x140027b29  movzx   edx, word ptr [rbx]
0x140027b2c  call    cs:__imp_ExAllocatePool2
0x140027b33  nop     dword ptr [rax+rax+00h]
0x140027b38  mov     [rsi+58h], rax
0x140027b3c  test    rax, rax
0x140027b3f  jz      loc_140027C7A
0x140027b45  movzx   r8d, word ptr [rbx]; Size
0x140027b49  mov     rdx, rbx; Src
0x140027b4c  mov     rcx, rax; void *
0x140027b4f  call    memmove
0x140027b54  mov     rax, [rsi+58h]
0x140027b58  xor     edx, edx; Val
0x140027b5a  mov     ecx, [rax+10h]
0x140027b5d  lea     r8, [rcx+rcx*2]
0x140027b61  mov     rcx, rdi; void *
0x140027b64  lea     r8, ds:38h[r8*8]; Size
0x140027b6c  call    memset
0x140027b71  mov     rax, [rsi+58h]
0x140027b75  movzx   ecx, word ptr [rax+10h]
0x140027b79  movzx   eax, cx
0x140027b7c  mov     word ptr [rdi+2], 1
0x140027b82  add     ax, ax
0x140027b85  add     cx, ax
0x140027b88  shl     cx, 3
0x140027b8c  add     cx, 38h ; '8'
0x140027b90  mov     [rdi], cx
0x140027b93  mov     rcx, r14; void *
0x140027b96  mov     rax, [rsi+50h]
0x140027b9a  mov     [rdi+18h], rax
0x140027b9e  mov     rdx, [rsi+58h]; Src
0x140027ba2  movzx   r8d, word ptr [rdx]; Size
0x140027ba6  call    memmove
0x140027bab  mov     ebx, r13d
0x140027bae  cmp     [r14+10h], r13d
0x140027bb2  jle     loc_140027C57
0x140027bb8  lea     r13, WPP_GLOBAL_Control
0x140027bbf  cmp     ebx, [rbp+arg_8]
0x140027bc2  jz      short loc_140027C07
0x140027bc4  cmp     ebx, [rbp+arg_10]
0x140027bc7  jz      short loc_140027C07
0x140027bc9  cmp     ebx, [rbp+arg_0]
0x140027bcc  jnz     short loc_140027C4B
0x140027bce  movsxd  rax, ebx
0x140027bd1  mov     r8d, 2
0x140027bd7  lea     rcx, [rax+rax*2]
0x140027bdb  mov     [r14+rcx*8+28h], r8d
0x140027be0  mov     rcx, cs:WPP_GLOBAL_Control
0x140027be7  cmp     rcx, r13
0x140027bea  jz      short loc_140027C4B
0x140027bec  test    dword ptr [rcx+2Ch], 100h
0x140027bf3  jz      short loc_140027C4B
0x140027bf5  cmp     [rcx+29h], r8b
0x140027bf9  jb      short loc_140027C4B
0x140027bfb  mov     edx, 0A2h
0x140027c00  mov     dword ptr [rsp+38h+var_18], r8d
0x140027c05  jmp     short loc_140027C3F
0x140027c07  movsxd  rax, ebx
0x140027c0a  lea     rcx, [rax+rax*2]
0x140027c0e  mov     dword ptr [r14+rcx*8+28h], 20000h
0x140027c17  mov     rcx, cs:WPP_GLOBAL_Control
0x140027c1e  cmp     rcx, r13
0x140027c21  jz      short loc_140027C4B
0x140027c23  test    dword ptr [rcx+2Ch], 100h
0x140027c2a  jz      short loc_140027C4B
0x140027c2c  cmp     byte ptr [rcx+29h], 2
0x140027c30  jb      short loc_140027C4B
0x140027c32  mov     edx, 0A1h
0x140027c37  mov     dword ptr [rsp+38h+var_18], 20000h
0x140027c3f  mov     rcx, [rcx+18h]
0x140027c43  mov     r9d, ebx
0x140027c46  call    WPP_SF_dD
0x140027c4b  inc     ebx
0x140027c4d  cmp     ebx, [r14+10h]
0x140027c51  jl      loc_140027BBF
0x140027c57  mov     rdx, rdi
0x140027c5a  mov     rcx, r15
0x140027c5d  call    USBSTOR_SyncSendUsbRequest
0x140027c62  mov     ebx, eax
0x140027c64  test    eax, eax
0x140027c66  js      short loc_140027C7F
0x140027c68  mov     rcx, [rsi+58h]; void *
0x140027c6c  mov     rdx, r14; Src
0x140027c6f  movzx   r8d, word ptr [rcx]; Size
0x140027c73  call    memmove
0x140027c78  jmp     short loc_140027C7F
0x140027c7a  mov     ebx, 0C000009Ah
0x140027c7f  xor     edx, edx; Tag
0x140027c81  mov     rcx, rdi; P
0x140027c84  call    cs:__imp_ExFreePoolWithTag
0x140027c8b  nop     dword ptr [rax+rax+00h]
0x140027c90  jmp     short loc_140027C97
0x140027c92  mov     ebx, 0C000009Ah
0x140027c97  lea     rdi, WPP_GLOBAL_Control
0x140027c9e  jmp     short loc_140027CA5
0x140027ca0  mov     ebx, 0C0000001h
0x140027ca5  xor     edx, edx; Tag
0x140027ca7  mov     rcx, r12; P
0x140027caa  call    cs:__imp_ExFreePoolWithTag
0x140027cb1  nop     dword ptr [rax+rax+00h]
0x140027cb6  jmp     short loc_140027CBD
0x140027cb8  mov     ebx, 0C000009Ah
0x140027cbd  mov     rcx, cs:WPP_GLOBAL_Control
0x140027cc4  cmp     rcx, rdi
0x140027cc7  jz      short loc_140027CF0
0x140027cc9  test    dword ptr [rcx+2Ch], 100h
0x140027cd0  jz      short loc_140027CF0
0x140027cd2  cmp     byte ptr [rcx+29h], 4
0x140027cd6  jb      short loc_140027CF0
0x140027cd8  mov     rcx, [rcx+18h]
0x140027cdc  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140027ce3  mov     edx, 0A3h
0x140027ce8  mov     r9d, ebx
0x140027ceb  call    WPP_SF_d
0x140027cf0  movsxd  rdx, ebx
0x140027cf3  xor     r9d, r9d
0x140027cf6  xor     r8d, r8d
0x140027cf9  mov     ecx, 6E6F6373h
0x140027cfe  call    USBSTOR_LogEntry
0x140027d03  mov     eax, ebx
0x140027d05  add     rsp, 38h
0x140027d09  pop     r15
0x140027d0b  pop     r14
0x140027d0d  pop     r13
0x140027d0f  pop     r12
0x140027d11  pop     rdi
0x140027d12  pop     rsi
0x140027d13  pop     rbx
0x140027d14  pop     rbp
0x140027d15  retn
```
