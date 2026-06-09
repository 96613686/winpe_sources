# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180005f94`
- end: `0x18000625a`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `710`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800040b4`

## callees

- `0x180002910`
- `0x180004d50`
- `0x180005b08`
- `0x180005b28`
- `0x180005e58`
- `0x180005f94`
- `0x180006474`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000607b`
- `KERNEL32!CloseHandle` at `0x1800060f9`
- `KERNEL32!CloseHandle` at `0x180006110`
- `KERNEL32!CloseHandle` at `0x18000612e`
- `KERNEL32!CloseHandle` at `0x180006159`
- `KERNEL32!CloseHandle` at `0x18000618c`
- `KERNEL32!CloseHandle` at `0x18000607b`
- `KERNEL32!CloseHandle` at `0x1800060f9`
- `KERNEL32!CloseHandle` at `0x180006110`
- `KERNEL32!CloseHandle` at `0x18000612e`
- `KERNEL32!CloseHandle` at `0x180006159`
- `KERNEL32!CloseHandle` at `0x18000618c`
- `KERNEL32!OpenSemaphoreW` at `0x180006028`
- `KERNEL32!OpenSemaphoreW` at `0x1800060b0`
- `KERNEL32!OpenSemaphoreW` at `0x180006028`
- `KERNEL32!OpenSemaphoreW` at `0x1800060b0`
- `KERNEL32!GetLastError` at `0x1800061a1`
- `KERNEL32!GetLastError` at `0x1800061a1`

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
  const char *v18; // r9
  void *v19; // rdi
  int v20; // eax
  unsigned int v21; // esi
  unsigned int v22; // r8d
  const char *v23; // r9
  unsigned int v24; // r8d
  const char *v25; // r9
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  unsigned int v30; // r8d
  const char *v31; // r9
  const char *v32; // r9
  int v33; // [rsp+20h] [rbp-E0h] BYREF
  int v34[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v32);
    return 0;
  }
  v34[0] = 0;
  v33 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v34);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v33);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v19 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v18);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    return LastError;
  }
  v20 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v33);
  v21 = v20;
  if ( v20 >= 0 )
  {
    if ( !CloseHandle(v19) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    *a3 = v34[0] | (unsigned __int64)((__int64)v33 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v20, v33);
  if ( !CloseHandle(v19) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  return v21;
}

```

## disassembly

```asm
0x180005f94  push    rbp
0x180005f96  push    rbx
0x180005f97  push    rsi
0x180005f98  push    rdi
0x180005f99  push    r14
0x180005f9b  push    r15
0x180005f9d  lea     rbp, [rsp-158h]
0x180005fa5  sub     rsp, 258h
0x180005fac  mov     rax, cs:__security_cookie
0x180005fb3  xor     rax, rsp
0x180005fb6  mov     [rbp+180h+var_40], rax
0x180005fbd  xor     r15d, r15d
0x180005fc0  lea     rax, [rsp+280h+Name]
0x180005fc5  mov     [r8], r15
0x180005fc8  mov     r14, r8
0x180005fcb  mov     edx, 104h
0x180005fd0  mov     r9d, 7FFFFFFEh
0x180005fd6  test    r9, r9
0x180005fd9  jz      short loc_180005FFA
0x180005fdb  movzx   r8d, word ptr [rcx]
0x180005fdf  test    r8w, r8w
0x180005fe3  jz      short loc_180005FFA
0x180005fe5  mov     [rax], r8w
0x180005fe9  add     rcx, 2
0x180005fed  add     rax, 2
0x180005ff1  dec     r9
0x180005ff4  sub     rdx, 1; unsigned __int64
0x180005ff8  jnz     short loc_180005FD6
0x180005ffa  test    rdx, rdx
0x180005ffd  lea     rcx, [rax-2]
0x180006001  lea     r8, aP0; "_p0"
0x180006008  cmovnz  rcx, rax
0x18000600c  mov     [rcx], r15w
0x180006010  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006015  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000601a  mov     esi, 1F0003h
0x18000601f  lea     r8, [rsp+280h+Name]; lpName
0x180006024  mov     ecx, esi; dwDesiredAccess
0x180006026  xor     edx, edx; bInheritHandle
0x180006028  call    cs:__imp_OpenSemaphoreW
0x18000602f  nop     dword ptr [rax+rax+00h]
0x180006034  mov     rbx, rax
0x180006037  test    rax, rax
0x18000603a  jz      loc_1800061A1
0x180006040  lea     rdx, [rsp+280h+var_25C]; int *
0x180006045  mov     [rsp+280h+var_25C], r15d
0x18000604a  mov     rcx, rax; hHandle
0x18000604d  mov     [rsp+280h+var_260], r15d; int
0x180006052  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006057  mov     edi, eax
0x180006059  test    eax, eax
0x18000605b  jns     short loc_180006096
0x18000605d  mov     rcx, [rbp+188h]; this
0x180006064  lea     r8, aWil; "wil"
0x18000606b  mov     r9d, eax; char *
0x18000606e  mov     edx, 0D6h; void *
0x180006073  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006078  mov     rcx, rbx; hObject
0x18000607b  call    cs:__imp_CloseHandle
0x180006082  nop     dword ptr [rax+rax+00h]
0x180006087  test    eax, eax
0x180006089  jz      loc_180006224
0x18000608f  mov     eax, edi
0x180006091  jmp     loc_1800061CE
0x180006096  lea     r8, asc_180012BA0; "h"
0x18000609d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800060a2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800060a7  lea     r8, [rsp+280h+Name]; lpName
0x1800060ac  xor     edx, edx; bInheritHandle
0x1800060ae  mov     ecx, esi; dwDesiredAccess
0x1800060b0  call    cs:__imp_OpenSemaphoreW
0x1800060b7  nop     dword ptr [rax+rax+00h]
0x1800060bc  mov     rdi, rax
0x1800060bf  test    rax, rax
0x1800060c2  jz      loc_18000616F
0x1800060c8  lea     rdx, [rsp+280h+var_260]; int *
0x1800060cd  mov     rcx, rax; hHandle
0x1800060d0  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800060d5  mov     esi, eax
0x1800060d7  test    eax, eax
0x1800060d9  jns     short loc_18000612B
0x1800060db  mov     rcx, [rbp+188h]; this
0x1800060e2  lea     r8, aWil; "wil"
0x1800060e9  mov     r9d, eax; char *
0x1800060ec  mov     edx, 0DEh; void *
0x1800060f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800060f6  mov     rcx, rdi; hObject
0x1800060f9  call    cs:__imp_CloseHandle
0x180006100  nop     dword ptr [rax+rax+00h]
0x180006105  test    eax, eax
0x180006107  jz      loc_180006236
0x18000610d  mov     rcx, rbx; hObject
0x180006110  call    cs:__imp_CloseHandle
0x180006117  nop     dword ptr [rax+rax+00h]
0x18000611c  test    eax, eax
0x18000611e  jz      loc_180006248
0x180006124  mov     eax, esi
0x180006126  jmp     loc_1800061CE
0x18000612b  mov     rcx, rdi; hObject
0x18000612e  call    cs:__imp_CloseHandle
0x180006135  nop     dword ptr [rax+rax+00h]
0x18000613a  test    eax, eax
0x18000613c  jz      loc_1800061EE
0x180006142  movsxd  rax, [rsp+280h+var_25C]
0x180006147  movsxd  rcx, [rsp+280h+var_260]
0x18000614c  shl     rcx, 1Fh
0x180006150  or      rcx, rax
0x180006153  mov     [r14], rcx
0x180006156  mov     rcx, rbx; hObject
0x180006159  call    cs:__imp_CloseHandle
0x180006160  nop     dword ptr [rax+rax+00h]
0x180006165  test    eax, eax
0x180006167  jz      loc_180006200
0x18000616d  jmp     short loc_1800061B2
0x18000616f  mov     rcx, [rbp+188h]; this
0x180006176  lea     r8, aWil; "wil"
0x18000617d  mov     edx, 0DCh; void *
0x180006182  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006187  mov     rcx, rbx; hObject
0x18000618a  mov     edi, eax
0x18000618c  call    cs:__imp_CloseHandle
0x180006193  nop     dword ptr [rax+rax+00h]
0x180006198  test    eax, eax
0x18000619a  jz      short loc_180006212
0x18000619c  jmp     loc_18000608F
0x1800061a1  call    cs:__imp_GetLastError
0x1800061a8  nop     dword ptr [rax+rax+00h]
0x1800061ad  cmp     eax, 2
0x1800061b0  jnz     short loc_1800061B6
0x1800061b2  xor     eax, eax
0x1800061b4  jmp     short loc_1800061CE
0x1800061b6  mov     rcx, [rbp+188h]; this
0x1800061bd  lea     r8, aWil; "wil"
0x1800061c4  mov     edx, 0D0h; void *
0x1800061c9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800061ce  mov     rcx, [rbp+180h+var_40]
0x1800061d5  xor     rcx, rsp; StackCookie
0x1800061d8  call    __security_check_cookie
0x1800061dd  add     rsp, 258h
0x1800061e4  pop     r15
0x1800061e6  pop     r14
0x1800061e8  pop     rdi
0x1800061e9  pop     rsi
0x1800061ea  pop     rbx
0x1800061eb  pop     rbp
0x1800061ec  retn
0x1800061ee  mov     rcx, [rbp+188h]; this
0x1800061f5  mov     edx, 0A0Bh; void *
0x1800061fa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006200  mov     rcx, [rbp+188h]; this
0x180006207  mov     edx, 0A0Bh; void *
0x18000620c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006212  mov     rcx, [rbp+188h]; this
0x180006219  mov     edx, 0A0Bh; void *
0x18000621e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006224  mov     rcx, [rbp+188h]; this
0x18000622b  mov     edx, 0A0Bh; void *
0x180006230  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006236  mov     rcx, [rbp+188h]; this
0x18000623d  mov     edx, 0A0Bh; void *
0x180006242  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006248  mov     rcx, [rbp+188h]; this
0x18000624f  mov     edx, 0A0Bh; void *
0x180006254  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
