# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000608c`
- end: `0x18000630f`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `643`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003670`

## callees

- `0x180004868`
- `0x180005624`
- `0x180005644`
- `0x180005d60`
- `0x18000608c`
- `0x180006560`
- `0x180010f80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006123`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800061a5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006123`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800061a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006264`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006264`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006170`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800061e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800061f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000620e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006233`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006255`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006170`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800061e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800061f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000620e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006233`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006255`

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
  unsigned int LastError; // edi
  __int64 v13; // r8
  const char *v14; // r9
  HANDLE v16; // rax
  unsigned int v17; // r8d
  const char *v18; // r9
  void *v19; // rdi
  int v20; // eax
  unsigned int v21; // esi
  __int64 v22; // r8
  const char *v23; // r9
  __int64 v24; // r8
  const char *v25; // r9
  __int64 v26; // r8
  const char *v27; // r9
  __int64 v28; // r8
  const char *v29; // r9
  __int64 v30; // r8
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  int v34; // [rsp+20h] [rbp-E0h] BYREF
  int v35[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v32, v33);
    return 0;
  }
  v35[0] = 0;
  v34 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v35);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, (int)"wil", (const char *)(unsigned int)ValueFromSemaphore);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v14);
    return LastError;
  }
  StringCchCatW(Name, 260, L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v19 = v16;
  if ( !v16 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v17, v18);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    return LastError;
  }
  v20 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, &v34);
  v21 = v20;
  if ( v20 >= 0 )
  {
    if ( !CloseHandle(v19) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    *a3 = v35[0] | (unsigned __int64)((__int64)v34 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v20);
  if ( !CloseHandle(v19) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  return v21;
}

```

## disassembly

```asm
0x18000608c  push    rbp
0x18000608e  push    rbx
0x18000608f  push    rsi
0x180006090  push    rdi
0x180006091  push    r14
0x180006093  push    r15
0x180006095  lea     rbp, [rsp-158h]
0x18000609d  sub     rsp, 258h
0x1800060a4  mov     rax, cs:__security_cookie
0x1800060ab  xor     rax, rsp
0x1800060ae  mov     [rbp+180h+var_40], rax
0x1800060b5  xor     r15d, r15d
0x1800060b8  lea     rax, [rsp+280h+Name]
0x1800060bd  mov     esi, 104h
0x1800060c2  mov     [r8], r15
0x1800060c5  mov     edx, esi
0x1800060c7  mov     r14, r8
0x1800060ca  mov     r9d, 7FFFFFFEh
0x1800060d0  test    r9, r9
0x1800060d3  jz      short loc_1800060F4
0x1800060d5  movzx   r8d, word ptr [rcx]
0x1800060d9  test    r8w, r8w
0x1800060dd  jz      short loc_1800060F4
0x1800060df  mov     [rax], r8w
0x1800060e3  add     rcx, 2
0x1800060e7  add     rax, 2
0x1800060eb  dec     r9
0x1800060ee  sub     rdx, 1
0x1800060f2  jnz     short loc_1800060D0
0x1800060f4  test    rdx, rdx
0x1800060f7  lea     rcx, [rax-2]
0x1800060fb  lea     r8, aP0; "_p0"
0x180006102  mov     rdx, rsi; unsigned __int64
0x180006105  cmovnz  rcx, rax
0x180006109  mov     [rcx], r15w
0x18000610d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006112  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006117  lea     r8, [rsp+280h+Name]; lpName
0x18000611c  xor     edx, edx; bInheritHandle
0x18000611e  mov     ecx, 1F0003h; dwDesiredAccess
0x180006123  call    cs:__imp_OpenSemaphoreW
0x180006129  mov     rbx, rax
0x18000612c  test    rax, rax
0x18000612f  jz      loc_180006264
0x180006135  lea     rdx, [rsp+280h+var_25C]; int *
0x18000613a  mov     [rsp+280h+var_25C], r15d
0x18000613f  mov     rcx, rax; hHandle
0x180006142  mov     [rsp+280h+var_260], r15d; int
0x180006147  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000614c  mov     edi, eax
0x18000614e  test    eax, eax
0x180006150  jns     short loc_180006185
0x180006152  mov     rcx, [rbp+188h]; this
0x180006159  lea     r8, aWil; "wil"
0x180006160  mov     r9d, eax; char *
0x180006163  mov     edx, 0D6h; void *
0x180006168  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000616d  mov     rcx, rbx; hObject
0x180006170  call    cs:__imp_CloseHandle
0x180006176  test    eax, eax
0x180006178  jz      loc_1800062D9
0x18000617e  mov     eax, edi
0x180006180  jmp     loc_180006284
0x180006185  lea     r8, asc_180014238; "h"
0x18000618c  mov     rdx, rsi; unsigned __int64
0x18000618f  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006194  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006199  lea     r8, [rsp+280h+Name]; lpName
0x18000619e  xor     edx, edx; bInheritHandle
0x1800061a0  mov     ecx, 1F0003h; dwDesiredAccess
0x1800061a5  call    cs:__imp_OpenSemaphoreW
0x1800061ab  mov     rdi, rax
0x1800061ae  test    rax, rax
0x1800061b1  jz      loc_18000623F
0x1800061b7  lea     rdx, [rsp+280h+var_260]; int *
0x1800061bc  mov     rcx, rax; hHandle
0x1800061bf  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800061c4  mov     esi, eax
0x1800061c6  test    eax, eax
0x1800061c8  jns     short loc_18000620B
0x1800061ca  mov     rcx, [rbp+188h]; this
0x1800061d1  lea     r8, aWil; "wil"
0x1800061d8  mov     r9d, eax; char *
0x1800061db  mov     edx, 0DEh; void *
0x1800061e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800061e5  mov     rcx, rdi; hObject
0x1800061e8  call    cs:__imp_CloseHandle
0x1800061ee  test    eax, eax
0x1800061f0  jz      loc_1800062EB
0x1800061f6  mov     rcx, rbx; hObject
0x1800061f9  call    cs:__imp_CloseHandle
0x1800061ff  test    eax, eax
0x180006201  jz      loc_1800062FD
0x180006207  mov     eax, esi
0x180006209  jmp     short loc_180006284
0x18000620b  mov     rcx, rdi; hObject
0x18000620e  call    cs:__imp_CloseHandle
0x180006214  test    eax, eax
0x180006216  jz      loc_1800062A3
0x18000621c  movsxd  rax, [rsp+280h+var_25C]
0x180006221  movsxd  rcx, [rsp+280h+var_260]
0x180006226  shl     rcx, 1Fh
0x18000622a  or      rcx, rax
0x18000622d  mov     [r14], rcx
0x180006230  mov     rcx, rbx; hObject
0x180006233  call    cs:__imp_CloseHandle
0x180006239  test    eax, eax
0x18000623b  jz      short loc_1800062B5
0x18000623d  jmp     short loc_18000626F
0x18000623f  mov     rcx, [rbp+188h]; this
0x180006246  mov     edx, 0DCh; void *
0x18000624b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006250  mov     rcx, rbx; hObject
0x180006253  mov     edi, eax
0x180006255  call    cs:__imp_CloseHandle
0x18000625b  test    eax, eax
0x18000625d  jz      short loc_1800062C7
0x18000625f  jmp     loc_18000617E
0x180006264  call    cs:__imp_GetLastError
0x18000626a  cmp     eax, 2
0x18000626d  jnz     short loc_180006273
0x18000626f  xor     eax, eax
0x180006271  jmp     short loc_180006284
0x180006273  mov     rcx, [rbp+188h]; this
0x18000627a  mov     edx, 0D0h; void *
0x18000627f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006284  mov     rcx, [rbp+180h+var_40]
0x18000628b  xor     rcx, rsp; StackCookie
0x18000628e  call    __security_check_cookie
0x180006293  add     rsp, 258h
0x18000629a  pop     r15
0x18000629c  pop     r14
0x18000629e  pop     rdi
0x18000629f  pop     rsi
0x1800062a0  pop     rbx
0x1800062a1  pop     rbp
0x1800062a2  retn
0x1800062a3  mov     rcx, [rbp+188h]; this
0x1800062aa  mov     edx, 0A0Bh; void *
0x1800062af  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800062b5  mov     rcx, [rbp+188h]; this
0x1800062bc  mov     edx, 0A0Bh; void *
0x1800062c1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800062c7  mov     rcx, [rbp+188h]; this
0x1800062ce  mov     edx, 0A0Bh; void *
0x1800062d3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800062d9  mov     rcx, [rbp+188h]; this
0x1800062e0  mov     edx, 0A0Bh; void *
0x1800062e5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800062eb  mov     rcx, [rbp+188h]; this
0x1800062f2  mov     edx, 0A0Bh; void *
0x1800062f7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800062fd  mov     rcx, [rbp+188h]; this
0x180006304  mov     edx, 0A0Bh; void *
0x180006309  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
