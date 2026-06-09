# BthCompleteRequest(DEVICE_EXTENSION *,_IRP *,long)

- ea: `0x1400b9d78`
- end: `0x1400b9f4a`
- name: `?BthCompleteRequest@@YAXPEAUDEVICE_EXTENSION@@PEAU_IRP@@J@Z`
- size: `466`
- prototype: `void(struct DEVICE_EXTENSION *, struct _IRP *, int)`
- caller_count: `59`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001c780`
- `0x14001cce0`
- `0x14001df30`
- `0x14001df9c`
- `0x14001e010`
- `0x14001f284`
- `0x14001f6f0`
- `0x14002bb6c`
- `0x140049700`
- `0x14005d8b0`
- `0x14005e140`
- `0x14006fb30`
- `0x140077144`
- `0x140077ee0`
- `0x140078c00`
- `0x140094f0c`
- `0x140099254`
- `0x1400a9a50`
- `0x1400adf20`
- `0x1400afe50`
- `0x1400b3990`
- `0x1400b5a48`
- `0x1400b9f50`
- `0x1400b9f98`
- `0x1400b9fb4`
- `0x1400ba054`
- `0x1400babe0`
- `0x1400bb72c`
- `0x1400bbae0`
- `0x1400bea80`
- `0x1400beb30`
- `0x1400ca774`
- `0x1400cc2f0`
- `0x1400ccbc4`
- `0x1400d01a8`
- `0x1400d0ad0`
- `0x1400d9404`
- `0x1400da970`
- `0x1400dae40`
- `0x1400dbaec`
- `0x1400dcee8`
- `0x140134fe4`
- `0x140144b3c`
- `0x140146310`
- `0x140147864`
- `0x140147934`
- `0x140147fe0`
- `0x14014ada0`
- `0x140150b80`
- `0x1401518a0`

## callees

- `0x140005ce8`
- `0x14000812c`
- `0x1400b9d78`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400b9f2d`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400b9f2d`
- `ntoskrnl!IofCompleteRequest` at `0x1400b9f14`
- `ntoskrnl!IofCompleteRequest` at `0x1400b9f14`

## pseudocode

```c
void __fastcall BthCompleteRequest(struct DEVICE_EXTENSION *a1, struct _IRP *a2, int a3)
{
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  unsigned int LowPart; // edx
  struct _BRB *SecurityContext; // rsi
  char v8; // cl
  __int16 DeviceType; // ax
  char v10; // [rsp+50h] [rbp-18h]
  char v11; // [rsp+50h] [rbp-18h]
  char v12; // [rsp+50h] [rbp-18h]

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  a2->IoStatus.Status = a3;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  if ( CurrentStackLocation->MajorFunction == 15 && LowPart == 4259843 )
  {
    SecurityContext = (struct _BRB *)CurrentStackLocation->Parameters.Create.SecurityContext;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      LOBYTE(LowPart) = 1;
    else
      LowPart = 0;
    v10 = a3;
    LOBYTE(a3) = 1;
    WPP_RECORDER_AND_TRACE_SF_qiD(
      WPP_GLOBAL_Control->AttachedDevice,
      LowPart,
      a3,
      *(_QWORD *)a1[-2].DeviceExtensionSessionId.Data4,
      4,
      16,
      10,
      (__int64)WPP_ee857c6212043aa79332603f7640d18b_Traceguids,
      a1[-2].EtwLogger.m_lock.m_kSpinLock,
      (char)a2,
      v10);
    BthMarkBrbInUse(SecurityContext, 0);
  }
  else if ( LowPart == 4259840 )
  {
    BYTE1(LowPart) = 0;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) == 0 || (v8 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
      v8 = 0;
    DeviceType = WPP_GLOBAL_Control->DeviceType;
    if ( v8 || DeviceType )
    {
      LOBYTE(LowPart) = v8;
      v11 = a3;
      LOBYTE(a3) = DeviceType != 0;
      WPP_RECORDER_AND_TRACE_SF_qiD(
        WPP_GLOBAL_Control->AttachedDevice,
        LowPart,
        a3,
        *(_QWORD *)a1[-2].DeviceExtensionSessionId.Data4,
        5,
        16,
        11,
        (__int64)WPP_ee857c6212043aa79332603f7640d18b_Traceguids,
        a1[-2].EtwLogger.m_lock.m_kSpinLock,
        (char)a2,
        v11);
    }
  }
  else
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      LOBYTE(LowPart) = 1;
    else
      LOWORD(LowPart) = 0;
    v12 = a3;
    LOBYTE(a3) = 1;
    WPP_RECORDER_AND_TRACE_SF_qiD(
      WPP_GLOBAL_Control->AttachedDevice,
      LowPart,
      a3,
      *(_QWORD *)a1[-2].DeviceExtensionSessionId.Data4,
      4,
      16,
      12,
      (__int64)WPP_ee857c6212043aa79332603f7640d18b_Traceguids,
      a1[-2].EtwLogger.m_lock.m_kSpinLock,
      (char)a2,
      v12);
  }
  IofCompleteRequest(a2, 8);
  IoReleaseRemoveLockEx(&a1->RemoveLock, a2, 0x20u);
}

```

## disassembly

```asm
0x1400b9d78  mov     [rsp+arg_0], rbx
0x1400b9d7d  mov     [rsp+arg_8], rsi
0x1400b9d82  push    rdi
0x1400b9d83  sub     rsp, 60h
0x1400b9d87  mov     rax, [rdx+0B8h]
0x1400b9d8e  mov     rbx, rdx
0x1400b9d91  mov     [rdx+30h], r8d
0x1400b9d95  mov     rdi, rcx
0x1400b9d98  cmp     byte ptr [rax], 0Fh
0x1400b9d9b  mov     edx, [rax+18h]
0x1400b9d9e  jnz     loc_1400B9E28
0x1400b9da4  cmp     edx, 410003h
0x1400b9daa  jnz     short loc_1400B9E28
0x1400b9dac  mov     rsi, [rax+8]
0x1400b9db0  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400b9db7  mov     cl, 1
0x1400b9db9  test    dword ptr [r10+2Ch], 8000h
0x1400b9dc1  jz      short loc_1400B9DCE
0x1400b9dc3  cmp     byte ptr [r10+29h], 4
0x1400b9dc8  jb      short loc_1400B9DCE
0x1400b9dca  mov     dl, cl
0x1400b9dcc  jmp     short loc_1400B9DD0
0x1400b9dce  xor     edx, edx
0x1400b9dd0  mov     rax, [rdi-330h]
0x1400b9dd7  mov     r9, [rdi-308h]
0x1400b9dde  mov     dword ptr [rsp+68h+var_18], r8d
0x1400b9de3  mov     r8b, cl
0x1400b9de6  mov     rcx, [r10+18h]
0x1400b9dea  mov     [rsp+68h+var_20], rbx
0x1400b9def  mov     [rsp+68h+var_28], rax
0x1400b9df4  lea     rax, WPP_ee857c6212043aa79332603f7640d18b_Traceguids
0x1400b9dfb  mov     [rsp+68h+var_30], rax
0x1400b9e00  mov     [rsp+68h+var_38], 0Ah
0x1400b9e07  mov     [rsp+68h+var_40], 10h
0x1400b9e0f  mov     [rsp+68h+var_48], 4
0x1400b9e14  call    WPP_RECORDER_AND_TRACE_SF_qiD
0x1400b9e19  xor     edx, edx; unsigned __int8
0x1400b9e1b  mov     rcx, rsi; struct _BRB *
0x1400b9e1e  call    ?BthMarkBrbInUse@@YAXPEAU_BRB@@E@Z; BthMarkBrbInUse(_BRB *,uchar)
0x1400b9e23  jmp     loc_1400B9F0F
0x1400b9e28  cmp     edx, 410000h
0x1400b9e2e  jnz     short loc_1400B9EA5
0x1400b9e30  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400b9e37  xor     dx, dx
0x1400b9e3a  test    dword ptr [r10+2Ch], 8000h
0x1400b9e42  jz      short loc_1400B9E4D
0x1400b9e44  cmp     byte ptr [r10+29h], 5
0x1400b9e49  mov     cl, 1
0x1400b9e4b  jnb     short loc_1400B9E4F
0x1400b9e4d  mov     cl, dl
0x1400b9e4f  movzx   eax, word ptr [r10+48h]
0x1400b9e54  test    ax, ax
0x1400b9e57  setnz   r11b
0x1400b9e5b  test    cl, cl
0x1400b9e5d  jnz     short loc_1400B9E68
0x1400b9e5f  test    ax, ax
0x1400b9e62  jz      loc_1400B9F0F
0x1400b9e68  mov     rax, [rdi-330h]
0x1400b9e6f  mov     dl, cl
0x1400b9e71  mov     dword ptr [rsp+68h+var_18], r8d
0x1400b9e76  mov     r8b, r11b
0x1400b9e79  mov     [rsp+68h+var_20], rbx
0x1400b9e7e  mov     [rsp+68h+var_28], rax
0x1400b9e83  lea     rax, WPP_ee857c6212043aa79332603f7640d18b_Traceguids
0x1400b9e8a  mov     [rsp+68h+var_30], rax
0x1400b9e8f  mov     [rsp+68h+var_38], 0Bh
0x1400b9e96  mov     [rsp+68h+var_40], 10h
0x1400b9e9e  mov     [rsp+68h+var_48], 5
0x1400b9ea3  jmp     short loc_1400B9EFF
0x1400b9ea5  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400b9eac  mov     cl, 1
0x1400b9eae  test    dword ptr [r10+2Ch], 8000h
0x1400b9eb6  jz      short loc_1400B9EC3
0x1400b9eb8  cmp     byte ptr [r10+29h], 4
0x1400b9ebd  jb      short loc_1400B9EC3
0x1400b9ebf  mov     dl, cl
0x1400b9ec1  jmp     short loc_1400B9EC6
0x1400b9ec3  xor     dx, dx
0x1400b9ec6  mov     rax, [rdi-330h]
0x1400b9ecd  mov     dword ptr [rsp+68h+var_18], r8d
0x1400b9ed2  mov     r8b, cl
0x1400b9ed5  mov     [rsp+68h+var_20], rbx
0x1400b9eda  mov     [rsp+68h+var_28], rax
0x1400b9edf  lea     rax, WPP_ee857c6212043aa79332603f7640d18b_Traceguids
0x1400b9ee6  mov     [rsp+68h+var_30], rax
0x1400b9eeb  mov     [rsp+68h+var_38], 0Ch
0x1400b9ef2  mov     [rsp+68h+var_40], 10h
0x1400b9efa  mov     [rsp+68h+var_48], 4
0x1400b9eff  mov     r9, [rdi-308h]
0x1400b9f06  mov     rcx, [r10+18h]
0x1400b9f0a  call    WPP_RECORDER_AND_TRACE_SF_qiD
0x1400b9f0f  mov     dl, 8; PriorityBoost
0x1400b9f11  mov     rcx, rbx; Irp
0x1400b9f14  call    cs:__imp_IofCompleteRequest
0x1400b9f1b  nop     dword ptr [rax+rax+00h]
0x1400b9f20  lea     rcx, [rdi+38h]; RemoveLock
0x1400b9f24  mov     r8d, 20h ; ' '; RemlockSize
0x1400b9f2a  mov     rdx, rbx; Tag
0x1400b9f2d  call    cs:__imp_IoReleaseRemoveLockEx
0x1400b9f34  nop     dword ptr [rax+rax+00h]
0x1400b9f39  mov     rbx, [rsp+68h+arg_0]
0x1400b9f3e  mov     rsi, [rsp+68h+arg_8]
0x1400b9f43  add     rsp, 60h
0x1400b9f47  pop     rdi
0x1400b9f48  retn
```
