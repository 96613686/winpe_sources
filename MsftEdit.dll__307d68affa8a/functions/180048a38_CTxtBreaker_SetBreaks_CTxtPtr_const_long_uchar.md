# CTxtBreaker::SetBreaks(CTxtPtr const &,long,uchar)

- ea: `0x180048a38`
- end: `0x180048d56`
- name: `?SetBreaks@CTxtBreaker@@QEAA_NAEBVCTxtPtr@@JE@Z`
- size: `798`
- prototype: `bool(CTxtBreaker *__hidden this, const struct CTxtPtr *, int, unsigned __int8)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180047d90`

## callees

- `0x180021a20`
- `0x180048490`
- `0x180048a38`
- `0x180048d5c`
- `0x180048f8c`
- `0x180068408`
- `0x18010d344`
- `0x18013bad0`
- `0x18013bea0`
- `0x18013c916`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048af7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048c4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048c85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048ce0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048af7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048c4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048c85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048ce0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180048b10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180048b10`

## pseudocode

```c
char __fastcall CTxtBreaker::SetBreaks(CBreakArray **this, const struct CTxtPtr *a2, UINT32 a3, char a4)
{
  const struct CTxtPtr *v4; // r12
  __int64 v7; // rsi
  unsigned __int16 *Buf; // rdi
  int (__fastcall *v10)(__int64, HSTRING, __int64 *); // rbx
  int v11; // r12d
  unsigned int v12; // r14d
  int v13; // r15d
  __int64 v14; // rdi
  int (__fastcall *v15)(__int64, _QWORD, __int64 *); // rbx
  int v16; // edi
  int i; // ebx
  __int64 v18; // rcx
  __int64 v19; // rcx
  unsigned __int64 v20; // rdx
  __int64 v21; // rcx
  unsigned __int64 v22; // rdx
  __int64 v23; // rcx
  unsigned __int64 v24; // rdx
  __int64 v25; // [rsp+20h] [rbp-E0h] BYREF
  HSTRING string; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v27; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v28; // [rsp+38h] [rbp-C8h] BYREF
  _DWORD v29[4]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v30[256]; // [rsp+50h] [rbp-B0h] BYREF
  void *v31; // [rsp+150h] [rbp+50h]
  int v32; // [rsp+158h] [rbp+58h]

  v4 = a2;
  LOBYTE(a2) = a4;
  GetSegmenter(&v28, a2);
  v7 = v28;
  Buf = 0;
  if ( !v28 )
    return 0;
  if ( a3 )
  {
    v29[0] = 0;
    v31 = v30;
    v32 = 256;
    v25 = 0;
    memset_0(v30, 0, sizeof(v30));
    if ( a3 + 1 < 0x3FFFFFFF )
      Buf = (unsigned __int16 *)CTempBuf::GetBuf((CTempBuf *)v30, 2 * (a3 + 1));
    CTxtPtr::GetText(v4, a3, Buf);
    WindowsDeleteString(0);
    string = 0;
    if ( WindowsCreateString(Buf, a3, &string)
      || (v10 = *(int (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v7 + 64LL),
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25),
          v10(v7, string, &v25) < 0)
      || (*(int (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v25 + 56LL))(v25, v29) < 0 )
    {
      WindowsDeleteString(string);
      string = 0;
      if ( v31 != v30 )
        operator delete(v31, v24);
      v21 = v25;
      if ( v25 )
      {
        v25 = 0;
LABEL_35:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      }
    }
    else
    {
      v11 = *((_DWORD *)v4 + 4);
      v12 = 0;
      v13 = v11;
      while ( 1 )
      {
        if ( v12 >= v29[0] )
        {
          WindowsDeleteString(string);
          string = 0;
          if ( v31 != v30 )
            operator delete(v31, v22);
          v23 = v25;
          if ( v25 )
          {
            v25 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
          }
          if ( v7 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
          return 1;
        }
        v27 = 0;
        v28 = 0;
        v14 = v25;
        v15 = *(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v25 + 48LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
        if ( v15(v14, v12, &v27) < 0
          || (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 56LL))(v27, &v28) < 0 )
        {
          break;
        }
        v16 = v11 + v28;
        for ( i = v11 + v28 + HIDWORD(v28) - v13; i; --i )
        {
          CBreakArray::SetBreak(this[3], v13, v13 == v16);
          ++v13;
        }
        v18 = v27;
        if ( v27 )
        {
          v27 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        }
        ++v12;
      }
      v19 = v27;
      if ( v27 )
      {
        v27 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      }
      WindowsDeleteString(string);
      string = 0;
      if ( v31 != v30 )
        operator delete(v31, v20);
      v21 = v25;
      if ( v25 )
      {
        v25 = 0;
        goto LABEL_35;
      }
    }
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    return 0;
  }
  Microsoft::WRL::ComPtr<Windows::Data::Text::ISelectableWordsSegmenter>::InternalRelease(&v28);
  return 1;
}

```

## disassembly

```asm
0x180048a38  mov     [rsp-8+arg_18], rbx
0x180048a3d  push    rbp
0x180048a3e  push    rsi
0x180048a3f  push    rdi
0x180048a40  push    r12
0x180048a42  push    r13
0x180048a44  push    r14
0x180048a46  push    r15
0x180048a48  lea     rbp, [rsp-70h]
0x180048a4d  sub     rsp, 170h
0x180048a54  mov     rax, cs:__security_cookie
0x180048a5b  xor     rax, rsp
0x180048a5e  mov     [rbp+0A0h+var_40], rax
0x180048a62  mov     r12, rdx
0x180048a65  mov     r13, rcx
0x180048a68  mov     dl, r9b
0x180048a6b  lea     rcx, [rsp+1A0h+var_168]
0x180048a70  mov     ebx, r8d
0x180048a73  call    ?GetSegmenter@@YA?AV?$ComPtr@UISelectableWordsSegmenter@Text@Data@Windows@@@WRL@Microsoft@@E@Z; GetSegmenter(uchar)
0x180048a78  mov     rsi, [rsp+1A0h+var_168]
0x180048a7d  xor     edi, edi
0x180048a7f  test    rsi, rsi
0x180048a82  jz      loc_180048D2D
0x180048a88  test    ebx, ebx
0x180048a8a  jnz     short loc_180048A9D
0x180048a8c  lea     rcx, [rsp+1A0h+var_168]
0x180048a91  call    ?InternalRelease@?$ComPtr@UISelectableWordsSegmenter@Text@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Text::ISelectableWordsSegmenter>::InternalRelease(void)
0x180048a96  mov     al, 1
0x180048a98  jmp     loc_180048D2F
0x180048a9d  lea     rax, [rsp+1A0h+var_150]
0x180048aa2  mov     [rsp+1A0h+var_160], edi
0x180048aa6  mov     r8d, 100h; Size
0x180048aac  mov     [rbp+0A0h+var_50], rax
0x180048ab0  xor     edx, edx; Val
0x180048ab2  mov     [rbp+0A0h+var_48], r8d
0x180048ab6  lea     rcx, [rsp+1A0h+var_150]; void *
0x180048abb  mov     [rsp+1A0h+var_180], rdi
0x180048ac0  call    memset_0
0x180048ac5  lea     edx, [rbx+1]
0x180048ac8  cmp     edx, 3FFFFFFFh
0x180048ace  jnb     short loc_180048ADF
0x180048ad0  add     edx, edx; int
0x180048ad2  lea     rcx, [rsp+1A0h+var_150]; this
0x180048ad7  call    ?GetBuf@CTempBuf@@QEAAPEAXJ@Z; CTempBuf::GetBuf(long)
0x180048adc  mov     rdi, rax
0x180048adf  mov     r8, rdi; unsigned __int16 *
0x180048ae2  mov     edx, ebx; int
0x180048ae4  mov     rcx, r12; this
0x180048ae7  call    ?GetText@CTxtPtr@@QEBAJJPEAG@Z; CTxtPtr::GetText(long,ushort *)
0x180048aec  xor     ecx, ecx; string
0x180048aee  mov     [rsp+1A0h+string], 0
0x180048af7  call    cs:__imp_WindowsDeleteString
0x180048afd  lea     r8, [rsp+1A0h+string]; string
0x180048b02  mov     [rsp+1A0h+string], 0
0x180048b0b  mov     edx, ebx; length
0x180048b0d  mov     rcx, rdi; sourceString
0x180048b10  call    cs:__imp_WindowsCreateString
0x180048b16  xor     edi, edi
0x180048b18  test    eax, eax
0x180048b1a  jnz     loc_180048CDB
0x180048b20  mov     rax, [rsi]
0x180048b23  lea     rcx, [rsp+1A0h+var_180]
0x180048b28  mov     rbx, [rax+40h]
0x180048b2c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048b31  mov     rdx, [rsp+1A0h+string]
0x180048b36  lea     r8, [rsp+1A0h+var_180]
0x180048b3b  mov     rcx, rsi
0x180048b3e  mov     rax, rbx
0x180048b41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048b46  test    eax, eax
0x180048b48  js      loc_180048CDB
0x180048b4e  mov     rcx, [rsp+1A0h+var_180]
0x180048b53  lea     rdx, [rsp+1A0h+var_160]
0x180048b58  mov     rax, [rcx]
0x180048b5b  mov     rax, [rax+38h]
0x180048b5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048b64  test    eax, eax
0x180048b66  js      loc_180048CDB
0x180048b6c  mov     r12d, [r12+10h]
0x180048b71  mov     r14d, edi
0x180048b74  mov     r15d, r12d
0x180048b77  cmp     r14d, [rsp+1A0h+var_160]
0x180048b7c  jnb     loc_180048C80
0x180048b82  mov     [rsp+1A0h+var_170], rdi
0x180048b87  lea     rcx, [rsp+1A0h+var_170]
0x180048b8c  mov     [rsp+1A0h+var_168], rdi
0x180048b91  mov     rdi, [rsp+1A0h+var_180]
0x180048b96  mov     rax, [rdi]
0x180048b99  mov     rbx, [rax+30h]
0x180048b9d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048ba2  lea     r8, [rsp+1A0h+var_170]
0x180048ba7  mov     edx, r14d
0x180048baa  mov     rcx, rdi
0x180048bad  mov     rax, rbx
0x180048bb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048bb5  xor     ebx, ebx
0x180048bb7  test    eax, eax
0x180048bb9  js      short loc_180048C2A
0x180048bbb  mov     rcx, [rsp+1A0h+var_170]
0x180048bc0  lea     rdx, [rsp+1A0h+var_168]
0x180048bc5  mov     rax, [rcx]
0x180048bc8  mov     rax, [rax+38h]
0x180048bcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048bd1  test    eax, eax
0x180048bd3  js      short loc_180048C2A
0x180048bd5  mov     edi, dword ptr [rsp+1A0h+var_168]
0x180048bd9  mov     ebx, dword ptr [rsp+1A0h+var_168+4]
0x180048bdd  add     edi, r12d
0x180048be0  sub     ebx, r15d
0x180048be3  add     ebx, edi
0x180048be5  jz      short loc_180048C05
0x180048be7  mov     rcx, [r13+18h]; this
0x180048beb  xor     r8d, r8d
0x180048bee  cmp     r15d, edi
0x180048bf1  mov     edx, r15d; int
0x180048bf4  setz    r8b; int
0x180048bf8  call    ?SetBreak@CBreakArray@@QEAAXJH@Z; CBreakArray::SetBreak(long,int)
0x180048bfd  inc     r15d
0x180048c00  sub     ebx, 1
0x180048c03  jnz     short loc_180048BE7
0x180048c05  mov     rcx, [rsp+1A0h+var_170]
0x180048c0a  xor     edi, edi
0x180048c0c  test    rcx, rcx
0x180048c0f  jz      short loc_180048C22
0x180048c11  mov     [rsp+1A0h+var_170], rdi
0x180048c16  mov     rax, [rcx]
0x180048c19  mov     rax, [rax+10h]
0x180048c1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048c22  inc     r14d
0x180048c25  jmp     loc_180048B77
0x180048c2a  mov     rcx, [rsp+1A0h+var_170]
0x180048c2f  test    rcx, rcx
0x180048c32  jz      short loc_180048C45
0x180048c34  mov     [rsp+1A0h+var_170], rbx
0x180048c39  mov     rax, [rcx]
0x180048c3c  mov     rax, [rax+10h]
0x180048c40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048c45  mov     rcx, [rsp+1A0h+string]; string
0x180048c4a  call    cs:__imp_WindowsDeleteString
0x180048c50  mov     rcx, [rbp+0A0h+var_50]; void *
0x180048c54  lea     rax, [rsp+1A0h+var_150]
0x180048c59  mov     [rsp+1A0h+string], rbx
0x180048c5e  cmp     rcx, rax
0x180048c61  jz      short loc_180048C68
0x180048c63  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180048c68  mov     rcx, [rsp+1A0h+var_180]
0x180048c6d  test    rcx, rcx
0x180048c70  jz      loc_180048D19
0x180048c76  mov     [rsp+1A0h+var_180], rbx
0x180048c7b  jmp     loc_180048D0D
0x180048c80  mov     rcx, [rsp+1A0h+string]; string
0x180048c85  call    cs:__imp_WindowsDeleteString
0x180048c8b  mov     rcx, [rbp+0A0h+var_50]; void *
0x180048c8f  lea     rax, [rsp+1A0h+var_150]
0x180048c94  mov     [rsp+1A0h+string], rdi
0x180048c99  cmp     rcx, rax
0x180048c9c  jz      short loc_180048CA3
0x180048c9e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180048ca3  mov     rcx, [rsp+1A0h+var_180]
0x180048ca8  test    rcx, rcx
0x180048cab  jz      short loc_180048CBE
0x180048cad  mov     [rsp+1A0h+var_180], rdi
0x180048cb2  mov     rax, [rcx]
0x180048cb5  mov     rax, [rax+10h]
0x180048cb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048cbe  test    rsi, rsi
0x180048cc1  jz      loc_180048A96
0x180048cc7  mov     rax, [rsi]
0x180048cca  mov     rcx, rsi
0x180048ccd  mov     rax, [rax+10h]
0x180048cd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048cd6  jmp     loc_180048A96
0x180048cdb  mov     rcx, [rsp+1A0h+string]; string
0x180048ce0  call    cs:__imp_WindowsDeleteString
0x180048ce6  mov     rcx, [rbp+0A0h+var_50]; void *
0x180048cea  lea     rax, [rsp+1A0h+var_150]
0x180048cef  mov     [rsp+1A0h+string], rdi
0x180048cf4  cmp     rcx, rax
0x180048cf7  jz      short loc_180048CFE
0x180048cf9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180048cfe  mov     rcx, [rsp+1A0h+var_180]
0x180048d03  test    rcx, rcx
0x180048d06  jz      short loc_180048D19
0x180048d08  mov     [rsp+1A0h+var_180], rdi
0x180048d0d  mov     rax, [rcx]
0x180048d10  mov     rax, [rax+10h]
0x180048d14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048d19  test    rsi, rsi
0x180048d1c  jz      short loc_180048D2D
0x180048d1e  mov     rax, [rsi]
0x180048d21  mov     rcx, rsi
0x180048d24  mov     rax, [rax+10h]
0x180048d28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048d2d  xor     al, al
0x180048d2f  mov     rcx, [rbp+0A0h+var_40]
0x180048d33  xor     rcx, rsp; StackCookie
0x180048d36  call    __security_check_cookie
0x180048d3b  mov     rbx, [rsp+1A0h+arg_18]
0x180048d43  add     rsp, 170h
0x180048d4a  pop     r15
0x180048d4c  pop     r14
0x180048d4e  pop     r13
0x180048d50  pop     r12
0x180048d52  pop     rdi
0x180048d53  pop     rsi
0x180048d54  pop     rbp
0x180048d55  retn
```
