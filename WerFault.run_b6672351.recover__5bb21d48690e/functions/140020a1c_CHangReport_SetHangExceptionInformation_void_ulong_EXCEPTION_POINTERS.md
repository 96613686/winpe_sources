# CHangReport::SetHangExceptionInformation(void *,ulong,_EXCEPTION_POINTERS *)

- ea: `0x140020a1c`
- end: `0x140020bea`
- name: `?SetHangExceptionInformation@CHangReport@@CAJPEAXKPEAU_EXCEPTION_POINTERS@@@Z`
- size: `462`
- prototype: `__int64 __fastcall(HANDLE hThread, unsigned int, struct _EXCEPTION_POINTERS *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400221f4`

## callees

- `0x140002490`
- `0x1400030f8`
- `0x140014ee4`
- `0x140014f14`
- `0x1400166ec`
- `0x140020a1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020ac6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020ac6`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadContext` at `0x140020ab6`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadContext` at `0x140020ab6`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x140020b44`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x140020b44`

## pseudocode

```c
__int64 __fastcall CHangReport::SetHangExceptionInformation(HANDLE hThread, DWORD a2, struct _EXCEPTION_POINTERS *a3)
{
  signed int LastError; // eax
  unsigned int v6; // ebx
  PCONTEXT ContextRecord; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  _BYTE Source2[48]; // [rsp+20h] [rbp-4E8h] BYREF
  int v14; // [rsp+50h] [rbp-4B8h]

  if ( a3 && a3->ContextRecord && a3->ExceptionRecord && hThread )
  {
    a3->ExceptionRecord->ExceptionCode = a2;
    a3->ExceptionRecord->ExceptionFlags = 1;
    a3->ExceptionRecord->ExceptionAddress = (PVOID)a3->ContextRecord->Rip;
    a3->ExceptionRecord->NumberParameters = 0;
    memset_0(a3->ExceptionRecord->ExceptionInformation, 0, sizeof(a3->ExceptionRecord->ExceptionInformation));
    a3->ContextRecord->ContextFlags = 1048607;
    if ( GetThreadContext(hThread, a3->ContextRecord) )
    {
      memset_0(Source2, 0, 0x4D0u);
      ContextRecord = a3->ContextRecord;
      v14 = 1048607;
      if ( RtlCompareMemory(ContextRecord, Source2, 0x4D0u) == 1232 )
      {
        v6 = -2147467259;
        MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8, v10, v11);
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids);
        }
      }
      else
      {
        return 0;
      }
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids, v6);
      }
    }
    return v6;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids);
    }
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x140020a1c  mov     [rsp+arg_8], rbx
0x140020a21  push    rdi
0x140020a22  sub     rsp, 500h
0x140020a29  mov     rax, cs:__security_cookie
0x140020a30  xor     rax, rsp
0x140020a33  mov     [rsp+508h+var_18], rax
0x140020a3b  mov     rbx, r8
0x140020a3e  mov     rdi, rcx
0x140020a41  test    r8, r8
0x140020a44  jz      loc_140020B95
0x140020a4a  cmp     qword ptr [r8+8], 0
0x140020a4f  jz      loc_140020B95
0x140020a55  mov     rax, [r8]
0x140020a58  test    rax, rax
0x140020a5b  jz      loc_140020B95
0x140020a61  test    rcx, rcx
0x140020a64  jz      loc_140020B95
0x140020a6a  mov     [rax], edx
0x140020a6c  mov     rax, [r8]
0x140020a6f  mov     dword ptr [rax+4], 1
0x140020a76  mov     rax, [r8+8]
0x140020a7a  mov     rdx, [r8]
0x140020a7d  mov     rax, [rax+0F8h]
0x140020a84  mov     [rdx+10h], rax
0x140020a88  xor     edx, edx; Val
0x140020a8a  mov     rax, [r8]
0x140020a8d  mov     dword ptr [rax+18h], 0
0x140020a94  mov     rcx, [r8]
0x140020a97  lea     r8d, [rdx+78h]; Size
0x140020a9b  add     rcx, 20h ; ' '; void *
0x140020a9f  call    memset_0
0x140020aa4  mov     rax, [rbx+8]
0x140020aa8  mov     rcx, rdi; hThread
0x140020aab  mov     dword ptr [rax+30h], 10001Fh
0x140020ab2  mov     rdx, [rbx+8]; lpContext
0x140020ab6  call    cs:__imp_GetThreadContext
0x140020abd  nop     dword ptr [rax+rax+00h]
0x140020ac2  test    eax, eax
0x140020ac4  jnz     short loc_140020B1C
0x140020ac6  call    cs:__imp_GetLastError
0x140020acd  nop     dword ptr [rax+rax+00h]
0x140020ad2  mov     ebx, eax
0x140020ad4  test    eax, eax
0x140020ad6  jle     short loc_140020AE1
0x140020ad8  movzx   ebx, ax
0x140020adb  or      ebx, 80070000h
0x140020ae1  mov     rcx, cs:WPP_GLOBAL_Control
0x140020ae8  lea     rax, WPP_GLOBAL_Control
0x140020aef  cmp     rcx, rax
0x140020af2  jz      loc_140020B91
0x140020af8  test    byte ptr [rcx+1Ch], 1
0x140020afc  jz      loc_140020B91
0x140020b02  mov     rcx, [rcx+10h]
0x140020b06  lea     r8, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x140020b0d  mov     edx, 58h ; 'X'
0x140020b12  mov     r9d, ebx
0x140020b15  call    WPP_SF_d
0x140020b1a  jmp     short loc_140020B91
0x140020b1c  mov     edi, 4D0h
0x140020b21  lea     rcx, [rsp+508h+Source2]; void *
0x140020b26  mov     r8d, edi; Size
0x140020b29  xor     edx, edx; Val
0x140020b2b  call    memset_0
0x140020b30  mov     rcx, [rbx+8]; Source1
0x140020b34  lea     rdx, [rsp+508h+Source2]; Source2
0x140020b39  mov     r8d, edi; Length
0x140020b3c  mov     [rsp+508h+var_4B8], 10001Fh
0x140020b44  call    cs:__imp_RtlCompareMemory
0x140020b4b  nop     dword ptr [rax+rax+00h]
0x140020b50  cmp     rax, rdi
0x140020b53  jnz     short loc_140020B8F
0x140020b55  mov     ebx, 80004005h
0x140020b5a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140020b5f  mov     rcx, cs:WPP_GLOBAL_Control
0x140020b66  lea     rax, WPP_GLOBAL_Control
0x140020b6d  cmp     rcx, rax
0x140020b70  jz      short loc_140020B91
0x140020b72  test    byte ptr [rcx+1Ch], 1
0x140020b76  jz      short loc_140020B91
0x140020b78  mov     rcx, [rcx+10h]
0x140020b7c  lea     r8, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x140020b83  mov     edx, 59h ; 'Y'
0x140020b88  call    WPP_SF_
0x140020b8d  jmp     short loc_140020B91
0x140020b8f  xor     ebx, ebx
0x140020b91  mov     eax, ebx
0x140020b93  jmp     short loc_140020BC8
0x140020b95  mov     rcx, cs:WPP_GLOBAL_Control
0x140020b9c  lea     rax, WPP_GLOBAL_Control
0x140020ba3  cmp     rcx, rax
0x140020ba6  jz      short loc_140020BC3
0x140020ba8  test    byte ptr [rcx+1Ch], 1
0x140020bac  jz      short loc_140020BC3
0x140020bae  mov     rcx, [rcx+10h]
0x140020bb2  lea     r8, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x140020bb9  mov     edx, 57h ; 'W'
0x140020bbe  call    WPP_SF_
0x140020bc3  mov     eax, 80070057h
0x140020bc8  mov     rcx, [rsp+508h+var_18]
0x140020bd0  xor     rcx, rsp; StackCookie
0x140020bd3  call    __security_check_cookie
0x140020bd8  mov     rbx, [rsp+508h+arg_8]
0x140020be0  add     rsp, 500h
0x140020be7  pop     rdi
0x140020be8  retn
```
