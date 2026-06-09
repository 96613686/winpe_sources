# ClientProxyManager::GetTable(tagSAFEARRAY * *)

- ea: `0x180200270`
- end: `0x18020049a`
- name: `?GetTable@ClientProxyManager@@UEAAJPEAPEAUtagSAFEARRAY@@@Z`
- size: `554`
- prototype: `__int64 __fastcall(ClientProxyManager *__hidden this, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x18002f580`
- `0x18003ea38`
- `0x180069c44`
- `0x180097d20`
- `0x180098570`
- `0x180099c50`
- `0x18009ab54`
- `0x1800b3338`
- `0x1800c20c0`
- `0x1801e8320`
- `0x180200270`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18020035a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18020035a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1802003ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180200452`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1802003ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180200452`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1802003c7`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1802003c7`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180200412`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180200412`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18020036b`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18020036b`

## string_xrefs

- `0x18020032d`: `onecore\windows\accessibletech\uiautomationcore\clientproxymanager.cpp`
- `0x180200392`: `onecore\windows\accessibletech\uiautomationcore\clientproxymanager.cpp`

## pseudocode

```c
__int64 __fastcall ClientProxyManager::GetTable(ClientProxyManager *this, struct tagSAFEARRAY **a2)
{
  unsigned int v4; // esi
  __int64 v5; // rdx
  __int64 v6; // r9
  int v7; // eax
  SAFEARRAY *Vector; // rax
  struct tagSAFEARRAY *v9; // rbx
  __int64 v10; // rdx
  __int64 v11; // r9
  HRESULT v12; // eax
  _QWORD *v13; // r12
  __int64 i; // rsi
  __int64 v15; // rcx
  HRESULT v16; // eax
  int v18[2]; // [rsp+20h] [rbp-E0h] BYREF
  void *ppvData; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v20[80]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v21[336]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  ClientApiCallTrace::ClientApiCallTrace(
    (ClientApiCallTrace *)v21,
    "ClientProxyManager::GetTable",
    this,
    (HINSTANCE)retaddr);
  ClientApiErrorTrace::ClientApiErrorTrace(
    (ClientApiErrorTrace *)v20,
    "ClientProxyManager::GetTable",
    this,
    (HINSTANCE)retaddr);
  if ( !BasicUiaUtils::IsOneCore() )
  {
    if ( !a2 )
    {
      v7 = Error::ClientApiError(L"IUIAutomationProxyFactoryMapping::GetTable", L"table", -2147467261, 500);
      v4 = v7;
      if ( v7 < 0 )
      {
        v6 = (unsigned int)v7;
        v5 = 153;
        goto LABEL_6;
      }
      ClientApiCallTrace::Stop((ClientApiCallTrace *)v21);
LABEL_18:
      v4 = 0;
      goto LABEL_19;
    }
    *a2 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    Vector = SafeArrayCreateVector(0xDu, 0, *((_DWORD *)this + 13));
    *(_QWORD *)v18 = Vector;
    v9 = Vector;
    if ( Vector )
    {
      ppvData = 0;
      v12 = SafeArrayAccessData(Vector, &ppvData);
      v4 = v12;
      if ( v12 >= 0 )
      {
        v13 = (_QWORD *)*((_QWORD *)this + 8);
        for ( i = 0; (unsigned int)i < *((_DWORD *)this + 13); i = (unsigned int)(i + 1) )
        {
          v15 = v13[2];
          *((_QWORD *)ppvData + i) = v15;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
          v13 = (_QWORD *)*v13;
        }
        v16 = SafeArrayUnaccessData(v9);
        v4 = v16;
        if ( v16 >= 0 )
        {
          *a2 = v9;
          *((_BYTE *)this + 88) = 1;
          *(_QWORD *)v18 = 0;
          ClientApiCallTrace::Stop((ClientApiCallTrace *)v21);
          AutoCleanupInfo<tagSAFEARRAY *>::SafeRelease(v18);
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
          goto LABEL_18;
        }
        v11 = (unsigned int)v16;
        v10 = 174;
      }
      else
      {
        v11 = (unsigned int)v12;
        v10 = 162;
      }
    }
    else
    {
      v4 = -2147024882;
      v10 = 159;
      v11 = 2147942414LL;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\clientproxymanager.cpp",
      (const char *)v11,
      v18[0]);
    AutoCleanupInfo<tagSAFEARRAY *>::SafeRelease(v18);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    goto LABEL_19;
  }
  v4 = -2147467263;
  v5 = 149;
  v6 = 2147500033LL;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\clientproxymanager.cpp",
    (const char *)v6,
    v18[0]);
LABEL_19:
  ClientApiErrorTrace::~ClientApiErrorTrace((ClientApiErrorTrace *)v20);
  UiaProvider::ClientApiCallActivity::~ClientApiCallActivity((UiaProvider::ClientApiCallActivity *)v21);
  return v4;
}

```

## disassembly

```asm
0x180200270  mov     [rsp-8+arg_10], rbx
0x180200275  mov     [rsp-8+arg_18], rsi
0x18020027a  push    rbp
0x18020027b  push    rdi
0x18020027c  push    r12
0x18020027e  push    r14
0x180200280  push    r15
0x180200282  lea     rbp, [rsp-0E0h]
0x18020028a  sub     rsp, 1E0h
0x180200291  mov     rax, cs:__security_cookie
0x180200298  xor     rax, rsp
0x18020029b  mov     [rbp+100h+var_30], rax
0x1802002a2  mov     rbx, [rbp+108h]
0x1802002a9  mov     r15, rdx
0x1802002ac  mov     r14, rcx
0x1802002af  lea     rdx, aClientproxyman_5; "ClientProxyManager::GetTable"
0x1802002b6  mov     r8, rcx; void *
0x1802002b9  mov     r9, rbx; void *
0x1802002bc  lea     rcx, [rbp+100h+var_180]; this
0x1802002c0  call    ??0ClientApiCallTrace@@QEAA@PEBDPEBX1@Z; ClientApiCallTrace::ClientApiCallTrace(char const *,void const *,void const *)
0x1802002c5  mov     r9, rbx; void *
0x1802002c8  lea     rdx, aClientproxyman_5; "ClientProxyManager::GetTable"
0x1802002cf  mov     r8, r14; void *
0x1802002d2  lea     rcx, [rsp+200h+var_1D0]; this
0x1802002d7  call    ??0ClientApiErrorTrace@@QEAA@PEBDPEBX1@Z; ClientApiErrorTrace::ClientApiErrorTrace(char const *,void const *,void const *)
0x1802002dc  call    ?IsOneCore@BasicUiaUtils@@SA_NXZ; BasicUiaUtils::IsOneCore(void)
0x1802002e1  test    al, al
0x1802002e3  jz      short loc_1802002F4
0x1802002e5  mov     esi, 80004001h
0x1802002ea  mov     edx, 95h
0x1802002ef  mov     r9d, esi
0x1802002f2  jmp     short loc_180200326
0x1802002f4  test    r15, r15
0x1802002f7  jnz     short loc_18020034C
0x1802002f9  mov     r9d, 1F4h; int
0x1802002ff  lea     rdx, aTable; "table"
0x180200306  mov     r8d, 80004003h; int
0x18020030c  lea     rcx, aIuiautomationp_7; "IUIAutomationProxyFactoryMapping::GetTa"...
0x180200313  call    ?ClientApiError@Error@@SAJPEBG0JH@Z; Error::ClientApiError(ushort const *,ushort const *,long,int)
0x180200318  mov     esi, eax
0x18020031a  test    eax, eax
0x18020031c  jns     short loc_18020033E
0x18020031e  mov     r9d, eax; char *
0x180200321  mov     edx, 99h; void *
0x180200326  mov     rcx, [rbp+108h]; this
0x18020032d  lea     r8, aOnecoreWindows_185; "onecore\\windows\\accessibletech\\uiaut"...
0x180200334  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180200339  jmp     loc_18020045A
0x18020033e  lea     rcx, [rbp+100h+var_180]; this
0x180200342  call    ?Stop@ClientApiCallTrace@@QEAAXXZ; ClientApiCallTrace::Stop(void)
0x180200347  jmp     loc_180200458
0x18020034c  lea     rdi, [r14+8]
0x180200350  mov     qword ptr [r15], 0
0x180200357  mov     rcx, rdi; lpCriticalSection
0x18020035a  call    cs:__imp_EnterCriticalSection
0x180200360  mov     r8d, [r14+34h]; cElements
0x180200364  mov     ecx, 0Dh; vt
0x180200369  xor     edx, edx; lLbound
0x18020036b  call    cs:__imp_SafeArrayCreateVector
0x180200371  mov     qword ptr [rsp+200h+var_1E0], rax; int
0x180200376  mov     rbx, rax
0x180200379  test    rax, rax
0x18020037c  jnz     short loc_1802003B6
0x18020037e  mov     esi, 8007000Eh
0x180200383  mov     edx, 9Fh; void *
0x180200388  mov     r9d, esi; char *
0x18020038b  mov     rcx, [rbp+108h]; this
0x180200392  lea     r8, aOnecoreWindows_185; "onecore\\windows\\accessibletech\\uiaut"...
0x180200399  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020039e  lea     rcx, [rsp+200h+var_1E0]
0x1802003a3  call    ?SafeRelease@?$AutoCleanupInfo@PEAUtagSAFEARRAY@@@@SAXAEAPEAUtagSAFEARRAY@@@Z; AutoCleanupInfo<tagSAFEARRAY *>::SafeRelease(tagSAFEARRAY * &)
0x1802003a8  mov     rcx, rdi; lpCriticalSection
0x1802003ab  call    cs:__imp_LeaveCriticalSection
0x1802003b1  jmp     loc_18020045A
0x1802003b6  lea     rdx, [rsp+200h+ppvData]; ppvData
0x1802003bb  mov     [rsp+200h+ppvData], 0
0x1802003c4  mov     rcx, rbx; psa
0x1802003c7  call    cs:__imp_SafeArrayAccessData
0x1802003cd  mov     esi, eax
0x1802003cf  test    eax, eax
0x1802003d1  jns     short loc_1802003DD
0x1802003d3  mov     r9d, eax
0x1802003d6  mov     edx, 0A2h
0x1802003db  jmp     short loc_18020038B
0x1802003dd  mov     r12, [r14+40h]
0x1802003e1  xor     esi, esi
0x1802003e3  cmp     [r14+34h], esi
0x1802003e7  jbe     short loc_18020040F
0x1802003e9  mov     rax, [rsp+200h+ppvData]
0x1802003ee  mov     rcx, [r12+10h]
0x1802003f3  mov     [rax+rsi*8], rcx
0x1802003f7  mov     rax, [rcx]
0x1802003fa  mov     rax, [rax+8]
0x1802003fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180200403  mov     r12, [r12]
0x180200407  inc     esi
0x180200409  cmp     esi, [r14+34h]
0x18020040d  jb      short loc_1802003E9
0x18020040f  mov     rcx, rbx; psa
0x180200412  call    cs:__imp_SafeArrayUnaccessData
0x180200418  mov     esi, eax
0x18020041a  test    eax, eax
0x18020041c  jns     short loc_18020042B
0x18020041e  mov     r9d, eax
0x180200421  mov     edx, 0AEh
0x180200426  jmp     loc_18020038B
0x18020042b  mov     [r15], rbx
0x18020042e  lea     rcx, [rbp+100h+var_180]; this
0x180200432  mov     byte ptr [r14+58h], 1
0x180200437  mov     qword ptr [rsp+200h+var_1E0], 0
0x180200440  call    ?Stop@ClientApiCallTrace@@QEAAXXZ; ClientApiCallTrace::Stop(void)
0x180200445  lea     rcx, [rsp+200h+var_1E0]
0x18020044a  call    ?SafeRelease@?$AutoCleanupInfo@PEAUtagSAFEARRAY@@@@SAXAEAPEAUtagSAFEARRAY@@@Z; AutoCleanupInfo<tagSAFEARRAY *>::SafeRelease(tagSAFEARRAY * &)
0x18020044f  mov     rcx, rdi; lpCriticalSection
0x180200452  call    cs:__imp_LeaveCriticalSection
0x180200458  xor     esi, esi
0x18020045a  lea     rcx, [rsp+200h+var_1D0]; this
0x18020045f  call    ??1ClientApiErrorTrace@@QEAA@XZ; ClientApiErrorTrace::~ClientApiErrorTrace(void)
0x180200464  lea     rcx, [rbp+100h+var_180]; this
0x180200468  call    ??1ClientApiCallActivity@UiaProvider@@QEAA@XZ; UiaProvider::ClientApiCallActivity::~ClientApiCallActivity(void)
0x18020046d  mov     eax, esi
0x18020046f  mov     rcx, [rbp+100h+var_30]
0x180200476  xor     rcx, rsp; StackCookie
0x180200479  call    __security_check_cookie
0x18020047e  lea     r11, [rsp+200h+var_20]
0x180200486  mov     rbx, [r11+40h]
0x18020048a  mov     rsi, [r11+48h]
0x18020048e  mov     rsp, r11
0x180200491  pop     r15
0x180200493  pop     r14
0x180200495  pop     r12
0x180200497  pop     rdi
0x180200498  pop     rbp
0x180200499  retn
```
