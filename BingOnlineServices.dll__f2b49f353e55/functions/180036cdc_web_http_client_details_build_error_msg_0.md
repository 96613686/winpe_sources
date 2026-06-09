# web::http::client::details::build_error_msg_0

- ea: `0x180036cdc`
- end: `0x180036e18`
- name: `web::http::client::details::build_error_msg_0`
- size: `316`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800372b0`

## callees

- `0x180004fa0`
- `0x180009698`
- `0x18000eca4`
- `0x180036bf0`
- `0x180036cdc`

## string_xrefs

- `0x180036d93`: `WinHttpReadData`
- `0x180036d74`: `WinHttpWriteData`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall web::http::client::details::build_error_msg_0(__int64 a1, __int64 a2)
{
  _BYTE v5[32]; // [rsp+30h] [rbp-30h] BYREF

  if ( *(_QWORD *)a2 == 1 )
  {
    std::string::string(v5, "WinHttpReceiveResponse");
    web::http::client::details::build_error_msg(a1, *(unsigned int *)(a2 + 8), v5);
  }
  else if ( *(_QWORD *)a2 == 2 )
  {
    std::string::string(v5, "WinHttpQueryDataAvaliable");
    web::http::client::details::build_error_msg(a1, *(unsigned int *)(a2 + 8), v5);
  }
  else if ( *(_QWORD *)a2 == 3 )
  {
    std::string::string(v5, "WinHttpReadData");
    web::http::client::details::build_error_msg(a1, *(unsigned int *)(a2 + 8), v5);
  }
  else if ( *(_QWORD *)a2 == 4 )
  {
    std::string::string(v5, "WinHttpWriteData");
    web::http::client::details::build_error_msg(a1, *(unsigned int *)(a2 + 8), v5);
  }
  else
  {
    if ( *(_QWORD *)a2 == 5 )
      std::string::string(v5, "WinHttpSendRequest");
    else
      std::string::string(v5, "Unknown WinHTTP Function");
    web::http::client::details::build_error_msg(a1, *(unsigned int *)(a2 + 8), v5);
  }
  std::string::_Tidy_deallocate(v5);
  return a1;
}

```

## disassembly

```asm
0x180036cdc  mov     [rsp-8+arg_10], rbx
0x180036ce1  mov     [rsp-8+arg_18], rdi
0x180036ce6  push    rbp
0x180036ce7  mov     rbp, rsp
0x180036cea  sub     rsp, 60h
0x180036cee  mov     rax, cs:__security_cookie
0x180036cf5  xor     rax, rsp
0x180036cf8  mov     [rbp+var_10], rax
0x180036cfc  mov     rdi, rdx
0x180036cff  mov     rbx, rcx
0x180036d02  mov     [rbp+var_38], rcx
0x180036d06  mov     rax, [rdx]
0x180036d09  sub     rax, 1
0x180036d0d  lea     rcx, [rbp+var_30]
0x180036d11  jz      loc_180036DD1
0x180036d17  sub     rax, 1
0x180036d1b  jz      loc_180036DB2
0x180036d21  sub     rax, 1
0x180036d25  jz      short loc_180036D93
0x180036d27  sub     rax, 1
0x180036d2b  jz      short loc_180036D74
0x180036d2d  cmp     rax, 1
0x180036d31  jz      short loc_180036D55
0x180036d33  lea     rdx, aUnknownWinhttp; "Unknown WinHTTP Function"
0x180036d3a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180036d3f  nop
0x180036d40  lea     r8, [rbp+var_30]
0x180036d44  mov     edx, [rdi+8]
0x180036d47  mov     rcx, rbx
0x180036d4a  call    web__http__client__details__build_error_msg
0x180036d4f  nop
0x180036d50  jmp     loc_180036DEE
0x180036d55  lea     rdx, aWinhttpsendreq; "WinHttpSendRequest"
0x180036d5c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180036d61  nop
0x180036d62  lea     r8, [rbp+var_30]
0x180036d66  mov     edx, [rdi+8]
0x180036d69  mov     rcx, rbx
0x180036d6c  call    web__http__client__details__build_error_msg
0x180036d71  nop
0x180036d72  jmp     short loc_180036DEE
0x180036d74  lea     rdx, aWinhttpwriteda; "WinHttpWriteData"
0x180036d7b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180036d80  nop
0x180036d81  lea     r8, [rbp+var_30]
0x180036d85  mov     edx, [rdi+8]
0x180036d88  mov     rcx, rbx
0x180036d8b  call    web__http__client__details__build_error_msg
0x180036d90  nop
0x180036d91  jmp     short loc_180036DEE
0x180036d93  lea     rdx, aWinhttpreaddat; "WinHttpReadData"
0x180036d9a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180036d9f  nop
0x180036da0  lea     r8, [rbp+var_30]
0x180036da4  mov     edx, [rdi+8]
0x180036da7  mov     rcx, rbx
0x180036daa  call    web__http__client__details__build_error_msg
0x180036daf  nop
0x180036db0  jmp     short loc_180036DEE
0x180036db2  lea     rdx, aWinhttpqueryda; "WinHttpQueryDataAvaliable"
0x180036db9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180036dbe  nop
0x180036dbf  lea     r8, [rbp+var_30]
0x180036dc3  mov     edx, [rdi+8]
0x180036dc6  mov     rcx, rbx
0x180036dc9  call    web__http__client__details__build_error_msg
0x180036dce  nop
0x180036dcf  jmp     short loc_180036DEE
0x180036dd1  lea     rdx, aWinhttpreceive; "WinHttpReceiveResponse"
0x180036dd8  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180036ddd  nop
0x180036dde  lea     r8, [rbp+var_30]
0x180036de2  mov     edx, [rdi+8]
0x180036de5  mov     rcx, rbx
0x180036de8  call    web__http__client__details__build_error_msg
0x180036ded  nop
0x180036dee  lea     rcx, [rbp+var_30]
0x180036df2  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180036df7  mov     rax, rbx
0x180036dfa  mov     rcx, [rbp+var_10]
0x180036dfe  xor     rcx, rsp; StackCookie
0x180036e01  call    __security_check_cookie
0x180036e06  lea     r11, [rsp+60h+var_s0]
0x180036e0b  mov     rbx, [r11+20h]
0x180036e0f  mov     rdi, [r11+28h]
0x180036e13  mov     rsp, r11
0x180036e16  pop     rbp
0x180036e17  retn
```
