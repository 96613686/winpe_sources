# CHangReport::SetHangExceptionInformation(void *,ulong,_EXCEPTION_POINTERS *)

- ea: `0x14001f44c`
- end: `0x14001f607`
- name: `?SetHangExceptionInformation@CHangReport@@CAJPEAXKPEAU_EXCEPTION_POINTERS@@@Z`
- size: `443`
- prototype: `__int64 __fastcall(HANDLE hThread, unsigned int, struct _EXCEPTION_POINTERS *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140020c20`

## callees

- `0x140002470`
- `0x1400030a8`
- `0x14001444c`
- `0x140014474`
- `0x140015b40`
- `0x14001f44c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f4f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f4f0`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadContext` at `0x14001f4e6`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadContext` at `0x14001f4e6`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x14001f568`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x14001f568`

## pseudocode

```c
__int64 __fastcall CHangReport::SetHangExceptionInformation(HANDLE hThread, DWORD a2, struct _EXCEPTION_POINTERS *a3)
{
  signed int LastError; // eax
  unsigned int v6; // ebx
  PCONTEXT ContextRecord; // rcx
  __int64 v8; // rcx
  _BYTE Source2[48]; // [rsp+20h] [rbp-4E8h] BYREF
  int v11; // [rsp+50h] [rbp-4B8h]

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
      v11 = 1048607;
      if ( RtlCompareMemory(ContextRecord, Source2, 0x4D0u) == 1232 )
      {
        v6 = -2147467259;
        MicrosoftTelemetryAssertTriggeredNoArgs(v8);
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
0x14001f44c  mov     [rsp+arg_8], rbx
0x14001f451  push    rdi
0x14001f452  sub     rsp, 500h
0x14001f459  mov     rax, cs:__security_cookie
0x14001f460  xor     rax, rsp
0x14001f463  mov     [rsp+508h+var_18], rax
0x14001f46b  mov     rbx, r8
0x14001f46e  mov     rdi, rcx
0x14001f471  test    r8, r8
0x14001f474  jz      loc_14001F5B3
0x14001f47a  cmp     qword ptr [r8+8], 0
0x14001f47f  jz      loc_14001F5B3
0x14001f485  mov     rax, [r8]
0x14001f488  test    rax, rax
0x14001f48b  jz      loc_14001F5B3
0x14001f491  test    rcx, rcx
0x14001f494  jz      loc_14001F5B3
0x14001f49a  mov     [rax], edx
0x14001f49c  mov     rax, [r8]
0x14001f49f  mov     dword ptr [rax+4], 1
0x14001f4a6  mov     rax, [r8+8]
0x14001f4aa  mov     rdx, [r8]
0x14001f4ad  mov     rax, [rax+0F8h]
0x14001f4b4  mov     [rdx+10h], rax
0x14001f4b8  xor     edx, edx; Val
0x14001f4ba  mov     rax, [r8]
0x14001f4bd  mov     dword ptr [rax+18h], 0
0x14001f4c4  mov     rcx, [r8]
0x14001f4c7  lea     r8d, [rdx+78h]; Size
0x14001f4cb  add     rcx, 20h ; ' '; void *
0x14001f4cf  call    memset_0
0x14001f4d4  mov     rax, [rbx+8]
0x14001f4d8  mov     rcx, rdi; hThread
0x14001f4db  mov     dword ptr [rax+30h], 10001Fh
0x14001f4e2  mov     rdx, [rbx+8]; lpContext
0x14001f4e6  call    cs:__imp_GetThreadContext
0x14001f4ec  test    eax, eax
0x14001f4ee  jnz     short loc_14001F540
0x14001f4f0  call    cs:__imp_GetLastError
0x14001f4f6  mov     ebx, eax
0x14001f4f8  test    eax, eax
0x14001f4fa  jle     short loc_14001F505
0x14001f4fc  movzx   ebx, ax
0x14001f4ff  or      ebx, 80070000h
0x14001f505  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f50c  lea     rax, WPP_GLOBAL_Control
0x14001f513  cmp     rcx, rax
0x14001f516  jz      loc_14001F5AF
0x14001f51c  test    byte ptr [rcx+1Ch], 1
0x14001f520  jz      loc_14001F5AF
0x14001f526  mov     rcx, [rcx+10h]
0x14001f52a  lea     r8, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x14001f531  mov     edx, 58h ; 'X'
0x14001f536  mov     r9d, ebx
0x14001f539  call    WPP_SF_d
0x14001f53e  jmp     short loc_14001F5AF
0x14001f540  mov     edi, 4D0h
0x14001f545  lea     rcx, [rsp+508h+Source2]; void *
0x14001f54a  mov     r8d, edi; Size
0x14001f54d  xor     edx, edx; Val
0x14001f54f  call    memset_0
0x14001f554  mov     rcx, [rbx+8]; Source1
0x14001f558  lea     rdx, [rsp+508h+Source2]; Source2
0x14001f55d  mov     r8d, edi; Length
0x14001f560  mov     [rsp+508h+var_4B8], 10001Fh
0x14001f568  call    cs:__imp_RtlCompareMemory
0x14001f56e  cmp     rax, rdi
0x14001f571  jnz     short loc_14001F5AD
0x14001f573  mov     ebx, 80004005h
0x14001f578  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001f57d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f584  lea     rax, WPP_GLOBAL_Control
0x14001f58b  cmp     rcx, rax
0x14001f58e  jz      short loc_14001F5AF
0x14001f590  test    byte ptr [rcx+1Ch], 1
0x14001f594  jz      short loc_14001F5AF
0x14001f596  mov     rcx, [rcx+10h]
0x14001f59a  lea     r8, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x14001f5a1  mov     edx, 59h ; 'Y'
0x14001f5a6  call    WPP_SF_
0x14001f5ab  jmp     short loc_14001F5AF
0x14001f5ad  xor     ebx, ebx
0x14001f5af  mov     eax, ebx
0x14001f5b1  jmp     short loc_14001F5E6
0x14001f5b3  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f5ba  lea     rax, WPP_GLOBAL_Control
0x14001f5c1  cmp     rcx, rax
0x14001f5c4  jz      short loc_14001F5E1
0x14001f5c6  test    byte ptr [rcx+1Ch], 1
0x14001f5ca  jz      short loc_14001F5E1
0x14001f5cc  mov     rcx, [rcx+10h]
0x14001f5d0  lea     r8, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x14001f5d7  mov     edx, 57h ; 'W'
0x14001f5dc  call    WPP_SF_
0x14001f5e1  mov     eax, 80070057h
0x14001f5e6  mov     rcx, [rsp+508h+var_18]
0x14001f5ee  xor     rcx, rsp; StackCookie
0x14001f5f1  call    __security_check_cookie
0x14001f5f6  mov     rbx, [rsp+508h+arg_8]
0x14001f5fe  add     rsp, 500h
0x14001f605  pop     rdi
0x14001f606  retn
```
