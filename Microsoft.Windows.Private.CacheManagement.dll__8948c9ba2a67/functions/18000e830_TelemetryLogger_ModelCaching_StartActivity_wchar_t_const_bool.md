# TelemetryLogger::ModelCaching::StartActivity(wchar_t const *,bool)

- ea: `0x18000e830`
- end: `0x18000eaa7`
- name: `?StartActivity@ModelCaching@TelemetryLogger@@QEAAXPEB_W_N@Z`
- size: `631`
- prototype: `void __fastcall(TelemetryLogger::ModelCaching *this, const wchar_t *, char)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180007410`

## callees

- `0x18000e830`
- `0x18000eb80`
- `0x1800116f0`
- `0x1800181b0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000e940`
- `KERNEL32!GetCurrentThreadId` at `0x18000e940`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000e885`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000e885`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000e8ab`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000e909`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000e8ab`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000e909`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000ea62`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000ea62`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000e8ec`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000e8ec`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall TelemetryLogger::ModelCaching::StartActivity(
        TelemetryLogger::ModelCaching *this,
        const wchar_t *a2,
        char a3)
{
  RTL_SRWLOCK *v3; // rbx
  RTL_SRWLOCK *v7; // rbx
  __int64 v8; // rsi
  __int64 v9; // rcx
  __int64 v10; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v12; // r8
  const GUID *v13; // r9
  __int64 v14; // rax
  int v16; // eax
  char v17; // [rsp+30h] [rbp-69h] BYREF
  __int64 v18; // [rsp+38h] [rbp-61h]
  PSRWLOCK SRWLock; // [rsp+40h] [rbp-59h] BYREF
  __int64 v20; // [rsp+48h] [rbp-51h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+50h] [rbp-49h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-39h] BYREF
  int *v23; // [rsp+70h] [rbp-29h]
  int v24; // [rsp+78h] [rbp-21h]
  int v25; // [rsp+7Ch] [rbp-1Dh]
  __int64 *v26; // [rsp+80h] [rbp-19h]
  __int64 v27; // [rsp+88h] [rbp-11h]
  PSRWLOCK *p_SRWLock; // [rsp+90h] [rbp-9h]
  __int64 v29; // [rsp+98h] [rbp-1h]
  const wchar_t *v30; // [rsp+A0h] [rbp+7h]
  int v31; // [rsp+A8h] [rbp+Fh]
  int v32; // [rsp+ACh] [rbp+13h]
  char *v33; // [rsp+B0h] [rbp+17h]
  __int64 v34; // [rsp+B8h] [rbp+1Fh]

  v3 = (RTL_SRWLOCK *)*((_QWORD *)this + 35);
  if ( v3 )
  {
    v7 = v3 + 33;
    AcquireSRWLockExclusive(v7);
    v18 = 0;
  }
  else
  {
    v7 = 0;
    SRWLock = 0;
  }
  v8 = *((_QWORD *)this + 34);
  v9 = *((_QWORD *)TelemetryLogger::Instance() + 1);
  if ( *(_DWORD *)v9 > 5u
    && (*(_QWORD *)(v9 + 16) & 0x400000000000LL) != 0
    && (*(_QWORD *)(v9 + 24) & 0x400000000000LL) == *(_QWORD *)(v9 + 24) )
  {
    EventActivityIdControl(3u, (LPGUID)(v8 + 8));
  }
  else
  {
    *(_OWORD *)(v8 + 8) = 0;
  }
  *(_DWORD *)v8 = 1;
  if ( v7 )
    ReleaseSRWLockExclusive(v7);
  v10 = *((_QWORD *)TelemetryLogger::Instance() + 1);
  if ( *(_DWORD *)v10 > 5u
    && (*(_QWORD *)(v10 + 16) & 0x400000000000LL) != 0
    && (*(_QWORD *)(v10 + 24) & 0x400000000000LL) == *(_QWORD *)(v10 + 24) )
  {
    v17 = a3;
    CurrentThreadId = GetCurrentThreadId();
    v12 = *((_QWORD *)this + 34);
    LODWORD(SRWLock) = CurrentThreadId;
    v20 = 0x1000000;
    if ( !*(_BYTE *)(v12 + 4)
      || (v13 = (const GUID *)(v12 + 24), !*(_DWORD *)(v12 + 24))
      && !*(_DWORD *)(v12 + 28)
      && !*(_DWORD *)(v12 + 32)
      && !*(_DWORD *)(v12 + 36) )
    {
      v13 = 0;
    }
    v34 = 1;
    v33 = &v17;
    if ( a2 )
    {
      v14 = -1;
      while ( a2[++v14] != 0 )
        ;
      v16 = 2 * v14 + 2;
    }
    else
    {
      a2 = &S2;
      v16 = 2;
    }
    v31 = v16;
    v30 = a2;
    p_SRWLock = &SRWLock;
    v32 = 0;
    v26 = &v20;
    *(_DWORD *)&EventDescriptor.Level = 261;
    UserData.Ptr = *(_QWORD *)(v10 + 8);
    v29 = 4;
    v27 = 8;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0x400000000000LL;
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    v23 = &dword_180026FFC;
    UserData.Reserved = 2;
    v24 = 79;
    v25 = 1;
    LODWORD(v18) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(*(_QWORD *)(v10 + 32), &EventDescriptor, (LPCGUID)(v12 + 8), v13, 6u, &UserData);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((TelemetryLogger::ModelCaching *)((char *)this + 288));
}

```

## disassembly

```asm
0x18000e830  mov     [rsp-8+arg_8], rbx
0x18000e835  mov     [rsp-8+arg_10], rsi
0x18000e83a  mov     [rsp-8+arg_18], rdi
0x18000e83f  push    rbp
0x18000e840  push    r12
0x18000e842  push    r13
0x18000e844  push    r14
0x18000e846  push    r15
0x18000e848  lea     rbp, [rsp-37h]
0x18000e84d  sub     rsp, 0D0h
0x18000e854  mov     rax, cs:__security_cookie
0x18000e85b  xor     rax, rsp
0x18000e85e  mov     [rbp+57h+var_30], rax
0x18000e862  mov     rbx, [rcx+118h]
0x18000e869  xor     r12d, r12d
0x18000e86c  movzx   r15d, r8b
0x18000e870  mov     rdi, rdx
0x18000e873  mov     r14, rcx
0x18000e876  test    rbx, rbx
0x18000e879  jz      short loc_18000E898
0x18000e87b  add     rbx, 108h
0x18000e882  mov     rcx, rbx; SRWLock
0x18000e885  call    cs:__imp_AcquireSRWLockExclusive
0x18000e88b  lea     rax, [rbp+57h+var_B8]
0x18000e88f  mov     [rax], r12
0x18000e892  mov     rcx, [rbp+57h+var_B8]
0x18000e896  jmp     short loc_18000E8A6
0x18000e898  lea     rax, [rbp+57h+SRWLock]
0x18000e89c  mov     rbx, r12
0x18000e89f  mov     [rax], r12
0x18000e8a2  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18000e8a6  test    rcx, rcx
0x18000e8a9  jz      short loc_18000E8B1
0x18000e8ab  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e8b1  mov     rsi, [r14+110h]
0x18000e8b8  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x18000e8bd  mov     r13, 400000000000h
0x18000e8c7  mov     rcx, [rax+8]
0x18000e8cb  cmp     dword ptr [rcx], 5
0x18000e8ce  jbe     short loc_18000E8F4
0x18000e8d0  test    [rcx+10h], r13
0x18000e8d4  jz      short loc_18000E8F4
0x18000e8d6  mov     rax, [rcx+18h]
0x18000e8da  and     rax, r13
0x18000e8dd  cmp     rax, [rcx+18h]
0x18000e8e1  jnz     short loc_18000E8F4
0x18000e8e3  lea     rdx, [rsi+8]; ActivityId
0x18000e8e7  mov     ecx, 3; ControlCode
0x18000e8ec  call    cs:__imp_EventActivityIdControl
0x18000e8f2  jmp     short loc_18000E8FB
0x18000e8f4  xorps   xmm0, xmm0
0x18000e8f7  movups  xmmword ptr [rsi+8], xmm0
0x18000e8fb  mov     dword ptr [rsi], 1
0x18000e901  test    rbx, rbx
0x18000e904  jz      short loc_18000E90F
0x18000e906  mov     rcx, rbx; SRWLock
0x18000e909  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e90f  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x18000e914  mov     rbx, [rax+8]
0x18000e918  cmp     dword ptr [rbx], 5
0x18000e91b  jbe     loc_18000EA68
0x18000e921  test    [rbx+10h], r13
0x18000e925  jz      loc_18000EA68
0x18000e92b  mov     rax, [rbx+18h]
0x18000e92f  and     rax, r13
0x18000e932  cmp     rax, [rbx+18h]
0x18000e936  jnz     loc_18000EA68
0x18000e93c  mov     [rbp+57h+var_C0], r15b
0x18000e940  call    cs:__imp_GetCurrentThreadId
0x18000e946  mov     r8, [r14+110h]
0x18000e94d  mov     dword ptr [rbp+57h+SRWLock], eax
0x18000e950  mov     [rbp+57h+var_A8], 1000000h
0x18000e958  cmp     [r8+4], r12b
0x18000e95c  jz      short loc_18000E97A
0x18000e95e  cmp     [r8+18h], r12d
0x18000e962  lea     r9, [r8+18h]
0x18000e966  jnz     short loc_18000E97D
0x18000e968  cmp     [r9+4], r12d
0x18000e96c  jnz     short loc_18000E97D
0x18000e96e  cmp     [r9+8], r12d
0x18000e972  jnz     short loc_18000E97D
0x18000e974  cmp     [r9+0Ch], r12d
0x18000e978  jnz     short loc_18000E97D
0x18000e97a  mov     r9, r12; RelatedActivityId
0x18000e97d  mov     [rbp+57h+var_38], 1
0x18000e985  lea     rax, [rbp+57h+var_C0]
0x18000e989  mov     [rbp+57h+var_40], rax
0x18000e98d  test    rdi, rdi
0x18000e990  jz      short loc_18000E9B5
0x18000e992  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000e999  nop     dword ptr [rax+00000000h]
0x18000e9a0  cmp     [rdi+rax*2+2], r12w
0x18000e9a6  lea     rax, [rax+1]
0x18000e9aa  jnz     short loc_18000E9A0
0x18000e9ac  lea     eax, ds:2[rax*2]
0x18000e9b3  jmp     short loc_18000E9C1
0x18000e9b5  lea     rdi, S2
0x18000e9bc  mov     eax, 2
0x18000e9c1  mov     [rbp+57h+var_48], eax
0x18000e9c4  lea     rcx, _TraceLoggingMetadata
0x18000e9cb  mov     [rbp+57h+var_50], rdi
0x18000e9cf  lea     rax, [rbp+57h+SRWLock]
0x18000e9d3  mov     [rbp+57h+var_60], rax
0x18000e9d7  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18000e9db  lea     rax, [rbp+57h+var_A8]
0x18000e9df  mov     [rbp+57h+var_44], r12d
0x18000e9e3  mov     [rbp+57h+var_70], rax
0x18000e9e7  add     r8, 8; ActivityId
0x18000e9eb  movzx   eax, cs:word_180026FF2
0x18000e9f2  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18000e9f5  mov     rax, [rbx+8]
0x18000e9f9  mov     [rbp+57h+var_90.Ptr], rax
0x18000e9fd  mov     [rbp+57h+var_58], 4
0x18000ea05  mov     [rbp+57h+var_68], 8
0x18000ea0d  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18000ea14  mov     [rbp+57h+EventDescriptor.Keyword], r13
0x18000ea18  movzx   eax, word ptr [rax]
0x18000ea1b  mov     [rbp+57h+var_90.Size], eax
0x18000ea1e  lea     rax, dword_180026FFC
0x18000ea25  mov     [rbp+57h+var_80], rax
0x18000ea29  lea     rax, _TraceLoggingMetadataEnd
0x18000ea30  sub     eax, ecx
0x18000ea32  mov     dword ptr [rbp+57h+var_90.0Ch], 2
0x18000ea39  mov     [rbp+57h+var_78], 4Fh ; 'O'
0x18000ea40  mov     [rbp+57h+var_74], 1
0x18000ea47  mov     dword ptr [rbp+57h+var_B8], eax
0x18000ea4a  mov     eax, dword ptr [rbp+57h+var_B8]
0x18000ea4d  mov     rcx, [rbx+20h]; RegHandle
0x18000ea51  lea     rax, [rbp+57h+var_90]
0x18000ea55  mov     [rsp+0F0h+UserData], rax; UserData
0x18000ea5a  mov     [rsp+0F0h+UserDataCount], 6; UserDataCount
0x18000ea62  call    cs:__imp_EventWriteTransfer
0x18000ea68  lea     rcx, [r14+120h]; this
0x18000ea6f  cmp     [rcx+18h], r12d
0x18000ea73  jnz     short loc_18000EA7A
0x18000ea75  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18000ea7a  mov     rcx, [rbp+57h+var_30]
0x18000ea7e  xor     rcx, rsp; StackCookie
0x18000ea81  call    __security_check_cookie
0x18000ea86  lea     r11, [rsp+0F0h+var_20]
0x18000ea8e  mov     rbx, [r11+38h]
0x18000ea92  mov     rsi, [r11+40h]
0x18000ea96  mov     rdi, [r11+48h]
0x18000ea9a  mov     rsp, r11
0x18000ea9d  pop     r15
0x18000ea9f  pop     r14
0x18000eaa1  pop     r13
0x18000eaa3  pop     r12
0x18000eaa5  pop     rbp
0x18000eaa6  retn
```
