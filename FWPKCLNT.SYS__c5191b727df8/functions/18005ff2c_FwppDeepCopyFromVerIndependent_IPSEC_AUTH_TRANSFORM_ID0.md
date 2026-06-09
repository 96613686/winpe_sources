# FwppDeepCopyFromVerIndependent_IPSEC_AUTH_TRANSFORM_ID0

- ea: `0x18005ff2c`
- end: `0x18005ffcc`
- name: `FwppDeepCopyFromVerIndependent_IPSEC_AUTH_TRANSFORM_ID0`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18005fe9c`

## callees

- `0x1800050cc`
- `0x18000c9b4`
- `0x18005ff2c`
- `0x18006445c`

## string_xrefs

- `0x18005ff67`: `FwppDeepCopyFromVerIndependent_IPSEC_AUTH_CONFIG`
- `0x18005ff7b`: `FwppDeepCopyFromVerIndependent_IPSEC_AUTH_CONFIG`
- `0x18005ff92`: `FwppDeepCopyFromVerIndependent_IPSEC_AUTH_TRANSFORM_ID0`
- `0x18005ffae`: `FwppDeepCopyFromVerIndependent_IPSEC_AUTH_TRANSFORM_ID0`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyFromVerIndependent_IPSEC_AUTH_TRANSFORM_ID0(_DWORD *a1, _DWORD *a2)
{
  _BYTE *v3; // rax
  __int64 v4; // rbx
  __int64 v5; // rax

  if ( !a1 || !a2 )
  {
    v4 = WfpReportAppErrorAsNtStatus(
           (__int64)a1,
           (__int64)"FwppDeepCopyFromVerIndependent_IPSEC_AUTH_TRANSFORM_ID0",
           3223453724LL);
    if ( !v4 )
      return v4;
    goto LABEL_9;
  }
  *a2 = *a1;
  v3 = a1 + 1;
  if ( a1 == (_DWORD *)-4LL || (a1 = a2 + 1, a2 == (_DWORD *)-4LL) )
  {
    v5 = WfpReportAppErrorAsNtStatus(
           (__int64)a1,
           (__int64)"FwppDeepCopyFromVerIndependent_IPSEC_AUTH_CONFIG",
           3223453724LL);
    v4 = v5;
    if ( !v5 )
      return v4;
    WfpReportError(v5, (int)"FwppDeepCopyFromVerIndependent_IPSEC_AUTH_CONFIG");
LABEL_9:
    FwppDeepFreeContentsOnly_IPSEC_SA_IDLE_TIMEOUT0(a2);
    WfpReportError(v4, (int)"FwppDeepCopyFromVerIndependent_IPSEC_AUTH_TRANSFORM_ID0");
    return v4;
  }
  v4 = 0;
  *(_BYTE *)a1 = *v3;
  return v4;
}

```

## disassembly

```asm
0x18005ff2c  mov     [rsp+arg_0], rbx
0x18005ff31  push    rdi
0x18005ff32  sub     rsp, 30h
0x18005ff36  mov     rdi, rdx
0x18005ff39  test    rcx, rcx
0x18005ff3c  jz      short loc_18005FF8C
0x18005ff3e  test    rdx, rdx
0x18005ff41  jz      short loc_18005FF8C
0x18005ff43  mov     eax, [rcx]
0x18005ff45  mov     [rdx], eax
0x18005ff47  lea     rax, [rcx+4]
0x18005ff4b  test    rax, rax
0x18005ff4e  jz      short loc_18005FF61
0x18005ff50  lea     rcx, [rdx+4]
0x18005ff54  test    rcx, rcx
0x18005ff57  jz      short loc_18005FF61
0x18005ff59  mov     al, [rax]
0x18005ff5b  xor     ebx, ebx
0x18005ff5d  mov     [rcx], al
0x18005ff5f  jmp     short loc_18005FFBD
0x18005ff61  mov     r8d, 0C022001Ch
0x18005ff67  lea     rdx, aFwppdeepcopyfr_39; "FwppDeepCopyFromVerIndependent_IPSEC_AU"...
0x18005ff6e  call    WfpReportAppErrorAsNtStatus
0x18005ff73  mov     rbx, rax
0x18005ff76  test    rax, rax
0x18005ff79  jz      short loc_18005FFBD
0x18005ff7b  lea     rdx, aFwppdeepcopyfr_39; "FwppDeepCopyFromVerIndependent_IPSEC_AU"...
0x18005ff82  mov     rcx, rax
0x18005ff85  call    WfpReportError
0x18005ff8a  jmp     short loc_18005FFA6
0x18005ff8c  mov     r8d, 0C022001Ch
0x18005ff92  lea     rdx, aFwppdeepcopyfr_117; "FwppDeepCopyFromVerIndependent_IPSEC_AU"...
0x18005ff99  call    WfpReportAppErrorAsNtStatus
0x18005ff9e  mov     rbx, rax
0x18005ffa1  test    rax, rax
0x18005ffa4  jz      short loc_18005FFBD
0x18005ffa6  mov     rcx, rdi
0x18005ffa9  call    FwppDeepFreeContentsOnly_IPSEC_SA_IDLE_TIMEOUT0
0x18005ffae  lea     rdx, aFwppdeepcopyfr_117; "FwppDeepCopyFromVerIndependent_IPSEC_AU"...
0x18005ffb5  mov     rcx, rbx
0x18005ffb8  call    WfpReportError
0x18005ffbd  mov     rax, rbx
0x18005ffc0  mov     rbx, [rsp+38h+arg_0]
0x18005ffc5  add     rsp, 30h
0x18005ffc9  pop     rdi
0x18005ffca  retn
```
