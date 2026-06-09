# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180018ecc`
- end: `0x180019141`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `629`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180014d7c`
- `0x180015120`

## callees

- `0x1800016d0`
- `0x18000cc10`
- `0x1800165c4`
- `0x180018194`
- `0x1800181b4`
- `0x180018ecc`
- `0x1800196bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019096`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019096`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018fa9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001901a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001902b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019040`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019065`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019087`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018fa9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001901a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001902b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019040`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019065`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019087`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180018f63`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180018fde`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180018f63`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180018fde`

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
  unsigned int v12; // r8d
  unsigned int LastError; // edi
  __int64 v14; // r8
  const char *v15; // r9
  HANDLE v17; // rax
  unsigned int v18; // r8d
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  unsigned int v22; // r8d
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore, v36);
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v22, (const char *)(unsigned int)v21, v36);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
  return v23;
}

```

## disassembly

```asm
0x180018ecc  push    rbp
0x180018ece  push    rbx
0x180018ecf  push    rsi
0x180018ed0  push    rdi
0x180018ed1  push    r14
0x180018ed3  push    r15
0x180018ed5  lea     rbp, [rsp-158h]
0x180018edd  sub     rsp, 258h
0x180018ee4  mov     rax, cs:__security_cookie
0x180018eeb  xor     rax, rsp
0x180018eee  mov     [rbp+180h+var_40], rax
0x180018ef5  xor     r15d, r15d
0x180018ef8  lea     rax, [rsp+280h+Name]
0x180018efd  mov     esi, 104h
0x180018f02  mov     [r8], r15
0x180018f05  mov     edx, esi
0x180018f07  mov     r14, r8
0x180018f0a  mov     r9d, 7FFFFFFEh
0x180018f10  test    r9, r9
0x180018f13  jz      short loc_180018F34
0x180018f15  movzx   r8d, word ptr [rcx]
0x180018f19  test    r8w, r8w
0x180018f1d  jz      short loc_180018F34
0x180018f1f  mov     [rax], r8w
0x180018f23  add     rcx, 2
0x180018f27  add     rax, 2
0x180018f2b  dec     r9
0x180018f2e  sub     rdx, 1
0x180018f32  jnz     short loc_180018F10
0x180018f34  test    rdx, rdx
0x180018f37  lea     rcx, [rax-2]
0x180018f3b  lea     r8, aP0; "_p0"
0x180018f42  mov     rdx, rsi; unsigned __int64
0x180018f45  cmovnz  rcx, rax
0x180018f49  mov     [rcx], r15w
0x180018f4d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180018f52  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180018f57  lea     r8, [rsp+280h+Name]; lpName
0x180018f5c  xor     edx, edx; bInheritHandle
0x180018f5e  mov     ecx, 1F0003h; dwDesiredAccess
0x180018f63  call    cs:__imp_OpenSemaphoreW
0x180018f69  mov     rbx, rax
0x180018f6c  test    rax, rax
0x180018f6f  jz      loc_180019096
0x180018f75  lea     rdx, [rsp+280h+var_25C]; int *
0x180018f7a  mov     [rsp+280h+var_25C], r15d
0x180018f7f  mov     rcx, rax; hHandle
0x180018f82  mov     [rsp+280h+var_260], r15d; int
0x180018f87  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180018f8c  mov     edi, eax
0x180018f8e  test    eax, eax
0x180018f90  jns     short loc_180018FBE
0x180018f92  mov     rcx, [rbp+188h]; this
0x180018f99  mov     r9d, eax; char *
0x180018f9c  mov     edx, 0D6h; void *
0x180018fa1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018fa6  mov     rcx, rbx; hObject
0x180018fa9  call    cs:__imp_CloseHandle
0x180018faf  test    eax, eax
0x180018fb1  jz      loc_18001910B
0x180018fb7  mov     eax, edi
0x180018fb9  jmp     loc_1800190B6
0x180018fbe  lea     r8, asc_1800306E0; "h"
0x180018fc5  mov     rdx, rsi; unsigned __int64
0x180018fc8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180018fcd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180018fd2  lea     r8, [rsp+280h+Name]; lpName
0x180018fd7  xor     edx, edx; bInheritHandle
0x180018fd9  mov     ecx, 1F0003h; dwDesiredAccess
0x180018fde  call    cs:__imp_OpenSemaphoreW
0x180018fe4  mov     rdi, rax
0x180018fe7  test    rax, rax
0x180018fea  jz      loc_180019071
0x180018ff0  lea     rdx, [rsp+280h+var_260]; int *
0x180018ff5  mov     rcx, rax; hHandle
0x180018ff8  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180018ffd  mov     esi, eax
0x180018fff  test    eax, eax
0x180019001  jns     short loc_18001903D
0x180019003  mov     rcx, [rbp+188h]; this
0x18001900a  mov     r9d, eax; char *
0x18001900d  mov     edx, 0DEh; void *
0x180019012  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019017  mov     rcx, rdi; hObject
0x18001901a  call    cs:__imp_CloseHandle
0x180019020  test    eax, eax
0x180019022  jz      loc_18001911D
0x180019028  mov     rcx, rbx; hObject
0x18001902b  call    cs:__imp_CloseHandle
0x180019031  test    eax, eax
0x180019033  jz      loc_18001912F
0x180019039  mov     eax, esi
0x18001903b  jmp     short loc_1800190B6
0x18001903d  mov     rcx, rdi; hObject
0x180019040  call    cs:__imp_CloseHandle
0x180019046  test    eax, eax
0x180019048  jz      loc_1800190D5
0x18001904e  movsxd  rax, [rsp+280h+var_25C]
0x180019053  movsxd  rcx, [rsp+280h+var_260]
0x180019058  shl     rcx, 1Fh
0x18001905c  or      rcx, rax
0x18001905f  mov     [r14], rcx
0x180019062  mov     rcx, rbx; hObject
0x180019065  call    cs:__imp_CloseHandle
0x18001906b  test    eax, eax
0x18001906d  jz      short loc_1800190E7
0x18001906f  jmp     short loc_1800190A1
0x180019071  mov     rcx, [rbp+188h]; this
0x180019078  mov     edx, 0DCh; void *
0x18001907d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180019082  mov     rcx, rbx; hObject
0x180019085  mov     edi, eax
0x180019087  call    cs:__imp_CloseHandle
0x18001908d  test    eax, eax
0x18001908f  jz      short loc_1800190F9
0x180019091  jmp     loc_180018FB7
0x180019096  call    cs:__imp_GetLastError
0x18001909c  cmp     eax, 2
0x18001909f  jnz     short loc_1800190A5
0x1800190a1  xor     eax, eax
0x1800190a3  jmp     short loc_1800190B6
0x1800190a5  mov     rcx, [rbp+188h]; this
0x1800190ac  mov     edx, 0D0h; void *
0x1800190b1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800190b6  mov     rcx, [rbp+180h+var_40]
0x1800190bd  xor     rcx, rsp; StackCookie
0x1800190c0  call    __security_check_cookie
0x1800190c5  add     rsp, 258h
0x1800190cc  pop     r15
0x1800190ce  pop     r14
0x1800190d0  pop     rdi
0x1800190d1  pop     rsi
0x1800190d2  pop     rbx
0x1800190d3  pop     rbp
0x1800190d4  retn
0x1800190d5  mov     rcx, [rbp+188h]; this
0x1800190dc  mov     edx, 0A0Bh; void *
0x1800190e1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800190e7  mov     rcx, [rbp+188h]; this
0x1800190ee  mov     edx, 0A0Bh; void *
0x1800190f3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800190f9  mov     rcx, [rbp+188h]; this
0x180019100  mov     edx, 0A0Bh; void *
0x180019105  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001910b  mov     rcx, [rbp+188h]; this
0x180019112  mov     edx, 0A0Bh; void *
0x180019117  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001911d  mov     rcx, [rbp+188h]; this
0x180019124  mov     edx, 0A0Bh; void *
0x180019129  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001912f  mov     rcx, [rbp+188h]; this
0x180019136  mov     edx, 0A0Bh; void *
0x18001913b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
