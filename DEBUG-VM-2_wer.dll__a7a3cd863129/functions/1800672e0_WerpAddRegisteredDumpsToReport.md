# WerpAddRegisteredDumpsToReport

- ea: `0x1800672e0`
- end: `0x18006748d`
- name: `WerpAddRegisteredDumpsToReport`
- size: `429`
- prototype: `__int64 __fastcall(HREPORT hReportHandle, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18002e4b8`

## callees

- `0x180004bb4`
- `0x180007e10`
- `0x180007e34`
- `0x180050db0`
- `0x1800606f0`
- `0x1800672e0`
- `0x1800a3b48`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x1800673da`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x1800673da`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800673ae`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800673ae`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18006737d`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18006737d`

## pseudocode

```c
__int64 __fastcall WerpAddRegisteredDumpsToReport(HREPORT hReportHandle, void *a2)
{
  __int64 result; // rax
  LPCVOID v5; // rdi
  unsigned int v6; // r14d
  char *v7; // rbx
  void *v8; // r8
  HANDLE v9; // rax
  LPCVOID lpBaseAddress; // [rsp+40h] [rbp-30h] BYREF
  SIZE_T NumberOfBytesRead; // [rsp+48h] [rbp-28h] BYREF
  char *v12; // [rsp+50h] [rbp-20h] BYREF
  __int128 Buffer; // [rsp+58h] [rbp-18h] BYREF

  lpBaseAddress = 0;
  if ( hReportHandle && a2 )
  {
    result = WerpGetDumpCollectionListStart(a2, (struct _WER_DUMP_COLLECTION **)&lpBaseAddress);
    if ( (int)result >= 0 )
    {
      v5 = lpBaseAddress;
      if ( lpBaseAddress )
      {
        v6 = 0;
        do
        {
          if ( v6 >= 0x200 )
            break;
          NumberOfBytesRead = 0;
          Buffer = 0;
          ++v6;
          if ( ReadProcessMemory(a2, v5, &Buffer, 0x10u, &NumberOfBytesRead) )
          {
            if ( NumberOfBytesRead == 16 )
            {
              v5 = (LPCVOID)Buffer;
              if ( DWORD2(Buffer) )
              {
                v7 = (char *)OpenProcess(0x100450u, 0, DWORD2(Buffer));
                v12 = v7;
                if ( v7 != (char *)-1LL && v7 + 1 != (char *)1 )
                {
                  v8 = 0;
                  lpBaseAddress = 0;
                  if ( HIDWORD(Buffer) )
                  {
                    v9 = OpenThread(0x48u, 0, HIDWORD(Buffer));
                    tlx::unique_any<tlx::file_handle_traits>::reset(&lpBaseAddress, v9);
                    v8 = (void *)lpBaseAddress;
                  }
                  WerReportAddDump(hReportHandle, v7, v8, WerDumpTypeTriageDump, 0, 0, 0x80000002);
                  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&lpBaseAddress);
                }
                tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v12);
              }
            }
          }
        }
        while ( v5 );
        return 0;
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 169, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids);
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800672e0  mov     [rsp-28h+arg_10], rbx
0x1800672e5  push    rbp
0x1800672e6  push    rsi
0x1800672e7  push    rdi
0x1800672e8  push    r14
0x1800672ea  push    r15
0x1800672ec  mov     rbp, rsp
0x1800672ef  sub     rsp, 70h
0x1800672f3  mov     rax, cs:__security_cookie
0x1800672fa  xor     rax, rsp
0x1800672fd  mov     [rbp+var_8], rax
0x180067301  mov     [rbp+lpBaseAddress], 0
0x180067309  mov     rsi, rdx
0x18006730c  mov     r15, rcx
0x18006730f  test    rcx, rcx
0x180067312  jz      loc_18006743A
0x180067318  test    rdx, rdx
0x18006731b  jz      loc_18006743A
0x180067321  lea     rdx, [rbp+lpBaseAddress]; struct _WER_DUMP_COLLECTION **
0x180067325  mov     rcx, rsi; void *
0x180067328  call    ?WerpGetDumpCollectionListStart@@YAJPEAXPEAPEAU_WER_DUMP_COLLECTION@@@Z; WerpGetDumpCollectionListStart(void *,_WER_DUMP_COLLECTION * *)
0x18006732d  test    eax, eax
0x18006732f  js      loc_18006746D
0x180067335  mov     rdi, [rbp+lpBaseAddress]
0x180067339  test    rdi, rdi
0x18006733c  jz      loc_18006746D
0x180067342  xor     r14d, r14d
0x180067345  cmp     r14d, 200h
0x18006734c  jnb     loc_180067436
0x180067352  xorps   xmm0, xmm0
0x180067355  mov     [rbp+NumberOfBytesRead], 0
0x18006735d  lea     rax, [rbp+NumberOfBytesRead]
0x180067361  mov     r9d, 10h; nSize
0x180067367  lea     r8, [rbp+Buffer]; lpBuffer
0x18006736b  mov     [rsp+70h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x180067370  mov     rdx, rdi; lpBaseAddress
0x180067373  mov     rcx, rsi; hProcess
0x180067376  movups  [rbp+Buffer], xmm0
0x18006737a  inc     r14d
0x18006737d  call    cs:__imp_ReadProcessMemory
0x180067383  test    eax, eax
0x180067385  jz      loc_18006742D
0x18006738b  cmp     [rbp+NumberOfBytesRead], 10h
0x180067390  jnz     loc_18006742D
0x180067396  mov     r8d, dword ptr [rbp+Buffer+8]; dwProcessId
0x18006739a  mov     rdi, qword ptr [rbp+Buffer]
0x18006739e  test    r8d, r8d
0x1800673a1  jz      loc_18006742D
0x1800673a7  xor     edx, edx; bInheritHandle
0x1800673a9  mov     ecx, 100450h; dwDesiredAccess
0x1800673ae  call    cs:__imp_OpenProcess
0x1800673b4  mov     rbx, rax
0x1800673b7  mov     [rbp+var_20], rax
0x1800673bb  inc     rax
0x1800673be  cmp     rax, 1
0x1800673c2  jbe     short loc_180067424
0x1800673c4  mov     eax, dword ptr [rbp+Buffer+0Ch]
0x1800673c7  xor     r8d, r8d
0x1800673ca  mov     [rbp+lpBaseAddress], r8
0x1800673ce  test    eax, eax
0x1800673d0  jz      short loc_1800673F0
0x1800673d2  xor     edx, edx; bInheritHandle
0x1800673d4  mov     r8d, eax; dwThreadId
0x1800673d7  lea     ecx, [rdx+48h]; dwDesiredAccess
0x1800673da  call    cs:__imp_OpenThread
0x1800673e0  mov     rdx, rax
0x1800673e3  lea     rcx, [rbp+lpBaseAddress]
0x1800673e7  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x1800673ec  mov     r8, [rbp+lpBaseAddress]; hThread
0x1800673f0  mov     [rsp+70h+dwFlags], 80000002h; dwFlags
0x1800673f8  mov     r9d, 4; dumpType
0x1800673fe  mov     [rsp+70h+pDumpCustomOptions], 0; pDumpCustomOptions
0x180067407  mov     rdx, rbx; hProcess
0x18006740a  mov     rcx, r15; hReportHandle
0x18006740d  mov     [rsp+70h+lpNumberOfBytesRead], 0; pExceptionParam
0x180067416  call    WerReportAddDump
0x18006741b  lea     rcx, [rbp+lpBaseAddress]
0x18006741f  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180067424  lea     rcx, [rbp+var_20]
0x180067428  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18006742d  test    rdi, rdi
0x180067430  jnz     loc_180067345
0x180067436  xor     eax, eax
0x180067438  jmp     short loc_18006746D
0x18006743a  mov     rcx, cs:WPP_GLOBAL_Control
0x180067441  lea     rax, WPP_GLOBAL_Control
0x180067448  cmp     rcx, rax
0x18006744b  jz      short loc_180067468
0x18006744d  test    byte ptr [rcx+1Ch], 1
0x180067451  jz      short loc_180067468
0x180067453  mov     rcx, [rcx+10h]
0x180067457  lea     r8, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids
0x18006745e  mov     edx, 0A9h
0x180067463  call    WPP_SF_
0x180067468  mov     eax, 80070057h
0x18006746d  mov     rcx, [rbp+var_8]
0x180067471  xor     rcx, rsp; StackCookie
0x180067474  call    __security_check_cookie
0x180067479  mov     rbx, [rsp+70h+arg_10]
0x180067481  add     rsp, 70h
0x180067485  pop     r15
0x180067487  pop     r14
0x180067489  pop     rdi
0x18006748a  pop     rsi
0x18006748b  pop     rbp
0x18006748c  retn
```
