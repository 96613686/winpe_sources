# Microsoft::WRL::Details::RegisterWinRTObject<2>(ushort const *,ushort const * *,_RO_REGISTRATION_COOKIE * *,uint)

- ea: `0x180006fa0`
- end: `0x1800070a0`
- name: `??$RegisterWinRTObject@$01@Details@WRL@Microsoft@@YAJPEBGPEAPEBGPEAPEAU_RO_REGISTRATION_COOKIE@@I@Z`
- size: `256`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000a9c0`

## callees

- `0x180003c94`
- `0x1800040bc`
- `0x180006fa0`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x180007055`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x180007055`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000706a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000706a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180007037`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180007037`

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
0x180006fa0  push    rbx
0x180006fa2  push    rbp
0x180006fa3  push    rsi
0x180006fa4  push    rdi
0x180006fa5  push    r12
0x180006fa7  push    r13
0x180006fa9  push    r14
0x180006fab  push    r15
0x180006fad  sub     rsp, 28h
0x180006fb1  mov     r12, rdx
0x180006fb4  mov     edi, r9d
0x180006fb7  mov     esi, 8
0x180006fbc  mov     rbp, r8
0x180006fbf  mov     eax, esi
0x180006fc1  mul     rdi
0x180006fc4  lea     r14, [rsi-9]
0x180006fc8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006fcf  cmovb   rax, r14
0x180006fd3  mov     rcx, rax; unsigned __int64
0x180006fd6  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180006fdb  mov     r15, rax
0x180006fde  mov     eax, esi
0x180006fe0  mul     rdi
0x180006fe3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006fea  cmovb   rax, r14
0x180006fee  mov     rcx, rax; unsigned __int64
0x180006ff1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180006ff6  xor     r13d, r13d
0x180006ff9  mov     r14, rax
0x180006ffc  test    r15, r15
0x180006fff  jz      short loc_180007078
0x180007001  test    rax, rax
0x180007004  jz      short loc_180007078
0x180007006  mov     ebx, r13d
0x180007009  mov     esi, r13d
0x18000700c  test    edi, edi
0x18000700e  jz      short loc_180007049
0x180007010  test    ebx, ebx
0x180007012  js      short loc_18000705D
0x180007014  mov     eax, esi
0x180007016  lea     rcx, ??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)
0x18000701d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180007021  mov     [r15+rax*8], rcx
0x180007025  mov     rcx, [r12+rax*8]; sourceString
0x180007029  inc     rdx; length
0x18000702c  cmp     [rcx+rdx*2], r13w
0x180007031  jnz     short loc_180007029
0x180007033  lea     r8, [r14+rax*8]; string
0x180007037  call    cs:__imp_WindowsCreateString
0x18000703d  inc     esi
0x18000703f  mov     ebx, eax
0x180007041  cmp     esi, edi
0x180007043  jb      short loc_180007010
0x180007045  test    eax, eax
0x180007047  js      short loc_18000705D
0x180007049  mov     r9, rbp
0x18000704c  mov     r8d, edi
0x18000704f  mov     rdx, r15
0x180007052  mov     rcx, r14
0x180007055  call    cs:__imp_RoRegisterActivationFactories
0x18000705b  mov     ebx, eax
0x18000705d  mov     edi, r13d
0x180007060  test    esi, esi
0x180007062  jz      short loc_18000707D
0x180007064  mov     ecx, edi
0x180007066  mov     rcx, [r14+rcx*8]; string
0x18000706a  call    cs:__imp_WindowsDeleteString
0x180007070  inc     edi
0x180007072  cmp     edi, esi
0x180007074  jb      short loc_180007064
0x180007076  jmp     short loc_18000707D
0x180007078  mov     ebx, 8007000Eh
0x18000707d  mov     rcx, r15; void *
0x180007080  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007085  mov     rcx, r14; void *
0x180007088  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000708d  mov     eax, ebx
0x18000708f  add     rsp, 28h
0x180007093  pop     r15
0x180007095  pop     r14
0x180007097  pop     r13
0x180007099  pop     r12
0x18000709b  pop     rdi
0x18000709c  pop     rsi
0x18000709d  pop     rbp
0x18000709e  pop     rbx
0x18000709f  retn
```
