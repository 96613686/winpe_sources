# Log_Text_F

- ea: `0x18000f0e8`
- end: `0x18000f2b8`
- name: `Log_Text_F`
- size: `464`
- prototype: `__int64(_QWORD, _QWORD, const char *, ...)`
- caller_count: `21`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x180002880`
- `0x18000f774`
- `0x18001a92c`
- `0x1800209a8`
- `0x180020dd8`
- `0x180020f40`
- `0x180020f70`
- `0x180020fa0`
- `0x180021070`
- `0x180021330`
- `0x1800213a4`
- `0x1800217fc`
- `0x180021f00`
- `0x180024248`
- `0x1800315f7`
- `0x180031778`
- `0x1800317ac`
- `0x1800317e6`
- `0x18003181a`
- `0x180031d67`
- `0x180031dca`

## callees

- `0x18000f0e8`
- `0x180012aa8`
- `0x180012b18`
- `0x18001ab90`
- `0x18001b564`
- `0x18002fb50`

## import_xrefs

- `msvcrt!_vsnprintf_s` at `0x18000f21b`
- `msvcrt!_vsnprintf_s` at `0x18000f21b`
- `msvcrt!_snprintf_s` at `0x18000f1c8`
- `msvcrt!_snprintf_s` at `0x18000f1c8`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x18000f23b`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x18000f23b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000f194`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000f194`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000f17b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000f17b`

## pseudocode

```c
char Log_Text_F(__int64 a1, int a2, const char *a3, ...)
{
  int v5; // eax
  DWORD CurrentProcessId; // edi
  const char *v7; // rbx
  DWORD TickCount; // eax
  unsigned __int64 v9; // rdx
  char *p_Buffer; // rcx
  size_t v11; // rdi
  char *v12; // rax
  int v13; // ebx
  __int64 v14; // rdx
  char *v15; // r9
  char Buffer; // [rsp+50h] [rbp-438h] BYREF
  char v18; // [rsp+51h] [rbp-437h] BYREF
  va_list va; // [rsp+4A8h] [rbp+20h] BYREF

  va_start(va, a3);
  if ( dword_180050680 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180050680);
    if ( dword_180050680 == -1 )
    {
      byte_180050670 = *a3;
      Init_thread_footer(&dword_180050680);
    }
  }
  LOBYTE(v5) = (_BYTE)a3;
  if ( *a3 )
  {
    CurrentProcessId = GetCurrentProcessId();
    v7 = (const char *)mlib::efn<char>(a1);
    TickCount = GetTickCount();
    v5 = _snprintf_s(
           &Buffer,
           0x400u,
           0xFFFFFFFFFFFFFFFFuLL,
           "%06u (%04u) - %s:%04d: ",
           TickCount,
           CurrentProcessId,
           v7,
           a2);
    if ( v5 > 0 )
    {
      v9 = v5;
      p_Buffer = &Buffer;
      v11 = 1024LL - v5;
      if ( (unsigned __int64)v5 >= 0x400 )
        v11 = 1024;
      v12 = &Buffer + v5;
      if ( v9 < 0x400 )
        p_Buffer = v12;
      v5 = _vsnprintf_s(p_Buffer, v11, 0xFFFFFFFFFFFFFFFFuLL, a3, va);
      v13 = v5;
      if ( v5 > 0 )
      {
        LOBYTE(v5) = EventEnabled(WINSATAPI_ETW_PROVIDER_Context, &AnsiTextMessageEv);
        if ( (_BYTE)v5 )
        {
          v15 = &v18;
          LOWORD(v13) = v13 - v11 + 1023;
          LOBYTE(v5) = 1;
          while ( (_WORD)v13 )
          {
            if ( *v15 == 32 && *(v15 - 1) == 45 )
            {
              ++v15;
              LOWORD(v13) = v13 - 1;
              break;
            }
            ++v15;
            LOWORD(v13) = v13 - 1;
          }
          if ( (WINSATAPI_ETW_PROVIDEREnableBits & 1) != 0 )
            LOBYTE(v5) = McTemplateU0hsr0_EventWriteTransfer(
                           &WINSATAPI_ETW_PROVIDER_Context,
                           v14,
                           (unsigned int)(v13 + 1),
                           v15);
        }
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18000f0e8  mov     [rsp+Format], r8
0x18000f0ed  mov     qword ptr [rsp+arg_18], r9
0x18000f0f2  push    rbx
0x18000f0f3  push    rbp
0x18000f0f4  push    rsi
0x18000f0f5  push    rdi
0x18000f0f6  sub     rsp, 468h
0x18000f0fd  mov     rax, cs:__security_cookie
0x18000f104  xor     rax, rsp
0x18000f107  mov     [rsp+488h+var_38], rax
0x18000f10f  mov     rax, gs:58h
0x18000f118  mov     rbx, rcx
0x18000f11b  mov     ecx, cs:_tls_index
0x18000f121  mov     esi, edx
0x18000f123  mov     edx, 4
0x18000f128  mov     rax, [rax+rcx*8]
0x18000f12c  mov     eax, [rdx+rax]
0x18000f12f  cmp     cs:dword_180050680, eax
0x18000f135  jle     short loc_18000F168
0x18000f137  lea     rcx, dword_180050680
0x18000f13e  call    _Init_thread_header
0x18000f143  cmp     cs:dword_180050680, 0FFFFFFFFh
0x18000f14a  jnz     short loc_18000F168
0x18000f14c  mov     rax, [rsp+488h+Format]
0x18000f154  lea     rcx, dword_180050680
0x18000f15b  mov     dl, [rax]
0x18000f15d  mov     cs:byte_180050670, dl
0x18000f163  call    _Init_thread_footer
0x18000f168  mov     rax, [rsp+488h+Format]
0x18000f170  xor     ebp, ebp
0x18000f172  cmp     [rax], bpl
0x18000f175  jz      loc_18000F29B
0x18000f17b  call    cs:__imp_GetCurrentProcessId
0x18000f182  nop     dword ptr [rax+rax+00h]
0x18000f187  mov     rcx, rbx
0x18000f18a  mov     edi, eax
0x18000f18c  call    ??$efn@D@mlib@@YAPEBDPEBD@Z; mlib::efn<char>(char const *)
0x18000f191  mov     rbx, rax
0x18000f194  call    cs:__imp_GetTickCount
0x18000f19b  nop     dword ptr [rax+rax+00h]
0x18000f1a0  mov     [rsp+488h+var_450], esi
0x18000f1a4  lea     r9, Format; "%06u (%04u) - %s:%04d: "
0x18000f1ab  mov     [rsp+488h+var_458], rbx
0x18000f1b0  lea     rcx, [rsp+488h+Buffer]; Buffer
0x18000f1b5  mov     ebx, 400h
0x18000f1ba  mov     [rsp+488h+var_460], edi
0x18000f1be  mov     edx, ebx; BufferCount
0x18000f1c0  mov     dword ptr [rsp+488h+ArgList], eax
0x18000f1c4  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18000f1c8  call    cs:__imp__snprintf_s
0x18000f1cf  nop     dword ptr [rax+rax+00h]
0x18000f1d4  test    eax, eax
0x18000f1d6  jle     loc_18000F29B
0x18000f1dc  movsxd  rdx, eax
0x18000f1df  lea     r9, [rsp+488h+arg_18]
0x18000f1e7  mov     [rsp+488h+ArgList], r9; ArgList
0x18000f1ec  lea     rax, [rsp+488h+Buffer]
0x18000f1f1  mov     r9, [rsp+488h+Format]; Format
0x18000f1f9  lea     rcx, [rsp+488h+Buffer]
0x18000f1fe  mov     edi, ebx
0x18000f200  sub     rdi, rdx
0x18000f203  cmp     rdx, rbx
0x18000f206  cmovnb  rdi, rbx
0x18000f20a  add     rax, rdx
0x18000f20d  cmp     rdx, rbx
0x18000f210  mov     rdx, rdi; BufferCount
0x18000f213  cmovb   rcx, rax; Buffer
0x18000f217  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18000f21b  call    cs:__imp__vsnprintf_s
0x18000f222  nop     dword ptr [rax+rax+00h]
0x18000f227  mov     ebx, eax
0x18000f229  test    eax, eax
0x18000f22b  jle     short loc_18000F29B
0x18000f22d  mov     rcx, cs:WINSATAPI_ETW_PROVIDER_Context; RegHandle
0x18000f234  lea     rdx, AnsiTextMessageEv; EventDescriptor
0x18000f23b  call    cs:__imp_EventEnabled
0x18000f242  nop     dword ptr [rax+rax+00h]
0x18000f247  test    al, al
0x18000f249  jz      short loc_18000F29B
0x18000f24b  mov     eax, 3FFh
0x18000f250  lea     r9, [rsp+488h+var_437]
0x18000f255  sub     bx, di
0x18000f258  mov     ecx, 0FFFFh
0x18000f25d  add     bx, ax
0x18000f260  lea     eax, [rbp+1]
0x18000f263  test    bx, bx
0x18000f266  jz      short loc_18000F283
0x18000f268  cmp     byte ptr [r9], 20h ; ' '
0x18000f26c  jnz     short loc_18000F275
0x18000f26e  cmp     byte ptr [r9-1], 2Dh ; '-'
0x18000f273  jz      short loc_18000F27D
0x18000f275  add     r9, rax
0x18000f278  add     bx, cx
0x18000f27b  jmp     short loc_18000F263
0x18000f27d  add     r9, rax
0x18000f280  add     bx, cx
0x18000f283  test    cs:WINSATAPI_ETW_PROVIDEREnableBits, al
0x18000f289  jz      short loc_18000F29B
0x18000f28b  lea     r8d, [rax+rbx]
0x18000f28f  lea     rcx, WINSATAPI_ETW_PROVIDER_Context
0x18000f296  call    McTemplateU0hsr0_EventWriteTransfer
0x18000f29b  mov     rcx, [rsp+488h+var_38]
0x18000f2a3  xor     rcx, rsp; StackCookie
0x18000f2a6  call    __security_check_cookie
0x18000f2ab  add     rsp, 468h
0x18000f2b2  pop     rdi
0x18000f2b3  pop     rsi
0x18000f2b4  pop     rbp
0x18000f2b5  pop     rbx
0x18000f2b6  retn
```
