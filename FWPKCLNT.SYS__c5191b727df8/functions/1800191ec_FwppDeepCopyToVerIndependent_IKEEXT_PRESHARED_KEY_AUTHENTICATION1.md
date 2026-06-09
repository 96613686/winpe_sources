# FwppDeepCopyToVerIndependent_IKEEXT_PRESHARED_KEY_AUTHENTICATION1

- ea: `0x1800191ec`
- end: `0x1800192a5`
- name: `FwppDeepCopyToVerIndependent_IKEEXT_PRESHARED_KEY_AUTHENTICATION1`
- size: `185`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180018788`
- `0x180018878`

## callees

- `0x180004904`
- `0x18000c9b4`
- `0x180018660`
- `0x1800191ec`
- `0x180064a38`

## string_xrefs

- `0x180019236`: `FwppDeepCopyToVerIndependent_IKEEXT_PSK_FLAGS`
- `0x18001924a`: `FwppDeepCopyToVerIndependent_IKEEXT_PSK_FLAGS`
- `0x180019261`: `FwppDeepCopyToVerIndependent_IKEEXT_PRESHARED_KEY_AUTHENTICATION1`
- `0x180019282`: `FwppDeepCopyToVerIndependent_IKEEXT_PRESHARED_KEY_AUTHENTICATION1`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyToVerIndependent_IKEEXT_PRESHARED_KEY_AUTHENTICATION1(__int64 a1, __int64 a2)
{
  _DWORD *v4; // rcx
  __int64 v5; // rbx
  __int64 v6; // rax

  if ( a1 && a2 )
  {
    v5 = FwppDeepCopyToVerIndependent_FWP_BYTE_BLOB(a1, a2);
    if ( !v5 )
    {
      if ( a1 != -16 )
      {
        v4 = (_DWORD *)(a2 + 16);
        if ( a2 != -16 )
        {
          *v4 = *(_DWORD *)(a1 + 16);
          return v5;
        }
      }
      v6 = WfpReportSysErrorAsNtStatus((__int64)v4, (int)"FwppDeepCopyToVerIndependent_IKEEXT_PSK_FLAGS", -1071513572);
      v5 = v6;
      if ( !v6 )
        return v5;
      WfpReportError(v6, (int)"FwppDeepCopyToVerIndependent_IKEEXT_PSK_FLAGS");
    }
  }
  else
  {
    v5 = WfpReportSysErrorAsNtStatus(
           a1,
           (int)"FwppDeepCopyToVerIndependent_IKEEXT_PRESHARED_KEY_AUTHENTICATION1",
           -1071513572);
    if ( !v5 )
      return v5;
  }
  FwppDeepFreeContentsOnly_IKEEXT_PRESHARED_KEY_AUTHENTICATION0(a2);
  if ( v5 )
    WfpReportError(v5, (int)"FwppDeepCopyToVerIndependent_IKEEXT_PRESHARED_KEY_AUTHENTICATION1");
  return v5;
}

```

## disassembly

```asm
0x1800191ec  mov     [rsp+arg_0], rbx
0x1800191f1  mov     [rsp+arg_8], rsi
0x1800191f6  push    rdi
0x1800191f7  sub     rsp, 20h
0x1800191fb  mov     rdi, rdx
0x1800191fe  mov     rsi, rcx
0x180019201  test    rcx, rcx
0x180019204  jz      short loc_18001925B
0x180019206  test    rdx, rdx
0x180019209  jz      short loc_18001925B
0x18001920b  call    FwppDeepCopyToVerIndependent_FWP_BYTE_BLOB
0x180019210  mov     rbx, rax
0x180019213  test    rax, rax
0x180019216  jnz     short loc_180019275
0x180019218  lea     rax, [rsi+10h]
0x18001921c  test    rax, rax
0x18001921f  jz      short loc_180019230
0x180019221  lea     rcx, [rdi+10h]
0x180019225  test    rcx, rcx
0x180019228  jz      short loc_180019230
0x18001922a  mov     eax, [rax]
0x18001922c  mov     [rcx], eax
0x18001922e  jmp     short loc_180019291
0x180019230  mov     r8d, 0C022001Ch
0x180019236  lea     rdx, aFwppdeepcopyto_38; "FwppDeepCopyToVerIndependent_IKEEXT_PSK"...
0x18001923d  call    WfpReportSysErrorAsNtStatus
0x180019242  mov     rbx, rax
0x180019245  test    rax, rax
0x180019248  jz      short loc_180019291
0x18001924a  lea     rdx, aFwppdeepcopyto_38; "FwppDeepCopyToVerIndependent_IKEEXT_PSK"...
0x180019251  mov     rcx, rax
0x180019254  call    WfpReportError
0x180019259  jmp     short loc_180019275
0x18001925b  mov     r8d, 0C022001Ch
0x180019261  lea     rdx, aFwppdeepcopyto_73; "FwppDeepCopyToVerIndependent_IKEEXT_PRE"...
0x180019268  call    WfpReportSysErrorAsNtStatus
0x18001926d  mov     rbx, rax
0x180019270  test    rax, rax
0x180019273  jz      short loc_180019291
0x180019275  mov     rcx, rdi
0x180019278  call    FwppDeepFreeContentsOnly_IKEEXT_PRESHARED_KEY_AUTHENTICATION0
0x18001927d  test    rbx, rbx
0x180019280  jz      short loc_180019291
0x180019282  lea     rdx, aFwppdeepcopyto_73; "FwppDeepCopyToVerIndependent_IKEEXT_PRE"...
0x180019289  mov     rcx, rbx
0x18001928c  call    WfpReportError
0x180019291  mov     rsi, [rsp+28h+arg_8]
0x180019296  mov     rax, rbx
0x180019299  mov     rbx, [rsp+28h+arg_0]
0x18001929e  add     rsp, 20h
0x1800192a2  pop     rdi
0x1800192a3  retn
```
