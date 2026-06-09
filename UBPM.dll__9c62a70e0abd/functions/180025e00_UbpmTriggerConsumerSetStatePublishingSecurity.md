# UbpmTriggerConsumerSetStatePublishingSecurity

- ea: `0x180025e00`
- end: `0x180026227`
- name: `UbpmTriggerConsumerSetStatePublishingSecurity`
- size: `1063`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000fbf0`
- `0x1800150c0`
- `0x18001af64`
- `0x180025e00`
- `0x180026230`
- `0x180035184`
- `0x180040222`
- `0x18004022e`
- `0x180040260`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18002607d`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18002607d`
- `ntdll!RtlFreeHeap` at `0x18002619b`
- `ntdll!RtlFreeHeap` at `0x18002619b`
- `ntdll!RtlNtStatusToDosError` at `0x1800261d7`
- `ntdll!RtlNtStatusToDosError` at `0x1800261d7`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180025ebf`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180025ebf`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180025f2c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800260c6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002617d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180025f2c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800260c6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002617d`
- `ntdll!NtDeleteWnfStateName` at `0x1800261b3`
- `ntdll!NtDeleteWnfStateName` at `0x1800261b3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180025e4a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180025f6d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180025e4a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180025f6d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025ecb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025ecb`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180025e66`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180025f87`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180025e66`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180025f87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025fca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025fca`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180025ef3`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180025ef3`

## pseudocode

```c
__int64 __fastcall UbpmTriggerConsumerSetStatePublishingSecurity(struct _WNF_STATE_NAME *a1, const void **a2)
{
  DWORD v4; // ebx
  unsigned int v5; // ebp
  const void *v6; // rcx
  SIZE_T v7; // rbx
  DWORD v8; // ebx
  void *v10; // rax
  void *v11; // r15
  DWORD LastError; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  NTSTATUS v16; // eax
  char v17; // al
  _BYTE TlsValue[144]; // [rsp+30h] [rbp-C8h] BYREF

  memset_0(TlsValue, 0, 0x88u);
  v4 = UbpmpLockTrackerId;
  if ( UbpmpLockTrackerId != -1 )
  {
    if ( TlsGetValue(UbpmpLockTrackerId) )
      __int2c();
    TlsSetValue(v4, TlsValue);
  }
  if ( a2 && a2[1] && *(_DWORD *)a2 )
  {
    v5 = 0;
    RtlAcquireSRWLockExclusive(&a1[26]);
    a1[27].Data[0] = GetCurrentThreadId();
    v6 = (const void *)a1[44];
    if ( v6 )
    {
      v7 = *(unsigned int *)a2;
      if ( RtlCompareMemory(v6, a2[1], v7) == v7 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            &WPP_854cad5030553c91fcf88b43a20977bf_Traceguids,
            *(_QWORD *)(*(_QWORD *)&a1[3] + 8LL));
LABEL_13:
        a1[27].Data[0] = 0;
        RtlReleaseSRWLockExclusive(&a1[26]);
        goto LABEL_14;
      }
    }
    v10 = UbpmAlloc(*(unsigned int *)a2);
    v11 = v10;
    if ( !v10 )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          (unsigned int)&WPP_854cad5030553c91fcf88b43a20977bf_Traceguids,
          *(_QWORD *)(*(_QWORD *)&a1[3] + 8LL),
          LastError);
      goto LABEL_13;
    }
    memcpy_0(v10, a2[1], *(unsigned int *)a2);
    if ( IsValidSecurityDescriptor(v11) )
    {
      if ( UbpmUtilsIsStateNameAllocated(a1 + 42) )
      {
        v16 = NtDeleteWnfStateName(&a1[42]);
        if ( v16 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v17 = RtlNtStatusToDosError(v16);
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            23,
            (unsigned int)&WPP_854cad5030553c91fcf88b43a20977bf_Traceguids,
            *(_QWORD *)(*(_QWORD *)&a1[3] + 8LL),
            v17);
        }
        a1[42] = 0;
        a1[43].Data[0] = 0;
      }
      UBPM_MIDL_user_free(*(_QWORD *)&a1[44], v13, v14, v15);
      a1[44] = (struct _WNF_STATE_NAME)v11;
      a1[27].Data[0] = 0;
      RtlReleaseSRWLockExclusive(&a1[26]);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          24,
          &WPP_854cad5030553c91fcf88b43a20977bf_Traceguids,
          *(_QWORD *)(*(_QWORD *)&a1[3] + 8LL));
    }
    else
    {
      v5 = 87;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          (unsigned int)&WPP_854cad5030553c91fcf88b43a20977bf_Traceguids,
          *(_QWORD *)(*(_QWORD *)&a1[3] + 8LL),
          87);
      a1[27].Data[0] = 0;
      RtlReleaseSRWLockExclusive(&a1[26]);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
    }
  }
  else
  {
    v5 = 87;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        (unsigned int)&WPP_854cad5030553c91fcf88b43a20977bf_Traceguids,
        *(_QWORD *)(*(_QWORD *)&a1[3] + 8LL),
        87);
  }
LABEL_14:
  v8 = UbpmpLockTrackerId;
  if ( UbpmpLockTrackerId != -1 )
  {
    if ( *(_QWORD *)TlsGetValue(UbpmpLockTrackerId) )
      __int2c();
    TlsSetValue(v8, 0);
  }
  return v5;
}

```

## disassembly

```asm
0x180025e00  mov     r11, rsp
0x180025e03  push    rbx
0x180025e04  sub     rsp, 0F0h
0x180025e0b  mov     rax, cs:__security_cookie
0x180025e12  xor     rax, rsp
0x180025e15  mov     [rsp+0F8h+var_38], rax
0x180025e1d  mov     [r11+20h], rsi
0x180025e21  mov     r8d, 88h; Size
0x180025e27  mov     [r11-20h], r14
0x180025e2b  mov     rsi, rdx
0x180025e2e  mov     r14, rcx
0x180025e31  xor     edx, edx; Val
0x180025e33  lea     rcx, [rsp+0F8h+TlsValue]; void *
0x180025e38  call    memset_0
0x180025e3d  mov     ebx, cs:UbpmpLockTrackerId
0x180025e43  cmp     ebx, 0FFFFFFFFh
0x180025e46  jz      short loc_180025E72
0x180025e48  mov     ecx, ebx; dwTlsIndex
0x180025e4a  call    cs:__imp_TlsGetValue
0x180025e51  nop     dword ptr [rax+rax+00h]
0x180025e56  test    rax, rax
0x180025e59  jnz     loc_18002610E
0x180025e5f  lea     rdx, [rsp+0F8h+TlsValue]; lpTlsValue
0x180025e64  mov     ecx, ebx; dwTlsIndex
0x180025e66  call    cs:__imp_TlsSetValue
0x180025e6d  nop     dword ptr [rax+rax+00h]
0x180025e72  mov     [rsp+0F8h+arg_10], rbp
0x180025e7a  mov     [rsp+0F8h+var_10], rdi
0x180025e82  mov     [rsp+0F8h+var_18], r12
0x180025e8a  mov     [rsp+0F8h+var_28], r15
0x180025e92  test    rsi, rsi
0x180025e95  jz      loc_18002601F
0x180025e9b  cmp     qword ptr [rsi+8], 0
0x180025ea0  jz      loc_18002601F
0x180025ea6  cmp     dword ptr [rsi], 0
0x180025ea9  jz      loc_18002601F
0x180025eaf  lea     rdi, [r14+0D0h]
0x180025eb6  xor     r12d, r12d
0x180025eb9  mov     rcx, rdi
0x180025ebc  mov     ebp, r12d
0x180025ebf  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180025ec6  nop     dword ptr [rax+rax+00h]
0x180025ecb  call    cs:__imp_GetCurrentThreadId
0x180025ed2  nop     dword ptr [rax+rax+00h]
0x180025ed7  mov     [rdi+8], eax
0x180025eda  mov     rcx, [r14+160h]; Source1
0x180025ee1  test    rcx, rcx
0x180025ee4  jz      loc_180025FB7
0x180025eea  mov     ebx, [rsi]
0x180025eec  mov     rdx, [rsi+8]; Source2
0x180025ef0  mov     r8d, ebx; Length
0x180025ef3  call    cs:__imp_RtlCompareMemory
0x180025efa  nop     dword ptr [rax+rax+00h]
0x180025eff  cmp     rax, rbx
0x180025f02  jnz     loc_180025FB7
0x180025f08  mov     rcx, cs:WPP_GLOBAL_Control
0x180025f0f  lea     rbx, WPP_GLOBAL_Control
0x180025f16  cmp     rcx, rbx
0x180025f19  jz      short loc_180025F25
0x180025f1b  test    byte ptr [rcx+1Ch], 4
0x180025f1f  jnz     loc_180026115
0x180025f25  mov     rcx, rdi
0x180025f28  mov     [rdi+8], r12d
0x180025f2c  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180025f33  nop     dword ptr [rax+rax+00h]
0x180025f38  mov     ebx, cs:UbpmpLockTrackerId
0x180025f3e  mov     r15, [rsp+0F8h+var_28]
0x180025f46  mov     r14, [rsp+0F8h+var_20]
0x180025f4e  mov     r12, [rsp+0F8h+var_18]
0x180025f56  mov     rdi, [rsp+0F8h+var_10]
0x180025f5e  mov     rsi, [rsp+0F8h+arg_18]
0x180025f66  cmp     ebx, 0FFFFFFFFh
0x180025f69  jz      short loc_180025F93
0x180025f6b  mov     ecx, ebx; dwTlsIndex
0x180025f6d  call    cs:__imp_TlsGetValue
0x180025f74  nop     dword ptr [rax+rax+00h]
0x180025f79  cmp     qword ptr [rax], 0
0x180025f7d  jnz     loc_180026220
0x180025f83  xor     edx, edx; lpTlsValue
0x180025f85  mov     ecx, ebx; dwTlsIndex
0x180025f87  call    cs:__imp_TlsSetValue
0x180025f8e  nop     dword ptr [rax+rax+00h]
0x180025f93  mov     eax, ebp
0x180025f95  mov     rbp, [rsp+0F8h+arg_10]
0x180025f9d  mov     rcx, [rsp+0F8h+var_38]
0x180025fa5  xor     rcx, rsp; StackCookie
0x180025fa8  call    __security_check_cookie
0x180025fad  add     rsp, 0F0h
0x180025fb4  pop     rbx
0x180025fb5  retn
0x180025fb7  mov     ecx, [rsi]; Size
0x180025fb9  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x180025fbe  mov     r15, rax
0x180025fc1  test    rax, rax
0x180025fc4  jnz     loc_18002606B
0x180025fca  call    cs:__imp_GetLastError
0x180025fd1  nop     dword ptr [rax+rax+00h]
0x180025fd6  mov     ebp, eax
0x180025fd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180025fdf  lea     rbx, WPP_GLOBAL_Control
0x180025fe6  cmp     rcx, rbx
0x180025fe9  jz      loc_180025F25
0x180025fef  test    byte ptr [rcx+1Ch], 1
0x180025ff3  jz      loc_180025F25
0x180025ff9  mov     r9, [r14+18h]
0x180025ffd  lea     r8, WPP_854cad5030553c91fcf88b43a20977bf_Traceguids
0x180026004  mov     rcx, [rcx+10h]
0x180026008  mov     edx, 15h
0x18002600d  mov     [rsp+0F8h+var_D8], eax
0x180026011  mov     r9, [r9+8]
0x180026015  call    WPP_SF_Sd
0x18002601a  jmp     loc_180025F25
0x18002601f  mov     ebp, 57h ; 'W'
0x180026024  mov     rcx, cs:WPP_GLOBAL_Control
0x18002602b  lea     rbx, WPP_GLOBAL_Control
0x180026032  cmp     rcx, rbx
0x180026035  jz      loc_180025F38
0x18002603b  test    byte ptr [rcx+1Ch], 1
0x18002603f  jz      loc_180025F38
0x180026045  mov     r9, [r14+18h]
0x180026049  lea     r8, WPP_854cad5030553c91fcf88b43a20977bf_Traceguids
0x180026050  mov     rcx, [rcx+10h]
0x180026054  mov     edx, 13h
0x180026059  mov     [rsp+0F8h+var_D8], ebp
0x18002605d  mov     r9, [r9+8]
0x180026061  call    WPP_SF_Sd
0x180026066  jmp     loc_180025F38
0x18002606b  mov     r8d, [rsi]; Size
0x18002606e  mov     rcx, r15; void *
0x180026071  mov     rdx, [rsi+8]; Src
0x180026075  call    memcpy_0
0x18002607a  mov     rcx, r15; pSecurityDescriptor
0x18002607d  call    cs:__imp_IsValidSecurityDescriptor
0x180026084  nop     dword ptr [rax+rax+00h]
0x180026089  test    eax, eax
0x18002608b  jz      loc_180026137
0x180026091  lea     rcx, [r14+150h]; struct _WNF_STATE_NAME *
0x180026098  call    ?UbpmUtilsIsStateNameAllocated@@YAEPEAU_WNF_STATE_NAME@@@Z; UbpmUtilsIsStateNameAllocated(_WNF_STATE_NAME *)
0x18002609d  lea     rbx, WPP_GLOBAL_Control
0x1800260a4  test    al, al
0x1800260a6  jnz     loc_1800261AC
0x1800260ac  mov     rcx, [r14+160h]
0x1800260b3  call    UBPM_MIDL_user_free
0x1800260b8  mov     [r14+160h], r15
0x1800260bf  mov     rcx, rdi
0x1800260c2  mov     [rdi+8], r12d
0x1800260c6  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800260cd  nop     dword ptr [rax+rax+00h]
0x1800260d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800260d9  cmp     rcx, rbx
0x1800260dc  jz      loc_180025F38
0x1800260e2  test    byte ptr [rcx+1Ch], 4
0x1800260e6  jz      loc_180025F38
0x1800260ec  mov     r9, [r14+18h]
0x1800260f0  lea     r8, WPP_854cad5030553c91fcf88b43a20977bf_Traceguids
0x1800260f7  mov     rcx, [rcx+10h]
0x1800260fb  mov     edx, 18h
0x180026100  mov     r9, [r9+8]
0x180026104  call    WPP_SF_S
0x180026109  jmp     loc_180025F38
0x18002610e  int     2Ch; Windows NT - assertion failure
0x180026110  jmp     loc_180025E5F
0x180026115  mov     r9, [r14+18h]
0x180026119  lea     r8, WPP_854cad5030553c91fcf88b43a20977bf_Traceguids
0x180026120  mov     rcx, [rcx+10h]
0x180026124  mov     edx, 14h
0x180026129  mov     r9, [r9+8]
0x18002612d  call    WPP_SF_S
0x180026132  jmp     loc_180025F25
0x180026137  mov     ebp, 57h ; 'W'
0x18002613c  mov     rcx, cs:WPP_GLOBAL_Control
0x180026143  lea     rbx, WPP_GLOBAL_Control
0x18002614a  cmp     rcx, rbx
0x18002614d  jz      short loc_180026176
0x18002614f  test    byte ptr [rcx+1Ch], 1
0x180026153  jz      short loc_180026176
0x180026155  mov     r9, [r14+18h]
0x180026159  lea     r8, WPP_854cad5030553c91fcf88b43a20977bf_Traceguids
0x180026160  mov     rcx, [rcx+10h]
0x180026164  mov     edx, 16h
0x180026169  mov     [rsp+0F8h+var_D8], ebp
0x18002616d  mov     r9, [r9+8]
0x180026171  call    WPP_SF_Sd
0x180026176  mov     rcx, rdi
0x180026179  mov     [rdi+8], r12d
0x18002617d  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180026184  nop     dword ptr [rax+rax+00h]
0x180026189  mov     rcx, gs:60h
0x180026192  mov     r8, r15; P
0x180026195  xor     edx, edx; Flags
0x180026197  mov     rcx, [rcx+30h]; HeapHandle
0x18002619b  call    cs:__imp_RtlFreeHeap
0x1800261a2  nop     dword ptr [rax+rax+00h]
0x1800261a7  jmp     loc_180025F38
0x1800261ac  lea     rcx, [r14+150h]
0x1800261b3  call    cs:__imp_NtDeleteWnfStateName
0x1800261ba  nop     dword ptr [rax+rax+00h]
0x1800261bf  test    eax, eax
0x1800261c1  jns     short loc_18002620B
0x1800261c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800261ca  cmp     rcx, rbx
0x1800261cd  jz      short loc_18002620B
0x1800261cf  test    byte ptr [rcx+1Ch], 1
0x1800261d3  jz      short loc_18002620B
0x1800261d5  mov     ecx, eax; Status
0x1800261d7  call    cs:__imp_RtlNtStatusToDosError
0x1800261de  nop     dword ptr [rax+rax+00h]
0x1800261e3  mov     r9, [r14+18h]
0x1800261e7  lea     r8, WPP_854cad5030553c91fcf88b43a20977bf_Traceguids
0x1800261ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800261f5  mov     edx, 17h
0x1800261fa  mov     [rsp+0F8h+var_D8], eax
0x1800261fe  mov     r9, [r9+8]
0x180026202  mov     rcx, [rcx+10h]
0x180026206  call    WPP_SF_Sd
0x18002620b  xor     eax, eax
0x18002620d  mov     [r14+150h], rax
0x180026214  mov     [r14+158h], r12d
0x18002621b  jmp     loc_1800260AC
0x180026220  int     2Ch; Windows NT - assertion failure
0x180026222  jmp     loc_180025F83
```
