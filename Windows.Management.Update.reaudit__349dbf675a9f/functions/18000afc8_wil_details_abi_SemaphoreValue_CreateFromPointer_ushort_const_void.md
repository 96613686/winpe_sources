# wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)

- ea: `0x18000afc8`
- end: `0x18000b17e`
- name: `?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z`
- size: `438`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, void *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000a82c`
- `0x18000abf0`

## callees

- `0x180002880`
- `0x18000afc8`
- `0x18000c1b8`
- `0x18000eb04`
- `0x18000f5a0`
- `0x180010464`
- `0x18001080c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000b08a`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000b109`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000b08a`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000b109`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b0c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b132`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b0c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b132`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromPointer(
        wil::details_abi::SemaphoreValue *this,
        char *a2,
        unsigned __int64 a3)
{
  unsigned __int64 v4; // rbx
  signed __int64 v5; // r8
  WCHAR *v6; // rcx
  unsigned __int64 v7; // rdx
  LONG v8; // edi
  WCHAR v9; // ax
  WCHAR *v10; // rax
  LONG v11; // r8d
  unsigned __int64 v12; // rsi
  LONG v13; // ebx
  wil::details *v14; // rcx
  HANDLE Semaphore; // rbx
  int LastErrorFailHr; // eax
  unsigned __int64 v17; // rdx
  unsigned int v18; // r8d
  unsigned int v19; // ebx
  __int64 v20; // rdx
  wil::details *v21; // rcx
  HANDLE v22; // rbx
  DWORD dwFlags; // [rsp+20h] [rbp-248h]
  WCHAR Name[264]; // [rsp+30h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

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
  StringCchCatW(Name, v7, L"_p0");
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
    StringCchCatW(Name, v17, L"h");
    if ( (_DWORD)v12 )
      v8 = v12;
    v22 = CreateSemaphoreExW(0, v12, v8, Name, 0, 0x1F0003u);
    if ( v22 )
    {
      GetLastError();
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        (char *)this + 8,
        v22);
    }
    else
    {
      LastErrorFailHr = wil::details::GetLastErrorFailHr(v21);
      v19 = LastErrorFailHr;
      if ( LastErrorFailHr < 0 )
      {
        v20 = 141;
        goto LABEL_13;
      }
    }
    return 0;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v14);
  v19 = LastErrorFailHr;
  if ( LastErrorFailHr >= 0 )
    goto LABEL_15;
  v20 = 136;
LABEL_13:
  wil::details::in1diag3::Return_Hr(retaddr, (void *)v20, v18, (const char *)(unsigned int)LastErrorFailHr, dwFlags);
  return v19;
}

```

## disassembly

```asm
0x18000afc8  mov     [rsp+arg_8], rbx
0x18000afcd  mov     [rsp+arg_18], rbp
0x18000afd2  push    rsi
0x18000afd3  push    rdi
0x18000afd4  push    r14
0x18000afd6  sub     rsp, 250h
0x18000afdd  mov     rax, cs:__security_cookie
0x18000afe4  xor     rax, rsp
0x18000afe7  mov     [rsp+268h+var_28], rax
0x18000afef  mov     rbx, r8
0x18000aff2  mov     rbp, rcx
0x18000aff5  mov     r8, rdx
0x18000aff8  test    bl, 3
0x18000affb  jnz     loc_18000B178
0x18000b001  lea     rax, [rsp+268h+Name]
0x18000b006  shr     rbx, 2
0x18000b00a  sub     r8, rax
0x18000b00d  lea     rcx, [rsp+268h+Name]
0x18000b012  xor     r14d, r14d
0x18000b015  mov     edx, 104h
0x18000b01a  lea     edi, [r14+1]
0x18000b01e  lea     rax, [rdx+7FFFFEFAh]
0x18000b025  test    rax, rax
0x18000b028  jz      short loc_18000B040
0x18000b02a  movzx   eax, word ptr [r8+rcx]
0x18000b02f  test    ax, ax
0x18000b032  jz      short loc_18000B040
0x18000b034  mov     [rcx], ax
0x18000b037  add     rcx, 2
0x18000b03b  sub     rdx, rdi; unsigned __int64
0x18000b03e  jnz     short loc_18000B01E
0x18000b040  lea     rax, [rcx-2]
0x18000b044  test    rdx, rdx
0x18000b047  lea     r8, aP0; "_p0"
0x18000b04e  cmovnz  rax, rcx
0x18000b052  lea     rcx, [rsp+268h+Name]; unsigned __int16 *
0x18000b057  mov     [rax], r14w
0x18000b05b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b060  mov     rsi, rbx
0x18000b063  mov     [rsp+268h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000b06b  mov     r8d, edi
0x18000b06e  shr     rsi, 1Fh
0x18000b072  and     ebx, 7FFFFFFFh
0x18000b078  mov     [rsp+268h+dwFlags], r14d; int
0x18000b07d  lea     r9, [rsp+268h+Name]; lpName
0x18000b082  mov     edx, ebx; lInitialCount
0x18000b084  cmova   r8d, ebx; lMaximumCount
0x18000b088  xor     ecx, ecx; lpSemaphoreAttributes
0x18000b08a  call    cs:__imp_CreateSemaphoreExW
0x18000b091  nop     dword ptr [rax+rax+00h]
0x18000b096  mov     rbx, rax
0x18000b099  test    rax, rax
0x18000b09c  jnz     short loc_18000B0C3
0x18000b09e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000b0a3  mov     ebx, eax
0x18000b0a5  test    eax, eax
0x18000b0a7  jns     short loc_18000B0DA
0x18000b0a9  mov     edx, 88h; void *
0x18000b0ae  mov     rcx, [rsp+268h]; this
0x18000b0b6  mov     r9d, eax; char *
0x18000b0b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b0be  jmp     loc_18000B14D
0x18000b0c3  call    cs:__imp_GetLastError
0x18000b0ca  nop     dword ptr [rax+rax+00h]
0x18000b0cf  mov     rdx, rbx
0x18000b0d2  mov     rcx, rbp
0x18000b0d5  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000b0da  lea     r8, asc_180030EF0; "h"
0x18000b0e1  lea     rcx, [rsp+268h+Name]; unsigned __int16 *
0x18000b0e6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b0eb  test    esi, esi
0x18000b0ed  mov     [rsp+268h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000b0f5  lea     r9, [rsp+268h+Name]; lpName
0x18000b0fa  mov     [rsp+268h+dwFlags], r14d; dwFlags
0x18000b0ff  cmovnz  edi, esi
0x18000b102  mov     edx, esi; lInitialCount
0x18000b104  mov     r8d, edi; lMaximumCount
0x18000b107  xor     ecx, ecx; lpSemaphoreAttributes
0x18000b109  call    cs:__imp_CreateSemaphoreExW
0x18000b110  nop     dword ptr [rax+rax+00h]
0x18000b115  mov     rbx, rax
0x18000b118  test    rax, rax
0x18000b11b  jnz     short loc_18000B132
0x18000b11d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000b122  mov     ebx, eax
0x18000b124  test    eax, eax
0x18000b126  jns     short loc_18000B14A
0x18000b128  mov     edx, 8Dh
0x18000b12d  jmp     loc_18000B0AE
0x18000b132  call    cs:__imp_GetLastError
0x18000b139  nop     dword ptr [rax+rax+00h]
0x18000b13e  mov     rdx, rbx
0x18000b141  lea     rcx, [rbp+8]
0x18000b145  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000b14a  mov     ebx, r14d
0x18000b14d  mov     eax, ebx
0x18000b14f  mov     rcx, [rsp+268h+var_28]
0x18000b157  xor     rcx, rsp; StackCookie
0x18000b15a  call    __security_check_cookie
0x18000b15f  lea     r11, [rsp+268h+var_18]
0x18000b167  mov     rbx, [r11+28h]
0x18000b16b  mov     rbp, [r11+38h]
0x18000b16f  mov     rsp, r11
0x18000b172  pop     r14
0x18000b174  pop     rdi
0x18000b175  pop     rsi
0x18000b176  retn
0x18000b178  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
