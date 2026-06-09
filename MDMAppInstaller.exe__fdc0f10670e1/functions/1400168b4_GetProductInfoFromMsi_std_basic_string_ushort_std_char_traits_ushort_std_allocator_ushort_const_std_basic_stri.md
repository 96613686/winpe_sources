# GetProductInfoFromMsi(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1400168b4`
- end: `0x140016a7f`
- name: `?GetProductInfoFromMsi@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV12@0@Z`
- size: `459`
- prototype: `__int64 __fastcall(const WCHAR *szProduct, const WCHAR *szAttribute, _QWORD *, char *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, installer_update`

## callers

- `0x1400177bc`
- `0x140018e48`

## callees

- `0x140002618`
- `0x140003674`
- `0x140006604`
- `0x1400068c8`
- `0x140015b7c`
- `0x1400168b4`
- `0x140017610`

## import_xrefs

- `ADVAPI32!RevertToSelf` at `0x140016a63`
- `ADVAPI32!RevertToSelf` at `0x140016a63`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140016a2b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140016a57`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140016a2b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140016a57`
- `msi!__imp_MsiGetProductInfoW` at `0x1400169a0`
- `msi!__imp_MsiGetProductInfoW` at `0x140016a1c`
- `msi!__imp_MsiGetProductInfoW` at `0x1400169a0`
- `msi!__imp_MsiGetProductInfoW` at `0x140016a1c`

## pseudocode

```c
__int64 __fastcall GetProductInfoFromMsi(const WCHAR *szProduct, const WCHAR *szAttribute, _QWORD *a3, char *a4)
{
  bool v4; // cf
  _WORD *v9; // rcx
  int SessionIDFromUserSid; // ebx
  char *v11; // rax
  char *v12; // r8
  int v13; // edx
  int v14; // ecx
  wchar_t *v15; // rax
  wchar_t *v16; // rax
  const WCHAR *v17; // rdx
  const WCHAR *v18; // rcx
  signed int ProductInfoW; // eax
  int v20; // ebx
  DWORD v21; // ecx
  WCHAR *v22; // rax
  WCHAR *v23; // r14
  signed int v24; // edi
  __int64 v25; // rax
  DWORD SessionId[4]; // [rsp+20h] [rbp-30h] BYREF
  _BYTE v28[32]; // [rsp+30h] [rbp-20h] BYREF
  char v29; // [rsp+90h] [rbp+40h] BYREF
  DWORD pcchValueBuf; // [rsp+98h] [rbp+48h] BYREF

  v4 = a3[3] < 8u;
  pcchValueBuf = 0;
  SessionId[0] = -1;
  v29 = 0;
  if ( v4 )
    v9 = a3;
  else
    v9 = (_WORD *)*a3;
  a3[2] = 0;
  SessionIDFromUserSid = 0;
  *v9 = 0;
  if ( *((_QWORD *)a4 + 3) < 8u )
    v11 = a4;
  else
    v11 = *(char **)a4;
  v12 = (char *)((char *)L"S-0-0-00-0000000000-0000000000-000000000-000" - v11);
  do
  {
    v13 = *(unsigned __int16 *)&v12[(_QWORD)v11];
    v14 = *(unsigned __int16 *)v11 - v13;
    if ( v14 )
      break;
    v11 += 2;
  }
  while ( v13 );
  if ( !v14 )
    goto LABEL_13;
  v15 = (wchar_t *)std::wstring::wstring((__int64)v28, (__int64)a4);
  SessionIDFromUserSid = FindSessionIDFromUserSid(v15, SessionId);
  if ( SessionIDFromUserSid < 0 )
    return (unsigned int)SessionIDFromUserSid;
  v16 = (wchar_t *)std::wstring::wstring((__int64)v28, (__int64)a4);
  SessionIDFromUserSid = ImpersonateUser(v16, SessionId[0], &v29);
  if ( SessionIDFromUserSid >= 0 )
  {
LABEL_13:
    if ( *((_QWORD *)szAttribute + 3) < 8u )
      v17 = szAttribute;
    else
      v17 = *(const WCHAR **)szAttribute;
    if ( *((_QWORD *)szProduct + 3) < 8u )
      v18 = szProduct;
    else
      v18 = *(const WCHAR **)szProduct;
    ProductInfoW = MsiGetProductInfoW(v18, v17, 0, &pcchValueBuf);
    if ( ProductInfoW )
    {
      if ( ProductInfoW <= 0 )
      {
        SessionIDFromUserSid = ProductInfoW;
        goto LABEL_36;
      }
      v20 = (unsigned __int16)ProductInfoW;
      goto LABEL_23;
    }
    v21 = pcchValueBuf;
    if ( pcchValueBuf )
    {
      ++pcchValueBuf;
      v22 = (WCHAR *)operator new[](saturated_mul(v21 + 1, 2u));
      v23 = v22;
      if ( v22 )
      {
        if ( *((_QWORD *)szAttribute + 3) >= 8u )
          szAttribute = *(const WCHAR **)szAttribute;
        if ( *((_QWORD *)szProduct + 3) >= 8u )
          szProduct = *(const WCHAR **)szProduct;
        v24 = MsiGetProductInfoW(szProduct, szAttribute, v22, &pcchValueBuf);
        if ( v24 )
        {
          operator delete[](v23);
          if ( v24 > 0 )
          {
            v20 = (unsigned __int16)v24;
LABEL_23:
            SessionIDFromUserSid = v20 | 0x80070000;
            goto LABEL_36;
          }
          SessionIDFromUserSid = v24;
        }
        else
        {
          v25 = std::char_traits<unsigned short>::length(v23);
          std::wstring::assign(a3, (unsigned __int64)v23, v25);
          operator delete[](v23);
        }
      }
      else
      {
        SessionIDFromUserSid = -2147024882;
      }
    }
  }
LABEL_36:
  if ( v29 )
    RevertToSelf();
  return (unsigned int)SessionIDFromUserSid;
}

```

## disassembly

```asm
0x1400168b4  mov     [rsp-28h+arg_0], rbx
0x1400168b9  push    rbp
0x1400168ba  push    rsi
0x1400168bb  push    rdi
0x1400168bc  push    r14
0x1400168be  push    r15
0x1400168c0  mov     rbp, rsp
0x1400168c3  sub     rsp, 50h
0x1400168c7  cmp     qword ptr [r8+18h], 8
0x1400168cc  mov     r14, r9
0x1400168cf  mov     r15, r8
0x1400168d2  mov     [rbp+pcchValueBuf], 0
0x1400168d9  mov     rdi, rdx
0x1400168dc  mov     [rbp+SessionId], 0FFFFFFFFh
0x1400168e3  mov     rsi, rcx
0x1400168e6  mov     [rbp+arg_10], 0
0x1400168ea  jb      short loc_1400168F1
0x1400168ec  mov     rcx, [r8]
0x1400168ef  jmp     short loc_1400168F4
0x1400168f1  mov     rcx, r15
0x1400168f4  xor     eax, eax
0x1400168f6  mov     qword ptr [r8+10h], 0
0x1400168fe  xor     ebx, ebx
0x140016900  mov     [rcx], ax
0x140016903  cmp     qword ptr [r9+18h], 8
0x140016908  jb      short loc_14001690F
0x14001690a  mov     rax, [r9]
0x14001690d  jmp     short loc_140016912
0x14001690f  mov     rax, r14
0x140016912  lea     r8, aS0000000000000_0; "S-0-0-00-0000000000-0000000000-00000000"...
0x140016919  sub     r8, rax
0x14001691c  movzx   ecx, word ptr [rax]
0x14001691f  movzx   edx, word ptr [rax+r8]
0x140016924  sub     ecx, edx
0x140016926  jnz     short loc_140016930
0x140016928  add     rax, 2
0x14001692c  test    edx, edx
0x14001692e  jnz     short loc_14001691C
0x140016930  test    ecx, ecx
0x140016932  jz      short loc_14001697B
0x140016934  mov     rdx, r14
0x140016937  lea     rcx, [rbp+var_20]
0x14001693b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140016940  lea     rdx, [rbp+SessionId]
0x140016944  mov     rcx, rax; String2
0x140016947  call    ?FindSessionIDFromUserSid@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAK@Z; FindSessionIDFromUserSid(std::wstring,ulong &)
0x14001694c  mov     ebx, eax
0x14001694e  test    eax, eax
0x140016950  js      loc_140016A69
0x140016956  mov     rdx, r14
0x140016959  lea     rcx, [rbp+var_20]
0x14001695d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140016962  mov     edx, [rbp+SessionId]; SessionId
0x140016965  lea     r8, [rbp+arg_10]
0x140016969  mov     rcx, rax; String2
0x14001696c  call    ?ImpersonateUser@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KAEA_N@Z; ImpersonateUser(std::wstring,ulong,bool &)
0x140016971  mov     ebx, eax
0x140016973  test    eax, eax
0x140016975  js      loc_140016A5D
0x14001697b  cmp     qword ptr [rdi+18h], 8
0x140016980  jb      short loc_140016987
0x140016982  mov     rdx, [rdi]
0x140016985  jmp     short loc_14001698A
0x140016987  mov     rdx, rdi; szAttribute
0x14001698a  cmp     qword ptr [rsi+18h], 8
0x14001698f  jb      short loc_140016996
0x140016991  mov     rcx, [rsi]
0x140016994  jmp     short loc_140016999
0x140016996  mov     rcx, rsi; szProduct
0x140016999  lea     r9, [rbp+pcchValueBuf]; pcchValueBuf
0x14001699d  xor     r8d, r8d; lpValueBuf
0x1400169a0  call    cs:__imp_MsiGetProductInfoW
0x1400169a6  test    eax, eax
0x1400169a8  jz      short loc_1400169C1
0x1400169aa  jg      short loc_1400169B3
0x1400169ac  mov     ebx, eax
0x1400169ae  jmp     loc_140016A5D
0x1400169b3  movzx   ebx, ax
0x1400169b6  or      ebx, 80070000h
0x1400169bc  jmp     loc_140016A5D
0x1400169c1  mov     ecx, [rbp+pcchValueBuf]
0x1400169c4  test    ecx, ecx
0x1400169c6  jz      loc_140016A5D
0x1400169cc  inc     ecx
0x1400169ce  mov     eax, 2
0x1400169d3  mul     rcx
0x1400169d6  mov     [rbp+pcchValueBuf], ecx
0x1400169d9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1400169e0  cmovb   rax, rcx
0x1400169e4  mov     rcx, rax; unsigned __int64
0x1400169e7  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1400169ec  mov     r14, rax
0x1400169ef  test    rax, rax
0x1400169f2  jnz     short loc_1400169FB
0x1400169f4  mov     ebx, 8007000Eh
0x1400169f9  jmp     short loc_140016A5D
0x1400169fb  cmp     qword ptr [rdi+18h], 8
0x140016a00  jb      short loc_140016A05
0x140016a02  mov     rdi, [rdi]
0x140016a05  cmp     qword ptr [rsi+18h], 8
0x140016a0a  jb      short loc_140016A0F
0x140016a0c  mov     rsi, [rsi]
0x140016a0f  lea     r9, [rbp+pcchValueBuf]; pcchValueBuf
0x140016a13  mov     r8, r14; lpValueBuf
0x140016a16  mov     rdx, rdi; szAttribute
0x140016a19  mov     rcx, rsi; szProduct
0x140016a1c  call    cs:__imp_MsiGetProductInfoW
0x140016a22  mov     edi, eax
0x140016a24  mov     rcx, r14
0x140016a27  test    eax, eax
0x140016a29  jz      short loc_140016A41
0x140016a2b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x140016a31  test    edi, edi
0x140016a33  jg      short loc_140016A39
0x140016a35  mov     ebx, edi
0x140016a37  jmp     short loc_140016A5D
0x140016a39  movzx   ebx, di
0x140016a3c  jmp     loc_1400169B6
0x140016a41  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x140016a46  mov     r8, rax
0x140016a49  mov     rdx, r14
0x140016a4c  mov     rcx, r15
0x140016a4f  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x140016a54  mov     rcx, r14
0x140016a57  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x140016a5d  cmp     [rbp+arg_10], 0
0x140016a61  jz      short loc_140016A69
0x140016a63  call    cs:__imp_RevertToSelf
0x140016a69  mov     eax, ebx
0x140016a6b  mov     rbx, [rsp+50h+arg_0]
0x140016a73  add     rsp, 50h
0x140016a77  pop     r15
0x140016a79  pop     r14
0x140016a7b  pop     rdi
0x140016a7c  pop     rsi
0x140016a7d  pop     rbp
0x140016a7e  retn
```
