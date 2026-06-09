# FwppDeepCopyFromVerIndependent_IPSEC_TOKEN0

- ea: `0x180060bcc`
- end: `0x180060cd1`
- name: `FwppDeepCopyFromVerIndependent_IPSEC_TOKEN0`
- size: `261`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18005bc84`

## callees

- `0x1800050cc`
- `0x18000c9b4`
- `0x180060bcc`
- `0x180061318`
- `0x18006445c`

## string_xrefs

- `0x180060c6e`: `FwppDeepCopyFromVerIndependent_IPSEC_TOKEN_PRINCIPAL`
- `0x180060c82`: `FwppDeepCopyFromVerIndependent_IPSEC_TOKEN_PRINCIPAL`
- `0x180060c99`: `FwppDeepCopyFromVerIndependent_IPSEC_TOKEN_MODE`
- `0x180060cb1`: `FwppDeepCopyFromVerIndependent_IPSEC_TOKEN_MODE`
- `0x180060c45`: `FwppDeepCopyFromVerIndependent_IPSEC_TOKEN0`
- `0x180060cc0`: `FwppDeepCopyFromVerIndependent_IPSEC_TOKEN0`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyFromVerIndependent_IPSEC_TOKEN0(_DWORD *a1, _DWORD *a2)
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
    v5 = WfpReportAppErrorAsNtStatus((__int64)a1, (__int64)"FwppDeepCopyFromVerIndependent_IPSEC_TOKEN0", 3223453724LL);
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
           (__int64)"FwppDeepCopyFromVerIndependent_IPSEC_TOKEN_PRINCIPAL",
           3223453724LL);
    v6 = v8;
    if ( v8 )
    {
      v9 = "FwppDeepCopyFromVerIndependent_IPSEC_TOKEN_PRINCIPAL";
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
      v5 = FwppDeepCopyFromVerIndependent_UINT64(v3 + 4, a2 + 4);
      goto LABEL_10;
    }
  }
  v8 = WfpReportAppErrorAsNtStatus(
         (__int64)a1,
         (__int64)"FwppDeepCopyFromVerIndependent_IPSEC_TOKEN_MODE",
         3223453724LL);
  v6 = v8;
  if ( !v8 )
    goto LABEL_9;
  v9 = "FwppDeepCopyFromVerIndependent_IPSEC_TOKEN_MODE";
LABEL_16:
  WfpReportError(v8, (int)v9);
LABEL_11:
  FwppDeepFreeContentsOnly_IPSEC_SA_IDLE_TIMEOUT0(a2);
  if ( v6 )
    WfpReportError(v6, (int)"FwppDeepCopyFromVerIndependent_IPSEC_TOKEN0");
  return v6;
}

```

## disassembly

```asm
0x180060bcc  mov     [rsp+arg_0], rbx
0x180060bd1  mov     [rsp+arg_8], rsi
0x180060bd6  push    rdi
0x180060bd7  sub     rsp, 30h
0x180060bdb  mov     rdi, rdx
0x180060bde  mov     rsi, rcx
0x180060be1  test    rcx, rcx
0x180060be4  jz      loc_180060CBA
0x180060bea  test    rdx, rdx
0x180060bed  jz      loc_180060CBA
0x180060bf3  mov     eax, [rcx]
0x180060bf5  mov     [rdx], eax
0x180060bf7  lea     rax, [rcx+4]
0x180060bfb  test    rax, rax
0x180060bfe  jz      short loc_180060C68
0x180060c00  lea     rcx, [rdx+4]
0x180060c04  test    rcx, rcx
0x180060c07  jz      short loc_180060C68
0x180060c09  mov     eax, [rax]
0x180060c0b  mov     [rcx], eax
0x180060c0d  lea     rax, [rsi+8]
0x180060c11  test    rax, rax
0x180060c14  jz      short loc_180060C93
0x180060c16  lea     rcx, [rdi+8]
0x180060c1a  test    rcx, rcx
0x180060c1d  jz      short loc_180060C93
0x180060c1f  mov     eax, [rax]
0x180060c21  mov     [rcx], eax
0x180060c23  lea     rdx, [rdi+10h]
0x180060c27  lea     rcx, [rsi+10h]
0x180060c2b  call    FwppDeepCopyFromVerIndependent_UINT64
0x180060c30  mov     rbx, rax
0x180060c33  test    rax, rax
0x180060c36  jz      short loc_180060C54
0x180060c38  mov     rcx, rdi
0x180060c3b  call    FwppDeepFreeContentsOnly_IPSEC_SA_IDLE_TIMEOUT0
0x180060c40  test    rbx, rbx
0x180060c43  jz      short loc_180060C54
0x180060c45  lea     rdx, aFwppdeepcopyfr_40; "FwppDeepCopyFromVerIndependent_IPSEC_TO"...
0x180060c4c  mov     rcx, rbx
0x180060c4f  call    WfpReportError
0x180060c54  mov     rsi, [rsp+38h+arg_8]
0x180060c59  mov     rax, rbx
0x180060c5c  mov     rbx, [rsp+38h+arg_0]
0x180060c61  add     rsp, 30h
0x180060c65  pop     rdi
0x180060c66  retn
0x180060c68  mov     r8d, 0C022001Ch
0x180060c6e  lea     rdx, aFwppdeepcopyfr_32; "FwppDeepCopyFromVerIndependent_IPSEC_TO"...
0x180060c75  call    WfpReportAppErrorAsNtStatus
0x180060c7a  mov     rbx, rax
0x180060c7d  test    rax, rax
0x180060c80  jz      short loc_180060C0D
0x180060c82  lea     rdx, aFwppdeepcopyfr_32; "FwppDeepCopyFromVerIndependent_IPSEC_TO"...
0x180060c89  mov     rcx, rax
0x180060c8c  call    WfpReportError
0x180060c91  jmp     short loc_180060C38
0x180060c93  mov     r8d, 0C022001Ch
0x180060c99  lea     rdx, aFwppdeepcopyfr_102; "FwppDeepCopyFromVerIndependent_IPSEC_TO"...
0x180060ca0  call    WfpReportAppErrorAsNtStatus
0x180060ca5  mov     rbx, rax
0x180060ca8  test    rax, rax
0x180060cab  jz      loc_180060C23
0x180060cb1  lea     rdx, aFwppdeepcopyfr_102; "FwppDeepCopyFromVerIndependent_IPSEC_TO"...
0x180060cb8  jmp     short loc_180060C89
0x180060cba  mov     r8d, 0C022001Ch
0x180060cc0  lea     rdx, aFwppdeepcopyfr_40; "FwppDeepCopyFromVerIndependent_IPSEC_TO"...
0x180060cc7  call    WfpReportAppErrorAsNtStatus
0x180060ccc  jmp     loc_180060C30
```
