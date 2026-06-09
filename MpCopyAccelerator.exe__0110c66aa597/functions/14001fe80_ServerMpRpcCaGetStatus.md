# ServerMpRpcCaGetStatus

- ea: `0x14001fe80`
- end: `0x14001ffcf`
- name: `ServerMpRpcCaGetStatus`
- size: `335`
- prototype: `__int64 __fastcall(__int64, bool *, _DWORD *, _DWORD *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x14001da70`
- `0x14001efa4`
- `0x14001fe80`
- `0x1400203f0`
- `0x140020748`
- `0x140022a08`
- `0x140024148`

## import_xrefs

- `KERNEL32!AcquireSRWLockShared` at `0x14001ff60`
- `KERNEL32!AcquireSRWLockShared` at `0x14001ff60`
- `KERNEL32!ReleaseSRWLockShared` at `0x14001ff6d`
- `KERNEL32!ReleaseSRWLockShared` at `0x14001ff6d`
- `KERNEL32!WaitForSingleObject` at `0x14001ff2e`
- `KERNEL32!WaitForSingleObject` at `0x14001ff2e`

## string_xrefs

- `0x14001ff0e`: `Tampering attempt: MpCopyAccelerator GetStatus invoked by non-authorized application, access denied.`

## pseudocode

```c
__int64 __fastcall ServerMpRpcCaGetStatus(__int64 a1, bool *a2, _DWORD *a3, _DWORD *a4)
{
  bool v6; // zf
  int v7; // ebx
  HANDLE *Instance; // rax
  DWORD v10; // eax
  int v11; // edx
  bool v12; // bp
  RTL_SRWLOCK *v13; // rbx
  RTL_SRWLOCK *v14; // rdi
  PVOID Ptr; // rbx
  int v16; // [rsp+58h] [rbp+10h] BYREF

  *a4 = 0;
  if ( !a2 || !a3 )
    return 2147942487LL;
  v6 = dword_14003DB98 == 0;
  *a2 = 0;
  *a3 = 0;
  if ( v6 )
  {
    v16 = 0;
    v7 = CheckRpcClientIdentity(a1, &v16);
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          46,
          &WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids,
          (unsigned int)v7);
      return (unsigned int)v7;
    }
    if ( !v16 )
    {
      MpCmdLogPrintf(L"Tampering attempt: MpCopyAccelerator GetStatus invoked by non-authorized application, access denied.");
      return 2147942405LL;
    }
  }
  Instance = (HANDLE *)CCopyControl::GetInstance();
  v10 = WaitForSingleObject(*Instance, 0);
  if ( v10 )
    v11 = v10 != 258 ? 2 : 0;
  else
    v11 = 1;
  v12 = v11 == 0;
  v13 = (RTL_SRWLOCK *)CCopyControl::GetInstance();
  v14 = v13 + 3;
  AcquireSRWLockShared(v13 + 3);
  Ptr = v13[2].Ptr;
  ReleaseSRWLockShared(v14);
  *a2 = v12;
  *a3 = (_DWORD)Ptr;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      47,
      &WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids,
      v12,
      (_DWORD)Ptr);
  SendAggregatedCopyStatsTelemetry();
  return 0;
}

```

## disassembly

```asm
0x14001fe80  mov     rax, rsp
0x14001fe83  mov     [rax+8], rbx
0x14001fe87  mov     [rax+18h], rbp
0x14001fe8b  push    rsi
0x14001fe8c  push    rdi
0x14001fe8d  push    r14
0x14001fe8f  sub     rsp, 30h
0x14001fe93  xor     edi, edi
0x14001fe95  mov     rsi, r8
0x14001fe98  mov     [r9], edi
0x14001fe9b  mov     r14, rdx
0x14001fe9e  test    rdx, rdx
0x14001fea1  jz      loc_14001FFB7
0x14001fea7  test    r8, r8
0x14001feaa  jz      loc_14001FFB7
0x14001feb0  cmp     cs:dword_14003DB98, edi
0x14001feb6  mov     [rdx], dil
0x14001feb9  mov     [r8], edi
0x14001febc  jnz     short loc_14001FF24
0x14001febe  lea     rdx, [rax+10h]; int *
0x14001fec2  mov     [rax+10h], edi
0x14001fec5  call    ?CheckRpcClientIdentity@@YAJKPEAH@Z; CheckRpcClientIdentity(ulong,int *)
0x14001feca  mov     ebx, eax
0x14001fecc  test    eax, eax
0x14001fece  jns     short loc_14001FF08
0x14001fed0  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fed7  lea     rax, WPP_GLOBAL_Control
0x14001fede  cmp     rcx, rax
0x14001fee1  jz      short loc_14001FF01
0x14001fee3  lea     edx, [rdi+1]
0x14001fee6  test    [rcx+1Ch], dl
0x14001fee9  jz      short loc_14001FF01
0x14001feeb  mov     rcx, [rcx+10h]
0x14001feef  lea     edx, [rdi+2Eh]
0x14001fef2  mov     r9d, ebx
0x14001fef5  lea     r8, WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids
0x14001fefc  call    WPP_SF_d
0x14001ff01  mov     eax, ebx
0x14001ff03  jmp     loc_14001FFBC
0x14001ff08  cmp     [rsp+48h+arg_8], edi
0x14001ff0c  jnz     short loc_14001FF24
0x14001ff0e  lea     rcx, aTamperingAttem; "Tampering attempt: MpCopyAccelerator Ge"...
0x14001ff15  call    ?MpCmdLogPrintf@@YAXPEB_WZZ; MpCmdLogPrintf(wchar_t const *,...)
0x14001ff1a  mov     eax, 80070005h
0x14001ff1f  jmp     loc_14001FFBC
0x14001ff24  call    ?GetInstance@CCopyControl@@SAAEAV1@XZ; CCopyControl::GetInstance(void)
0x14001ff29  xor     edx, edx; dwMilliseconds
0x14001ff2b  mov     rcx, [rax]; hHandle
0x14001ff2e  call    cs:__imp_WaitForSingleObject
0x14001ff34  test    eax, eax
0x14001ff36  jz      short loc_14001FF46
0x14001ff38  sub     eax, 102h
0x14001ff3d  neg     eax
0x14001ff3f  sbb     edx, edx
0x14001ff41  and     edx, 2
0x14001ff44  jmp     short loc_14001FF4B
0x14001ff46  mov     edx, 1
0x14001ff4b  test    edx, edx
0x14001ff4d  setz    bpl
0x14001ff51  call    ?GetInstance@CCopyControl@@SAAEAV1@XZ; CCopyControl::GetInstance(void)
0x14001ff56  mov     rbx, rax
0x14001ff59  lea     rdi, [rax+18h]
0x14001ff5d  mov     rcx, rdi; SRWLock
0x14001ff60  call    cs:__imp_AcquireSRWLockShared
0x14001ff66  mov     rbx, [rbx+10h]
0x14001ff6a  mov     rcx, rdi; SRWLock
0x14001ff6d  call    cs:__imp_ReleaseSRWLockShared
0x14001ff73  mov     [r14], bpl
0x14001ff76  mov     [rsi], ebx
0x14001ff78  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ff7f  lea     rax, WPP_GLOBAL_Control
0x14001ff86  cmp     rcx, rax
0x14001ff89  jz      short loc_14001FFAE
0x14001ff8b  test    byte ptr [rcx+1Ch], 4
0x14001ff8f  jz      short loc_14001FFAE
0x14001ff91  mov     rcx, [rcx+10h]
0x14001ff95  lea     r8, WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids
0x14001ff9c  movzx   r9d, bpl
0x14001ffa0  mov     edx, 2Fh ; '/'
0x14001ffa5  mov     [rsp+48h+var_28], ebx
0x14001ffa9  call    WPP_SF_Dd
0x14001ffae  call    SendAggregatedCopyStatsTelemetry
0x14001ffb3  xor     eax, eax
0x14001ffb5  jmp     short loc_14001FFBC
0x14001ffb7  mov     eax, 80070057h
0x14001ffbc  mov     rbx, [rsp+48h+arg_0]
0x14001ffc1  mov     rbp, [rsp+48h+arg_10]
0x14001ffc6  add     rsp, 30h
0x14001ffca  pop     r14
0x14001ffcc  pop     rdi
0x14001ffcd  pop     rsi
0x14001ffce  retn
```
