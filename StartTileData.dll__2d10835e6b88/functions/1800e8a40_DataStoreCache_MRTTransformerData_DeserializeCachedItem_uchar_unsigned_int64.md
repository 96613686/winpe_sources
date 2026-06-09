# DataStoreCache::MRTTransformerData::DeserializeCachedItem(uchar *,unsigned __int64)

- ea: `0x1800e8a40`
- end: `0x1800e8c48`
- name: `?DeserializeCachedItem@MRTTransformerData@DataStoreCache@@UEAAXPEAE_K@Z`
- size: `520`
- prototype: `void(DataStoreCache::MRTTransformerData *__hidden this, unsigned __int8 *, unsigned __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001dac0`
- `0x1800e8a40`
- `0x1800e8c50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e8a65`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e8a65`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e8c1f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e8c1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e8a8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e8aa6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e8ac8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e8ae0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e8b02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e8b1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e8b3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e8b54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e8b76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e8b8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e8bb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e8bc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e8bea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e8c02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e8a8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e8aa6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e8ac8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e8ae0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e8b02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e8b1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e8b3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e8b54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e8b76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e8b8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e8bb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e8bc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e8bea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e8c02`

## string_xrefs

- `0x1800e8c36`: `shellcommon\shell\datastorecache\transformers\mrttransformer\lib\mrttransformer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall DataStoreCache::MRTTransformerData::DeserializeCachedItem(
        DataStoreCache::MRTTransformerData *this,
        unsigned __int8 *a2,
        __int64 a3)
{
  RTL_SRWLOCK *v5; // rsi
  _QWORD *v6; // rbx
  _QWORD *v7; // rbx
  _QWORD *v8; // rbx
  _QWORD *v9; // rbx
  _QWORD *v10; // rbx
  _QWORD *v11; // rbx
  _QWORD *v12; // rbx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+28h]
  unsigned __int8 *v15; // [rsp+50h] [rbp+30h] BYREF
  HSTRING string; // [rsp+58h] [rbp+38h] BYREF
  __int64 v17; // [rsp+60h] [rbp+40h] BYREF
  RTL_SRWLOCK *v18; // [rsp+68h] [rbp+48h]

  v17 = a3;
  v5 = (RTL_SRWLOCK *)((char *)this + 136);
  AcquireSRWLockExclusive((PSRWLOCK)this + 17);
  v18 = v5;
  v15 = a2;
  v6 = (_QWORD *)DeserializeString(&string, a2, &v17, &v15);
  WindowsDeleteString(*((HSTRING *)this + 11));
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 11) = *v6;
  *v6 = 0;
  WindowsDeleteString(string);
  v7 = (_QWORD *)DeserializeString(&string, v15, &v17, &v15);
  WindowsDeleteString(*((HSTRING *)this + 12));
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 12) = *v7;
  *v7 = 0;
  WindowsDeleteString(string);
  v8 = (_QWORD *)DeserializeString(&string, v15, &v17, &v15);
  WindowsDeleteString(*((HSTRING *)this + 13));
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 13) = *v8;
  *v8 = 0;
  WindowsDeleteString(string);
  v9 = (_QWORD *)DeserializeString(&string, v15, &v17, &v15);
  WindowsDeleteString(*((HSTRING *)this + 14));
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 14) = *v9;
  *v9 = 0;
  WindowsDeleteString(string);
  v10 = (_QWORD *)DeserializeString(&string, v15, &v17, &v15);
  WindowsDeleteString(*((HSTRING *)this + 15));
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 15) = *v10;
  *v10 = 0;
  WindowsDeleteString(string);
  v11 = (_QWORD *)DeserializeString(&string, v15, &v17, &v15);
  WindowsDeleteString(*((HSTRING *)this + 9));
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 9) = *v11;
  *v11 = 0;
  WindowsDeleteString(string);
  v12 = (_QWORD *)DeserializeString(&string, v15, &v17, &v15);
  WindowsDeleteString(*((HSTRING *)this + 10));
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 10) = *v12;
  *v12 = 0;
  WindowsDeleteString(string);
  if ( v17 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x27A,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\mrttransformer\\lib\\mrttransformer.cpp",
      (const char *)0x80070057LL,
      savedregs);
  if ( v5 )
    ReleaseSRWLockExclusive(v5);
}

```

## disassembly

```asm
0x1800e8a40  mov     [rsp-28h+arg_10], r8
0x1800e8a45  push    rbp
0x1800e8a46  push    rbx
0x1800e8a47  push    rsi
0x1800e8a48  push    rdi
0x1800e8a49  push    r14; int
0x1800e8a4b  mov     rbp, rsp
0x1800e8a4e  sub     rsp, 20h
0x1800e8a52  mov     rbx, rdx
0x1800e8a55  mov     rdi, rcx
0x1800e8a58  xor     r14d, r14d
0x1800e8a5b  lea     rsi, [rcx+88h]
0x1800e8a62  mov     rcx, rsi; SRWLock
0x1800e8a65  call    cs:__imp_AcquireSRWLockExclusive
0x1800e8a6b  mov     [rbp+arg_18], rsi
0x1800e8a6f  mov     [rbp+arg_0], rbx
0x1800e8a73  lea     r9, [rbp+arg_0]
0x1800e8a77  lea     r8, [rbp+arg_10]
0x1800e8a7b  mov     rdx, rbx
0x1800e8a7e  lea     rcx, [rbp+string]
0x1800e8a82  call    ?DeserializeString@@YA?AVHString@Wrappers@WRL@Microsoft@@PEAEPEA_KPEAPEAE@Z; DeserializeString(uchar *,unsigned __int64 *,uchar * *)
0x1800e8a87  mov     rbx, rax
0x1800e8a8a  mov     rcx, [rdi+58h]; string
0x1800e8a8e  call    cs:__imp_WindowsDeleteString
0x1800e8a94  mov     [rdi+58h], r14
0x1800e8a98  mov     rcx, [rbx]
0x1800e8a9b  mov     [rdi+58h], rcx
0x1800e8a9f  mov     [rbx], r14
0x1800e8aa2  mov     rcx, [rbp+string]; string
0x1800e8aa6  call    cs:__imp_WindowsDeleteString
0x1800e8aac  lea     r9, [rbp+arg_0]
0x1800e8ab0  lea     r8, [rbp+arg_10]
0x1800e8ab4  mov     rdx, [rbp+arg_0]
0x1800e8ab8  lea     rcx, [rbp+string]
0x1800e8abc  call    ?DeserializeString@@YA?AVHString@Wrappers@WRL@Microsoft@@PEAEPEA_KPEAPEAE@Z; DeserializeString(uchar *,unsigned __int64 *,uchar * *)
0x1800e8ac1  mov     rbx, rax
0x1800e8ac4  mov     rcx, [rdi+60h]; string
0x1800e8ac8  call    cs:__imp_WindowsDeleteString
0x1800e8ace  mov     [rdi+60h], r14
0x1800e8ad2  mov     rcx, [rbx]
0x1800e8ad5  mov     [rdi+60h], rcx
0x1800e8ad9  mov     [rbx], r14
0x1800e8adc  mov     rcx, [rbp+string]; string
0x1800e8ae0  call    cs:__imp_WindowsDeleteString
0x1800e8ae6  lea     r9, [rbp+arg_0]
0x1800e8aea  lea     r8, [rbp+arg_10]
0x1800e8aee  mov     rdx, [rbp+arg_0]
0x1800e8af2  lea     rcx, [rbp+string]
0x1800e8af6  call    ?DeserializeString@@YA?AVHString@Wrappers@WRL@Microsoft@@PEAEPEA_KPEAPEAE@Z; DeserializeString(uchar *,unsigned __int64 *,uchar * *)
0x1800e8afb  mov     rbx, rax
0x1800e8afe  mov     rcx, [rdi+68h]; string
0x1800e8b02  call    cs:__imp_WindowsDeleteString
0x1800e8b08  mov     [rdi+68h], r14
0x1800e8b0c  mov     rcx, [rbx]
0x1800e8b0f  mov     [rdi+68h], rcx
0x1800e8b13  mov     [rbx], r14
0x1800e8b16  mov     rcx, [rbp+string]; string
0x1800e8b1a  call    cs:__imp_WindowsDeleteString
0x1800e8b20  lea     r9, [rbp+arg_0]
0x1800e8b24  lea     r8, [rbp+arg_10]
0x1800e8b28  mov     rdx, [rbp+arg_0]
0x1800e8b2c  lea     rcx, [rbp+string]
0x1800e8b30  call    ?DeserializeString@@YA?AVHString@Wrappers@WRL@Microsoft@@PEAEPEA_KPEAPEAE@Z; DeserializeString(uchar *,unsigned __int64 *,uchar * *)
0x1800e8b35  mov     rbx, rax
0x1800e8b38  mov     rcx, [rdi+70h]; string
0x1800e8b3c  call    cs:__imp_WindowsDeleteString
0x1800e8b42  mov     [rdi+70h], r14
0x1800e8b46  mov     rcx, [rbx]
0x1800e8b49  mov     [rdi+70h], rcx
0x1800e8b4d  mov     [rbx], r14
0x1800e8b50  mov     rcx, [rbp+string]; string
0x1800e8b54  call    cs:__imp_WindowsDeleteString
0x1800e8b5a  lea     r9, [rbp+arg_0]
0x1800e8b5e  lea     r8, [rbp+arg_10]
0x1800e8b62  mov     rdx, [rbp+arg_0]
0x1800e8b66  lea     rcx, [rbp+string]
0x1800e8b6a  call    ?DeserializeString@@YA?AVHString@Wrappers@WRL@Microsoft@@PEAEPEA_KPEAPEAE@Z; DeserializeString(uchar *,unsigned __int64 *,uchar * *)
0x1800e8b6f  mov     rbx, rax
0x1800e8b72  mov     rcx, [rdi+78h]; string
0x1800e8b76  call    cs:__imp_WindowsDeleteString
0x1800e8b7c  mov     [rdi+78h], r14
0x1800e8b80  mov     rcx, [rbx]
0x1800e8b83  mov     [rdi+78h], rcx
0x1800e8b87  mov     [rbx], r14
0x1800e8b8a  mov     rcx, [rbp+string]; string
0x1800e8b8e  call    cs:__imp_WindowsDeleteString
0x1800e8b94  lea     r9, [rbp+arg_0]
0x1800e8b98  lea     r8, [rbp+arg_10]
0x1800e8b9c  mov     rdx, [rbp+arg_0]
0x1800e8ba0  lea     rcx, [rbp+string]
0x1800e8ba4  call    ?DeserializeString@@YA?AVHString@Wrappers@WRL@Microsoft@@PEAEPEA_KPEAPEAE@Z; DeserializeString(uchar *,unsigned __int64 *,uchar * *)
0x1800e8ba9  mov     rbx, rax
0x1800e8bac  mov     rcx, [rdi+48h]; string
0x1800e8bb0  call    cs:__imp_WindowsDeleteString
0x1800e8bb6  mov     [rdi+48h], r14
0x1800e8bba  mov     rcx, [rbx]
0x1800e8bbd  mov     [rdi+48h], rcx
0x1800e8bc1  mov     [rbx], r14
0x1800e8bc4  mov     rcx, [rbp+string]; string
0x1800e8bc8  call    cs:__imp_WindowsDeleteString
0x1800e8bce  lea     r9, [rbp+arg_0]
0x1800e8bd2  lea     r8, [rbp+arg_10]
0x1800e8bd6  mov     rdx, [rbp+arg_0]
0x1800e8bda  lea     rcx, [rbp+string]
0x1800e8bde  call    ?DeserializeString@@YA?AVHString@Wrappers@WRL@Microsoft@@PEAEPEA_KPEAPEAE@Z; DeserializeString(uchar *,unsigned __int64 *,uchar * *)
0x1800e8be3  mov     rbx, rax
0x1800e8be6  mov     rcx, [rdi+50h]; string
0x1800e8bea  call    cs:__imp_WindowsDeleteString
0x1800e8bf0  mov     [rdi+50h], r14
0x1800e8bf4  mov     rcx, [rbx]
0x1800e8bf7  mov     [rdi+50h], rcx
0x1800e8bfb  mov     [rbx], r14
0x1800e8bfe  mov     rcx, [rbp+string]; string
0x1800e8c02  call    cs:__imp_WindowsDeleteString
0x1800e8c08  cmp     [rbp+arg_10], r14
0x1800e8c0c  setnz   al
0x1800e8c0f  mov     rcx, [rbp+28h]; this
0x1800e8c13  test    al, al
0x1800e8c15  jnz     short loc_1800E8C30
0x1800e8c17  test    rsi, rsi
0x1800e8c1a  jz      short loc_1800E8C25
0x1800e8c1c  mov     rcx, rsi; SRWLock
0x1800e8c1f  call    cs:__imp_ReleaseSRWLockExclusive
0x1800e8c25  add     rsp, 20h
0x1800e8c29  pop     r14
0x1800e8c2b  pop     rdi
0x1800e8c2c  pop     rsi
0x1800e8c2d  pop     rbx
0x1800e8c2e  pop     rbp
0x1800e8c2f  retn
0x1800e8c30  mov     r9d, 80070057h; char *
0x1800e8c36  lea     r8, aShellcommonShe_14; "shellcommon\\shell\\datastorecache\\tra"...
0x1800e8c3d  mov     edx, 27Ah; void *
0x1800e8c42  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
