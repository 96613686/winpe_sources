# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180009d88`
- end: `0x18000a017`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `655`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180006a78`
- `0x180015244`

## callees

- `0x180003520`
- `0x180008458`
- `0x180009284`
- `0x1800092a4`
- `0x180009be4`
- `0x180009d88`
- `0x18000a374`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009e1c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009e98`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009e1c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009e98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009e69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009edb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009eec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009f04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009f29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009f56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009e69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009edb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009eec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009f04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009f29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009f56`

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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, (int)"wil", (const char *)(unsigned int)ValueFromSemaphore);
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
0x180009d88  push    rbp
0x180009d8a  push    rbx
0x180009d8b  push    rsi
0x180009d8c  push    rdi
0x180009d8d  push    r14
0x180009d8f  push    r15
0x180009d91  lea     rbp, [rsp-158h]
0x180009d99  sub     rsp, 258h
0x180009da0  mov     rax, cs:__security_cookie
0x180009da7  xor     rax, rsp
0x180009daa  mov     [rbp+180h+var_40], rax
0x180009db1  xor     r15d, r15d
0x180009db4  lea     rax, [rsp+280h+Name]
0x180009db9  mov     [r8], r15
0x180009dbc  mov     r14, r8
0x180009dbf  mov     edx, 104h
0x180009dc4  mov     r9d, 7FFFFFFEh
0x180009dca  test    r9, r9
0x180009dcd  jz      short loc_180009DEE
0x180009dcf  movzx   r8d, word ptr [rcx]
0x180009dd3  test    r8w, r8w
0x180009dd7  jz      short loc_180009DEE
0x180009dd9  mov     [rax], r8w
0x180009ddd  add     rcx, 2
0x180009de1  add     rax, 2
0x180009de5  dec     r9
0x180009de8  sub     rdx, 1; unsigned __int64
0x180009dec  jnz     short loc_180009DCA
0x180009dee  test    rdx, rdx
0x180009df1  lea     rcx, [rax-2]
0x180009df5  lea     r8, aP0; "_p0"
0x180009dfc  cmovnz  rcx, rax
0x180009e00  mov     [rcx], r15w
0x180009e04  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180009e09  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009e0e  mov     esi, 1F0003h
0x180009e13  lea     r8, [rsp+280h+Name]; lpName
0x180009e18  mov     ecx, esi; dwDesiredAccess
0x180009e1a  xor     edx, edx; bInheritHandle
0x180009e1c  call    cs:__imp_OpenSemaphoreW
0x180009e22  mov     rbx, rax
0x180009e25  test    rax, rax
0x180009e28  jz      loc_180009F65
0x180009e2e  lea     rdx, [rsp+280h+var_25C]; int *
0x180009e33  mov     [rsp+280h+var_25C], r15d
0x180009e38  mov     rcx, rax; hHandle
0x180009e3b  mov     [rsp+280h+var_260], r15d; int
0x180009e40  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009e45  mov     edi, eax
0x180009e47  test    eax, eax
0x180009e49  jns     short loc_180009E7E
0x180009e4b  mov     rcx, [rbp+188h]; this
0x180009e52  lea     r8, aWil; "wil"
0x180009e59  mov     r9d, eax; char *
0x180009e5c  mov     edx, 0D6h; void *
0x180009e61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009e66  mov     rcx, rbx; hObject
0x180009e69  call    cs:__imp_CloseHandle
0x180009e6f  test    eax, eax
0x180009e71  jz      loc_180009FE1
0x180009e77  mov     eax, edi
0x180009e79  jmp     loc_180009F8C
0x180009e7e  lea     r8, asc_18002CBE0; "h"
0x180009e85  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180009e8a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009e8f  lea     r8, [rsp+280h+Name]; lpName
0x180009e94  xor     edx, edx; bInheritHandle
0x180009e96  mov     ecx, esi; dwDesiredAccess
0x180009e98  call    cs:__imp_OpenSemaphoreW
0x180009e9e  mov     rdi, rax
0x180009ea1  test    rax, rax
0x180009ea4  jz      loc_180009F39
0x180009eaa  lea     rdx, [rsp+280h+var_260]; int *
0x180009eaf  mov     rcx, rax; hHandle
0x180009eb2  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009eb7  mov     esi, eax
0x180009eb9  test    eax, eax
0x180009ebb  jns     short loc_180009F01
0x180009ebd  mov     rcx, [rbp+188h]; this
0x180009ec4  lea     r8, aWil; "wil"
0x180009ecb  mov     r9d, eax; char *
0x180009ece  mov     edx, 0DEh; void *
0x180009ed3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009ed8  mov     rcx, rdi; hObject
0x180009edb  call    cs:__imp_CloseHandle
0x180009ee1  test    eax, eax
0x180009ee3  jz      loc_180009FF3
0x180009ee9  mov     rcx, rbx; hObject
0x180009eec  call    cs:__imp_CloseHandle
0x180009ef2  test    eax, eax
0x180009ef4  jz      loc_18000A005
0x180009efa  mov     eax, esi
0x180009efc  jmp     loc_180009F8C
0x180009f01  mov     rcx, rdi; hObject
0x180009f04  call    cs:__imp_CloseHandle
0x180009f0a  test    eax, eax
0x180009f0c  jz      loc_180009FAB
0x180009f12  movsxd  rax, [rsp+280h+var_25C]
0x180009f17  movsxd  rcx, [rsp+280h+var_260]
0x180009f1c  shl     rcx, 1Fh
0x180009f20  or      rcx, rax
0x180009f23  mov     [r14], rcx
0x180009f26  mov     rcx, rbx; hObject
0x180009f29  call    cs:__imp_CloseHandle
0x180009f2f  test    eax, eax
0x180009f31  jz      loc_180009FBD
0x180009f37  jmp     short loc_180009F70
0x180009f39  mov     rcx, [rbp+188h]; this
0x180009f40  lea     r8, aWil; "wil"
0x180009f47  mov     edx, 0DCh; void *
0x180009f4c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009f51  mov     rcx, rbx; hObject
0x180009f54  mov     edi, eax
0x180009f56  call    cs:__imp_CloseHandle
0x180009f5c  test    eax, eax
0x180009f5e  jz      short loc_180009FCF
0x180009f60  jmp     loc_180009E77
0x180009f65  call    cs:__imp_GetLastError
0x180009f6b  cmp     eax, 2
0x180009f6e  jnz     short loc_180009F74
0x180009f70  xor     eax, eax
0x180009f72  jmp     short loc_180009F8C
0x180009f74  mov     rcx, [rbp+188h]; this
0x180009f7b  lea     r8, aWil; "wil"
0x180009f82  mov     edx, 0D0h; void *
0x180009f87  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009f8c  mov     rcx, [rbp+180h+var_40]
0x180009f93  xor     rcx, rsp; StackCookie
0x180009f96  call    __security_check_cookie
0x180009f9b  add     rsp, 258h
0x180009fa2  pop     r15
0x180009fa4  pop     r14
0x180009fa6  pop     rdi
0x180009fa7  pop     rsi
0x180009fa8  pop     rbx
0x180009fa9  pop     rbp
0x180009faa  retn
0x180009fab  mov     rcx, [rbp+188h]; this
0x180009fb2  mov     edx, 0A0Bh; void *
0x180009fb7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009fbd  mov     rcx, [rbp+188h]; this
0x180009fc4  mov     edx, 0A0Bh; void *
0x180009fc9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009fcf  mov     rcx, [rbp+188h]; this
0x180009fd6  mov     edx, 0A0Bh; void *
0x180009fdb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009fe1  mov     rcx, [rbp+188h]; this
0x180009fe8  mov     edx, 0A0Bh; void *
0x180009fed  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009ff3  mov     rcx, [rbp+188h]; this
0x180009ffa  mov     edx, 0A0Bh; void *
0x180009fff  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a005  mov     rcx, [rbp+188h]; this
0x18000a00c  mov     edx, 0A0Bh; void *
0x18000a011  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
