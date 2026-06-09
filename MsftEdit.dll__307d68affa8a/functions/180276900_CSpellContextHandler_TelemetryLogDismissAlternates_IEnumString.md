# CSpellContextHandler::TelemetryLogDismissAlternates(IEnumString *)

- ea: `0x180276900`
- end: `0x180276b6e`
- name: `?TelemetryLogDismissAlternates@CSpellContextHandler@@AEAAXPEAUIEnumString@@@Z`
- size: `622`
- prototype: `void __fastcall(CSpellContextHandler *__hidden this, struct IEnumString *)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x1802753a0`
- `0x180275934`
- `0x180275d5c`

## callees

- `0x180048d5c`
- `0x18010ba14`
- `0x18013bad0`
- `0x18013beb8`
- `0x18013bf70`
- `0x18013c8c2`
- `0x180276900`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x1802769ac`
- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x1802769ac`
- `OLEAUT32!__imp_SysFreeString` at `0x180276b05`
- `OLEAUT32!__imp_SysFreeString` at `0x180276b05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180276afd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180276afd`

## pseudocode

```c
void __fastcall CSpellContextHandler::TelemetryLogDismissAlternates(CSpellContextHandler *this, struct IEnumString *a2)
{
  _QWORD *v2; // r15
  int v5; // r12d
  rsize_t v6; // rcx
  wchar_t *v7; // r13
  LCID CurrentInputMethodLCID; // eax
  char v9; // di
  int v10; // ebx
  __int64 v11; // rdi
  int (__fastcall *v12)(__int64, _QWORD, __int64 *); // rbx
  wchar_t *v13; // r8
  __int64 v14; // rax
  char v15; // [rsp+30h] [rbp-D0h]
  BOOL v16; // [rsp+34h] [rbp-CCh] BYREF
  wchar_t *Source; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v18; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+48h] [rbp-B8h] BYREF
  rsize_t SizeInWords; // [rsp+50h] [rbp-B0h]
  WCHAR Name[88]; // [rsp+60h] [rbp-A0h] BYREF

  v2 = (_QWORD *)((char *)this + 48);
  if ( a2 )
  {
    ((void (__fastcall *)(struct IEnumString *))a2->lpVtbl->Reset)(a2);
  }
  else if ( !*v2 )
  {
    return;
  }
  v5 = *((_DWORD *)this + 16);
  v6 = (unsigned int)(129 * (*((_DWORD *)this + 18) - v5 + 1));
  v18 = *((_DWORD *)this + 18) - v5 + 1;
  SizeInWords = v6;
  v7 = (wchar_t *)operator new(saturated_mul(v6, 2u));
  *v7 = 0;
  CurrentInputMethodLCID = CSpellerGlobalState::GetCurrentInputMethodLCID(*(CSpellerGlobalState **)(*((_QWORD *)this + 3)
                                                                                                  + 64LL));
  if ( LCIDToLocaleName(CurrentInputMethodLCID, Name, 85, 0) > 0 )
  {
    if ( a2 )
    {
      v9 = 0;
      v15 = 0;
      goto LABEL_10;
    }
    if ( *v2 )
    {
      v9 = 1;
      v15 = 1;
      (*(void (__fastcall **)(_QWORD, unsigned int *))(*(_QWORD *)*v2 + 40LL))(*v2, &v18);
      do
      {
LABEL_10:
        Source = 0;
        v16 = 0;
        if ( v9 )
        {
          v11 = *v2;
          v19 = 0;
          v12 = *(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v11 + 32LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
          if ( v12(v11, (unsigned int)(v5 - *((_DWORD *)this + 16)), &v19) < 0 )
          {
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
            goto LABEL_30;
          }
          v10 = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v19 + 24LL))(v19, &Source);
          if ( v10 >= 0 )
            v16 = *Source != 12080;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
          v9 = v15;
        }
        else
        {
          v10 = ((__int64 (__fastcall *)(struct IEnumString *, __int64, wchar_t **, BOOL *))a2->lpVtbl->Next)(
                  a2,
                  1,
                  &Source,
                  &v16);
          if ( v10 < 0 )
            goto LABEL_30;
        }
        if ( v16 )
        {
          if ( v5 != *((_DWORD *)this + 16) )
            wcscat_s(v7, SizeInWords, L",");
        }
        else if ( v5 != *((_DWORD *)this + 16) )
        {
          break;
        }
        v13 = (wchar_t *)&qword_1802C16F8;
        if ( Source )
          v13 = Source;
        wcscat_s(v7, SizeInWords, v13);
        if ( a2 )
          CoTaskMemFree(Source);
        else
          SysFreeString(Source);
        ++v5;
      }
      while ( v18 >= v5 - *((_DWORD *)this + 16) + 1 );
      if ( v10 < 0 )
        goto LABEL_30;
    }
    v14 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 3) + 64LL) + 80LL);
    ++*(_DWORD *)(v14 + 32);
  }
LABEL_30:
  operator delete(v7);
}

```

## disassembly

```asm
0x180276900  mov     [rsp-8+arg_10], rbx
0x180276905  push    rbp
0x180276906  push    rsi
0x180276907  push    rdi
0x180276908  push    r12
0x18027690a  push    r13
0x18027690c  push    r14
0x18027690e  push    r15
0x180276910  lea     rbp, [rsp-20h]
0x180276915  sub     rsp, 120h
0x18027691c  mov     rax, cs:__security_cookie
0x180276923  xor     rax, rsp
0x180276926  mov     [rbp+50h+var_40], rax
0x18027692a  lea     r15, [rcx+30h]
0x18027692e  mov     r14, rdx
0x180276931  mov     rsi, rcx
0x180276934  test    rdx, rdx
0x180276937  jnz     short loc_180276944
0x180276939  cmp     [r15], rdx
0x18027693c  jz      loc_180276B3B
0x180276942  jmp     short loc_180276953
0x180276944  mov     rax, [rdx]
0x180276947  mov     rcx, r14
0x18027694a  mov     rax, [rax+28h]
0x18027694e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180276953  mov     eax, [rsi+48h]
0x180276956  mov     r12d, [rsi+40h]
0x18027695a  sub     eax, r12d
0x18027695d  inc     eax
0x18027695f  imul    ecx, eax, 81h
0x180276965  mov     [rsp+150h+var_110], eax
0x180276969  mov     eax, 2
0x18027696e  mul     rcx
0x180276971  mov     [rsp+150h+SizeInWords], rcx
0x180276976  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18027697d  cmovb   rax, rcx
0x180276981  mov     rcx, rax; Size
0x180276984  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180276989  xor     ecx, ecx
0x18027698b  mov     r13, rax
0x18027698e  mov     [rax], cx
0x180276991  mov     rcx, [rsi+18h]
0x180276995  mov     rcx, [rcx+40h]; this
0x180276999  call    ?GetCurrentInputMethodLCID@CSpellerGlobalState@@QEBAKXZ; CSpellerGlobalState::GetCurrentInputMethodLCID(void)
0x18027699e  xor     r9d, r9d; dwFlags
0x1802769a1  lea     rdx, [rsp+150h+Name]; lpName
0x1802769a6  mov     ecx, eax; Locale
0x1802769a8  lea     r8d, [r9+55h]; cchName
0x1802769ac  call    cs:__imp_LCIDToLocaleName
0x1802769b2  test    eax, eax
0x1802769b4  jle     loc_180276B33
0x1802769ba  test    r14, r14
0x1802769bd  jz      short loc_1802769C9
0x1802769bf  xor     dil, dil
0x1802769c2  mov     [rsp+150h+var_120], dil
0x1802769c7  jmp     short loc_1802769EE
0x1802769c9  mov     rcx, [r15]
0x1802769cc  test    rcx, rcx
0x1802769cf  jz      loc_180276B24
0x1802769d5  mov     rax, [rcx]
0x1802769d8  lea     rdx, [rsp+150h+var_110]
0x1802769dd  mov     dil, 1
0x1802769e0  mov     [rsp+150h+var_120], dil
0x1802769e5  mov     rax, [rax+28h]
0x1802769e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802769ee  mov     [rsp+150h+Source], 0
0x1802769f7  mov     [rsp+150h+var_11C], 0
0x1802769ff  test    dil, dil
0x180276a02  jnz     short loc_180276A2E
0x180276a04  mov     rax, [r14]
0x180276a07  lea     r9, [rsp+150h+var_11C]
0x180276a0c  lea     r8, [rsp+150h+Source]
0x180276a11  mov     edx, 1
0x180276a16  mov     rcx, r14
0x180276a19  mov     rax, [rax+18h]
0x180276a1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180276a22  mov     ebx, eax
0x180276a24  test    eax, eax
0x180276a26  js      loc_180276B33
0x180276a2c  jmp     short loc_180276AAA
0x180276a2e  mov     rdi, [r15]
0x180276a31  lea     rcx, [rsp+150h+var_108]
0x180276a36  mov     [rsp+150h+var_108], 0
0x180276a3f  mov     rax, [rdi]
0x180276a42  mov     rbx, [rax+20h]
0x180276a46  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180276a4b  mov     edx, r12d
0x180276a4e  lea     r8, [rsp+150h+var_108]
0x180276a53  sub     edx, [rsi+40h]
0x180276a56  mov     rcx, rdi
0x180276a59  mov     rax, rbx
0x180276a5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180276a61  test    eax, eax
0x180276a63  js      loc_180276B62
0x180276a69  mov     rcx, [rsp+150h+var_108]
0x180276a6e  lea     rdx, [rsp+150h+Source]
0x180276a73  mov     rax, [rcx]
0x180276a76  mov     rax, [rax+18h]
0x180276a7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180276a7f  mov     ebx, eax
0x180276a81  test    eax, eax
0x180276a83  js      short loc_180276A9B
0x180276a85  mov     rax, [rsp+150h+Source]
0x180276a8a  xor     ecx, ecx
0x180276a8c  mov     edx, 2F30h
0x180276a91  cmp     [rax], dx
0x180276a94  setnz   cl
0x180276a97  mov     [rsp+150h+var_11C], ecx
0x180276a9b  lea     rcx, [rsp+150h+var_108]
0x180276aa0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180276aa5  mov     dil, [rsp+150h+var_120]
0x180276aaa  cmp     [rsp+150h+var_11C], 0
0x180276aaf  jnz     short loc_180276AB9
0x180276ab1  cmp     r12d, [rsi+40h]
0x180276ab5  jnz     short loc_180276B20
0x180276ab7  jmp     short loc_180276AD3
0x180276ab9  cmp     r12d, [rsi+40h]
0x180276abd  jz      short loc_180276AD3
0x180276abf  mov     rdx, [rsp+150h+SizeInWords]; SizeInWords
0x180276ac4  lea     r8, asc_1802ACAC4; ","
0x180276acb  mov     rcx, r13; Destination
0x180276ace  call    wcscat_s
0x180276ad3  mov     rax, [rsp+150h+Source]
0x180276ad8  lea     r8, qword_1802C16F8
0x180276adf  mov     rdx, [rsp+150h+SizeInWords]; SizeInWords
0x180276ae4  test    rax, rax
0x180276ae7  mov     rcx, r13; Destination
0x180276aea  cmovnz  r8, rax; Source
0x180276aee  call    wcscat_s
0x180276af3  mov     rcx, [rsp+150h+Source]; bstrString
0x180276af8  test    r14, r14
0x180276afb  jz      short loc_180276B05
0x180276afd  call    cs:__imp_CoTaskMemFree
0x180276b03  jmp     short loc_180276B0B
0x180276b05  call    cs:__imp_SysFreeString
0x180276b0b  inc     r12d
0x180276b0e  mov     eax, r12d
0x180276b11  sub     eax, [rsi+40h]
0x180276b14  inc     eax
0x180276b16  cmp     [rsp+150h+var_110], eax
0x180276b1a  jnb     loc_1802769EE
0x180276b20  test    ebx, ebx
0x180276b22  js      short loc_180276B33
0x180276b24  mov     rax, [rsi+18h]
0x180276b28  mov     rcx, [rax+40h]
0x180276b2c  mov     rax, [rcx+50h]
0x180276b30  inc     dword ptr [rax+20h]
0x180276b33  mov     rcx, r13; Block
0x180276b36  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180276b3b  mov     rcx, [rbp+50h+var_40]
0x180276b3f  xor     rcx, rsp; StackCookie
0x180276b42  call    __security_check_cookie
0x180276b47  mov     rbx, [rsp+150h+arg_10]
0x180276b4f  add     rsp, 120h
0x180276b56  pop     r15
0x180276b58  pop     r14
0x180276b5a  pop     r13
0x180276b5c  pop     r12
0x180276b5e  pop     rdi
0x180276b5f  pop     rsi
0x180276b60  pop     rbp
0x180276b61  retn
0x180276b62  lea     rcx, [rsp+150h+var_108]
0x180276b67  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180276b6c  jmp     short loc_180276B33
```
