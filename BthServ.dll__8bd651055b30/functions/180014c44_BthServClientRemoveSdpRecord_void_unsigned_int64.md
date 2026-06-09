# BthServClientRemoveSdpRecord(void *,unsigned __int64)

- ea: `0x180014c44`
- end: `0x180014efe`
- name: `?BthServClientRemoveSdpRecord@@YAKPEAX_K@Z`
- size: `698`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180012a70`

## callees

- `0x18000d404`
- `0x18000f2e8`
- `0x1800110d0`
- `0x180011194`
- `0x18001140c`
- `0x180012e00`
- `0x180014c44`
- `0x180015db4`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014d53`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014d9c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014d53`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014d9c`

## pseudocode

```c
__int64 __fastcall BthServClientRemoveSdpRecord(_QWORD *a1, __int64 a2)
{
  __int64 v2; // rsi
  char v4; // di
  _QWORD *v6; // rax
  _QWORD *v7; // rcx
  _QWORD *v8; // rbp
  _QWORD *v9; // rdx
  int v10; // edx
  int v11; // r8d
  DWORD v12; // esi
  volatile signed __int32 *v13; // rbx
  int v14; // edx
  int v15; // r8d
  int v16; // [rsp+20h] [rbp-78h]
  DWORD v17; // [rsp+28h] [rbp-70h]
  HANDLE *v18; // [rsp+60h] [rbp-38h] BYREF
  volatile signed __int32 *v19; // [rsp+68h] [rbp-30h]
  DWORD NumberOfBytesTransferred; // [rsp+A0h] [rbp+8h] BYREF

  v2 = a2;
  NumberOfBytesTransferred = 0;
  v4 = 1;
  LOBYTE(a2) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_sqi(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v16,
      v17,
      23,
      (__int64)WPP_db4ee0e4eaba3bdc4454fe810b066fe8_Traceguids);
  if ( !(unsigned int)BthServLockDbClients() )
    return 167;
  v6 = (_QWORD *)a1[7];
  if ( v6 == a1 + 7 )
  {
LABEL_13:
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      v4 = 0;
    if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_si(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v4,
        WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
        *((_QWORD *)WPP_GLOBAL_Control + 5));
    ReleaseMutex(qword_180044B50);
    return 160;
  }
  else
  {
    while ( 1 )
    {
      v7 = (_QWORD *)*v6;
      v8 = v6 - 1;
      if ( v6[2] == v2 )
        break;
      v6 = (_QWORD *)*v6;
      if ( v7 == a1 + 7 )
        goto LABEL_13;
    }
    if ( (_QWORD *)v7[1] != v6 || (v9 = (_QWORD *)v6[1], (_QWORD *)*v9 != v6) )
      __fastfail(3u);
    *v9 = v7;
    v7[1] = v9;
    ReleaseMutex(qword_180044B50);
    BthServGlobals::GetSafeRadioHandle(&Globals, &v18);
    if ( v18 && (char *)*v18 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v12 = BthServOverlappedIoctl(*v18, 0x410218u, v8, 8u, 0, 0, &NumberOfBytesTransferred);
    else
      v12 = 6;
    v13 = v19;
    if ( v19 )
    {
      if ( _InterlockedExchangeAdd(v19 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
        if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
      }
    }
    if ( v12 )
    {
      LOBYTE(v10) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
      if ( (_BYTE)v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v10,
          v11,
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v16,
          v17,
          25,
          (__int64)WPP_db4ee0e4eaba3bdc4454fe810b066fe8_Traceguids);
      }
    }
    SdpFreePool(v8);
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      v4 = 0;
    if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v14) = v4;
      LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v14,
        v15,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v16,
        v17,
        26,
        (__int64)WPP_db4ee0e4eaba3bdc4454fe810b066fe8_Traceguids);
    }
    return v12;
  }
}

```

## disassembly

```asm
0x180014c44  mov     rax, rsp
0x180014c47  mov     [rax+10h], rbx
0x180014c4b  mov     [rax+18h], rbp
0x180014c4f  push    rsi
0x180014c50  push    rdi
0x180014c51  push    r12
0x180014c53  push    r13
0x180014c55  push    r15
0x180014c57  sub     rsp, 70h
0x180014c5b  mov     rsi, rdx
0x180014c5e  mov     dword ptr [rax+8], 0
0x180014c65  mov     rbx, rcx
0x180014c68  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c6f  lea     r12, WPP_GLOBAL_Control
0x180014c76  mov     dil, 1
0x180014c79  cmp     rcx, r12
0x180014c7c  jz      short loc_180014C89
0x180014c7e  cmp     byte ptr [rcx+19h], 4
0x180014c82  jb      short loc_180014C89
0x180014c84  mov     dl, dil
0x180014c87  jmp     short loc_180014C8B
0x180014c89  xor     dl, dl
0x180014c8b  lea     r13, WPP_RECORDER_INITIALIZED
0x180014c92  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180014c99  lea     r15, WPP_db4ee0e4eaba3bdc4454fe810b066fe8_Traceguids
0x180014ca0  setnz   r8b
0x180014ca4  test    dl, dl
0x180014ca6  jnz     short loc_180014CAD
0x180014ca8  test    r8b, r8b
0x180014cab  jz      short loc_180014CD0
0x180014cad  mov     r9, [rcx+28h]
0x180014cb1  mov     rcx, [rcx+10h]
0x180014cb5  mov     [rsp+98h+var_48], rsi
0x180014cba  mov     [rsp+98h+var_50], rbx
0x180014cbf  mov     [rsp+98h+var_60], r15
0x180014cc4  mov     word ptr [rsp+98h+lpNumberOfBytesTransferred], 17h
0x180014ccb  call    WPP_RECORDER_AND_TRACE_SF_sqi
0x180014cd0  call    ?BthServLockDbClients@@YAHXZ; BthServLockDbClients(void)
0x180014cd5  test    eax, eax
0x180014cd7  jnz     short loc_180014CE0
0x180014cd9  mov     eax, 0A7h
0x180014cde  jmp     short loc_180014D5E
0x180014ce0  lea     rdx, [rbx+38h]
0x180014ce4  mov     rax, [rdx]
0x180014ce7  cmp     rax, rdx
0x180014cea  jz      short loc_180014D01
0x180014cec  mov     rcx, [rax]
0x180014cef  lea     rbp, [rax-8]
0x180014cf3  cmp     [rbp+18h], rsi
0x180014cf7  jz      short loc_180014D77
0x180014cf9  mov     rax, rcx
0x180014cfc  cmp     rcx, rdx
0x180014cff  jnz     short loc_180014CEC
0x180014d01  mov     rcx, cs:WPP_GLOBAL_Control
0x180014d08  cmp     rcx, r12
0x180014d0b  jz      short loc_180014D13
0x180014d0d  cmp     byte ptr [rcx+19h], 3
0x180014d11  jnb     short loc_180014D16
0x180014d13  xor     dil, dil
0x180014d16  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180014d1d  setnz   r8b
0x180014d21  test    dil, dil
0x180014d24  jnz     short loc_180014D2B
0x180014d26  test    r8b, r8b
0x180014d29  jz      short loc_180014D4C
0x180014d2b  mov     r9, [rcx+28h]
0x180014d2f  mov     dl, dil
0x180014d32  mov     rcx, [rcx+10h]
0x180014d36  mov     [rsp+98h+var_50], rsi
0x180014d3b  mov     [rsp+98h+var_60], r15
0x180014d40  mov     word ptr [rsp+98h+lpNumberOfBytesTransferred], 18h
0x180014d47  call    WPP_RECORDER_AND_TRACE_SF_si
0x180014d4c  mov     rcx, cs:qword_180044B50; hMutex
0x180014d53  call    cs:__imp_ReleaseMutex
0x180014d59  mov     eax, 0A0h
0x180014d5e  lea     r11, [rsp+98h+var_28]
0x180014d63  mov     rbx, [r11+38h]
0x180014d67  mov     rbp, [r11+40h]
0x180014d6b  mov     rsp, r11
0x180014d6e  pop     r15
0x180014d70  pop     r13
0x180014d72  pop     r12
0x180014d74  pop     rdi
0x180014d75  pop     rsi
0x180014d76  retn
0x180014d77  cmp     [rcx+8], rax
0x180014d7b  jnz     loc_180014EF7
0x180014d81  mov     rdx, [rax+8]
0x180014d85  cmp     [rdx], rax
0x180014d88  jnz     loc_180014EF7
0x180014d8e  mov     [rdx], rcx
0x180014d91  mov     [rcx+8], rdx
0x180014d95  mov     rcx, cs:qword_180044B50; hMutex
0x180014d9c  call    cs:__imp_ReleaseMutex
0x180014da2  lea     rdx, [rsp+98h+var_38]
0x180014da7  lea     rcx, ?Globals@@3VBthServGlobals@@A; BthServGlobals Globals
0x180014dae  call    ?GetSafeRadioHandle@BthServGlobals@@QEAA?AV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@XZ; BthServGlobals::GetSafeRadioHandle(void)
0x180014db3  mov     rcx, [rsp+98h+var_38]
0x180014db8  test    rcx, rcx
0x180014dbb  jz      short loc_180014DFF
0x180014dbd  mov     rcx, [rcx]; hFile
0x180014dc0  lea     rax, [rcx-1]
0x180014dc4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180014dc8  ja      short loc_180014DFF
0x180014dca  lea     rax, [rsp+98h+NumberOfBytesTransferred]
0x180014dd2  mov     r9d, 8; nInBufferSize
0x180014dd8  mov     [rsp+98h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x180014ddd  mov     r8, rbp; lpInBuffer
0x180014de0  mov     [rsp+98h+var_70], 0; DWORD
0x180014de8  mov     edx, 410218h; dwIoControlCode
0x180014ded  mov     [rsp+98h+var_78], 0; void *
0x180014df6  call    ?BthServOverlappedIoctl@@YAKPEAXK0K0KPEAK@Z; BthServOverlappedIoctl(void *,ulong,void *,ulong,void *,ulong,ulong *)
0x180014dfb  mov     esi, eax
0x180014dfd  jmp     short loc_180014E04
0x180014dff  mov     esi, 6
0x180014e04  mov     rbx, [rsp+98h+var_30]
0x180014e09  test    rbx, rbx
0x180014e0c  jz      short loc_180014E50
0x180014e0e  or      r15d, 0FFFFFFFFh
0x180014e12  mov     eax, r15d
0x180014e15  lock xadd [rbx+8], eax
0x180014e1a  add     eax, r15d
0x180014e1d  jnz     short loc_180014E49
0x180014e1f  mov     rax, [rbx]
0x180014e22  mov     rcx, rbx
0x180014e25  mov     rax, [rax]
0x180014e28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e2d  mov     eax, r15d
0x180014e30  lock xadd [rbx+0Ch], eax
0x180014e35  add     eax, r15d
0x180014e38  jnz     short loc_180014E49
0x180014e3a  mov     rax, [rbx]
0x180014e3d  mov     rcx, rbx
0x180014e40  mov     rax, [rax+8]
0x180014e44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e49  lea     r15, WPP_db4ee0e4eaba3bdc4454fe810b066fe8_Traceguids
0x180014e50  test    esi, esi
0x180014e52  jz      short loc_180014E9E
0x180014e54  mov     rcx, cs:WPP_GLOBAL_Control
0x180014e5b  cmp     rcx, r12
0x180014e5e  jz      short loc_180014E6B
0x180014e60  cmp     byte ptr [rcx+19h], 3
0x180014e64  jb      short loc_180014E6B
0x180014e66  mov     dl, dil
0x180014e69  jmp     short loc_180014E6D
0x180014e6b  xor     dl, dl
0x180014e6d  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180014e74  setnz   r8b
0x180014e78  test    dl, dl
0x180014e7a  jnz     short loc_180014E81
0x180014e7c  test    r8b, r8b
0x180014e7f  jz      short loc_180014E9E
0x180014e81  mov     r9, [rcx+28h]
0x180014e85  mov     rcx, [rcx+10h]
0x180014e89  mov     dword ptr [rsp+98h+var_50], esi
0x180014e8d  mov     [rsp+98h+var_60], r15
0x180014e92  mov     word ptr [rsp+98h+lpNumberOfBytesTransferred], 19h
0x180014e99  call    WPP_RECORDER_AND_TRACE_SF_sd
0x180014e9e  mov     rcx, rbp
0x180014ea1  call    SdpFreePool
0x180014ea6  mov     rcx, cs:WPP_GLOBAL_Control
0x180014ead  cmp     rcx, r12
0x180014eb0  jz      short loc_180014EB8
0x180014eb2  cmp     byte ptr [rcx+19h], 4
0x180014eb6  jnb     short loc_180014EBB
0x180014eb8  xor     dil, dil
0x180014ebb  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180014ec2  setnz   r8b
0x180014ec6  test    dil, dil
0x180014ec9  jnz     short loc_180014ED0
0x180014ecb  test    r8b, r8b
0x180014ece  jz      short loc_180014EF0
0x180014ed0  mov     r9, [rcx+28h]
0x180014ed4  mov     dl, dil
0x180014ed7  mov     rcx, [rcx+10h]
0x180014edb  mov     dword ptr [rsp+98h+var_50], esi
0x180014edf  mov     [rsp+98h+var_60], r15
0x180014ee4  mov     word ptr [rsp+98h+lpNumberOfBytesTransferred], 1Ah
0x180014eeb  call    WPP_RECORDER_AND_TRACE_SF_sd
0x180014ef0  mov     eax, esi
0x180014ef2  jmp     loc_180014D5E
0x180014ef7  mov     ecx, 3
0x180014efc  int     29h; Win8: RtlFailFast(ecx)
```
