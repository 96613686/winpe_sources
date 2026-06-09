# CWMResampleMediaObject::CheckForPlatformOverrides(void)

- ea: `0x180008ad4`
- end: `0x180008d0d`
- name: `?CheckForPlatformOverrides@CWMResampleMediaObject@@IEAAJXZ`
- size: `569`
- prototype: `__int64 __fastcall(CWMResampleMediaObject *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009b48`

## callees

- `0x1800085d0`
- `0x180008ad4`
- `0x18000ab90`
- `0x18000abd8`
- `0x18000b79c`
- `0x18000b808`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtof` at `0x180008c8b`
- `api-ms-win-crt-private-l1-1-0!_o__wtof` at `0x180008c8b`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180008c5f`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180008cbc`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180008c5f`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180008cbc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008bd6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008bd6`

## pseudocode

```c
__int64 __fastcall CWMResampleMediaObject::CheckForPlatformOverrides(CWMResampleMediaObject *this)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  unsigned __int64 v4; // rcx
  unsigned __int64 v5; // rax
  void *v6; // rax
  wchar_t *v8; // rax
  unsigned int v9; // edi
  unsigned int i; // esi
  unsigned int v11; // ecx
  float v12; // xmm1_4
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *Context; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t Delimiter[3]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v16[522]; // [rsp+56h] [rbp-AAh] BYREF
  wchar_t Buffer[264]; // [rsp+260h] [rbp+160h] BYREF
  wchar_t String[1024]; // [rsp+470h] [rbp+370h] BYREF

  wcscpy(Delimiter, L" ;");
  pcbData = 2048;
  Context = 0;
  memset_0(v16, 0, 0x202u);
  if ( swprintf_s(
         Buffer,
         0x104u,
         L"Mtx_%d_0x%X_to_%d_0x%X",
         *((unsigned __int16 *)this + 241),
         *((_DWORD *)this + 125),
         *((unsigned __int16 *)this + 261),
         *((_DWORD *)this + 135)) == -1 )
    return 2147500037LL;
  v3 = *((_QWORD *)this + 86);
  if ( v3 )
  {
    auFree(v3, v2);
    *((_QWORD *)this + 86) = 0;
  }
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Audio\\Policy",
         Buffer,
         2u,
         0,
         String,
         &pcbData) )
  {
    return 2147500037LL;
  }
  v4 = *((unsigned __int16 *)this + 241) * *((unsigned __int16 *)this + 261);
  v5 = 4 * v4;
  if ( !is_mul_ok(v4, 4u) )
    v5 = -1;
  v6 = operator new[](v5, (const struct std::nothrow_t *)&std::nothrow);
  *((_QWORD *)this + 86) = v6;
  if ( !v6 )
    return 2147942414LL;
  memset_0(v6, 0, 4LL * *((unsigned __int16 *)this + 241) * *((unsigned __int16 *)this + 261));
  v8 = wcstok_s(String, Delimiter, &Context);
  v9 = 0;
LABEL_10:
  if ( v9 < *((unsigned __int16 *)this + 261) )
  {
    for ( i = 0; ; ++i )
    {
      v11 = *((unsigned __int16 *)this + 241);
      if ( i >= v11 )
      {
        ++v9;
        goto LABEL_10;
      }
      if ( !v8 )
        break;
      v12 = _wtof(v8);
      *(float *)(*((_QWORD *)this + 86) + 4LL * (i + v9 * *((unsigned __int16 *)this + 241))) = v12;
      v8 = wcstok_s(0, Delimiter, &Context);
    }
    memset_0(*((void **)this + 86), 0, 4LL * (int)(v11 * *((unsigned __int16 *)this + 261)));
    return 2147500037LL;
  }
  return 0;
}

```

## disassembly

```asm
0x180008ad4  push    rbp
0x180008ad6  push    rbx
0x180008ad7  push    rsi
0x180008ad8  push    rdi
0x180008ad9  lea     rbp, [rsp-0B88h]
0x180008ae1  sub     rsp, 0C88h
0x180008ae8  mov     rax, cs:__security_cookie
0x180008aef  xor     rax, rsp
0x180008af2  mov     [rbp+0BA0h+var_30], rax
0x180008af9  mov     eax, dword ptr cs:asc_18008831C; " ;"
0x180008aff  mov     rbx, rcx
0x180008b02  mov     dword ptr [rsp+0CA0h+Delimiter], eax
0x180008b06  lea     rcx, [rsp+0CA0h+var_C4A]; void *
0x180008b0b  movzx   eax, word ptr cs:asc_18008831C+4; ""
0x180008b12  xor     edx, edx; Val
0x180008b14  mov     r8d, 202h; Size
0x180008b1a  mov     [rsp+0CA0h+var_C4C], ax
0x180008b1f  mov     [rsp+0CA0h+var_C60], 800h
0x180008b27  mov     [rsp+0CA0h+Context], 0
0x180008b30  call    memset_0
0x180008b35  movzx   ecx, word ptr [rbx+20Ah]
0x180008b3c  lea     r8, aMtxD0xXToD0xX; "Mtx_%d_0x%X_to_%d_0x%X"
0x180008b43  mov     eax, [rbx+21Ch]
0x180008b49  mov     edx, 104h; BufferCount
0x180008b4e  movzx   r9d, word ptr [rbx+1E2h]
0x180008b56  mov     dword ptr [rsp+0CA0h+pcbData], eax
0x180008b5a  mov     eax, [rbx+1F4h]
0x180008b60  mov     dword ptr [rsp+0CA0h+pvData], ecx
0x180008b64  lea     rcx, [rbp+0BA0h+Buffer]; Buffer
0x180008b6b  mov     dword ptr [rsp+0CA0h+pdwType], eax
0x180008b6f  call    swprintf_s
0x180008b74  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180008b78  cmp     eax, edi
0x180008b7a  jz      loc_180008CE9
0x180008b80  mov     rcx, [rbx+2B0h]
0x180008b87  test    rcx, rcx
0x180008b8a  jz      short loc_180008B9C
0x180008b8c  call    auFree
0x180008b91  mov     qword ptr [rbx+2B0h], 0
0x180008b9c  lea     rax, [rsp+0CA0h+var_C60]
0x180008ba1  mov     r9d, 2; dwFlags
0x180008ba7  mov     [rsp+0CA0h+pcbData], rax; pcbData
0x180008bac  lea     r8, [rbp+0BA0h+Buffer]; lpValue
0x180008bb3  lea     rax, [rbp+0BA0h+String]
0x180008bba  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180008bc1  mov     [rsp+0CA0h+pvData], rax; pvData
0x180008bc6  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180008bcd  mov     [rsp+0CA0h+pdwType], 0; pdwType
0x180008bd6  call    cs:__imp_RegGetValueW
0x180008bdc  test    eax, eax
0x180008bde  jnz     loc_180008CE9
0x180008be4  movzx   ecx, word ptr [rbx+20Ah]
0x180008beb  movzx   eax, word ptr [rbx+1E2h]
0x180008bf2  imul    ecx, eax
0x180008bf5  mov     eax, 4
0x180008bfa  movsxd  rcx, ecx
0x180008bfd  mul     rcx
0x180008c00  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008c07  cmovb   rax, rdi
0x180008c0b  mov     rcx, rax; unsigned __int64
0x180008c0e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180008c13  mov     [rbx+2B0h], rax
0x180008c1a  mov     r9, rax
0x180008c1d  test    rax, rax
0x180008c20  jnz     short loc_180008C2C
0x180008c22  mov     eax, 8007000Eh
0x180008c27  jmp     loc_180008CEE
0x180008c2c  movzx   ecx, word ptr [rbx+20Ah]
0x180008c33  xor     edx, edx; Val
0x180008c35  movzx   eax, word ptr [rbx+1E2h]
0x180008c3c  imul    ecx, eax
0x180008c3f  movsxd  r8, ecx
0x180008c42  mov     rcx, r9; void *
0x180008c45  shl     r8, 2; Size
0x180008c49  call    memset_0
0x180008c4e  lea     r8, [rsp+0CA0h+Context]; Context
0x180008c53  lea     rdx, [rsp+0CA0h+Delimiter]; Delimiter
0x180008c58  lea     rcx, [rbp+0BA0h+String]; String
0x180008c5f  call    cs:__imp_wcstok_s
0x180008c65  xor     edi, edi
0x180008c67  movzx   ecx, word ptr [rbx+20Ah]
0x180008c6e  cmp     edi, ecx
0x180008c70  jnb     loc_180008D09
0x180008c76  xor     esi, esi
0x180008c78  movzx   ecx, word ptr [rbx+1E2h]
0x180008c7f  cmp     esi, ecx
0x180008c81  jnb     short loc_180008CC6
0x180008c83  test    rax, rax
0x180008c86  jz      short loc_180008CCA
0x180008c88  mov     rcx, rax; String
0x180008c8b  call    cs:__imp__wtof
0x180008c91  movzx   ecx, word ptr [rbx+1E2h]
0x180008c98  lea     r8, [rsp+0CA0h+Context]; Context
0x180008c9d  mov     rax, [rbx+2B0h]
0x180008ca4  lea     rdx, [rsp+0CA0h+Delimiter]; Delimiter
0x180008ca9  imul    ecx, edi
0x180008cac  xorps   xmm1, xmm1
0x180008caf  cvtsd2ss xmm1, xmm0
0x180008cb3  add     ecx, esi
0x180008cb5  movss   dword ptr [rax+rcx*4], xmm1
0x180008cba  xor     ecx, ecx; String
0x180008cbc  call    cs:__imp_wcstok_s
0x180008cc2  inc     esi
0x180008cc4  jmp     short loc_180008C78
0x180008cc6  inc     edi
0x180008cc8  jmp     short loc_180008C67
0x180008cca  movzx   eax, word ptr [rbx+20Ah]
0x180008cd1  xor     edx, edx; Val
0x180008cd3  imul    eax, ecx
0x180008cd6  mov     rcx, [rbx+2B0h]; void *
0x180008cdd  movsxd  r8, eax
0x180008ce0  shl     r8, 2; Size
0x180008ce4  call    memset_0
0x180008ce9  mov     eax, 80004005h
0x180008cee  mov     rcx, [rbp+0BA0h+var_30]
0x180008cf5  xor     rcx, rsp; StackCookie
0x180008cf8  call    __security_check_cookie
0x180008cfd  add     rsp, 0C88h
0x180008d04  pop     rdi
0x180008d05  pop     rsi
0x180008d06  pop     rbx
0x180008d07  pop     rbp
0x180008d08  retn
0x180008d09  xor     eax, eax
0x180008d0b  jmp     short loc_180008CEE
```
