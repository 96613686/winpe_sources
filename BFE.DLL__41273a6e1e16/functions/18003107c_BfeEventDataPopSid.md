# BfeEventDataPopSid

- ea: `0x18003107c`
- end: `0x18003120a`
- name: `BfeEventDataPopSid`
- size: `398`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800309e4`

## callees

- `0x18000fb34`
- `0x180011510`
- `0x1800135ac`
- `0x1800197d0`
- `0x18003107c`
- `0x18005aa60`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x1800310be`
- `ntdll!RtlLengthSid` at `0x1800310be`
- `ntdll!RtlValidSid` at `0x1800310a7`
- `ntdll!RtlValidSid` at `0x1800310a7`

## string_xrefs

- `0x1800311e2`: `BfeEventDataPopSid`
- `0x1800311f6`: `BfeEventDataPopSid`

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
          if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
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
0x18003107c  mov     [rsp+arg_10], rbx
0x180031081  mov     [rsp+arg_18], rsi
0x180031086  push    rdi
0x180031087  sub     rsp, 70h
0x18003108b  mov     rax, cs:__security_cookie
0x180031092  xor     rax, rsp
0x180031095  mov     [rsp+78h+var_10], rax
0x18003109a  mov     rbx, [rcx+8]
0x18003109e  mov     rdi, rcx
0x1800310a1  mov     rcx, rbx; Sid
0x1800310a4  mov     rsi, rdx
0x1800310a7  call    cs:__imp_RtlValidSid
0x1800310ae  nop     dword ptr [rax+rax+00h]
0x1800310b3  test    al, al
0x1800310b5  jz      loc_1800311DC
0x1800310bb  mov     rcx, rbx; Sid
0x1800310be  call    cs:__imp_RtlLengthSid
0x1800310c5  nop     dword ptr [rax+rax+00h]
0x1800310ca  xor     ebx, ebx
0x1800310cc  test    eax, eax
0x1800310ce  jz      short loc_18003111A
0x1800310d0  mov     rdx, [rdi+8]
0x1800310d4  mov     eax, eax
0x1800310d6  lea     rcx, [rdx+7]
0x1800310da  add     rcx, rax
0x1800310dd  and     rcx, 0FFFFFFFFFFFFFFF8h
0x1800310e1  cmp     rcx, [rdi+10h]
0x1800310e5  ja      short loc_18003111F
0x1800310e7  mov     [rsi], rdx
0x1800310ea  mov     [rdi+8], rcx
0x1800310ee  test    rbx, rbx
0x1800310f1  jnz     loc_1800311F6
0x1800310f7  mov     rax, rbx
0x1800310fa  mov     rcx, [rsp+78h+var_10]
0x1800310ff  xor     rcx, rsp; StackCookie
0x180031102  call    __security_check_cookie
0x180031107  lea     r11, [rsp+78h+var_8]
0x18003110c  mov     rbx, [r11+20h]
0x180031110  mov     rsi, [r11+28h]
0x180031114  mov     rsp, r11
0x180031117  pop     rdi
0x180031118  retn
0x18003111a  mov     [rsi], rbx
0x18003111d  jmp     short loc_1800310EE
0x18003111f  lea     rdi, aBfeeventdatapo_4; "BfeEventDataPop"
0x180031126  mov     r8d, 0C000000Dh
0x18003112c  mov     rdx, rdi
0x18003112f  call    WfpReportSysErrorAsNtStatus
0x180031134  mov     rbx, rax
0x180031137  test    rax, rax
0x18003113a  jz      short loc_1800310EE
0x18003113c  mov     rcx, cs:WPP_GLOBAL_Control
0x180031143  lea     rax, WPP_GLOBAL_Control
0x18003114a  cmp     rcx, rax
0x18003114d  jz      short loc_180031175
0x18003114f  cmp     byte ptr [rcx+19h], 2
0x180031153  jb      short loc_180031175
0x180031155  test    byte ptr [rcx+1Ch], 1
0x180031159  jz      short loc_180031175
0x18003115b  mov     rcx, [rcx+10h]
0x18003115f  mov     edx, 1Ah
0x180031164  mov     [rsp+78h+var_50], ebx
0x180031168  xor     r9d, r9d
0x18003116b  mov     [rsp+78h+var_58], rdi
0x180031170  call    WPP_SF_Ssd
0x180031175  cmp     cs:gWfpLogUserModeErrors, 0
0x18003117c  jz      loc_1800310EE
0x180031182  test    cs:byte_1800F6115, 1
0x180031189  jz      loc_1800310EE
0x18003118f  lea     rax, [rsp+78h+var_48]
0x180031194  mov     [rsp+78h+var_48], ebx
0x180031198  mov     [rsp+78h+var_20], rax
0x18003119d  lea     rdx, WFP_USERMODE_ERROR
0x1800311a4  lea     rax, [rsp+78h+var_40]
0x1800311a9  mov     [rsp+78h+var_30], rdi
0x1800311ae  mov     r9d, 3
0x1800311b4  mov     [rsp+78h+var_58], rax
0x1800311b9  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x1800311c0  mov     [rsp+78h+var_28], 10h
0x1800311c9  mov     [rsp+78h+var_18], 4
0x1800311d2  call    McGenEventWrite_EtwEventWriteTransfer
0x1800311d7  jmp     loc_1800310EE
0x1800311dc  mov     r8d, 0C0000078h
0x1800311e2  lea     rdx, aBfeeventdatapo_2; "BfeEventDataPopSid"
0x1800311e9  call    WfpReportSysErrorAsNtStatus
0x1800311ee  mov     rbx, rax
0x1800311f1  jmp     loc_1800310EE
0x1800311f6  lea     rdx, aBfeeventdatapo_2; "BfeEventDataPopSid"
0x1800311fd  mov     rcx, rbx
0x180031200  call    WfpReportError
0x180031205  jmp     loc_1800310F7
```
