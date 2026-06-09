# FwppDeepCopyToVerIndependent_IPSEC_AUTH_TRANSFORM_ID0

- ea: `0x180062e64`
- end: `0x180062f04`
- name: `FwppDeepCopyToVerIndependent_IPSEC_AUTH_TRANSFORM_ID0`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180062dd4`

## callees

- `0x1800050cc`
- `0x18000c9b4`
- `0x180062e64`
- `0x18006445c`

## string_xrefs

- `0x180062e9f`: `FwppDeepCopyToVerIndependent_IPSEC_AUTH_CONFIG`
- `0x180062eb3`: `FwppDeepCopyToVerIndependent_IPSEC_AUTH_CONFIG`
- `0x180062eca`: `FwppDeepCopyToVerIndependent_IPSEC_AUTH_TRANSFORM_ID0`
- `0x180062ee6`: `FwppDeepCopyToVerIndependent_IPSEC_AUTH_TRANSFORM_ID0`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyToVerIndependent_IPSEC_AUTH_TRANSFORM_ID0(_DWORD *a1, _DWORD *a2)
{
  _BYTE *v3; // rax
  __int64 v4; // rbx
  __int64 v5; // rax

  if ( !a1 || !a2 )
  {
    v4 = WfpReportAppErrorAsNtStatus(
           (__int64)a1,
           (__int64)"FwppDeepCopyToVerIndependent_IPSEC_AUTH_TRANSFORM_ID0",
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
           (__int64)"FwppDeepCopyToVerIndependent_IPSEC_AUTH_CONFIG",
           3223453724LL);
    v4 = v5;
    if ( !v5 )
      return v4;
    WfpReportError(v5, (int)"FwppDeepCopyToVerIndependent_IPSEC_AUTH_CONFIG");
LABEL_9:
    FwppDeepFreeContentsOnly_IPSEC_SA_IDLE_TIMEOUT0(a2);
    WfpReportError(v4, (int)"FwppDeepCopyToVerIndependent_IPSEC_AUTH_TRANSFORM_ID0");
    return v4;
  }
  v4 = 0;
  *(_BYTE *)a1 = *v3;
  return v4;
}

```

## disassembly

```asm
0x180062e64  mov     [rsp+arg_0], rbx
0x180062e69  push    rdi
0x180062e6a  sub     rsp, 30h
0x180062e6e  mov     rdi, rdx
0x180062e71  test    rcx, rcx
0x180062e74  jz      short loc_180062EC4
0x180062e76  test    rdx, rdx
0x180062e79  jz      short loc_180062EC4
0x180062e7b  mov     eax, [rcx]
0x180062e7d  mov     [rdx], eax
0x180062e7f  lea     rax, [rcx+4]
0x180062e83  test    rax, rax
0x180062e86  jz      short loc_180062E99
0x180062e88  lea     rcx, [rdx+4]
0x180062e8c  test    rcx, rcx
0x180062e8f  jz      short loc_180062E99
0x180062e91  mov     al, [rax]
0x180062e93  xor     ebx, ebx
0x180062e95  mov     [rcx], al
0x180062e97  jmp     short loc_180062EF5
0x180062e99  mov     r8d, 0C022001Ch
0x180062e9f  lea     rdx, aFwppdeepcopyto_103; "FwppDeepCopyToVerIndependent_IPSEC_AUTH"...
0x180062ea6  call    WfpReportAppErrorAsNtStatus
0x180062eab  mov     rbx, rax
0x180062eae  test    rax, rax
0x180062eb1  jz      short loc_180062EF5
0x180062eb3  lea     rdx, aFwppdeepcopyto_103; "FwppDeepCopyToVerIndependent_IPSEC_AUTH"...
0x180062eba  mov     rcx, rax
0x180062ebd  call    WfpReportError
0x180062ec2  jmp     short loc_180062EDE
0x180062ec4  mov     r8d, 0C022001Ch
0x180062eca  lea     rdx, aFwppdeepcopyto_43; "FwppDeepCopyToVerIndependent_IPSEC_AUTH"...
0x180062ed1  call    WfpReportAppErrorAsNtStatus
0x180062ed6  mov     rbx, rax
0x180062ed9  test    rax, rax
0x180062edc  jz      short loc_180062EF5
0x180062ede  mov     rcx, rdi
0x180062ee1  call    FwppDeepFreeContentsOnly_IPSEC_SA_IDLE_TIMEOUT0
0x180062ee6  lea     rdx, aFwppdeepcopyto_43; "FwppDeepCopyToVerIndependent_IPSEC_AUTH"...
0x180062eed  mov     rcx, rbx
0x180062ef0  call    WfpReportError
0x180062ef5  mov     rax, rbx
0x180062ef8  mov     rbx, [rsp+38h+arg_0]
0x180062efd  add     rsp, 30h
0x180062f01  pop     rdi
0x180062f02  retn
```
