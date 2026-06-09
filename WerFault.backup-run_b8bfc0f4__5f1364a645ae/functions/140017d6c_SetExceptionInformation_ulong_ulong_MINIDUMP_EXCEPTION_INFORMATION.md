# SetExceptionInformation(ulong,ulong,_MINIDUMP_EXCEPTION_INFORMATION *)

- ea: `0x140017d6c`
- end: `0x140017eff`
- name: `?SetExceptionInformation@@YAJKKPEAU_MINIDUMP_EXCEPTION_INFORMATION@@@Z`
- size: `403`
- prototype: `__int64 __fastcall(DWORD dwThreadId, unsigned int, struct _MINIDUMP_EXCEPTION_INFORMATION *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140016cbc`

## callees

- `0x1400030a8`
- `0x1400032ef`
- `0x14001444c`
- `0x140014474`
- `0x140017d6c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x140017dd9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x140017dd9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140017e99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140017e99`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadContext` at `0x140017dfc`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadContext` at `0x140017dfc`

## pseudocode

```c
__int64 __fastcall SetExceptionInformation(DWORD dwThreadId, DWORD a2, struct _MINIDUMP_EXCEPTION_INFORMATION *a3)
{
  signed int v6; // edi
  PEXCEPTION_POINTERS ExceptionPointers; // rax
  CONTEXT *ContextRecord; // rbp
  PEXCEPTION_RECORD ExceptionRecord; // rsi
  char *v10; // rbx
  signed int v11; // eax
  signed int LastError_0; // eax

  if ( a3 )
  {
    ExceptionPointers = a3->ExceptionPointers;
    ContextRecord = ExceptionPointers->ContextRecord;
    ExceptionRecord = ExceptionPointers->ExceptionRecord;
    v10 = (char *)OpenThread(0x48u, 0, dwThreadId);
    if ( v10 == (char *)-1LL || v10 + 1 == (char *)1 )
    {
      LastError_0 = GetLastError_0();
      v6 = LastError_0;
      if ( LastError_0 > 0 )
        v6 = (unsigned __int16)LastError_0 | 0x80070000;
      if ( v6 >= 0 )
        v6 = -2147467259;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids,
          (unsigned int)v6);
      }
    }
    else
    {
      ContextRecord->ContextFlags = 1048607;
      if ( GetThreadContext(v10, ContextRecord) )
      {
        ExceptionRecord->ExceptionCode = a2;
        ExceptionRecord->ExceptionFlags = 1;
        ExceptionRecord->ExceptionRecord = 0;
        ExceptionRecord->ExceptionAddress = (PVOID)ContextRecord->Rip;
        ExceptionRecord->NumberParameters = 0;
        memset_0(ExceptionRecord->ExceptionInformation, 0, sizeof(ExceptionRecord->ExceptionInformation));
        a3->ThreadId = dwThreadId;
        a3->ClientPointers = 0;
        v6 = 0;
      }
      else
      {
        v11 = GetLastError_0();
        v6 = v11;
        if ( v11 > 0 )
          v6 = (unsigned __int16)v11 | 0x80070000;
        if ( v6 >= 0 )
          v6 = -2147467259;
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            12,
            WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids,
            (unsigned int)v6);
        }
      }
      CloseHandle(v10);
    }
  }
  else
  {
    v6 = -2147024809;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140017d6c  push    rbx
0x140017d6e  push    rbp
0x140017d6f  push    rsi
0x140017d70  push    rdi
0x140017d71  push    r14
0x140017d73  push    r15
0x140017d75  sub     rsp, 28h
0x140017d79  mov     rdi, r8
0x140017d7c  mov     r15d, edx
0x140017d7f  mov     r14d, ecx
0x140017d82  test    r8, r8
0x140017d85  jnz     short loc_140017DC6
0x140017d87  mov     edi, 80070057h
0x140017d8c  mov     rcx, cs:WPP_GLOBAL_Control
0x140017d93  lea     rax, WPP_GLOBAL_Control
0x140017d9a  cmp     rcx, rax
0x140017d9d  jz      loc_140017EF0
0x140017da3  test    byte ptr [rcx+1Ch], 1
0x140017da7  jz      loc_140017EF0
0x140017dad  mov     rcx, [rcx+10h]
0x140017db1  lea     edx, [r8+0Ah]
0x140017db5  lea     r8, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids
0x140017dbc  call    WPP_SF_
0x140017dc1  jmp     loc_140017EF0
0x140017dc6  mov     rax, [r8+4]
0x140017dca  xor     edx, edx; bInheritHandle
0x140017dcc  mov     r8d, r14d; dwThreadId
0x140017dcf  mov     rbp, [rax+8]
0x140017dd3  lea     ecx, [rdx+48h]; dwDesiredAccess
0x140017dd6  mov     rsi, [rax]
0x140017dd9  call    cs:__imp_OpenThread
0x140017ddf  mov     rbx, rax
0x140017de2  inc     rax
0x140017de5  cmp     rax, 1
0x140017de9  jbe     loc_140017EA1
0x140017def  mov     rdx, rbp; lpContext
0x140017df2  mov     dword ptr [rbp+30h], 10001Fh
0x140017df9  mov     rcx, rbx; hThread
0x140017dfc  call    cs:__imp_GetThreadContext
0x140017e02  test    eax, eax
0x140017e04  jnz     short loc_140017E57
0x140017e06  call    GetLastError_0
0x140017e0b  mov     edi, eax
0x140017e0d  test    eax, eax
0x140017e0f  jle     short loc_140017E1A
0x140017e11  movzx   edi, ax
0x140017e14  or      edi, 80070000h
0x140017e1a  test    edi, edi
0x140017e1c  mov     eax, 80004005h
0x140017e21  cmovns  edi, eax
0x140017e24  mov     rcx, cs:WPP_GLOBAL_Control
0x140017e2b  lea     rax, WPP_GLOBAL_Control
0x140017e32  cmp     rcx, rax
0x140017e35  jz      short loc_140017E96
0x140017e37  test    byte ptr [rcx+1Ch], 1
0x140017e3b  jz      short loc_140017E96
0x140017e3d  mov     rcx, [rcx+10h]
0x140017e41  lea     r8, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids
0x140017e48  mov     edx, 0Ch
0x140017e4d  mov     r9d, edi
0x140017e50  call    WPP_SF_d
0x140017e55  jmp     short loc_140017E96
0x140017e57  xor     edx, edx; Val
0x140017e59  mov     [rsi], r15d
0x140017e5c  mov     dword ptr [rsi+4], 1
0x140017e63  lea     rcx, [rsi+20h]; void *
0x140017e67  mov     qword ptr [rsi+8], 0
0x140017e6f  mov     rax, [rbp+0F8h]
0x140017e76  lea     r8d, [rdx+78h]; Size
0x140017e7a  mov     [rsi+10h], rax
0x140017e7e  mov     dword ptr [rsi+18h], 0
0x140017e85  call    memset_0
0x140017e8a  mov     [rdi], r14d
0x140017e8d  mov     dword ptr [rdi+0Ch], 0
0x140017e94  xor     edi, edi
0x140017e96  mov     rcx, rbx; hObject
0x140017e99  call    cs:__imp_CloseHandle
0x140017e9f  jmp     short loc_140017EF0
0x140017ea1  call    GetLastError_0
0x140017ea6  mov     edi, eax
0x140017ea8  test    eax, eax
0x140017eaa  jle     short loc_140017EB5
0x140017eac  movzx   edi, ax
0x140017eaf  or      edi, 80070000h
0x140017eb5  test    edi, edi
0x140017eb7  mov     eax, 80004005h
0x140017ebc  cmovns  edi, eax
0x140017ebf  mov     rcx, cs:WPP_GLOBAL_Control
0x140017ec6  lea     rax, WPP_GLOBAL_Control
0x140017ecd  cmp     rcx, rax
0x140017ed0  jz      short loc_140017EF0
0x140017ed2  test    byte ptr [rcx+1Ch], 1
0x140017ed6  jz      short loc_140017EF0
0x140017ed8  mov     rcx, [rcx+10h]
0x140017edc  lea     r8, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids
0x140017ee3  mov     edx, 0Bh
0x140017ee8  mov     r9d, edi
0x140017eeb  call    WPP_SF_d
0x140017ef0  mov     eax, edi
0x140017ef2  add     rsp, 28h
0x140017ef6  pop     r15
0x140017ef8  pop     r14
0x140017efa  pop     rdi
0x140017efb  pop     rsi
0x140017efc  pop     rbp
0x140017efd  pop     rbx
0x140017efe  retn
```
