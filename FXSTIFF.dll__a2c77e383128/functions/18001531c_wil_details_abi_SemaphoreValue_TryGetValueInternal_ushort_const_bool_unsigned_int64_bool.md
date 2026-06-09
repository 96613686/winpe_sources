# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18001531c`
- end: `0x180015598`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `636`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180010f58`
- `0x180011324`

## callees

- `0x1800127c4`
- `0x180014644`
- `0x180014664`
- `0x180014eec`
- `0x18001531c`
- `0x180015b6c`
- `0x180017c00`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x1800153b0`
- `KERNEL32!OpenSemaphoreW` at `0x180015432`
- `KERNEL32!OpenSemaphoreW` at `0x1800153b0`
- `KERNEL32!OpenSemaphoreW` at `0x180015432`
- `KERNEL32!GetLastError` at `0x180015516`
- `KERNEL32!GetLastError` at `0x180015516`
- `KERNEL32!CloseHandle` at `0x1800153fc`
- `KERNEL32!CloseHandle` at `0x180015474`
- `KERNEL32!CloseHandle` at `0x18001548c`
- `KERNEL32!CloseHandle` at `0x1800154ab`
- `KERNEL32!CloseHandle` at `0x1800154d7`
- `KERNEL32!CloseHandle` at `0x180015500`
- `KERNEL32!CloseHandle` at `0x1800153fc`
- `KERNEL32!CloseHandle` at `0x180015474`
- `KERNEL32!CloseHandle` at `0x18001548c`
- `KERNEL32!CloseHandle` at `0x1800154ab`
- `KERNEL32!CloseHandle` at `0x1800154d7`
- `KERNEL32!CloseHandle` at `0x180015500`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned __int64 v5; // rdx
  __int64 v6; // r9
  WCHAR *v7; // rax
  WCHAR v8; // r8
  WCHAR *v9; // rcx
  HANDLE v10; // rax
  void *v11; // rbx
  int ValueFromSemaphore; // eax
  unsigned __int64 v13; // rdx
  int v14; // r8d
  unsigned int LastError; // edi
  __int64 v16; // r8
  const char *v17; // r9
  HANDLE v19; // rax
  unsigned int v20; // r8d
  const char *v21; // r9
  void *v22; // rdi
  int v23; // eax
  int v24; // r8d
  unsigned int v25; // esi
  __int64 v26; // r8
  const char *v27; // r9
  __int64 v28; // r8
  const char *v29; // r9
  __int64 v30; // r8
  const char *v31; // r9
  __int64 v32; // r8
  const char *v33; // r9
  __int64 v34; // r8
  const char *v35; // r9
  unsigned int v36; // r8d
  const char *v37; // r9
  int v38; // [rsp+20h] [rbp-E0h] BYREF
  int v39; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v40; // [rsp+28h] [rbp-D8h]
  HANDLE v41; // [rsp+30h] [rbp-D0h]
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  *a3 = 0;
  v5 = 260;
  v6 = 2147483646;
  v7 = Name;
  do
  {
    if ( !v6 )
      break;
    v8 = *a1;
    if ( !*a1 )
      break;
    ++a1;
    *v7++ = v8;
    --v6;
    --v5;
  }
  while ( v5 );
  v9 = v7 - 1;
  if ( v5 )
    v9 = v7;
  *v9 = 0;
  StringCchCatW(Name, v5, L"_p0");
  v10 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v11 = v10;
  v40 = v10;
  if ( !v10 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v36, v37);
    return 0;
  }
  v39 = 0;
  v38 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, &v39);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v14, (const char *)(unsigned int)ValueFromSemaphore);
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v16, v17);
    return LastError;
  }
  StringCchCatW(Name, v13, L"h");
  v19 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v22 = v19;
  v41 = v19;
  if ( !v19 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v20, v21);
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v34, v35);
    return LastError;
  }
  v23 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v19, &v38);
  v25 = v23;
  if ( v23 >= 0 )
  {
    if ( !CloseHandle(v22) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    *a3 = v39 | (unsigned __int64)((__int64)v38 << 31);
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v24, (const char *)(unsigned int)v23);
  if ( !CloseHandle(v22) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
  if ( !CloseHandle(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
  return v25;
}

```

## disassembly

```asm
0x18001531c  push    rbp
0x18001531e  push    rbx
0x18001531f  push    rsi
0x180015320  push    rdi
0x180015321  push    r14
0x180015323  push    r15
0x180015325  lea     rbp, [rsp-168h]
0x18001532d  sub     rsp, 268h
0x180015334  mov     rax, cs:__security_cookie
0x18001533b  xor     rax, rsp
0x18001533e  mov     [rbp+190h+var_40], rax
0x180015345  mov     r14, r8
0x180015348  xor     r15d, r15d
0x18001534b  mov     [r8], r15
0x18001534e  mov     edx, 104h
0x180015353  mov     r9d, 7FFFFFFEh
0x180015359  lea     rax, [rsp+290h+Name]
0x18001535e  test    r9, r9
0x180015361  jz      short loc_180015382
0x180015363  movzx   r8d, word ptr [rcx]
0x180015367  test    r8w, r8w
0x18001536b  jz      short loc_180015382
0x18001536d  add     rcx, 2
0x180015371  mov     [rax], r8w
0x180015375  add     rax, 2
0x180015379  dec     r9
0x18001537c  sub     rdx, 1; unsigned __int64
0x180015380  jnz     short loc_18001535E
0x180015382  lea     rcx, [rax-2]
0x180015386  test    rdx, rdx
0x180015389  cmovnz  rcx, rax
0x18001538d  mov     [rcx], r15w
0x180015391  lea     r8, aP0; "_p0"
0x180015398  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x18001539d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800153a2  lea     r8, [rsp+290h+Name]; lpName
0x1800153a7  xor     edx, edx; bInheritHandle
0x1800153a9  mov     esi, 1F0003h
0x1800153ae  mov     ecx, esi; dwDesiredAccess
0x1800153b0  call    cs:__imp_OpenSemaphoreW
0x1800153b6  mov     rbx, rax
0x1800153b9  mov     [rsp+290h+var_268], rax
0x1800153be  test    rax, rax
0x1800153c1  jz      loc_180015516
0x1800153c7  mov     [rsp+290h+var_26C], r15d
0x1800153cc  mov     [rsp+290h+var_270], r15d; int
0x1800153d1  lea     rdx, [rsp+290h+var_26C]; int *
0x1800153d6  mov     rcx, rax; hHandle
0x1800153d9  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800153de  mov     edi, eax
0x1800153e0  test    eax, eax
0x1800153e2  jns     short loc_180015418
0x1800153e4  mov     rcx, [rbp+198h]; this
0x1800153eb  mov     r9d, eax; char *
0x1800153ee  mov     edx, 0D6h; void *
0x1800153f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800153f8  nop
0x1800153f9  mov     rcx, rbx; hObject
0x1800153fc  call    cs:__imp_CloseHandle
0x180015402  mov     rcx, [rbp+198h]; this
0x180015409  test    eax, eax
0x18001540b  jz      loc_18001556C
0x180015411  mov     eax, edi
0x180015413  jmp     loc_180015537
0x180015418  lea     r8, asc_18006CC40; "h"
0x18001541f  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x180015424  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180015429  lea     r8, [rsp+290h+Name]; lpName
0x18001542e  xor     edx, edx; bInheritHandle
0x180015430  mov     ecx, esi; dwDesiredAccess
0x180015432  call    cs:__imp_OpenSemaphoreW
0x180015438  mov     rdi, rax
0x18001543b  mov     [rsp+290h+var_260], rax
0x180015440  test    rax, rax
0x180015443  jz      loc_1800154EA
0x180015449  lea     rdx, [rsp+290h+var_270]; int *
0x18001544e  mov     rcx, rax; hHandle
0x180015451  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180015456  mov     esi, eax
0x180015458  test    eax, eax
0x18001545a  jns     short loc_1800154A8
0x18001545c  mov     rcx, [rbp+198h]; this
0x180015463  mov     r9d, eax; char *
0x180015466  mov     edx, 0DEh; void *
0x18001546b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015470  nop
0x180015471  mov     rcx, rdi; hObject
0x180015474  call    cs:__imp_CloseHandle
0x18001547a  mov     rcx, [rbp+198h]; this
0x180015481  test    eax, eax
0x180015483  jz      loc_180015577
0x180015489  mov     rcx, rbx; hObject
0x18001548c  call    cs:__imp_CloseHandle
0x180015492  mov     rcx, [rbp+198h]; this
0x180015499  test    eax, eax
0x18001549b  jz      loc_180015582
0x1800154a1  mov     eax, esi
0x1800154a3  jmp     loc_180015537
0x1800154a8  mov     rcx, rdi; hObject
0x1800154ab  call    cs:__imp_CloseHandle
0x1800154b1  mov     rcx, [rbp+198h]; this
0x1800154b8  test    eax, eax
0x1800154ba  jz      loc_18001558D
0x1800154c0  movsxd  rcx, [rsp+290h+var_270]
0x1800154c5  shl     rcx, 1Fh
0x1800154c9  movsxd  rax, [rsp+290h+var_26C]
0x1800154ce  or      rcx, rax
0x1800154d1  mov     [r14], rcx
0x1800154d4  mov     rcx, rbx; hObject
0x1800154d7  call    cs:__imp_CloseHandle
0x1800154dd  mov     rcx, [rbp+198h]; this
0x1800154e4  test    eax, eax
0x1800154e6  jz      short loc_180015561
0x1800154e8  jmp     short loc_180015521
0x1800154ea  mov     rcx, [rbp+198h]; this
0x1800154f1  mov     edx, 0DCh; void *
0x1800154f6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800154fb  mov     edi, eax
0x1800154fd  mov     rcx, rbx; hObject
0x180015500  call    cs:__imp_CloseHandle
0x180015506  mov     rcx, [rbp+198h]; this
0x18001550d  test    eax, eax
0x18001550f  jz      short loc_180015556
0x180015511  jmp     loc_180015411
0x180015516  call    cs:__imp_GetLastError
0x18001551c  cmp     eax, 2
0x18001551f  jnz     short loc_180015525
0x180015521  xor     eax, eax
0x180015523  jmp     short loc_180015537
0x180015525  mov     rcx, [rbp+198h]; this
0x18001552c  mov     edx, 0D0h; void *
0x180015531  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180015536  nop
0x180015537  mov     rcx, [rbp+190h+var_40]
0x18001553e  xor     rcx, rsp; StackCookie
0x180015541  call    __security_check_cookie
0x180015546  add     rsp, 268h
0x18001554d  pop     r15
0x18001554f  pop     r14
0x180015551  pop     rdi
0x180015552  pop     rsi
0x180015553  pop     rbx
0x180015554  pop     rbp
0x180015555  retn
0x180015556  mov     edx, 0A0Bh; void *
0x18001555b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180015561  mov     edx, 0A0Bh; void *
0x180015566  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001556c  mov     edx, 0A0Bh; void *
0x180015571  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180015577  mov     edx, 0A0Bh; void *
0x18001557c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180015582  mov     edx, 0A0Bh; void *
0x180015587  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001558d  mov     edx, 0A0Bh; void *
0x180015592  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
