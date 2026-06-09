# Microsoft::WRL::Details::RegisterWinRTObject<2>(ushort const *,ushort const * *,_RO_REGISTRATION_COOKIE * *,uint)

- ea: `0x18000d14c`
- end: `0x18000d267`
- name: `??$RegisterWinRTObject@$01@Details@WRL@Microsoft@@YAJPEBGPEAPEBGPEAPEAU_RO_REGISTRATION_COOKIE@@I@Z`
- size: `283`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180011ad0`

## callees

- `0x18000535c`
- `0x180005404`
- `0x18000d14c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d22a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d22a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000d1eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000d1eb`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x18000d20f`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x18000d20f`

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
0x18000d14c  push    rbx
0x18000d14e  push    rbp
0x18000d14f  push    rsi
0x18000d150  push    rdi
0x18000d151  push    r12
0x18000d153  push    r13
0x18000d155  push    r14
0x18000d157  push    r15
0x18000d159  sub     rsp, 28h
0x18000d15d  mov     r12, rdx
0x18000d160  mov     edi, r9d
0x18000d163  mov     esi, 8
0x18000d168  mov     rbp, r8
0x18000d16b  mov     eax, esi
0x18000d16d  mul     rdi
0x18000d170  lea     r14, [rsi-9]
0x18000d174  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d17b  cmovb   rax, r14
0x18000d17f  mov     rcx, rax; unsigned __int64
0x18000d182  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000d187  mov     r15, rax
0x18000d18a  mov     eax, esi
0x18000d18c  mul     rdi
0x18000d18f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d196  cmovb   rax, r14
0x18000d19a  mov     rcx, rax; unsigned __int64
0x18000d19d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000d1a2  xor     r13d, r13d
0x18000d1a5  mov     r14, rax
0x18000d1a8  test    r15, r15
0x18000d1ab  jz      loc_18000D23E
0x18000d1b1  test    rax, rax
0x18000d1b4  jz      loc_18000D23E
0x18000d1ba  mov     ebx, r13d
0x18000d1bd  mov     esi, r13d
0x18000d1c0  test    edi, edi
0x18000d1c2  jz      short loc_18000D203
0x18000d1c4  test    ebx, ebx
0x18000d1c6  js      short loc_18000D21D
0x18000d1c8  mov     eax, esi
0x18000d1ca  lea     rcx, ??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)
0x18000d1d1  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000d1d5  mov     [r15+rax*8], rcx
0x18000d1d9  mov     rcx, [r12+rax*8]; sourceString
0x18000d1dd  inc     rdx; length
0x18000d1e0  cmp     [rcx+rdx*2], r13w
0x18000d1e5  jnz     short loc_18000D1DD
0x18000d1e7  lea     r8, [r14+rax*8]; string
0x18000d1eb  call    cs:__imp_WindowsCreateString
0x18000d1f2  nop     dword ptr [rax+rax+00h]
0x18000d1f7  inc     esi
0x18000d1f9  mov     ebx, eax
0x18000d1fb  cmp     esi, edi
0x18000d1fd  jb      short loc_18000D1C4
0x18000d1ff  test    eax, eax
0x18000d201  js      short loc_18000D21D
0x18000d203  mov     r9, rbp
0x18000d206  mov     r8d, edi
0x18000d209  mov     rdx, r15
0x18000d20c  mov     rcx, r14
0x18000d20f  call    cs:__imp_RoRegisterActivationFactories
0x18000d216  nop     dword ptr [rax+rax+00h]
0x18000d21b  mov     ebx, eax
0x18000d21d  mov     edi, r13d
0x18000d220  test    esi, esi
0x18000d222  jz      short loc_18000D243
0x18000d224  mov     ecx, edi
0x18000d226  mov     rcx, [r14+rcx*8]; string
0x18000d22a  call    cs:__imp_WindowsDeleteString
0x18000d231  nop     dword ptr [rax+rax+00h]
0x18000d236  inc     edi
0x18000d238  cmp     edi, esi
0x18000d23a  jb      short loc_18000D224
0x18000d23c  jmp     short loc_18000D243
0x18000d23e  mov     ebx, 8007000Eh
0x18000d243  mov     rcx, r15; Block
0x18000d246  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000d24b  mov     rcx, r14; Block
0x18000d24e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000d253  mov     eax, ebx
0x18000d255  add     rsp, 28h
0x18000d259  pop     r15
0x18000d25b  pop     r14
0x18000d25d  pop     r13
0x18000d25f  pop     r12
0x18000d261  pop     rdi
0x18000d262  pop     rsi
0x18000d263  pop     rbp
0x18000d264  pop     rbx
0x18000d265  retn
```
