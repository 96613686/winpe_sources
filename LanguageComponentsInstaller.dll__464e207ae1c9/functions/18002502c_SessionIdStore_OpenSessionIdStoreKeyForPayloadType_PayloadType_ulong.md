# SessionIdStore::OpenSessionIdStoreKeyForPayloadType(PayloadType,ulong)

- ea: `0x18002502c`
- end: `0x18002523a`
- name: `?OpenSessionIdStoreKeyForPayloadType@SessionIdStore@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@W4PayloadType@@K@Z`
- size: `526`
- prototype: `PHKEY __fastcall(PHKEY phkResult, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180025b58`

## callees

- `0x180003520`
- `0x180004100`
- `0x18000410c`
- `0x180005954`
- `0x180006380`
- `0x180021494`
- `0x180024638`
- `0x18002502c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800251eb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800251eb`

## string_xrefs

- `0x1800250e4`: `SOFTWARE\Microsoft\Windows\CurrentVersion\LanguageComponentsInstaller\InstallResults\`

## pseudocode

```c
PHKEY __fastcall SessionIdStore::OpenSessionIdStoreKeyForPayloadType(PHKEY phkResult, int a2)
{
  wchar_t **v3; // rax
  __int64 **v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r8
  void **v7; // rsi
  __int64 v8; // rdi
  void **v9; // rcx
  const WCHAR *v10; // rdx
  unsigned int Key; // eax
  DWORD dwOptions; // [rsp+20h] [rbp-79h]
  DWORD dwOptionsa; // [rsp+20h] [rbp-79h]
  void *Src[2]; // [rsp+58h] [rbp-41h] BYREF
  __int128 v16; // [rsp+68h] [rbp-31h]
  PHKEY v17; // [rsp+78h] [rbp-21h]
  LPCWSTR lpSubKey[2]; // [rsp+80h] [rbp-19h] BYREF
  __int128 v19; // [rsp+90h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v17 = phkResult;
  v3 = &off_18002B6B0;
  do
  {
    if ( *((_DWORD *)v3 + 2) == a2 )
      break;
    v3 += 2;
  }
  while ( v3 != (wchar_t **)&Feature_TestAccPerf__private_requiresFeatures );
  v4 = (__int64 **)*v3;
  *(_OWORD *)Src = 0;
  v16 = 0;
  v5 = -1;
  do
    ++v5;
  while ( *((_WORD *)v4 + v5) );
  std::wstring::_Construct<1,unsigned short const *>(Src);
  v6 = v16;
  if ( *((_QWORD *)&v16 + 1) - (_QWORD)v16 < 0x55u )
  {
    v9 = (void **)std::wstring::_Reallocate_grow_by<_lambda_c5c7986eab02a925bb28d3483355880c_,unsigned __int64,unsigned short const *,unsigned __int64>(
                    Src,
                    dwOptions,
                    85);
  }
  else
  {
    *(_QWORD *)&v16 = v16 + 85;
    v7 = Src;
    if ( *((_QWORD *)&v16 + 1) > 7u )
      v7 = (void **)Src[0];
    if ( L"" <= (wchar_t *)v7
      || L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\LanguageComponentsInstaller\\InstallResults\\" > (wchar_t *)v7 + v6 )
    {
      v8 = 85;
    }
    else if ( v7 > (void **)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\LanguageComponentsInstaller\\InstallResults\\" )
    {
      v8 = ((char *)v7
          - (char *)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\LanguageComponentsInstaller\\InstallResults\\") >> 1;
    }
    else
    {
      v8 = 0;
    }
    memmove_0((char *)v7 + 170, v7, 2 * v6 + 2);
    memcpy_0(v7, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\LanguageComponentsInstaller\\InstallResults\\", 2 * v8);
    memcpy_0((char *)v7 + 2 * v8, &aSoftwareMicros_3[v8 + 85], 2 * (85 - v8));
    v9 = Src;
  }
  *(_OWORD *)lpSubKey = 0;
  v19 = 0;
  *(_OWORD *)lpSubKey = *(_OWORD *)v9;
  v19 = *((_OWORD *)v9 + 1);
  v9[2] = 0;
  v9[3] = (void *)7;
  *(_WORD *)v9 = 0;
  std::wstring::~wstring(Src);
  *phkResult = 0;
  v10 = (const WCHAR *)lpSubKey;
  if ( *((_QWORD *)&v19 + 1) > 7u )
    v10 = lpSubKey[0];
  Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v10, 0, 0, 1u, 0x106u, 0, phkResult, 0);
  if ( Key )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x32,
      (unsigned int)"onecore\\internal\\shell\\inc\\SessionIdStore.h",
      (const char *)Key,
      dwOptionsa);
  std::wstring::~wstring(lpSubKey);
  return phkResult;
}

```

## disassembly

```asm
0x18002502c  push    rbp
0x18002502e  push    rbx
0x18002502f  push    rsi
0x180025030  push    rdi
0x180025031  push    r12
0x180025033  push    r13
0x180025035  push    r14
0x180025037  push    r15
0x180025039  lea     rbp, [rsp-1Fh]
0x18002503e  sub     rsp, 0B8h
0x180025045  mov     rax, cs:__security_cookie
0x18002504c  xor     rax, rsp
0x18002504f  mov     [rbp+57h+var_50], rax
0x180025053  mov     r15, rcx
0x180025056  mov     [rbp+57h+var_78], rcx
0x18002505a  xor     r12d, r12d
0x18002505d  mov     [rbp+57h+var_A0], r12d
0x180025061  lea     rax, off_18002B6B0; "Basic"
0x180025068  cmp     [rax+8], edx
0x18002506b  jz      short loc_18002507D
0x18002506d  add     rax, 10h
0x180025071  lea     rcx, Feature_TestAccPerf__private_requiresFeatures
0x180025078  cmp     rax, rcx
0x18002507b  jnz     short loc_180025068
0x18002507d  mov     rdx, [rax]
0x180025080  xorps   xmm0, xmm0
0x180025083  movups  xmmword ptr [rbp+57h+Src], xmm0
0x180025087  xorps   xmm1, xmm1
0x18002508a  movdqu  [rbp+57h+var_88], xmm1
0x18002508f  or      r8, 0FFFFFFFFFFFFFFFFh
0x180025093  inc     r8
0x180025096  cmp     [rdx+r8*2], r12w
0x18002509b  jnz     short loc_180025093
0x18002509d  lea     rcx, [rbp+57h+Src]
0x1800250a1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800250a6  mov     [rbp+57h+var_A0], 4
0x1800250ad  mov     r8, qword ptr [rbp+57h+var_88]
0x1800250b1  mov     rax, qword ptr [rbp+57h+var_88+8]
0x1800250b5  sub     rax, r8
0x1800250b8  mov     r14d, 55h ; 'U'
0x1800250be  cmp     rax, r14
0x1800250c1  jb      loc_18002515B
0x1800250c7  lea     rax, [r8+55h]
0x1800250cb  mov     qword ptr [rbp+57h+var_88], rax
0x1800250cf  lea     rsi, [rbp+57h+Src]
0x1800250d3  cmp     qword ptr [rbp+57h+var_88+8], 7
0x1800250d8  cmova   rsi, [rbp+57h+Src]
0x1800250dd  lea     rax, aSoftwareMicros_3+0AAh; ""
0x1800250e4  lea     r13, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800250eb  cmp     rax, rsi
0x1800250ee  jbe     short loc_18002510E
0x1800250f0  lea     rax, [rsi+r8*2]
0x1800250f4  cmp     r13, rax
0x1800250f7  ja      short loc_18002510E
0x1800250f9  cmp     rsi, r13
0x1800250fc  ja      short loc_180025103
0x1800250fe  mov     rdi, r12
0x180025101  jmp     short loc_180025111
0x180025103  mov     rdi, rsi
0x180025106  sub     rdi, r13
0x180025109  sar     rdi, 1
0x18002510c  jmp     short loc_180025111
0x18002510e  mov     rdi, r14
0x180025111  lea     r8, ds:2[r8*2]; Size
0x180025119  lea     rcx, [rsi+0AAh]; void *
0x180025120  mov     rdx, rsi; Src
0x180025123  call    memmove_0
0x180025128  lea     rbx, [rdi+rdi]
0x18002512c  mov     r8, rbx; Size
0x18002512f  mov     rdx, r13; Src
0x180025132  mov     rcx, rsi; void *
0x180025135  call    memcpy_0
0x18002513a  sub     r14, rdi
0x18002513d  lea     r8, [r14+r14]; Size
0x180025141  lea     rdx, [r13+0AAh]
0x180025148  lea     rdx, [rdx+rdi*2]; Src
0x18002514c  lea     rcx, [rbx+rsi]; void *
0x180025150  call    memcpy_0
0x180025155  lea     rcx, [rbp+57h+Src]
0x180025159  jmp     short loc_18002516F
0x18002515b  mov     qword ptr [rsp+0F0h+samDesired], r14; __int64
0x180025160  mov     rdx, r14
0x180025163  lea     rcx, [rbp+57h+Src]; Src
0x180025167  call    ??$_Reallocate_grow_by@V_lambda_c5c7986eab02a925bb28d3483355880c_@@_KPEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c5c7986eab02a925bb28d3483355880c_@@_KPEBG2@Z; std::wstring::_Reallocate_grow_by<_lambda_c5c7986eab02a925bb28d3483355880c_,unsigned __int64,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c5c7986eab02a925bb28d3483355880c_,unsigned __int64,ushort const *,unsigned __int64)
0x18002516c  mov     rcx, rax
0x18002516f  xorps   xmm0, xmm0
0x180025172  movups  xmmword ptr [rbp+57h+lpSubKey], xmm0
0x180025176  xorps   xmm1, xmm1
0x180025179  movdqu  [rbp+57h+var_60], xmm1
0x18002517e  movups  xmm0, xmmword ptr [rcx]
0x180025181  movups  xmmword ptr [rbp+57h+lpSubKey], xmm0
0x180025185  movups  xmm1, xmmword ptr [rcx+10h]
0x180025189  movups  [rbp+57h+var_60], xmm1
0x18002518d  mov     [rcx+10h], r12
0x180025191  mov     qword ptr [rcx+18h], 7
0x180025199  mov     [rcx], r12w
0x18002519d  lea     rcx, [rbp+57h+Src]; void *
0x1800251a1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800251a6  nop
0x1800251a7  mov     [rbp+57h+var_A0], 0Fh
0x1800251ae  mov     [r15], r12
0x1800251b1  lea     rdx, [rbp+57h+lpSubKey]
0x1800251b5  cmp     qword ptr [rbp+57h+var_60+8], 7
0x1800251ba  cmova   rdx, [rbp+57h+lpSubKey]; lpSubKey
0x1800251bf  mov     [rsp+0F0h+lpdwDisposition], r12; lpdwDisposition
0x1800251c4  mov     [rsp+0F0h+phkResult], r15; phkResult
0x1800251c9  mov     [rsp+0F0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1800251ce  mov     [rsp+0F0h+samDesired], 106h; samDesired
0x1800251d6  mov     [rsp+0F0h+dwOptions], 1; unsigned int
0x1800251de  xor     r9d, r9d; lpClass
0x1800251e1  xor     r8d, r8d; Reserved
0x1800251e4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800251eb  call    cs:__imp_RegCreateKeyExW
0x1800251f1  mov     rcx, [rbp+5Fh]; this
0x1800251f5  test    eax, eax
0x1800251f7  jnz     short loc_180025225
0x1800251f9  lea     rcx, [rbp+57h+lpSubKey]; void *
0x1800251fd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180025202  mov     rax, r15
0x180025205  mov     rcx, [rbp+57h+var_50]
0x180025209  xor     rcx, rsp; StackCookie
0x18002520c  call    __security_check_cookie
0x180025211  add     rsp, 0B8h
0x180025218  pop     r15
0x18002521a  pop     r14
0x18002521c  pop     r13
0x18002521e  pop     r12
0x180025220  pop     rdi
0x180025221  pop     rsi
0x180025222  pop     rbx
0x180025223  pop     rbp
0x180025224  retn
0x180025225  mov     r9d, eax; char *
0x180025228  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\SessionI"...
0x18002522f  mov     edx, 32h ; '2'; void *
0x180025234  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
