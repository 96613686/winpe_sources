# RoutingMgr::SetCustomProperties(_GUID const &,uint,uchar const *)

- ea: `0x180033f68`
- end: `0x1800341aa`
- name: `?SetCustomProperties@RoutingMgr@@QEAAJAEBU_GUID@@IPEBE@Z`
- size: `578`
- prototype: `int(RoutingMgr *__hidden this, const struct _GUID *, unsigned int, const unsigned __int8 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012240`

## callees

- `0x1800049a0`
- `0x180005858`
- `0x18000c964`
- `0x180013274`
- `0x180033f68`
- `0x18003ce74`
- `0x18007d3a0`
- `0x18007d434`
- `0x18007d804`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180034053`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180034053`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034181`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034181`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033ff9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033ff9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800340a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800340a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800340b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800340b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800340b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003413a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800340b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003413a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180034110`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180034110`

## string_xrefs

- `0x180033fba`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingmgr.cpp`
- `0x180034164`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingmgr.cpp`
- `0x18003414e`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingregistrationstore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall RoutingMgr::SetCustomProperties(
        struct _RTL_CRITICAL_SECTION *this,
        const struct _GUID *a2,
        unsigned int a3,
        const unsigned __int8 *a4)
{
  signed int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rdx
  unsigned int v11; // edx
  int v12; // eax
  int v13; // eax
  int lpData; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v17[2]; // [rsp+38h] [rbp-C8h] BYREF
  char v18; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v19[3]; // [rsp+50h] [rbp-B0h] BYREF
  char v20; // [rsp+68h] [rbp-98h]
  _BYTE v21[16]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v22[32]; // [rsp+80h] [rbp-80h] BYREF
  OLECHAR sz[40]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v24[144]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v8 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *, _BYTE *))this->DebugInfo->ProcessLocksList.Blink)(
         this,
         v24);
  if ( v8 >= 0 )
  {
    v8 = ValidateCustomProperties(a3, a4);
    if ( v8 < 0 )
    {
      v9 = 764;
      goto LABEL_3;
    }
    v19[2] = this + 2;
    EnterCriticalSection(this + 2);
    v20 = 1;
    if ( BYTE1(this[4].OwningThread) )
    {
      hKey = 0;
      memset_0(sz, 0, 0x4Eu);
      NfcRegPath::NfcRegPath((NfcRegPath *)v21, (const struct NfcRegistryLocation *)&qword_1800A1C18);
      if ( StringFromGUID2(a2, sz, 39) )
      {
        v17[0] = v24;
        v17[1] = sz;
        v19[0] = v17;
        v19[1] = &v18;
        NfcRegPath::AppendSubKeys(v21, v19);
        hKey = 0;
        v12 = NfcRegOpenKeyEx((const struct NfcRegistryLocation *)v21, v11, 0x2001Fu, &hKey);
        v8 = v12;
        if ( v12 > 0 )
          v8 = (unsigned __int16)v12 | 0x80070000;
        if ( v8 >= 0 )
        {
          v13 = RegSetValueExW(hKey, L"Properties", 0, 3u, a4, a3);
          if ( v13 > 0 )
            v13 = (unsigned __int16)v13 | 0x80070000;
          v8 = 0;
          if ( v13 < 0 )
            v8 = v13;
        }
      }
      else
      {
        v8 = -2147467259;
      }
      std::wstring::~wstring(v22);
      if ( hKey )
        RegCloseKey(hKey);
      if ( v8 >= 0 )
      {
        v8 = 0;
        goto LABEL_23;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x245,
        (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingregistrationstore.cpp",
        (const char *)(unsigned int)v8,
        lpData);
      v10 = 770;
    }
    else
    {
      v8 = -2147019873;
      v10 = 768;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingmgr.cpp",
      (const char *)(unsigned int)v8,
      lpData);
LABEL_23:
    LeaveCriticalSection(this + 2);
    return (unsigned int)v8;
  }
  v9 = 763;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingmgr.cpp",
    (const char *)(unsigned int)v8,
    lpData);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180033f68  push    rbp
0x180033f6a  push    rbx
0x180033f6b  push    rsi
0x180033f6c  push    rdi
0x180033f6d  push    r12
0x180033f6f  push    r14
0x180033f71  push    r15
0x180033f73  lea     rbp, [rsp-90h]
0x180033f7b  sub     rsp, 190h
0x180033f82  mov     rax, cs:__security_cookie
0x180033f89  xor     rax, rsp
0x180033f8c  mov     [rbp+0C0h+var_40], rax
0x180033f93  mov     r15, r9
0x180033f96  mov     r14d, r8d
0x180033f99  mov     r12, rdx
0x180033f9c  mov     rsi, rcx
0x180033f9f  mov     rax, [rcx]
0x180033fa2  lea     rdx, [rbp+0C0h+var_D0]
0x180033fa6  mov     rax, [rax+18h]
0x180033faa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033faf  mov     ebx, eax
0x180033fb1  test    eax, eax
0x180033fb3  jns     short loc_180033FD5
0x180033fb5  mov     edx, 2FBh; void *
0x180033fba  lea     r8, aOnecoreuapDsNf_15; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x180033fc1  mov     r9d, ebx; char *
0x180033fc4  mov     rcx, [rbp+0C8h]; this
0x180033fcb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033fd0  jmp     loc_180034187
0x180033fd5  mov     rdx, r15; unsigned __int8 *
0x180033fd8  mov     ecx, r14d; unsigned int
0x180033fdb  call    ?ValidateCustomProperties@@YAJIPEBE@Z; ValidateCustomProperties(uint,uchar const *)
0x180033fe0  mov     ebx, eax
0x180033fe2  test    eax, eax
0x180033fe4  jns     short loc_180033FED
0x180033fe6  mov     edx, 2FCh
0x180033feb  jmp     short loc_180033FBA
0x180033fed  lea     rdi, [rsi+50h]
0x180033ff1  mov     [rsp+1C0h+var_160], rdi
0x180033ff6  mov     rcx, rdi; lpCriticalSection
0x180033ff9  call    cs:__imp_EnterCriticalSection
0x180033fff  mov     [rsp+1C0h+var_158], 1
0x180034004  cmp     byte ptr [rsi+0B1h], 0
0x18003400b  jnz     short loc_18003401C
0x18003400d  mov     ebx, 8007139Fh
0x180034012  mov     edx, 300h
0x180034017  jmp     loc_180034164
0x18003401c  mov     [rsp+1C0h+hKey], 0
0x180034025  xor     edx, edx; Val
0x180034027  lea     r8d, [rdx+4Eh]; Size
0x18003402b  lea     rcx, [rbp+0C0h+sz]; void *
0x18003402f  call    memset_0
0x180034034  lea     rdx, qword_1800A1C18; struct NfcRegistryLocation *
0x18003403b  lea     rcx, [rsp+1C0h+var_150]; this
0x180034040  call    ??0NfcRegPath@@QEAA@AEBUNfcRegistryLocation@@@Z; NfcRegPath::NfcRegPath(NfcRegistryLocation const &)
0x180034045  nop
0x180034046  mov     r8d, 27h ; '''; cchMax
0x18003404c  lea     rdx, [rbp+0C0h+sz]; lpsz
0x180034050  mov     rcx, r12; rguid
0x180034053  call    cs:__imp_StringFromGUID2
0x180034059  test    eax, eax
0x18003405b  jnz     short loc_180034067
0x18003405d  mov     ebx, 80004005h
0x180034062  jmp     loc_180034126
0x180034067  lea     rax, [rbp+0C0h+var_D0]
0x18003406b  mov     [rsp+1C0h+var_188], rax
0x180034070  lea     rax, [rbp+0C0h+sz]
0x180034074  mov     [rsp+1C0h+var_180], rax
0x180034079  lea     rax, [rsp+1C0h+var_188]
0x18003407e  mov     [rsp+1C0h+var_170], rax
0x180034083  lea     rax, [rsp+1C0h+var_178]
0x180034088  mov     [rsp+1C0h+var_168], rax
0x18003408d  lea     rdx, [rsp+1C0h+var_170]
0x180034092  lea     rcx, [rsp+1C0h+var_150]
0x180034097  call    ?AppendSubKeys@NfcRegPath@@QEAAXV?$initializer_list@PEBG@std@@@Z; NfcRegPath::AppendSubKeys(std::initializer_list<ushort const *>)
0x18003409c  mov     rsi, [rsp+1C0h+hKey]
0x1800340a1  test    rsi, rsi
0x1800340a4  jz      short loc_1800340BF
0x1800340a6  call    cs:__imp_GetLastError
0x1800340ac  mov     ebx, eax
0x1800340ae  mov     rcx, rsi; hKey
0x1800340b1  call    cs:__imp_RegCloseKey
0x1800340b7  mov     ecx, ebx; dwErrCode
0x1800340b9  call    cs:__imp_SetLastError
0x1800340bf  mov     [rsp+1C0h+hKey], 0
0x1800340c8  lea     r9, [rsp+1C0h+hKey]; HKEY *
0x1800340cd  mov     r8d, 2001Fh; unsigned int
0x1800340d3  lea     rcx, [rsp+1C0h+var_150]; struct NfcRegistryLocation *
0x1800340d8  call    ?NfcRegOpenKeyEx@@YAJAEBUNfcRegistryLocation@@KKPEAPEAUHKEY__@@@Z; NfcRegOpenKeyEx(NfcRegistryLocation const &,ulong,ulong,HKEY__ * *)
0x1800340dd  mov     ebx, eax
0x1800340df  mov     esi, 80070000h
0x1800340e4  test    eax, eax
0x1800340e6  jle     short loc_1800340ED
0x1800340e8  movzx   ebx, ax
0x1800340eb  or      ebx, esi
0x1800340ed  test    ebx, ebx
0x1800340ef  js      short loc_180034126
0x1800340f1  mov     [rsp+1C0h+cbData], r14d; cbData
0x1800340f6  mov     [rsp+1C0h+lpData], r15; int
0x1800340fb  mov     r9d, 3; dwType
0x180034101  xor     r8d, r8d; Reserved
0x180034104  lea     rdx, ValueName; "Properties"
0x18003410b  mov     rcx, [rsp+1C0h+hKey]; hKey
0x180034110  call    cs:__imp_RegSetValueExW
0x180034116  test    eax, eax
0x180034118  jle     short loc_18003411F
0x18003411a  movzx   eax, ax
0x18003411d  or      eax, esi
0x18003411f  xor     ebx, ebx
0x180034121  test    eax, eax
0x180034123  cmovs   ebx, eax
0x180034126  lea     rcx, [rbp+0C0h+var_140]
0x18003412a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003412f  nop
0x180034130  mov     rcx, [rsp+1C0h+hKey]; hKey
0x180034135  test    rcx, rcx
0x180034138  jz      short loc_180034140
0x18003413a  call    cs:__imp_RegCloseKey
0x180034140  test    ebx, ebx
0x180034142  jns     short loc_18003417C
0x180034144  mov     rcx, [rbp+0C8h]; this
0x18003414b  mov     r9d, ebx; char *
0x18003414e  lea     r8, aOnecoreuapDsNf_23; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x180034155  mov     edx, 245h; void *
0x18003415a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003415f  mov     edx, 302h; void *
0x180034164  lea     r8, aOnecoreuapDsNf_15; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x18003416b  mov     r9d, ebx; char *
0x18003416e  mov     rcx, [rbp+0C8h]; this
0x180034175  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003417a  jmp     short loc_18003417E
0x18003417c  xor     ebx, ebx
0x18003417e  mov     rcx, rdi; lpCriticalSection
0x180034181  call    cs:__imp_LeaveCriticalSection
0x180034187  mov     eax, ebx
0x180034189  mov     rcx, [rbp+0C0h+var_40]
0x180034190  xor     rcx, rsp; StackCookie
0x180034193  call    __security_check_cookie
0x180034198  add     rsp, 190h
0x18003419f  pop     r15
0x1800341a1  pop     r14
0x1800341a3  pop     r12
0x1800341a5  pop     rdi
0x1800341a6  pop     rsi
0x1800341a7  pop     rbx
0x1800341a8  pop     rbp
0x1800341a9  retn
```
