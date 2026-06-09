# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000f36c`
- end: `0x18000f5fb`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `655`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000c450`
- `0x1800114d8`

## callees

- `0x18000e900`
- `0x18000efcc`
- `0x18000efec`
- `0x18000f29c`
- `0x18000f36c`
- `0x18000f6f0`
- `0x180019760`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000f400`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000f47c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000f400`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000f47c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f549`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f549`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f44d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f4bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f4d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f4e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f50d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f53a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f44d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f4bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f4d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f4e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f50d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f53a`

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
0x18000f36c  push    rbp
0x18000f36e  push    rbx
0x18000f36f  push    rsi
0x18000f370  push    rdi
0x18000f371  push    r14
0x18000f373  push    r15
0x18000f375  lea     rbp, [rsp-158h]
0x18000f37d  sub     rsp, 258h
0x18000f384  mov     rax, cs:__security_cookie
0x18000f38b  xor     rax, rsp
0x18000f38e  mov     [rbp+180h+var_40], rax
0x18000f395  xor     r15d, r15d
0x18000f398  lea     rax, [rsp+280h+Name]
0x18000f39d  mov     [r8], r15
0x18000f3a0  mov     r14, r8
0x18000f3a3  mov     edx, 104h
0x18000f3a8  mov     r9d, 7FFFFFFEh
0x18000f3ae  test    r9, r9
0x18000f3b1  jz      short loc_18000F3D2
0x18000f3b3  movzx   r8d, word ptr [rcx]
0x18000f3b7  test    r8w, r8w
0x18000f3bb  jz      short loc_18000F3D2
0x18000f3bd  mov     [rax], r8w
0x18000f3c1  add     rcx, 2
0x18000f3c5  add     rax, 2
0x18000f3c9  dec     r9
0x18000f3cc  sub     rdx, 1; unsigned __int64
0x18000f3d0  jnz     short loc_18000F3AE
0x18000f3d2  test    rdx, rdx
0x18000f3d5  lea     rcx, [rax-2]
0x18000f3d9  lea     r8, aP0; "_p0"
0x18000f3e0  cmovnz  rcx, rax
0x18000f3e4  mov     [rcx], r15w
0x18000f3e8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000f3ed  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000f3f2  mov     esi, 1F0003h
0x18000f3f7  lea     r8, [rsp+280h+Name]; lpName
0x18000f3fc  mov     ecx, esi; dwDesiredAccess
0x18000f3fe  xor     edx, edx; bInheritHandle
0x18000f400  call    cs:__imp_OpenSemaphoreW
0x18000f406  mov     rbx, rax
0x18000f409  test    rax, rax
0x18000f40c  jz      loc_18000F549
0x18000f412  lea     rdx, [rsp+280h+var_25C]; int *
0x18000f417  mov     [rsp+280h+var_25C], r15d
0x18000f41c  mov     rcx, rax; hHandle
0x18000f41f  mov     [rsp+280h+var_260], r15d; int
0x18000f424  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000f429  mov     edi, eax
0x18000f42b  test    eax, eax
0x18000f42d  jns     short loc_18000F462
0x18000f42f  mov     rcx, [rbp+188h]; this
0x18000f436  lea     r8, aWil; "wil"
0x18000f43d  mov     r9d, eax; char *
0x18000f440  mov     edx, 0D6h; void *
0x18000f445  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f44a  mov     rcx, rbx; hObject
0x18000f44d  call    cs:__imp_CloseHandle
0x18000f453  test    eax, eax
0x18000f455  jz      loc_18000F5C5
0x18000f45b  mov     eax, edi
0x18000f45d  jmp     loc_18000F570
0x18000f462  lea     r8, asc_18001F368; "h"
0x18000f469  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000f46e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000f473  lea     r8, [rsp+280h+Name]; lpName
0x18000f478  xor     edx, edx; bInheritHandle
0x18000f47a  mov     ecx, esi; dwDesiredAccess
0x18000f47c  call    cs:__imp_OpenSemaphoreW
0x18000f482  mov     rdi, rax
0x18000f485  test    rax, rax
0x18000f488  jz      loc_18000F51D
0x18000f48e  lea     rdx, [rsp+280h+var_260]; int *
0x18000f493  mov     rcx, rax; hHandle
0x18000f496  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000f49b  mov     esi, eax
0x18000f49d  test    eax, eax
0x18000f49f  jns     short loc_18000F4E5
0x18000f4a1  mov     rcx, [rbp+188h]; this
0x18000f4a8  lea     r8, aWil; "wil"
0x18000f4af  mov     r9d, eax; char *
0x18000f4b2  mov     edx, 0DEh; void *
0x18000f4b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f4bc  mov     rcx, rdi; hObject
0x18000f4bf  call    cs:__imp_CloseHandle
0x18000f4c5  test    eax, eax
0x18000f4c7  jz      loc_18000F5D7
0x18000f4cd  mov     rcx, rbx; hObject
0x18000f4d0  call    cs:__imp_CloseHandle
0x18000f4d6  test    eax, eax
0x18000f4d8  jz      loc_18000F5E9
0x18000f4de  mov     eax, esi
0x18000f4e0  jmp     loc_18000F570
0x18000f4e5  mov     rcx, rdi; hObject
0x18000f4e8  call    cs:__imp_CloseHandle
0x18000f4ee  test    eax, eax
0x18000f4f0  jz      loc_18000F58F
0x18000f4f6  movsxd  rax, [rsp+280h+var_25C]
0x18000f4fb  movsxd  rcx, [rsp+280h+var_260]
0x18000f500  shl     rcx, 1Fh
0x18000f504  or      rcx, rax
0x18000f507  mov     [r14], rcx
0x18000f50a  mov     rcx, rbx; hObject
0x18000f50d  call    cs:__imp_CloseHandle
0x18000f513  test    eax, eax
0x18000f515  jz      loc_18000F5A1
0x18000f51b  jmp     short loc_18000F554
0x18000f51d  mov     rcx, [rbp+188h]; this
0x18000f524  lea     r8, aWil; "wil"
0x18000f52b  mov     edx, 0DCh; void *
0x18000f530  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f535  mov     rcx, rbx; hObject
0x18000f538  mov     edi, eax
0x18000f53a  call    cs:__imp_CloseHandle
0x18000f540  test    eax, eax
0x18000f542  jz      short loc_18000F5B3
0x18000f544  jmp     loc_18000F45B
0x18000f549  call    cs:__imp_GetLastError
0x18000f54f  cmp     eax, 2
0x18000f552  jnz     short loc_18000F558
0x18000f554  xor     eax, eax
0x18000f556  jmp     short loc_18000F570
0x18000f558  mov     rcx, [rbp+188h]; this
0x18000f55f  lea     r8, aWil; "wil"
0x18000f566  mov     edx, 0D0h; void *
0x18000f56b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f570  mov     rcx, [rbp+180h+var_40]
0x18000f577  xor     rcx, rsp; StackCookie
0x18000f57a  call    __security_check_cookie
0x18000f57f  add     rsp, 258h
0x18000f586  pop     r15
0x18000f588  pop     r14
0x18000f58a  pop     rdi
0x18000f58b  pop     rsi
0x18000f58c  pop     rbx
0x18000f58d  pop     rbp
0x18000f58e  retn
0x18000f58f  mov     rcx, [rbp+188h]; this
0x18000f596  mov     edx, 0A0Bh; void *
0x18000f59b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000f5a1  mov     rcx, [rbp+188h]; this
0x18000f5a8  mov     edx, 0A0Bh; void *
0x18000f5ad  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000f5b3  mov     rcx, [rbp+188h]; this
0x18000f5ba  mov     edx, 0A0Bh; void *
0x18000f5bf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000f5c5  mov     rcx, [rbp+188h]; this
0x18000f5cc  mov     edx, 0A0Bh; void *
0x18000f5d1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000f5d7  mov     rcx, [rbp+188h]; this
0x18000f5de  mov     edx, 0A0Bh; void *
0x18000f5e3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000f5e9  mov     rcx, [rbp+188h]; this
0x18000f5f0  mov     edx, 0A0Bh; void *
0x18000f5f5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
