# QueryPerUserIsA9DataAnalysisDisabledByPolicy(void)

- ea: `0x18002afc8`
- end: `0x18002b26b`
- name: `?QueryPerUserIsA9DataAnalysisDisabledByPolicy@@YA?AV?$optional@_N@std@@XZ`
- size: `675`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002a514`

## callees

- `0x180002ba0`
- `0x18002062c`
- `0x18002065c`
- `0x180026be4`
- `0x18002afc8`
- `0x18002e0a8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b1b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b21b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b1b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b21b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b192`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b1d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b192`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b1d7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002b0c5`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002b0c5`
- `WTSAPI32!WTSQueryUserToken` at `0x18002b05c`
- `WTSAPI32!WTSQueryUserToken` at `0x18002b05c`
- `WTSAPI32!WTSFreeMemory` at `0x18002b234`
- `WTSAPI32!WTSFreeMemory` at `0x18002b234`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x18002b00d`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x18002b00d`
- `ext-ms-win-devmgmt-policy-l1-1-1!PolicyManager_GetPolicy` at `0x18002b119`
- `ext-ms-win-devmgmt-policy-l1-1-1!PolicyManager_GetPolicy` at `0x18002b119`
- `ext-ms-win-devmgmt-policy-l1-1-1!PolicyManager_FreeGetPolicyData` at `0x18002b17e`
- `ext-ms-win-devmgmt-policy-l1-1-1!PolicyManager_FreeGetPolicyData` at `0x18002b1c3`
- `ext-ms-win-devmgmt-policy-l1-1-1!PolicyManager_FreeGetPolicyData` at `0x18002b17e`
- `ext-ms-win-devmgmt-policy-l1-1-1!PolicyManager_FreeGetPolicyData` at `0x18002b1c3`

## string_xrefs

- `0x18002b12e`: `pcshell\shell\aix\shellconfigtask\lib\RecallTaskHandlerHelpers.h`
- `0x18002b252`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
bool *__fastcall QueryPerUserIsA9DataAnalysisDisabledByPolicy(bool *a1)
{
  unsigned int v2; // esi
  _BYTE *v3; // r12
  PWTS_SESSION_INFOW v4; // rdi
  struct _WTS_SESSION_INFOW *v5; // r13
  int v6; // esi
  int token_information; // eax
  void *v8; // r14
  void *v9; // rdx
  unsigned int v10; // r8d
  const char *v11; // r9
  int Policy; // eax
  _DWORD *v13; // rcx
  bool v14; // al
  int pCount; // [rsp+20h] [rbp-98h]
  void *phToken; // [rsp+30h] [rbp-88h] BYREF
  _DWORD *v18; // [rsp+38h] [rbp-80h] BYREF
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+40h] [rbp-78h] BYREF
  void *Block[2]; // [rsp+48h] [rbp-70h] BYREF
  bool *v21; // [rsp+58h] [rbp-60h]
  struct _WTS_SESSION_INFOW *v22; // [rsp+60h] [rbp-58h]
  _BYTE *v23; // [rsp+68h] [rbp-50h]
  _DWORD v24[2]; // [rsp+70h] [rbp-48h] BYREF
  LPWSTR v25; // [rsp+78h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  DWORD v27; // [rsp+D0h] [rbp+18h] BYREF
  LPWSTR StringSid; // [rsp+D8h] [rbp+20h] BYREF

  v2 = 0;
  v3 = a1 + 1;
  a1[1] = 0;
  v27 = 0;
  ppSessionInfo = 0;
  if ( WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &v27) )
  {
    v23 = v3;
    v21 = a1;
    v4 = ppSessionInfo;
    v5 = &ppSessionInfo[v27];
    v22 = v5;
    while ( 1 )
    {
      Block[1] = v4;
      if ( v4 == v5 )
        break;
      phToken = 0;
      if ( WTSQueryUserToken(v4->SessionId, &phToken) )
      {
        Block[0] = 0;
        v6 = v2 | 2;
        token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(Block, (__int64)phToken);
        if ( token_information < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x1CBE,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
            (const char *)(unsigned int)token_information,
            pCount);
        v2 = v6 & 0xFFFFFFFC | 1;
        StringSid = 0;
        v8 = Block[0];
        if ( !ConvertSidToStringSidW(*(PSID *)Block[0], &StringSid) )
          wil::details::in1diag3::_Throw_GetLastError(retaddr, v9, v10, v11);
        v24[0] = 2;
        v24[1] = 1;
        v25 = StringSid;
        v18 = 0;
        Policy = PolicyManager_GetPolicy(L"WindowsAI", L"DisableAIDataAnalysis", v24, &v18);
        if ( Policy >= 0 )
        {
          v13 = v18;
          if ( v18[1] && v18[2] == 1 && (!*v3 || !*a1) )
          {
            v14 = v18[4] == 1;
            *v21 = v14;
            *v3 = 1;
            if ( v14 )
            {
              if ( v13 )
                PolicyManager_FreeGetPolicyData();
              if ( StringSid )
                LocalFree(StringSid);
              if ( v8 )
                operator delete(v8);
              if ( (char *)phToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
                CloseHandle(phToken);
              break;
            }
          }
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x23C,
            (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\RecallTaskHandlerHelpers.h",
            (const char *)(unsigned int)Policy,
            pCount);
          v13 = v18;
        }
        if ( v13 )
          PolicyManager_FreeGetPolicyData();
        if ( StringSid )
          LocalFree(StringSid);
        if ( v8 )
          operator delete(v8);
      }
      if ( (char *)phToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(phToken);
      ++v4;
    }
  }
  if ( ppSessionInfo )
    WTSFreeMemory(ppSessionInfo);
  return a1;
}

```

## disassembly

```asm
0x18002afc8  mov     rax, rsp
0x18002afcb  mov     [rax+8], rcx
0x18002afcf  push    rsi
0x18002afd0  push    rdi
0x18002afd1  push    r12
0x18002afd3  push    r13
0x18002afd5  push    r14
0x18002afd7  push    r15
0x18002afd9  sub     rsp, 88h
0x18002afe0  mov     r15, rcx
0x18002afe3  xor     esi, esi
0x18002afe5  mov     [rax+10h], esi
0x18002afe8  lea     r12, [rcx+1]
0x18002afec  mov     [r12], sil
0x18002aff0  mov     [rax+18h], esi
0x18002aff3  mov     [rax-78h], rsi
0x18002aff7  lea     rax, [rax+18h]
0x18002affb  mov     qword ptr [rsp+0B8h+pCount], rax; int
0x18002b000  lea     r9, [rsp+0B8h+ppSessionInfo]; ppSessionInfo
0x18002b005  xor     edx, edx; Reserved
0x18002b007  xor     ecx, ecx; hServer
0x18002b009  lea     r8d, [rsi+1]; Version
0x18002b00d  call    cs:__imp_WTSEnumerateSessionsW
0x18002b013  test    eax, eax
0x18002b015  jz      loc_18002B22A
0x18002b01b  mov     [rsp+0B8h+var_50], r12
0x18002b020  mov     [rsp+0B8h+var_60], r15
0x18002b025  mov     rdi, [rsp+0B8h+ppSessionInfo]
0x18002b02a  mov     eax, [rsp+0B8h+arg_10]
0x18002b031  lea     rcx, [rax+rax*2]
0x18002b035  lea     r13, [rdi+rcx*8]
0x18002b039  mov     [rsp+0B8h+var_58], r13
0x18002b03e  mov     [rsp+0B8h+var_68], rdi
0x18002b043  cmp     rdi, r13
0x18002b046  jz      loc_18002B22A
0x18002b04c  mov     [rsp+0B8h+phToken], 0
0x18002b055  lea     rdx, [rsp+0B8h+phToken]; phToken
0x18002b05a  mov     ecx, [rdi]; SessionId
0x18002b05c  call    cs:__imp_WTSQueryUserToken
0x18002b062  test    eax, eax
0x18002b064  jz      loc_18002B20C
0x18002b06a  mov     [rsp+0B8h+Block], 0
0x18002b073  or      esi, 2
0x18002b076  mov     [rsp+0B8h+arg_8], esi
0x18002b07d  mov     rdx, [rsp+0B8h+phToken]
0x18002b082  lea     rcx, [rsp+0B8h+Block]
0x18002b087  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x18002b08c  mov     rcx, [rsp+0B8h]; this
0x18002b094  test    eax, eax
0x18002b096  js      loc_18002B24F
0x18002b09c  and     esi, 0FFFFFFFDh
0x18002b09f  or      esi, 1
0x18002b0a2  mov     [rsp+0B8h+arg_8], esi
0x18002b0a9  mov     [rsp+0B8h+StringSid], 0
0x18002b0b5  lea     rdx, [rsp+0B8h+StringSid]; StringSid
0x18002b0bd  mov     r14, [rsp+0B8h+Block]
0x18002b0c2  mov     rcx, [r14]; Sid
0x18002b0c5  call    cs:__imp_ConvertSidToStringSidW
0x18002b0cb  mov     rcx, [rsp+0B8h]; this
0x18002b0d3  test    eax, eax
0x18002b0d5  jz      loc_18002B264
0x18002b0db  mov     [rsp+0B8h+var_48], 2
0x18002b0e3  mov     [rsp+0B8h+var_44], 1
0x18002b0eb  mov     rax, [rsp+0B8h+StringSid]
0x18002b0f3  mov     [rsp+0B8h+var_40], rax
0x18002b0f8  mov     [rsp+0B8h+var_80], 0
0x18002b101  lea     r9, [rsp+0B8h+var_80]
0x18002b106  lea     r8, [rsp+0B8h+var_48]
0x18002b10b  lea     rdx, aDisableaidataa; "DisableAIDataAnalysis"
0x18002b112  lea     rcx, aWindowsai; "WindowsAI"
0x18002b119  call    cs:__imp_PolicyManager_GetPolicy
0x18002b11f  mov     rcx, [rsp+0B8h]; this
0x18002b127  test    eax, eax
0x18002b129  jns     short loc_18002B146
0x18002b12b  mov     r9d, eax; char *
0x18002b12e  lea     r8, aPcshellShellAi_1; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x18002b135  mov     edx, 23Ch; void *
0x18002b13a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002b13f  mov     rcx, [rsp+0B8h+var_80]
0x18002b144  jmp     short loc_18002B1BE
0x18002b146  mov     rcx, [rsp+0B8h+var_80]
0x18002b14b  cmp     dword ptr [rcx+4], 0
0x18002b14f  jz      short loc_18002B1BE
0x18002b151  cmp     dword ptr [rcx+8], 1
0x18002b155  jnz     short loc_18002B1BE
0x18002b157  cmp     byte ptr [r12], 0
0x18002b15c  jz      short loc_18002B164
0x18002b15e  cmp     byte ptr [r15], 0
0x18002b162  jnz     short loc_18002B1BE
0x18002b164  cmp     dword ptr [rcx+10h], 1
0x18002b168  setz    al
0x18002b16b  mov     rdx, [rsp+0B8h+var_60]
0x18002b170  mov     [rdx], al
0x18002b172  mov     byte ptr [r12], 1
0x18002b177  jnz     short loc_18002B1BE
0x18002b179  test    rcx, rcx
0x18002b17c  jz      short loc_18002B185
0x18002b17e  call    cs:__imp_PolicyManager_FreeGetPolicyData
0x18002b184  nop
0x18002b185  mov     rcx, [rsp+0B8h+StringSid]; hMem
0x18002b18d  test    rcx, rcx
0x18002b190  jz      short loc_18002B199
0x18002b192  call    cs:__imp_LocalFree
0x18002b198  nop
0x18002b199  test    r14, r14
0x18002b19c  jz      short loc_18002B1A7
0x18002b19e  mov     rcx, r14; Block
0x18002b1a1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002b1a6  nop
0x18002b1a7  mov     rcx, [rsp+0B8h+phToken]; hObject
0x18002b1ac  lea     rax, [rcx-1]
0x18002b1b0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002b1b4  ja      short loc_18002B1BC
0x18002b1b6  call    cs:__imp_CloseHandle
0x18002b1bc  jmp     short loc_18002B22A
0x18002b1be  test    rcx, rcx
0x18002b1c1  jz      short loc_18002B1CA
0x18002b1c3  call    cs:__imp_PolicyManager_FreeGetPolicyData
0x18002b1c9  nop
0x18002b1ca  mov     rcx, [rsp+0B8h+StringSid]; hMem
0x18002b1d2  test    rcx, rcx
0x18002b1d5  jz      short loc_18002B1DE
0x18002b1d7  call    cs:__imp_LocalFree
0x18002b1dd  nop
0x18002b1de  test    r14, r14
0x18002b1e1  jz      short loc_18002B1EC
0x18002b1e3  mov     rcx, r14; Block
0x18002b1e6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002b1eb  nop
0x18002b1ec  jmp     short loc_18002B20C
0x18002b1ee  mov     r15, [rsp+0B8h+arg_0]
0x18002b1f6  mov     rdi, [rsp+0B8h+var_68]
0x18002b1fb  mov     r13, [rsp+0B8h+var_58]
0x18002b200  mov     esi, [rsp+0B8h+arg_8]
0x18002b207  mov     r12, [rsp+0B8h+var_50]
0x18002b20c  mov     rcx, [rsp+0B8h+phToken]; hObject
0x18002b211  lea     rax, [rcx-1]
0x18002b215  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002b219  ja      short loc_18002B221
0x18002b21b  call    cs:__imp_CloseHandle
0x18002b221  add     rdi, 18h
0x18002b225  jmp     loc_18002B03E
0x18002b22a  mov     rcx, [rsp+0B8h+ppSessionInfo]; pMemory
0x18002b22f  test    rcx, rcx
0x18002b232  jz      short loc_18002B23A
0x18002b234  call    cs:__imp_WTSFreeMemory
0x18002b23a  mov     rax, r15
0x18002b23d  add     rsp, 88h
0x18002b244  pop     r15
0x18002b246  pop     r14
0x18002b248  pop     r13
0x18002b24a  pop     r12
0x18002b24c  pop     rdi
0x18002b24d  pop     rsi
0x18002b24e  retn
0x18002b24f  mov     r9d, eax; char *
0x18002b252  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002b259  mov     edx, 1CBEh; void *
0x18002b25e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002b264  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
