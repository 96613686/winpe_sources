# Windows::Globalization::Spelling::CHostProviderFactory::CreateSpellCheckProvider(ushort const *,ISpellCheckProvider * *)

- ea: `0x14000fef0`
- end: `0x14001003b`
- name: `?CreateSpellCheckProvider@CHostProviderFactory@Spelling@Globalization@Windows@@UEAAJPEBGPEAPEAUISpellCheckProvider@@@Z`
- size: `331`
- prototype: `__int64 __fastcall(Windows::Globalization::Spelling::CHostProviderFactory *__hidden this, const unsigned __int16 *, struct ISpellCheckProvider **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x14000f9b0`
- `0x14000fe00`
- `0x14000fef0`
- `0x140011e10`
- `0x140013010`

## pseudocode

```c
__int64 __fastcall Windows::Globalization::Spelling::CHostProviderFactory::CreateSpellCheckProvider(
        Windows::Globalization::Spelling::CHostProviderFactory *this,
        const unsigned __int16 *a2,
        struct ISpellCheckProvider **a3)
{
  const wchar_t *v4; // rbx
  int v5; // eax
  __int64 v6; // r8
  int v7; // edi
  __int64 v8; // rax
  int v9; // eax
  struct ISpellCheckProvider *v10; // rbx
  struct ISpellCheckProvider *v12; // [rsp+30h] [rbp-50h] BYREF
  __int64 v13; // [rsp+38h] [rbp-48h] BYREF
  char v14[16]; // [rsp+40h] [rbp-40h] BYREF
  const wchar_t *v15; // [rsp+50h] [rbp-30h]
  int v16; // [rsp+58h] [rbp-28h]
  int v17; // [rsp+5Ch] [rbp-24h]
  struct ISpellCheckProvider **v18; // [rsp+60h] [rbp-20h]
  __int64 v19; // [rsp+68h] [rbp-18h]

  v4 = a2;
  *a3 = 0;
  v13 = 0;
  v5 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, __int64 *))(**((_QWORD **)this + 4) + 40LL))(
         *((_QWORD *)this + 4),
         a2,
         &v13);
  v7 = v5;
  if ( v5 >= 0 )
  {
    v12 = 0;
    v7 = ATL::CComObject<Windows::Globalization::Spelling::CHostSpellCheckProvider>::CreateInstance(&v12);
    if ( v7 >= 0 )
    {
      v10 = v12;
      (*(void (__fastcall **)(struct ISpellCheckProvider *))(*(_QWORD *)v12 + 8LL))(v12);
      v7 = (*(__int64 (__fastcall **)(struct ISpellCheckProvider *, __int64 *))(*(_QWORD *)v10 + 104LL))(v10, &v13);
      if ( v7 < 0 )
      {
        if ( v10 )
          (*(void (__fastcall **)(struct ISpellCheckProvider *))(*(_QWORD *)v10 + 16LL))(v10);
      }
      else
      {
        *a3 = v10;
      }
    }
  }
  else if ( (Microsoft_Windows_Spellchecking_HostEnableBits & 1) != 0 )
  {
    LODWORD(v12) = v5;
    if ( v4 )
    {
      v8 = -1;
      do
        ++v8;
      while ( v4[v8] );
      v9 = 2 * v8 + 2;
    }
    else
    {
      v9 = 10;
    }
    if ( !v4 )
      v4 = L"NULL";
    v15 = v4;
    v16 = v9;
    v17 = 0;
    v18 = &v12;
    v19 = 4;
    McGenEventWrite_EventWriteTransfer(L"NULL", ThirdPartySpellCheckerInstantiationFailed, v6, 3, v14);
  }
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14000fef0  push    rbp
0x14000fef2  push    rbx
0x14000fef3  push    rsi
0x14000fef4  push    rdi
0x14000fef5  push    r14
0x14000fef7  mov     rbp, rsp
0x14000fefa  sub     rsp, 80h
0x14000ff01  mov     rax, cs:__security_cookie
0x14000ff08  xor     rax, rsp
0x14000ff0b  mov     [rbp+var_10], rax
0x14000ff0f  mov     rsi, r8
0x14000ff12  mov     rbx, rdx
0x14000ff15  xor     r14d, r14d
0x14000ff18  mov     [r8], r14
0x14000ff1b  mov     [rbp+var_48], r14
0x14000ff1f  mov     rcx, [rcx+20h]
0x14000ff23  mov     rax, [rcx]
0x14000ff26  lea     r8, [rbp+var_48]
0x14000ff2a  mov     rax, [rax+28h]
0x14000ff2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ff33  mov     edi, eax
0x14000ff35  test    eax, eax
0x14000ff37  jns     short loc_14000FFB0
0x14000ff39  test    cs:Microsoft_Windows_Spellchecking_HostEnableBits, 1
0x14000ff40  jz      loc_140010009
0x14000ff46  mov     dword ptr [rbp+var_50], eax
0x14000ff49  test    rbx, rbx
0x14000ff4c  jz      short loc_14000FF65
0x14000ff4e  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000ff52  inc     rax
0x14000ff55  cmp     [rbx+rax*2], r14w
0x14000ff5a  jnz     short loc_14000FF52
0x14000ff5c  lea     eax, ds:2[rax*2]
0x14000ff63  jmp     short loc_14000FF6A
0x14000ff65  mov     eax, 0Ah
0x14000ff6a  lea     rcx, aNull; "NULL"
0x14000ff71  test    rbx, rbx
0x14000ff74  cmovz   rbx, rcx
0x14000ff78  mov     [rbp+var_30], rbx
0x14000ff7c  mov     [rbp+var_28], eax
0x14000ff7f  mov     [rbp+var_24], r14d
0x14000ff83  lea     rax, [rbp+var_50]
0x14000ff87  mov     [rbp+var_20], rax
0x14000ff8b  mov     [rbp+var_18], 4
0x14000ff93  lea     rax, [rbp+var_40]
0x14000ff97  mov     [rsp+80h+var_60], rax
0x14000ff9c  mov     r9d, 3
0x14000ffa2  lea     rdx, ThirdPartySpellCheckerInstantiationFailed
0x14000ffa9  call    McGenEventWrite_EventWriteTransfer
0x14000ffae  jmp     short loc_140010009
0x14000ffb0  mov     [rbp+var_50], r14
0x14000ffb4  lea     rcx, [rbp+var_50]
0x14000ffb8  call    ?CreateInstance@?$CComObject@VCHostSpellCheckProvider@Spelling@Globalization@Windows@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<Windows::Globalization::Spelling::CHostSpellCheckProvider>::CreateInstance(ATL::CComObject<Windows::Globalization::Spelling::CHostSpellCheckProvider> * *)
0x14000ffbd  mov     edi, eax
0x14000ffbf  test    eax, eax
0x14000ffc1  js      short loc_140010009
0x14000ffc3  mov     rbx, [rbp+var_50]
0x14000ffc7  mov     rax, [rbx]
0x14000ffca  mov     rcx, rbx
0x14000ffcd  mov     rax, [rax+8]
0x14000ffd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ffd6  mov     rax, [rbx]
0x14000ffd9  lea     rdx, [rbp+var_48]
0x14000ffdd  mov     rcx, rbx
0x14000ffe0  mov     rax, [rax+68h]
0x14000ffe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ffe9  mov     edi, eax
0x14000ffeb  test    eax, eax
0x14000ffed  js      short loc_14000FFF4
0x14000ffef  mov     [rsi], rbx
0x14000fff2  jmp     short loc_140010009
0x14000fff4  test    rbx, rbx
0x14000fff7  jz      short loc_140010009
0x14000fff9  mov     rax, [rbx]
0x14000fffc  mov     rcx, rbx
0x14000ffff  mov     rax, [rax+10h]
0x140010003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010008  nop
0x140010009  mov     rcx, [rbp+var_48]
0x14001000d  test    rcx, rcx
0x140010010  jz      short loc_14001001F
0x140010012  mov     rax, [rcx]
0x140010015  mov     rax, [rax+10h]
0x140010019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001001e  nop
0x14001001f  mov     eax, edi
0x140010021  mov     rcx, [rbp+var_10]
0x140010025  xor     rcx, rsp; StackCookie
0x140010028  call    __security_check_cookie
0x14001002d  add     rsp, 80h
0x140010034  pop     r14
0x140010036  pop     rdi
0x140010037  pop     rsi
0x140010038  pop     rbx
0x140010039  pop     rbp
0x14001003a  retn
```
