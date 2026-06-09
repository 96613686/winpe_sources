# Microsoft::WRL::Details::RegisterWinRTObject<2>(ushort const *,ushort const * *,_RO_REGISTRATION_COOKIE * *,uint)

- ea: `0x18000cd98`
- end: `0x18000ce98`
- name: `??$RegisterWinRTObject@$01@Details@WRL@Microsoft@@YAJPEBGPEAPEBGPEAPEAU_RO_REGISTRATION_COOKIE@@I@Z`
- size: `256`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000d960`

## callees

- `0x180006a10`
- `0x180006a90`
- `0x18000cd98`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ce62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ce62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000ce2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000ce2f`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x18000ce4d`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x18000ce4d`

## pseudocode

```c
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
0x18000cd98  push    rbx
0x18000cd9a  push    rbp
0x18000cd9b  push    rsi
0x18000cd9c  push    rdi
0x18000cd9d  push    r12
0x18000cd9f  push    r13
0x18000cda1  push    r14
0x18000cda3  push    r15
0x18000cda5  sub     rsp, 28h
0x18000cda9  mov     r12, rdx
0x18000cdac  mov     edi, r9d
0x18000cdaf  mov     esi, 8
0x18000cdb4  mov     rbp, r8
0x18000cdb7  mov     eax, esi
0x18000cdb9  mul     rdi
0x18000cdbc  lea     r14, [rsi-9]
0x18000cdc0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000cdc7  cmovb   rax, r14
0x18000cdcb  mov     rcx, rax; unsigned __int64
0x18000cdce  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000cdd3  mov     r15, rax
0x18000cdd6  mov     eax, esi
0x18000cdd8  mul     rdi
0x18000cddb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000cde2  cmovb   rax, r14
0x18000cde6  mov     rcx, rax; unsigned __int64
0x18000cde9  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000cdee  xor     r13d, r13d
0x18000cdf1  mov     r14, rax
0x18000cdf4  test    r15, r15
0x18000cdf7  jz      short loc_18000CE70
0x18000cdf9  test    rax, rax
0x18000cdfc  jz      short loc_18000CE70
0x18000cdfe  mov     ebx, r13d
0x18000ce01  mov     esi, r13d
0x18000ce04  test    edi, edi
0x18000ce06  jz      short loc_18000CE41
0x18000ce08  test    ebx, ebx
0x18000ce0a  js      short loc_18000CE55
0x18000ce0c  mov     eax, esi
0x18000ce0e  lea     rcx, ??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)
0x18000ce15  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000ce19  mov     [r15+rax*8], rcx
0x18000ce1d  mov     rcx, [r12+rax*8]; sourceString
0x18000ce21  inc     rdx; length
0x18000ce24  cmp     [rcx+rdx*2], r13w
0x18000ce29  jnz     short loc_18000CE21
0x18000ce2b  lea     r8, [r14+rax*8]; string
0x18000ce2f  call    cs:__imp_WindowsCreateString
0x18000ce35  inc     esi
0x18000ce37  mov     ebx, eax
0x18000ce39  cmp     esi, edi
0x18000ce3b  jb      short loc_18000CE08
0x18000ce3d  test    eax, eax
0x18000ce3f  js      short loc_18000CE55
0x18000ce41  mov     r9, rbp
0x18000ce44  mov     r8d, edi
0x18000ce47  mov     rdx, r15
0x18000ce4a  mov     rcx, r14
0x18000ce4d  call    cs:__imp_RoRegisterActivationFactories
0x18000ce53  mov     ebx, eax
0x18000ce55  mov     edi, r13d
0x18000ce58  test    esi, esi
0x18000ce5a  jz      short loc_18000CE75
0x18000ce5c  mov     ecx, edi
0x18000ce5e  mov     rcx, [r14+rcx*8]; string
0x18000ce62  call    cs:__imp_WindowsDeleteString
0x18000ce68  inc     edi
0x18000ce6a  cmp     edi, esi
0x18000ce6c  jb      short loc_18000CE5C
0x18000ce6e  jmp     short loc_18000CE75
0x18000ce70  mov     ebx, 8007000Eh
0x18000ce75  mov     rcx, r15; void *
0x18000ce78  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000ce7d  mov     rcx, r14; void *
0x18000ce80  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000ce85  mov     eax, ebx
0x18000ce87  add     rsp, 28h
0x18000ce8b  pop     r15
0x18000ce8d  pop     r14
0x18000ce8f  pop     r13
0x18000ce91  pop     r12
0x18000ce93  pop     rdi
0x18000ce94  pop     rsi
0x18000ce95  pop     rbp
0x18000ce96  pop     rbx
0x18000ce97  retn
```
