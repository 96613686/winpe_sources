# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1400051c0`
- end: `0x1400052d3`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `275`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140007d8c`
- `0x140007ee0`

## callees

- `0x1400051c0`
- `0x14000a18c`
- `0x14000a9c4`
- `0x14000aab8`
- `0x14000ba28`
- `0x14000beb8`
- `0x140015aa0`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  LONG v6; // esi
  LONG v7; // r8d
  int semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v9; // r8d
  unsigned int v10; // edi
  unsigned __int64 v12; // rbx
  int v13; // eax
  unsigned int v14; // r8d
  unsigned int v15; // ebx
  int v16; // [rsp+20h] [rbp-268h]
  unsigned __int16 v17[264]; // [rsp+40h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCchCopyW(v17, 0x104u, a2);
  StringCchCatW(v17, 0x104u, L"_p0");
  v6 = 1;
  v7 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v7 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v7, v17);
  v10 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v12 = a4 >> 31;
    StringCchCatW(v17, 0x104u, L"h");
    if ( (_DWORD)v12 )
      v6 = v12;
    v13 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (__int64)this + 8,
            v12,
            v6,
            v17);
    v15 = v13;
    if ( v13 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x90, v14, (const char *)(unsigned int)v13, v16);
      return v15;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      v9,
      (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v16);
    return v10;
  }
}

```

## disassembly

```asm
0x1400051c0  push    rbx
0x1400051c2  push    rbp
0x1400051c3  push    rsi
0x1400051c4  push    rdi
0x1400051c5  push    r14
0x1400051c7  sub     rsp, 260h
0x1400051ce  mov     rax, cs:__security_cookie
0x1400051d5  xor     rax, rsp
0x1400051d8  mov     [rsp+288h+var_38], rax
0x1400051e0  mov     rax, 0C000000000000000h
0x1400051ea  mov     rbx, r9
0x1400051ed  mov     rbp, rcx
0x1400051f0  test    rax, r9
0x1400051f3  jz      short loc_1400051FB
0x1400051f5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400051fb  mov     r8, rdx; unsigned __int16 *
0x1400051fe  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x140005203  mov     r14d, 104h
0x140005209  mov     edx, r14d; unsigned __int64
0x14000520c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140005211  lea     r8, aP0; "_p0"
0x140005218  mov     edx, r14d; unsigned __int64
0x14000521b  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x140005220  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140005225  mov     edx, ebx
0x140005227  lea     r9, [rsp+288h+var_248]
0x14000522c  and     edx, 7FFFFFFFh
0x140005232  mov     esi, 1
0x140005237  mov     r8d, esi
0x14000523a  mov     rcx, rbp
0x14000523d  cmova   r8d, edx
0x140005241  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140005246  mov     edi, eax
0x140005248  test    eax, eax
0x14000524a  jns     short loc_140005264
0x14000524c  mov     rcx, [rsp+288h]; this
0x140005254  lea     edx, [r14-79h]; void *
0x140005258  mov     r9d, eax; char *
0x14000525b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005260  mov     eax, edi
0x140005262  jmp     short loc_1400052B5
0x140005264  lea     r8, asc_14001AFC8; "h"
0x14000526b  shr     rbx, 1Fh
0x14000526f  mov     rdx, r14; unsigned __int64
0x140005272  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x140005277  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000527c  test    ebx, ebx
0x14000527e  lea     rcx, [rbp+8]
0x140005282  lea     r9, [rsp+288h+var_248]
0x140005287  mov     edx, ebx
0x140005289  cmovnz  esi, ebx
0x14000528c  mov     r8d, esi
0x14000528f  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140005294  mov     ebx, eax
0x140005296  test    eax, eax
0x140005298  jns     short loc_1400052B3
0x14000529a  mov     rcx, [rsp+288h]; this
0x1400052a2  mov     r9d, eax; char *
0x1400052a5  mov     edx, 90h; void *
0x1400052aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400052af  mov     eax, ebx
0x1400052b1  jmp     short loc_1400052B5
0x1400052b3  xor     eax, eax
0x1400052b5  mov     rcx, [rsp+288h+var_38]
0x1400052bd  xor     rcx, rsp; StackCookie
0x1400052c0  call    __security_check_cookie
0x1400052c5  add     rsp, 260h
0x1400052cc  pop     r14
0x1400052ce  pop     rdi
0x1400052cf  pop     rsi
0x1400052d0  pop     rbp
0x1400052d1  pop     rbx
0x1400052d2  retn
```
