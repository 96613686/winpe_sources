# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000acc8`
- end: `0x18000add8`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `272`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000df7c`
- `0x18000e0cc`

## callees

- `0x180003fc0`
- `0x18000acc8`
- `0x18001025c`
- `0x1800112d0`
- `0x18001134c`
- `0x180012744`
- `0x180012b10`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        const unsigned __int16 *a2,
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
0x18000acc8  mov     [rsp+arg_10], rbx
0x18000accd  push    rbp
0x18000acce  push    rsi
0x18000accf  push    rdi
0x18000acd0  sub     rsp, 260h
0x18000acd7  mov     rax, cs:__security_cookie
0x18000acde  xor     rax, rsp
0x18000ace1  mov     [rsp+278h+var_28], rax
0x18000ace9  mov     rax, 0C000000000000000h
0x18000acf3  mov     rbx, r9
0x18000acf6  mov     rbp, rcx
0x18000acf9  test    rax, r9
0x18000acfc  jz      short loc_18000AD04
0x18000acfe  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000ad04  mov     r8, rdx; unsigned __int16 *
0x18000ad07  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18000ad0c  mov     edx, 104h; unsigned __int64
0x18000ad11  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ad16  lea     r8, aP0; "_p0"
0x18000ad1d  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18000ad22  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ad27  mov     edx, ebx
0x18000ad29  lea     r9, [rsp+278h+var_238]
0x18000ad2e  and     edx, 7FFFFFFFh
0x18000ad34  mov     esi, 1
0x18000ad39  mov     r8d, esi
0x18000ad3c  mov     rcx, rbp
0x18000ad3f  cmova   r8d, edx
0x18000ad43  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000ad48  mov     edi, eax
0x18000ad4a  test    eax, eax
0x18000ad4c  jns     short loc_18000AD67
0x18000ad4e  mov     rcx, [rsp+278h]; this
0x18000ad56  mov     r9d, eax; char *
0x18000ad59  mov     edx, 8Bh; void *
0x18000ad5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ad63  mov     eax, edi
0x18000ad65  jmp     short loc_18000ADB5
0x18000ad67  lea     r8, asc_18002BD90; "h"
0x18000ad6e  shr     rbx, 1Fh
0x18000ad72  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18000ad77  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ad7c  test    ebx, ebx
0x18000ad7e  lea     rcx, [rbp+8]
0x18000ad82  lea     r9, [rsp+278h+var_238]
0x18000ad87  mov     edx, ebx
0x18000ad89  cmovnz  esi, ebx
0x18000ad8c  mov     r8d, esi
0x18000ad8f  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000ad94  mov     ebx, eax
0x18000ad96  test    eax, eax
0x18000ad98  jns     short loc_18000ADB3
0x18000ad9a  mov     rcx, [rsp+278h]; this
0x18000ada2  mov     r9d, eax; char *
0x18000ada5  mov     edx, 90h; void *
0x18000adaa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000adaf  mov     eax, ebx
0x18000adb1  jmp     short loc_18000ADB5
0x18000adb3  xor     eax, eax
0x18000adb5  mov     rcx, [rsp+278h+var_28]
0x18000adbd  xor     rcx, rsp; StackCookie
0x18000adc0  call    __security_check_cookie
0x18000adc5  mov     rbx, [rsp+278h+arg_10]
0x18000adcd  add     rsp, 260h
0x18000add4  pop     rdi
0x18000add5  pop     rsi
0x18000add6  pop     rbp
0x18000add7  retn
```
