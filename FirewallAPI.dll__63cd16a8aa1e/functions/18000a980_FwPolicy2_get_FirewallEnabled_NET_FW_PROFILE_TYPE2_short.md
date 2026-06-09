# FwPolicy2::get_FirewallEnabled(NET_FW_PROFILE_TYPE2_,short *)

- ea: `0x18000a980`
- end: `0x18000acce`
- name: `?get_FirewallEnabled@FwPolicy2@@UEAAJW4NET_FW_PROFILE_TYPE2_@@PEAF@Z`
- size: `846`
- prototype: `__int64 __fastcall(FwPolicy2 *__hidden this, enum NET_FW_PROFILE_TYPE2_, __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callees

- `0x180005954`
- `0x180008b30`
- `0x18000a980`
- `0x18000c560`
- `0x1800277b0`
- `0x18003104c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000ab3e`
- `ntdll!EtwEventWrite` at `0x18000abc4`
- `ntdll!EtwEventWrite` at `0x18000ab3e`
- `ntdll!EtwEventWrite` at `0x18000abc4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000ab61`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000ab61`
- `fwbase!FwReportReturnError` at `0x18000aac6`
- `fwbase!FwReportReturnError` at `0x18000aad5`
- `fwbase!FwReportReturnError` at `0x18000aaeb`
- `fwbase!FwReportReturnError` at `0x18000aafa`
- `fwbase!FwReportReturnError` at `0x18000aac6`
- `fwbase!FwReportReturnError` at `0x18000aad5`
- `fwbase!FwReportReturnError` at `0x18000aaeb`
- `fwbase!FwReportReturnError` at `0x18000aafa`

## pseudocode

```c
__int64 __fastcall FwPolicy2::get_FirewallEnabled(FwPolicy2 *this, enum NET_FW_PROFILE_TYPE2_ a2, __int16 *a3)
{
  FwPolicy2 *v6; // rcx
  unsigned int v7; // ebx
  __int64 *v8; // rdi
  __int64 v9; // rbp
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  int v13; // eax
  unsigned int v14; // edi
  unsigned int v15; // eax
  int v16; // edi
  __int16 v17; // ax
  _DWORD v19[2]; // [rsp+40h] [rbp-48h] BYREF
  int v20; // [rsp+48h] [rbp-40h] BYREF

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_651265e8da5238d82b2cc9a323e5c212_Traceguids);
      v6 = WPP_GLOBAL_Control;
    }
    if ( v6 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)v6 + 2), 38, WPP_651265e8da5238d82b2cc9a323e5c212_Traceguids);
      v6 = WPP_GLOBAL_Control;
    }
  }
  v19[0] = 0;
  v20 = 4;
  if ( (unsigned int)(a2 - 1) > 3 )
  {
    v7 = -2147024809;
  }
  else
  {
    if ( a3 )
    {
      if ( v6 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
      {
        WPP_SF_(*((_QWORD *)v6 + 2), 40, WPP_651265e8da5238d82b2cc9a323e5c212_Traceguids);
        v6 = WPP_GLOBAL_Control;
      }
      v7 = 0;
      v8 = (__int64 *)((char *)this + 32);
      if ( !*v8 )
      {
        v10 = FWOpenPolicyStore(0x221u, 0, 2u, 2u, 0, v8);
        v7 = v10;
        if ( v10 > 0 )
          v7 = (unsigned __int16)v10 | 0x80070000;
        if ( v7 == -2147024891 )
        {
          v11 = FWOpenPolicyStore(0x221u, 0, 2u, 1u, 0, v8);
          v7 = v11;
          if ( v11 > 0 )
            v7 = (unsigned __int16)v11 | 0x80070000;
        }
        if ( (v7 & 0x80000000) != 0 )
        {
          FwReportReturnError("FwPolicy2::GetPolicyStoreHandle", v7);
          v13 = FwReportReturnError("FwPolicy2::GetPolicyStoreHandle", v7);
          v9 = 0;
          v7 = v13;
          if ( v13 < 0 )
          {
            v12 = (unsigned int)v13;
            goto LABEL_24;
          }
          v6 = WPP_GLOBAL_Control;
          goto LABEL_27;
        }
        v6 = WPP_GLOBAL_Control;
      }
      v9 = *v8;
LABEL_27:
      if ( a2 == NET_FW_PROFILE2_DOMAIN )
      {
        v14 = 1;
      }
      else if ( a2 == NET_FW_PROFILE2_PRIVATE )
      {
        v14 = 2;
      }
      else
      {
        v14 = 0;
        if ( a2 == NET_FW_PROFILE2_PUBLIC )
          v14 = 4;
      }
      v19[1] = 0;
      if ( g_Provider )
      {
        EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_GetConfig, 0, 0);
        v6 = WPP_GLOBAL_Control;
      }
      if ( v6 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)v6 + 2), 106, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
      GetTickCount64();
      v15 = Int_FWGetOrSetConfig(1u, v9, 1u, v14, 0, (__int64)v19, &v20);
      v16 = v15;
      if ( v15
        && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v15);
      }
      if ( g_Provider )
        EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_GetConfig, 0, 0);
      if ( v16 == 2 )
        goto LABEL_42;
      if ( v16 > 0 )
        v7 = (unsigned __int16)v16 | 0x80070000;
      else
        v7 = v16;
      if ( (v7 & 0x80000000) == 0 )
      {
        if ( !v19[0] )
        {
          v17 = 0;
          goto LABEL_43;
        }
LABEL_42:
        v17 = -1;
LABEL_43:
        *a3 = v17;
        return v7;
      }
      goto LABEL_22;
    }
    v7 = -2147467261;
  }
LABEL_22:
  v12 = v7;
LABEL_24:
  FwReportReturnError("FwPolicy2::GetBool", v12);
  return (unsigned int)FwReportReturnError("FwPolicy2::GetBool", v7);
}

```

## disassembly

```asm
0x18000a980  mov     [rsp+arg_8], rbx
0x18000a985  push    rbp
0x18000a986  push    rsi
0x18000a987  push    rdi
0x18000a988  push    r12
0x18000a98a  push    r14
0x18000a98c  sub     rsp, 60h
0x18000a990  mov     rax, cs:__security_cookie
0x18000a997  xor     rax, rsp
0x18000a99a  mov     [rsp+88h+var_38], rax
0x18000a99f  mov     r14, r8
0x18000a9a2  mov     esi, edx
0x18000a9a4  mov     rdi, rcx
0x18000a9a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a9ae  lea     rbp, WPP_GLOBAL_Control
0x18000a9b5  lea     rbx, WPP_651265e8da5238d82b2cc9a323e5c212_Traceguids
0x18000a9bc  mov     r12b, 8
0x18000a9bf  cmp     rcx, rbp
0x18000a9c2  jnz     short loc_18000AA0F
0x18000a9c4  lea     eax, [rsi-1]
0x18000a9c7  mov     [rsp+88h+var_48], 0
0x18000a9cf  mov     [rsp+88h+var_40], 4
0x18000a9d7  cmp     eax, 3
0x18000a9da  ja      loc_18000AAB4
0x18000a9e0  test    r14, r14
0x18000a9e3  jz      loc_18000AC8D
0x18000a9e9  cmp     rcx, rbp
0x18000a9ec  jz      short loc_18000A9F8
0x18000a9ee  test    [rcx+1Ch], r12b
0x18000a9f2  jnz     loc_18000AC97
0x18000a9f8  xor     ebx, ebx
0x18000a9fa  add     rdi, 20h ; ' '
0x18000a9fe  lea     r12d, [rbx+2]
0x18000aa02  cmp     [rdi], rbx
0x18000aa05  jz      short loc_18000AA3E
0x18000aa07  mov     rbp, [rdi]
0x18000aa0a  jmp     loc_18000AB0F
0x18000aa0f  test    [rcx+1Ch], r12b
0x18000aa13  jnz     loc_18000AC70
0x18000aa19  cmp     rcx, rbp
0x18000aa1c  jz      short loc_18000A9C4
0x18000aa1e  test    [rcx+1Ch], r12b
0x18000aa22  jz      short loc_18000A9C4
0x18000aa24  mov     rcx, [rcx+10h]
0x18000aa28  mov     edx, 26h ; '&'
0x18000aa2d  mov     r8, rbx
0x18000aa30  call    WPP_SF_
0x18000aa35  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa3c  jmp     short loc_18000A9C4
0x18000aa3e  mov     ebp, 221h
0x18000aa43  mov     [rsp+88h+var_60], rdi
0x18000aa48  mov     ecx, ebp
0x18000aa4a  mov     [rsp+88h+var_68], ebx
0x18000aa4e  mov     r9d, r12d
0x18000aa51  mov     r8d, r12d
0x18000aa54  xor     edx, edx
0x18000aa56  call    FWOpenPolicyStore
0x18000aa5b  mov     ebx, eax
0x18000aa5d  test    eax, eax
0x18000aa5f  jg      short loc_18000AA9E
0x18000aa61  cmp     ebx, 80070005h
0x18000aa67  jnz     short loc_18000AA8E
0x18000aa69  mov     ecx, ebp
0x18000aa6b  mov     [rsp+88h+var_60], rdi
0x18000aa70  mov     r9d, 1
0x18000aa76  mov     [rsp+88h+var_68], 0
0x18000aa7e  mov     r8d, r12d
0x18000aa81  xor     edx, edx
0x18000aa83  call    FWOpenPolicyStore
0x18000aa88  mov     ebx, eax
0x18000aa8a  test    eax, eax
0x18000aa8c  jg      short loc_18000AAA9
0x18000aa8e  test    ebx, ebx
0x18000aa90  js      short loc_18000AAE2
0x18000aa92  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa99  jmp     loc_18000AA07
0x18000aa9e  movzx   ebx, ax
0x18000aaa1  or      ebx, 80070000h
0x18000aaa7  jmp     short loc_18000AA61
0x18000aaa9  movzx   ebx, ax
0x18000aaac  or      ebx, 80070000h
0x18000aab2  jmp     short loc_18000AA8E
0x18000aab4  mov     ebx, 80070057h
0x18000aab9  mov     edx, ebx
0x18000aabb  jmp     short loc_18000AABF
0x18000aabd  mov     edx, eax
0x18000aabf  lea     rcx, aFwpolicy2Getbo; "FwPolicy2::GetBool"
0x18000aac6  call    cs:__imp_FwReportReturnError
0x18000aacc  mov     edx, ebx
0x18000aace  lea     rcx, aFwpolicy2Getbo; "FwPolicy2::GetBool"
0x18000aad5  call    cs:__imp_FwReportReturnError
0x18000aadb  mov     ebx, eax
0x18000aadd  jmp     loc_18000ABEB
0x18000aae2  mov     edx, ebx
0x18000aae4  lea     rcx, aFwpolicy2Getpo; "FwPolicy2::GetPolicyStoreHandle"
0x18000aaeb  call    cs:__imp_FwReportReturnError
0x18000aaf1  mov     edx, ebx
0x18000aaf3  lea     rcx, aFwpolicy2Getpo; "FwPolicy2::GetPolicyStoreHandle"
0x18000aafa  call    cs:__imp_FwReportReturnError
0x18000ab00  xor     ebp, ebp
0x18000ab02  mov     ebx, eax
0x18000ab04  test    eax, eax
0x18000ab06  js      short loc_18000AABD
0x18000ab08  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab0f  cmp     esi, 1
0x18000ab12  jnz     loc_18000AC12
0x18000ab18  mov     edi, esi
0x18000ab1a  mov     rax, cs:g_Provider
0x18000ab21  mov     [rsp+88h+var_44], 0
0x18000ab29  test    rax, rax
0x18000ab2c  jz      short loc_18000AB4B
0x18000ab2e  xor     r9d, r9d
0x18000ab31  lea     rdx, MPS_CLNT_API_Enter_GetConfig
0x18000ab38  xor     r8d, r8d
0x18000ab3b  mov     rcx, rax
0x18000ab3e  call    cs:__imp_EtwEventWrite
0x18000ab44  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab4b  lea     rsi, WPP_GLOBAL_Control
0x18000ab52  cmp     rcx, rsi
0x18000ab55  jz      short loc_18000AB61
0x18000ab57  test    byte ptr [rcx+1Ch], 8
0x18000ab5b  jnz     loc_18000ACB4
0x18000ab61  call    cs:__imp_GetTickCount64
0x18000ab67  lea     rax, [rsp+88h+var_44]
0x18000ab6c  mov     r8d, 1
0x18000ab72  mov     [rsp+88h+var_50], rax
0x18000ab77  mov     r9d, edi
0x18000ab7a  lea     rax, [rsp+88h+var_40]
0x18000ab7f  mov     rdx, rbp
0x18000ab82  mov     [rsp+88h+var_58], rax
0x18000ab87  mov     ecx, r8d
0x18000ab8a  lea     rax, [rsp+88h+var_48]
0x18000ab8f  mov     [rsp+88h+var_60], rax
0x18000ab94  mov     [rsp+88h+var_68], 0
0x18000ab9c  call    Int_FWGetOrSetConfig
0x18000aba1  mov     edi, eax
0x18000aba3  test    eax, eax
0x18000aba5  jnz     loc_18000AC39
0x18000abab  mov     rcx, cs:g_Provider
0x18000abb2  test    rcx, rcx
0x18000abb5  jz      short loc_18000ABCA
0x18000abb7  xor     r9d, r9d
0x18000abba  lea     rdx, MPS_CLNT_API_Exit_GetConfig
0x18000abc1  xor     r8d, r8d
0x18000abc4  call    cs:__imp_EtwEventWrite
0x18000abca  cmp     edi, r12d
0x18000abcd  jz      short loc_18000ABE4
0x18000abcf  test    edi, edi
0x18000abd1  jg      short loc_18000AC1F
0x18000abd3  mov     ebx, edi
0x18000abd5  test    ebx, ebx
0x18000abd7  js      loc_18000AAB9
0x18000abdd  cmp     [rsp+88h+var_48], 0
0x18000abe2  jz      short loc_18000AC0E
0x18000abe4  or      eax, 0FFFFFFFFh
0x18000abe7  mov     [r14], ax
0x18000abeb  mov     eax, ebx
0x18000abed  mov     rcx, [rsp+88h+var_38]
0x18000abf2  xor     rcx, rsp; StackCookie
0x18000abf5  call    __security_check_cookie
0x18000abfa  mov     rbx, [rsp+88h+arg_8]
0x18000ac02  add     rsp, 60h
0x18000ac06  pop     r14
0x18000ac08  pop     r12
0x18000ac0a  pop     rdi
0x18000ac0b  pop     rsi
0x18000ac0c  pop     rbp
0x18000ac0d  retn
0x18000ac0e  xor     eax, eax
0x18000ac10  jmp     short loc_18000ABE7
0x18000ac12  cmp     esi, r12d
0x18000ac15  jnz     short loc_18000AC2A
0x18000ac17  mov     edi, r12d
0x18000ac1a  jmp     loc_18000AB1A
0x18000ac1f  movzx   ebx, di
0x18000ac22  or      ebx, 80070000h
0x18000ac28  jmp     short loc_18000ABD5
0x18000ac2a  xor     edi, edi
0x18000ac2c  lea     eax, [rdi+4]
0x18000ac2f  cmp     esi, eax
0x18000ac31  cmovz   edi, eax
0x18000ac34  jmp     loc_18000AB1A
0x18000ac39  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ac40  cmp     rcx, rsi
0x18000ac43  jz      loc_18000ABAB
0x18000ac49  test    byte ptr [rcx+1Ch], 1
0x18000ac4d  jz      loc_18000ABAB
0x18000ac53  mov     rcx, [rcx+10h]
0x18000ac57  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000ac5e  mov     edx, 6Bh ; 'k'
0x18000ac63  mov     r9d, edi
0x18000ac66  call    WPP_SF_d
0x18000ac6b  jmp     loc_18000ABAB
0x18000ac70  mov     rcx, [rcx+10h]
0x18000ac74  mov     edx, 0Ch
0x18000ac79  mov     r8, rbx
0x18000ac7c  call    WPP_SF_
0x18000ac81  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ac88  jmp     loc_18000AA19
0x18000ac8d  mov     ebx, 80004003h
0x18000ac92  jmp     loc_18000AAB9
0x18000ac97  mov     rcx, [rcx+10h]
0x18000ac9b  mov     edx, 28h ; '('
0x18000aca0  mov     r8, rbx
0x18000aca3  call    WPP_SF_
0x18000aca8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000acaf  jmp     loc_18000A9F8
0x18000acb4  mov     rcx, [rcx+10h]
0x18000acb8  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000acbf  mov     edx, 6Ah ; 'j'
0x18000acc4  call    WPP_SF_
0x18000acc9  jmp     loc_18000AB61
```
