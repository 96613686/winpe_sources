# CClipboardMobileDataObject::EnumFormatEtc(ulong,IEnumFORMATETC * *)

- ea: `0x1801f6a50`
- end: `0x1801f6be7`
- name: `?EnumFormatEtc@CClipboardMobileDataObject@@UEAAJKPEAPEAUIEnumFORMATETC@@@Z`
- size: `407`
- prototype: `int(CClipboardMobileDataObject *__hidden this, unsigned int, struct IEnumFORMATETC **)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180012f50`
- `0x1800498d0`
- `0x18007e0f0`
- `0x1800e5578`
- `0x180148558`
- `0x1801f6a50`
- `0x1801f74a0`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801f6b2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801f6b2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f6b05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f6b7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f6b05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f6b7e`

## pseudocode

```c
__int64 __fastcall CClipboardMobileDataObject::EnumFormatEtc(
        CClipboardMobileDataObject *this,
        int a2,
        struct IEnumFORMATETC **a3)
{
  unsigned int v4; // r15d
  __int64 v5; // rcx
  unsigned int v7; // esi
  __int64 v8; // rdi
  void (__fastcall *v9)(__int64, _QWORD, HSTRING *); // rbx
  HSTRING v10; // rcx
  __int16 v11; // bx
  _QWORD *v12; // rax
  const struct tagFORMATETC *v13; // rax
  int v14; // r10d
  HSTRING string; // [rsp+20h] [rbp-30h] BYREF
  __int64 v16; // [rsp+28h] [rbp-28h] BYREF
  __int64 v17; // [rsp+30h] [rbp-20h] BYREF
  __m128i si128; // [rsp+38h] [rbp-18h]
  int v19; // [rsp+48h] [rbp-8h]
  unsigned int v20; // [rsp+90h] [rbp+40h] BYREF
  UINT32 length; // [rsp+98h] [rbp+48h] BYREF

  v4 = -2147024809;
  if ( a3 )
  {
    *a3 = 0;
    if ( a2 == 1 )
    {
      v5 = *((_QWORD *)this + 1);
      v16 = 0;
      v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v5 + 72LL))(v5, &v16);
      v20 = 0;
      (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v16 + 56LL))(v16, &v20);
      if ( !v20 )
      {
        Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(&v16);
        return 0;
      }
      v7 = 0;
      v17 = 0;
      v19 = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      do
      {
        v8 = v16;
        string = 0;
        v9 = *(void (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v16 + 48LL);
        WindowsDeleteString(0);
        string = 0;
        v9(v8, v7, &string);
        length = 0;
        WindowsGetStringRawBuffer(string, &length);
        v10 = string;
        if ( length )
        {
          v11 = SupportedFormat(string);
          if ( v11 )
          {
            v12 = CArrayBase::ArAdd((CArrayBase *)&v17, 1, 0);
            if ( v12 )
            {
              *(_WORD *)v12 = v11;
              v12[1] = 0;
              *((_DWORD *)v12 + 4) = 1;
              *((_DWORD *)v12 + 5) = -1;
              *((_DWORD *)v12 + 6) = 1;
            }
          }
          v10 = string;
        }
        WindowsDeleteString(v10);
        ++v7;
      }
      while ( v7 < v20 );
      if ( si128.m128i_i32[0] > 0 )
      {
        v13 = (const struct tagFORMATETC *)CArrayBase::Elem((CArrayBase *)&v17, 0);
        v4 = RichEdit::CEnumFormatEtc::Create(v13, v14, a3);
      }
      CArrayBase::Clear(&v17, 2);
      Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(&v16);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1801f6a50  mov     [rsp-28h+arg_0], rbx
0x1801f6a55  mov     [rsp-28h+arg_8], rsi
0x1801f6a5a  push    rbp
0x1801f6a5b  push    rdi
0x1801f6a5c  push    r12
0x1801f6a5e  push    r14
0x1801f6a60  push    r15
0x1801f6a62  mov     rbp, rsp
0x1801f6a65  sub     rsp, 50h
0x1801f6a69  xor     r12d, r12d
0x1801f6a6c  mov     r14, r8
0x1801f6a6f  mov     r15d, 80070057h
0x1801f6a75  test    r8, r8
0x1801f6a78  jz      loc_1801F6BCB
0x1801f6a7e  mov     [r8], r12
0x1801f6a81  cmp     edx, 1
0x1801f6a84  jnz     loc_1801F6BCB
0x1801f6a8a  mov     rcx, [rcx+8]
0x1801f6a8e  lea     rdx, [rbp+var_28]
0x1801f6a92  mov     [rbp+var_28], r12
0x1801f6a96  mov     rax, [rcx]
0x1801f6a99  mov     rax, [rax+48h]
0x1801f6a9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f6aa2  mov     rcx, [rbp+var_28]
0x1801f6aa6  lea     rdx, [rbp+arg_10]
0x1801f6aaa  mov     r15d, eax
0x1801f6aad  mov     [rbp+arg_10], r12d
0x1801f6ab1  mov     rax, [rcx]
0x1801f6ab4  mov     rax, [rax+38h]
0x1801f6ab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f6abd  mov     eax, [rbp+arg_10]
0x1801f6ac0  test    eax, eax
0x1801f6ac2  jnz     short loc_1801F6AD4
0x1801f6ac4  lea     rcx, [rbp+var_28]; void *
0x1801f6ac8  call    ??1?$TCntPtr@UIDataObject@@@Resp@@QEAA@XZ; Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(void)
0x1801f6acd  xor     eax, eax
0x1801f6acf  jmp     loc_1801F6BCE
0x1801f6ad4  movdqa  xmm0, cs:__xmm@00000000000000200000000000000000
0x1801f6adc  mov     esi, r12d
0x1801f6adf  mov     [rbp+var_20], r12
0x1801f6ae3  mov     [rbp+var_8], r12d
0x1801f6ae7  movdqu  [rbp+var_18], xmm0
0x1801f6aec  test    eax, eax
0x1801f6aee  jz      loc_1801F6B8F
0x1801f6af4  mov     rdi, [rbp+var_28]
0x1801f6af8  xor     ecx, ecx; string
0x1801f6afa  mov     [rbp+string], r12
0x1801f6afe  mov     rax, [rdi]
0x1801f6b01  mov     rbx, [rax+30h]
0x1801f6b05  call    cs:__imp_WindowsDeleteString
0x1801f6b0b  lea     r8, [rbp+string]
0x1801f6b0f  mov     [rbp+string], r12
0x1801f6b13  mov     edx, esi
0x1801f6b15  mov     rcx, rdi
0x1801f6b18  mov     rax, rbx
0x1801f6b1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f6b20  mov     rcx, [rbp+string]; string
0x1801f6b24  lea     rdx, [rbp+length]; length
0x1801f6b28  mov     [rbp+length], r12d
0x1801f6b2c  call    cs:__imp_WindowsGetStringRawBuffer
0x1801f6b32  mov     rcx, [rbp+string]
0x1801f6b36  cmp     [rbp+length], r12d
0x1801f6b3a  jz      short loc_1801F6B7E
0x1801f6b3c  call    SupportedFormat
0x1801f6b41  movzx   ebx, ax
0x1801f6b44  test    ax, ax
0x1801f6b47  jz      short loc_1801F6B7A
0x1801f6b49  xor     r8d, r8d; int *
0x1801f6b4c  lea     rcx, [rbp+var_20]; this
0x1801f6b50  lea     edx, [r8+1]; int
0x1801f6b54  call    ?ArAdd@CArrayBase@@IEAAPEAXJPEAJ@Z; CArrayBase::ArAdd(long,long *)
0x1801f6b59  test    rax, rax
0x1801f6b5c  jz      short loc_1801F6B7A
0x1801f6b5e  mov     [rax], bx
0x1801f6b61  mov     [rax+8], r12
0x1801f6b65  mov     dword ptr [rax+10h], 1
0x1801f6b6c  mov     dword ptr [rax+14h], 0FFFFFFFFh
0x1801f6b73  mov     dword ptr [rax+18h], 1
0x1801f6b7a  mov     rcx, [rbp+string]; string
0x1801f6b7e  call    cs:__imp_WindowsDeleteString
0x1801f6b84  inc     esi
0x1801f6b86  cmp     esi, [rbp+arg_10]
0x1801f6b89  jb      loc_1801F6AF4
0x1801f6b8f  mov     r10d, dword ptr [rbp+var_18]
0x1801f6b93  test    r10d, r10d
0x1801f6b96  jle     short loc_1801F6BB4
0x1801f6b98  xor     edx, edx; int
0x1801f6b9a  lea     rcx, [rbp+var_20]; this
0x1801f6b9e  call    ?Elem@CArrayBase@@IEBAPEAXJ@Z; CArrayBase::Elem(long)
0x1801f6ba3  mov     rcx, rax; Src
0x1801f6ba6  mov     r8, r14; struct IEnumFORMATETC **
0x1801f6ba9  mov     edx, r10d; int
0x1801f6bac  call    ?Create@CEnumFormatEtc@RichEdit@@SAJPEBUtagFORMATETC@@JPEAPEAUIEnumFORMATETC@@@Z; RichEdit::CEnumFormatEtc::Create(tagFORMATETC const *,long,IEnumFORMATETC * *)
0x1801f6bb1  mov     r15d, eax
0x1801f6bb4  mov     edx, 2
0x1801f6bb9  lea     rcx, [rbp+var_20]
0x1801f6bbd  call    ?Clear@CArrayBase@@QEAAXW4tagArrayFlag@@@Z; CArrayBase::Clear(tagArrayFlag)
0x1801f6bc2  lea     rcx, [rbp+var_28]; void *
0x1801f6bc6  call    ??1?$TCntPtr@UIDataObject@@@Resp@@QEAA@XZ; Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(void)
0x1801f6bcb  mov     eax, r15d
0x1801f6bce  lea     r11, [rsp+50h+var_s0]
0x1801f6bd3  mov     rbx, [r11+30h]
0x1801f6bd7  mov     rsi, [r11+38h]
0x1801f6bdb  mov     rsp, r11
0x1801f6bde  pop     r15
0x1801f6be0  pop     r14
0x1801f6be2  pop     r12
0x1801f6be4  pop     rdi
0x1801f6be5  pop     rbp
0x1801f6be6  retn
```
