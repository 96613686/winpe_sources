# Microsoft::WRL::Details::RegisterWinRTObject<2>(ushort const *,ushort const * *,_RO_REGISTRATION_COOKIE * *,uint)

- ea: `0x180002dd0`
- end: `0x180002ed0`
- name: `??$RegisterWinRTObject@$01@Details@WRL@Microsoft@@YAJPEBGPEAPEBGPEAPEAU_RO_REGISTRATION_COOKIE@@I@Z`
- size: `256`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800064b0`

## callees

- `0x180001644`
- `0x180001a40`
- `0x180002dd0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002e9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002e9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180002e67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180002e67`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x180002e85`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x180002e85`

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
0x180002dd0  push    rbx
0x180002dd2  push    rbp
0x180002dd3  push    rsi
0x180002dd4  push    rdi
0x180002dd5  push    r12
0x180002dd7  push    r13
0x180002dd9  push    r14
0x180002ddb  push    r15
0x180002ddd  sub     rsp, 28h
0x180002de1  mov     r12, rdx
0x180002de4  mov     edi, r9d
0x180002de7  mov     esi, 8
0x180002dec  mov     rbp, r8
0x180002def  mov     eax, esi
0x180002df1  mul     rdi
0x180002df4  lea     r14, [rsi-9]
0x180002df8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180002dff  cmovb   rax, r14
0x180002e03  mov     rcx, rax; unsigned __int64
0x180002e06  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180002e0b  mov     r15, rax
0x180002e0e  mov     eax, esi
0x180002e10  mul     rdi
0x180002e13  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180002e1a  cmovb   rax, r14
0x180002e1e  mov     rcx, rax; unsigned __int64
0x180002e21  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180002e26  xor     r13d, r13d
0x180002e29  mov     r14, rax
0x180002e2c  test    r15, r15
0x180002e2f  jz      short loc_180002EA8
0x180002e31  test    rax, rax
0x180002e34  jz      short loc_180002EA8
0x180002e36  mov     ebx, r13d
0x180002e39  mov     esi, r13d
0x180002e3c  test    edi, edi
0x180002e3e  jz      short loc_180002E79
0x180002e40  test    ebx, ebx
0x180002e42  js      short loc_180002E8D
0x180002e44  mov     eax, esi
0x180002e46  lea     rcx, ??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)
0x180002e4d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180002e51  mov     [r15+rax*8], rcx
0x180002e55  mov     rcx, [r12+rax*8]; sourceString
0x180002e59  inc     rdx; length
0x180002e5c  cmp     [rcx+rdx*2], r13w
0x180002e61  jnz     short loc_180002E59
0x180002e63  lea     r8, [r14+rax*8]; string
0x180002e67  call    cs:__imp_WindowsCreateString
0x180002e6d  inc     esi
0x180002e6f  mov     ebx, eax
0x180002e71  cmp     esi, edi
0x180002e73  jb      short loc_180002E40
0x180002e75  test    eax, eax
0x180002e77  js      short loc_180002E8D
0x180002e79  mov     r9, rbp
0x180002e7c  mov     r8d, edi
0x180002e7f  mov     rdx, r15
0x180002e82  mov     rcx, r14
0x180002e85  call    cs:__imp_RoRegisterActivationFactories
0x180002e8b  mov     ebx, eax
0x180002e8d  mov     edi, r13d
0x180002e90  test    esi, esi
0x180002e92  jz      short loc_180002EAD
0x180002e94  mov     ecx, edi
0x180002e96  mov     rcx, [r14+rcx*8]; string
0x180002e9a  call    cs:__imp_WindowsDeleteString
0x180002ea0  inc     edi
0x180002ea2  cmp     edi, esi
0x180002ea4  jb      short loc_180002E94
0x180002ea6  jmp     short loc_180002EAD
0x180002ea8  mov     ebx, 8007000Eh
0x180002ead  mov     rcx, r15; void *
0x180002eb0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002eb5  mov     rcx, r14; void *
0x180002eb8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002ebd  mov     eax, ebx
0x180002ebf  add     rsp, 28h
0x180002ec3  pop     r15
0x180002ec5  pop     r14
0x180002ec7  pop     r13
0x180002ec9  pop     r12
0x180002ecb  pop     rdi
0x180002ecc  pop     rsi
0x180002ecd  pop     rbp
0x180002ece  pop     rbx
0x180002ecf  retn
```
