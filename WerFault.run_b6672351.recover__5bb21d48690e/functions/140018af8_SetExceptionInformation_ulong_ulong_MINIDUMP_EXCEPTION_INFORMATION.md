# SetExceptionInformation(ulong,ulong,_MINIDUMP_EXCEPTION_INFORMATION *)

- ea: `0x140018af8`
- end: `0x140018c9e`
- name: `?SetExceptionInformation@@YAJKKPEAU_MINIDUMP_EXCEPTION_INFORMATION@@@Z`
- size: `422`
- prototype: `__int64 __fastcall(DWORD dwThreadId, unsigned int, struct _MINIDUMP_EXCEPTION_INFORMATION *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140017998`

## callees

- `0x1400030f8`
- `0x14000333f`
- `0x140014ee4`
- `0x140014f14`
- `0x140018af8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x140018b65`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x140018b65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140018c31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140018c31`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadContext` at `0x140018b8e`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadContext` at `0x140018b8e`

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
0x140018af8  push    rbx
0x140018afa  push    rbp
0x140018afb  push    rsi
0x140018afc  push    rdi
0x140018afd  push    r14
0x140018aff  push    r15
0x140018b01  sub     rsp, 28h
0x140018b05  mov     rdi, r8
0x140018b08  mov     r15d, edx
0x140018b0b  mov     r14d, ecx
0x140018b0e  test    r8, r8
0x140018b11  jnz     short loc_140018B52
0x140018b13  mov     edi, 80070057h
0x140018b18  mov     rcx, cs:WPP_GLOBAL_Control
0x140018b1f  lea     rax, WPP_GLOBAL_Control
0x140018b26  cmp     rcx, rax
0x140018b29  jz      loc_140018C8E
0x140018b2f  test    byte ptr [rcx+1Ch], 1
0x140018b33  jz      loc_140018C8E
0x140018b39  mov     rcx, [rcx+10h]
0x140018b3d  lea     edx, [r8+0Ah]
0x140018b41  lea     r8, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids
0x140018b48  call    WPP_SF_
0x140018b4d  jmp     loc_140018C8E
0x140018b52  mov     rax, [r8+4]
0x140018b56  xor     edx, edx; bInheritHandle
0x140018b58  mov     r8d, r14d; dwThreadId
0x140018b5b  mov     rbp, [rax+8]
0x140018b5f  lea     ecx, [rdx+48h]; dwDesiredAccess
0x140018b62  mov     rsi, [rax]
0x140018b65  call    cs:__imp_OpenThread
0x140018b6c  nop     dword ptr [rax+rax+00h]
0x140018b71  mov     rbx, rax
0x140018b74  inc     rax
0x140018b77  cmp     rax, 1
0x140018b7b  jbe     loc_140018C3F
0x140018b81  mov     rdx, rbp; lpContext
0x140018b84  mov     dword ptr [rbp+30h], 10001Fh
0x140018b8b  mov     rcx, rbx; hThread
0x140018b8e  call    cs:__imp_GetThreadContext
0x140018b95  nop     dword ptr [rax+rax+00h]
0x140018b9a  test    eax, eax
0x140018b9c  jnz     short loc_140018BEF
0x140018b9e  call    GetLastError_0
0x140018ba3  mov     edi, eax
0x140018ba5  test    eax, eax
0x140018ba7  jle     short loc_140018BB2
0x140018ba9  movzx   edi, ax
0x140018bac  or      edi, 80070000h
0x140018bb2  test    edi, edi
0x140018bb4  mov     eax, 80004005h
0x140018bb9  cmovns  edi, eax
0x140018bbc  mov     rcx, cs:WPP_GLOBAL_Control
0x140018bc3  lea     rax, WPP_GLOBAL_Control
0x140018bca  cmp     rcx, rax
0x140018bcd  jz      short loc_140018C2E
0x140018bcf  test    byte ptr [rcx+1Ch], 1
0x140018bd3  jz      short loc_140018C2E
0x140018bd5  mov     rcx, [rcx+10h]
0x140018bd9  lea     r8, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids
0x140018be0  mov     edx, 0Ch
0x140018be5  mov     r9d, edi
0x140018be8  call    WPP_SF_d
0x140018bed  jmp     short loc_140018C2E
0x140018bef  xor     edx, edx; Val
0x140018bf1  mov     [rsi], r15d
0x140018bf4  mov     dword ptr [rsi+4], 1
0x140018bfb  lea     rcx, [rsi+20h]; void *
0x140018bff  mov     qword ptr [rsi+8], 0
0x140018c07  mov     rax, [rbp+0F8h]
0x140018c0e  lea     r8d, [rdx+78h]; Size
0x140018c12  mov     [rsi+10h], rax
0x140018c16  mov     dword ptr [rsi+18h], 0
0x140018c1d  call    memset_0
0x140018c22  mov     [rdi], r14d
0x140018c25  mov     dword ptr [rdi+0Ch], 0
0x140018c2c  xor     edi, edi
0x140018c2e  mov     rcx, rbx; hObject
0x140018c31  call    cs:__imp_CloseHandle
0x140018c38  nop     dword ptr [rax+rax+00h]
0x140018c3d  jmp     short loc_140018C8E
0x140018c3f  call    GetLastError_0
0x140018c44  mov     edi, eax
0x140018c46  test    eax, eax
0x140018c48  jle     short loc_140018C53
0x140018c4a  movzx   edi, ax
0x140018c4d  or      edi, 80070000h
0x140018c53  test    edi, edi
0x140018c55  mov     eax, 80004005h
0x140018c5a  cmovns  edi, eax
0x140018c5d  mov     rcx, cs:WPP_GLOBAL_Control
0x140018c64  lea     rax, WPP_GLOBAL_Control
0x140018c6b  cmp     rcx, rax
0x140018c6e  jz      short loc_140018C8E
0x140018c70  test    byte ptr [rcx+1Ch], 1
0x140018c74  jz      short loc_140018C8E
0x140018c76  mov     rcx, [rcx+10h]
0x140018c7a  lea     r8, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids
0x140018c81  mov     edx, 0Bh
0x140018c86  mov     r9d, edi
0x140018c89  call    WPP_SF_d
0x140018c8e  mov     eax, edi
0x140018c90  add     rsp, 28h
0x140018c94  pop     r15
0x140018c96  pop     r14
0x140018c98  pop     rdi
0x140018c99  pop     rsi
0x140018c9a  pop     rbp
0x140018c9b  pop     rbx
0x140018c9c  retn
```
