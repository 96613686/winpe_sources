# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x14001ffc0`
- end: `0x14002028b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `715`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140005330`
- `0x1400056f4`

## callees

- `0x140010c04`
- `0x14001d214`
- `0x14001d240`
- `0x14001f668`
- `0x14001ffc0`
- `0x140020ff8`
- `0x140080d70`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x140020062`
- `KERNEL32!OpenSemaphoreW` at `0x1400200e9`
- `KERNEL32!OpenSemaphoreW` at `0x140020062`
- `KERNEL32!OpenSemaphoreW` at `0x1400200e9`
- `KERNEL32!CloseHandle` at `0x1400200ae`
- `KERNEL32!CloseHandle` at `0x14002012b`
- `KERNEL32!CloseHandle` at `0x140020142`
- `KERNEL32!CloseHandle` at `0x140020160`
- `KERNEL32!CloseHandle` at `0x14002018b`
- `KERNEL32!CloseHandle` at `0x1400201b7`
- `KERNEL32!CloseHandle` at `0x1400200ae`
- `KERNEL32!CloseHandle` at `0x14002012b`
- `KERNEL32!CloseHandle` at `0x140020142`
- `KERNEL32!CloseHandle` at `0x140020160`
- `KERNEL32!CloseHandle` at `0x14002018b`
- `KERNEL32!CloseHandle` at `0x1400201b7`
- `KERNEL32!GetLastError` at `0x1400201cc`
- `KERNEL32!GetLastError` at `0x1400201cc`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        char *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  __int64 v4; // r9
  WCHAR *v5; // rdx
  signed __int64 v6; // rcx
  WCHAR v8; // ax
  WCHAR *v9; // rax
  HANDLE v10; // rax
  void *v11; // rbx
  int ValueFromSemaphore; // eax
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
  int v37; // [rsp+28h] [rbp-E0h] BYREF
  int v38[3]; // [rsp+2Ch] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+38h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+270h] [rbp+168h]

  *a3 = 0;
  v4 = 260;
  v5 = Name;
  v6 = a1 - (char *)Name;
  do
  {
    if ( v4 == -2147483386 )
      break;
    v8 = *(WCHAR *)((char *)v5 + v6);
    if ( !v8 )
      break;
    *v5++ = v8;
    --v4;
  }
  while ( v4 );
  v9 = v5 - 1;
  if ( v4 )
    v9 = v5;
  *v9 = 0;
  StringCchCatW(Name, 0x104u, L"_p0");
  v10 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v11 = v10;
  if ( !v10 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xCD, v35, v36);
    return 0;
  }
  v38[0] = 0;
  v37 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, v38);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD3, v13, (const char *)(unsigned int)ValueFromSemaphore, v37);
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9E2, v15, v16);
    return LastError;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v18 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v21 = v18;
  if ( !v18 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD9, v19, v20);
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9E2, v33, v34);
    return LastError;
  }
  v22 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v18, &v37);
  v24 = v22;
  if ( v22 >= 0 )
  {
    if ( !CloseHandle(v21) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9E2, v29, v30);
    *a3 = v38[0] | (unsigned __int64)((__int64)v37 << 31);
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9E2, v31, v32);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDB, v23, (const char *)(unsigned int)v22, v37);
  if ( !CloseHandle(v21) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9E2, v25, v26);
  if ( !CloseHandle(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9E2, v27, v28);
  return v24;
}

```

## disassembly

```asm
0x14001ffc0  mov     rax, rsp
0x14001ffc3  mov     [rax+8], rbx
0x14001ffc7  mov     [rax+10h], rsi
0x14001ffcb  mov     [rax+20h], rdi
0x14001ffcf  push    rbp
0x14001ffd0  push    r14
0x14001ffd2  push    r15
0x14001ffd4  lea     rbp, [rax-168h]
0x14001ffdb  sub     rsp, 250h
0x14001ffe2  mov     rax, cs:__security_cookie
0x14001ffe9  xor     rax, rsp
0x14001ffec  mov     [rbp+160h+var_20], rax
0x14001fff3  xor     r15d, r15d
0x14001fff6  lea     rax, [rsp+260h+Name]
0x14001fffb  mov     esi, 104h
0x140020000  mov     [r8], r15
0x140020003  mov     r9d, esi
0x140020006  lea     rdx, [rsp+260h+Name]
0x14002000b  sub     rcx, rax
0x14002000e  mov     r14, r8
0x140020011  lea     rax, [r9+7FFFFEFAh]
0x140020018  test    rax, rax
0x14002001b  jz      short loc_140020033
0x14002001d  movzx   eax, word ptr [rdx+rcx]
0x140020021  test    ax, ax
0x140020024  jz      short loc_140020033
0x140020026  mov     [rdx], ax
0x140020029  add     rdx, 2
0x14002002d  sub     r9, 1
0x140020031  jnz     short loc_140020011
0x140020033  lea     rax, [rdx-2]
0x140020037  test    r9, r9
0x14002003a  lea     r8, aP0; "_p0"
0x140020041  cmovnz  rax, rdx
0x140020045  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x14002004a  mov     rdx, rsi; unsigned __int64
0x14002004d  mov     [rax], r15w
0x140020051  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140020056  lea     r8, [rsp+260h+Name]; lpName
0x14002005b  xor     edx, edx; bInheritHandle
0x14002005d  mov     ecx, 1F0003h; dwDesiredAccess
0x140020062  call    cs:__imp_OpenSemaphoreW
0x140020069  nop     dword ptr [rax+rax+00h]
0x14002006e  mov     rbx, rax
0x140020071  test    rax, rax
0x140020074  jz      loc_1400201CC
0x14002007a  lea     rdx, [rsp+260h+var_23C]; int *
0x14002007f  mov     [rsp+260h+var_23C], r15d
0x140020084  mov     rcx, rax; hHandle
0x140020087  mov     [rsp+260h+var_240], r15d; int
0x14002008c  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140020091  mov     edi, eax
0x140020093  test    eax, eax
0x140020095  jns     short loc_1400200C9
0x140020097  mov     rcx, [rbp+168h]; this
0x14002009e  mov     r9d, eax; char *
0x1400200a1  mov     edx, 0D3h; void *
0x1400200a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400200ab  mov     rcx, rbx; hObject
0x1400200ae  call    cs:__imp_CloseHandle
0x1400200b5  nop     dword ptr [rax+rax+00h]
0x1400200ba  test    eax, eax
0x1400200bc  jz      loc_140020255
0x1400200c2  mov     eax, edi
0x1400200c4  jmp     loc_1400201F2
0x1400200c9  lea     r8, asc_1400865E0; "h"
0x1400200d0  mov     rdx, rsi; unsigned __int64
0x1400200d3  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1400200d8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400200dd  lea     r8, [rsp+260h+Name]; lpName
0x1400200e2  xor     edx, edx; bInheritHandle
0x1400200e4  mov     ecx, 1F0003h; dwDesiredAccess
0x1400200e9  call    cs:__imp_OpenSemaphoreW
0x1400200f0  nop     dword ptr [rax+rax+00h]
0x1400200f5  mov     rdi, rax
0x1400200f8  test    rax, rax
0x1400200fb  jz      loc_1400201A1
0x140020101  lea     rdx, [rsp+260h+var_240]; int *
0x140020106  mov     rcx, rax; hHandle
0x140020109  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14002010e  mov     esi, eax
0x140020110  test    eax, eax
0x140020112  jns     short loc_14002015D
0x140020114  mov     rcx, [rbp+168h]; this
0x14002011b  mov     r9d, eax; char *
0x14002011e  mov     edx, 0DBh; void *
0x140020123  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140020128  mov     rcx, rdi; hObject
0x14002012b  call    cs:__imp_CloseHandle
0x140020132  nop     dword ptr [rax+rax+00h]
0x140020137  test    eax, eax
0x140020139  jz      loc_140020267
0x14002013f  mov     rcx, rbx; hObject
0x140020142  call    cs:__imp_CloseHandle
0x140020149  nop     dword ptr [rax+rax+00h]
0x14002014e  test    eax, eax
0x140020150  jz      loc_140020279
0x140020156  mov     eax, esi
0x140020158  jmp     loc_1400201F2
0x14002015d  mov     rcx, rdi; hObject
0x140020160  call    cs:__imp_CloseHandle
0x140020167  nop     dword ptr [rax+rax+00h]
0x14002016c  test    eax, eax
0x14002016e  jz      loc_14002021F
0x140020174  movsxd  rax, [rsp+260h+var_23C]
0x140020179  movsxd  rcx, [rsp+260h+var_240]
0x14002017e  shl     rcx, 1Fh
0x140020182  or      rcx, rax
0x140020185  mov     [r14], rcx
0x140020188  mov     rcx, rbx; hObject
0x14002018b  call    cs:__imp_CloseHandle
0x140020192  nop     dword ptr [rax+rax+00h]
0x140020197  test    eax, eax
0x140020199  jz      loc_140020231
0x14002019f  jmp     short loc_1400201DD
0x1400201a1  mov     rcx, [rbp+168h]; this
0x1400201a8  mov     edx, 0D9h; void *
0x1400201ad  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400201b2  mov     rcx, rbx; hObject
0x1400201b5  mov     edi, eax
0x1400201b7  call    cs:__imp_CloseHandle
0x1400201be  nop     dword ptr [rax+rax+00h]
0x1400201c3  test    eax, eax
0x1400201c5  jz      short loc_140020243
0x1400201c7  jmp     loc_1400200C2
0x1400201cc  call    cs:__imp_GetLastError
0x1400201d3  nop     dword ptr [rax+rax+00h]
0x1400201d8  cmp     eax, 2
0x1400201db  jnz     short loc_1400201E1
0x1400201dd  xor     eax, eax
0x1400201df  jmp     short loc_1400201F2
0x1400201e1  mov     rcx, [rbp+168h]; this
0x1400201e8  mov     edx, 0CDh; void *
0x1400201ed  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400201f2  mov     rcx, [rbp+160h+var_20]
0x1400201f9  xor     rcx, rsp; StackCookie
0x1400201fc  call    __security_check_cookie
0x140020201  lea     r11, [rsp+260h+var_10]
0x140020209  mov     rbx, [r11+20h]
0x14002020d  mov     rsi, [r11+28h]
0x140020211  mov     rdi, [r11+38h]
0x140020215  mov     rsp, r11
0x140020218  pop     r15
0x14002021a  pop     r14
0x14002021c  pop     rbp
0x14002021d  retn
0x14002021f  mov     rcx, [rbp+168h]; this
0x140020226  mov     edx, 9E2h; void *
0x14002022b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140020231  mov     rcx, [rbp+168h]; this
0x140020238  mov     edx, 9E2h; void *
0x14002023d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140020243  mov     rcx, [rbp+168h]; this
0x14002024a  mov     edx, 9E2h; void *
0x14002024f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140020255  mov     rcx, [rbp+168h]; this
0x14002025c  mov     edx, 9E2h; void *
0x140020261  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140020267  mov     rcx, [rbp+168h]; this
0x14002026e  mov     edx, 9E2h; void *
0x140020273  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140020279  mov     rcx, [rbp+168h]; this
0x140020280  mov     edx, 9E2h; void *
0x140020285  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
