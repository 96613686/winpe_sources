# UtilGetProcessUserSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)

- ea: `0x14001186c`
- end: `0x1400119fe`
- name: `?UtilGetProcessUserSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z`
- size: `402`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation`

## callers

- `0x140016e8c`
- `0x140048748`

## callees

- `0x140002748`
- `0x14000e6d8`
- `0x14001186c`
- `0x140011d64`
- `0x140014ee4`
- `0x140014f14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011935`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011935`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400118f8`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400118f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140011925`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400119e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140011925`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400119e4`

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
          WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids,
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
          WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids,
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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids);
    }
  }
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  return (unsigned int)TokenUserSid;
}

```

## disassembly

```asm
0x14001186c  mov     [rsp+arg_0], rbx
0x140011871  push    rdi
0x140011872  sub     rsp, 40h
0x140011876  mov     rbx, rdx
0x140011879  mov     rdi, rcx
0x14001187c  mov     [rsp+48h+hObject], 0
0x140011885  test    rdx, rdx
0x140011888  jnz     short loc_1400118CA
0x14001188a  mov     ebx, 80070057h
0x14001188f  lea     rax, WPP_GLOBAL_Control
0x140011896  mov     rcx, cs:WPP_GLOBAL_Control
0x14001189d  cmp     rcx, rax
0x1400118a0  jz      loc_1400119D5
0x1400118a6  test    byte ptr [rcx+1Ch], 1
0x1400118aa  jz      loc_1400119D5
0x1400118b0  mov     edx, 0Fh
0x1400118b5  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x1400118bc  mov     rcx, [rcx+10h]
0x1400118c0  call    WPP_SF_
0x1400118c5  jmp     loc_1400119D5
0x1400118ca  mov     rcx, [rdx]; void *
0x1400118cd  mov     qword ptr [rdx], 0
0x1400118d4  test    rcx, rcx
0x1400118d7  jz      short loc_1400118DE
0x1400118d9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400118de  lea     rdx, [rsp+48h+hObject]
0x1400118e3  lea     rcx, [rsp+48h+var_28]
0x1400118e8  call    ??$out_ptr@XV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@$$V@utl@@YA?A_PAEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z
0x1400118ed  mov     r8, rax; TokenHandle
0x1400118f0  mov     edx, 8; DesiredAccess
0x1400118f5  mov     rcx, rdi; ProcessHandle
0x1400118f8  call    cs:__imp_OpenProcessToken
0x1400118ff  nop     dword ptr [rax+rax+00h]
0x140011904  mov     edi, eax
0x140011906  mov     r8, [rsp+48h+var_28]
0x14001190b  test    r8, r8
0x14001190e  jz      short loc_140011931
0x140011910  mov     rdx, [rsp+48h+var_20]
0x140011915  mov     rcx, [rdx]; hObject
0x140011918  mov     [rdx], r8
0x14001191b  lea     rdx, [rcx+1]
0x14001191f  cmp     rdx, 1
0x140011923  jbe     short loc_140011931
0x140011925  call    cs:__imp_CloseHandle
0x14001192c  nop     dword ptr [rax+rax+00h]
0x140011931  test    edi, edi
0x140011933  jnz     short loc_14001198D
0x140011935  call    cs:__imp_GetLastError
0x14001193c  nop     dword ptr [rax+rax+00h]
0x140011941  mov     ebx, eax
0x140011943  test    eax, eax
0x140011945  jle     short loc_140011950
0x140011947  movzx   ebx, ax
0x14001194a  or      ebx, 80070000h
0x140011950  mov     eax, 80004005h
0x140011955  test    ebx, ebx
0x140011957  cmovns  ebx, eax
0x14001195a  lea     rax, WPP_GLOBAL_Control
0x140011961  mov     rcx, cs:WPP_GLOBAL_Control
0x140011968  cmp     rcx, rax
0x14001196b  jz      short loc_1400119D5
0x14001196d  test    byte ptr [rcx+1Ch], 1
0x140011971  jz      short loc_1400119D5
0x140011973  mov     edx, 10h
0x140011978  mov     r9d, ebx
0x14001197b  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x140011982  mov     rcx, [rcx+10h]
0x140011986  call    WPP_SF_d
0x14001198b  jmp     short loc_1400119D5
0x14001198d  mov     rdx, rbx
0x140011990  mov     rcx, [rsp+48h+hObject]; TokenHandle
0x140011995  call    ?UtilGetTokenUserSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z; UtilGetTokenUserSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)
0x14001199a  mov     ebx, eax
0x14001199c  test    eax, eax
0x14001199e  jns     short loc_1400119D3
0x1400119a0  lea     rax, WPP_GLOBAL_Control
0x1400119a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400119ae  cmp     rcx, rax
0x1400119b1  jz      short loc_1400119D5
0x1400119b3  test    byte ptr [rcx+1Ch], 1
0x1400119b7  jz      short loc_1400119D5
0x1400119b9  mov     edx, 11h
0x1400119be  mov     r9d, ebx
0x1400119c1  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x1400119c8  mov     rcx, [rcx+10h]
0x1400119cc  call    WPP_SF_d
0x1400119d1  jmp     short loc_1400119D5
0x1400119d3  xor     ebx, ebx
0x1400119d5  mov     rcx, [rsp+48h+hObject]; hObject
0x1400119da  lea     rax, [rcx+1]
0x1400119de  cmp     rax, 1
0x1400119e2  jbe     short loc_1400119F0
0x1400119e4  call    cs:__imp_CloseHandle
0x1400119eb  nop     dword ptr [rax+rax+00h]
0x1400119f0  mov     eax, ebx
0x1400119f2  mov     rbx, [rsp+48h+arg_0]
0x1400119f7  add     rsp, 40h
0x1400119fb  pop     rdi
0x1400119fc  retn
```
