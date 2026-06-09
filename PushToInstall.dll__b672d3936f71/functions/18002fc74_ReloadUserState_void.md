# ReloadUserState(void)

- ea: `0x18002fc74`
- end: `0x18002fd68`
- name: `?ReloadUserState@@YA?AV?$ComPtr@U?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@XZ`
- size: `244`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update`

## callers

- `0x18002f800`

## callees

- `0x18002008c`
- `0x18002d050`
- `0x18002d380`
- `0x18002fc74`
- `0x18004f010`

## string_xrefs

- `0x18002fd41`: `onecoreuap\enduser\winstore\pushtoinstall\lib\service.cpp`
- `0x18002fd56`: `onecoreuap\enduser\winstore\pushtoinstall\lib\service.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall ReloadUserState(_QWORD *a1, __int64 a2, unsigned int a3)
{
  int v4; // eax
  int v5; // eax
  __int64 v6; // rcx
  __int64 v7; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]
  __int64 v10; // [rsp+48h] [rbp+18h] BYREF
  __int64 v11; // [rsp+50h] [rbp+20h] BYREF

  *a1 = 0;
  GetActivationFactory<Windows::System::IUserStatics>((const WCHAR *)&v11, a2, a3);
  v10 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11 + 56LL))(v11, &v10);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x9B,
      (int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\service.cpp",
      (const char *)(unsigned int)v4,
      1);
  WaitForOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>(&v10);
  v5 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v10 + 64LL))(v10, a1);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x9F,
      (int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\service.cpp",
      (const char *)(unsigned int)v5,
      1);
  v6 = v10;
  if ( v10 )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  v7 = v11;
  if ( v11 )
  {
    v11 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  return a1;
}

```

## disassembly

```asm
0x18002fc74  mov     [rsp-8+arg_18], rbx
0x18002fc79  mov     [rsp-8+arg_0], rcx
0x18002fc7e  push    rbp
0x18002fc7f  mov     rbp, rsp
0x18002fc82  sub     rsp, 30h
0x18002fc86  mov     rbx, rcx
0x18002fc89  mov     [rbp+var_10], 0
0x18002fc90  mov     qword ptr [rcx], 0
0x18002fc97  mov     [rbp+var_10], 1
0x18002fc9e  lea     rcx, [rbp+arg_10]
0x18002fca2  call    ??$GetActivationFactory@UIUserStatics@System@Windows@@@@YA?AV?$ComPtr@UIUserStatics@System@Windows@@@WRL@Microsoft@@PEBG@Z; GetActivationFactory<Windows::System::IUserStatics>(ushort const *)
0x18002fca7  nop
0x18002fca8  mov     [rbp+arg_8], 0
0x18002fcb0  mov     rcx, [rbp+arg_10]
0x18002fcb4  mov     rax, [rcx]
0x18002fcb7  lea     rdx, [rbp+arg_8]
0x18002fcbb  mov     rax, [rax+38h]
0x18002fcbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fcc4  mov     rcx, [rbp+8]; this
0x18002fcc8  test    eax, eax
0x18002fcca  js      loc_18002FD53
0x18002fcd0  lea     rcx, [rbp+arg_8]
0x18002fcd4  call    ??$WaitForOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@@YAXAEBV?$ComPtr@U?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@WRL@Microsoft@@@Z; WaitForOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>(Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>> const &)
0x18002fcd9  mov     rcx, [rbp+arg_8]
0x18002fcdd  mov     rax, [rcx]
0x18002fce0  mov     rdx, rbx
0x18002fce3  mov     rax, [rax+40h]
0x18002fce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fcec  mov     rcx, [rbp+8]; this
0x18002fcf0  test    eax, eax
0x18002fcf2  js      short loc_18002FD3E
0x18002fcf4  mov     rcx, [rbp+arg_8]
0x18002fcf8  test    rcx, rcx
0x18002fcfb  jz      short loc_18002FD12
0x18002fcfd  mov     [rbp+arg_8], 0
0x18002fd05  mov     rax, [rcx]
0x18002fd08  mov     rax, [rax+10h]
0x18002fd0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd11  nop
0x18002fd12  mov     rcx, [rbp+arg_10]
0x18002fd16  test    rcx, rcx
0x18002fd19  jz      short loc_18002FD30
0x18002fd1b  mov     [rbp+arg_10], 0
0x18002fd23  mov     rax, [rcx]
0x18002fd26  mov     rax, [rax+10h]
0x18002fd2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd2f  nop
0x18002fd30  mov     rax, rbx
0x18002fd33  mov     rbx, [rsp+30h+arg_18]
0x18002fd38  add     rsp, 30h
0x18002fd3c  pop     rbp
0x18002fd3d  retn
0x18002fd3e  mov     r9d, eax; char *
0x18002fd41  lea     r8, aOnecoreuapEndu_14; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x18002fd48  mov     edx, 9Fh; void *
0x18002fd4d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002fd53  mov     r9d, eax; char *
0x18002fd56  lea     r8, aOnecoreuapEndu_14; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x18002fd5d  mov     edx, 9Bh; void *
0x18002fd62  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
