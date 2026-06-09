# UtilGetProcessUserSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)

- ea: `0x14001114c`
- end: `0x1400112c5`
- name: `?UtilGetProcessUserSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z`
- size: `377`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation`

## callers

- `0x14001623c`
- `0x1400455ac`

## callees

- `0x140002728`
- `0x14000e404`
- `0x14001114c`
- `0x1400115cc`
- `0x14001444c`
- `0x140014474`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011209`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011209`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400111d8`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400111d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400111ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400112b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400111ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400112b2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UtilGetProcessUserSid(HANDLE ProcessHandle, const struct std::nothrow_t *a2)
{
  int TokenUserSid; // ebx
  void *v5; // rcx
  void **v6; // rax
  BOOL v7; // edi
  void *v8; // rcx
  signed int LastError; // eax
  void *v11; // [rsp+20h] [rbp-28h] BYREF
  void **v12; // [rsp+28h] [rbp-20h]
  HANDLE hObject; // [rsp+58h] [rbp+10h] BYREF

  hObject = 0;
  if ( a2 )
  {
    v5 = *(void **)a2;
    *(_QWORD *)a2 = 0;
    if ( v5 )
      operator delete(v5, a2);
    v6 = (void **)utl::out_ptr<void,tlx::unique_any<tlx::file_handle_traits>,>(&v11, &hObject);
    v7 = OpenProcessToken(ProcessHandle, 8u, v6);
    if ( v11 )
    {
      v8 = *v12;
      *v12 = v11;
      if ( (unsigned __int64)v8 + 1 > 1 )
        CloseHandle(v8);
    }
    if ( v7 )
    {
      TokenUserSid = UtilGetTokenUserSid(hObject, a2);
      if ( TokenUserSid >= 0 )
      {
        TokenUserSid = 0;
      }
      else if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          &WPP_988ce82756cb3ec502560a762615dae0_Traceguids,
          (unsigned int)TokenUserSid);
      }
    }
    else
    {
      LastError = GetLastError();
      TokenUserSid = LastError;
      if ( LastError > 0 )
        TokenUserSid = (unsigned __int16)LastError | 0x80070000;
      if ( TokenUserSid >= 0 )
        TokenUserSid = -2147467259;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          &WPP_988ce82756cb3ec502560a762615dae0_Traceguids,
          (unsigned int)TokenUserSid);
      }
    }
  }
  else
  {
    TokenUserSid = -2147024809;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
    }
  }
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  return (unsigned int)TokenUserSid;
}

```

## disassembly

```asm
0x14001114c  mov     [rsp+arg_0], rbx
0x140011151  push    rdi
0x140011152  sub     rsp, 40h
0x140011156  mov     rbx, rdx
0x140011159  mov     rdi, rcx
0x14001115c  mov     [rsp+48h+hObject], 0
0x140011165  test    rdx, rdx
0x140011168  jnz     short loc_1400111AA
0x14001116a  mov     ebx, 80070057h
0x14001116f  lea     rax, WPP_GLOBAL_Control
0x140011176  mov     rcx, cs:WPP_GLOBAL_Control
0x14001117d  cmp     rcx, rax
0x140011180  jz      loc_1400112A3
0x140011186  test    byte ptr [rcx+1Ch], 1
0x14001118a  jz      loc_1400112A3
0x140011190  mov     edx, 0Fh
0x140011195  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x14001119c  mov     rcx, [rcx+10h]
0x1400111a0  call    WPP_SF_
0x1400111a5  jmp     loc_1400112A3
0x1400111aa  mov     rcx, [rdx]; void *
0x1400111ad  mov     qword ptr [rdx], 0
0x1400111b4  test    rcx, rcx
0x1400111b7  jz      short loc_1400111BE
0x1400111b9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400111be  lea     rdx, [rsp+48h+hObject]
0x1400111c3  lea     rcx, [rsp+48h+var_28]
0x1400111c8  call    ??$out_ptr@XV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@$$V@utl@@YA?A_PAEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z
0x1400111cd  mov     r8, rax; TokenHandle
0x1400111d0  mov     edx, 8; DesiredAccess
0x1400111d5  mov     rcx, rdi; ProcessHandle
0x1400111d8  call    cs:__imp_OpenProcessToken
0x1400111de  mov     edi, eax
0x1400111e0  mov     r8, [rsp+48h+var_28]
0x1400111e5  test    r8, r8
0x1400111e8  jz      short loc_140011205
0x1400111ea  mov     rdx, [rsp+48h+var_20]
0x1400111ef  mov     rcx, [rdx]; hObject
0x1400111f2  mov     [rdx], r8
0x1400111f5  lea     rdx, [rcx+1]
0x1400111f9  cmp     rdx, 1
0x1400111fd  jbe     short loc_140011205
0x1400111ff  call    cs:__imp_CloseHandle
0x140011205  test    edi, edi
0x140011207  jnz     short loc_14001125B
0x140011209  call    cs:__imp_GetLastError
0x14001120f  mov     ebx, eax
0x140011211  test    eax, eax
0x140011213  jle     short loc_14001121E
0x140011215  movzx   ebx, ax
0x140011218  or      ebx, 80070000h
0x14001121e  mov     eax, 80004005h
0x140011223  test    ebx, ebx
0x140011225  cmovns  ebx, eax
0x140011228  lea     rax, WPP_GLOBAL_Control
0x14001122f  mov     rcx, cs:WPP_GLOBAL_Control
0x140011236  cmp     rcx, rax
0x140011239  jz      short loc_1400112A3
0x14001123b  test    byte ptr [rcx+1Ch], 1
0x14001123f  jz      short loc_1400112A3
0x140011241  mov     edx, 10h
0x140011246  mov     r9d, ebx
0x140011249  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x140011250  mov     rcx, [rcx+10h]
0x140011254  call    WPP_SF_d
0x140011259  jmp     short loc_1400112A3
0x14001125b  mov     rdx, rbx
0x14001125e  mov     rcx, [rsp+48h+hObject]; TokenHandle
0x140011263  call    ?UtilGetTokenUserSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z; UtilGetTokenUserSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)
0x140011268  mov     ebx, eax
0x14001126a  test    eax, eax
0x14001126c  jns     short loc_1400112A1
0x14001126e  lea     rax, WPP_GLOBAL_Control
0x140011275  mov     rcx, cs:WPP_GLOBAL_Control
0x14001127c  cmp     rcx, rax
0x14001127f  jz      short loc_1400112A3
0x140011281  test    byte ptr [rcx+1Ch], 1
0x140011285  jz      short loc_1400112A3
0x140011287  mov     edx, 11h
0x14001128c  mov     r9d, ebx
0x14001128f  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x140011296  mov     rcx, [rcx+10h]
0x14001129a  call    WPP_SF_d
0x14001129f  jmp     short loc_1400112A3
0x1400112a1  xor     ebx, ebx
0x1400112a3  mov     rcx, [rsp+48h+hObject]; hObject
0x1400112a8  lea     rax, [rcx+1]
0x1400112ac  cmp     rax, 1
0x1400112b0  jbe     short loc_1400112B8
0x1400112b2  call    cs:__imp_CloseHandle
0x1400112b8  mov     eax, ebx
0x1400112ba  mov     rbx, [rsp+48h+arg_0]
0x1400112bf  add     rsp, 40h
0x1400112c3  pop     rdi
0x1400112c4  retn
```
