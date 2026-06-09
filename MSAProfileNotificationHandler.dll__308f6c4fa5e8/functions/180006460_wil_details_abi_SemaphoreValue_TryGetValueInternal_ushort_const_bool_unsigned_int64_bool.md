# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180006460`
- end: `0x1800066cc`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003ff8`

## callees

- `0x180001cb0`
- `0x180004f34`
- `0x180005da4`
- `0x180005dc4`
- `0x180006070`
- `0x180006460`
- `0x180006f0c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000653a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800065a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800065b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800065cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800065f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006612`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000653a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800065a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800065b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800065cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800065f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006612`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006621`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006621`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800064f4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006569`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800064f4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006569`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v6; // rdx
  __int64 v7; // r9
  WCHAR *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  __int64 v12; // rdx
  int v13; // r8d
  unsigned int LastError; // edi
  __int64 v15; // r8
  const char *v16; // r9
  HANDLE v18; // rax
  __int64 v19; // r8
  const char *v20; // r9
  void *v21; // rdi
  int v22; // eax
  int v23; // r8d
  unsigned int v24; // esi
  __int64 v25; // r8
  const char *v26; // r9
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // r9
  __int64 v35; // r8
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore);
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v23, (const char *)(unsigned int)v22);
  if ( !CloseHandle(v21) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
  return v24;
}

```

## disassembly

```asm
0x180006460  push    rbp
0x180006462  push    rbx
0x180006463  push    rsi
0x180006464  push    rdi
0x180006465  push    r14
0x180006467  push    r15
0x180006469  lea     rbp, [rsp-158h]
0x180006471  sub     rsp, 258h
0x180006478  mov     rax, cs:__security_cookie
0x18000647f  xor     rax, rsp
0x180006482  mov     [rbp+180h+var_40], rax
0x180006489  xor     r15d, r15d
0x18000648c  lea     rax, [rsp+280h+Name]
0x180006491  mov     [r8], r15
0x180006494  mov     r14, r8
0x180006497  mov     edx, 104h
0x18000649c  mov     r9d, 7FFFFFFEh
0x1800064a2  test    r9, r9
0x1800064a5  jz      short loc_1800064C6
0x1800064a7  movzx   r8d, word ptr [rcx]
0x1800064ab  test    r8w, r8w
0x1800064af  jz      short loc_1800064C6
0x1800064b1  mov     [rax], r8w
0x1800064b5  add     rcx, 2
0x1800064b9  add     rax, 2
0x1800064bd  dec     r9
0x1800064c0  sub     rdx, 1; unsigned __int64
0x1800064c4  jnz     short loc_1800064A2
0x1800064c6  test    rdx, rdx
0x1800064c9  lea     rcx, [rax-2]
0x1800064cd  lea     r8, aP0; "_p0"
0x1800064d4  cmovnz  rcx, rax
0x1800064d8  mov     [rcx], r15w
0x1800064dc  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800064e1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800064e6  mov     esi, 1F0003h
0x1800064eb  lea     r8, [rsp+280h+Name]; lpName
0x1800064f0  mov     ecx, esi; dwDesiredAccess
0x1800064f2  xor     edx, edx; bInheritHandle
0x1800064f4  call    cs:__imp_OpenSemaphoreW
0x1800064fa  mov     rbx, rax
0x1800064fd  test    rax, rax
0x180006500  jz      loc_180006621
0x180006506  lea     rdx, [rsp+280h+var_25C]; int *
0x18000650b  mov     [rsp+280h+var_25C], r15d
0x180006510  mov     rcx, rax; hHandle
0x180006513  mov     [rsp+280h+var_260], r15d; int
0x180006518  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000651d  mov     edi, eax
0x18000651f  test    eax, eax
0x180006521  jns     short loc_18000654F
0x180006523  mov     rcx, [rbp+188h]; this
0x18000652a  mov     r9d, eax; char *
0x18000652d  mov     edx, 0D6h; void *
0x180006532  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006537  mov     rcx, rbx; hObject
0x18000653a  call    cs:__imp_CloseHandle
0x180006540  test    eax, eax
0x180006542  jz      loc_180006696
0x180006548  mov     eax, edi
0x18000654a  jmp     loc_180006641
0x18000654f  lea     r8, asc_18000E088; "h"
0x180006556  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000655b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006560  lea     r8, [rsp+280h+Name]; lpName
0x180006565  xor     edx, edx; bInheritHandle
0x180006567  mov     ecx, esi; dwDesiredAccess
0x180006569  call    cs:__imp_OpenSemaphoreW
0x18000656f  mov     rdi, rax
0x180006572  test    rax, rax
0x180006575  jz      loc_1800065FC
0x18000657b  lea     rdx, [rsp+280h+var_260]; int *
0x180006580  mov     rcx, rax; hHandle
0x180006583  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006588  mov     esi, eax
0x18000658a  test    eax, eax
0x18000658c  jns     short loc_1800065C8
0x18000658e  mov     rcx, [rbp+188h]; this
0x180006595  mov     r9d, eax; char *
0x180006598  mov     edx, 0DEh; void *
0x18000659d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800065a2  mov     rcx, rdi; hObject
0x1800065a5  call    cs:__imp_CloseHandle
0x1800065ab  test    eax, eax
0x1800065ad  jz      loc_1800066A8
0x1800065b3  mov     rcx, rbx; hObject
0x1800065b6  call    cs:__imp_CloseHandle
0x1800065bc  test    eax, eax
0x1800065be  jz      loc_1800066BA
0x1800065c4  mov     eax, esi
0x1800065c6  jmp     short loc_180006641
0x1800065c8  mov     rcx, rdi; hObject
0x1800065cb  call    cs:__imp_CloseHandle
0x1800065d1  test    eax, eax
0x1800065d3  jz      loc_180006660
0x1800065d9  movsxd  rax, [rsp+280h+var_25C]
0x1800065de  movsxd  rcx, [rsp+280h+var_260]
0x1800065e3  shl     rcx, 1Fh
0x1800065e7  or      rcx, rax
0x1800065ea  mov     [r14], rcx
0x1800065ed  mov     rcx, rbx; hObject
0x1800065f0  call    cs:__imp_CloseHandle
0x1800065f6  test    eax, eax
0x1800065f8  jz      short loc_180006672
0x1800065fa  jmp     short loc_18000662C
0x1800065fc  mov     rcx, [rbp+188h]; this
0x180006603  mov     edx, 0DCh; void *
0x180006608  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000660d  mov     rcx, rbx; hObject
0x180006610  mov     edi, eax
0x180006612  call    cs:__imp_CloseHandle
0x180006618  test    eax, eax
0x18000661a  jz      short loc_180006684
0x18000661c  jmp     loc_180006548
0x180006621  call    cs:__imp_GetLastError
0x180006627  cmp     eax, 2
0x18000662a  jnz     short loc_180006630
0x18000662c  xor     eax, eax
0x18000662e  jmp     short loc_180006641
0x180006630  mov     rcx, [rbp+188h]; this
0x180006637  mov     edx, 0D0h; void *
0x18000663c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006641  mov     rcx, [rbp+180h+var_40]
0x180006648  xor     rcx, rsp; StackCookie
0x18000664b  call    __security_check_cookie
0x180006650  add     rsp, 258h
0x180006657  pop     r15
0x180006659  pop     r14
0x18000665b  pop     rdi
0x18000665c  pop     rsi
0x18000665d  pop     rbx
0x18000665e  pop     rbp
0x18000665f  retn
0x180006660  mov     rcx, [rbp+188h]; this
0x180006667  mov     edx, 0A0Bh; void *
0x18000666c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006672  mov     rcx, [rbp+188h]; this
0x180006679  mov     edx, 0A0Bh; void *
0x18000667e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006684  mov     rcx, [rbp+188h]; this
0x18000668b  mov     edx, 0A0Bh; void *
0x180006690  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006696  mov     rcx, [rbp+188h]; this
0x18000669d  mov     edx, 0A0Bh; void *
0x1800066a2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800066a8  mov     rcx, [rbp+188h]; this
0x1800066af  mov     edx, 0A0Bh; void *
0x1800066b4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800066ba  mov     rcx, [rbp+188h]; this
0x1800066c1  mov     edx, 0A0Bh; void *
0x1800066c6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
