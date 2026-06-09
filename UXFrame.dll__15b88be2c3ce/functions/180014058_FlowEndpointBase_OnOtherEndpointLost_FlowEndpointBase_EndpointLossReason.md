# FlowEndpointBase::OnOtherEndpointLost(FlowEndpointBase::EndpointLossReason)

- ea: `0x180014058`
- end: `0x1800141b5`
- name: `?OnOtherEndpointLost@FlowEndpointBase@@IEAAXW4EndpointLossReason@1@@Z`
- size: `349`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001c8c0`
- `0x1800447bc`

## callees

- `0x180002b20`
- `0x1800041c4`
- `0x1800096f8`
- `0x180014058`
- `0x180014ac0`
- `0x180017024`
- `0x18005a010`

## import_xrefs

- `USER32!SendNotifyMessageW` at `0x1800140a9`
- `USER32!SendNotifyMessageW` at `0x1800140a9`
- `USER32!GetWindowThreadProcessId` at `0x180014103`
- `USER32!GetWindowThreadProcessId` at `0x180014103`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014147`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014147`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180014166`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180014166`

## string_xrefs

- `0x18001418e`: `ShellCommon\Internal\Shell\Inc\ValueSetChannel.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall FlowEndpointBase::OnOtherEndpointLost(__int64 a1, int a2)
{
  int v4; // esi
  HWND v5; // rcx
  void (__fastcall ***v6)(_QWORD, __int64, DWORD *); // rcx
  void (__fastcall **v7)(_QWORD, __int64, DWORD *); // rax
  HWND v8; // rcx
  DWORD WindowThreadProcessId; // eax
  __int64 *v10; // rax
  __int64 v11; // rbx
  DWORD CurrentThreadId; // eax
  int v13; // edi
  _DWORD v14[2]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v15; // [rsp+38h] [rbp-20h] BYREF
  DWORD dwProcessId[2]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+20h]

  v4 = *(_DWORD *)(a1 + 112);
  if ( (unsigned int)(v4 - 3) > 1 )
  {
    *(_DWORD *)(a1 + 112) = 3;
    if ( a2 != 2 )
    {
      v5 = *(HWND *)(a1 + 40);
      if ( v5 )
        SendNotifyMessageW(v5, 0x401u, 2u, 0);
    }
    if ( v4 )
    {
      v6 = *(void (__fastcall ****)(_QWORD, __int64, DWORD *))(a1 + 80);
      v7 = *v6;
      *(_QWORD *)dwProcessId = 0;
      (*v7)(v6, 1, dwProcessId);
      winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)dwProcessId);
    }
    if ( *(_BYTE *)(a1 + 92) )
    {
      if ( !a2 )
      {
        v8 = *(HWND *)(a1 + 40);
        if ( v8 )
        {
          dwProcessId[0] = 0;
          WindowThreadProcessId = GetWindowThreadProcessId(v8, dwProcessId);
          if ( WindowThreadProcessId )
          {
            v14[0] = dwProcessId[0];
            v14[1] = WindowThreadProcessId;
            v10 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_b84298806a3ade5bf2f206695eab1b51_ &>,_lambda_b84298806a3ade5bf2f206695eab1b51_ &>(
                               &v15,
                               v14);
            v11 = *v10;
            *v10 = 0;
            if ( v15 )
            {
              v15 = 0;
              Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,1,IWeakReference>::Release();
            }
            CurrentThreadId = GetCurrentThreadId();
            v13 = SHTaskPoolQueueTask(3, 0, CurrentThreadId, 0);
            if ( v11 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
            if ( v13 < 0 )
              wil::details::in1diag3::_Throw_Hr(
                retaddr,
                (void *)0x1EE,
                (unsigned int)"ShellCommon\\Internal\\Shell\\Inc\\ValueSetChannel.h",
                (const char *)(unsigned int)v13,
                v11);
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180014058  push    rbp
0x18001405a  push    rbx
0x18001405b  push    rsi
0x18001405c  push    rdi
0x18001405d  mov     rbp, rsp
0x180014060  sub     rsp, 58h
0x180014064  mov     rax, cs:__security_cookie
0x18001406b  xor     rax, rsp
0x18001406e  mov     [rbp+var_10], rax
0x180014072  mov     edi, edx
0x180014074  mov     rbx, rcx
0x180014077  mov     esi, [rcx+70h]
0x18001407a  lea     eax, [rsi-3]
0x18001407d  cmp     eax, 1
0x180014080  jbe     loc_1800141A0
0x180014086  mov     dword ptr [rcx+70h], 3
0x18001408d  mov     r8d, 2; wParam
0x180014093  cmp     edx, r8d
0x180014096  jz      short loc_1800140AF
0x180014098  mov     rcx, [rcx+28h]; hWnd
0x18001409c  test    rcx, rcx
0x18001409f  jz      short loc_1800140AF
0x1800140a1  xor     r9d, r9d; lParam
0x1800140a4  mov     edx, 401h; Msg
0x1800140a9  call    cs:__imp_SendNotifyMessageW
0x1800140af  test    esi, esi
0x1800140b1  jz      short loc_1800140DD
0x1800140b3  mov     rcx, [rbx+50h]
0x1800140b7  mov     rax, [rcx]
0x1800140ba  mov     qword ptr [rbp+dwProcessId], 0
0x1800140c2  lea     r8, [rbp+dwProcessId]
0x1800140c6  mov     edx, 1
0x1800140cb  mov     rax, [rax]
0x1800140ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140d3  nop
0x1800140d4  lea     rcx, [rbp+dwProcessId]; this
0x1800140d8  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x1800140dd  cmp     byte ptr [rbx+5Ch], 0
0x1800140e1  jz      loc_1800141A0
0x1800140e7  test    edi, edi
0x1800140e9  jnz     loc_1800141A0
0x1800140ef  mov     rcx, [rbx+28h]; hWnd
0x1800140f3  test    rcx, rcx
0x1800140f6  jz      loc_1800141A0
0x1800140fc  mov     [rbp+dwProcessId], edi
0x1800140ff  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x180014103  call    cs:__imp_GetWindowThreadProcessId
0x180014109  test    eax, eax
0x18001410b  jz      loc_1800141A0
0x180014111  mov     ecx, [rbp+dwProcessId]
0x180014114  mov     [rbp+var_28], ecx
0x180014117  mov     [rbp+var_24], eax
0x18001411a  lea     rdx, [rbp+var_28]
0x18001411e  lea     rcx, [rbp+var_20]
0x180014122  call    ??$Make@V?$CTaskWrapper@AEAV_lambda_b84298806a3ade5bf2f206695eab1b51_@@@ComTaskPool@Internal@Windows@@AEAV_lambda_b84298806a3ade5bf2f206695eab1b51_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@AEAV_lambda_b84298806a3ade5bf2f206695eab1b51_@@@ComTaskPool@Internal@Windows@@@12@AEAV_lambda_b84298806a3ade5bf2f206695eab1b51_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_b84298806a3ade5bf2f206695eab1b51_ &>,_lambda_b84298806a3ade5bf2f206695eab1b51_ &>(_lambda_b84298806a3ade5bf2f206695eab1b51_ &)
0x180014127  mov     rbx, [rax]
0x18001412a  mov     qword ptr [rax], 0
0x180014131  mov     rcx, [rbp+var_20]
0x180014135  test    rcx, rcx
0x180014138  jz      short loc_180014147
0x18001413a  mov     [rbp+var_20], 0
0x180014142  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$00UIWeakReference@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,1,IWeakReference>::Release(void)
0x180014147  call    cs:__imp_GetCurrentThreadId
0x18001414d  mov     [rsp+58h+var_30], 0
0x180014156  mov     qword ptr [rsp+58h+var_38], rbx; int
0x18001415b  xor     r9d, r9d
0x18001415e  mov     r8d, eax
0x180014161  xor     edx, edx
0x180014163  lea     ecx, [rdx+3]
0x180014166  call    cs:__imp_SHTaskPoolQueueTask
0x18001416c  mov     edi, eax
0x18001416e  test    rbx, rbx
0x180014171  jz      short loc_180014183
0x180014173  mov     rdx, [rbx]
0x180014176  mov     rcx, rbx
0x180014179  mov     rax, [rdx+10h]
0x18001417d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014182  nop
0x180014183  test    edi, edi
0x180014185  jns     short loc_1800141A0
0x180014187  mov     rcx, [rbp+20h]; this
0x18001418b  mov     r9d, edi; char *
0x18001418e  lea     r8, aShellcommonInt_0; "ShellCommon\\Internal\\Shell\\Inc\\Valu"...
0x180014195  mov     edx, 1EEh; void *
0x18001419a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800141a0  mov     rcx, [rbp+var_10]
0x1800141a4  xor     rcx, rsp; StackCookie
0x1800141a7  call    __security_check_cookie
0x1800141ac  add     rsp, 58h
0x1800141b0  pop     rdi
0x1800141b1  pop     rsi
0x1800141b2  pop     rbx
0x1800141b3  pop     rbp
0x1800141b4  retn
```
