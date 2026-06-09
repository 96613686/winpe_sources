# CTSF30Base::OnTextUpdatingWorker(Windows::UI::Text::Core::ICoreTextEditContext *,Windows::UI::Text::Core::ICoreTextTextUpdatingEventArgs *)

- ea: `0x1800e62d0`
- end: `0x1800e6747`
- name: `?OnTextUpdatingWorker@CTSF30Base@@QEAAJPEAUICoreTextEditContext@Core@Text@UI@Windows@@PEAUICoreTextTextUpdatingEventArgs@3456@@Z`
- size: `1143`
- prototype: `__int64 __fastcall(CTSF30Base *__hidden this, struct Windows::UI::Text::Core::ICoreTextEditContext *, struct Windows::UI::Text::Core::ICoreTextTextUpdatingEventArgs *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800e6200`

## callees

- `0x180021928`
- `0x180021b88`
- `0x180074a94`
- `0x1800e62d0`
- `0x1800e6750`
- `0x18013c8fe`
- `0x180147d38`
- `0x18016c2dc`
- `0x180178400`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e6411`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e6411`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e6337`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e655e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e6337`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e655e`

## pseudocode

```c
__int64 __fastcall CTSF30Base::OnTextUpdatingWorker(
        CTSF30Base *this,
        struct Windows::UI::Text::Core::ICoreTextEditContext *a2,
        struct Windows::UI::Text::Core::ICoreTextTextUpdatingEventArgs *a3)
{
  int v4; // r15d
  __int64 v5; // r8
  __int64 (__fastcall *v7)(struct Windows::UI::Text::Core::ICoreTextTextUpdatingEventArgs *, __int64 *); // rax
  int v8; // esi
  __int64 (__fastcall *v9)(struct Windows::UI::Text::Core::ICoreTextTextUpdatingEventArgs *, HSTRING *); // rbx
  char v10; // r13
  _QWORD *v11; // rbx
  __int64 v12; // rdx
  CTxtEdit *v13; // rcx
  struct CTxtStory *ActiveStory; // rax
  unsigned __int16 *v15; // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  int v17; // r14d
  int v18; // r13d
  int v19; // ecx
  int v20; // edx
  int v21; // esi
  _QWORD *v22; // rcx
  _QWORD *v23; // rcx
  __int64 result; // rax
  _QWORD *v25; // rcx
  __int64 v26; // rax
  int v27; // eax
  CTxtEdit *v28; // rcx
  int v29; // eax
  const unsigned __int16 **v30; // r14
  Resp::BStrHolder *v31; // rcx
  int v32; // r15d
  __int64 v33; // [rsp+30h] [rbp-30h] BYREF
  _QWORD *v34; // [rsp+38h] [rbp-28h] BYREF
  HSTRING string; // [rsp+40h] [rbp-20h] BYREF
  __int64 v36; // [rsp+48h] [rbp-18h] BYREF
  _QWORD *v37; // [rsp+50h] [rbp-10h] BYREF
  int v38; // [rsp+A0h] [rbp+40h] BYREF
  struct Windows::UI::Text::Core::ICoreTextEditContext *length; // [rsp+A8h] [rbp+48h] BYREF
  int v40; // [rsp+B8h] [rbp+58h] BYREF

  length = a2;
  *((_BYTE *)this + 112) = 1;
  v4 = 0;
  v5 = *(_QWORD *)a3;
  if ( (*(_BYTE *)(*((_QWORD *)this + 13) + 176LL) & 4) != 0 )
  {
    result = (*(__int64 (__fastcall **)(struct Windows::UI::Text::Core::ICoreTextTextUpdatingEventArgs *, __int64))(v5 + 88))(
               a3,
               1);
    goto LABEL_37;
  }
  v7 = *(__int64 (__fastcall **)(struct Windows::UI::Text::Core::ICoreTextTextUpdatingEventArgs *, __int64 *))(v5 + 48);
  v33 = 0;
  string = 0;
  v8 = v7(a3, &v33);
  if ( v8 >= 0 )
  {
    v9 = *(__int64 (__fastcall **)(struct Windows::UI::Text::Core::ICoreTextTextUpdatingEventArgs *, HSTRING *))(*(_QWORD *)a3 + 56LL);
    WindowsDeleteString(string);
    string = 0;
    v8 = v9(a3, &string);
  }
  v37 = 0;
  v10 = 0;
  v34 = 0;
  if ( v8 >= 0 )
  {
    if ( *((_BYTE *)this + 116)
      || ((*(void (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)(*((_QWORD *)this + 13) + 16LL) + 304LL))(
            *((_QWORD *)this + 13) + 16LL,
            &v34),
          (v11 = v34) == 0) )
    {
      v12 = (unsigned int)v33;
    }
    else
    {
      v38 = -1;
      v40 = -1;
      (*(void (__fastcall **)(_QWORD *, int *))(*v34 + 112LL))(v34, &v38);
      (*(void (__fastcall **)(_QWORD *, int *))(*v11 + 128LL))(v11, &v40);
      v12 = (unsigned int)v33;
      if ( __PAIR64__(v40, v38) == v33 )
      {
        v10 = 1;
        goto LABEL_9;
      }
    }
    (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD **))(*(_QWORD *)(*((_QWORD *)this + 13) + 16LL) + 424LL))(
      *((_QWORD *)this + 13) + 16LL,
      v12,
      HIDWORD(v33),
      &v37);
  }
LABEL_9:
  v13 = (CTxtEdit *)*((_QWORD *)this + 13);
  if ( (*((_BYTE *)v13 + 176) & 1) != 0 )
  {
    ActiveStory = CTxtEdit::GetActiveStory(v13);
    if ( *((_DWORD *)ActiveStory + 10) <= SHIDWORD(v33) )
      --HIDWORD(v33);
  }
  LODWORD(length) = 0;
  v15 = 0;
  if ( v8 < 0 )
    goto LABEL_15;
  StringRawBuffer = WindowsGetStringRawBuffer(string, (UINT32 *)&length);
  v15 = CW32System::SysAllocStringLen(StringRawBuffer, (unsigned int)length);
  if ( !v15 )
  {
    v8 = -2147024882;
    goto LABEL_15;
  }
  if ( !*((_BYTE *)this + 116) )
  {
LABEL_40:
    if ( v10 )
    {
      v25 = v34;
      v26 = *v34;
      if ( *v15 )
      {
        v27 = (*(__int64 (__fastcall **)(_QWORD *, unsigned __int16 *))(v26 + 536))(v34, v15);
LABEL_43:
        v8 = v27;
        goto LABEL_15;
      }
    }
    else
    {
      v25 = v37;
      v26 = *v37;
    }
    v27 = (*(__int64 (__fastcall **)(_QWORD *, __int64, unsigned __int16 *))(v26 + 824))(v25, 96, v15);
    goto LABEL_43;
  }
  v29 = *((_DWORD *)this + 32);
  v30 = (const unsigned __int16 **)((char *)this + 144);
  v31 = (CTSF30Base *)((char *)this + 144);
  if ( v29 == 0x3FFFFFFF )
  {
    *((_DWORD *)this + 32) = v33;
    v8 = Resp::BStrHolder::HrCopyWz(v31, v15);
    if ( v8 >= 0 )
      goto LABEL_40;
  }
  else
  {
    v32 = v33 - v29;
    v8 = CW32System::SysReAllocStringLen((unsigned __int16 **)v31, *v30, (int)v33 - v29 + (int)length);
    if ( v8 >= 0 )
    {
      if ( *v30 )
      {
        memcpy_0((void *)&(*v30)[v32], v15, 2LL * (unsigned int)length);
        v4 = 0;
        goto LABEL_40;
      }
      v8 = -2147024882;
    }
    v4 = 0;
  }
LABEL_15:
  v17 = 0x3FFFFFFF;
  v18 = 0;
  if ( *((_BYTE *)this + 169) && !*((_BYTE *)this + 168) )
  {
    v17 = *((_DWORD *)this + 44);
    if ( v17 == 0x3FFFFFFF )
    {
      v19 = 0;
      v20 = 0;
    }
    else
    {
      v19 = *((_DWORD *)this + 45) - v17;
      v20 = v19 + *((_DWORD *)this + 46);
      *((_DWORD *)this + 44) = 0x3FFFFFFF;
    }
    v4 = v17 + v19;
    v18 = v17 + v20;
  }
  *((_BYTE *)this + 169) = 0;
  if ( v8 >= 0 )
  {
    v8 = 0;
    if ( v17 == 0x3FFFFFFF )
      v8 = -2147418113;
  }
  v36 = 0;
  if ( v8 < 0 )
    goto LABEL_44;
  if ( !v34 )
    (*(void (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)(*((_QWORD *)this + 13) + 16LL) + 304LL))(
      *((_QWORD *)this + 13) + 16LL,
      &v34);
  v21 = (*(__int64 (__fastcall **)(struct Windows::UI::Text::Core::ICoreTextTextUpdatingEventArgs *, __int64 *))(*(_QWORD *)a3 + 64LL))(
          a3,
          &v36);
  if ( v21 < 0 )
  {
LABEL_44:
    v21 = (*(__int64 (__fastcall **)(struct Windows::UI::Text::Core::ICoreTextTextUpdatingEventArgs *, __int64))(*(_QWORD *)a3 + 88LL))(
            a3,
            1);
  }
  else if ( v18 - v4 == (_DWORD)v33 + (_DWORD)length - HIDWORD(v33) && __PAIR64__(v4, v17) == v33 )
  {
    (*(void (__fastcall **)(_QWORD *, _QWORD, _QWORD))(*v34 + 224LL))(v34, (unsigned int)v36, HIDWORD(v36));
    if ( *((_BYTE *)this + 116) )
    {
      v28 = (CTxtEdit *)*((_QWORD *)this + 13);
      if ( *((_QWORD *)v28 + 64) )
        CTxtEdit::RaiseUiaTextEditTextChangedEvent(
          v28,
          TextEditChangeType_Composition,
          *((const unsigned __int16 **)this + 18));
    }
  }
  else
  {
    CTSF30Base::SendTextChangedNotification(this, v17, v4 - v17, v18 - v17);
  }
  if ( v15 )
    CW32System::SysFreeString(v15);
  v22 = v34;
  if ( v34 )
  {
    v34 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v22 + 16LL))(v22);
  }
  v23 = v37;
  if ( v37 )
  {
    v37 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v23 + 16LL))(v23);
  }
  WindowsDeleteString(string);
  result = (unsigned int)v21;
LABEL_37:
  *((_BYTE *)this + 112) = 0;
  return result;
}

```

## disassembly

```asm
0x1800e62d0  mov     [rsp-38h+arg_10], rbx
0x1800e62d5  mov     [rsp-38h+length], rdx
0x1800e62da  push    rbp
0x1800e62db  push    rsi
0x1800e62dc  push    rdi
0x1800e62dd  push    r12
0x1800e62df  push    r13
0x1800e62e1  push    r14
0x1800e62e3  push    r15
0x1800e62e5  mov     rbp, rsp
0x1800e62e8  sub     rsp, 60h
0x1800e62ec  mov     byte ptr [rcx+70h], 1
0x1800e62f0  mov     r12, r8
0x1800e62f3  mov     rax, [rcx+68h]
0x1800e62f7  xor     r15d, r15d
0x1800e62fa  mov     r8, [r8]
0x1800e62fd  mov     rdi, rcx
0x1800e6300  mov     rcx, r12
0x1800e6303  test    byte ptr [rax+0B0h], 4
0x1800e630a  jnz     loc_1800E66A1
0x1800e6310  mov     rax, [r8+30h]
0x1800e6314  lea     rdx, [rbp+var_30]
0x1800e6318  mov     [rbp+var_30], r15
0x1800e631c  mov     [rbp+string], r15
0x1800e6320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6325  mov     esi, eax
0x1800e6327  test    eax, eax
0x1800e6329  js      short loc_1800E6352
0x1800e632b  mov     rax, [r12]
0x1800e632f  mov     rcx, [rbp+string]; string
0x1800e6333  mov     rbx, [rax+38h]
0x1800e6337  call    cs:__imp_WindowsDeleteString
0x1800e633d  lea     rdx, [rbp+string]
0x1800e6341  mov     [rbp+string], r15
0x1800e6345  mov     rcx, r12
0x1800e6348  mov     rax, rbx
0x1800e634b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6350  mov     esi, eax
0x1800e6352  mov     [rbp+var_10], r15
0x1800e6356  mov     r13b, r15b
0x1800e6359  mov     [rbp+var_28], r15
0x1800e635d  test    esi, esi
0x1800e635f  js      short loc_1800E63E0
0x1800e6361  cmp     [rdi+74h], r15b
0x1800e6365  jnz     loc_1800E6609
0x1800e636b  mov     rcx, [rdi+68h]
0x1800e636f  lea     rdx, [rbp+var_28]
0x1800e6373  add     rcx, 10h
0x1800e6377  mov     rax, [rcx]
0x1800e637a  mov     rax, [rax+130h]
0x1800e6381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6386  mov     rbx, [rbp+var_28]
0x1800e638a  test    rbx, rbx
0x1800e638d  jz      loc_1800E6609
0x1800e6393  or      eax, 0FFFFFFFFh
0x1800e6396  lea     rdx, [rbp+arg_0]
0x1800e639a  mov     [rbp+arg_0], eax
0x1800e639d  mov     rcx, rbx
0x1800e63a0  mov     [rbp+arg_18], eax
0x1800e63a3  mov     rax, [rbx]
0x1800e63a6  mov     rax, [rax+70h]
0x1800e63aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e63af  mov     rax, [rbx]
0x1800e63b2  lea     rdx, [rbp+arg_18]
0x1800e63b6  mov     rcx, rbx
0x1800e63b9  mov     rax, [rax+80h]
0x1800e63c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e63c5  mov     edx, dword ptr [rbp+var_30]
0x1800e63c8  cmp     [rbp+arg_0], edx
0x1800e63cb  jnz     loc_1800E660C
0x1800e63d1  mov     eax, dword ptr [rbp+var_30+4]
0x1800e63d4  cmp     [rbp+arg_18], eax
0x1800e63d7  jnz     loc_1800E660C
0x1800e63dd  mov     r13b, 1
0x1800e63e0  mov     rcx, [rdi+68h]; this
0x1800e63e4  test    byte ptr [rcx+0B0h], 1
0x1800e63eb  jz      short loc_1800E63FE
0x1800e63ed  call    ?GetActiveStory@CTxtEdit@@QEAAPEAVCTxtStory@@XZ; CTxtEdit::GetActiveStory(void)
0x1800e63f2  mov     ecx, dword ptr [rbp+var_30+4]
0x1800e63f5  cmp     [rax+28h], ecx
0x1800e63f8  jle     loc_1800E66B4
0x1800e63fe  mov     dword ptr [rbp+length], r15d
0x1800e6402  mov     rbx, r15
0x1800e6405  test    esi, esi
0x1800e6407  js      short loc_1800E6433
0x1800e6409  mov     rcx, [rbp+string]; string
0x1800e640d  lea     rdx, [rbp+length]; length
0x1800e6411  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e6417  mov     edx, dword ptr [rbp+length]; unsigned int
0x1800e641a  mov     rcx, rax; unsigned __int16 *
0x1800e641d  call    ?SysAllocStringLen@CW32System@@SAPEAGPEBGI@Z; CW32System::SysAllocStringLen(ushort const *,uint)
0x1800e6422  mov     rbx, rax
0x1800e6425  test    rax, rax
0x1800e6428  jnz     loc_1800E65AB
0x1800e642e  mov     esi, 8007000Eh
0x1800e6433  xor     r8d, r8d
0x1800e6436  mov     r9d, 3FFFFFFFh
0x1800e643c  mov     r14d, r9d
0x1800e643f  mov     r13d, r8d
0x1800e6442  cmp     [rdi+0A9h], r8b
0x1800e6449  jz      short loc_1800E6484
0x1800e644b  cmp     [rdi+0A8h], r8b
0x1800e6452  jnz     short loc_1800E6484
0x1800e6454  mov     r14d, [rdi+0B0h]
0x1800e645b  cmp     r14d, r9d
0x1800e645e  jz      loc_1800E65FE
0x1800e6464  mov     ecx, [rdi+0B4h]
0x1800e646a  mov     edx, [rdi+0B8h]
0x1800e6470  sub     ecx, r14d
0x1800e6473  add     edx, ecx
0x1800e6475  mov     [rdi+0B0h], r9d
0x1800e647c  lea     r15d, [r14+rcx]
0x1800e6480  lea     r13d, [r14+rdx]
0x1800e6484  mov     [rdi+0A9h], r8b
0x1800e648b  test    esi, esi
0x1800e648d  js      short loc_1800E649D
0x1800e648f  cmp     r14d, r9d
0x1800e6492  mov     esi, r8d
0x1800e6495  mov     eax, 8000FFFFh
0x1800e649a  cmovz   esi, eax
0x1800e649d  mov     [rbp+var_18], r8
0x1800e64a1  test    esi, esi
0x1800e64a3  js      loc_1800E65E5
0x1800e64a9  cmp     [rbp+var_28], r8
0x1800e64ad  jz      loc_1800E6727
0x1800e64b3  mov     rax, [r12]
0x1800e64b7  lea     rdx, [rbp+var_18]
0x1800e64bb  mov     rcx, r12
0x1800e64be  mov     rax, [rax+40h]
0x1800e64c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e64c7  mov     esi, eax
0x1800e64c9  test    eax, eax
0x1800e64cb  js      loc_1800E65E5
0x1800e64d1  mov     edx, dword ptr [rbp+length]
0x1800e64d4  mov     ecx, r13d
0x1800e64d7  sub     edx, dword ptr [rbp+var_30+4]
0x1800e64da  sub     ecx, r15d
0x1800e64dd  add     edx, dword ptr [rbp+var_30]
0x1800e64e0  cmp     ecx, edx
0x1800e64e2  jnz     loc_1800E658C
0x1800e64e8  cmp     r14d, dword ptr [rbp+var_30]
0x1800e64ec  jnz     loc_1800E658C
0x1800e64f2  cmp     r15d, dword ptr [rbp+var_30+4]
0x1800e64f6  jnz     loc_1800E658C
0x1800e64fc  mov     rcx, [rbp+var_28]
0x1800e6500  mov     r8d, dword ptr [rbp+var_18+4]
0x1800e6504  mov     edx, dword ptr [rbp+var_18]
0x1800e6507  mov     rax, [rcx]
0x1800e650a  mov     rax, [rax+0E0h]
0x1800e6511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6516  xor     r15d, r15d
0x1800e6519  cmp     [rdi+74h], r15b
0x1800e651d  jnz     loc_1800E667A
0x1800e6523  test    rbx, rbx
0x1800e6526  jnz     short loc_1800E6582
0x1800e6528  mov     rcx, [rbp+var_28]
0x1800e652c  test    rcx, rcx
0x1800e652f  jz      short loc_1800E6541
0x1800e6531  mov     [rbp+var_28], r15
0x1800e6535  mov     rax, [rcx]
0x1800e6538  mov     rax, [rax+10h]
0x1800e653c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6541  mov     rcx, [rbp+var_10]
0x1800e6545  test    rcx, rcx
0x1800e6548  jz      short loc_1800E655A
0x1800e654a  mov     [rbp+var_10], r15
0x1800e654e  mov     rax, [rcx]
0x1800e6551  mov     rax, [rax+10h]
0x1800e6555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e655a  mov     rcx, [rbp+string]; string
0x1800e655e  call    cs:__imp_WindowsDeleteString
0x1800e6564  mov     eax, esi
0x1800e6566  mov     rbx, [rsp+60h+arg_10]
0x1800e656e  mov     [rdi+70h], r15b
0x1800e6572  add     rsp, 60h
0x1800e6576  pop     r15
0x1800e6578  pop     r14
0x1800e657a  pop     r13
0x1800e657c  pop     r12
0x1800e657e  pop     rdi
0x1800e657f  pop     rsi
0x1800e6580  pop     rbp
0x1800e6581  retn
0x1800e6582  mov     rcx, rbx; unsigned __int16 *
0x1800e6585  call    ?SysFreeString@CW32System@@SAXPEAG@Z; CW32System::SysFreeString(ushort *)
0x1800e658a  jmp     short loc_1800E6528
0x1800e658c  sub     r13d, r14d
0x1800e658f  sub     r15d, r14d
0x1800e6592  mov     r9d, r13d; int
0x1800e6595  mov     r8d, r15d; int
0x1800e6598  mov     edx, r14d; int
0x1800e659b  mov     rcx, rdi; this
0x1800e659e  call    ?SendTextChangedNotification@CTSF30Base@@AEAAXJJJ@Z; CTSF30Base::SendTextChangedNotification(long,long,long)
0x1800e65a3  xor     r15d, r15d
0x1800e65a6  jmp     loc_1800E6523
0x1800e65ab  cmp     [rdi+74h], r15b
0x1800e65af  jnz     loc_1800E66BC
0x1800e65b5  test    r13b, r13b
0x1800e65b8  jz      loc_1800E6707
0x1800e65be  mov     rcx, [rbp+var_28]
0x1800e65c2  mov     rax, [rcx]
0x1800e65c5  cmp     [rbx], r15w
0x1800e65c9  jz      loc_1800E670E
0x1800e65cf  mov     rax, [rax+218h]
0x1800e65d6  mov     rdx, rbx
0x1800e65d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e65de  mov     esi, eax
0x1800e65e0  jmp     loc_1800E6433
0x1800e65e5  mov     rax, [r12]
0x1800e65e9  mov     edx, 1
0x1800e65ee  mov     rcx, r12
0x1800e65f1  mov     rax, [rax+58h]
0x1800e65f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e65fa  mov     esi, eax
0x1800e65fc  jmp     short loc_1800E65A3
0x1800e65fe  mov     ecx, r8d
0x1800e6601  mov     edx, r8d
0x1800e6604  jmp     loc_1800E647C
0x1800e6609  mov     edx, dword ptr [rbp+var_30]
0x1800e660c  mov     rcx, [rdi+68h]
0x1800e6610  lea     r9, [rbp+var_10]
0x1800e6614  mov     r8d, dword ptr [rbp+var_30+4]
0x1800e6618  add     rcx, 10h
0x1800e661c  mov     rax, [rcx]
0x1800e661f  mov     rax, [rax+1A8h]
0x1800e6626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e662b  jmp     loc_1800E63E0
0x1800e6630  mov     eax, dword ptr [rbp+var_30]
0x1800e6633  mov     rdx, rbx; unsigned __int16 *
0x1800e6636  mov     [rdi+80h], eax
0x1800e663c  call    ?HrCopyWz@BStrHolder@Resp@@QEAAJPEBG@Z; Resp::BStrHolder::HrCopyWz(ushort const *)
0x1800e6641  mov     esi, eax
0x1800e6643  test    eax, eax
0x1800e6645  jns     loc_1800E65B5
0x1800e664b  jmp     loc_1800E6433
0x1800e6650  cmp     [r14], rax
0x1800e6653  jz      loc_1800E66FA
0x1800e6659  mov     rax, [r14]
0x1800e665c  mov     rdx, rbx; Src
0x1800e665f  mov     r8d, dword ptr [rbp+length]
0x1800e6663  movsxd  rcx, r15d
0x1800e6666  add     r8, r8; Size
0x1800e6669  lea     rcx, [rax+rcx*2]; void *
0x1800e666d  call    memcpy_0
0x1800e6672  xor     r15d, r15d
0x1800e6675  jmp     loc_1800E65B5
0x1800e667a  mov     rcx, [rdi+68h]; this
0x1800e667e  cmp     [rcx+200h], r15
0x1800e6685  jz      loc_1800E6523
0x1800e668b  mov     r8, [rdi+90h]; unsigned __int16 *
0x1800e6692  mov     edx, 2; enum TextEditChangeType
0x1800e6697  call    ?RaiseUiaTextEditTextChangedEvent@CTxtEdit@@QEAAXW4TextEditChangeType@@PEBG@Z; CTxtEdit::RaiseUiaTextEditTextChangedEvent(TextEditChangeType,ushort const *)
0x1800e669c  jmp     loc_1800E6523
0x1800e66a1  mov     rax, [r8+58h]
0x1800e66a5  mov     edx, 1
0x1800e66aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e66af  jmp     loc_1800E6566
0x1800e66b4  dec     dword ptr [rbp+var_30+4]
0x1800e66b7  jmp     loc_1800E63FE
0x1800e66bc  mov     eax, [rdi+80h]
0x1800e66c2  lea     r14, [rdi+90h]
0x1800e66c9  mov     rcx, r14; unsigned __int16 **
0x1800e66cc  cmp     eax, 3FFFFFFFh
0x1800e66d1  jz      loc_1800E6630
0x1800e66d7  mov     r15d, dword ptr [rbp+var_30]
0x1800e66db  mov     r8d, dword ptr [rbp+length]
0x1800e66df  sub     r15d, eax
0x1800e66e2  mov     rdx, [r14]; unsigned __int16 *
0x1800e66e5  add     r8d, r15d; unsigned int
0x1800e66e8  call    ?SysReAllocStringLen@CW32System@@SAHPEAPEAGPEBGI@Z; CW32System::SysReAllocStringLen(ushort * *,ushort const *,uint)
0x1800e66ed  mov     esi, eax
0x1800e66ef  xor     eax, eax
0x1800e66f1  test    esi, esi
0x1800e66f3  js      short loc_1800E66FF
0x1800e66f5  jmp     loc_1800E6650
0x1800e66fa  mov     esi, 8007000Eh
0x1800e66ff  xor     r15d, r15d
0x1800e6702  jmp     loc_1800E6433
0x1800e6707  mov     rcx, [rbp+var_10]
0x1800e670b  mov     rax, [rcx]
0x1800e670e  mov     rax, [rax+338h]
0x1800e6715  mov     r8, rbx
0x1800e6718  mov     edx, 60h ; '`'
0x1800e671d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6722  jmp     loc_1800E65DE
0x1800e6727  mov     rcx, [rdi+68h]
0x1800e672b  lea     rdx, [rbp+var_28]
0x1800e672f  add     rcx, 10h
0x1800e6733  mov     rax, [rcx]
0x1800e6736  mov     rax, [rax+130h]
0x1800e673d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6742  jmp     loc_1800E64B3
```
