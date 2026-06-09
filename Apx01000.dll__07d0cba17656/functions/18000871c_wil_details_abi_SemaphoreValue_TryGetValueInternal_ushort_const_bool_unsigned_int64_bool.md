# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000871c`
- end: `0x180008988`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003f58`
- `0x1800042fc`

## callees

- `0x180001d30`
- `0x180005844`
- `0x1800077a4`
- `0x1800077c4`
- `0x180008208`
- `0x18000871c`
- `0x180008fdc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800087b0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008825`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800087b0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008825`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800088dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800088dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800087f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008861`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008872`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008887`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800088ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800088ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800087f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008861`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008872`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008887`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800088ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800088ce`

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
  int v13; // r8d
  unsigned int LastError; // edi
  __int64 v15; // r8
  const char *v16; // r9
  HANDLE v18; // rax
  unsigned int v19; // r8d
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
0x18000871c  push    rbp
0x18000871e  push    rbx
0x18000871f  push    rsi
0x180008720  push    rdi
0x180008721  push    r14
0x180008723  push    r15
0x180008725  lea     rbp, [rsp-158h]
0x18000872d  sub     rsp, 258h
0x180008734  mov     rax, cs:__security_cookie
0x18000873b  xor     rax, rsp
0x18000873e  mov     [rbp+180h+var_40], rax
0x180008745  xor     r15d, r15d
0x180008748  lea     rax, [rsp+280h+Name]
0x18000874d  mov     [r8], r15
0x180008750  mov     r14, r8
0x180008753  mov     edx, 104h
0x180008758  mov     r9d, 7FFFFFFEh
0x18000875e  test    r9, r9
0x180008761  jz      short loc_180008782
0x180008763  movzx   r8d, word ptr [rcx]
0x180008767  test    r8w, r8w
0x18000876b  jz      short loc_180008782
0x18000876d  mov     [rax], r8w
0x180008771  add     rcx, 2
0x180008775  add     rax, 2
0x180008779  dec     r9
0x18000877c  sub     rdx, 1; unsigned __int64
0x180008780  jnz     short loc_18000875E
0x180008782  test    rdx, rdx
0x180008785  lea     rcx, [rax-2]
0x180008789  lea     r8, aP0; "_p0"
0x180008790  cmovnz  rcx, rax
0x180008794  mov     [rcx], r15w
0x180008798  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000879d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800087a2  mov     esi, 1F0003h
0x1800087a7  lea     r8, [rsp+280h+Name]; lpName
0x1800087ac  mov     ecx, esi; dwDesiredAccess
0x1800087ae  xor     edx, edx; bInheritHandle
0x1800087b0  call    cs:__imp_OpenSemaphoreW
0x1800087b6  mov     rbx, rax
0x1800087b9  test    rax, rax
0x1800087bc  jz      loc_1800088DD
0x1800087c2  lea     rdx, [rsp+280h+var_25C]; int *
0x1800087c7  mov     [rsp+280h+var_25C], r15d
0x1800087cc  mov     rcx, rax; hHandle
0x1800087cf  mov     [rsp+280h+var_260], r15d; int
0x1800087d4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800087d9  mov     edi, eax
0x1800087db  test    eax, eax
0x1800087dd  jns     short loc_18000880B
0x1800087df  mov     rcx, [rbp+188h]; this
0x1800087e6  mov     r9d, eax; char *
0x1800087e9  mov     edx, 0D6h; void *
0x1800087ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800087f3  mov     rcx, rbx; hObject
0x1800087f6  call    cs:__imp_CloseHandle
0x1800087fc  test    eax, eax
0x1800087fe  jz      loc_180008952
0x180008804  mov     eax, edi
0x180008806  jmp     loc_1800088FD
0x18000880b  lea     r8, asc_18002C608; "h"
0x180008812  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008817  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000881c  lea     r8, [rsp+280h+Name]; lpName
0x180008821  xor     edx, edx; bInheritHandle
0x180008823  mov     ecx, esi; dwDesiredAccess
0x180008825  call    cs:__imp_OpenSemaphoreW
0x18000882b  mov     rdi, rax
0x18000882e  test    rax, rax
0x180008831  jz      loc_1800088B8
0x180008837  lea     rdx, [rsp+280h+var_260]; int *
0x18000883c  mov     rcx, rax; hHandle
0x18000883f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008844  mov     esi, eax
0x180008846  test    eax, eax
0x180008848  jns     short loc_180008884
0x18000884a  mov     rcx, [rbp+188h]; this
0x180008851  mov     r9d, eax; char *
0x180008854  mov     edx, 0DEh; void *
0x180008859  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000885e  mov     rcx, rdi; hObject
0x180008861  call    cs:__imp_CloseHandle
0x180008867  test    eax, eax
0x180008869  jz      loc_180008964
0x18000886f  mov     rcx, rbx; hObject
0x180008872  call    cs:__imp_CloseHandle
0x180008878  test    eax, eax
0x18000887a  jz      loc_180008976
0x180008880  mov     eax, esi
0x180008882  jmp     short loc_1800088FD
0x180008884  mov     rcx, rdi; hObject
0x180008887  call    cs:__imp_CloseHandle
0x18000888d  test    eax, eax
0x18000888f  jz      loc_18000891C
0x180008895  movsxd  rax, [rsp+280h+var_25C]
0x18000889a  movsxd  rcx, [rsp+280h+var_260]
0x18000889f  shl     rcx, 1Fh
0x1800088a3  or      rcx, rax
0x1800088a6  mov     [r14], rcx
0x1800088a9  mov     rcx, rbx; hObject
0x1800088ac  call    cs:__imp_CloseHandle
0x1800088b2  test    eax, eax
0x1800088b4  jz      short loc_18000892E
0x1800088b6  jmp     short loc_1800088E8
0x1800088b8  mov     rcx, [rbp+188h]; this
0x1800088bf  mov     edx, 0DCh; void *
0x1800088c4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800088c9  mov     rcx, rbx; hObject
0x1800088cc  mov     edi, eax
0x1800088ce  call    cs:__imp_CloseHandle
0x1800088d4  test    eax, eax
0x1800088d6  jz      short loc_180008940
0x1800088d8  jmp     loc_180008804
0x1800088dd  call    cs:__imp_GetLastError
0x1800088e3  cmp     eax, 2
0x1800088e6  jnz     short loc_1800088EC
0x1800088e8  xor     eax, eax
0x1800088ea  jmp     short loc_1800088FD
0x1800088ec  mov     rcx, [rbp+188h]; this
0x1800088f3  mov     edx, 0D0h; void *
0x1800088f8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800088fd  mov     rcx, [rbp+180h+var_40]
0x180008904  xor     rcx, rsp; StackCookie
0x180008907  call    __security_check_cookie
0x18000890c  add     rsp, 258h
0x180008913  pop     r15
0x180008915  pop     r14
0x180008917  pop     rdi
0x180008918  pop     rsi
0x180008919  pop     rbx
0x18000891a  pop     rbp
0x18000891b  retn
0x18000891c  mov     rcx, [rbp+188h]; this
0x180008923  mov     edx, 0A0Bh; void *
0x180008928  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000892e  mov     rcx, [rbp+188h]; this
0x180008935  mov     edx, 0A0Bh; void *
0x18000893a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008940  mov     rcx, [rbp+188h]; this
0x180008947  mov     edx, 0A0Bh; void *
0x18000894c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008952  mov     rcx, [rbp+188h]; this
0x180008959  mov     edx, 0A0Bh; void *
0x18000895e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008964  mov     rcx, [rbp+188h]; this
0x18000896b  mov     edx, 0A0Bh; void *
0x180008970  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008976  mov     rcx, [rbp+188h]; this
0x18000897d  mov     edx, 0A0Bh; void *
0x180008982  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
