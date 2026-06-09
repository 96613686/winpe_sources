# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800070e4`
- end: `0x18000738e`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `682`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003354`
- `0x180003700`

## callees

- `0x18000490c`
- `0x180006850`
- `0x180006870`
- `0x180006be8`
- `0x1800070e4`
- `0x18000787c`
- `0x1800096b0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800071c4`
- `KERNEL32!CloseHandle` at `0x18000723b`
- `KERNEL32!CloseHandle` at `0x180007252`
- `KERNEL32!CloseHandle` at `0x180007270`
- `KERNEL32!CloseHandle` at `0x18000729b`
- `KERNEL32!CloseHandle` at `0x1800072c7`
- `KERNEL32!CloseHandle` at `0x1800071c4`
- `KERNEL32!CloseHandle` at `0x18000723b`
- `KERNEL32!CloseHandle` at `0x180007252`
- `KERNEL32!CloseHandle` at `0x180007270`
- `KERNEL32!CloseHandle` at `0x18000729b`
- `KERNEL32!CloseHandle` at `0x1800072c7`
- `KERNEL32!GetLastError` at `0x1800072dc`
- `KERNEL32!GetLastError` at `0x1800072dc`
- `KERNEL32!OpenSemaphoreW` at `0x180007178`
- `KERNEL32!OpenSemaphoreW` at `0x1800071f9`
- `KERNEL32!OpenSemaphoreW` at `0x180007178`
- `KERNEL32!OpenSemaphoreW` at `0x1800071f9`

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
0x1800070e4  push    rbp
0x1800070e6  push    rbx
0x1800070e7  push    rsi
0x1800070e8  push    rdi
0x1800070e9  push    r14
0x1800070eb  push    r15
0x1800070ed  lea     rbp, [rsp-158h]
0x1800070f5  sub     rsp, 258h
0x1800070fc  mov     rax, cs:__security_cookie
0x180007103  xor     rax, rsp
0x180007106  mov     [rbp+180h+var_40], rax
0x18000710d  xor     r15d, r15d
0x180007110  lea     rax, [rsp+280h+Name]
0x180007115  mov     [r8], r15
0x180007118  mov     r14, r8
0x18000711b  mov     edx, 104h
0x180007120  mov     r9d, 7FFFFFFEh
0x180007126  test    r9, r9
0x180007129  jz      short loc_18000714A
0x18000712b  movzx   r8d, word ptr [rcx]
0x18000712f  test    r8w, r8w
0x180007133  jz      short loc_18000714A
0x180007135  mov     [rax], r8w
0x180007139  add     rcx, 2
0x18000713d  add     rax, 2
0x180007141  dec     r9
0x180007144  sub     rdx, 1; unsigned __int64
0x180007148  jnz     short loc_180007126
0x18000714a  test    rdx, rdx
0x18000714d  lea     rcx, [rax-2]
0x180007151  lea     r8, aP0; "_p0"
0x180007158  cmovnz  rcx, rax
0x18000715c  mov     [rcx], r15w
0x180007160  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180007165  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000716a  mov     esi, 1F0003h
0x18000716f  lea     r8, [rsp+280h+Name]; lpName
0x180007174  mov     ecx, esi; dwDesiredAccess
0x180007176  xor     edx, edx; bInheritHandle
0x180007178  call    cs:__imp_OpenSemaphoreW
0x18000717f  nop     dword ptr [rax+rax+00h]
0x180007184  mov     rbx, rax
0x180007187  test    rax, rax
0x18000718a  jz      loc_1800072DC
0x180007190  lea     rdx, [rsp+280h+var_25C]; int *
0x180007195  mov     [rsp+280h+var_25C], r15d
0x18000719a  mov     rcx, rax; hHandle
0x18000719d  mov     [rsp+280h+var_260], r15d; int
0x1800071a2  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800071a7  mov     edi, eax
0x1800071a9  test    eax, eax
0x1800071ab  jns     short loc_1800071DF
0x1800071ad  mov     rcx, [rbp+188h]; this
0x1800071b4  mov     r9d, eax; char *
0x1800071b7  mov     edx, 0D6h; void *
0x1800071bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800071c1  mov     rcx, rbx; hObject
0x1800071c4  call    cs:__imp_CloseHandle
0x1800071cb  nop     dword ptr [rax+rax+00h]
0x1800071d0  test    eax, eax
0x1800071d2  jz      loc_180007358
0x1800071d8  mov     eax, edi
0x1800071da  jmp     loc_180007302
0x1800071df  lea     r8, asc_18000B810; "h"
0x1800071e6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800071eb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800071f0  lea     r8, [rsp+280h+Name]; lpName
0x1800071f5  xor     edx, edx; bInheritHandle
0x1800071f7  mov     ecx, esi; dwDesiredAccess
0x1800071f9  call    cs:__imp_OpenSemaphoreW
0x180007200  nop     dword ptr [rax+rax+00h]
0x180007205  mov     rdi, rax
0x180007208  test    rax, rax
0x18000720b  jz      loc_1800072B1
0x180007211  lea     rdx, [rsp+280h+var_260]; int *
0x180007216  mov     rcx, rax; hHandle
0x180007219  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000721e  mov     esi, eax
0x180007220  test    eax, eax
0x180007222  jns     short loc_18000726D
0x180007224  mov     rcx, [rbp+188h]; this
0x18000722b  mov     r9d, eax; char *
0x18000722e  mov     edx, 0DEh; void *
0x180007233  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007238  mov     rcx, rdi; hObject
0x18000723b  call    cs:__imp_CloseHandle
0x180007242  nop     dword ptr [rax+rax+00h]
0x180007247  test    eax, eax
0x180007249  jz      loc_18000736A
0x18000724f  mov     rcx, rbx; hObject
0x180007252  call    cs:__imp_CloseHandle
0x180007259  nop     dword ptr [rax+rax+00h]
0x18000725e  test    eax, eax
0x180007260  jz      loc_18000737C
0x180007266  mov     eax, esi
0x180007268  jmp     loc_180007302
0x18000726d  mov     rcx, rdi; hObject
0x180007270  call    cs:__imp_CloseHandle
0x180007277  nop     dword ptr [rax+rax+00h]
0x18000727c  test    eax, eax
0x18000727e  jz      loc_180007322
0x180007284  movsxd  rax, [rsp+280h+var_25C]
0x180007289  movsxd  rcx, [rsp+280h+var_260]
0x18000728e  shl     rcx, 1Fh
0x180007292  or      rcx, rax
0x180007295  mov     [r14], rcx
0x180007298  mov     rcx, rbx; hObject
0x18000729b  call    cs:__imp_CloseHandle
0x1800072a2  nop     dword ptr [rax+rax+00h]
0x1800072a7  test    eax, eax
0x1800072a9  jz      loc_180007334
0x1800072af  jmp     short loc_1800072ED
0x1800072b1  mov     rcx, [rbp+188h]; this
0x1800072b8  mov     edx, 0DCh; void *
0x1800072bd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800072c2  mov     rcx, rbx; hObject
0x1800072c5  mov     edi, eax
0x1800072c7  call    cs:__imp_CloseHandle
0x1800072ce  nop     dword ptr [rax+rax+00h]
0x1800072d3  test    eax, eax
0x1800072d5  jz      short loc_180007346
0x1800072d7  jmp     loc_1800071D8
0x1800072dc  call    cs:__imp_GetLastError
0x1800072e3  nop     dword ptr [rax+rax+00h]
0x1800072e8  cmp     eax, 2
0x1800072eb  jnz     short loc_1800072F1
0x1800072ed  xor     eax, eax
0x1800072ef  jmp     short loc_180007302
0x1800072f1  mov     rcx, [rbp+188h]; this
0x1800072f8  mov     edx, 0D0h; void *
0x1800072fd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007302  mov     rcx, [rbp+180h+var_40]
0x180007309  xor     rcx, rsp; StackCookie
0x18000730c  call    __security_check_cookie
0x180007311  add     rsp, 258h
0x180007318  pop     r15
0x18000731a  pop     r14
0x18000731c  pop     rdi
0x18000731d  pop     rsi
0x18000731e  pop     rbx
0x18000731f  pop     rbp
0x180007320  retn
0x180007322  mov     rcx, [rbp+188h]; this
0x180007329  mov     edx, 0A0Bh; void *
0x18000732e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007334  mov     rcx, [rbp+188h]; this
0x18000733b  mov     edx, 0A0Bh; void *
0x180007340  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007346  mov     rcx, [rbp+188h]; this
0x18000734d  mov     edx, 0A0Bh; void *
0x180007352  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007358  mov     rcx, [rbp+188h]; this
0x18000735f  mov     edx, 0A0Bh; void *
0x180007364  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000736a  mov     rcx, [rbp+188h]; this
0x180007371  mov     edx, 0A0Bh; void *
0x180007376  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000737c  mov     rcx, [rbp+188h]; this
0x180007383  mov     edx, 0A0Bh; void *
0x180007388  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
