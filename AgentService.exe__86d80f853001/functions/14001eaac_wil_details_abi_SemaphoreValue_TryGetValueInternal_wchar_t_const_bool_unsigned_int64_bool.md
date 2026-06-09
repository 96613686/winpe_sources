# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x14001eaac`
- end: `0x14001ed18`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14001c61c`

## callees

- `0x140003e50`
- `0x14001d570`
- `0x14001dfd4`
- `0x14001dff4`
- `0x14001e8d0`
- `0x14001eaac`
- `0x14001ee6c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14001eb86`
- `KERNEL32!CloseHandle` at `0x14001ebf1`
- `KERNEL32!CloseHandle` at `0x14001ec02`
- `KERNEL32!CloseHandle` at `0x14001ec17`
- `KERNEL32!CloseHandle` at `0x14001ec3c`
- `KERNEL32!CloseHandle` at `0x14001ec5e`
- `KERNEL32!CloseHandle` at `0x14001eb86`
- `KERNEL32!CloseHandle` at `0x14001ebf1`
- `KERNEL32!CloseHandle` at `0x14001ec02`
- `KERNEL32!CloseHandle` at `0x14001ec17`
- `KERNEL32!CloseHandle` at `0x14001ec3c`
- `KERNEL32!CloseHandle` at `0x14001ec5e`
- `KERNEL32!GetLastError` at `0x14001ec6d`
- `KERNEL32!GetLastError` at `0x14001ec6d`
- `KERNEL32!OpenSemaphoreW` at `0x14001eb40`
- `KERNEL32!OpenSemaphoreW` at `0x14001ebb5`
- `KERNEL32!OpenSemaphoreW` at `0x14001eb40`
- `KERNEL32!OpenSemaphoreW` at `0x14001ebb5`

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
0x14001eaac  push    rbp
0x14001eaae  push    rbx
0x14001eaaf  push    rsi
0x14001eab0  push    rdi
0x14001eab1  push    r14
0x14001eab3  push    r15
0x14001eab5  lea     rbp, [rsp-158h]
0x14001eabd  sub     rsp, 258h
0x14001eac4  mov     rax, cs:__security_cookie
0x14001eacb  xor     rax, rsp
0x14001eace  mov     [rbp+180h+var_40], rax
0x14001ead5  xor     r15d, r15d
0x14001ead8  lea     rax, [rsp+280h+Name]
0x14001eadd  mov     [r8], r15
0x14001eae0  mov     r14, r8
0x14001eae3  mov     edx, 104h
0x14001eae8  mov     r9d, 7FFFFFFEh
0x14001eaee  test    r9, r9
0x14001eaf1  jz      short loc_14001EB12
0x14001eaf3  movzx   r8d, word ptr [rcx]
0x14001eaf7  test    r8w, r8w
0x14001eafb  jz      short loc_14001EB12
0x14001eafd  mov     [rax], r8w
0x14001eb01  add     rcx, 2
0x14001eb05  add     rax, 2
0x14001eb09  dec     r9
0x14001eb0c  sub     rdx, 1; unsigned __int64
0x14001eb10  jnz     short loc_14001EAEE
0x14001eb12  test    rdx, rdx
0x14001eb15  lea     rcx, [rax-2]
0x14001eb19  lea     r8, aP0; "_p0"
0x14001eb20  cmovnz  rcx, rax
0x14001eb24  mov     [rcx], r15w
0x14001eb28  lea     rcx, [rsp+280h+Name]; wchar_t *
0x14001eb2d  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x14001eb32  mov     esi, 1F0003h
0x14001eb37  lea     r8, [rsp+280h+Name]; lpName
0x14001eb3c  mov     ecx, esi; dwDesiredAccess
0x14001eb3e  xor     edx, edx; bInheritHandle
0x14001eb40  call    cs:__imp_OpenSemaphoreW
0x14001eb46  mov     rbx, rax
0x14001eb49  test    rax, rax
0x14001eb4c  jz      loc_14001EC6D
0x14001eb52  lea     rdx, [rsp+280h+var_25C]; int *
0x14001eb57  mov     [rsp+280h+var_25C], r15d
0x14001eb5c  mov     rcx, rax; hHandle
0x14001eb5f  mov     [rsp+280h+var_260], r15d; int
0x14001eb64  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14001eb69  mov     edi, eax
0x14001eb6b  test    eax, eax
0x14001eb6d  jns     short loc_14001EB9B
0x14001eb6f  mov     rcx, [rbp+188h]; this
0x14001eb76  mov     r9d, eax; char *
0x14001eb79  mov     edx, 0D6h; void *
0x14001eb7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001eb83  mov     rcx, rbx; hObject
0x14001eb86  call    cs:__imp_CloseHandle
0x14001eb8c  test    eax, eax
0x14001eb8e  jz      loc_14001ECE2
0x14001eb94  mov     eax, edi
0x14001eb96  jmp     loc_14001EC8D
0x14001eb9b  lea     r8, asc_1400A77A8; "h"
0x14001eba2  lea     rcx, [rsp+280h+Name]; wchar_t *
0x14001eba7  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x14001ebac  lea     r8, [rsp+280h+Name]; lpName
0x14001ebb1  xor     edx, edx; bInheritHandle
0x14001ebb3  mov     ecx, esi; dwDesiredAccess
0x14001ebb5  call    cs:__imp_OpenSemaphoreW
0x14001ebbb  mov     rdi, rax
0x14001ebbe  test    rax, rax
0x14001ebc1  jz      loc_14001EC48
0x14001ebc7  lea     rdx, [rsp+280h+var_260]; int *
0x14001ebcc  mov     rcx, rax; hHandle
0x14001ebcf  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14001ebd4  mov     esi, eax
0x14001ebd6  test    eax, eax
0x14001ebd8  jns     short loc_14001EC14
0x14001ebda  mov     rcx, [rbp+188h]; this
0x14001ebe1  mov     r9d, eax; char *
0x14001ebe4  mov     edx, 0DEh; void *
0x14001ebe9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001ebee  mov     rcx, rdi; hObject
0x14001ebf1  call    cs:__imp_CloseHandle
0x14001ebf7  test    eax, eax
0x14001ebf9  jz      loc_14001ECF4
0x14001ebff  mov     rcx, rbx; hObject
0x14001ec02  call    cs:__imp_CloseHandle
0x14001ec08  test    eax, eax
0x14001ec0a  jz      loc_14001ED06
0x14001ec10  mov     eax, esi
0x14001ec12  jmp     short loc_14001EC8D
0x14001ec14  mov     rcx, rdi; hObject
0x14001ec17  call    cs:__imp_CloseHandle
0x14001ec1d  test    eax, eax
0x14001ec1f  jz      loc_14001ECAC
0x14001ec25  movsxd  rax, [rsp+280h+var_25C]
0x14001ec2a  movsxd  rcx, [rsp+280h+var_260]
0x14001ec2f  shl     rcx, 1Fh
0x14001ec33  or      rcx, rax
0x14001ec36  mov     [r14], rcx
0x14001ec39  mov     rcx, rbx; hObject
0x14001ec3c  call    cs:__imp_CloseHandle
0x14001ec42  test    eax, eax
0x14001ec44  jz      short loc_14001ECBE
0x14001ec46  jmp     short loc_14001EC78
0x14001ec48  mov     rcx, [rbp+188h]; this
0x14001ec4f  mov     edx, 0DCh; void *
0x14001ec54  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14001ec59  mov     rcx, rbx; hObject
0x14001ec5c  mov     edi, eax
0x14001ec5e  call    cs:__imp_CloseHandle
0x14001ec64  test    eax, eax
0x14001ec66  jz      short loc_14001ECD0
0x14001ec68  jmp     loc_14001EB94
0x14001ec6d  call    cs:__imp_GetLastError
0x14001ec73  cmp     eax, 2
0x14001ec76  jnz     short loc_14001EC7C
0x14001ec78  xor     eax, eax
0x14001ec7a  jmp     short loc_14001EC8D
0x14001ec7c  mov     rcx, [rbp+188h]; this
0x14001ec83  mov     edx, 0D0h; void *
0x14001ec88  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14001ec8d  mov     rcx, [rbp+180h+var_40]
0x14001ec94  xor     rcx, rsp; StackCookie
0x14001ec97  call    __security_check_cookie
0x14001ec9c  add     rsp, 258h
0x14001eca3  pop     r15
0x14001eca5  pop     r14
0x14001eca7  pop     rdi
0x14001eca8  pop     rsi
0x14001eca9  pop     rbx
0x14001ecaa  pop     rbp
0x14001ecab  retn
0x14001ecac  mov     rcx, [rbp+188h]; this
0x14001ecb3  mov     edx, 0A0Bh; void *
0x14001ecb8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14001ecbe  mov     rcx, [rbp+188h]; this
0x14001ecc5  mov     edx, 0A0Bh; void *
0x14001ecca  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14001ecd0  mov     rcx, [rbp+188h]; this
0x14001ecd7  mov     edx, 0A0Bh; void *
0x14001ecdc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14001ece2  mov     rcx, [rbp+188h]; this
0x14001ece9  mov     edx, 0A0Bh; void *
0x14001ecee  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14001ecf4  mov     rcx, [rbp+188h]; this
0x14001ecfb  mov     edx, 0A0Bh; void *
0x14001ed00  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14001ed06  mov     rcx, [rbp+188h]; this
0x14001ed0d  mov     edx, 0A0Bh; void *
0x14001ed12  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
