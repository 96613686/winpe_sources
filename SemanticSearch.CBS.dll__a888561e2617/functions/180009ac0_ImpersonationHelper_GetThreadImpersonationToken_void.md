# ImpersonationHelper::GetThreadImpersonationToken(void)

- ea: `0x180009ac0`
- end: `0x180009bab`
- name: `?GetThreadImpersonationToken@ImpersonationHelper@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ`
- size: `235`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, service_task`

## callers

- `0x180051770`
- `0x180052c90`
- `0x180053610`
- `0x1800583b0`
- `0x18005bc90`

## callees

- `0x180009ac0`
- `0x1800103e0`
- `0x180015bd0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180009b63`
- `KERNEL32!SetLastError` at `0x180009b63`
- `KERNEL32!GetLastError` at `0x180009b50`
- `KERNEL32!GetLastError` at `0x180009b71`
- `KERNEL32!GetLastError` at `0x180009b50`
- `KERNEL32!GetLastError` at `0x180009b71`
- `KERNEL32!GetCurrentThread` at `0x180009b10`
- `KERNEL32!GetCurrentThread` at `0x180009b10`
- `KERNEL32!CloseHandle` at `0x180009b5b`
- `KERNEL32!CloseHandle` at `0x180009b5b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009b29`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009b29`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void **__fastcall ImpersonationHelper::GetThreadImpersonationToken(void **a1)
{
  HANDLE CurrentThread; // rax
  BOOL v3; // r15d
  HANDLE v4; // rbp
  void *v5; // rsi
  DWORD LastError; // ebx
  unsigned int v7; // r8d
  const char *v8; // r9
  HANDLE TokenHandle; // [rsp+30h] [rbp-38h] BYREF
  char v11; // [rsp+38h] [rbp-30h]
  void **v12; // [rsp+40h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v12 = a1;
  *a1 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AIFabric_LocalService_Support>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AIFabric_LocalService_Support>::GetImpl'::`2'::impl) )
  {
    TokenHandle = 0;
    v11 = 1;
    CurrentThread = GetCurrentThread();
    v3 = OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle);
    if ( v11 )
    {
      v4 = TokenHandle;
      v5 = *a1;
      if ( *a1 && v5 != (void *)-1LL )
      {
        LastError = GetLastError();
        CloseHandle(v5);
        SetLastError(LastError);
      }
      *a1 = v4;
    }
    if ( !v3 && GetLastError() != 1008 )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0xE, v7, v8);
  }
  return a1;
}

```

## disassembly

```asm
0x180009ac0  mov     [rsp+arg_8], rbx
0x180009ac5  mov     [rsp+arg_10], rbp
0x180009aca  mov     [rsp+arg_18], rsi
0x180009acf  push    rdi
0x180009ad0  push    r14
0x180009ad2  push    r15
0x180009ad4  sub     rsp, 50h
0x180009ad8  mov     rdi, rcx
0x180009adb  mov     [rsp+68h+var_28], rcx
0x180009ae0  xor     ebx, ebx
0x180009ae2  mov     [rsp+68h+var_48], ebx
0x180009ae6  mov     [rcx], rbx
0x180009ae9  mov     [rsp+68h+var_48], 1
0x180009af1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AIFabric_LocalService_Support@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AIFabric_LocalService_Support@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AIFabric_LocalService_Support> `wil::Feature<__WilFeatureTraits_Feature_AIFabric_LocalService_Support>::GetImpl(void)'::`2'::impl
0x180009af8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AIFabric_LocalService_Support@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AIFabric_LocalService_Support>::__private_IsEnabled(void)
0x180009afd  test    al, al
0x180009aff  jz      short loc_180009B7E
0x180009b01  mov     [rsp+68h+var_40], rdi
0x180009b06  mov     [rsp+68h+TokenHandle], rbx
0x180009b0b  mov     [rsp+68h+var_30], 1
0x180009b10  call    cs:__imp_GetCurrentThread
0x180009b16  lea     r9, [rsp+68h+TokenHandle]; TokenHandle
0x180009b1b  mov     edx, 0F01FFh; DesiredAccess
0x180009b20  mov     r8d, 1; OpenAsSelf
0x180009b26  mov     rcx, rax; ThreadHandle
0x180009b29  call    cs:__imp_OpenThreadToken
0x180009b2f  mov     r15d, eax
0x180009b32  cmp     [rsp+68h+var_30], bl
0x180009b36  jz      short loc_180009B6C
0x180009b38  mov     rbp, [rsp+68h+TokenHandle]
0x180009b3d  mov     r14, [rsp+68h+var_40]
0x180009b42  mov     rsi, [r14]
0x180009b45  test    rsi, rsi
0x180009b48  jz      short loc_180009B69
0x180009b4a  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180009b4e  jz      short loc_180009B69
0x180009b50  call    cs:__imp_GetLastError
0x180009b56  mov     ebx, eax
0x180009b58  mov     rcx, rsi; hObject
0x180009b5b  call    cs:__imp_CloseHandle
0x180009b61  mov     ecx, ebx; dwErrCode
0x180009b63  call    cs:__imp_SetLastError
0x180009b69  mov     [r14], rbp
0x180009b6c  test    r15d, r15d
0x180009b6f  jnz     short loc_180009B7E
0x180009b71  call    cs:__imp_GetLastError
0x180009b77  cmp     eax, 3F0h
0x180009b7c  jnz     short loc_180009B9B
0x180009b7e  mov     rax, rdi
0x180009b81  lea     r11, [rsp+68h+var_18]
0x180009b86  mov     rbx, [r11+28h]
0x180009b8a  mov     rbp, [r11+30h]
0x180009b8e  mov     rsi, [r11+38h]
0x180009b92  mov     rsp, r11
0x180009b95  pop     r15
0x180009b97  pop     r14
0x180009b99  pop     rdi
0x180009b9a  retn
0x180009b9b  mov     rcx, [rsp+68h]; this
0x180009ba0  mov     edx, 0Eh; void *
0x180009ba5  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
