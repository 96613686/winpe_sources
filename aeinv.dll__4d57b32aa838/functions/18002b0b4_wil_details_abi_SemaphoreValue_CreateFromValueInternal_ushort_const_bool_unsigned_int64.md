# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18002b0b4`
- end: `0x18002b25e`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `426`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002ad5c`
- `0x18003de88`

## callees

- `0x180007420`
- `0x18002b0b4`
- `0x18003eeec`
- `0x18003f184`
- `0x180040658`
- `0x1800407d8`
- `0x18004f970`
- `0x180059920`
- `0x1800679c4`

## import_xrefs

- `KERNEL32!CreateSemaphoreExW` at `0x18002b1b0`
- `KERNEL32!CreateSemaphoreExW` at `0x18002b1b0`
- `KERNEL32!GetLastError` at `0x18002b1e9`
- `KERNEL32!GetLastError` at `0x18002b1e9`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        WCHAR *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  WCHAR *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // r8
  unsigned int v10; // edi
  bool v11; // zf
  WCHAR *v12; // rcx
  __int64 v13; // r8
  WCHAR *v14; // rax
  __int64 v15; // r9
  LONG v16; // r8d
  wil::details *v17; // rcx
  HANDLE Semaphore; // rbx
  __int64 v19; // rdx
  int LastErrorFailHr; // ebx
  __int64 v21; // rdx
  unsigned __int64 v23; // rsi
  size_t dwFlags; // [rsp+20h] [rbp-258h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-258h]
  WCHAR Name[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  v7 = Name;
  v8 = 2147483646;
  v9 = 260;
  v10 = 1;
  do
  {
    if ( !v8 )
      break;
    if ( !*a2 )
      break;
    *v7++ = *a2++;
    --v8;
    --v9;
  }
  while ( v9 );
  v11 = v9 == 0;
  v12 = v7 - 1;
  v13 = 260;
  if ( !v11 )
    v12 = v7;
  v14 = Name;
  *v12 = 0;
  do
  {
    if ( !*v14 )
      break;
    ++v14;
    --v13;
  }
  while ( v13 );
  if ( v13 )
  {
    v15 = (260 - v13) & -(__int64)(v13 != 0);
    StringCopyWorkerW(&Name[v15], 260 - v15, 0, L"_p0", dwFlags);
  }
  v16 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v16 = a4 & 0x7FFFFFFF;
  Semaphore = CreateSemaphoreExW(0, a4 & 0x7FFFFFFF, v16, Name, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      this,
      Semaphore);
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v17);
    if ( LastErrorFailHr < 0 )
    {
      v21 = 139;
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"wil",
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlagsa);
      return (unsigned int)LastErrorFailHr;
    }
  }
  v23 = a4 >> 31;
  StringCchCatW(Name, v19, L"h");
  if ( (_DWORD)v23 )
    v10 = v23;
  LastErrorFailHr = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
                      (char *)this + 8,
                      (unsigned int)v23,
                      v10,
                      Name);
  if ( LastErrorFailHr < 0 )
  {
    v21 = 144;
    goto LABEL_19;
  }
  return 0;
}

```

## disassembly

```asm
0x18002b0b4  mov     [rsp+arg_8], rbx
0x18002b0b9  mov     [rsp+arg_10], rbp
0x18002b0be  push    rsi
0x18002b0bf  push    rdi
0x18002b0c0  push    r14
0x18002b0c2  sub     rsp, 260h
0x18002b0c9  mov     rax, cs:__security_cookie
0x18002b0d0  xor     rax, rsp
0x18002b0d3  mov     [rsp+278h+var_28], rax
0x18002b0db  mov     rax, 0C000000000000000h
0x18002b0e5  mov     rsi, r9
0x18002b0e8  mov     r10, rdx
0x18002b0eb  mov     rbp, rcx
0x18002b0ee  test    rax, r9
0x18002b0f1  jz      short loc_18002B0F9
0x18002b0f3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18002b0f9  xor     r14d, r14d
0x18002b0fc  lea     rax, [rsp+278h+Name]
0x18002b101  mov     edx, 104h
0x18002b106  mov     ecx, 7FFFFFFEh
0x18002b10b  mov     r8d, edx
0x18002b10e  lea     edi, [r14+1]
0x18002b112  test    rcx, rcx
0x18002b115  jz      short loc_18002B135
0x18002b117  movzx   r9d, word ptr [r10]
0x18002b11b  test    r9w, r9w
0x18002b11f  jz      short loc_18002B135
0x18002b121  mov     [rax], r9w
0x18002b125  add     r10, 2
0x18002b129  add     rax, 2
0x18002b12d  sub     rcx, rdi
0x18002b130  sub     r8, rdi
0x18002b133  jnz     short loc_18002B112
0x18002b135  test    r8, r8
0x18002b138  lea     rcx, [rax-2]
0x18002b13c  mov     r8, rdx
0x18002b13f  cmovnz  rcx, rax
0x18002b143  lea     rax, [rsp+278h+Name]
0x18002b148  mov     [rcx], r14w
0x18002b14c  cmp     [rax], r14w
0x18002b150  jz      short loc_18002B15B
0x18002b152  add     rax, 2
0x18002b156  sub     r8, rdi
0x18002b159  jnz     short loc_18002B14C
0x18002b15b  mov     rcx, rdx
0x18002b15e  mov     rax, r8
0x18002b161  sub     rcx, r8
0x18002b164  neg     rax
0x18002b167  sbb     r9, r9
0x18002b16a  and     r9, rcx
0x18002b16d  test    r8, r8
0x18002b170  jz      short loc_18002B18D
0x18002b172  sub     rdx, r9; cchDest
0x18002b175  lea     rcx, [rsp+278h+Name]
0x18002b17a  lea     rcx, [rcx+r9*2]; pszDest
0x18002b17e  xor     r8d, r8d; pcchNewDestLength
0x18002b181  lea     r9, aP0; "_p0"
0x18002b188  call    StringCopyWorkerW
0x18002b18d  mov     edx, esi
0x18002b18f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18002b197  and     edx, 7FFFFFFFh; lInitialCount
0x18002b19d  mov     dword ptr [rsp+278h+dwFlags], r14d; int
0x18002b1a2  mov     r8d, edi
0x18002b1a5  lea     r9, [rsp+278h+Name]; lpName
0x18002b1aa  cmova   r8d, edx; lMaximumCount
0x18002b1ae  xor     ecx, ecx; lpSemaphoreAttributes
0x18002b1b0  call    cs:__imp_CreateSemaphoreExW
0x18002b1b6  mov     rbx, rax
0x18002b1b9  test    rax, rax
0x18002b1bc  jnz     short loc_18002B1E9
0x18002b1be  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002b1c3  mov     ebx, eax
0x18002b1c5  test    eax, eax
0x18002b1c7  jns     short loc_18002B1FA
0x18002b1c9  mov     edx, 8Bh; void *
0x18002b1ce  mov     rcx, [rsp+278h]; this
0x18002b1d6  lea     r8, aWil; "wil"
0x18002b1dd  mov     r9d, ebx; char *
0x18002b1e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b1e5  mov     eax, ebx
0x18002b1e7  jmp     short loc_18002B236
0x18002b1e9  call    cs:__imp_GetLastError
0x18002b1ef  mov     rdx, rbx
0x18002b1f2  mov     rcx, rbp
0x18002b1f5  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18002b1fa  lea     r8, asc_18013B62C; "h"
0x18002b201  shr     rsi, 1Fh
0x18002b205  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18002b20a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002b20f  test    esi, esi
0x18002b211  lea     rcx, [rbp+8]
0x18002b215  lea     r9, [rsp+278h+Name]
0x18002b21a  mov     edx, esi
0x18002b21c  cmovnz  edi, esi
0x18002b21f  mov     r8d, edi
0x18002b222  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18002b227  mov     ebx, eax
0x18002b229  test    eax, eax
0x18002b22b  jns     short loc_18002B234
0x18002b22d  mov     edx, 90h
0x18002b232  jmp     short loc_18002B1CE
0x18002b234  xor     eax, eax
0x18002b236  mov     rcx, [rsp+278h+var_28]
0x18002b23e  xor     rcx, rsp; StackCookie
0x18002b241  call    __security_check_cookie
0x18002b246  lea     r11, [rsp+278h+var_18]
0x18002b24e  mov     rbx, [r11+28h]
0x18002b252  mov     rbp, [r11+30h]
0x18002b256  mov     rsp, r11
0x18002b259  pop     r14
0x18002b25b  pop     rdi
0x18002b25c  pop     rsi
0x18002b25d  retn
```
