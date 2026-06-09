# BfeGetRpcCallersProcessImageName

- ea: `0x1800707e0`
- end: `0x18007095b`
- name: `BfeGetRpcCallersProcessImageName`
- size: `379`
- prototype: `__int64 __fastcall(void *, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180063180`

## callees

- `0x18001236c`
- `0x180012400`
- `0x180012950`
- `0x180023a04`
- `0x180058b30`
- `0x1800707e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800708a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800708d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800708a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800708d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007092d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007092d`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180070823`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180070823`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18007089a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18007089a`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800708ce`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800708ce`

## string_xrefs

- `0x1800708ae`: `OpenProcess`

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
0x1800707e0  mov     [rsp+arg_10], rbx
0x1800707e5  mov     [rsp+arg_18], rsi
0x1800707ea  push    rdi
0x1800707eb  sub     rsp, 260h
0x1800707f2  mov     rax, cs:__security_cookie
0x1800707f9  xor     rax, rsp
0x1800707fc  mov     [rsp+268h+var_18], rax
0x180070804  mov     rsi, rdx
0x180070807  mov     qword ptr [rdx], 0
0x18007080e  lea     rdx, [rsp+268h+Pid]; Pid
0x180070813  mov     [rsp+268h+dwSize], 104h
0x18007081b  mov     [rsp+268h+Pid], 0
0x180070823  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180070829  mov     ebx, eax
0x18007082b  test    eax, eax
0x18007082d  jz      short loc_18007088E
0x18007082f  xor     edi, edi
0x180070831  mov     rcx, cs:WPP_GLOBAL_Control
0x180070838  lea     rax, WPP_GLOBAL_Control
0x18007083f  lea     rsi, aIRpcbindinginq; "I_RpcBindingInqLocalClientPID"
0x180070846  cmp     rcx, rax
0x180070849  jz      short loc_18007086F
0x18007084b  cmp     byte ptr [rcx+19h], 2
0x18007084f  jb      short loc_18007086F
0x180070851  test    byte ptr [rcx+1Ch], 1
0x180070855  jz      short loc_18007086F
0x180070857  mov     rcx, [rcx+10h]
0x18007085b  lea     edx, [rdi+18h]
0x18007085e  mov     [rsp+268h+var_240], ebx
0x180070862  xor     r9d, r9d
0x180070865  mov     [rsp+268h+var_248], rsi
0x18007086a  call    WPP_SF_SsD
0x18007086f  mov     edx, ebx
0x180070871  mov     rcx, rsi
0x180070874  call    WfpCallUsermodeErrorUTMacro
0x180070879  test    ebx, ebx
0x18007087b  jle     short loc_180070886
0x18007087d  movzx   ebx, bx
0x180070880  or      ebx, 80070000h
0x180070886  movsxd  rbx, ebx
0x180070889  jmp     loc_18007091B
0x18007088e  mov     r8d, [rsp+268h+Pid]; dwProcessId
0x180070893  xor     edx, edx; bInheritHandle
0x180070895  mov     ecx, 1000h; dwDesiredAccess
0x18007089a  call    cs:__imp_OpenProcess
0x1800708a0  mov     rdi, rax
0x1800708a3  test    rax, rax
0x1800708a6  jnz     short loc_1800708BF
0x1800708a8  call    cs:__imp_GetLastError
0x1800708ae  lea     rdx, aOpenprocess; "OpenProcess"
0x1800708b5  mov     r8d, eax
0x1800708b8  call    WfpReportSysErrorAsWinError
0x1800708bd  jmp     short loc_180070918
0x1800708bf  lea     r9, [rsp+268h+dwSize]; lpdwSize
0x1800708c4  xor     edx, edx; dwFlags
0x1800708c6  lea     r8, [rsp+268h+ExeName]; lpExeName
0x1800708cb  mov     rcx, rax; hProcess
0x1800708ce  call    cs:__imp_QueryFullProcessImageNameW
0x1800708d4  test    eax, eax
0x1800708d6  jnz     short loc_1800708E7
0x1800708d8  call    cs:__imp_GetLastError
0x1800708de  lea     rdx, aQueryfullproce; "QueryFullProcessImageNameW"
0x1800708e5  jmp     short loc_1800708B5
0x1800708e7  mov     eax, [rsp+268h+dwSize]
0x1800708eb  test    eax, eax
0x1800708ed  jnz     short loc_1800708FC
0x1800708ef  lea     r8d, [rax+3]
0x1800708f3  lea     rdx, aBfegetrpccalle; "BfeGetRpcCallersProcessImageName"
0x1800708fa  jmp     short loc_1800708B8
0x1800708fc  cmp     eax, 103h
0x180070901  jbe     short loc_18007090B
0x180070903  mov     r8d, 6Fh ; 'o'
0x180070909  jmp     short loc_1800708F3
0x18007090b  mov     r8, rsi
0x18007090e  lea     rcx, [rsp+268h+ExeName]; Src
0x180070913  call    WfpStringCopy
0x180070918  mov     rbx, rax
0x18007091b  test    rbx, rbx
0x18007091e  jz      short loc_180070933
0x180070920  lea     rax, [rdi-1]
0x180070924  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180070928  ja      short loc_180070933
0x18007092a  mov     rcx, rdi; hObject
0x18007092d  call    cs:__imp_CloseHandle
0x180070933  mov     rax, rbx
0x180070936  mov     rcx, [rsp+268h+var_18]
0x18007093e  xor     rcx, rsp; StackCookie
0x180070941  call    __security_check_cookie
0x180070946  lea     r11, [rsp+268h+var_8]
0x18007094e  mov     rbx, [r11+20h]
0x180070952  mov     rsi, [r11+28h]
0x180070956  mov     rsp, r11
0x180070959  pop     rdi
0x18007095a  retn
```
