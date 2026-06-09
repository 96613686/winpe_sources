# _anonymous_namespace_::GetMessageResourceRootDirectory

- ea: `0x1800420ec`
- end: `0x180042331`
- name: `_anonymous_namespace_::GetMessageResourceRootDirectory`
- size: `581`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180032470`

## callees

- `0x180001b50`
- `0x18000a17c`
- `0x18000a2d0`
- `0x18001662c`
- `0x180040d8c`
- `0x1800420ec`
- `0x180044044`
- `0x180049b50`

## import_xrefs

- `VCRUNTIME140!wcsrchr` at `0x180042185`
- `VCRUNTIME140!wcsrchr` at `0x180042185`
- `OLEAUT32!__imp_SysFreeString` at `0x180042302`
- `OLEAUT32!__imp_SysFreeString` at `0x180042302`
- `ADVAPI32!RegCloseKey` at `0x1800422b1`
- `ADVAPI32!RegCloseKey` at `0x1800422c8`
- `ADVAPI32!RegCloseKey` at `0x1800422b1`
- `ADVAPI32!RegCloseKey` at `0x1800422c8`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1800421d5`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x180042235`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x180042289`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1800421d5`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x180042235`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x180042289`

## string_xrefs

- `0x180042256`: `MessageResource.RootDirectory`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall anonymous_namespace_::GetMessageResourceRootDirectory(_QWORD *a1)
{
  OLECHAR *v3; // rbx
  signed int ModulePath; // edi
  wchar_t *v5; // rax
  unsigned __int16 **v6; // r8
  wchar_t *v7; // rcx
  HKEY v8; // rdx
  int v9; // ebx
  int v10; // eax
  int v11; // eax
  wchar_t *v12; // rbx
  int v13; // eax
  wchar_t *v14; // rdx
  unsigned __int16 v15[4]; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v16; // [rsp+28h] [rbp-D8h] BYREF
  HKEY hKey[3]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t *Str[2]; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *String[2]; // [rsp+58h] [rbp-A8h]
  wchar_t *v20; // [rsp+68h] [rbp-98h]
  wchar_t v21[264]; // [rsp+70h] [rbp-90h] BYREF

  if ( _InterlockedCompareExchange64(&qword_180077170, 0, 0) )
  {
    *a1 = qword_180077170;
    return 0;
  }
  v3 = 0;
  *(_QWORD *)v15 = 0;
  *a1 = 0;
  *(_OWORD *)Str = 0;
  *(_OWORD *)String = 0;
  v20 = 0;
  ModulePath = DiagHubCommon::ModulePath::GetModulePath((HMODULE)0x180000000LL);
  if ( ModulePath >= 0 )
  {
    v5 = wcsrchr(Str[0], 0x5Cu);
    if ( v5 )
    {
      *v5 = 0;
      v7 = Str[0];
      String[1] = Str[0];
      v20 = v5 + 1;
      ModulePath = 0;
    }
    else
    {
      ModulePath = -2147024735;
      v7 = String[1];
    }
    if ( ModulePath >= 0 )
    {
      v9 = DiagHubCommon::DetermineVsInstanceRoot((DiagHubCommon *)v7, (BSTR *)v15, v6);
      if ( !v9 )
      {
        v10 = wcslen(L"\\Team Tools\\DiagnosticsHub");
        ModulePath = ATL::CComBSTR::Append((ATL::CComBSTR *)v15, L"\\Team Tools\\DiagnosticsHub", v10);
        if ( ModulePath < 0 )
        {
LABEL_26:
          v3 = *(OLECHAR **)v15;
          goto LABEL_30;
        }
LABEL_29:
        v3 = (OLECHAR *)(*(_QWORD *)v15
                       & -(__int64)(_InterlockedCompareExchange64(&qword_180077170, *(signed __int64 *)v15, 0) != 0));
        *a1 = qword_180077170;
        ModulePath = 0;
        goto LABEL_30;
      }
      memset(hKey, 0, sizeof(hKey));
      v11 = ATL::CRegKey::Open((ATL::CRegKey *)hKey, v8, L"Software\\Microsoft\\VisualStudio\\17.0\\DiagnosticsHub");
      if ( v11 == 2 )
      {
        v12 = String[1];
        if ( String[1] )
          v13 = wcslen(String[1]);
        else
          v13 = 0;
        v14 = v12;
      }
      else
      {
        if ( v11
          || (v16 = 261,
              (v11 = ATL::CRegKey::QueryStringValue((ATL::CRegKey *)hKey, L"MessageResource.RootDirectory", v21, &v16)) != 0) )
        {
          ModulePath = -518979493;
          if ( v9 != -518979493 )
          {
            ModulePath = (unsigned __int16)v11 | 0x80070000;
            if ( v11 <= 0 )
              ModulePath = v11;
          }
          goto LABEL_24;
        }
        v13 = wcslen(v21);
        v14 = v21;
      }
      ModulePath = ATL::CComBSTR::Append((ATL::CComBSTR *)v15, v14, v13);
      if ( ModulePath >= 0 )
      {
        if ( hKey[0] )
          RegCloseKey(hKey[0]);
        goto LABEL_29;
      }
LABEL_24:
      if ( hKey[0] )
        RegCloseKey(hKey[0]);
      goto LABEL_26;
    }
  }
LABEL_30:
  std::vector<unsigned short>::~vector<unsigned short>(Str);
  SysFreeString(v3);
  return (unsigned int)ModulePath;
}

```

## disassembly

```asm
0x1800420ec  mov     [rsp-8+arg_8], rbx
0x1800420f1  mov     [rsp-8+arg_10], rsi
0x1800420f6  push    rbp
0x1800420f7  push    rdi
0x1800420f8  push    r14
0x1800420fa  lea     rbp, [rsp-190h]
0x180042102  sub     rsp, 290h
0x180042109  mov     rax, cs:__security_cookie
0x180042110  xor     rax, rsp
0x180042113  mov     [rbp+1A0h+var_20], rax
0x18004211a  mov     rsi, rcx
0x18004211d  xor     r14d, r14d
0x180042120  xor     eax, eax
0x180042122  lock cmpxchg cs:qword_180077170, r14
0x18004212b  jz      short loc_18004213E
0x18004212d  mov     rax, cs:qword_180077170
0x180042134  mov     [rcx], rax
0x180042137  xor     eax, eax
0x180042139  jmp     loc_18004230A
0x18004213e  mov     rbx, r14
0x180042141  mov     qword ptr [rsp+2A0h+var_280], rbx
0x180042146  mov     [rcx], r14
0x180042149  xorps   xmm0, xmm0
0x18004214c  movdqu  xmmword ptr [rsp+2A0h+Str], xmm0
0x180042152  xorps   xmm1, xmm1
0x180042155  movdqu  xmmword ptr [rsp+2A0h+String], xmm1
0x18004215b  mov     [rsp+2A0h+var_238], r14
0x180042160  lea     rdx, [rsp+2A0h+Str]
0x180042165  lea     rcx, cs:180000000h; hModule
0x18004216c  call    ?GetModulePath@ModulePath@DiagHubCommon@@SAJPEAUHINSTANCE__@@AEAV?$vector@GV?$allocator@G@std@@@std@@@Z; DiagHubCommon::ModulePath::GetModulePath(HINSTANCE__ *,std::vector<ushort> &)
0x180042171  mov     edi, eax
0x180042173  test    eax, eax
0x180042175  js      loc_1800422F4
0x18004217b  mov     edx, 5Ch ; '\'; Ch
0x180042180  mov     rcx, [rsp+2A0h+Str]; Str
0x180042185  call    cs:__imp_wcsrchr
0x18004218b  test    rax, rax
0x18004218e  jnz     short loc_18004219C
0x180042190  mov     edi, 800700A1h
0x180042195  mov     rcx, [rsp+2A0h+String+8]
0x18004219a  jmp     short loc_1800421B6
0x18004219c  mov     [rax], r14w
0x1800421a0  mov     rcx, [rsp+2A0h+Str]; this
0x1800421a5  mov     [rsp+2A0h+String+8], rcx
0x1800421aa  add     rax, 2
0x1800421ae  mov     [rsp+2A0h+var_238], rax
0x1800421b3  mov     edi, r14d
0x1800421b6  test    edi, edi
0x1800421b8  js      loc_1800422F4
0x1800421be  lea     rdx, [rsp+2A0h+var_280]; unsigned __int16 *
0x1800421c3  call    ?DetermineVsInstanceRoot@DiagHubCommon@@YAJPEBGPEAPEAG@Z; DiagHubCommon::DetermineVsInstanceRoot(ushort const *,ushort * *)
0x1800421c8  mov     ebx, eax
0x1800421ca  test    eax, eax
0x1800421cc  jnz     short loc_1800421FE
0x1800421ce  lea     rcx, aTeamToolsDiagn; "\\Team Tools\\DiagnosticsHub"
0x1800421d5  call    cs:__imp_wcslen
0x1800421db  mov     r8d, eax; int
0x1800421de  lea     rdx, aTeamToolsDiagn; "\\Team Tools\\DiagnosticsHub"
0x1800421e5  lea     rcx, [rsp+2A0h+var_280]; this
0x1800421ea  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x1800421ef  mov     edi, eax
0x1800421f1  test    eax, eax
0x1800421f3  jns     loc_1800422CE
0x1800421f9  jmp     loc_1800422B7
0x1800421fe  mov     [rsp+2A0h+var_268], r14
0x180042203  mov     [rsp+2A0h+hKey], r14
0x180042208  mov     [rsp+2A0h+var_260], r14
0x18004220d  lea     r8, aSoftwareMicros_0; "Software\\Microsoft\\VisualStudio\\17.0"...
0x180042214  lea     rcx, [rsp+2A0h+hKey]; this
0x180042219  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18004221e  cmp     eax, 2
0x180042221  jnz     short loc_180042240
0x180042223  mov     rbx, [rsp+2A0h+String+8]
0x180042228  test    rbx, rbx
0x18004222b  jnz     short loc_180042232
0x18004222d  mov     eax, r14d
0x180042230  jmp     short loc_18004223B
0x180042232  mov     rcx, rbx; String
0x180042235  call    cs:__imp_wcslen
0x18004223b  mov     rdx, rbx
0x18004223e  jmp     short loc_180042294
0x180042240  test    eax, eax
0x180042242  jnz     short loc_18004226B
0x180042244  mov     [rsp+2A0h+var_278], 105h
0x18004224c  lea     r9, [rsp+2A0h+var_278]; unsigned int *
0x180042251  lea     r8, [rsp+2A0h+var_230]; unsigned __int16 *
0x180042256  lea     rdx, aMessageresourc; "MessageResource.RootDirectory"
0x18004225d  lea     rcx, [rsp+2A0h+hKey]; this
0x180042262  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x180042267  test    eax, eax
0x180042269  jz      short loc_180042284
0x18004226b  mov     edi, 0E111005Bh
0x180042270  cmp     ebx, edi
0x180042272  jz      short loc_1800422A7
0x180042274  movzx   edi, ax
0x180042277  or      edi, 80070000h
0x18004227d  test    eax, eax
0x18004227f  cmovle  edi, eax
0x180042282  jmp     short loc_1800422A7
0x180042284  lea     rcx, [rsp+2A0h+var_230]; String
0x180042289  call    cs:__imp_wcslen
0x18004228f  lea     rdx, [rsp+2A0h+var_230]; unsigned __int16 *
0x180042294  mov     r8d, eax; int
0x180042297  lea     rcx, [rsp+2A0h+var_280]; this
0x18004229c  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x1800422a1  test    eax, eax
0x1800422a3  mov     edi, eax
0x1800422a5  jns     short loc_1800422BE
0x1800422a7  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800422ac  test    rcx, rcx
0x1800422af  jz      short loc_1800422B7
0x1800422b1  call    cs:__imp_RegCloseKey
0x1800422b7  mov     rbx, qword ptr [rsp+2A0h+var_280]
0x1800422bc  jmp     short loc_1800422F4
0x1800422be  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800422c3  test    rcx, rcx
0x1800422c6  jz      short loc_1800422CE
0x1800422c8  call    cs:__imp_RegCloseKey
0x1800422ce  mov     rdx, qword ptr [rsp+2A0h+var_280]
0x1800422d3  xor     eax, eax
0x1800422d5  lock cmpxchg cs:qword_180077170, rdx
0x1800422de  neg     rax
0x1800422e1  sbb     rbx, rbx
0x1800422e4  and     rbx, rdx
0x1800422e7  mov     rax, cs:qword_180077170
0x1800422ee  mov     [rsi], rax
0x1800422f1  mov     edi, r14d
0x1800422f4  lea     rcx, [rsp+2A0h+Str]
0x1800422f9  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800422fe  nop
0x1800422ff  mov     rcx, rbx; bstrString
0x180042302  call    cs:__imp_SysFreeString
0x180042308  mov     eax, edi
0x18004230a  mov     rcx, [rbp+1A0h+var_20]
0x180042311  xor     rcx, rsp; StackCookie
0x180042314  call    __security_check_cookie
0x180042319  lea     r11, [rsp+2A0h+var_10]
0x180042321  mov     rbx, [r11+28h]
0x180042325  mov     rsi, [r11+30h]
0x180042329  mov     rsp, r11
0x18004232c  pop     r14
0x18004232e  pop     rdi
0x18004232f  pop     rbp
0x180042330  retn
```
