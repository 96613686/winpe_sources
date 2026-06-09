# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x14006cb6c`
- end: `0x14006cde1`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `629`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1400687a8`
- `0x140068b4c`

## callees

- `0x14000c450`
- `0x14006a094`
- `0x14006bee4`
- `0x14006bf04`
- `0x14006cb6c`
- `0x14006d34c`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x14006cc03`
- `KERNEL32!OpenSemaphoreW` at `0x14006cc7e`
- `KERNEL32!OpenSemaphoreW` at `0x14006cc03`
- `KERNEL32!OpenSemaphoreW` at `0x14006cc7e`
- `KERNEL32!GetLastError` at `0x14006cd36`
- `KERNEL32!GetLastError` at `0x14006cd36`
- `KERNEL32!CloseHandle` at `0x14006cc49`
- `KERNEL32!CloseHandle` at `0x14006ccba`
- `KERNEL32!CloseHandle` at `0x14006cccb`
- `KERNEL32!CloseHandle` at `0x14006cce0`
- `KERNEL32!CloseHandle` at `0x14006cd05`
- `KERNEL32!CloseHandle` at `0x14006cd27`
- `KERNEL32!CloseHandle` at `0x14006cc49`
- `KERNEL32!CloseHandle` at `0x14006ccba`
- `KERNEL32!CloseHandle` at `0x14006cccb`
- `KERNEL32!CloseHandle` at `0x14006cce0`
- `KERNEL32!CloseHandle` at `0x14006cd05`
- `KERNEL32!CloseHandle` at `0x14006cd27`

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
  unsigned int v12; // r8d
  unsigned int LastError; // edi
  unsigned int v14; // r8d
  const char *v15; // r9
  HANDLE v17; // rax
  unsigned int v18; // r8d
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  unsigned int v22; // r8d
  unsigned int v23; // esi
  unsigned int v24; // r8d
  const char *v25; // r9
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
  int v36; // [rsp+20h] [rbp-E0h] BYREF
  int v37[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v34, v35);
    return 0;
  }
  v37[0] = 0;
  v36 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v37);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore, v36);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, 260, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v18, v19);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return LastError;
  }
  v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v36);
  v23 = v21;
  if ( v21 >= 0 )
  {
    if ( !CloseHandle(v20) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    *a3 = v37[0] | (unsigned __int64)((__int64)v36 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v22, (const char *)(unsigned int)v21, v36);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
  return v23;
}

```

## disassembly

```asm
0x14006cb6c  push    rbp
0x14006cb6e  push    rbx
0x14006cb6f  push    rsi
0x14006cb70  push    rdi
0x14006cb71  push    r14
0x14006cb73  push    r15
0x14006cb75  lea     rbp, [rsp-158h]
0x14006cb7d  sub     rsp, 258h
0x14006cb84  mov     rax, cs:__security_cookie
0x14006cb8b  xor     rax, rsp
0x14006cb8e  mov     [rbp+180h+var_40], rax
0x14006cb95  xor     r15d, r15d
0x14006cb98  lea     rax, [rsp+280h+Name]
0x14006cb9d  mov     esi, 104h
0x14006cba2  mov     [r8], r15
0x14006cba5  mov     edx, esi
0x14006cba7  mov     r14, r8
0x14006cbaa  mov     r9d, 7FFFFFFEh
0x14006cbb0  test    r9, r9
0x14006cbb3  jz      short loc_14006CBD4
0x14006cbb5  movzx   r8d, word ptr [rcx]
0x14006cbb9  test    r8w, r8w
0x14006cbbd  jz      short loc_14006CBD4
0x14006cbbf  mov     [rax], r8w
0x14006cbc3  add     rcx, 2
0x14006cbc7  add     rax, 2
0x14006cbcb  dec     r9
0x14006cbce  sub     rdx, 1
0x14006cbd2  jnz     short loc_14006CBB0
0x14006cbd4  test    rdx, rdx
0x14006cbd7  lea     rcx, [rax-2]
0x14006cbdb  lea     r8, aP0; "_p0"
0x14006cbe2  mov     rdx, rsi; unsigned __int64
0x14006cbe5  cmovnz  rcx, rax
0x14006cbe9  mov     [rcx], r15w
0x14006cbed  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14006cbf2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14006cbf7  lea     r8, [rsp+280h+Name]; lpName
0x14006cbfc  xor     edx, edx; bInheritHandle
0x14006cbfe  mov     ecx, 1F0003h; dwDesiredAccess
0x14006cc03  call    cs:__imp_OpenSemaphoreW
0x14006cc09  mov     rbx, rax
0x14006cc0c  test    rax, rax
0x14006cc0f  jz      loc_14006CD36
0x14006cc15  lea     rdx, [rsp+280h+var_25C]; int *
0x14006cc1a  mov     [rsp+280h+var_25C], r15d
0x14006cc1f  mov     rcx, rax; hHandle
0x14006cc22  mov     [rsp+280h+var_260], r15d; int
0x14006cc27  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14006cc2c  mov     edi, eax
0x14006cc2e  test    eax, eax
0x14006cc30  jns     short loc_14006CC5E
0x14006cc32  mov     rcx, [rbp+188h]; this
0x14006cc39  mov     r9d, eax; char *
0x14006cc3c  mov     edx, 0D6h; void *
0x14006cc41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006cc46  mov     rcx, rbx; hObject
0x14006cc49  call    cs:__imp_CloseHandle
0x14006cc4f  test    eax, eax
0x14006cc51  jz      loc_14006CDAB
0x14006cc57  mov     eax, edi
0x14006cc59  jmp     loc_14006CD56
0x14006cc5e  lea     r8, asc_14008F5A4; "h"
0x14006cc65  mov     rdx, rsi; unsigned __int64
0x14006cc68  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14006cc6d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14006cc72  lea     r8, [rsp+280h+Name]; lpName
0x14006cc77  xor     edx, edx; bInheritHandle
0x14006cc79  mov     ecx, 1F0003h; dwDesiredAccess
0x14006cc7e  call    cs:__imp_OpenSemaphoreW
0x14006cc84  mov     rdi, rax
0x14006cc87  test    rax, rax
0x14006cc8a  jz      loc_14006CD11
0x14006cc90  lea     rdx, [rsp+280h+var_260]; int *
0x14006cc95  mov     rcx, rax; hHandle
0x14006cc98  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14006cc9d  mov     esi, eax
0x14006cc9f  test    eax, eax
0x14006cca1  jns     short loc_14006CCDD
0x14006cca3  mov     rcx, [rbp+188h]; this
0x14006ccaa  mov     r9d, eax; char *
0x14006ccad  mov     edx, 0DEh; void *
0x14006ccb2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006ccb7  mov     rcx, rdi; hObject
0x14006ccba  call    cs:__imp_CloseHandle
0x14006ccc0  test    eax, eax
0x14006ccc2  jz      loc_14006CDBD
0x14006ccc8  mov     rcx, rbx; hObject
0x14006cccb  call    cs:__imp_CloseHandle
0x14006ccd1  test    eax, eax
0x14006ccd3  jz      loc_14006CDCF
0x14006ccd9  mov     eax, esi
0x14006ccdb  jmp     short loc_14006CD56
0x14006ccdd  mov     rcx, rdi; hObject
0x14006cce0  call    cs:__imp_CloseHandle
0x14006cce6  test    eax, eax
0x14006cce8  jz      loc_14006CD75
0x14006ccee  movsxd  rax, [rsp+280h+var_25C]
0x14006ccf3  movsxd  rcx, [rsp+280h+var_260]
0x14006ccf8  shl     rcx, 1Fh
0x14006ccfc  or      rcx, rax
0x14006ccff  mov     [r14], rcx
0x14006cd02  mov     rcx, rbx; hObject
0x14006cd05  call    cs:__imp_CloseHandle
0x14006cd0b  test    eax, eax
0x14006cd0d  jz      short loc_14006CD87
0x14006cd0f  jmp     short loc_14006CD41
0x14006cd11  mov     rcx, [rbp+188h]; this
0x14006cd18  mov     edx, 0DCh; void *
0x14006cd1d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14006cd22  mov     rcx, rbx; hObject
0x14006cd25  mov     edi, eax
0x14006cd27  call    cs:__imp_CloseHandle
0x14006cd2d  test    eax, eax
0x14006cd2f  jz      short loc_14006CD99
0x14006cd31  jmp     loc_14006CC57
0x14006cd36  call    cs:__imp_GetLastError
0x14006cd3c  cmp     eax, 2
0x14006cd3f  jnz     short loc_14006CD45
0x14006cd41  xor     eax, eax
0x14006cd43  jmp     short loc_14006CD56
0x14006cd45  mov     rcx, [rbp+188h]; this
0x14006cd4c  mov     edx, 0D0h; void *
0x14006cd51  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14006cd56  mov     rcx, [rbp+180h+var_40]
0x14006cd5d  xor     rcx, rsp; StackCookie
0x14006cd60  call    __security_check_cookie
0x14006cd65  add     rsp, 258h
0x14006cd6c  pop     r15
0x14006cd6e  pop     r14
0x14006cd70  pop     rdi
0x14006cd71  pop     rsi
0x14006cd72  pop     rbx
0x14006cd73  pop     rbp
0x14006cd74  retn
0x14006cd75  mov     rcx, [rbp+188h]; this
0x14006cd7c  mov     edx, 0A0Bh; void *
0x14006cd81  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14006cd87  mov     rcx, [rbp+188h]; this
0x14006cd8e  mov     edx, 0A0Bh; void *
0x14006cd93  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14006cd99  mov     rcx, [rbp+188h]; this
0x14006cda0  mov     edx, 0A0Bh; void *
0x14006cda5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14006cdab  mov     rcx, [rbp+188h]; this
0x14006cdb2  mov     edx, 0A0Bh; void *
0x14006cdb7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14006cdbd  mov     rcx, [rbp+188h]; this
0x14006cdc4  mov     edx, 0A0Bh; void *
0x14006cdc9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14006cdcf  mov     rcx, [rbp+188h]; this
0x14006cdd6  mov     edx, 0A0Bh; void *
0x14006cddb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
