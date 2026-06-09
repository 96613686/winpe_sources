# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000513c`
- end: `0x1800053a8`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180002d18`

## callees

- `0x180001590`
- `0x180003c54`
- `0x1800046b4`
- `0x1800046d4`
- `0x180004fb0`
- `0x18000513c`
- `0x1800054fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800051d0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005245`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800051d0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005245`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005216`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005281`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005292`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005216`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005281`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005292`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052ee`

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
0x18000513c  push    rbp
0x18000513e  push    rbx
0x18000513f  push    rsi
0x180005140  push    rdi
0x180005141  push    r14
0x180005143  push    r15
0x180005145  lea     rbp, [rsp-158h]
0x18000514d  sub     rsp, 258h
0x180005154  mov     rax, cs:__security_cookie
0x18000515b  xor     rax, rsp
0x18000515e  mov     [rbp+180h+var_40], rax
0x180005165  xor     r15d, r15d
0x180005168  lea     rax, [rsp+280h+Name]
0x18000516d  mov     [r8], r15
0x180005170  mov     r14, r8
0x180005173  mov     edx, 104h
0x180005178  mov     r9d, 7FFFFFFEh
0x18000517e  test    r9, r9
0x180005181  jz      short loc_1800051A2
0x180005183  movzx   r8d, word ptr [rcx]
0x180005187  test    r8w, r8w
0x18000518b  jz      short loc_1800051A2
0x18000518d  mov     [rax], r8w
0x180005191  add     rcx, 2
0x180005195  add     rax, 2
0x180005199  dec     r9
0x18000519c  sub     rdx, 1; unsigned __int64
0x1800051a0  jnz     short loc_18000517E
0x1800051a2  test    rdx, rdx
0x1800051a5  lea     rcx, [rax-2]
0x1800051a9  lea     r8, aP0; "_p0"
0x1800051b0  cmovnz  rcx, rax
0x1800051b4  mov     [rcx], r15w
0x1800051b8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800051bd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800051c2  mov     esi, 1F0003h
0x1800051c7  lea     r8, [rsp+280h+Name]; lpName
0x1800051cc  mov     ecx, esi; dwDesiredAccess
0x1800051ce  xor     edx, edx; bInheritHandle
0x1800051d0  call    cs:__imp_OpenSemaphoreW
0x1800051d6  mov     rbx, rax
0x1800051d9  test    rax, rax
0x1800051dc  jz      loc_1800052FD
0x1800051e2  lea     rdx, [rsp+280h+var_25C]; int *
0x1800051e7  mov     [rsp+280h+var_25C], r15d
0x1800051ec  mov     rcx, rax; hHandle
0x1800051ef  mov     [rsp+280h+var_260], r15d; int
0x1800051f4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800051f9  mov     edi, eax
0x1800051fb  test    eax, eax
0x1800051fd  jns     short loc_18000522B
0x1800051ff  mov     rcx, [rbp+188h]; this
0x180005206  mov     r9d, eax; char *
0x180005209  mov     edx, 0D6h; void *
0x18000520e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005213  mov     rcx, rbx; hObject
0x180005216  call    cs:__imp_CloseHandle
0x18000521c  test    eax, eax
0x18000521e  jz      loc_180005372
0x180005224  mov     eax, edi
0x180005226  jmp     loc_18000531D
0x18000522b  lea     r8, asc_1800088B0; "h"
0x180005232  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005237  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000523c  lea     r8, [rsp+280h+Name]; lpName
0x180005241  xor     edx, edx; bInheritHandle
0x180005243  mov     ecx, esi; dwDesiredAccess
0x180005245  call    cs:__imp_OpenSemaphoreW
0x18000524b  mov     rdi, rax
0x18000524e  test    rax, rax
0x180005251  jz      loc_1800052D8
0x180005257  lea     rdx, [rsp+280h+var_260]; int *
0x18000525c  mov     rcx, rax; hHandle
0x18000525f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180005264  mov     esi, eax
0x180005266  test    eax, eax
0x180005268  jns     short loc_1800052A4
0x18000526a  mov     rcx, [rbp+188h]; this
0x180005271  mov     r9d, eax; char *
0x180005274  mov     edx, 0DEh; void *
0x180005279  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000527e  mov     rcx, rdi; hObject
0x180005281  call    cs:__imp_CloseHandle
0x180005287  test    eax, eax
0x180005289  jz      loc_180005384
0x18000528f  mov     rcx, rbx; hObject
0x180005292  call    cs:__imp_CloseHandle
0x180005298  test    eax, eax
0x18000529a  jz      loc_180005396
0x1800052a0  mov     eax, esi
0x1800052a2  jmp     short loc_18000531D
0x1800052a4  mov     rcx, rdi; hObject
0x1800052a7  call    cs:__imp_CloseHandle
0x1800052ad  test    eax, eax
0x1800052af  jz      loc_18000533C
0x1800052b5  movsxd  rax, [rsp+280h+var_25C]
0x1800052ba  movsxd  rcx, [rsp+280h+var_260]
0x1800052bf  shl     rcx, 1Fh
0x1800052c3  or      rcx, rax
0x1800052c6  mov     [r14], rcx
0x1800052c9  mov     rcx, rbx; hObject
0x1800052cc  call    cs:__imp_CloseHandle
0x1800052d2  test    eax, eax
0x1800052d4  jz      short loc_18000534E
0x1800052d6  jmp     short loc_180005308
0x1800052d8  mov     rcx, [rbp+188h]; this
0x1800052df  mov     edx, 0DCh; void *
0x1800052e4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800052e9  mov     rcx, rbx; hObject
0x1800052ec  mov     edi, eax
0x1800052ee  call    cs:__imp_CloseHandle
0x1800052f4  test    eax, eax
0x1800052f6  jz      short loc_180005360
0x1800052f8  jmp     loc_180005224
0x1800052fd  call    cs:__imp_GetLastError
0x180005303  cmp     eax, 2
0x180005306  jnz     short loc_18000530C
0x180005308  xor     eax, eax
0x18000530a  jmp     short loc_18000531D
0x18000530c  mov     rcx, [rbp+188h]; this
0x180005313  mov     edx, 0D0h; void *
0x180005318  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000531d  mov     rcx, [rbp+180h+var_40]
0x180005324  xor     rcx, rsp; StackCookie
0x180005327  call    __security_check_cookie
0x18000532c  add     rsp, 258h
0x180005333  pop     r15
0x180005335  pop     r14
0x180005337  pop     rdi
0x180005338  pop     rsi
0x180005339  pop     rbx
0x18000533a  pop     rbp
0x18000533b  retn
0x18000533c  mov     rcx, [rbp+188h]; this
0x180005343  mov     edx, 0A0Bh; void *
0x180005348  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000534e  mov     rcx, [rbp+188h]; this
0x180005355  mov     edx, 0A0Bh; void *
0x18000535a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005360  mov     rcx, [rbp+188h]; this
0x180005367  mov     edx, 0A0Bh; void *
0x18000536c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005372  mov     rcx, [rbp+188h]; this
0x180005379  mov     edx, 0A0Bh; void *
0x18000537e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005384  mov     rcx, [rbp+188h]; this
0x18000538b  mov     edx, 0A0Bh; void *
0x180005390  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005396  mov     rcx, [rbp+188h]; this
0x18000539d  mov     edx, 0A0Bh; void *
0x1800053a2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
