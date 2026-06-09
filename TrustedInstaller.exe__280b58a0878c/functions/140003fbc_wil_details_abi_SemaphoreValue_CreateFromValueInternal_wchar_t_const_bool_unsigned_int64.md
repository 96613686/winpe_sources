# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x140003fbc`
- end: `0x1400040dd`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `289`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const wchar_t *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400050a8`
- `0x140007d68`

## callees

- `0x1400023e0`
- `0x140003fbc`
- `0x1400054b0`
- `0x1400057b8`
- `0x14000580c`
- `0x140005dc8`
- `0x140005e48`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        const wchar_t *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  LONG v6; // esi
  LONG v7; // r8d
  int semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v9; // edi
  unsigned __int64 v11; // rbx
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // [rsp+20h] [rbp-268h]
  wchar_t v15[264]; // [rsp+40h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCchCopyW(v15, 0x104u, a2);
  StringCchCatW(v15, 0x104u, L"_p0");
  v6 = 1;
  v7 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v7 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v7, v15);
  v9 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v11 = a4 >> 31;
    StringCchCatW(v15, 0x104u, L"h");
    if ( (_DWORD)v11 )
      v6 = v11;
    v12 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (__int64)this + 8,
            v11,
            v6,
            v15);
    v13 = v12;
    if ( v12 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"wil",
        (const char *)(unsigned int)v12,
        v14);
      return v13;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"wil",
      (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v14);
    return v9;
  }
}

```

## disassembly

```asm
0x140003fbc  push    rbx
0x140003fbe  push    rbp
0x140003fbf  push    rsi
0x140003fc0  push    rdi
0x140003fc1  push    r14
0x140003fc3  sub     rsp, 260h
0x140003fca  mov     rax, cs:__security_cookie
0x140003fd1  xor     rax, rsp
0x140003fd4  mov     [rsp+288h+var_38], rax
0x140003fdc  mov     rax, 0C000000000000000h
0x140003fe6  mov     rbx, r9
0x140003fe9  mov     rbp, rcx
0x140003fec  test    rax, r9
0x140003fef  jz      short loc_140003FF7
0x140003ff1  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140003ff7  mov     r8, rdx; wchar_t *
0x140003ffa  lea     rcx, [rsp+288h+var_248]; wchar_t *
0x140003fff  mov     r14d, 104h
0x140004005  mov     edx, r14d; unsigned __int64
0x140004008  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x14000400d  lea     r8, aP0; "_p0"
0x140004014  mov     edx, r14d; unsigned __int64
0x140004017  lea     rcx, [rsp+288h+var_248]; wchar_t *
0x14000401c  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140004021  mov     edx, ebx
0x140004023  lea     r9, [rsp+288h+var_248]
0x140004028  and     edx, 7FFFFFFFh
0x14000402e  mov     esi, 1
0x140004033  mov     r8d, esi
0x140004036  mov     rcx, rbp
0x140004039  cmova   r8d, edx
0x14000403d  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140004042  mov     edi, eax
0x140004044  test    eax, eax
0x140004046  jns     short loc_140004067
0x140004048  mov     rcx, [rsp+288h]; this
0x140004050  lea     r8, aWil; "wil"
0x140004057  mov     r9d, eax; char *
0x14000405a  lea     edx, [r14-79h]; void *
0x14000405e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004063  mov     eax, edi
0x140004065  jmp     short loc_1400040BF
0x140004067  lea     r8, asc_14002F638; "h"
0x14000406e  shr     rbx, 1Fh
0x140004072  mov     rdx, r14; unsigned __int64
0x140004075  lea     rcx, [rsp+288h+var_248]; wchar_t *
0x14000407a  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x14000407f  test    ebx, ebx
0x140004081  lea     rcx, [rbp+8]
0x140004085  lea     r9, [rsp+288h+var_248]
0x14000408a  mov     edx, ebx
0x14000408c  cmovnz  esi, ebx
0x14000408f  mov     r8d, esi
0x140004092  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140004097  mov     ebx, eax
0x140004099  test    eax, eax
0x14000409b  jns     short loc_1400040BD
0x14000409d  mov     rcx, [rsp+288h]; this
0x1400040a5  lea     r8, aWil; "wil"
0x1400040ac  mov     r9d, eax; char *
0x1400040af  mov     edx, 90h; void *
0x1400040b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400040b9  mov     eax, ebx
0x1400040bb  jmp     short loc_1400040BF
0x1400040bd  xor     eax, eax
0x1400040bf  mov     rcx, [rsp+288h+var_38]
0x1400040c7  xor     rcx, rsp; StackCookie
0x1400040ca  call    __security_check_cookie
0x1400040cf  add     rsp, 260h
0x1400040d6  pop     r14
0x1400040d8  pop     rdi
0x1400040d9  pop     rsi
0x1400040da  pop     rbp
0x1400040db  pop     rbx
0x1400040dc  retn
```
