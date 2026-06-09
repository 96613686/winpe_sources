# CGrepWdsResolver::GetRemoteIndexConfigForItem(IShellItem *,_GUID const &,void * *)

- ea: `0x1800999a0`
- end: `0x180099be9`
- name: `?GetRemoteIndexConfigForItem@CGrepWdsResolver@@UEAAJPEAUIShellItem@@AEBU_GUID@@PEAPEAX@Z`
- size: `585`
- prototype: `__int64 __fastcall(CGrepWdsResolver *__hidden this, struct IShellItem *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180006fb8`
- `0x180015588`
- `0x18002da80`
- `0x18003cdc8`
- `0x18003d6b0`
- `0x18003ed00`
- `0x18005de90`
- `0x18006c5c8`
- `0x180071dc0`
- `0x1800999a0`
- `0x1800e4c10`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800999f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180099a29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180099ac7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180099aeb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180099ba6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180099bb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180099bbe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800999f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180099a29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180099ac7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180099aeb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180099ba6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180099bb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180099bbe`
- `api-ms-win-core-path-l1-1-0!PathIsUNCEx` at `0x180099a58`
- `api-ms-win-core-path-l1-1-0!PathIsUNCEx` at `0x180099a58`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x180099a6f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x180099a6f`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CGrepWdsResolver::GetRemoteIndexConfigForItem(
        CGrepWdsResolver *this,
        struct IShellItem *a2,
        const struct _GUID *a3,
        void **a4)
{
  HRESULT (__stdcall *GetDisplayName)(IShellItem *, SIGDN, LPWSTR *); // rbx
  int v9; // ebx
  LPCWSTR *v10; // rdi
  PWSTR v11; // rax
  int v12; // eax
  unsigned __int64 v13; // rax
  PCWSTR ppszServer; // [rsp+40h] [rbp-C0h] BYREF
  void *v16; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  PCWSTR pszStr; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpLocalPath[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v20[2104]; // [rsp+70h] [rbp-90h] BYREF

  *a4 = 0;
  lpLocalPath[0] = 0;
  GetDisplayName = a2->lpVtbl->GetDisplayName;
  CoTaskMemFree(0);
  v9 = ((__int64 (__fastcall *)(struct IShellItem *, __int64, LPCWSTR *))GetDisplayName)(a2, 2147647488LL, lpLocalPath);
  if ( v9 >= 0 )
  {
    *((_DWORD *)this + 8) = 1;
    v10 = (LPCWSTR *)((char *)this + 576);
    CoTaskMemFree(*((LPVOID *)this + 72));
    v9 = PathConvertToUNC(lpLocalPath[0], (unsigned __int16 **)this + 72);
    if ( v9 >= 0 )
    {
      v9 = -2147024809;
      ppszServer = 0;
      if ( PathIsUNCEx(*v10, &ppszServer) )
      {
        v11 = StrChrW(ppszServer, 0x5Cu);
        if ( v11 )
        {
          v13 = v11 - ppszServer;
          if ( !v13 )
            goto LABEL_18;
          v12 = StringCchCopyNW((unsigned __int16 *)this + 26, 0x104u, ppszServer, v13);
        }
        else
        {
          if ( !*ppszServer )
            goto LABEL_18;
          v12 = StringCchCopyW((unsigned __int16 *)this + 26, 0x104u, ppszServer);
        }
        v9 = v12;
        if ( v12 >= 0 )
        {
          pszStr = 0;
          CoTaskMemFree(0);
          v9 = PathConvertToIndexerUNC(*v10, (unsigned __int16 **)&pszStr);
          if ( v9 >= 0 )
          {
            pv = 0;
            CoTaskMemFree(0);
            v9 = ScopeStrEscapeValue(pszStr, (unsigned __int16 **)&pv);
            if ( v9 >= 0 )
            {
              v9 = StringCchPrintfW(v20, 0x834u, L"Scope = '%s'", pv);
              if ( v9 >= 0 )
              {
                LODWORD(ppszServer) = 0;
                v16 = 0;
                v9 = CGrepWdsResolver::_CreateWDSConfigFromScopeString(
                       (unsigned __int16 *)this - 4,
                       v20,
                       L"SystemIndex",
                       1,
                       0,
                       &ppszServer,
                       &GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9,
                       &v16);
                if ( v9 >= 0 )
                  v9 = (*(__int64 (__fastcall **)(void *, _QWORD, const struct _GUID *, void **))(*(_QWORD *)v16 + 32LL))(
                         v16,
                         0,
                         a3,
                         a4);
                ATL::CComPtr<IResultShape>::~CComPtr<IResultShape>(&v16);
              }
            }
            CoTaskMemFree(pv);
          }
          CoTaskMemFree((LPVOID)pszStr);
        }
      }
    }
  }
LABEL_18:
  CoTaskMemFree((LPVOID)lpLocalPath[0]);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800999a0  push    rbp
0x1800999a2  push    rbx
0x1800999a3  push    rsi
0x1800999a4  push    rdi
0x1800999a5  push    r12
0x1800999a7  push    r13
0x1800999a9  push    r14
0x1800999ab  push    r15
0x1800999ad  lea     rbp, [rsp-0FF8h]
0x1800999b5  mov     eax, 10F8h
0x1800999ba  call    _alloca_probe
0x1800999bf  sub     rsp, rax
0x1800999c2  mov     rax, cs:__security_cookie
0x1800999c9  xor     rax, rsp
0x1800999cc  mov     [rbp+1030h+var_50], rax
0x1800999d3  mov     r15, r9
0x1800999d6  mov     r12, r8
0x1800999d9  mov     rdi, rdx
0x1800999dc  mov     rsi, rcx
0x1800999df  xor     r13d, r13d
0x1800999e2  mov     [r9], r13
0x1800999e5  mov     [rsp+1130h+lpLocalPath], r13
0x1800999ea  mov     rax, [rdx]
0x1800999ed  mov     rbx, [rax+28h]
0x1800999f1  xor     ecx, ecx; pv
0x1800999f3  call    cs:__imp_CoTaskMemFree
0x1800999f9  lea     r8, [rsp+1130h+lpLocalPath]
0x1800999fe  mov     edx, 80028000h
0x180099a03  mov     rcx, rdi
0x180099a06  mov     rax, rbx
0x180099a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099a0e  mov     ebx, eax
0x180099a10  test    eax, eax
0x180099a12  js      loc_180099BB9
0x180099a18  mov     dword ptr [rsi+20h], 1
0x180099a1f  lea     rdi, [rsi+240h]
0x180099a26  mov     rcx, [rdi]; pv
0x180099a29  call    cs:__imp_CoTaskMemFree
0x180099a2f  mov     rdx, rdi; unsigned __int16 **
0x180099a32  mov     rcx, [rsp+1130h+lpLocalPath]; lpLocalPath
0x180099a37  call    ?PathConvertToUNC@@YAJPEBGPEAPEAG@Z; PathConvertToUNC(ushort const *,ushort * *)
0x180099a3c  mov     ebx, eax
0x180099a3e  test    eax, eax
0x180099a40  js      loc_180099BB9
0x180099a46  mov     ebx, 80070057h
0x180099a4b  mov     [rsp+1130h+ppszServer], r13
0x180099a50  lea     rdx, [rsp+1130h+ppszServer]; ppszServer
0x180099a55  mov     rcx, [rdi]; pszPath
0x180099a58  call    cs:__imp_PathIsUNCEx
0x180099a5e  test    eax, eax
0x180099a60  jz      loc_180099BB9
0x180099a66  lea     edx, [r13+5Ch]; wMatch
0x180099a6a  mov     rcx, [rsp+1130h+ppszServer]; pszStart
0x180099a6f  call    cs:__imp_StrChrW
0x180099a75  mov     r8, [rsp+1130h+ppszServer]; unsigned __int16 *
0x180099a7a  test    rax, rax
0x180099a7d  jnz     short loc_180099A99
0x180099a7f  cmp     [r8], r13w
0x180099a83  jz      loc_180099BB9
0x180099a89  mov     edx, 104h; unsigned __int64
0x180099a8e  lea     rcx, [rsi+34h]; unsigned __int16 *
0x180099a92  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180099a97  jmp     short loc_180099AB6
0x180099a99  sub     rax, r8
0x180099a9c  sar     rax, 1
0x180099a9f  jz      loc_180099BB9
0x180099aa5  mov     r9, rax; unsigned __int64
0x180099aa8  mov     edx, 104h; unsigned __int64
0x180099aad  lea     rcx, [rsi+34h]; unsigned __int16 *
0x180099ab1  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180099ab6  mov     ebx, eax
0x180099ab8  test    eax, eax
0x180099aba  js      loc_180099BB9
0x180099ac0  mov     [rsp+1130h+pszStr], r13
0x180099ac5  xor     ecx, ecx; pv
0x180099ac7  call    cs:__imp_CoTaskMemFree
0x180099acd  lea     rdx, [rsp+1130h+pszStr]; unsigned __int16 **
0x180099ad2  mov     rcx, [rdi]; lpLocalPath
0x180099ad5  call    ?PathConvertToIndexerUNC@@YAJPEBGPEAPEAG@Z; PathConvertToIndexerUNC(ushort const *,ushort * *)
0x180099ada  mov     ebx, eax
0x180099adc  test    eax, eax
0x180099ade  js      loc_180099BAD
0x180099ae4  mov     [rsp+1130h+pv], r13
0x180099ae9  xor     ecx, ecx; pv
0x180099aeb  call    cs:__imp_CoTaskMemFree
0x180099af1  lea     rdx, [rsp+1130h+pv]; unsigned __int16 **
0x180099af6  mov     rcx, [rsp+1130h+pszStr]; pszStr
0x180099afb  call    ?ScopeStrEscapeValue@@YAJPEBGPEAPEAG@Z; ScopeStrEscapeValue(ushort const *,ushort * *)
0x180099b00  mov     ebx, eax
0x180099b02  test    eax, eax
0x180099b04  js      loc_180099BA1
0x180099b0a  mov     r9, [rsp+1130h+pv]
0x180099b0f  lea     r8, aScopeS; "Scope = '%s'"
0x180099b16  mov     edx, 834h; unsigned __int64
0x180099b1b  lea     rcx, [rsp+1130h+var_10C0]; unsigned __int16 *
0x180099b20  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180099b25  mov     ebx, eax
0x180099b27  test    eax, eax
0x180099b29  js      short loc_180099BA1
0x180099b2b  mov     dword ptr [rsp+1130h+ppszServer], r13d
0x180099b30  mov     [rsp+1130h+var_10E8], r13
0x180099b35  lea     rax, [rsp+1130h+var_10E8]
0x180099b3a  mov     [rsp+1130h+var_10F8], rax
0x180099b3f  lea     rax, _GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9
0x180099b46  mov     [rsp+1130h+var_1100], rax
0x180099b4b  lea     rax, [rsp+1130h+ppszServer]
0x180099b50  mov     [rsp+1130h+var_1108], rax
0x180099b55  mov     [rsp+1130h+var_1110], r13
0x180099b5a  mov     r9d, 1
0x180099b60  lea     r8, aSystemindex; "SystemIndex"
0x180099b67  lea     rdx, [rsp+1130h+var_10C0]
0x180099b6c  lea     rcx, [rsi-8]
0x180099b70  call    ?_CreateWDSConfigFromScopeString@CGrepWdsResolver@@AEAAJPEBG0W4REUSEWHERE_MODE@@PEAUICondition@@PEAHAEBU_GUID@@PEAPEAX@Z; CGrepWdsResolver::_CreateWDSConfigFromScopeString(ushort const *,ushort const *,REUSEWHERE_MODE,ICondition *,int *,_GUID const &,void * *)
0x180099b75  mov     ebx, eax
0x180099b77  test    eax, eax
0x180099b79  js      short loc_180099B96
0x180099b7b  mov     rcx, [rsp+1130h+var_10E8]
0x180099b80  mov     rax, [rcx]
0x180099b83  mov     r9, r15
0x180099b86  mov     r8, r12
0x180099b89  xor     edx, edx
0x180099b8b  mov     rax, [rax+20h]
0x180099b8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099b94  mov     ebx, eax
0x180099b96  lea     rcx, [rsp+1130h+var_10E8]
0x180099b9b  call    ??1?$CComPtr@UIResultShape@@@ATL@@QEAA@XZ; ATL::CComPtr<IResultShape>::~CComPtr<IResultShape>(void)
0x180099ba0  nop
0x180099ba1  mov     rcx, [rsp+1130h+pv]; pv
0x180099ba6  call    cs:__imp_CoTaskMemFree
0x180099bac  nop
0x180099bad  mov     rcx, [rsp+1130h+pszStr]; pv
0x180099bb2  call    cs:__imp_CoTaskMemFree
0x180099bb8  nop
0x180099bb9  mov     rcx, [rsp+1130h+lpLocalPath]; pv
0x180099bbe  call    cs:__imp_CoTaskMemFree
0x180099bc4  mov     eax, ebx
0x180099bc6  mov     rcx, [rbp+1030h+var_50]
0x180099bcd  xor     rcx, rsp; StackCookie
0x180099bd0  call    __security_check_cookie
0x180099bd5  add     rsp, 10F8h
0x180099bdc  pop     r15
0x180099bde  pop     r14
0x180099be0  pop     r13
0x180099be2  pop     r12
0x180099be4  pop     rdi
0x180099be5  pop     rsi
0x180099be6  pop     rbx
0x180099be7  pop     rbp
0x180099be8  retn
```
