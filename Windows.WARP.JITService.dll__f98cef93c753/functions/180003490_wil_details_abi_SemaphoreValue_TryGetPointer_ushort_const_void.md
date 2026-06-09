# wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)

- ea: `0x180003490`
- end: `0x18000374e`
- name: `?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z`
- size: `702`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void **)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003924`
- `0x180005b00`

## callees

- `0x1800012b4`
- `0x180002de0`
- `0x180002e04`
- `0x180002e24`
- `0x180003490`
- `0x180003754`
- `0x180008a80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180003530`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800035f6`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180003530`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800035f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000353e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000353e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800035cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000361a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003657`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003668`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000367e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000368f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800035cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000361a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003657`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003668`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000367e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000368f`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetPointer(const unsigned __int16 *a1, void **a2)
{
  WCHAR *v2; // rax
  unsigned __int64 v3; // rdi
  void **v4; // r15
  __int64 v5; // r9
  __int64 v6; // r8
  WCHAR *v7; // rcx
  HANDLE v8; // rax
  void *v9; // rsi
  unsigned int v10; // r8d
  const char *v11; // r9
  unsigned int LastError; // ebx
  __int64 v13; // r8
  int v14; // r8d
  int ValueFromSemaphore; // eax
  __int64 v17; // rdx
  int v18; // r8d
  const char *v19; // r9
  HANDLE v20; // rax
  unsigned int v21; // r8d
  const char *v22; // r9
  void *v23; // r14
  const char *v24; // r9
  int v25; // eax
  int v26; // r8d
  __int64 v27; // r8
  const char *v28; // r9
  const char *v29; // r9
  __int64 v30; // r8
  const char *v31; // r9
  __int64 v32; // r8
  const char *v33; // r9
  int v34; // [rsp+20h] [rbp-E0h] BYREF
  int v35[3]; // [rsp+24h] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  v2 = Name;
  *a2 = 0;
  v3 = 0;
  v4 = a2;
  v5 = 2147483646;
  v6 = 260;
  do
  {
    if ( !v5 )
      break;
    a2 = (void **)*a1;
    if ( !(_WORD)a2 )
      break;
    *v2 = (unsigned __int16)a2;
    ++a1;
    ++v2;
    --v5;
    --v6;
  }
  while ( v6 );
  v7 = v2 - 1;
  if ( v6 )
    v7 = v2;
  *v7 = 0;
  StringCchCatW(Name, (__int64)a2, L"_p0");
  v8 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v9 = v8;
  if ( v8 )
  {
    v35[0] = 0;
    v34 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v8, v35);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v18, (const char *)(unsigned int)ValueFromSemaphore);
      if ( !CloseHandle(v9) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v19);
      goto LABEL_11;
    }
    StringCchCatW(Name, v17, L"h");
    v20 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v23 = v20;
    if ( v20 )
    {
      v25 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v20, &v34);
      LastError = v25;
      if ( v25 < 0 )
      {
        wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v26, (const char *)(unsigned int)v25);
        if ( !CloseHandle(v23) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
        if ( !CloseHandle(v9) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v29);
        goto LABEL_11;
      }
      if ( !CloseHandle(v23) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
      if ( !CloseHandle(v9) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
      v3 = v35[0] | (unsigned __int64)((__int64)v34 << 31);
      goto LABEL_25;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v21, v22);
    if ( !CloseHandle(v9) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v24);
  }
  else
  {
    if ( GetLastError() == 2 )
      goto LABEL_25;
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v10, v11);
  }
  if ( (LastError & 0x80000000) != 0 )
  {
LABEL_11:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v13, (const char *)LastError);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v14, (const char *)LastError);
    return LastError;
  }
LABEL_25:
  *v4 = (void *)(4 * v3);
  return 0;
}

```

## disassembly

```asm
0x180003490  mov     [rsp-8+arg_0], rbx
0x180003495  mov     [rsp-8+arg_10], rsi
0x18000349a  push    rbp
0x18000349b  push    rdi
0x18000349c  push    r12
0x18000349e  push    r14
0x1800034a0  push    r15
0x1800034a2  lea     rbp, [rsp-150h]
0x1800034aa  sub     rsp, 250h
0x1800034b1  mov     rax, cs:__security_cookie
0x1800034b8  xor     rax, rsp
0x1800034bb  mov     [rbp+170h+var_30], rax
0x1800034c2  xor     r12d, r12d
0x1800034c5  lea     rax, [rsp+270h+Name]
0x1800034ca  mov     [rdx], r12
0x1800034cd  mov     edi, r12d
0x1800034d0  mov     r15, rdx
0x1800034d3  mov     r9d, 7FFFFFFEh
0x1800034d9  mov     r8d, 104h
0x1800034df  test    r9, r9
0x1800034e2  jz      short loc_180003500
0x1800034e4  movzx   edx, word ptr [rcx]; unsigned __int64
0x1800034e7  test    dx, dx
0x1800034ea  jz      short loc_180003500
0x1800034ec  mov     [rax], dx
0x1800034ef  add     rcx, 2
0x1800034f3  add     rax, 2
0x1800034f7  dec     r9
0x1800034fa  sub     r8, 1
0x1800034fe  jnz     short loc_1800034DF
0x180003500  test    r8, r8
0x180003503  lea     rcx, [rax-2]
0x180003507  lea     r8, aP0; "_p0"
0x18000350e  cmovnz  rcx, rax
0x180003512  mov     [rcx], r12w
0x180003516  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000351b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003520  mov     r14d, 1F0003h
0x180003526  lea     r8, [rsp+270h+Name]; lpName
0x18000352b  mov     ecx, r14d; dwDesiredAccess
0x18000352e  xor     edx, edx; bInheritHandle
0x180003530  call    cs:__imp_OpenSemaphoreW
0x180003536  mov     rsi, rax
0x180003539  test    rax, rax
0x18000353c  jnz     short loc_180003597
0x18000353e  call    cs:__imp_GetLastError
0x180003544  cmp     eax, 2
0x180003547  jz      loc_1800036AA
0x18000354d  mov     rcx, [rbp+178h]; this
0x180003554  mov     edx, 0D0h; void *
0x180003559  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000355e  mov     ebx, eax
0x180003560  test    ebx, ebx
0x180003562  jns     loc_1800036AA
0x180003568  mov     rcx, [rbp+178h]; this
0x18000356f  mov     r9d, ebx; char *
0x180003572  mov     edx, 66h ; 'f'; void *
0x180003577  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000357c  mov     rcx, [rbp+178h]; this
0x180003583  mov     r9d, ebx; char *
0x180003586  mov     edx, 6Fh ; 'o'; void *
0x18000358b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003590  mov     eax, ebx
0x180003592  jmp     loc_1800036B7
0x180003597  lea     rdx, [rsp+270h+var_24C]; int *
0x18000359c  mov     [rsp+270h+var_24C], r12d
0x1800035a1  mov     rcx, rsi; hHandle
0x1800035a4  mov     [rsp+270h+var_250], r12d; int
0x1800035a9  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800035ae  mov     ebx, eax
0x1800035b0  test    eax, eax
0x1800035b2  jns     short loc_1800035DB
0x1800035b4  mov     rcx, [rbp+178h]; this
0x1800035bb  mov     r9d, eax; char *
0x1800035be  mov     edx, 0D6h; void *
0x1800035c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800035c8  mov     rcx, rsi; hObject
0x1800035cb  call    cs:__imp_CloseHandle
0x1800035d1  test    eax, eax
0x1800035d3  jz      loc_1800036F4
0x1800035d9  jmp     short loc_180003568
0x1800035db  lea     r8, asc_18000BC28; "h"
0x1800035e2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800035e7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800035ec  lea     r8, [rsp+270h+Name]; lpName
0x1800035f1  xor     edx, edx; bInheritHandle
0x1800035f3  mov     ecx, r14d; dwDesiredAccess
0x1800035f6  call    cs:__imp_OpenSemaphoreW
0x1800035fc  mov     r14, rax
0x1800035ff  test    rax, rax
0x180003602  jnz     short loc_18000362D
0x180003604  mov     rcx, [rbp+178h]; this
0x18000360b  mov     edx, 0DCh; void *
0x180003610  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180003615  mov     rcx, rsi; hObject
0x180003618  mov     ebx, eax
0x18000361a  call    cs:__imp_CloseHandle
0x180003620  test    eax, eax
0x180003622  jz      loc_180003706
0x180003628  jmp     loc_180003560
0x18000362d  lea     rdx, [rsp+270h+var_250]; int *
0x180003632  mov     rcx, r14; hHandle
0x180003635  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000363a  mov     ebx, eax
0x18000363c  test    eax, eax
0x18000363e  jns     short loc_18000367B
0x180003640  mov     rcx, [rbp+178h]; this
0x180003647  mov     r9d, eax; char *
0x18000364a  mov     edx, 0DEh; void *
0x18000364f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003654  mov     rcx, r14; hObject
0x180003657  call    cs:__imp_CloseHandle
0x18000365d  test    eax, eax
0x18000365f  jz      loc_18000372A
0x180003665  mov     rcx, rsi; hObject
0x180003668  call    cs:__imp_CloseHandle
0x18000366e  test    eax, eax
0x180003670  jz      loc_180003718
0x180003676  jmp     loc_180003568
0x18000367b  mov     rcx, r14; hObject
0x18000367e  call    cs:__imp_CloseHandle
0x180003684  test    eax, eax
0x180003686  jz      loc_18000373C
0x18000368c  mov     rcx, rsi; hObject
0x18000368f  call    cs:__imp_CloseHandle
0x180003695  test    eax, eax
0x180003697  jz      short loc_1800036E2
0x180003699  movsxd  rdi, [rsp+270h+var_250]
0x18000369e  movsxd  rax, [rsp+270h+var_24C]
0x1800036a3  shl     rdi, 1Fh
0x1800036a7  or      rdi, rax
0x1800036aa  lea     rax, ds:0[rdi*4]
0x1800036b2  mov     [r15], rax
0x1800036b5  xor     eax, eax
0x1800036b7  mov     rcx, [rbp+170h+var_30]
0x1800036be  xor     rcx, rsp; StackCookie
0x1800036c1  call    __security_check_cookie
0x1800036c6  lea     r11, [rsp+270h+var_20]
0x1800036ce  mov     rbx, [r11+30h]
0x1800036d2  mov     rsi, [r11+40h]
0x1800036d6  mov     rsp, r11
0x1800036d9  pop     r15
0x1800036db  pop     r14
0x1800036dd  pop     r12
0x1800036df  pop     rdi
0x1800036e0  pop     rbp
0x1800036e1  retn
0x1800036e2  mov     rcx, [rbp+178h]; this
0x1800036e9  mov     edx, 0A0Bh; void *
0x1800036ee  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800036f4  mov     rcx, [rbp+178h]; this
0x1800036fb  mov     edx, 0A0Bh; void *
0x180003700  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003706  mov     rcx, [rbp+178h]; this
0x18000370d  mov     edx, 0A0Bh; void *
0x180003712  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003718  mov     rcx, [rbp+178h]; this
0x18000371f  mov     edx, 0A0Bh; void *
0x180003724  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000372a  mov     rcx, [rbp+178h]; this
0x180003731  mov     edx, 0A0Bh; void *
0x180003736  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000373c  mov     rcx, [rbp+178h]; this
0x180003743  mov     edx, 0A0Bh; void *
0x180003748  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
