# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x180014900`
- end: `0x180014bea`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `746`
- prototype: `__int64 __fastcall(const wchar_t *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180015990`

## callees

- `0x180013f70`
- `0x180013f90`
- `0x180013fb0`
- `0x180014780`
- `0x180014900`
- `0x1800181b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180014a11`
- `KERNEL32!GetLastError` at `0x180014a11`
- `KERNEL32!OpenSemaphoreW` at `0x180014a03`
- `KERNEL32!OpenSemaphoreW` at `0x180014b1e`
- `KERNEL32!OpenSemaphoreW` at `0x180014a03`
- `KERNEL32!OpenSemaphoreW` at `0x180014b1e`
- `KERNEL32!CloseHandle` at `0x180014b72`
- `KERNEL32!CloseHandle` at `0x180014b81`
- `KERNEL32!CloseHandle` at `0x180014ba2`
- `KERNEL32!CloseHandle` at `0x180014b72`
- `KERNEL32!CloseHandle` at `0x180014b81`
- `KERNEL32!CloseHandle` at `0x180014ba2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const wchar_t *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned int LastError; // ebp
  __int64 v5; // r9
  WCHAR *v6; // rdx
  signed __int64 v7; // rcx
  WCHAR v9; // ax
  WCHAR *v10; // rax
  __int64 v11; // rcx
  WCHAR *v12; // rax
  __int64 v13; // rsi
  __int64 v14; // rax
  WCHAR *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rax
  char *v18; // r9
  WCHAR v19; // r8
  WCHAR *v20; // rax
  HANDLE v21; // rax
  void *v22; // rbx
  unsigned int v23; // r8d
  const char *v24; // r9
  int ValueFromSemaphore; // eax
  unsigned int v26; // r8d
  int v27; // r14d
  __int64 v29; // rcx
  WCHAR *v30; // rax
  WCHAR *v31; // rdx
  __int64 v32; // rdi
  char *v33; // rcx
  WCHAR v34; // ax
  WCHAR *v35; // rax
  HANDLE v36; // rax
  unsigned int v37; // r8d
  const char *v38; // r9
  void *v39; // rsi
  int v40; // edi
  int v41; // eax
  unsigned int v42; // r8d
  unsigned int v43; // r8d
  const char *v44; // r9
  unsigned int v45; // r8d
  const char *v46; // r9
  unsigned int v47; // r8d
  const char *v48; // r9
  int v49; // [rsp+20h] [rbp-248h] BYREF
  int v50[3]; // [rsp+24h] [rbp-244h] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  LastError = 0;
  *a3 = 0;
  v5 = 260;
  v6 = Name;
  v7 = (char *)a1 - (char *)Name;
  do
  {
    if ( v5 == -2147483386 )
      break;
    v9 = *(WCHAR *)((char *)v6 + v7);
    if ( !v9 )
      break;
    *v6++ = v9;
    --v5;
  }
  while ( v5 );
  v10 = v6 - 1;
  v11 = 260;
  if ( v5 )
    v10 = v6;
  *v10 = 0;
  v12 = Name;
  do
  {
    if ( !*v12 )
      break;
    ++v12;
    --v11;
  }
  while ( v11 );
  v13 = 2147483646;
  v14 = 260 - v11;
  if ( v11 )
  {
    v15 = &Name[v14];
    v16 = 260 - v14;
    if ( v14 != 260 )
    {
      v17 = 2147483646;
      v18 = (char *)((char *)L"_p0" - (char *)v15);
      do
      {
        if ( !v17 )
          break;
        v19 = *(_WORD *)&v18[(_QWORD)v15];
        if ( !v19 )
          break;
        *v15 = v19;
        --v17;
        ++v15;
        --v16;
      }
      while ( v16 );
    }
    v20 = v15 - 1;
    if ( v16 )
      v20 = v15;
    *v20 = 0;
  }
  v21 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v22 = v21;
  if ( !v21 )
  {
    if ( GetLastError() != 2 )
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xCD, v23, v24);
LABEL_24:
    if ( !v22 )
      return LastError;
    goto LABEL_45;
  }
  v49 = 0;
  v50[0] = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v21, &v49);
  v27 = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    _mm_lfence();
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD3, v26, (const char *)(unsigned int)ValueFromSemaphore, v49);
    LastError = v27;
    goto LABEL_24;
  }
  v29 = 260;
  v30 = Name;
  do
  {
    if ( !*v30 )
      break;
    ++v30;
    --v29;
  }
  while ( v29 );
  if ( v29 )
  {
    v31 = &Name[260 - v29];
    v32 = v29;
    v33 = (char *)((char *)L"h" - (char *)v31);
    do
    {
      if ( !v13 )
        break;
      v34 = *(WCHAR *)((char *)v31 + (_QWORD)v33);
      if ( !v34 )
        break;
      *v31 = v34;
      --v13;
      ++v31;
      --v32;
    }
    while ( v32 );
    v35 = v31 - 1;
    if ( v32 )
      v35 = v31;
    *v35 = 0;
  }
  v36 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v39 = v36;
  if ( v36 )
  {
    v41 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v36, v50);
    v40 = v41;
    _mm_lfence();
    if ( v41 >= 0 )
    {
      if ( !CloseHandle(v39) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v45, v46);
      *a3 = v49 | (unsigned __int64)((__int64)v50[0] << 31);
      goto LABEL_45;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDB, v42, (const char *)(unsigned int)v41, v49);
    if ( !CloseHandle(v39) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v43, v44);
  }
  else
  {
    v40 = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD9, v37, v38);
  }
  LastError = v40;
LABEL_45:
  if ( !CloseHandle(v22) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v47, v48);
  return LastError;
}

```

## disassembly

```asm
0x180014900  mov     [rsp+arg_8], rbx
0x180014905  mov     [rsp+arg_18], rbp
0x18001490a  push    rsi
0x18001490b  push    rdi
0x18001490c  push    r15
0x18001490e  sub     rsp, 250h
0x180014915  mov     rax, cs:__security_cookie
0x18001491c  xor     rax, rsp
0x18001491f  mov     [rsp+268h+var_28], rax
0x180014927  xor     ebp, ebp
0x180014929  lea     rax, [rsp+268h+Name]
0x18001492e  mov     edi, 104h
0x180014933  mov     [r8], rbp
0x180014936  mov     r9d, edi
0x180014939  lea     rdx, [rsp+268h+Name]
0x18001493e  sub     rcx, rax
0x180014941  mov     r15, r8
0x180014944  lea     rax, [r9+7FFFFEFAh]
0x18001494b  test    rax, rax
0x18001494e  jz      short loc_180014966
0x180014950  movzx   eax, word ptr [rdx+rcx]
0x180014954  test    ax, ax
0x180014957  jz      short loc_180014966
0x180014959  mov     [rdx], ax
0x18001495c  add     rdx, 2
0x180014960  sub     r9, 1
0x180014964  jnz     short loc_180014944
0x180014966  test    r9, r9
0x180014969  lea     rax, [rdx-2]
0x18001496d  mov     rcx, rdi
0x180014970  cmovnz  rax, rdx
0x180014974  mov     [rax], bp
0x180014977  lea     rax, [rsp+268h+Name]
0x18001497c  nop     dword ptr [rax+00h]
0x180014980  cmp     [rax], bp
0x180014983  jz      short loc_18001498F
0x180014985  add     rax, 2
0x180014989  sub     rcx, 1
0x18001498d  jnz     short loc_180014980
0x18001498f  mov     rax, rdi
0x180014992  mov     esi, 7FFFFFFEh
0x180014997  sub     rax, rcx
0x18001499a  test    rcx, rcx
0x18001499d  cmovz   rax, rbp
0x1800149a1  jz      short loc_1800149EF
0x1800149a3  mov     rdx, rdi
0x1800149a6  lea     rcx, [rsp+268h+Name]
0x1800149ab  lea     rcx, [rcx+rax*2]
0x1800149af  sub     rdx, rax
0x1800149b2  jz      short loc_1800149E1
0x1800149b4  lea     r9, aP0; "_p0"
0x1800149bb  mov     eax, esi
0x1800149bd  sub     r9, rcx
0x1800149c0  test    rax, rax
0x1800149c3  jz      short loc_1800149E1
0x1800149c5  movzx   r8d, word ptr [rcx+r9]
0x1800149ca  test    r8w, r8w
0x1800149ce  jz      short loc_1800149E1
0x1800149d0  mov     [rcx], r8w
0x1800149d4  dec     rax
0x1800149d7  add     rcx, 2
0x1800149db  sub     rdx, 1
0x1800149df  jnz     short loc_1800149C0
0x1800149e1  test    rdx, rdx
0x1800149e4  lea     rax, [rcx-2]
0x1800149e8  cmovnz  rax, rcx
0x1800149ec  mov     [rax], bp
0x1800149ef  lea     r8, [rsp+268h+Name]; lpName
0x1800149f4  mov     [rsp+268h+arg_0], r14
0x1800149fc  xor     edx, edx; bInheritHandle
0x1800149fe  mov     ecx, 1F0003h; dwDesiredAccess
0x180014a03  call    cs:__imp_OpenSemaphoreW
0x180014a09  mov     rbx, rax
0x180014a0c  test    rax, rax
0x180014a0f  jnz     short loc_180014A32
0x180014a11  call    cs:__imp_GetLastError
0x180014a17  cmp     eax, 2
0x180014a1a  jz      short loc_180014A69
0x180014a1c  mov     rcx, [rsp+268h]; this
0x180014a24  mov     edx, 0CDh; void *
0x180014a29  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180014a2e  mov     ebp, eax
0x180014a30  jmp     short loc_180014A69
0x180014a32  lea     rdx, [rsp+268h+var_248]; int *
0x180014a37  mov     [rsp+268h+var_248], ebp; int
0x180014a3b  mov     rcx, rbx; hHandle
0x180014a3e  mov     [rsp+268h+var_244], ebp
0x180014a42  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180014a47  mov     r14d, eax
0x180014a4a  test    eax, eax
0x180014a4c  jns     short loc_180014AA4
0x180014a4e  lfence
0x180014a51  mov     rcx, [rsp+268h]; this
0x180014a59  mov     r9d, eax; char *
0x180014a5c  mov     edx, 0D3h; void *
0x180014a61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014a66  mov     ebp, r14d
0x180014a69  test    rbx, rbx
0x180014a6c  jnz     loc_180014B9F
0x180014a72  mov     r14, [rsp+268h+arg_0]
0x180014a7a  mov     eax, ebp
0x180014a7c  mov     rcx, [rsp+268h+var_28]
0x180014a84  xor     rcx, rsp; StackCookie
0x180014a87  call    __security_check_cookie
0x180014a8c  lea     r11, [rsp+268h+var_18]
0x180014a94  mov     rbx, [r11+28h]
0x180014a98  mov     rbp, [r11+38h]
0x180014a9c  mov     rsp, r11
0x180014a9f  pop     r15
0x180014aa1  pop     rdi
0x180014aa2  pop     rsi
0x180014aa3  retn
0x180014aa4  mov     rcx, rdi
0x180014aa7  lea     rax, [rsp+268h+Name]
0x180014aac  nop     dword ptr [rax+00h]
0x180014ab0  cmp     [rax], bp
0x180014ab3  jz      short loc_180014ABF
0x180014ab5  add     rax, 2
0x180014ab9  sub     rcx, 1
0x180014abd  jnz     short loc_180014AB0
0x180014abf  mov     rax, rdi
0x180014ac2  sub     rax, rcx
0x180014ac5  test    rcx, rcx
0x180014ac8  cmovz   rax, rbp
0x180014acc  jz      short loc_180014B12
0x180014ace  lea     rdx, [rsp+268h+Name]
0x180014ad3  lea     rdx, [rdx+rax*2]
0x180014ad7  sub     rdi, rax
0x180014ada  jz      short loc_180014B04
0x180014adc  lea     rcx, asc_180026148; "h"
0x180014ae3  sub     rcx, rdx
0x180014ae6  test    rsi, rsi
0x180014ae9  jz      short loc_180014B04
0x180014aeb  movzx   eax, word ptr [rcx+rdx]
0x180014aef  test    ax, ax
0x180014af2  jz      short loc_180014B04
0x180014af4  mov     [rdx], ax
0x180014af7  dec     rsi
0x180014afa  add     rdx, 2
0x180014afe  sub     rdi, 1
0x180014b02  jnz     short loc_180014AE6
0x180014b04  test    rdi, rdi
0x180014b07  lea     rax, [rdx-2]
0x180014b0b  cmovnz  rax, rdx
0x180014b0f  mov     [rax], bp
0x180014b12  lea     r8, [rsp+268h+Name]; lpName
0x180014b17  xor     edx, edx; bInheritHandle
0x180014b19  mov     ecx, 1F0003h; dwDesiredAccess
0x180014b1e  call    cs:__imp_OpenSemaphoreW
0x180014b24  mov     rsi, rax
0x180014b27  test    rax, rax
0x180014b2a  jnz     short loc_180014B44
0x180014b2c  mov     rcx, [rsp+268h]; this
0x180014b34  mov     edx, 0D9h; void *
0x180014b39  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180014b3e  mov     edi, eax
0x180014b40  mov     ebp, edi
0x180014b42  jmp     short loc_180014B9F
0x180014b44  lea     rdx, [rsp+268h+var_244]; int *
0x180014b49  mov     rcx, rsi; hHandle
0x180014b4c  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180014b51  mov     edi, eax
0x180014b53  lfence
0x180014b56  test    eax, eax
0x180014b58  jns     short loc_180014B7E
0x180014b5a  mov     rcx, [rsp+268h]; this
0x180014b62  mov     r9d, eax; char *
0x180014b65  mov     edx, 0DBh; void *
0x180014b6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014b6f  mov     rcx, rsi; hObject
0x180014b72  call    cs:__imp_CloseHandle
0x180014b78  test    eax, eax
0x180014b7a  jz      short loc_180014BC4
0x180014b7c  jmp     short loc_180014B40
0x180014b7e  mov     rcx, rsi; hObject
0x180014b81  call    cs:__imp_CloseHandle
0x180014b87  test    eax, eax
0x180014b89  jz      short loc_180014BB1
0x180014b8b  movsxd  rcx, [rsp+268h+var_244]
0x180014b90  movsxd  rax, [rsp+268h+var_248]
0x180014b95  shl     rcx, 1Fh
0x180014b99  or      rcx, rax
0x180014b9c  mov     [r15], rcx
0x180014b9f  mov     rcx, rbx; hObject
0x180014ba2  call    cs:__imp_CloseHandle
0x180014ba8  test    eax, eax
0x180014baa  jz      short loc_180014BD7
0x180014bac  jmp     loc_180014A72
0x180014bb1  mov     rcx, [rsp+268h]; this
0x180014bb9  mov     edx, 9CDh; void *
0x180014bbe  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180014bc4  mov     rcx, [rsp+268h]; this
0x180014bcc  mov     edx, 9CDh; void *
0x180014bd1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180014bd7  mov     rcx, [rsp+268h]; this
0x180014bdf  mov     edx, 9CDh; void *
0x180014be4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
