# CARPUninstallerProxy::UninstallCBSPackage(ushort const *,HWND__ *,int,ulong *)

- ea: `0x18001d980`
- end: `0x18001db86`
- name: `?UninstallCBSPackage@CARPUninstallerProxy@@UEAAJPEBGPEAUHWND__@@HPEAK@Z`
- size: `518`
- prototype: `int(CARPUninstallerProxy *__hidden this, const unsigned __int16 *, HWND, int, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800108d4`
- `0x180014548`
- `0x18001d668`
- `0x18001d980`
- `0x18001dd4c`
- `0x18001ddf8`
- `0x180055d30`
- `0x180055da0`
- `0x180059010`

## import_xrefs

- `SHELL32!__imp_RestartDialogEx` at `0x18001dacd`
- `SHELL32!__imp_RestartDialogEx` at `0x18001dacd`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18001daaf`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18001daaf`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001da57`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001da57`

## pseudocode

```c
__int64 __fastcall CARPUninstallerProxy::UninstallCBSPackage(
        struct ICbsSession7 **this,
        const unsigned __int16 *a2,
        HWND a3,
        int a4,
        const WCHAR *lpString1)
{
  CARPUninstallerProxy *v5; // rbx
  int v10; // esi
  const WCHAR *v11; // r14
  int v12; // r13d
  __int64 v13; // r8
  ULONG_PTR ulCookie; // [rsp+80h] [rbp+8h] BYREF

  v5 = (CARPUninstallerProxy *)(this - 1);
  v10 = 0;
  if ( !this[1] )
    v10 = InitializeCBSSession(this + 1);
  v11 = lpString1;
  if ( lpString1 )
    *(_DWORD *)lpString1 = 0;
  ulCookie = 0;
  v12 = SHActivateContext(&ulCookie);
  if ( v10 >= 0 )
  {
    v10 = CARPUninstallerProxy::_PreInitiateChanges(v5, a2);
    if ( v10 >= 0 )
    {
      *((_DWORD *)this + 142) = 0;
      lpString1 = 0;
      if ( (*(int (__fastcall **)(struct ICbsSession7 *, __int64, const WCHAR **))(*(_QWORD *)this[2] + 32LL))(
             this[2],
             8,
             &lpString1) >= 0
        && CompareStringW(0x7Fu, 1u, lpString1, -1, L"Product", -1) == 2 )
      {
        *((_DWORD *)this + 142) = 1;
      }
      if ( a4 )
      {
        CARPUninstallerProxy::_InitializeProgressDialog(v5, a3);
        if ( *((int *)this + 9) < 0 )
        {
          v13 = (__int64)(this + 5);
          if ( !*((_WORD *)this + 20) )
            v13 = 501;
          ShellMessageBoxW(g_hinst, a3, (LPCWSTR)v13, (LPCWSTR)0x1F4, 0x10u);
        }
        if ( *((_DWORD *)this + 140) )
          RestartDialogEx(a3, 0, 2u, 0x20004u);
        (*(void (__fastcall **)(struct ICbsSession7 *, const WCHAR *))(*(_QWORD *)this[1] + 32LL))(this[1], v11);
        CReleasePtr<ICbsCustomInformation>::~CReleasePtr<ICbsCustomInformation>(this + 1);
        CReleasePtr<ICbsCustomInformation>::~CReleasePtr<ICbsCustomInformation>(this + 2);
        if ( *((_DWORD *)this + 141) )
          *((_DWORD *)this + 9) = -2147023673;
      }
      else
      {
        v10 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, CARPUninstallerProxy *))(**((_QWORD **)v5 + 3) + 88LL))(
                *((_QWORD *)v5 + 3),
                5,
                0,
                v5);
        if ( v10 >= 0 )
          (*(void (__fastcall **)(struct ICbsSession7 *, const WCHAR *))(*(_QWORD *)this[1] + 32LL))(this[1], v11);
        CReleasePtr<ICbsCustomInformation>::~CReleasePtr<ICbsCustomInformation>(this + 2);
        CReleasePtr<ICbsCustomInformation>::~CReleasePtr<ICbsCustomInformation>(this + 1);
      }
      CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&lpString1);
    }
  }
  if ( v12 )
    SHDeactivateContext(ulCookie);
  if ( v10 >= 0 )
    return (unsigned int)*((_DWORD *)this + 9);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001d980  push    rbx
0x18001d982  push    rbp
0x18001d983  push    rsi
0x18001d984  push    rdi
0x18001d985  push    r12
0x18001d987  push    r13
0x18001d989  push    r14
0x18001d98b  push    r15
0x18001d98d  sub     rsp, 38h
0x18001d991  xor     r13d, r13d
0x18001d994  lea     rbx, [rcx-8]
0x18001d998  mov     r12d, r9d
0x18001d99b  mov     rbp, r8
0x18001d99e  mov     r15, rdx
0x18001d9a1  mov     rdi, rcx
0x18001d9a4  mov     esi, r13d
0x18001d9a7  cmp     [rbx+10h], r13
0x18001d9ab  jnz     short loc_18001D9B8
0x18001d9ad  add     rcx, 8; struct ICbsSession7 **
0x18001d9b1  call    ?InitializeCBSSession@@YAJPEAPEAUICbsSession7@@@Z; InitializeCBSSession(ICbsSession7 * *)
0x18001d9b6  mov     esi, eax
0x18001d9b8  mov     r14, [rsp+78h+lpString1]
0x18001d9c0  test    r14, r14
0x18001d9c3  jz      short loc_18001D9C8
0x18001d9c5  mov     [r14], r13d
0x18001d9c8  lea     rcx, [rsp+78h+ulCookie]
0x18001d9d0  mov     [rsp+78h+ulCookie], r13
0x18001d9d8  call    SHActivateContext
0x18001d9dd  mov     r13d, eax
0x18001d9e0  test    esi, esi
0x18001d9e2  js      loc_18001DB5A
0x18001d9e8  mov     rdx, r15; unsigned __int16 *
0x18001d9eb  mov     rcx, rbx; this
0x18001d9ee  call    ?_PreInitiateChanges@CARPUninstallerProxy@@AEAAJPEBG@Z; CARPUninstallerProxy::_PreInitiateChanges(ushort const *)
0x18001d9f3  xor     r15d, r15d
0x18001d9f6  mov     esi, eax
0x18001d9f8  test    eax, eax
0x18001d9fa  js      loc_18001DB5A
0x18001da00  mov     [rdi+238h], r15d
0x18001da07  lea     r8, [rsp+78h+lpString1]
0x18001da0f  mov     [rsp+78h+lpString1], r15
0x18001da17  mov     edx, 8
0x18001da1c  lea     r15, [rdi+10h]
0x18001da20  mov     rcx, [r15]
0x18001da23  mov     rax, [rcx]
0x18001da26  mov     rax, [rax+20h]
0x18001da2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da2f  test    eax, eax
0x18001da31  js      short loc_18001DA6C
0x18001da33  mov     r8, [rsp+78h+lpString1]; lpString1
0x18001da3b  lea     rax, aProduct; "Product"
0x18001da42  or      r9d, 0FFFFFFFFh; cchCount1
0x18001da46  mov     [rsp+78h+cchCount2], r9d; cchCount2
0x18001da4b  mov     [rsp+78h+lpString2], rax; lpString2
0x18001da50  lea     edx, [r9+2]; dwCmpFlags
0x18001da54  lea     ecx, [rdx+7Eh]; Locale
0x18001da57  call    cs:__imp_CompareStringW
0x18001da5d  cmp     eax, 2
0x18001da60  jnz     short loc_18001DA6C
0x18001da62  mov     dword ptr [rdi+238h], 1
0x18001da6c  test    r12d, r12d
0x18001da6f  jz      loc_18001DB09
0x18001da75  mov     rdx, rbp; HWND
0x18001da78  mov     rcx, rbx; this
0x18001da7b  call    ?_InitializeProgressDialog@CARPUninstallerProxy@@AEAAKPEAUHWND__@@@Z; CARPUninstallerProxy::_InitializeProgressDialog(HWND__ *)
0x18001da80  xor     r12d, r12d
0x18001da83  cmp     [rdi+24h], r12d
0x18001da87  jge     short loc_18001DAB5
0x18001da89  mov     rcx, cs:g_hinst; hAppInst
0x18001da90  lea     r8, [rdi+28h]
0x18001da94  mov     r9d, 1F4h; lpcTitle
0x18001da9a  mov     dword ptr [rsp+78h+lpString2], 10h; fuStyle
0x18001daa2  mov     rdx, rbp; hWnd
0x18001daa5  cmp     [r8], r12w
0x18001daa9  jnz     short loc_18001DAAF
0x18001daab  lea     r8d, [r9+1]; lpcText
0x18001daaf  call    cs:__imp_ShellMessageBoxW
0x18001dab5  cmp     [rdi+230h], r12d
0x18001dabc  jz      short loc_18001DAD3
0x18001dabe  xor     edx, edx; pszPrompt
0x18001dac0  mov     r9d, 20004h; dwReasonCode
0x18001dac6  mov     rcx, rbp; hwnd
0x18001dac9  lea     r8d, [rdx+2]; dwReturn
0x18001dacd  call    cs:__imp_RestartDialogEx
0x18001dad3  mov     rcx, [rdi+8]
0x18001dad7  mov     rdx, r14
0x18001dada  mov     rax, [rcx]
0x18001dadd  mov     rax, [rax+20h]
0x18001dae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dae6  lea     rcx, [rdi+8]
0x18001daea  call    ??1?$CReleasePtr@UICbsCustomInformation@@@@QEAA@XZ; CReleasePtr<ICbsCustomInformation>::~CReleasePtr<ICbsCustomInformation>(void)
0x18001daef  mov     rcx, r15
0x18001daf2  call    ??1?$CReleasePtr@UICbsCustomInformation@@@@QEAA@XZ; CReleasePtr<ICbsCustomInformation>::~CReleasePtr<ICbsCustomInformation>(void)
0x18001daf7  cmp     [rdi+234h], r12d
0x18001dafe  jz      short loc_18001DB4D
0x18001db00  mov     dword ptr [rdi+24h], 800704C7h
0x18001db07  jmp     short loc_18001DB4D
0x18001db09  mov     rcx, [rbx+18h]
0x18001db0d  xor     r8d, r8d
0x18001db10  mov     r9, rbx
0x18001db13  mov     rax, [rcx]
0x18001db16  lea     edx, [r8+5]
0x18001db1a  mov     rax, [rax+58h]
0x18001db1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db23  mov     esi, eax
0x18001db25  test    eax, eax
0x18001db27  js      short loc_18001DB3C
0x18001db29  mov     rcx, [rdi+8]
0x18001db2d  mov     rdx, r14
0x18001db30  mov     rax, [rcx]
0x18001db33  mov     rax, [rax+20h]
0x18001db37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db3c  mov     rcx, r15
0x18001db3f  call    ??1?$CReleasePtr@UICbsCustomInformation@@@@QEAA@XZ; CReleasePtr<ICbsCustomInformation>::~CReleasePtr<ICbsCustomInformation>(void)
0x18001db44  lea     rcx, [rdi+8]
0x18001db48  call    ??1?$CReleasePtr@UICbsCustomInformation@@@@QEAA@XZ; CReleasePtr<ICbsCustomInformation>::~CReleasePtr<ICbsCustomInformation>(void)
0x18001db4d  lea     rcx, [rsp+78h+lpString1]
0x18001db55  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18001db5a  test    r13d, r13d
0x18001db5d  jz      short loc_18001DB6C
0x18001db5f  mov     rcx, [rsp+78h+ulCookie]; ulCookie
0x18001db67  call    SHDeactivateContext
0x18001db6c  test    esi, esi
0x18001db6e  js      short loc_18001DB73
0x18001db70  mov     esi, [rdi+24h]
0x18001db73  mov     eax, esi
0x18001db75  add     rsp, 38h
0x18001db79  pop     r15
0x18001db7b  pop     r14
0x18001db7d  pop     r13
0x18001db7f  pop     r12
0x18001db81  pop     rdi
0x18001db82  pop     rsi
0x18001db83  pop     rbp
0x18001db84  pop     rbx
0x18001db85  retn
```
