# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180005fcc`
- end: `0x180006246`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003b08`

## callees

- `0x180001e20`
- `0x180004a94`
- `0x180005504`
- `0x180005524`
- `0x180005e64`
- `0x180005fcc`
- `0x18000639c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006060`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800060dc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006060`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800060dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000619b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000619b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800060ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000611f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006130`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006145`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000616a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000618c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800060ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000611f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006130`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006145`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000616a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000618c`

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
0x180005fcc  push    rbp
0x180005fce  push    rbx
0x180005fcf  push    rsi
0x180005fd0  push    rdi
0x180005fd1  push    r14
0x180005fd3  push    r15
0x180005fd5  lea     rbp, [rsp-158h]
0x180005fdd  sub     rsp, 258h
0x180005fe4  mov     rax, cs:__security_cookie
0x180005feb  xor     rax, rsp
0x180005fee  mov     [rbp+180h+var_40], rax
0x180005ff5  xor     r15d, r15d
0x180005ff8  lea     rax, [rsp+280h+Name]
0x180005ffd  mov     [r8], r15
0x180006000  mov     r14, r8
0x180006003  mov     edx, 104h
0x180006008  mov     r9d, 7FFFFFFEh
0x18000600e  test    r9, r9
0x180006011  jz      short loc_180006032
0x180006013  movzx   r8d, word ptr [rcx]
0x180006017  test    r8w, r8w
0x18000601b  jz      short loc_180006032
0x18000601d  mov     [rax], r8w
0x180006021  add     rcx, 2
0x180006025  add     rax, 2
0x180006029  dec     r9
0x18000602c  sub     rdx, 1; unsigned __int64
0x180006030  jnz     short loc_18000600E
0x180006032  test    rdx, rdx
0x180006035  lea     rcx, [rax-2]
0x180006039  lea     r8, aP0; "_p0"
0x180006040  cmovnz  rcx, rax
0x180006044  mov     [rcx], r15w
0x180006048  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000604d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006052  mov     esi, 1F0003h
0x180006057  lea     r8, [rsp+280h+Name]; lpName
0x18000605c  mov     ecx, esi; dwDesiredAccess
0x18000605e  xor     edx, edx; bInheritHandle
0x180006060  call    cs:__imp_OpenSemaphoreW
0x180006066  mov     rbx, rax
0x180006069  test    rax, rax
0x18000606c  jz      loc_18000619B
0x180006072  lea     rdx, [rsp+280h+var_25C]; int *
0x180006077  mov     [rsp+280h+var_25C], r15d
0x18000607c  mov     rcx, rax; hHandle
0x18000607f  mov     [rsp+280h+var_260], r15d; int
0x180006084  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006089  mov     edi, eax
0x18000608b  test    eax, eax
0x18000608d  jns     short loc_1800060C2
0x18000608f  mov     rcx, [rbp+188h]; this
0x180006096  lea     r8, aWil; "wil"
0x18000609d  mov     r9d, eax; char *
0x1800060a0  mov     edx, 0D6h; void *
0x1800060a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800060aa  mov     rcx, rbx; hObject
0x1800060ad  call    cs:__imp_CloseHandle
0x1800060b3  test    eax, eax
0x1800060b5  jz      loc_180006210
0x1800060bb  mov     eax, edi
0x1800060bd  jmp     loc_1800061BB
0x1800060c2  lea     r8, asc_180015348; "h"
0x1800060c9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800060ce  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800060d3  lea     r8, [rsp+280h+Name]; lpName
0x1800060d8  xor     edx, edx; bInheritHandle
0x1800060da  mov     ecx, esi; dwDesiredAccess
0x1800060dc  call    cs:__imp_OpenSemaphoreW
0x1800060e2  mov     rdi, rax
0x1800060e5  test    rax, rax
0x1800060e8  jz      loc_180006176
0x1800060ee  lea     rdx, [rsp+280h+var_260]; int *
0x1800060f3  mov     rcx, rax; hHandle
0x1800060f6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800060fb  mov     esi, eax
0x1800060fd  test    eax, eax
0x1800060ff  jns     short loc_180006142
0x180006101  mov     rcx, [rbp+188h]; this
0x180006108  lea     r8, aWil; "wil"
0x18000610f  mov     r9d, eax; char *
0x180006112  mov     edx, 0DEh; void *
0x180006117  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000611c  mov     rcx, rdi; hObject
0x18000611f  call    cs:__imp_CloseHandle
0x180006125  test    eax, eax
0x180006127  jz      loc_180006222
0x18000612d  mov     rcx, rbx; hObject
0x180006130  call    cs:__imp_CloseHandle
0x180006136  test    eax, eax
0x180006138  jz      loc_180006234
0x18000613e  mov     eax, esi
0x180006140  jmp     short loc_1800061BB
0x180006142  mov     rcx, rdi; hObject
0x180006145  call    cs:__imp_CloseHandle
0x18000614b  test    eax, eax
0x18000614d  jz      loc_1800061DA
0x180006153  movsxd  rax, [rsp+280h+var_25C]
0x180006158  movsxd  rcx, [rsp+280h+var_260]
0x18000615d  shl     rcx, 1Fh
0x180006161  or      rcx, rax
0x180006164  mov     [r14], rcx
0x180006167  mov     rcx, rbx; hObject
0x18000616a  call    cs:__imp_CloseHandle
0x180006170  test    eax, eax
0x180006172  jz      short loc_1800061EC
0x180006174  jmp     short loc_1800061A6
0x180006176  mov     rcx, [rbp+188h]; this
0x18000617d  mov     edx, 0DCh; void *
0x180006182  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006187  mov     rcx, rbx; hObject
0x18000618a  mov     edi, eax
0x18000618c  call    cs:__imp_CloseHandle
0x180006192  test    eax, eax
0x180006194  jz      short loc_1800061FE
0x180006196  jmp     loc_1800060BB
0x18000619b  call    cs:__imp_GetLastError
0x1800061a1  cmp     eax, 2
0x1800061a4  jnz     short loc_1800061AA
0x1800061a6  xor     eax, eax
0x1800061a8  jmp     short loc_1800061BB
0x1800061aa  mov     rcx, [rbp+188h]; this
0x1800061b1  mov     edx, 0D0h; void *
0x1800061b6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800061bb  mov     rcx, [rbp+180h+var_40]
0x1800061c2  xor     rcx, rsp; StackCookie
0x1800061c5  call    __security_check_cookie
0x1800061ca  add     rsp, 258h
0x1800061d1  pop     r15
0x1800061d3  pop     r14
0x1800061d5  pop     rdi
0x1800061d6  pop     rsi
0x1800061d7  pop     rbx
0x1800061d8  pop     rbp
0x1800061d9  retn
0x1800061da  mov     rcx, [rbp+188h]; this
0x1800061e1  mov     edx, 0A0Bh; void *
0x1800061e6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800061ec  mov     rcx, [rbp+188h]; this
0x1800061f3  mov     edx, 0A0Bh; void *
0x1800061f8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800061fe  mov     rcx, [rbp+188h]; this
0x180006205  mov     edx, 0A0Bh; void *
0x18000620a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006210  mov     rcx, [rbp+188h]; this
0x180006217  mov     edx, 0A0Bh; void *
0x18000621c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006222  mov     rcx, [rbp+188h]; this
0x180006229  mov     edx, 0A0Bh; void *
0x18000622e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006234  mov     rcx, [rbp+188h]; this
0x18000623b  mov     edx, 0A0Bh; void *
0x180006240  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
