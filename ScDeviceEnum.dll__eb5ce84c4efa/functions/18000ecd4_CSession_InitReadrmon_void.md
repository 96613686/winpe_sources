# CSession::_InitReadrmon(void)

- ea: `0x18000ecd4`
- end: `0x18000ee65`
- name: `?_InitReadrmon@CSession@@AEAAJXZ`
- size: `401`
- prototype: `__int64 __fastcall(HANDLE *this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000d754`

## callees

- `0x180006d40`
- `0x1800071d4`
- `0x18000c8ac`
- `0x18000d14c`
- `0x18000d570`
- `0x18000ecd4`
- `0x18001c758`
- `0x18001e020`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000edf4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000edf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ed60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ed60`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000ed56`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000ed56`

## string_xrefs

- `0x18000ed08`: `CSession::_InitReadrmon`

## pseudocode

```c
__int64 __fastcall CSession::_InitReadrmon(HANDLE *this)
{
  signed int LastError; // eax
  __int64 v3; // rcx
  int v4; // eax
  unsigned int v5; // ebx
  unsigned int v7; // [rsp+30h] [rbp-50h] BYREF
  char v8; // [rsp+34h] [rbp-4Ch] BYREF
  __int16 v9; // [rsp+35h] [rbp-4Bh]
  int v10; // [rsp+38h] [rbp-48h] BYREF
  _QWORD *v11; // [rsp+40h] [rbp-40h] BYREF
  _QWORD v12[3]; // [rsp+48h] [rbp-38h] BYREF
  char v13[24]; // [rsp+60h] [rbp-20h] BYREF

  v7 = 0;
  v10 = 0;
  strcpy(v13, "CSession::_InitReadrmon");
  v12[0] = v13;
  v12[1] = &v10;
  v12[2] = &v7;
  lambda_c31ae6585624ce606d045e361ca8fd8c_::operator()(v12);
  v10 = 1;
  v11 = v12;
  if ( !SetThreadToken(0, this[3]) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v7 = LastError;
    WppTraceIndent(v3, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)&WPP_c994ce8613043ca68e2941225ff180e5_Traceguids,
        (_DWORD)WPP_pszIndent,
        v7);
    }
    goto LABEL_13;
  }
  v9 = 258;
  this[4] = HANDLE_FLAG_INHERIT;
  this[5] = 0;
  this[6] = 0;
  *((_DWORD *)this + 15) = 1;
  this[8] = GetProcessHeap();
  *((_DWORD *)this + 18) = 0;
  v4 = ReaderMonitorInitialize(this + 4);
  v5 = v4;
  if ( !v4 )
  {
    wil::details::ScopeExitFnGuard__lambda_50cef3df7a2899e4d80253e7bc680178___::operator()(&v8);
LABEL_13:
    v5 = v7;
    goto LABEL_14;
  }
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  v7 = v5;
  wil::details::ScopeExitFnGuard__lambda_50cef3df7a2899e4d80253e7bc680178___::operator()(&v8);
LABEL_14:
  WppTraceUnwinder__lambda_c31ae6585624ce606d045e361ca8fd8c____::_WppTraceUnwinder__lambda_c31ae6585624ce606d045e361ca8fd8c____(&v11);
  return v5;
}

```

## disassembly

```asm
0x18000ecd4  mov     [rsp-8+arg_8], rbx
0x18000ecd9  mov     [rsp-8+arg_10], rdi
0x18000ecde  push    rbp
0x18000ecdf  mov     rbp, rsp
0x18000ece2  sub     rsp, 80h
0x18000ece9  mov     rax, cs:__security_cookie
0x18000ecf0  xor     rax, rsp
0x18000ecf3  mov     [rbp+var_8], rax
0x18000ecf7  mov     rdi, rcx
0x18000ecfa  mov     [rbp+var_50], 0
0x18000ed01  mov     [rbp+var_48], 0
0x18000ed08  movups  xmm0, xmmword ptr cs:aCsessionInitre; "CSession::_InitReadrmon"
0x18000ed0f  movups  xmmword ptr [rbp+var_20], xmm0
0x18000ed13  movsd   xmm1, qword ptr cs:aCsessionInitre+10h; "eadrmon"
0x18000ed1b  movsd   qword ptr [rbp+var_20+10h], xmm1
0x18000ed20  lea     rax, [rbp+var_20]
0x18000ed24  mov     [rbp+var_38], rax
0x18000ed28  lea     rax, [rbp+var_48]
0x18000ed2c  mov     [rbp+var_30], rax
0x18000ed30  lea     rax, [rbp+var_50]
0x18000ed34  mov     [rbp+var_28], rax
0x18000ed38  lea     rcx, [rbp+var_38]
0x18000ed3c  call    _lambda_c31ae6585624ce606d045e361ca8fd8c___operator__
0x18000ed41  mov     [rbp+var_48], 1
0x18000ed48  lea     rax, [rbp+var_38]
0x18000ed4c  mov     [rbp+var_40], rax
0x18000ed50  mov     rdx, [rdi+18h]; Token
0x18000ed54  xor     ecx, ecx; Thread
0x18000ed56  call    cs:__imp_SetThreadToken
0x18000ed5c  test    eax, eax
0x18000ed5e  jnz     short loc_18000EDCF
0x18000ed60  call    cs:__imp_GetLastError
0x18000ed66  test    eax, eax
0x18000ed68  jle     short loc_18000ED72
0x18000ed6a  movzx   eax, ax
0x18000ed6d  or      eax, 80070000h
0x18000ed72  mov     [rbp+var_50], eax
0x18000ed75  mov     edx, 2
0x18000ed7a  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000ed7f  lea     rax, WPP_GLOBAL_Control
0x18000ed86  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed8d  cmp     rcx, rax
0x18000ed90  jz      loc_18000EE36
0x18000ed96  test    byte ptr [rcx+1Ch], 1
0x18000ed9a  jz      loc_18000EE36
0x18000eda0  cmp     byte ptr [rcx+19h], 2
0x18000eda4  jb      loc_18000EE36
0x18000edaa  mov     edx, 0Eh
0x18000edaf  mov     eax, [rbp+var_50]
0x18000edb2  mov     [rsp+80h+var_60], eax
0x18000edb6  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000edbd  lea     r8, WPP_c994ce8613043ca68e2941225ff180e5_Traceguids
0x18000edc4  mov     rcx, [rcx+10h]
0x18000edc8  call    WPP_SF_sd
0x18000edcd  jmp     short loc_18000EE36
0x18000edcf  mov     [rbp+var_4B], 102h
0x18000edd5  mov     qword ptr [rdi+20h], 1
0x18000eddd  mov     qword ptr [rdi+28h], 0
0x18000ede5  mov     qword ptr [rdi+30h], 0
0x18000eded  mov     dword ptr [rdi+3Ch], 1
0x18000edf4  call    cs:__imp_GetProcessHeap
0x18000edfa  mov     [rdi+40h], rax
0x18000edfe  mov     dword ptr [rdi+48h], 0
0x18000ee05  lea     rcx, [rdi+20h]
0x18000ee09  call    ReaderMonitorInitialize
0x18000ee0e  mov     ebx, eax
0x18000ee10  test    eax, eax
0x18000ee12  jz      short loc_18000EE2D
0x18000ee14  jle     short loc_18000EE1F
0x18000ee16  movzx   ebx, ax
0x18000ee19  or      ebx, 80070000h
0x18000ee1f  mov     [rbp+var_50], ebx
0x18000ee22  lea     rcx, [rbp+var_4C]
0x18000ee26  call    wil__details__ScopeExitFnGuard__lambda_50cef3df7a2899e4d80253e7bc680178_____operator__
0x18000ee2b  jmp     short loc_18000EE39
0x18000ee2d  lea     rcx, [rbp+var_4C]
0x18000ee31  call    wil__details__ScopeExitFnGuard__lambda_50cef3df7a2899e4d80253e7bc680178_____operator__
0x18000ee36  mov     ebx, [rbp+var_50]
0x18000ee39  lea     rcx, [rbp+var_40]
0x18000ee3d  call    WppTraceUnwinder__lambda_c31ae6585624ce606d045e361ca8fd8c_______WppTraceUnwinder__lambda_c31ae6585624ce606d045e361ca8fd8c____
0x18000ee42  mov     eax, ebx
0x18000ee44  mov     rcx, [rbp+var_8]
0x18000ee48  xor     rcx, rsp; StackCookie
0x18000ee4b  call    __security_check_cookie
0x18000ee50  lea     r11, [rsp+80h+var_s0]
0x18000ee58  mov     rbx, [r11+18h]
0x18000ee5c  mov     rdi, [r11+20h]
0x18000ee60  mov     rsp, r11
0x18000ee63  pop     rbp
0x18000ee64  retn
```
