# BfeGetRpcCallersProcessImageName

- ea: `0x180072f20`
- end: `0x1800730c0`
- name: `BfeGetRpcCallersProcessImageName`
- size: `416`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800654d0`

## callees

- `0x180012d8c`
- `0x180012e20`
- `0x1800133a0`
- `0x180026138`
- `0x18005aa60`
- `0x180072f20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072ff4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073030`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072ff4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073030`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007308b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007308b`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180072f63`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180072f63`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180072fe0`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180072fe0`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180073020`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180073020`

## string_xrefs

- `0x180073000`: `OpenProcess`

## pseudocode

```c
__int64 __fastcall BfeGetRpcCallersProcessImageName(void *a1, _QWORD *a2)
{
  __int64 v2; // rbx
  int v3; // r8d
  char *v4; // rdi
  char *v5; // rax
  DWORD LastError; // eax
  __int64 v7; // rcx
  const char *v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rax
  unsigned int Pid; // [rsp+30h] [rbp-238h] BYREF
  DWORD dwSize[3]; // [rsp+34h] [rbp-234h] BYREF
  WCHAR ExeName[264]; // [rsp+40h] [rbp-228h] BYREF

  *a2 = 0;
  dwSize[0] = 260;
  Pid = 0;
  LODWORD(v2) = I_RpcBindingInqLocalClientPID(a1, &Pid);
  if ( !(_DWORD)v2 )
  {
    v5 = (char *)OpenProcess(0x1000u, 0, Pid);
    v4 = v5;
    if ( v5 )
    {
      if ( QueryFullProcessImageNameW(v5, 0, ExeName, dwSize) )
      {
        if ( dwSize[0] )
        {
          if ( dwSize[0] <= 0x103 )
          {
            v10 = WfpStringCopy(ExeName);
            goto LABEL_21;
          }
          v9 = 111;
        }
        else
        {
          v9 = 3;
        }
        v8 = "BfeGetRpcCallersProcessImageName";
LABEL_12:
        v10 = WfpReportSysErrorAsWinError(v7, v8, v9);
LABEL_21:
        v2 = v10;
        goto LABEL_22;
      }
      LastError = GetLastError();
      v8 = "QueryFullProcessImageNameW";
    }
    else
    {
      LastError = GetLastError();
      v8 = "OpenProcess";
    }
    v9 = LastError;
    goto LABEL_12;
  }
  v4 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_SsD(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, v3, 0, (__int64)"I_RpcBindingInqLocalClientPID", v2);
  }
  WfpCallUsermodeErrorUTMacro("I_RpcBindingInqLocalClientPID", (unsigned int)v2);
  if ( (int)v2 > 0 )
    LODWORD(v2) = (unsigned __int16)v2 | 0x80070000;
  v2 = (int)v2;
LABEL_22:
  if ( v2 && (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v4);
  return v2;
}

```

## disassembly

```asm
0x180072f20  mov     [rsp+arg_10], rbx
0x180072f25  mov     [rsp+arg_18], rsi
0x180072f2a  push    rdi
0x180072f2b  sub     rsp, 260h
0x180072f32  mov     rax, cs:__security_cookie
0x180072f39  xor     rax, rsp
0x180072f3c  mov     [rsp+268h+var_18], rax
0x180072f44  mov     rsi, rdx
0x180072f47  mov     qword ptr [rdx], 0
0x180072f4e  lea     rdx, [rsp+268h+Pid]; Pid
0x180072f53  mov     [rsp+268h+dwSize], 104h
0x180072f5b  mov     [rsp+268h+Pid], 0
0x180072f63  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180072f6a  nop     dword ptr [rax+rax+00h]
0x180072f6f  mov     ebx, eax
0x180072f71  test    eax, eax
0x180072f73  jz      short loc_180072FD4
0x180072f75  xor     edi, edi
0x180072f77  mov     rcx, cs:WPP_GLOBAL_Control
0x180072f7e  lea     rax, WPP_GLOBAL_Control
0x180072f85  lea     rsi, aIRpcbindinginq; "I_RpcBindingInqLocalClientPID"
0x180072f8c  cmp     rcx, rax
0x180072f8f  jz      short loc_180072FB5
0x180072f91  cmp     byte ptr [rcx+19h], 2
0x180072f95  jb      short loc_180072FB5
0x180072f97  test    byte ptr [rcx+1Ch], 1
0x180072f9b  jz      short loc_180072FB5
0x180072f9d  mov     rcx, [rcx+10h]
0x180072fa1  lea     edx, [rdi+18h]
0x180072fa4  mov     [rsp+268h+var_240], ebx
0x180072fa8  xor     r9d, r9d
0x180072fab  mov     [rsp+268h+var_248], rsi
0x180072fb0  call    WPP_SF_SsD
0x180072fb5  mov     edx, ebx
0x180072fb7  mov     rcx, rsi
0x180072fba  call    WfpCallUsermodeErrorUTMacro
0x180072fbf  test    ebx, ebx
0x180072fc1  jle     short loc_180072FCC
0x180072fc3  movzx   ebx, bx
0x180072fc6  or      ebx, 80070000h
0x180072fcc  movsxd  rbx, ebx
0x180072fcf  jmp     loc_180073079
0x180072fd4  mov     r8d, [rsp+268h+Pid]; dwProcessId
0x180072fd9  xor     edx, edx; bInheritHandle
0x180072fdb  mov     ecx, 1000h; dwDesiredAccess
0x180072fe0  call    cs:__imp_OpenProcess
0x180072fe7  nop     dword ptr [rax+rax+00h]
0x180072fec  mov     rdi, rax
0x180072fef  test    rax, rax
0x180072ff2  jnz     short loc_180073011
0x180072ff4  call    cs:__imp_GetLastError
0x180072ffb  nop     dword ptr [rax+rax+00h]
0x180073000  lea     rdx, aOpenprocess; "OpenProcess"
0x180073007  mov     r8d, eax
0x18007300a  call    WfpReportSysErrorAsWinError
0x18007300f  jmp     short loc_180073076
0x180073011  lea     r9, [rsp+268h+dwSize]; lpdwSize
0x180073016  xor     edx, edx; dwFlags
0x180073018  lea     r8, [rsp+268h+ExeName]; lpExeName
0x18007301d  mov     rcx, rax; hProcess
0x180073020  call    cs:__imp_QueryFullProcessImageNameW
0x180073027  nop     dword ptr [rax+rax+00h]
0x18007302c  test    eax, eax
0x18007302e  jnz     short loc_180073045
0x180073030  call    cs:__imp_GetLastError
0x180073037  nop     dword ptr [rax+rax+00h]
0x18007303c  lea     rdx, aQueryfullproce; "QueryFullProcessImageNameW"
0x180073043  jmp     short loc_180073007
0x180073045  mov     eax, [rsp+268h+dwSize]
0x180073049  test    eax, eax
0x18007304b  jnz     short loc_18007305A
0x18007304d  lea     r8d, [rax+3]
0x180073051  lea     rdx, aBfegetrpccalle; "BfeGetRpcCallersProcessImageName"
0x180073058  jmp     short loc_18007300A
0x18007305a  cmp     eax, 103h
0x18007305f  jbe     short loc_180073069
0x180073061  mov     r8d, 6Fh ; 'o'
0x180073067  jmp     short loc_180073051
0x180073069  mov     r8, rsi
0x18007306c  lea     rcx, [rsp+268h+ExeName]; Src
0x180073071  call    WfpStringCopy
0x180073076  mov     rbx, rax
0x180073079  test    rbx, rbx
0x18007307c  jz      short loc_180073097
0x18007307e  lea     rax, [rdi-1]
0x180073082  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180073086  ja      short loc_180073097
0x180073088  mov     rcx, rdi; hObject
0x18007308b  call    cs:__imp_CloseHandle
0x180073092  nop     dword ptr [rax+rax+00h]
0x180073097  mov     rax, rbx
0x18007309a  mov     rcx, [rsp+268h+var_18]
0x1800730a2  xor     rcx, rsp; StackCookie
0x1800730a5  call    __security_check_cookie
0x1800730aa  lea     r11, [rsp+268h+var_8]
0x1800730b2  mov     rbx, [r11+20h]
0x1800730b6  mov     rsi, [r11+28h]
0x1800730ba  mov     rsp, r11
0x1800730bd  pop     rdi
0x1800730be  retn
```
