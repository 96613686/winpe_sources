# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180015dcc`
- end: `0x180016083`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `695`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180011648`
- `0x180011a14`

## callees

- `0x180012e70`
- `0x180014f44`
- `0x180014f64`
- `0x180015844`
- `0x180015dcc`
- `0x180016644`
- `0x1800189d0`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x180015e60`
- `KERNEL32!OpenSemaphoreW` at `0x180015eee`
- `KERNEL32!OpenSemaphoreW` at `0x180015e60`
- `KERNEL32!OpenSemaphoreW` at `0x180015eee`
- `KERNEL32!GetLastError` at `0x180015ffa`
- `KERNEL32!GetLastError` at `0x180015ffa`
- `KERNEL32!CloseHandle` at `0x180015eb2`
- `KERNEL32!CloseHandle` at `0x180015f36`
- `KERNEL32!CloseHandle` at `0x180015f54`
- `KERNEL32!CloseHandle` at `0x180015f79`
- `KERNEL32!CloseHandle` at `0x180015fab`
- `KERNEL32!CloseHandle` at `0x180015fde`
- `KERNEL32!CloseHandle` at `0x180015eb2`
- `KERNEL32!CloseHandle` at `0x180015f36`
- `KERNEL32!CloseHandle` at `0x180015f54`
- `KERNEL32!CloseHandle` at `0x180015f79`
- `KERNEL32!CloseHandle` at `0x180015fab`
- `KERNEL32!CloseHandle` at `0x180015fde`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
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
  unsigned int v14; // r8d
  unsigned int LastError; // edi
  unsigned int v16; // r8d
  const char *v17; // r9
  HANDLE v19; // rax
  unsigned int v20; // r8d
  const char *v21; // r9
  void *v22; // rdi
  int v23; // eax
  unsigned int v24; // r8d
  unsigned int v25; // esi
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v14, (const char *)(unsigned int)ValueFromSemaphore, v38);
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v24, (const char *)(unsigned int)v23, v38);
  if ( !CloseHandle(v22) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
  if ( !CloseHandle(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
  return v25;
}

```

## disassembly

```asm
0x180015dcc  push    rbp
0x180015dce  push    rbx
0x180015dcf  push    rsi
0x180015dd0  push    rdi
0x180015dd1  push    r14
0x180015dd3  push    r15
0x180015dd5  lea     rbp, [rsp-168h]
0x180015ddd  sub     rsp, 268h
0x180015de4  mov     rax, cs:__security_cookie
0x180015deb  xor     rax, rsp
0x180015dee  mov     [rbp+190h+var_40], rax
0x180015df5  mov     r14, r8
0x180015df8  xor     r15d, r15d
0x180015dfb  mov     [r8], r15
0x180015dfe  mov     edx, 104h
0x180015e03  mov     r9d, 7FFFFFFEh
0x180015e09  lea     rax, [rsp+290h+Name]
0x180015e0e  test    r9, r9
0x180015e11  jz      short loc_180015E32
0x180015e13  movzx   r8d, word ptr [rcx]
0x180015e17  test    r8w, r8w
0x180015e1b  jz      short loc_180015E32
0x180015e1d  add     rcx, 2
0x180015e21  mov     [rax], r8w
0x180015e25  add     rax, 2
0x180015e29  dec     r9
0x180015e2c  sub     rdx, 1; unsigned __int64
0x180015e30  jnz     short loc_180015E0E
0x180015e32  lea     rcx, [rax-2]
0x180015e36  test    rdx, rdx
0x180015e39  cmovnz  rcx, rax
0x180015e3d  mov     [rcx], r15w
0x180015e41  lea     r8, aP0; "_p0"
0x180015e48  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x180015e4d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180015e52  lea     r8, [rsp+290h+Name]; lpName
0x180015e57  xor     edx, edx; bInheritHandle
0x180015e59  mov     esi, 1F0003h
0x180015e5e  mov     ecx, esi; dwDesiredAccess
0x180015e60  call    cs:__imp_OpenSemaphoreW
0x180015e67  nop     dword ptr [rax+rax+00h]
0x180015e6c  mov     rbx, rax
0x180015e6f  mov     [rsp+290h+var_268], rax
0x180015e74  test    rax, rax
0x180015e77  jz      loc_180015FFA
0x180015e7d  mov     [rsp+290h+var_26C], r15d
0x180015e82  mov     [rsp+290h+var_270], r15d; int
0x180015e87  lea     rdx, [rsp+290h+var_26C]; int *
0x180015e8c  mov     rcx, rax; hHandle
0x180015e8f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180015e94  mov     edi, eax
0x180015e96  test    eax, eax
0x180015e98  jns     short loc_180015ED4
0x180015e9a  mov     rcx, [rbp+198h]; this
0x180015ea1  mov     r9d, eax; char *
0x180015ea4  mov     edx, 0D6h; void *
0x180015ea9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015eae  nop
0x180015eaf  mov     rcx, rbx; hObject
0x180015eb2  call    cs:__imp_CloseHandle
0x180015eb9  nop     dword ptr [rax+rax+00h]
0x180015ebe  mov     rcx, [rbp+198h]; this
0x180015ec5  test    eax, eax
0x180015ec7  jz      loc_180016057
0x180015ecd  mov     eax, edi
0x180015ecf  jmp     loc_180016021
0x180015ed4  lea     r8, asc_18006CC78; "h"
0x180015edb  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x180015ee0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180015ee5  lea     r8, [rsp+290h+Name]; lpName
0x180015eea  xor     edx, edx; bInheritHandle
0x180015eec  mov     ecx, esi; dwDesiredAccess
0x180015eee  call    cs:__imp_OpenSemaphoreW
0x180015ef5  nop     dword ptr [rax+rax+00h]
0x180015efa  mov     rdi, rax
0x180015efd  mov     [rsp+290h+var_260], rax
0x180015f02  test    rax, rax
0x180015f05  jz      loc_180015FC8
0x180015f0b  lea     rdx, [rsp+290h+var_270]; int *
0x180015f10  mov     rcx, rax; hHandle
0x180015f13  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180015f18  mov     esi, eax
0x180015f1a  test    eax, eax
0x180015f1c  jns     short loc_180015F76
0x180015f1e  mov     rcx, [rbp+198h]; this
0x180015f25  mov     r9d, eax; char *
0x180015f28  mov     edx, 0DEh; void *
0x180015f2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015f32  nop
0x180015f33  mov     rcx, rdi; hObject
0x180015f36  call    cs:__imp_CloseHandle
0x180015f3d  nop     dword ptr [rax+rax+00h]
0x180015f42  mov     rcx, [rbp+198h]; this
0x180015f49  test    eax, eax
0x180015f4b  jz      loc_180016062
0x180015f51  mov     rcx, rbx; hObject
0x180015f54  call    cs:__imp_CloseHandle
0x180015f5b  nop     dword ptr [rax+rax+00h]
0x180015f60  mov     rcx, [rbp+198h]; this
0x180015f67  test    eax, eax
0x180015f69  jz      loc_18001606D
0x180015f6f  mov     eax, esi
0x180015f71  jmp     loc_180016021
0x180015f76  mov     rcx, rdi; hObject
0x180015f79  call    cs:__imp_CloseHandle
0x180015f80  nop     dword ptr [rax+rax+00h]
0x180015f85  mov     rcx, [rbp+198h]; this
0x180015f8c  test    eax, eax
0x180015f8e  jz      loc_180016078
0x180015f94  movsxd  rcx, [rsp+290h+var_270]
0x180015f99  shl     rcx, 1Fh
0x180015f9d  movsxd  rax, [rsp+290h+var_26C]
0x180015fa2  or      rcx, rax
0x180015fa5  mov     [r14], rcx
0x180015fa8  mov     rcx, rbx; hObject
0x180015fab  call    cs:__imp_CloseHandle
0x180015fb2  nop     dword ptr [rax+rax+00h]
0x180015fb7  mov     rcx, [rbp+198h]; this
0x180015fbe  test    eax, eax
0x180015fc0  jz      loc_18001604C
0x180015fc6  jmp     short loc_18001600B
0x180015fc8  mov     rcx, [rbp+198h]; this
0x180015fcf  mov     edx, 0DCh; void *
0x180015fd4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180015fd9  mov     edi, eax
0x180015fdb  mov     rcx, rbx; hObject
0x180015fde  call    cs:__imp_CloseHandle
0x180015fe5  nop     dword ptr [rax+rax+00h]
0x180015fea  mov     rcx, [rbp+198h]; this
0x180015ff1  test    eax, eax
0x180015ff3  jz      short loc_180016041
0x180015ff5  jmp     loc_180015ECD
0x180015ffa  call    cs:__imp_GetLastError
0x180016001  nop     dword ptr [rax+rax+00h]
0x180016006  cmp     eax, 2
0x180016009  jnz     short loc_18001600F
0x18001600b  xor     eax, eax
0x18001600d  jmp     short loc_180016021
0x18001600f  mov     rcx, [rbp+198h]; this
0x180016016  mov     edx, 0D0h; void *
0x18001601b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180016020  nop
0x180016021  mov     rcx, [rbp+190h+var_40]
0x180016028  xor     rcx, rsp; StackCookie
0x18001602b  call    __security_check_cookie
0x180016030  add     rsp, 268h
0x180016037  pop     r15
0x180016039  pop     r14
0x18001603b  pop     rdi
0x18001603c  pop     rsi
0x18001603d  pop     rbx
0x18001603e  pop     rbp
0x18001603f  retn
0x180016041  mov     edx, 0A0Bh; void *
0x180016046  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001604c  mov     edx, 0A0Bh; void *
0x180016051  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180016057  mov     edx, 0A0Bh; void *
0x18001605c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180016062  mov     edx, 0A0Bh; void *
0x180016067  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001606d  mov     edx, 0A0Bh; void *
0x180016072  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180016078  mov     edx, 0A0Bh; void *
0x18001607d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
