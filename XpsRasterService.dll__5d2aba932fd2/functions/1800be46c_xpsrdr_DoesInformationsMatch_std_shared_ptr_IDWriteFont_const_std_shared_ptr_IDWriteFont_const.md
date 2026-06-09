# xpsrdr::DoesInformationsMatch(std::shared_ptr<IDWriteFont> const &,std::shared_ptr<IDWriteFont> const &)

- ea: `0x1800be46c`
- end: `0x1800be6da`
- name: `?DoesInformationsMatch@xpsrdr@@YA_NAEBV?$shared_ptr@UIDWriteFont@@@std@@0@Z`
- size: `622`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800be794`

## callees

- `0x180003180`
- `0x1800a2c1c`
- `0x1800a5230`
- `0x1800a9530`
- `0x1800aba64`
- `0x1800ada28`
- `0x1800b20e8`
- `0x1800b8a30`
- `0x1800bd63c`
- `0x1800be46c`
- `0x1800c3010`

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
  __int64 v19; // rax
  __int64 v20; // r8
  int v22; // [rsp+30h] [rbp-49h] BYREF
  int v23; // [rsp+34h] [rbp-45h] BYREF
  int v24; // [rsp+38h] [rbp-41h] BYREF
  std::_Ref_count_base *v25[2]; // [rsp+40h] [rbp-39h] BYREF
  std::_Ref_count_base *v26[2]; // [rsp+50h] [rbp-29h] BYREF
  __int64 v27; // [rsp+60h] [rbp-19h] BYREF
  int *v28; // [rsp+68h] [rbp-11h]
  std::_Ref_count_base **v29; // [rsp+70h] [rbp-9h]
  _BYTE v30[16]; // [rsp+80h] [rbp+7h] BYREF
  __int64 v31; // [rsp+90h] [rbp+17h]

  v24 = 0;
  v23 = 0;
  *(_OWORD *)v26 = 0;
  *(_OWORD *)v25 = 0;
  for ( i = 0; (unsigned int)i < 6; i = (unsigned int)(i + 1) )
  {
    v22 = 0;
    v5 = *a1;
    v6 = **a1;
    v27 = 0;
    v28 = &v22;
    v29 = v26;
    v7 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *, int *))(v6 + 72))(
           v5,
           *((unsigned int *)qword_180114A00 + i),
           &v27,
           &v24);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v27);
    if ( v22 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v22, v8, v9, v10);
    if ( v7 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v7, v8, v9, v10);
    v22 = 0;
    v11 = *a2;
    v12 = **a2;
    v27 = 0;
    v28 = &v22;
    v29 = v25;
    v13 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *, int *))(v12 + 72))(
            v11,
            *((unsigned int *)qword_180114A00 + i),
            &v27,
            &v23);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v27);
    if ( v22 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v22, v14, v15, v16);
    if ( v13 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v13, v14, v15, v16);
    if ( v24 )
    {
      if ( v23 )
      {
        v17 = (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v26[0] + 24LL))(v26[0]);
        if ( v17 == (*(unsigned int (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v25[0] + 24LL))(v25[0]) )
        {
          std::wstring::wstring(v30);
          std::wstring::wstring(&v27);
          for ( j = 0; ; ++j )
          {
            if ( j >= v17 )
            {
              std::wstring::_Tidy_deallocate(&v27);
              std::wstring::_Tidy_deallocate(v30);
              goto LABEL_16;
            }
            xpsrdr::GetName<std::shared_ptr<IDWriteLocalizedStrings>>(v26, j, (__int64)v30);
            xpsrdr::GetName<std::shared_ptr<IDWriteLocalizedStrings>>(v25, j, (__int64)&v27);
            std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v27);
            v19 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v30);
            if ( !(unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(v19, v31, v20, v29) )
              break;
          }
          std::wstring::_Tidy_deallocate(&v27);
          std::wstring::_Tidy_deallocate(v30);
        }
      }
LABEL_18:
      if ( v25[1] )
        std::_Ref_count_base::_Decref(v25[1]);
      if ( v26[1] )
        std::_Ref_count_base::_Decref(v26[1]);
      return 0;
    }
    if ( v23 )
      goto LABEL_18;
LABEL_16:
    ;
  }
  if ( v25[1] )
    std::_Ref_count_base::_Decref(v25[1]);
  if ( v26[1] )
    std::_Ref_count_base::_Decref(v26[1]);
  return 1;
}

```

## disassembly

```asm
0x1800be46c  mov     [rsp-8+arg_10], rbx
0x1800be471  mov     [rsp-8+arg_18], rsi
0x1800be476  push    rbp
0x1800be477  push    rdi
0x1800be478  push    r13
0x1800be47a  push    r14
0x1800be47c  push    r15
0x1800be47e  lea     rbp, [rsp-37h]
0x1800be483  sub     rsp, 0B0h
0x1800be48a  mov     rax, cs:__security_cookie
0x1800be491  xor     rax, rsp
0x1800be494  mov     [rbp+57h+var_30], rax
0x1800be498  mov     r14, rdx
0x1800be49b  mov     r15, rcx
0x1800be49e  mov     [rbp+57h+var_98], 0
0x1800be4a5  mov     dword ptr [rbp+57h+var_A0+4], 0
0x1800be4ac  xorps   xmm0, xmm0
0x1800be4af  movdqu  xmmword ptr [rbp+57h+var_80], xmm0
0x1800be4b4  movdqu  xmmword ptr [rbp+57h+var_90], xmm0
0x1800be4b9  xor     edi, edi
0x1800be4bb  cmp     edi, 6
0x1800be4be  jnb     loc_1800BE693
0x1800be4c4  mov     dword ptr [rbp+57h+var_A0], 0
0x1800be4cb  mov     rcx, [r15]
0x1800be4ce  mov     rax, [rcx]
0x1800be4d1  mov     [rbp+57h+var_70], 0
0x1800be4d9  lea     rdx, [rbp+57h+var_A0]
0x1800be4dd  mov     [rbp+57h+var_68], rdx
0x1800be4e1  lea     rdx, [rbp+57h+var_80]
0x1800be4e5  mov     [rbp+57h+var_60], rdx
0x1800be4e9  lea     r13, qword_180114A00
0x1800be4f0  lea     r9, [rbp+57h+var_98]
0x1800be4f4  lea     r8, [rbp+57h+var_70]
0x1800be4f8  mov     edx, [r13+rdi*4+0]
0x1800be4fd  mov     rax, [rax+48h]
0x1800be501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be506  mov     ebx, eax
0x1800be508  lea     rcx, [rbp+57h+var_70]
0x1800be50c  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800be511  mov     ecx, dword ptr [rbp+57h+var_A0]; this
0x1800be514  test    ecx, ecx
0x1800be516  js      loc_1800BE68D
0x1800be51c  test    ebx, ebx
0x1800be51e  js      loc_1800BE685
0x1800be524  mov     dword ptr [rbp+57h+var_A0], 0
0x1800be52b  mov     rcx, [r14]
0x1800be52e  mov     rax, [rcx]
0x1800be531  mov     [rbp+57h+var_70], 0
0x1800be539  lea     rdx, [rbp+57h+var_A0]
0x1800be53d  mov     [rbp+57h+var_68], rdx
0x1800be541  lea     rdx, [rbp+57h+var_90]
0x1800be545  mov     [rbp+57h+var_60], rdx
0x1800be549  lea     r9, [rbp+57h+var_A0+4]
0x1800be54d  lea     r8, [rbp+57h+var_70]
0x1800be551  mov     edx, [r13+rdi*4+0]
0x1800be556  mov     rax, [rax+48h]
0x1800be55a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be55f  mov     ebx, eax
0x1800be561  lea     rcx, [rbp+57h+var_70]
0x1800be565  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800be56a  mov     ecx, dword ptr [rbp+57h+var_A0]; this
0x1800be56d  test    ecx, ecx
0x1800be56f  js      loc_1800BE67F
0x1800be575  test    ebx, ebx
0x1800be577  js      loc_1800BE677
0x1800be57d  cmp     [rbp+57h+var_98], 0
0x1800be581  jz      loc_1800BE635
0x1800be587  cmp     dword ptr [rbp+57h+var_A0+4], 0
0x1800be58b  jz      loc_1800BE656
0x1800be591  mov     rcx, [rbp+57h+var_80]
0x1800be595  mov     rax, [rcx]
0x1800be598  mov     rax, [rax+18h]
0x1800be59c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be5a1  mov     esi, eax
0x1800be5a3  mov     rcx, [rbp+57h+var_90]
0x1800be5a7  mov     rax, [rcx]
0x1800be5aa  mov     rax, [rax+18h]
0x1800be5ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be5b3  cmp     esi, eax
0x1800be5b5  jnz     loc_1800BE656
0x1800be5bb  lea     rcx, [rbp+57h+var_50]
0x1800be5bf  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800be5c4  nop
0x1800be5c5  lea     rcx, [rbp+57h+var_70]
0x1800be5c9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800be5ce  nop
0x1800be5cf  xor     ebx, ebx
0x1800be5d1  cmp     ebx, esi
0x1800be5d3  jnb     short loc_1800BE620
0x1800be5d5  lea     r8, [rbp+57h+var_50]
0x1800be5d9  mov     edx, ebx
0x1800be5db  lea     rcx, [rbp+57h+var_80]
0x1800be5df  call    ??$GetName@V?$shared_ptr@UIDWriteLocalizedStrings@@@std@@@xpsrdr@@YAXAEBV?$shared_ptr@UIDWriteLocalizedStrings@@@std@@IAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; xpsrdr::GetName<std::shared_ptr<IDWriteLocalizedStrings>>(std::shared_ptr<IDWriteLocalizedStrings> const &,uint,std::wstring &)
0x1800be5e4  lea     r8, [rbp+57h+var_70]
0x1800be5e8  mov     edx, ebx
0x1800be5ea  lea     rcx, [rbp+57h+var_90]
0x1800be5ee  call    ??$GetName@V?$shared_ptr@UIDWriteLocalizedStrings@@@std@@@xpsrdr@@YAXAEBV?$shared_ptr@UIDWriteLocalizedStrings@@@std@@IAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; xpsrdr::GetName<std::shared_ptr<IDWriteLocalizedStrings>>(std::shared_ptr<IDWriteLocalizedStrings> const &,uint,std::wstring &)
0x1800be5f3  lea     rcx, [rbp+57h+var_70]
0x1800be5f7  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800be5fc  mov     r8, rax
0x1800be5ff  lea     rcx, [rbp+57h+var_50]
0x1800be603  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800be608  mov     rcx, rax
0x1800be60b  mov     r9, [rbp+57h+var_60]
0x1800be60f  mov     rdx, [rbp+57h+var_40]
0x1800be613  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800be618  test    al, al
0x1800be61a  jz      short loc_1800BE642
0x1800be61c  inc     ebx
0x1800be61e  jmp     short loc_1800BE5D1
0x1800be620  lea     rcx, [rbp+57h+var_70]
0x1800be624  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800be629  nop
0x1800be62a  lea     rcx, [rbp+57h+var_50]
0x1800be62e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800be633  jmp     short loc_1800BE63B
0x1800be635  cmp     dword ptr [rbp+57h+var_A0+4], 0
0x1800be639  jnz     short loc_1800BE656
0x1800be63b  inc     edi
0x1800be63d  jmp     loc_1800BE4BB
0x1800be642  lea     rcx, [rbp+57h+var_70]
0x1800be646  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800be64b  nop
0x1800be64c  lea     rcx, [rbp+57h+var_50]
0x1800be650  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800be655  nop
0x1800be656  mov     rcx, [rbp+57h+var_90+8]; this
0x1800be65a  test    rcx, rcx
0x1800be65d  jz      short loc_1800BE665
0x1800be65f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800be664  nop
0x1800be665  mov     rcx, [rbp+57h+var_80+8]; this
0x1800be669  test    rcx, rcx
0x1800be66c  jz      short loc_1800BE673
0x1800be66e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800be673  xor     al, al
0x1800be675  jmp     short loc_1800BE6B2
0x1800be677  mov     ecx, ebx; this
0x1800be679  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800be67f  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800be685  mov     ecx, ebx; this
0x1800be687  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800be68d  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800be693  mov     rcx, [rbp+57h+var_90+8]; this
0x1800be697  test    rcx, rcx
0x1800be69a  jz      short loc_1800BE6A2
0x1800be69c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800be6a1  nop
0x1800be6a2  mov     rcx, [rbp+57h+var_80+8]; this
0x1800be6a6  test    rcx, rcx
0x1800be6a9  jz      short loc_1800BE6B0
0x1800be6ab  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800be6b0  mov     al, 1
0x1800be6b2  mov     rcx, [rbp+57h+var_30]
0x1800be6b6  xor     rcx, rsp; StackCookie
0x1800be6b9  call    __security_check_cookie
0x1800be6be  lea     r11, [rsp+0D0h+var_20]
0x1800be6c6  mov     rbx, [r11+40h]
0x1800be6ca  mov     rsi, [r11+48h]
0x1800be6ce  mov     rsp, r11
0x1800be6d1  pop     r15
0x1800be6d3  pop     r14
0x1800be6d5  pop     r13
0x1800be6d7  pop     rdi
0x1800be6d8  pop     rbp
0x1800be6d9  retn
```
