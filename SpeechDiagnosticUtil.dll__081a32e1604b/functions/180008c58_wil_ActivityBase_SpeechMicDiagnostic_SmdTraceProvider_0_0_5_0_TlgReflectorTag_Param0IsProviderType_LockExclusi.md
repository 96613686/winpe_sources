# wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)

- ea: `0x180008c58`
- end: `0x180008d05`
- name: `?LockExclusive@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ`
- size: `173`
- prototype: ``
- caller_count: `18`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007f18`
- `0x180009420`
- `0x18000a964`
- `0x18000ac60`
- `0x18000af58`
- `0x18000b26c`
- `0x18000b590`
- `0x18000b888`
- `0x18000bb90`
- `0x18000be20`
- `0x18000c0b0`
- `0x18000c340`
- `0x18000c5d0`
- `0x18000c860`
- `0x18000caf0`
- `0x18000cd80`
- `0x18000d010`
- `0x18000d774`

## callees

- `0x180008c58`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x180008c88`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180008c88`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180008cc9`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180008ce5`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180008cc9`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180008ce5`

## pseudocode

```c
RTL_SRWLOCK **__fastcall wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
        __int64 a1,
        RTL_SRWLOCK **a2)
{
  RTL_SRWLOCK *v3; // rbx
  RTL_SRWLOCK *v4; // rbx
  PSRWLOCK *p_SRWLock; // rax
  char v6; // di
  PSRWLOCK SRWLock; // [rsp+30h] [rbp+8h] BYREF
  PSRWLOCK v9; // [rsp+38h] [rbp+10h] BYREF

  LODWORD(SRWLock) = 0;
  v3 = *(RTL_SRWLOCK **)(a1 + 280);
  if ( v3 )
  {
    v4 = v3 + 33;
    AcquireSRWLockExclusive(v4);
    p_SRWLock = &v9;
    v6 = 1;
  }
  else
  {
    p_SRWLock = &SRWLock;
    v6 = 2;
    v4 = 0;
  }
  *a2 = v4;
  *p_SRWLock = 0;
  if ( (v6 & 2) != 0 )
  {
    v6 &= ~2u;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
  }
  if ( (v6 & 1) != 0 && v9 )
    ReleaseSRWLockExclusive(v9);
  return a2;
}

```

## disassembly

```asm
0x180008c58  mov     [rsp+arg_10], rbx
0x180008c5d  mov     [rsp+arg_18], rsi
0x180008c62  push    rdi
0x180008c63  sub     rsp, 20h
0x180008c67  mov     dword ptr [rsp+28h+SRWLock], 0
0x180008c6f  mov     rsi, rdx
0x180008c72  mov     rbx, [rcx+118h]
0x180008c79  test    rbx, rbx
0x180008c7c  jz      short loc_180008CA0
0x180008c7e  add     rbx, 108h
0x180008c85  mov     rcx, rbx; SRWLock
0x180008c88  call    cs:__imp_AcquireSRWLockExclusive
0x180008c8f  nop     dword ptr [rax+rax+00h]
0x180008c94  lea     rax, [rsp+28h+arg_8]
0x180008c99  mov     edi, 1
0x180008c9e  jmp     short loc_180008CAC
0x180008ca0  lea     rax, [rsp+28h+SRWLock]
0x180008ca5  mov     edi, 2
0x180008caa  xor     ebx, ebx
0x180008cac  mov     [rsi], rbx
0x180008caf  mov     qword ptr [rax], 0
0x180008cb6  test    dil, 2
0x180008cba  jz      short loc_180008CD5
0x180008cbc  mov     rcx, [rsp+28h+SRWLock]; SRWLock
0x180008cc1  and     edi, 0FFFFFFFDh
0x180008cc4  test    rcx, rcx
0x180008cc7  jz      short loc_180008CD5
0x180008cc9  call    cs:__imp_ReleaseSRWLockExclusive
0x180008cd0  nop     dword ptr [rax+rax+00h]
0x180008cd5  test    dil, 1
0x180008cd9  jz      short loc_180008CF1
0x180008cdb  mov     rcx, [rsp+28h+arg_8]; SRWLock
0x180008ce0  test    rcx, rcx
0x180008ce3  jz      short loc_180008CF1
0x180008ce5  call    cs:__imp_ReleaseSRWLockExclusive
0x180008cec  nop     dword ptr [rax+rax+00h]
0x180008cf1  mov     rbx, [rsp+28h+arg_10]
0x180008cf6  mov     rax, rsi
0x180008cf9  mov     rsi, [rsp+28h+arg_18]
0x180008cfe  add     rsp, 20h
0x180008d02  pop     rdi
0x180008d03  retn
```
