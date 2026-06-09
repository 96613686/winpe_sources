# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800437d8`
- end: `0x1800438eb`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `275`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004a83c`
- `0x1800671bc`

## callees

- `0x180016258`
- `0x1800162e4`
- `0x1800437d8`
- `0x18004c09c`
- `0x18004c6e8`
- `0x18004ca24`
- `0x18009e300`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        size_t *a2,
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
0x1800437d8  push    rbx
0x1800437da  push    rbp
0x1800437db  push    rsi
0x1800437dc  push    rdi
0x1800437dd  push    r14
0x1800437df  sub     rsp, 260h
0x1800437e6  mov     rax, cs:__security_cookie
0x1800437ed  xor     rax, rsp
0x1800437f0  mov     [rsp+288h+var_38], rax
0x1800437f8  mov     rax, 0C000000000000000h
0x180043802  mov     rbx, r9
0x180043805  mov     rbp, rcx
0x180043808  test    rax, r9
0x18004380b  jz      short loc_180043813
0x18004380d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180043813  mov     r8, rdx; unsigned __int16 *
0x180043816  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x18004381b  mov     r14d, 104h
0x180043821  mov     edx, r14d; unsigned __int64
0x180043824  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180043829  lea     r8, aP0; "_p0"
0x180043830  mov     edx, r14d; unsigned __int64
0x180043833  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x180043838  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004383d  mov     edx, ebx
0x18004383f  lea     r9, [rsp+288h+var_248]
0x180043844  and     edx, 7FFFFFFFh
0x18004384a  mov     esi, 1
0x18004384f  mov     r8d, esi
0x180043852  mov     rcx, rbp
0x180043855  cmova   r8d, edx
0x180043859  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18004385e  mov     edi, eax
0x180043860  test    eax, eax
0x180043862  jns     short loc_18004387C
0x180043864  mov     rcx, [rsp+288h]; this
0x18004386c  lea     edx, [r14-79h]; void *
0x180043870  mov     r9d, eax; char *
0x180043873  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043878  mov     eax, edi
0x18004387a  jmp     short loc_1800438CD
0x18004387c  lea     r8, asc_1800BE788; "h"
0x180043883  shr     rbx, 1Fh
0x180043887  mov     rdx, r14; unsigned __int64
0x18004388a  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x18004388f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180043894  test    ebx, ebx
0x180043896  lea     rcx, [rbp+8]
0x18004389a  lea     r9, [rsp+288h+var_248]
0x18004389f  mov     edx, ebx
0x1800438a1  cmovnz  esi, ebx
0x1800438a4  mov     r8d, esi
0x1800438a7  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800438ac  mov     ebx, eax
0x1800438ae  test    eax, eax
0x1800438b0  jns     short loc_1800438CB
0x1800438b2  mov     rcx, [rsp+288h]; this
0x1800438ba  mov     r9d, eax; char *
0x1800438bd  mov     edx, 90h; void *
0x1800438c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800438c7  mov     eax, ebx
0x1800438c9  jmp     short loc_1800438CD
0x1800438cb  xor     eax, eax
0x1800438cd  mov     rcx, [rsp+288h+var_38]
0x1800438d5  xor     rcx, rsp; StackCookie
0x1800438d8  call    __security_check_cookie
0x1800438dd  add     rsp, 260h
0x1800438e4  pop     r14
0x1800438e6  pop     rdi
0x1800438e7  pop     rsi
0x1800438e8  pop     rbp
0x1800438e9  pop     rbx
0x1800438ea  retn
```
