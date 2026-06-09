# CXAMLHostWindow::Hide(HideViewOptions)

- ea: `0x18002c2b0`
- end: `0x18002c400`
- name: `?Hide@CXAMLHostWindow@@UEAAJW4HideViewOptions@@@Z`
- size: `336`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180007b3c`
- `0x18002c2b0`
- `0x18002f9ac`
- `0x18002f9f0`
- `0x18007b010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x18002c3ae`
- `SHCORE!IUnknown_QueryService` at `0x18002c3ae`
- `USER32!ShowWindow` at `0x18002c36d`
- `USER32!ShowWindow` at `0x18002c36d`
- `dwmapi!DwmSetWindowAttribute` at `0x18002c2f6`
- `dwmapi!DwmSetWindowAttribute` at `0x18002c2f6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CXAMLHostWindow::Hide(__int64 a1, int a2)
{
  HWND v3; // rcx
  void *v4; // rdi
  void (__fastcall *v5)(void *, _QWORD); // rbx
  __int64 v6; // rax
  int v8; // [rsp+38h] [rbp+10h] BYREF
  void *ppvOut; // [rsp+40h] [rbp+18h] BYREF

  if ( a2 != 2 || *(_BYTE *)(a1 + 288) )
  {
    if ( *(_QWORD *)(a1 + 64) )
    {
      CXAMLHostWindow::_ReturnActivation((CXAMLHostWindow *)(a1 - 128));
      ShowWindow(*(HWND *)(a1 + 64), 0);
      if ( *(_DWORD *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 80) + 24LL))(*(_QWORD *)(a1 + 80)) == 8 )
      {
        ppvOut = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
        if ( IUnknown_QueryService(
               *(IUnknown **)(a1 - 16),
               &IID_IImmersiveApplicationManager,
               &GUID_bf63999f_7411_40da_861c_df72c0ffee84,
               &ppvOut) >= 0 )
        {
          v4 = ppvOut;
          v5 = *(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)ppvOut + 40LL);
          v6 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 80) + 24LL))(*(_QWORD *)(a1 + 80));
          v5(v4, *(_QWORD *)(v6 + 32));
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
      }
    }
  }
  else
  {
    v3 = *(HWND *)(a1 + 64);
    if ( v3 )
    {
      v8 = 1;
      DwmSetWindowAttribute(v3, 0xFu, &v8, 4u);
      *(_BYTE *)(a1 + 320) = 1;
      *(_WORD *)(a1 + 264) = 256;
      CXAMLHostWindow::_ShutdownXAML((CXAMLHostWindow *)(a1 - 128));
      *(_BYTE *)(a1 + 265) = 0;
      if ( *(_BYTE *)(a1 + 264) )
      {
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 24LL))(a1, *(unsigned int *)(a1 + 268));
        *(_DWORD *)(a1 + 268) = 1;
        *(_BYTE *)(a1 + 264) = 0;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002c2b0  mov     rax, rsp
0x18002c2b3  mov     [rax+8], rbx
0x18002c2b7  mov     [rax+20h], rsi
0x18002c2bb  push    rdi
0x18002c2bc  sub     rsp, 20h
0x18002c2c0  mov     rsi, rcx
0x18002c2c3  xor     edi, edi
0x18002c2c5  cmp     edx, 2
0x18002c2c8  jnz     loc_18002C354
0x18002c2ce  cmp     [rcx+120h], dil
0x18002c2d5  jnz     short loc_18002C354
0x18002c2d7  mov     rcx, [rcx+40h]; hwnd
0x18002c2db  test    rcx, rcx
0x18002c2de  jz      loc_18002C3EE
0x18002c2e4  mov     dword ptr [rax+10h], 1
0x18002c2eb  lea     r9d, [rdi+4]; cbAttribute
0x18002c2ef  lea     r8, [rax+10h]; pvAttribute
0x18002c2f3  lea     edx, [rdi+0Fh]; dwAttribute
0x18002c2f6  call    cs:__imp_DwmSetWindowAttribute
0x18002c2fc  mov     byte ptr [rsi+140h], 1
0x18002c303  mov     word ptr [rsi+108h], 100h
0x18002c30c  lea     rcx, [rsi-80h]; this
0x18002c310  call    ?_ShutdownXAML@CXAMLHostWindow@@AEAAXXZ; CXAMLHostWindow::_ShutdownXAML(void)
0x18002c315  mov     [rsi+109h], dil
0x18002c31c  cmp     [rsi+108h], dil
0x18002c323  jz      loc_18002C3EE
0x18002c329  mov     rax, [rsi]
0x18002c32c  mov     edx, [rsi+10Ch]
0x18002c332  mov     rcx, rsi
0x18002c335  mov     rax, [rax+18h]
0x18002c339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c33e  mov     dword ptr [rsi+10Ch], 1
0x18002c348  mov     [rsi+108h], dil
0x18002c34f  jmp     loc_18002C3EE
0x18002c354  cmp     [rcx+40h], rdi
0x18002c358  jz      loc_18002C3EE
0x18002c35e  add     rcx, 0FFFFFFFFFFFFFF80h; this
0x18002c362  call    ?_ReturnActivation@CXAMLHostWindow@@AEAAXXZ; CXAMLHostWindow::_ReturnActivation(void)
0x18002c367  xor     edx, edx; nCmdShow
0x18002c369  mov     rcx, [rsi+40h]; hWnd
0x18002c36d  call    cs:__imp_ShowWindow
0x18002c373  mov     rcx, [rsi+50h]
0x18002c377  mov     rax, [rcx]
0x18002c37a  mov     rax, [rax+18h]
0x18002c37e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c383  cmp     dword ptr [rax], 8
0x18002c386  jnz     short loc_18002C3EE
0x18002c388  mov     [rsp+28h+ppvOut], rdi
0x18002c38d  lea     rcx, [rsp+28h+ppvOut]
0x18002c392  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002c397  lea     r9, [rsp+28h+ppvOut]; ppvOut
0x18002c39c  lea     r8, _GUID_bf63999f_7411_40da_861c_df72c0ffee84; riid
0x18002c3a3  lea     rdx, IID_IImmersiveApplicationManager; guidService
0x18002c3aa  mov     rcx, [rsi-10h]; punk
0x18002c3ae  call    cs:__imp_IUnknown_QueryService
0x18002c3b4  test    eax, eax
0x18002c3b6  js      short loc_18002C3E4
0x18002c3b8  mov     rdi, [rsp+28h+ppvOut]
0x18002c3bd  mov     rax, [rdi]
0x18002c3c0  mov     rbx, [rax+28h]
0x18002c3c4  mov     rcx, [rsi+50h]
0x18002c3c8  mov     rdx, [rcx]
0x18002c3cb  mov     rax, [rdx+18h]
0x18002c3cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c3d4  mov     rdx, [rax+20h]
0x18002c3d8  mov     rcx, rdi
0x18002c3db  mov     rax, rbx
0x18002c3de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c3e3  nop
0x18002c3e4  lea     rcx, [rsp+28h+ppvOut]
0x18002c3e9  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002c3ee  xor     eax, eax
0x18002c3f0  mov     rbx, [rsp+28h+arg_0]
0x18002c3f5  mov     rsi, [rsp+28h+arg_18]
0x18002c3fa  add     rsp, 20h
0x18002c3fe  pop     rdi
0x18002c3ff  retn
```
