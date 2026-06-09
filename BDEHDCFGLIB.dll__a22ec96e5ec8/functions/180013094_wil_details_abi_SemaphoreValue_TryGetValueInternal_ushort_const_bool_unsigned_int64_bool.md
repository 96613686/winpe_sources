# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180013094`
- end: `0x180013309`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `629`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800113dc`

## callees

- `0x18000990c`
- `0x180012330`
- `0x180012dc4`
- `0x180012de4`
- `0x180013094`
- `0x18001345c`
- `0x1800135c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001325e`
- `KERNEL32!GetLastError` at `0x18001325e`
- `KERNEL32!CloseHandle` at `0x180013171`
- `KERNEL32!CloseHandle` at `0x1800131e2`
- `KERNEL32!CloseHandle` at `0x1800131f3`
- `KERNEL32!CloseHandle` at `0x180013208`
- `KERNEL32!CloseHandle` at `0x18001322d`
- `KERNEL32!CloseHandle` at `0x18001324f`
- `KERNEL32!CloseHandle` at `0x180013171`
- `KERNEL32!CloseHandle` at `0x1800131e2`
- `KERNEL32!CloseHandle` at `0x1800131f3`
- `KERNEL32!CloseHandle` at `0x180013208`
- `KERNEL32!CloseHandle` at `0x18001322d`
- `KERNEL32!CloseHandle` at `0x18001324f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001312b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800131a6`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001312b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800131a6`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // rdx
  __int64 v7; // r9
  WCHAR *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  int v12; // r8d
  unsigned int LastError; // edi
  __int64 v14; // r8
  const char *v15; // r9
  HANDLE v17; // rax
  unsigned int v18; // r8d
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  int v22; // r8d
  unsigned int v23; // esi
  __int64 v24; // r8
  const char *v25; // r9
  __int64 v26; // r8
  const char *v27; // r9
  __int64 v28; // r8
  const char *v29; // r9
  __int64 v30; // r8
  const char *v31; // r9
  __int64 v32; // r8
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  int v36; // [rsp+20h] [rbp-E0h] BYREF
  int v37[3]; // [rsp+24h] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = Name;
  *a3 = 0;
  v5 = 260;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v5;
  }
  while ( v5 );
  v8 = v4 - 1;
  if ( v5 )
    v8 = v4;
  *v8 = 0;
  StringCchCatW(Name, 260, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v34, v35);
    return 0;
  }
  v37[0] = 0;
  v36 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v37);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, 260, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v18, v19);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return LastError;
  }
  v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v36);
  v23 = v21;
  if ( v21 >= 0 )
  {
    if ( !CloseHandle(v20) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    *a3 = v37[0] | (unsigned __int64)((__int64)v36 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v22, (const char *)(unsigned int)v21);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
  return v23;
}

```

## disassembly

```asm
0x180013094  push    rbp
0x180013096  push    rbx
0x180013097  push    rsi
0x180013098  push    rdi
0x180013099  push    r14
0x18001309b  push    r15
0x18001309d  lea     rbp, [rsp-158h]
0x1800130a5  sub     rsp, 258h
0x1800130ac  mov     rax, cs:__security_cookie
0x1800130b3  xor     rax, rsp
0x1800130b6  mov     [rbp+180h+var_40], rax
0x1800130bd  xor     r15d, r15d
0x1800130c0  lea     rax, [rsp+280h+Name]
0x1800130c5  mov     esi, 104h
0x1800130ca  mov     [r8], r15
0x1800130cd  mov     edx, esi
0x1800130cf  mov     r14, r8
0x1800130d2  mov     r9d, 7FFFFFFEh
0x1800130d8  test    r9, r9
0x1800130db  jz      short loc_1800130FC
0x1800130dd  movzx   r8d, word ptr [rcx]
0x1800130e1  test    r8w, r8w
0x1800130e5  jz      short loc_1800130FC
0x1800130e7  mov     [rax], r8w
0x1800130eb  add     rcx, 2
0x1800130ef  add     rax, 2
0x1800130f3  dec     r9
0x1800130f6  sub     rdx, 1
0x1800130fa  jnz     short loc_1800130D8
0x1800130fc  test    rdx, rdx
0x1800130ff  lea     rcx, [rax-2]
0x180013103  lea     r8, aP0; "_p0"
0x18001310a  mov     rdx, rsi; unsigned __int64
0x18001310d  cmovnz  rcx, rax
0x180013111  mov     [rcx], r15w
0x180013115  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001311a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001311f  lea     r8, [rsp+280h+Name]; lpName
0x180013124  xor     edx, edx; bInheritHandle
0x180013126  mov     ecx, 1F0003h; dwDesiredAccess
0x18001312b  call    cs:__imp_OpenSemaphoreW
0x180013131  mov     rbx, rax
0x180013134  test    rax, rax
0x180013137  jz      loc_18001325E
0x18001313d  lea     rdx, [rsp+280h+var_25C]; int *
0x180013142  mov     [rsp+280h+var_25C], r15d
0x180013147  mov     rcx, rax; hHandle
0x18001314a  mov     [rsp+280h+var_260], r15d; int
0x18001314f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180013154  mov     edi, eax
0x180013156  test    eax, eax
0x180013158  jns     short loc_180013186
0x18001315a  mov     rcx, [rbp+188h]; this
0x180013161  mov     r9d, eax; char *
0x180013164  mov     edx, 0D6h; void *
0x180013169  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001316e  mov     rcx, rbx; hObject
0x180013171  call    cs:__imp_CloseHandle
0x180013177  test    eax, eax
0x180013179  jz      loc_1800132D3
0x18001317f  mov     eax, edi
0x180013181  jmp     loc_18001327E
0x180013186  lea     r8, asc_180017CE8; "h"
0x18001318d  mov     rdx, rsi; unsigned __int64
0x180013190  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180013195  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001319a  lea     r8, [rsp+280h+Name]; lpName
0x18001319f  xor     edx, edx; bInheritHandle
0x1800131a1  mov     ecx, 1F0003h; dwDesiredAccess
0x1800131a6  call    cs:__imp_OpenSemaphoreW
0x1800131ac  mov     rdi, rax
0x1800131af  test    rax, rax
0x1800131b2  jz      loc_180013239
0x1800131b8  lea     rdx, [rsp+280h+var_260]; int *
0x1800131bd  mov     rcx, rax; hHandle
0x1800131c0  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800131c5  mov     esi, eax
0x1800131c7  test    eax, eax
0x1800131c9  jns     short loc_180013205
0x1800131cb  mov     rcx, [rbp+188h]; this
0x1800131d2  mov     r9d, eax; char *
0x1800131d5  mov     edx, 0DEh; void *
0x1800131da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800131df  mov     rcx, rdi; hObject
0x1800131e2  call    cs:__imp_CloseHandle
0x1800131e8  test    eax, eax
0x1800131ea  jz      loc_1800132E5
0x1800131f0  mov     rcx, rbx; hObject
0x1800131f3  call    cs:__imp_CloseHandle
0x1800131f9  test    eax, eax
0x1800131fb  jz      loc_1800132F7
0x180013201  mov     eax, esi
0x180013203  jmp     short loc_18001327E
0x180013205  mov     rcx, rdi; hObject
0x180013208  call    cs:__imp_CloseHandle
0x18001320e  test    eax, eax
0x180013210  jz      loc_18001329D
0x180013216  movsxd  rax, [rsp+280h+var_25C]
0x18001321b  movsxd  rcx, [rsp+280h+var_260]
0x180013220  shl     rcx, 1Fh
0x180013224  or      rcx, rax
0x180013227  mov     [r14], rcx
0x18001322a  mov     rcx, rbx; hObject
0x18001322d  call    cs:__imp_CloseHandle
0x180013233  test    eax, eax
0x180013235  jz      short loc_1800132AF
0x180013237  jmp     short loc_180013269
0x180013239  mov     rcx, [rbp+188h]; this
0x180013240  mov     edx, 0DCh; void *
0x180013245  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001324a  mov     rcx, rbx; hObject
0x18001324d  mov     edi, eax
0x18001324f  call    cs:__imp_CloseHandle
0x180013255  test    eax, eax
0x180013257  jz      short loc_1800132C1
0x180013259  jmp     loc_18001317F
0x18001325e  call    cs:__imp_GetLastError
0x180013264  cmp     eax, 2
0x180013267  jnz     short loc_18001326D
0x180013269  xor     eax, eax
0x18001326b  jmp     short loc_18001327E
0x18001326d  mov     rcx, [rbp+188h]; this
0x180013274  mov     edx, 0D0h; void *
0x180013279  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001327e  mov     rcx, [rbp+180h+var_40]
0x180013285  xor     rcx, rsp; StackCookie
0x180013288  call    __security_check_cookie
0x18001328d  add     rsp, 258h
0x180013294  pop     r15
0x180013296  pop     r14
0x180013298  pop     rdi
0x180013299  pop     rsi
0x18001329a  pop     rbx
0x18001329b  pop     rbp
0x18001329c  retn
0x18001329d  mov     rcx, [rbp+188h]; this
0x1800132a4  mov     edx, 0A0Bh; void *
0x1800132a9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800132af  mov     rcx, [rbp+188h]; this
0x1800132b6  mov     edx, 0A0Bh; void *
0x1800132bb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800132c1  mov     rcx, [rbp+188h]; this
0x1800132c8  mov     edx, 0A0Bh; void *
0x1800132cd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800132d3  mov     rcx, [rbp+188h]; this
0x1800132da  mov     edx, 0A0Bh; void *
0x1800132df  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800132e5  mov     rcx, [rbp+188h]; this
0x1800132ec  mov     edx, 0A0Bh; void *
0x1800132f1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800132f7  mov     rcx, [rbp+188h]; this
0x1800132fe  mov     edx, 0A0Bh; void *
0x180013303  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
