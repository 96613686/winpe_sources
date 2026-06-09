# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1400037b0`
- end: `0x1400038ce`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `286`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, size_t *, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140004e38`
- `0x140004f68`

## callees

- `0x1400014c0`
- `0x1400037b0`
- `0x140005fcc`
- `0x140006690`
- `0x140006770`
- `0x140007160`
- `0x140007318`

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
  unsigned int v11; // edi
  unsigned __int64 v13; // rbx
  int v14; // eax
  unsigned int v15; // ebx
  size_t v16; // [rsp+20h] [rbp-258h]
  int v17; // [rsp+20h] [rbp-258h]
  wchar_t pszDest[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCopyWorkerW(pszDest, 0x104u, a3, a2, v16);
  StringCchCatW(pszDest, v6, L"_p0");
  v7 = 1;
  v8 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v8 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v8, pszDest);
  v11 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v13 = a4 >> 31;
    StringCchCatW(pszDest, v10, L"h");
    if ( (_DWORD)v13 )
      v7 = v13;
    v14 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (__int64)this + 8,
            v13,
            v7,
            pszDest);
    v15 = v14;
    if ( v14 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"wil",
        (const char *)(unsigned int)v14,
        v17);
      return v15;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"wil",
      (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v17);
    return v11;
  }
}

```

## disassembly

```asm
0x1400037b0  mov     [rsp+arg_10], rbx
0x1400037b5  push    rbp
0x1400037b6  push    rsi
0x1400037b7  push    rdi
0x1400037b8  sub     rsp, 260h
0x1400037bf  mov     rax, cs:__security_cookie
0x1400037c6  xor     rax, rsp
0x1400037c9  mov     [rsp+278h+var_28], rax
0x1400037d1  mov     rax, 0C000000000000000h
0x1400037db  mov     rbx, r9
0x1400037de  mov     rbp, rcx
0x1400037e1  test    rax, r9
0x1400037e4  jz      short loc_1400037EC
0x1400037e6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400037ec  mov     r9, rdx; pszSrc
0x1400037ef  lea     rcx, [rsp+278h+pszDest]; pszDest
0x1400037f4  mov     edx, 104h; cchDest
0x1400037f9  call    StringCopyWorkerW
0x1400037fe  lea     r8, aP0; "_p0"
0x140003805  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x14000380a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000380f  mov     edx, ebx
0x140003811  lea     r9, [rsp+278h+pszDest]
0x140003816  and     edx, 7FFFFFFFh
0x14000381c  mov     esi, 1
0x140003821  mov     r8d, esi
0x140003824  mov     rcx, rbp
0x140003827  cmova   r8d, edx
0x14000382b  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140003830  mov     edi, eax
0x140003832  test    eax, eax
0x140003834  jns     short loc_140003856
0x140003836  mov     rcx, [rsp+278h]; this
0x14000383e  lea     r8, aWil; "wil"
0x140003845  mov     r9d, eax; char *
0x140003848  mov     edx, 8Bh; void *
0x14000384d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003852  mov     eax, edi
0x140003854  jmp     short loc_1400038AB
0x140003856  lea     r8, asc_14000A9E0; "h"
0x14000385d  shr     rbx, 1Fh
0x140003861  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x140003866  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000386b  test    ebx, ebx
0x14000386d  lea     rcx, [rbp+8]
0x140003871  lea     r9, [rsp+278h+pszDest]
0x140003876  mov     edx, ebx
0x140003878  cmovnz  esi, ebx
0x14000387b  mov     r8d, esi
0x14000387e  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140003883  mov     ebx, eax
0x140003885  test    eax, eax
0x140003887  jns     short loc_1400038A9
0x140003889  mov     rcx, [rsp+278h]; this
0x140003891  lea     r8, aWil; "wil"
0x140003898  mov     r9d, eax; char *
0x14000389b  mov     edx, 90h; void *
0x1400038a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400038a5  mov     eax, ebx
0x1400038a7  jmp     short loc_1400038AB
0x1400038a9  xor     eax, eax
0x1400038ab  mov     rcx, [rsp+278h+var_28]
0x1400038b3  xor     rcx, rsp; StackCookie
0x1400038b6  call    __security_check_cookie
0x1400038bb  mov     rbx, [rsp+278h+arg_10]
0x1400038c3  add     rsp, 260h
0x1400038ca  pop     rdi
0x1400038cb  pop     rsi
0x1400038cc  pop     rbp
0x1400038cd  retn
```
