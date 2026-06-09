# Microsoft::WRL::Module<2,MultipleUseOutOfProcModule>::RegisterWinRTObject(ushort const *,ushort const * *,_RO_REGISTRATION_COOKIE * *,uint)

- ea: `0x14000bf90`
- end: `0x14000c096`
- name: `?RegisterWinRTObject@?$Module@$01VMultipleUseOutOfProcModule@@@WRL@Microsoft@@UEAAJPEBGPEAPEBGPEAPEAU_RO_REGISTRATION_COOKIE@@I@Z`
- size: `262`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140002600`
- `0x14000bf90`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x14000c074`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14000c07d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14000c074`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14000c07d`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x14000c049`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x14000c049`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x14000c02b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x14000c02b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000c05e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000c05e`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Module<2,MultipleUseOutOfProcModule>::RegisterWinRTObject(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5)
{
  unsigned __int64 v6; // rax
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

  v6 = 8LL * a5;
  if ( !is_mul_ok(a5, 8u) )
    v6 = -1;
  v8 = operator new[](v6, (const struct std::nothrow_t *)&std::nothrow);
  v9 = 8LL * a5;
  if ( !is_mul_ok(a5, 8u) )
    v9 = -1;
  v10 = (HSTRING *)operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v10;
  if ( v8 && v10 )
  {
    v12 = 0;
    v13 = 0;
    if ( a5 )
    {
      while ( v12 >= 0 )
      {
        v14 = -1;
        v8[v13] = Microsoft::WRL::Details::ActivationFactoryCallback<2>;
        v15 = *(const WCHAR **)(a3 + 8LL * v13);
        do
          ++v14;
        while ( v15[v14] );
        String = WindowsCreateString(v15, v14, &v11[v13++]);
        v12 = String;
        if ( v13 >= a5 )
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
      v12 = RoRegisterActivationFactories(v11, v8, a5, a4);
    }
    for ( i = 0; i < v13; ++i )
      WindowsDeleteString(v11[i]);
  }
  else
  {
    v12 = -2147024882;
  }
  operator delete[](v8);
  operator delete[](v11);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14000bf90  push    rbx
0x14000bf92  push    rbp
0x14000bf93  push    rsi
0x14000bf94  push    rdi
0x14000bf95  push    r12
0x14000bf97  push    r13
0x14000bf99  push    r14
0x14000bf9b  push    r15
0x14000bf9d  sub     rsp, 28h
0x14000bfa1  mov     edi, [rsp+68h+arg_20]
0x14000bfa8  mov     esi, 8
0x14000bfad  mov     eax, esi
0x14000bfaf  mov     rbp, r9
0x14000bfb2  mul     rdi
0x14000bfb5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000bfbc  mov     r12, r8
0x14000bfbf  lea     r14, [rsi-9]
0x14000bfc3  cmovb   rax, r14
0x14000bfc7  mov     rcx, rax; unsigned __int64
0x14000bfca  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14000bfcf  mov     r15, rax
0x14000bfd2  mov     eax, esi
0x14000bfd4  mul     rdi
0x14000bfd7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000bfde  cmovb   rax, r14
0x14000bfe2  mov     rcx, rax; unsigned __int64
0x14000bfe5  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14000bfea  xor     r13d, r13d
0x14000bfed  mov     r14, rax
0x14000bff0  test    r15, r15
0x14000bff3  jz      short loc_14000C06C
0x14000bff5  test    rax, rax
0x14000bff8  jz      short loc_14000C06C
0x14000bffa  mov     ebx, r13d
0x14000bffd  mov     esi, r13d
0x14000c000  test    edi, edi
0x14000c002  jz      short loc_14000C03D
0x14000c004  test    ebx, ebx
0x14000c006  js      short loc_14000C051
0x14000c008  mov     eax, esi
0x14000c00a  lea     rcx, ??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)
0x14000c011  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14000c015  mov     [r15+rax*8], rcx
0x14000c019  mov     rcx, [r12+rax*8]; sourceString
0x14000c01d  inc     rdx; length
0x14000c020  cmp     [rcx+rdx*2], r13w
0x14000c025  jnz     short loc_14000C01D
0x14000c027  lea     r8, [r14+rax*8]; string
0x14000c02b  call    cs:__imp_WindowsCreateString
0x14000c031  inc     esi
0x14000c033  mov     ebx, eax
0x14000c035  cmp     esi, edi
0x14000c037  jb      short loc_14000C004
0x14000c039  test    eax, eax
0x14000c03b  js      short loc_14000C051
0x14000c03d  mov     r9, rbp
0x14000c040  mov     r8d, edi
0x14000c043  mov     rdx, r15
0x14000c046  mov     rcx, r14
0x14000c049  call    cs:__imp_RoRegisterActivationFactories
0x14000c04f  mov     ebx, eax
0x14000c051  mov     edi, r13d
0x14000c054  test    esi, esi
0x14000c056  jz      short loc_14000C071
0x14000c058  mov     ecx, edi
0x14000c05a  mov     rcx, [r14+rcx*8]; string
0x14000c05e  call    cs:__imp_WindowsDeleteString
0x14000c064  inc     edi
0x14000c066  cmp     edi, esi
0x14000c068  jb      short loc_14000C058
0x14000c06a  jmp     short loc_14000C071
0x14000c06c  mov     ebx, 8007000Eh
0x14000c071  mov     rcx, r15
0x14000c074  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x14000c07a  mov     rcx, r14
0x14000c07d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x14000c083  mov     eax, ebx
0x14000c085  add     rsp, 28h
0x14000c089  pop     r15
0x14000c08b  pop     r14
0x14000c08d  pop     r13
0x14000c08f  pop     r12
0x14000c091  pop     rdi
0x14000c092  pop     rsi
0x14000c093  pop     rbp
0x14000c094  pop     rbx
0x14000c095  retn
```
