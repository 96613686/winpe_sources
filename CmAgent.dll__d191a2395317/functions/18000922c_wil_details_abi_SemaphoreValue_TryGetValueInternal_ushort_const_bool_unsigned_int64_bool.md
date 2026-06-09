# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000922c`
- end: `0x1800094f2`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `710`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180005eb4`
- `0x180015c7c`

## callees

- `0x180002140`
- `0x1800045e4`
- `0x180006ab8`
- `0x180007b2c`
- `0x1800090f0`
- `0x18000922c`
- `0x180009518`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800092c0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009348`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800092c0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009348`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009439`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009439`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009313`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009391`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800093a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800093c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800093f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009424`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009313`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009391`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800093a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800093c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800093f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009424`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  unsigned __int64 v6; // rdx
  __int64 v7; // r9
  WCHAR *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  unsigned __int64 v12; // rdx
  unsigned int LastError; // edi
  __int64 v14; // r8
  const char *v15; // r9
  HANDLE v17; // rax
  const char *v18; // r9
  void *v19; // rdi
  int v20; // eax
  unsigned int v21; // esi
  __int64 v22; // r8
  const char *v23; // r9
  __int64 v24; // r8
  const char *v25; // r9
  __int64 v26; // r8
  const char *v27; // r9
  __int64 v28; // r8
  const char *v29; // r9
  __int64 v30; // r8
  const char *v31; // r9
  const char *v32; // r9
  int v33; // [rsp+20h] [rbp-E0h] BYREF
  int v34[3]; // [rsp+24h] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = Name;
  *a3 = 0;
  v6 = 260;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v6;
  }
  while ( v6 );
  v8 = v4 - 1;
  if ( v6 )
    v8 = v4;
  *v8 = 0;
  StringCchCatW(Name, v6, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (int)"wil", v32);
    return 0;
  }
  v34[0] = 0;
  v33 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v34);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, (int)"wil", (const char *)(unsigned int)ValueFromSemaphore);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v19 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (int)"wil", v18);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    return LastError;
  }
  v20 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v33);
  v21 = v20;
  if ( v20 >= 0 )
  {
    if ( !CloseHandle(v19) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    *a3 = v34[0] | (unsigned __int64)((__int64)v33 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v20);
  if ( !CloseHandle(v19) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  return v21;
}

```

## disassembly

```asm
0x18000922c  push    rbp
0x18000922e  push    rbx
0x18000922f  push    rsi
0x180009230  push    rdi
0x180009231  push    r14
0x180009233  push    r15
0x180009235  lea     rbp, [rsp-158h]
0x18000923d  sub     rsp, 258h
0x180009244  mov     rax, cs:__security_cookie
0x18000924b  xor     rax, rsp
0x18000924e  mov     [rbp+180h+var_40], rax
0x180009255  xor     r15d, r15d
0x180009258  lea     rax, [rsp+280h+Name]
0x18000925d  mov     [r8], r15
0x180009260  mov     r14, r8
0x180009263  mov     edx, 104h
0x180009268  mov     r9d, 7FFFFFFEh
0x18000926e  test    r9, r9
0x180009271  jz      short loc_180009292
0x180009273  movzx   r8d, word ptr [rcx]
0x180009277  test    r8w, r8w
0x18000927b  jz      short loc_180009292
0x18000927d  mov     [rax], r8w
0x180009281  add     rcx, 2
0x180009285  add     rax, 2
0x180009289  dec     r9
0x18000928c  sub     rdx, 1; unsigned __int64
0x180009290  jnz     short loc_18000926E
0x180009292  test    rdx, rdx
0x180009295  lea     rcx, [rax-2]
0x180009299  lea     r8, aP0; "_p0"
0x1800092a0  cmovnz  rcx, rax
0x1800092a4  mov     [rcx], r15w
0x1800092a8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800092ad  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800092b2  mov     esi, 1F0003h
0x1800092b7  lea     r8, [rsp+280h+Name]; lpName
0x1800092bc  mov     ecx, esi; dwDesiredAccess
0x1800092be  xor     edx, edx; bInheritHandle
0x1800092c0  call    cs:__imp_OpenSemaphoreW
0x1800092c7  nop     dword ptr [rax+rax+00h]
0x1800092cc  mov     rbx, rax
0x1800092cf  test    rax, rax
0x1800092d2  jz      loc_180009439
0x1800092d8  lea     rdx, [rsp+280h+var_25C]; int *
0x1800092dd  mov     [rsp+280h+var_25C], r15d
0x1800092e2  mov     rcx, rax; hHandle
0x1800092e5  mov     [rsp+280h+var_260], r15d; int
0x1800092ea  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800092ef  mov     edi, eax
0x1800092f1  test    eax, eax
0x1800092f3  jns     short loc_18000932E
0x1800092f5  mov     rcx, [rbp+188h]; this
0x1800092fc  lea     r8, aWil; "wil"
0x180009303  mov     r9d, eax; char *
0x180009306  mov     edx, 0D6h; void *
0x18000930b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009310  mov     rcx, rbx; hObject
0x180009313  call    cs:__imp_CloseHandle
0x18000931a  nop     dword ptr [rax+rax+00h]
0x18000931f  test    eax, eax
0x180009321  jz      loc_1800094BC
0x180009327  mov     eax, edi
0x180009329  jmp     loc_180009466
0x18000932e  lea     r8, asc_18003F730; "h"
0x180009335  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000933a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000933f  lea     r8, [rsp+280h+Name]; lpName
0x180009344  xor     edx, edx; bInheritHandle
0x180009346  mov     ecx, esi; dwDesiredAccess
0x180009348  call    cs:__imp_OpenSemaphoreW
0x18000934f  nop     dword ptr [rax+rax+00h]
0x180009354  mov     rdi, rax
0x180009357  test    rax, rax
0x18000935a  jz      loc_180009407
0x180009360  lea     rdx, [rsp+280h+var_260]; int *
0x180009365  mov     rcx, rax; hHandle
0x180009368  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000936d  mov     esi, eax
0x18000936f  test    eax, eax
0x180009371  jns     short loc_1800093C3
0x180009373  mov     rcx, [rbp+188h]; this
0x18000937a  lea     r8, aWil; "wil"
0x180009381  mov     r9d, eax; char *
0x180009384  mov     edx, 0DEh; void *
0x180009389  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000938e  mov     rcx, rdi; hObject
0x180009391  call    cs:__imp_CloseHandle
0x180009398  nop     dword ptr [rax+rax+00h]
0x18000939d  test    eax, eax
0x18000939f  jz      loc_1800094CE
0x1800093a5  mov     rcx, rbx; hObject
0x1800093a8  call    cs:__imp_CloseHandle
0x1800093af  nop     dword ptr [rax+rax+00h]
0x1800093b4  test    eax, eax
0x1800093b6  jz      loc_1800094E0
0x1800093bc  mov     eax, esi
0x1800093be  jmp     loc_180009466
0x1800093c3  mov     rcx, rdi; hObject
0x1800093c6  call    cs:__imp_CloseHandle
0x1800093cd  nop     dword ptr [rax+rax+00h]
0x1800093d2  test    eax, eax
0x1800093d4  jz      loc_180009486
0x1800093da  movsxd  rax, [rsp+280h+var_25C]
0x1800093df  movsxd  rcx, [rsp+280h+var_260]
0x1800093e4  shl     rcx, 1Fh
0x1800093e8  or      rcx, rax
0x1800093eb  mov     [r14], rcx
0x1800093ee  mov     rcx, rbx; hObject
0x1800093f1  call    cs:__imp_CloseHandle
0x1800093f8  nop     dword ptr [rax+rax+00h]
0x1800093fd  test    eax, eax
0x1800093ff  jz      loc_180009498
0x180009405  jmp     short loc_18000944A
0x180009407  mov     rcx, [rbp+188h]; this
0x18000940e  lea     r8, aWil; "wil"
0x180009415  mov     edx, 0DCh; void *
0x18000941a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000941f  mov     rcx, rbx; hObject
0x180009422  mov     edi, eax
0x180009424  call    cs:__imp_CloseHandle
0x18000942b  nop     dword ptr [rax+rax+00h]
0x180009430  test    eax, eax
0x180009432  jz      short loc_1800094AA
0x180009434  jmp     loc_180009327
0x180009439  call    cs:__imp_GetLastError
0x180009440  nop     dword ptr [rax+rax+00h]
0x180009445  cmp     eax, 2
0x180009448  jnz     short loc_18000944E
0x18000944a  xor     eax, eax
0x18000944c  jmp     short loc_180009466
0x18000944e  mov     rcx, [rbp+188h]; this
0x180009455  lea     r8, aWil; "wil"
0x18000945c  mov     edx, 0D0h; void *
0x180009461  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009466  mov     rcx, [rbp+180h+var_40]
0x18000946d  xor     rcx, rsp; StackCookie
0x180009470  call    __security_check_cookie
0x180009475  add     rsp, 258h
0x18000947c  pop     r15
0x18000947e  pop     r14
0x180009480  pop     rdi
0x180009481  pop     rsi
0x180009482  pop     rbx
0x180009483  pop     rbp
0x180009484  retn
0x180009486  mov     rcx, [rbp+188h]; this
0x18000948d  mov     edx, 0A0Bh; void *
0x180009492  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009498  mov     rcx, [rbp+188h]; this
0x18000949f  mov     edx, 0A0Bh; void *
0x1800094a4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800094aa  mov     rcx, [rbp+188h]; this
0x1800094b1  mov     edx, 0A0Bh; void *
0x1800094b6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800094bc  mov     rcx, [rbp+188h]; this
0x1800094c3  mov     edx, 0A0Bh; void *
0x1800094c8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800094ce  mov     rcx, [rbp+188h]; this
0x1800094d5  mov     edx, 0A0Bh; void *
0x1800094da  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800094e0  mov     rcx, [rbp+188h]; this
0x1800094e7  mov     edx, 0A0Bh; void *
0x1800094ec  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
