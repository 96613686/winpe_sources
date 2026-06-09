# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1400057fc`
- end: `0x140005a68`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140003258`

## callees

- `0x1400016a0`
- `0x1400041a4`
- `0x140004d94`
- `0x140004db4`
- `0x140005690`
- `0x1400057fc`
- `0x140005bbc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400059bd`
- `KERNEL32!GetLastError` at `0x1400059bd`
- `KERNEL32!OpenSemaphoreW` at `0x140005890`
- `KERNEL32!OpenSemaphoreW` at `0x140005905`
- `KERNEL32!OpenSemaphoreW` at `0x140005890`
- `KERNEL32!OpenSemaphoreW` at `0x140005905`
- `KERNEL32!CloseHandle` at `0x1400058d6`
- `KERNEL32!CloseHandle` at `0x140005941`
- `KERNEL32!CloseHandle` at `0x140005952`
- `KERNEL32!CloseHandle` at `0x140005967`
- `KERNEL32!CloseHandle` at `0x14000598c`
- `KERNEL32!CloseHandle` at `0x1400059ae`
- `KERNEL32!CloseHandle` at `0x1400058d6`
- `KERNEL32!CloseHandle` at `0x140005941`
- `KERNEL32!CloseHandle` at `0x140005952`
- `KERNEL32!CloseHandle` at `0x140005967`
- `KERNEL32!CloseHandle` at `0x14000598c`
- `KERNEL32!CloseHandle` at `0x1400059ae`

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
0x1400057fc  push    rbp
0x1400057fe  push    rbx
0x1400057ff  push    rsi
0x140005800  push    rdi
0x140005801  push    r14
0x140005803  push    r15
0x140005805  lea     rbp, [rsp-158h]
0x14000580d  sub     rsp, 258h
0x140005814  mov     rax, cs:__security_cookie
0x14000581b  xor     rax, rsp
0x14000581e  mov     [rbp+180h+var_40], rax
0x140005825  xor     r15d, r15d
0x140005828  lea     rax, [rsp+280h+Name]
0x14000582d  mov     [r8], r15
0x140005830  mov     r14, r8
0x140005833  mov     edx, 104h
0x140005838  mov     r9d, 7FFFFFFEh
0x14000583e  test    r9, r9
0x140005841  jz      short loc_140005862
0x140005843  movzx   r8d, word ptr [rcx]
0x140005847  test    r8w, r8w
0x14000584b  jz      short loc_140005862
0x14000584d  mov     [rax], r8w
0x140005851  add     rcx, 2
0x140005855  add     rax, 2
0x140005859  dec     r9
0x14000585c  sub     rdx, 1; unsigned __int64
0x140005860  jnz     short loc_14000583E
0x140005862  test    rdx, rdx
0x140005865  lea     rcx, [rax-2]
0x140005869  lea     r8, aP0; "_p0"
0x140005870  cmovnz  rcx, rax
0x140005874  mov     [rcx], r15w
0x140005878  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000587d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140005882  mov     esi, 1F0003h
0x140005887  lea     r8, [rsp+280h+Name]; lpName
0x14000588c  mov     ecx, esi; dwDesiredAccess
0x14000588e  xor     edx, edx; bInheritHandle
0x140005890  call    cs:__imp_OpenSemaphoreW
0x140005896  mov     rbx, rax
0x140005899  test    rax, rax
0x14000589c  jz      loc_1400059BD
0x1400058a2  lea     rdx, [rsp+280h+var_25C]; int *
0x1400058a7  mov     [rsp+280h+var_25C], r15d
0x1400058ac  mov     rcx, rax; hHandle
0x1400058af  mov     [rsp+280h+var_260], r15d; int
0x1400058b4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1400058b9  mov     edi, eax
0x1400058bb  test    eax, eax
0x1400058bd  jns     short loc_1400058EB
0x1400058bf  mov     rcx, [rbp+188h]; this
0x1400058c6  mov     r9d, eax; char *
0x1400058c9  mov     edx, 0D6h; void *
0x1400058ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400058d3  mov     rcx, rbx; hObject
0x1400058d6  call    cs:__imp_CloseHandle
0x1400058dc  test    eax, eax
0x1400058de  jz      loc_140005A32
0x1400058e4  mov     eax, edi
0x1400058e6  jmp     loc_1400059DD
0x1400058eb  lea     r8, asc_140014EA0; "h"
0x1400058f2  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400058f7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400058fc  lea     r8, [rsp+280h+Name]; lpName
0x140005901  xor     edx, edx; bInheritHandle
0x140005903  mov     ecx, esi; dwDesiredAccess
0x140005905  call    cs:__imp_OpenSemaphoreW
0x14000590b  mov     rdi, rax
0x14000590e  test    rax, rax
0x140005911  jz      loc_140005998
0x140005917  lea     rdx, [rsp+280h+var_260]; int *
0x14000591c  mov     rcx, rax; hHandle
0x14000591f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140005924  mov     esi, eax
0x140005926  test    eax, eax
0x140005928  jns     short loc_140005964
0x14000592a  mov     rcx, [rbp+188h]; this
0x140005931  mov     r9d, eax; char *
0x140005934  mov     edx, 0DEh; void *
0x140005939  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000593e  mov     rcx, rdi; hObject
0x140005941  call    cs:__imp_CloseHandle
0x140005947  test    eax, eax
0x140005949  jz      loc_140005A44
0x14000594f  mov     rcx, rbx; hObject
0x140005952  call    cs:__imp_CloseHandle
0x140005958  test    eax, eax
0x14000595a  jz      loc_140005A56
0x140005960  mov     eax, esi
0x140005962  jmp     short loc_1400059DD
0x140005964  mov     rcx, rdi; hObject
0x140005967  call    cs:__imp_CloseHandle
0x14000596d  test    eax, eax
0x14000596f  jz      loc_1400059FC
0x140005975  movsxd  rax, [rsp+280h+var_25C]
0x14000597a  movsxd  rcx, [rsp+280h+var_260]
0x14000597f  shl     rcx, 1Fh
0x140005983  or      rcx, rax
0x140005986  mov     [r14], rcx
0x140005989  mov     rcx, rbx; hObject
0x14000598c  call    cs:__imp_CloseHandle
0x140005992  test    eax, eax
0x140005994  jz      short loc_140005A0E
0x140005996  jmp     short loc_1400059C8
0x140005998  mov     rcx, [rbp+188h]; this
0x14000599f  mov     edx, 0DCh; void *
0x1400059a4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400059a9  mov     rcx, rbx; hObject
0x1400059ac  mov     edi, eax
0x1400059ae  call    cs:__imp_CloseHandle
0x1400059b4  test    eax, eax
0x1400059b6  jz      short loc_140005A20
0x1400059b8  jmp     loc_1400058E4
0x1400059bd  call    cs:__imp_GetLastError
0x1400059c3  cmp     eax, 2
0x1400059c6  jnz     short loc_1400059CC
0x1400059c8  xor     eax, eax
0x1400059ca  jmp     short loc_1400059DD
0x1400059cc  mov     rcx, [rbp+188h]; this
0x1400059d3  mov     edx, 0D0h; void *
0x1400059d8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400059dd  mov     rcx, [rbp+180h+var_40]
0x1400059e4  xor     rcx, rsp; StackCookie
0x1400059e7  call    __security_check_cookie
0x1400059ec  add     rsp, 258h
0x1400059f3  pop     r15
0x1400059f5  pop     r14
0x1400059f7  pop     rdi
0x1400059f8  pop     rsi
0x1400059f9  pop     rbx
0x1400059fa  pop     rbp
0x1400059fb  retn
0x1400059fc  mov     rcx, [rbp+188h]; this
0x140005a03  mov     edx, 0A0Bh; void *
0x140005a08  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005a0e  mov     rcx, [rbp+188h]; this
0x140005a15  mov     edx, 0A0Bh; void *
0x140005a1a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005a20  mov     rcx, [rbp+188h]; this
0x140005a27  mov     edx, 0A0Bh; void *
0x140005a2c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005a32  mov     rcx, [rbp+188h]; this
0x140005a39  mov     edx, 0A0Bh; void *
0x140005a3e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005a44  mov     rcx, [rbp+188h]; this
0x140005a4b  mov     edx, 0A0Bh; void *
0x140005a50  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005a56  mov     rcx, [rbp+188h]; this
0x140005a5d  mov     edx, 0A0Bh; void *
0x140005a62  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
