# wprt::PassThroughAPI_impl::Process(void)

- ea: `0x180007960`
- end: `0x180007b03`
- name: `?Process@PassThroughAPI_impl@wprt@@QEAAJXZ`
- size: `419`
- prototype: `__int64 __fastcall(wprt::PassThroughAPI_impl *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180003e40`

## callees

- `0x180003180`
- `0x180003d3c`
- `0x180007960`
- `0x1800a031b`
- `0x1800a0387`
- `0x1800bf3b0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180007ab3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180007ab3`

## pseudocode

```c
__int64 __fastcall wprt::PassThroughAPI_impl::Process(wprt::PassThroughAPI_impl *this)
{
  unsigned int v2; // esi
  PCWSTR StringRawBuffer_0; // rax
  __int64 v4; // rdi
  void (__fastcall *v5)(__int64, _BYTE *, __int64); // rbx
  __int64 v6; // rax
  __int64 v7; // rax
  const WCHAR *v8; // rax
  __int64 v10; // [rsp+30h] [rbp-68h] BYREF
  HSTRING string; // [rsp+38h] [rbp-60h] BYREF
  __int64 v12; // [rsp+40h] [rbp-58h] BYREF
  _BYTE v13[16]; // [rsp+48h] [rbp-50h] BYREF
  _QWORD v14[3]; // [rsp+58h] [rbp-40h] BYREF

  v2 = -2147467259;
  string = 0;
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD, HSTRING *))(**((_QWORD **)this + 1) + 16LL))(
         *((_QWORD *)this + 1),
         &string) )
  {
    v10 = 0;
    StringRawBuffer_0 = WindowsGetStringRawBuffer_0(string, 0);
    if ( !(unsigned int)CreateRandomAccessStreamOnFile_0(
                          StringRawBuffer_0,
                          0,
                          &GUID_905a0fe1_bc53_11df_8c49_001e4fc686da,
                          &v10) )
    {
      v4 = *((_QWORD *)this + 2);
      v5 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)v4 + 8LL);
      v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 24LL))(*((_QWORD *)this + 1));
      v5(v4, v13, v6);
      v7 = *((_QWORD *)this + 1);
      v14[0] = &wprt::ProcCallback::`vftable';
      v14[1] = v7;
      v14[2] = v13;
      if ( !(*(unsigned int (__fastcall **)(_QWORD, _BYTE *, __int64, _QWORD *))(**(_QWORD **)this + 8LL))(
              *(_QWORD *)this,
              v13,
              v10,
              v14) )
        v2 = 0;
      v12 = 0;
      if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v10)(
             v10,
             &GUID_30d5a829_7fa4_4026_83bb_d75bae4ea99e,
             &v12) >= 0 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 48LL))(v12);
      if ( v12 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    v8 = WindowsGetStringRawBuffer_0(string, 0);
    DeleteFileW(v8);
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  WindowsDeleteString_0(string);
  return v2;
}

```

## disassembly

```asm
0x180007960  mov     [rsp+arg_8], rbx
0x180007965  mov     [rsp+arg_10], rbp
0x18000796a  push    rsi
0x18000796b  push    rdi
0x18000796c  push    r14
0x18000796e  sub     rsp, 80h
0x180007975  mov     rax, cs:__security_cookie
0x18000797c  xor     rax, rsp
0x18000797f  mov     [rsp+98h+var_28], rax
0x180007984  mov     r14, rcx
0x180007987  mov     esi, 80004005h
0x18000798c  xor     ebp, ebp
0x18000798e  mov     [rsp+98h+string], rbp
0x180007993  mov     rcx, [rcx+8]
0x180007997  mov     rax, [rcx]
0x18000799a  lea     rdx, [rsp+98h+string]
0x18000799f  mov     rax, [rax+10h]
0x1800079a3  call    cs:__guard_dispatch_icall_fptr
0x1800079a9  test    al, al
0x1800079ab  jz      loc_180007AD2
0x1800079b1  mov     [rsp+98h+var_68], rbp
0x1800079b6  xor     edx, edx; length
0x1800079b8  mov     rcx, [rsp+98h+string]; string
0x1800079bd  call    WindowsGetStringRawBuffer_0
0x1800079c2  lea     r9, [rsp+98h+var_68]
0x1800079c7  lea     r8, _GUID_905a0fe1_bc53_11df_8c49_001e4fc686da
0x1800079ce  xor     edx, edx
0x1800079d0  mov     rcx, rax
0x1800079d3  call    CreateRandomAccessStreamOnFile_0
0x1800079d8  test    eax, eax
0x1800079da  jnz     loc_180007AA4
0x1800079e0  mov     rdi, [r14+10h]
0x1800079e4  mov     rax, [rdi]
0x1800079e7  mov     rbx, [rax+8]
0x1800079eb  mov     rcx, [r14+8]
0x1800079ef  mov     rax, [rcx]
0x1800079f2  mov     rax, [rax+18h]
0x1800079f6  call    cs:__guard_dispatch_icall_fptr
0x1800079fc  mov     r8, rax
0x1800079ff  lea     rdx, [rsp+98h+var_50]
0x180007a04  mov     rcx, rdi
0x180007a07  mov     rax, rbx
0x180007a0a  call    cs:__guard_dispatch_icall_fptr
0x180007a10  mov     rax, [r14+8]
0x180007a14  lea     rcx, ??_7ProcCallback@wprt@@6B@; const wprt::ProcCallback::`vftable'
0x180007a1b  mov     [rsp+98h+var_40], rcx
0x180007a20  mov     [rsp+98h+var_38], rax
0x180007a25  lea     rax, [rsp+98h+var_50]
0x180007a2a  mov     [rsp+98h+var_30], rax
0x180007a2f  mov     rcx, [r14]
0x180007a32  mov     rax, [rcx]
0x180007a35  lea     r9, [rsp+98h+var_40]
0x180007a3a  mov     r8, [rsp+98h+var_68]
0x180007a3f  lea     rdx, [rsp+98h+var_50]
0x180007a44  mov     rax, [rax+8]
0x180007a48  call    cs:__guard_dispatch_icall_fptr
0x180007a4e  test    eax, eax
0x180007a50  cmovz   esi, ebp
0x180007a53  mov     [rsp+98h+var_58], rbp
0x180007a58  mov     rcx, [rsp+98h+var_68]
0x180007a5d  mov     rax, [rcx]
0x180007a60  lea     r8, [rsp+98h+var_58]
0x180007a65  lea     rdx, _GUID_30d5a829_7fa4_4026_83bb_d75bae4ea99e
0x180007a6c  mov     rax, [rax]
0x180007a6f  call    cs:__guard_dispatch_icall_fptr
0x180007a75  test    eax, eax
0x180007a77  js      short loc_180007A8C
0x180007a79  mov     rcx, [rsp+98h+var_58]
0x180007a7e  mov     rax, [rcx]
0x180007a81  mov     rax, [rax+30h]
0x180007a85  call    cs:__guard_dispatch_icall_fptr
0x180007a8b  nop
0x180007a8c  mov     rcx, [rsp+98h+var_58]
0x180007a91  test    rcx, rcx
0x180007a94  jz      short loc_180007AA4
0x180007a96  mov     rax, [rcx]
0x180007a99  mov     rax, [rax+10h]
0x180007a9d  call    cs:__guard_dispatch_icall_fptr
0x180007aa3  nop
0x180007aa4  xor     edx, edx; length
0x180007aa6  mov     rcx, [rsp+98h+string]; string
0x180007aab  call    WindowsGetStringRawBuffer_0
0x180007ab0  mov     rcx, rax; lpFileName
0x180007ab3  call    cs:__imp_DeleteFileW
0x180007ab9  nop
0x180007aba  mov     rcx, [rsp+98h+var_68]
0x180007abf  test    rcx, rcx
0x180007ac2  jz      short loc_180007AD2
0x180007ac4  mov     rdx, [rcx]
0x180007ac7  mov     rax, [rdx+10h]
0x180007acb  call    cs:__guard_dispatch_icall_fptr
0x180007ad1  nop
0x180007ad2  mov     rcx, [rsp+98h+string]; string
0x180007ad7  call    WindowsDeleteString_0
0x180007adc  mov     eax, esi
0x180007ade  mov     rcx, [rsp+98h+var_28]
0x180007ae3  xor     rcx, rsp; StackCookie
0x180007ae6  call    __security_check_cookie
0x180007aeb  lea     r11, [rsp+98h+var_18]
0x180007af3  mov     rbx, [r11+28h]
0x180007af7  mov     rbp, [r11+30h]
0x180007afb  mov     rsp, r11
0x180007afe  pop     r14
0x180007b00  pop     rdi
0x180007b01  pop     rsi
0x180007b02  retn
```
