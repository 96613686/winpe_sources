# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x18002eb70`
- end: `0x18002ee78`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `776`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800300f0`

## callees

- `0x180010a50`
- `0x180010df0`
- `0x18002e1e0`
- `0x18002e9c0`
- `0x18002eb70`
- `0x180034ef0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002ec81`
- `KERNEL32!GetLastError` at `0x18002ec81`
- `KERNEL32!CloseHandle` at `0x18002ee00`
- `KERNEL32!CloseHandle` at `0x18002ee0f`
- `KERNEL32!CloseHandle` at `0x18002ee30`
- `KERNEL32!CloseHandle` at `0x18002ee00`
- `KERNEL32!CloseHandle` at `0x18002ee0f`
- `KERNEL32!CloseHandle` at `0x18002ee30`
- `KERNEL32!OpenSemaphoreW` at `0x18002ec73`
- `KERNEL32!OpenSemaphoreW` at `0x18002ed9e`
- `KERNEL32!OpenSemaphoreW` at `0x18002ec73`
- `KERNEL32!OpenSemaphoreW` at `0x18002ed9e`

## pseudocode

```c
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
  const char *v23; // r9
  int ValueFromSemaphore; // eax
  int v25; // r14d
  __int64 v27; // rcx
  WCHAR *v28; // rax
  WCHAR *v29; // rdx
  __int64 v30; // rdi
  char *v31; // rcx
  WCHAR v32; // ax
  WCHAR *v33; // rax
  HANDLE v34; // rax
  const char *v35; // r9
  void *v36; // rsi
  int v37; // edi
  int v38; // eax
  unsigned int v39; // r8d
  const char *v40; // r9
  unsigned int v41; // r8d
  const char *v42; // r9
  unsigned int v43; // r8d
  const char *v44; // r9
  int v45; // [rsp+20h] [rbp-248h] BYREF
  int v46[3]; // [rsp+24h] [rbp-244h] BYREF
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
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xCD, (unsigned int)"wil", v23);
LABEL_24:
    if ( !v22 )
      return LastError;
    goto LABEL_45;
  }
  v45 = 0;
  v46[0] = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v21, &v45);
  v25 = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    _mm_lfence();
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD3,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v45);
    LastError = v25;
    goto LABEL_24;
  }
  v27 = 260;
  v28 = Name;
  do
  {
    if ( !*v28 )
      break;
    ++v28;
    --v27;
  }
  while ( v27 );
  if ( v27 )
  {
    v29 = &Name[260 - v27];
    v30 = v27;
    v31 = (char *)((char *)L"h" - (char *)v29);
    do
    {
      if ( !v13 )
        break;
      v32 = *(WCHAR *)((char *)v29 + (_QWORD)v31);
      if ( !v32 )
        break;
      *v29 = v32;
      --v13;
      ++v29;
      --v30;
    }
    while ( v30 );
    v33 = v29 - 1;
    if ( v30 )
      v33 = v29;
    *v33 = 0;
  }
  v34 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v36 = v34;
  if ( v34 )
  {
    v38 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v34, v46);
    v37 = v38;
    _mm_lfence();
    if ( v38 >= 0 )
    {
      if ( !CloseHandle(v36) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v41, v42);
      *a3 = v45 | (unsigned __int64)((__int64)v46[0] << 31);
      goto LABEL_45;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDB, (unsigned int)"wil", (const char *)(unsigned int)v38, v45);
    if ( !CloseHandle(v36) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v39, v40);
  }
  else
  {
    v37 = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD9, (unsigned int)"wil", v35);
  }
  LastError = v37;
LABEL_45:
  if ( !CloseHandle(v22) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v43, v44);
  return LastError;
}

```

## disassembly

```asm
0x18002eb70  mov     [rsp+arg_8], rbx
0x18002eb75  mov     [rsp+arg_18], rbp
0x18002eb7a  push    rsi
0x18002eb7b  push    rdi
0x18002eb7c  push    r15
0x18002eb7e  sub     rsp, 250h
0x18002eb85  mov     rax, cs:__security_cookie
0x18002eb8c  xor     rax, rsp
0x18002eb8f  mov     [rsp+268h+var_28], rax
0x18002eb97  xor     ebp, ebp
0x18002eb99  lea     rax, [rsp+268h+Name]
0x18002eb9e  mov     edi, 104h
0x18002eba3  mov     [r8], rbp
0x18002eba6  mov     r9d, edi
0x18002eba9  lea     rdx, [rsp+268h+Name]
0x18002ebae  sub     rcx, rax
0x18002ebb1  mov     r15, r8
0x18002ebb4  lea     rax, [r9+7FFFFEFAh]
0x18002ebbb  test    rax, rax
0x18002ebbe  jz      short loc_18002EBD6
0x18002ebc0  movzx   eax, word ptr [rdx+rcx]
0x18002ebc4  test    ax, ax
0x18002ebc7  jz      short loc_18002EBD6
0x18002ebc9  mov     [rdx], ax
0x18002ebcc  add     rdx, 2
0x18002ebd0  sub     r9, 1
0x18002ebd4  jnz     short loc_18002EBB4
0x18002ebd6  test    r9, r9
0x18002ebd9  lea     rax, [rdx-2]
0x18002ebdd  mov     rcx, rdi
0x18002ebe0  cmovnz  rax, rdx
0x18002ebe4  mov     [rax], bp
0x18002ebe7  lea     rax, [rsp+268h+Name]
0x18002ebec  nop     dword ptr [rax+00h]
0x18002ebf0  cmp     [rax], bp
0x18002ebf3  jz      short loc_18002EBFF
0x18002ebf5  add     rax, 2
0x18002ebf9  sub     rcx, 1
0x18002ebfd  jnz     short loc_18002EBF0
0x18002ebff  mov     rax, rdi
0x18002ec02  mov     esi, 7FFFFFFEh
0x18002ec07  sub     rax, rcx
0x18002ec0a  test    rcx, rcx
0x18002ec0d  cmovz   rax, rbp
0x18002ec11  jz      short loc_18002EC5F
0x18002ec13  mov     rdx, rdi
0x18002ec16  lea     rcx, [rsp+268h+Name]
0x18002ec1b  lea     rcx, [rcx+rax*2]
0x18002ec1f  sub     rdx, rax
0x18002ec22  jz      short loc_18002EC51
0x18002ec24  lea     r9, aP0; "_p0"
0x18002ec2b  mov     eax, esi
0x18002ec2d  sub     r9, rcx
0x18002ec30  test    rax, rax
0x18002ec33  jz      short loc_18002EC51
0x18002ec35  movzx   r8d, word ptr [rcx+r9]
0x18002ec3a  test    r8w, r8w
0x18002ec3e  jz      short loc_18002EC51
0x18002ec40  mov     [rcx], r8w
0x18002ec44  dec     rax
0x18002ec47  add     rcx, 2
0x18002ec4b  sub     rdx, 1
0x18002ec4f  jnz     short loc_18002EC30
0x18002ec51  test    rdx, rdx
0x18002ec54  lea     rax, [rcx-2]
0x18002ec58  cmovnz  rax, rcx
0x18002ec5c  mov     [rax], bp
0x18002ec5f  lea     r8, [rsp+268h+Name]; lpName
0x18002ec64  mov     [rsp+268h+arg_0], r14
0x18002ec6c  xor     edx, edx; bInheritHandle
0x18002ec6e  mov     ecx, 1F0003h; dwDesiredAccess
0x18002ec73  call    cs:__imp_OpenSemaphoreW
0x18002ec79  mov     rbx, rax
0x18002ec7c  test    rax, rax
0x18002ec7f  jnz     short loc_18002ECA9
0x18002ec81  call    cs:__imp_GetLastError
0x18002ec87  cmp     eax, 2
0x18002ec8a  jz      short loc_18002ECE7
0x18002ec8c  mov     rcx, [rsp+268h]; this
0x18002ec94  lea     r8, aWil; "wil"
0x18002ec9b  mov     edx, 0CDh; void *
0x18002eca0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002eca5  mov     ebp, eax
0x18002eca7  jmp     short loc_18002ECE7
0x18002eca9  lea     rdx, [rsp+268h+var_248]; int *
0x18002ecae  mov     [rsp+268h+var_248], ebp; int
0x18002ecb2  mov     rcx, rbx; hHandle
0x18002ecb5  mov     [rsp+268h+var_244], ebp
0x18002ecb9  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002ecbe  mov     r14d, eax
0x18002ecc1  test    eax, eax
0x18002ecc3  jns     short loc_18002ED22
0x18002ecc5  lfence
0x18002ecc8  mov     rcx, [rsp+268h]; this
0x18002ecd0  lea     r8, aWil; "wil"
0x18002ecd7  mov     r9d, eax; char *
0x18002ecda  mov     edx, 0D3h; void *
0x18002ecdf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ece4  mov     ebp, r14d
0x18002ece7  test    rbx, rbx
0x18002ecea  jnz     loc_18002EE2D
0x18002ecf0  mov     r14, [rsp+268h+arg_0]
0x18002ecf8  mov     eax, ebp
0x18002ecfa  mov     rcx, [rsp+268h+var_28]
0x18002ed02  xor     rcx, rsp; StackCookie
0x18002ed05  call    __security_check_cookie
0x18002ed0a  lea     r11, [rsp+268h+var_18]
0x18002ed12  mov     rbx, [r11+28h]
0x18002ed16  mov     rbp, [r11+38h]
0x18002ed1a  mov     rsp, r11
0x18002ed1d  pop     r15
0x18002ed1f  pop     rdi
0x18002ed20  pop     rsi
0x18002ed21  retn
0x18002ed22  mov     rcx, rdi
0x18002ed25  lea     rax, [rsp+268h+Name]
0x18002ed2a  nop     word ptr [rax+rax+00h]
0x18002ed30  cmp     [rax], bp
0x18002ed33  jz      short loc_18002ED3F
0x18002ed35  add     rax, 2
0x18002ed39  sub     rcx, 1
0x18002ed3d  jnz     short loc_18002ED30
0x18002ed3f  mov     rax, rdi
0x18002ed42  sub     rax, rcx
0x18002ed45  test    rcx, rcx
0x18002ed48  cmovz   rax, rbp
0x18002ed4c  jz      short loc_18002ED92
0x18002ed4e  lea     rdx, [rsp+268h+Name]
0x18002ed53  lea     rdx, [rdx+rax*2]
0x18002ed57  sub     rdi, rax
0x18002ed5a  jz      short loc_18002ED84
0x18002ed5c  lea     rcx, asc_18004BBE8; "h"
0x18002ed63  sub     rcx, rdx
0x18002ed66  test    rsi, rsi
0x18002ed69  jz      short loc_18002ED84
0x18002ed6b  movzx   eax, word ptr [rcx+rdx]
0x18002ed6f  test    ax, ax
0x18002ed72  jz      short loc_18002ED84
0x18002ed74  mov     [rdx], ax
0x18002ed77  dec     rsi
0x18002ed7a  add     rdx, 2
0x18002ed7e  sub     rdi, 1
0x18002ed82  jnz     short loc_18002ED66
0x18002ed84  test    rdi, rdi
0x18002ed87  lea     rax, [rdx-2]
0x18002ed8b  cmovnz  rax, rdx
0x18002ed8f  mov     [rax], bp
0x18002ed92  lea     r8, [rsp+268h+Name]; lpName
0x18002ed97  xor     edx, edx; bInheritHandle
0x18002ed99  mov     ecx, 1F0003h; dwDesiredAccess
0x18002ed9e  call    cs:__imp_OpenSemaphoreW
0x18002eda4  mov     rsi, rax
0x18002eda7  test    rax, rax
0x18002edaa  jnz     short loc_18002EDCB
0x18002edac  mov     rcx, [rsp+268h]; this
0x18002edb4  lea     r8, aWil; "wil"
0x18002edbb  mov     edx, 0D9h; void *
0x18002edc0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002edc5  mov     edi, eax
0x18002edc7  mov     ebp, edi
0x18002edc9  jmp     short loc_18002EE2D
0x18002edcb  lea     rdx, [rsp+268h+var_244]; int *
0x18002edd0  mov     rcx, rsi; hHandle
0x18002edd3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002edd8  mov     edi, eax
0x18002edda  lfence
0x18002eddd  test    eax, eax
0x18002eddf  jns     short loc_18002EE0C
0x18002ede1  mov     rcx, [rsp+268h]; this
0x18002ede9  lea     r8, aWil; "wil"
0x18002edf0  mov     r9d, eax; char *
0x18002edf3  mov     edx, 0DBh; void *
0x18002edf8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002edfd  mov     rcx, rsi; hObject
0x18002ee00  call    cs:__imp_CloseHandle
0x18002ee06  test    eax, eax
0x18002ee08  jz      short loc_18002EE52
0x18002ee0a  jmp     short loc_18002EDC7
0x18002ee0c  mov     rcx, rsi; hObject
0x18002ee0f  call    cs:__imp_CloseHandle
0x18002ee15  test    eax, eax
0x18002ee17  jz      short loc_18002EE3F
0x18002ee19  movsxd  rcx, [rsp+268h+var_244]
0x18002ee1e  movsxd  rax, [rsp+268h+var_248]
0x18002ee23  shl     rcx, 1Fh
0x18002ee27  or      rcx, rax
0x18002ee2a  mov     [r15], rcx
0x18002ee2d  mov     rcx, rbx; hObject
0x18002ee30  call    cs:__imp_CloseHandle
0x18002ee36  test    eax, eax
0x18002ee38  jz      short loc_18002EE65
0x18002ee3a  jmp     loc_18002ECF0
0x18002ee3f  mov     rcx, [rsp+268h]; this
0x18002ee47  mov     edx, 9CDh; void *
0x18002ee4c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002ee52  mov     rcx, [rsp+268h]; this
0x18002ee5a  mov     edx, 9CDh; void *
0x18002ee5f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002ee65  mov     rcx, [rsp+268h]; this
0x18002ee6d  mov     edx, 9CDh; void *
0x18002ee72  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
