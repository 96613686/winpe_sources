# AIXPolicyHelper::IsDLPProviderPolicyConfigured(void)

- ea: `0x18001c81c`
- end: `0x18001c97f`
- name: `?IsDLPProviderPolicyConfigured@AIXPolicyHelper@@YA_NXZ`
- size: `355`
- prototype: `bool __fastcall(AIXPolicyHelper *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e518`

## callees

- `0x180003060`
- `0x180003078`
- `0x18001a654`
- `0x18001c81c`
- `0x18001ce58`
- `0x180024b4c`
- `0x180024f28`
- `0x180033010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001c954`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001c954`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall AIXPolicyHelper::IsDLPProviderPolicyConfigured(AIXPolicyHelper *this)
{
  char v1; // si
  const char *v2; // r9
  signed int v3; // eax
  __int64 v4; // r8
  volatile signed __int32 *v5; // rbx
  char v6; // di
  int v7; // eax
  HANDLE ProcessHeap; // rax
  unsigned int v10; // [rsp+20h] [rbp-78h] BYREF
  __int128 v11; // [rsp+28h] [rbp-70h]
  _DWORD *v12; // [rsp+38h] [rbp-60h] BYREF
  _DWORD v13[4]; // [rsp+40h] [rbp-58h] BYREF
  const wchar_t *v14; // [rsp+50h] [rbp-48h]
  _DWORD *v15; // [rsp+58h] [rbp-40h] BYREF
  _DWORD v16[4]; // [rsp+60h] [rbp-38h] BYREF
  const wchar_t *v17; // [rsp+70h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  volatile signed __int32 *v19; // [rsp+A0h] [rbp+8h]
  char v20; // [rsp+A0h] [rbp+8h]
  __int64 v22; // [rsp+A8h] [rbp+10h] BYREF
  LPVOID lpMem; // [rsp+B0h] [rbp+18h] BYREF

  try
  {
    v1 = 0;
    LODWORD(v19) = 0;
    v13[0] = 1;
    v13[1] = 29;
    v14 = L"SetDataLossPreventionProvider";
    v12 = v13;
    v16[0] = 1;
    v16[1] = 9;
    v17 = L"WindowsAI";
    v15 = v16;
    winrt::Windows::Management::Policies::NamedPolicy::GetPolicyFromPath(
      (const struct winrt::param::hstring *)&v22,
      (const struct winrt::param::hstring *)&v15,
      &v12);
    if ( (unsigned __int8)winrt::impl::consume_Windows_Management_Policies_INamedPolicyData<winrt::Windows::Management::Policies::INamedPolicyData>::IsManaged(&v22) )
    {
      lpMem = 0;
      v10 = 0;
      v11 = 0;
      v3 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v22 + 128LL))(v22, &lpMem);
      if ( v3 < 0 )
        winrt::throw_hresult(v3, &v10, v4);
      v5 = (volatile signed __int32 *)lpMem;
      v1 = 3;
      if ( lpMem )
      {
        v6 = 1;
        goto LABEL_8;
      }
    }
    else
    {
      v5 = v19;
    }
    v6 = 0;
LABEL_8:
    v20 = v6;
    if ( (v1 & 1) != 0 && v5 )
    {
      v7 = _InterlockedDecrement(v5 + 6);
      if ( v7 )
      {
        if ( v7 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v5);
      }
    }
    if ( v22 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v22);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x360,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\AIXPolicyHelper.h",
      v2);
    return v20;
  }
  return v6;
}

```

## disassembly

```asm
0x18001c81c  mov     r11, rsp
0x18001c81f  push    rbx
0x18001c820  push    rsi
0x18001c821  push    rdi
0x18001c822  sub     rsp, 80h
0x18001c829  xor     esi, esi
0x18001c82b  mov     dword ptr [rsp+98h+arg_0], esi
0x18001c832  mov     byte ptr [rsp+98h+arg_0], sil
0x18001c83a  mov     [rsp+98h+var_58], 1
0x18001c842  mov     [rsp+98h+var_54], 1Dh
0x18001c84a  lea     rax, aSetdatalosspre; "SetDataLossPreventionProvider"
0x18001c851  mov     [r11-48h], rax
0x18001c855  lea     rax, [r11-58h]
0x18001c859  mov     [r11-60h], rax
0x18001c85d  mov     [rsp+98h+var_38], 1
0x18001c865  mov     [rsp+98h+var_34], 9
0x18001c86d  lea     rax, aWindowsai; "WindowsAI"
0x18001c874  mov     [r11-28h], rax
0x18001c878  lea     rax, [r11-38h]
0x18001c87c  mov     [r11-40h], rax
0x18001c880  lea     r8, [r11-60h]
0x18001c884  lea     rdx, [r11-40h]; struct winrt::param::hstring *
0x18001c888  lea     rcx, [r11+10h]; struct winrt::param::hstring *
0x18001c88c  call    ?GetPolicyFromPath@NamedPolicy@Policies@Management@Windows@winrt@@SA@AEBUhstring@param@5@0@Z; winrt::Windows::Management::Policies::NamedPolicy::GetPolicyFromPath(winrt::param::hstring const &,winrt::param::hstring const &)
0x18001c891  nop
0x18001c892  lea     rcx, [rsp+98h+arg_8]
0x18001c89a  call    ?IsManaged@?$consume_Windows_Management_Policies_INamedPolicyData@UINamedPolicyData@Policies@Management@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Management_Policies_INamedPolicyData<winrt::Windows::Management::Policies::INamedPolicyData>::IsManaged(void)
0x18001c89f  test    al, al
0x18001c8a1  jz      short loc_18001C8F6
0x18001c8a3  mov     [rsp+98h+lpMem], rsi
0x18001c8ab  mov     rcx, [rsp+98h+arg_8]
0x18001c8b3  mov     [rsp+98h+var_78], esi
0x18001c8b7  xorps   xmm0, xmm0
0x18001c8ba  movdqu  [rsp+98h+var_70], xmm0
0x18001c8c0  mov     rax, [rcx]
0x18001c8c3  lea     rdx, [rsp+98h+lpMem]
0x18001c8cb  mov     rax, [rax+80h]
0x18001c8d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c8d7  test    eax, eax
0x18001c8d9  js      loc_18001C971
0x18001c8df  mov     rbx, [rsp+98h+lpMem]
0x18001c8e7  mov     esi, 3
0x18001c8ec  test    rbx, rbx
0x18001c8ef  jz      short loc_18001C8FE
0x18001c8f1  mov     dil, 1
0x18001c8f4  jmp     short loc_18001C901
0x18001c8f6  mov     rbx, [rsp+98h+arg_0]
0x18001c8fe  xor     dil, dil
0x18001c901  mov     byte ptr [rsp+98h+arg_0], dil
0x18001c909  test    sil, 1
0x18001c90d  jz      short loc_18001C935
0x18001c90f  test    rbx, rbx
0x18001c912  jz      short loc_18001C935
0x18001c914  or      eax, 0FFFFFFFFh
0x18001c917  lock xadd [rbx+18h], eax
0x18001c91c  sub     eax, 1
0x18001c91f  jnz     short loc_18001C950
0x18001c921  nop
0x18001c922  call    WINRT_IMPL_GetProcessHeap
0x18001c927  mov     rcx, rax; hHeap
0x18001c92a  mov     r8, rbx; lpMem
0x18001c92d  xor     edx, edx; dwFlags
0x18001c92f  call    WINRT_IMPL_HeapFree
0x18001c934  nop
0x18001c935  cmp     [rsp+98h+arg_8], 0
0x18001c93e  jz      short loc_18001C94E
0x18001c940  lea     rcx, [rsp+98h+arg_8]
0x18001c948  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001c94d  nop
0x18001c94e  jmp     short loc_18001C963
0x18001c950  test    eax, eax
0x18001c952  jns     short loc_18001C935
0x18001c954  call    cs:__imp_abort
0x18001c95b  mov     dil, byte ptr [rsp+98h+arg_0]
0x18001c963  mov     al, dil
0x18001c966  add     rsp, 80h
0x18001c96d  pop     rdi
0x18001c96e  pop     rsi
0x18001c96f  pop     rbx
0x18001c970  retn
0x18001c971  lea     rdx, [rsp+98h+var_78]
0x18001c976  mov     ecx, eax
0x18001c978  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
