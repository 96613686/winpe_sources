# Microsoft::WRL::Details::RegisterWinRTObject<2>(ushort const *,ushort const * *,_RO_REGISTRATION_COOKIE * *,uint)

- ea: `0x18003db4c`
- end: `0x18003dc4c`
- name: `??$RegisterWinRTObject@$01@Details@WRL@Microsoft@@YAJPEBGPEAPEBGPEAPEAU_RO_REGISTRATION_COOKIE@@I@Z`
- size: `256`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180041190`

## callees

- `0x180022a90`
- `0x180022afc`
- `0x18003db4c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003dbe3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003dbe3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003dc16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003dc16`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x18003dc01`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x18003dc01`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18003db4c  push    rbx
0x18003db4e  push    rbp
0x18003db4f  push    rsi
0x18003db50  push    rdi
0x18003db51  push    r12
0x18003db53  push    r13
0x18003db55  push    r14
0x18003db57  push    r15
0x18003db59  sub     rsp, 28h
0x18003db5d  mov     r12, rdx
0x18003db60  mov     edi, r9d
0x18003db63  mov     esi, 8
0x18003db68  mov     rbp, r8
0x18003db6b  mov     eax, esi
0x18003db6d  mul     rdi
0x18003db70  lea     r14, [rsi-9]
0x18003db74  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003db7b  cmovb   rax, r14
0x18003db7f  mov     rcx, rax; unsigned __int64
0x18003db82  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003db87  mov     r15, rax
0x18003db8a  mov     eax, esi
0x18003db8c  mul     rdi
0x18003db8f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003db96  cmovb   rax, r14
0x18003db9a  mov     rcx, rax; unsigned __int64
0x18003db9d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003dba2  xor     r13d, r13d
0x18003dba5  mov     r14, rax
0x18003dba8  test    r15, r15
0x18003dbab  jz      short loc_18003DC24
0x18003dbad  test    rax, rax
0x18003dbb0  jz      short loc_18003DC24
0x18003dbb2  mov     ebx, r13d
0x18003dbb5  mov     esi, r13d
0x18003dbb8  test    edi, edi
0x18003dbba  jz      short loc_18003DBF5
0x18003dbbc  test    ebx, ebx
0x18003dbbe  js      short loc_18003DC09
0x18003dbc0  mov     eax, esi
0x18003dbc2  lea     rcx, ??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)
0x18003dbc9  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18003dbcd  mov     [r15+rax*8], rcx
0x18003dbd1  mov     rcx, [r12+rax*8]; sourceString
0x18003dbd5  inc     rdx; length
0x18003dbd8  cmp     [rcx+rdx*2], r13w
0x18003dbdd  jnz     short loc_18003DBD5
0x18003dbdf  lea     r8, [r14+rax*8]; string
0x18003dbe3  call    cs:__imp_WindowsCreateString
0x18003dbe9  inc     esi
0x18003dbeb  mov     ebx, eax
0x18003dbed  cmp     esi, edi
0x18003dbef  jb      short loc_18003DBBC
0x18003dbf1  test    eax, eax
0x18003dbf3  js      short loc_18003DC09
0x18003dbf5  mov     r9, rbp
0x18003dbf8  mov     r8d, edi
0x18003dbfb  mov     rdx, r15
0x18003dbfe  mov     rcx, r14
0x18003dc01  call    cs:__imp_RoRegisterActivationFactories
0x18003dc07  mov     ebx, eax
0x18003dc09  mov     edi, r13d
0x18003dc0c  test    esi, esi
0x18003dc0e  jz      short loc_18003DC29
0x18003dc10  mov     ecx, edi
0x18003dc12  mov     rcx, [r14+rcx*8]; string
0x18003dc16  call    cs:__imp_WindowsDeleteString
0x18003dc1c  inc     edi
0x18003dc1e  cmp     edi, esi
0x18003dc20  jb      short loc_18003DC10
0x18003dc22  jmp     short loc_18003DC29
0x18003dc24  mov     ebx, 8007000Eh
0x18003dc29  mov     rcx, r15; void *
0x18003dc2c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003dc31  mov     rcx, r14; void *
0x18003dc34  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003dc39  mov     eax, ebx
0x18003dc3b  add     rsp, 28h
0x18003dc3f  pop     r15
0x18003dc41  pop     r14
0x18003dc43  pop     r13
0x18003dc45  pop     r12
0x18003dc47  pop     rdi
0x18003dc48  pop     rsi
0x18003dc49  pop     rbp
0x18003dc4a  pop     rbx
0x18003dc4b  retn
```
