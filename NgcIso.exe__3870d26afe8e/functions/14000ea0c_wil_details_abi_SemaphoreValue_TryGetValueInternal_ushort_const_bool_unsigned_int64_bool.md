# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x14000ea0c`
- end: `0x14000ebca`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `446`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14000e1c0`

## callees

- `0x14000e034`
- `0x14000ea0c`
- `0x14000ebd0`
- `0x14000ec5c`
- `0x14000ec88`
- `0x14000ede0`
- `0x14000ee38`
- `0x14000f6a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ea85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ea85`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000ea77`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000eb17`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000ea77`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000eb17`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_PCNZWCH pszSrc,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  wil::details *v5; // rax
  wil::details *v6; // rdi
  const char *v7; // r9
  int ValueFromSemaphore; // eax
  unsigned int LastError; // ebx
  void *v11; // rdx
  wil::details *v12; // rax
  const char *v13; // r9
  wil::details *v14; // rbx
  int v15; // eax
  void *v16; // rdx
  int v17; // esi
  void *v18; // rdx
  size_t v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+30h] [rbp-D0h] BYREF
  int v22[3]; // [rsp+34h] [rbp-CCh] BYREF
  wchar_t pszDest[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v19);
  StringCchCatW(pszDest, 0x104u, L"_p0");
  v5 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v6 = v5;
  if ( v5 )
  {
    v22[0] = 0;
    v21 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, v22);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore >= 0 )
    {
      StringCchCatW(pszDest, 0x104u, L"h");
      v12 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
      v14 = v12;
      if ( v12 )
      {
        v15 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v21);
        v17 = v15;
        if ( v15 >= 0 )
        {
          wil::details::CloseHandle(v14, v16);
          *a3 = v22[0] | (unsigned __int64)((__int64)v21 << 31);
          LastError = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xDE,
            (unsigned int)"wil",
            (const char *)(unsigned int)v15,
            v20);
          wil::details::CloseHandle(v14, v18);
          LastError = v17;
        }
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v13);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v20);
    }
    wil::details::CloseHandle(v6, v11);
    return LastError;
  }
  else if ( GetLastError() == 2 )
  {
    return 0;
  }
  else
  {
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v7);
  }
}

```

## disassembly

```asm
0x14000ea0c  mov     [rsp-8+arg_8], rbx
0x14000ea11  mov     [rsp-8+arg_18], rsi
0x14000ea16  push    rbp
0x14000ea17  push    rdi
0x14000ea18  push    r14
0x14000ea1a  lea     rbp, [rsp-160h]
0x14000ea22  sub     rsp, 260h
0x14000ea29  mov     rax, cs:__security_cookie
0x14000ea30  xor     rax, rsp
0x14000ea33  mov     [rbp+170h+var_20], rax
0x14000ea3a  mov     r9, rcx; pszSrc
0x14000ea3d  mov     qword ptr [r8], 0
0x14000ea44  mov     esi, 104h
0x14000ea49  lea     rcx, [rsp+270h+pszDest]; pszDest
0x14000ea4e  mov     edx, esi; cchDest
0x14000ea50  mov     r14, r8
0x14000ea53  call    StringCopyWorkerW
0x14000ea58  lea     r8, aP0; "_p0"
0x14000ea5f  mov     edx, esi; unsigned __int64
0x14000ea61  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x14000ea66  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000ea6b  lea     r8, [rsp+270h+pszDest]; lpName
0x14000ea70  xor     edx, edx; bInheritHandle
0x14000ea72  mov     ecx, 1F0003h; dwDesiredAccess
0x14000ea77  call    cs:__imp_OpenSemaphoreW
0x14000ea7d  mov     rdi, rax
0x14000ea80  test    rax, rax
0x14000ea83  jnz     short loc_14000EAB4
0x14000ea85  call    cs:__imp_GetLastError
0x14000ea8b  cmp     eax, 2
0x14000ea8e  jnz     short loc_14000EA97
0x14000ea90  xor     eax, eax
0x14000ea92  jmp     loc_14000EBA3
0x14000ea97  mov     rcx, [rbp+178h]; this
0x14000ea9e  lea     r8, aWil; "wil"
0x14000eaa5  mov     edx, 0D0h; void *
0x14000eaaa  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000eaaf  jmp     loc_14000EBA3
0x14000eab4  lea     rdx, [rsp+270h+var_23C]; int *
0x14000eab9  mov     [rsp+270h+var_23C], 0
0x14000eac1  mov     rcx, rdi; hHandle
0x14000eac4  mov     [rsp+270h+var_240], 0
0x14000eacc  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000ead1  mov     ebx, eax
0x14000ead3  test    eax, eax
0x14000ead5  jns     short loc_14000EAF7
0x14000ead7  mov     rcx, [rbp+178h]; this
0x14000eade  lea     r8, aWil; "wil"
0x14000eae5  mov     r9d, eax; char *
0x14000eae8  mov     edx, 0D6h; void *
0x14000eaed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000eaf2  jmp     loc_14000EB99
0x14000eaf7  lea     r8, asc_140079670; "h"
0x14000eafe  mov     rdx, rsi; unsigned __int64
0x14000eb01  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x14000eb06  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000eb0b  lea     r8, [rsp+270h+pszDest]; lpName
0x14000eb10  xor     edx, edx; bInheritHandle
0x14000eb12  mov     ecx, 1F0003h; dwDesiredAccess
0x14000eb17  call    cs:__imp_OpenSemaphoreW
0x14000eb1d  mov     rbx, rax
0x14000eb20  test    rax, rax
0x14000eb23  jnz     short loc_14000EB41
0x14000eb25  mov     rcx, [rbp+178h]; this
0x14000eb2c  lea     r8, aWil; "wil"
0x14000eb33  mov     edx, 0DCh; void *
0x14000eb38  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000eb3d  mov     ebx, eax
0x14000eb3f  jmp     short loc_14000EB99
0x14000eb41  lea     rdx, [rsp+270h+var_240]; int *
0x14000eb46  mov     rcx, rbx; hHandle
0x14000eb49  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000eb4e  mov     esi, eax
0x14000eb50  test    eax, eax
0x14000eb52  jns     short loc_14000EB7B
0x14000eb54  mov     rcx, [rbp+178h]; this
0x14000eb5b  lea     r8, aWil; "wil"
0x14000eb62  mov     r9d, eax; char *
0x14000eb65  mov     edx, 0DEh; void *
0x14000eb6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000eb6f  mov     rcx, rbx; this
0x14000eb72  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x14000eb77  mov     ebx, esi
0x14000eb79  jmp     short loc_14000EB99
0x14000eb7b  mov     rcx, rbx; this
0x14000eb7e  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x14000eb83  movsxd  rcx, [rsp+270h+var_240]
0x14000eb88  movsxd  rax, [rsp+270h+var_23C]
0x14000eb8d  shl     rcx, 1Fh
0x14000eb91  or      rcx, rax
0x14000eb94  mov     [r14], rcx
0x14000eb97  xor     ebx, ebx
0x14000eb99  mov     rcx, rdi; this
0x14000eb9c  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x14000eba1  mov     eax, ebx
0x14000eba3  mov     rcx, [rbp+170h+var_20]
0x14000ebaa  xor     rcx, rsp; StackCookie
0x14000ebad  call    __security_check_cookie
0x14000ebb2  lea     r11, [rsp+270h+var_10]
0x14000ebba  mov     rbx, [r11+28h]
0x14000ebbe  mov     rsi, [r11+38h]
0x14000ebc2  mov     rsp, r11
0x14000ebc5  pop     r14
0x14000ebc7  pop     rdi
0x14000ebc8  pop     rbp
0x14000ebc9  retn
```
