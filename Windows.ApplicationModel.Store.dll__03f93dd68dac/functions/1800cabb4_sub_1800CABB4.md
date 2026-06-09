# sub_1800CABB4

- ea: `0x1800cabb4`
- end: `0x1800cae12`
- name: `sub_1800CABB4`
- size: `606`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task`

## callers

- `0x1800c8510`

## callees

- `0x1800044c0`
- `0x180004890`
- `0x18001102c`
- `0x18001b940`
- `0x180038a50`
- `0x1800457c4`
- `0x1800aa6b0`
- `0x1800ad46c`
- `0x1800aed50`
- `0x1800c7ec4`
- `0x1800cabb4`
- `0x1801519b8`
- `0x180159010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cabf3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cac56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cac6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cacf3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cadd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cade5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cabf3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cac56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cac6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cacf3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cadd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cade5`

## string_xrefs

- `0x1800cad19`: `ChkHr(JsonHelpers::Stringify(_response, jsonResponse.GetAddressOf()))`
- `0x1800cac93`: `Windows::Services::Store::PurchaseOperation::_FirePurchaseTelemetry`
- `0x1800cacc2`: `Windows::Services::Store::PurchaseOperation::_FirePurchaseTelemetry`
- `0x1800cad20`: `Windows::Services::Store::PurchaseOperation::_FirePurchaseTelemetry`
- `0x1800cac8c`: `ChkHr(JsonHelpers::Stringify(_request, jsonRequest.GetAddressOf()))`

## pseudocode

```c
__int64 __fastcall sub_1800CABB4(__int64 a1, int a2)
{
  unsigned int v4; // esi
  _QWORD *v5; // r15
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, _QWORD, _QWORD); // rbx
  __int64 v8; // rax
  int v9; // eax
  unsigned int v10; // ebx
  int v11; // eax
  HSTRING v12; // rcx
  int v13; // eax
  HSTRING v15; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING v16; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING string[2]; // [rsp+40h] [rbp-C0h] BYREF
  char Str[136]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v19; // [rsp+D8h] [rbp-28h]
  __int64 v20; // [rsp+E0h] [rbp-20h]
  __int64 v21; // [rsp+E8h] [rbp-18h]
  HSTRING_HEADER hstringHeader; // [rsp+F0h] [rbp-10h] BYREF

  v4 = 0;
  v5 = (_QWORD *)(a1 + 416);
  do
  {
    string[0] = 0;
    WindowsDeleteString(0);
    string[0] = 0;
    if ( (int)sub_1800AD46C(*v5, off_18019EAD0[v4], string) >= 0 )
    {
      v6 = *v5;
      v7 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)*v5 + 56LL);
      v8 = sub_18001102C(&hstringHeader);
      v9 = v7(v6, *(_QWORD *)(v8 + 24), 0);
      v10 = v9;
      if ( v9 < 0 )
      {
        sub_1801519B8(
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensing\\winrt\\lib\\windows\\purchaseoperation.cpp",
          507,
          (unsigned int)"Windows::Services::Store::PurchaseOperation::_FirePurchaseTelemetry",
          (unsigned int)"ChkHr(_request->SetNamedValue(HStringReference(g_DoNotLogTheseValues[i]).Get(), nullptr))",
          v9);
        sub_18001B940(v10);
        v12 = string[0];
        goto LABEL_19;
      }
    }
    WindowsDeleteString(string[0]);
    ++v4;
  }
  while ( v4 < 4 );
  WindowsDeleteString(0);
  v16 = 0;
  v11 = sub_1800AED50(v5, &v16);
  v10 = v11;
  if ( v11 >= 0 )
  {
    WindowsDeleteString(0);
    v15 = 0;
    v13 = sub_1800AED50(a1 + 224, &v15);
    v10 = v13;
    if ( v13 >= 0 )
    {
      sub_1800C7EC4(Str);
      if ( v20 && !Str[0] )
      {
        Str[0] = 0;
        sub_1800457C4(v20, _InterlockedExchangeAdd64((volatile signed __int64 *)(v20 + 136), 0), Str);
      }
      sub_1800AA6B0((unsigned int)Str, a1 + 376, (unsigned int)&v16, (unsigned int)&v15, a2);
      if ( v21 )
      {
        j_j__o_free(v21);
        v21 = 0;
      }
      if ( v19 )
      {
        j_j__o_free(v19);
        v19 = 0;
      }
    }
    else
    {
      sub_1801519B8(
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensing\\winrt\\lib\\windows\\purchaseoperation.cpp",
        515,
        (unsigned int)"Windows::Services::Store::PurchaseOperation::_FirePurchaseTelemetry",
        (unsigned int)"ChkHr(JsonHelpers::Stringify(_response, jsonResponse.GetAddressOf()))",
        v13);
      sub_18001B940(v10);
    }
    WindowsDeleteString(v15);
    v15 = 0;
  }
  else
  {
    sub_1801519B8(
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensing\\winrt\\lib\\windows\\purchaseoperation.cpp",
      512,
      (unsigned int)"Windows::Services::Store::PurchaseOperation::_FirePurchaseTelemetry",
      (unsigned int)"ChkHr(JsonHelpers::Stringify(_request, jsonRequest.GetAddressOf()))",
      v11);
    sub_18001B940(v10);
  }
  v12 = v16;
LABEL_19:
  WindowsDeleteString(v12);
  return sub_180038A50(v10);
}

```

## disassembly

```asm
0x1800cabb4  push    rbp
0x1800cabb6  push    rbx
0x1800cabb7  push    rsi
0x1800cabb8  push    rdi
0x1800cabb9  push    r12
0x1800cabbb  push    r13
0x1800cabbd  push    r14
0x1800cabbf  push    r15
0x1800cabc1  lea     rbp, [rsp-28h]
0x1800cabc6  sub     rsp, 128h
0x1800cabcd  mov     rax, cs:__security_cookie
0x1800cabd4  xor     rax, rsp
0x1800cabd7  mov     [rbp+60h+var_50], rax
0x1800cabdb  mov     r13d, edx
0x1800cabde  mov     r14, rcx
0x1800cabe1  xor     edi, edi
0x1800cabe3  mov     esi, edi
0x1800cabe5  lea     r15, [rcx+1A0h]
0x1800cabec  mov     [rsp+160h+string], rdi
0x1800cabf1  xor     ecx, ecx; string
0x1800cabf3  call    cs:WindowsDeleteString
0x1800cabf9  mov     [rsp+160h+string], rdi
0x1800cabfe  mov     eax, esi
0x1800cac00  lea     rcx, off_18019EAD0; "Auth"
0x1800cac07  lea     r12, [rcx+rax*8]
0x1800cac0b  lea     r8, [rsp+160h+string]
0x1800cac10  mov     rdx, [r12]
0x1800cac14  mov     rcx, [r15]
0x1800cac17  call    sub_1800AD46C
0x1800cac1c  test    eax, eax
0x1800cac1e  js      short loc_1800CAC51
0x1800cac20  mov     rdi, [r15]
0x1800cac23  mov     rax, [rdi]
0x1800cac26  mov     rbx, [rax+38h]
0x1800cac2a  mov     rdx, r12
0x1800cac2d  lea     rcx, [rbp+60h+hstringHeader]; hstringHeader
0x1800cac31  call    sub_18001102C
0x1800cac36  nop
0x1800cac37  xor     r8d, r8d
0x1800cac3a  mov     rdx, [rax+18h]
0x1800cac3e  mov     rcx, rdi
0x1800cac41  mov     rax, rbx
0x1800cac44  call    j__guard_dispatch_icall
0x1800cac49  mov     ebx, eax
0x1800cac4b  xor     edi, edi
0x1800cac4d  test    eax, eax
0x1800cac4f  js      short loc_1800CACB7
0x1800cac51  mov     rcx, [rsp+160h+string]; string
0x1800cac56  call    cs:WindowsDeleteString
0x1800cac5c  inc     esi
0x1800cac5e  cmp     esi, 4
0x1800cac61  jb      short loc_1800CABEC
0x1800cac63  mov     [rsp+160h+var_128], rdi
0x1800cac68  xor     ecx, ecx; string
0x1800cac6a  call    cs:WindowsDeleteString
0x1800cac70  mov     [rsp+160h+var_128], rdi
0x1800cac75  lea     rdx, [rsp+160h+var_128]
0x1800cac7a  mov     rcx, r15
0x1800cac7d  call    sub_1800AED50
0x1800cac82  mov     ebx, eax
0x1800cac84  test    eax, eax
0x1800cac86  jns     short loc_1800CACEC
0x1800cac88  mov     [rsp+160h+var_140], eax
0x1800cac8c  lea     r9, aChkhrJsonhelpe_171; "ChkHr(JsonHelpers::Stringify(_request, "...
0x1800cac93  lea     r8, aWindowsService_225; "Windows::Services::Store::PurchaseOpera"...
0x1800cac9a  mov     edx, 200h
0x1800cac9f  lea     rcx, aOnecoreuapEndu_36; "onecoreuap\\enduser\\winstore\\licensin"...
0x1800caca6  call    sub_1801519B8
0x1800cacab  mov     ecx, ebx
0x1800cacad  call    sub_18001B940
0x1800cacb2  jmp     loc_1800CADE0
0x1800cacb7  mov     [rsp+160h+var_140], ebx
0x1800cacbb  lea     r9, aChkhrRequestSe; "ChkHr(_request->SetNamedValue(HStringRe"...
0x1800cacc2  lea     r8, aWindowsService_225; "Windows::Services::Store::PurchaseOpera"...
0x1800cacc9  mov     edx, 1FBh
0x1800cacce  lea     rcx, aOnecoreuapEndu_36; "onecoreuap\\enduser\\winstore\\licensin"...
0x1800cacd5  call    sub_1801519B8
0x1800cacda  mov     ecx, ebx
0x1800cacdc  call    sub_18001B940
0x1800cace1  nop
0x1800cace2  mov     rcx, [rsp+160h+string]
0x1800cace7  jmp     loc_1800CADE5
0x1800cacec  mov     [rsp+160h+var_130], rdi
0x1800cacf1  xor     ecx, ecx; string
0x1800cacf3  call    cs:WindowsDeleteString
0x1800cacf9  mov     [rsp+160h+var_130], rdi
0x1800cacfe  lea     rcx, [r14+0E0h]
0x1800cad05  lea     rdx, [rsp+160h+var_130]
0x1800cad0a  call    sub_1800AED50
0x1800cad0f  mov     ebx, eax
0x1800cad11  test    eax, eax
0x1800cad13  jns     short loc_1800CAD44
0x1800cad15  mov     [rsp+160h+var_140], eax
0x1800cad19  lea     r9, aChkhrJsonhelpe_172; "ChkHr(JsonHelpers::Stringify(_response,"...
0x1800cad20  lea     r8, aWindowsService_225; "Windows::Services::Store::PurchaseOpera"...
0x1800cad27  mov     edx, 203h
0x1800cad2c  lea     rcx, aOnecoreuapEndu_36; "onecoreuap\\enduser\\winstore\\licensin"...
0x1800cad33  call    sub_1801519B8
0x1800cad38  mov     ecx, ebx
0x1800cad3a  call    sub_18001B940
0x1800cad3f  jmp     loc_1800CADD0
0x1800cad44  lea     rdx, [r14+0F0h]
0x1800cad4b  lea     rcx, [rsp+160h+Str]; Str
0x1800cad50  call    sub_1800C7EC4
0x1800cad55  nop
0x1800cad56  mov     rcx, [rbp+60h+var_80]
0x1800cad5a  test    rcx, rcx
0x1800cad5d  jz      short loc_1800CAD81
0x1800cad5f  cmp     [rsp+160h+Str], dil
0x1800cad64  jnz     short loc_1800CAD81
0x1800cad66  mov     [rsp+160h+Str], dil
0x1800cad6b  mov     rdx, rdi
0x1800cad6e  lock xadd [rcx+88h], rdx
0x1800cad77  lea     r8, [rsp+160h+Str]
0x1800cad7c  call    sub_1800457C4
0x1800cad81  lea     rdx, [r14+178h]
0x1800cad88  mov     [rsp+160h+var_140], r13d
0x1800cad8d  lea     r9, [rsp+160h+var_130]
0x1800cad92  lea     r8, [rsp+160h+var_128]
0x1800cad97  lea     rcx, [rsp+160h+Str]
0x1800cad9c  call    sub_1800AA6B0
0x1800cada1  nop
0x1800cada2  mov     rcx, [rbp+60h+var_78]
0x1800cada6  test    rcx, rcx
0x1800cada9  jz      short loc_1800CADB9
0x1800cadab  mov     edx, 90h
0x1800cadb0  call    j_j__o_free
0x1800cadb5  mov     [rbp+60h+var_78], rdi
0x1800cadb9  mov     rcx, [rbp+60h+var_88]
0x1800cadbd  test    rcx, rcx
0x1800cadc0  jz      short loc_1800CADD0
0x1800cadc2  mov     edx, 2
0x1800cadc7  call    j_j__o_free
0x1800cadcc  mov     [rbp+60h+var_88], rdi
0x1800cadd0  mov     rcx, [rsp+160h+var_130]; string
0x1800cadd5  call    cs:WindowsDeleteString
0x1800caddb  mov     [rsp+160h+var_130], rdi
0x1800cade0  mov     rcx, [rsp+160h+var_128]; string
0x1800cade5  call    cs:WindowsDeleteString
0x1800cadeb  mov     ecx, ebx
0x1800caded  call    sub_180038A50
0x1800cadf2  mov     rcx, [rbp+60h+var_50]
0x1800cadf6  xor     rcx, rsp; StackCookie
0x1800cadf9  call    __security_check_cookie
0x1800cadfe  add     rsp, 128h
0x1800cae05  pop     r15
0x1800cae07  pop     r14
0x1800cae09  pop     r13
0x1800cae0b  pop     r12
0x1800cae0d  pop     rdi
0x1800cae0e  pop     rsi
0x1800cae0f  pop     rbx
0x1800cae10  pop     rbp
0x1800cae11  retn
```
