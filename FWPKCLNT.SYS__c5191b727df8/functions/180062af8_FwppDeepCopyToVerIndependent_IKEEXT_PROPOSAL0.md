# FwppDeepCopyToVerIndependent_IKEEXT_PROPOSAL0

- ea: `0x180062af8`
- end: `0x180062bf0`
- name: `FwppDeepCopyToVerIndependent_IKEEXT_PROPOSAL0`
- size: `248`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18005c2d0`

## callees

- `0x1800050cc`
- `0x18000c9b4`
- `0x1800624f4`
- `0x1800626d0`
- `0x180062af8`
- `0x180064264`
- `0x18006445c`

## string_xrefs

- `0x180062bb7`: `FwppDeepCopyToVerIndependent_IKEEXT_DH_GROUP`
- `0x180062bcb`: `FwppDeepCopyToVerIndependent_IKEEXT_DH_GROUP`
- `0x180062b8e`: `FwppDeepCopyToVerIndependent_IKEEXT_PROPOSAL0`
- `0x180062be2`: `FwppDeepCopyToVerIndependent_IKEEXT_PROPOSAL0`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyToVerIndependent_IKEEXT_PROPOSAL0(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  _DWORD *v5; // rcx
  __int64 v6; // rax
  __int64 v8; // rax

  if ( !a1 || !a2 )
  {
    v6 = WfpReportAppErrorAsNtStatus(a1, (__int64)"FwppDeepCopyToVerIndependent_IKEEXT_PROPOSAL0", 3223453724LL);
LABEL_10:
    v4 = v6;
    if ( !v6 )
      return v4;
    goto LABEL_11;
  }
  v4 = FwppDeepCopyToVerIndependent_IKEEXT_CIPHER_ALGORITHM0();
  if ( !v4 )
  {
    v4 = FwppDeepCopyToVerIndependent_IKEEXT_INTEGRITY_ALGORITHM0(a1 + 12, a2 + 12);
    if ( !v4 )
    {
      v4 = FwppDeepCopyToVerIndependent_UINT32(a1 + 16, a2 + 16);
      if ( !v4 )
      {
        if ( a1 != -20 )
        {
          v5 = (_DWORD *)(a2 + 20);
          if ( a2 != -20 )
          {
            *v5 = *(_DWORD *)(a1 + 20);
LABEL_9:
            v6 = FwppDeepCopyToVerIndependent_UINT32(a1 + 24, a2 + 24);
            goto LABEL_10;
          }
        }
        v8 = WfpReportAppErrorAsNtStatus(
               (__int64)v5,
               (__int64)"FwppDeepCopyToVerIndependent_IKEEXT_DH_GROUP",
               3223453724LL);
        v4 = v8;
        if ( !v8 )
          goto LABEL_9;
        WfpReportError(v8, (int)"FwppDeepCopyToVerIndependent_IKEEXT_DH_GROUP");
      }
    }
  }
LABEL_11:
  FwppDeepFreeContentsOnly_IPSEC_SA_IDLE_TIMEOUT0(a2);
  if ( v4 )
    WfpReportError(v4, (int)"FwppDeepCopyToVerIndependent_IKEEXT_PROPOSAL0");
  return v4;
}

```

## disassembly

```asm
0x180062af8  mov     [rsp+arg_0], rbx
0x180062afd  mov     [rsp+arg_8], rsi
0x180062b02  push    rdi
0x180062b03  sub     rsp, 30h
0x180062b07  mov     rdi, rdx
0x180062b0a  mov     rsi, rcx
0x180062b0d  test    rcx, rcx
0x180062b10  jz      loc_180062BDC
0x180062b16  test    rdx, rdx
0x180062b19  jz      loc_180062BDC
0x180062b1f  call    FwppDeepCopyToVerIndependent_IKEEXT_CIPHER_ALGORITHM0
0x180062b24  mov     rbx, rax
0x180062b27  test    rax, rax
0x180062b2a  jnz     short loc_180062B81
0x180062b2c  lea     rdx, [rdi+0Ch]
0x180062b30  lea     rcx, [rsi+0Ch]
0x180062b34  call    FwppDeepCopyToVerIndependent_IKEEXT_INTEGRITY_ALGORITHM0
0x180062b39  mov     rbx, rax
0x180062b3c  test    rax, rax
0x180062b3f  jnz     short loc_180062B81
0x180062b41  lea     rdx, [rdi+10h]
0x180062b45  lea     rcx, [rsi+10h]
0x180062b49  call    FwppDeepCopyToVerIndependent_UINT32
0x180062b4e  mov     rbx, rax
0x180062b51  test    rax, rax
0x180062b54  jnz     short loc_180062B81
0x180062b56  lea     rax, [rsi+14h]
0x180062b5a  test    rax, rax
0x180062b5d  jz      short loc_180062BB1
0x180062b5f  lea     rcx, [rdi+14h]
0x180062b63  test    rcx, rcx
0x180062b66  jz      short loc_180062BB1
0x180062b68  mov     eax, [rax]
0x180062b6a  mov     [rcx], eax
0x180062b6c  lea     rdx, [rdi+18h]
0x180062b70  lea     rcx, [rsi+18h]
0x180062b74  call    FwppDeepCopyToVerIndependent_UINT32
0x180062b79  mov     rbx, rax
0x180062b7c  test    rax, rax
0x180062b7f  jz      short loc_180062B9D
0x180062b81  mov     rcx, rdi
0x180062b84  call    FwppDeepFreeContentsOnly_IPSEC_SA_IDLE_TIMEOUT0
0x180062b89  test    rbx, rbx
0x180062b8c  jz      short loc_180062B9D
0x180062b8e  lea     rdx, aFwppdeepcopyto_47; "FwppDeepCopyToVerIndependent_IKEEXT_PRO"...
0x180062b95  mov     rcx, rbx
0x180062b98  call    WfpReportError
0x180062b9d  mov     rsi, [rsp+38h+arg_8]
0x180062ba2  mov     rax, rbx
0x180062ba5  mov     rbx, [rsp+38h+arg_0]
0x180062baa  add     rsp, 30h
0x180062bae  pop     rdi
0x180062baf  retn
0x180062bb1  mov     r8d, 0C022001Ch
0x180062bb7  lea     rdx, aFwppdeepcopyto_101; "FwppDeepCopyToVerIndependent_IKEEXT_DH_"...
0x180062bbe  call    WfpReportAppErrorAsNtStatus
0x180062bc3  mov     rbx, rax
0x180062bc6  test    rax, rax
0x180062bc9  jz      short loc_180062B6C
0x180062bcb  lea     rdx, aFwppdeepcopyto_101; "FwppDeepCopyToVerIndependent_IKEEXT_DH_"...
0x180062bd2  mov     rcx, rax
0x180062bd5  call    WfpReportError
0x180062bda  jmp     short loc_180062B81
0x180062bdc  mov     r8d, 0C022001Ch
0x180062be2  lea     rdx, aFwppdeepcopyto_47; "FwppDeepCopyToVerIndependent_IKEEXT_PRO"...
0x180062be9  call    WfpReportAppErrorAsNtStatus
0x180062bee  jmp     short loc_180062B79
```
