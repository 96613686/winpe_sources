# BfeEventDataPopSid

- ea: `0x18002f59c`
- end: `0x18002f71d`
- name: `BfeEventDataPopSid`
- size: `385`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002ef04`

## callees

- `0x18000f1a8`
- `0x180010ad0`
- `0x180012b54`
- `0x180018b74`
- `0x18002f59c`
- `0x180058b30`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18002f5d8`
- `ntdll!RtlLengthSid` at `0x18002f5d8`
- `ntdll!RtlValidSid` at `0x18002f5c7`
- `ntdll!RtlValidSid` at `0x18002f5c7`

## string_xrefs

- `0x18002f6f5`: `BfeEventDataPopSid`
- `0x18002f709`: `BfeEventDataPopSid`

## pseudocode

```c
__int64 __fastcall BfeEventDataPopSid(__int64 a1, _QWORD *a2)
{
  void *v2; // rbx
  __int64 v5; // rcx
  ULONG v6; // eax
  __int64 v7; // rbx
  __int64 v8; // rdx
  unsigned __int64 v9; // rcx
  int v11; // r8d
  int v12; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v13[16]; // [rsp+38h] [rbp-40h] BYREF
  const char *v14; // [rsp+48h] [rbp-30h]
  __int64 v15; // [rsp+50h] [rbp-28h]
  int *v16; // [rsp+58h] [rbp-20h]
  __int64 v17; // [rsp+60h] [rbp-18h]

  v2 = *(void **)(a1 + 8);
  if ( RtlValidSid(v2) )
  {
    v6 = RtlLengthSid(v2);
    v7 = 0;
    if ( v6 )
    {
      v8 = *(_QWORD *)(a1 + 8);
      v9 = (v6 + v8 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
      if ( v9 > *(_QWORD *)(a1 + 16) )
      {
        v7 = WfpReportSysErrorAsNtStatus(v9, "BfeEventDataPop", 3221225485LL);
        if ( v7 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v11, 0, (__int64)"BfeEventDataPop", v7);
          }
          if ( gWfpLogUserModeErrors && (byte_1800F30F5 & 1) != 0 )
          {
            v12 = v7;
            v16 = &v12;
            v14 = "BfeEventDataPop";
            v15 = 16;
            v17 = 4;
            McGenEventWrite_EtwEventWriteTransfer(
              (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
              (unsigned int)WFP_USERMODE_ERROR,
              v11,
              3,
              (__int64)v13);
          }
        }
      }
      else
      {
        *a2 = v8;
        *(_QWORD *)(a1 + 8) = v9;
      }
    }
    else
    {
      *a2 = 0;
    }
  }
  else
  {
    v7 = WfpReportSysErrorAsNtStatus(v5, "BfeEventDataPopSid", 3221225592LL);
  }
  if ( v7 )
    WfpReportError(v7, "BfeEventDataPopSid");
  return v7;
}

```

## disassembly

```asm
0x18002f59c  mov     [rsp+arg_10], rbx
0x18002f5a1  mov     [rsp+arg_18], rsi
0x18002f5a6  push    rdi
0x18002f5a7  sub     rsp, 70h
0x18002f5ab  mov     rax, cs:__security_cookie
0x18002f5b2  xor     rax, rsp
0x18002f5b5  mov     [rsp+78h+var_10], rax
0x18002f5ba  mov     rbx, [rcx+8]
0x18002f5be  mov     rdi, rcx
0x18002f5c1  mov     rcx, rbx; Sid
0x18002f5c4  mov     rsi, rdx
0x18002f5c7  call    cs:__imp_RtlValidSid
0x18002f5cd  test    al, al
0x18002f5cf  jz      loc_18002F6EF
0x18002f5d5  mov     rcx, rbx; Sid
0x18002f5d8  call    cs:__imp_RtlLengthSid
0x18002f5de  xor     ebx, ebx
0x18002f5e0  test    eax, eax
0x18002f5e2  jz      short loc_18002F62D
0x18002f5e4  mov     rdx, [rdi+8]
0x18002f5e8  mov     eax, eax
0x18002f5ea  lea     rcx, [rdx+7]
0x18002f5ee  add     rcx, rax
0x18002f5f1  and     rcx, 0FFFFFFFFFFFFFFF8h
0x18002f5f5  cmp     rcx, [rdi+10h]
0x18002f5f9  ja      short loc_18002F632
0x18002f5fb  mov     [rsi], rdx
0x18002f5fe  mov     [rdi+8], rcx
0x18002f602  test    rbx, rbx
0x18002f605  jnz     loc_18002F709
0x18002f60b  mov     rax, rbx
0x18002f60e  mov     rcx, [rsp+78h+var_10]
0x18002f613  xor     rcx, rsp; StackCookie
0x18002f616  call    __security_check_cookie
0x18002f61b  lea     r11, [rsp+78h+var_8]
0x18002f620  mov     rbx, [r11+20h]
0x18002f624  mov     rsi, [r11+28h]
0x18002f628  mov     rsp, r11
0x18002f62b  pop     rdi
0x18002f62c  retn
0x18002f62d  mov     [rsi], rbx
0x18002f630  jmp     short loc_18002F602
0x18002f632  lea     rdi, aBfeeventdatapo_4; "BfeEventDataPop"
0x18002f639  mov     r8d, 0C000000Dh
0x18002f63f  mov     rdx, rdi
0x18002f642  call    WfpReportSysErrorAsNtStatus
0x18002f647  mov     rbx, rax
0x18002f64a  test    rax, rax
0x18002f64d  jz      short loc_18002F602
0x18002f64f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f656  lea     rax, WPP_GLOBAL_Control
0x18002f65d  cmp     rcx, rax
0x18002f660  jz      short loc_18002F688
0x18002f662  cmp     byte ptr [rcx+19h], 2
0x18002f666  jb      short loc_18002F688
0x18002f668  test    byte ptr [rcx+1Ch], 1
0x18002f66c  jz      short loc_18002F688
0x18002f66e  mov     rcx, [rcx+10h]
0x18002f672  mov     edx, 1Ah
0x18002f677  mov     [rsp+78h+var_50], ebx
0x18002f67b  xor     r9d, r9d
0x18002f67e  mov     [rsp+78h+var_58], rdi
0x18002f683  call    WPP_SF_Ssd
0x18002f688  cmp     cs:gWfpLogUserModeErrors, 0
0x18002f68f  jz      loc_18002F602
0x18002f695  test    cs:byte_1800F30F5, 1
0x18002f69c  jz      loc_18002F602
0x18002f6a2  lea     rax, [rsp+78h+var_48]
0x18002f6a7  mov     [rsp+78h+var_48], ebx
0x18002f6ab  mov     [rsp+78h+var_20], rax
0x18002f6b0  lea     rdx, WFP_USERMODE_ERROR
0x18002f6b7  lea     rax, [rsp+78h+var_40]
0x18002f6bc  mov     [rsp+78h+var_30], rdi
0x18002f6c1  mov     r9d, 3
0x18002f6c7  mov     [rsp+78h+var_58], rax
0x18002f6cc  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x18002f6d3  mov     [rsp+78h+var_28], 10h
0x18002f6dc  mov     [rsp+78h+var_18], 4
0x18002f6e5  call    McGenEventWrite_EtwEventWriteTransfer
0x18002f6ea  jmp     loc_18002F602
0x18002f6ef  mov     r8d, 0C0000078h
0x18002f6f5  lea     rdx, aBfeeventdatapo_2; "BfeEventDataPopSid"
0x18002f6fc  call    WfpReportSysErrorAsNtStatus
0x18002f701  mov     rbx, rax
0x18002f704  jmp     loc_18002F602
0x18002f709  lea     rdx, aBfeeventdatapo_2; "BfeEventDataPopSid"
0x18002f710  mov     rcx, rbx
0x18002f713  call    WfpReportError
0x18002f718  jmp     loc_18002F60B
```
