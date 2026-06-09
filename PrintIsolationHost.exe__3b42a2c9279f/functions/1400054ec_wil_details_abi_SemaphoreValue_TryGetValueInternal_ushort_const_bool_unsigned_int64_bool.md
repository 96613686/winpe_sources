# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1400054ec`
- end: `0x140005758`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14000323c`

## callees

- `0x140001cd0`
- `0x1400041c0`
- `0x1400050e8`
- `0x140005108`
- `0x1400053b0`
- `0x1400054ec`
- `0x1400058ac`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400056ad`
- `KERNEL32!GetLastError` at `0x1400056ad`
- `KERNEL32!OpenSemaphoreW` at `0x140005580`
- `KERNEL32!OpenSemaphoreW` at `0x1400055f5`
- `KERNEL32!OpenSemaphoreW` at `0x140005580`
- `KERNEL32!OpenSemaphoreW` at `0x1400055f5`
- `KERNEL32!CloseHandle` at `0x1400055c6`
- `KERNEL32!CloseHandle` at `0x140005631`
- `KERNEL32!CloseHandle` at `0x140005642`
- `KERNEL32!CloseHandle` at `0x140005657`
- `KERNEL32!CloseHandle` at `0x14000567c`
- `KERNEL32!CloseHandle` at `0x14000569e`
- `KERNEL32!CloseHandle` at `0x1400055c6`
- `KERNEL32!CloseHandle` at `0x140005631`
- `KERNEL32!CloseHandle` at `0x140005642`
- `KERNEL32!CloseHandle` at `0x140005657`
- `KERNEL32!CloseHandle` at `0x14000567c`
- `KERNEL32!CloseHandle` at `0x14000569e`

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
  unsigned int v13; // r8d
  unsigned int LastError; // edi
  unsigned int v15; // r8d
  const char *v16; // r9
  HANDLE v18; // rax
  unsigned int v19; // r8d
  const char *v20; // r9
  void *v21; // rdi
  int v22; // eax
  unsigned int v23; // r8d
  unsigned int v24; // esi
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  unsigned int v35; // r8d
  const char *v36; // r9
  int v37; // [rsp+20h] [rbp-E0h] BYREF
  int v38[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v35, v36);
    return 0;
  }
  v38[0] = 0;
  v37 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v38);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore, v37);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v15, v16);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v18 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v21 = v18;
  if ( !v18 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v19, v20);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    return LastError;
  }
  v22 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v18, &v37);
  v24 = v22;
  if ( v22 >= 0 )
  {
    if ( !CloseHandle(v21) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    *a3 = v38[0] | (unsigned __int64)((__int64)v37 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v23, (const char *)(unsigned int)v22, v37);
  if ( !CloseHandle(v21) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
  return v24;
}

```

## disassembly

```asm
0x1400054ec  push    rbp
0x1400054ee  push    rbx
0x1400054ef  push    rsi
0x1400054f0  push    rdi
0x1400054f1  push    r14
0x1400054f3  push    r15
0x1400054f5  lea     rbp, [rsp-158h]
0x1400054fd  sub     rsp, 258h
0x140005504  mov     rax, cs:__security_cookie
0x14000550b  xor     rax, rsp
0x14000550e  mov     [rbp+180h+var_40], rax
0x140005515  xor     r15d, r15d
0x140005518  lea     rax, [rsp+280h+Name]
0x14000551d  mov     [r8], r15
0x140005520  mov     r14, r8
0x140005523  mov     edx, 104h
0x140005528  mov     r9d, 7FFFFFFEh
0x14000552e  test    r9, r9
0x140005531  jz      short loc_140005552
0x140005533  movzx   r8d, word ptr [rcx]
0x140005537  test    r8w, r8w
0x14000553b  jz      short loc_140005552
0x14000553d  mov     [rax], r8w
0x140005541  add     rcx, 2
0x140005545  add     rax, 2
0x140005549  dec     r9
0x14000554c  sub     rdx, 1; unsigned __int64
0x140005550  jnz     short loc_14000552E
0x140005552  test    rdx, rdx
0x140005555  lea     rcx, [rax-2]
0x140005559  lea     r8, aP0; "_p0"
0x140005560  cmovnz  rcx, rax
0x140005564  mov     [rcx], r15w
0x140005568  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000556d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140005572  mov     esi, 1F0003h
0x140005577  lea     r8, [rsp+280h+Name]; lpName
0x14000557c  mov     ecx, esi; dwDesiredAccess
0x14000557e  xor     edx, edx; bInheritHandle
0x140005580  call    cs:__imp_OpenSemaphoreW
0x140005586  mov     rbx, rax
0x140005589  test    rax, rax
0x14000558c  jz      loc_1400056AD
0x140005592  lea     rdx, [rsp+280h+var_25C]; int *
0x140005597  mov     [rsp+280h+var_25C], r15d
0x14000559c  mov     rcx, rax; hHandle
0x14000559f  mov     [rsp+280h+var_260], r15d; int
0x1400055a4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1400055a9  mov     edi, eax
0x1400055ab  test    eax, eax
0x1400055ad  jns     short loc_1400055DB
0x1400055af  mov     rcx, [rbp+188h]; this
0x1400055b6  mov     r9d, eax; char *
0x1400055b9  mov     edx, 0D6h; void *
0x1400055be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400055c3  mov     rcx, rbx; hObject
0x1400055c6  call    cs:__imp_CloseHandle
0x1400055cc  test    eax, eax
0x1400055ce  jz      loc_140005722
0x1400055d4  mov     eax, edi
0x1400055d6  jmp     loc_1400056CD
0x1400055db  lea     r8, asc_140009A88; "h"
0x1400055e2  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400055e7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400055ec  lea     r8, [rsp+280h+Name]; lpName
0x1400055f1  xor     edx, edx; bInheritHandle
0x1400055f3  mov     ecx, esi; dwDesiredAccess
0x1400055f5  call    cs:__imp_OpenSemaphoreW
0x1400055fb  mov     rdi, rax
0x1400055fe  test    rax, rax
0x140005601  jz      loc_140005688
0x140005607  lea     rdx, [rsp+280h+var_260]; int *
0x14000560c  mov     rcx, rax; hHandle
0x14000560f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140005614  mov     esi, eax
0x140005616  test    eax, eax
0x140005618  jns     short loc_140005654
0x14000561a  mov     rcx, [rbp+188h]; this
0x140005621  mov     r9d, eax; char *
0x140005624  mov     edx, 0DEh; void *
0x140005629  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000562e  mov     rcx, rdi; hObject
0x140005631  call    cs:__imp_CloseHandle
0x140005637  test    eax, eax
0x140005639  jz      loc_140005734
0x14000563f  mov     rcx, rbx; hObject
0x140005642  call    cs:__imp_CloseHandle
0x140005648  test    eax, eax
0x14000564a  jz      loc_140005746
0x140005650  mov     eax, esi
0x140005652  jmp     short loc_1400056CD
0x140005654  mov     rcx, rdi; hObject
0x140005657  call    cs:__imp_CloseHandle
0x14000565d  test    eax, eax
0x14000565f  jz      loc_1400056EC
0x140005665  movsxd  rax, [rsp+280h+var_25C]
0x14000566a  movsxd  rcx, [rsp+280h+var_260]
0x14000566f  shl     rcx, 1Fh
0x140005673  or      rcx, rax
0x140005676  mov     [r14], rcx
0x140005679  mov     rcx, rbx; hObject
0x14000567c  call    cs:__imp_CloseHandle
0x140005682  test    eax, eax
0x140005684  jz      short loc_1400056FE
0x140005686  jmp     short loc_1400056B8
0x140005688  mov     rcx, [rbp+188h]; this
0x14000568f  mov     edx, 0DCh; void *
0x140005694  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140005699  mov     rcx, rbx; hObject
0x14000569c  mov     edi, eax
0x14000569e  call    cs:__imp_CloseHandle
0x1400056a4  test    eax, eax
0x1400056a6  jz      short loc_140005710
0x1400056a8  jmp     loc_1400055D4
0x1400056ad  call    cs:__imp_GetLastError
0x1400056b3  cmp     eax, 2
0x1400056b6  jnz     short loc_1400056BC
0x1400056b8  xor     eax, eax
0x1400056ba  jmp     short loc_1400056CD
0x1400056bc  mov     rcx, [rbp+188h]; this
0x1400056c3  mov     edx, 0D0h; void *
0x1400056c8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400056cd  mov     rcx, [rbp+180h+var_40]
0x1400056d4  xor     rcx, rsp; StackCookie
0x1400056d7  call    __security_check_cookie
0x1400056dc  add     rsp, 258h
0x1400056e3  pop     r15
0x1400056e5  pop     r14
0x1400056e7  pop     rdi
0x1400056e8  pop     rsi
0x1400056e9  pop     rbx
0x1400056ea  pop     rbp
0x1400056eb  retn
0x1400056ec  mov     rcx, [rbp+188h]; this
0x1400056f3  mov     edx, 0A0Bh; void *
0x1400056f8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400056fe  mov     rcx, [rbp+188h]; this
0x140005705  mov     edx, 0A0Bh; void *
0x14000570a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005710  mov     rcx, [rbp+188h]; this
0x140005717  mov     edx, 0A0Bh; void *
0x14000571c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005722  mov     rcx, [rbp+188h]; this
0x140005729  mov     edx, 0A0Bh; void *
0x14000572e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005734  mov     rcx, [rbp+188h]; this
0x14000573b  mov     edx, 0A0Bh; void *
0x140005740  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005746  mov     rcx, [rbp+188h]; this
0x14000574d  mov     edx, 0A0Bh; void *
0x140005752  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
