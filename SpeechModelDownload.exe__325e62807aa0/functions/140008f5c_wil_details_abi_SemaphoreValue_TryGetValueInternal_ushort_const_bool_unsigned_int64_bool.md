# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140008f5c`
- end: `0x1400091f4`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `664`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140005150`
- `0x14000b964`

## callees

- `0x140002600`
- `0x140006c68`
- `0x140007da8`
- `0x140007dc8`
- `0x140008dd4`
- `0x140008f5c`
- `0x1400093f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140008ff3`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140009075`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140008ff3`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140009075`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009142`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009142`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009040`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400090b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400090c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400090e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009106`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009133`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009040`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400090b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400090c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400090e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009106`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009133`

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
  const char *v17; // r9
  void *v18; // rdi
  int v19; // eax
  unsigned int v20; // esi
  __int64 v21; // r8
  const char *v22; // r9
  __int64 v23; // r8
  const char *v24; // r9
  __int64 v25; // r8
  const char *v26; // r9
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  const char *v31; // r9
  int v32; // [rsp+20h] [rbp-E0h] BYREF
  int v33[3]; // [rsp+24h] [rbp-DCh] BYREF
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
  StringCchCatW(Name, 0x104u, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v31);
    return 0;
  }
  v33[0] = 0;
  v32 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v33);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, (int)"wil", (const char *)(unsigned int)ValueFromSemaphore);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v14);
    return LastError;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18 = v16;
  if ( !v16 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v17);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    return LastError;
  }
  v19 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, &v32);
  v20 = v19;
  if ( v19 >= 0 )
  {
    if ( !CloseHandle(v18) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
    *a3 = v33[0] | (unsigned __int64)((__int64)v32 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v19);
  if ( !CloseHandle(v18) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v21, v22);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  return v20;
}

```

## disassembly

```asm
0x140008f5c  push    rbp
0x140008f5e  push    rbx
0x140008f5f  push    rsi
0x140008f60  push    rdi
0x140008f61  push    r14
0x140008f63  push    r15
0x140008f65  lea     rbp, [rsp-158h]
0x140008f6d  sub     rsp, 258h
0x140008f74  mov     rax, cs:__security_cookie
0x140008f7b  xor     rax, rsp
0x140008f7e  mov     [rbp+180h+var_40], rax
0x140008f85  xor     r15d, r15d
0x140008f88  lea     rax, [rsp+280h+Name]
0x140008f8d  mov     esi, 104h
0x140008f92  mov     [r8], r15
0x140008f95  mov     edx, esi
0x140008f97  mov     r14, r8
0x140008f9a  mov     r9d, 7FFFFFFEh
0x140008fa0  test    r9, r9
0x140008fa3  jz      short loc_140008FC4
0x140008fa5  movzx   r8d, word ptr [rcx]
0x140008fa9  test    r8w, r8w
0x140008fad  jz      short loc_140008FC4
0x140008faf  mov     [rax], r8w
0x140008fb3  add     rcx, 2
0x140008fb7  add     rax, 2
0x140008fbb  dec     r9
0x140008fbe  sub     rdx, 1
0x140008fc2  jnz     short loc_140008FA0
0x140008fc4  test    rdx, rdx
0x140008fc7  lea     rcx, [rax-2]
0x140008fcb  lea     r8, aP0; "_p0"
0x140008fd2  mov     rdx, rsi; unsigned __int64
0x140008fd5  cmovnz  rcx, rax
0x140008fd9  mov     [rcx], r15w
0x140008fdd  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140008fe2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140008fe7  lea     r8, [rsp+280h+Name]; lpName
0x140008fec  xor     edx, edx; bInheritHandle
0x140008fee  mov     ecx, 1F0003h; dwDesiredAccess
0x140008ff3  call    cs:__imp_OpenSemaphoreW
0x140008ff9  mov     rbx, rax
0x140008ffc  test    rax, rax
0x140008fff  jz      loc_140009142
0x140009005  lea     rdx, [rsp+280h+var_25C]; int *
0x14000900a  mov     [rsp+280h+var_25C], r15d
0x14000900f  mov     rcx, rax; hHandle
0x140009012  mov     [rsp+280h+var_260], r15d; int
0x140009017  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000901c  mov     edi, eax
0x14000901e  test    eax, eax
0x140009020  jns     short loc_140009055
0x140009022  mov     rcx, [rbp+188h]; this
0x140009029  lea     r8, aWil; "wil"
0x140009030  mov     r9d, eax; char *
0x140009033  mov     edx, 0D6h; void *
0x140009038  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000903d  mov     rcx, rbx; hObject
0x140009040  call    cs:__imp_CloseHandle
0x140009046  test    eax, eax
0x140009048  jz      loc_1400091BE
0x14000904e  mov     eax, edi
0x140009050  jmp     loc_140009169
0x140009055  lea     r8, asc_14001F2F0; "h"
0x14000905c  mov     rdx, rsi; unsigned __int64
0x14000905f  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140009064  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140009069  lea     r8, [rsp+280h+Name]; lpName
0x14000906e  xor     edx, edx; bInheritHandle
0x140009070  mov     ecx, 1F0003h; dwDesiredAccess
0x140009075  call    cs:__imp_OpenSemaphoreW
0x14000907b  mov     rdi, rax
0x14000907e  test    rax, rax
0x140009081  jz      loc_140009116
0x140009087  lea     rdx, [rsp+280h+var_260]; int *
0x14000908c  mov     rcx, rax; hHandle
0x14000908f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140009094  mov     esi, eax
0x140009096  test    eax, eax
0x140009098  jns     short loc_1400090DE
0x14000909a  mov     rcx, [rbp+188h]; this
0x1400090a1  lea     r8, aWil; "wil"
0x1400090a8  mov     r9d, eax; char *
0x1400090ab  mov     edx, 0DEh; void *
0x1400090b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400090b5  mov     rcx, rdi; hObject
0x1400090b8  call    cs:__imp_CloseHandle
0x1400090be  test    eax, eax
0x1400090c0  jz      loc_1400091D0
0x1400090c6  mov     rcx, rbx; hObject
0x1400090c9  call    cs:__imp_CloseHandle
0x1400090cf  test    eax, eax
0x1400090d1  jz      loc_1400091E2
0x1400090d7  mov     eax, esi
0x1400090d9  jmp     loc_140009169
0x1400090de  mov     rcx, rdi; hObject
0x1400090e1  call    cs:__imp_CloseHandle
0x1400090e7  test    eax, eax
0x1400090e9  jz      loc_140009188
0x1400090ef  movsxd  rax, [rsp+280h+var_25C]
0x1400090f4  movsxd  rcx, [rsp+280h+var_260]
0x1400090f9  shl     rcx, 1Fh
0x1400090fd  or      rcx, rax
0x140009100  mov     [r14], rcx
0x140009103  mov     rcx, rbx; hObject
0x140009106  call    cs:__imp_CloseHandle
0x14000910c  test    eax, eax
0x14000910e  jz      loc_14000919A
0x140009114  jmp     short loc_14000914D
0x140009116  mov     rcx, [rbp+188h]; this
0x14000911d  lea     r8, aWil; "wil"
0x140009124  mov     edx, 0DCh; void *
0x140009129  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000912e  mov     rcx, rbx; hObject
0x140009131  mov     edi, eax
0x140009133  call    cs:__imp_CloseHandle
0x140009139  test    eax, eax
0x14000913b  jz      short loc_1400091AC
0x14000913d  jmp     loc_14000904E
0x140009142  call    cs:__imp_GetLastError
0x140009148  cmp     eax, 2
0x14000914b  jnz     short loc_140009151
0x14000914d  xor     eax, eax
0x14000914f  jmp     short loc_140009169
0x140009151  mov     rcx, [rbp+188h]; this
0x140009158  lea     r8, aWil; "wil"
0x14000915f  mov     edx, 0D0h; void *
0x140009164  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140009169  mov     rcx, [rbp+180h+var_40]
0x140009170  xor     rcx, rsp; StackCookie
0x140009173  call    __security_check_cookie
0x140009178  add     rsp, 258h
0x14000917f  pop     r15
0x140009181  pop     r14
0x140009183  pop     rdi
0x140009184  pop     rsi
0x140009185  pop     rbx
0x140009186  pop     rbp
0x140009187  retn
0x140009188  mov     rcx, [rbp+188h]; this
0x14000918f  mov     edx, 0A0Bh; void *
0x140009194  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000919a  mov     rcx, [rbp+188h]; this
0x1400091a1  mov     edx, 0A0Bh; void *
0x1400091a6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400091ac  mov     rcx, [rbp+188h]; this
0x1400091b3  mov     edx, 0A0Bh; void *
0x1400091b8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400091be  mov     rcx, [rbp+188h]; this
0x1400091c5  mov     edx, 0A0Bh; void *
0x1400091ca  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400091d0  mov     rcx, [rbp+188h]; this
0x1400091d7  mov     edx, 0A0Bh; void *
0x1400091dc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400091e2  mov     rcx, [rbp+188h]; this
0x1400091e9  mov     edx, 0A0Bh; void *
0x1400091ee  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
