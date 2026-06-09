# WriteHangReportingDataToFile(void *,ulong,void *,void *,utl::forward_list<FileInfo,utl::allocator<FileInfo>> &)

- ea: `0x14002d318`
- end: `0x14002d85d`
- name: `?WriteHangReportingDataToFile@@YAJPEAXK00AEAV?$forward_list@UFileInfo@@V?$allocator@UFileInfo@@@utl@@@utl@@@Z`
- size: `1349`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation`

## callers

- `0x140029940`

## callees

- `0x140002490`
- `0x1400024b4`
- `0x140002748`
- `0x1400030f8`
- `0x1400041e8`
- `0x140014ee4`
- `0x140014f14`
- `0x14002d150`
- `0x14002d318`
- `0x14002e288`
- `0x14002e704`
- `0x14002e8a0`
- `0x14002f70c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d379`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d43a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d4f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d509`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d379`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d43a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d4f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d509`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14002d366`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14002d366`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002d498`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002d559`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002d498`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002d559`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32Next` at `0x14002d4e1`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32Next` at `0x14002d4e1`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32First` at `0x14002d42a`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32First` at `0x14002d42a`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x14002d3fd`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x14002d3fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
0x14002d318  mov     [rsp-8+arg_8], rbx
0x14002d31d  push    rbp
0x14002d31e  push    rsi
0x14002d31f  push    rdi
0x14002d320  push    r12
0x14002d322  push    r13
0x14002d324  push    r14
0x14002d326  push    r15
0x14002d328  lea     rbp, [rsp-1Fh]
0x14002d32d  sub     rsp, 0D0h
0x14002d334  mov     rax, cs:__security_cookie
0x14002d33b  xor     rax, rsp
0x14002d33e  mov     [rbp+4Fh+var_38], rax
0x14002d342  mov     rbx, rcx
0x14002d345  mov     r13, [rbp+4Fh+arg_20]
0x14002d349  lea     rax, [rcx-1]
0x14002d34d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14002d351  ja      loc_14002D802
0x14002d357  xor     r15d, r15d
0x14002d35a  test    r8, r8
0x14002d35d  jz      loc_14002D802
0x14002d363  mov     rcx, r8; Process
0x14002d366  call    cs:__imp_GetProcessId
0x14002d36d  nop     dword ptr [rax+rax+00h]
0x14002d372  mov     r12d, eax
0x14002d375  test    eax, eax
0x14002d377  jnz     short loc_14002D3CC
0x14002d379  call    cs:__imp_GetLastError
0x14002d380  nop     dword ptr [rax+rax+00h]
0x14002d385  mov     ebx, eax
0x14002d387  test    eax, eax
0x14002d389  jle     short loc_14002D394
0x14002d38b  movzx   ebx, ax
0x14002d38e  or      ebx, 80070000h
0x14002d394  lea     rdi, WPP_GLOBAL_Control
0x14002d39b  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d3a2  cmp     rcx, rdi
0x14002d3a5  jz      short loc_14002D3C5
0x14002d3a7  test    byte ptr [rcx+1Ch], 1
0x14002d3ab  jz      short loc_14002D3C5
0x14002d3ad  mov     edx, 11h
0x14002d3b2  mov     r9d, ebx
0x14002d3b5  lea     r8, WPP_1969d98add70354507e1e1f7959b3b3f_Traceguids
0x14002d3bc  mov     rcx, [rcx+10h]
0x14002d3c0  call    WPP_SF_d
0x14002d3c5  mov     eax, ebx
0x14002d3c7  jmp     loc_14002D835
0x14002d3cc  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14002d3d4  movdqu  [rbp+4Fh+var_88], xmm0
0x14002d3d9  mov     [rbp+4Fh+var_78], r15
0x14002d3dd  mov     [rbp+4Fh+var_70], r15d
0x14002d3e1  mov     [rbp+4Fh+var_68], r15
0x14002d3e5  mov     [rbp+4Fh+var_60], r15
0x14002d3e9  mov     [rbp+4Fh+var_A8], 0FFFFFFFFFFFFFFFFh
0x14002d3f1  mov     r14, r15
0x14002d3f4  mov     [rbp+4Fh+var_90], r15
0x14002d3f8  xor     edx, edx; th32ProcessID
0x14002d3fa  lea     ecx, [rdx+4]; dwFlags
0x14002d3fd  call    cs:__imp_CreateToolhelp32Snapshot
0x14002d404  nop     dword ptr [rax+rax+00h]
0x14002d409  mov     rsi, rax
0x14002d40c  mov     qword ptr [rbp+4Fh+var_98], rax
0x14002d410  xorps   xmm0, xmm0
0x14002d413  movdqu  xmmword ptr [rbp+4Fh+te.cntUsage], xmm0
0x14002d418  mov     qword ptr [rbp+4Fh+te.tpDeltaPri], r15
0x14002d41c  mov     [rbp+4Fh+te.dwSize], 1Ch
0x14002d423  lea     rdx, [rbp+4Fh+te]; lpte
0x14002d427  mov     rcx, rax; hSnapshot
0x14002d42a  call    cs:__imp_Thread32First
0x14002d431  nop     dword ptr [rax+rax+00h]
0x14002d436  test    eax, eax
0x14002d438  jnz     short loc_14002D4A9
0x14002d43a  call    cs:__imp_GetLastError
0x14002d441  nop     dword ptr [rax+rax+00h]
0x14002d446  mov     ebx, eax
0x14002d448  test    eax, eax
0x14002d44a  jle     short loc_14002D455
0x14002d44c  movzx   ebx, ax
0x14002d44f  or      ebx, 80070000h
0x14002d455  lea     rdi, WPP_GLOBAL_Control
0x14002d45c  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d463  cmp     rcx, rdi
0x14002d466  jz      short loc_14002D487
0x14002d468  test    byte ptr [rcx+1Ch], 1
0x14002d46c  jz      short loc_14002D487
0x14002d46e  mov     edx, 15h
0x14002d473  mov     r9d, ebx
0x14002d476  lea     r8, WPP_1969d98add70354507e1e1f7959b3b3f_Traceguids
0x14002d47d  mov     rcx, [rcx+10h]
0x14002d481  call    WPP_SF_d
0x14002d486  nop
0x14002d487  lea     rax, [rsi+1]
0x14002d48b  cmp     rax, 1
0x14002d48f  jbe     loc_14002D7C7
0x14002d495  mov     rcx, rsi; hObject
0x14002d498  call    cs:__imp_CloseHandle
0x14002d49f  nop     dword ptr [rax+rax+00h]
0x14002d4a4  jmp     loc_14002D7C7
0x14002d4a9  cmp     [rbp+4Fh+te.th32OwnerProcessID], r12d
0x14002d4ad  jnz     short loc_14002D4DA
0x14002d4af  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002d4b6  mov     ecx, 10h; unsigned __int64
0x14002d4bb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14002d4c0  test    rax, rax
0x14002d4c3  jz      loc_14002D576
0x14002d4c9  mov     ecx, [rbp+4Fh+te.th32ThreadID]
0x14002d4cc  mov     [rax+8], ecx
0x14002d4cf  mov     rcx, [rbp+4Fh+var_A8]
0x14002d4d3  mov     [rax], rcx
0x14002d4d6  mov     [rbp+4Fh+var_A8], rax
0x14002d4da  lea     rdx, [rbp+4Fh+te]; lpte
0x14002d4de  mov     rcx, rsi; hSnapshot
0x14002d4e1  call    cs:__imp_Thread32Next
0x14002d4e8  nop     dword ptr [rax+rax+00h]
0x14002d4ed  test    eax, eax
0x14002d4ef  jnz     short loc_14002D4A9
0x14002d4f1  call    cs:__imp_GetLastError
0x14002d4f8  nop     dword ptr [rax+rax+00h]
0x14002d4fd  lea     rdi, WPP_GLOBAL_Control
0x14002d504  cmp     eax, 12h
0x14002d507  jz      short loc_14002D54C
0x14002d509  call    cs:__imp_GetLastError
0x14002d510  nop     dword ptr [rax+rax+00h]
0x14002d515  test    eax, eax
0x14002d517  jle     short loc_14002D521
0x14002d519  movzx   eax, ax
0x14002d51c  or      eax, 80070000h
0x14002d521  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d528  cmp     rcx, rdi
0x14002d52b  jz      short loc_14002D54C
0x14002d52d  test    byte ptr [rcx+1Ch], 1
0x14002d531  jz      short loc_14002D54C
0x14002d533  mov     edx, 17h
0x14002d538  mov     r9d, eax
0x14002d53b  lea     r8, WPP_1969d98add70354507e1e1f7959b3b3f_Traceguids
0x14002d542  mov     rcx, [rcx+10h]
0x14002d546  call    WPP_SF_d
0x14002d54b  nop
0x14002d54c  lea     rax, [rsi+1]
0x14002d550  cmp     rax, 1
0x14002d554  jbe     short loc_14002D565
0x14002d556  mov     rcx, rsi; hObject
0x14002d559  call    cs:__imp_CloseHandle
0x14002d560  nop     dword ptr [rax+rax+00h]
0x14002d565  cmp     [rbp+4Fh+var_A8], 0FFFFFFFFFFFFFFFFh
0x14002d56a  jnz     short loc_14002D5B6
0x14002d56c  mov     ebx, 80004005h
0x14002d571  jmp     loc_14002D7C7
0x14002d576  mov     ebx, 8007000Eh
0x14002d57b  lea     rdi, WPP_GLOBAL_Control
0x14002d582  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d589  cmp     rcx, rdi
0x14002d58c  jz      loc_14002D487
0x14002d592  test    byte ptr [rcx+1Ch], 1
0x14002d596  jz      loc_14002D487
0x14002d59c  mov     edx, 16h
0x14002d5a1  lea     r8, WPP_1969d98add70354507e1e1f7959b3b3f_Traceguids
0x14002d5a8  mov     rcx, [rcx+10h]
0x14002d5ac  call    WPP_SF_
0x14002d5b1  jmp     loc_14002D487
0x14002d5b6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002d5bd  mov     esi, 1180h
0x14002d5c2  mov     ecx, esi; unsigned __int64
0x14002d5c4  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14002d5c9  mov     r14, rax
0x14002d5cc  test    rax, rax
0x14002d5cf  jz      short loc_14002D5E0
0x14002d5d1  mov     r8d, esi; Size
0x14002d5d4  xor     edx, edx; Val
0x14002d5d6  mov     rcx, rax; void *
0x14002d5d9  call    memset_0
0x14002d5de  jmp     short loc_14002D5E3
0x14002d5e0  mov     r14, r15
0x14002d5e3  mov     [rbp+4Fh+var_90], r14
0x14002d5e7  test    r14, r14
0x14002d5ea  jnz     short loc_14002D624
0x14002d5ec  mov     ebx, 8007000Eh
0x14002d5f1  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d5f8  cmp     rcx, rdi
0x14002d5fb  jz      loc_14002D7C7
0x14002d601  test    byte ptr [rcx+1Ch], 1
0x14002d605  jz      loc_14002D7C7
0x14002d60b  lea     edx, [r14+18h]
0x14002d60f  lea     r8, WPP_1969d98add70354507e1e1f7959b3b3f_Traceguids
0x14002d616  mov     rcx, [rcx+10h]
0x14002d61a  call    WPP_SF_
0x14002d61f  jmp     loc_14002D7C7
0x14002d624  mov     rdx, rbx; void *
0x14002d627  lea     rcx, [rbp+4Fh+var_88]; this
0x14002d62b  call    ?Start@CWCTInfoWriter@@QEAAJPEAX@Z; CWCTInfoWriter::Start(void *)
0x14002d630  mov     ebx, eax
0x14002d632  test    eax, eax
0x14002d634  jns     short loc_14002D66D
0x14002d636  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d63d  cmp     rcx, rdi
0x14002d640  jz      loc_14002D7C7
0x14002d646  test    byte ptr [rcx+1Ch], 1
0x14002d64a  jz      loc_14002D7C7
0x14002d650  mov     edx, 19h
0x14002d655  mov     r9d, eax
0x14002d658  lea     r8, WPP_1969d98add70354507e1e1f7959b3b3f_Traceguids
0x14002d65f  mov     rcx, [rcx+10h]
0x14002d663  call    WPP_SF_d
0x14002d668  jmp     loc_14002D7C7
0x14002d66d  mov     rdx, [rbp+4Fh+var_A8]
0x14002d671  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x14002d675  jz      loc_14002D799
0x14002d67b  mov     [rbp+4Fh+var_B0], r15d
0x14002d67f  mov     [rbp+4Fh+var_A0], r15d
0x14002d683  mov     [rbp+4Fh+var_98], r15d
0x14002d687  lea     rax, [rbp+4Fh+var_98]
0x14002d68b  mov     qword ptr [rsp+100h+var_D8], rax
0x14002d690  lea     rax, [rbp+4Fh+var_A0]
0x14002d694  mov     [rsp+100h+var_E0], rax
0x14002d699  lea     r9, [rbp+4Fh+var_B0]
0x14002d69d  mov     r8, r14
0x14002d6a0  mov     edx, [rdx+8]
0x14002d6a3  mov     ecx, r12d
0x14002d6a6  call    ChaseThreads
0x14002d6ab  mov     ebx, eax
0x14002d6ad  test    eax, eax
0x14002d6af  js      loc_14002D77D
0x14002d6b5  mov     eax, [rbp+4Fh+var_A0]
0x14002d6b8  mov     [rsp+100h+var_C0], r15; struct SharedHangRepData *
0x14002d6bd  mov     [rsp+100h+var_C8], eax; int
0x14002d6c1  mov     eax, [rbp+4Fh+var_98]
0x14002d6c4  mov     [rsp+100h+var_D0], eax; int
0x14002d6c8  mov     [rsp+100h+var_D8], r15d; unsigned int
0x14002d6cd  mov     [rsp+100h+var_E0], r15; void **
0x14002d6d2  mov     r9, r13
0x14002d6d5  mov     r8d, [rbp+4Fh+var_B0]
0x14002d6d9  mov     rdx, r14
0x14002d6dc  lea     rcx, [rbp+4Fh+var_88]; this
0x14002d6e0  call    ?WriteNodeInfoToFile@CWCTInfoWriter@@QEAAJPEAU_WAITCHAIN_NODE_INFO@@IAEAV?$forward_list@UFileInfo@@V?$allocator@UFileInfo@@@utl@@@utl@@PEAPEAXKHHPEAUSharedHangRepData@@@Z; CWCTInfoWriter::WriteNodeInfoToFile(_WAITCHAIN_NODE_INFO *,uint,utl::forward_list<FileInfo,utl::allocator<FileInfo>> &,void * *,ulong,int,int,SharedHangRepData *)
0x14002d6e5  mov     ebx, eax
0x14002d6e7  test    eax, eax
0x14002d6e9  js      short loc_14002D761
0x14002d6eb  mov     rcx, [rbp+4Fh+var_A8]; void *
0x14002d6ef  mov     rax, [rcx]
0x14002d6f2  mov     [rbp+4Fh+var_A8], rax
0x14002d6f6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002d6fd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002d702  mov     esi, r15d
0x14002d705  mov     ecx, [rbp+4Fh+var_B0]
0x14002d708  test    ecx, ecx
0x14002d70a  jz      loc_14002D66D
0x14002d710  mov     eax, esi
0x14002d712  imul    r15, rax, 118h
0x14002d719  cmp     dword ptr [r15+r14], 8
0x14002d71e  jnz     short loc_14002D753
0x14002d720  lea     rbx, [rbp+4Fh+var_A8]
0x14002d724  mov     rcx, [rbx]; void *
0x14002d727  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14002d72b  jz      short loc_14002D750
0x14002d72d  mov     eax, [r15+r14+0Ch]
0x14002d732  cmp     [rcx+8], eax
0x14002d735  jnz     short loc_14002D74B
0x14002d737  mov     rax, [rcx]
0x14002d73a  mov     [rbx], rax
0x14002d73d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002d744  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002d749  jmp     short loc_14002D724
0x14002d74b  mov     rbx, rcx
0x14002d74e  jmp     short loc_14002D724
0x14002d750  mov     ecx, [rbp+4Fh+var_B0]
0x14002d753  inc     esi
0x14002d755  cmp     esi, ecx
0x14002d757  jb      short loc_14002D710
0x14002d759  xor     r15d, r15d
0x14002d75c  jmp     loc_14002D66D
0x14002d761  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d768  cmp     rcx, rdi
0x14002d76b  jz      short loc_14002D7C7
0x14002d76d  test    byte ptr [rcx+1Ch], 2
0x14002d771  jz      short loc_14002D7C7
0x14002d773  mov     edx, 1Bh
0x14002d778  jmp     loc_14002D655
0x14002d77d  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d784  cmp     rcx, rdi
0x14002d787  jz      short loc_14002D7C7
0x14002d789  test    byte ptr [rcx+1Ch], 1
0x14002d78d  jz      short loc_14002D7C7
0x14002d78f  mov     edx, 1Ah
0x14002d794  jmp     loc_14002D655
0x14002d799  lea     rcx, [rbp+4Fh+var_88]; this
0x14002d79d  call    ?End@CWCTInfoWriter@@QEAAJXZ; CWCTInfoWriter::End(void)
0x14002d7a2  mov     ebx, eax
0x14002d7a4  test    eax, eax
0x14002d7a6  jns     short loc_14002D7C4
0x14002d7a8  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d7af  cmp     rcx, rdi
0x14002d7b2  jz      short loc_14002D7C7
0x14002d7b4  test    byte ptr [rcx+1Ch], 1
0x14002d7b8  jz      short loc_14002D7C7
0x14002d7ba  mov     edx, 1Ch
0x14002d7bf  jmp     loc_14002D655
0x14002d7c4  mov     ebx, r15d
0x14002d7c7  test    r14, r14
0x14002d7ca  jz      short loc_14002D7D5
0x14002d7cc  mov     rcx, r14; void *
  ... truncated ...
```
