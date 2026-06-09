# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x140008ff8`
- end: `0x140009236`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `574`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14000a69c`

## callees

- `0x140007610`
- `0x140008de4`
- `0x140008e08`
- `0x140008e28`
- `0x140008e84`
- `0x140008ff8`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400090a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400090a8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000909a`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140009163`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000909a`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140009163`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400091be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400091cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400091f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400091be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400091cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400091f1`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const wchar_t *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  __int64 v4; // r9
  WCHAR *v5; // rdx
  signed __int64 v6; // rcx
  WCHAR v8; // ax
  WCHAR *v9; // rax
  HANDLE v10; // rax
  void *v11; // rsi
  const char *v12; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  HANDLE v16; // rax
  const char *v17; // r9
  void *v18; // rdi
  int v19; // eax
  unsigned int v20; // r8d
  const char *v21; // r9
  unsigned int v22; // r8d
  const char *v23; // r9
  unsigned int v24; // r8d
  const char *v25; // r9
  int v26; // [rsp+28h] [rbp-E0h] BYREF
  int v27[3]; // [rsp+2Ch] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+38h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+270h] [rbp+168h]

  *a3 = 0;
  v4 = 260;
  v5 = Name;
  v6 = (char *)a1 - (char *)Name;
  do
  {
    if ( v4 == -2147483386 )
      break;
    v8 = *(WCHAR *)((char *)v5 + v6);
    if ( !v8 )
      break;
    *v5++ = v8;
    --v4;
  }
  while ( v4 );
  v9 = v5 - 1;
  if ( v4 )
    v9 = v5;
  *v9 = 0;
  StringCchCatW(Name, 0x104u, L"_p0");
  v10 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v11 = v10;
  if ( !v10 )
  {
    if ( GetLastError() == 2 )
      LastError = 0;
    else
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xCD, (unsigned int)"wil", v12);
LABEL_13:
    if ( !v11 )
      return LastError;
    goto LABEL_22;
  }
  v26 = 0;
  v27[0] = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, &v26);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD3,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v26);
    goto LABEL_13;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18 = v16;
  if ( v16 )
  {
    v19 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, v27);
    LastError = v19;
    if ( v19 >= 0 )
    {
      if ( !CloseHandle(v18) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v22, v23);
      LastError = 0;
      *a3 = v26 | (unsigned __int64)((__int64)v27[0] << 31);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDB,
        (unsigned int)"wil",
        (const char *)(unsigned int)v19,
        v26);
      if ( !CloseHandle(v18) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v20, v21);
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD9, (unsigned int)"wil", v17);
  }
LABEL_22:
  if ( !CloseHandle(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v24, v25);
  return LastError;
}

```

## disassembly

```asm
0x140008ff8  mov     rax, rsp
0x140008ffb  mov     [rax+8], rbx
0x140008fff  mov     [rax+10h], rsi
0x140009003  mov     [rax+20h], rdi
0x140009007  push    rbp
0x140009008  push    r14
0x14000900a  push    r15
0x14000900c  lea     rbp, [rax-168h]
0x140009013  sub     rsp, 250h
0x14000901a  mov     rax, cs:__security_cookie
0x140009021  xor     rax, rsp
0x140009024  mov     [rbp+160h+var_20], rax
0x14000902b  xor     r15d, r15d
0x14000902e  lea     rax, [rsp+260h+Name]
0x140009033  mov     edi, 104h
0x140009038  mov     [r8], r15
0x14000903b  mov     r9d, edi
0x14000903e  lea     rdx, [rsp+260h+Name]
0x140009043  sub     rcx, rax
0x140009046  mov     r14, r8
0x140009049  lea     rax, [r9+7FFFFEFAh]
0x140009050  test    rax, rax
0x140009053  jz      short loc_14000906B
0x140009055  movzx   eax, word ptr [rdx+rcx]
0x140009059  test    ax, ax
0x14000905c  jz      short loc_14000906B
0x14000905e  mov     [rdx], ax
0x140009061  add     rdx, 2
0x140009065  sub     r9, 1
0x140009069  jnz     short loc_140009049
0x14000906b  lea     rax, [rdx-2]
0x14000906f  test    r9, r9
0x140009072  lea     r8, aP0; "_p0"
0x140009079  cmovnz  rax, rdx
0x14000907d  lea     rcx, [rsp+260h+Name]; wchar_t *
0x140009082  mov     rdx, rdi; unsigned __int64
0x140009085  mov     [rax], r15w
0x140009089  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x14000908e  lea     r8, [rsp+260h+Name]; lpName
0x140009093  xor     edx, edx; bInheritHandle
0x140009095  mov     ecx, 1F0003h; dwDesiredAccess
0x14000909a  call    cs:__imp_OpenSemaphoreW
0x1400090a0  mov     rsi, rax
0x1400090a3  test    rax, rax
0x1400090a6  jnz     short loc_1400090D4
0x1400090a8  call    cs:__imp_GetLastError
0x1400090ae  cmp     eax, 2
0x1400090b1  jnz     short loc_1400090B8
0x1400090b3  mov     ebx, r15d
0x1400090b6  jmp     short loc_14000910C
0x1400090b8  mov     rcx, [rbp+168h]; this
0x1400090bf  lea     r8, aWil; "wil"
0x1400090c6  mov     edx, 0CDh; void *
0x1400090cb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400090d0  mov     ebx, eax
0x1400090d2  jmp     short loc_14000910C
0x1400090d4  lea     rdx, [rsp+260h+var_240]; int *
0x1400090d9  mov     [rsp+260h+var_240], r15d; int
0x1400090de  mov     rcx, rsi; hHandle
0x1400090e1  mov     [rsp+260h+var_23C], r15d
0x1400090e6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1400090eb  mov     ebx, eax
0x1400090ed  test    eax, eax
0x1400090ef  jns     short loc_140009143
0x1400090f1  mov     rcx, [rbp+168h]; this
0x1400090f8  lea     r8, aWil; "wil"
0x1400090ff  mov     r9d, eax; char *
0x140009102  mov     edx, 0D3h; void *
0x140009107  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000910c  test    rsi, rsi
0x14000910f  jnz     loc_1400091EE
0x140009115  mov     eax, ebx
0x140009117  mov     rcx, [rbp+160h+var_20]
0x14000911e  xor     rcx, rsp; StackCookie
0x140009121  call    __security_check_cookie
0x140009126  lea     r11, [rsp+260h+var_10]
0x14000912e  mov     rbx, [r11+20h]
0x140009132  mov     rsi, [r11+28h]
0x140009136  mov     rdi, [r11+38h]
0x14000913a  mov     rsp, r11
0x14000913d  pop     r15
0x14000913f  pop     r14
0x140009141  pop     rbp
0x140009142  retn
0x140009143  lea     r8, asc_140053918; "h"
0x14000914a  mov     rdx, rdi; unsigned __int64
0x14000914d  lea     rcx, [rsp+260h+Name]; wchar_t *
0x140009152  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140009157  lea     r8, [rsp+260h+Name]; lpName
0x14000915c  xor     edx, edx; bInheritHandle
0x14000915e  mov     ecx, 1F0003h; dwDesiredAccess
0x140009163  call    cs:__imp_OpenSemaphoreW
0x140009169  mov     rdi, rax
0x14000916c  test    rax, rax
0x14000916f  jnz     short loc_14000918D
0x140009171  mov     rcx, [rbp+168h]; this
0x140009178  lea     r8, aWil; "wil"
0x14000917f  mov     edx, 0D9h; void *
0x140009184  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140009189  mov     ebx, eax
0x14000918b  jmp     short loc_1400091EE
0x14000918d  lea     rdx, [rsp+260h+var_23C]; int *
0x140009192  mov     rcx, rdi; hHandle
0x140009195  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000919a  mov     ebx, eax
0x14000919c  test    eax, eax
0x14000919e  jns     short loc_1400091CA
0x1400091a0  mov     rcx, [rbp+168h]; this
0x1400091a7  lea     r8, aWil; "wil"
0x1400091ae  mov     r9d, eax; char *
0x1400091b1  mov     edx, 0DBh; void *
0x1400091b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400091bb  mov     rcx, rdi; hObject
0x1400091be  call    cs:__imp_CloseHandle
0x1400091c4  test    eax, eax
0x1400091c6  jz      short loc_140009212
0x1400091c8  jmp     short loc_1400091EE
0x1400091ca  mov     rcx, rdi; hObject
0x1400091cd  call    cs:__imp_CloseHandle
0x1400091d3  test    eax, eax
0x1400091d5  jz      short loc_140009200
0x1400091d7  movsxd  rcx, [rsp+260h+var_23C]
0x1400091dc  mov     ebx, r15d
0x1400091df  movsxd  rax, [rsp+260h+var_240]
0x1400091e4  shl     rcx, 1Fh
0x1400091e8  or      rcx, rax
0x1400091eb  mov     [r14], rcx
0x1400091ee  mov     rcx, rsi; hObject
0x1400091f1  call    cs:__imp_CloseHandle
0x1400091f7  test    eax, eax
0x1400091f9  jz      short loc_140009224
0x1400091fb  jmp     loc_140009115
0x140009200  mov     rcx, [rbp+168h]; this
0x140009207  mov     edx, 9D1h; void *
0x14000920c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140009212  mov     rcx, [rbp+168h]; this
0x140009219  mov     edx, 9D1h; void *
0x14000921e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140009224  mov     rcx, [rbp+168h]; this
0x14000922b  mov     edx, 9D1h; void *
0x140009230  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
