# GetDumpSecurityDescriptor

- ea: `0x140016e8c`
- end: `0x140017154`
- name: `GetDumpSecurityDescriptor`
- size: `712`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140017998`

## callees

- `0x140002748`
- `0x14000333f`
- `0x1400054e4`
- `0x140011714`
- `0x14001186c`
- `0x140014f14`
- `0x1400167a4`
- `0x140016e8c`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400170b2`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400170b2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x140016f39`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x140016f39`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140016f25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001710e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140016f25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001710e`

## pseudocode

```c
__int64 __fastcall GetDumpSecurityDescriptor(HANDLE ProcessHandle, __int64 a2)
{
  signed int ProcessUserSid; // ebx
  CUserModeHangReport *v5; // rcx
  __int64 v6; // rdx
  HLOCAL v7; // rcx
  signed int v8; // eax
  PSECURITY_DESCRIPTOR *v9; // rax
  signed int LastError_0; // eax
  LPCWSTR StringSecurityDescriptor[2]; // [rsp+28h] [rbp-28h] BYREF
  _WORD v13[12]; // [rsp+38h] [rbp-18h] BYREF
  unsigned int v14; // [rsp+80h] [rbp+30h] BYREF
  HLOCAL hMem; // [rsp+88h] [rbp+38h] BYREF

  StringSecurityDescriptor[0] = v13;
  StringSecurityDescriptor[1] = v13;
  v13[0] = 0;
  hMem = 0;
  v14 = 0;
  ProcessUserSid = UtilGetProcessUserSid(ProcessHandle);
  if ( ProcessUserSid >= 0 )
  {
    v7 = hMem;
    hMem = 0;
    if ( v7 )
      LocalFree(v7);
    if ( ConvertSidToStringSidW(0, (LPWSTR *)&hMem) )
    {
      ProcessUserSid = UtilGetProcessIntegrityRid(ProcessHandle, &v14);
      if ( ProcessUserSid >= 0 )
      {
        if ( v14 < 0x3000 )
        {
          if ( v14 < 0x2000 )
          {
            ProcessUserSid = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                               StringSecurityDescriptor,
                               L"D:P(A;;GA;;;BA)(A;;GA;;;SY)(A;;GA;;;%s)",
                               hMem);
            if ( ProcessUserSid < 0 )
            {
              v5 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v6 = 25;
                goto LABEL_5;
              }
              goto LABEL_43;
            }
          }
          else
          {
            ProcessUserSid = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                               StringSecurityDescriptor,
                               L"D:P(A;;GA;;;BA)(A;;GA;;;SY)(A;;GA;;;%s)S:(ML;;NR;;;ME)",
                               hMem);
            if ( ProcessUserSid < 0 )
            {
              v5 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v6 = 24;
                goto LABEL_5;
              }
              goto LABEL_43;
            }
          }
        }
        else
        {
          ProcessUserSid = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                             StringSecurityDescriptor,
                             L"D:P(A;;GA;;;BA)(A;;GA;;;SY)(A;;GA;;;%s)S:(ML;;NR;;;HI)",
                             hMem);
          if ( ProcessUserSid < 0 )
          {
            v5 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v6 = 23;
              goto LABEL_5;
            }
            goto LABEL_43;
          }
        }
        v9 = (PSECURITY_DESCRIPTOR *)___replace_XU__generic_delete_XU__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___utl__YAPEAPEAXAEAV__unique_ptr_XU__generic_delete_XU__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___0__Z(a2);
        if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor[0], 1u, v9, 0) )
        {
          ProcessUserSid = 0;
        }
        else
        {
          LastError_0 = GetLastError_0();
          ProcessUserSid = LastError_0;
          if ( LastError_0 > 0 )
            ProcessUserSid = (unsigned __int16)LastError_0 | 0x80070000;
          if ( ProcessUserSid >= 0 )
            ProcessUserSid = -2147467259;
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v6 = 26;
            goto LABEL_5;
          }
        }
        goto LABEL_43;
      }
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v6 = 22;
        goto LABEL_5;
      }
    }
    else
    {
      v8 = GetLastError_0();
      ProcessUserSid = v8;
      if ( v8 > 0 )
        ProcessUserSid = (unsigned __int16)v8 | 0x80070000;
      if ( ProcessUserSid >= 0 )
        ProcessUserSid = -2147467259;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v6 = 21;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 20;
LABEL_5:
      WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids, (unsigned int)ProcessUserSid);
    }
  }
LABEL_43:
  if ( hMem )
    LocalFree(hMem);
  if ( StringSecurityDescriptor[0] != v13 )
    operator delete((void *)StringSecurityDescriptor[0], (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)ProcessUserSid;
}

```

## disassembly

```asm
0x140016e8c  mov     [rsp-18h+arg_0], rbx
0x140016e91  push    rbp
0x140016e92  push    rdi
0x140016e93  push    r14
0x140016e95  mov     rbp, rsp
0x140016e98  sub     rsp, 50h
0x140016e9c  lea     rax, [rbp+var_18]
0x140016ea0  mov     [rbp+Sid], 0
0x140016ea8  mov     [rbp+StringSecurityDescriptor], rax
0x140016eac  mov     r14, rdx
0x140016eaf  lea     rax, [rbp+var_18]
0x140016eb3  mov     rdi, rcx
0x140016eb6  mov     [rbp+var_20], rax
0x140016eba  lea     rdx, [rbp+Sid]
0x140016ebe  xor     eax, eax
0x140016ec0  mov     [rbp+var_18], ax
0x140016ec4  mov     [rbp+hMem], rax
0x140016ec8  mov     [rbp+arg_10], eax
0x140016ecb  call    ?UtilGetProcessUserSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z; UtilGetProcessUserSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)
0x140016ed0  mov     ebx, eax
0x140016ed2  test    eax, eax
0x140016ed4  jns     short loc_140016F14
0x140016ed6  mov     rcx, cs:WPP_GLOBAL_Control
0x140016edd  lea     rax, WPP_GLOBAL_Control
0x140016ee4  cmp     rcx, rax
0x140016ee7  jz      loc_140017105
0x140016eed  test    byte ptr [rcx+1Ch], 1
0x140016ef1  jz      loc_140017105
0x140016ef7  mov     edx, 14h
0x140016efc  mov     rcx, [rcx+10h]
0x140016f00  lea     r8, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids
0x140016f07  mov     r9d, ebx
0x140016f0a  call    WPP_SF_d
0x140016f0f  jmp     loc_140017105
0x140016f14  mov     rcx, [rbp+hMem]; hMem
0x140016f18  mov     [rbp+hMem], 0
0x140016f20  test    rcx, rcx
0x140016f23  jz      short loc_140016F31
0x140016f25  call    cs:__imp_LocalFree
0x140016f2c  nop     dword ptr [rax+rax+00h]
0x140016f31  mov     rcx, [rbp+Sid]; Sid
0x140016f35  lea     rdx, [rbp+hMem]; StringSid
0x140016f39  call    cs:__imp_ConvertSidToStringSidW
0x140016f40  nop     dword ptr [rax+rax+00h]
0x140016f45  test    eax, eax
0x140016f47  jnz     short loc_140016F92
0x140016f49  call    GetLastError_0
0x140016f4e  mov     ebx, eax
0x140016f50  test    eax, eax
0x140016f52  jle     short loc_140016F5D
0x140016f54  movzx   ebx, ax
0x140016f57  or      ebx, 80070000h
0x140016f5d  test    ebx, ebx
0x140016f5f  mov     eax, 80004005h
0x140016f64  cmovns  ebx, eax
0x140016f67  mov     rcx, cs:WPP_GLOBAL_Control
0x140016f6e  lea     rax, WPP_GLOBAL_Control
0x140016f75  cmp     rcx, rax
0x140016f78  jz      loc_140017105
0x140016f7e  test    byte ptr [rcx+1Ch], 1
0x140016f82  jz      loc_140017105
0x140016f88  mov     edx, 15h
0x140016f8d  jmp     loc_140016EFC
0x140016f92  lea     rdx, [rbp+arg_10]; unsigned int *
0x140016f96  mov     rcx, rdi; ProcessHandle
0x140016f99  call    ?UtilGetProcessIntegrityRid@@YAJPEAXPEAK@Z; UtilGetProcessIntegrityRid(void *,ulong *)
0x140016f9e  mov     ebx, eax
0x140016fa0  test    eax, eax
0x140016fa2  jns     short loc_140016FCF
0x140016fa4  mov     rcx, cs:WPP_GLOBAL_Control
0x140016fab  lea     rax, WPP_GLOBAL_Control
0x140016fb2  cmp     rcx, rax
0x140016fb5  jz      loc_140017105
0x140016fbb  test    byte ptr [rcx+1Ch], 1
0x140016fbf  jz      loc_140017105
0x140016fc5  mov     edx, 16h
0x140016fca  jmp     loc_140016EFC
0x140016fcf  cmp     [rbp+arg_10], 3000h
0x140016fd6  lea     rcx, [rbp+StringSecurityDescriptor]
0x140016fda  mov     r8, [rbp+hMem]
0x140016fde  jb      short loc_140017021
0x140016fe0  lea     rdx, aDPAGaBaAGaSyAG_1; "D:P(A;;GA;;;BA)(A;;GA;;;SY)(A;;GA;;;%s)"...
0x140016fe7  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x140016fec  mov     ebx, eax
0x140016fee  test    eax, eax
0x140016ff0  jns     loc_14001709C
0x140016ff6  mov     rcx, cs:WPP_GLOBAL_Control
0x140016ffd  lea     rax, WPP_GLOBAL_Control
0x140017004  cmp     rcx, rax
0x140017007  jz      loc_140017105
0x14001700d  test    byte ptr [rcx+1Ch], 1
0x140017011  jz      loc_140017105
0x140017017  mov     edx, 17h
0x14001701c  jmp     loc_140016EFC
0x140017021  cmp     [rbp+arg_10], 2000h
0x140017028  jb      short loc_140017067
0x14001702a  lea     rdx, aDPAGaBaAGaSyAG_0; "D:P(A;;GA;;;BA)(A;;GA;;;SY)(A;;GA;;;%s)"...
0x140017031  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x140017036  mov     ebx, eax
0x140017038  test    eax, eax
0x14001703a  jns     short loc_14001709C
0x14001703c  mov     rcx, cs:WPP_GLOBAL_Control
0x140017043  lea     rax, WPP_GLOBAL_Control
0x14001704a  cmp     rcx, rax
0x14001704d  jz      loc_140017105
0x140017053  test    byte ptr [rcx+1Ch], 1
0x140017057  jz      loc_140017105
0x14001705d  mov     edx, 18h
0x140017062  jmp     loc_140016EFC
0x140017067  lea     rdx, aDPAGaBaAGaSyAG; "D:P(A;;GA;;;BA)(A;;GA;;;SY)(A;;GA;;;%s)"
0x14001706e  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x140017073  mov     ebx, eax
0x140017075  test    eax, eax
0x140017077  jns     short loc_14001709C
0x140017079  mov     rcx, cs:WPP_GLOBAL_Control
0x140017080  lea     rax, WPP_GLOBAL_Control
0x140017087  cmp     rcx, rax
0x14001708a  jz      short loc_140017105
0x14001708c  test    byte ptr [rcx+1Ch], 1
0x140017090  jz      short loc_140017105
0x140017092  mov     edx, 19h
0x140017097  jmp     loc_140016EFC
0x14001709c  mov     rcx, r14
0x14001709f  call    ??$replace@XU?$generic_delete@XU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@utl@@YAPEAPEAXAEAV?$unique_ptr@XU?$generic_delete@XU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@0@@Z
0x1400170a4  mov     rcx, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x1400170a8  xor     r9d, r9d; SecurityDescriptorSize
0x1400170ab  mov     r8, rax; SecurityDescriptor
0x1400170ae  lea     edx, [r9+1]; StringSDRevision
0x1400170b2  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1400170b9  nop     dword ptr [rax+rax+00h]
0x1400170be  test    eax, eax
0x1400170c0  jnz     short loc_140017103
0x1400170c2  call    GetLastError_0
0x1400170c7  mov     ebx, eax
0x1400170c9  test    eax, eax
0x1400170cb  jle     short loc_1400170D6
0x1400170cd  movzx   ebx, ax
0x1400170d0  or      ebx, 80070000h
0x1400170d6  test    ebx, ebx
0x1400170d8  mov     eax, 80004005h
0x1400170dd  cmovns  ebx, eax
0x1400170e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400170e7  lea     rax, WPP_GLOBAL_Control
0x1400170ee  cmp     rcx, rax
0x1400170f1  jz      short loc_140017105
0x1400170f3  test    byte ptr [rcx+1Ch], 1
0x1400170f7  jz      short loc_140017105
0x1400170f9  mov     edx, 1Ah
0x1400170fe  jmp     loc_140016EFC
0x140017103  xor     ebx, ebx
0x140017105  mov     rcx, [rbp+hMem]; hMem
0x140017109  test    rcx, rcx
0x14001710c  jz      short loc_14001711A
0x14001710e  call    cs:__imp_LocalFree
0x140017115  nop     dword ptr [rax+rax+00h]
0x14001711a  mov     rcx, [rbp+StringSecurityDescriptor]; void *
0x14001711e  lea     rax, [rbp+var_18]
0x140017122  cmp     rcx, rax
0x140017125  jz      short loc_140017133
0x140017127  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001712e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140017133  cmp     [rbp+Sid], 0
0x140017138  jz      short loc_140017143
0x14001713a  mov     rcx, [rbp+Sid]; void *
0x14001713e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140017143  mov     eax, ebx
0x140017145  mov     rbx, [rsp+50h+arg_0]
0x14001714a  add     rsp, 50h
0x14001714e  pop     r14
0x140017150  pop     rdi
0x140017151  pop     rbp
0x140017152  retn
```
