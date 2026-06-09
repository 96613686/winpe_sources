# Log_Text_F

- ea: `0x14003ec14`
- end: `0x14003eeba`
- name: `Log_Text_F`
- size: `678`
- prototype: `__int64(_QWORD, _QWORD, const char *, ...)`
- caller_count: `109`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14000917c`
- `0x14000a920`
- `0x14000af10`
- `0x14000b1ac`
- `0x14000bc7c`
- `0x14000d274`
- `0x14000d65c`
- `0x14000d91c`
- `0x14000e240`
- `0x14000e51c`
- `0x14000f448`
- `0x14000fcb8`
- `0x1400100a4`
- `0x140010258`
- `0x140011920`
- `0x140011fd0`
- `0x1400120e0`
- `0x1400127ac`
- `0x140012984`
- `0x140012f64`
- `0x140013170`
- `0x140013ed4`
- `0x14001a54c`
- `0x14001e350`
- `0x14001e5b0`
- `0x14001e684`
- `0x14001e7a8`
- `0x14001f108`
- `0x14001f5f8`
- `0x14001fc70`
- `0x140020f30`
- `0x14002d9a4`
- `0x14002e0a4`
- `0x14002e584`
- `0x14002e924`
- `0x14002f430`
- `0x14002fe20`
- `0x140032ec8`
- `0x1400337c4`
- `0x140033910`
- `0x140033bf4`
- `0x140034990`
- `0x14003b020`
- `0x14003b628`
- `0x14003baec`
- `0x14003bdf4`
- `0x14003c9e0`
- `0x14003d044`
- `0x14003d15c`
- `0x14003dbb4`

## callees

- `0x140002f80`
- `0x140002ff0`
- `0x140004e24`
- `0x14001a3cc`
- `0x14003ec14`
- `0x140113220`

## import_xrefs

- `ADVAPI32!EventEnabled` at `0x14003ecb8`
- `ADVAPI32!EventEnabled` at `0x14003ed7d`
- `ADVAPI32!EventEnabled` at `0x14003ecb8`
- `ADVAPI32!EventEnabled` at `0x14003ed7d`
- `KERNEL32!GetTickCount` at `0x14003ece3`
- `KERNEL32!GetTickCount` at `0x14003ece3`
- `KERNEL32!EnterCriticalSection` at `0x14003ee58`
- `KERNEL32!EnterCriticalSection` at `0x14003ee58`
- `KERNEL32!LeaveCriticalSection` at `0x14003ee95`
- `KERNEL32!LeaveCriticalSection` at `0x14003ee95`
- `KERNEL32!GetCurrentProcessId` at `0x14003ecd0`
- `KERNEL32!GetCurrentProcessId` at `0x14003ecd0`
- `KERNEL32!WriteFile` at `0x14003ee88`
- `KERNEL32!WriteFile` at `0x14003ee88`
- `msvcrt!_vsnprintf_s` at `0x14003ed5e`
- `msvcrt!_vsnprintf_s` at `0x14003ed5e`
- `msvcrt!_snprintf_s` at `0x14003ed10`
- `msvcrt!_snprintf_s` at `0x14003ed10`

## pseudocode

```c
void Log_Text_F(__int64 a1, int a2, const char *a3, ...)
{
  BOOLEAN v5; // al
  DWORD CurrentProcessId; // edi
  const char *v7; // rbx
  DWORD TickCount; // eax
  int v9; // eax
  unsigned __int64 v10; // rdx
  char *p_Buffer; // rcx
  size_t v12; // rbx
  char *v13; // rax
  int v14; // eax
  __int64 v15; // rdi
  __int64 v16; // r8
  char *v17; // rdx
  __int16 i; // cx
  unsigned __int64 v19; // rbx
  char *v20; // rax
  bool v21; // zf
  char *v22; // rbx
  DWORD NumberOfBytesWritten[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v24[16]; // [rsp+48h] [rbp-B8h] BYREF
  DWORD *v25; // [rsp+58h] [rbp-A8h]
  __int64 v26; // [rsp+60h] [rbp-A0h]
  char *v27; // [rsp+68h] [rbp-98h]
  int v28; // [rsp+70h] [rbp-90h]
  int v29; // [rsp+74h] [rbp-8Ch]
  char Buffer; // [rsp+80h] [rbp-80h] BYREF
  char v31; // [rsp+81h] [rbp-7Fh] BYREF
  _QWORD v32[8]; // [rsp+480h] [rbp+380h] BYREF
  va_list va; // [rsp+4E8h] [rbp+3E8h] BYREF

  va_start(va, a3);
  if ( dword_1401CBBA4 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 4LL) )
  {
    Init_thread_header(&dword_1401CBBA4);
    if ( dword_1401CBBA4 == -1 )
    {
      byte_1401CBB98 = *a3;
      Init_thread_footer(&dword_1401CBBA4);
    }
  }
  if ( *a3 )
  {
    v5 = EventEnabled(WINSAT_ETW_PROVIDER_Context, &AnsiTextMessageEv);
    if ( hFile != (HANDLE)-1LL || v5 )
    {
      CurrentProcessId = GetCurrentProcessId();
      v7 = (const char *)mlib::efn<char>(a1);
      TickCount = GetTickCount();
      v9 = _snprintf_s(
             &Buffer,
             0x400u,
             0xFFFFFFFFFFFFFFFFuLL,
             "%06u (%04u) - %s:%04d: ",
             TickCount,
             CurrentProcessId,
             v7,
             a2);
      if ( v9 > 0 )
      {
        v10 = v9;
        p_Buffer = &Buffer;
        *(_QWORD *)NumberOfBytesWritten = 0;
        v12 = 1024LL - v9;
        if ( (unsigned __int64)v9 >= 0x400 )
          v12 = 1024;
        v13 = &Buffer + v9;
        if ( v10 < 0x400 )
          p_Buffer = v13;
        v14 = _vsnprintf_s(p_Buffer, v12, 0xFFFFFFFFFFFFFFFFuLL, a3, va);
        v15 = v14;
        if ( v14 > 0 )
        {
          if ( !EventEnabled(WINSAT_ETW_PROVIDER_Context, &AnsiTextMessageEv) )
          {
LABEL_23:
            v19 = v12 - v15;
            if ( v19 < 2 )
              v19 = 2;
            v20 = (char *)v32 - v19;
            v21 = UngracefulShutdownInProgress == 0;
            v22 = (char *)v32 - v19 + 1;
            *v20 = 13;
            v20[1] = 10;
            if ( v21 )
            {
              EnterCriticalSection(&stru_1401C6570);
              if ( hFile != (HANDLE)-1LL )
              {
                NumberOfBytesWritten[0] = 0;
                WriteFile(hFile, &Buffer, (_DWORD)v22 - (unsigned int)&Buffer + 1, NumberOfBytesWritten, 0);
              }
              LeaveCriticalSection(&stru_1401C6570);
            }
            return;
          }
          v17 = &v31;
          for ( i = v15 - v12 + 1023; i; --i )
          {
            if ( *v17 == 32 && *(v17 - 1) == 45 )
            {
              ++v17;
              --i;
              break;
            }
            ++v17;
          }
          if ( !UngracefulShutdownInProgress )
          {
            if ( (Microsoft_Windows_WindowsSystemAssessmentToolEnableBits & 1) != 0 )
            {
              v27 = v17;
              LOWORD(NumberOfBytesWritten[0]) = i + 1;
              v28 = (unsigned __int16)(i + 1);
              v25 = NumberOfBytesWritten;
              v26 = 2;
              v29 = 0;
              McGenEventWrite_EventWriteTransfer(&WINSAT_ETW_PROVIDER_Context, &AnsiTextMessageEv, v16, 3, v24);
            }
            goto LABEL_23;
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x14003ec14  mov     [rsp-8+Format], r8
0x14003ec19  mov     qword ptr [rsp-8+arg_18], r9
0x14003ec1e  push    rbp
0x14003ec1f  push    rbx
0x14003ec20  push    rsi
0x14003ec21  push    rdi
0x14003ec22  push    r13
0x14003ec24  push    r14
0x14003ec26  lea     rbp, [rsp-398h]
0x14003ec2e  sub     rsp, 498h
0x14003ec35  mov     rax, cs:__security_cookie
0x14003ec3c  xor     rax, rsp
0x14003ec3f  mov     [rbp+3C0h+var_40], rax
0x14003ec46  mov     rax, gs:58h
0x14003ec4f  mov     rbx, rcx
0x14003ec52  mov     ecx, 4
0x14003ec57  mov     esi, edx
0x14003ec59  mov     rax, [rax]
0x14003ec5c  mov     eax, [rcx+rax]
0x14003ec5f  cmp     cs:dword_1401CBBA4, eax
0x14003ec65  jle     short loc_14003EC97
0x14003ec67  lea     rcx, dword_1401CBBA4
0x14003ec6e  call    _Init_thread_header
0x14003ec73  cmp     cs:dword_1401CBBA4, 0FFFFFFFFh
0x14003ec7a  jnz     short loc_14003EC97
0x14003ec7c  mov     rax, [rbp+3C0h+Format]
0x14003ec83  mov     cl, [rax]
0x14003ec85  mov     cs:byte_1401CBB98, cl
0x14003ec8b  lea     rcx, dword_1401CBBA4
0x14003ec92  call    _Init_thread_footer
0x14003ec97  mov     rax, [rbp+3C0h+Format]
0x14003ec9e  xor     r14d, r14d
0x14003eca1  cmp     [rax], r14b
0x14003eca4  jz      loc_14003EE9B
0x14003ecaa  mov     rcx, cs:WINSAT_ETW_PROVIDER_Context; RegHandle
0x14003ecb1  lea     rdx, AnsiTextMessageEv; EventDescriptor
0x14003ecb8  call    cs:__imp_EventEnabled
0x14003ecbe  cmp     cs:hFile, 0FFFFFFFFFFFFFFFFh
0x14003ecc6  jnz     short loc_14003ECD0
0x14003ecc8  test    al, al
0x14003ecca  jz      loc_14003EE9B
0x14003ecd0  call    cs:__imp_GetCurrentProcessId
0x14003ecd6  mov     rcx, rbx
0x14003ecd9  mov     edi, eax
0x14003ecdb  call    ??$efn@D@mlib@@YAPEBDPEBD@Z; mlib::efn<char>(char const *)
0x14003ece0  mov     rbx, rax
0x14003ece3  call    cs:__imp_GetTickCount
0x14003ece9  mov     [rsp+4C0h+var_488], esi
0x14003eced  lea     r9, a06u04uS04d; "%06u (%04u) - %s:%04d: "
0x14003ecf4  mov     [rsp+4C0h+var_490], rbx
0x14003ecf9  lea     rcx, [rbp+3C0h+Buffer]; Buffer
0x14003ecfd  mov     [rsp+4C0h+var_498], edi
0x14003ed01  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14003ed05  mov     edi, 400h
0x14003ed0a  mov     dword ptr [rsp+4C0h+ArgList], eax
0x14003ed0e  mov     edx, edi; BufferCount
0x14003ed10  call    cs:__imp__snprintf_s
0x14003ed16  test    eax, eax
0x14003ed18  jle     loc_14003EE9B
0x14003ed1e  mov     r9, [rbp+3C0h+Format]; Format
0x14003ed25  lea     r8, [rbp+3C0h+arg_18]
0x14003ed2c  movsxd  rdx, eax
0x14003ed2f  lea     rcx, [rbp+3C0h+Buffer]
0x14003ed33  mov     [rsp+4C0h+ArgList], r8; ArgList
0x14003ed38  lea     rax, [rbp+3C0h+Buffer]
0x14003ed3c  mov     ebx, edi
0x14003ed3e  mov     qword ptr [rsp+4C0h+NumberOfBytesWritten], r14
0x14003ed43  sub     rbx, rdx
0x14003ed46  cmp     rdx, rdi
0x14003ed49  cmovnb  rbx, rdi
0x14003ed4d  add     rax, rdx
0x14003ed50  cmp     rdx, rdi
0x14003ed53  mov     rdx, rbx; BufferCount
0x14003ed56  cmovb   rcx, rax; Buffer
0x14003ed5a  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14003ed5e  call    cs:__imp__vsnprintf_s
0x14003ed64  movsxd  rdi, eax
0x14003ed67  test    eax, eax
0x14003ed69  jle     loc_14003EE9B
0x14003ed6f  mov     rcx, cs:WINSAT_ETW_PROVIDER_Context; RegHandle
0x14003ed76  lea     rdx, AnsiTextMessageEv; EventDescriptor
0x14003ed7d  call    cs:__imp_EventEnabled
0x14003ed83  mov     esi, 1
0x14003ed88  lea     r13d, [rsi+1]
0x14003ed8c  test    al, al
0x14003ed8e  jz      loc_14003EE2A
0x14003ed94  mov     eax, 3FFh
0x14003ed99  lea     rdx, [rbp+3C0h+var_43F]
0x14003ed9d  movzx   ecx, di
0x14003eda0  sub     cx, bx
0x14003eda3  add     cx, ax
0x14003eda6  mov     eax, 0FFFFh
0x14003edab  test    cx, cx
0x14003edae  jz      short loc_14003EDC9
0x14003edb0  cmp     byte ptr [rdx], 20h ; ' '
0x14003edb3  jnz     short loc_14003EDBB
0x14003edb5  cmp     byte ptr [rdx-1], 2Dh ; '-'
0x14003edb9  jz      short loc_14003EDC3
0x14003edbb  add     rdx, rsi
0x14003edbe  add     cx, ax
0x14003edc1  jmp     short loc_14003EDAB
0x14003edc3  add     rdx, rsi
0x14003edc6  add     cx, ax
0x14003edc9  cmp     cs:UngracefulShutdownInProgress, r14b
0x14003edd0  jnz     loc_14003EE9B
0x14003edd6  test    cs:Microsoft_Windows_WindowsSystemAssessmentToolEnableBits, sil
0x14003eddd  jz      short loc_14003EE2A
0x14003eddf  add     cx, si
0x14003ede2  mov     [rsp+4C0h+var_458], rdx
0x14003ede7  movzx   eax, cx
0x14003edea  lea     rdx, AnsiTextMessageEv
0x14003edf1  lea     rcx, [rsp+4C0h+NumberOfBytesWritten]
0x14003edf6  mov     word ptr [rsp+4C0h+NumberOfBytesWritten], ax
0x14003edfb  mov     [rsp+4C0h+var_450], eax
0x14003edff  mov     r9d, 3
0x14003ee05  mov     [rsp+4C0h+var_468], rcx
0x14003ee0a  lea     rax, [rsp+4C0h+var_478]
0x14003ee0f  lea     rcx, WINSAT_ETW_PROVIDER_Context
0x14003ee16  mov     [rsp+4C0h+ArgList], rax
0x14003ee1b  mov     [rsp+4C0h+var_460], r13
0x14003ee20  mov     [rsp+4C0h+var_44C], r14d
0x14003ee25  call    McGenEventWrite_EventWriteTransfer
0x14003ee2a  sub     rbx, rdi
0x14003ee2d  lea     rax, [rbp+3C0h+var_40]
0x14003ee34  cmp     rbx, r13
0x14003ee37  cmovb   rbx, r13
0x14003ee3b  sub     rax, rbx
0x14003ee3e  cmp     cs:UngracefulShutdownInProgress, r14b
0x14003ee45  lea     rbx, [rax+1]
0x14003ee49  mov     byte ptr [rax], 0Dh
0x14003ee4c  mov     byte ptr [rbx], 0Ah
0x14003ee4f  jnz     short loc_14003EE9B
0x14003ee51  lea     rcx, stru_1401C6570; lpCriticalSection
0x14003ee58  call    cs:__imp_EnterCriticalSection
0x14003ee5e  mov     rcx, cs:hFile; hFile
0x14003ee65  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14003ee69  jz      short loc_14003EE8E
0x14003ee6b  lea     rax, [rbp+3C0h+Buffer]
0x14003ee6f  mov     [rsp+4C0h+NumberOfBytesWritten], r14d
0x14003ee74  sub     ebx, eax
0x14003ee76  mov     [rsp+4C0h+ArgList], r14; lpOverlapped
0x14003ee7b  lea     r9, [rsp+4C0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14003ee80  lea     rdx, [rbp+3C0h+Buffer]; lpBuffer
0x14003ee84  lea     r8d, [rsi+rbx]; nNumberOfBytesToWrite
0x14003ee88  call    cs:__imp_WriteFile
0x14003ee8e  lea     rcx, stru_1401C6570; lpCriticalSection
0x14003ee95  call    cs:__imp_LeaveCriticalSection
0x14003ee9b  mov     rcx, [rbp+3C0h+var_40]
0x14003eea2  xor     rcx, rsp; StackCookie
0x14003eea5  call    __security_check_cookie
0x14003eeaa  add     rsp, 498h
0x14003eeb1  pop     r14
0x14003eeb3  pop     r13
0x14003eeb5  pop     rdi
0x14003eeb6  pop     rsi
0x14003eeb7  pop     rbx
0x14003eeb8  pop     rbp
0x14003eeb9  retn
```
