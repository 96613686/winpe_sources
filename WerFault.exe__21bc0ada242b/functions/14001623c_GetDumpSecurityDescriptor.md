# GetDumpSecurityDescriptor

- ea: `0x14001623c`
- end: `0x1400164fa`
- name: `GetDumpSecurityDescriptor`
- size: `702`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, PSECURITY_DESCRIPTOR *SecurityDescriptor)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140016cbc`

## callees

- `0x140002728`
- `0x1400032ef`
- `0x140005430`
- `0x140011010`
- `0x14001114c`
- `0x140014474`
- `0x14001623c`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140016466`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140016466`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1400162e2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1400162e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400162d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140016452`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400164bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400162d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140016452`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400164bc`

## pseudocode

```c
__int64 __fastcall GetDumpSecurityDescriptor(HANDLE ProcessHandle, PSECURITY_DESCRIPTOR *SecurityDescriptor)
{
  int ProcessUserSid; // ebx
  CUserModeHangReport *v5; // rcx
  __int64 v6; // rdx
  HLOCAL v7; // rcx
  signed int v8; // eax
  PSECURITY_DESCRIPTOR v9; // rcx
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
                               (__int64)StringSecurityDescriptor,
                               (__int64)L"D:P(A;;GA;;;BA)(A;;GA;;;SY)(A;;GA;;;%s)",
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
              goto LABEL_45;
            }
          }
          else
          {
            ProcessUserSid = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                               (__int64)StringSecurityDescriptor,
                               (__int64)L"D:P(A;;GA;;;BA)(A;;GA;;;SY)(A;;GA;;;%s)S:(ML;;NR;;;ME)",
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
              goto LABEL_45;
            }
          }
        }
        else
        {
          ProcessUserSid = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                             (__int64)StringSecurityDescriptor,
                             (__int64)L"D:P(A;;GA;;;BA)(A;;GA;;;SY)(A;;GA;;;%s)S:(ML;;NR;;;HI)",
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
            goto LABEL_45;
          }
        }
        v9 = *SecurityDescriptor;
        *SecurityDescriptor = 0;
        if ( v9 )
          LocalFree(v9);
        if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
               StringSecurityDescriptor[0],
               1u,
               SecurityDescriptor,
               0) )
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
        goto LABEL_45;
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
LABEL_45:
  if ( hMem )
    LocalFree(hMem);
  if ( StringSecurityDescriptor[0] != v13 )
    operator delete((void *)StringSecurityDescriptor[0], (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)ProcessUserSid;
}

```

## disassembly

```asm
0x14001623c  mov     [rsp-18h+arg_0], rbx
0x140016241  push    rbp
0x140016242  push    rsi
0x140016243  push    rdi
0x140016244  mov     rbp, rsp
0x140016247  sub     rsp, 50h
0x14001624b  lea     rax, [rbp+var_18]
0x14001624f  mov     [rbp+Sid], 0
0x140016257  mov     [rbp+StringSecurityDescriptor], rax
0x14001625b  mov     rdi, rdx
0x14001625e  lea     rax, [rbp+var_18]
0x140016262  mov     rsi, rcx
0x140016265  mov     [rbp+var_20], rax
0x140016269  lea     rdx, [rbp+Sid]
0x14001626d  xor     eax, eax
0x14001626f  mov     [rbp+var_18], ax
0x140016273  mov     [rbp+hMem], rax
0x140016277  mov     [rbp+arg_10], eax
0x14001627a  call    ?UtilGetProcessUserSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z; UtilGetProcessUserSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)
0x14001627f  mov     ebx, eax
0x140016281  test    eax, eax
0x140016283  jns     short loc_1400162C3
0x140016285  mov     rcx, cs:WPP_GLOBAL_Control
0x14001628c  lea     rax, WPP_GLOBAL_Control
0x140016293  cmp     rcx, rax
0x140016296  jz      loc_1400164B3
0x14001629c  test    byte ptr [rcx+1Ch], 1
0x1400162a0  jz      loc_1400164B3
0x1400162a6  mov     edx, 14h
0x1400162ab  mov     rcx, [rcx+10h]
0x1400162af  lea     r8, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids
0x1400162b6  mov     r9d, ebx
0x1400162b9  call    WPP_SF_d
0x1400162be  jmp     loc_1400164B3
0x1400162c3  mov     rcx, [rbp+hMem]; hMem
0x1400162c7  mov     [rbp+hMem], 0
0x1400162cf  test    rcx, rcx
0x1400162d2  jz      short loc_1400162DA
0x1400162d4  call    cs:__imp_LocalFree
0x1400162da  mov     rcx, [rbp+Sid]; Sid
0x1400162de  lea     rdx, [rbp+hMem]; StringSid
0x1400162e2  call    cs:__imp_ConvertSidToStringSidW
0x1400162e8  test    eax, eax
0x1400162ea  jnz     short loc_140016335
0x1400162ec  call    GetLastError_0
0x1400162f1  mov     ebx, eax
0x1400162f3  test    eax, eax
0x1400162f5  jle     short loc_140016300
0x1400162f7  movzx   ebx, ax
0x1400162fa  or      ebx, 80070000h
0x140016300  test    ebx, ebx
0x140016302  mov     eax, 80004005h
0x140016307  cmovns  ebx, eax
0x14001630a  mov     rcx, cs:WPP_GLOBAL_Control
0x140016311  lea     rax, WPP_GLOBAL_Control
0x140016318  cmp     rcx, rax
0x14001631b  jz      loc_1400164B3
0x140016321  test    byte ptr [rcx+1Ch], 1
0x140016325  jz      loc_1400164B3
0x14001632b  mov     edx, 15h
0x140016330  jmp     loc_1400162AB
0x140016335  lea     rdx, [rbp+arg_10]; unsigned int *
0x140016339  mov     rcx, rsi; ProcessHandle
0x14001633c  call    ?UtilGetProcessIntegrityRid@@YAJPEAXPEAK@Z; UtilGetProcessIntegrityRid(void *,ulong *)
0x140016341  mov     ebx, eax
0x140016343  test    eax, eax
0x140016345  jns     short loc_140016372
0x140016347  mov     rcx, cs:WPP_GLOBAL_Control
0x14001634e  lea     rax, WPP_GLOBAL_Control
0x140016355  cmp     rcx, rax
0x140016358  jz      loc_1400164B3
0x14001635e  test    byte ptr [rcx+1Ch], 1
0x140016362  jz      loc_1400164B3
0x140016368  mov     edx, 16h
0x14001636d  jmp     loc_1400162AB
0x140016372  cmp     [rbp+arg_10], 3000h
0x140016379  lea     rcx, [rbp+StringSecurityDescriptor]
0x14001637d  mov     r8, [rbp+hMem]
0x140016381  jb      short loc_1400163C4
0x140016383  lea     rdx, aDPAGaBaAGaSyAG_1; "D:P(A;;GA;;;BA)(A;;GA;;;SY)(A;;GA;;;%s)"...
0x14001638a  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x14001638f  mov     ebx, eax
0x140016391  test    eax, eax
0x140016393  jns     loc_140016443
0x140016399  mov     rcx, cs:WPP_GLOBAL_Control
0x1400163a0  lea     rax, WPP_GLOBAL_Control
0x1400163a7  cmp     rcx, rax
0x1400163aa  jz      loc_1400164B3
0x1400163b0  test    byte ptr [rcx+1Ch], 1
0x1400163b4  jz      loc_1400164B3
0x1400163ba  mov     edx, 17h
0x1400163bf  jmp     loc_1400162AB
0x1400163c4  cmp     [rbp+arg_10], 2000h
0x1400163cb  jb      short loc_14001640A
0x1400163cd  lea     rdx, aDPAGaBaAGaSyAG_0; "D:P(A;;GA;;;BA)(A;;GA;;;SY)(A;;GA;;;%s)"...
0x1400163d4  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1400163d9  mov     ebx, eax
0x1400163db  test    eax, eax
0x1400163dd  jns     short loc_140016443
0x1400163df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400163e6  lea     rax, WPP_GLOBAL_Control
0x1400163ed  cmp     rcx, rax
0x1400163f0  jz      loc_1400164B3
0x1400163f6  test    byte ptr [rcx+1Ch], 1
0x1400163fa  jz      loc_1400164B3
0x140016400  mov     edx, 18h
0x140016405  jmp     loc_1400162AB
0x14001640a  lea     rdx, aDPAGaBaAGaSyAG; "D:P(A;;GA;;;BA)(A;;GA;;;SY)(A;;GA;;;%s)"
0x140016411  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x140016416  mov     ebx, eax
0x140016418  test    eax, eax
0x14001641a  jns     short loc_140016443
0x14001641c  mov     rcx, cs:WPP_GLOBAL_Control
0x140016423  lea     rax, WPP_GLOBAL_Control
0x14001642a  cmp     rcx, rax
0x14001642d  jz      loc_1400164B3
0x140016433  test    byte ptr [rcx+1Ch], 1
0x140016437  jz      short loc_1400164B3
0x140016439  mov     edx, 19h
0x14001643e  jmp     loc_1400162AB
0x140016443  mov     rcx, [rdi]; hMem
0x140016446  mov     qword ptr [rdi], 0
0x14001644d  test    rcx, rcx
0x140016450  jz      short loc_140016458
0x140016452  call    cs:__imp_LocalFree
0x140016458  mov     rcx, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x14001645c  xor     r9d, r9d; SecurityDescriptorSize
0x14001645f  mov     r8, rdi; SecurityDescriptor
0x140016462  lea     edx, [r9+1]; StringSDRevision
0x140016466  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x14001646c  test    eax, eax
0x14001646e  jnz     short loc_1400164B1
0x140016470  call    GetLastError_0
0x140016475  mov     ebx, eax
0x140016477  test    eax, eax
0x140016479  jle     short loc_140016484
0x14001647b  movzx   ebx, ax
0x14001647e  or      ebx, 80070000h
0x140016484  test    ebx, ebx
0x140016486  mov     eax, 80004005h
0x14001648b  cmovns  ebx, eax
0x14001648e  mov     rcx, cs:WPP_GLOBAL_Control
0x140016495  lea     rax, WPP_GLOBAL_Control
0x14001649c  cmp     rcx, rax
0x14001649f  jz      short loc_1400164B3
0x1400164a1  test    byte ptr [rcx+1Ch], 1
0x1400164a5  jz      short loc_1400164B3
0x1400164a7  mov     edx, 1Ah
0x1400164ac  jmp     loc_1400162AB
0x1400164b1  xor     ebx, ebx
0x1400164b3  mov     rcx, [rbp+hMem]; hMem
0x1400164b7  test    rcx, rcx
0x1400164ba  jz      short loc_1400164C2
0x1400164bc  call    cs:__imp_LocalFree
0x1400164c2  mov     rcx, [rbp+StringSecurityDescriptor]; void *
0x1400164c6  lea     rax, [rbp+var_18]
0x1400164ca  cmp     rcx, rax
0x1400164cd  jz      short loc_1400164DB
0x1400164cf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400164d6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400164db  cmp     [rbp+Sid], 0
0x1400164e0  jz      short loc_1400164EB
0x1400164e2  mov     rcx, [rbp+Sid]; void *
0x1400164e6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400164eb  mov     eax, ebx
0x1400164ed  mov     rbx, [rsp+50h+arg_0]
0x1400164f2  add     rsp, 50h
0x1400164f6  pop     rdi
0x1400164f7  pop     rsi
0x1400164f8  pop     rbp
0x1400164f9  retn
```
