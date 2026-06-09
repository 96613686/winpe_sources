# RichEdit::PlatformAPIs::ExecuteRichContentUpdating(Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *,RichEdit::IRichEditSmartLinkHandler *)

- ea: `0x1801f4710`
- end: `0x1801f4962`
- name: `?ExecuteRichContentUpdating@PlatformAPIs@RichEdit@@UEAAJPEAUICoreTextRichContentUpdatingEventArgs@Core@Text@Internal@UI@Windows@@PEAUIRichEditSmartLinkHandler@2@@Z`
- size: `594`
- prototype: `__int64 __fastcall(RichEdit::PlatformAPIs *__hidden this, struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *, struct RichEdit::IRichEditSmartLinkHandler *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180021928`
- `0x180048d5c`
- `0x1801376bc`
- `0x1801f4710`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801f4872`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801f488b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801f4872`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801f488b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f4814`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f483c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f48ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f4911`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f4814`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f483c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f48ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f4911`

## pseudocode

```c
__int64 __fastcall RichEdit::PlatformAPIs::ExecuteRichContentUpdating(
        RichEdit::PlatformAPIs *this,
        struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *a2,
        struct RichEdit::IRichEditSmartLinkHandler *a3)
{
  __int64 v5; // rax
  char v6; // al
  __int64 v7; // r8
  __int64 result; // rax
  __int64 (__fastcall *v9)(struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *, __int64 *); // rax
  int v10; // eax
  int v11; // eax
  __int64 v12; // rax
  int v13; // r15d
  __int64 v14; // rax
  void (__fastcall *v15)(struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *, HSTRING *); // rbx
  void (__fastcall *v16)(struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *, HSTRING *); // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  unsigned __int16 *v18; // rdi
  const unsigned __int16 *v19; // rax
  unsigned __int16 *v20; // rbx
  __int64 v21; // rax
  HSTRING v22; // [rsp+30h] [rbp-50h] BYREF
  HSTRING string; // [rsp+38h] [rbp-48h] BYREF
  __int64 v24; // [rsp+40h] [rbp-40h] BYREF
  __int64 v25; // [rsp+48h] [rbp-38h] BYREF
  __int128 v26; // [rsp+50h] [rbp-30h] BYREF
  __int128 v27; // [rsp+60h] [rbp-20h]
  unsigned __int16 *v28; // [rsp+70h] [rbp-10h]
  int v29; // [rsp+C0h] [rbp+40h] BYREF
  UINT32 length; // [rsp+C8h] [rbp+48h] BYREF

  if ( !a3 )
  {
    v5 = *(_QWORD *)a2;
    return (*(__int64 (__fastcall **)(struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *, __int64))(v5 + 104))(
             a2,
             1);
  }
  v6 = (*(__int64 (__fastcall **)(struct RichEdit::IRichEditSmartLinkHandler *))(*(_QWORD *)a3 + 16LL))(a3);
  v7 = *(_QWORD *)a2;
  if ( v6 )
    return (*(__int64 (__fastcall **)(struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *, __int64))(v7 + 104))(
             a2,
             1);
  v9 = *(__int64 (__fastcall **)(struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *, __int64 *))(v7 + 48);
  v25 = 0;
  v10 = v9(a2, &v25);
  v29 = 0;
  if ( v10 < 0
    || (*(int (__fastcall **)(struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *, int *))(*(_QWORD *)a2 + 88LL))(
         a2,
         &v29) < 0 )
  {
    goto LABEL_14;
  }
  v11 = (*(__int64 (__fastcall **)(struct RichEdit::IRichEditSmartLinkHandler *))(*(_QWORD *)a3 + 8LL))(a3);
  if ( v29 != 4 )
  {
    if ( (v11 & v29) == 0 || (_DWORD)v25 == HIDWORD(v25) )
      goto LABEL_14;
    v12 = *(_QWORD *)a3;
    v24 = 0;
    v13 = (*(__int64 (__fastcall **)(struct RichEdit::IRichEditSmartLinkHandler *, __int64, _QWORD, __int64 *))(v12 + 24))(
            a3,
            v25,
            HIDWORD(v25),
            &v24);
    if ( v13 >= 0 )
    {
      v14 = *(_QWORD *)a2;
      string = 0;
      v22 = 0;
      length = 0;
      v15 = *(void (__fastcall **)(struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *, HSTRING *))(v14 + 72);
      WindowsDeleteString(0);
      v22 = 0;
      v15(a2, &v22);
      v16 = *(void (__fastcall **)(struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *, HSTRING *))(*(_QWORD *)a2 + 56LL);
      WindowsDeleteString(string);
      string = 0;
      v16(a2, &string);
      v26 = 0;
      v28 = 0;
      v27 = 0;
      StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
      v18 = CW32System::SysAllocString(StringRawBuffer);
      v19 = WindowsGetStringRawBuffer(v22, &length);
      v20 = CW32System::SysAllocString(v19);
      (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v24 + 112LL))(v24, (char *)&v26 + 4);
      (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v24 + 128LL))(v24, (char *)&v26 + 8);
      HIDWORD(v26) = v29;
      v21 = *(_QWORD *)a3;
      *((_QWORD *)&v27 + 1) = v18;
      v28 = v20;
      v13 = (*(__int64 (__fastcall **)(struct RichEdit::IRichEditSmartLinkHandler *, __int128 *))(v21 + 32))(a3, &v26);
      CW32System::SysFreeString(v18);
      CW32System::SysFreeString(v20);
      WindowsDeleteString(v22);
      v22 = 0;
      WindowsDeleteString(string);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
    if ( v13 < 0 )
      goto LABEL_14;
  }
  result = (**(__int64 (__fastcall ***)(struct RichEdit::IRichEditSmartLinkHandler *))a3)(a3);
  if ( (int)result < 0 )
  {
LABEL_14:
    v5 = *(_QWORD *)a2;
    return (*(__int64 (__fastcall **)(struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *, __int64))(v5 + 104))(
             a2,
             1);
  }
  return result;
}

```

## disassembly

```asm
0x1801f4710  mov     [rsp-28h+arg_0], rbx
0x1801f4715  push    rbp
0x1801f4716  push    rsi
0x1801f4717  push    rdi
0x1801f4718  push    r14
0x1801f471a  push    r15
0x1801f471c  mov     rbp, rsp
0x1801f471f  sub     rsp, 80h
0x1801f4726  mov     r14, r8
0x1801f4729  mov     rsi, rdx
0x1801f472c  test    r8, r8
0x1801f472f  jnz     short loc_1801F4739
0x1801f4731  mov     rax, [rdx]
0x1801f4734  jmp     loc_1801F493A
0x1801f4739  mov     rax, [r8]
0x1801f473c  mov     rcx, r14
0x1801f473f  mov     rax, [rax+10h]
0x1801f4743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f4748  mov     r8, [rsi]
0x1801f474b  mov     rcx, rsi
0x1801f474e  test    al, al
0x1801f4750  jz      short loc_1801F475B
0x1801f4752  mov     rax, [r8+68h]
0x1801f4756  jmp     loc_1801F4941
0x1801f475b  mov     rax, [r8+30h]
0x1801f475f  lea     rdx, [rbp+var_38]
0x1801f4763  mov     [rbp+var_38], 0
0x1801f476b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f4770  mov     [rbp+arg_10], 0
0x1801f4777  test    eax, eax
0x1801f4779  js      loc_1801F4937
0x1801f477f  mov     rax, [rsi]
0x1801f4782  lea     rdx, [rbp+arg_10]
0x1801f4786  mov     rcx, rsi
0x1801f4789  mov     rax, [rax+58h]
0x1801f478d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f4792  test    eax, eax
0x1801f4794  js      loc_1801F4937
0x1801f479a  mov     rax, [r14]
0x1801f479d  mov     rcx, r14
0x1801f47a0  mov     rax, [rax+8]
0x1801f47a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f47a9  mov     ecx, [rbp+arg_10]
0x1801f47ac  cmp     ecx, 4
0x1801f47af  jz      loc_1801F4925
0x1801f47b5  test    ecx, eax
0x1801f47b7  jz      loc_1801F4937
0x1801f47bd  mov     rdx, [rbp+var_38]
0x1801f47c1  mov     r8d, dword ptr [rbp+var_38+4]
0x1801f47c5  cmp     edx, r8d
0x1801f47c8  jz      loc_1801F4937
0x1801f47ce  mov     rax, [r14]
0x1801f47d1  lea     r9, [rbp+var_40]
0x1801f47d5  mov     rcx, r14
0x1801f47d8  mov     [rbp+var_40], 0
0x1801f47e0  mov     rax, [rax+18h]
0x1801f47e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f47e9  mov     r15d, eax
0x1801f47ec  test    eax, eax
0x1801f47ee  js      loc_1801F4917
0x1801f47f4  mov     rax, [rsi]
0x1801f47f7  xor     ecx, ecx; string
0x1801f47f9  mov     [rbp+string], 0
0x1801f4801  mov     [rbp+var_50], 0
0x1801f4809  mov     [rbp+length], 0
0x1801f4810  mov     rbx, [rax+48h]
0x1801f4814  call    cs:__imp_WindowsDeleteString
0x1801f481a  lea     rdx, [rbp+var_50]
0x1801f481e  mov     [rbp+var_50], 0
0x1801f4826  mov     rcx, rsi
0x1801f4829  mov     rax, rbx
0x1801f482c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f4831  mov     rax, [rsi]
0x1801f4834  mov     rcx, [rbp+string]; string
0x1801f4838  mov     rbx, [rax+38h]
0x1801f483c  call    cs:__imp_WindowsDeleteString
0x1801f4842  lea     rdx, [rbp+string]
0x1801f4846  mov     [rbp+string], 0
0x1801f484e  mov     rcx, rsi
0x1801f4851  mov     rax, rbx
0x1801f4854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f4859  mov     rcx, [rbp+string]; string
0x1801f485d  lea     rdx, [rbp+length]; length
0x1801f4861  xorps   xmm0, xmm0
0x1801f4864  xor     eax, eax
0x1801f4866  movups  [rbp+var_30], xmm0
0x1801f486a  mov     [rbp+var_10], rax
0x1801f486e  movups  [rbp+var_20], xmm0
0x1801f4872  call    cs:__imp_WindowsGetStringRawBuffer
0x1801f4878  mov     rcx, rax; unsigned __int16 *
0x1801f487b  call    ?SysAllocString@CW32System@@SAPEAGPEBG@Z; CW32System::SysAllocString(ushort const *)
0x1801f4880  mov     rcx, [rbp+var_50]; string
0x1801f4884  lea     rdx, [rbp+length]; length
0x1801f4888  mov     rdi, rax
0x1801f488b  call    cs:__imp_WindowsGetStringRawBuffer
0x1801f4891  mov     rcx, rax; unsigned __int16 *
0x1801f4894  call    ?SysAllocString@CW32System@@SAPEAGPEBG@Z; CW32System::SysAllocString(ushort const *)
0x1801f4899  mov     rcx, [rbp+var_40]
0x1801f489d  mov     rbx, rax
0x1801f48a0  mov     rdx, [rcx]
0x1801f48a3  mov     rax, [rdx+70h]
0x1801f48a7  lea     rdx, [rbp+var_30+4]
0x1801f48ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f48b0  mov     rcx, [rbp+var_40]
0x1801f48b4  mov     rdx, [rcx]
0x1801f48b7  mov     rax, [rdx+80h]
0x1801f48be  lea     rdx, [rbp+var_30+8]
0x1801f48c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f48c7  mov     eax, [rbp+arg_10]
0x1801f48ca  lea     rdx, [rbp+var_30]
0x1801f48ce  mov     dword ptr [rbp+var_30+0Ch], eax
0x1801f48d1  mov     rcx, r14
0x1801f48d4  mov     rax, [r14]
0x1801f48d7  mov     qword ptr [rbp+var_20+8], rdi
0x1801f48db  mov     [rbp+var_10], rbx
0x1801f48df  mov     rax, [rax+20h]
0x1801f48e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f48e8  mov     rcx, rdi; unsigned __int16 *
0x1801f48eb  mov     r15d, eax
0x1801f48ee  call    ?SysFreeString@CW32System@@SAXPEAG@Z; CW32System::SysFreeString(ushort *)
0x1801f48f3  mov     rcx, rbx; unsigned __int16 *
0x1801f48f6  call    ?SysFreeString@CW32System@@SAXPEAG@Z; CW32System::SysFreeString(ushort *)
0x1801f48fb  mov     rcx, [rbp+var_50]; string
0x1801f48ff  call    cs:__imp_WindowsDeleteString
0x1801f4905  mov     rcx, [rbp+string]; string
0x1801f4909  mov     [rbp+var_50], 0
0x1801f4911  call    cs:__imp_WindowsDeleteString
0x1801f4917  lea     rcx, [rbp+var_40]
0x1801f491b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801f4920  test    r15d, r15d
0x1801f4923  js      short loc_1801F4937
0x1801f4925  mov     rax, [r14]
0x1801f4928  mov     rcx, r14
0x1801f492b  mov     rax, [rax]
0x1801f492e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f4933  test    eax, eax
0x1801f4935  jns     short loc_1801F494B
0x1801f4937  mov     rax, [rsi]
0x1801f493a  mov     rax, [rax+68h]
0x1801f493e  mov     rcx, rsi
0x1801f4941  mov     edx, 1
0x1801f4946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f494b  mov     rbx, [rsp+80h+arg_0]
0x1801f4953  add     rsp, 80h
0x1801f495a  pop     r15
0x1801f495c  pop     r14
0x1801f495e  pop     rdi
0x1801f495f  pop     rsi
0x1801f4960  pop     rbp
0x1801f4961  retn
```
