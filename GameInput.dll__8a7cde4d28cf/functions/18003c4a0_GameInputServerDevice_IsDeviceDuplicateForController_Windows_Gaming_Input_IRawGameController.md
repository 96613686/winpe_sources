# GameInputServerDevice::IsDeviceDuplicateForController(Windows::Gaming::Input::IRawGameController *)

- ea: `0x18003c4a0`
- end: `0x18003c711`
- name: `?IsDeviceDuplicateForController@GameInputServerDevice@@QEBA_NPEAUIRawGameController@Input@Gaming@Windows@@@Z`
- size: `625`
- prototype: `bool __fastcall(GameInputServerDevice *__hidden this, struct Windows::Gaming::Input::IRawGameController *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18003ee94`

## callees

- `0x18000d68c`
- `0x18003c4a0`
- `0x18003fe64`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18003c64f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18003c64f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c4d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c596`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c5e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c60d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c66e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c6dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c4d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c596`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c5e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c60d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c66e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c6dc`

## pseudocode

```c
bool __fastcall GameInputServerDevice::IsDeviceDuplicateForController(
        GameInputServerDevice *this,
        struct Windows::Gaming::Input::IRawGameController *a2)
{
  __int64 v2; // rdi
  HSTRING v3; // rcx
  int (__fastcall *v5)(__int64, HSTRING *); // rbx
  __int64 (__fastcall **v6)(struct Windows::Gaming::Input::IRawGameController *, GUID *, __int64 *); // rax
  int v7; // eax
  int v8; // eax
  __int64 (__fastcall ***v9)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v10; // rcx
  int v12; // eax
  __int64 v13; // rdi
  int (__fastcall *v14)(__int64, HSTRING *); // rbx
  __int64 v15; // rcx
  HRESULT v16; // eax
  int v17; // edx
  unsigned int v18; // r8d
  bool v19; // bl
  __int64 v20; // rcx
  __int64 (__fastcall ***v21)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v22; // rcx
  HSTRING string2; // [rsp+20h] [rbp-20h] BYREF
  HSTRING string; // [rsp+28h] [rbp-18h] BYREF
  __int64 v25; // [rsp+30h] [rbp-10h] BYREF
  INT32 result; // [rsp+70h] [rbp+30h] BYREF
  __int64 (__fastcall ***v27)(_QWORD, GUID *, __int64 *); // [rsp+80h] [rbp+40h] BYREF
  __int64 v28; // [rsp+88h] [rbp+48h] BYREF

  v2 = *((_QWORD *)this + 65);
  v3 = 0;
  string = 0;
  if ( !v2 )
    goto LABEL_13;
  v5 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v2 + 136LL);
  WindowsDeleteString(0);
  string = 0;
  if ( v5(v2, &string) < 0 )
  {
LABEL_12:
    v3 = string;
LABEL_13:
    WindowsDeleteString(v3);
    return 0;
  }
  if ( a2 )
    (*(void (__fastcall **)(struct Windows::Gaming::Input::IRawGameController *))(*(_QWORD *)a2 + 8LL))(a2);
  v6 = *(__int64 (__fastcall ***)(struct Windows::Gaming::Input::IRawGameController *, GUID *, __int64 *))a2;
  v28 = 0;
  v7 = (*v6)(a2, &GUID_debcfefe_f763_4670_940b_57aae2b143ff, &v28);
  if ( v7 < 0 )
  {
    GameInputFailFast((unsigned int)v7, 1692);
    JUMPOUT(0x18003C710LL);
  }
  v27 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v28 + 48LL))(
         v28,
         &v27);
  v9 = v27;
  if ( v8 < 0 )
  {
LABEL_7:
    if ( v9 )
    {
      v27 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v9)[2])(v9);
    }
    v10 = v28;
    if ( v28 )
    {
      v28 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    (*(void (__fastcall **)(struct Windows::Gaming::Input::IRawGameController *))(*(_QWORD *)a2 + 16LL))(a2);
    goto LABEL_12;
  }
  v25 = 0;
  v12 = (**v27)(v27, &GUID_c3542377_1ea7_4454_8deb_8aa6070db645, &v25);
  if ( v12 < 0 )
  {
    GameInputFailFast((unsigned int)v12, 1702);
    __debugbreak();
  }
  v13 = v25;
  string2 = 0;
  v14 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v25 + 136LL);
  WindowsDeleteString(0);
  string2 = 0;
  if ( v14(v13, &string2) < 0 )
  {
    WindowsDeleteString(string2);
    v15 = v25;
    string2 = 0;
    if ( v25 )
    {
      v25 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    v9 = v27;
    goto LABEL_7;
  }
  result = 0;
  v16 = WindowsCompareStringOrdinal(string, string2, &result);
  if ( v16 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v16, v17, v18);
    __debugbreak();
  }
  v19 = result == 0;
  WindowsDeleteString(string2);
  v20 = v25;
  string2 = 0;
  if ( v25 )
  {
    v25 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  }
  v21 = v27;
  if ( v27 )
  {
    v27 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v21)[2])(v21);
  }
  v22 = v28;
  if ( v28 )
  {
    v28 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  }
  (*(void (__fastcall **)(struct Windows::Gaming::Input::IRawGameController *))(*(_QWORD *)a2 + 16LL))(a2);
  WindowsDeleteString(string);
  return v19;
}

```

## disassembly

```asm
0x18003c4a0  push    rbp
0x18003c4a2  push    rbx
0x18003c4a3  push    rsi
0x18003c4a4  push    rdi
0x18003c4a5  push    r14
0x18003c4a7  mov     rbp, rsp
0x18003c4aa  sub     rsp, 40h
0x18003c4ae  mov     rdi, [rcx+208h]
0x18003c4b5  xor     r14d, r14d
0x18003c4b8  mov     ecx, r14d; string
0x18003c4bb  mov     rsi, rdx
0x18003c4be  mov     [rbp+string], rcx
0x18003c4c2  test    rdi, rdi
0x18003c4c5  jz      loc_18003C596
0x18003c4cb  mov     rax, [rdi]
0x18003c4ce  mov     rbx, [rax+88h]
0x18003c4d5  call    cs:__imp_WindowsDeleteString
0x18003c4dc  nop     dword ptr [rax+rax+00h]
0x18003c4e1  lea     rdx, [rbp+string]
0x18003c4e5  mov     [rbp+string], r14
0x18003c4e9  mov     rcx, rdi
0x18003c4ec  mov     rax, rbx
0x18003c4ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c4f4  test    eax, eax
0x18003c4f6  js      loc_18003C592
0x18003c4fc  test    rsi, rsi
0x18003c4ff  jz      short loc_18003C510
0x18003c501  mov     rax, [rsi]
0x18003c504  mov     rcx, rsi
0x18003c507  mov     rax, [rax+8]
0x18003c50b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c510  mov     rax, [rsi]
0x18003c513  lea     r8, [rbp+arg_18]
0x18003c517  lea     rdx, _GUID_debcfefe_f763_4670_940b_57aae2b143ff
0x18003c51e  mov     [rbp+arg_18], r14
0x18003c522  mov     rcx, rsi
0x18003c525  mov     rax, [rax]
0x18003c528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c52d  test    eax, eax
0x18003c52f  js      loc_18003C704
0x18003c535  mov     rcx, [rbp+arg_18]
0x18003c539  lea     rdx, [rbp+arg_10]
0x18003c53d  mov     [rbp+arg_10], r14
0x18003c541  mov     rax, [rcx]
0x18003c544  mov     rax, [rax+30h]
0x18003c548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c54d  mov     rcx, [rbp+arg_10]
0x18003c551  test    eax, eax
0x18003c553  jns     short loc_18003C5B0
0x18003c555  test    rcx, rcx
0x18003c558  jz      short loc_18003C56A
0x18003c55a  mov     [rbp+arg_10], r14
0x18003c55e  mov     rax, [rcx]
0x18003c561  mov     rax, [rax+10h]
0x18003c565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c56a  mov     rcx, [rbp+arg_18]
0x18003c56e  test    rcx, rcx
0x18003c571  jz      short loc_18003C583
0x18003c573  mov     [rbp+arg_18], r14
0x18003c577  mov     rax, [rcx]
0x18003c57a  mov     rax, [rax+10h]
0x18003c57e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c583  mov     rax, [rsi]
0x18003c586  mov     rcx, rsi
0x18003c589  mov     rax, [rax+10h]
0x18003c58d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c592  mov     rcx, [rbp+string]; string
0x18003c596  call    cs:__imp_WindowsDeleteString
0x18003c59d  nop     dword ptr [rax+rax+00h]
0x18003c5a2  xor     al, al
0x18003c5a4  add     rsp, 40h
0x18003c5a8  pop     r14
0x18003c5aa  pop     rdi
0x18003c5ab  pop     rsi
0x18003c5ac  pop     rbx
0x18003c5ad  pop     rbp
0x18003c5ae  retn
0x18003c5b0  mov     [rbp+var_10], r14
0x18003c5b4  lea     r8, [rbp+var_10]
0x18003c5b8  mov     rax, [rcx]
0x18003c5bb  lea     rdx, _GUID_c3542377_1ea7_4454_8deb_8aa6070db645
0x18003c5c2  mov     rax, [rax]
0x18003c5c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c5ca  test    eax, eax
0x18003c5cc  js      loc_18003C6EF
0x18003c5d2  mov     rdi, [rbp+var_10]
0x18003c5d6  xor     ecx, ecx; string
0x18003c5d8  mov     [rbp+string2], r14
0x18003c5dc  mov     rax, [rdi]
0x18003c5df  mov     rbx, [rax+88h]
0x18003c5e6  call    cs:__imp_WindowsDeleteString
0x18003c5ed  nop     dword ptr [rax+rax+00h]
0x18003c5f2  lea     rdx, [rbp+string2]
0x18003c5f6  mov     [rbp+string2], r14
0x18003c5fa  mov     rcx, rdi
0x18003c5fd  mov     rax, rbx
0x18003c600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c605  test    eax, eax
0x18003c607  jns     short loc_18003C63F
0x18003c609  mov     rcx, [rbp+string2]; string
0x18003c60d  call    cs:__imp_WindowsDeleteString
0x18003c614  nop     dword ptr [rax+rax+00h]
0x18003c619  mov     rcx, [rbp+var_10]
0x18003c61d  mov     [rbp+string2], r14
0x18003c621  test    rcx, rcx
0x18003c624  jz      short loc_18003C636
0x18003c626  mov     [rbp+var_10], r14
0x18003c62a  mov     rax, [rcx]
0x18003c62d  mov     rax, [rax+10h]
0x18003c631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c636  mov     rcx, [rbp+arg_10]
0x18003c63a  jmp     loc_18003C555
0x18003c63f  mov     rdx, [rbp+string2]; string2
0x18003c643  lea     r8, [rbp+result]; result
0x18003c647  mov     rcx, [rbp+string]; string1
0x18003c64b  mov     [rbp+result], r14d
0x18003c64f  call    cs:__imp_WindowsCompareStringOrdinal
0x18003c656  nop     dword ptr [rax+rax+00h]
0x18003c65b  test    eax, eax
0x18003c65d  js      loc_18003C6FC
0x18003c663  cmp     [rbp+result], r14d
0x18003c667  mov     rcx, [rbp+string2]; string
0x18003c66b  setz    bl
0x18003c66e  call    cs:__imp_WindowsDeleteString
0x18003c675  nop     dword ptr [rax+rax+00h]
0x18003c67a  mov     rcx, [rbp+var_10]
0x18003c67e  mov     [rbp+string2], r14
0x18003c682  test    rcx, rcx
0x18003c685  jz      short loc_18003C697
0x18003c687  mov     [rbp+var_10], r14
0x18003c68b  mov     rax, [rcx]
0x18003c68e  mov     rax, [rax+10h]
0x18003c692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c697  mov     rcx, [rbp+arg_10]
0x18003c69b  test    rcx, rcx
0x18003c69e  jz      short loc_18003C6B0
0x18003c6a0  mov     [rbp+arg_10], r14
0x18003c6a4  mov     rax, [rcx]
0x18003c6a7  mov     rax, [rax+10h]
0x18003c6ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c6b0  mov     rcx, [rbp+arg_18]
0x18003c6b4  test    rcx, rcx
0x18003c6b7  jz      short loc_18003C6C9
0x18003c6b9  mov     [rbp+arg_18], r14
0x18003c6bd  mov     rax, [rcx]
0x18003c6c0  mov     rax, [rax+10h]
0x18003c6c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c6c9  mov     rcx, [rsi]
0x18003c6cc  mov     rax, [rcx+10h]
0x18003c6d0  mov     rcx, rsi
0x18003c6d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c6d8  mov     rcx, [rbp+string]; string
0x18003c6dc  call    cs:__imp_WindowsDeleteString
0x18003c6e3  nop     dword ptr [rax+rax+00h]
0x18003c6e8  mov     al, bl
0x18003c6ea  jmp     loc_18003C5A4
0x18003c6ef  mov     edx, 6A6h
0x18003c6f4  mov     ecx, eax
0x18003c6f6  call    GameInputFailFast
0x18003c6fb  int     3; Trap to Debugger
0x18003c6fc  mov     ecx, eax; this
0x18003c6fe  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18003c703  int     3; Trap to Debugger
0x18003c704  mov     edx, 69Ch
0x18003c709  mov     ecx, eax
0x18003c70b  call    GameInputFailFast
```
