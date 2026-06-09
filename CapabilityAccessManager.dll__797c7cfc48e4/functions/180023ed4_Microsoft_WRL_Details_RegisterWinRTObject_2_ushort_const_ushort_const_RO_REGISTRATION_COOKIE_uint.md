# Microsoft::WRL::Details::RegisterWinRTObject<2>(ushort const *,ushort const * *,_RO_REGISTRATION_COOKIE * *,uint)

- ea: `0x180023ed4`
- end: `0x180023fd4`
- name: `??$RegisterWinRTObject@$01@Details@WRL@Microsoft@@YAJPEBGPEAPEBGPEAPEAU_RO_REGISTRATION_COOKIE@@I@Z`
- size: `256`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180024440`

## callees

- `0x1800099d4`
- `0x180009a0c`
- `0x180023ed4`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x180023f89`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x180023f89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180023f6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180023f6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023f9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023f9e`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RegisterWinRTObject<2>(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  unsigned __int64 v5; // rdi
  unsigned __int64 v7; // rax
  _QWORD *v8; // r15
  unsigned __int64 v9; // rax
  HSTRING *v10; // rax
  HSTRING *v11; // r14
  int v12; // ebx
  unsigned int v13; // esi
  __int64 v14; // rdx
  const WCHAR *v15; // rcx
  HRESULT String; // eax
  unsigned int i; // edi

  v5 = a4;
  v7 = 8LL * a4;
  if ( !is_mul_ok(a4, 8u) )
    v7 = -1;
  v8 = operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
  v9 = 8 * v5;
  if ( !is_mul_ok(v5, 8u) )
    v9 = -1;
  v10 = (HSTRING *)operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v10;
  if ( v8 && v10 )
  {
    v12 = 0;
    v13 = 0;
    if ( (_DWORD)v5 )
    {
      while ( v12 >= 0 )
      {
        v14 = -1;
        v8[v13] = Microsoft::WRL::Details::ActivationFactoryCallback<2>;
        v15 = *(const WCHAR **)(a2 + 8LL * v13);
        do
          ++v14;
        while ( v15[v14] );
        String = WindowsCreateString(v15, v14, &v11[v13++]);
        v12 = String;
        if ( v13 >= (unsigned int)v5 )
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
      v12 = RoRegisterActivationFactories(v11, v8, (unsigned int)v5, a3);
    }
    for ( i = 0; i < v13; ++i )
      WindowsDeleteString(v11[i]);
  }
  else
  {
    v12 = -2147024882;
  }
  operator delete(v8);
  operator delete(v11);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180023ed4  push    rbx
0x180023ed6  push    rbp
0x180023ed7  push    rsi
0x180023ed8  push    rdi
0x180023ed9  push    r12
0x180023edb  push    r13
0x180023edd  push    r14
0x180023edf  push    r15
0x180023ee1  sub     rsp, 28h
0x180023ee5  mov     r12, rdx
0x180023ee8  mov     edi, r9d
0x180023eeb  mov     esi, 8
0x180023ef0  mov     rbp, r8
0x180023ef3  mov     eax, esi
0x180023ef5  mul     rdi
0x180023ef8  lea     r14, [rsi-9]
0x180023efc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180023f03  cmovb   rax, r14
0x180023f07  mov     rcx, rax; unsigned __int64
0x180023f0a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180023f0f  mov     r15, rax
0x180023f12  mov     eax, esi
0x180023f14  mul     rdi
0x180023f17  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180023f1e  cmovb   rax, r14
0x180023f22  mov     rcx, rax; unsigned __int64
0x180023f25  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180023f2a  xor     r13d, r13d
0x180023f2d  mov     r14, rax
0x180023f30  test    r15, r15
0x180023f33  jz      short loc_180023FAC
0x180023f35  test    rax, rax
0x180023f38  jz      short loc_180023FAC
0x180023f3a  mov     ebx, r13d
0x180023f3d  mov     esi, r13d
0x180023f40  test    edi, edi
0x180023f42  jz      short loc_180023F7D
0x180023f44  test    ebx, ebx
0x180023f46  js      short loc_180023F91
0x180023f48  mov     eax, esi
0x180023f4a  lea     rcx, ??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)
0x180023f51  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180023f55  mov     [r15+rax*8], rcx
0x180023f59  mov     rcx, [r12+rax*8]; sourceString
0x180023f5d  inc     rdx; length
0x180023f60  cmp     [rcx+rdx*2], r13w
0x180023f65  jnz     short loc_180023F5D
0x180023f67  lea     r8, [r14+rax*8]; string
0x180023f6b  call    cs:__imp_WindowsCreateString
0x180023f71  inc     esi
0x180023f73  mov     ebx, eax
0x180023f75  cmp     esi, edi
0x180023f77  jb      short loc_180023F44
0x180023f79  test    eax, eax
0x180023f7b  js      short loc_180023F91
0x180023f7d  mov     r9, rbp
0x180023f80  mov     r8d, edi
0x180023f83  mov     rdx, r15
0x180023f86  mov     rcx, r14
0x180023f89  call    cs:__imp_RoRegisterActivationFactories
0x180023f8f  mov     ebx, eax
0x180023f91  mov     edi, r13d
0x180023f94  test    esi, esi
0x180023f96  jz      short loc_180023FB1
0x180023f98  mov     ecx, edi
0x180023f9a  mov     rcx, [r14+rcx*8]; string
0x180023f9e  call    cs:__imp_WindowsDeleteString
0x180023fa4  inc     edi
0x180023fa6  cmp     edi, esi
0x180023fa8  jb      short loc_180023F98
0x180023faa  jmp     short loc_180023FB1
0x180023fac  mov     ebx, 8007000Eh
0x180023fb1  mov     rcx, r15; Block
0x180023fb4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180023fb9  mov     rcx, r14; Block
0x180023fbc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180023fc1  mov     eax, ebx
0x180023fc3  add     rsp, 28h
0x180023fc7  pop     r15
0x180023fc9  pop     r14
0x180023fcb  pop     r13
0x180023fcd  pop     r12
0x180023fcf  pop     rdi
0x180023fd0  pop     rsi
0x180023fd1  pop     rbp
0x180023fd2  pop     rbx
0x180023fd3  retn
```
