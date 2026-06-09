# CReport::SetDeleteFilesToken(void *)

- ea: `0x180072ec4`
- end: `0x18007302e`
- name: `?SetDeleteFilesToken@CReport@@IEAAJPEAX@Z`
- size: `362`
- prototype: `int(CReport *__hidden this, void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800278f0`
- `0x1800722a0`

## callees

- `0x18000716c`
- `0x180007e34`
- `0x18001fe24`
- `0x18002bed4`
- `0x180072ec4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180072fc8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180072fc8`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180072fe4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180072fe4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072ffc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072ffc`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x180072f75`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x180072f75`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180072eff`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180072eff`

## pseudocode

```c
__int64 __fastcall CReport::SetDeleteFilesToken(CReport *this, void *a2)
{
  char *v2; // rdi
  void **v4; // rax
  HANDLE CurrentProcess; // rbx
  __int64 v7; // rcx
  int v8; // eax
  unsigned int v9; // ebx
  wchar_t *v10; // rcx
  __int64 v11; // rdx
  void **v12; // rax
  DWORD LastError; // eax
  void *v14; // [rsp+30h] [rbp+8h] BYREF

  v2 = (char *)this + 46616;
  v14 = 0;
  if ( *((_QWORD *)this + 5827) )
    return 0;
  if ( a2 )
  {
    v4 = (void **)tlx::replace<tlx::file_handle_traits>((char *)this + 46616);
    if ( !DuplicateToken(a2, SecurityImpersonation, v4) )
    {
      tlx::unique_any<tlx::file_handle_traits>::reset(v2, 0);
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 303, WPP_6898268820d636d20e115db2eaa75970_Traceguids, 0);
    }
    return 0;
  }
  CurrentProcess = (HANDLE)*((_QWORD *)this + 830);
  if ( !CurrentProcess )
  {
    v7 = *((_QWORD *)this + 1139);
    if ( v7 )
    {
      v8 = PssQuerySnapshot(v7, 1, &v14);
      v9 = v8;
      if ( v8 )
      {
        if ( v8 > 0 )
          v9 = (unsigned __int16)v8 | 0x80070000;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          return v9;
        v11 = 304;
        goto LABEL_16;
      }
      CurrentProcess = v14;
    }
    else
    {
      CurrentProcess = GetCurrentProcess();
    }
  }
  v12 = (void **)tlx::replace<tlx::file_handle_traits>(v2);
  if ( OpenProcessToken(CurrentProcess, 0xAu, v12) )
    return 0;
  tlx::unique_any<tlx::file_handle_traits>::reset(v2, 0);
  LastError = GetLastError();
  v9 = ERROR_HR_FROM_WIN32(LastError);
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
    return v9;
  v11 = 305;
LABEL_16:
  WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_6898268820d636d20e115db2eaa75970_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x180072ec4  mov     [rsp+arg_8], rbx
0x180072ec9  push    rdi
0x180072eca  sub     rsp, 20h
0x180072ece  lea     rdi, [rcx+0B618h]
0x180072ed5  mov     [rsp+28h+arg_0], 0
0x180072ede  cmp     qword ptr [rdi], 0
0x180072ee2  mov     rbx, rdx
0x180072ee5  jnz     short loc_180072F44
0x180072ee7  test    rdx, rdx
0x180072eea  jz      short loc_180072F51
0x180072eec  mov     rcx, rdi
0x180072eef  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180072ef4  mov     r8, rax; DuplicateTokenHandle
0x180072ef7  mov     edx, 2; ImpersonationLevel
0x180072efc  mov     rcx, rbx; ExistingTokenHandle
0x180072eff  call    cs:__imp_DuplicateToken
0x180072f05  test    eax, eax
0x180072f07  jnz     short loc_180072F44
0x180072f09  xor     edx, edx
0x180072f0b  mov     rcx, rdi
0x180072f0e  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180072f13  mov     rcx, cs:WPP_GLOBAL_Control
0x180072f1a  lea     rax, WPP_GLOBAL_Control
0x180072f21  cmp     rcx, rax
0x180072f24  jz      short loc_180072F44
0x180072f26  test    byte ptr [rcx+1Ch], 1
0x180072f2a  jz      short loc_180072F44
0x180072f2c  mov     rcx, [rcx+10h]
0x180072f30  lea     r8, WPP_6898268820d636d20e115db2eaa75970_Traceguids
0x180072f37  mov     edx, 12Fh
0x180072f3c  xor     r9d, r9d
0x180072f3f  call    WPP_SF_d
0x180072f44  xor     eax, eax
0x180072f46  mov     rbx, [rsp+28h+arg_8]
0x180072f4b  add     rsp, 20h
0x180072f4f  pop     rdi
0x180072f50  retn
0x180072f51  mov     rbx, [rcx+19F0h]
0x180072f58  test    rbx, rbx
0x180072f5b  jnz     short loc_180072FD1
0x180072f5d  mov     rcx, [rcx+2398h]
0x180072f64  test    rcx, rcx
0x180072f67  jz      short loc_180072FC8
0x180072f69  lea     r9d, [rbx+8]
0x180072f6d  lea     r8, [rsp+28h+arg_0]
0x180072f72  lea     edx, [rbx+1]
0x180072f75  call    cs:__imp_PssQuerySnapshot
0x180072f7b  mov     ebx, eax
0x180072f7d  test    eax, eax
0x180072f7f  jz      short loc_180072FC1
0x180072f81  jle     short loc_180072F8C
0x180072f83  movzx   ebx, ax
0x180072f86  or      ebx, 80070000h
0x180072f8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180072f93  lea     rax, WPP_GLOBAL_Control
0x180072f9a  cmp     rcx, rax
0x180072f9d  jz      short loc_180072FBD
0x180072f9f  test    byte ptr [rcx+1Ch], 1
0x180072fa3  jz      short loc_180072FBD
0x180072fa5  mov     edx, 130h
0x180072faa  mov     rcx, [rcx+10h]
0x180072fae  lea     r8, WPP_6898268820d636d20e115db2eaa75970_Traceguids
0x180072fb5  mov     r9d, ebx
0x180072fb8  call    WPP_SF_d
0x180072fbd  mov     eax, ebx
0x180072fbf  jmp     short loc_180072F46
0x180072fc1  mov     rbx, [rsp+28h+arg_0]
0x180072fc6  jmp     short loc_180072FD1
0x180072fc8  call    cs:__imp_GetCurrentProcess
0x180072fce  mov     rbx, rax
0x180072fd1  mov     rcx, rdi
0x180072fd4  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180072fd9  mov     r8, rax; TokenHandle
0x180072fdc  mov     edx, 0Ah; DesiredAccess
0x180072fe1  mov     rcx, rbx; ProcessHandle
0x180072fe4  call    cs:__imp_OpenProcessToken
0x180072fea  test    eax, eax
0x180072fec  jnz     loc_180072F44
0x180072ff2  xor     edx, edx
0x180072ff4  mov     rcx, rdi
0x180072ff7  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180072ffc  call    cs:__imp_GetLastError
0x180073002  mov     ecx, eax; unsigned int
0x180073004  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180073009  mov     ebx, eax
0x18007300b  mov     rcx, cs:WPP_GLOBAL_Control
0x180073012  lea     rax, WPP_GLOBAL_Control
0x180073019  cmp     rcx, rax
0x18007301c  jz      short loc_180072FBD
0x18007301e  test    byte ptr [rcx+1Ch], 1
0x180073022  jz      short loc_180072FBD
0x180073024  mov     edx, 131h
0x180073029  jmp     loc_180072FAA
```
