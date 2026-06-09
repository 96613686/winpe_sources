# FwppDeepCopyFromVerIndependent_IKEEXT_PRESHARED_KEY_AUTHENTICATION1

- ea: `0x180016f40`
- end: `0x180016ff9`
- name: `FwppDeepCopyFromVerIndependent_IKEEXT_PRESHARED_KEY_AUTHENTICATION1`
- size: `185`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800124f8`
- `0x1800162a4`
- `0x180016394`

## callees

- `0x180004904`
- `0x18000c9b4`
- `0x180016f40`
- `0x180018660`
- `0x180064a38`

## string_xrefs

- `0x180016f8a`: `FwppDeepCopyFromVerIndependent_IKEEXT_PSK_FLAGS`
- `0x180016f9e`: `FwppDeepCopyFromVerIndependent_IKEEXT_PSK_FLAGS`
- `0x180016fb5`: `FwppDeepCopyFromVerIndependent_IKEEXT_PRESHARED_KEY_AUTHENTICATION1`
- `0x180016fd6`: `FwppDeepCopyFromVerIndependent_IKEEXT_PRESHARED_KEY_AUTHENTICATION1`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyFromVerIndependent_IKEEXT_PRESHARED_KEY_AUTHENTICATION1(__int64 a1, __int64 a2)
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
      v6 = WfpReportSysErrorAsNtStatus((__int64)v4, (int)"FwppDeepCopyFromVerIndependent_IKEEXT_PSK_FLAGS", -1071513572);
      v5 = v6;
      if ( !v6 )
        return v5;
      WfpReportError(v6, (int)"FwppDeepCopyFromVerIndependent_IKEEXT_PSK_FLAGS");
    }
  }
  else
  {
    v5 = WfpReportSysErrorAsNtStatus(
           a1,
           (int)"FwppDeepCopyFromVerIndependent_IKEEXT_PRESHARED_KEY_AUTHENTICATION1",
           -1071513572);
    if ( !v5 )
      return v5;
  }
  FwppDeepFreeContentsOnly_IKEEXT_PRESHARED_KEY_AUTHENTICATION0(a2);
  if ( v5 )
    WfpReportError(v5, (int)"FwppDeepCopyFromVerIndependent_IKEEXT_PRESHARED_KEY_AUTHENTICATION1");
  return v5;
}

```

## disassembly

```asm
0x180016f40  mov     [rsp+arg_0], rbx
0x180016f45  mov     [rsp+arg_8], rsi
0x180016f4a  push    rdi
0x180016f4b  sub     rsp, 20h
0x180016f4f  mov     rdi, rdx
0x180016f52  mov     rsi, rcx
0x180016f55  test    rcx, rcx
0x180016f58  jz      short loc_180016FAF
0x180016f5a  test    rdx, rdx
0x180016f5d  jz      short loc_180016FAF
0x180016f5f  call    FwppDeepCopyToVerIndependent_FWP_BYTE_BLOB
0x180016f64  mov     rbx, rax
0x180016f67  test    rax, rax
0x180016f6a  jnz     short loc_180016FC9
0x180016f6c  lea     rax, [rsi+10h]
0x180016f70  test    rax, rax
0x180016f73  jz      short loc_180016F84
0x180016f75  lea     rcx, [rdi+10h]
0x180016f79  test    rcx, rcx
0x180016f7c  jz      short loc_180016F84
0x180016f7e  mov     eax, [rax]
0x180016f80  mov     [rcx], eax
0x180016f82  jmp     short loc_180016FE5
0x180016f84  mov     r8d, 0C022001Ch
0x180016f8a  lea     rdx, aFwppdeepcopyfr_114; "FwppDeepCopyFromVerIndependent_IKEEXT_P"...
0x180016f91  call    WfpReportSysErrorAsNtStatus
0x180016f96  mov     rbx, rax
0x180016f99  test    rax, rax
0x180016f9c  jz      short loc_180016FE5
0x180016f9e  lea     rdx, aFwppdeepcopyfr_114; "FwppDeepCopyFromVerIndependent_IKEEXT_P"...
0x180016fa5  mov     rcx, rax
0x180016fa8  call    WfpReportError
0x180016fad  jmp     short loc_180016FC9
0x180016faf  mov     r8d, 0C022001Ch
0x180016fb5  lea     rdx, aFwppdeepcopyfr_67; "FwppDeepCopyFromVerIndependent_IKEEXT_P"...
0x180016fbc  call    WfpReportSysErrorAsNtStatus
0x180016fc1  mov     rbx, rax
0x180016fc4  test    rax, rax
0x180016fc7  jz      short loc_180016FE5
0x180016fc9  mov     rcx, rdi
0x180016fcc  call    FwppDeepFreeContentsOnly_IKEEXT_PRESHARED_KEY_AUTHENTICATION0
0x180016fd1  test    rbx, rbx
0x180016fd4  jz      short loc_180016FE5
0x180016fd6  lea     rdx, aFwppdeepcopyfr_67; "FwppDeepCopyFromVerIndependent_IKEEXT_P"...
0x180016fdd  mov     rcx, rbx
0x180016fe0  call    WfpReportError
0x180016fe5  mov     rsi, [rsp+28h+arg_8]
0x180016fea  mov     rax, rbx
0x180016fed  mov     rbx, [rsp+28h+arg_0]
0x180016ff2  add     rsp, 20h
0x180016ff6  pop     rdi
0x180016ff7  retn
```
