# FwppDeepCopyToVerIndependent_IPSEC_TOKEN0

- ea: `0x180063b6c`
- end: `0x180063c71`
- name: `FwppDeepCopyToVerIndependent_IPSEC_TOKEN0`
- size: `261`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18005c6d0`

## callees

- `0x1800050cc`
- `0x18000c9b4`
- `0x180063b6c`
- `0x1800642b8`
- `0x18006445c`

## string_xrefs

- `0x180063c0e`: `FwppDeepCopyToVerIndependent_IPSEC_TOKEN_PRINCIPAL`
- `0x180063c22`: `FwppDeepCopyToVerIndependent_IPSEC_TOKEN_PRINCIPAL`
- `0x180063c39`: `FwppDeepCopyToVerIndependent_IPSEC_TOKEN_MODE`
- `0x180063c51`: `FwppDeepCopyToVerIndependent_IPSEC_TOKEN_MODE`
- `0x180063be5`: `FwppDeepCopyToVerIndependent_IPSEC_TOKEN0`
- `0x180063c60`: `FwppDeepCopyToVerIndependent_IPSEC_TOKEN0`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyToVerIndependent_IPSEC_TOKEN0(_DWORD *a1, _DWORD *a2)
{
  _DWORD *v3; // rsi
  _DWORD *v4; // rax
  __int64 v5; // rax
  __int64 v6; // rbx
  __int64 v8; // rax
  const char *v9; // rdx

  v3 = a1;
  if ( !a1 || !a2 )
  {
    v5 = WfpReportAppErrorAsNtStatus((__int64)a1, (__int64)"FwppDeepCopyToVerIndependent_IPSEC_TOKEN0", 3223453724LL);
LABEL_10:
    v6 = v5;
    if ( !v5 )
      return v6;
    goto LABEL_11;
  }
  *a2 = *a1;
  v4 = a1 + 1;
  if ( a1 == (_DWORD *)-4LL || (a1 = a2 + 1, a2 == (_DWORD *)-4LL) )
  {
    v8 = WfpReportAppErrorAsNtStatus(
           (__int64)a1,
           (__int64)"FwppDeepCopyToVerIndependent_IPSEC_TOKEN_PRINCIPAL",
           3223453724LL);
    v6 = v8;
    if ( v8 )
    {
      v9 = "FwppDeepCopyToVerIndependent_IPSEC_TOKEN_PRINCIPAL";
      goto LABEL_16;
    }
  }
  else
  {
    *a1 = *v4;
  }
  if ( v3 != (_DWORD *)-8LL )
  {
    a1 = a2 + 2;
    if ( a2 != (_DWORD *)-8LL )
    {
      *a1 = v3[2];
LABEL_9:
      v5 = FwppDeepCopyToVerIndependent_UINT64(v3 + 4, a2 + 4);
      goto LABEL_10;
    }
  }
  v8 = WfpReportAppErrorAsNtStatus((__int64)a1, (__int64)"FwppDeepCopyToVerIndependent_IPSEC_TOKEN_MODE", 3223453724LL);
  v6 = v8;
  if ( !v8 )
    goto LABEL_9;
  v9 = "FwppDeepCopyToVerIndependent_IPSEC_TOKEN_MODE";
LABEL_16:
  WfpReportError(v8, (int)v9);
LABEL_11:
  FwppDeepFreeContentsOnly_IPSEC_SA_IDLE_TIMEOUT0(a2);
  if ( v6 )
    WfpReportError(v6, (int)"FwppDeepCopyToVerIndependent_IPSEC_TOKEN0");
  return v6;
}

```

## disassembly

```asm
0x180063b6c  mov     [rsp+arg_0], rbx
0x180063b71  mov     [rsp+arg_8], rsi
0x180063b76  push    rdi
0x180063b77  sub     rsp, 30h
0x180063b7b  mov     rdi, rdx
0x180063b7e  mov     rsi, rcx
0x180063b81  test    rcx, rcx
0x180063b84  jz      loc_180063C5A
0x180063b8a  test    rdx, rdx
0x180063b8d  jz      loc_180063C5A
0x180063b93  mov     eax, [rcx]
0x180063b95  mov     [rdx], eax
0x180063b97  lea     rax, [rcx+4]
0x180063b9b  test    rax, rax
0x180063b9e  jz      short loc_180063C08
0x180063ba0  lea     rcx, [rdx+4]
0x180063ba4  test    rcx, rcx
0x180063ba7  jz      short loc_180063C08
0x180063ba9  mov     eax, [rax]
0x180063bab  mov     [rcx], eax
0x180063bad  lea     rax, [rsi+8]
0x180063bb1  test    rax, rax
0x180063bb4  jz      short loc_180063C33
0x180063bb6  lea     rcx, [rdi+8]
0x180063bba  test    rcx, rcx
0x180063bbd  jz      short loc_180063C33
0x180063bbf  mov     eax, [rax]
0x180063bc1  mov     [rcx], eax
0x180063bc3  lea     rdx, [rdi+10h]
0x180063bc7  lea     rcx, [rsi+10h]
0x180063bcb  call    FwppDeepCopyToVerIndependent_UINT64
0x180063bd0  mov     rbx, rax
0x180063bd3  test    rax, rax
0x180063bd6  jz      short loc_180063BF4
0x180063bd8  mov     rcx, rdi
0x180063bdb  call    FwppDeepFreeContentsOnly_IPSEC_SA_IDLE_TIMEOUT0
0x180063be0  test    rbx, rbx
0x180063be3  jz      short loc_180063BF4
0x180063be5  lea     rdx, aFwppdeepcopyto_22; "FwppDeepCopyToVerIndependent_IPSEC_TOKE"...
0x180063bec  mov     rcx, rbx
0x180063bef  call    WfpReportError
0x180063bf4  mov     rsi, [rsp+38h+arg_8]
0x180063bf9  mov     rax, rbx
0x180063bfc  mov     rbx, [rsp+38h+arg_0]
0x180063c01  add     rsp, 30h
0x180063c05  pop     rdi
0x180063c06  retn
0x180063c08  mov     r8d, 0C022001Ch
0x180063c0e  lea     rdx, aFwppdeepcopyto_14; "FwppDeepCopyToVerIndependent_IPSEC_TOKE"...
0x180063c15  call    WfpReportAppErrorAsNtStatus
0x180063c1a  mov     rbx, rax
0x180063c1d  test    rax, rax
0x180063c20  jz      short loc_180063BAD
0x180063c22  lea     rdx, aFwppdeepcopyto_14; "FwppDeepCopyToVerIndependent_IPSEC_TOKE"...
0x180063c29  mov     rcx, rax
0x180063c2c  call    WfpReportError
0x180063c31  jmp     short loc_180063BD8
0x180063c33  mov     r8d, 0C022001Ch
0x180063c39  lea     rdx, aFwppdeepcopyto_111; "FwppDeepCopyToVerIndependent_IPSEC_TOKE"...
0x180063c40  call    WfpReportAppErrorAsNtStatus
0x180063c45  mov     rbx, rax
0x180063c48  test    rax, rax
0x180063c4b  jz      loc_180063BC3
0x180063c51  lea     rdx, aFwppdeepcopyto_111; "FwppDeepCopyToVerIndependent_IPSEC_TOKE"...
0x180063c58  jmp     short loc_180063C29
0x180063c5a  mov     r8d, 0C022001Ch
0x180063c60  lea     rdx, aFwppdeepcopyto_22; "FwppDeepCopyToVerIndependent_IPSEC_TOKE"...
0x180063c67  call    WfpReportAppErrorAsNtStatus
0x180063c6c  jmp     loc_180063BD0
```
