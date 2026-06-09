# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x140070b54`
- end: `0x140070da7`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `595`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140071554`

## callees

- `0x14003fd58`
- `0x14004045c`
- `0x1400407f8`
- `0x14006ffac`
- `0x1400709e0`
- `0x140070b54`
- `0x140379070`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140070c04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140070c04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140070d1a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140070d29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140070d4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140070d1a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140070d29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140070d4d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140070bf6`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140070cbf`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140070bf6`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140070cbf`

## string_xrefs

- `0x140070d63`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x140070d7c`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x140070d95`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`

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
  const char *v20; // r9
  const char *v21; // r9
  const char *v22; // r9
  int v23; // [rsp+28h] [rbp-E0h] BYREF
  int v24[3]; // [rsp+2Ch] [rbp-DCh] BYREF
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
  v23 = 0;
  v24[0] = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, &v23);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD3,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v23);
    goto LABEL_13;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18 = v16;
  if ( v16 )
  {
    v19 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, v24);
    LastError = v19;
    if ( v19 >= 0 )
    {
      if ( !CloseHandle(v18) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0x9D1,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
          v21);
      LastError = 0;
      *a3 = v23 | (unsigned __int64)((__int64)v24[0] << 31);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDB,
        (unsigned int)"wil",
        (const char *)(unsigned int)v19,
        v23);
      if ( !CloseHandle(v18) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0x9D1,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
          v20);
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD9, (unsigned int)"wil", v17);
  }
LABEL_22:
  if ( !CloseHandle(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x9D1,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
      v22);
  return LastError;
}

```

## disassembly

```asm
0x140070b54  mov     rax, rsp
0x140070b57  mov     [rax+8], rbx
0x140070b5b  mov     [rax+10h], rsi
0x140070b5f  mov     [rax+20h], rdi
0x140070b63  push    rbp
0x140070b64  push    r14
0x140070b66  push    r15
0x140070b68  lea     rbp, [rax-168h]
0x140070b6f  sub     rsp, 250h
0x140070b76  mov     rax, cs:__security_cookie
0x140070b7d  xor     rax, rsp
0x140070b80  mov     [rbp+160h+var_20], rax
0x140070b87  xor     r15d, r15d
0x140070b8a  lea     rax, [rsp+260h+Name]
0x140070b8f  mov     edi, 104h
0x140070b94  mov     [r8], r15
0x140070b97  mov     r9d, edi
0x140070b9a  lea     rdx, [rsp+260h+Name]
0x140070b9f  sub     rcx, rax
0x140070ba2  mov     r14, r8
0x140070ba5  lea     rax, [r9+7FFFFEFAh]
0x140070bac  test    rax, rax
0x140070baf  jz      short loc_140070BC7
0x140070bb1  movzx   eax, word ptr [rdx+rcx]
0x140070bb5  test    ax, ax
0x140070bb8  jz      short loc_140070BC7
0x140070bba  mov     [rdx], ax
0x140070bbd  add     rdx, 2
0x140070bc1  sub     r9, 1
0x140070bc5  jnz     short loc_140070BA5
0x140070bc7  lea     rax, [rdx-2]
0x140070bcb  test    r9, r9
0x140070bce  lea     r8, aP0; "_p0"
0x140070bd5  cmovnz  rax, rdx
0x140070bd9  lea     rcx, [rsp+260h+Name]; wchar_t *
0x140070bde  mov     rdx, rdi; unsigned __int64
0x140070be1  mov     [rax], r15w
0x140070be5  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140070bea  lea     r8, [rsp+260h+Name]; lpName
0x140070bef  xor     edx, edx; bInheritHandle
0x140070bf1  mov     ecx, 1F0003h; dwDesiredAccess
0x140070bf6  call    cs:__imp_OpenSemaphoreW
0x140070bfc  mov     rsi, rax
0x140070bff  test    rax, rax
0x140070c02  jnz     short loc_140070C30
0x140070c04  call    cs:__imp_GetLastError
0x140070c0a  cmp     eax, 2
0x140070c0d  jnz     short loc_140070C14
0x140070c0f  mov     ebx, r15d
0x140070c12  jmp     short loc_140070C68
0x140070c14  mov     rcx, [rbp+168h]; this
0x140070c1b  lea     r8, aWil; "wil"
0x140070c22  mov     edx, 0CDh; void *
0x140070c27  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140070c2c  mov     ebx, eax
0x140070c2e  jmp     short loc_140070C68
0x140070c30  lea     rdx, [rsp+260h+var_240]; int *
0x140070c35  mov     [rsp+260h+var_240], r15d; int
0x140070c3a  mov     rcx, rsi; hHandle
0x140070c3d  mov     [rsp+260h+var_23C], r15d
0x140070c42  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140070c47  mov     ebx, eax
0x140070c49  test    eax, eax
0x140070c4b  jns     short loc_140070C9F
0x140070c4d  mov     rcx, [rbp+168h]; this
0x140070c54  lea     r8, aWil; "wil"
0x140070c5b  mov     r9d, eax; char *
0x140070c5e  mov     edx, 0D3h; void *
0x140070c63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140070c68  test    rsi, rsi
0x140070c6b  jnz     loc_140070D4A
0x140070c71  mov     eax, ebx
0x140070c73  mov     rcx, [rbp+160h+var_20]
0x140070c7a  xor     rcx, rsp; StackCookie
0x140070c7d  call    __security_check_cookie
0x140070c82  lea     r11, [rsp+260h+var_10]
0x140070c8a  mov     rbx, [r11+20h]
0x140070c8e  mov     rsi, [r11+28h]
0x140070c92  mov     rdi, [r11+38h]
0x140070c96  mov     rsp, r11
0x140070c99  pop     r15
0x140070c9b  pop     r14
0x140070c9d  pop     rbp
0x140070c9e  retn
0x140070c9f  lea     r8, asc_1403FCB6C; "h"
0x140070ca6  mov     rdx, rdi; unsigned __int64
0x140070ca9  lea     rcx, [rsp+260h+Name]; wchar_t *
0x140070cae  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140070cb3  lea     r8, [rsp+260h+Name]; lpName
0x140070cb8  xor     edx, edx; bInheritHandle
0x140070cba  mov     ecx, 1F0003h; dwDesiredAccess
0x140070cbf  call    cs:__imp_OpenSemaphoreW
0x140070cc5  mov     rdi, rax
0x140070cc8  test    rax, rax
0x140070ccb  jnz     short loc_140070CE9
0x140070ccd  mov     rcx, [rbp+168h]; this
0x140070cd4  lea     r8, aWil; "wil"
0x140070cdb  mov     edx, 0D9h; void *
0x140070ce0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140070ce5  mov     ebx, eax
0x140070ce7  jmp     short loc_140070D4A
0x140070ce9  lea     rdx, [rsp+260h+var_23C]; int *
0x140070cee  mov     rcx, rdi; hHandle
0x140070cf1  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140070cf6  mov     ebx, eax
0x140070cf8  test    eax, eax
0x140070cfa  jns     short loc_140070D26
0x140070cfc  mov     rcx, [rbp+168h]; this
0x140070d03  lea     r8, aWil; "wil"
0x140070d0a  mov     r9d, eax; char *
0x140070d0d  mov     edx, 0DBh; void *
0x140070d12  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140070d17  mov     rcx, rdi; hObject
0x140070d1a  call    cs:__imp_CloseHandle
0x140070d20  test    eax, eax
0x140070d22  jz      short loc_140070D75
0x140070d24  jmp     short loc_140070D4A
0x140070d26  mov     rcx, rdi; hObject
0x140070d29  call    cs:__imp_CloseHandle
0x140070d2f  test    eax, eax
0x140070d31  jz      short loc_140070D5C
0x140070d33  movsxd  rcx, [rsp+260h+var_23C]
0x140070d38  mov     ebx, r15d
0x140070d3b  movsxd  rax, [rsp+260h+var_240]
0x140070d40  shl     rcx, 1Fh
0x140070d44  or      rcx, rax
0x140070d47  mov     [r14], rcx
0x140070d4a  mov     rcx, rsi; hObject
0x140070d4d  call    cs:__imp_CloseHandle
0x140070d53  test    eax, eax
0x140070d55  jz      short loc_140070D8E
0x140070d57  jmp     loc_140070C71
0x140070d5c  mov     rcx, [rbp+168h]; this
0x140070d63  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140070d6a  mov     edx, 9D1h; void *
0x140070d6f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140070d75  mov     rcx, [rbp+168h]; this
0x140070d7c  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140070d83  mov     edx, 9D1h; void *
0x140070d88  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140070d8e  mov     rcx, [rbp+168h]; this
0x140070d95  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140070d9c  mov     edx, 9D1h; void *
0x140070da1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
