# FwpsInjectionHandleCreate0

- ea: `0x18000baa0`
- end: `0x18000bcdf`
- name: `FwpsInjectionHandleCreate0`
- size: `575`
- prototype: `NTSTATUS __stdcall(ADDRESS_FAMILY addressFamily, UINT32 flags, HANDLE *injectionHandle)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180004904`
- `0x180006ce0`
- `0x180006f00`
- `0x180007a1c`
- `0x180008480`
- `0x18000891c`
- `0x18000baa0`
- `0x18000c3a0`
- `0x18000ca00`

## string_xrefs

- `0x18000bae9`: `FwpsInjectionHandleCreate0`
- `0x18000bb09`: `FwpsInjectionHandleCreate0`
- `0x18000bb2d`: `FwpsInjectionHandleCreate0`
- `0x18000bb5c`: `FwpsInjectionHandleCreate0`
- `0x18000bcbd`: `FwpsInjectionHandleCreate0`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
NTSTATUS __stdcall FwpsInjectionHandleCreate0(ADDRESS_FAMILY addressFamily, UINT32 flags, HANDLE *injectionHandle)
{
  _QWORD *v3; // rdi
  UINT32 v7; // r12d
  __int64 inited; // rbx
  int v9; // r8d
  __int64 v10; // rax
  _QWORD *v11; // rsi
  int v12; // eax
  _QWORD *v13; // rax
  __int64 *v14; // rcx
  _QWORD *v15; // rax
  __int64 v16; // rcx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-68h] BYREF
  _QWORD *v19; // [rsp+A8h] [rbp+20h] BYREF

  v3 = 0;
  v19 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v7 = flags & 0x10;
  if ( (flags & 0x10) == 0 )
  {
    if ( _InterlockedAdd(&gFwpTcpIp, 1u) < 0 )
    {
      inited = WfpReportSysErrorAsNtStatus(addressFamily, (int)"FwpsInjectionHandleCreate0", -1071513344);
LABEL_31:
      _InterlockedDecrement(&gFwpTcpIp);
      goto LABEL_34;
    }
    goto LABEL_8;
  }
  if ( flags == 16 )
  {
    if ( _InterlockedAdd(&gFwpL2, 1u) < 0 )
    {
      inited = WfpReportSysErrorAsNtStatus(addressFamily, (int)"FwpsInjectionHandleCreate0", -1071513538);
      goto LABEL_33;
    }
LABEL_8:
    if ( (flags & 4) != 0 && addressFamily != 2 && addressFamily != 23 )
    {
      v9 = -1071513547;
LABEL_12:
      inited = WfpReportSysErrorAsNtStatus(addressFamily, (int)"FwpsInjectionHandleCreate0", v9);
LABEL_30:
      if ( !v7 )
        goto LABEL_31;
      if ( flags != 16 )
        goto LABEL_34;
LABEL_33:
      _InterlockedDecrement(&gFwpL2);
      goto LABEL_34;
    }
    if ( !injectionHandle )
    {
      v9 = -1071513572;
      goto LABEL_12;
    }
    v10 = WfpPoolAllocNonPaged(96, 1886418758, &v19);
    v3 = v19;
    inited = v10;
    if ( v10 )
      goto LABEL_30;
    v11 = v19 + 1;
    v19[2] = v19 + 1;
    v3[1] = v3 + 1;
    *(_DWORD *)v3 = flags;
    v3[4] = 0;
    *((_DWORD *)v3 + 10) = 0;
    if ( addressFamily == 2 )
    {
      *((_DWORD *)v3 + 6) = 0;
    }
    else
    {
      v12 = 41;
      if ( addressFamily != 23 )
        v12 = 59;
      *((_DWORD *)v3 + 6) = v12;
    }
    if ( (flags & 4) != 0 )
    {
      inited = FwppInitInjectionHandleForInjectRawSend(addressFamily, v3);
      if ( inited )
        goto LABEL_30;
    }
    if ( v7 )
    {
      WfpAcquireSpinLock(&qword_1800481C0, &LockHandle);
      v15 = (_QWORD *)qword_1800481D0;
      v14 = &qword_1800481C8;
      if ( *(__int64 **)qword_1800481D0 == &qword_1800481C8 )
      {
        *v11 = &qword_1800481C8;
        v3[2] = v15;
        *v15 = v11;
        qword_1800481D0 = (__int64)(v3 + 1);
        goto LABEL_29;
      }
    }
    else
    {
      WfpAcquireSpinLock(&qword_1800482C0, &LockHandle);
      v13 = (_QWORD *)qword_1800482D0;
      v14 = &qword_1800482C8;
      if ( *(__int64 **)qword_1800482D0 == &qword_1800482C8 )
      {
        *v11 = &qword_1800482C8;
        v3[2] = v13;
        *v13 = v11;
        qword_1800482D0 = (__int64)(v3 + 1);
LABEL_29:
        WfpReleaseSpinLock(v14, &LockHandle);
        *injectionHandle = v3;
        goto LABEL_30;
      }
    }
    __fastfail(3u);
  }
  inited = WfpReportSysErrorAsNtStatus(addressFamily, (int)"FwpsInjectionHandleCreate0", -1071513547);
LABEL_34:
  if ( inited && v3 )
  {
    FwppInjectSessionAbort(v3);
    WfpNamedPoolFree(v16, (PVOID *)&v19);
  }
  if ( (int)inited < 0 )
    WfpReportStatus((unsigned int)inited, "FwpsInjectionHandleCreate0", 281);
  return inited;
}

```

## disassembly

```asm
0x18000baa0  mov     r11, rsp
0x18000baa3  push    rbx
0x18000baa4  push    rbp
0x18000baa5  push    rsi
0x18000baa6  push    rdi
0x18000baa7  push    r12
0x18000baa9  push    r13
0x18000baab  push    r14
0x18000baad  push    r15
0x18000baaf  sub     rsp, 48h
0x18000bab3  xor     edi, edi
0x18000bab5  xor     eax, eax
0x18000bab7  xorps   xmm0, xmm0
0x18000baba  mov     [r11+20h], rdi
0x18000babe  mov     r12d, edx
0x18000bac1  mov     r13, r8
0x18000bac4  mov     r14d, edx
0x18000bac7  movzx   ebp, cx
0x18000baca  movups  xmmword ptr [rsp+88h+LockHandle.LockQueue.Next], xmm0
0x18000bacf  mov     [r11-58h], rax
0x18000bad3  and     r12d, 10h
0x18000bad7  jnz     short loc_18000BAFD
0x18000bad9  lock add cs:gFwpTcpIp, 1
0x18000bae1  jns     short loc_18000BB41
0x18000bae3  mov     r8d, 0C0220100h
0x18000bae9  lea     rdx, aFwpsinjectionh; "FwpsInjectionHandleCreate0"
0x18000baf0  call    WfpReportSysErrorAsNtStatus
0x18000baf5  mov     rbx, rax
0x18000baf8  jmp     loc_18000BC7E
0x18000bafd  cmp     r14d, 10h
0x18000bb01  jz      short loc_18000BB1D
0x18000bb03  mov     r8d, 0C0220035h
0x18000bb09  lea     rdx, aFwpsinjectionh; "FwpsInjectionHandleCreate0"
0x18000bb10  call    WfpReportSysErrorAsNtStatus
0x18000bb15  mov     rbx, rax
0x18000bb18  jmp     loc_18000BC94
0x18000bb1d  lock add cs:gFwpL2, 1
0x18000bb25  jns     short loc_18000BB41
0x18000bb27  mov     r8d, 0C022003Eh
0x18000bb2d  lea     rdx, aFwpsinjectionh; "FwpsInjectionHandleCreate0"
0x18000bb34  call    WfpReportSysErrorAsNtStatus
0x18000bb39  mov     rbx, rax
0x18000bb3c  jmp     loc_18000BC8D
0x18000bb41  mov     r15d, r14d
0x18000bb44  and     r15d, 4
0x18000bb48  jz      short loc_18000BB70
0x18000bb4a  cmp     bp, 2
0x18000bb4e  jz      short loc_18000BB70
0x18000bb50  cmp     bp, 17h
0x18000bb54  jz      short loc_18000BB70
0x18000bb56  mov     r8d, 0C0220035h
0x18000bb5c  lea     rdx, aFwpsinjectionh; "FwpsInjectionHandleCreate0"
0x18000bb63  call    WfpReportSysErrorAsNtStatus
0x18000bb68  mov     rbx, rax
0x18000bb6b  jmp     loc_18000BC79
0x18000bb70  test    r13, r13
0x18000bb73  jnz     short loc_18000BB7D
0x18000bb75  mov     r8d, 0C022001Ch
0x18000bb7b  jmp     short loc_18000BB5C
0x18000bb7d  lea     r8, [rsp+88h+arg_18]
0x18000bb85  mov     edx, 70707746h
0x18000bb8a  mov     ecx, 60h ; '`'
0x18000bb8f  call    WfpPoolAllocNonPaged
0x18000bb94  mov     rdi, [rsp+88h+arg_18]
0x18000bb9c  mov     rbx, rax
0x18000bb9f  test    rax, rax
0x18000bba2  jnz     loc_18000BC79
0x18000bba8  lea     rsi, [rdi+8]
0x18000bbac  mov     [rsi+8], rsi
0x18000bbb0  mov     [rsi], rsi
0x18000bbb3  mov     [rdi], r14d
0x18000bbb6  mov     [rdi+20h], rax
0x18000bbba  mov     [rdi+28h], eax
0x18000bbbd  cmp     bp, 2
0x18000bbc1  jz      short loc_18000BBD5
0x18000bbc3  cmp     bp, 17h
0x18000bbc7  lea     eax, [rbx+29h]
0x18000bbca  lea     ecx, [rbx+3Bh]
0x18000bbcd  cmovnz  eax, ecx
0x18000bbd0  mov     [rdi+18h], eax
0x18000bbd3  jmp     short loc_18000BBDC
0x18000bbd5  mov     dword ptr [rdi+18h], 0
0x18000bbdc  test    r15d, r15d
0x18000bbdf  jz      short loc_18000BBF8
0x18000bbe1  mov     rdx, rdi
0x18000bbe4  movzx   ecx, bp
0x18000bbe7  call    FwppInitInjectionHandleForInjectRawSend
0x18000bbec  mov     rbx, rax
0x18000bbef  test    rax, rax
0x18000bbf2  jnz     loc_18000BC79
0x18000bbf8  lea     rdx, [rsp+88h+LockHandle]; LockHandle
0x18000bbfd  test    r12d, r12d
0x18000bc00  jnz     short loc_18000BC34
0x18000bc02  lea     rcx, qword_1800482C0; SpinLock
0x18000bc09  call    WfpAcquireSpinLock
0x18000bc0e  mov     rax, cs:qword_1800482D0
0x18000bc15  lea     rcx, qword_1800482C8
0x18000bc1c  cmp     [rax], rcx
0x18000bc1f  jnz     short loc_18000BC53
0x18000bc21  mov     [rsi], rcx
0x18000bc24  mov     [rsi+8], rax
0x18000bc28  mov     [rax], rsi
0x18000bc2b  mov     cs:qword_1800482D0, rsi
0x18000bc32  jmp     short loc_18000BC6B
0x18000bc34  lea     rcx, qword_1800481C0; SpinLock
0x18000bc3b  call    WfpAcquireSpinLock
0x18000bc40  mov     rax, cs:qword_1800481D0
0x18000bc47  lea     rcx, qword_1800481C8
0x18000bc4e  cmp     [rax], rcx
0x18000bc51  jz      short loc_18000BC5A
0x18000bc53  mov     ecx, 3
0x18000bc58  int     29h; Win8: RtlFailFast(ecx)
0x18000bc5a  mov     [rsi], rcx
0x18000bc5d  mov     [rsi+8], rax
0x18000bc61  mov     [rax], rsi
0x18000bc64  mov     cs:qword_1800481D0, rsi
0x18000bc6b  lea     rdx, [rsp+88h+LockHandle]
0x18000bc70  call    WfpReleaseSpinLock
0x18000bc75  mov     [r13+0], rdi
0x18000bc79  test    r12d, r12d
0x18000bc7c  jnz     short loc_18000BC87
0x18000bc7e  lock dec cs:gFwpTcpIp
0x18000bc85  jmp     short loc_18000BC94
0x18000bc87  cmp     r14d, 10h
0x18000bc8b  jnz     short loc_18000BC94
0x18000bc8d  lock dec cs:gFwpL2
0x18000bc94  test    rbx, rbx
0x18000bc97  jz      short loc_18000BCB3
0x18000bc99  test    rdi, rdi
0x18000bc9c  jz      short loc_18000BCB3
0x18000bc9e  mov     rcx, rdi
0x18000bca1  call    FwppInjectSessionAbort
0x18000bca6  lea     rdx, [rsp+88h+arg_18]
0x18000bcae  call    WfpNamedPoolFree
0x18000bcb3  test    ebx, ebx
0x18000bcb5  jns     short loc_18000BCCB
0x18000bcb7  mov     r8d, 119h
0x18000bcbd  lea     rdx, aFwpsinjectionh; "FwpsInjectionHandleCreate0"
0x18000bcc4  mov     ecx, ebx
0x18000bcc6  call    WfpReportStatus
0x18000bccb  mov     eax, ebx
0x18000bccd  add     rsp, 48h
0x18000bcd1  pop     r15
0x18000bcd3  pop     r14
0x18000bcd5  pop     r13
0x18000bcd7  pop     r12
0x18000bcd9  pop     rdi
0x18000bcda  pop     rsi
0x18000bcdb  pop     rbp
0x18000bcdc  pop     rbx
0x18000bcdd  retn
```
