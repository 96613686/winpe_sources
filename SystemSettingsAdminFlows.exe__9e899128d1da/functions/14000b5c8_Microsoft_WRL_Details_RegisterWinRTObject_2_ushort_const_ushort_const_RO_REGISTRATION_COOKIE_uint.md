# Microsoft::WRL::Details::RegisterWinRTObject<2>(ushort const *,ushort const * *,_RO_REGISTRATION_COOKIE * *,uint)

- ea: `0x14000b5c8`
- end: `0x14000b6c8`
- name: `??$RegisterWinRTObject@$01@Details@WRL@Microsoft@@YAJPEBGPEAPEBGPEAPEAU_RO_REGISTRATION_COOKIE@@I@Z`
- size: `256`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14001cd20`

## callees

- `0x140005f54`
- `0x140005f84`
- `0x14000b5c8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000b692`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000b692`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x14000b65f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x14000b65f`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x14000b67d`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x14000b67d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
  v8 = operator new[](v7, (const struct std::nothrow_t *)std::nothrow);
  v9 = 8 * v5;
  if ( !is_mul_ok(v5, 8u) )
    v9 = -1;
  v10 = (HSTRING *)operator new[](v9, (const struct std::nothrow_t *)std::nothrow);
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
0x14000b5c8  push    rbx
0x14000b5ca  push    rbp
0x14000b5cb  push    rsi
0x14000b5cc  push    rdi
0x14000b5cd  push    r12
0x14000b5cf  push    r13
0x14000b5d1  push    r14
0x14000b5d3  push    r15
0x14000b5d5  sub     rsp, 28h
0x14000b5d9  mov     r12, rdx
0x14000b5dc  mov     edi, r9d
0x14000b5df  mov     esi, 8
0x14000b5e4  mov     rbp, r8
0x14000b5e7  mov     eax, esi
0x14000b5e9  mul     rdi
0x14000b5ec  lea     r14, [rsi-9]
0x14000b5f0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000b5f7  cmovb   rax, r14
0x14000b5fb  mov     rcx, rax; unsigned __int64
0x14000b5fe  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14000b603  mov     r15, rax
0x14000b606  mov     eax, esi
0x14000b608  mul     rdi
0x14000b60b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000b612  cmovb   rax, r14
0x14000b616  mov     rcx, rax; unsigned __int64
0x14000b619  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14000b61e  xor     r13d, r13d
0x14000b621  mov     r14, rax
0x14000b624  test    r15, r15
0x14000b627  jz      short loc_14000B6A0
0x14000b629  test    rax, rax
0x14000b62c  jz      short loc_14000B6A0
0x14000b62e  mov     ebx, r13d
0x14000b631  mov     esi, r13d
0x14000b634  test    edi, edi
0x14000b636  jz      short loc_14000B671
0x14000b638  test    ebx, ebx
0x14000b63a  js      short loc_14000B685
0x14000b63c  mov     eax, esi
0x14000b63e  lea     rcx, ??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)
0x14000b645  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14000b649  mov     [r15+rax*8], rcx
0x14000b64d  mov     rcx, [r12+rax*8]; sourceString
0x14000b651  inc     rdx; length
0x14000b654  cmp     [rcx+rdx*2], r13w
0x14000b659  jnz     short loc_14000B651
0x14000b65b  lea     r8, [r14+rax*8]; string
0x14000b65f  call    cs:__imp_WindowsCreateString
0x14000b665  inc     esi
0x14000b667  mov     ebx, eax
0x14000b669  cmp     esi, edi
0x14000b66b  jb      short loc_14000B638
0x14000b66d  test    eax, eax
0x14000b66f  js      short loc_14000B685
0x14000b671  mov     r9, rbp
0x14000b674  mov     r8d, edi
0x14000b677  mov     rdx, r15
0x14000b67a  mov     rcx, r14
0x14000b67d  call    cs:__imp_RoRegisterActivationFactories
0x14000b683  mov     ebx, eax
0x14000b685  mov     edi, r13d
0x14000b688  test    esi, esi
0x14000b68a  jz      short loc_14000B6A5
0x14000b68c  mov     ecx, edi
0x14000b68e  mov     rcx, [r14+rcx*8]; string
0x14000b692  call    cs:__imp_WindowsDeleteString
0x14000b698  inc     edi
0x14000b69a  cmp     edi, esi
0x14000b69c  jb      short loc_14000B68C
0x14000b69e  jmp     short loc_14000B6A5
0x14000b6a0  mov     ebx, 8007000Eh
0x14000b6a5  mov     rcx, r15; void *
0x14000b6a8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000b6ad  mov     rcx, r14; void *
0x14000b6b0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000b6b5  mov     eax, ebx
0x14000b6b7  add     rsp, 28h
0x14000b6bb  pop     r15
0x14000b6bd  pop     r14
0x14000b6bf  pop     r13
0x14000b6c1  pop     r12
0x14000b6c3  pop     rdi
0x14000b6c4  pop     rsi
0x14000b6c5  pop     rbp
0x14000b6c6  pop     rbx
0x14000b6c7  retn
```
