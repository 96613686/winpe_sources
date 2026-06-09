# Microsoft::WRL::Details::RegisterWinRTObject<2>(wchar_t const *,wchar_t const * *,_RO_REGISTRATION_COOKIE * *,uint)

- ea: `0x18000cd58`
- end: `0x18000ce58`
- name: `??$RegisterWinRTObject@$01@Details@WRL@Microsoft@@YAJPEB_WPEAPEB_WPEAPEAU_RO_REGISTRATION_COOKIE@@I@Z`
- size: `256`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000def0`

## callees

- `0x1800029cc`
- `0x180002a0c`
- `0x18000cd58`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x18000ce0d`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x18000ce0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ce22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ce22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000cdef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000cdef`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::Details::RegisterWinRTObject<2>(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  unsigned __int64 v5; // rdi
  unsigned __int64 v7; // rax
  _QWORD *v8; // r15
  unsigned __int64 v9; // rax
  HSTRING *v10; // rax
  const struct std::nothrow_t *v11; // rdx
  HSTRING *v12; // r14
  int v13; // ebx
  unsigned int v14; // esi
  __int64 v15; // rdx
  const WCHAR *v16; // rcx
  HRESULT String; // eax
  unsigned int i; // edi
  const struct std::nothrow_t *v19; // rdx

  v5 = a4;
  v7 = 8LL * a4;
  if ( !is_mul_ok(a4, 8u) )
    v7 = -1;
  v8 = operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
  v9 = 8 * v5;
  if ( !is_mul_ok(v5, 8u) )
    v9 = -1;
  v10 = (HSTRING *)operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
  v12 = v10;
  if ( v8 && v10 )
  {
    v13 = 0;
    v14 = 0;
    if ( (_DWORD)v5 )
    {
      while ( v13 >= 0 )
      {
        v15 = -1;
        v8[v14] = Microsoft::WRL::Details::ActivationFactoryCallback<2>;
        v16 = *(const WCHAR **)(a2 + 8LL * v14);
        do
          ++v15;
        while ( v16[v15] );
        String = WindowsCreateString(v16, v15, &v12[v14++]);
        v13 = String;
        if ( v14 >= (unsigned int)v5 )
        {
          if ( String < 0 )
            break;
          goto LABEL_13;
        }
      }
    }
    else
    {
LABEL_13:
      v13 = RoRegisterActivationFactories(v12, v8, (unsigned int)v5, a3);
    }
    for ( i = 0; i < v14; ++i )
      WindowsDeleteString(v12[i]);
  }
  else
  {
    v13 = -2147024882;
  }
  operator delete(v8, v11);
  operator delete(v12, v19);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18000cd58  push    rbx
0x18000cd5a  push    rbp
0x18000cd5b  push    rsi
0x18000cd5c  push    rdi
0x18000cd5d  push    r12
0x18000cd5f  push    r13
0x18000cd61  push    r14
0x18000cd63  push    r15
0x18000cd65  sub     rsp, 28h
0x18000cd69  mov     r12, rdx
0x18000cd6c  mov     edi, r9d
0x18000cd6f  mov     esi, 8
0x18000cd74  mov     rbp, r8
0x18000cd77  mov     eax, esi
0x18000cd79  mul     rdi
0x18000cd7c  lea     r14, [rsi-9]
0x18000cd80  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000cd87  cmovb   rax, r14
0x18000cd8b  mov     rcx, rax; unsigned __int64
0x18000cd8e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000cd93  mov     r15, rax
0x18000cd96  mov     eax, esi
0x18000cd98  mul     rdi
0x18000cd9b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000cda2  cmovb   rax, r14
0x18000cda6  mov     rcx, rax; unsigned __int64
0x18000cda9  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000cdae  xor     r13d, r13d
0x18000cdb1  mov     r14, rax
0x18000cdb4  test    r15, r15
0x18000cdb7  jz      short loc_18000CE30
0x18000cdb9  test    rax, rax
0x18000cdbc  jz      short loc_18000CE30
0x18000cdbe  mov     ebx, r13d
0x18000cdc1  mov     esi, r13d
0x18000cdc4  test    edi, edi
0x18000cdc6  jz      short loc_18000CE01
0x18000cdc8  test    ebx, ebx
0x18000cdca  js      short loc_18000CE15
0x18000cdcc  mov     eax, esi
0x18000cdce  lea     rcx, ??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)
0x18000cdd5  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000cdd9  mov     [r15+rax*8], rcx
0x18000cddd  mov     rcx, [r12+rax*8]; sourceString
0x18000cde1  inc     rdx; length
0x18000cde4  cmp     [rcx+rdx*2], r13w
0x18000cde9  jnz     short loc_18000CDE1
0x18000cdeb  lea     r8, [r14+rax*8]; string
0x18000cdef  call    cs:__imp_WindowsCreateString
0x18000cdf5  inc     esi
0x18000cdf7  mov     ebx, eax
0x18000cdf9  cmp     esi, edi
0x18000cdfb  jb      short loc_18000CDC8
0x18000cdfd  test    eax, eax
0x18000cdff  js      short loc_18000CE15
0x18000ce01  mov     r9, rbp
0x18000ce04  mov     r8d, edi
0x18000ce07  mov     rdx, r15
0x18000ce0a  mov     rcx, r14
0x18000ce0d  call    cs:__imp_RoRegisterActivationFactories
0x18000ce13  mov     ebx, eax
0x18000ce15  mov     edi, r13d
0x18000ce18  test    esi, esi
0x18000ce1a  jz      short loc_18000CE35
0x18000ce1c  mov     ecx, edi
0x18000ce1e  mov     rcx, [r14+rcx*8]; string
0x18000ce22  call    cs:__imp_WindowsDeleteString
0x18000ce28  inc     edi
0x18000ce2a  cmp     edi, esi
0x18000ce2c  jb      short loc_18000CE1C
0x18000ce2e  jmp     short loc_18000CE35
0x18000ce30  mov     ebx, 8007000Eh
0x18000ce35  mov     rcx, r15; void *
0x18000ce38  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000ce3d  mov     rcx, r14; void *
0x18000ce40  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000ce45  mov     eax, ebx
0x18000ce47  add     rsp, 28h
0x18000ce4b  pop     r15
0x18000ce4d  pop     r14
0x18000ce4f  pop     r13
0x18000ce51  pop     r12
0x18000ce53  pop     rdi
0x18000ce54  pop     rsi
0x18000ce55  pop     rbp
0x18000ce56  pop     rbx
0x18000ce57  retn
```
