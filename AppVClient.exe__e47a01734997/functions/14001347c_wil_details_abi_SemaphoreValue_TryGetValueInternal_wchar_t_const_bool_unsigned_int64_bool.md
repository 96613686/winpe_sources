# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x14001347c`
- end: `0x1400136e8`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140009d54`
- `0x14005f364`

## callees

- `0x140004280`
- `0x14000d528`
- `0x140011544`
- `0x140011564`
- `0x140013260`
- `0x14001347c`
- `0x140013c58`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140013556`
- `KERNEL32!CloseHandle` at `0x1400135c1`
- `KERNEL32!CloseHandle` at `0x1400135d2`
- `KERNEL32!CloseHandle` at `0x1400135e7`
- `KERNEL32!CloseHandle` at `0x14001360c`
- `KERNEL32!CloseHandle` at `0x14001362e`
- `KERNEL32!CloseHandle` at `0x140013556`
- `KERNEL32!CloseHandle` at `0x1400135c1`
- `KERNEL32!CloseHandle` at `0x1400135d2`
- `KERNEL32!CloseHandle` at `0x1400135e7`
- `KERNEL32!CloseHandle` at `0x14001360c`
- `KERNEL32!CloseHandle` at `0x14001362e`
- `KERNEL32!OpenSemaphoreW` at `0x140013510`
- `KERNEL32!OpenSemaphoreW` at `0x140013585`
- `KERNEL32!OpenSemaphoreW` at `0x140013510`
- `KERNEL32!OpenSemaphoreW` at `0x140013585`
- `KERNEL32!GetLastError` at `0x14001363d`
- `KERNEL32!GetLastError` at `0x14001363d`

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
0x14001347c  push    rbp
0x14001347e  push    rbx
0x14001347f  push    rsi
0x140013480  push    rdi
0x140013481  push    r14
0x140013483  push    r15
0x140013485  lea     rbp, [rsp-158h]
0x14001348d  sub     rsp, 258h
0x140013494  mov     rax, cs:__security_cookie
0x14001349b  xor     rax, rsp
0x14001349e  mov     [rbp+180h+var_40], rax
0x1400134a5  xor     r15d, r15d
0x1400134a8  lea     rax, [rsp+280h+Name]
0x1400134ad  mov     [r8], r15
0x1400134b0  mov     r14, r8
0x1400134b3  mov     edx, 104h
0x1400134b8  mov     r9d, 7FFFFFFEh
0x1400134be  test    r9, r9
0x1400134c1  jz      short loc_1400134E2
0x1400134c3  movzx   r8d, word ptr [rcx]
0x1400134c7  test    r8w, r8w
0x1400134cb  jz      short loc_1400134E2
0x1400134cd  mov     [rax], r8w
0x1400134d1  add     rcx, 2
0x1400134d5  add     rax, 2
0x1400134d9  dec     r9
0x1400134dc  sub     rdx, 1; unsigned __int64
0x1400134e0  jnz     short loc_1400134BE
0x1400134e2  test    rdx, rdx
0x1400134e5  lea     rcx, [rax-2]
0x1400134e9  lea     r8, aP0; "_p0"
0x1400134f0  cmovnz  rcx, rax
0x1400134f4  mov     [rcx], r15w
0x1400134f8  lea     rcx, [rsp+280h+Name]; wchar_t *
0x1400134fd  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140013502  mov     esi, 1F0003h
0x140013507  lea     r8, [rsp+280h+Name]; lpName
0x14001350c  mov     ecx, esi; dwDesiredAccess
0x14001350e  xor     edx, edx; bInheritHandle
0x140013510  call    cs:__imp_OpenSemaphoreW
0x140013516  mov     rbx, rax
0x140013519  test    rax, rax
0x14001351c  jz      loc_14001363D
0x140013522  lea     rdx, [rsp+280h+var_25C]; int *
0x140013527  mov     [rsp+280h+var_25C], r15d
0x14001352c  mov     rcx, rax; hHandle
0x14001352f  mov     [rsp+280h+var_260], r15d; int
0x140013534  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140013539  mov     edi, eax
0x14001353b  test    eax, eax
0x14001353d  jns     short loc_14001356B
0x14001353f  mov     rcx, [rbp+188h]; this
0x140013546  mov     r9d, eax; char *
0x140013549  mov     edx, 0D6h; void *
0x14001354e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140013553  mov     rcx, rbx; hObject
0x140013556  call    cs:__imp_CloseHandle
0x14001355c  test    eax, eax
0x14001355e  jz      loc_1400136B2
0x140013564  mov     eax, edi
0x140013566  jmp     loc_14001365D
0x14001356b  lea     r8, asc_1400853D8; "h"
0x140013572  lea     rcx, [rsp+280h+Name]; wchar_t *
0x140013577  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x14001357c  lea     r8, [rsp+280h+Name]; lpName
0x140013581  xor     edx, edx; bInheritHandle
0x140013583  mov     ecx, esi; dwDesiredAccess
0x140013585  call    cs:__imp_OpenSemaphoreW
0x14001358b  mov     rdi, rax
0x14001358e  test    rax, rax
0x140013591  jz      loc_140013618
0x140013597  lea     rdx, [rsp+280h+var_260]; int *
0x14001359c  mov     rcx, rax; hHandle
0x14001359f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1400135a4  mov     esi, eax
0x1400135a6  test    eax, eax
0x1400135a8  jns     short loc_1400135E4
0x1400135aa  mov     rcx, [rbp+188h]; this
0x1400135b1  mov     r9d, eax; char *
0x1400135b4  mov     edx, 0DEh; void *
0x1400135b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400135be  mov     rcx, rdi; hObject
0x1400135c1  call    cs:__imp_CloseHandle
0x1400135c7  test    eax, eax
0x1400135c9  jz      loc_1400136C4
0x1400135cf  mov     rcx, rbx; hObject
0x1400135d2  call    cs:__imp_CloseHandle
0x1400135d8  test    eax, eax
0x1400135da  jz      loc_1400136D6
0x1400135e0  mov     eax, esi
0x1400135e2  jmp     short loc_14001365D
0x1400135e4  mov     rcx, rdi; hObject
0x1400135e7  call    cs:__imp_CloseHandle
0x1400135ed  test    eax, eax
0x1400135ef  jz      loc_14001367C
0x1400135f5  movsxd  rax, [rsp+280h+var_25C]
0x1400135fa  movsxd  rcx, [rsp+280h+var_260]
0x1400135ff  shl     rcx, 1Fh
0x140013603  or      rcx, rax
0x140013606  mov     [r14], rcx
0x140013609  mov     rcx, rbx; hObject
0x14001360c  call    cs:__imp_CloseHandle
0x140013612  test    eax, eax
0x140013614  jz      short loc_14001368E
0x140013616  jmp     short loc_140013648
0x140013618  mov     rcx, [rbp+188h]; this
0x14001361f  mov     edx, 0DCh; void *
0x140013624  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140013629  mov     rcx, rbx; hObject
0x14001362c  mov     edi, eax
0x14001362e  call    cs:__imp_CloseHandle
0x140013634  test    eax, eax
0x140013636  jz      short loc_1400136A0
0x140013638  jmp     loc_140013564
0x14001363d  call    cs:__imp_GetLastError
0x140013643  cmp     eax, 2
0x140013646  jnz     short loc_14001364C
0x140013648  xor     eax, eax
0x14001364a  jmp     short loc_14001365D
0x14001364c  mov     rcx, [rbp+188h]; this
0x140013653  mov     edx, 0D0h; void *
0x140013658  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14001365d  mov     rcx, [rbp+180h+var_40]
0x140013664  xor     rcx, rsp; StackCookie
0x140013667  call    __security_check_cookie
0x14001366c  add     rsp, 258h
0x140013673  pop     r15
0x140013675  pop     r14
0x140013677  pop     rdi
0x140013678  pop     rsi
0x140013679  pop     rbx
0x14001367a  pop     rbp
0x14001367b  retn
0x14001367c  mov     rcx, [rbp+188h]; this
0x140013683  mov     edx, 0A0Bh; void *
0x140013688  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14001368e  mov     rcx, [rbp+188h]; this
0x140013695  mov     edx, 0A0Bh; void *
0x14001369a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400136a0  mov     rcx, [rbp+188h]; this
0x1400136a7  mov     edx, 0A0Bh; void *
0x1400136ac  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400136b2  mov     rcx, [rbp+188h]; this
0x1400136b9  mov     edx, 0A0Bh; void *
0x1400136be  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400136c4  mov     rcx, [rbp+188h]; this
0x1400136cb  mov     edx, 0A0Bh; void *
0x1400136d0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400136d6  mov     rcx, [rbp+188h]; this
0x1400136dd  mov     edx, 0A0Bh; void *
0x1400136e2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
