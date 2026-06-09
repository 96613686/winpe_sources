# Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<char const *>::StructuredObjectCopy<char const *>(Mso::Logging::StructuredObject<char const *,1> const &)

- ea: `0x18000ce20`
- end: `0x18000d000`
- name: `??0?$StructuredObjectCopy@PEBD@StructuredTraceCopier@Logging@Mso@@QEAA@AEBU?$StructuredObject@PEBD$00@23@@Z`
- size: `480`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000e76c`

## callees

- `0x18000410c`
- `0x18000a208`
- `0x18000ce20`
- `0x1800266e0`
- `0x18002b3c0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000cf80`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000cf80`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000cf38`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000cf87`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000cf38`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000cf87`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<char const *>::StructuredObjectCopy<char const *>(
        __int64 a1,
        _QWORD *a2)
{
  _QWORD *v4; // rbx
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rsi
  __int64 v8; // r8
  __int64 v9; // rdx
  void **v10; // rax
  char v11; // si
  void *v12; // rcx
  void *v13; // rcx
  __int16 v14; // cx
  _QWORD *v15; // rax
  __int128 v17; // [rsp+38h] [rbp-11h] BYREF
  __m128i si128; // [rsp+48h] [rbp-1h]
  __int64 v19; // [rsp+58h] [rbp+Fh]
  void *Block[2]; // [rsp+60h] [rbp+17h] BYREF
  __int128 v21; // [rsp+70h] [rbp+27h]

  v19 = a1;
  v4 = 0;
  *(_QWORD *)a1 = &Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<char const *>::`vftable';
  v5 = a1 + 8;
  v6 = a2[1];
  *(_OWORD *)v5 = 0;
  *(_QWORD *)(v5 + 16) = 0;
  *(_QWORD *)(v5 + 24) = 0;
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( *(_WORD *)(v6 + 2 * v8) );
  std::wstring::_Construct<1,wchar_t const *>(v5, v6, v8);
  v9 = a2[2];
  if ( v9 )
  {
    *(_OWORD *)Block = 0;
    v21 = 0;
    do
      ++v7;
    while ( *(_BYTE *)(v9 + v7) );
    std::string::_Construct<1,char const *>(Block);
    v10 = Block;
    v11 = 1;
  }
  else
  {
    v17 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v17) = 0;
    v10 = (void **)&v17;
    v11 = 2;
  }
  *(_OWORD *)(a1 + 40) = *(_OWORD *)v10;
  *(_OWORD *)(a1 + 56) = *((_OWORD *)v10 + 1);
  *(_BYTE *)v10 = 0;
  v10[2] = 0;
  v10[3] = (void *)15;
  if ( (v11 & 2) != 0 )
  {
    v11 &= ~2u;
    if ( si128.m128i_i64[1] > 0xFuLL )
    {
      v12 = (void *)v17;
      if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
      {
        v12 = *(void **)(v17 - 8);
        if ( (unsigned __int64)(v17 - (_QWORD)v12 - 8) > 0x1F )
LABEL_17:
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v12);
    }
  }
  if ( (v11 & 1) != 0 && *((_QWORD *)&v21 + 1) > 0xFu )
  {
    v13 = Block[0];
    if ( (unsigned __int64)(*((_QWORD *)&v21 + 1) + 1LL) >= 0x1000 )
    {
      v13 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v13 - 8) > 0x1F )
        goto LABEL_17;
    }
    free(v13);
  }
  v14 = (*(__int64 (__fastcall **)(_QWORD *))(*a2 + 24LL))(a2);
  if ( a2[2] )
  {
    v4 = (_QWORD *)(a1 + 40);
    if ( *(_QWORD *)(a1 + 64) > 0xFu )
      v4 = (_QWORD *)*v4;
  }
  v15 = (_QWORD *)(a1 + 8);
  if ( *(_QWORD *)(a1 + 32) > 7u )
    v15 = (_QWORD *)*v15;
  *(_QWORD *)(a1 + 72) = &Mso::Logging::StructuredObject<char const *,1>::`vftable';
  *(_QWORD *)(a1 + 80) = v15;
  *(_QWORD *)(a1 + 88) = v4;
  *(_WORD *)(a1 + 96) = v14;
  return a1;
}

```

## disassembly

```asm
0x18000ce20  mov     [rsp-8+arg_10], rbx
0x18000ce25  mov     [rsp-8+arg_18], rsi
0x18000ce2a  push    rbp
0x18000ce2b  push    rdi
0x18000ce2c  push    r14
0x18000ce2e  lea     rbp, [rsp-47h]
0x18000ce33  sub     rsp, 90h
0x18000ce3a  mov     rax, cs:__security_cookie
0x18000ce41  xor     rax, rsp
0x18000ce44  mov     [rbp+57h+var_20], rax
0x18000ce48  mov     r14, rdx
0x18000ce4b  mov     rdi, rcx
0x18000ce4e  mov     [rbp+57h+var_48], rcx
0x18000ce52  xor     ebx, ebx
0x18000ce54  mov     dword ptr [rbp+57h+var_70], ebx
0x18000ce57  lea     rax, ??_7?$StructuredObjectCopy@PEBD@StructuredTraceCopier@Logging@Mso@@6B@; const Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<char const *>::`vftable'
0x18000ce5e  mov     [rcx], rax
0x18000ce61  add     rcx, 8
0x18000ce65  mov     [rbp+57h+var_70], rcx
0x18000ce69  mov     rdx, [rdx+8]
0x18000ce6d  xorps   xmm0, xmm0
0x18000ce70  movups  xmmword ptr [rcx], xmm0
0x18000ce73  mov     [rcx+10h], rbx
0x18000ce77  mov     [rcx+18h], rbx
0x18000ce7b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000ce7f  mov     r8, rsi
0x18000ce82  inc     r8
0x18000ce85  cmp     [rdx+r8*2], bx
0x18000ce8a  jnz     short loc_18000CE82
0x18000ce8c  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000ce91  mov     rdx, [r14+10h]
0x18000ce95  xorps   xmm0, xmm0
0x18000ce98  test    rdx, rdx
0x18000ce9b  jz      short loc_18000CEC8
0x18000ce9d  movups  xmmword ptr [rbp+57h+Block], xmm0
0x18000cea1  xorps   xmm1, xmm1
0x18000cea4  movdqu  [rbp+57h+var_30], xmm1
0x18000cea9  inc     rsi
0x18000ceac  cmp     [rdx+rsi], bl
0x18000ceaf  jnz     short loc_18000CEA9
0x18000ceb1  mov     r8, rsi
0x18000ceb4  lea     rcx, [rbp+57h+Block]
0x18000ceb8  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18000cebd  lea     rax, [rbp+57h+Block]
0x18000cec1  mov     esi, 1
0x18000cec6  jmp     short loc_18000CEE5
0x18000cec8  movups  [rbp+57h+var_68], xmm0
0x18000cecc  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x18000ced4  movdqu  [rbp+57h+var_58], xmm1
0x18000ced9  mov     byte ptr [rbp+57h+var_68], bl
0x18000cedc  lea     rax, [rbp+57h+var_68]
0x18000cee0  mov     esi, 2
0x18000cee5  movups  xmm0, xmmword ptr [rax]
0x18000cee8  movups  xmmword ptr [rdi+28h], xmm0
0x18000ceec  movups  xmm1, xmmword ptr [rax+10h]
0x18000cef0  movups  xmmword ptr [rdi+38h], xmm1
0x18000cef4  mov     [rax], bl
0x18000cef6  mov     [rax+10h], rbx
0x18000cefa  mov     qword ptr [rax+18h], 0Fh
0x18000cf02  test    sil, 2
0x18000cf06  jz      short loc_18000CF3E
0x18000cf08  and     esi, 0FFFFFFFDh
0x18000cf0b  mov     rax, qword ptr [rbp+57h+var_58+8]
0x18000cf0f  cmp     rax, 0Fh
0x18000cf13  jbe     short loc_18000CF3E
0x18000cf15  mov     rcx, qword ptr [rbp+57h+var_68]
0x18000cf19  mov     rdx, rcx
0x18000cf1c  inc     rax
0x18000cf1f  cmp     rax, 1000h
0x18000cf25  jb      short loc_18000CF38
0x18000cf27  mov     rcx, [rcx-8]; Block
0x18000cf2b  sub     rdx, rcx
0x18000cf2e  lea     rax, [rdx-8]
0x18000cf32  cmp     rax, 1Fh
0x18000cf36  ja      short loc_18000CF71
0x18000cf38  call    cs:__imp_free
0x18000cf3e  test    sil, 1
0x18000cf42  jz      short loc_18000CF8D
0x18000cf44  mov     rax, qword ptr [rbp+57h+var_30+8]
0x18000cf48  cmp     rax, 0Fh
0x18000cf4c  jbe     short loc_18000CF8D
0x18000cf4e  mov     rcx, [rbp+57h+Block]; Block
0x18000cf52  mov     rdx, rcx
0x18000cf55  inc     rax
0x18000cf58  cmp     rax, 1000h
0x18000cf5e  jb      short loc_18000CF87
0x18000cf60  mov     rcx, [rcx-8]
0x18000cf64  sub     rdx, rcx
0x18000cf67  lea     rax, [rdx-8]
0x18000cf6b  cmp     rax, 1Fh
0x18000cf6f  jbe     short loc_18000CF87
0x18000cf71  mov     [rsp+0A0h+Reserved], rbx; Reserved
0x18000cf76  xor     r9d, r9d; LineNo
0x18000cf79  xor     r8d, r8d; FileName
0x18000cf7c  xor     edx, edx; FunctionName
0x18000cf7e  xor     ecx, ecx; Expression
0x18000cf80  call    cs:__imp__invoke_watson
0x18000cf87  call    cs:__imp_free
0x18000cf8d  mov     rax, [r14]
0x18000cf90  mov     rcx, r14
0x18000cf93  mov     rax, [rax+18h]
0x18000cf97  call    cs:__guard_dispatch_icall_fptr
0x18000cf9d  movzx   ecx, ax
0x18000cfa0  cmp     [r14+10h], rbx
0x18000cfa4  jz      short loc_18000CFB4
0x18000cfa6  lea     rbx, [rdi+28h]
0x18000cfaa  cmp     qword ptr [rbx+18h], 0Fh
0x18000cfaf  jbe     short loc_18000CFB4
0x18000cfb1  mov     rbx, [rbx]
0x18000cfb4  lea     rax, [rdi+8]
0x18000cfb8  cmp     qword ptr [rax+18h], 7
0x18000cfbd  jbe     short loc_18000CFC2
0x18000cfbf  mov     rax, [rax]
0x18000cfc2  lea     rdx, ??_7?$StructuredObject@PEBD$00@Logging@Mso@@6B@; const Mso::Logging::StructuredObject<char const *,1>::`vftable'
0x18000cfc9  mov     [rdi+48h], rdx
0x18000cfcd  mov     [rdi+50h], rax
0x18000cfd1  mov     [rdi+58h], rbx
0x18000cfd5  mov     [rdi+60h], cx
0x18000cfd9  mov     rax, rdi
0x18000cfdc  mov     rcx, [rbp+57h+var_20]
0x18000cfe0  xor     rcx, rsp; StackCookie
0x18000cfe3  call    __security_check_cookie
0x18000cfe8  lea     r11, [rsp+0A0h+var_10]
0x18000cff0  mov     rbx, [r11+30h]
0x18000cff4  mov     rsi, [r11+38h]
0x18000cff8  mov     rsp, r11
0x18000cffb  pop     r14
0x18000cffd  pop     rdi
0x18000cffe  pop     rbp
0x18000cfff  retn
```
