# ProviderGetProperty(void *,KspProp,uchar *,ulong,ulong *)

- ea: `0x18000f240`
- end: `0x18000f5e7`
- name: `?ProviderGetProperty@@YAJPEAXW4KspProp@@PEAEKPEAK@Z`
- size: `935`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180015ac0`
- `0x180019ed4`
- `0x18001b298`
- `0x18001bb00`
- `0x18002809c`
- `0x180037250`
- `0x180037f94`
- `0x180038efc`
- `0x180051618`
- `0x1800973d0`
- `0x180098970`

## callees

- `0x18000f240`
- `0x18000f858`
- `0x1800113f0`
- `0x1800133c4`
- `0x180014a60`
- `0x1800157c0`
- `0x180069088`
- `0x180090988`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f36d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f36d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f328`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f328`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000f473`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000f490`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000f473`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000f490`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000f28c`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000f28c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ProviderGetProperty(__int64 a1, unsigned int a2, __int64 a3, unsigned int a4, int a5)
{
  const char *v9; // r9
  int LastError; // edi
  __int64 *v11; // rcx
  __int64 *v12; // rax
  __int64 *i; // rdx
  const wchar_t *v14; // rdx
  WINBOOL v15; // ebx
  unsigned int v16; // edi
  int v18; // eax
  int v19; // [rsp+20h] [rbp-88h]
  int v20; // [rsp+20h] [rbp-88h]
  _BYTE v21[36]; // [rsp+40h] [rbp-68h] BYREF
  int v22; // [rsp+64h] [rbp-44h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]
  WINBOOL fPending; // [rsp+B8h] [rbp+10h] BYREF

  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v21, L"ProviderGetProperty", 1);
  fPending = 0;
  if ( InitOnceBeginInitialize(&g_initOnceEnumToString, 0, &fPending, 0) )
  {
    if ( fPending )
    {
      v18 = lambda_78a0d25065c9a3e1bb832c6a29bdb43c_::operator()();
      LastError = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x37F,
          (unsigned int)"wil",
          (const char *)(unsigned int)v18,
          v19);
        InitOnceComplete(&g_initOnceEnumToString, 4u, 0);
        goto LABEL_3;
      }
      InitOnceComplete(&g_initOnceEnumToString, 0, 0);
    }
    LastError = 0;
    goto LABEL_3;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x37A, (unsigned int)"wil", v9);
LABEL_3:
  if ( LastError < 0 )
    goto LABEL_9;
  v11 = *(__int64 **)qword_180109BD0;
  v12 = *(__int64 **)(*(_QWORD *)qword_180109BD0 + 8LL);
  v22 = 0;
  for ( i = v11; !*((_BYTE *)v12 + 25); v12 = (__int64 *)*v12 )
  {
    if ( *((_DWORD *)v12 + 8) >= a2 )
      i = v12;
    else
      v12 += 2;
  }
  if ( *((_BYTE *)i + 25) || i == v11 || a2 < *((_DWORD *)i + 8) )
LABEL_9:
    v14 = L"UNRECOGNIZED";
  else
    v14 = (const wchar_t *)i[5];
  KspDebugProvider::TraceLoggingInfo("Property = %ls", v14);
  if ( (*(_DWORD *)(a1 + 12) & 1) == 0 )
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  v20 = a5;
  v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(*(_QWORD *)a1 + 1112LL))(a1, a2, a3, a4);
  if ( (*(_DWORD *)(a1 + 12) & 1) == 0 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  fPending = v15;
  if ( v15 && v15 != -2146893810 && v15 != -2146893808 && (v15 & 0xFFFF00) != 0x290400 )
  {
    if ( (v15 & 0xFFFF0000) != 0x80280000 )
    {
      if ( v15 == -2144862196 )
      {
LABEL_26:
        v16 = -2144795646;
        goto LABEL_27;
      }
      if ( v15 <= -2144862202 )
      {
        if ( v15 != -2144862202 )
        {
          if ( v15 <= -2146893786 )
          {
            if ( v15 == -2146893786 )
              goto LABEL_26;
            if ( v15 != -2147024809 && v15 != -2147024774 && v15 != -2146893819 )
            {
              if ( v15 == -2146893818 )
              {
                v16 = -2144795636;
                goto LABEL_27;
              }
              if ( v15 == -2146893807 )
                goto LABEL_45;
LABEL_66:
              KspLoggingProvider::PcpInternalErrorRemap<long &>(&fPending);
              v16 = -2144795641;
              goto LABEL_27;
            }
LABEL_53:
            v16 = -2144795645;
            goto LABEL_27;
          }
          if ( v15 == -2146893785 )
            goto LABEL_53;
          if ( v15 == -2146893784 )
          {
            v16 = -2144795642;
            goto LABEL_27;
          }
          if ( v15 != -2146893783 )
          {
            if ( v15 != -2144862207 )
              goto LABEL_66;
LABEL_60:
            v16 = -2144795640;
            goto LABEL_27;
          }
LABEL_61:
          v16 = -2144795643;
          goto LABEL_27;
        }
        goto LABEL_45;
      }
      if ( v15 > -2144860157 )
      {
        if ( v15 != -2144845816 && v15 != -2144845809 && v15 != -2144845808 && v15 != -2144845806 )
          goto LABEL_66;
        goto LABEL_45;
      }
      if ( v15 != -2144860157 )
      {
        if ( v15 != -2144862201 )
        {
          if ( v15 == -2144862193 )
            goto LABEL_61;
          if ( v15 != -2144862190 )
          {
            if ( v15 != -2144862179 )
              goto LABEL_66;
            goto LABEL_60;
          }
        }
LABEL_45:
        v16 = -2144795647;
        goto LABEL_27;
      }
LABEL_35:
      v16 = -2144795639;
      goto LABEL_27;
    }
    if ( (unsigned __int16)v15 == 142 )
      goto LABEL_60;
    if ( (unsigned __int16)v15 == 2337 )
      goto LABEL_35;
  }
  v16 = v15;
  if ( v15 >= 0 )
  {
    KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v21);
    return 0;
  }
LABEL_27:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4F,
    (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcprovider.cpp",
    (const char *)v16,
    v20);
  KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v21);
  return v16;
}

```

## disassembly

```asm
0x18000f240  push    rbx
0x18000f242  push    rbp
0x18000f243  push    rsi
0x18000f244  push    rdi
0x18000f245  push    r14
0x18000f247  push    r15
0x18000f249  sub     rsp, 78h
0x18000f24d  mov     ebp, r9d
0x18000f250  mov     r14, r8
0x18000f253  mov     ebx, edx
0x18000f255  mov     rsi, rcx
0x18000f258  mov     r8b, 1; bool
0x18000f25b  lea     rdx, aProvidergetpro; "ProviderGetProperty"
0x18000f262  lea     rcx, [rsp+0A8h+var_68]; this
0x18000f267  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x18000f26c  nop
0x18000f26d  xor     r15d, r15d
0x18000f270  mov     [rsp+0A8h+fPending], r15d
0x18000f278  xor     r9d, r9d; lpContext
0x18000f27b  lea     r8, [rsp+0A8h+fPending]; fPending
0x18000f283  xor     edx, edx; dwFlags
0x18000f285  lea     rcx, ?g_initOnceEnumToString@@3T_RTL_RUN_ONCE@@A; lpInitOnce
0x18000f28c  call    cs:__imp_InitOnceBeginInitialize
0x18000f293  nop     dword ptr [rax+rax+00h]
0x18000f298  test    eax, eax
0x18000f29a  jnz     loc_18000F433
0x18000f2a0  mov     rcx, [rsp+0A8h]; this
0x18000f2a8  lea     r8, aWil; "wil"
0x18000f2af  mov     edx, 37Ah; void *
0x18000f2b4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f2b9  mov     edi, eax
0x18000f2bb  test    edi, edi
0x18000f2bd  js      short loc_18000F2FC
0x18000f2bf  mov     rax, cs:qword_180109BD0
0x18000f2c6  mov     rcx, [rax]
0x18000f2c9  mov     rax, [rcx+8]
0x18000f2cd  xor     edx, edx
0x18000f2cf  mov     [rsp+0A8h+var_44], edx
0x18000f2d3  mov     rdx, rcx
0x18000f2d6  cmp     byte ptr [rax+19h], 0
0x18000f2da  jnz     short loc_18000F2F2
0x18000f2dc  nop     dword ptr [rax+00h]
0x18000f2e0  cmp     [rax+20h], ebx
0x18000f2e3  jnb     short loc_18000F305
0x18000f2e5  add     rax, 10h
0x18000f2e9  mov     rax, [rax]
0x18000f2ec  cmp     byte ptr [rax+19h], 0
0x18000f2f0  jz      short loc_18000F2E0
0x18000f2f2  cmp     byte ptr [rdx+19h], 0
0x18000f2f6  jz      loc_18000F3A4
0x18000f2fc  lea     rdx, aUnrecognized; "UNRECOGNIZED"
0x18000f303  jmp     short loc_18000F30E
0x18000f305  mov     rdx, rax
0x18000f308  jmp     short loc_18000F2E9
0x18000f30a  mov     rdx, [rdx+28h]
0x18000f30e  lea     rcx, aPropertyLs; "Property = %ls"
0x18000f315  call    ?TraceLoggingInfo@KspDebugProvider@@SAXPEBDZZ; KspDebugProvider::TraceLoggingInfo(char const *,...)
0x18000f31a  mov     eax, [rsi+0Ch]
0x18000f31d  lea     rdi, [rsi+10h]
0x18000f321  test    al, 1
0x18000f323  jnz     short loc_18000F334
0x18000f325  mov     rcx, rdi; lpCriticalSection
0x18000f328  call    cs:__imp_EnterCriticalSection
0x18000f32f  nop     dword ptr [rax+rax+00h]
0x18000f334  mov     rax, [rsi]
0x18000f337  mov     [rsp+0A8h+var_80], r15d
0x18000f33c  mov     rdx, qword ptr [rsp+0A8h+arg_20]
0x18000f344  mov     qword ptr [rsp+0A8h+var_88], rdx; int
0x18000f349  mov     r9d, ebp
0x18000f34c  mov     r8, r14
0x18000f34f  mov     edx, ebx
0x18000f351  mov     rcx, rsi
0x18000f354  mov     rax, [rax+458h]
0x18000f35b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f360  mov     ebx, eax
0x18000f362  mov     edx, [rsi+0Ch]
0x18000f365  test    dl, 1
0x18000f368  jnz     short loc_18000F379
0x18000f36a  mov     rcx, rdi; lpCriticalSection
0x18000f36d  call    cs:__imp_LeaveCriticalSection
0x18000f374  nop     dword ptr [rax+rax+00h]
0x18000f379  mov     [rsp+0A8h+fPending], ebx
0x18000f380  test    ebx, ebx
0x18000f382  jnz     short loc_18000F3BB
0x18000f384  mov     edi, ebx
0x18000f386  test    ebx, ebx
0x18000f388  js      short loc_18000F3FC
0x18000f38a  lea     rcx, [rsp+0A8h+var_68]; this
0x18000f38f  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18000f394  xor     eax, eax
0x18000f396  add     rsp, 78h
0x18000f39a  pop     r15
0x18000f39c  pop     r14
0x18000f39e  pop     rdi
0x18000f39f  pop     rsi
0x18000f3a0  pop     rbp
0x18000f3a1  pop     rbx
0x18000f3a2  retn
0x18000f3a4  cmp     rdx, rcx
0x18000f3a7  jz      loc_18000F2FC
0x18000f3ad  cmp     ebx, [rdx+20h]
0x18000f3b0  jb      loc_18000F2FC
0x18000f3b6  jmp     loc_18000F30A
0x18000f3bb  cmp     ebx, 8009000Eh
0x18000f3c1  jz      short loc_18000F384
0x18000f3c3  cmp     ebx, 80090010h
0x18000f3c9  jz      short loc_18000F384
0x18000f3cb  mov     eax, ebx
0x18000f3cd  and     eax, 0FFFF00h
0x18000f3d2  cmp     eax, 290400h
0x18000f3d7  jz      short loc_18000F384
0x18000f3d9  mov     eax, ebx
0x18000f3db  and     eax, 0FFFF0000h
0x18000f3e0  cmp     eax, 80280000h
0x18000f3e5  jz      loc_18000F4A4
0x18000f3eb  cmp     ebx, 8028000Ch
0x18000f3f1  jnz     loc_18000F4C7
0x18000f3f7  mov     edi, 80290402h
0x18000f3fc  mov     rcx, [rsp+0A8h]; this
0x18000f404  mov     r9d, edi; char *
0x18000f407  lea     r8, aOnecoreBaseNgs_25; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18000f40e  mov     edx, 4Fh ; 'O'; void *
0x18000f413  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f418  nop
0x18000f419  lea     rcx, [rsp+0A8h+var_68]; this
0x18000f41e  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18000f423  mov     eax, edi
0x18000f425  add     rsp, 78h
0x18000f429  pop     r15
0x18000f42b  pop     r14
0x18000f42d  pop     rdi
0x18000f42e  pop     rsi
0x18000f42f  pop     rbp
0x18000f430  pop     rbx
0x18000f431  retn
0x18000f433  cmp     [rsp+0A8h+fPending], r15d
0x18000f43b  jz      short loc_18000F49C
0x18000f43d  call    _lambda_78a0d25065c9a3e1bb832c6a29bdb43c___operator__
0x18000f442  mov     edi, eax
0x18000f444  test    eax, eax
0x18000f446  jns     short loc_18000F484
0x18000f448  mov     rcx, [rsp+0A8h]; this
0x18000f450  mov     r9d, eax; char *
0x18000f453  lea     r8, aWil; "wil"
0x18000f45a  mov     edx, 37Fh; void *
0x18000f45f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f464  xor     r8d, r8d; lpContext
0x18000f467  mov     edx, 4; dwFlags
0x18000f46c  lea     rcx, ?g_initOnceEnumToString@@3T_RTL_RUN_ONCE@@A; lpInitOnce
0x18000f473  call    cs:__imp_InitOnceComplete
0x18000f47a  nop     dword ptr [rax+rax+00h]
0x18000f47f  jmp     loc_18000F2BB
0x18000f484  xor     r8d, r8d; lpContext
0x18000f487  xor     edx, edx; dwFlags
0x18000f489  lea     rcx, ?g_initOnceEnumToString@@3T_RTL_RUN_ONCE@@A; lpInitOnce
0x18000f490  call    cs:__imp_InitOnceComplete
0x18000f497  nop     dword ptr [rax+rax+00h]
0x18000f49c  mov     edi, r15d
0x18000f49f  jmp     loc_18000F2BB
0x18000f4a4  movzx   eax, bx
0x18000f4a7  cmp     eax, 8Eh
0x18000f4ac  jz      loc_18000F58B
0x18000f4b2  cmp     eax, 921h
0x18000f4b7  jnz     loc_18000F384
0x18000f4bd  mov     edi, 80290409h
0x18000f4c2  jmp     loc_18000F3FC
0x18000f4c7  cmp     ebx, 80280006h
0x18000f4cd  jg      loc_18000F55D
0x18000f4d3  jz      short loc_18000F50F
0x18000f4d5  cmp     ebx, 80090026h
0x18000f4db  jg      short loc_18000F523
0x18000f4dd  jz      loc_18000F3F7
0x18000f4e3  cmp     ebx, 80070057h
0x18000f4e9  jz      short loc_18000F553
0x18000f4eb  cmp     ebx, 8007007Ah
0x18000f4f1  jz      short loc_18000F553
0x18000f4f3  cmp     ebx, 80090005h
0x18000f4f9  jz      short loc_18000F553
0x18000f4fb  cmp     ebx, 80090006h
0x18000f501  jz      short loc_18000F519
0x18000f503  cmp     ebx, 80090011h
0x18000f509  jnz     loc_18000F5CF
0x18000f50f  mov     edi, 80290401h
0x18000f514  jmp     loc_18000F3FC
0x18000f519  mov     edi, 8029040Ch
0x18000f51e  jmp     loc_18000F3FC
0x18000f523  cmp     ebx, 80090027h
0x18000f529  jz      short loc_18000F553
0x18000f52b  cmp     ebx, 80090028h
0x18000f531  jz      short loc_18000F549
0x18000f533  cmp     ebx, 80090029h
0x18000f539  jz      short loc_18000F595
0x18000f53b  cmp     ebx, 80280001h
0x18000f541  jnz     loc_18000F5CF
0x18000f547  jmp     short loc_18000F58B
0x18000f549  mov     edi, 80290406h
0x18000f54e  jmp     loc_18000F3FC
0x18000f553  mov     edi, 80290403h
0x18000f558  jmp     loc_18000F3FC
0x18000f55d  cmp     ebx, 80280803h
0x18000f563  jg      short loc_18000F59F
0x18000f565  jz      loc_18000F4BD
0x18000f56b  cmp     ebx, 80280007h
0x18000f571  jz      short loc_18000F50F
0x18000f573  cmp     ebx, 8028000Fh
0x18000f579  jz      short loc_18000F595
0x18000f57b  cmp     ebx, 80280012h
0x18000f581  jz      short loc_18000F50F
0x18000f583  cmp     ebx, 8028001Dh
0x18000f589  jnz     short loc_18000F5CF
0x18000f58b  mov     edi, 80290408h
0x18000f590  jmp     loc_18000F3FC
0x18000f595  mov     edi, 80290405h
0x18000f59a  jmp     loc_18000F3FC
0x18000f59f  cmp     ebx, 80284008h
0x18000f5a5  jz      loc_18000F50F
0x18000f5ab  cmp     ebx, 8028400Fh
0x18000f5b1  jz      loc_18000F50F
0x18000f5b7  cmp     ebx, 80284010h
0x18000f5bd  jz      loc_18000F50F
0x18000f5c3  cmp     ebx, 80284012h
0x18000f5c9  jz      loc_18000F50F
0x18000f5cf  lea     rcx, [rsp+0A8h+fPending]
0x18000f5d7  call    ??$PcpInternalErrorRemap@AEAJ@KspLoggingProvider@@SAXAEAJ@Z; KspLoggingProvider::PcpInternalErrorRemap<long &>(long &)
0x18000f5dc  mov     edi, 80290407h
0x18000f5e1  jmp     loc_18000F3FC
```
