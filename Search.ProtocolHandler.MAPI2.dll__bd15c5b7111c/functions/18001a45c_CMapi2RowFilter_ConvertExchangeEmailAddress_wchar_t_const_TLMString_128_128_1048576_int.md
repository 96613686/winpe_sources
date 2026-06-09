# CMapi2RowFilter::ConvertExchangeEmailAddress(wchar_t const *,TLMString<128,128,1048576> &,int *)

- ea: `0x18001a45c`
- end: `0x18001a575`
- name: `?ConvertExchangeEmailAddress@CMapi2RowFilter@@AEAAHPEB_WAEAV?$TLMString@$0IA@$0IA@$0BAAAAA@@@PEAH@Z`
- size: `281`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, __int64, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001e700`
- `0x180020a48`

## callees

- `0x180002300`
- `0x180014448`
- `0x18001a45c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswdigit` at `0x18001a52a`
- `api-ms-win-crt-private-l1-1-0!_o_iswdigit` at `0x18001a52a`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18001a4e0`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18001a4e0`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001a498`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001a498`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001a511`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001a511`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CMapi2RowFilter::ConvertExchangeEmailAddress(__int64 a1, const wchar_t *a2, __int64 a3, int *a4)
{
  unsigned int v7; // r15d
  int v8; // esi
  wchar_t *v9; // rbx
  __int64 v10; // rdi
  unsigned __int64 v11; // rax
  const wchar_t *v12; // rbx
  const wchar_t *v13; // rdx
  wchar_t *EndPtr; // [rsp+20h] [rbp-58h] BYREF
  GUID pclsid; // [rsp+28h] [rbp-50h] BYREF

  v7 = 0;
  v8 = 0;
  v9 = wcsrchr(a2, 0x3Du);
  if ( v9 )
  {
    v10 = -1;
    v11 = -1;
    do
      ++v11;
    while ( v9[v11] );
    if ( v11 > 1 )
    {
      EndPtr = 0;
      v12 = v9 + 1;
      pclsid = 0;
      wcstoul(v12, &EndPtr, 10);
      if ( EndPtr && !*EndPtr || *v12 == 123 && CLSIDFromString(v12, &pclsid) >= 0 )
      {
        v8 = 1;
      }
      else
      {
        do
          ++v10;
        while ( v12[v10] );
        if ( !(unsigned int)_o_iswdigit(v12[v10 - 1]) )
        {
          v7 = 1;
          goto LABEL_9;
        }
      }
      v12 = a2;
LABEL_9:
      v13 = v12;
      goto LABEL_16;
    }
  }
  v13 = a2;
LABEL_16:
  CLMString::operator=(a3, v13);
  if ( a4 )
    *a4 = v8;
  return v7;
}

```

## disassembly

```asm
0x18001a45c  mov     [rsp+arg_0], rbx
0x18001a461  push    rbp
0x18001a462  push    rsi
0x18001a463  push    rdi
0x18001a464  push    r12
0x18001a466  push    r13
0x18001a468  push    r14
0x18001a46a  push    r15
0x18001a46c  sub     rsp, 40h
0x18001a470  mov     rax, cs:__security_cookie
0x18001a477  xor     rax, rsp
0x18001a47a  mov     [rsp+78h+var_40], rax
0x18001a47f  xor     r13d, r13d
0x18001a482  mov     rbp, rdx
0x18001a485  mov     rcx, rbp; Str
0x18001a488  mov     r14, r9
0x18001a48b  mov     r12, r8
0x18001a48e  mov     r15d, r13d
0x18001a491  mov     esi, r13d
0x18001a494  lea     edx, [r13+3Dh]; Ch
0x18001a498  call    cs:__imp_wcsrchr
0x18001a49e  mov     rbx, rax
0x18001a4a1  test    rax, rax
0x18001a4a4  jz      loc_18001A53A
0x18001a4aa  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001a4ae  mov     rax, rdi
0x18001a4b1  inc     rax
0x18001a4b4  cmp     [rbx+rax*2], r13w
0x18001a4b9  jnz     short loc_18001A4B1
0x18001a4bb  cmp     rax, 1
0x18001a4bf  jbe     short loc_18001A53A
0x18001a4c1  xorps   xmm0, xmm0
0x18001a4c4  mov     [rsp+78h+EndPtr], r13
0x18001a4c9  add     rbx, 2
0x18001a4cd  lea     rdx, [rsp+78h+EndPtr]; EndPtr
0x18001a4d2  mov     rcx, rbx; String
0x18001a4d5  mov     r8d, 0Ah; Radix
0x18001a4db  movups  xmmword ptr [rsp+78h+pclsid.Data1], xmm0
0x18001a4e0  call    cs:__imp_wcstoul
0x18001a4e6  mov     rax, [rsp+78h+EndPtr]
0x18001a4eb  test    rax, rax
0x18001a4ee  jz      short loc_18001A503
0x18001a4f0  cmp     [rax], r13w
0x18001a4f4  jnz     short loc_18001A503
0x18001a4f6  mov     esi, 1
0x18001a4fb  mov     rbx, rbp
0x18001a4fe  mov     rdx, rbx
0x18001a501  jmp     short loc_18001A53D
0x18001a503  cmp     word ptr [rbx], 7Bh ; '{'
0x18001a507  jnz     short loc_18001A51B
0x18001a509  lea     rdx, [rsp+78h+pclsid]; pclsid
0x18001a50e  mov     rcx, rbx; lpsz
0x18001a511  call    cs:__imp_CLSIDFromString
0x18001a517  test    eax, eax
0x18001a519  jns     short loc_18001A4F6
0x18001a51b  inc     rdi
0x18001a51e  cmp     [rbx+rdi*2], r13w
0x18001a523  jnz     short loc_18001A51B
0x18001a525  movzx   ecx, word ptr [rbx+rdi*2-2]
0x18001a52a  call    cs:__imp__o_iswdigit
0x18001a530  test    eax, eax
0x18001a532  jnz     short loc_18001A4FB
0x18001a534  lea     r15d, [rax+1]
0x18001a538  jmp     short loc_18001A4FE
0x18001a53a  mov     rdx, rbp
0x18001a53d  mov     rcx, r12
0x18001a540  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x18001a545  test    r14, r14
0x18001a548  jz      short loc_18001A54D
0x18001a54a  mov     [r14], esi
0x18001a54d  mov     eax, r15d
0x18001a550  mov     rcx, [rsp+78h+var_40]
0x18001a555  xor     rcx, rsp; StackCookie
0x18001a558  call    __security_check_cookie
0x18001a55d  mov     rbx, [rsp+78h+arg_0]
0x18001a565  add     rsp, 40h
0x18001a569  pop     r15
0x18001a56b  pop     r14
0x18001a56d  pop     r13
0x18001a56f  pop     r12
0x18001a571  pop     rdi
0x18001a572  pop     rsi
0x18001a573  pop     rbp
0x18001a574  retn
```
