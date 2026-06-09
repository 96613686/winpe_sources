# ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z

- ea: `0x140071960`
- end: `0x140071c04`
- name: `?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z`
- size: `676`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x140071554`

## callees

- `0x14003f924`
- `0x140040308`
- `0x140040364`
- `0x1400407f8`
- `0x140040bbc`
- `0x14006ffac`
- `0x1400718f8`
- `0x140071960`
- `0x140379070`
- `0x140380bd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140071a99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140071b37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140071a99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140071b37`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140071bbe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140071bbe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140071bcc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140071bcc`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140071a79`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140071ae6`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140071a79`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140071ae6`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(
        __int64 a1,
        _QWORD *a2,
        unsigned __int64 *a3)
{
  unsigned __int64 v6; // rax
  wil::details::in1diag3 *v7; // rcx
  unsigned __int64 v8; // rbx
  int LastErrorFailHr; // edi
  unsigned __int64 v10; // rsi
  WCHAR *v11; // rcx
  __int64 v12; // rdi
  __int64 v13; // rdx
  WCHAR v14; // ax
  WCHAR *v15; // rax
  LONG v16; // r8d
  unsigned __int64 v17; // r14
  LONG v18; // esi
  wil::details *v19; // rcx
  HANDLE Semaphore; // rdi
  __int64 v21; // rdx
  LONG v22; // r8d
  wil::details *v23; // rcx
  HANDLE v24; // rdi
  unsigned __int64 v25; // rax
  HANDLE ProcessHeap; // rax
  DWORD dwFlags; // [rsp+20h] [rbp-E0h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-E0h]
  DWORD dwFlagsb; // [rsp+20h] [rbp-E0h]
  __int128 v31; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  *a3 = 0;
  v6 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, (unsigned __int64)a3);
  v8 = v6;
  if ( !v6 )
  {
    LastErrorFailHr = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x148, (unsigned int)"wil", (const char *)0x8007000ELL, dwFlags);
    return (unsigned int)LastErrorFailHr;
  }
  v31 = 0;
  if ( (v6 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v7);
  v10 = v6 >> 2;
  v11 = Name;
  v12 = a1 - (_QWORD)Name;
  v13 = 260;
  do
  {
    if ( v13 == -2147483386 )
      break;
    v14 = *(WCHAR *)((char *)v11 + v12);
    if ( !v14 )
      break;
    *v11++ = v14;
    --v13;
  }
  while ( v13 );
  v15 = v11 - 1;
  if ( v13 )
    v15 = v11;
  *v15 = 0;
  StringCchCatW(Name, 0x104u, L"_p0");
  v16 = 1;
  v17 = v8 >> 33;
  v18 = v10 & 0x7FFFFFFF;
  if ( v18 )
    v16 = v18;
  Semaphore = CreateSemaphoreExW(0, v18, v16, Name, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      &v31,
      Semaphore);
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v19);
    if ( LastErrorFailHr < 0 )
    {
      v21 = 136;
LABEL_21:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"wil",
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlagsa);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14B,
        (unsigned int)"wil",
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlagsb);
      goto LABEL_24;
    }
  }
  StringCchCatW(Name, 0x104u, L"h");
  v22 = 1;
  if ( (_DWORD)v17 )
    v22 = v8 >> 33;
  v24 = CreateSemaphoreExW(0, v17, v22, Name, 0, 0x1F0003u);
  if ( v24 )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      (char *)&v31 + 8,
      v24);
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v23);
    if ( LastErrorFailHr < 0 )
    {
      v21 = 141;
      goto LABEL_21;
    }
  }
  *(_DWORD *)v8 = 1;
  *(_QWORD *)(v8 + 8) = *a2;
  v25 = v31;
  *a2 = 0;
  *(_OWORD *)(v8 + 16) = __PAIR128__(*((unsigned __int64 *)&v31 + 1), v25);
  v31 = 0u;
  memset((void *)(v8 + 34), 0, 0x56u);
  *(_WORD *)(v8 + 32) = 88;
  *(_DWORD *)(v8 + 36) = 1;
  memset((void *)(v8 + 40), 0, 0x50u);
  *a3 = v8;
  v8 = 0;
  LastErrorFailHr = 0;
LABEL_24:
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)&v31);
  if ( v8 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)v8);
  }
  return (unsigned int)LastErrorFailHr;
}

```

## disassembly

```asm
0x140071960  mov     [rsp-8+arg_0], rbx
0x140071965  push    rbp
0x140071966  push    rsi
0x140071967  push    rdi
0x140071968  push    r12
0x14007196a  push    r13
0x14007196c  push    r14
0x14007196e  push    r15
0x140071970  lea     rbp, [rsp-160h]
0x140071978  sub     rsp, 260h
0x14007197f  mov     rax, cs:__security_cookie
0x140071986  xor     rax, rsp
0x140071989  mov     [rbp+190h+var_40], rax
0x140071990  xor     r13d, r13d
0x140071993  mov     r12, rdx
0x140071996  mov     rdi, rcx
0x140071999  mov     [r8], r13
0x14007199c  mov     r15, r8
0x14007199f  lea     edx, [r13+78h]; dwBytes
0x1400719a3  lea     ecx, [rdx-70h]; dwFlags
0x1400719a6  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400719ab  mov     rbx, rax
0x1400719ae  test    rax, rax
0x1400719b1  jnz     short loc_1400719D8
0x1400719b3  mov     rcx, [rbp+198h]; this
0x1400719ba  lea     r8, aWil; "wil"
0x1400719c1  mov     edi, 8007000Eh
0x1400719c6  mov     edx, 148h; void *
0x1400719cb  mov     r9d, edi; char *
0x1400719ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400719d3  jmp     loc_140071BD2
0x1400719d8  xorps   xmm0, xmm0
0x1400719db  movdqu  [rsp+290h+var_260], xmm0
0x1400719e1  test    bl, 3
0x1400719e4  jnz     loc_140071BFE
0x1400719ea  mov     rsi, rbx
0x1400719ed  lea     rax, [rsp+290h+Name]
0x1400719f2  shr     rsi, 2
0x1400719f6  lea     rcx, [rsp+290h+Name]
0x1400719fb  mov     r9d, 104h
0x140071a01  sub     rdi, rax
0x140071a04  mov     edx, r9d
0x140071a07  lea     rax, [rdx+7FFFFEFAh]
0x140071a0e  test    rax, rax
0x140071a11  jz      short loc_140071A29
0x140071a13  movzx   eax, word ptr [rcx+rdi]
0x140071a17  test    ax, ax
0x140071a1a  jz      short loc_140071A29
0x140071a1c  mov     [rcx], ax
0x140071a1f  add     rcx, 2
0x140071a23  sub     rdx, 1
0x140071a27  jnz     short loc_140071A07
0x140071a29  test    rdx, rdx
0x140071a2c  lea     rax, [rcx-2]
0x140071a30  lea     r8, aP0; "_p0"
0x140071a37  mov     rdx, r9; unsigned __int64
0x140071a3a  cmovnz  rax, rcx
0x140071a3e  lea     rcx, [rsp+290h+Name]; wchar_t *
0x140071a43  mov     [rax], r13w
0x140071a47  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140071a4c  mov     r14, rsi
0x140071a4f  mov     [rsp+290h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140071a57  mov     r8d, 1
0x140071a5d  shr     r14, 1Fh
0x140071a61  and     esi, 7FFFFFFFh
0x140071a67  mov     [rsp+290h+dwFlags], r13d; dwFlags
0x140071a6c  lea     r9, [rsp+290h+Name]; lpName
0x140071a71  mov     edx, esi; lInitialCount
0x140071a73  cmova   r8d, esi; lMaximumCount
0x140071a77  xor     ecx, ecx; lpSemaphoreAttributes
0x140071a79  call    cs:__imp_CreateSemaphoreExW
0x140071a7f  mov     rdi, rax
0x140071a82  test    rax, rax
0x140071a85  jnz     short loc_140071A99
0x140071a87  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140071a8c  mov     edi, eax
0x140071a8e  test    eax, eax
0x140071a90  jns     short loc_140071AAC
0x140071a92  mov     edx, 88h
0x140071a97  jmp     short loc_140071B04
0x140071a99  call    cs:__imp_GetLastError
0x140071a9f  mov     rdx, rdi
0x140071aa2  lea     rcx, [rsp+290h+var_260]
0x140071aa7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140071aac  lea     r8, asc_1403FCB6C; "h"
0x140071ab3  mov     edx, 104h; unsigned __int64
0x140071ab8  lea     rcx, [rsp+290h+Name]; wchar_t *
0x140071abd  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140071ac2  mov     r8d, 1
0x140071ac8  mov     [rsp+290h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140071ad0  test    r14d, r14d
0x140071ad3  mov     [rsp+290h+dwFlags], r13d; int
0x140071ad8  lea     r9, [rsp+290h+Name]; lpName
0x140071add  mov     edx, r14d; lInitialCount
0x140071ae0  cmovnz  r8d, r14d; lMaximumCount
0x140071ae4  xor     ecx, ecx; lpSemaphoreAttributes
0x140071ae6  call    cs:__imp_CreateSemaphoreExW
0x140071aec  mov     rdi, rax
0x140071aef  test    rax, rax
0x140071af2  jnz     short loc_140071B37
0x140071af4  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140071af9  mov     edi, eax
0x140071afb  test    eax, eax
0x140071afd  jns     short loc_140071B4A
0x140071aff  mov     edx, 8Dh; void *
0x140071b04  mov     rcx, [rbp+198h]; this
0x140071b0b  lea     r8, aWil; "wil"
0x140071b12  mov     r9d, edi; char *
0x140071b15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140071b1a  mov     rcx, [rbp+198h]; this
0x140071b21  lea     r8, aWil; "wil"
0x140071b28  mov     r9d, edi; char *
0x140071b2b  mov     edx, 14Bh; void *
0x140071b30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140071b35  jmp     short loc_140071BAF
0x140071b37  call    cs:__imp_GetLastError
0x140071b3d  mov     rdx, rdi
0x140071b40  lea     rcx, [rsp+290h+var_260+8]
0x140071b45  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140071b4a  mov     dword ptr [rbx], 1
0x140071b50  lea     rcx, [rbx+22h]; void *
0x140071b54  mov     rax, [r12]
0x140071b58  xor     edx, edx; Val
0x140071b5a  mov     [rbx+8], rax
0x140071b5e  mov     rdi, rbx
0x140071b61  mov     rax, qword ptr [rsp+290h+var_260]
0x140071b66  mov     [r12], r13
0x140071b6a  mov     [rbx+10h], rax
0x140071b6e  lea     r8d, [rdx+56h]; Size
0x140071b72  mov     rax, qword ptr [rsp+290h+var_260+8]
0x140071b77  mov     [rbx+18h], rax
0x140071b7b  mov     qword ptr [rsp+290h+var_260], r13
0x140071b80  mov     qword ptr [rsp+290h+var_260+8], r13
0x140071b85  call    memset
0x140071b8a  xor     edx, edx; Val
0x140071b8c  mov     word ptr [rbx+20h], 58h ; 'X'
0x140071b92  lea     rcx, [rbx+28h]; void *
0x140071b96  mov     dword ptr [rbx+24h], 1
0x140071b9d  lea     r8d, [rdx+50h]; Size
0x140071ba1  call    memset
0x140071ba6  mov     [r15], rdi
0x140071ba9  mov     rbx, r13
0x140071bac  mov     edi, r13d
0x140071baf  lea     rcx, [rsp+290h+var_260]; this
0x140071bb4  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x140071bb9  test    rbx, rbx
0x140071bbc  jz      short loc_140071BD2
0x140071bbe  call    cs:__imp_GetProcessHeap
0x140071bc4  mov     r8, rbx; lpMem
0x140071bc7  xor     edx, edx; dwFlags
0x140071bc9  mov     rcx, rax; hHeap
0x140071bcc  call    cs:__imp_HeapFree
0x140071bd2  mov     eax, edi
0x140071bd4  mov     rcx, [rbp+190h+var_40]
0x140071bdb  xor     rcx, rsp; StackCookie
0x140071bde  call    __security_check_cookie
0x140071be3  mov     rbx, [rsp+290h+arg_0]
0x140071beb  add     rsp, 260h
0x140071bf2  pop     r15
0x140071bf4  pop     r14
0x140071bf6  pop     r13
0x140071bf8  pop     r12
0x140071bfa  pop     rdi
0x140071bfb  pop     rsi
0x140071bfc  pop     rbp
0x140071bfd  retn
0x140071bfe  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
