# FwppDeepCopyFromVerIndependent_IPSEC_CIPHER_TRANSFORM_ID0

- ea: `0x180060064`
- end: `0x180060104`
- name: `FwppDeepCopyFromVerIndependent_IPSEC_CIPHER_TRANSFORM_ID0`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18005ffd4`

## callees

- `0x1800050cc`
- `0x18000c9b4`
- `0x180060064`
- `0x18006445c`

## string_xrefs

- `0x18006009f`: `FwppDeepCopyFromVerIndependent_IPSEC_CIPHER_CONFIG`
- `0x1800600b3`: `FwppDeepCopyFromVerIndependent_IPSEC_CIPHER_CONFIG`
- `0x1800600ca`: `FwppDeepCopyFromVerIndependent_IPSEC_CIPHER_TRANSFORM_ID0`
- `0x1800600e6`: `FwppDeepCopyFromVerIndependent_IPSEC_CIPHER_TRANSFORM_ID0`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyFromVerIndependent_IPSEC_CIPHER_TRANSFORM_ID0(_DWORD *a1, _DWORD *a2)
{
  _BYTE *v3; // rax
  __int64 v4; // rbx
  __int64 v5; // rax

  if ( !a1 || !a2 )
  {
    v4 = WfpReportAppErrorAsNtStatus(
           (__int64)a1,
           (__int64)"FwppDeepCopyFromVerIndependent_IPSEC_CIPHER_TRANSFORM_ID0",
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
           (__int64)"FwppDeepCopyFromVerIndependent_IPSEC_CIPHER_CONFIG",
           3223453724LL);
    v4 = v5;
    if ( !v5 )
      return v4;
    WfpReportError(v5, (int)"FwppDeepCopyFromVerIndependent_IPSEC_CIPHER_CONFIG");
LABEL_9:
    FwppDeepFreeContentsOnly_IPSEC_SA_IDLE_TIMEOUT0(a2);
    WfpReportError(v4, (int)"FwppDeepCopyFromVerIndependent_IPSEC_CIPHER_TRANSFORM_ID0");
    return v4;
  }
  v4 = 0;
  *(_BYTE *)a1 = *v3;
  return v4;
}

```

## disassembly

```asm
0x180060064  mov     [rsp+arg_0], rbx
0x180060069  push    rdi
0x18006006a  sub     rsp, 30h
0x18006006e  mov     rdi, rdx
0x180060071  test    rcx, rcx
0x180060074  jz      short loc_1800600C4
0x180060076  test    rdx, rdx
0x180060079  jz      short loc_1800600C4
0x18006007b  mov     eax, [rcx]
0x18006007d  mov     [rdx], eax
0x18006007f  lea     rax, [rcx+4]
0x180060083  test    rax, rax
0x180060086  jz      short loc_180060099
0x180060088  lea     rcx, [rdx+4]
0x18006008c  test    rcx, rcx
0x18006008f  jz      short loc_180060099
0x180060091  mov     al, [rax]
0x180060093  xor     ebx, ebx
0x180060095  mov     [rcx], al
0x180060097  jmp     short loc_1800600F5
0x180060099  mov     r8d, 0C022001Ch
0x18006009f  lea     rdx, aFwppdeepcopyfr_9; "FwppDeepCopyFromVerIndependent_IPSEC_CI"...
0x1800600a6  call    WfpReportAppErrorAsNtStatus
0x1800600ab  mov     rbx, rax
0x1800600ae  test    rax, rax
0x1800600b1  jz      short loc_1800600F5
0x1800600b3  lea     rdx, aFwppdeepcopyfr_9; "FwppDeepCopyFromVerIndependent_IPSEC_CI"...
0x1800600ba  mov     rcx, rax
0x1800600bd  call    WfpReportError
0x1800600c2  jmp     short loc_1800600DE
0x1800600c4  mov     r8d, 0C022001Ch
0x1800600ca  lea     rdx, aFwppdeepcopyfr_131; "FwppDeepCopyFromVerIndependent_IPSEC_CI"...
0x1800600d1  call    WfpReportAppErrorAsNtStatus
0x1800600d6  mov     rbx, rax
0x1800600d9  test    rax, rax
0x1800600dc  jz      short loc_1800600F5
0x1800600de  mov     rcx, rdi
0x1800600e1  call    FwppDeepFreeContentsOnly_IPSEC_SA_IDLE_TIMEOUT0
0x1800600e6  lea     rdx, aFwppdeepcopyfr_131; "FwppDeepCopyFromVerIndependent_IPSEC_CI"...
0x1800600ed  mov     rcx, rbx
0x1800600f0  call    WfpReportError
0x1800600f5  mov     rax, rbx
0x1800600f8  mov     rbx, [rsp+38h+arg_0]
0x1800600fd  add     rsp, 30h
0x180060101  pop     rdi
0x180060102  retn
```
