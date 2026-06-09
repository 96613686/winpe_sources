# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000941c`
- end: `0x180009696`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180004b58`

## callees

- `0x180002e70`
- `0x180006ac4`
- `0x180008904`
- `0x180008924`
- `0x1800092b4`
- `0x18000941c`
- `0x180009ad4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800094b0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000952c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800094b0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000952c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800094fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000956f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009580`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009595`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800095ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800095dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800094fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000956f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009580`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009595`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800095ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800095dc`

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
0x18000941c  push    rbp
0x18000941e  push    rbx
0x18000941f  push    rsi
0x180009420  push    rdi
0x180009421  push    r14
0x180009423  push    r15
0x180009425  lea     rbp, [rsp-158h]
0x18000942d  sub     rsp, 258h
0x180009434  mov     rax, cs:__security_cookie
0x18000943b  xor     rax, rsp
0x18000943e  mov     [rbp+180h+var_40], rax
0x180009445  xor     r15d, r15d
0x180009448  lea     rax, [rsp+280h+Name]
0x18000944d  mov     [r8], r15
0x180009450  mov     r14, r8
0x180009453  mov     edx, 104h
0x180009458  mov     r9d, 7FFFFFFEh
0x18000945e  test    r9, r9
0x180009461  jz      short loc_180009482
0x180009463  movzx   r8d, word ptr [rcx]
0x180009467  test    r8w, r8w
0x18000946b  jz      short loc_180009482
0x18000946d  mov     [rax], r8w
0x180009471  add     rcx, 2
0x180009475  add     rax, 2
0x180009479  dec     r9
0x18000947c  sub     rdx, 1; unsigned __int64
0x180009480  jnz     short loc_18000945E
0x180009482  test    rdx, rdx
0x180009485  lea     rcx, [rax-2]
0x180009489  lea     r8, aP0; "_p0"
0x180009490  cmovnz  rcx, rax
0x180009494  mov     [rcx], r15w
0x180009498  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000949d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800094a2  mov     esi, 1F0003h
0x1800094a7  lea     r8, [rsp+280h+Name]; lpName
0x1800094ac  mov     ecx, esi; dwDesiredAccess
0x1800094ae  xor     edx, edx; bInheritHandle
0x1800094b0  call    cs:__imp_OpenSemaphoreW
0x1800094b6  mov     rbx, rax
0x1800094b9  test    rax, rax
0x1800094bc  jz      loc_1800095EB
0x1800094c2  lea     rdx, [rsp+280h+var_25C]; int *
0x1800094c7  mov     [rsp+280h+var_25C], r15d
0x1800094cc  mov     rcx, rax; hHandle
0x1800094cf  mov     [rsp+280h+var_260], r15d; int
0x1800094d4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800094d9  mov     edi, eax
0x1800094db  test    eax, eax
0x1800094dd  jns     short loc_180009512
0x1800094df  mov     rcx, [rbp+188h]; this
0x1800094e6  lea     r8, aWil; "wil"
0x1800094ed  mov     r9d, eax; char *
0x1800094f0  mov     edx, 0D6h; void *
0x1800094f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800094fa  mov     rcx, rbx; hObject
0x1800094fd  call    cs:__imp_CloseHandle
0x180009503  test    eax, eax
0x180009505  jz      loc_180009660
0x18000950b  mov     eax, edi
0x18000950d  jmp     loc_18000960B
0x180009512  lea     r8, asc_180015510; "h"
0x180009519  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000951e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009523  lea     r8, [rsp+280h+Name]; lpName
0x180009528  xor     edx, edx; bInheritHandle
0x18000952a  mov     ecx, esi; dwDesiredAccess
0x18000952c  call    cs:__imp_OpenSemaphoreW
0x180009532  mov     rdi, rax
0x180009535  test    rax, rax
0x180009538  jz      loc_1800095C6
0x18000953e  lea     rdx, [rsp+280h+var_260]; int *
0x180009543  mov     rcx, rax; hHandle
0x180009546  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000954b  mov     esi, eax
0x18000954d  test    eax, eax
0x18000954f  jns     short loc_180009592
0x180009551  mov     rcx, [rbp+188h]; this
0x180009558  lea     r8, aWil; "wil"
0x18000955f  mov     r9d, eax; char *
0x180009562  mov     edx, 0DEh; void *
0x180009567  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000956c  mov     rcx, rdi; hObject
0x18000956f  call    cs:__imp_CloseHandle
0x180009575  test    eax, eax
0x180009577  jz      loc_180009672
0x18000957d  mov     rcx, rbx; hObject
0x180009580  call    cs:__imp_CloseHandle
0x180009586  test    eax, eax
0x180009588  jz      loc_180009684
0x18000958e  mov     eax, esi
0x180009590  jmp     short loc_18000960B
0x180009592  mov     rcx, rdi; hObject
0x180009595  call    cs:__imp_CloseHandle
0x18000959b  test    eax, eax
0x18000959d  jz      loc_18000962A
0x1800095a3  movsxd  rax, [rsp+280h+var_25C]
0x1800095a8  movsxd  rcx, [rsp+280h+var_260]
0x1800095ad  shl     rcx, 1Fh
0x1800095b1  or      rcx, rax
0x1800095b4  mov     [r14], rcx
0x1800095b7  mov     rcx, rbx; hObject
0x1800095ba  call    cs:__imp_CloseHandle
0x1800095c0  test    eax, eax
0x1800095c2  jz      short loc_18000963C
0x1800095c4  jmp     short loc_1800095F6
0x1800095c6  mov     rcx, [rbp+188h]; this
0x1800095cd  mov     edx, 0DCh; void *
0x1800095d2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800095d7  mov     rcx, rbx; hObject
0x1800095da  mov     edi, eax
0x1800095dc  call    cs:__imp_CloseHandle
0x1800095e2  test    eax, eax
0x1800095e4  jz      short loc_18000964E
0x1800095e6  jmp     loc_18000950B
0x1800095eb  call    cs:__imp_GetLastError
0x1800095f1  cmp     eax, 2
0x1800095f4  jnz     short loc_1800095FA
0x1800095f6  xor     eax, eax
0x1800095f8  jmp     short loc_18000960B
0x1800095fa  mov     rcx, [rbp+188h]; this
0x180009601  mov     edx, 0D0h; void *
0x180009606  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000960b  mov     rcx, [rbp+180h+var_40]
0x180009612  xor     rcx, rsp; StackCookie
0x180009615  call    __security_check_cookie
0x18000961a  add     rsp, 258h
0x180009621  pop     r15
0x180009623  pop     r14
0x180009625  pop     rdi
0x180009626  pop     rsi
0x180009627  pop     rbx
0x180009628  pop     rbp
0x180009629  retn
0x18000962a  mov     rcx, [rbp+188h]; this
0x180009631  mov     edx, 0A0Bh; void *
0x180009636  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000963c  mov     rcx, [rbp+188h]; this
0x180009643  mov     edx, 0A0Bh; void *
0x180009648  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000964e  mov     rcx, [rbp+188h]; this
0x180009655  mov     edx, 0A0Bh; void *
0x18000965a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009660  mov     rcx, [rbp+188h]; this
0x180009667  mov     edx, 0A0Bh; void *
0x18000966c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009672  mov     rcx, [rbp+188h]; this
0x180009679  mov     edx, 0A0Bh; void *
0x18000967e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009684  mov     rcx, [rbp+188h]; this
0x18000968b  mov     edx, 0A0Bh; void *
0x180009690  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
