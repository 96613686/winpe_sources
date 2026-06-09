# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x40aec9`
- end: `0x40af69`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AAEJPBG_N_K@Z`
- size: `160`
- prototype: `void *__thiscall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *cchDest, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x40c61e`

## callees

- `0x402625`
- `0x402dc4`
- `0x40adfa`
- `0x40ae65`
- `0x40aec9`
- `0x40c01c`
- `0x40cb60`

## pseudocode

```c
void *__thiscall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        const unsigned __int16 *cchDest,
        bool a3,
        unsigned __int64 a4)
{
  LONG v5; // eax
  void *semaphore_t_V__unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QAEJJJPBGKPAU_SECURITY_ATTRIBUTES__PA_N_Z; // eax
  wil::details::in1diag3 *v7; // ecx
  void *v8; // esi
  int v10; // [esp-Ch] [ebp-224h]
  int v11; // [esp-8h] [ebp-220h]
  int v12; // [esp-4h] [ebp-21Ch]
  wil::details::in1diag3 *v13; // [esp+0h] [ebp-218h]
  unsigned int v14; // [esp+0h] [ebp-218h]
  unsigned int v15; // [esp+0h] [ebp-218h]
  const unsigned __int16 *v16; // [esp+4h] [ebp-214h]
  const unsigned __int16 *v17; // [esp+4h] [ebp-214h]
  const char *v18; // [esp+4h] [ebp-214h]
  int v19[131]; // [esp+8h] [ebp-210h] BYREF

  if ( HIDWORD(a4) | a4 & 0x80000000 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  StringCchCopyW((size_t)cchDest, (unsigned int)v13, v16);
  StringCchCatW(L"_p0", v14, v17);
  v5 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v5 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QAEJJJPBGKPAU_SECURITY_ATTRIBUTES__PA_N_Z = (void *)_create___semaphore_t_V__unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QAEJJJPBGKPAU_SECURITY_ATTRIBUTES__PA_N_Z(this, a4 & 0x7FFFFFFF, v5, (const WCHAR *)v19, v10, v11, v12);
  v8 = semaphore_t_V__unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QAEJJJPBGKPAU_SECURITY_ATTRIBUTES__PA_N_Z;
  if ( (int)semaphore_t_V__unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QAEJJJPBGKPAU_SECURITY_ATTRIBUTES__PA_N_Z >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    v7,
    semaphore_t_V__unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QAEJJJPBGKPAU_SECURITY_ATTRIBUTES__PA_N_Z,
    v15,
    v18,
    v19[0]);
  return v8;
}

```

## disassembly

```asm
0x40aec9  mov     edi, edi
0x40aecb  push    ebp
0x40aecc  mov     ebp, esp
0x40aece  sub     esp, 210h
0x40aed4  mov     eax, ___security_cookie
0x40aed9  xor     eax, ebp
0x40aedb  mov     [ebp+var_4], eax
0x40aede  push    esi; char *
0x40aedf  mov     esi, dword ptr [ebp+arg_8]
0x40aee2  mov     eax, esi
0x40aee4  and     eax, 80000000h
0x40aee9  or      eax, dword ptr [ebp+arg_8+4]
0x40aeec  push    edi; this
0x40aeed  mov     edi, ecx
0x40aeef  mov     ecx, [ebp+cchDest]
0x40aef2  jnz     short loc_40AF64
0x40aef4  push    ecx; cchDest
0x40aef5  mov     edx, 104h
0x40aefa  lea     ecx, [ebp+var_210]
0x40af00  call    ?StringCchCopyW@@YGJPAGIPBG@Z; StringCchCopyW(ushort *,uint,ushort const *)
0x40af05  push    offset aP0; "_p0"
0x40af0a  mov     edx, 104h
0x40af0f  lea     ecx, [ebp+var_210]
0x40af15  call    ?StringCchCatW@@YGJPAGIPBG@Z; StringCchCatW(ushort *,uint,ushort const *)
0x40af1a  sub     esp, 0Ch
0x40af1d  lea     eax, [ebp+var_210]
0x40af23  mov     ecx, edi
0x40af25  push    eax
0x40af26  xor     eax, eax
0x40af28  inc     eax
0x40af29  and     esi, 7FFFFFFFh
0x40af2f  cmovnz  eax, esi
0x40af32  push    eax
0x40af33  push    esi
0x40af34  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QAEJJJPBGKPAU_SECURITY_ATTRIBUTES@@PA_N@Z
0x40af39  mov     esi, eax
0x40af3b  test    esi, esi
0x40af3d  jns     short loc_40AF52
0x40af3f  push    esi; void *
0x40af40  push    ecx; this
0x40af41  mov     ecx, [ebp+4]
0x40af44  mov     edx, 8Bh
0x40af49  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x40af4e  mov     eax, esi
0x40af50  jmp     short loc_40AF54
0x40af52  xor     eax, eax
0x40af54  mov     ecx, [ebp+var_4]
0x40af57  pop     edi
0x40af58  xor     ecx, ebp; StackCookie
0x40af5a  pop     esi
0x40af5b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x40af60  leave
0x40af61  retn    10h
0x40af64  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YGXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
