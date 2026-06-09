# GetWERProcesses

- ea: `0x140007888`
- end: `0x140007a84`
- name: `GetWERProcesses`
- size: `508`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x14000d0e4`

## callees

- `0x140002fbc`
- `0x140003200`
- `0x140004398`
- `0x140007888`
- `0x14000e340`
- `0x14000e3e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000795c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140007972`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000795c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140007972`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000797c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000797c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400078f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007a17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400078f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007a17`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400079fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007a0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400079fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007a0d`
- `api-ms-win-core-toolhelp-l1-1-0!Process32FirstW` at `0x1400078ec`
- `api-ms-win-core-toolhelp-l1-1-0!Process32FirstW` at `0x1400078ec`
- `api-ms-win-core-toolhelp-l1-1-0!Process32NextW` at `0x1400079ea`
- `api-ms-win-core-toolhelp-l1-1-0!Process32NextW` at `0x1400079ea`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x1400078ce`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x1400078ce`

## pseudocode

```c
__int64 __fastcall GetWERProcesses(__int64 a1)
{
  char *Toolhelp32Snapshot; // rbx
  signed int v3; // eax
  unsigned int v4; // edi
  DWORD *v5; // rax
  signed int LastError; // eax
  unsigned int v8; // ebx
  PROCESSENTRY32W pe; // [rsp+30h] [rbp-258h] BYREF

  memset_0(&pe.cntUsage, 0, 0x234u);
  pe.dwSize = 568;
  Toolhelp32Snapshot = (char *)CreateToolhelp32Snapshot(2u, 0);
  if ( Toolhelp32Snapshot == (char *)-1LL || Toolhelp32Snapshot + 1 == (char *)1 )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_9d8c324f5ff538d6084a6c746c899545_Traceguids, v8);
    return v8;
  }
  else
  {
    if ( Process32FirstW(Toolhelp32Snapshot, &pe) )
    {
      while ( 1 )
      {
        if ( (!(unsigned int)_o__wcsicmp(L"WerFault.exe", pe.szExeFile)
           || !(unsigned int)_o__wcsicmp(L"wermgr.exe", pe.szExeFile))
          && pe.th32ProcessID != GetCurrentProcessId() )
        {
          v5 = *(DWORD **)(a1 + 8);
          if ( v5 == *(DWORD **)(a1 + 16) )
          {
            if ( !(unsigned __int8)utl::vector<unsigned long,utl::allocator<unsigned long>>::_PushBackOne2<unsigned long const &>(
                                     a1,
                                     &pe.th32ProcessID) )
            {
              v4 = -2147024882;
              goto LABEL_20;
            }
          }
          else
          {
            *v5 = pe.th32ProcessID;
            *(_QWORD *)(a1 + 8) += 4LL;
          }
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_SD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              13,
              (unsigned int)WPP_9d8c324f5ff538d6084a6c746c899545_Traceguids,
              (unsigned int)pe.szExeFile,
              pe.th32ProcessID);
        }
        if ( !Process32NextW(Toolhelp32Snapshot, &pe) )
        {
          CloseHandle(Toolhelp32Snapshot);
          return 0;
        }
      }
    }
    v3 = GetLastError();
    v4 = v3;
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_9d8c324f5ff538d6084a6c746c899545_Traceguids, v4);
LABEL_20:
    CloseHandle(Toolhelp32Snapshot);
    return v4;
  }
}

```

## disassembly

```asm
0x140007888  mov     [rsp+arg_8], rbx
0x14000788d  mov     [rsp+arg_10], rsi
0x140007892  push    rdi
0x140007893  sub     rsp, 280h
0x14000789a  mov     rax, cs:__security_cookie
0x1400078a1  xor     rax, rsp
0x1400078a4  mov     [rsp+288h+var_18], rax
0x1400078ac  mov     rdi, rcx
0x1400078af  xor     edx, edx; Val
0x1400078b1  lea     rcx, [rsp+288h+pe.cntUsage]; void *
0x1400078b6  mov     r8d, 234h; Size
0x1400078bc  call    memset_0
0x1400078c1  xor     edx, edx; th32ProcessID
0x1400078c3  mov     [rsp+288h+pe.dwSize], 238h
0x1400078cb  lea     ecx, [rdx+2]; dwFlags
0x1400078ce  call    cs:__imp_CreateToolhelp32Snapshot
0x1400078d4  mov     rbx, rax
0x1400078d7  inc     rax
0x1400078da  cmp     rax, 1
0x1400078de  jbe     loc_140007A17
0x1400078e4  lea     rdx, [rsp+288h+pe]; lppe
0x1400078e9  mov     rcx, rbx; hSnapshot
0x1400078ec  call    cs:__imp_Process32FirstW
0x1400078f2  test    eax, eax
0x1400078f4  jnz     short loc_140007949
0x1400078f6  call    cs:__imp_GetLastError
0x1400078fc  mov     edi, eax
0x1400078fe  test    eax, eax
0x140007900  jle     short loc_14000790B
0x140007902  movzx   edi, ax
0x140007905  or      edi, 80070000h
0x14000790b  mov     rcx, cs:WPP_GLOBAL_Control
0x140007912  lea     rsi, WPP_GLOBAL_Control
0x140007919  cmp     rcx, rsi
0x14000791c  jz      loc_140007A0A
0x140007922  test    byte ptr [rcx+1Ch], 1
0x140007926  jz      loc_140007A0A
0x14000792c  mov     rcx, [rcx+10h]
0x140007930  lea     r8, WPP_9d8c324f5ff538d6084a6c746c899545_Traceguids
0x140007937  mov     edx, 0Ch
0x14000793c  mov     r9d, edi
0x14000793f  call    WPP_SF_d
0x140007944  jmp     loc_140007A0A
0x140007949  lea     rsi, WPP_GLOBAL_Control
0x140007950  lea     rdx, [rsp+288h+pe.szExeFile]
0x140007955  lea     rcx, aWerfaultExe; "WerFault.exe"
0x14000795c  call    cs:__imp__o__wcsicmp
0x140007962  test    eax, eax
0x140007964  jz      short loc_14000797C
0x140007966  lea     rdx, [rsp+288h+pe.szExeFile]
0x14000796b  lea     rcx, aWermgrExe; "wermgr.exe"
0x140007972  call    cs:__imp__o__wcsicmp
0x140007978  test    eax, eax
0x14000797a  jnz     short loc_1400079E2
0x14000797c  call    cs:__imp_GetCurrentProcessId
0x140007982  mov     ecx, [rsp+288h+pe.th32ProcessID]
0x140007986  cmp     ecx, eax
0x140007988  jz      short loc_1400079E2
0x14000798a  mov     rax, [rdi+8]
0x14000798e  cmp     rax, [rdi+10h]
0x140007992  jz      short loc_14000799D
0x140007994  mov     [rax], ecx
0x140007996  add     qword ptr [rdi+8], 4
0x14000799b  jmp     short loc_1400079AE
0x14000799d  lea     rdx, [rsp+288h+pe.th32ProcessID]
0x1400079a2  mov     rcx, rdi
0x1400079a5  call    ??$_PushBackOne2@AEBK@?$vector@KV?$allocator@K@utl@@@utl@@AEAA_NAEBK@Z; utl::vector<ulong,utl::allocator<ulong>>::_PushBackOne2<ulong const &>(ulong const &)
0x1400079aa  test    al, al
0x1400079ac  jz      short loc_140007A05
0x1400079ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400079b5  cmp     rcx, rsi
0x1400079b8  jz      short loc_1400079E2
0x1400079ba  test    byte ptr [rcx+1Ch], 8
0x1400079be  jz      short loc_1400079E2
0x1400079c0  mov     eax, [rsp+288h+pe.th32ProcessID]
0x1400079c4  lea     r9, [rsp+288h+pe.szExeFile]
0x1400079c9  mov     rcx, [rcx+10h]
0x1400079cd  lea     r8, WPP_9d8c324f5ff538d6084a6c746c899545_Traceguids
0x1400079d4  mov     edx, 0Dh
0x1400079d9  mov     [rsp+288h+var_268], eax
0x1400079dd  call    WPP_SF_SD
0x1400079e2  lea     rdx, [rsp+288h+pe]; lppe
0x1400079e7  mov     rcx, rbx; hSnapshot
0x1400079ea  call    cs:__imp_Process32NextW
0x1400079f0  test    eax, eax
0x1400079f2  jnz     loc_140007950
0x1400079f8  mov     rcx, rbx; hObject
0x1400079fb  call    cs:__imp_CloseHandle
0x140007a01  xor     eax, eax
0x140007a03  jmp     short loc_140007A5F
0x140007a05  mov     edi, 8007000Eh
0x140007a0a  mov     rcx, rbx; hObject
0x140007a0d  call    cs:__imp_CloseHandle
0x140007a13  mov     eax, edi
0x140007a15  jmp     short loc_140007A5F
0x140007a17  call    cs:__imp_GetLastError
0x140007a1d  mov     ebx, eax
0x140007a1f  test    eax, eax
0x140007a21  jle     short loc_140007A2C
0x140007a23  movzx   ebx, ax
0x140007a26  or      ebx, 80070000h
0x140007a2c  mov     rcx, cs:WPP_GLOBAL_Control
0x140007a33  lea     rsi, WPP_GLOBAL_Control
0x140007a3a  cmp     rcx, rsi
0x140007a3d  jz      short loc_140007A5D
0x140007a3f  test    byte ptr [rcx+1Ch], 1
0x140007a43  jz      short loc_140007A5D
0x140007a45  mov     rcx, [rcx+10h]
0x140007a49  lea     r8, WPP_9d8c324f5ff538d6084a6c746c899545_Traceguids
0x140007a50  mov     edx, 0Bh
0x140007a55  mov     r9d, ebx
0x140007a58  call    WPP_SF_d
0x140007a5d  mov     eax, ebx
0x140007a5f  mov     rcx, [rsp+288h+var_18]
0x140007a67  xor     rcx, rsp; StackCookie
0x140007a6a  call    __security_check_cookie
0x140007a6f  lea     r11, [rsp+288h+var_8]
0x140007a77  mov     rbx, [r11+18h]
0x140007a7b  mov     rsi, [r11+20h]
0x140007a7f  mov     rsp, r11
0x140007a82  pop     rdi
0x140007a83  retn
```
