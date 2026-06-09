# CComAuthInfo2::SetComputerNameW(ushort const *)

- ea: `0x18001c398`
- end: `0x18001c4af`
- name: `?SetComputerNameW@CComAuthInfo2@@IEAAXPEBG@Z`
- size: `279`
- prototype: `void(CComAuthInfo2 *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001bf30`

## callees

- `0x180004284`
- `0x18001c398`
- `0x18001d66a`
- `0x18001d68e`
- `0x18001d6c0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001c3f2`
- `msvcrt!_wcsicmp` at `0x18001c43f`
- `msvcrt!_wcsicmp` at `0x18001c3f2`
- `msvcrt!_wcsicmp` at `0x18001c43f`
- `KERNEL32!GetComputerNameW` at `0x18001c425`
- `KERNEL32!GetComputerNameW` at `0x18001c471`
- `KERNEL32!GetComputerNameW` at `0x18001c425`
- `KERNEL32!GetComputerNameW` at `0x18001c471`

## pseudocode

```c
void __fastcall CComAuthInfo2::SetComputerNameW(CComAuthInfo2 *this, const unsigned __int16 *a2)
{
  bool v4; // zf
  const wchar_t *v5; // rdi
  const wchar_t *v6; // rdx
  const wchar_t *v7; // rdx
  int v8; // eax
  DWORD nSize; // [rsp+20h] [rbp-268h] BYREF
  WCHAR Buffer[20]; // [rsp+28h] [rbp-260h] BYREF
  WCHAR v11[264]; // [rsp+50h] [rbp-238h] BYREF

  if ( !a2 || !*a2 )
  {
    memset_0(v11, 0, 0x20Au);
    nSize = 260;
    GetComputerNameW(v11, &nSize);
    ATL::CComBSTR::operator=(this, v11);
LABEL_15:
    v8 = 1;
    goto LABEL_16;
  }
  ATL::CComBSTR::operator=(this, a2);
  v4 = *a2 == 92;
  v5 = a2 + 2;
  v6 = a2 + 2;
  nSize = 16;
  if ( !v4 )
    v6 = a2;
  if ( !_wcsicmp(L"localhost", v6) )
    goto LABEL_15;
  v7 = a2 + 2;
  if ( *a2 != 92 )
    v7 = a2;
  if ( !wcscmp_0(L"127.0.0.1", v7) )
    goto LABEL_15;
  if ( GetComputerNameW(Buffer, &nSize) )
  {
    if ( *a2 != 92 )
      v5 = a2;
    if ( !_wcsicmp(Buffer, v5) )
      goto LABEL_15;
  }
  v8 = 0;
LABEL_16:
  *((_DWORD *)this + 6) = v8;
}

```

## disassembly

```asm
0x18001c398  mov     [rsp+arg_10], rbx
0x18001c39d  push    rbp
0x18001c39e  push    rsi
0x18001c39f  push    rdi
0x18001c3a0  sub     rsp, 270h
0x18001c3a7  mov     rax, cs:__security_cookie
0x18001c3ae  xor     rax, rsp
0x18001c3b1  mov     [rsp+288h+var_28], rax
0x18001c3b9  xor     ebp, ebp
0x18001c3bb  mov     rbx, rdx
0x18001c3be  mov     rsi, rcx
0x18001c3c1  test    rdx, rdx
0x18001c3c4  jz      loc_18001C44D
0x18001c3ca  cmp     [rdx], bp
0x18001c3cd  jz      short loc_18001C44D
0x18001c3cf  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18001c3d4  cmp     word ptr [rbx], 5Ch ; '\'
0x18001c3d8  lea     rdi, [rbx+4]
0x18001c3dc  mov     rdx, rdi
0x18001c3df  mov     [rsp+288h+nSize], 10h
0x18001c3e7  cmovnz  rdx, rbx; String2
0x18001c3eb  lea     rcx, aLocalhost_0; "localhost"
0x18001c3f2  call    cs:__imp__wcsicmp
0x18001c3f8  test    eax, eax
0x18001c3fa  jz      loc_18001C484
0x18001c400  cmp     word ptr [rbx], 5Ch ; '\'
0x18001c404  lea     rcx, a127001; "127.0.0.1"
0x18001c40b  mov     rdx, rdi
0x18001c40e  cmovnz  rdx, rbx; String2
0x18001c412  call    wcscmp_0
0x18001c417  test    eax, eax
0x18001c419  jz      short loc_18001C484
0x18001c41b  lea     rdx, [rsp+288h+nSize]; nSize
0x18001c420  lea     rcx, [rsp+288h+Buffer]; lpBuffer
0x18001c425  call    cs:__imp_GetComputerNameW
0x18001c42b  test    eax, eax
0x18001c42d  jz      short loc_18001C449
0x18001c42f  cmp     word ptr [rbx], 5Ch ; '\'
0x18001c433  lea     rcx, [rsp+288h+Buffer]; String1
0x18001c438  cmovnz  rdi, rbx
0x18001c43c  mov     rdx, rdi; String2
0x18001c43f  call    cs:__imp__wcsicmp
0x18001c445  test    eax, eax
0x18001c447  jz      short loc_18001C484
0x18001c449  mov     eax, ebp
0x18001c44b  jmp     short loc_18001C489
0x18001c44d  xor     edx, edx; Val
0x18001c44f  lea     rcx, [rsp+288h+var_238]; void *
0x18001c454  mov     r8d, 20Ah; Size
0x18001c45a  call    memset_0
0x18001c45f  lea     rdx, [rsp+288h+nSize]; nSize
0x18001c464  mov     [rsp+288h+nSize], 104h
0x18001c46c  lea     rcx, [rsp+288h+var_238]; lpBuffer
0x18001c471  call    cs:__imp_GetComputerNameW
0x18001c477  lea     rdx, [rsp+288h+var_238]
0x18001c47c  mov     rcx, rsi
0x18001c47f  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18001c484  mov     eax, 1
0x18001c489  mov     [rsi+18h], eax
0x18001c48c  mov     rcx, [rsp+288h+var_28]
0x18001c494  xor     rcx, rsp; StackCookie
0x18001c497  call    __security_check_cookie
0x18001c49c  mov     rbx, [rsp+288h+arg_10]
0x18001c4a4  add     rsp, 270h
0x18001c4ab  pop     rdi
0x18001c4ac  pop     rsi
0x18001c4ad  pop     rbp
0x18001c4ae  retn
```
