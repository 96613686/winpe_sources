# Microsoft::WRL::Details::RegisterWinRTObject<2>(ushort const *,ushort const * *,_RO_REGISTRATION_COOKIE * *,uint)

- ea: `0x18000cc44`
- end: `0x18000cd44`
- name: `??$RegisterWinRTObject@$01@Details@WRL@Microsoft@@YAJPEBGPEAPEBGPEAPEAU_RO_REGISTRATION_COOKIE@@I@Z`
- size: `256`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800114d0`

## callees

- `0x1800051fc`
- `0x1800052a4`
- `0x18000cc44`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000cd0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000cd0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000ccdb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000ccdb`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x18000ccf9`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x18000ccf9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x18000cc44  push    rbx
0x18000cc46  push    rbp
0x18000cc47  push    rsi
0x18000cc48  push    rdi
0x18000cc49  push    r12
0x18000cc4b  push    r13
0x18000cc4d  push    r14
0x18000cc4f  push    r15
0x18000cc51  sub     rsp, 28h
0x18000cc55  mov     r12, rdx
0x18000cc58  mov     edi, r9d
0x18000cc5b  mov     esi, 8
0x18000cc60  mov     rbp, r8
0x18000cc63  mov     eax, esi
0x18000cc65  mul     rdi
0x18000cc68  lea     r14, [rsi-9]
0x18000cc6c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000cc73  cmovb   rax, r14
0x18000cc77  mov     rcx, rax; unsigned __int64
0x18000cc7a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000cc7f  mov     r15, rax
0x18000cc82  mov     eax, esi
0x18000cc84  mul     rdi
0x18000cc87  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000cc8e  cmovb   rax, r14
0x18000cc92  mov     rcx, rax; unsigned __int64
0x18000cc95  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000cc9a  xor     r13d, r13d
0x18000cc9d  mov     r14, rax
0x18000cca0  test    r15, r15
0x18000cca3  jz      short loc_18000CD1C
0x18000cca5  test    rax, rax
0x18000cca8  jz      short loc_18000CD1C
0x18000ccaa  mov     ebx, r13d
0x18000ccad  mov     esi, r13d
0x18000ccb0  test    edi, edi
0x18000ccb2  jz      short loc_18000CCED
0x18000ccb4  test    ebx, ebx
0x18000ccb6  js      short loc_18000CD01
0x18000ccb8  mov     eax, esi
0x18000ccba  lea     rcx, ??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)
0x18000ccc1  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000ccc5  mov     [r15+rax*8], rcx
0x18000ccc9  mov     rcx, [r12+rax*8]; sourceString
0x18000cccd  inc     rdx; length
0x18000ccd0  cmp     [rcx+rdx*2], r13w
0x18000ccd5  jnz     short loc_18000CCCD
0x18000ccd7  lea     r8, [r14+rax*8]; string
0x18000ccdb  call    cs:__imp_WindowsCreateString
0x18000cce1  inc     esi
0x18000cce3  mov     ebx, eax
0x18000cce5  cmp     esi, edi
0x18000cce7  jb      short loc_18000CCB4
0x18000cce9  test    eax, eax
0x18000cceb  js      short loc_18000CD01
0x18000cced  mov     r9, rbp
0x18000ccf0  mov     r8d, edi
0x18000ccf3  mov     rdx, r15
0x18000ccf6  mov     rcx, r14
0x18000ccf9  call    cs:__imp_RoRegisterActivationFactories
0x18000ccff  mov     ebx, eax
0x18000cd01  mov     edi, r13d
0x18000cd04  test    esi, esi
0x18000cd06  jz      short loc_18000CD21
0x18000cd08  mov     ecx, edi
0x18000cd0a  mov     rcx, [r14+rcx*8]; string
0x18000cd0e  call    cs:__imp_WindowsDeleteString
0x18000cd14  inc     edi
0x18000cd16  cmp     edi, esi
0x18000cd18  jb      short loc_18000CD08
0x18000cd1a  jmp     short loc_18000CD21
0x18000cd1c  mov     ebx, 8007000Eh
0x18000cd21  mov     rcx, r15; Block
0x18000cd24  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000cd29  mov     rcx, r14; Block
0x18000cd2c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000cd31  mov     eax, ebx
0x18000cd33  add     rsp, 28h
0x18000cd37  pop     r15
0x18000cd39  pop     r14
0x18000cd3b  pop     r13
0x18000cd3d  pop     r12
0x18000cd3f  pop     rdi
0x18000cd40  pop     rsi
0x18000cd41  pop     rbp
0x18000cd42  pop     rbx
0x18000cd43  retn
```
