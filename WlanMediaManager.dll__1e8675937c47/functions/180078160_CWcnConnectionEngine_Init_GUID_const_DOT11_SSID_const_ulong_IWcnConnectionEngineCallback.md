# CWcnConnectionEngine::Init(_GUID const *,_DOT11_SSID const *,ulong,IWcnConnectionEngineCallback *)

- ea: `0x180078160`
- end: `0x180078472`
- name: `?Init@CWcnConnectionEngine@@QEAAJPEBU_GUID@@PEBU_DOT11_SSID@@KPEAVIWcnConnectionEngineCallback@@@Z`
- size: `786`
- prototype: `__int64 __usercall@<rax>(CWcnConnectionEngine *__hidden this@<rcx>, const struct _GUID *@<rdx>, const struct _DOT11_SSID *@<r8>, unsigned int@<r9d>, struct IWcnConnectionEngineCallback *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x18007785c`

## callees

- `0x180003ed0`
- `0x180006249`
- `0x180076f84`
- `0x180076fe0`
- `0x180078160`
- `0x180079424`
- `0x180088304`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800782bf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007832f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800782bf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007832f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800782ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800782d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800782e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007833e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078348`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078352`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800783c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800783cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800783d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800782ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800782d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800782e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007833e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078348`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078352`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800783c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800783cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800783d6`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800783b3`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800783b3`

## string_xrefs

- `0x1800781e4`: `pSsid`

## pseudocode

```c
__int64 __fastcall CWcnConnectionEngine::Init(
        CWcnConnectionEngine *this,
        const struct _GUID *a2,
        const struct _DOT11_SSID *a3,
        int a4,
        struct IWcnConnectionEngineCallback *a5)
{
  PVOID *v9; // r10
  const char *Indent; // rax
  __int64 v11; // r10
  __int64 v12; // rdx
  const char *v13; // r9
  PVOID *v15; // rsi
  size_t uSSIDLength; // r8
  unsigned int v17; // eax
  int v18; // edx
  int v19; // r8d
  HANDLE EventW; // rax
  unsigned int v21; // ebx
  unsigned int v22; // ebx
  PVOID *v23; // r10
  unsigned int v24; // eax
  __int64 v25; // r10
  int v26; // edx
  HANDLE v27; // rax
  unsigned int v28; // ebx
  HANDLE Thread; // rax
  unsigned int LastError; // ebx
  unsigned int v31; // eax
  __int64 v32; // r10
  _OWORD v33[2]; // [rsp+40h] [rbp-68h] BYREF
  char v34; // [rsp+60h] [rbp-48h]

  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v11 + 16), 10, WPP_2ea1fd34665a3647954ba5ee5f2f60a4_Traceguids, Indent);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a3 )
  {
    if ( v9 == &WPP_GLOBAL_Control || *((_BYTE *)v9 + 25) < 2u )
      return 2147500035LL;
    v12 = 11;
    v13 = "pSsid";
LABEL_12:
    WPP_SF_s(v9[2], v12, WPP_2ea1fd34665a3647954ba5ee5f2f60a4_Traceguids, v13);
    return 2147500035LL;
  }
  if ( !a5 )
  {
    if ( v9 == &WPP_GLOBAL_Control || *((_BYTE *)v9 + 25) < 2u )
      return 2147500035LL;
    v12 = 12;
    v13 = "pCallback";
    goto LABEL_12;
  }
  *((_DWORD *)this + 10) = a4;
  *(struct _GUID *)((char *)this + 44) = *a2;
  *(_OWORD *)((char *)this + 60) = *(_OWORD *)&a3->uSSIDLength;
  *(_OWORD *)((char *)this + 76) = *(_OWORD *)&a3->ucSSID[12];
  *((_DWORD *)this + 23) = *(_DWORD *)&a3->ucSSID[28];
  *((_QWORD *)this + 20) = a5;
  v15 = (PVOID *)WPP_GLOBAL_Control;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) != 0 )
  {
    uSSIDLength = a3->uSSIDLength;
    memset(v33, 0, sizeof(v33));
    v34 = 0;
    memcpy_0(v33, a3->ucSSID, uSSIDLength);
    if ( v15 != &WPP_GLOBAL_Control && *((_BYTE *)v15 + 25) >= 5u )
    {
      v17 = (unsigned int)GetIndent(0);
      WPP_SF_s_guid_sD((unsigned int)v15[2], v18, v19, v17, (__int64)a2, (__int64)v33, a4);
    }
  }
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 4) = EventW;
  if ( EventW )
  {
    v27 = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 3) = v27;
    if ( v27 )
    {
      v22 = 0;
      *((_DWORD *)this + 42) = 2;
      Thread = CreateThread(0, 0, CWcnConnectionEngine::WorkerThreadThunk, this, 0, 0);
      *((_QWORD *)this + 2) = Thread;
      if ( Thread )
      {
LABEL_40:
        v23 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_41;
      }
      if ( (int)GetLastError() > 0 )
        LastError = (unsigned __int16)GetLastError() | 0x80070000;
      else
        LastError = GetLastError();
      v22 = LastError | 0x80000000;
      v23 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v22;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_41;
      v24 = (unsigned int)GetIndent(0);
      v26 = 16;
    }
    else
    {
      if ( (int)GetLastError() > 0 )
        v28 = (unsigned __int16)GetLastError() | 0x80070000;
      else
        v28 = GetLastError();
      v22 = v28 | 0x80000000;
      v23 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v22;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_41;
      v24 = (unsigned int)GetIndent(0);
      v26 = 15;
    }
LABEL_39:
    WPP_SF_sd(*(_QWORD *)(v25 + 16), v26, (unsigned int)WPP_2ea1fd34665a3647954ba5ee5f2f60a4_Traceguids, v24, v22);
    goto LABEL_40;
  }
  if ( (int)GetLastError() > 0 )
    v21 = (unsigned __int16)GetLastError() | 0x80070000;
  else
    v21 = GetLastError();
  v22 = v21 | 0x80000000;
  v23 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v22;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v24 = (unsigned int)GetIndent(0);
    v26 = 14;
    goto LABEL_39;
  }
LABEL_41:
  if ( v23 != &WPP_GLOBAL_Control && ((v22 & 0x80000000) != 0 || *((_BYTE *)v23 + 25) >= 6u) )
  {
    v31 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v32 + 16), 17, (unsigned int)WPP_2ea1fd34665a3647954ba5ee5f2f60a4_Traceguids, v31, v22);
  }
  return v22;
}

```

## disassembly

```asm
0x180078160  push    rbx
0x180078162  push    rbp
0x180078163  push    rsi
0x180078164  push    rdi
0x180078165  push    r12
0x180078167  push    r14
0x180078169  push    r15
0x18007816b  sub     rsp, 70h
0x18007816f  mov     rax, cs:__security_cookie
0x180078176  xor     rax, rsp
0x180078179  mov     [rsp+0A8h+var_40], rax
0x18007817e  mov     ebp, r9d
0x180078181  mov     rbx, r8
0x180078184  mov     r14, rdx
0x180078187  mov     rdi, rcx
0x18007818a  mov     r10, cs:WPP_GLOBAL_Control
0x180078191  lea     r15, WPP_GLOBAL_Control
0x180078198  lea     r12, WPP_2ea1fd34665a3647954ba5ee5f2f60a4_Traceguids
0x18007819f  cmp     r10, r15
0x1800781a2  jz      short loc_1800781D0
0x1800781a4  cmp     byte ptr [r10+19h], 6
0x1800781a9  jb      short loc_1800781D0
0x1800781ab  mov     ecx, 1; int
0x1800781b0  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800781b5  mov     rcx, [r10+10h]
0x1800781b9  mov     edx, 0Ah
0x1800781be  mov     r9, rax
0x1800781c1  mov     r8, r12
0x1800781c4  call    WPP_SF_s
0x1800781c9  mov     r10, cs:WPP_GLOBAL_Control
0x1800781d0  test    rbx, rbx
0x1800781d3  jnz     short loc_1800781ED
0x1800781d5  cmp     r10, r15
0x1800781d8  jz      short loc_18007821C
0x1800781da  cmp     byte ptr [r10+19h], 2
0x1800781df  jb      short loc_18007821C
0x1800781e1  lea     edx, [rbx+0Bh]
0x1800781e4  lea     r9, aPssid; "pSsid"
0x1800781eb  jmp     short loc_180078210
0x1800781ed  mov     rcx, [rsp+0A8h+arg_20]
0x1800781f5  test    rcx, rcx
0x1800781f8  jnz     short loc_180078226
0x1800781fa  cmp     r10, r15
0x1800781fd  jz      short loc_18007821C
0x1800781ff  cmp     byte ptr [r10+19h], 2
0x180078204  jb      short loc_18007821C
0x180078206  lea     edx, [rcx+0Ch]
0x180078209  lea     r9, aPcallback; "pCallback"
0x180078210  mov     rcx, [r10+10h]
0x180078214  mov     r8, r12
0x180078217  call    WPP_SF_s
0x18007821c  mov     eax, 80004003h
0x180078221  jmp     loc_180078456
0x180078226  mov     [rdi+28h], ebp
0x180078229  movups  xmm0, xmmword ptr [r14]
0x18007822d  movdqu  xmmword ptr [rdi+2Ch], xmm0
0x180078232  movups  xmm0, xmmword ptr [rbx]
0x180078235  movups  xmmword ptr [rdi+3Ch], xmm0
0x180078239  movups  xmm1, xmmword ptr [rbx+10h]
0x18007823d  movups  xmmword ptr [rdi+4Ch], xmm1
0x180078241  mov     eax, [rbx+20h]
0x180078244  mov     [rdi+5Ch], eax
0x180078247  mov     [rdi+0A0h], rcx
0x18007824e  mov     rsi, cs:WPP_GLOBAL_Control
0x180078255  test    dword ptr [rsi+1Ch], 20000h
0x18007825c  jz      short loc_1800782B3
0x18007825e  mov     r8d, [rbx]; Size
0x180078261  lea     rdx, [rbx+4]; Src
0x180078265  xorps   xmm0, xmm0
0x180078268  lea     rcx, [rsp+0A8h+var_68]; void *
0x18007826d  xor     eax, eax
0x18007826f  movups  [rsp+0A8h+var_68], xmm0
0x180078274  mov     [rsp+0A8h+var_48], al
0x180078278  movups  [rsp+0A8h+var_58], xmm0
0x18007827d  call    memcpy_0
0x180078282  cmp     rsi, r15
0x180078285  jz      short loc_1800782B3
0x180078287  cmp     byte ptr [rsi+19h], 5
0x18007828b  jb      short loc_1800782B3
0x18007828d  xor     ecx, ecx; int
0x18007828f  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180078294  lea     rcx, [rsp+0A8h+var_68]
0x180078299  mov     [rsp+0A8h+var_78], ebp
0x18007829d  mov     [rsp+0A8h+lpThreadId], rcx
0x1800782a2  mov     r9, rax
0x1800782a5  mov     rcx, [rsi+10h]
0x1800782a9  mov     qword ptr [rsp+0A8h+dwCreationFlags], r14
0x1800782ae  call    WPP_SF_s_guid_sD
0x1800782b3  xor     r9d, r9d; lpName
0x1800782b6  xor     r8d, r8d; bInitialState
0x1800782b9  xor     ecx, ecx; lpEventAttributes
0x1800782bb  lea     edx, [r9+1]; bManualReset
0x1800782bf  call    cs:__imp_CreateEventW
0x1800782c5  mov     [rdi+20h], rax
0x1800782c9  test    rax, rax
0x1800782cc  jnz     short loc_180078323
0x1800782ce  call    cs:__imp_GetLastError
0x1800782d4  test    eax, eax
0x1800782d6  jg      short loc_1800782E2
0x1800782d8  call    cs:__imp_GetLastError
0x1800782de  mov     ebx, eax
0x1800782e0  jmp     short loc_1800782F1
0x1800782e2  call    cs:__imp_GetLastError
0x1800782e8  movzx   ebx, ax
0x1800782eb  or      ebx, 80070000h
0x1800782f1  or      ebx, 80000000h
0x1800782f7  mov     r10, cs:WPP_GLOBAL_Control
0x1800782fe  cmp     r10, r15
0x180078301  jz      loc_180078454
0x180078307  cmp     byte ptr [r10+19h], 2
0x18007830c  jb      loc_180078424
0x180078312  xor     ecx, ecx; int
0x180078314  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180078319  mov     edx, 0Eh
0x18007831e  jmp     loc_18007840A
0x180078323  xor     r9d, r9d; lpName
0x180078326  xor     r8d, r8d; bInitialState
0x180078329  xor     ecx, ecx; lpEventAttributes
0x18007832b  lea     edx, [r9+1]; bManualReset
0x18007832f  call    cs:__imp_CreateEventW
0x180078335  mov     [rdi+18h], rax
0x180078339  test    rax, rax
0x18007833c  jnz     short loc_180078390
0x18007833e  call    cs:__imp_GetLastError
0x180078344  test    eax, eax
0x180078346  jg      short loc_180078352
0x180078348  call    cs:__imp_GetLastError
0x18007834e  mov     ebx, eax
0x180078350  jmp     short loc_180078361
0x180078352  call    cs:__imp_GetLastError
0x180078358  movzx   ebx, ax
0x18007835b  or      ebx, 80070000h
0x180078361  or      ebx, 80000000h
0x180078367  mov     r10, cs:WPP_GLOBAL_Control
0x18007836e  cmp     r10, r15
0x180078371  jz      loc_180078454
0x180078377  cmp     byte ptr [r10+19h], 2
0x18007837c  jb      loc_180078424
0x180078382  xor     ecx, ecx; int
0x180078384  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180078389  mov     edx, 0Fh
0x18007838e  jmp     short loc_18007840A
0x180078390  xor     ebx, ebx
0x180078392  mov     dword ptr [rdi+0A8h], 2
0x18007839c  mov     [rsp+0A8h+lpThreadId], rbx; lpThreadId
0x1800783a1  lea     r8, ?WorkerThreadThunk@CWcnConnectionEngine@@CAKPEAX@Z; lpStartAddress
0x1800783a8  mov     r9, rdi; lpParameter
0x1800783ab  mov     [rsp+0A8h+dwCreationFlags], ebx; dwCreationFlags
0x1800783af  xor     edx, edx; dwStackSize
0x1800783b1  xor     ecx, ecx; lpThreadAttributes
0x1800783b3  call    cs:__imp_CreateThread
0x1800783b9  mov     [rdi+10h], rax
0x1800783bd  test    rax, rax
0x1800783c0  jnz     short loc_18007841D
0x1800783c2  call    cs:__imp_GetLastError
0x1800783c8  test    eax, eax
0x1800783ca  jg      short loc_1800783D6
0x1800783cc  call    cs:__imp_GetLastError
0x1800783d2  mov     ebx, eax
0x1800783d4  jmp     short loc_1800783E5
0x1800783d6  call    cs:__imp_GetLastError
0x1800783dc  movzx   ebx, ax
0x1800783df  or      ebx, 80070000h
0x1800783e5  or      ebx, 80000000h
0x1800783eb  mov     r10, cs:WPP_GLOBAL_Control
0x1800783f2  cmp     r10, r15
0x1800783f5  jz      short loc_180078454
0x1800783f7  cmp     byte ptr [r10+19h], 2
0x1800783fc  jb      short loc_180078424
0x1800783fe  xor     ecx, ecx; int
0x180078400  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180078405  mov     edx, 10h
0x18007840a  mov     rcx, [r10+10h]
0x18007840e  mov     r9, rax
0x180078411  mov     r8, r12
0x180078414  mov     [rsp+0A8h+dwCreationFlags], ebx
0x180078418  call    WPP_SF_sd
0x18007841d  mov     r10, cs:WPP_GLOBAL_Control
0x180078424  cmp     r10, r15
0x180078427  jz      short loc_180078454
0x180078429  test    ebx, ebx
0x18007842b  js      short loc_180078434
0x18007842d  cmp     byte ptr [r10+19h], 6
0x180078432  jb      short loc_180078454
0x180078434  or      ecx, 0FFFFFFFFh; int
0x180078437  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18007843c  mov     rcx, [r10+10h]
0x180078440  mov     edx, 11h
0x180078445  mov     r9, rax
0x180078448  mov     [rsp+0A8h+dwCreationFlags], ebx
0x18007844c  mov     r8, r12
0x18007844f  call    WPP_SF_sd
0x180078454  mov     eax, ebx
0x180078456  mov     rcx, [rsp+0A8h+var_40]
0x18007845b  xor     rcx, rsp; StackCookie
0x18007845e  call    __security_check_cookie
0x180078463  add     rsp, 70h
0x180078467  pop     r15
0x180078469  pop     r14
0x18007846b  pop     r12
0x18007846d  pop     rdi
0x18007846e  pop     rsi
0x18007846f  pop     rbp
0x180078470  pop     rbx
0x180078471  retn
```
