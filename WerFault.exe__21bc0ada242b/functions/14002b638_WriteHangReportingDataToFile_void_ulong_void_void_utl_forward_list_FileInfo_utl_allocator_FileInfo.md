# WriteHangReportingDataToFile(void *,ulong,void *,void *,utl::forward_list<FileInfo,utl::allocator<FileInfo>> &)

- ea: `0x14002b638`
- end: `0x14002bb40`
- name: `?WriteHangReportingDataToFile@@YAJPEAXK00AEAV?$forward_list@UFileInfo@@V?$allocator@UFileInfo@@@utl@@@utl@@@Z`
- size: `1288`
- prototype: `__int64 __fastcall(char *, __int64, void *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation`

## callers

- `0x140027f00`

## callees

- `0x140002470`
- `0x140002494`
- `0x140002728`
- `0x1400030a8`
- `0x140004198`
- `0x14001444c`
- `0x140014474`
- `0x14002b494`
- `0x14002b638`
- `0x14002c4b4`
- `0x14002c91c`
- `0x14002caa4`
- `0x14002d8f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b693`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b742`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b7e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b7f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b693`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b742`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b7e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b7f9`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14002b686`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14002b686`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002b79a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002b843`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002b79a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002b843`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32Next` at `0x14002b7dd`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32Next` at `0x14002b7dd`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32First` at `0x14002b738`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32First` at `0x14002b738`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x14002b711`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x14002b711`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WriteHangReportingDataToFile(char *a1, __int64 a2, void *a3)
{
  DWORD ProcessId; // r12d
  signed int v5; // eax
  unsigned int v6; // ebx
  char *v8; // r14
  HANDLE Toolhelp32Snapshot; // rsi
  signed int v10; // eax
  const struct std::nothrow_t *v11; // rdx
  _DWORD *v12; // rax
  signed int LastError; // eax
  char *v14; // rax
  int v15; // eax
  CUserModeHangReport *v16; // rcx
  __int64 v17; // rdx
  void *v18; // rcx
  unsigned int v19; // esi
  unsigned int i; // ecx
  __int64 v21; // r15
  void **v22; // rbx
  _DWORD *v23; // rcx
  void *v24; // rcx
  unsigned int v25; // [rsp+50h] [rbp-61h] BYREF
  void *v26; // [rsp+58h] [rbp-59h] BYREF
  int v27; // [rsp+60h] [rbp-51h] BYREF
  int v28[2]; // [rsp+68h] [rbp-49h] BYREF
  char *v29; // [rsp+70h] [rbp-41h]
  __m128i si128; // [rsp+78h] [rbp-39h] BYREF
  __int64 v31; // [rsp+88h] [rbp-29h]
  int v32; // [rsp+90h] [rbp-21h]
  __int64 v33; // [rsp+98h] [rbp-19h]
  __int64 v34; // [rsp+A0h] [rbp-11h]
  THREADENTRY32 te; // [rsp+A8h] [rbp-9h] BYREF

  if ( (unsigned __int64)(a1 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && a3 )
  {
    ProcessId = GetProcessId(a3);
    if ( ProcessId )
    {
      si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
      v31 = 0;
      v32 = 0;
      v33 = 0;
      v34 = 0;
      v26 = (void *)-1LL;
      v8 = 0;
      v29 = 0;
      Toolhelp32Snapshot = CreateToolhelp32Snapshot(4u, 0);
      *(_QWORD *)v28 = Toolhelp32Snapshot;
      memset(&te.cntUsage, 0, 24);
      te.dwSize = 28;
      if ( Thread32First(Toolhelp32Snapshot, &te) )
      {
        do
        {
          if ( te.th32OwnerProcessID == ProcessId )
          {
            v12 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
            if ( !v12 )
            {
              v6 = -2147024882;
              if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_1969d98add70354507e1e1f7959b3b3f_Traceguids);
              }
              goto LABEL_16;
            }
            v12[2] = te.th32ThreadID;
            *(_QWORD *)v12 = v26;
            v26 = v12;
          }
        }
        while ( Thread32Next(Toolhelp32Snapshot, &te) );
        if ( GetLastError() != 18 )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              23,
              WPP_1969d98add70354507e1e1f7959b3b3f_Traceguids,
              (unsigned int)LastError);
          }
        }
        if ( (unsigned __int64)Toolhelp32Snapshot + 1 > 1 )
          CloseHandle(Toolhelp32Snapshot);
        if ( v26 == (void *)-1LL )
        {
          v6 = -2147467259;
        }
        else
        {
          v14 = (char *)operator new[](0x1180u, (const struct std::nothrow_t *)&std::nothrow);
          v8 = v14;
          if ( v14 )
            memset_0(v14, 0, 0x1180u);
          else
            v8 = 0;
          v29 = v8;
          if ( v8 )
          {
            v15 = CWCTInfoWriter::Start((CWCTInfoWriter *)&si128, a1);
            v6 = v15;
            if ( v15 >= 0 )
            {
              while ( v26 != (void *)-1LL )
              {
                v25 = 0;
                v27 = 0;
                v28[0] = 0;
                v15 = ChaseThreads(ProcessId, *((unsigned int *)v26 + 2), v8, &v25, &v27, v28);
                v6 = v15;
                if ( v15 < 0 )
                {
                  v16 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  {
                    v17 = 26;
                    goto LABEL_46;
                  }
                  goto LABEL_71;
                }
                v15 = CWCTInfoWriter::WriteNodeInfoToFile((CWCTInfoWriter *)&si128, 0, 0, v28[0], v27, 0);
                v6 = v15;
                if ( v15 < 0 )
                {
                  v16 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  {
                    v17 = 27;
                    goto LABEL_46;
                  }
                  goto LABEL_71;
                }
                v18 = v26;
                v26 = *(void **)v26;
                operator delete(v18, (const struct std::nothrow_t *)&std::nothrow);
                v19 = 0;
                for ( i = v25; v19 < i; ++v19 )
                {
                  v21 = 280LL * v19;
                  if ( *(_DWORD *)&v8[v21] == 8 )
                  {
                    v22 = &v26;
                    while ( 1 )
                    {
                      v23 = *v22;
                      if ( *v22 == (void *)-1LL )
                        break;
                      if ( v23[2] == *(_DWORD *)&v8[v21 + 12] )
                      {
                        *v22 = *(void **)v23;
                        operator delete(v23, (const struct std::nothrow_t *)&std::nothrow);
                      }
                      else
                      {
                        v22 = (void **)*v22;
                      }
                    }
                    i = v25;
                  }
                }
              }
              v15 = CWCTInfoWriter::End((CWCTInfoWriter *)&si128);
              v6 = v15;
              if ( v15 >= 0 )
              {
                v6 = 0;
              }
              else
              {
                v16 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v17 = 28;
                  goto LABEL_46;
                }
              }
            }
            else
            {
              v16 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v17 = 25;
LABEL_46:
                WPP_SF_d(*((_QWORD *)v16 + 2), v17, WPP_1969d98add70354507e1e1f7959b3b3f_Traceguids, (unsigned int)v15);
              }
            }
          }
          else
          {
            v6 = -2147024882;
            if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_1969d98add70354507e1e1f7959b3b3f_Traceguids);
            }
          }
        }
      }
      else
      {
        v10 = GetLastError();
        v6 = v10;
        if ( v10 > 0 )
          v6 = (unsigned __int16)v10 | 0x80070000;
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_1969d98add70354507e1e1f7959b3b3f_Traceguids, v6);
        }
LABEL_16:
        if ( (unsigned __int64)Toolhelp32Snapshot + 1 > 1 )
          CloseHandle(Toolhelp32Snapshot);
      }
LABEL_71:
      if ( v8 )
        operator delete(v8, v11);
      while ( 1 )
      {
        v24 = v26;
        if ( v26 == (void *)-1LL )
          break;
        v26 = *(void **)v26;
        operator delete(v24, (const struct std::nothrow_t *)&std::nothrow);
      }
      CWCTInfoWriter::~CWCTInfoWriter((CWCTInfoWriter *)&si128);
    }
    else
    {
      v5 = GetLastError();
      v6 = v5;
      if ( v5 > 0 )
        v6 = (unsigned __int16)v5 | 0x80070000;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_1969d98add70354507e1e1f7959b3b3f_Traceguids, v6);
      }
    }
    return v6;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_1969d98add70354507e1e1f7959b3b3f_Traceguids);
    }
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x14002b638  mov     [rsp-8+arg_8], rbx
0x14002b63d  push    rbp
0x14002b63e  push    rsi
0x14002b63f  push    rdi
0x14002b640  push    r12
0x14002b642  push    r13
0x14002b644  push    r14
0x14002b646  push    r15
0x14002b648  lea     rbp, [rsp-1Fh]
0x14002b64d  sub     rsp, 0D0h
0x14002b654  mov     rax, cs:__security_cookie
0x14002b65b  xor     rax, rsp
0x14002b65e  mov     [rbp+4Fh+var_38], rax
0x14002b662  mov     rbx, rcx
0x14002b665  mov     r13, [rbp+4Fh+arg_20]
0x14002b669  lea     rax, [rcx-1]
0x14002b66d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14002b671  ja      loc_14002BAE6
0x14002b677  xor     r15d, r15d
0x14002b67a  test    r8, r8
0x14002b67d  jz      loc_14002BAE6
0x14002b683  mov     rcx, r8; Process
0x14002b686  call    cs:__imp_GetProcessId
0x14002b68c  mov     r12d, eax
0x14002b68f  test    eax, eax
0x14002b691  jnz     short loc_14002B6E0
0x14002b693  call    cs:__imp_GetLastError
0x14002b699  mov     ebx, eax
0x14002b69b  test    eax, eax
0x14002b69d  jle     short loc_14002B6A8
0x14002b69f  movzx   ebx, ax
0x14002b6a2  or      ebx, 80070000h
0x14002b6a8  lea     rdi, WPP_GLOBAL_Control
0x14002b6af  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b6b6  cmp     rcx, rdi
0x14002b6b9  jz      short loc_14002B6D9
0x14002b6bb  test    byte ptr [rcx+1Ch], 1
0x14002b6bf  jz      short loc_14002B6D9
0x14002b6c1  mov     edx, 11h
0x14002b6c6  mov     r9d, ebx
0x14002b6c9  lea     r8, WPP_1969d98add70354507e1e1f7959b3b3f_Traceguids
0x14002b6d0  mov     rcx, [rcx+10h]
0x14002b6d4  call    WPP_SF_d
0x14002b6d9  mov     eax, ebx
0x14002b6db  jmp     loc_14002BB19
0x14002b6e0  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14002b6e8  movdqu  [rbp+4Fh+var_88], xmm0
0x14002b6ed  mov     [rbp+4Fh+var_78], r15
0x14002b6f1  mov     [rbp+4Fh+var_70], r15d
0x14002b6f5  mov     [rbp+4Fh+var_68], r15
0x14002b6f9  mov     [rbp+4Fh+var_60], r15
0x14002b6fd  mov     [rbp+4Fh+var_A8], 0FFFFFFFFFFFFFFFFh
0x14002b705  mov     r14, r15
0x14002b708  mov     [rbp+4Fh+var_90], r15
0x14002b70c  xor     edx, edx; th32ProcessID
0x14002b70e  lea     ecx, [rdx+4]; dwFlags
0x14002b711  call    cs:__imp_CreateToolhelp32Snapshot
0x14002b717  mov     rsi, rax
0x14002b71a  mov     qword ptr [rbp+4Fh+var_98], rax
0x14002b71e  xorps   xmm0, xmm0
0x14002b721  movdqu  xmmword ptr [rbp+4Fh+te.cntUsage], xmm0
0x14002b726  mov     qword ptr [rbp+4Fh+te.tpDeltaPri], r15
0x14002b72a  mov     [rbp+4Fh+te.dwSize], 1Ch
0x14002b731  lea     rdx, [rbp+4Fh+te]; lpte
0x14002b735  mov     rcx, rax; hSnapshot
0x14002b738  call    cs:__imp_Thread32First
0x14002b73e  test    eax, eax
0x14002b740  jnz     short loc_14002B7A5
0x14002b742  call    cs:__imp_GetLastError
0x14002b748  mov     ebx, eax
0x14002b74a  test    eax, eax
0x14002b74c  jle     short loc_14002B757
0x14002b74e  movzx   ebx, ax
0x14002b751  or      ebx, 80070000h
0x14002b757  lea     rdi, WPP_GLOBAL_Control
0x14002b75e  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b765  cmp     rcx, rdi
0x14002b768  jz      short loc_14002B789
0x14002b76a  test    byte ptr [rcx+1Ch], 1
0x14002b76e  jz      short loc_14002B789
0x14002b770  mov     edx, 15h
0x14002b775  mov     r9d, ebx
0x14002b778  lea     r8, WPP_1969d98add70354507e1e1f7959b3b3f_Traceguids
0x14002b77f  mov     rcx, [rcx+10h]
0x14002b783  call    WPP_SF_d
0x14002b788  nop
0x14002b789  lea     rax, [rsi+1]
0x14002b78d  cmp     rax, 1
0x14002b791  jbe     loc_14002BAAB
0x14002b797  mov     rcx, rsi; hObject
0x14002b79a  call    cs:__imp_CloseHandle
0x14002b7a0  jmp     loc_14002BAAB
0x14002b7a5  cmp     [rbp+4Fh+te.th32OwnerProcessID], r12d
0x14002b7a9  jnz     short loc_14002B7D6
0x14002b7ab  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002b7b2  mov     ecx, 10h; unsigned __int64
0x14002b7b7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14002b7bc  test    rax, rax
0x14002b7bf  jz      loc_14002B85A
0x14002b7c5  mov     ecx, [rbp+4Fh+te.th32ThreadID]
0x14002b7c8  mov     [rax+8], ecx
0x14002b7cb  mov     rcx, [rbp+4Fh+var_A8]
0x14002b7cf  mov     [rax], rcx
0x14002b7d2  mov     [rbp+4Fh+var_A8], rax
0x14002b7d6  lea     rdx, [rbp+4Fh+te]; lpte
0x14002b7da  mov     rcx, rsi; hSnapshot
0x14002b7dd  call    cs:__imp_Thread32Next
0x14002b7e3  test    eax, eax
0x14002b7e5  jnz     short loc_14002B7A5
0x14002b7e7  call    cs:__imp_GetLastError
0x14002b7ed  lea     rdi, WPP_GLOBAL_Control
0x14002b7f4  cmp     eax, 12h
0x14002b7f7  jz      short loc_14002B836
0x14002b7f9  call    cs:__imp_GetLastError
0x14002b7ff  test    eax, eax
0x14002b801  jle     short loc_14002B80B
0x14002b803  movzx   eax, ax
0x14002b806  or      eax, 80070000h
0x14002b80b  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b812  cmp     rcx, rdi
0x14002b815  jz      short loc_14002B836
0x14002b817  test    byte ptr [rcx+1Ch], 1
0x14002b81b  jz      short loc_14002B836
0x14002b81d  mov     edx, 17h
0x14002b822  mov     r9d, eax
0x14002b825  lea     r8, WPP_1969d98add70354507e1e1f7959b3b3f_Traceguids
0x14002b82c  mov     rcx, [rcx+10h]
0x14002b830  call    WPP_SF_d
0x14002b835  nop
0x14002b836  lea     rax, [rsi+1]
0x14002b83a  cmp     rax, 1
0x14002b83e  jbe     short loc_14002B849
0x14002b840  mov     rcx, rsi; hObject
0x14002b843  call    cs:__imp_CloseHandle
0x14002b849  cmp     [rbp+4Fh+var_A8], 0FFFFFFFFFFFFFFFFh
0x14002b84e  jnz     short loc_14002B89A
0x14002b850  mov     ebx, 80004005h
0x14002b855  jmp     loc_14002BAAB
0x14002b85a  mov     ebx, 8007000Eh
0x14002b85f  lea     rdi, WPP_GLOBAL_Control
0x14002b866  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b86d  cmp     rcx, rdi
0x14002b870  jz      loc_14002B789
0x14002b876  test    byte ptr [rcx+1Ch], 1
0x14002b87a  jz      loc_14002B789
0x14002b880  mov     edx, 16h
0x14002b885  lea     r8, WPP_1969d98add70354507e1e1f7959b3b3f_Traceguids
0x14002b88c  mov     rcx, [rcx+10h]
0x14002b890  call    WPP_SF_
0x14002b895  jmp     loc_14002B789
0x14002b89a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002b8a1  mov     esi, 1180h
0x14002b8a6  mov     ecx, esi; unsigned __int64
0x14002b8a8  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14002b8ad  mov     r14, rax
0x14002b8b0  test    rax, rax
0x14002b8b3  jz      short loc_14002B8C4
0x14002b8b5  mov     r8d, esi; Size
0x14002b8b8  xor     edx, edx; Val
0x14002b8ba  mov     rcx, rax; void *
0x14002b8bd  call    memset_0
0x14002b8c2  jmp     short loc_14002B8C7
0x14002b8c4  mov     r14, r15
0x14002b8c7  mov     [rbp+4Fh+var_90], r14
0x14002b8cb  test    r14, r14
0x14002b8ce  jnz     short loc_14002B908
0x14002b8d0  mov     ebx, 8007000Eh
0x14002b8d5  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b8dc  cmp     rcx, rdi
0x14002b8df  jz      loc_14002BAAB
0x14002b8e5  test    byte ptr [rcx+1Ch], 1
0x14002b8e9  jz      loc_14002BAAB
0x14002b8ef  lea     edx, [r14+18h]
0x14002b8f3  lea     r8, WPP_1969d98add70354507e1e1f7959b3b3f_Traceguids
0x14002b8fa  mov     rcx, [rcx+10h]
0x14002b8fe  call    WPP_SF_
0x14002b903  jmp     loc_14002BAAB
0x14002b908  mov     rdx, rbx; void *
0x14002b90b  lea     rcx, [rbp+4Fh+var_88]; this
0x14002b90f  call    ?Start@CWCTInfoWriter@@QEAAJPEAX@Z; CWCTInfoWriter::Start(void *)
0x14002b914  mov     ebx, eax
0x14002b916  test    eax, eax
0x14002b918  jns     short loc_14002B951
0x14002b91a  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b921  cmp     rcx, rdi
0x14002b924  jz      loc_14002BAAB
0x14002b92a  test    byte ptr [rcx+1Ch], 1
0x14002b92e  jz      loc_14002BAAB
0x14002b934  mov     edx, 19h
0x14002b939  mov     r9d, eax
0x14002b93c  lea     r8, WPP_1969d98add70354507e1e1f7959b3b3f_Traceguids
0x14002b943  mov     rcx, [rcx+10h]
0x14002b947  call    WPP_SF_d
0x14002b94c  jmp     loc_14002BAAB
0x14002b951  mov     rdx, [rbp+4Fh+var_A8]
0x14002b955  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x14002b959  jz      loc_14002BA7D
0x14002b95f  mov     [rbp+4Fh+var_B0], r15d
0x14002b963  mov     [rbp+4Fh+var_A0], r15d
0x14002b967  mov     [rbp+4Fh+var_98], r15d
0x14002b96b  lea     rax, [rbp+4Fh+var_98]
0x14002b96f  mov     qword ptr [rsp+100h+var_D8], rax
0x14002b974  lea     rax, [rbp+4Fh+var_A0]
0x14002b978  mov     [rsp+100h+var_E0], rax
0x14002b97d  lea     r9, [rbp+4Fh+var_B0]
0x14002b981  mov     r8, r14
0x14002b984  mov     edx, [rdx+8]
0x14002b987  mov     ecx, r12d
0x14002b98a  call    ChaseThreads
0x14002b98f  mov     ebx, eax
0x14002b991  test    eax, eax
0x14002b993  js      loc_14002BA61
0x14002b999  mov     eax, [rbp+4Fh+var_A0]
0x14002b99c  mov     [rsp+100h+var_C0], r15; struct SharedHangRepData *
0x14002b9a1  mov     [rsp+100h+var_C8], eax; int
0x14002b9a5  mov     eax, [rbp+4Fh+var_98]
0x14002b9a8  mov     [rsp+100h+var_D0], eax; int
0x14002b9ac  mov     [rsp+100h+var_D8], r15d; unsigned int
0x14002b9b1  mov     [rsp+100h+var_E0], r15; void **
0x14002b9b6  mov     r9, r13
0x14002b9b9  mov     r8d, [rbp+4Fh+var_B0]
0x14002b9bd  mov     rdx, r14
0x14002b9c0  lea     rcx, [rbp+4Fh+var_88]; this
0x14002b9c4  call    ?WriteNodeInfoToFile@CWCTInfoWriter@@QEAAJPEAU_WAITCHAIN_NODE_INFO@@IAEAV?$forward_list@UFileInfo@@V?$allocator@UFileInfo@@@utl@@@utl@@PEAPEAXKHHPEAUSharedHangRepData@@@Z; CWCTInfoWriter::WriteNodeInfoToFile(_WAITCHAIN_NODE_INFO *,uint,utl::forward_list<FileInfo,utl::allocator<FileInfo>> &,void * *,ulong,int,int,SharedHangRepData *)
0x14002b9c9  mov     ebx, eax
0x14002b9cb  test    eax, eax
0x14002b9cd  js      short loc_14002BA45
0x14002b9cf  mov     rcx, [rbp+4Fh+var_A8]; void *
0x14002b9d3  mov     rax, [rcx]
0x14002b9d6  mov     [rbp+4Fh+var_A8], rax
0x14002b9da  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002b9e1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002b9e6  mov     esi, r15d
0x14002b9e9  mov     ecx, [rbp+4Fh+var_B0]
0x14002b9ec  test    ecx, ecx
0x14002b9ee  jz      loc_14002B951
0x14002b9f4  mov     eax, esi
0x14002b9f6  imul    r15, rax, 118h
0x14002b9fd  cmp     dword ptr [r15+r14], 8
0x14002ba02  jnz     short loc_14002BA37
0x14002ba04  lea     rbx, [rbp+4Fh+var_A8]
0x14002ba08  mov     rcx, [rbx]; void *
0x14002ba0b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14002ba0f  jz      short loc_14002BA34
0x14002ba11  mov     eax, [r15+r14+0Ch]
0x14002ba16  cmp     [rcx+8], eax
0x14002ba19  jnz     short loc_14002BA2F
0x14002ba1b  mov     rax, [rcx]
0x14002ba1e  mov     [rbx], rax
0x14002ba21  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002ba28  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002ba2d  jmp     short loc_14002BA08
0x14002ba2f  mov     rbx, rcx
0x14002ba32  jmp     short loc_14002BA08
0x14002ba34  mov     ecx, [rbp+4Fh+var_B0]
0x14002ba37  inc     esi
0x14002ba39  cmp     esi, ecx
0x14002ba3b  jb      short loc_14002B9F4
0x14002ba3d  xor     r15d, r15d
0x14002ba40  jmp     loc_14002B951
0x14002ba45  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ba4c  cmp     rcx, rdi
0x14002ba4f  jz      short loc_14002BAAB
0x14002ba51  test    byte ptr [rcx+1Ch], 2
0x14002ba55  jz      short loc_14002BAAB
0x14002ba57  mov     edx, 1Bh
0x14002ba5c  jmp     loc_14002B939
0x14002ba61  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ba68  cmp     rcx, rdi
0x14002ba6b  jz      short loc_14002BAAB
0x14002ba6d  test    byte ptr [rcx+1Ch], 1
0x14002ba71  jz      short loc_14002BAAB
0x14002ba73  mov     edx, 1Ah
0x14002ba78  jmp     loc_14002B939
0x14002ba7d  lea     rcx, [rbp+4Fh+var_88]; this
0x14002ba81  call    ?End@CWCTInfoWriter@@QEAAJXZ; CWCTInfoWriter::End(void)
0x14002ba86  mov     ebx, eax
0x14002ba88  test    eax, eax
0x14002ba8a  jns     short loc_14002BAA8
0x14002ba8c  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ba93  cmp     rcx, rdi
0x14002ba96  jz      short loc_14002BAAB
0x14002ba98  test    byte ptr [rcx+1Ch], 1
0x14002ba9c  jz      short loc_14002BAAB
0x14002ba9e  mov     edx, 1Ch
0x14002baa3  jmp     loc_14002B939
0x14002baa8  mov     ebx, r15d
0x14002baab  test    r14, r14
0x14002baae  jz      short loc_14002BAB9
0x14002bab0  mov     rcx, r14; void *
0x14002bab3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002bab8  nop
0x14002bab9  mov     rcx, [rbp+4Fh+var_A8]; void *
0x14002babd  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14002bac1  jz      short loc_14002BAD8
0x14002bac3  mov     rax, [rcx]
0x14002bac6  mov     [rbp+4Fh+var_A8], rax
0x14002baca  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002bad1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002bad6  jmp     short loc_14002BAB9
  ... truncated ...
```
