# UtilGetProcessUserSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)

- ea: `0x18009812c`
- end: `0x180098277`
- name: `?UtilGetProcessUserSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z`
- size: `331`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x18003dbd0`

## callees

- `0x180004bb4`
- `0x18000716c`
- `0x180007e10`
- `0x18001fe24`
- `0x180049310`
- `0x18004acbc`
- `0x18009812c`
- `0x180098544`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800981a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800981a0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800981c0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800981c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800981d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800981d6`

## pseudocode

```c
__int64 __fastcall UtilGetProcessUserSid(HANDLE ProcessHandle, void **a2)
{
  unsigned int TokenUserSid; // ebx
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
      TokenUserSid = UtilGetTokenUserSid(TokenHandle, a2);
      if ( (TokenUserSid & 0x80000000) == 0 )
      {
        TokenUserSid = 0;
      }
      else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_988ce82756cb3ec502560a762615dae0_Traceguids, TokenUserSid);
      }
    }
    else
    {
      LastError = GetLastError();
      TokenUserSid = ERROR_HR_FROM_WIN32(LastError);
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_988ce82756cb3ec502560a762615dae0_Traceguids, TokenUserSid);
    }
  }
  else
  {
    TokenUserSid = -2147024809;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&TokenHandle);
  return TokenUserSid;
}

```

## disassembly

```asm
0x18009812c  mov     [rsp+arg_0], rbx
0x180098131  push    rdi
0x180098132  sub     rsp, 40h
0x180098136  mov     rdi, rdx
0x180098139  mov     rbx, rcx
0x18009813c  mov     [rsp+48h+TokenHandle], 0
0x180098145  test    rdx, rdx
0x180098148  jnz     short loc_180098188
0x18009814a  mov     ebx, 80070057h
0x18009814f  lea     rax, WPP_GLOBAL_Control
0x180098156  mov     rcx, cs:WPP_GLOBAL_Control
0x18009815d  cmp     rcx, rax
0x180098160  jz      loc_180098260
0x180098166  test    byte ptr [rcx+1Ch], 1
0x18009816a  jz      loc_180098260
0x180098170  lea     edx, [rdi+0Fh]
0x180098173  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18009817a  mov     rcx, [rcx+10h]
0x18009817e  call    WPP_SF_
0x180098183  jmp     loc_180098260
0x180098188  mov     r8, [rdx]; lpMem
0x18009818b  mov     qword ptr [rdx], 0
0x180098192  test    r8, r8
0x180098195  jz      short loc_1800981A6
0x180098197  xor     edx, edx; dwFlags
0x180098199  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x1800981a0  call    cs:__imp_HeapFree
0x1800981a6  lea     rdx, [rsp+48h+TokenHandle]
0x1800981ab  lea     rcx, [rsp+48h+var_28]
0x1800981b0  call    ??$out_ptr@XV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@$$V@utl@@YA?A_PAEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z
0x1800981b5  mov     r8, rax; TokenHandle
0x1800981b8  mov     edx, 8; DesiredAccess
0x1800981bd  mov     rcx, rbx; ProcessHandle
0x1800981c0  call    cs:__imp_OpenProcessToken
0x1800981c6  mov     ebx, eax
0x1800981c8  lea     rcx, [rsp+48h+var_28]
0x1800981cd  call    ??1?$out_ptr_t@V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEAX$$V@utl@@QEAA@XZ; utl::out_ptr_t<tlx::unique_any<tlx::file_handle_traits>,void *,>::~out_ptr_t<tlx::unique_any<tlx::file_handle_traits>,void *,>(void)
0x1800981d2  test    ebx, ebx
0x1800981d4  jnz     short loc_180098218
0x1800981d6  call    cs:__imp_GetLastError
0x1800981dc  mov     ecx, eax; unsigned int
0x1800981de  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800981e3  mov     ebx, eax
0x1800981e5  lea     rax, WPP_GLOBAL_Control
0x1800981ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800981f3  cmp     rcx, rax
0x1800981f6  jz      short loc_180098260
0x1800981f8  test    byte ptr [rcx+1Ch], 1
0x1800981fc  jz      short loc_180098260
0x1800981fe  mov     edx, 10h
0x180098203  mov     r9d, ebx
0x180098206  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18009820d  mov     rcx, [rcx+10h]
0x180098211  call    WPP_SF_d
0x180098216  jmp     short loc_180098260
0x180098218  mov     rdx, rdi
0x18009821b  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x180098220  call    ?UtilGetTokenUserSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z; UtilGetTokenUserSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)
0x180098225  mov     ebx, eax
0x180098227  test    eax, eax
0x180098229  jns     short loc_18009825E
0x18009822b  lea     rax, WPP_GLOBAL_Control
0x180098232  mov     rcx, cs:WPP_GLOBAL_Control
0x180098239  cmp     rcx, rax
0x18009823c  jz      short loc_180098260
0x18009823e  test    byte ptr [rcx+1Ch], 1
0x180098242  jz      short loc_180098260
0x180098244  mov     edx, 11h
0x180098249  mov     r9d, ebx
0x18009824c  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x180098253  mov     rcx, [rcx+10h]
0x180098257  call    WPP_SF_d
0x18009825c  jmp     short loc_180098260
0x18009825e  xor     ebx, ebx
0x180098260  lea     rcx, [rsp+48h+TokenHandle]
0x180098265  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18009826a  mov     eax, ebx
0x18009826c  mov     rbx, [rsp+48h+arg_0]
0x180098271  add     rsp, 40h
0x180098275  pop     rdi
0x180098276  retn
```
