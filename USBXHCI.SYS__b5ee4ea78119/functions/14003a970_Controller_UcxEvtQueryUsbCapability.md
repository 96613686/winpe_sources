# Controller_UcxEvtQueryUsbCapability

- ea: `0x14003a970`
- end: `0x14003af60`
- name: `Controller_UcxEvtQueryUsbCapability`
- size: `1520`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x14001ac48`
- `0x14001ad0c`
- `0x140035fcc`
- `0x1400386c4`
- `0x14003a970`
- `0x14003b144`
- `0x1400599b0`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14003a9d5`
- `ntoskrnl!RtlCompareMemory` at `0x14003aa3b`
- `ntoskrnl!RtlCompareMemory` at `0x14003aaa0`
- `ntoskrnl!RtlCompareMemory` at `0x14003ab3b`
- `ntoskrnl!RtlCompareMemory` at `0x14003ab75`
- `ntoskrnl!RtlCompareMemory` at `0x14003abab`
- `ntoskrnl!RtlCompareMemory` at `0x14003ac04`
- `ntoskrnl!RtlCompareMemory` at `0x14003ac83`
- `ntoskrnl!RtlCompareMemory` at `0x14003ad95`
- `ntoskrnl!RtlCompareMemory` at `0x14003ae8b`
- `ntoskrnl!RtlCompareMemory` at `0x14003a9d5`
- `ntoskrnl!RtlCompareMemory` at `0x14003aa3b`
- `ntoskrnl!RtlCompareMemory` at `0x14003aaa0`
- `ntoskrnl!RtlCompareMemory` at `0x14003ab3b`
- `ntoskrnl!RtlCompareMemory` at `0x14003ab75`
- `ntoskrnl!RtlCompareMemory` at `0x14003abab`
- `ntoskrnl!RtlCompareMemory` at `0x14003ac04`
- `ntoskrnl!RtlCompareMemory` at `0x14003ac83`
- `ntoskrnl!RtlCompareMemory` at `0x14003ad95`
- `ntoskrnl!RtlCompareMemory` at `0x14003ae8b`

## pseudocode

```c
__int64 __fastcall Controller_UcxEvtQueryUsbCapability(
        __int64 a1,
        const void *a2,
        unsigned int a3,
        _WORD *a4,
        _DWORD *a5)
{
  int v8; // r13d
  __int64 v9; // rsi
  int v10; // edx
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  int v14; // r9d
  int v15; // r9d
  unsigned int v16; // ebx
  int v17; // r9d
  int v18; // r9d
  int v20; // [rsp+90h] [rbp+8h]

  v20 = a1;
  LOBYTE(v8) = 0;
  v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
         WdfDriverGlobals,
         a1,
         off_14006C310);
  *a5 = 0;
  if ( RtlCompareMemory(a2, &GUID_USB_CAPABILITY_CHAINED_MDLS, 0x10u) == 16 )
  {
    LOBYTE(v11) = *(_BYTE *)(v9 + 736);
    if ( (v11 & 0x80u) != 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v13 = 205;
LABEL_38:
        LOBYTE(v10) = 4;
        WPP_RECORDER_SF_(*(_QWORD *)(v9 + 72), v10, 4, v13, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids);
        goto LABEL_39;
      }
      goto LABEL_39;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v14 = 206;
LABEL_30:
      LOBYTE(v10) = 4;
      WPP_RECORDER_SF_(*(_QWORD *)(v9 + 72), v10, 4, v14, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids);
      goto LABEL_31;
    }
    goto LABEL_31;
  }
  if ( RtlCompareMemory(a2, &GUID_USB_CAPABILITY_SECURE_TRANSFERS, 0x10u) == 16 )
  {
    if ( !*(_BYTE *)(v9 + 1041) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v13 = 207;
        goto LABEL_38;
      }
LABEL_39:
      v16 = -1073741637;
      goto LABEL_85;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v14 = 208;
      goto LABEL_30;
    }
LABEL_31:
    v16 = 0;
    goto LABEL_85;
  }
  if ( RtlCompareMemory(a2, &GUID_USB_CAPABILITY_STATIC_STREAMS, 0x10u) == 16 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 4;
      WPP_RECORDER_SF_(*(_QWORD *)(v9 + 72), v10, 4, 209, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids);
    }
    *a5 = 2;
    if ( a3 >= 2 )
    {
      if ( a4 )
      {
        v8 = *(_DWORD *)(*(_QWORD *)(v9 + 88) + 116LL);
        *a4 = v8;
        goto LABEL_31;
      }
      goto LABEL_52;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_71;
    v15 = 210;
    LOBYTE(v10) = 4;
    goto LABEL_70;
  }
  if ( RtlCompareMemory(a2, &GUID_USB_CAPABILITY_FUNCTION_SUSPEND, 0x10u) == 16 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v14 = 211;
      goto LABEL_30;
    }
    goto LABEL_31;
  }
  if ( RtlCompareMemory(a2, &GUID_USB_CAPABILITY_SELECTIVE_SUSPEND, 0x10u) == 16 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v14 = 212;
      goto LABEL_30;
    }
    goto LABEL_31;
  }
  if ( RtlCompareMemory(a2, &GUID_USB_CAPABILITY_TIME_SYNC, 0x10u) == 16 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v14 = 213;
      goto LABEL_30;
    }
    goto LABEL_31;
  }
  if ( RtlCompareMemory(a2, &GUID_USB_CAPABILITY_CLEAR_TT_BUFFER_ON_ASYNC_TRANSFER_CANCEL, 0x10u) == 16 )
  {
    if ( !_bittest64((const signed __int64 *)(v9 + 736), 0x20u) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v13 = 215;
        goto LABEL_38;
      }
      goto LABEL_39;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v14 = 214;
      goto LABEL_30;
    }
    goto LABEL_31;
  }
  if ( RtlCompareMemory(a2, &GUID_USB_CAPABILITY_HIGH_BANDWIDTH_ISOCH, 0x10u) == 16 )
  {
    *a5 = 4;
    if ( a3 >= 4 )
    {
      if ( a4 )
      {
        v11 = *(_DWORD *)(*(_QWORD *)(v9 + 88) + 108LL);
        if ( (v11 & 0x10) == 0 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_39;
          v13 = 217;
          goto LABEL_38;
        }
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v10) = 4;
          WPP_RECORDER_SF_(*(_QWORD *)(v9 + 72), v10, 4, 216, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids);
        }
        v11 = *(_BYTE *)(v9 + 1050) != 0 ? 32 : 4;
        *(_DWORD *)a4 = v11;
        goto LABEL_31;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_52;
      v17 = 218;
LABEL_51:
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_(*(_QWORD *)(v9 + 72), v10, 4, v17, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids);
LABEL_52:
      v16 = -1073741811;
      goto LABEL_85;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v15 = 219;
LABEL_69:
      LOBYTE(v10) = 2;
LABEL_70:
      WPP_RECORDER_SF_d(*(_QWORD *)(v9 + 72), v10, 4, v15, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids, a3);
      goto LABEL_71;
    }
    goto LABEL_71;
  }
  if ( RtlCompareMemory(a2, &GUID_USB_CAPABILITY_ENDPOINT_OFFLOAD, 0x10u) == 16 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 4;
      WPP_RECORDER_SF_(*(_QWORD *)(v9 + 72), v10, 4, 220, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids);
    }
    *a5 = 4;
    if ( a3 >= 4 )
    {
      if ( a4 )
      {
        v11 = *(_DWORD *)(v9 + 1084);
        if ( !v11 )
          goto LABEL_39;
        if ( --v11 )
        {
          if ( v11 != 1 )
            goto LABEL_39;
          *(_DWORD *)a4 = 2;
        }
        else
        {
          *(_DWORD *)a4 = 1;
        }
        goto LABEL_31;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_52;
      v17 = 221;
      goto LABEL_51;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v15 = 222;
      goto LABEL_69;
    }
LABEL_71:
    v16 = -1073741789;
    goto LABEL_85;
  }
  if ( (unsigned int)Feature_EUSB2__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( RtlCompareMemory(a2, &GUID_USB_CAPABILITY_CONTROLLER_EUSB2_DOUBLE_ISOCH_COMPATIBLE, 0x10u) == 16 )
    {
      if ( (*(_DWORD *)(*(_QWORD *)(v9 + 88) + 108LL) & 0x800) == 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_39;
        v13 = 224;
        goto LABEL_38;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v14 = 223;
        goto LABEL_30;
      }
      goto LABEL_31;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_84;
    v18 = 225;
    goto LABEL_83;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v18 = 226;
LABEL_83:
    WPP_RECORDER_SF__guid_(*(_QWORD *)(v9 + 72), v10, v12, v18);
  }
LABEL_84:
  v16 = -1073741822;
LABEL_85:
  if ( SLOBYTE(WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc) < 0 )
    McTemplateK0pjqq_EtwWriteTransfer(v11, v10, v12, v20, (__int64)a2, v16, v8);
  return v16;
}

```

## disassembly

```asm
0x14003a970  mov     [rsp+arg_0], rcx
0x14003a975  push    rbx
0x14003a976  push    rbp
0x14003a977  push    rsi
0x14003a978  push    rdi
0x14003a979  push    r12
0x14003a97b  push    r13
0x14003a97d  push    r14
0x14003a97f  push    r15
0x14003a981  sub     rsp, 48h
0x14003a985  mov     rax, cs:WdfFunctions_01033
0x14003a98c  mov     rbp, rdx
0x14003a98f  mov     r15d, r8d
0x14003a992  mov     rdx, rcx
0x14003a995  mov     r8, cs:off_14006C310
0x14003a99c  mov     r14, r9
0x14003a99f  mov     rcx, cs:WdfDriverGlobals
0x14003a9a6  mov     rax, [rax+650h]
0x14003a9ad  call    _guard_dispatch_icall
0x14003a9b2  mov     r12, [rsp+88h+arg_20]
0x14003a9ba  lea     rdx, GUID_USB_CAPABILITY_CHAINED_MDLS; Source2
0x14003a9c1  xor     r13d, r13d
0x14003a9c4  mov     rcx, rbp; Source1
0x14003a9c7  mov     rsi, rax
0x14003a9ca  mov     [r12], r13d
0x14003a9ce  lea     ebx, [r13+10h]
0x14003a9d2  mov     r8d, ebx; Length
0x14003a9d5  call    cs:__imp_RtlCompareMemory
0x14003a9dc  nop     dword ptr [rax+rax+00h]
0x14003a9e1  cmp     rax, rbx
0x14003a9e4  jnz     short loc_14003AA2E
0x14003a9e6  mov     cl, [rsi+2E0h]
0x14003a9ec  test    cl, cl
0x14003a9ee  jns     short loc_14003AA0F
0x14003a9f0  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003a9f7  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14003a9fe  jz      loc_14003AC6C
0x14003aa04  mov     r9d, 0CDh
0x14003aa0a  jmp     loc_14003AC4E
0x14003aa0f  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003aa16  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14003aa1d  jz      loc_14003ABF0
0x14003aa23  mov     r9d, 0CEh
0x14003aa29  jmp     loc_14003ABD2
0x14003aa2e  mov     r8, rbx; Length
0x14003aa31  lea     rdx, GUID_USB_CAPABILITY_SECURE_TRANSFERS; Source2
0x14003aa38  mov     rcx, rbp; Source1
0x14003aa3b  call    cs:__imp_RtlCompareMemory
0x14003aa42  nop     dword ptr [rax+rax+00h]
0x14003aa47  cmp     rax, rbx
0x14003aa4a  jnz     short loc_14003AA93
0x14003aa4c  cmp     [rsi+411h], r13b
0x14003aa53  jnz     short loc_14003AA74
0x14003aa55  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003aa5c  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14003aa63  jz      loc_14003AC6C
0x14003aa69  mov     r9d, 0CFh
0x14003aa6f  jmp     loc_14003AC4E
0x14003aa74  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003aa7b  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14003aa82  jz      loc_14003ABF0
0x14003aa88  mov     r9d, 0D0h
0x14003aa8e  jmp     loc_14003ABD2
0x14003aa93  mov     r8, rbx; Length
0x14003aa96  lea     rdx, GUID_USB_CAPABILITY_STATIC_STREAMS; Source2
0x14003aa9d  mov     rcx, rbp; Source1
0x14003aaa0  call    cs:__imp_RtlCompareMemory
0x14003aaa7  nop     dword ptr [rax+rax+00h]
0x14003aaac  cmp     rax, rbx
0x14003aaaf  jnz     short loc_14003AB2E
0x14003aab1  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003aab8  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14003aabf  lea     rdi, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x14003aac6  jz      short loc_14003AAE5
0x14003aac8  mov     rcx, [rsi+48h]
0x14003aacc  mov     r8d, 4
0x14003aad2  mov     dl, r8b
0x14003aad5  mov     [rsp+88h+var_68], rdi
0x14003aada  mov     r9d, 0D1h
0x14003aae0  call    WPP_RECORDER_SF_
0x14003aae5  mov     dword ptr [r12], 2
0x14003aaed  cmp     r15d, 2
0x14003aaf1  jb      short loc_14003AB0D
0x14003aaf3  test    r14, r14
0x14003aaf6  jz      loc_14003AD58
0x14003aafc  mov     rax, [rsi+58h]
0x14003ab00  mov     r13d, [rax+74h]
0x14003ab04  mov     [r14], r13w
0x14003ab08  jmp     loc_14003ABF0
0x14003ab0d  cmp     cs:WPP_RECORDER_INITIALIZED, rbx; __annotation("TMF:",
0x14003ab14  jz      loc_14003AE67
0x14003ab1a  mov     r8d, 4
0x14003ab20  mov     r9d, 0D2h
0x14003ab26  mov     dl, r8b
0x14003ab29  jmp     loc_14003AE54
0x14003ab2e  mov     r8, rbx; Length
0x14003ab31  lea     rdx, GUID_USB_CAPABILITY_FUNCTION_SUSPEND; Source2
0x14003ab38  mov     rcx, rbp; Source1
0x14003ab3b  call    cs:__imp_RtlCompareMemory
0x14003ab42  nop     dword ptr [rax+rax+00h]
0x14003ab47  cmp     rax, rbx
0x14003ab4a  jnz     short loc_14003AB68
0x14003ab4c  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003ab53  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14003ab5a  jz      loc_14003ABF0
0x14003ab60  mov     r9d, 0D3h
0x14003ab66  jmp     short loc_14003ABD2
0x14003ab68  mov     r8, rbx; Length
0x14003ab6b  lea     rdx, GUID_USB_CAPABILITY_SELECTIVE_SUSPEND; Source2
0x14003ab72  mov     rcx, rbp; Source1
0x14003ab75  call    cs:__imp_RtlCompareMemory
0x14003ab7c  nop     dword ptr [rax+rax+00h]
0x14003ab81  cmp     rax, rbx
0x14003ab84  jnz     short loc_14003AB9E
0x14003ab86  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003ab8d  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14003ab94  jz      short loc_14003ABF0
0x14003ab96  mov     r9d, 0D4h
0x14003ab9c  jmp     short loc_14003ABD2
0x14003ab9e  mov     r8, rbx; Length
0x14003aba1  lea     rdx, GUID_USB_CAPABILITY_TIME_SYNC; Source2
0x14003aba8  mov     rcx, rbp; Source1
0x14003abab  call    cs:__imp_RtlCompareMemory
0x14003abb2  nop     dword ptr [rax+rax+00h]
0x14003abb7  cmp     rax, rbx
0x14003abba  jnz     short loc_14003ABF7
0x14003abbc  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003abc3  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14003abca  jz      short loc_14003ABF0
0x14003abcc  mov     r9d, 0D5h
0x14003abd2  mov     rcx, [rsi+48h]
0x14003abd6  lea     rdi, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x14003abdd  mov     r8d, 4
0x14003abe3  mov     [rsp+88h+var_68], rdi
0x14003abe8  mov     dl, r8b
0x14003abeb  call    WPP_RECORDER_SF_
0x14003abf0  xor     ebx, ebx
0x14003abf2  jmp     loc_14003AF28
0x14003abf7  mov     r8, rbx; Length
0x14003abfa  lea     rdx, GUID_USB_CAPABILITY_CLEAR_TT_BUFFER_ON_ASYNC_TRANSFER_CANCEL; Source2
0x14003ac01  mov     rcx, rbp; Source1
0x14003ac04  call    cs:__imp_RtlCompareMemory
0x14003ac0b  nop     dword ptr [rax+rax+00h]
0x14003ac10  cmp     rax, rbx
0x14003ac13  jnz     short loc_14003AC76
0x14003ac15  bt      qword ptr [rsi+2E0h], 20h ; ' '
0x14003ac1e  jnb     short loc_14003AC38
0x14003ac20  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003ac27  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14003ac2e  jz      short loc_14003ABF0
0x14003ac30  mov     r9d, 0D6h
0x14003ac36  jmp     short loc_14003ABD2
0x14003ac38  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003ac3f  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14003ac46  jz      short loc_14003AC6C
0x14003ac48  mov     r9d, 0D7h
0x14003ac4e  mov     rcx, [rsi+48h]
0x14003ac52  lea     rdi, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x14003ac59  mov     r8d, 4
0x14003ac5f  mov     [rsp+88h+var_68], rdi
0x14003ac64  mov     dl, r8b
0x14003ac67  call    WPP_RECORDER_SF_
0x14003ac6c  mov     ebx, 0C00000BBh
0x14003ac71  jmp     loc_14003AF28
0x14003ac76  mov     r8, rbx; Length
0x14003ac79  lea     rdx, GUID_USB_CAPABILITY_HIGH_BANDWIDTH_ISOCH; Source2
0x14003ac80  mov     rcx, rbp; Source1
0x14003ac83  call    cs:__imp_RtlCompareMemory
0x14003ac8a  nop     dword ptr [rax+rax+00h]
0x14003ac8f  cmp     rax, rbx
0x14003ac92  jnz     loc_14003AD88
0x14003ac98  mov     dword ptr [r12], 4
0x14003aca0  cmp     r15d, 4
0x14003aca4  jb      loc_14003AD62
0x14003acaa  test    r14, r14
0x14003acad  jz      short loc_14003AD25
0x14003acaf  mov     rax, [rsi+58h]
0x14003acb3  mov     ecx, [rax+6Ch]
0x14003acb6  test    bl, cl
0x14003acb8  jz      short loc_14003AD06
0x14003acba  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003acc1  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14003acc8  jz      short loc_14003ACEE
0x14003acca  mov     rcx, [rsi+48h]
0x14003acce  lea     rdi, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x14003acd5  mov     r8d, 4
0x14003acdb  mov     [rsp+88h+var_68], rdi
0x14003ace0  mov     dl, r8b
0x14003ace3  mov     r9d, 0D8h
0x14003ace9  call    WPP_RECORDER_SF_
0x14003acee  mov     al, [rsi+41Ah]
0x14003acf4  neg     al
0x14003acf6  sbb     ecx, ecx
0x14003acf8  and     ecx, 1Ch
0x14003acfb  add     ecx, 4
0x14003acfe  mov     [r14], ecx
0x14003ad01  jmp     loc_14003ABF0
0x14003ad06  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003ad0d  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14003ad14  jz      loc_14003AC6C
0x14003ad1a  mov     r9d, 0D9h
0x14003ad20  jmp     loc_14003AC4E
0x14003ad25  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003ad2c  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14003ad33  jz      short loc_14003AD58
0x14003ad35  mov     r9d, 0DAh
0x14003ad3b  lea     rdi, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x14003ad42  mov     rcx, [rsi+48h]
0x14003ad46  mov     r8d, 4
0x14003ad4c  mov     dl, 2
0x14003ad4e  mov     [rsp+88h+var_68], rdi
0x14003ad53  call    WPP_RECORDER_SF_
0x14003ad58  mov     ebx, 0C000000Dh
0x14003ad5d  jmp     loc_14003AF28
0x14003ad62  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003ad69  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14003ad70  jz      loc_14003AE67
0x14003ad76  mov     r9d, 0DBh
0x14003ad7c  lea     rdi, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x14003ad83  jmp     loc_14003AE4C
0x14003ad88  mov     r8, rbx; Length
0x14003ad8b  lea     rdx, GUID_USB_CAPABILITY_ENDPOINT_OFFLOAD; Source2
0x14003ad92  mov     rcx, rbp; Source1
0x14003ad95  call    cs:__imp_RtlCompareMemory
0x14003ad9c  nop     dword ptr [rax+rax+00h]
0x14003ada1  cmp     rax, rbx
0x14003ada4  jnz     loc_14003AE71
0x14003adaa  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003adb1  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14003adb8  lea     rdi, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x14003adbf  jz      short loc_14003ADDE
0x14003adc1  mov     rcx, [rsi+48h]
0x14003adc5  mov     r8d, 4
0x14003adcb  mov     dl, r8b
0x14003adce  mov     [rsp+88h+var_68], rdi
0x14003add3  mov     r9d, 0DCh
0x14003add9  call    WPP_RECORDER_SF_
0x14003adde  mov     dword ptr [r12], 4
0x14003ade6  cmp     r15d, 4
0x14003adea  jb      short loc_14003AE3D
0x14003adec  test    r14, r14
0x14003adef  jz      short loc_14003AE25
0x14003adf1  mov     ecx, [rsi+43Ch]
0x14003adf7  test    ecx, ecx
0x14003adf9  jz      loc_14003AC6C
0x14003adff  sub     ecx, 1
0x14003ae02  jz      short loc_14003AE19
0x14003ae04  cmp     ecx, 1
0x14003ae07  jnz     loc_14003AC6C
0x14003ae0d  mov     dword ptr [r14], 2
0x14003ae14  jmp     loc_14003ABF0
0x14003ae19  mov     dword ptr [r14], 1
0x14003ae20  jmp     loc_14003ABF0
0x14003ae25  cmp     cs:WPP_RECORDER_INITIALIZED, rbx; __annotation("TMF:",
0x14003ae2c  jz      loc_14003AD58
0x14003ae32  mov     r9d, 0DDh
0x14003ae38  jmp     loc_14003AD42
0x14003ae3d  cmp     cs:WPP_RECORDER_INITIALIZED, rbx; __annotation("TMF:",
0x14003ae44  jz      short loc_14003AE67
0x14003ae46  mov     r9d, 0DEh
0x14003ae4c  mov     r8d, 4
0x14003ae52  mov     dl, 2
0x14003ae54  mov     rcx, [rsi+48h]
0x14003ae58  mov     dword ptr [rsp+88h+var_60], r15d
0x14003ae5d  mov     [rsp+88h+var_68], rdi
0x14003ae62  call    WPP_RECORDER_SF_d
0x14003ae67  mov     ebx, 0C0000023h
0x14003ae6c  jmp     loc_14003AF28
0x14003ae71  call    Feature_EUSB2__private_IsEnabledDeviceUsageNoInline
0x14003ae76  test    eax, eax
0x14003ae78  jz      loc_14003AEFF
0x14003ae7e  mov     r8, rbx; Length
0x14003ae81  lea     rdx, GUID_USB_CAPABILITY_CONTROLLER_EUSB2_DOUBLE_ISOCH_COMPATIBLE; Source2
0x14003ae88  mov     rcx, rbp; Source1
0x14003ae8b  call    cs:__imp_RtlCompareMemory
0x14003ae92  nop     dword ptr [rax+rax+00h]
0x14003ae97  cmp     rax, rbx
0x14003ae9a  jnz     short loc_14003AEE7
0x14003ae9c  mov     rax, [rsi+58h]
0x14003aea0  test    dword ptr [rax+6Ch], 800h
0x14003aea7  jz      short loc_14003AEC8
0x14003aea9  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003aeb0  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14003aeb7  jz      loc_14003ABF0
0x14003aebd  mov     r9d, 0DFh
0x14003aec3  jmp     loc_14003ABD2
0x14003aec8  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003aecf  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14003aed6  jz      loc_14003AC6C
0x14003aedc  mov     r9d, 0E0h
0x14003aee2  jmp     loc_14003AC4E
0x14003aee7  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003aeee  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14003aef5  jz      short loc_14003AF23
0x14003aef7  mov     r9d, 0E1h
0x14003aefd  jmp     short loc_14003AF15
0x14003aeff  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003af06  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14003af0d  jz      short loc_14003AF23
0x14003af0f  mov     r9d, 0E2h
  ... truncated ...
```
