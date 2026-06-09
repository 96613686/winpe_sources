# UtilGetProcessAppContainerPackageSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)

- ea: `0x180097ce0`
- end: `0x180097e2b`
- name: `?UtilGetProcessAppContainerPackageSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z`
- size: `331`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003d990`
- `0x180066d40`

## callees

- `0x180004bb4`
- `0x18000716c`
- `0x180007e10`
- `0x18001fe24`
- `0x180049310`
- `0x18004acbc`
- `0x180097ce0`
- `0x1800982d0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180097d54`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180097d54`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180097d74`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180097d74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097d8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097d8a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UtilGetProcessAppContainerPackageSid(HANDLE ProcessHandle, void **a2)
{
  unsigned int TokenAppContainerPackageSid; // ebx
  void *v5; // r8
  void **v6; // rax
  BOOL v7; // ebx
  DWORD LastError; // eax
  _BYTE v10[40]; // [rsp+20h] [rbp-28h] BYREF
  HANDLE TokenHandle; // [rsp+58h] [rbp+10h] BYREF

  TokenHandle = 0;
  if ( a2 )
  {
    v5 = *a2;
    *a2 = 0;
    if ( v5 )
      HeapFree(g_hWerheap, 0, v5);
    v6 = (void **)utl::out_ptr<void,tlx::unique_any<tlx::file_handle_traits>,>(v10, &TokenHandle);
    v7 = OpenProcessToken(ProcessHandle, 8u, v6);
    utl::out_ptr_t<tlx::unique_any<tlx::file_handle_traits>,void *,>::~out_ptr_t<tlx::unique_any<tlx::file_handle_traits>,void *,>(v10);
    if ( v7 )
    {
      TokenAppContainerPackageSid = UtilGetTokenAppContainerPackageSid(TokenHandle, a2);
      if ( (TokenAppContainerPackageSid & 0x80000000) == 0 )
      {
        TokenAppContainerPackageSid = 0;
      }
      else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          WPP_988ce82756cb3ec502560a762615dae0_Traceguids,
          TokenAppContainerPackageSid);
      }
    }
    else
    {
      LastError = GetLastError();
      TokenAppContainerPackageSid = ERROR_HR_FROM_WIN32(LastError);
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          26,
          WPP_988ce82756cb3ec502560a762615dae0_Traceguids,
          TokenAppContainerPackageSid);
    }
  }
  else
  {
    TokenAppContainerPackageSid = -2147024809;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&TokenHandle);
  return TokenAppContainerPackageSid;
}

```

## disassembly

```asm
0x180097ce0  mov     [rsp+arg_0], rbx
0x180097ce5  push    rdi
0x180097ce6  sub     rsp, 40h
0x180097cea  mov     rdi, rdx
0x180097ced  mov     rbx, rcx
0x180097cf0  mov     [rsp+48h+TokenHandle], 0
0x180097cf9  test    rdx, rdx
0x180097cfc  jnz     short loc_180097D3C
0x180097cfe  mov     ebx, 80070057h
0x180097d03  lea     rax, WPP_GLOBAL_Control
0x180097d0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180097d11  cmp     rcx, rax
0x180097d14  jz      loc_180097E14
0x180097d1a  test    byte ptr [rcx+1Ch], 1
0x180097d1e  jz      loc_180097E14
0x180097d24  lea     edx, [rdi+19h]
0x180097d27  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x180097d2e  mov     rcx, [rcx+10h]
0x180097d32  call    WPP_SF_
0x180097d37  jmp     loc_180097E14
0x180097d3c  mov     r8, [rdx]; lpMem
0x180097d3f  mov     qword ptr [rdx], 0
0x180097d46  test    r8, r8
0x180097d49  jz      short loc_180097D5A
0x180097d4b  xor     edx, edx; dwFlags
0x180097d4d  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x180097d54  call    cs:__imp_HeapFree
0x180097d5a  lea     rdx, [rsp+48h+TokenHandle]
0x180097d5f  lea     rcx, [rsp+48h+var_28]
0x180097d64  call    ??$out_ptr@XV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@$$V@utl@@YA?A_PAEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z
0x180097d69  mov     r8, rax; TokenHandle
0x180097d6c  mov     edx, 8; DesiredAccess
0x180097d71  mov     rcx, rbx; ProcessHandle
0x180097d74  call    cs:__imp_OpenProcessToken
0x180097d7a  mov     ebx, eax
0x180097d7c  lea     rcx, [rsp+48h+var_28]
0x180097d81  call    ??1?$out_ptr_t@V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEAX$$V@utl@@QEAA@XZ; utl::out_ptr_t<tlx::unique_any<tlx::file_handle_traits>,void *,>::~out_ptr_t<tlx::unique_any<tlx::file_handle_traits>,void *,>(void)
0x180097d86  test    ebx, ebx
0x180097d88  jnz     short loc_180097DCC
0x180097d8a  call    cs:__imp_GetLastError
0x180097d90  mov     ecx, eax; unsigned int
0x180097d92  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180097d97  mov     ebx, eax
0x180097d99  lea     rax, WPP_GLOBAL_Control
0x180097da0  mov     rcx, cs:WPP_GLOBAL_Control
0x180097da7  cmp     rcx, rax
0x180097daa  jz      short loc_180097E14
0x180097dac  test    byte ptr [rcx+1Ch], 1
0x180097db0  jz      short loc_180097E14
0x180097db2  mov     edx, 1Ah
0x180097db7  mov     r9d, ebx
0x180097dba  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x180097dc1  mov     rcx, [rcx+10h]
0x180097dc5  call    WPP_SF_d
0x180097dca  jmp     short loc_180097E14
0x180097dcc  mov     rdx, rdi
0x180097dcf  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x180097dd4  call    ?UtilGetTokenAppContainerPackageSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z; UtilGetTokenAppContainerPackageSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)
0x180097dd9  mov     ebx, eax
0x180097ddb  test    eax, eax
0x180097ddd  jns     short loc_180097E12
0x180097ddf  lea     rax, WPP_GLOBAL_Control
0x180097de6  mov     rcx, cs:WPP_GLOBAL_Control
0x180097ded  cmp     rcx, rax
0x180097df0  jz      short loc_180097E14
0x180097df2  test    byte ptr [rcx+1Ch], 1
0x180097df6  jz      short loc_180097E14
0x180097df8  mov     edx, 1Bh
0x180097dfd  mov     r9d, ebx
0x180097e00  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x180097e07  mov     rcx, [rcx+10h]
0x180097e0b  call    WPP_SF_d
0x180097e10  jmp     short loc_180097E14
0x180097e12  xor     ebx, ebx
0x180097e14  lea     rcx, [rsp+48h+TokenHandle]
0x180097e19  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180097e1e  mov     eax, ebx
0x180097e20  mov     rbx, [rsp+48h+arg_0]
0x180097e25  add     rsp, 40h
0x180097e29  pop     rdi
0x180097e2a  retn
```
