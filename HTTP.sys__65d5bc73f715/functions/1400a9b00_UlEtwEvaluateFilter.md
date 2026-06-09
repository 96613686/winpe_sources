# UlEtwEvaluateFilter

- ea: `0x1400a9b00`
- end: `0x1400a9d1f`
- name: `UlEtwEvaluateFilter`
- size: `543`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD)`
- caller_count: `47`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140005d10`
- `0x1400068a8`
- `0x140009a90`
- `0x140032fb0`
- `0x14004d130`
- `0x14004e100`
- `0x14004edd0`
- `0x140057f40`
- `0x14005ce00`
- `0x14005d510`
- `0x14006460c`
- `0x1400647e0`
- `0x140065a10`
- `0x140068890`
- `0x1400703a0`
- `0x140079aa4`
- `0x14007a3a8`
- `0x14007f004`
- `0x140080160`
- `0x140080660`
- `0x14008d890`
- `0x140094520`
- `0x140097220`
- `0x1400b1acc`
- `0x1400b29d0`
- `0x1400b3e6c`
- `0x1400b94c8`
- `0x1400c2b60`
- `0x1400c3bd0`
- `0x1400c3ee0`
- `0x1400daf44`
- `0x1400dcf20`
- `0x1400e2a08`
- `0x1400e2aa0`
- `0x14010c7c0`
- `0x140110320`
- `0x140110510`
- `0x140110e20`
- `0x140111cb0`
- `0x140113f58`
- `0x140117830`
- `0x140131a94`
- `0x14013888c`
- `0x140139b20`
- `0x140139c30`
- `0x14013c708`
- `0x14013cda0`

## callees

- `0x14000a350`
- `0x140094f20`
- `0x1400a9b00`
- `0x1400e3190`
- `0x1400e31e0`
- `0x140132d2c`
- `0x1401c3008`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400a9cdb`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a9cdb`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400a9cb6`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400a9cb6`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400a9b86`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400a9b86`
- `NDIS!NdisReleaseRWLock` at `0x1400a9bfb`
- `NDIS!NdisReleaseRWLock` at `0x1400a9bfb`
- `NDIS!NdisAcquireRWLockRead` at `0x1400a9bac`
- `NDIS!NdisAcquireRWLockRead` at `0x1400a9bac`
- `NDIS!NdisGetJobObjectCompartmentId` at `0x1400a9c19`
- `NDIS!NdisGetJobObjectCompartmentId` at `0x1400a9c19`

## pseudocode

```c
char __fastcall UlEtwEvaluateFilter(
        __int64 a1,
        int a2,
        int a3,
        struct _KPROCESS *a4,
        __int64 a5,
        int a6,
        __int64 a7,
        unsigned int a8)
{
  int JobObjectCompartmentId; // esi
  ULONG_PTR *v13; // rdi
  struct _EX_RUNDOWN_REF *v14; // rbp
  ULONG_PTR v15; // rdi
  int v16; // eax
  __int64 v17; // rcx
  __int64 Buffer; // rbp
  int Length; // r14d
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-58h] BYREF
  _LOCK_STATE_EX LockState; // [rsp+A0h] [rbp+8h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  DestinationString = 0;
  JobObjectCompartmentId = 1;
  v13 = (ULONG_PTR *)(a1 + 1776);
  if ( (BYTE1(xmmword_1401A2CA0) & 0x10) != 0 )
    WPP_SF_qq(1036, 15, WPP_44c496324fa63838e09271a1387dbff3_Traceguids, a1, *v13);
  if ( !*(_BYTE *)(a1 + 4212) )
  {
    if ( *v13 )
    {
      v14 = (struct _EX_RUNDOWN_REF *)(a1 + 4216);
      if ( ExAcquireRundownProtection((PEX_RUNDOWN_REF)(a1 + 4216)) )
      {
        NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(a1 + 1768), &LockState, 0);
        v15 = *v13;
        if ( v15 )
        {
          v16 = _InterlockedIncrement((volatile signed __int32 *)v15);
          if ( UxDebugCheckRefcount )
          {
            if ( v16 <= -1 )
              UlBugCheckEx(3u, v15, 0x21u, v16);
          }
        }
        NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 1768), &LockState);
        if ( v15 )
        {
          v17 = *(_QWORD *)(a1 + 64);
          if ( v17 )
            JobObjectCompartmentId = NdisGetJobObjectCompartmentId(v17);
          Buffer = a5;
          if ( !a5 || (Length = a6) == 0 )
          {
            Buffer = 0;
            Length = 0;
            if ( a7 )
            {
              if ( a8 && (int)UxSslValidateSni(a1, a7, a8, &DestinationString) >= 0 )
              {
                Buffer = (__int64)DestinationString.Buffer;
                Length = DestinationString.Length;
              }
            }
          }
          LOBYTE(JobObjectCompartmentId) = UlpEtwEvaluateFilterInternal(
                                             *(_QWORD *)(v15 + 8),
                                             JobObjectCompartmentId,
                                             a2,
                                             a3,
                                             a4,
                                             Buffer,
                                             Length);
          UlpDereferenceEtwRules(v15, 0x21u);
          v14 = (struct _EX_RUNDOWN_REF *)(a1 + 4216);
        }
        ExReleaseRundownProtection(v14);
      }
    }
  }
  if ( DestinationString.Buffer )
  {
    UlFreeWideString(&DestinationString.Buffer);
    RtlInitUnicodeString(&DestinationString, 0);
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 0x10) != 0 )
    WPP_SF_d(1036, 16, WPP_44c496324fa63838e09271a1387dbff3_Traceguids, (unsigned __int8)JobObjectCompartmentId);
  return JobObjectCompartmentId;
}

```

## disassembly

```asm
0x1400a9b00  mov     r11, rsp
0x1400a9b03  push    rbx
0x1400a9b04  push    rbp
0x1400a9b05  push    rsi
0x1400a9b06  push    rdi
0x1400a9b07  push    r12
0x1400a9b09  push    r13
0x1400a9b0b  push    r14
0x1400a9b0d  push    r15
0x1400a9b0f  sub     rsp, 58h
0x1400a9b13  xor     eax, eax
0x1400a9b15  xorps   xmm0, xmm0
0x1400a9b18  mov     [r11+8], ax
0x1400a9b1d  mov     r15, r9
0x1400a9b20  mov     [r11+0Ah], al
0x1400a9b24  mov     r12, r8
0x1400a9b27  movups  xmmword ptr [rsp+98h+DestinationString.Length], xmm0
0x1400a9b2c  mov     r13, rdx
0x1400a9b2f  mov     rbx, rcx
0x1400a9b32  mov     esi, 1
0x1400a9b37  test    byte ptr cs:xmmword_1401A2CA0+1, 10h
0x1400a9b3e  lea     rdi, [rcx+6F0h]
0x1400a9b45  jz      short loc_1400A9B65
0x1400a9b47  mov     rax, [rdi]
0x1400a9b4a  lea     edx, [rsi+0Eh]
0x1400a9b4d  mov     ecx, 40Ch
0x1400a9b52  mov     [r11-78h], rax
0x1400a9b56  mov     r9, rbx
0x1400a9b59  lea     r8, WPP_44c496324fa63838e09271a1387dbff3_Traceguids
0x1400a9b60  call    WPP_SF_qq
0x1400a9b65  cmp     byte ptr [rbx+1074h], 0
0x1400a9b6c  jnz     loc_1400A9CC2
0x1400a9b72  cmp     qword ptr [rdi], 0
0x1400a9b76  jz      loc_1400A9CC2
0x1400a9b7c  lea     rbp, [rbx+1078h]
0x1400a9b83  mov     rcx, rbp; RunRef
0x1400a9b86  call    cs:__imp_ExAcquireRundownProtection
0x1400a9b8d  nop     dword ptr [rax+rax+00h]
0x1400a9b92  test    al, al
0x1400a9b94  jz      loc_1400A9CC2
0x1400a9b9a  mov     rcx, [rbx+6E8h]; Lock
0x1400a9ba1  lea     rdx, [rsp+98h+LockState]; LockState
0x1400a9ba9  xor     r8d, r8d; Flags
0x1400a9bac  call    cs:__imp_NdisAcquireRWLockRead
0x1400a9bb3  nop     dword ptr [rax+rax+00h]
0x1400a9bb8  mov     rdi, [rdi]
0x1400a9bbb  test    rdi, rdi
0x1400a9bbe  jz      short loc_1400A9BEC
0x1400a9bc0  mov     eax, esi
0x1400a9bc2  lock xadd [rdi], eax
0x1400a9bc6  add     eax, esi
0x1400a9bc8  cmp     cs:UxDebugCheckRefcount, 0
0x1400a9bcf  jz      short loc_1400A9BEC
0x1400a9bd1  cmp     eax, 0FFFFFFFFh
0x1400a9bd4  jg      short loc_1400A9BEC
0x1400a9bd6  mov     r8d, 21h ; '!'; BugCheckParameter3
0x1400a9bdc  movsxd  r9, eax; BugCheckParameter4
0x1400a9bdf  mov     rdx, rdi; BugCheckParameter2
0x1400a9be2  lea     ecx, [r8-1Eh]; BugCheckParameter1
0x1400a9be6  call    UlBugCheckEx
0x1400a9bec  mov     rcx, [rbx+6E8h]; Lock
0x1400a9bf3  lea     rdx, [rsp+98h+LockState]; LockState
0x1400a9bfb  call    cs:__imp_NdisReleaseRWLock
0x1400a9c02  nop     dword ptr [rax+rax+00h]
0x1400a9c07  test    rdi, rdi
0x1400a9c0a  jz      loc_1400A9CB3
0x1400a9c10  mov     rcx, [rbx+40h]
0x1400a9c14  test    rcx, rcx
0x1400a9c17  jz      short loc_1400A9C27
0x1400a9c19  call    cs:__imp_NdisGetJobObjectCompartmentId
0x1400a9c20  nop     dword ptr [rax+rax+00h]
0x1400a9c25  mov     esi, eax
0x1400a9c27  mov     rbp, [rsp+98h+arg_20]
0x1400a9c2f  test    rbp, rbp
0x1400a9c32  jz      short loc_1400A9C41
0x1400a9c34  mov     r14d, [rsp+98h+arg_28]
0x1400a9c3c  test    r14d, r14d
0x1400a9c3f  jnz     short loc_1400A9C7C
0x1400a9c41  mov     rdx, [rsp+98h+arg_30]
0x1400a9c49  xor     ebp, ebp
0x1400a9c4b  xor     r14d, r14d
0x1400a9c4e  test    rdx, rdx
0x1400a9c51  jz      short loc_1400A9C7C
0x1400a9c53  mov     r8d, [rsp+98h+arg_38]
0x1400a9c5b  test    r8d, r8d
0x1400a9c5e  jz      short loc_1400A9C7C
0x1400a9c60  lea     r9, [rsp+98h+DestinationString]
0x1400a9c65  mov     rcx, rbx
0x1400a9c68  call    UxSslValidateSni
0x1400a9c6d  test    eax, eax
0x1400a9c6f  js      short loc_1400A9C7C
0x1400a9c71  mov     rbp, [rsp+98h+DestinationString.Buffer]
0x1400a9c76  movzx   r14d, [rsp+98h+DestinationString.Length]
0x1400a9c7c  mov     rcx, [rdi+8]; int
0x1400a9c80  mov     r9, r12; int
0x1400a9c83  mov     [rsp+98h+var_68], r14d; int
0x1400a9c88  mov     r8, r13; int
0x1400a9c8b  mov     [rsp+98h+var_70], rbp; __int64
0x1400a9c90  mov     edx, esi; int
0x1400a9c92  mov     [rsp+98h+Process], r15; Process
0x1400a9c97  call    UlpEtwEvaluateFilterInternal
0x1400a9c9c  mov     sil, al
0x1400a9c9f  mov     edx, 21h ; '!'; BugCheckParameter3
0x1400a9ca4  mov     rcx, rdi; BugCheckParameter2
0x1400a9ca7  call    UlpDereferenceEtwRules
0x1400a9cac  lea     rbp, [rbx+1078h]
0x1400a9cb3  mov     rcx, rbp; RunRef
0x1400a9cb6  call    cs:__imp_ExReleaseRundownProtection
0x1400a9cbd  nop     dword ptr [rax+rax+00h]
0x1400a9cc2  cmp     [rsp+98h+DestinationString.Buffer], 0
0x1400a9cc8  jz      short loc_1400A9CE7
0x1400a9cca  lea     rcx, [rsp+98h+DestinationString.Buffer]
0x1400a9ccf  call    UlFreeWideString
0x1400a9cd4  xor     edx, edx; SourceString
0x1400a9cd6  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x1400a9cdb  call    cs:__imp_RtlInitUnicodeString
0x1400a9ce2  nop     dword ptr [rax+rax+00h]
0x1400a9ce7  test    byte ptr cs:xmmword_1401A2CA0+1, 10h
0x1400a9cee  jz      short loc_1400A9D0A
0x1400a9cf0  movzx   r9d, sil
0x1400a9cf4  lea     r8, WPP_44c496324fa63838e09271a1387dbff3_Traceguids
0x1400a9cfb  mov     edx, 10h
0x1400a9d00  mov     ecx, 40Ch
0x1400a9d05  call    WPP_SF_d
0x1400a9d0a  mov     al, sil
0x1400a9d0d  add     rsp, 58h
0x1400a9d11  pop     r15
0x1400a9d13  pop     r14
0x1400a9d15  pop     r13
0x1400a9d17  pop     r12
0x1400a9d19  pop     rdi
0x1400a9d1a  pop     rsi
0x1400a9d1b  pop     rbp
0x1400a9d1c  pop     rbx
0x1400a9d1d  retn
```
