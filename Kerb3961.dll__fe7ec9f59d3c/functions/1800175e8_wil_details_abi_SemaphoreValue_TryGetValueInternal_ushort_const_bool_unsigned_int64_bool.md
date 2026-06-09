# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800175e8`
- end: `0x180017854`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800109f4`
- `0x18001c7b4`

## callees

- `0x180001d40`
- `0x18001452c`
- `0x1800165c8`
- `0x1800165e8`
- `0x180016d24`
- `0x1800175e8`
- `0x180017f00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001767c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800176f1`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001767c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800176f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800177a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800177a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800176c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001772d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001773e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017753`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017778`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001779a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800176c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001772d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001773e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017753`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017778`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001779a`

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
0x1800175e8  push    rbp
0x1800175ea  push    rbx
0x1800175eb  push    rsi
0x1800175ec  push    rdi
0x1800175ed  push    r14
0x1800175ef  push    r15
0x1800175f1  lea     rbp, [rsp-158h]
0x1800175f9  sub     rsp, 258h
0x180017600  mov     rax, cs:__security_cookie
0x180017607  xor     rax, rsp
0x18001760a  mov     [rbp+180h+var_40], rax
0x180017611  xor     r15d, r15d
0x180017614  lea     rax, [rsp+280h+Name]
0x180017619  mov     [r8], r15
0x18001761c  mov     r14, r8
0x18001761f  mov     edx, 104h
0x180017624  mov     r9d, 7FFFFFFEh
0x18001762a  test    r9, r9
0x18001762d  jz      short loc_18001764E
0x18001762f  movzx   r8d, word ptr [rcx]
0x180017633  test    r8w, r8w
0x180017637  jz      short loc_18001764E
0x180017639  mov     [rax], r8w
0x18001763d  add     rcx, 2
0x180017641  add     rax, 2
0x180017645  dec     r9
0x180017648  sub     rdx, 1; unsigned __int64
0x18001764c  jnz     short loc_18001762A
0x18001764e  test    rdx, rdx
0x180017651  lea     rcx, [rax-2]
0x180017655  lea     r8, aP0; "_p0"
0x18001765c  cmovnz  rcx, rax
0x180017660  mov     [rcx], r15w
0x180017664  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180017669  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001766e  mov     esi, 1F0003h
0x180017673  lea     r8, [rsp+280h+Name]; lpName
0x180017678  mov     ecx, esi; dwDesiredAccess
0x18001767a  xor     edx, edx; bInheritHandle
0x18001767c  call    cs:__imp_OpenSemaphoreW
0x180017682  mov     rbx, rax
0x180017685  test    rax, rax
0x180017688  jz      loc_1800177A9
0x18001768e  lea     rdx, [rsp+280h+var_25C]; int *
0x180017693  mov     [rsp+280h+var_25C], r15d
0x180017698  mov     rcx, rax; hHandle
0x18001769b  mov     [rsp+280h+var_260], r15d; int
0x1800176a0  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800176a5  mov     edi, eax
0x1800176a7  test    eax, eax
0x1800176a9  jns     short loc_1800176D7
0x1800176ab  mov     rcx, [rbp+188h]; this
0x1800176b2  mov     r9d, eax; char *
0x1800176b5  mov     edx, 0D6h; void *
0x1800176ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800176bf  mov     rcx, rbx; hObject
0x1800176c2  call    cs:__imp_CloseHandle
0x1800176c8  test    eax, eax
0x1800176ca  jz      loc_18001781E
0x1800176d0  mov     eax, edi
0x1800176d2  jmp     loc_1800177C9
0x1800176d7  lea     r8, asc_180025128; "h"
0x1800176de  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800176e3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800176e8  lea     r8, [rsp+280h+Name]; lpName
0x1800176ed  xor     edx, edx; bInheritHandle
0x1800176ef  mov     ecx, esi; dwDesiredAccess
0x1800176f1  call    cs:__imp_OpenSemaphoreW
0x1800176f7  mov     rdi, rax
0x1800176fa  test    rax, rax
0x1800176fd  jz      loc_180017784
0x180017703  lea     rdx, [rsp+280h+var_260]; int *
0x180017708  mov     rcx, rax; hHandle
0x18001770b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180017710  mov     esi, eax
0x180017712  test    eax, eax
0x180017714  jns     short loc_180017750
0x180017716  mov     rcx, [rbp+188h]; this
0x18001771d  mov     r9d, eax; char *
0x180017720  mov     edx, 0DEh; void *
0x180017725  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001772a  mov     rcx, rdi; hObject
0x18001772d  call    cs:__imp_CloseHandle
0x180017733  test    eax, eax
0x180017735  jz      loc_180017830
0x18001773b  mov     rcx, rbx; hObject
0x18001773e  call    cs:__imp_CloseHandle
0x180017744  test    eax, eax
0x180017746  jz      loc_180017842
0x18001774c  mov     eax, esi
0x18001774e  jmp     short loc_1800177C9
0x180017750  mov     rcx, rdi; hObject
0x180017753  call    cs:__imp_CloseHandle
0x180017759  test    eax, eax
0x18001775b  jz      loc_1800177E8
0x180017761  movsxd  rax, [rsp+280h+var_25C]
0x180017766  movsxd  rcx, [rsp+280h+var_260]
0x18001776b  shl     rcx, 1Fh
0x18001776f  or      rcx, rax
0x180017772  mov     [r14], rcx
0x180017775  mov     rcx, rbx; hObject
0x180017778  call    cs:__imp_CloseHandle
0x18001777e  test    eax, eax
0x180017780  jz      short loc_1800177FA
0x180017782  jmp     short loc_1800177B4
0x180017784  mov     rcx, [rbp+188h]; this
0x18001778b  mov     edx, 0DCh; void *
0x180017790  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180017795  mov     rcx, rbx; hObject
0x180017798  mov     edi, eax
0x18001779a  call    cs:__imp_CloseHandle
0x1800177a0  test    eax, eax
0x1800177a2  jz      short loc_18001780C
0x1800177a4  jmp     loc_1800176D0
0x1800177a9  call    cs:__imp_GetLastError
0x1800177af  cmp     eax, 2
0x1800177b2  jnz     short loc_1800177B8
0x1800177b4  xor     eax, eax
0x1800177b6  jmp     short loc_1800177C9
0x1800177b8  mov     rcx, [rbp+188h]; this
0x1800177bf  mov     edx, 0D0h; void *
0x1800177c4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800177c9  mov     rcx, [rbp+180h+var_40]
0x1800177d0  xor     rcx, rsp; StackCookie
0x1800177d3  call    __security_check_cookie
0x1800177d8  add     rsp, 258h
0x1800177df  pop     r15
0x1800177e1  pop     r14
0x1800177e3  pop     rdi
0x1800177e4  pop     rsi
0x1800177e5  pop     rbx
0x1800177e6  pop     rbp
0x1800177e7  retn
0x1800177e8  mov     rcx, [rbp+188h]; this
0x1800177ef  mov     edx, 0A0Bh; void *
0x1800177f4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800177fa  mov     rcx, [rbp+188h]; this
0x180017801  mov     edx, 0A0Bh; void *
0x180017806  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001780c  mov     rcx, [rbp+188h]; this
0x180017813  mov     edx, 0A0Bh; void *
0x180017818  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001781e  mov     rcx, [rbp+188h]; this
0x180017825  mov     edx, 0A0Bh; void *
0x18001782a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180017830  mov     rcx, [rbp+188h]; this
0x180017837  mov     edx, 0A0Bh; void *
0x18001783c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180017842  mov     rcx, [rbp+188h]; this
0x180017849  mov     edx, 0A0Bh; void *
0x18001784e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
