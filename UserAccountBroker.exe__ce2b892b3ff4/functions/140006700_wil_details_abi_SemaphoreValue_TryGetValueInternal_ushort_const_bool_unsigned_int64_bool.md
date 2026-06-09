# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140006700`
- end: `0x14000697a`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1400049d0`

## callees

- `0x1400059c0`
- `0x1400062f4`
- `0x140006314`
- `0x1400065c4`
- `0x140006700`
- `0x140006acc`
- `0x140006b90`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400068cf`
- `KERNEL32!GetLastError` at `0x1400068cf`
- `KERNEL32!CloseHandle` at `0x1400067e1`
- `KERNEL32!CloseHandle` at `0x140006853`
- `KERNEL32!CloseHandle` at `0x140006864`
- `KERNEL32!CloseHandle` at `0x140006879`
- `KERNEL32!CloseHandle` at `0x14000689e`
- `KERNEL32!CloseHandle` at `0x1400068c0`
- `KERNEL32!CloseHandle` at `0x1400067e1`
- `KERNEL32!CloseHandle` at `0x140006853`
- `KERNEL32!CloseHandle` at `0x140006864`
- `KERNEL32!CloseHandle` at `0x140006879`
- `KERNEL32!CloseHandle` at `0x14000689e`
- `KERNEL32!CloseHandle` at `0x1400068c0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140006794`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140006810`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140006794`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140006810`

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
  unsigned int LastError; // edi
  __int64 v14; // r8
  const char *v15; // r9
  HANDLE v17; // rax
  __int64 v18; // r8
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  unsigned int v22; // esi
  __int64 v23; // r8
  const char *v24; // r9
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, (int)"wil", (const char *)(unsigned int)ValueFromSemaphore);
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v21);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  return v22;
}

```

## disassembly

```asm
0x140006700  push    rbp
0x140006702  push    rbx
0x140006703  push    rsi
0x140006704  push    rdi
0x140006705  push    r14
0x140006707  push    r15
0x140006709  lea     rbp, [rsp-158h]
0x140006711  sub     rsp, 258h
0x140006718  mov     rax, cs:__security_cookie
0x14000671f  xor     rax, rsp
0x140006722  mov     [rbp+180h+var_40], rax
0x140006729  xor     r15d, r15d
0x14000672c  lea     rax, [rsp+280h+Name]
0x140006731  mov     [r8], r15
0x140006734  mov     r14, r8
0x140006737  mov     edx, 104h
0x14000673c  mov     r9d, 7FFFFFFEh
0x140006742  test    r9, r9
0x140006745  jz      short loc_140006766
0x140006747  movzx   r8d, word ptr [rcx]
0x14000674b  test    r8w, r8w
0x14000674f  jz      short loc_140006766
0x140006751  mov     [rax], r8w
0x140006755  add     rcx, 2
0x140006759  add     rax, 2
0x14000675d  dec     r9
0x140006760  sub     rdx, 1; unsigned __int64
0x140006764  jnz     short loc_140006742
0x140006766  test    rdx, rdx
0x140006769  lea     rcx, [rax-2]
0x14000676d  lea     r8, aP0; "_p0"
0x140006774  cmovnz  rcx, rax
0x140006778  mov     [rcx], r15w
0x14000677c  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140006781  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140006786  mov     esi, 1F0003h
0x14000678b  lea     r8, [rsp+280h+Name]; lpName
0x140006790  mov     ecx, esi; dwDesiredAccess
0x140006792  xor     edx, edx; bInheritHandle
0x140006794  call    cs:__imp_OpenSemaphoreW
0x14000679a  mov     rbx, rax
0x14000679d  test    rax, rax
0x1400067a0  jz      loc_1400068CF
0x1400067a6  lea     rdx, [rsp+280h+var_25C]; int *
0x1400067ab  mov     [rsp+280h+var_25C], r15d
0x1400067b0  mov     rcx, rax; hHandle
0x1400067b3  mov     [rsp+280h+var_260], r15d; int
0x1400067b8  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1400067bd  mov     edi, eax
0x1400067bf  test    eax, eax
0x1400067c1  jns     short loc_1400067F6
0x1400067c3  mov     rcx, [rbp+188h]; this
0x1400067ca  lea     r8, aWil; "wil"
0x1400067d1  mov     r9d, eax; char *
0x1400067d4  mov     edx, 0D6h; void *
0x1400067d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400067de  mov     rcx, rbx; hObject
0x1400067e1  call    cs:__imp_CloseHandle
0x1400067e7  test    eax, eax
0x1400067e9  jz      loc_140006944
0x1400067ef  mov     eax, edi
0x1400067f1  jmp     loc_1400068EF
0x1400067f6  lea     r8, asc_140009D10; "h"
0x1400067fd  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140006802  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140006807  lea     r8, [rsp+280h+Name]; lpName
0x14000680c  xor     edx, edx; bInheritHandle
0x14000680e  mov     ecx, esi; dwDesiredAccess
0x140006810  call    cs:__imp_OpenSemaphoreW
0x140006816  mov     rdi, rax
0x140006819  test    rax, rax
0x14000681c  jz      loc_1400068AA
0x140006822  lea     rdx, [rsp+280h+var_260]; int *
0x140006827  mov     rcx, rax; hHandle
0x14000682a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000682f  mov     esi, eax
0x140006831  test    eax, eax
0x140006833  jns     short loc_140006876
0x140006835  mov     rcx, [rbp+188h]; this
0x14000683c  lea     r8, aWil; "wil"
0x140006843  mov     r9d, eax; char *
0x140006846  mov     edx, 0DEh; void *
0x14000684b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006850  mov     rcx, rdi; hObject
0x140006853  call    cs:__imp_CloseHandle
0x140006859  test    eax, eax
0x14000685b  jz      loc_140006956
0x140006861  mov     rcx, rbx; hObject
0x140006864  call    cs:__imp_CloseHandle
0x14000686a  test    eax, eax
0x14000686c  jz      loc_140006968
0x140006872  mov     eax, esi
0x140006874  jmp     short loc_1400068EF
0x140006876  mov     rcx, rdi; hObject
0x140006879  call    cs:__imp_CloseHandle
0x14000687f  test    eax, eax
0x140006881  jz      loc_14000690E
0x140006887  movsxd  rax, [rsp+280h+var_25C]
0x14000688c  movsxd  rcx, [rsp+280h+var_260]
0x140006891  shl     rcx, 1Fh
0x140006895  or      rcx, rax
0x140006898  mov     [r14], rcx
0x14000689b  mov     rcx, rbx; hObject
0x14000689e  call    cs:__imp_CloseHandle
0x1400068a4  test    eax, eax
0x1400068a6  jz      short loc_140006920
0x1400068a8  jmp     short loc_1400068DA
0x1400068aa  mov     rcx, [rbp+188h]; this
0x1400068b1  mov     edx, 0DCh; void *
0x1400068b6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400068bb  mov     rcx, rbx; hObject
0x1400068be  mov     edi, eax
0x1400068c0  call    cs:__imp_CloseHandle
0x1400068c6  test    eax, eax
0x1400068c8  jz      short loc_140006932
0x1400068ca  jmp     loc_1400067EF
0x1400068cf  call    cs:__imp_GetLastError
0x1400068d5  cmp     eax, 2
0x1400068d8  jnz     short loc_1400068DE
0x1400068da  xor     eax, eax
0x1400068dc  jmp     short loc_1400068EF
0x1400068de  mov     rcx, [rbp+188h]; this
0x1400068e5  mov     edx, 0D0h; void *
0x1400068ea  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400068ef  mov     rcx, [rbp+180h+var_40]
0x1400068f6  xor     rcx, rsp; StackCookie
0x1400068f9  call    __security_check_cookie
0x1400068fe  add     rsp, 258h
0x140006905  pop     r15
0x140006907  pop     r14
0x140006909  pop     rdi
0x14000690a  pop     rsi
0x14000690b  pop     rbx
0x14000690c  pop     rbp
0x14000690d  retn
0x14000690e  mov     rcx, [rbp+188h]; this
0x140006915  mov     edx, 0A0Bh; void *
0x14000691a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006920  mov     rcx, [rbp+188h]; this
0x140006927  mov     edx, 0A0Bh; void *
0x14000692c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006932  mov     rcx, [rbp+188h]; this
0x140006939  mov     edx, 0A0Bh; void *
0x14000693e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006944  mov     rcx, [rbp+188h]; this
0x14000694b  mov     edx, 0A0Bh; void *
0x140006950  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006956  mov     rcx, [rbp+188h]; this
0x14000695d  mov     edx, 0A0Bh; void *
0x140006962  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006968  mov     rcx, [rbp+188h]; this
0x14000696f  mov     edx, 0A0Bh; void *
0x140006974  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
