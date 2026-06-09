# ReplaceCommandLineInProcessMemory(void *,unsigned __int64)

- ea: `0x18020c2d4`
- end: `0x18020c4fd`
- name: `?ReplaceCommandLineInProcessMemory@@YAJPEAX_K@Z`
- size: `553`
- prototype: `__int64 __fastcall(HANDLE hProcess, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180095e58`

## callees

- `0x180013250`
- `0x1800261e0`
- `0x18009cf78`
- `0x1800a9014`
- `0x1800d0588`
- `0x1800eb920`
- `0x18020c2d4`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!VirtualQueryEx` at `0x18020c3fa`
- `api-ms-win-core-memory-l1-1-0!VirtualQueryEx` at `0x18020c3fa`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x18020c47f`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x18020c47f`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18020c39b`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18020c3d1`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18020c39b`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18020c3d1`
- `ntdll!NtQueryInformationProcess` at `0x18020c342`
- `ntdll!NtQueryInformationProcess` at `0x18020c342`

## string_xrefs

- `0x18020c356`: `onecore\base\cbs\sandbox\lib\sandboxcommunication.cpp`
- `0x18020c498`: `onecore\base\cbs\sandbox\lib\sandboxcommunication.cpp`
- `0x18020c4c6`: `onecore\base\cbs\sandbox\lib\sandboxcommunication.cpp`

## pseudocode

```c
__int64 __fastcall ReplaceCommandLineInProcessMemory(HANDLE hProcess, __int64 a2)
{
  NTSTATUS v4; // eax
  unsigned int LastError; // eax
  __int64 v6; // rdx
  const char *v7; // r9
  __int64 v8; // rdx
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // r9
  __int64 v12; // rax
  int ReturnLength; // [rsp+20h] [rbp-69h]
  LPCVOID lpBuffer; // [rsp+30h] [rbp-59h] BYREF
  __int64 Buffer; // [rsp+38h] [rbp-51h] BYREF
  LPCVOID lpAddress[2]; // [rsp+40h] [rbp-49h] BYREF
  _OWORD ProcessInformation[3]; // [rsp+50h] [rbp-39h] BYREF
  ULONG v19; // [rsp+80h] [rbp-9h] BYREF
  SIZE_T NumberOfBytesRead; // [rsp+88h] [rbp-1h] BYREF
  _MEMORY_BASIC_INFORMATION v21; // [rsp+90h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  Buffer = 0;
  v19 = 0;
  NumberOfBytesRead = 0;
  lpBuffer = 0;
  memset(ProcessInformation, 0, sizeof(ProcessInformation));
  *(_OWORD *)lpAddress = 0;
  memset(&v21, 0, sizeof(v21));
  v4 = NtQueryInformationProcess(hProcess, ProcessBasicInformation, ProcessInformation, 0x30u, &v19);
  if ( v4 >= 0 )
  {
    if ( v19 != 48 )
    {
      v6 = 103;
LABEL_25:
      v10 = -2147418113;
      v11 = 2147549183LL;
      goto LABEL_26;
    }
    if ( ReadProcessMemory(
           hProcess,
           (LPCVOID)(*((_QWORD *)&ProcessInformation[0] + 1) + 32LL),
           &Buffer,
           8u,
           &NumberOfBytesRead) )
    {
      if ( ReadProcessMemory(hProcess, (LPCVOID)(Buffer + 112), lpAddress, 0x10u, &NumberOfBytesRead) )
      {
        if ( VirtualQueryEx(hProcess, lpAddress[1], &v21, 0x30u) )
        {
          if ( v21.Type != 0x20000 || v21.Protect != 4 )
          {
            v6 = 130;
            goto LABEL_25;
          }
          v9 = SczAllocFormatted(&lpBuffer, L"%I64u", a2);
          v10 = v9;
          if ( v9 < 0 )
          {
            v11 = (unsigned int)v9;
            v6 = 133;
LABEL_26:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v6,
              (unsigned int)"onecore\\base\\cbs\\sandbox\\lib\\sandboxcommunication.cpp",
              (const char *)v11,
              ReturnLength);
            goto LABEL_27;
          }
          v12 = -1;
          do
            ++v12;
          while ( *((_WORD *)lpBuffer + v12) );
          if ( LOWORD(lpAddress[0]) < (unsigned __int64)(2 * v12) )
          {
            v6 = 139;
            goto LABEL_25;
          }
          if ( WriteProcessMemory(hProcess, (LPVOID)lpAddress[1], lpBuffer, 2 * v12, 0) )
          {
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpBuffer);
            return 0;
          }
          v8 = 149;
        }
        else
        {
          v8 = 125;
        }
      }
      else
      {
        v8 = 120;
      }
    }
    else
    {
      v8 = 111;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v8,
                  (unsigned int)"onecore\\base\\cbs\\sandbox\\lib\\sandboxcommunication.cpp",
                  v7);
    goto LABEL_22;
  }
  LastError = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0x63,
                (unsigned int)"onecore\\base\\cbs\\sandbox\\lib\\sandboxcommunication.cpp",
                (const char *)(unsigned int)v4,
                ReturnLength);
LABEL_22:
  v10 = LastError;
LABEL_27:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpBuffer);
  return v10;
}

```

## disassembly

```asm
0x18020c2d4  mov     [rsp-8+arg_10], rbx
0x18020c2d9  push    rbp
0x18020c2da  push    rsi
0x18020c2db  push    rdi
0x18020c2dc  lea     rbp, [rsp-47h]
0x18020c2e1  sub     rsp, 0D0h
0x18020c2e8  mov     rax, cs:__security_cookie
0x18020c2ef  xor     rax, rsp
0x18020c2f2  mov     [rbp+57h+var_20], rax
0x18020c2f6  xor     esi, esi
0x18020c2f8  lea     rax, [rbp+57h+var_60]
0x18020c2fc  xorps   xmm0, xmm0
0x18020c2ff  mov     [rbp+57h+Buffer], rsi
0x18020c303  xorps   xmm1, xmm1
0x18020c306  mov     [rbp+57h+var_60], esi
0x18020c309  mov     rbx, rdx
0x18020c30c  mov     [rbp+57h+NumberOfBytesRead], rsi
0x18020c310  lea     r9d, [rsi+30h]; ProcessInformationLength
0x18020c314  mov     [rbp+57h+lpBuffer], rsi
0x18020c318  lea     r8, [rbp+57h+ProcessInformation]; ProcessInformation
0x18020c31c  mov     qword ptr [rsp+0E0h+ReturnLength], rax; int
0x18020c321  xor     edx, edx; ProcessInformationClass
0x18020c323  mov     rdi, rcx
0x18020c326  movups  [rbp+57h+ProcessInformation], xmm0
0x18020c32a  movups  [rbp+57h+var_80], xmm0
0x18020c32e  movups  [rbp+57h+var_70], xmm0
0x18020c332  movups  xmmword ptr [rbp+57h+lpAddress], xmm0
0x18020c336  movups  xmmword ptr [rbp+57h+var_50.BaseAddress], xmm1
0x18020c33a  movups  xmmword ptr [rbp+57h+var_50.AllocationProtect], xmm1
0x18020c33e  movups  xmmword ptr [rbp+57h+var_50.State], xmm1
0x18020c342  call    cs:__imp_NtQueryInformationProcess
0x18020c349  nop     dword ptr [rax+rax+00h]
0x18020c34e  test    eax, eax
0x18020c350  jns     short loc_18020C36D
0x18020c352  mov     rcx, [rbp+5Fh]; this
0x18020c356  lea     r8, aOnecoreBaseCbs_39; "onecore\\base\\cbs\\sandbox\\lib\\sandb"...
0x18020c35d  mov     r9d, eax; char *
0x18020c360  lea     edx, [rsi+63h]; void *
0x18020c363  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18020c368  jmp     loc_18020C4A4
0x18020c36d  cmp     [rbp+57h+var_60], 30h ; '0'
0x18020c371  jz      short loc_18020C37D
0x18020c373  mov     edx, 67h ; 'g'
0x18020c378  jmp     loc_18020C4BA
0x18020c37d  mov     rdx, qword ptr [rbp+57h+ProcessInformation+8]
0x18020c381  lea     rax, [rbp+57h+NumberOfBytesRead]
0x18020c385  add     rdx, 20h ; ' '; lpBaseAddress
0x18020c389  mov     qword ptr [rsp+0E0h+ReturnLength], rax; lpNumberOfBytesRead
0x18020c38e  mov     r9d, 8; nSize
0x18020c394  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x18020c398  mov     rcx, rdi; hProcess
0x18020c39b  call    cs:__imp_ReadProcessMemory
0x18020c3a2  nop     dword ptr [rax+rax+00h]
0x18020c3a7  test    eax, eax
0x18020c3a9  jnz     short loc_18020C3B3
0x18020c3ab  lea     edx, [rax+6Fh]
0x18020c3ae  jmp     loc_18020C494
0x18020c3b3  mov     rdx, [rbp+57h+Buffer]
0x18020c3b7  lea     rax, [rbp+57h+NumberOfBytesRead]
0x18020c3bb  add     rdx, 70h ; 'p'; lpBaseAddress
0x18020c3bf  mov     qword ptr [rsp+0E0h+ReturnLength], rax; int
0x18020c3c4  mov     r9d, 10h; nSize
0x18020c3ca  lea     r8, [rbp+57h+lpAddress]; lpBuffer
0x18020c3ce  mov     rcx, rdi; hProcess
0x18020c3d1  call    cs:__imp_ReadProcessMemory
0x18020c3d8  nop     dword ptr [rax+rax+00h]
0x18020c3dd  test    eax, eax
0x18020c3df  jnz     short loc_18020C3E9
0x18020c3e1  lea     edx, [rax+78h]
0x18020c3e4  jmp     loc_18020C494
0x18020c3e9  mov     rdx, [rbp+57h+lpAddress+8]; lpAddress
0x18020c3ed  lea     r8, [rbp+57h+var_50]; lpBuffer
0x18020c3f1  mov     r9d, 30h ; '0'; dwLength
0x18020c3f7  mov     rcx, rdi; hProcess
0x18020c3fa  call    cs:__imp_VirtualQueryEx
0x18020c401  nop     dword ptr [rax+rax+00h]
0x18020c406  test    rax, rax
0x18020c409  jnz     short loc_18020C413
0x18020c40b  lea     edx, [rax+7Dh]
0x18020c40e  jmp     loc_18020C494
0x18020c413  cmp     [rbp+57h+var_50.Type], 20000h
0x18020c41a  jnz     loc_18020C4B5
0x18020c420  cmp     [rbp+57h+var_50.Protect], 4
0x18020c424  jnz     loc_18020C4B5
0x18020c42a  mov     r8, rbx
0x18020c42d  lea     rdx, aI64u_0; "%I64u"
0x18020c434  lea     rcx, [rbp+57h+lpBuffer]
0x18020c438  call    SczAllocFormatted
0x18020c43d  mov     ebx, eax
0x18020c43f  test    eax, eax
0x18020c441  jns     short loc_18020C44D
0x18020c443  mov     r9d, eax
0x18020c446  mov     edx, 85h
0x18020c44b  jmp     short loc_18020C4C2
0x18020c44d  mov     r8, [rbp+57h+lpBuffer]; lpBuffer
0x18020c451  or      rax, 0FFFFFFFFFFFFFFFFh
0x18020c455  inc     rax
0x18020c458  cmp     [r8+rax*2], si
0x18020c45d  jnz     short loc_18020C455
0x18020c45f  lea     r9, [rax+rax]; nSize
0x18020c463  movzx   eax, word ptr [rbp+57h+lpAddress]
0x18020c467  cmp     rax, r9
0x18020c46a  jnb     short loc_18020C473
0x18020c46c  mov     edx, 8Bh
0x18020c471  jmp     short loc_18020C4BA
0x18020c473  mov     rdx, [rbp+57h+lpAddress+8]; lpBaseAddress
0x18020c477  mov     rcx, rdi; hProcess
0x18020c47a  mov     qword ptr [rsp+0E0h+ReturnLength], rsi; lpNumberOfBytesWritten
0x18020c47f  call    cs:__imp_WriteProcessMemory
0x18020c486  nop     dword ptr [rax+rax+00h]
0x18020c48b  test    eax, eax
0x18020c48d  jnz     short loc_18020C4A8
0x18020c48f  mov     edx, 95h; void *
0x18020c494  mov     rcx, [rbp+5Fh]; this
0x18020c498  lea     r8, aOnecoreBaseCbs_39; "onecore\\base\\cbs\\sandbox\\lib\\sandb"...
0x18020c49f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18020c4a4  mov     ebx, eax
0x18020c4a6  jmp     short loc_18020C4D2
0x18020c4a8  lea     rcx, [rbp+57h+lpBuffer]
0x18020c4ac  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18020c4b1  xor     eax, eax
0x18020c4b3  jmp     short loc_18020C4DD
0x18020c4b5  mov     edx, 82h; void *
0x18020c4ba  mov     ebx, 8000FFFFh
0x18020c4bf  mov     r9d, ebx; char *
0x18020c4c2  mov     rcx, [rbp+5Fh]; this
0x18020c4c6  lea     r8, aOnecoreBaseCbs_39; "onecore\\base\\cbs\\sandbox\\lib\\sandb"...
0x18020c4cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020c4d2  lea     rcx, [rbp+57h+lpBuffer]
0x18020c4d6  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18020c4db  mov     eax, ebx
0x18020c4dd  mov     rcx, [rbp+57h+var_20]
0x18020c4e1  xor     rcx, rsp; StackCookie
0x18020c4e4  call    __security_check_cookie
0x18020c4e9  mov     rbx, [rsp+0E0h+arg_10]
0x18020c4f1  add     rsp, 0D0h
0x18020c4f8  pop     rdi
0x18020c4f9  pop     rsi
0x18020c4fa  pop     rbp
0x18020c4fb  retn
```
