# Microsoft::WRL::Details::RegisterWinRTObject<2>(ushort const *,ushort const * *,_RO_REGISTRATION_COOKIE * *,uint)

- ea: `0x18000a378`
- end: `0x18000a478`
- name: `??$RegisterWinRTObject@$01@Details@WRL@Microsoft@@YAJPEBGPEAPEBGPEAPEAU_RO_REGISTRATION_COOKIE@@I@Z`
- size: `256`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000d700`

## callees

- `0x1800021a0`
- `0x180002220`
- `0x18000a378`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a442`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a442`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000a40f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000a40f`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x18000a42d`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x18000a42d`

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
0x18000a378  push    rbx
0x18000a37a  push    rbp
0x18000a37b  push    rsi
0x18000a37c  push    rdi
0x18000a37d  push    r12
0x18000a37f  push    r13
0x18000a381  push    r14
0x18000a383  push    r15
0x18000a385  sub     rsp, 28h
0x18000a389  mov     r12, rdx
0x18000a38c  mov     edi, r9d
0x18000a38f  mov     esi, 8
0x18000a394  mov     rbp, r8
0x18000a397  mov     eax, esi
0x18000a399  mul     rdi
0x18000a39c  lea     r14, [rsi-9]
0x18000a3a0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a3a7  cmovb   rax, r14
0x18000a3ab  mov     rcx, rax; unsigned __int64
0x18000a3ae  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000a3b3  mov     r15, rax
0x18000a3b6  mov     eax, esi
0x18000a3b8  mul     rdi
0x18000a3bb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a3c2  cmovb   rax, r14
0x18000a3c6  mov     rcx, rax; unsigned __int64
0x18000a3c9  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000a3ce  xor     r13d, r13d
0x18000a3d1  mov     r14, rax
0x18000a3d4  test    r15, r15
0x18000a3d7  jz      short loc_18000A450
0x18000a3d9  test    rax, rax
0x18000a3dc  jz      short loc_18000A450
0x18000a3de  mov     ebx, r13d
0x18000a3e1  mov     esi, r13d
0x18000a3e4  test    edi, edi
0x18000a3e6  jz      short loc_18000A421
0x18000a3e8  test    ebx, ebx
0x18000a3ea  js      short loc_18000A435
0x18000a3ec  mov     eax, esi
0x18000a3ee  lea     rcx, ??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)
0x18000a3f5  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000a3f9  mov     [r15+rax*8], rcx
0x18000a3fd  mov     rcx, [r12+rax*8]; sourceString
0x18000a401  inc     rdx; length
0x18000a404  cmp     [rcx+rdx*2], r13w
0x18000a409  jnz     short loc_18000A401
0x18000a40b  lea     r8, [r14+rax*8]; string
0x18000a40f  call    cs:__imp_WindowsCreateString
0x18000a415  inc     esi
0x18000a417  mov     ebx, eax
0x18000a419  cmp     esi, edi
0x18000a41b  jb      short loc_18000A3E8
0x18000a41d  test    eax, eax
0x18000a41f  js      short loc_18000A435
0x18000a421  mov     r9, rbp
0x18000a424  mov     r8d, edi
0x18000a427  mov     rdx, r15
0x18000a42a  mov     rcx, r14
0x18000a42d  call    cs:__imp_RoRegisterActivationFactories
0x18000a433  mov     ebx, eax
0x18000a435  mov     edi, r13d
0x18000a438  test    esi, esi
0x18000a43a  jz      short loc_18000A455
0x18000a43c  mov     ecx, edi
0x18000a43e  mov     rcx, [r14+rcx*8]; string
0x18000a442  call    cs:__imp_WindowsDeleteString
0x18000a448  inc     edi
0x18000a44a  cmp     edi, esi
0x18000a44c  jb      short loc_18000A43C
0x18000a44e  jmp     short loc_18000A455
0x18000a450  mov     ebx, 8007000Eh
0x18000a455  mov     rcx, r15; void *
0x18000a458  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000a45d  mov     rcx, r14; void *
0x18000a460  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000a465  mov     eax, ebx
0x18000a467  add     rsp, 28h
0x18000a46b  pop     r15
0x18000a46d  pop     r14
0x18000a46f  pop     r13
0x18000a471  pop     r12
0x18000a473  pop     rdi
0x18000a474  pop     rsi
0x18000a475  pop     rbp
0x18000a476  pop     rbx
0x18000a477  retn
```
