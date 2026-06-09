# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800075ac`
- end: `0x180007826`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800048d8`
- `0x180009dec`

## callees

- `0x180002240`
- `0x180005dd4`
- `0x1800069f4`
- `0x180006a14`
- `0x180007354`
- `0x1800075ac`
- `0x180007a58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007640`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800076bc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007640`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800076bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000777b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000777b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000768d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800076ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007710`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007725`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000774a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000776c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000768d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800076ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007710`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007725`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000774a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000776c`

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
  unsigned int v14; // r8d
  const char *v15; // r9
  HANDLE v17; // rax
  unsigned int v18; // r8d
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  unsigned int v22; // esi
  unsigned int v23; // r8d
  const char *v24; // r9
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
  int v35; // [rsp+20h] [rbp-E0h] BYREF
  int v36[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v33, v34);
    return 0;
  }
  v36[0] = 0;
  v35 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v36);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v35);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v18, v19);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    return LastError;
  }
  v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v35);
  v22 = v21;
  if ( v21 >= 0 )
  {
    if ( !CloseHandle(v20) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    *a3 = v36[0] | (unsigned __int64)((__int64)v35 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v21, v35);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  return v22;
}

```

## disassembly

```asm
0x1800075ac  push    rbp
0x1800075ae  push    rbx
0x1800075af  push    rsi
0x1800075b0  push    rdi
0x1800075b1  push    r14
0x1800075b3  push    r15
0x1800075b5  lea     rbp, [rsp-158h]
0x1800075bd  sub     rsp, 258h
0x1800075c4  mov     rax, cs:__security_cookie
0x1800075cb  xor     rax, rsp
0x1800075ce  mov     [rbp+180h+var_40], rax
0x1800075d5  xor     r15d, r15d
0x1800075d8  lea     rax, [rsp+280h+Name]
0x1800075dd  mov     [r8], r15
0x1800075e0  mov     r14, r8
0x1800075e3  mov     edx, 104h
0x1800075e8  mov     r9d, 7FFFFFFEh
0x1800075ee  test    r9, r9
0x1800075f1  jz      short loc_180007612
0x1800075f3  movzx   r8d, word ptr [rcx]
0x1800075f7  test    r8w, r8w
0x1800075fb  jz      short loc_180007612
0x1800075fd  mov     [rax], r8w
0x180007601  add     rcx, 2
0x180007605  add     rax, 2
0x180007609  dec     r9
0x18000760c  sub     rdx, 1; unsigned __int64
0x180007610  jnz     short loc_1800075EE
0x180007612  test    rdx, rdx
0x180007615  lea     rcx, [rax-2]
0x180007619  lea     r8, aP0; "_p0"
0x180007620  cmovnz  rcx, rax
0x180007624  mov     [rcx], r15w
0x180007628  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000762d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007632  mov     esi, 1F0003h
0x180007637  lea     r8, [rsp+280h+Name]; lpName
0x18000763c  mov     ecx, esi; dwDesiredAccess
0x18000763e  xor     edx, edx; bInheritHandle
0x180007640  call    cs:__imp_OpenSemaphoreW
0x180007646  mov     rbx, rax
0x180007649  test    rax, rax
0x18000764c  jz      loc_18000777B
0x180007652  lea     rdx, [rsp+280h+var_25C]; int *
0x180007657  mov     [rsp+280h+var_25C], r15d
0x18000765c  mov     rcx, rax; hHandle
0x18000765f  mov     [rsp+280h+var_260], r15d; int
0x180007664  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007669  mov     edi, eax
0x18000766b  test    eax, eax
0x18000766d  jns     short loc_1800076A2
0x18000766f  mov     rcx, [rbp+188h]; this
0x180007676  lea     r8, aWil; "wil"
0x18000767d  mov     r9d, eax; char *
0x180007680  mov     edx, 0D6h; void *
0x180007685  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000768a  mov     rcx, rbx; hObject
0x18000768d  call    cs:__imp_CloseHandle
0x180007693  test    eax, eax
0x180007695  jz      loc_1800077F0
0x18000769b  mov     eax, edi
0x18000769d  jmp     loc_18000779B
0x1800076a2  lea     r8, asc_18006CEF8; "h"
0x1800076a9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800076ae  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800076b3  lea     r8, [rsp+280h+Name]; lpName
0x1800076b8  xor     edx, edx; bInheritHandle
0x1800076ba  mov     ecx, esi; dwDesiredAccess
0x1800076bc  call    cs:__imp_OpenSemaphoreW
0x1800076c2  mov     rdi, rax
0x1800076c5  test    rax, rax
0x1800076c8  jz      loc_180007756
0x1800076ce  lea     rdx, [rsp+280h+var_260]; int *
0x1800076d3  mov     rcx, rax; hHandle
0x1800076d6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800076db  mov     esi, eax
0x1800076dd  test    eax, eax
0x1800076df  jns     short loc_180007722
0x1800076e1  mov     rcx, [rbp+188h]; this
0x1800076e8  lea     r8, aWil; "wil"
0x1800076ef  mov     r9d, eax; char *
0x1800076f2  mov     edx, 0DEh; void *
0x1800076f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800076fc  mov     rcx, rdi; hObject
0x1800076ff  call    cs:__imp_CloseHandle
0x180007705  test    eax, eax
0x180007707  jz      loc_180007802
0x18000770d  mov     rcx, rbx; hObject
0x180007710  call    cs:__imp_CloseHandle
0x180007716  test    eax, eax
0x180007718  jz      loc_180007814
0x18000771e  mov     eax, esi
0x180007720  jmp     short loc_18000779B
0x180007722  mov     rcx, rdi; hObject
0x180007725  call    cs:__imp_CloseHandle
0x18000772b  test    eax, eax
0x18000772d  jz      loc_1800077BA
0x180007733  movsxd  rax, [rsp+280h+var_25C]
0x180007738  movsxd  rcx, [rsp+280h+var_260]
0x18000773d  shl     rcx, 1Fh
0x180007741  or      rcx, rax
0x180007744  mov     [r14], rcx
0x180007747  mov     rcx, rbx; hObject
0x18000774a  call    cs:__imp_CloseHandle
0x180007750  test    eax, eax
0x180007752  jz      short loc_1800077CC
0x180007754  jmp     short loc_180007786
0x180007756  mov     rcx, [rbp+188h]; this
0x18000775d  mov     edx, 0DCh; void *
0x180007762  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007767  mov     rcx, rbx; hObject
0x18000776a  mov     edi, eax
0x18000776c  call    cs:__imp_CloseHandle
0x180007772  test    eax, eax
0x180007774  jz      short loc_1800077DE
0x180007776  jmp     loc_18000769B
0x18000777b  call    cs:__imp_GetLastError
0x180007781  cmp     eax, 2
0x180007784  jnz     short loc_18000778A
0x180007786  xor     eax, eax
0x180007788  jmp     short loc_18000779B
0x18000778a  mov     rcx, [rbp+188h]; this
0x180007791  mov     edx, 0D0h; void *
0x180007796  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000779b  mov     rcx, [rbp+180h+var_40]
0x1800077a2  xor     rcx, rsp; StackCookie
0x1800077a5  call    __security_check_cookie
0x1800077aa  add     rsp, 258h
0x1800077b1  pop     r15
0x1800077b3  pop     r14
0x1800077b5  pop     rdi
0x1800077b6  pop     rsi
0x1800077b7  pop     rbx
0x1800077b8  pop     rbp
0x1800077b9  retn
0x1800077ba  mov     rcx, [rbp+188h]; this
0x1800077c1  mov     edx, 0A0Bh; void *
0x1800077c6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800077cc  mov     rcx, [rbp+188h]; this
0x1800077d3  mov     edx, 0A0Bh; void *
0x1800077d8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800077de  mov     rcx, [rbp+188h]; this
0x1800077e5  mov     edx, 0A0Bh; void *
0x1800077ea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800077f0  mov     rcx, [rbp+188h]; this
0x1800077f7  mov     edx, 0A0Bh; void *
0x1800077fc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007802  mov     rcx, [rbp+188h]; this
0x180007809  mov     edx, 0A0Bh; void *
0x18000780e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007814  mov     rcx, [rbp+188h]; this
0x18000781b  mov     edx, 0A0Bh; void *
0x180007820  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
