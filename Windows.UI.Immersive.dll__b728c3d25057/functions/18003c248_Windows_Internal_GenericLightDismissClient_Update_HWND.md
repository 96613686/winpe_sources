# Windows::Internal::GenericLightDismissClient::Update(HWND__ *)

- ea: `0x18003c248`
- end: `0x18003c436`
- name: `?Update@GenericLightDismissClient@Internal@Windows@@QEAAJPEAUHWND__@@@Z`
- size: `494`
- prototype: `__int64 __fastcall(Windows::Internal::GenericLightDismissClient *__hidden this, HWND)`
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180015e80`
- `0x18003c1f0`
- `0x1800a93c8`

## callees

- `0x18003217c`
- `0x18003c248`
- `0x18003c43c`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c26e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c26e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18003c41c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18003c41c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18003c2bf`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18003c2bf`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18003c407`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18003c407`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18003c28c`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18003c28c`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Internal::GenericLightDismissClient::Update(
        Windows::Internal::GenericLightDismissClient *this,
        HWND a2)
{
  __int64 v3; // rbx
  int LightDismissManager; // ebx
  __int64 v5; // rdx
  int v6; // eax
  int v7; // ecx
  Windows::Internal::GenericLightDismissClient *v8; // rcx
  struct ILightDismissProvider *v9; // rbx
  struct ILightDismissProvider *v10; // rcx
  _DWORD v12[2]; // [rsp+40h] [rbp-30h] BYREF
  HWND v13; // [rsp+48h] [rbp-28h]
  DWORD Parameter; // [rsp+50h] [rbp-20h] BYREF
  char v15; // [rsp+54h] [rbp-1Ch]
  HRESULT v16; // [rsp+58h] [rbp-18h]
  void *phNewTimer; // [rsp+60h] [rbp-10h] BYREF
  struct ILightDismissProvider *v18; // [rsp+80h] [rbp+10h] BYREF
  __int64 v19; // [rsp+88h] [rbp+18h] BYREF

  v12[1] = 0;
  v12[0] = *((_DWORD *)this + 1);
  v13 = a2;
  Parameter = GetCurrentThreadId();
  v15 = 0;
  phNewTimer = 0;
  v16 = CoEnableCallCancellation(0);
  if ( v16 >= 0 )
    CreateTimerQueueTimer(&phNewTimer, 0, CBaseRPCTimeout::s_Callback, &Parameter, 0x3E8u, 0x3E8u, 0);
  v3 = *((_QWORD *)this + 2);
  if ( v3 )
  {
    if ( *(_DWORD *)this == -1 )
    {
      LightDismissManager = -2147418113;
    }
    else
    {
      v19 = *((_QWORD *)this + 2);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
      v5 = *(unsigned int *)this;
      if ( (_DWORD)v5 )
      {
        v6 = (*(__int64 (__fastcall **)(__int64, __int64, _DWORD *))(*(_QWORD *)v3 + 32LL))(v3, v5, v12);
      }
      else
      {
        *(_DWORD *)this = -1;
        LODWORD(v18) = 0;
        v6 = (*(__int64 (__fastcall **)(__int64, _DWORD *, _QWORD, struct ILightDismissProvider **))(*(_QWORD *)v3 + 24LL))(
               v3,
               v12,
               *((_QWORD *)this + 1),
               &v18);
        v7 = 0;
        if ( v6 >= 0 )
          v7 = (int)v18;
        *(_DWORD *)this = v7;
      }
      LightDismissManager = v6;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
    }
  }
  else
  {
    v18 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
    LightDismissManager = Windows::Internal::GenericLightDismissClient::_GetLightDismissManager(v8, (LPVOID *)&v18);
    if ( LightDismissManager >= 0 && !*((_QWORD *)this + 2) )
    {
      v9 = v18;
      if ( v18 )
      {
        (*(void (__fastcall **)(struct ILightDismissProvider *))(*(_QWORD *)v18 + 8LL))(v18);
        v19 = *((_QWORD *)this + 2);
        *((_QWORD *)this + 2) = v9;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
      }
      LightDismissManager = (*(__int64 (__fastcall **)(_QWORD, _DWORD *, _QWORD, Windows::Internal::GenericLightDismissClient *))(**((_QWORD **)this + 2) + 24LL))(
                              *((_QWORD *)this + 2),
                              v12,
                              *((_QWORD *)this + 1),
                              this);
      if ( LightDismissManager < 0 )
        *(_DWORD *)this = 0;
    }
    v10 = v18;
    if ( v18 )
    {
      v18 = 0;
      (*(void (__fastcall **)(struct ILightDismissProvider *))(*(_QWORD *)v10 + 16LL))(v10);
    }
  }
  if ( v16 >= 0 )
  {
    v16 = -2147467259;
    CoDisableCallCancellation(0);
    if ( phNewTimer )
      DeleteTimerQueueTimer(0, phNewTimer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  }
  return (unsigned int)LightDismissManager;
}

```

## disassembly

```asm
0x18003c248  mov     [rsp-8+arg_10], rbx
0x18003c24d  mov     [rsp-8+arg_18], rdi
0x18003c252  push    rbp
0x18003c253  mov     rbp, rsp
0x18003c256  sub     rsp, 70h
0x18003c25a  mov     rdi, rcx
0x18003c25d  mov     dword ptr [rbp+var_30+4], 0
0x18003c264  mov     eax, [rcx+4]
0x18003c267  mov     dword ptr [rbp+var_30], eax
0x18003c26a  mov     qword ptr [rbp+var_30+8], rdx
0x18003c26e  call    cs:__imp_GetCurrentThreadId
0x18003c274  mov     [rbp+Parameter], eax
0x18003c277  mov     [rbp+var_1C], 0
0x18003c27b  mov     [rbp+var_18], 80004005h
0x18003c282  mov     [rbp+phNewTimer], 0
0x18003c28a  xor     ecx, ecx; pReserved
0x18003c28c  call    cs:__imp_CoEnableCallCancellation
0x18003c292  mov     [rbp+var_18], eax
0x18003c295  test    eax, eax
0x18003c297  js      short loc_18003C2C6
0x18003c299  mov     [rsp+70h+Flags], 0; Flags
0x18003c2a1  mov     eax, 3E8h
0x18003c2a6  mov     [rsp+70h+Period], eax; Period
0x18003c2aa  mov     [rsp+70h+DueTime], eax; DueTime
0x18003c2ae  lea     r9, [rbp+Parameter]; Parameter
0x18003c2b2  lea     r8, ?s_Callback@CBaseRPCTimeout@@CAXPEAXE@Z; Callback
0x18003c2b9  xor     edx, edx; TimerQueue
0x18003c2bb  lea     rcx, [rbp+phNewTimer]; phNewTimer
0x18003c2bf  call    cs:__imp_CreateTimerQueueTimer
0x18003c2c5  nop
0x18003c2c6  mov     rbx, [rdi+10h]
0x18003c2ca  test    rbx, rbx
0x18003c2cd  jz      loc_18003C355
0x18003c2d3  cmp     dword ptr [rdi], 0FFFFFFFFh
0x18003c2d6  jnz     short loc_18003C2E2
0x18003c2d8  mov     ebx, 8000FFFFh
0x18003c2dd  jmp     loc_18003C3F8
0x18003c2e2  mov     [rbp+arg_8], rbx
0x18003c2e6  mov     rax, [rbx]
0x18003c2e9  mov     rcx, rbx
0x18003c2ec  mov     rax, [rax+8]
0x18003c2f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c2f5  nop
0x18003c2f6  mov     edx, [rdi]
0x18003c2f8  movaps  xmm0, [rbp+var_30]
0x18003c2fc  mov     rcx, rbx
0x18003c2ff  movdqa  [rbp+var_30], xmm0
0x18003c304  test    edx, edx
0x18003c306  jnz     short loc_18003C335
0x18003c308  mov     dword ptr [rdi], 0FFFFFFFFh
0x18003c30e  mov     dword ptr [rbp+arg_0], edx
0x18003c311  mov     rax, [rbx]
0x18003c314  lea     r9, [rbp+arg_0]
0x18003c318  mov     r8, [rdi+8]
0x18003c31c  lea     rdx, [rbp+var_30]
0x18003c320  mov     rax, [rax+18h]
0x18003c324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c329  xor     ecx, ecx
0x18003c32b  test    eax, eax
0x18003c32d  cmovns  ecx, dword ptr [rbp+arg_0]
0x18003c331  mov     [rdi], ecx
0x18003c333  jmp     short loc_18003C345
0x18003c335  mov     rax, [rbx]
0x18003c338  lea     r8, [rbp+var_30]
0x18003c33c  mov     rax, [rax+20h]
0x18003c340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c345  mov     ebx, eax
0x18003c347  lea     rcx, [rbp+arg_8]
0x18003c34b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003c350  jmp     loc_18003C3F8
0x18003c355  mov     [rbp+arg_0], 0
0x18003c35d  lea     rcx, [rbp+arg_0]
0x18003c361  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003c366  lea     rdx, [rbp+arg_0]; struct ILightDismissProvider **
0x18003c36a  call    ?_GetLightDismissManager@GenericLightDismissClient@Internal@Windows@@AEAAJPEAPEAUILightDismissProvider@@@Z; Windows::Internal::GenericLightDismissClient::_GetLightDismissManager(ILightDismissProvider * *)
0x18003c36f  mov     ebx, eax
0x18003c371  test    eax, eax
0x18003c373  js      short loc_18003C3DA
0x18003c375  cmp     qword ptr [rdi+10h], 0
0x18003c37a  jnz     short loc_18003C3DA
0x18003c37c  mov     rbx, [rbp+arg_0]
0x18003c380  test    rbx, rbx
0x18003c383  jz      short loc_18003C3AA
0x18003c385  mov     rax, [rbx]
0x18003c388  mov     rcx, rbx
0x18003c38b  mov     rax, [rax+8]
0x18003c38f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c394  nop
0x18003c395  mov     rax, [rdi+10h]
0x18003c399  mov     [rbp+arg_8], rax
0x18003c39d  mov     [rdi+10h], rbx
0x18003c3a1  lea     rcx, [rbp+arg_8]
0x18003c3a5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003c3aa  mov     rcx, [rdi+10h]
0x18003c3ae  movaps  xmm0, [rbp+var_30]
0x18003c3b2  movdqa  [rbp+var_30], xmm0
0x18003c3b7  mov     rax, [rcx]
0x18003c3ba  mov     r9, rdi
0x18003c3bd  mov     r8, [rdi+8]
0x18003c3c1  lea     rdx, [rbp+var_30]
0x18003c3c5  mov     rax, [rax+18h]
0x18003c3c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c3ce  mov     ebx, eax
0x18003c3d0  test    eax, eax
0x18003c3d2  jns     short loc_18003C3DA
0x18003c3d4  mov     dword ptr [rdi], 0
0x18003c3da  mov     rcx, [rbp+arg_0]
0x18003c3de  test    rcx, rcx
0x18003c3e1  jz      short loc_18003C3F8
0x18003c3e3  mov     [rbp+arg_0], 0
0x18003c3eb  mov     rax, [rcx]
0x18003c3ee  mov     rax, [rax+10h]
0x18003c3f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c3f7  nop
0x18003c3f8  cmp     [rbp+var_18], 0
0x18003c3fc  jl      short loc_18003C422
0x18003c3fe  mov     [rbp+var_18], 80004005h
0x18003c405  xor     ecx, ecx; pReserved
0x18003c407  call    cs:__imp_CoDisableCallCancellation
0x18003c40d  mov     rdx, [rbp+phNewTimer]; Timer
0x18003c411  test    rdx, rdx
0x18003c414  jz      short loc_18003C422
0x18003c416  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18003c41a  xor     ecx, ecx; TimerQueue
0x18003c41c  call    cs:__imp_DeleteTimerQueueTimer
0x18003c422  mov     eax, ebx
0x18003c424  lea     r11, [rsp+70h+var_s0]
0x18003c429  mov     rbx, [r11+20h]
0x18003c42d  mov     rdi, [r11+28h]
0x18003c431  mov     rsp, r11
0x18003c434  pop     rbp
0x18003c435  retn
```
