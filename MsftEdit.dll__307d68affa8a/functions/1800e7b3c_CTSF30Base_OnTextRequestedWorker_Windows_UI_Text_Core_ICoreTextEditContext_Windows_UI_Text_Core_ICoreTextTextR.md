# CTSF30Base::OnTextRequestedWorker(Windows::UI::Text::Core::ICoreTextEditContext *,Windows::UI::Text::Core::ICoreTextTextRequestedEventArgs *)

- ea: `0x1800e7b3c`
- end: `0x1800e7e07`
- name: `?OnTextRequestedWorker@CTSF30Base@@QEAAJPEAUICoreTextEditContext@Core@Text@UI@Windows@@PEAUICoreTextTextRequestedEventArgs@3456@@Z`
- size: `715`
- prototype: `__int64 __fastcall(CTSF30Base *__hidden this, struct Windows::UI::Text::Core::ICoreTextEditContext *, struct Windows::UI::Text::Core::ICoreTextTextRequestedEventArgs *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800e7b30`

## callees

- `0x180021928`
- `0x1800277c0`
- `0x180048d5c`
- `0x1800e1264`
- `0x1800e7b3c`
- `0x1800e7e10`
- `0x180206624`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e7ca3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e7d19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e7ca3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e7d19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800e7d2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800e7d2c`

## pseudocode

```c
__int64 __fastcall CTSF30Base::OnTextRequestedWorker(
        CTSF30Base *this,
        struct Windows::UI::Text::Core::ICoreTextEditContext *a2,
        struct Windows::UI::Text::Core::ICoreTextTextRequestedEventArgs *a3)
{
  __int64 v3; // rax
  __int64 (__fastcall *v6)(struct Windows::UI::Text::Core::ICoreTextTextRequestedEventArgs *, __int64 *); // rbx
  int v7; // eax
  __int64 v8; // rcx
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rcx
  int v12; // ebx
  int v13; // eax
  CTSF30Base *v14; // rcx
  int v15; // eax
  const WCHAR *v16; // rdi
  unsigned __int64 v17; // rbx
  __int64 v18; // rcx
  unsigned __int16 *v19; // rcx
  struct ITextRange2 *v20; // rcx
  __int64 v21; // rcx
  HRESULT v23; // eax
  __int64 v24; // rcx
  unsigned __int16 *v25; // rcx
  struct ITextRange2 *v26; // rcx
  __int64 v27; // rcx
  struct ITextRange2 *v28; // [rsp+30h] [rbp-20h] BYREF
  __int64 v29; // [rsp+38h] [rbp-18h] BYREF
  HSTRING string; // [rsp+40h] [rbp-10h] BYREF
  __int64 v31; // [rsp+48h] [rbp-8h] BYREF
  struct Windows::UI::Text::Core::ICoreTextEditContext *v32; // [rsp+88h] [rbp+38h] BYREF
  __int64 v33; // [rsp+90h] [rbp+40h] BYREF
  PCNZWCH sourceString; // [rsp+98h] [rbp+48h] BYREF

  v32 = a2;
  v3 = *(_QWORD *)a3;
  v29 = 0;
  v33 = 0;
  v6 = *(__int64 (__fastcall **)(struct Windows::UI::Text::Core::ICoreTextTextRequestedEventArgs *, __int64 *))(v3 + 48);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
  v7 = v6(a3, &v33);
  v8 = v33;
  if ( v7 < 0 )
  {
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    return 2147500037LL;
  }
  else
  {
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v33 + 48LL))(v33, &v29);
    v9 = *((_QWORD *)this + 13) + 16LL;
    v28 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, struct ITextRange2 **))(*(_QWORD *)v9 + 424LL))(
            v9,
            (unsigned int)v29,
            HIDWORD(v29),
            &v28);
    sourceString = 0;
    v11 = 0;
    v31 = 0;
    v12 = v10;
    if ( v10 >= 0 )
    {
      v13 = ((__int64 (__fastcall *)(struct ITextRange2 *, __int64 *))v28->lpVtbl->GetFont2)(v28, &v31);
      v11 = v31;
      v12 = v13;
    }
    LODWORD(v32) = 0;
    if ( v12 < 0
      || (v12 = (*(__int64 (__fastcall **)(__int64, struct Windows::UI::Text::Core::ICoreTextEditContext **))(*(_QWORD *)v11 + 208LL))(
                  v11,
                  &v32),
          v12 < 0)
      || (CTxtEdit::fHiddenPassword(*((CTxtEdit **)this + 13))
        ? (v12 = CTSF30Base::FillWithPasswordCharacter(
                   this,
                   (unsigned __int16 **)&sourceString,
                   HIDWORD(v29) - (int)v29),
           v15 = 0,
           LODWORD(v32) = 0)
        : (v12 = ((__int64 (__fastcall *)(struct ITextRange2 *, PCNZWCH *))v28->lpVtbl->GetText)(v28, &sourceString),
           v15 = (int)v32),
          v12 < 0) )
    {
LABEL_12:
      string = 0;
      if ( v12 < 0 )
      {
LABEL_20:
        WindowsDeleteString(string);
        v18 = v31;
        string = 0;
        if ( v31 )
        {
          v31 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        }
        v19 = (unsigned __int16 *)sourceString;
        if ( sourceString )
        {
          sourceString = 0;
          CW32System::SysFreeString(v19);
        }
        v20 = v28;
        if ( v28 )
        {
          v28 = 0;
          ((void (__fastcall *)(struct ITextRange2 *))v20->lpVtbl->Release)(v20);
        }
        v21 = v33;
        if ( v33 )
        {
          v33 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        }
        return (unsigned int)v12;
      }
      v16 = sourceString;
      if ( sourceString )
      {
        v17 = -1;
        do
          ++v17;
        while ( sourceString[v17] );
        if ( v17 > 0xFFFFFFFF )
        {
          v12 = -2147024362;
          goto LABEL_18;
        }
        WindowsDeleteString(0);
        string = 0;
        v23 = WindowsCreateString(v16, v17, &string);
      }
      else
      {
        v23 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&string, &WindowName, 0);
      }
      v12 = v23;
LABEL_18:
      if ( v12 >= 0 )
        v12 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v33 + 64LL))(v33, string);
      goto LABEL_20;
    }
    if ( sourceString )
    {
      if ( v15 )
        v12 = CTSF30Base::ConvertHiddenCharacters(v14, v28, (struct Resp::BStrHolder *)&sourceString);
      goto LABEL_12;
    }
    v24 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      v25 = (unsigned __int16 *)sourceString;
      if ( sourceString )
      {
        sourceString = 0;
        CW32System::SysFreeString(v25);
      }
    }
    v26 = v28;
    if ( v28 )
    {
      v28 = 0;
      ((void (__fastcall *)(struct ITextRange2 *))v26->lpVtbl->Release)(v26);
    }
    v27 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x1800e7b3c  mov     [rsp-28h+arg_8], rdx
0x1800e7b41  push    rbp
0x1800e7b42  push    rbx
0x1800e7b43  push    rsi
0x1800e7b44  push    rdi
0x1800e7b45  push    r14
0x1800e7b47  mov     rbp, rsp
0x1800e7b4a  sub     rsp, 50h
0x1800e7b4e  mov     rax, [r8]
0x1800e7b51  mov     rsi, rcx
0x1800e7b54  xor     r14d, r14d
0x1800e7b57  lea     rcx, [rbp+arg_10]
0x1800e7b5b  mov     rdi, r8
0x1800e7b5e  mov     [rbp+var_18], r14
0x1800e7b62  mov     [rbp+arg_10], r14
0x1800e7b66  mov     rbx, [rax+30h]
0x1800e7b6a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e7b6f  lea     rdx, [rbp+arg_10]
0x1800e7b73  mov     rcx, rdi
0x1800e7b76  mov     rax, rbx
0x1800e7b79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7b7e  mov     rcx, [rbp+arg_10]
0x1800e7b82  test    eax, eax
0x1800e7b84  js      loc_1800E7DBC
0x1800e7b8a  mov     rax, [rcx]
0x1800e7b8d  lea     rdx, [rbp+var_18]
0x1800e7b91  mov     rax, [rax+30h]
0x1800e7b95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7b9a  mov     rcx, [rsi+68h]
0x1800e7b9e  lea     r9, [rbp+var_20]
0x1800e7ba2  mov     r8d, dword ptr [rbp+var_18+4]
0x1800e7ba6  add     rcx, 10h
0x1800e7baa  mov     edx, dword ptr [rbp+var_18]
0x1800e7bad  mov     [rbp+var_20], r14
0x1800e7bb1  mov     rax, [rcx]
0x1800e7bb4  mov     rax, [rax+1A8h]
0x1800e7bbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7bc0  mov     [rbp+sourceString], r14
0x1800e7bc4  mov     ecx, r14d
0x1800e7bc7  mov     [rbp+var_8], rcx
0x1800e7bcb  mov     ebx, eax
0x1800e7bcd  test    eax, eax
0x1800e7bcf  js      short loc_1800E7BEE
0x1800e7bd1  mov     rcx, [rbp+var_20]
0x1800e7bd5  lea     rdx, [rbp+var_8]
0x1800e7bd9  mov     rax, [rcx]
0x1800e7bdc  mov     rax, [rax+248h]
0x1800e7be3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7be8  mov     rcx, [rbp+var_8]
0x1800e7bec  mov     ebx, eax
0x1800e7bee  mov     dword ptr [rbp+arg_8], r14d
0x1800e7bf2  test    ebx, ebx
0x1800e7bf4  js      short loc_1800E7C4F
0x1800e7bf6  mov     rax, [rcx]
0x1800e7bf9  lea     rdx, [rbp+arg_8]
0x1800e7bfd  mov     rax, [rax+0D0h]
0x1800e7c04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7c09  mov     ebx, eax
0x1800e7c0b  test    eax, eax
0x1800e7c0d  js      short loc_1800E7C4F
0x1800e7c0f  mov     rcx, [rsi+68h]; this
0x1800e7c13  call    ?fHiddenPassword@CTxtEdit@@QEBA_NXZ; CTxtEdit::fHiddenPassword(void)
0x1800e7c18  lea     rdx, [rbp+sourceString]; unsigned __int16 **
0x1800e7c1c  test    al, al
0x1800e7c1e  jnz     loc_1800E7D9F
0x1800e7c24  mov     rcx, [rbp+var_20]
0x1800e7c28  mov     rax, [rcx]
0x1800e7c2b  mov     rax, [rax+38h]
0x1800e7c2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7c34  mov     ebx, eax
0x1800e7c36  mov     eax, dword ptr [rbp+arg_8]
0x1800e7c39  test    ebx, ebx
0x1800e7c3b  js      short loc_1800E7C4F
0x1800e7c3d  cmp     [rbp+sourceString], r14
0x1800e7c41  jz      loc_1800E7D39
0x1800e7c47  test    eax, eax
0x1800e7c49  jnz     loc_1800E7DDB
0x1800e7c4f  mov     [rbp+string], r14
0x1800e7c53  test    ebx, ebx
0x1800e7c55  js      short loc_1800E7C9F
0x1800e7c57  mov     rdi, [rbp+sourceString]
0x1800e7c5b  test    rdi, rdi
0x1800e7c5e  jz      loc_1800E7DEF
0x1800e7c64  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800e7c68  inc     rbx
0x1800e7c6b  cmp     [rdi+rbx*2], r14w
0x1800e7c70  jnz     short loc_1800E7C68
0x1800e7c72  mov     eax, 0FFFFFFFFh
0x1800e7c77  cmp     rbx, rax
0x1800e7c7a  jbe     loc_1800E7D17
0x1800e7c80  mov     ebx, 80070216h
0x1800e7c85  test    ebx, ebx
0x1800e7c87  js      short loc_1800E7C9F
0x1800e7c89  mov     rcx, [rbp+arg_10]
0x1800e7c8d  mov     rdx, [rbp+string]
0x1800e7c91  mov     rax, [rcx]
0x1800e7c94  mov     rax, [rax+40h]
0x1800e7c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7c9d  mov     ebx, eax
0x1800e7c9f  mov     rcx, [rbp+string]; string
0x1800e7ca3  call    cs:__imp_WindowsDeleteString
0x1800e7ca9  mov     rcx, [rbp+var_8]
0x1800e7cad  mov     [rbp+string], r14
0x1800e7cb1  test    rcx, rcx
0x1800e7cb4  jz      short loc_1800E7CC6
0x1800e7cb6  mov     [rbp+var_8], r14
0x1800e7cba  mov     rax, [rcx]
0x1800e7cbd  mov     rax, [rax+10h]
0x1800e7cc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7cc6  mov     rcx, [rbp+sourceString]; unsigned __int16 *
0x1800e7cca  test    rcx, rcx
0x1800e7ccd  jz      short loc_1800E7CD8
0x1800e7ccf  mov     [rbp+sourceString], r14
0x1800e7cd3  call    ?SysFreeString@CW32System@@SAXPEAG@Z; CW32System::SysFreeString(ushort *)
0x1800e7cd8  mov     rcx, [rbp+var_20]
0x1800e7cdc  test    rcx, rcx
0x1800e7cdf  jz      short loc_1800E7CF1
0x1800e7ce1  mov     [rbp+var_20], r14
0x1800e7ce5  mov     rax, [rcx]
0x1800e7ce8  mov     rax, [rax+10h]
0x1800e7cec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7cf1  mov     rcx, [rbp+arg_10]
0x1800e7cf5  test    rcx, rcx
0x1800e7cf8  jz      short loc_1800E7D0A
0x1800e7cfa  mov     [rbp+arg_10], r14
0x1800e7cfe  mov     rax, [rcx]
0x1800e7d01  mov     rax, [rax+10h]
0x1800e7d05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7d0a  mov     eax, ebx
0x1800e7d0c  add     rsp, 50h
0x1800e7d10  pop     r14
0x1800e7d12  pop     rdi
0x1800e7d13  pop     rsi
0x1800e7d14  pop     rbx
0x1800e7d15  pop     rbp
0x1800e7d16  retn
0x1800e7d17  xor     ecx, ecx; string
0x1800e7d19  call    cs:__imp_WindowsDeleteString
0x1800e7d1f  mov     edx, ebx; length
0x1800e7d21  mov     [rbp+string], r14
0x1800e7d25  lea     r8, [rbp+string]; string
0x1800e7d29  mov     rcx, rdi; sourceString
0x1800e7d2c  call    cs:__imp_WindowsCreateString
0x1800e7d32  mov     ebx, eax
0x1800e7d34  jmp     loc_1800E7C85
0x1800e7d39  mov     rcx, [rbp+var_8]
0x1800e7d3d  test    rcx, rcx
0x1800e7d40  jz      short loc_1800E7D5B
0x1800e7d42  mov     [rbp+var_8], r14
0x1800e7d46  mov     rax, [rcx]
0x1800e7d49  mov     rax, [rax+10h]
0x1800e7d4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7d52  mov     rcx, [rbp+sourceString]; unsigned __int16 *
0x1800e7d56  test    rcx, rcx
0x1800e7d59  jnz     short loc_1800E7D94
0x1800e7d5b  mov     rcx, [rbp+var_20]
0x1800e7d5f  test    rcx, rcx
0x1800e7d62  jz      short loc_1800E7D74
0x1800e7d64  mov     [rbp+var_20], r14
0x1800e7d68  mov     rax, [rcx]
0x1800e7d6b  mov     rax, [rax+10h]
0x1800e7d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7d74  mov     rcx, [rbp+arg_10]
0x1800e7d78  test    rcx, rcx
0x1800e7d7b  jz      short loc_1800E7D8D
0x1800e7d7d  mov     [rbp+arg_10], r14
0x1800e7d81  mov     rax, [rcx]
0x1800e7d84  mov     rax, [rax+10h]
0x1800e7d88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7d8d  xor     eax, eax
0x1800e7d8f  jmp     loc_1800E7D0C
0x1800e7d94  mov     [rbp+sourceString], r14
0x1800e7d98  call    ?SysFreeString@CW32System@@SAXPEAG@Z; CW32System::SysFreeString(ushort *)
0x1800e7d9d  jmp     short loc_1800E7D5B
0x1800e7d9f  mov     r8d, dword ptr [rbp+var_18+4]
0x1800e7da3  mov     rcx, rsi; this
0x1800e7da6  sub     r8d, dword ptr [rbp+var_18]; int
0x1800e7daa  call    ?FillWithPasswordCharacter@CTSF30Base@@AEAAJPEAPEAGJ@Z; CTSF30Base::FillWithPasswordCharacter(ushort * *,long)
0x1800e7daf  mov     ebx, eax
0x1800e7db1  mov     eax, r14d
0x1800e7db4  mov     dword ptr [rbp+arg_8], eax
0x1800e7db7  jmp     loc_1800E7C39
0x1800e7dbc  test    rcx, rcx
0x1800e7dbf  jz      short loc_1800E7DD1
0x1800e7dc1  mov     [rbp+arg_10], r14
0x1800e7dc5  mov     rax, [rcx]
0x1800e7dc8  mov     rax, [rax+10h]
0x1800e7dcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7dd1  mov     eax, 80004005h
0x1800e7dd6  jmp     loc_1800E7D0C
0x1800e7ddb  mov     rdx, [rbp+var_20]; struct ITextRange2 *
0x1800e7ddf  lea     r8, [rbp+sourceString]; struct Resp::BStrHolder *
0x1800e7de3  call    ?ConvertHiddenCharacters@CTSF30Base@@AEAAJPEAUITextRange2@@AEAVBStrHolder@Resp@@@Z; CTSF30Base::ConvertHiddenCharacters(ITextRange2 *,Resp::BStrHolder &)
0x1800e7de8  mov     ebx, eax
0x1800e7dea  jmp     loc_1800E7C4F
0x1800e7def  xor     r8d, r8d; unsigned int
0x1800e7df2  lea     rdx, WindowName; unsigned __int16 *
0x1800e7df9  lea     rcx, [rbp+string]; this
0x1800e7dfd  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x1800e7e02  jmp     loc_1800E7D32
```
