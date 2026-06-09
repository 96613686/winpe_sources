# OneSettings::GetValue(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x14001747c`
- end: `0x140017798`
- name: `?GetValue@OneSettings@@QEAAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `796`
- prototype: `__int64 __fastcall(__int64, __int64, char *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140013aec`

## callees

- `0x140002600`
- `0x140007870`
- `0x140007dc8`
- `0x1400138c8`
- `0x140013a2c`
- `0x1400146e4`
- `0x140015794`
- `0x14001747c`
- `0x14001bba8`
- `0x14001d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x14001756e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001765a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400176f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001773d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001765a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400176f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001773d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140017668`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140017702`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001774b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140017668`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140017702`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001774b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14001767c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14001767c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400175eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400175eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001759c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001763c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400176d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001759c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001763c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400176d6`

## pseudocode

```c
__int64 __fastcall OneSettings::GetValue(__int64 a1, __int64 a2, char *a3)
{
  unsigned __int64 *v5; // r12
  char *v6; // rcx
  unsigned int v7; // edi
  __int64 v8; // rdx
  _QWORD *v9; // rax
  PCWSTR *v10; // rsi
  PCWSTR *v11; // rdx
  PCWSTR *v12; // r15
  PCWSTR *v13; // rbx
  __int64 **v14; // rax
  __int64 *v15; // rsi
  __int64 v16; // r14
  unsigned int v17; // r8d
  const WCHAR *v18; // rcx
  unsigned __int64 v19; // rbx
  unsigned __int64 v20; // rdx
  HRESULT v21; // eax
  int v22; // edx
  unsigned int v23; // r8d
  int v24; // eax
  unsigned int v25; // esi
  void *v26; // rbx
  HANDLE v27; // rax
  PCWSTR StringRawBuffer; // rax
  __int64 v30; // r8
  size_t v31; // rbx
  void *v32; // rbx
  HANDLE v33; // rax
  void *v34; // rbx
  HANDLE ProcessHeap; // rax
  HSTRING string[2]; // [rsp+20h] [rbp-89h] BYREF
  _BYTE v37[16]; // [rsp+30h] [rbp-79h] BYREF
  LPVOID lpMem; // [rsp+40h] [rbp-69h]
  char v39; // [rsp+48h] [rbp-61h]
  _BYTE v40[48]; // [rsp+50h] [rbp-59h] BYREF
  PCWSTR sourceString[2]; // [rsp+80h] [rbp-29h] BYREF
  __int128 v42; // [rsp+90h] [rbp-19h]
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-9h] BYREF
  HSTRING v44; // [rsp+B8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)(a1 + 216) + 112LL))(a1 + 216, v37);
  v5 = (unsigned __int64 *)(a3 + 16);
  *((_QWORD *)a3 + 2) = 0;
  if ( *((_QWORD *)a3 + 3) <= 7u )
    v6 = a3;
  else
    v6 = *(char **)a3;
  *(_WORD *)v6 = 0;
  if ( !*(_DWORD *)(a1 + 704) )
  {
    v7 = -2147019873;
    v8 = 325;
LABEL_38:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\onesettings\\src\\onesettings.cpp",
      (const char *)v7,
      (int)string[0]);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v40);
    if ( v39 )
    {
      v34 = lpMem;
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v34);
    }
    return v7;
  }
  v9 = *(_QWORD **)(a1 + 208);
  if ( !v9 || !*v9 )
  {
    v7 = -2147024664;
    v8 = 326;
    goto LABEL_38;
  }
  string[0] = 0;
  *(_OWORD *)sourceString = 0;
  v42 = 0;
  std::wstring::_Construct<1,unsigned short const *>(sourceString, L"MetadataUrl", 0xBu);
  if ( *((_QWORD *)&v42 + 1) > 7u )
  {
    v10 = (PCWSTR *)sourceString[0];
    v11 = (PCWSTR *)sourceString[0];
  }
  else
  {
    v10 = sourceString;
    v11 = sourceString;
  }
  v12 = (PCWSTR *)((char *)v11 + 2 * v42);
  v13 = sourceString;
  if ( *((_QWORD *)&v42 + 1) > 7u )
    v13 = (PCWSTR *)sourceString[0];
  while ( v13 != v12 )
  {
    *(_WORD *)v10 = ((__int64 (__fastcall *)(_QWORD))towupper)(*(unsigned __int16 *)v13);
    v10 = (PCWSTR *)((char *)v10 + 2);
    v13 = (PCWSTR *)((char *)v13 + 2);
  }
  v14 = *(__int64 ***)(a1 + 208);
  v15 = *v14;
  v16 = **v14;
  WindowsDeleteString(string[0]);
  string[0] = 0;
  v18 = (const WCHAR *)sourceString;
  if ( *((_QWORD *)&v42 + 1) > 7u )
    v18 = sourceString[0];
  v44 = 0;
  v19 = -1;
  v20 = -1;
  do
    ++v20;
  while ( v18[v20] );
  if ( v20 > 0xFFFFFFFF )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v20, v17);
    __debugbreak();
  }
  if ( (int)v20 + 1 < (unsigned int)v20 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v20, v17);
    __debugbreak();
  }
  v21 = WindowsCreateStringReference(v18, v20, &hstringHeader, &v44);
  if ( v21 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v21, v22, v23);
    JUMPOUT(0x140017797LL);
  }
  v24 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, HSTRING *))(v16 + 80))(v15, v44, string);
  v25 = v24;
  if ( v24 >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string[0], 0);
    do
      ++v19;
    while ( StringRawBuffer[v19] );
    if ( v19 > *((_QWORD *)a3 + 3) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char **)a3,
        v19,
        v30,
        StringRawBuffer);
    }
    else
    {
      if ( *((_QWORD *)a3 + 3) > 7u )
        a3 = *(char **)a3;
      *v5 = v19;
      v31 = 2 * v19;
      memmove_0(a3, StringRawBuffer, v31);
      *(_WORD *)&a3[v31] = 0;
    }
    std::wstring::~wstring((char **)sourceString);
    WindowsDeleteString(string[0]);
    string[0] = 0;
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v40);
    if ( v39 )
    {
      v32 = lpMem;
      v33 = GetProcessHeap();
      HeapFree(v33, 0, v32);
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14C,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\onesettings\\src\\onesettings.cpp",
      (const char *)(unsigned int)v24,
      (int)string[0]);
    std::wstring::~wstring((char **)sourceString);
    WindowsDeleteString(string[0]);
    string[0] = 0;
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v40);
    if ( v39 )
    {
      v26 = lpMem;
      v27 = GetProcessHeap();
      HeapFree(v27, 0, v26);
    }
    return v25;
  }
}

```

## disassembly

```asm
0x14001747c  mov     [rsp-8+arg_8], rbx
0x140017481  push    rbp
0x140017482  push    rsi
0x140017483  push    rdi
0x140017484  push    r12
0x140017486  push    r13
0x140017488  push    r14
0x14001748a  push    r15
0x14001748c  lea     rbp, [rsp-27h]
0x140017491  sub     rsp, 0D0h
0x140017498  mov     rax, cs:__security_cookie
0x14001749f  xor     rax, rsp
0x1400174a2  mov     [rbp+57h+var_40], rax
0x1400174a6  mov     rdi, r8
0x1400174a9  mov     r14, rcx
0x1400174ac  add     rcx, 0D8h
0x1400174b3  mov     rax, [rcx]
0x1400174b6  lea     rdx, [rbp+57h+var_D0]
0x1400174ba  mov     rax, [rax+70h]
0x1400174be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400174c3  nop
0x1400174c4  lea     r12, [rdi+10h]
0x1400174c8  xor     r13d, r13d
0x1400174cb  mov     [r12], r13
0x1400174cf  cmp     qword ptr [rdi+18h], 7
0x1400174d4  jbe     short loc_1400174DB
0x1400174d6  mov     rcx, [rdi]
0x1400174d9  jmp     short loc_1400174DE
0x1400174db  mov     rcx, rdi
0x1400174de  mov     [rcx], r13w
0x1400174e2  cmp     [r14+2C0h], r13d
0x1400174e9  jnz     short loc_1400174FA
0x1400174eb  mov     edi, 8007139Fh
0x1400174f0  mov     edx, 145h
0x1400174f5  jmp     loc_140017716
0x1400174fa  mov     rax, [r14+0D0h]
0x140017501  test    rax, rax
0x140017504  jz      loc_14001770C
0x14001750a  cmp     [rax], r13
0x14001750d  jz      loc_14001770C
0x140017513  mov     [rsp+100h+string], r13
0x140017518  xorps   xmm0, xmm0
0x14001751b  movups  xmmword ptr [rbp+57h+sourceString], xmm0
0x14001751f  xorps   xmm1, xmm1
0x140017522  movdqu  [rbp+57h+var_70], xmm1
0x140017527  mov     r8d, 0Bh
0x14001752d  lea     rdx, aMetadataurl; "MetadataUrl"
0x140017534  lea     rcx, [rbp+57h+sourceString]
0x140017538  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14001753d  nop
0x14001753e  mov     rcx, [rbp+57h+sourceString]
0x140017542  cmp     qword ptr [rbp+57h+var_70+8], 7
0x140017547  ja      short loc_140017553
0x140017549  lea     rsi, [rbp+57h+sourceString]
0x14001754d  lea     rdx, [rbp+57h+sourceString]
0x140017551  jmp     short loc_140017559
0x140017553  mov     rsi, rcx
0x140017556  mov     rdx, rcx
0x140017559  mov     rax, qword ptr [rbp+57h+var_70]
0x14001755d  lea     r15, [rdx+rax*2]
0x140017561  lea     rbx, [rbp+57h+sourceString]
0x140017565  cmova   rbx, rcx
0x140017569  jmp     short loc_140017585
0x14001756b  movzx   ecx, word ptr [rbx]
0x14001756e  mov     rax, cs:__imp_towupper
0x140017575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001757a  mov     [rsi], ax
0x14001757d  lea     rsi, [rsi+2]
0x140017581  add     rbx, 2
0x140017585  cmp     rbx, r15
0x140017588  jnz     short loc_14001756B
0x14001758a  mov     rax, [r14+0D0h]
0x140017591  mov     rsi, [rax]
0x140017594  mov     r14, [rsi]
0x140017597  mov     rcx, [rsp+100h+string]; string
0x14001759c  call    cs:__imp_WindowsDeleteString
0x1400175a2  mov     [rsp+100h+string], r13; int
0x1400175a7  lea     rcx, [rbp+57h+sourceString]
0x1400175ab  cmp     qword ptr [rbp+57h+var_70+8], 7
0x1400175b0  cmova   rcx, [rbp+57h+sourceString]; sourceString
0x1400175b5  mov     [rbp+57h+var_48], r13
0x1400175b9  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400175bd  mov     rdx, rbx
0x1400175c0  inc     rdx; int
0x1400175c3  cmp     [rcx+rdx*2], r13w
0x1400175c8  jnz     short loc_1400175C0
0x1400175ca  mov     eax, 0FFFFFFFFh
0x1400175cf  cmp     rdx, rax
0x1400175d2  ja      loc_14001777A
0x1400175d8  lea     eax, [rdx+1]
0x1400175db  cmp     eax, edx
0x1400175dd  jb      loc_140017785
0x1400175e3  lea     r9, [rbp+57h+var_48]; string
0x1400175e7  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1400175eb  call    cs:__imp_WindowsCreateStringReference
0x1400175f1  test    eax, eax
0x1400175f3  js      loc_140017790
0x1400175f9  lea     r8, [rsp+100h+string]
0x1400175fe  mov     rdx, [rbp+57h+var_48]
0x140017602  mov     rcx, rsi
0x140017605  mov     rax, [r14+50h]
0x140017609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001760e  mov     esi, eax
0x140017610  test    eax, eax
0x140017612  jns     short loc_140017675
0x140017614  mov     rcx, [rbp+5Fh]; this
0x140017618  mov     r9d, eax; char *
0x14001761b  lea     r8, aOnecoreuapEndu_111; "onecoreuap\\enduser\\nui\\onecore\\ones"...
0x140017622  mov     edx, 14Ch; void *
0x140017627  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001762c  nop
0x14001762d  lea     rcx, [rbp+57h+sourceString]
0x140017631  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140017636  nop
0x140017637  mov     rcx, [rsp+100h+string]; string
0x14001763c  call    cs:__imp_WindowsDeleteString
0x140017642  mov     [rsp+100h+string], r13
0x140017647  lea     rcx, [rbp+57h+var_B0]; this
0x14001764b  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x140017650  cmp     [rbp+57h+var_B8], r13b
0x140017654  jz      short loc_14001766E
0x140017656  mov     rbx, [rbp+57h+lpMem]
0x14001765a  call    cs:__imp_GetProcessHeap
0x140017660  mov     r8, rbx; lpMem
0x140017663  xor     edx, edx; dwFlags
0x140017665  mov     rcx, rax; hHeap
0x140017668  call    cs:__imp_HeapFree
0x14001766e  mov     eax, esi
0x140017670  jmp     loc_140017753
0x140017675  xor     edx, edx; length
0x140017677  mov     rcx, [rsp+100h+string]; string
0x14001767c  call    cs:__imp_WindowsGetStringRawBuffer
0x140017682  inc     rbx
0x140017685  cmp     [rax+rbx*2], r13w
0x14001768a  jnz     short loc_140017682
0x14001768c  cmp     rbx, [rdi+18h]
0x140017690  ja      short loc_1400176B8
0x140017692  cmp     qword ptr [rdi+18h], 7
0x140017697  jbe     short loc_14001769C
0x140017699  mov     rdi, [rdi]
0x14001769c  mov     [r12], rbx
0x1400176a0  add     rbx, rbx
0x1400176a3  mov     r8, rbx; Size
0x1400176a6  mov     rdx, rax; Src
0x1400176a9  mov     rcx, rdi; void *
0x1400176ac  call    memmove_0
0x1400176b1  mov     [rbx+rdi], r13w
0x1400176b6  jmp     short loc_1400176C7
0x1400176b8  mov     r9, rax
0x1400176bb  mov     rdx, rbx
0x1400176be  mov     rcx, rdi
0x1400176c1  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1400176c6  nop
0x1400176c7  lea     rcx, [rbp+57h+sourceString]
0x1400176cb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400176d0  nop
0x1400176d1  mov     rcx, [rsp+100h+string]; string
0x1400176d6  call    cs:__imp_WindowsDeleteString
0x1400176dc  mov     [rsp+100h+string], r13
0x1400176e1  lea     rcx, [rbp+57h+var_B0]; this
0x1400176e5  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1400176ea  cmp     [rbp+57h+var_B8], r13b
0x1400176ee  jz      short loc_140017708
0x1400176f0  mov     rbx, [rbp+57h+lpMem]
0x1400176f4  call    cs:__imp_GetProcessHeap
0x1400176fa  mov     r8, rbx; lpMem
0x1400176fd  xor     edx, edx; dwFlags
0x1400176ff  mov     rcx, rax; hHeap
0x140017702  call    cs:__imp_HeapFree
0x140017708  xor     eax, eax
0x14001770a  jmp     short loc_140017753
0x14001770c  mov     edi, 800700E8h
0x140017711  mov     edx, 146h; void *
0x140017716  mov     r9d, edi; char *
0x140017719  lea     r8, aOnecoreuapEndu_111; "onecoreuap\\enduser\\nui\\onecore\\ones"...
0x140017720  mov     rcx, [rbp+5Fh]; this
0x140017724  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140017729  nop
0x14001772a  lea     rcx, [rbp+57h+var_B0]; this
0x14001772e  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x140017733  cmp     [rbp+57h+var_B8], r13b
0x140017737  jz      short loc_140017751
0x140017739  mov     rbx, [rbp+57h+lpMem]
0x14001773d  call    cs:__imp_GetProcessHeap
0x140017743  mov     r8, rbx; lpMem
0x140017746  xor     edx, edx; dwFlags
0x140017748  mov     rcx, rax; hHeap
0x14001774b  call    cs:__imp_HeapFree
0x140017751  mov     eax, edi
0x140017753  mov     rcx, [rbp+57h+var_40]
0x140017757  xor     rcx, rsp; StackCookie
0x14001775a  call    __security_check_cookie
0x14001775f  mov     rbx, [rsp+100h+arg_8]
0x140017767  add     rsp, 0D0h
0x14001776e  pop     r15
0x140017770  pop     r14
0x140017772  pop     r13
0x140017774  pop     r12
0x140017776  pop     rdi
0x140017777  pop     rsi
0x140017778  pop     rbp
0x140017779  retn
0x14001777a  mov     ecx, 80070216h; this
0x14001777f  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x140017784  int     3; Trap to Debugger
0x140017785  mov     ecx, 80070216h; this
0x14001778a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x14001778f  int     3; Trap to Debugger
0x140017790  mov     ecx, eax; this
0x140017792  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
