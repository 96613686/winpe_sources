# WdfIoQueueFindAndCompleteIoctlRequest

- ea: `0x14000a914`
- end: `0x14000aab7`
- name: `WdfIoQueueFindAndCompleteIoctlRequest`
- size: `419`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140006e8c`
- `0x14000e510`
- `0x14000e87c`
- `0x14000ecc4`
- `0x14000f700`
- `0x140013148`
- `0x140013df8`

## callees

- `0x1400041d0`
- `0x140004810`
- `0x14000a748`
- `0x14000a914`
- `0x14000ae30`
- `0x14001ae00`

## pseudocode

```c
__int64 __fastcall WdfIoQueueFindAndCompleteIoctlRequest(__int64 a1, __int64 a2, unsigned int a3, unsigned int a4)
{
  unsigned int v5; // ebp
  char v7; // bl
  bool v8; // dl
  int v9; // edx
  int IoctlRequest; // edi
  int v11; // r8d
  int v13; // [rsp+20h] [rbp-78h]
  int v14; // [rsp+28h] [rbp-70h]
  int v15; // [rsp+30h] [rbp-68h]
  int v16; // [rsp+38h] [rbp-60h]
  __int64 v17; // [rsp+A8h] [rbp+10h] BYREF

  v17 = 0;
  v5 = a3;
  v7 = 1;
  v8 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v8,
      a3,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      4,
      15,
      (__int64)WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids);
  }
  IoctlRequest = WdfIoQueueFindIoctlRequest(a1, 0, v5, &v17);
  if ( IoctlRequest >= 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      v7 = 0;
    }
    if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = v7;
      LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qIOCTL_BTHHFPd(
        WPP_GLOBAL_Control->AttachedDevice,
        v9,
        v11,
        WPP_GLOBAL_Control->DeviceExtension,
        v13,
        v14,
        v15,
        v16,
        v17,
        v5,
        a4);
    }
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, _QWORD))(WdfFunctions_01015 + 2120))(
      WdfDriverGlobals,
      v17,
      a4,
      0);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
    {
      v7 = 0;
    }
    if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = v7;
      LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP(
        WPP_GLOBAL_Control->AttachedDevice,
        v9,
        v11,
        WPP_GLOBAL_Control->DeviceExtension,
        3,
        4,
        16,
        (__int64)WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids,
        v5);
    }
    return (unsigned int)IoctlRequest;
  }
}

```

## disassembly

```asm
0x14000a914  mov     rax, rsp
0x14000a917  mov     [rax+10h], rdx
0x14000a91b  push    rbx
0x14000a91c  push    rbp
0x14000a91d  push    rsi
0x14000a91e  push    rdi
0x14000a91f  push    r12
0x14000a921  push    r13
0x14000a923  sub     rsp, 68h
0x14000a927  mov     esi, r9d
0x14000a92a  mov     qword ptr [rax+10h], 0
0x14000a932  mov     ebp, r8d
0x14000a935  mov     rdi, rcx
0x14000a938  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a93f  lea     r12, WPP_GLOBAL_Control
0x14000a946  mov     bl, 1
0x14000a948  cmp     rcx, r12
0x14000a94b  jz      short loc_14000A95E
0x14000a94d  mov     eax, [rcx+2Ch]
0x14000a950  test    al, 8
0x14000a952  jz      short loc_14000A95E
0x14000a954  cmp     byte ptr [rcx+29h], 4
0x14000a958  jb      short loc_14000A95E
0x14000a95a  mov     dl, bl
0x14000a95c  jmp     short loc_14000A960
0x14000a95e  xor     dl, dl
0x14000a960  lea     r13, WPP_RECORDER_INITIALIZED
0x14000a967  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14000a96e  lea     r9, WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids
0x14000a975  setnz   r8b
0x14000a979  test    dl, dl
0x14000a97b  jnz     short loc_14000A982
0x14000a97d  test    r8b, r8b
0x14000a980  jz      short loc_14000A9A8
0x14000a982  mov     [rsp+98h+var_60], r9
0x14000a987  mov     r9, [rcx+40h]
0x14000a98b  mov     rcx, [rcx+18h]
0x14000a98f  mov     [rsp+98h+var_68], 0Fh
0x14000a996  mov     [rsp+98h+var_70], 4
0x14000a99e  mov     [rsp+98h+var_78], 4
0x14000a9a3  call    WPP_RECORDER_AND_TRACE_SF_
0x14000a9a8  lea     r9, [rsp+98h+arg_8]
0x14000a9b0  mov     r8d, ebp
0x14000a9b3  xor     edx, edx
0x14000a9b5  mov     rcx, rdi
0x14000a9b8  call    WdfIoQueueFindIoctlRequest
0x14000a9bd  mov     edi, eax
0x14000a9bf  test    eax, eax
0x14000a9c1  jns     short loc_14000AA2C
0x14000a9c3  mov     r10, cs:WPP_GLOBAL_Control
0x14000a9ca  cmp     r10, r12
0x14000a9cd  jz      short loc_14000A9DF
0x14000a9cf  mov     ecx, [r10+2Ch]
0x14000a9d3  test    cl, 8
0x14000a9d6  jz      short loc_14000A9DF
0x14000a9d8  cmp     byte ptr [r10+29h], 3
0x14000a9dd  jnb     short loc_14000A9E1
0x14000a9df  xor     bl, bl
0x14000a9e1  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14000a9e8  setnz   r8b
0x14000a9ec  test    bl, bl
0x14000a9ee  jnz     short loc_14000A9F5
0x14000a9f0  test    r8b, r8b
0x14000a9f3  jz      short loc_14000AA28
0x14000a9f5  mov     r9, [r10+40h]
0x14000a9f9  lea     rcx, WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids
0x14000aa00  mov     dword ptr [rsp+98h+var_58], ebp
0x14000aa04  mov     dl, bl
0x14000aa06  mov     [rsp+98h+var_60], rcx
0x14000aa0b  mov     rcx, [r10+18h]
0x14000aa0f  mov     [rsp+98h+var_68], 10h
0x14000aa16  mov     [rsp+98h+var_70], 4
0x14000aa1e  mov     [rsp+98h+var_78], 3
0x14000aa23  call    WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP
0x14000aa28  mov     eax, edi
0x14000aa2a  jmp     short loc_14000AAA9
0x14000aa2c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000aa33  cmp     rcx, r12
0x14000aa36  jz      short loc_14000AA45
0x14000aa38  mov     eax, [rcx+2Ch]
0x14000aa3b  test    al, 8
0x14000aa3d  jz      short loc_14000AA45
0x14000aa3f  cmp     byte ptr [rcx+29h], 4
0x14000aa43  jnb     short loc_14000AA47
0x14000aa45  xor     bl, bl
0x14000aa47  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14000aa4e  setnz   r8b
0x14000aa52  test    bl, bl
0x14000aa54  jnz     short loc_14000AA5B
0x14000aa56  test    r8b, r8b
0x14000aa59  jz      short loc_14000AA7F
0x14000aa5b  mov     rax, [rsp+98h+arg_8]
0x14000aa63  mov     dl, bl
0x14000aa65  mov     r9, [rcx+40h]
0x14000aa69  mov     rcx, [rcx+18h]
0x14000aa6d  mov     [rsp+98h+var_48], esi
0x14000aa71  mov     [rsp+98h+var_50], ebp
0x14000aa75  mov     [rsp+98h+var_58], rax
0x14000aa7a  call    WPP_RECORDER_AND_TRACE_SF_qIOCTL_BTHHFPd
0x14000aa7f  mov     rax, cs:WdfFunctions_01015
0x14000aa86  xor     r9d, r9d
0x14000aa89  mov     rdx, [rsp+98h+arg_8]
0x14000aa91  mov     r8d, esi
0x14000aa94  mov     rcx, cs:WdfDriverGlobals
0x14000aa9b  mov     rax, [rax+848h]
0x14000aaa2  call    _guard_dispatch_icall
0x14000aaa7  xor     eax, eax
0x14000aaa9  add     rsp, 68h
0x14000aaad  pop     r13
0x14000aaaf  pop     r12
0x14000aab1  pop     rdi
0x14000aab2  pop     rsi
0x14000aab3  pop     rbp
0x14000aab4  pop     rbx
0x14000aab5  retn
```
