# FwppDeepCopyToVerIndependent_IPSEC_CIPHER_TRANSFORM_ID0

- ea: `0x180062f9c`
- end: `0x18006303c`
- name: `FwppDeepCopyToVerIndependent_IPSEC_CIPHER_TRANSFORM_ID0`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180062f0c`

## callees

- `0x1800050cc`
- `0x18000c9b4`
- `0x180062f9c`
- `0x18006445c`

## string_xrefs

- `0x180062fd7`: `FwppDeepCopyToVerIndependent_IPSEC_CIPHER_CONFIG`
- `0x180062feb`: `FwppDeepCopyToVerIndependent_IPSEC_CIPHER_CONFIG`
- `0x180063002`: `FwppDeepCopyToVerIndependent_IPSEC_CIPHER_TRANSFORM_ID0`
- `0x18006301e`: `FwppDeepCopyToVerIndependent_IPSEC_CIPHER_TRANSFORM_ID0`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyToVerIndependent_IPSEC_CIPHER_TRANSFORM_ID0(_DWORD *a1, _DWORD *a2)
{
  _BYTE *v3; // rax
  __int64 v4; // rbx
  __int64 v5; // rax

  if ( !a1 || !a2 )
  {
    v4 = WfpReportAppErrorAsNtStatus(
           (__int64)a1,
           (__int64)"FwppDeepCopyToVerIndependent_IPSEC_CIPHER_TRANSFORM_ID0",
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
           (__int64)"FwppDeepCopyToVerIndependent_IPSEC_CIPHER_CONFIG",
           3223453724LL);
    v4 = v5;
    if ( !v5 )
      return v4;
    WfpReportError(v5, (int)"FwppDeepCopyToVerIndependent_IPSEC_CIPHER_CONFIG");
LABEL_9:
    FwppDeepFreeContentsOnly_IPSEC_SA_IDLE_TIMEOUT0(a2);
    WfpReportError(v4, (int)"FwppDeepCopyToVerIndependent_IPSEC_CIPHER_TRANSFORM_ID0");
    return v4;
  }
  v4 = 0;
  *(_BYTE *)a1 = *v3;
  return v4;
}

```

## disassembly

```asm
0x180062f9c  mov     [rsp+arg_0], rbx
0x180062fa1  push    rdi
0x180062fa2  sub     rsp, 30h
0x180062fa6  mov     rdi, rdx
0x180062fa9  test    rcx, rcx
0x180062fac  jz      short loc_180062FFC
0x180062fae  test    rdx, rdx
0x180062fb1  jz      short loc_180062FFC
0x180062fb3  mov     eax, [rcx]
0x180062fb5  mov     [rdx], eax
0x180062fb7  lea     rax, [rcx+4]
0x180062fbb  test    rax, rax
0x180062fbe  jz      short loc_180062FD1
0x180062fc0  lea     rcx, [rdx+4]
0x180062fc4  test    rcx, rcx
0x180062fc7  jz      short loc_180062FD1
0x180062fc9  mov     al, [rax]
0x180062fcb  xor     ebx, ebx
0x180062fcd  mov     [rcx], al
0x180062fcf  jmp     short loc_18006302D
0x180062fd1  mov     r8d, 0C022001Ch
0x180062fd7  lea     rdx, aFwppdeepcopyto_29; "FwppDeepCopyToVerIndependent_IPSEC_CIPH"...
0x180062fde  call    WfpReportAppErrorAsNtStatus
0x180062fe3  mov     rbx, rax
0x180062fe6  test    rax, rax
0x180062fe9  jz      short loc_18006302D
0x180062feb  lea     rdx, aFwppdeepcopyto_29; "FwppDeepCopyToVerIndependent_IPSEC_CIPH"...
0x180062ff2  mov     rcx, rax
0x180062ff5  call    WfpReportError
0x180062ffa  jmp     short loc_180063016
0x180062ffc  mov     r8d, 0C022001Ch
0x180063002  lea     rdx, aFwppdeepcopyto_89; "FwppDeepCopyToVerIndependent_IPSEC_CIPH"...
0x180063009  call    WfpReportAppErrorAsNtStatus
0x18006300e  mov     rbx, rax
0x180063011  test    rax, rax
0x180063014  jz      short loc_18006302D
0x180063016  mov     rcx, rdi
0x180063019  call    FwppDeepFreeContentsOnly_IPSEC_SA_IDLE_TIMEOUT0
0x18006301e  lea     rdx, aFwppdeepcopyto_89; "FwppDeepCopyToVerIndependent_IPSEC_CIPH"...
0x180063025  mov     rcx, rbx
0x180063028  call    WfpReportError
0x18006302d  mov     rax, rbx
0x180063030  mov     rbx, [rsp+38h+arg_0]
0x180063035  add     rsp, 30h
0x180063039  pop     rdi
0x18006303a  retn
```
