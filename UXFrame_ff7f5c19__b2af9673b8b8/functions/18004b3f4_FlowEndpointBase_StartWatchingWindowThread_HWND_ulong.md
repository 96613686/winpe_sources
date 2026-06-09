# FlowEndpointBase::StartWatchingWindowThread(HWND__ *,ulong)

- ea: `0x18004b3f4`
- end: `0x18004b51f`
- name: `?StartWatchingWindowThread@FlowEndpointBase@@IEAA_NPEAUHWND__@@K@Z`
- size: `299`
- prototype: `bool(FlowEndpointBase *__hidden this, HWND, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800447bc`

## callees

- `0x180017124`
- `0x18001a798`
- `0x18002d484`
- `0x18004b3f4`

## import_xrefs

- `USER32!PostMessageW` at `0x18004b4f9`
- `USER32!PostMessageW` at `0x18004b4f9`
- `USER32!GetWindowThreadProcessId` at `0x18004b416`
- `USER32!GetWindowThreadProcessId` at `0x18004b416`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18004b462`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18004b462`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessIdOfThread` at `0x18004b49c`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessIdOfThread` at `0x18004b49c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18004b4b8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18004b4b8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18004b4e1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18004b4e1`

## pseudocode

```c
bool __fastcall FlowEndpointBase::StartWatchingWindowThread(FlowEndpointBase *this, HWND a2)
{
  DWORD *v2; // rsi
  DWORD WindowThreadProcessId; // ebp
  bool v5; // bl
  DWORD v6; // ebx
  HANDLE v7; // rax
  PTP_WAIT ThreadpoolWait; // rax

  v2 = (DWORD *)((char *)this + 48);
  WindowThreadProcessId = GetWindowThreadProcessId(a2, (LPDWORD)this + 12);
  v5 = WindowThreadProcessId != 0;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl'::`2'::impl);
  if ( WindowThreadProcessId )
  {
    v6 = 0x100000;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl'::`2'::impl)
      && !*v2 )
    {
      v6 = 1050624;
    }
    v7 = OpenThread(v6, 0, WindowThreadProcessId);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 56,
      v7);
    v5 = (unsigned __int64)(*((_QWORD *)this + 7) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl'::`2'::impl) )
    {
      if ( v5 )
      {
        if ( !*v2 )
          *v2 = GetProcessIdOfThread(*((HANDLE *)this + 7));
        goto LABEL_10;
      }
    }
    else if ( v5 )
    {
LABEL_10:
      ThreadpoolWait = CreateThreadpoolWait(
                         FlowEndpointBase::s_OtherEndpointThreadDestroyedCallback,
                         *((PVOID *)this + 1),
                         0);
      wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
        (char *)this + 64,
        ThreadpoolWait);
      v5 = *((_QWORD *)this + 8) != 0;
      goto LABEL_11;
    }
LABEL_13:
    PostMessageW(*((HWND *)this + 1), 0x401u, 1u, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 56,
      0);
    return v5;
  }
LABEL_11:
  if ( !v5 )
    goto LABEL_13;
  SetThreadpoolWait(*((PTP_WAIT *)this + 8), *((HANDLE *)this + 7), 0);
  return v5;
}

```

## disassembly

```asm
0x18004b3f4  mov     [rsp+arg_0], rbx
0x18004b3f9  mov     [rsp+arg_8], rbp
0x18004b3fe  push    rsi
0x18004b3ff  push    rdi
0x18004b400  push    r14
0x18004b402  sub     rsp, 20h
0x18004b406  mov     rax, rdx
0x18004b409  lea     rsi, [rcx+30h]
0x18004b40d  mov     rdi, rcx
0x18004b410  mov     rdx, rsi; lpdwProcessId
0x18004b413  mov     rcx, rax; hWnd
0x18004b416  call    cs:__imp_GetWindowThreadProcessId
0x18004b41c  test    eax, eax
0x18004b41e  mov     ebp, eax
0x18004b420  setnz   bl
0x18004b423  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_4@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4> `wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl(void)'::`2'::impl
0x18004b42a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(void)
0x18004b42f  test    ebp, ebp
0x18004b431  jz      loc_18004B4D2
0x18004b437  mov     ebx, 100000h
0x18004b43c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_4@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4> `wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl(void)'::`2'::impl
0x18004b443  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(void)
0x18004b448  test    al, al
0x18004b44a  jz      short loc_18004B457
0x18004b44c  cmp     dword ptr [rsi], 0
0x18004b44f  mov     eax, 100800h
0x18004b454  cmovz   ebx, eax
0x18004b457  mov     r8d, ebp; dwThreadId
0x18004b45a  lea     r14, [rdi+38h]
0x18004b45e  xor     edx, edx; bInheritHandle
0x18004b460  mov     ecx, ebx; dwDesiredAccess
0x18004b462  call    cs:__imp_OpenThread
0x18004b468  mov     rdx, rax
0x18004b46b  mov     rcx, r14
0x18004b46e  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18004b473  mov     rax, [r14]
0x18004b476  dec     rax
0x18004b479  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004b47d  setbe   bl
0x18004b480  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_4@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4> `wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl(void)'::`2'::impl
0x18004b487  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(void)
0x18004b48c  test    al, al
0x18004b48e  jz      short loc_18004B4A6
0x18004b490  test    bl, bl
0x18004b492  jz      short loc_18004B4E9
0x18004b494  cmp     dword ptr [rsi], 0
0x18004b497  jnz     short loc_18004B4AA
0x18004b499  mov     rcx, [r14]; Thread
0x18004b49c  call    cs:__imp_GetProcessIdOfThread
0x18004b4a2  mov     [rsi], eax
0x18004b4a4  jmp     short loc_18004B4AA
0x18004b4a6  test    bl, bl
0x18004b4a8  jz      short loc_18004B4E9
0x18004b4aa  mov     rdx, [rdi+8]; pv
0x18004b4ae  lea     rcx, ?s_OtherEndpointThreadDestroyedCallback@FlowEndpointBase@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@K@Z; pfnwa
0x18004b4b5  xor     r8d, r8d; pcbe
0x18004b4b8  call    cs:__imp_CreateThreadpoolWait
0x18004b4be  mov     rdx, rax
0x18004b4c1  lea     rcx, [rdi+40h]
0x18004b4c5  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x18004b4ca  cmp     qword ptr [rdi+40h], 0
0x18004b4cf  setnz   bl
0x18004b4d2  test    bl, bl
0x18004b4d4  jz      short loc_18004B4E9
0x18004b4d6  mov     rdx, [rdi+38h]; h
0x18004b4da  xor     r8d, r8d; pftTimeout
0x18004b4dd  mov     rcx, [rdi+40h]; pwa
0x18004b4e1  call    cs:__imp_SetThreadpoolWait
0x18004b4e7  jmp     short loc_18004B50A
0x18004b4e9  mov     rcx, [rdi+8]; hWnd
0x18004b4ed  xor     r9d, r9d; lParam
0x18004b4f0  mov     edx, 401h; Msg
0x18004b4f5  lea     r8d, [r9+1]; wParam
0x18004b4f9  call    cs:__imp_PostMessageW
0x18004b4ff  xor     edx, edx
0x18004b501  lea     rcx, [rdi+38h]
0x18004b505  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18004b50a  mov     rbp, [rsp+38h+arg_8]
0x18004b50f  mov     al, bl
0x18004b511  mov     rbx, [rsp+38h+arg_0]
0x18004b516  add     rsp, 20h
0x18004b51a  pop     r14
0x18004b51c  pop     rdi
0x18004b51d  pop     rsi
0x18004b51e  retn
```
