# xpsrdr::DoesInformationsMatch(std::shared_ptr<IDWriteFont> const &,std::shared_ptr<IDWriteFont> const &)

- ea: `0x180043a74`
- end: `0x180043cbd`
- name: `?DoesInformationsMatch@xpsrdr@@YA_NAEBV?$shared_ptr@UIDWriteFont@@@std@@0@Z`
- size: `585`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180043d74`

## callees

- `0x180008830`
- `0x18000e15c`
- `0x18000e4c4`
- `0x18000e5ec`
- `0x180011b0c`
- `0x18001be30`
- `0x18001cf2c`
- `0x180037278`
- `0x180042ec8`
- `0x180043a74`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
char __fastcall xpsrdr::DoesInformationsMatch(__int64 **a1, __int64 **a2)
{
  __int64 i; // rdi
  __int64 *v5; // rcx
  __int64 v6; // rax
  int v7; // ebx
  int v8; // edx
  const char *v9; // r8
  int v10; // r9d
  __int64 *v11; // rcx
  __int64 v12; // rax
  int v13; // ebx
  int v14; // edx
  const char *v15; // r8
  int v16; // r9d
  unsigned int v17; // esi
  unsigned int j; // ebx
  int v20; // [rsp+30h] [rbp-49h] BYREF
  int v21; // [rsp+34h] [rbp-45h] BYREF
  int v22; // [rsp+38h] [rbp-41h] BYREF
  _QWORD v23[2]; // [rsp+40h] [rbp-39h] BYREF
  _QWORD v24[2]; // [rsp+50h] [rbp-29h] BYREF
  __int64 v25; // [rsp+60h] [rbp-19h] BYREF
  int *v26; // [rsp+68h] [rbp-11h]
  _QWORD *v27; // [rsp+70h] [rbp-9h]
  _BYTE v28[32]; // [rsp+80h] [rbp+7h] BYREF

  v22 = 0;
  v21 = 0;
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v24);
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v23);
  for ( i = 0; (unsigned int)i < 6; i = (unsigned int)(i + 1) )
  {
    v20 = 0;
    v5 = *a1;
    v6 = **a1;
    v25 = 0;
    v26 = &v20;
    v27 = v24;
    v7 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *, int *))(v6 + 72))(
           v5,
           *((unsigned int *)qword_18004E460 + i),
           &v25,
           &v22);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v25);
    if ( v20 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v20, v8, v9, v10);
    if ( v7 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v7, v8, v9, v10);
    v20 = 0;
    v11 = *a2;
    v12 = **a2;
    v25 = 0;
    v26 = &v20;
    v27 = v23;
    v13 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *, int *))(v12 + 72))(
            v11,
            *((unsigned int *)qword_18004E460 + i),
            &v25,
            &v21);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v25);
    if ( v20 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v20, v14, v15, v16);
    if ( v13 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v13, v14, v15, v16);
    if ( v22 )
    {
      if ( v21 )
      {
        v17 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v24[0] + 24LL))(v24[0]);
        if ( v17 == (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)v23[0] + 24LL))(v23[0]) )
        {
          std::wstring::wstring(v28);
          std::wstring::wstring(&v25);
          for ( j = 0; ; ++j )
          {
            if ( j >= v17 )
            {
              std::wstring::~wstring(&v25);
              std::wstring::~wstring(v28);
              goto LABEL_16;
            }
            xpsrdr::GetName<std::shared_ptr<IDWriteLocalizedStrings>>(v24, j, v28);
            xpsrdr::GetName<std::shared_ptr<IDWriteLocalizedStrings>>(v23, j, &v25);
            if ( !(unsigned __int8)std::operator==<wchar_t>(v28, &v25) )
              break;
          }
          std::wstring::~wstring(&v25);
          std::wstring::~wstring(v28);
        }
      }
LABEL_18:
      std::_Ptr_base<ID2D1RenderTarget>::_Decref(v23);
      std::_Ptr_base<ID2D1RenderTarget>::_Decref(v24);
      return 0;
    }
    if ( v21 )
      goto LABEL_18;
LABEL_16:
    ;
  }
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v23);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v24);
  return 1;
}

```

## disassembly

```asm
0x180043a74  mov     [rsp-8+arg_10], rbx
0x180043a79  mov     [rsp-8+arg_18], rsi
0x180043a7e  push    rbp
0x180043a7f  push    rdi
0x180043a80  push    r13
0x180043a82  push    r14
0x180043a84  push    r15
0x180043a86  lea     rbp, [rsp-37h]
0x180043a8b  sub     rsp, 0B0h
0x180043a92  mov     rax, cs:__security_cookie
0x180043a99  xor     rax, rsp
0x180043a9c  mov     [rbp+57h+var_30], rax
0x180043aa0  mov     r14, rdx
0x180043aa3  mov     r15, rcx
0x180043aa6  mov     [rbp+57h+var_98], 0
0x180043aad  mov     dword ptr [rbp+57h+var_A0+4], 0
0x180043ab4  lea     rcx, [rbp+57h+var_80]
0x180043ab8  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180043abd  nop
0x180043abe  lea     rcx, [rbp+57h+var_90]
0x180043ac2  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180043ac7  nop
0x180043ac8  xor     edi, edi
0x180043aca  cmp     edi, 6
0x180043acd  jnb     loc_180043C80
0x180043ad3  mov     dword ptr [rbp+57h+var_A0], 0
0x180043ada  mov     rcx, [r15]
0x180043add  mov     rax, [rcx]
0x180043ae0  mov     [rbp+57h+var_70], 0
0x180043ae8  lea     rdx, [rbp+57h+var_A0]
0x180043aec  mov     [rbp+57h+var_68], rdx
0x180043af0  lea     rdx, [rbp+57h+var_80]
0x180043af4  mov     [rbp+57h+var_60], rdx
0x180043af8  lea     r13, qword_18004E460
0x180043aff  lea     r9, [rbp+57h+var_98]
0x180043b03  lea     r8, [rbp+57h+var_70]
0x180043b07  mov     edx, [r13+rdi*4+0]
0x180043b0c  mov     rax, [rax+48h]
0x180043b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043b15  mov     ebx, eax
0x180043b17  lea     rcx, [rbp+57h+var_70]
0x180043b1b  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180043b20  mov     ecx, dword ptr [rbp+57h+var_A0]; this
0x180043b23  test    ecx, ecx
0x180043b25  js      loc_180043C7A
0x180043b2b  test    ebx, ebx
0x180043b2d  js      loc_180043C72
0x180043b33  mov     dword ptr [rbp+57h+var_A0], 0
0x180043b3a  mov     rcx, [r14]
0x180043b3d  mov     rax, [rcx]
0x180043b40  mov     [rbp+57h+var_70], 0
0x180043b48  lea     rdx, [rbp+57h+var_A0]
0x180043b4c  mov     [rbp+57h+var_68], rdx
0x180043b50  lea     rdx, [rbp+57h+var_90]
0x180043b54  mov     [rbp+57h+var_60], rdx
0x180043b58  lea     r9, [rbp+57h+var_A0+4]
0x180043b5c  lea     r8, [rbp+57h+var_70]
0x180043b60  mov     edx, [r13+rdi*4+0]
0x180043b65  mov     rax, [rax+48h]
0x180043b69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043b6e  mov     ebx, eax
0x180043b70  lea     rcx, [rbp+57h+var_70]
0x180043b74  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180043b79  mov     ecx, dword ptr [rbp+57h+var_A0]; this
0x180043b7c  test    ecx, ecx
0x180043b7e  js      loc_180043C6C
0x180043b84  test    ebx, ebx
0x180043b86  js      loc_180043C64
0x180043b8c  cmp     [rbp+57h+var_98], 0
0x180043b90  jz      loc_180043C2C
0x180043b96  cmp     dword ptr [rbp+57h+var_A0+4], 0
0x180043b9a  jz      loc_180043C4D
0x180043ba0  mov     rcx, [rbp+57h+var_80]
0x180043ba4  mov     rax, [rcx]
0x180043ba7  mov     rax, [rax+18h]
0x180043bab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043bb0  mov     esi, eax
0x180043bb2  mov     rcx, [rbp+57h+var_90]
0x180043bb6  mov     rax, [rcx]
0x180043bb9  mov     rax, [rax+18h]
0x180043bbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043bc2  cmp     esi, eax
0x180043bc4  jnz     loc_180043C4D
0x180043bca  lea     rcx, [rbp+57h+var_50]
0x180043bce  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180043bd3  nop
0x180043bd4  lea     rcx, [rbp+57h+var_70]
0x180043bd8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180043bdd  nop
0x180043bde  xor     ebx, ebx
0x180043be0  cmp     ebx, esi
0x180043be2  jnb     short loc_180043C17
0x180043be4  lea     r8, [rbp+57h+var_50]
0x180043be8  mov     edx, ebx
0x180043bea  lea     rcx, [rbp+57h+var_80]
0x180043bee  call    ??$GetName@V?$shared_ptr@UIDWriteLocalizedStrings@@@std@@@xpsrdr@@YAXAEBV?$shared_ptr@UIDWriteLocalizedStrings@@@std@@IAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; xpsrdr::GetName<std::shared_ptr<IDWriteLocalizedStrings>>(std::shared_ptr<IDWriteLocalizedStrings> const &,uint,std::wstring &)
0x180043bf3  lea     r8, [rbp+57h+var_70]
0x180043bf7  mov     edx, ebx
0x180043bf9  lea     rcx, [rbp+57h+var_90]
0x180043bfd  call    ??$GetName@V?$shared_ptr@UIDWriteLocalizedStrings@@@std@@@xpsrdr@@YAXAEBV?$shared_ptr@UIDWriteLocalizedStrings@@@std@@IAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; xpsrdr::GetName<std::shared_ptr<IDWriteLocalizedStrings>>(std::shared_ptr<IDWriteLocalizedStrings> const &,uint,std::wstring &)
0x180043c02  lea     rdx, [rbp+57h+var_70]
0x180043c06  lea     rcx, [rbp+57h+var_50]
0x180043c0a  call    ??$?8_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@0@Z; std::operator==<wchar_t>(std::wstring const &,std::wstring const &)
0x180043c0f  test    al, al
0x180043c11  jz      short loc_180043C39
0x180043c13  inc     ebx
0x180043c15  jmp     short loc_180043BE0
0x180043c17  lea     rcx, [rbp+57h+var_70]
0x180043c1b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180043c20  nop
0x180043c21  lea     rcx, [rbp+57h+var_50]
0x180043c25  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180043c2a  jmp     short loc_180043C32
0x180043c2c  cmp     dword ptr [rbp+57h+var_A0+4], 0
0x180043c30  jnz     short loc_180043C4D
0x180043c32  inc     edi
0x180043c34  jmp     loc_180043ACA
0x180043c39  lea     rcx, [rbp+57h+var_70]
0x180043c3d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180043c42  nop
0x180043c43  lea     rcx, [rbp+57h+var_50]
0x180043c47  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180043c4c  nop
0x180043c4d  lea     rcx, [rbp+57h+var_90]
0x180043c51  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180043c56  nop
0x180043c57  lea     rcx, [rbp+57h+var_80]
0x180043c5b  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180043c60  xor     al, al
0x180043c62  jmp     short loc_180043C95
0x180043c64  mov     ecx, ebx; this
0x180043c66  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180043c6c  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180043c72  mov     ecx, ebx; this
0x180043c74  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180043c7a  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180043c80  lea     rcx, [rbp+57h+var_90]
0x180043c84  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180043c89  nop
0x180043c8a  lea     rcx, [rbp+57h+var_80]
0x180043c8e  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180043c93  mov     al, 1
0x180043c95  mov     rcx, [rbp+57h+var_30]
0x180043c99  xor     rcx, rsp; StackCookie
0x180043c9c  call    __security_check_cookie
0x180043ca1  lea     r11, [rsp+0D0h+var_20]
0x180043ca9  mov     rbx, [r11+40h]
0x180043cad  mov     rsi, [r11+48h]
0x180043cb1  mov     rsp, r11
0x180043cb4  pop     r15
0x180043cb6  pop     r14
0x180043cb8  pop     r13
0x180043cba  pop     rdi
0x180043cbb  pop     rbp
0x180043cbc  retn
```
