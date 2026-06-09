# CWinHttpConnectionT<CEmptyType>::Init(ushort const *)

- ea: `0x18024b588`
- end: `0x18024b7f4`
- name: `?Init@?$CWinHttpConnectionT@VCEmptyType@@@@AEAAJPEBG@Z`
- size: `620`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18024aba0`

## callees

- `0x18009204c`
- `0x18009206c`
- `0x180099328`
- `0x18024b588`
- `0x18024baf8`
- `0x18024beb0`
- `0x18024bf18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18024b5fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18024b5fe`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18024b656`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18024b687`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18024b6bb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18024b656`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18024b687`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18024b6bb`
- `WINHTTP!WinHttpOpen` at `0x18024b5dd`
- `WINHTTP!WinHttpOpen` at `0x18024b5dd`
- `WINHTTP!WinHttpSetOption` at `0x18024b638`
- `WINHTTP!WinHttpSetOption` at `0x18024b71a`
- `WINHTTP!WinHttpSetOption` at `0x18024b638`
- `WINHTTP!WinHttpSetOption` at `0x18024b71a`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18024b7df`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18024b7df`

## pseudocode

```c
__int64 __fastcall CWinHttpConnectionT<CEmptyType>::Init(__int64 a1, __int64 a2)
{
  void *v3; // rsi
  DWORD LastError; // eax
  int IsPlatformGreaterOrEqualToVista; // eax
  unsigned int v6; // edi
  HANDLE EventW; // r14
  HANDLE v8; // rbx
  HANDLE v9; // r12
  int v10; // r13d
  bool v11; // zf
  HANDLE v13; // [rsp+30h] [rbp-30h] BYREF
  void *v14; // [rsp+38h] [rbp-28h] BYREF
  __int64 Buffer; // [rsp+40h] [rbp-20h] BYREF
  HANDLE v16[3]; // [rsp+48h] [rbp-18h] BYREF
  int v17; // [rsp+A8h] [rbp+48h] BYREF
  int v18; // [rsp+ACh] [rbp+4Ch]
  HANDLE v19; // [rsp+B0h] [rbp+50h] BYREF
  HANDLE v20; // [rsp+B8h] [rbp+58h] BYREF

  v18 = HIDWORD(a2);
  v14 = 0;
  v13 = 0;
  v20 = 0;
  v19 = 0;
  v16[0] = 0;
  v17 = 0;
  Buffer = 0;
  v3 = WinHttpOpen(L"Activation UX Library", 0, 0, 0, 0x10000000u);
  SH<void *,CWinHttpConnectionT<CEmptyType>::SH_HINTERNET>::Reset(&v14);
  if ( v3 )
  {
    v14 = v3;
    Buffer = a1;
    if ( WinHttpSetOption(v3, 0x2Du, &Buffer, 8u) )
    {
      EventW = CreateEventW(0, 1, 0, 0);
      SH<void *,SH_HANDLE>::Reset(&v13);
      if ( EventW )
      {
        v13 = EventW;
        v8 = CreateEventW(0, 1, 0, 0);
        SH<void *,SH_HANDLE>::Reset(&v20);
        if ( v8 )
        {
          v20 = v8;
          v9 = CreateEventW(0, 0, 0, 0);
          SH<void *,SH_HANDLE>::Reset(&v19);
          if ( v9 )
          {
            v19 = v9;
            IsPlatformGreaterOrEqualToVista = CMiscHelpersT<CEmptyType>::IsPlatformGreaterOrEqualToVista(&v17);
            v6 = IsPlatformGreaterOrEqualToVista;
            if ( IsPlatformGreaterOrEqualToVista < 0 )
              goto LABEL_4;
            v10 = v17;
            if ( v17 )
            {
              v16[0] = EventW;
              v11 = !WinHttpSetOption(v3, 0x63u, v16, 8u);
            }
            else
            {
              v11 = (WINHTTP_STATUS_CALLBACK)((char *)WinHttpSetStatusCallback(
                                                        v3,
                                                        CWinHttpConnectionT<CEmptyType>::WinHttpStatusCallbackStatic,
                                                        0xC00u,
                                                        0)
                                            + 1) == 0;
            }
            if ( !v11 )
            {
              *(_QWORD *)(a1 + 8) = v3;
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
              v6 = 0;
              v13 = 0;
              SH<void *,SH_HANDLE>::Reset(a1 + 96);
              *(_QWORD *)(a1 + 96) = EventW;
              v20 = 0;
              SH<void *,SH_HANDLE>::Reset(a1 + 104);
              *(_QWORD *)(a1 + 104) = v8;
              v19 = 0;
              SH<void *,SH_HANDLE>::Reset(a1 + 48);
              *(_QWORD *)(a1 + 48) = v9;
              v14 = 0;
              SH<void *,CWinHttpConnectionT<CEmptyType>::SH_HINTERNET>::Reset(a1 + 112);
              *(_QWORD *)(a1 + 112) = v3;
              *(_DWORD *)(a1 + 208) = v10;
              goto LABEL_17;
            }
          }
          else
          {
            v19 = 0;
          }
        }
        else
        {
          v20 = 0;
        }
      }
      else
      {
        v13 = 0;
      }
    }
  }
  else
  {
    v14 = 0;
  }
  LastError = GetLastError();
  IsPlatformGreaterOrEqualToVista = SErrorConverterT<CEmptyType>::C_LR2HR(LastError);
  v6 = IsPlatformGreaterOrEqualToVista;
LABEL_4:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)IsPlatformGreaterOrEqualToVista);
LABEL_17:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  SH<void *,SH_HANDLE>::Reset(&v19);
  SH<void *,SH_HANDLE>::Reset(&v20);
  SH<void *,SH_HANDLE>::Reset(&v13);
  SH<void *,CWinHttpConnectionT<CEmptyType>::SH_HINTERNET>::Reset(&v14);
  return v6;
}

```

## disassembly

```asm
0x18024b588  mov     [rsp-38h+arg_0], rbx
0x18024b58d  mov     [rsp-38h+arg_8], rdx
0x18024b592  push    rbp
0x18024b593  push    rsi
0x18024b594  push    rdi
0x18024b595  push    r12
0x18024b597  push    r13
0x18024b599  push    r14
0x18024b59b  push    r15
0x18024b59d  mov     rbp, rsp
0x18024b5a0  sub     rsp, 60h
0x18024b5a4  xor     r13d, r13d
0x18024b5a7  mov     [rsp+60h+dwFlags], 10000000h; dwFlags
0x18024b5af  mov     r15, rcx
0x18024b5b2  mov     [rbp+var_28], r13
0x18024b5b6  lea     rcx, pszAgentW; "Activation UX Library"
0x18024b5bd  mov     [rbp+var_30], r13
0x18024b5c1  xor     r9d, r9d; pszProxyBypassW
0x18024b5c4  mov     [rbp+arg_18], r13
0x18024b5c8  xor     r8d, r8d; pszProxyW
0x18024b5cb  mov     [rbp+arg_10], r13
0x18024b5cf  xor     edx, edx; dwAccessType
0x18024b5d1  mov     [rbp+var_18], r13
0x18024b5d5  mov     dword ptr [rbp+arg_8], r13d
0x18024b5d9  mov     [rbp+Buffer], r13
0x18024b5dd  call    cs:__imp_WinHttpOpen
0x18024b5e4  nop     dword ptr [rax+rax+00h]
0x18024b5e9  lea     rcx, [rbp+var_28]
0x18024b5ed  mov     rsi, rax
0x18024b5f0  call    ?Reset@?$SH@PEAXVSH_HINTERNET@?$CWinHttpConnectionT@VCEmptyType@@@@@@QEAAXXZ; SH<void *,CWinHttpConnectionT<CEmptyType>::SH_HINTERNET>::Reset(void)
0x18024b5f5  test    rsi, rsi
0x18024b5f8  jnz     short loc_18024B61F
0x18024b5fa  mov     [rbp+var_28], r13
0x18024b5fe  call    cs:__imp_GetLastError
0x18024b605  nop     dword ptr [rax+rax+00h]
0x18024b60a  mov     ecx, eax
0x18024b60c  call    ?C_LR2HR@?$SErrorConverterT@VCEmptyType@@@@SAJK@Z; SErrorConverterT<CEmptyType>::C_LR2HR(ulong)
0x18024b611  mov     edi, eax
0x18024b613  mov     ecx, eax
0x18024b615  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18024b61a  jmp     loc_18024B789
0x18024b61f  mov     r9d, 8; dwBufferLength
0x18024b625  mov     [rbp+var_28], rsi
0x18024b629  lea     r8, [rbp+Buffer]; lpBuffer
0x18024b62d  mov     [rbp+Buffer], r15
0x18024b631  mov     rcx, rsi; hInternet
0x18024b634  lea     edx, [r9+25h]; dwOption
0x18024b638  call    cs:__imp_WinHttpSetOption
0x18024b63f  nop     dword ptr [rax+rax+00h]
0x18024b644  test    eax, eax
0x18024b646  jz      short loc_18024B5FE
0x18024b648  xor     r9d, r9d; lpName
0x18024b64b  xor     r8d, r8d; bInitialState
0x18024b64e  xor     ecx, ecx; lpEventAttributes
0x18024b650  lea     ebx, [r9+1]
0x18024b654  mov     edx, ebx; bManualReset
0x18024b656  call    cs:__imp_CreateEventW
0x18024b65d  nop     dword ptr [rax+rax+00h]
0x18024b662  lea     rcx, [rbp+var_30]
0x18024b666  mov     r14, rax
0x18024b669  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x18024b66e  test    r14, r14
0x18024b671  jnz     short loc_18024B679
0x18024b673  mov     [rbp+var_30], r13
0x18024b677  jmp     short loc_18024B5FE
0x18024b679  xor     r9d, r9d; lpName
0x18024b67c  mov     [rbp+var_30], r14
0x18024b680  xor     r8d, r8d; bInitialState
0x18024b683  mov     edx, ebx; bManualReset
0x18024b685  xor     ecx, ecx; lpEventAttributes
0x18024b687  call    cs:__imp_CreateEventW
0x18024b68e  nop     dword ptr [rax+rax+00h]
0x18024b693  lea     rcx, [rbp+arg_18]
0x18024b697  mov     rbx, rax
0x18024b69a  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x18024b69f  test    rbx, rbx
0x18024b6a2  jnz     short loc_18024B6AD
0x18024b6a4  mov     [rbp+arg_18], r13
0x18024b6a8  jmp     loc_18024B5FE
0x18024b6ad  xor     r9d, r9d; lpName
0x18024b6b0  mov     [rbp+arg_18], rbx
0x18024b6b4  xor     r8d, r8d; bInitialState
0x18024b6b7  xor     edx, edx; bManualReset
0x18024b6b9  xor     ecx, ecx; lpEventAttributes
0x18024b6bb  call    cs:__imp_CreateEventW
0x18024b6c2  nop     dword ptr [rax+rax+00h]
0x18024b6c7  lea     rcx, [rbp+arg_10]
0x18024b6cb  mov     r12, rax
0x18024b6ce  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x18024b6d3  test    r12, r12
0x18024b6d6  jnz     short loc_18024B6E1
0x18024b6d8  mov     [rbp+arg_10], r13
0x18024b6dc  jmp     loc_18024B5FE
0x18024b6e1  lea     rcx, [rbp+arg_8]
0x18024b6e5  mov     [rbp+arg_10], r12
0x18024b6e9  call    ?IsPlatformGreaterOrEqualToVista@?$CMiscHelpersT@VCEmptyType@@@@SAJPEAH@Z; CMiscHelpersT<CEmptyType>::IsPlatformGreaterOrEqualToVista(int *)
0x18024b6ee  mov     edi, eax
0x18024b6f0  test    eax, eax
0x18024b6f2  js      loc_18024B613
0x18024b6f8  mov     r13d, dword ptr [rbp+arg_8]
0x18024b6fc  mov     rcx, rsi; hInternet
0x18024b6ff  test    r13d, r13d
0x18024b702  jz      loc_18024B7CF
0x18024b708  mov     r9d, 8; dwBufferLength
0x18024b70e  mov     [rbp+var_18], r14
0x18024b712  lea     r8, [rbp+var_18]; lpBuffer
0x18024b716  lea     edx, [r9+5Bh]; dwOption
0x18024b71a  call    cs:__imp_WinHttpSetOption
0x18024b721  nop     dword ptr [rax+rax+00h]
0x18024b726  test    eax, eax
0x18024b728  jz      loc_18024B5FE
0x18024b72e  mov     [r15+8], rsi
0x18024b732  xor     ecx, ecx
0x18024b734  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18024b739  xor     edi, edi
0x18024b73b  lea     rcx, [r15+60h]
0x18024b73f  mov     [rbp+var_30], rdi
0x18024b743  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x18024b748  mov     [r15+60h], r14
0x18024b74c  lea     rcx, [r15+68h]
0x18024b750  xor     r14d, r14d
0x18024b753  mov     [rbp+arg_18], r14
0x18024b757  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x18024b75c  lea     rcx, [r15+30h]
0x18024b760  mov     [r15+68h], rbx
0x18024b764  mov     [rbp+arg_10], r14
0x18024b768  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x18024b76d  lea     rcx, [r15+70h]
0x18024b771  mov     [r15+30h], r12
0x18024b775  mov     [rbp+var_28], r14
0x18024b779  call    ?Reset@?$SH@PEAXVSH_HINTERNET@?$CWinHttpConnectionT@VCEmptyType@@@@@@QEAAXXZ; SH<void *,CWinHttpConnectionT<CEmptyType>::SH_HINTERNET>::Reset(void)
0x18024b77e  mov     [r15+70h], rsi
0x18024b782  mov     [r15+0D0h], r13d
0x18024b789  mov     ecx, edi
0x18024b78b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18024b790  lea     rcx, [rbp+arg_10]
0x18024b794  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x18024b799  lea     rcx, [rbp+arg_18]
0x18024b79d  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x18024b7a2  lea     rcx, [rbp+var_30]
0x18024b7a6  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x18024b7ab  lea     rcx, [rbp+var_28]
0x18024b7af  call    ?Reset@?$SH@PEAXVSH_HINTERNET@?$CWinHttpConnectionT@VCEmptyType@@@@@@QEAAXXZ; SH<void *,CWinHttpConnectionT<CEmptyType>::SH_HINTERNET>::Reset(void)
0x18024b7b4  mov     rbx, [rsp+60h+arg_0]
0x18024b7bc  mov     eax, edi
0x18024b7be  add     rsp, 60h
0x18024b7c2  pop     r15
0x18024b7c4  pop     r14
0x18024b7c6  pop     r13
0x18024b7c8  pop     r12
0x18024b7ca  pop     rdi
0x18024b7cb  pop     rsi
0x18024b7cc  pop     rbp
0x18024b7cd  retn
0x18024b7cf  xor     r9d, r9d; dwReserved
0x18024b7d2  lea     rdx, ?WinHttpStatusCallbackStatic@?$CWinHttpConnectionT@VCEmptyType@@@@CAXPEAX_KK0K@Z; lpfnInternetCallback
0x18024b7d9  mov     r8d, 0C00h; dwNotificationFlags
0x18024b7df  call    cs:__imp_WinHttpSetStatusCallback
0x18024b7e6  nop     dword ptr [rax+rax+00h]
0x18024b7eb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18024b7ef  jmp     loc_18024B728
```
