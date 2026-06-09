# wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)

- ea: `0x140009c54`
- end: `0x140009e11`
- name: `?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z`
- size: `445`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140005330`
- `0x1400056f4`

## callees

- `0x140009c54`
- `0x14000f8a4`
- `0x14001d240`
- `0x14001f668`
- `0x140020fe8`
- `0x1400213a8`
- `0x140080d70`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140009d54`
- `KERNEL32!GetLastError` at `0x140009dc6`
- `KERNEL32!GetLastError` at `0x140009d54`
- `KERNEL32!GetLastError` at `0x140009dc6`
- `KERNEL32!CreateSemaphoreExW` at `0x140009d1b`
- `KERNEL32!CreateSemaphoreExW` at `0x140009d9d`
- `KERNEL32!CreateSemaphoreExW` at `0x140009d1b`
- `KERNEL32!CreateSemaphoreExW` at `0x140009d9d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromPointer(
        wil::details_abi::SemaphoreValue *this,
        char *a2,
        unsigned __int64 a3)
{
  unsigned __int64 v4; // rbx
  signed __int64 v5; // r8
  WCHAR *v6; // rcx
  __int64 v7; // rdx
  LONG v8; // edi
  WCHAR v9; // ax
  WCHAR *v10; // rax
  LONG v11; // r8d
  unsigned __int64 v12; // rbp
  LONG v13; // ebx
  wil::details *v14; // rcx
  HANDLE Semaphore; // rbx
  int LastErrorFailHr; // eax
  unsigned int v17; // r8d
  unsigned int v18; // ebx
  __int64 v19; // rdx
  wil::details *v20; // rcx
  HANDLE v21; // rbx
  DWORD dwFlags; // [rsp+20h] [rbp-258h]
  WCHAR Name[264]; // [rsp+30h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a3 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  v4 = a3 >> 2;
  v5 = a2 - (char *)Name;
  v6 = Name;
  v7 = 260;
  v8 = 1;
  do
  {
    if ( v7 == -2147483386 )
      break;
    v9 = *(WCHAR *)((char *)v6 + v5);
    if ( !v9 )
      break;
    *v6++ = v9;
    --v7;
  }
  while ( v7 );
  v10 = v6 - 1;
  if ( v7 )
    v10 = v6;
  *v10 = 0;
  StringCchCatW(Name, 0x104u, L"_p0");
  v11 = 1;
  v12 = v4 >> 31;
  v13 = v4 & 0x7FFFFFFF;
  if ( v13 )
    v11 = v13;
  Semaphore = CreateSemaphoreExW(0, v13, v11, Name, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      this,
      Semaphore);
LABEL_15:
    StringCchCatW(Name, 0x104u, L"h");
    if ( (_DWORD)v12 )
      v8 = v12;
    v21 = CreateSemaphoreExW(0, v12, v8, Name, 0, 0x1F0003u);
    if ( v21 )
    {
      GetLastError();
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        (char *)this + 8,
        v21);
    }
    else
    {
      LastErrorFailHr = wil::details::GetLastErrorFailHr(v20);
      v18 = LastErrorFailHr;
      if ( LastErrorFailHr < 0 )
      {
        v19 = 141;
        goto LABEL_13;
      }
    }
    return 0;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v14);
  v18 = LastErrorFailHr;
  if ( LastErrorFailHr >= 0 )
    goto LABEL_15;
  v19 = 136;
LABEL_13:
  wil::details::in1diag3::Return_Hr(retaddr, (void *)v19, v17, (const char *)(unsigned int)LastErrorFailHr, dwFlags);
  return v18;
}

```

## disassembly

```asm
0x140009c54  mov     [rsp+arg_8], rbx
0x140009c59  push    rbp
0x140009c5a  push    rsi
0x140009c5b  push    rdi
0x140009c5c  push    r14
0x140009c5e  push    r15
0x140009c60  sub     rsp, 250h
0x140009c67  mov     rax, cs:__security_cookie
0x140009c6e  xor     rax, rsp
0x140009c71  mov     [rsp+278h+var_38], rax
0x140009c79  mov     rbx, r8
0x140009c7c  mov     rsi, rcx
0x140009c7f  mov     r8, rdx
0x140009c82  test    bl, 3
0x140009c85  jnz     loc_140009E0B
0x140009c8b  lea     rax, [rsp+278h+Name]
0x140009c90  shr     rbx, 2
0x140009c94  sub     r8, rax
0x140009c97  lea     rcx, [rsp+278h+Name]
0x140009c9c  xor     r14d, r14d
0x140009c9f  mov     r15d, 104h
0x140009ca5  mov     edx, r15d
0x140009ca8  lea     edi, [r14+1]
0x140009cac  lea     rax, [rdx+7FFFFEFAh]
0x140009cb3  test    rax, rax
0x140009cb6  jz      short loc_140009CCE
0x140009cb8  movzx   eax, word ptr [rcx+r8]
0x140009cbd  test    ax, ax
0x140009cc0  jz      short loc_140009CCE
0x140009cc2  mov     [rcx], ax
0x140009cc5  add     rcx, 2
0x140009cc9  sub     rdx, rdi
0x140009ccc  jnz     short loc_140009CAC
0x140009cce  test    rdx, rdx
0x140009cd1  lea     rax, [rcx-2]
0x140009cd5  lea     r8, aP0; "_p0"
0x140009cdc  mov     rdx, r15; unsigned __int64
0x140009cdf  cmovnz  rax, rcx
0x140009ce3  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140009ce8  mov     [rax], r14w
0x140009cec  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140009cf1  mov     rbp, rbx
0x140009cf4  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140009cfc  mov     r8d, edi
0x140009cff  shr     rbp, 1Fh
0x140009d03  and     ebx, 7FFFFFFFh
0x140009d09  mov     [rsp+278h+dwFlags], r14d; int
0x140009d0e  lea     r9, [rsp+278h+Name]; lpName
0x140009d13  mov     edx, ebx; lInitialCount
0x140009d15  cmova   r8d, ebx; lMaximumCount
0x140009d19  xor     ecx, ecx; lpSemaphoreAttributes
0x140009d1b  call    cs:__imp_CreateSemaphoreExW
0x140009d22  nop     dword ptr [rax+rax+00h]
0x140009d27  mov     rbx, rax
0x140009d2a  test    rax, rax
0x140009d2d  jnz     short loc_140009D54
0x140009d2f  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140009d34  mov     ebx, eax
0x140009d36  test    eax, eax
0x140009d38  jns     short loc_140009D6B
0x140009d3a  mov     edx, 88h; void *
0x140009d3f  mov     rcx, [rsp+278h]; this
0x140009d47  mov     r9d, eax; char *
0x140009d4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009d4f  jmp     loc_140009DE1
0x140009d54  call    cs:__imp_GetLastError
0x140009d5b  nop     dword ptr [rax+rax+00h]
0x140009d60  mov     rdx, rbx
0x140009d63  mov     rcx, rsi
0x140009d66  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140009d6b  lea     r8, asc_1400865E0; "h"
0x140009d72  mov     rdx, r15; unsigned __int64
0x140009d75  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140009d7a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140009d7f  test    ebp, ebp
0x140009d81  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140009d89  lea     r9, [rsp+278h+Name]; lpName
0x140009d8e  mov     [rsp+278h+dwFlags], r14d; dwFlags
0x140009d93  cmovnz  edi, ebp
0x140009d96  mov     edx, ebp; lInitialCount
0x140009d98  mov     r8d, edi; lMaximumCount
0x140009d9b  xor     ecx, ecx; lpSemaphoreAttributes
0x140009d9d  call    cs:__imp_CreateSemaphoreExW
0x140009da4  nop     dword ptr [rax+rax+00h]
0x140009da9  mov     rbx, rax
0x140009dac  test    rax, rax
0x140009daf  jnz     short loc_140009DC6
0x140009db1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140009db6  mov     ebx, eax
0x140009db8  test    eax, eax
0x140009dba  jns     short loc_140009DDE
0x140009dbc  mov     edx, 8Dh
0x140009dc1  jmp     loc_140009D3F
0x140009dc6  call    cs:__imp_GetLastError
0x140009dcd  nop     dword ptr [rax+rax+00h]
0x140009dd2  mov     rdx, rbx
0x140009dd5  lea     rcx, [rsi+8]
0x140009dd9  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140009dde  mov     ebx, r14d
0x140009de1  mov     eax, ebx
0x140009de3  mov     rcx, [rsp+278h+var_38]
0x140009deb  xor     rcx, rsp; StackCookie
0x140009dee  call    __security_check_cookie
0x140009df3  mov     rbx, [rsp+278h+arg_8]
0x140009dfb  add     rsp, 250h
0x140009e02  pop     r15
0x140009e04  pop     r14
0x140009e06  pop     rdi
0x140009e07  pop     rsi
0x140009e08  pop     rbp
0x140009e09  retn
0x140009e0b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
