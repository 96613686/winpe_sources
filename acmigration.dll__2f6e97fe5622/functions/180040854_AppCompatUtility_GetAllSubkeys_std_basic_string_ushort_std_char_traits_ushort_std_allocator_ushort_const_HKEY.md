# AppCompatUtility::GetAllSubkeys(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,HKEY__ *)

- ea: `0x180040854`
- end: `0x180040c58`
- name: `?GetAllSubkeys@AppCompatUtility@@YAPEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@PEAUHKEY__@@@Z`
- size: `1028`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000ef90`
- `0x180047734`

## callees

- `0x180001cf0`
- `0x1800020c0`
- `0x180002120`
- `0x18000b5fc`
- `0x18000b720`
- `0x18000e428`
- `0x18001067c`
- `0x18001163c`
- `0x180011a98`
- `0x180011d40`
- `0x18003f538`
- `0x180040854`
- `0x180043858`
- `0x1800543c0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180040b49`
- `ADVAPI32!RegCloseKey` at `0x180040bdc`
- `ADVAPI32!RegCloseKey` at `0x180040b49`
- `ADVAPI32!RegCloseKey` at `0x180040bdc`
- `ADVAPI32!RegOpenKeyExW` at `0x180040b08`
- `ADVAPI32!RegOpenKeyExW` at `0x180040b08`

## string_xrefs

- `0x180040b73`: `RegOpenKeyEx failed, %d, %ws`
- `0x180040a1b`: `AppCompatUtility::GetAllSubkeys`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall AppCompatUtility::GetAllSubkeys(_QWORD *a1, HKEY a2)
{
  _QWORD *v4; // rdi
  HKEY v5; // rsi
  HKEY *v6; // rax
  char v7; // r12
  void *v8; // rax
  int v9; // r15d
  __int64 v10; // r13
  char v11; // bl
  __int64 v12; // rcx
  __int64 v13; // rbx
  unsigned __int64 v14; // rax
  LPCWSTR *v15; // rcx
  LPCWSTR *v17; // rax
  const WCHAR *v18; // rdx
  LSTATUS v19; // eax
  LSTATUS v20; // ecx
  LPCWSTR *v21; // rax
  PHKEY phkResult; // [rsp+28h] [rbp-79h]
  PHKEY phkResulta; // [rsp+28h] [rbp-79h]
  __int64 v25; // [rsp+30h] [rbp-71h]
  HKEY v26[2]; // [rsp+38h] [rbp-69h] BYREF
  __int128 v27; // [rsp+48h] [rbp-59h] BYREF
  __int64 v28; // [rsp+58h] [rbp-49h]
  HKEY hKey; // [rsp+60h] [rbp-41h]
  __int64 v30; // [rsp+68h] [rbp-39h]
  LPCWSTR lpSubKey[2]; // [rsp+70h] [rbp-31h] BYREF
  __int64 v32; // [rsp+80h] [rbp-21h]
  unsigned __int64 v33; // [rsp+88h] [rbp-19h]
  unsigned __int64 v34; // [rsp+90h] [rbp-11h]
  __int128 v35; // [rsp+98h] [rbp-9h] BYREF
  __int64 v36; // [rsp+A8h] [rbp+7h]
  __int64 v37; // [rsp+B0h] [rbp+Fh]

  v30 = -2;
  hKey = a2;
  v27 = 0;
  v28 = 0;
  v4 = operator new(0x18u);
  *v4 = 0;
  v4[1] = 0;
  v4[2] = 0;
  v5 = (HKEY)operator new(0x28u);
  v26[1] = v5;
  *(_QWORD *)v5 = 0;
  *((_QWORD *)v5 + 1) = 0;
  *((_QWORD *)v5 + 2) = 0;
  *((_QWORD *)v5 + 3) = 0;
  *((_QWORD *)v5 + 4) = 0;
  v6 = (HKEY *)operator new(0x10u);
  v6[1] = 0;
  *(_QWORD *)v5 = v6;
  *v6 = v5;
  v26[0] = 0;
  v7 = 0;
  *(_OWORD *)lpSubKey = 0;
  v32 = 0;
  v33 = 7;
  LOWORD(lpSubKey[0]) = 0;
  v8 = (void *)std::wstring::wstring(&v35, a1);
  if ( (unsigned __int8)AppCompatUtility::BreakRegKeyToChunks(v8) )
  {
    v9 = 0;
    v10 = (__int64)(*((_QWORD *)&v27 + 1) - v27) >> 5;
    v35 = 0;
    v36 = 0;
    v37 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v35, &psz, 0);
    v11 = AppCompatUtility::PopulateChildrenToStack(a2, 0);
    std::wstring::~wstring(&v35);
    if ( v11 )
    {
      while ( 1 )
      {
        v12 = *((_QWORD *)v5 + 4);
        if ( !v12 )
        {
          v7 = 1;
          goto LABEL_31;
        }
        v13 = *(_QWORD *)(*((_QWORD *)v5 + 1) + 8 * ((*((_QWORD *)v5 + 2) - 1LL) & (v12 - 1 + *((_QWORD *)v5 + 3))));
        std::wstring::operator=(lpSubKey, v13);
        v14 = *(_QWORD *)(v13 + 32);
        v34 = v14;
        v15 = lpSubKey;
        if ( v33 > 7 )
          v15 = (LPCWSTR *)lpSubKey[0];
        LODWORD(v25) = v14;
        AslLogCallPrintf(3, "AppCompatUtility::GetAllSubkeys", 1930, "Current node: %ws; level: %d", v15, v25);
        std::wstring::~wstring(*(void **)(*((_QWORD *)v5 + 1)
                                        + 8
                                        * ((*((_QWORD *)v5 + 2) - 1LL)
                                         & (*((_QWORD *)v5 + 4) - 1LL + *((_QWORD *)v5 + 3)))));
        if ( (*((_QWORD *)v5 + 4))-- == 1 )
          *((_QWORD *)v5 + 3) = 0;
        if ( ++v9 > 10000 )
          break;
        if ( v34 == v10 - 1 )
        {
          v17 = lpSubKey;
          if ( v33 > 7 )
            v17 = (LPCWSTR *)lpSubKey[0];
          AslLogCallPrintf(3, "AppCompatUtility::GetAllSubkeys", 1943, "Found a matched subkey: %ws", v17);
          if ( v4[1] == v4[2] )
          {
            std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(v4, v4[1], lpSubKey);
          }
          else
          {
            std::wstring::wstring(v4[1], lpSubKey);
            v4[1] += 32LL;
          }
        }
        else
        {
          if ( v34 > v10 - 1 )
          {
            LODWORD(phkResult) = v34;
            AslLogCallPrintf(
              1,
              "AppCompatUtility::GetAllSubkeys",
              1948,
              "Tree traversal error, current level: %d",
              phkResult);
            goto LABEL_31;
          }
          v18 = (const WCHAR *)lpSubKey;
          if ( v33 > 7 )
            v18 = lpSubKey[0];
          v19 = RegOpenKeyExW(hKey, v18, 0, 0x20019u, v26);
          v20 = v19;
          if ( v19 != 5 )
          {
            if ( v19 )
            {
              v21 = lpSubKey;
              if ( v33 > 7 )
                v21 = (LPCWSTR *)lpSubKey[0];
              LODWORD(phkResulta) = v20;
              AslLogCallPrintf(
                1,
                "AppCompatUtility::GetAllSubkeys",
                1966,
                "RegOpenKeyEx failed, %d, %ws",
                phkResulta,
                v21);
              goto LABEL_31;
            }
            if ( !(unsigned __int8)AppCompatUtility::PopulateChildrenToStack(v26[0], v34 + 1) )
              goto LABEL_31;
            RegCloseKey(v26[0]);
            v26[0] = 0;
          }
        }
      }
      if ( a1[3] > 7u )
        a1 = (_QWORD *)*a1;
      AslLogCallPrintf(1, "AppCompatUtility::GetAllSubkeys", 1937, "Reached max count of processed keys for %ws", a1);
    }
  }
LABEL_31:
  if ( v26[0] )
  {
    RegCloseKey(v26[0]);
    v26[0] = 0;
  }
  std::deque<AppCompatUtility::_SubkeyNode>::~deque<AppCompatUtility::_SubkeyNode>(v5);
  operator delete(v5);
  if ( !v7 )
  {
    std::vector<std::wstring>::_Tidy(v4);
    operator delete(v4);
    v4 = 0;
  }
  std::wstring::~wstring(lpSubKey);
  std::vector<std::wstring>::_Tidy(&v27);
  return v4;
}

```

## disassembly

```asm
0x180040854  mov     rax, rsp
0x180040857  push    rbp
0x180040858  push    rsi
0x180040859  push    rdi
0x18004085a  push    r12
0x18004085c  push    r13
0x18004085e  push    r14
0x180040860  push    r15
0x180040862  lea     rbp, [rax-5Fh]
0x180040866  sub     rsp, 0C0h
0x18004086d  mov     [rbp+57h+var_90], 0FFFFFFFFFFFFFFFEh
0x180040875  mov     [rax+18h], rbx
0x180040879  mov     rax, cs:__security_cookie
0x180040880  xor     rax, rsp
0x180040883  mov     [rbp+57h+var_40], rax
0x180040887  mov     rbx, rdx
0x18004088a  mov     [rbp+57h+hKey], rdx
0x18004088e  mov     r14, rcx
0x180040891  xorps   xmm0, xmm0
0x180040894  movdqu  [rbp+57h+var_B0], xmm0
0x180040899  mov     [rbp+57h+var_A0], 0
0x1800408a1  mov     ecx, 18h; Size
0x1800408a6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800408ab  mov     rdi, rax
0x1800408ae  mov     qword ptr [rax], 0
0x1800408b5  mov     qword ptr [rax+8], 0
0x1800408bd  mov     qword ptr [rax+10h], 0
0x1800408c5  mov     ecx, 28h ; '('; Size
0x1800408ca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800408cf  mov     rsi, rax
0x1800408d2  mov     [rbp+57h+var_B8], rax
0x1800408d6  mov     qword ptr [rax], 0
0x1800408dd  mov     qword ptr [rax+8], 0
0x1800408e5  mov     qword ptr [rax+10h], 0
0x1800408ed  mov     qword ptr [rax+18h], 0
0x1800408f5  mov     qword ptr [rax+20h], 0
0x1800408fd  mov     ecx, 10h; Size
0x180040902  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180040907  mov     qword ptr [rax+8], 0
0x18004090f  mov     [rsi], rax
0x180040912  mov     [rax], rsi
0x180040915  mov     [rbp+57h+var_C0], 0
0x18004091d  xor     r12b, r12b
0x180040920  xorps   xmm0, xmm0
0x180040923  movups  xmmword ptr [rbp+57h+lpSubKey], xmm0
0x180040927  mov     [rbp+57h+var_78], 0
0x18004092f  mov     [rbp+57h+var_70], 7
0x180040937  xor     eax, eax
0x180040939  mov     word ptr [rbp+57h+lpSubKey], ax
0x18004093d  mov     rdx, r14
0x180040940  lea     rcx, [rbp+57h+var_60]
0x180040944  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180040949  lea     rdx, [rbp+57h+var_B0]
0x18004094d  mov     rcx, rax; void *
0x180040950  call    ?BreakRegKeyToChunks@AppCompatUtility@@YA_NV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@3@@Z; AppCompatUtility::BreakRegKeyToChunks(std::wstring,std::vector<std::wstring> &)
0x180040955  test    al, al
0x180040957  jz      loc_180040BD3
0x18004095d  xor     r15d, r15d
0x180040960  mov     r13, qword ptr [rbp+57h+var_B0+8]
0x180040964  sub     r13, qword ptr [rbp+57h+var_B0]
0x180040968  sar     r13, 5
0x18004096c  xorps   xmm0, xmm0
0x18004096f  movups  [rbp+57h+var_60], xmm0
0x180040973  mov     [rbp+57h+var_50], r15
0x180040977  mov     [rbp+57h+var_48], r15
0x18004097b  xor     r8d, r8d
0x18004097e  lea     rdx, psz
0x180040985  lea     rcx, [rbp+57h+var_60]
0x180040989  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004098e  nop
0x18004098f  mov     [rsp+0F0h+phkResult], r15; __int64
0x180040994  lea     r9, [rbp+57h+var_B0]
0x180040998  mov     r8, rsi
0x18004099b  lea     rdx, [rbp+57h+var_60]
0x18004099f  mov     rcx, rbx; hKey
0x1800409a2  call    ?PopulateChildrenToStack@AppCompatUtility@@YA_NPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV?$stack@U_SubkeyNode@AppCompatUtility@@V?$deque@U_SubkeyNode@AppCompatUtility@@V?$allocator@U_SubkeyNode@AppCompatUtility@@@std@@@std@@@4@AEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@4@_K@Z; AppCompatUtility::PopulateChildrenToStack(HKEY__ *,std::wstring const &,std::stack<AppCompatUtility::_SubkeyNode> *,std::vector<std::wstring> const &,unsigned __int64)
0x1800409a7  mov     bl, al
0x1800409a9  lea     rcx, [rbp+57h+var_60]; void *
0x1800409ad  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800409b2  test    bl, bl
0x1800409b4  jz      loc_180040BD3
0x1800409ba  mov     rcx, [rsi+20h]
0x1800409be  test    rcx, rcx
0x1800409c1  jz      loc_180040BD0
0x1800409c7  mov     rbx, [rsi+18h]
0x1800409cb  dec     rcx
0x1800409ce  add     rbx, rcx
0x1800409d1  mov     rax, [rsi+10h]
0x1800409d5  dec     rax
0x1800409d8  and     rbx, rax
0x1800409db  mov     rax, [rsi+8]
0x1800409df  mov     rbx, [rax+rbx*8]
0x1800409e3  mov     rdx, rbx
0x1800409e6  lea     rcx, [rbp+57h+lpSubKey]
0x1800409ea  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800409ef  mov     rax, [rbx+20h]
0x1800409f3  mov     [rbp+57h+var_68], rax
0x1800409f7  lea     rcx, [rbp+57h+lpSubKey]
0x1800409fb  cmp     [rbp+57h+var_70], 7
0x180040a00  cmova   rcx, [rbp+57h+lpSubKey]
0x180040a05  mov     [rsp+28h], eax
0x180040a09  mov     [rsp+0F0h+phkResult], rcx
0x180040a0e  lea     r9, aCurrentNodeWsL; "Current node: %ws; level: %d"
0x180040a15  mov     r8d, 78Ah
0x180040a1b  lea     rbx, aAppcompatutili_8; "AppCompatUtility::GetAllSubkeys"
0x180040a22  mov     rdx, rbx
0x180040a25  mov     ecx, 3
0x180040a2a  call    AslLogCallPrintf
0x180040a2f  mov     rcx, [rsi+20h]
0x180040a33  mov     rdx, [rsi+18h]
0x180040a37  dec     rcx
0x180040a3a  add     rdx, rcx
0x180040a3d  mov     rax, [rsi+10h]
0x180040a41  dec     rax
0x180040a44  and     rdx, rax
0x180040a47  mov     rcx, [rsi+8]
0x180040a4b  mov     rcx, [rcx+rdx*8]; void *
0x180040a4f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180040a54  sub     qword ptr [rsi+20h], 1
0x180040a59  jnz     short loc_180040A63
0x180040a5b  mov     qword ptr [rsi+18h], 0
0x180040a63  inc     r15d
0x180040a66  cmp     r15d, 2710h
0x180040a6d  jg      loc_180040BA5
0x180040a73  lea     rax, [r13-1]
0x180040a77  cmp     [rbp+57h+var_68], rax
0x180040a7b  jnz     short loc_180040ADE
0x180040a7d  lea     rax, [rbp+57h+lpSubKey]
0x180040a81  cmp     [rbp+57h+var_70], 7
0x180040a86  cmova   rax, [rbp+57h+lpSubKey]
0x180040a8b  mov     [rsp+0F0h+phkResult], rax
0x180040a90  lea     r9, aFoundAMatchedS_0; "Found a matched subkey: %ws"
0x180040a97  mov     r8d, 797h
0x180040a9d  mov     rdx, rbx
0x180040aa0  mov     ecx, 3
0x180040aa5  call    AslLogCallPrintf
0x180040aaa  mov     rax, [rdi+8]
0x180040aae  cmp     rax, [rdi+10h]
0x180040ab2  jz      short loc_180040ACA
0x180040ab4  lea     rdx, [rbp+57h+lpSubKey]
0x180040ab8  mov     rcx, rax
0x180040abb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180040ac0  add     qword ptr [rdi+8], 20h ; ' '
0x180040ac5  jmp     loc_1800409BA
0x180040aca  lea     r8, [rbp+57h+lpSubKey]
0x180040ace  mov     rdx, rax
0x180040ad1  mov     rcx, rdi
0x180040ad4  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x180040ad9  jmp     loc_1800409BA
0x180040ade  ja      loc_180040B8F
0x180040ae4  lea     rdx, [rbp+57h+lpSubKey]
0x180040ae8  cmp     [rbp+57h+var_70], 7
0x180040aed  cmova   rdx, [rbp+57h+lpSubKey]; lpSubKey
0x180040af2  lea     rax, [rbp+57h+var_C0]
0x180040af6  mov     [rsp+0F0h+phkResult], rax; phkResult
0x180040afb  mov     r9d, 20019h; samDesired
0x180040b01  xor     r8d, r8d; ulOptions
0x180040b04  mov     rcx, [rbp+57h+hKey]; hKey
0x180040b08  call    cs:__imp_RegOpenKeyExW
0x180040b0e  mov     ecx, eax
0x180040b10  cmp     eax, 5
0x180040b13  jz      loc_1800409BA
0x180040b19  test    eax, eax
0x180040b1b  jnz     short loc_180040B5C
0x180040b1d  mov     rax, [rbp+57h+var_68]
0x180040b21  inc     rax
0x180040b24  mov     [rsp+0F0h+phkResult], rax; __int64
0x180040b29  lea     r9, [rbp+57h+var_B0]
0x180040b2d  mov     r8, rsi
0x180040b30  lea     rdx, [rbp+57h+lpSubKey]
0x180040b34  mov     rcx, [rbp+57h+var_C0]; hKey
0x180040b38  call    ?PopulateChildrenToStack@AppCompatUtility@@YA_NPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV?$stack@U_SubkeyNode@AppCompatUtility@@V?$deque@U_SubkeyNode@AppCompatUtility@@V?$allocator@U_SubkeyNode@AppCompatUtility@@@std@@@std@@@4@AEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@4@_K@Z; AppCompatUtility::PopulateChildrenToStack(HKEY__ *,std::wstring const &,std::stack<AppCompatUtility::_SubkeyNode> *,std::vector<std::wstring> const &,unsigned __int64)
0x180040b3d  test    al, al
0x180040b3f  jz      loc_180040BD3
0x180040b45  mov     rcx, [rbp+57h+var_C0]; hKey
0x180040b49  call    cs:__imp_RegCloseKey
0x180040b4f  mov     [rbp+57h+var_C0], 0
0x180040b57  jmp     loc_1800409BA
0x180040b5c  lea     rax, [rbp+57h+lpSubKey]
0x180040b60  cmp     [rbp+57h+var_70], 7
0x180040b65  cmova   rax, [rbp+57h+lpSubKey]
0x180040b6a  mov     [rsp+28h], rax
0x180040b6f  mov     dword ptr [rsp+0F0h+phkResult], ecx
0x180040b73  lea     r9, aRegopenkeyexFa; "RegOpenKeyEx failed, %d, %ws"
0x180040b7a  mov     r8d, 7AEh
0x180040b80  mov     rdx, rbx
0x180040b83  mov     ecx, 1
0x180040b88  call    AslLogCallPrintf
0x180040b8d  jmp     short loc_180040BD3
0x180040b8f  mov     eax, dword ptr [rbp+57h+var_68]
0x180040b92  mov     dword ptr [rsp+0F0h+phkResult], eax
0x180040b96  lea     r9, aTreeTraversalE; "Tree traversal error, current level: %d"
0x180040b9d  mov     r8d, 79Ch
0x180040ba3  jmp     short loc_180040BC1
0x180040ba5  cmp     qword ptr [r14+18h], 7
0x180040baa  jbe     short loc_180040BAF
0x180040bac  mov     r14, [r14]
0x180040baf  mov     [rsp+0F0h+phkResult], r14
0x180040bb4  lea     r9, aReachedMaxCoun; "Reached max count of processed keys for"...
0x180040bbb  mov     r8d, 791h
0x180040bc1  mov     rdx, rbx
0x180040bc4  mov     ecx, 1
0x180040bc9  call    AslLogCallPrintf
0x180040bce  jmp     short loc_180040BD3
0x180040bd0  mov     r12b, 1
0x180040bd3  mov     rcx, [rbp+57h+var_C0]; hKey
0x180040bd7  test    rcx, rcx
0x180040bda  jz      short loc_180040BEA
0x180040bdc  call    cs:__imp_RegCloseKey
0x180040be2  mov     [rbp+57h+var_C0], 0
0x180040bea  mov     rcx, rsi
0x180040bed  call    ??1?$deque@U_SubkeyNode@AppCompatUtility@@V?$allocator@U_SubkeyNode@AppCompatUtility@@@std@@@std@@QEAA@XZ; std::deque<AppCompatUtility::_SubkeyNode>::~deque<AppCompatUtility::_SubkeyNode>(void)
0x180040bf2  mov     edx, 28h ; '('
0x180040bf7  mov     rcx, rsi; Block
0x180040bfa  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180040bff  test    r12b, r12b
0x180040c02  jnz     short loc_180040C1B
0x180040c04  mov     rcx, rdi
0x180040c07  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180040c0c  mov     edx, 18h
0x180040c11  mov     rcx, rdi; Block
0x180040c14  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180040c19  xor     edi, edi
0x180040c1b  lea     rcx, [rbp+57h+lpSubKey]; void *
0x180040c1f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180040c24  nop
0x180040c25  lea     rcx, [rbp+57h+var_B0]
0x180040c29  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180040c2e  mov     rax, rdi
0x180040c31  mov     rcx, [rbp+57h+var_40]
0x180040c35  xor     rcx, rsp; StackCookie
0x180040c38  call    __security_check_cookie
0x180040c3d  mov     rbx, [rsp+0F0h+arg_10]
0x180040c45  add     rsp, 0C0h
0x180040c4c  pop     r15
0x180040c4e  pop     r14
0x180040c50  pop     r13
0x180040c52  pop     r12
0x180040c54  pop     rdi
0x180040c55  pop     rsi
0x180040c56  pop     rbp
0x180040c57  retn
```
