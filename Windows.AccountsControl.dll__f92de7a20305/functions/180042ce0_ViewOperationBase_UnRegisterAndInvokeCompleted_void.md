# ViewOperationBase::UnRegisterAndInvokeCompleted(void)

- ea: `0x180042ce0`
- end: `0x180042dda`
- name: `?UnRegisterAndInvokeCompleted@ViewOperationBase@@AEAAJXZ`
- size: `250`
- prototype: `__int64 __fastcall(ViewOperationBase *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003f220`
- `0x18003f470`

## callees

- `0x180011f64`
- `0x180011ffc`
- `0x180015850`
- `0x18001908c`
- `0x18003dc58`
- `0x18003e1e8`
- `0x180042ce0`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042cfc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042cfc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042d0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042d0a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180042d64`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180042d64`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180042d83`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180042d83`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ViewOperationBase::UnRegisterAndInvokeCompleted(ViewOperationBase *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  __int64 v3; // rax
  __int64 *v4; // rax
  __int64 v5; // rbx
  DWORD CurrentThreadId; // eax
  int v7; // edi
  _BYTE v9[32]; // [rsp+30h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  __int64 v11; // [rsp+70h] [rbp+20h] BYREF
  ViewOperationBase *v12; // [rsp+78h] [rbp+28h] BYREF
  __int64 v13; // [rsp+80h] [rbp+30h]

  LODWORD(v11) = 0;
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  if ( v2 )
    LeaveCriticalSection(v2);
  v12 = this;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v12);
  v3 = lambda_79c377706334d23a117ba252dfbddd20_::_lambda_79c377706334d23a117ba252dfbddd20_(v9, &v12, this, &v11);
  v4 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_79c377706334d23a117ba252dfbddd20_____lambda_79c377706334d23a117ba252dfbddd20___(
                    &v11,
                    v3);
  v5 = *v4;
  v13 = *v4;
  *v4 = 0;
  if ( v11 )
  {
    v11 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::ApplicationSettings::IViewOperation *,int>>::Release();
  }
  CurrentThreadId = GetCurrentThreadId();
  v7 = SHTaskPoolQueueTask(3, 0, CurrentThreadId, 0);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  if ( v7 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x153,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrolsharedlib\\viewoperationbase.cpp",
      (const char *)(unsigned int)v7,
      v5);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v9);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v12);
  return 0;
}

```

## disassembly

```asm
0x180042ce0  push    rbp
0x180042ce2  push    rbx
0x180042ce3  push    rdi
0x180042ce4  mov     rbp, rsp
0x180042ce7  sub     rsp, 50h
0x180042ceb  mov     rdi, rcx
0x180042cee  mov     dword ptr [rbp+arg_0], 0
0x180042cf5  lea     rbx, [rcx+30h]
0x180042cf9  mov     rcx, rbx; lpCriticalSection
0x180042cfc  call    cs:__imp_EnterCriticalSection
0x180042d02  test    rbx, rbx
0x180042d05  jz      short loc_180042D10
0x180042d07  mov     rcx, rbx; lpCriticalSection
0x180042d0a  call    cs:__imp_LeaveCriticalSection
0x180042d10  mov     [rbp+arg_8], rdi
0x180042d14  lea     rcx, [rbp+arg_8]
0x180042d18  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180042d1d  nop
0x180042d1e  lea     r9, [rbp+arg_0]
0x180042d22  mov     r8, rdi
0x180042d25  lea     rdx, [rbp+arg_8]
0x180042d29  lea     rcx, [rbp+var_20]
0x180042d2d  call    _lambda_79c377706334d23a117ba252dfbddd20____lambda_79c377706334d23a117ba252dfbddd20_
0x180042d32  nop
0x180042d33  mov     rdx, rax
0x180042d36  lea     rcx, [rbp+arg_0]
0x180042d3a  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_79c377706334d23a117ba252dfbddd20_____lambda_79c377706334d23a117ba252dfbddd20___
0x180042d3f  mov     rbx, [rax]
0x180042d42  mov     [rbp+arg_10], rbx
0x180042d46  mov     qword ptr [rax], 0
0x180042d4d  mov     rcx, [rbp+arg_0]
0x180042d51  test    rcx, rcx
0x180042d54  jz      short loc_180042D64
0x180042d56  mov     [rbp+arg_0], 0
0x180042d5e  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$ITypedEventHandler@PEAUIViewOperation@ApplicationSettings@UI@Internal@Windows@@H@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::ApplicationSettings::IViewOperation *,int>>::Release(void)
0x180042d63  nop
0x180042d64  call    cs:__imp_GetCurrentThreadId
0x180042d6a  mov     [rsp+50h+var_28], 0
0x180042d73  mov     qword ptr [rsp+50h+var_30], rbx; int
0x180042d78  xor     r9d, r9d
0x180042d7b  mov     r8d, eax
0x180042d7e  xor     edx, edx
0x180042d80  lea     ecx, [rdx+3]
0x180042d83  call    cs:__imp_SHTaskPoolQueueTask
0x180042d89  mov     edi, eax
0x180042d8b  test    rbx, rbx
0x180042d8e  jz      short loc_180042DA0
0x180042d90  mov     rdx, [rbx]
0x180042d93  mov     rcx, rbx
0x180042d96  mov     rax, [rdx+10h]
0x180042d9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042d9f  nop
0x180042da0  mov     rcx, [rbp+18h]; this
0x180042da4  test    edi, edi
0x180042da6  jns     short loc_180042DBD
0x180042da8  mov     r9d, edi; char *
0x180042dab  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\accountscontrol\\api"...
0x180042db2  mov     edx, 153h; void *
0x180042db7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180042dbc  nop
0x180042dbd  lea     rcx, [rbp+var_20]
0x180042dc1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180042dc6  nop
0x180042dc7  lea     rcx, [rbp+arg_8]
0x180042dcb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180042dd0  xor     eax, eax
0x180042dd2  add     rsp, 50h
0x180042dd6  pop     rdi
0x180042dd7  pop     rbx
0x180042dd8  pop     rbp
0x180042dd9  retn
```
