# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1400092d8`
- end: `0x1400093e8`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `272`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000af14`
- `0x14000b058`

## callees

- `0x1400092d8`
- `0x14000bedc`
- `0x14000c644`
- `0x14000c724`
- `0x14000d3ec`
- `0x14000d7b0`
- `0x140038d10`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        const unsigned __int16 *a2,
        size_t *a3,
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
  size_t v18; // [rsp+20h] [rbp-258h]
  int v19; // [rsp+20h] [rbp-258h]
  wchar_t pszDest[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCopyWorkerW(pszDest, 0x104u, a3, a2, v18);
  StringCchCatW(pszDest, v6, L"_p0");
  v7 = 1;
  v8 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v8 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v8, pszDest);
  v12 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v14 = a4 >> 31;
    StringCchCatW(pszDest, v10, L"h");
    if ( (_DWORD)v14 )
      v7 = v14;
    v15 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (__int64)this + 8,
            v14,
            v7,
            pszDest);
    v17 = v15;
    if ( v15 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x90, v16, (const char *)(unsigned int)v15, v19);
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
      v19);
    return v12;
  }
}

```

## disassembly

```asm
0x1400092d8  mov     [rsp+arg_10], rbx
0x1400092dd  push    rbp
0x1400092de  push    rsi
0x1400092df  push    rdi
0x1400092e0  sub     rsp, 260h
0x1400092e7  mov     rax, cs:__security_cookie
0x1400092ee  xor     rax, rsp
0x1400092f1  mov     [rsp+278h+var_28], rax
0x1400092f9  mov     rax, 0C000000000000000h
0x140009303  mov     rbx, r9
0x140009306  mov     rbp, rcx
0x140009309  test    rax, r9
0x14000930c  jz      short loc_140009314
0x14000930e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140009314  mov     r9, rdx; pszSrc
0x140009317  lea     rcx, [rsp+278h+pszDest]; pszDest
0x14000931c  mov     edx, 104h; cchDest
0x140009321  call    StringCopyWorkerW
0x140009326  lea     r8, aP0; "_p0"
0x14000932d  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x140009332  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140009337  mov     edx, ebx
0x140009339  lea     r9, [rsp+278h+pszDest]
0x14000933e  and     edx, 7FFFFFFFh
0x140009344  mov     esi, 1
0x140009349  mov     r8d, esi
0x14000934c  mov     rcx, rbp
0x14000934f  cmova   r8d, edx
0x140009353  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140009358  mov     edi, eax
0x14000935a  test    eax, eax
0x14000935c  jns     short loc_140009377
0x14000935e  mov     rcx, [rsp+278h]; this
0x140009366  mov     r9d, eax; char *
0x140009369  mov     edx, 8Bh; void *
0x14000936e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009373  mov     eax, edi
0x140009375  jmp     short loc_1400093C5
0x140009377  lea     r8, asc_140046E88; "h"
0x14000937e  shr     rbx, 1Fh
0x140009382  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x140009387  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000938c  test    ebx, ebx
0x14000938e  lea     rcx, [rbp+8]
0x140009392  lea     r9, [rsp+278h+pszDest]
0x140009397  mov     edx, ebx
0x140009399  cmovnz  esi, ebx
0x14000939c  mov     r8d, esi
0x14000939f  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1400093a4  mov     ebx, eax
0x1400093a6  test    eax, eax
0x1400093a8  jns     short loc_1400093C3
0x1400093aa  mov     rcx, [rsp+278h]; this
0x1400093b2  mov     r9d, eax; char *
0x1400093b5  mov     edx, 90h; void *
0x1400093ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400093bf  mov     eax, ebx
0x1400093c1  jmp     short loc_1400093C5
0x1400093c3  xor     eax, eax
0x1400093c5  mov     rcx, [rsp+278h+var_28]
0x1400093cd  xor     rcx, rsp; StackCookie
0x1400093d0  call    __security_check_cookie
0x1400093d5  mov     rbx, [rsp+278h+arg_10]
0x1400093dd  add     rsp, 260h
0x1400093e4  pop     rdi
0x1400093e5  pop     rsi
0x1400093e6  pop     rbp
0x1400093e7  retn
```
