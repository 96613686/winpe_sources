# Microsoft::WRL::Details::RegisterWinRTObject<2>(ushort const *,ushort const * *,_RO_REGISTRATION_COOKIE * *,uint)

- ea: `0x140006484`
- end: `0x140006584`
- name: `??$RegisterWinRTObject@$01@Details@WRL@Microsoft@@YAJPEBGPEAPEBGPEAPEAU_RO_REGISTRATION_COOKIE@@I@Z`
- size: `256`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140012a60`

## callees

- `0x1400032e4`
- `0x1400038d8`
- `0x140006484`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000654e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000654e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x14000651b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x14000651b`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x140006539`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x140006539`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RegisterWinRTObject<2>(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  unsigned __int64 v5; // rdi
  unsigned __int64 v7; // rax
  _QWORD *v8; // r15
  unsigned __int64 v9; // rax
  HSTRING *v10; // rax
  unsigned __int64 v11; // rdx
  HSTRING *v12; // r14
  int v13; // ebx
  unsigned int v14; // esi
  __int64 v15; // rdx
  const WCHAR *v16; // rcx
  HRESULT String; // eax
  unsigned int i; // edi
  unsigned __int64 v19; // rdx

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
0x140006484  push    rbx
0x140006486  push    rbp
0x140006487  push    rsi
0x140006488  push    rdi
0x140006489  push    r12
0x14000648b  push    r13
0x14000648d  push    r14
0x14000648f  push    r15
0x140006491  sub     rsp, 28h
0x140006495  mov     r12, rdx
0x140006498  mov     edi, r9d
0x14000649b  mov     esi, 8
0x1400064a0  mov     rbp, r8
0x1400064a3  mov     eax, esi
0x1400064a5  mul     rdi
0x1400064a8  lea     r14, [rsi-9]
0x1400064ac  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400064b3  cmovb   rax, r14
0x1400064b7  mov     rcx, rax; unsigned __int64
0x1400064ba  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1400064bf  mov     r15, rax
0x1400064c2  mov     eax, esi
0x1400064c4  mul     rdi
0x1400064c7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400064ce  cmovb   rax, r14
0x1400064d2  mov     rcx, rax; unsigned __int64
0x1400064d5  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1400064da  xor     r13d, r13d
0x1400064dd  mov     r14, rax
0x1400064e0  test    r15, r15
0x1400064e3  jz      short loc_14000655C
0x1400064e5  test    rax, rax
0x1400064e8  jz      short loc_14000655C
0x1400064ea  mov     ebx, r13d
0x1400064ed  mov     esi, r13d
0x1400064f0  test    edi, edi
0x1400064f2  jz      short loc_14000652D
0x1400064f4  test    ebx, ebx
0x1400064f6  js      short loc_140006541
0x1400064f8  mov     eax, esi
0x1400064fa  lea     rcx, ??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)
0x140006501  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140006505  mov     [r15+rax*8], rcx
0x140006509  mov     rcx, [r12+rax*8]; sourceString
0x14000650d  inc     rdx; length
0x140006510  cmp     [rcx+rdx*2], r13w
0x140006515  jnz     short loc_14000650D
0x140006517  lea     r8, [r14+rax*8]; string
0x14000651b  call    cs:__imp_WindowsCreateString
0x140006521  inc     esi
0x140006523  mov     ebx, eax
0x140006525  cmp     esi, edi
0x140006527  jb      short loc_1400064F4
0x140006529  test    eax, eax
0x14000652b  js      short loc_140006541
0x14000652d  mov     r9, rbp
0x140006530  mov     r8d, edi
0x140006533  mov     rdx, r15
0x140006536  mov     rcx, r14
0x140006539  call    cs:__imp_RoRegisterActivationFactories
0x14000653f  mov     ebx, eax
0x140006541  mov     edi, r13d
0x140006544  test    esi, esi
0x140006546  jz      short loc_140006561
0x140006548  mov     ecx, edi
0x14000654a  mov     rcx, [r14+rcx*8]; string
0x14000654e  call    cs:__imp_WindowsDeleteString
0x140006554  inc     edi
0x140006556  cmp     edi, esi
0x140006558  jb      short loc_140006548
0x14000655a  jmp     short loc_140006561
0x14000655c  mov     ebx, 8007000Eh
0x140006561  mov     rcx, r15; void *
0x140006564  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140006569  mov     rcx, r14; void *
0x14000656c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140006571  mov     eax, ebx
0x140006573  add     rsp, 28h
0x140006577  pop     r15
0x140006579  pop     r14
0x14000657b  pop     r13
0x14000657d  pop     r12
0x14000657f  pop     rdi
0x140006580  pop     rsi
0x140006581  pop     rbp
0x140006582  pop     rbx
0x140006583  retn
```
