# CTSF30Base::OnRichContentUpdatingWorker(Windows::UI::Text::Core::ICoreTextEditContext *,Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *)

- ea: `0x1802069dc`
- end: `0x180206cd3`
- name: `?OnRichContentUpdatingWorker@CTSF30Base@@QEAAJPEAUICoreTextEditContext@Core@Text@UI@Windows@@PEAUICoreTextRichContentUpdatingEventArgs@34Internal@56@@Z`
- size: `759`
- prototype: `__int64 __fastcall(CTSF30Base *__hidden this, struct Windows::UI::Text::Core::ICoreTextEditContext *, struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1802061e0`

## callees

- `0x180021928`
- `0x1800498d0`
- `0x1800e6750`
- `0x1801008d4`
- `0x18010cb90`
- `0x1802069dc`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180206b48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180206b7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180206b48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180206b7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180206ae0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180206b04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180206c1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180206c28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180206ae0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180206b04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180206c1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180206c28`

## pseudocode

```c
__int64 __fastcall CTSF30Base::OnRichContentUpdatingWorker(
        CTSF30Base *this,
        struct Windows::UI::Text::Core::ICoreTextEditContext *a2,
        struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *a3)
{
  __int64 v4; // r8
  __int64 result; // rax
  __int64 (__fastcall *v7)(struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *, __int64 *); // rax
  int v8; // eax
  int v9; // esi
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rax
  void (__fastcall *v14)(struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *, HSTRING *); // rbx
  void (__fastcall *v15)(struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *, HSTRING *); // rbx
  unsigned __int16 *v16; // rbx
  unsigned __int16 *v17; // rdi
  const unsigned __int16 *StringRawBuffer; // rax
  int v19; // eax
  const unsigned __int16 *v20; // rax
  int v21; // eax
  __int64 v22; // rcx
  unsigned int v23; // ebx
  __int64 v24; // rcx
  HSTRING string; // [rsp+30h] [rbp-50h] BYREF
  __int64 v26; // [rsp+38h] [rbp-48h] BYREF
  __int64 v27; // [rsp+40h] [rbp-40h] BYREF
  unsigned __int16 *v28; // [rsp+48h] [rbp-38h] BYREF
  unsigned __int16 *v29; // [rsp+50h] [rbp-30h] BYREF
  __int128 v30; // [rsp+58h] [rbp-28h] BYREF
  __int128 v31; // [rsp+68h] [rbp-18h]
  unsigned __int16 *v32; // [rsp+78h] [rbp-8h]
  int v33; // [rsp+C0h] [rbp+40h] BYREF
  struct Windows::UI::Text::Core::ICoreTextEditContext *length; // [rsp+C8h] [rbp+48h] BYREF
  HSTRING v35; // [rsp+D8h] [rbp+58h] BYREF

  length = a2;
  *((_BYTE *)this + 112) = 1;
  v4 = *(_QWORD *)a3;
  if ( (*(_BYTE *)(*((_QWORD *)this + 13) + 176LL) & 4) != 0 )
  {
    result = (*(__int64 (__fastcall **)(struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *, __int64))(v4 + 104))(
               a3,
               1);
  }
  else
  {
    v7 = *(__int64 (__fastcall **)(struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *, __int64 *))(v4 + 48);
    v27 = 0;
    v8 = v7(a3, &v27);
    v33 = 0;
    v9 = v8;
    if ( v8 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *, int *))(*(_QWORD *)a3 + 88LL))(
             a3,
             &v33);
      if ( v9 >= 0 && v33 != 4 )
      {
        v10 = *(_QWORD *)(*((_QWORD *)this + 13) + 256LL);
        if ( v10 )
          v11 = *(_DWORD *)(v10 + 236);
        else
          v11 = 0;
        if ( (v11 & v33) == 0 || (_DWORD)v27 == HIDWORD(v27) )
        {
          v9 = -2147467259;
        }
        else
        {
          v12 = *((_QWORD *)this + 13) + 16LL;
          v26 = 0;
          v9 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64 *))(*(_QWORD *)v12 + 424LL))(
                 v12,
                 v27,
                 HIDWORD(v27),
                 &v26);
          if ( v9 >= 0 )
          {
            v13 = *(_QWORD *)a3;
            string = 0;
            v35 = 0;
            v14 = *(void (__fastcall **)(struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *, HSTRING *))(v13 + 72);
            WindowsDeleteString(0);
            v35 = 0;
            v14(a3, &v35);
            v15 = *(void (__fastcall **)(struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *, HSTRING *))(*(_QWORD *)a3 + 56LL);
            WindowsDeleteString(0);
            string = 0;
            v15(a3, &string);
            v28 = 0;
            LODWORD(length) = 0;
            v16 = 0;
            v32 = 0;
            v30 = 0;
            v17 = 0;
            v29 = 0;
            v31 = 0;
            StringRawBuffer = WindowsGetStringRawBuffer(string, (UINT32 *)&length);
            if ( !(_DWORD)length
              || (v19 = Resp::BStrHolder::HrCopyRgwch((Resp::BStrHolder *)&v28, StringRawBuffer, (unsigned int)length),
                  v17 = v28,
                  v9 = v19,
                  v19 >= 0) )
            {
              v20 = WindowsGetStringRawBuffer(v35, (UINT32 *)&length);
              if ( !(_DWORD)length
                || (v21 = Resp::BStrHolder::HrCopyRgwch((Resp::BStrHolder *)&v29, v20, (unsigned int)length),
                    v16 = v29,
                    v9 = v21,
                    v21 >= 0) )
              {
                (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v26 + 112LL))(v26, (char *)&v30 + 4);
                (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v26 + 128LL))(v26, (char *)&v30 + 8);
                v22 = *((_QWORD *)this + 13);
                HIDWORD(v30) = v33;
                *((_QWORD *)&v31 + 1) = v17;
                v32 = v16;
                v9 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int128 *, _QWORD))(*(_QWORD *)v22 + 24LL))(
                       v22,
                       1390,
                       0,
                       &v30,
                       0);
              }
              if ( v16 )
                CW32System::SysFreeString(v16);
            }
            if ( v17 )
              CW32System::SysFreeString(v17);
            WindowsDeleteString(v35);
            v35 = 0;
            WindowsDeleteString(string);
          }
          Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(&v26);
        }
      }
    }
    LODWORD(string) = 0;
    LODWORD(length) = 0x3FFFFFFF;
    LODWORD(v35) = 0;
    CTextInputDriverNotifyChanges::GetChanges(
      (CTSF30Base *)((char *)this + 152),
      (int *)&length,
      (int *)&string,
      (int *)&v35);
    if ( v9 < 0 || (_DWORD)length == 0x3FFFFFFF )
    {
      v23 = (*(__int64 (__fastcall **)(struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *, __int64))(*(_QWORD *)a3 + 104LL))(
              a3,
              1);
    }
    else
    {
      v23 = 0;
      CTSF30Base::SendTextChangedNotification(
        this,
        (int)length,
        (_DWORD)string - (_DWORD)length,
        (_DWORD)v35 - (_DWORD)length);
    }
    v24 = *((_QWORD *)this + 13);
    if ( (*(_BYTE *)(v24 + 184) & 0x10) == 0 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)(v24 + 16) + 168LL))(v24 + 16);
    result = v23;
  }
  *((_BYTE *)this + 112) = 0;
  return result;
}

```

## disassembly

```asm
0x1802069dc  mov     [rsp-38h+length], rdx
0x1802069e1  push    rbp
0x1802069e2  push    rbx
0x1802069e3  push    rsi
0x1802069e4  push    rdi
0x1802069e5  push    r12
0x1802069e7  push    r14
0x1802069e9  push    r15
0x1802069eb  mov     rbp, rsp
0x1802069ee  sub     rsp, 80h
0x1802069f5  mov     byte ptr [rcx+70h], 1
0x1802069f9  mov     r15, r8
0x1802069fc  mov     rax, [rcx+68h]
0x180206a00  xor     r12d, r12d
0x180206a03  mov     r8, [r8]
0x180206a06  mov     r14, rcx
0x180206a09  mov     rcx, r15
0x180206a0c  test    byte ptr [rax+0B0h], 4
0x180206a13  jz      short loc_180206A28
0x180206a15  mov     rax, [r8+68h]
0x180206a19  lea     edx, [r12+1]
0x180206a1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180206a23  jmp     loc_180206CBD
0x180206a28  mov     rax, [r8+30h]
0x180206a2c  lea     rdx, [rbp+var_40]
0x180206a30  mov     [rbp+var_40], r12
0x180206a34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180206a39  mov     [rbp+arg_0], r12d
0x180206a3d  mov     esi, eax
0x180206a3f  test    eax, eax
0x180206a41  js      loc_180206C37
0x180206a47  mov     rax, [r15]
0x180206a4a  lea     rdx, [rbp+arg_0]
0x180206a4e  mov     rcx, r15
0x180206a51  mov     rax, [rax+58h]
0x180206a55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180206a5a  mov     esi, eax
0x180206a5c  test    eax, eax
0x180206a5e  js      loc_180206C37
0x180206a64  mov     ecx, [rbp+arg_0]
0x180206a67  cmp     ecx, 4
0x180206a6a  jz      loc_180206C37
0x180206a70  mov     rax, [r14+68h]
0x180206a74  mov     rax, [rax+100h]
0x180206a7b  test    rax, rax
0x180206a7e  jz      short loc_180206A88
0x180206a80  mov     eax, [rax+0ECh]
0x180206a86  jmp     short loc_180206A8B
0x180206a88  mov     eax, r12d
0x180206a8b  test    ecx, eax
0x180206a8d  jnz     short loc_180206A99
0x180206a8f  mov     esi, 80004005h
0x180206a94  jmp     loc_180206C37
0x180206a99  mov     rdx, [rbp+var_40]
0x180206a9d  mov     r8d, dword ptr [rbp+var_40+4]
0x180206aa1  cmp     edx, r8d
0x180206aa4  jz      short loc_180206A8F
0x180206aa6  mov     rcx, [r14+68h]
0x180206aaa  lea     r9, [rbp+var_48]
0x180206aae  add     rcx, 10h
0x180206ab2  mov     [rbp+var_48], r12
0x180206ab6  mov     rax, [rcx]
0x180206ab9  mov     rax, [rax+1A8h]
0x180206ac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180206ac5  mov     esi, eax
0x180206ac7  test    eax, eax
0x180206ac9  js      loc_180206C2E
0x180206acf  mov     rax, [r15]
0x180206ad2  xor     ecx, ecx; string
0x180206ad4  mov     [rbp+string], r12
0x180206ad8  mov     [rbp+arg_18], r12
0x180206adc  mov     rbx, [rax+48h]
0x180206ae0  call    cs:__imp_WindowsDeleteString
0x180206ae6  lea     rdx, [rbp+arg_18]
0x180206aea  mov     [rbp+arg_18], r12
0x180206aee  mov     rcx, r15
0x180206af1  mov     rax, rbx
0x180206af4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180206af9  mov     rax, [r15]
0x180206afc  mov     rcx, [rbp+string]; string
0x180206b00  mov     rbx, [rax+38h]
0x180206b04  call    cs:__imp_WindowsDeleteString
0x180206b0a  lea     rdx, [rbp+string]
0x180206b0e  mov     [rbp+string], r12
0x180206b12  mov     rcx, r15
0x180206b15  mov     rax, rbx
0x180206b18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180206b1d  mov     rcx, [rbp+string]; string
0x180206b21  lea     rdx, [rbp+length]; length
0x180206b25  xorps   xmm0, xmm0
0x180206b28  mov     [rbp+var_38], r12
0x180206b2c  xor     eax, eax
0x180206b2e  mov     dword ptr [rbp+length], r12d
0x180206b32  mov     rbx, r12
0x180206b35  mov     [rbp+var_8], rax
0x180206b39  movups  [rbp+var_28], xmm0
0x180206b3d  mov     rdi, r12
0x180206b40  mov     [rbp+var_30], rbx
0x180206b44  movups  [rbp+var_18], xmm0
0x180206b48  call    cs:__imp_WindowsGetStringRawBuffer
0x180206b4e  mov     ecx, dword ptr [rbp+length]
0x180206b51  test    ecx, ecx
0x180206b53  jz      short loc_180206B72
0x180206b55  mov     r8d, ecx; unsigned __int64
0x180206b58  mov     rdx, rax; unsigned __int16 *
0x180206b5b  lea     rcx, [rbp+var_38]; this
0x180206b5f  call    ?HrCopyRgwch@BStrHolder@Resp@@QEAAJPEBG_K@Z; Resp::BStrHolder::HrCopyRgwch(ushort const *,unsigned __int64)
0x180206b64  mov     rdi, [rbp+var_38]
0x180206b68  mov     esi, eax
0x180206b6a  test    eax, eax
0x180206b6c  js      loc_180206C09
0x180206b72  mov     rcx, [rbp+arg_18]; string
0x180206b76  lea     rdx, [rbp+length]; length
0x180206b7a  call    cs:__imp_WindowsGetStringRawBuffer
0x180206b80  mov     ecx, dword ptr [rbp+length]
0x180206b83  test    ecx, ecx
0x180206b85  jz      short loc_180206BA0
0x180206b87  mov     r8d, ecx; unsigned __int64
0x180206b8a  mov     rdx, rax; unsigned __int16 *
0x180206b8d  lea     rcx, [rbp+var_30]; this
0x180206b91  call    ?HrCopyRgwch@BStrHolder@Resp@@QEAAJPEBG_K@Z; Resp::BStrHolder::HrCopyRgwch(ushort const *,unsigned __int64)
0x180206b96  mov     rbx, [rbp+var_30]
0x180206b9a  mov     esi, eax
0x180206b9c  test    eax, eax
0x180206b9e  js      short loc_180206BFC
0x180206ba0  mov     rcx, [rbp+var_48]
0x180206ba4  lea     rdx, [rbp+var_28+4]
0x180206ba8  mov     rax, [rcx]
0x180206bab  mov     rax, [rax+70h]
0x180206baf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180206bb4  mov     rcx, [rbp+var_48]
0x180206bb8  lea     rdx, [rbp+var_28+8]
0x180206bbc  mov     rax, [rcx]
0x180206bbf  mov     rax, [rax+80h]
0x180206bc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180206bcb  mov     eax, [rbp+arg_0]
0x180206bce  lea     r9, [rbp+var_28]
0x180206bd2  mov     rcx, [r14+68h]
0x180206bd6  xor     r8d, r8d
0x180206bd9  mov     dword ptr [rbp+var_28+0Ch], eax
0x180206bdc  mov     edx, 56Eh
0x180206be1  mov     qword ptr [rbp+var_18+8], rdi
0x180206be5  mov     [rbp+var_8], rbx
0x180206be9  mov     rax, [rcx]
0x180206bec  mov     [rsp+80h+var_60], r12
0x180206bf1  mov     rax, [rax+18h]
0x180206bf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180206bfa  mov     esi, eax
0x180206bfc  test    rbx, rbx
0x180206bff  jz      short loc_180206C09
0x180206c01  mov     rcx, rbx; unsigned __int16 *
0x180206c04  call    ?SysFreeString@CW32System@@SAXPEAG@Z; CW32System::SysFreeString(ushort *)
0x180206c09  test    rdi, rdi
0x180206c0c  jz      short loc_180206C16
0x180206c0e  mov     rcx, rdi; unsigned __int16 *
0x180206c11  call    ?SysFreeString@CW32System@@SAXPEAG@Z; CW32System::SysFreeString(ushort *)
0x180206c16  mov     rcx, [rbp+arg_18]; string
0x180206c1a  call    cs:__imp_WindowsDeleteString
0x180206c20  mov     rcx, [rbp+string]; string
0x180206c24  mov     [rbp+arg_18], r12
0x180206c28  call    cs:__imp_WindowsDeleteString
0x180206c2e  lea     rcx, [rbp+var_48]; void *
0x180206c32  call    ??1?$TCntPtr@UIDataObject@@@Resp@@QEAA@XZ; Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(void)
0x180206c37  mov     ebx, 3FFFFFFFh
0x180206c3c  mov     dword ptr [rbp+string], r12d
0x180206c40  lea     rcx, [r14+98h]; this
0x180206c47  mov     dword ptr [rbp+length], ebx
0x180206c4a  lea     r9, [rbp+arg_18]; int *
0x180206c4e  mov     dword ptr [rbp+arg_18], r12d
0x180206c52  lea     r8, [rbp+string]; int *
0x180206c56  lea     rdx, [rbp+length]; int *
0x180206c5a  call    ?GetChanges@CTextInputDriverNotifyChanges@@QEAA_NAEAH00@Z; CTextInputDriverNotifyChanges::GetChanges(int &,int &,int &)
0x180206c5f  test    esi, esi
0x180206c61  js      short loc_180206C85
0x180206c63  mov     edx, dword ptr [rbp+length]; int
0x180206c66  cmp     edx, ebx
0x180206c68  jz      short loc_180206C85
0x180206c6a  mov     r9d, dword ptr [rbp+arg_18]
0x180206c6e  mov     rcx, r14; this
0x180206c71  mov     r8d, dword ptr [rbp+string]
0x180206c75  sub     r9d, edx; int
0x180206c78  sub     r8d, edx; int
0x180206c7b  mov     ebx, r12d
0x180206c7e  call    ?SendTextChangedNotification@CTSF30Base@@AEAAXJJJ@Z; CTSF30Base::SendTextChangedNotification(long,long,long)
0x180206c83  jmp     short loc_180206C9B
0x180206c85  mov     rax, [r15]
0x180206c88  mov     edx, 1
0x180206c8d  mov     rcx, r15
0x180206c90  mov     rax, [rax+68h]
0x180206c94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180206c99  mov     ebx, eax
0x180206c9b  mov     rcx, [r14+68h]
0x180206c9f  test    byte ptr [rcx+0B8h], 10h
0x180206ca6  jnz     short loc_180206CBB
0x180206ca8  add     rcx, 10h
0x180206cac  mov     rdx, [rcx]
0x180206caf  mov     rax, [rdx+0A8h]
0x180206cb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180206cbb  mov     eax, ebx
0x180206cbd  mov     [r14+70h], r12b
0x180206cc1  add     rsp, 80h
0x180206cc8  pop     r15
0x180206cca  pop     r14
0x180206ccc  pop     r12
0x180206cce  pop     rdi
0x180206ccf  pop     rsi
0x180206cd0  pop     rbx
0x180206cd1  pop     rbp
0x180206cd2  retn
```
