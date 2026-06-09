# AppEnumeratorImpl::MoveNext(void)

- ea: `0x180002c40`
- end: `0x180002f35`
- name: `?MoveNext@AppEnumeratorImpl@@QEAAXXZ`
- size: `757`
- prototype: `void __fastcall(AppEnumeratorImpl *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001d70`

## callees

- `0x180002c40`
- `0x180003210`
- `0x1800a6cd8`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_toupper` at `0x180002e6c`
- `api-ms-win-crt-private-l1-1-0!_o_toupper` at `0x180002e76`
- `api-ms-win-crt-private-l1-1-0!_o_toupper` at `0x180002e6c`
- `api-ms-win-crt-private-l1-1-0!_o_toupper` at `0x180002e76`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180002dc4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180002dc4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180002d8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180002d8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002d31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002d63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002dcf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002f16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002f28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002d31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002d63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002dcf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002f16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002f28`
- `USERENV!DeriveAppContainerSidFromAppContainerName` at `0x180002d9b`
- `USERENV!DeriveAppContainerSidFromAppContainerName` at `0x180002d9b`

## pseudocode

```c
void __fastcall AppEnumeratorImpl::MoveNext(AppEnumeratorImpl *this)
{
  AppEnumeratorImpl *v1; // r14
  _BYTE *v2; // rbx
  int v3; // eax
  __int64 v4; // rcx
  int v5; // eax
  unsigned __int16 *v6; // rsi
  int (__fastcall *v7)(unsigned __int16 *, char *); // rdi
  unsigned __int16 *v8; // rdi
  int (__fastcall *v9)(unsigned __int16 *, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  int FilenameInAppContainerStorage; // ebx
  unsigned __int16 *v12; // r12
  __int64 v13; // rax
  char *v14; // r8
  unsigned __int16 *v15; // r13
  __int64 v16; // rax
  __int64 v17; // rcx
  unsigned __int16 *v18; // r14
  unsigned __int16 *v19; // r15
  unsigned __int16 *i; // rbx
  int v21; // edi
  int v22; // esi
  int v23; // eax
  unsigned __int16 *v24; // [rsp+20h] [rbp-38h]
  void **pExceptionObject; // [rsp+28h] [rbp-30h] BYREF
  int v26; // [rsp+30h] [rbp-28h]
  __int128 v27; // [rsp+38h] [rbp-20h]
  HSTRING string; // [rsp+A8h] [rbp+50h] BYREF
  unsigned __int16 *v30; // [rsp+B0h] [rbp+58h] BYREF
  PSID pSid; // [rsp+B8h] [rbp+60h] BYREF

  v1 = this;
  v2 = (char *)this + 32;
  v3 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 3) + 64LL))(
         *((_QWORD *)this + 3),
         (char *)this + 32);
  if ( v3 < 0 )
  {
    pExceptionObject = &_com_error::`vftable';
    v26 = v3;
    v27 = 0;
    throw (_com_error *)&pExceptionObject;
  }
  while ( *v2 )
  {
    v4 = *((_QWORD *)v1 + 5);
    if ( v4 )
    {
      *((_QWORD *)v1 + 5) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
    v5 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v1 + 3) + 48LL))(
           *((_QWORD *)v1 + 3),
           (__int64)v1 + 40);
    if ( v5 < 0 )
    {
      pExceptionObject = &_com_error::`vftable';
      v26 = v5;
      v27 = 0;
      throw (_com_error *)&pExceptionObject;
    }
    v30 = 0;
    if ( (*(int (__fastcall **)(_QWORD, unsigned __int16 **))(**((_QWORD **)v1 + 5) + 48LL))(*((_QWORD *)v1 + 5), &v30) < 0 )
      goto LABEL_31;
    v6 = v30;
    v7 = *(int (__fastcall **)(unsigned __int16 *, char *))(*(_QWORD *)v30 + 48LL);
    WindowsDeleteString(*((HSTRING *)v1 + 6));
    *((_QWORD *)v1 + 6) = 0;
    if ( v7(v6, (char *)v1 + 48) < 0 )
      goto LABEL_31;
    string = 0;
    v8 = v30;
    v9 = *(int (__fastcall **)(unsigned __int16 *, HSTRING *))(*(_QWORD *)v30 + 104LL);
    WindowsDeleteString(0);
    string = 0;
    if ( v9(v8, &string) < 0
      || (pSid = 0,
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0),
          (int)DeriveAppContainerSidFromAppContainerName(StringRawBuffer, &pSid) < 0) )
    {
      WindowsDeleteString(string);
      string = 0;
LABEL_31:
      if ( v30 )
        (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v30 + 16LL))(v30);
      goto LABEL_29;
    }
    FilenameInAppContainerStorage = GetFilenameInAppContainerStorage((unsigned __int16 *)v1 + 28, 0x104u, pSid, 0);
    FreeSid(pSid);
    WindowsDeleteString(string);
    string = 0;
    if ( v30 )
      (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v30 + 16LL))(v30);
    if ( FilenameInAppContainerStorage >= 0 )
    {
      v12 = (unsigned __int16 *)((char *)v1 + 56);
      v13 = -1;
      do
        ++v13;
      while ( v12[v13] );
      v14 = (char *)v1 + 2 * v13 + 56;
      v24 = (unsigned __int16 *)v14;
      v15 = *(unsigned __int16 **)v1;
      v16 = -1;
      do
        ++v16;
      while ( v15[v16] );
      v17 = (2 * v16) >> 1;
      if ( (v14 - (char *)v12) >> 1 >= v17 )
      {
        v18 = &v15[v16];
        v30 = (unsigned __int16 *)&v14[-2 * v17];
LABEL_21:
        v19 = v12;
        for ( i = v15; i != v18; ++i )
        {
          v21 = *v19;
          v22 = toupper(*i);
          if ( toupper(v21) != v22 )
          {
            if ( v12 != v30 )
            {
              ++v12;
              goto LABEL_21;
            }
            goto LABEL_28;
          }
          ++v19;
        }
        if ( v12 != v24 )
          return;
LABEL_28:
        v1 = this;
      }
    }
LABEL_29:
    v2 = (char *)v1 + 32;
    v23 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v1 + 3) + 64LL))(
            *((_QWORD *)v1 + 3),
            (__int64)v1 + 32);
    if ( v23 < 0 )
    {
      pExceptionObject = &_com_error::`vftable';
      v26 = v23;
      v27 = 0;
      throw (_com_error *)&pExceptionObject;
    }
  }
}

```

## disassembly

```asm
0x180002c40  mov     [rsp-40h+arg_0], rcx
0x180002c45  push    rbp
0x180002c46  push    rbx
0x180002c47  push    rsi
0x180002c48  push    rdi
0x180002c49  push    r12
0x180002c4b  push    r13
0x180002c4d  push    r14
0x180002c4f  push    r15
0x180002c51  mov     rbp, rsp
0x180002c54  sub     rsp, 58h
0x180002c58  mov     r14, rcx
0x180002c5b  mov     rcx, [rcx+18h]
0x180002c5f  lea     rbx, [r14+20h]
0x180002c63  mov     rax, [rcx]
0x180002c66  mov     rdx, rbx
0x180002c69  mov     rax, [rax+40h]
0x180002c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c72  test    eax, eax
0x180002c74  jns     short loc_180002C9D
0x180002c76  lea     rcx, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180002c7d  mov     [rbp+pExceptionObject], rcx
0x180002c81  mov     [rbp+var_28], eax
0x180002c84  xorps   xmm0, xmm0
0x180002c87  movdqu  [rbp+var_20], xmm0
0x180002c8c  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x180002c93  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180002c97  call    _CxxThrowException_0
0x180002c9d  xor     r15d, r15d
0x180002ca0  cmp     byte ptr [rbx], 0
0x180002ca3  jz      loc_180002F01
0x180002ca9  mov     rcx, [r14+28h]
0x180002cad  test    rcx, rcx
0x180002cb0  jz      short loc_180002CC3
0x180002cb2  mov     [r14+28h], r15
0x180002cb6  mov     rax, [rcx]
0x180002cb9  mov     rax, [rax+10h]
0x180002cbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cc2  nop
0x180002cc3  mov     rcx, [r14+18h]
0x180002cc7  mov     rax, [rcx]
0x180002cca  lea     rdx, [r14+28h]
0x180002cce  mov     rax, [rax+30h]
0x180002cd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cd7  test    eax, eax
0x180002cd9  jns     short loc_180002D02
0x180002cdb  lea     rcx, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180002ce2  mov     [rbp+pExceptionObject], rcx
0x180002ce6  mov     [rbp+var_28], eax
0x180002ce9  xorps   xmm0, xmm0
0x180002cec  movdqu  [rbp+var_20], xmm0
0x180002cf1  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x180002cf8  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180002cfc  call    _CxxThrowException_0
0x180002d02  mov     [rbp+arg_10], r15
0x180002d06  mov     rcx, [r14+28h]
0x180002d0a  mov     rax, [rcx]
0x180002d0d  lea     rdx, [rbp+arg_10]
0x180002d11  mov     rax, [rax+30h]
0x180002d15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d1a  test    eax, eax
0x180002d1c  js      loc_180002EE9
0x180002d22  mov     rsi, [rbp+arg_10]
0x180002d26  mov     rax, [rsi]
0x180002d29  mov     rdi, [rax+30h]
0x180002d2d  mov     rcx, [r14+30h]; string
0x180002d31  call    cs:__imp_WindowsDeleteString
0x180002d37  mov     [r14+30h], r15
0x180002d3b  lea     rdx, [r14+30h]
0x180002d3f  mov     rcx, rsi
0x180002d42  mov     rax, rdi
0x180002d45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d4a  test    eax, eax
0x180002d4c  js      loc_180002F22
0x180002d52  mov     [rbp+string], r15
0x180002d56  mov     rdi, [rbp+arg_10]
0x180002d5a  mov     rax, [rdi]
0x180002d5d  mov     rbx, [rax+68h]
0x180002d61  xor     ecx, ecx; string
0x180002d63  call    cs:__imp_WindowsDeleteString
0x180002d69  mov     [rbp+string], r15
0x180002d6d  lea     rdx, [rbp+string]
0x180002d71  mov     rcx, rdi
0x180002d74  mov     rax, rbx
0x180002d77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d7c  test    eax, eax
0x180002d7e  js      loc_180002F24
0x180002d84  mov     [rbp+pSid], r15
0x180002d88  xor     edx, edx; length
0x180002d8a  mov     rcx, [rbp+string]; string
0x180002d8e  call    cs:__imp_WindowsGetStringRawBuffer
0x180002d94  lea     rdx, [rbp+pSid]
0x180002d98  mov     rcx, rax
0x180002d9b  call    cs:__imp_DeriveAppContainerSidFromAppContainerName
0x180002da1  test    eax, eax
0x180002da3  js      loc_180002F12
0x180002da9  lea     rcx, [r14+38h]; unsigned __int16 *
0x180002dad  xor     r9d, r9d; unsigned __int16 *
0x180002db0  mov     r8, [rbp+pSid]; Sid
0x180002db4  mov     edx, 104h; unsigned int
0x180002db9  call    ?GetFilenameInAppContainerStorage@@YAJPEAGIPEAXPEBGZZ; GetFilenameInAppContainerStorage(ushort *,uint,void *,ushort const *,...)
0x180002dbe  mov     ebx, eax
0x180002dc0  mov     rcx, [rbp+pSid]; pSid
0x180002dc4  call    cs:__imp_FreeSid
0x180002dca  nop
0x180002dcb  mov     rcx, [rbp+string]; string
0x180002dcf  call    cs:__imp_WindowsDeleteString
0x180002dd5  mov     [rbp+string], r15
0x180002dd9  mov     rcx, [rbp+arg_10]
0x180002ddd  test    rcx, rcx
0x180002de0  jz      short loc_180002DEF
0x180002de2  mov     rdx, [rcx]
0x180002de5  mov     rax, [rdx+10h]
0x180002de9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dee  nop
0x180002def  test    ebx, ebx
0x180002df1  js      loc_180002EA3
0x180002df7  lea     r12, [r14+38h]
0x180002dfb  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180002e02  inc     rax
0x180002e05  cmp     word ptr [r12+rax*2], 0
0x180002e0b  jnz     short loc_180002E02
0x180002e0d  add     rax, 1Ch
0x180002e11  lea     r8, [r14+rax*2]
0x180002e15  mov     [rbp+var_38], r8
0x180002e19  mov     r13, [r14]
0x180002e1c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180002e23  lea     rax, [rax+1]
0x180002e27  cmp     word ptr [r13+rax*2+0], 0
0x180002e2e  jnz     short loc_180002E23
0x180002e30  lea     rdx, [rax+rax]
0x180002e34  mov     rcx, rdx
0x180002e37  sar     rcx, 1
0x180002e3a  mov     rax, r8
0x180002e3d  sub     rax, r12
0x180002e40  sar     rax, 1
0x180002e43  cmp     rax, rcx
0x180002e46  jl      short loc_180002EA3
0x180002e48  lea     r14, [rdx+r13]
0x180002e4c  lea     rax, [rcx+rcx]
0x180002e50  mov     rcx, r8
0x180002e53  sub     rcx, rax
0x180002e56  mov     [rbp+arg_10], rcx
0x180002e5a  mov     r15, r12
0x180002e5d  mov     rbx, r13
0x180002e60  cmp     rbx, r14
0x180002e63  jz      short loc_180002E96
0x180002e65  movzx   ecx, word ptr [rbx]; C
0x180002e68  movzx   edi, word ptr [r15]
0x180002e6c  call    cs:__imp_toupper
0x180002e72  mov     esi, eax
0x180002e74  mov     ecx, edi; C
0x180002e76  call    cs:__imp_toupper
0x180002e7c  cmp     eax, esi
0x180002e7e  jnz     short loc_180002E8A
0x180002e80  add     r15, 2
0x180002e84  add     rbx, 2
0x180002e88  jmp     short loc_180002E60
0x180002e8a  cmp     r12, [rbp+arg_10]
0x180002e8e  jz      short loc_180002E9C
0x180002e90  add     r12, 2
0x180002e94  jmp     short loc_180002E5A
0x180002e96  cmp     r12, [rbp+var_38]
0x180002e9a  jnz     short loc_180002F01
0x180002e9c  xor     r15d, r15d
0x180002e9f  mov     r14, [rbp+arg_0]
0x180002ea3  mov     rcx, [r14+18h]
0x180002ea7  mov     rax, [rcx]
0x180002eaa  lea     rbx, [r14+20h]
0x180002eae  mov     rdx, rbx
0x180002eb1  mov     rax, [rax+40h]
0x180002eb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002eba  test    eax, eax
0x180002ebc  jns     loc_180002CA0
0x180002ec2  lea     rcx, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180002ec9  mov     [rbp+pExceptionObject], rcx
0x180002ecd  mov     [rbp+var_28], eax
0x180002ed0  xorps   xmm0, xmm0
0x180002ed3  movdqu  [rbp+var_20], xmm0
0x180002ed8  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x180002edf  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180002ee3  call    _CxxThrowException_0
0x180002ee9  mov     rcx, [rbp+arg_10]
0x180002eed  test    rcx, rcx
0x180002ef0  jz      short loc_180002EFF
0x180002ef2  mov     rax, [rcx]
0x180002ef5  mov     rax, [rax+10h]
0x180002ef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002efe  nop
0x180002eff  jmp     short loc_180002EA3
0x180002f01  add     rsp, 58h
0x180002f05  pop     r15
0x180002f07  pop     r14
0x180002f09  pop     r13
0x180002f0b  pop     r12
0x180002f0d  pop     rdi
0x180002f0e  pop     rsi
0x180002f0f  pop     rbx
0x180002f10  pop     rbp
0x180002f11  retn
0x180002f12  mov     rcx, [rbp+string]; string
0x180002f16  call    cs:__imp_WindowsDeleteString
0x180002f1c  mov     [rbp+string], r15
0x180002f20  jmp     short loc_180002EE9
0x180002f22  jmp     short loc_180002EE9
0x180002f24  mov     rcx, [rbp+string]; string
0x180002f28  call    cs:__imp_WindowsDeleteString
0x180002f2e  mov     [rbp+string], r15
0x180002f32  jmp     short loc_180002EE9
```
