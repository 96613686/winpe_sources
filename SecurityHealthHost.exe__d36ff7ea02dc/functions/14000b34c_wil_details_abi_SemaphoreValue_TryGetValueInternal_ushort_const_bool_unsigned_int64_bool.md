# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x14000b34c`
- end: `0x14000b5c6`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1400078ec`
- `0x140007cbc`

## callees

- `0x1400015f0`
- `0x14000674c`
- `0x140008e98`
- `0x14000a4d4`
- `0x14000af18`
- `0x14000b34c`
- `0x14000ba50`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14000b42d`
- `KERNEL32!CloseHandle` at `0x14000b49f`
- `KERNEL32!CloseHandle` at `0x14000b4b0`
- `KERNEL32!CloseHandle` at `0x14000b4c5`
- `KERNEL32!CloseHandle` at `0x14000b4ea`
- `KERNEL32!CloseHandle` at `0x14000b50c`
- `KERNEL32!CloseHandle` at `0x14000b42d`
- `KERNEL32!CloseHandle` at `0x14000b49f`
- `KERNEL32!CloseHandle` at `0x14000b4b0`
- `KERNEL32!CloseHandle` at `0x14000b4c5`
- `KERNEL32!CloseHandle` at `0x14000b4ea`
- `KERNEL32!CloseHandle` at `0x14000b50c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b51b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b51b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000b3e0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000b45c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000b3e0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000b45c`

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
  __int64 v14; // r8
  const char *v15; // r9
  HANDLE v17; // rax
  unsigned int v18; // r8d
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
  unsigned int v33; // r8d
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
0x14000b34c  push    rbp
0x14000b34e  push    rbx
0x14000b34f  push    rsi
0x14000b350  push    rdi
0x14000b351  push    r14
0x14000b353  push    r15
0x14000b355  lea     rbp, [rsp-158h]
0x14000b35d  sub     rsp, 258h
0x14000b364  mov     rax, cs:__security_cookie
0x14000b36b  xor     rax, rsp
0x14000b36e  mov     [rbp+180h+var_40], rax
0x14000b375  xor     r15d, r15d
0x14000b378  lea     rax, [rsp+280h+Name]
0x14000b37d  mov     [r8], r15
0x14000b380  mov     r14, r8
0x14000b383  mov     edx, 104h
0x14000b388  mov     r9d, 7FFFFFFEh
0x14000b38e  test    r9, r9
0x14000b391  jz      short loc_14000B3B2
0x14000b393  movzx   r8d, word ptr [rcx]
0x14000b397  test    r8w, r8w
0x14000b39b  jz      short loc_14000B3B2
0x14000b39d  mov     [rax], r8w
0x14000b3a1  add     rcx, 2
0x14000b3a5  add     rax, 2
0x14000b3a9  dec     r9
0x14000b3ac  sub     rdx, 1; unsigned __int64
0x14000b3b0  jnz     short loc_14000B38E
0x14000b3b2  test    rdx, rdx
0x14000b3b5  lea     rcx, [rax-2]
0x14000b3b9  lea     r8, aP0; "_p0"
0x14000b3c0  cmovnz  rcx, rax
0x14000b3c4  mov     [rcx], r15w
0x14000b3c8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000b3cd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000b3d2  mov     esi, 1F0003h
0x14000b3d7  lea     r8, [rsp+280h+Name]; lpName
0x14000b3dc  mov     ecx, esi; dwDesiredAccess
0x14000b3de  xor     edx, edx; bInheritHandle
0x14000b3e0  call    cs:__imp_OpenSemaphoreW
0x14000b3e6  mov     rbx, rax
0x14000b3e9  test    rax, rax
0x14000b3ec  jz      loc_14000B51B
0x14000b3f2  lea     rdx, [rsp+280h+var_25C]; int *
0x14000b3f7  mov     [rsp+280h+var_25C], r15d
0x14000b3fc  mov     rcx, rax; hHandle
0x14000b3ff  mov     [rsp+280h+var_260], r15d; int
0x14000b404  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000b409  mov     edi, eax
0x14000b40b  test    eax, eax
0x14000b40d  jns     short loc_14000B442
0x14000b40f  mov     rcx, [rbp+188h]; this
0x14000b416  lea     r8, aWil; "wil"
0x14000b41d  mov     r9d, eax; char *
0x14000b420  mov     edx, 0D6h; void *
0x14000b425  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b42a  mov     rcx, rbx; hObject
0x14000b42d  call    cs:__imp_CloseHandle
0x14000b433  test    eax, eax
0x14000b435  jz      loc_14000B590
0x14000b43b  mov     eax, edi
0x14000b43d  jmp     loc_14000B53B
0x14000b442  lea     r8, asc_140013580; "h"
0x14000b449  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000b44e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000b453  lea     r8, [rsp+280h+Name]; lpName
0x14000b458  xor     edx, edx; bInheritHandle
0x14000b45a  mov     ecx, esi; dwDesiredAccess
0x14000b45c  call    cs:__imp_OpenSemaphoreW
0x14000b462  mov     rdi, rax
0x14000b465  test    rax, rax
0x14000b468  jz      loc_14000B4F6
0x14000b46e  lea     rdx, [rsp+280h+var_260]; int *
0x14000b473  mov     rcx, rax; hHandle
0x14000b476  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000b47b  mov     esi, eax
0x14000b47d  test    eax, eax
0x14000b47f  jns     short loc_14000B4C2
0x14000b481  mov     rcx, [rbp+188h]; this
0x14000b488  lea     r8, aWil; "wil"
0x14000b48f  mov     r9d, eax; char *
0x14000b492  mov     edx, 0DEh; void *
0x14000b497  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b49c  mov     rcx, rdi; hObject
0x14000b49f  call    cs:__imp_CloseHandle
0x14000b4a5  test    eax, eax
0x14000b4a7  jz      loc_14000B5A2
0x14000b4ad  mov     rcx, rbx; hObject
0x14000b4b0  call    cs:__imp_CloseHandle
0x14000b4b6  test    eax, eax
0x14000b4b8  jz      loc_14000B5B4
0x14000b4be  mov     eax, esi
0x14000b4c0  jmp     short loc_14000B53B
0x14000b4c2  mov     rcx, rdi; hObject
0x14000b4c5  call    cs:__imp_CloseHandle
0x14000b4cb  test    eax, eax
0x14000b4cd  jz      loc_14000B55A
0x14000b4d3  movsxd  rax, [rsp+280h+var_25C]
0x14000b4d8  movsxd  rcx, [rsp+280h+var_260]
0x14000b4dd  shl     rcx, 1Fh
0x14000b4e1  or      rcx, rax
0x14000b4e4  mov     [r14], rcx
0x14000b4e7  mov     rcx, rbx; hObject
0x14000b4ea  call    cs:__imp_CloseHandle
0x14000b4f0  test    eax, eax
0x14000b4f2  jz      short loc_14000B56C
0x14000b4f4  jmp     short loc_14000B526
0x14000b4f6  mov     rcx, [rbp+188h]; this
0x14000b4fd  mov     edx, 0DCh; void *
0x14000b502  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000b507  mov     rcx, rbx; hObject
0x14000b50a  mov     edi, eax
0x14000b50c  call    cs:__imp_CloseHandle
0x14000b512  test    eax, eax
0x14000b514  jz      short loc_14000B57E
0x14000b516  jmp     loc_14000B43B
0x14000b51b  call    cs:__imp_GetLastError
0x14000b521  cmp     eax, 2
0x14000b524  jnz     short loc_14000B52A
0x14000b526  xor     eax, eax
0x14000b528  jmp     short loc_14000B53B
0x14000b52a  mov     rcx, [rbp+188h]; this
0x14000b531  mov     edx, 0D0h; void *
0x14000b536  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000b53b  mov     rcx, [rbp+180h+var_40]
0x14000b542  xor     rcx, rsp; StackCookie
0x14000b545  call    __security_check_cookie
0x14000b54a  add     rsp, 258h
0x14000b551  pop     r15
0x14000b553  pop     r14
0x14000b555  pop     rdi
0x14000b556  pop     rsi
0x14000b557  pop     rbx
0x14000b558  pop     rbp
0x14000b559  retn
0x14000b55a  mov     rcx, [rbp+188h]; this
0x14000b561  mov     edx, 0A0Bh; void *
0x14000b566  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000b56c  mov     rcx, [rbp+188h]; this
0x14000b573  mov     edx, 0A0Bh; void *
0x14000b578  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000b57e  mov     rcx, [rbp+188h]; this
0x14000b585  mov     edx, 0A0Bh; void *
0x14000b58a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000b590  mov     rcx, [rbp+188h]; this
0x14000b597  mov     edx, 0A0Bh; void *
0x14000b59c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000b5a2  mov     rcx, [rbp+188h]; this
0x14000b5a9  mov     edx, 0A0Bh; void *
0x14000b5ae  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000b5b4  mov     rcx, [rbp+188h]; this
0x14000b5bb  mov     edx, 0A0Bh; void *
0x14000b5c0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
