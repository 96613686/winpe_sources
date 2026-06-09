# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18003475c`
- end: `0x18003486c`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `272`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180039270`

## callees

- `0x1800015d0`
- `0x18000ff88`
- `0x18003475c`
- `0x18003a93c`
- `0x18003b3cc`
- `0x18003be5c`
- `0x18003c008`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        unsigned __int16 *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  unsigned __int64 v6; // rdx
  LONG v7; // esi
  LONG v8; // r8d
  int semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned __int64 v10; // rdx
  unsigned int v11; // r8d
  unsigned int v12; // edi
  unsigned __int64 v14; // rbx
  int v15; // eax
  unsigned int v16; // r8d
  unsigned int v17; // ebx
  int v18; // [rsp+20h] [rbp-258h]
  unsigned __int16 v19[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCchCopyW(v19, 0x104u, a2);
  StringCchCatW(v19, v6, L"_p0");
  v7 = 1;
  v8 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v8 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v8, v19);
  v12 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v14 = a4 >> 31;
    StringCchCatW(v19, v10, L"h");
    if ( (_DWORD)v14 )
      v7 = v14;
    v15 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (__int64)this + 8,
            v14,
            v7,
            v19);
    v17 = v15;
    if ( v15 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x90, v16, (const char *)(unsigned int)v15, v18);
      return v17;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      v11,
      (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v18);
    return v12;
  }
}

```

## disassembly

```asm
0x18003475c  mov     [rsp+arg_10], rbx
0x180034761  push    rbp
0x180034762  push    rsi
0x180034763  push    rdi
0x180034764  sub     rsp, 260h
0x18003476b  mov     rax, cs:__security_cookie
0x180034772  xor     rax, rsp
0x180034775  mov     [rsp+278h+var_28], rax
0x18003477d  mov     rax, 0C000000000000000h
0x180034787  mov     rbx, r9
0x18003478a  mov     rbp, rcx
0x18003478d  test    rax, r9
0x180034790  jz      short loc_180034798
0x180034792  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180034798  mov     r8, rdx; unsigned __int16 *
0x18003479b  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x1800347a0  mov     edx, 104h; unsigned __int64
0x1800347a5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800347aa  lea     r8, aP0; "_p0"
0x1800347b1  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x1800347b6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800347bb  mov     edx, ebx
0x1800347bd  lea     r9, [rsp+278h+var_238]
0x1800347c2  and     edx, 7FFFFFFFh
0x1800347c8  mov     esi, 1
0x1800347cd  mov     r8d, esi
0x1800347d0  mov     rcx, rbp
0x1800347d3  cmova   r8d, edx
0x1800347d7  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800347dc  mov     edi, eax
0x1800347de  test    eax, eax
0x1800347e0  jns     short loc_1800347FB
0x1800347e2  mov     rcx, [rsp+278h]; this
0x1800347ea  mov     r9d, eax; char *
0x1800347ed  mov     edx, 8Bh; void *
0x1800347f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800347f7  mov     eax, edi
0x1800347f9  jmp     short loc_180034849
0x1800347fb  lea     r8, asc_180046FE0; "h"
0x180034802  shr     rbx, 1Fh
0x180034806  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18003480b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180034810  test    ebx, ebx
0x180034812  lea     rcx, [rbp+8]
0x180034816  lea     r9, [rsp+278h+var_238]
0x18003481b  mov     edx, ebx
0x18003481d  cmovnz  esi, ebx
0x180034820  mov     r8d, esi
0x180034823  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180034828  mov     ebx, eax
0x18003482a  test    eax, eax
0x18003482c  jns     short loc_180034847
0x18003482e  mov     rcx, [rsp+278h]; this
0x180034836  mov     r9d, eax; char *
0x180034839  mov     edx, 90h; void *
0x18003483e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034843  mov     eax, ebx
0x180034845  jmp     short loc_180034849
0x180034847  xor     eax, eax
0x180034849  mov     rcx, [rsp+278h+var_28]
0x180034851  xor     rcx, rsp; StackCookie
0x180034854  call    __security_check_cookie
0x180034859  mov     rbx, [rsp+278h+arg_10]
0x180034861  add     rsp, 260h
0x180034868  pop     rdi
0x180034869  pop     rsi
0x18003486a  pop     rbp
0x18003486b  retn
```
