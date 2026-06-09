# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800061bc`
- end: `0x180006428`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003c14`

## callees

- `0x180001c80`
- `0x180004b64`
- `0x180005754`
- `0x180005774`
- `0x180006050`
- `0x1800061bc`
- `0x18000657c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006250`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800062c5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006250`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800062c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000637d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000637d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006296`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006301`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006312`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006327`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000634c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000636e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006296`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006301`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006312`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006327`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000634c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000636e`

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
0x1800061bc  push    rbp
0x1800061be  push    rbx
0x1800061bf  push    rsi
0x1800061c0  push    rdi
0x1800061c1  push    r14
0x1800061c3  push    r15
0x1800061c5  lea     rbp, [rsp-158h]
0x1800061cd  sub     rsp, 258h
0x1800061d4  mov     rax, cs:__security_cookie
0x1800061db  xor     rax, rsp
0x1800061de  mov     [rbp+180h+var_40], rax
0x1800061e5  xor     r15d, r15d
0x1800061e8  lea     rax, [rsp+280h+Name]
0x1800061ed  mov     [r8], r15
0x1800061f0  mov     r14, r8
0x1800061f3  mov     edx, 104h
0x1800061f8  mov     r9d, 7FFFFFFEh
0x1800061fe  test    r9, r9
0x180006201  jz      short loc_180006222
0x180006203  movzx   r8d, word ptr [rcx]
0x180006207  test    r8w, r8w
0x18000620b  jz      short loc_180006222
0x18000620d  mov     [rax], r8w
0x180006211  add     rcx, 2
0x180006215  add     rax, 2
0x180006219  dec     r9
0x18000621c  sub     rdx, 1; unsigned __int64
0x180006220  jnz     short loc_1800061FE
0x180006222  test    rdx, rdx
0x180006225  lea     rcx, [rax-2]
0x180006229  lea     r8, aP0; "_p0"
0x180006230  cmovnz  rcx, rax
0x180006234  mov     [rcx], r15w
0x180006238  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000623d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006242  mov     esi, 1F0003h
0x180006247  lea     r8, [rsp+280h+Name]; lpName
0x18000624c  mov     ecx, esi; dwDesiredAccess
0x18000624e  xor     edx, edx; bInheritHandle
0x180006250  call    cs:__imp_OpenSemaphoreW
0x180006256  mov     rbx, rax
0x180006259  test    rax, rax
0x18000625c  jz      loc_18000637D
0x180006262  lea     rdx, [rsp+280h+var_25C]; int *
0x180006267  mov     [rsp+280h+var_25C], r15d
0x18000626c  mov     rcx, rax; hHandle
0x18000626f  mov     [rsp+280h+var_260], r15d; int
0x180006274  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006279  mov     edi, eax
0x18000627b  test    eax, eax
0x18000627d  jns     short loc_1800062AB
0x18000627f  mov     rcx, [rbp+188h]; this
0x180006286  mov     r9d, eax; char *
0x180006289  mov     edx, 0D6h; void *
0x18000628e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006293  mov     rcx, rbx; hObject
0x180006296  call    cs:__imp_CloseHandle
0x18000629c  test    eax, eax
0x18000629e  jz      loc_1800063F2
0x1800062a4  mov     eax, edi
0x1800062a6  jmp     loc_18000639D
0x1800062ab  lea     r8, asc_180012048; "h"
0x1800062b2  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800062b7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800062bc  lea     r8, [rsp+280h+Name]; lpName
0x1800062c1  xor     edx, edx; bInheritHandle
0x1800062c3  mov     ecx, esi; dwDesiredAccess
0x1800062c5  call    cs:__imp_OpenSemaphoreW
0x1800062cb  mov     rdi, rax
0x1800062ce  test    rax, rax
0x1800062d1  jz      loc_180006358
0x1800062d7  lea     rdx, [rsp+280h+var_260]; int *
0x1800062dc  mov     rcx, rax; hHandle
0x1800062df  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800062e4  mov     esi, eax
0x1800062e6  test    eax, eax
0x1800062e8  jns     short loc_180006324
0x1800062ea  mov     rcx, [rbp+188h]; this
0x1800062f1  mov     r9d, eax; char *
0x1800062f4  mov     edx, 0DEh; void *
0x1800062f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800062fe  mov     rcx, rdi; hObject
0x180006301  call    cs:__imp_CloseHandle
0x180006307  test    eax, eax
0x180006309  jz      loc_180006404
0x18000630f  mov     rcx, rbx; hObject
0x180006312  call    cs:__imp_CloseHandle
0x180006318  test    eax, eax
0x18000631a  jz      loc_180006416
0x180006320  mov     eax, esi
0x180006322  jmp     short loc_18000639D
0x180006324  mov     rcx, rdi; hObject
0x180006327  call    cs:__imp_CloseHandle
0x18000632d  test    eax, eax
0x18000632f  jz      loc_1800063BC
0x180006335  movsxd  rax, [rsp+280h+var_25C]
0x18000633a  movsxd  rcx, [rsp+280h+var_260]
0x18000633f  shl     rcx, 1Fh
0x180006343  or      rcx, rax
0x180006346  mov     [r14], rcx
0x180006349  mov     rcx, rbx; hObject
0x18000634c  call    cs:__imp_CloseHandle
0x180006352  test    eax, eax
0x180006354  jz      short loc_1800063CE
0x180006356  jmp     short loc_180006388
0x180006358  mov     rcx, [rbp+188h]; this
0x18000635f  mov     edx, 0DCh; void *
0x180006364  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006369  mov     rcx, rbx; hObject
0x18000636c  mov     edi, eax
0x18000636e  call    cs:__imp_CloseHandle
0x180006374  test    eax, eax
0x180006376  jz      short loc_1800063E0
0x180006378  jmp     loc_1800062A4
0x18000637d  call    cs:__imp_GetLastError
0x180006383  cmp     eax, 2
0x180006386  jnz     short loc_18000638C
0x180006388  xor     eax, eax
0x18000638a  jmp     short loc_18000639D
0x18000638c  mov     rcx, [rbp+188h]; this
0x180006393  mov     edx, 0D0h; void *
0x180006398  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000639d  mov     rcx, [rbp+180h+var_40]
0x1800063a4  xor     rcx, rsp; StackCookie
0x1800063a7  call    __security_check_cookie
0x1800063ac  add     rsp, 258h
0x1800063b3  pop     r15
0x1800063b5  pop     r14
0x1800063b7  pop     rdi
0x1800063b8  pop     rsi
0x1800063b9  pop     rbx
0x1800063ba  pop     rbp
0x1800063bb  retn
0x1800063bc  mov     rcx, [rbp+188h]; this
0x1800063c3  mov     edx, 0A0Bh; void *
0x1800063c8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800063ce  mov     rcx, [rbp+188h]; this
0x1800063d5  mov     edx, 0A0Bh; void *
0x1800063da  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800063e0  mov     rcx, [rbp+188h]; this
0x1800063e7  mov     edx, 0A0Bh; void *
0x1800063ec  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800063f2  mov     rcx, [rbp+188h]; this
0x1800063f9  mov     edx, 0A0Bh; void *
0x1800063fe  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006404  mov     rcx, [rbp+188h]; this
0x18000640b  mov     edx, 0A0Bh; void *
0x180006410  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006416  mov     rcx, [rbp+188h]; this
0x18000641d  mov     edx, 0A0Bh; void *
0x180006422  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
