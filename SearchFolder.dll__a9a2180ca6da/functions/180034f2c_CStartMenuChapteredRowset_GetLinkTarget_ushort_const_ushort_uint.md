# CStartMenuChapteredRowset::_GetLinkTarget(ushort const *,ushort *,uint)

- ea: `0x180034f2c`
- end: `0x180035089`
- name: `?_GetLinkTarget@CStartMenuChapteredRowset@@AEAAJPEBGPEAGI@Z`
- size: `349`
- prototype: `__int64 __fastcall(CStartMenuChapteredRowset *this, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180034468`

## callees

- `0x1800054b0`
- `0x180005c88`
- `0x180006900`
- `0x18000ebd0`
- `0x180030020`
- `0x180034f2c`
- `0x180051010`

## import_xrefs

- `SHELL32!__imp_GetAppPathFromLink` at `0x180034fc1`
- `SHELL32!__imp_GetAppPathFromLink` at `0x180034fc1`
- `SHLWAPI!PathRemoveBlanksW` at `0x180035034`
- `SHLWAPI!PathRemoveBlanksW` at `0x180035034`

## pseudocode

```c
__int64 __fastcall CStartMenuChapteredRowset::_GetLinkTarget(
        CStartMenuChapteredRowset *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  PCWSTR v4; // rdx
  const struct _GUID *v5; // r8
  int AppPathFromLink; // ebx
  void *v8; // [rsp+30h] [rbp-D0h] BYREF
  int v9; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v10[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pszPath[264]; // [rsp+50h] [rbp-B0h] BYREF

  *a3 = 0;
  ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v8);
  AppPathFromLink = SHSimpleItemFromAttributes(v4, (unsigned int)v4, v5, &v8);
  if ( AppPathFromLink >= 0 )
  {
    v9 = 0;
    if ( (*(unsigned int (__fastcall **)(void *, __int64, int *))(*(_QWORD *)v8 + 48LL))(v8, 0x10000, &v9) )
    {
      AppPathFromLink = -2147467259;
    }
    else
    {
      AppPathFromLink = GetAppPathFromLink(v8, a3, 260);
      if ( AppPathFromLink >= 0 )
      {
        ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(v10);
        AppPathFromLink = (*(__int64 (__fastcall **)(void *, _QWORD, const GUID *, GUID *, _QWORD *))(*(_QWORD *)v8 + 24LL))(
                            v8,
                            0,
                            &BHID_SFUIObject,
                            &GUID_000214f9_0000_0000_c000_000000000046,
                            v10);
        if ( AppPathFromLink >= 0 )
        {
          AppPathFromLink = (*(__int64 (__fastcall **)(_QWORD, WCHAR *, __int64))(*(_QWORD *)v10[0] + 80LL))(
                              v10[0],
                              pszPath,
                              260);
          if ( AppPathFromLink >= 0 )
          {
            PathRemoveBlanksW(pszPath);
            AppPathFromLink = StringCchCatW(a3, 0x104u, pszPath);
          }
        }
        ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(v10);
      }
    }
  }
  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(&v8);
  return (unsigned int)AppPathFromLink;
}

```

## disassembly

```asm
0x180034f2c  mov     [rsp-8+arg_0], rbx
0x180034f31  mov     [rsp-8+arg_18], rdi
0x180034f36  push    rbp
0x180034f37  lea     rbp, [rsp-170h]
0x180034f3f  sub     rsp, 270h
0x180034f46  mov     rax, cs:__security_cookie
0x180034f4d  xor     rax, rsp
0x180034f50  mov     [rbp+170h+var_10], rax
0x180034f57  mov     rdi, r8
0x180034f5a  xor     eax, eax
0x180034f5c  mov     [r8], ax
0x180034f60  lea     rcx, [rsp+270h+var_240]; void *
0x180034f65  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180034f6a  nop
0x180034f6b  lea     r9, [rsp+270h+var_240]; void **
0x180034f70  mov     rcx, rdx; pszPath
0x180034f73  call    ?SHSimpleItemFromAttributes@@YAJPEBGKAEBU_GUID@@PEAPEAX@Z; SHSimpleItemFromAttributes(ushort const *,ulong,_GUID const &,void * *)
0x180034f78  mov     ebx, eax
0x180034f7a  test    eax, eax
0x180034f7c  js      loc_180035059
0x180034f82  mov     [rsp+270h+var_238], 0
0x180034f8a  mov     rcx, [rsp+270h+var_240]
0x180034f8f  mov     rax, [rcx]
0x180034f92  lea     r8, [rsp+270h+var_238]
0x180034f97  mov     edx, 10000h
0x180034f9c  mov     rax, [rax+30h]
0x180034fa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034fa5  test    eax, eax
0x180034fa7  jz      short loc_180034FB3
0x180034fa9  mov     ebx, 80004005h
0x180034fae  jmp     loc_180035059
0x180034fb3  mov     r8d, 104h
0x180034fb9  mov     rdx, rdi
0x180034fbc  mov     rcx, [rsp+270h+var_240]
0x180034fc1  call    cs:__imp_GetAppPathFromLink
0x180034fc7  mov     ebx, eax
0x180034fc9  test    eax, eax
0x180034fcb  js      loc_180035059
0x180034fd1  lea     rcx, [rsp+270h+var_230]; void *
0x180034fd6  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180034fdb  nop
0x180034fdc  mov     rcx, [rsp+270h+var_240]
0x180034fe1  mov     rax, [rcx]
0x180034fe4  lea     rdx, [rsp+270h+var_230]
0x180034fe9  mov     [rsp+270h+var_250], rdx
0x180034fee  lea     r9, _GUID_000214f9_0000_0000_c000_000000000046
0x180034ff5  lea     r8, BHID_SFUIObject
0x180034ffc  xor     edx, edx
0x180034ffe  mov     rax, [rax+18h]
0x180035002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035007  mov     ebx, eax
0x180035009  test    eax, eax
0x18003500b  js      short loc_18003504E
0x18003500d  mov     rcx, [rsp+270h+var_230]
0x180035012  mov     rax, [rcx]
0x180035015  mov     r8d, 104h
0x18003501b  lea     rdx, [rsp+270h+pszPath]
0x180035020  mov     rax, [rax+50h]
0x180035024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035029  mov     ebx, eax
0x18003502b  test    eax, eax
0x18003502d  js      short loc_18003504E
0x18003502f  lea     rcx, [rsp+270h+pszPath]; pszPath
0x180035034  call    cs:__imp_PathRemoveBlanksW
0x18003503a  lea     r8, [rsp+270h+pszPath]; unsigned __int16 *
0x18003503f  mov     edx, 104h; unsigned __int64
0x180035044  mov     rcx, rdi; unsigned __int16 *
0x180035047  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003504c  mov     ebx, eax
0x18003504e  lea     rcx, [rsp+270h+var_230]
0x180035053  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180035058  nop
0x180035059  lea     rcx, [rsp+270h+var_240]
0x18003505e  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180035063  mov     eax, ebx
0x180035065  mov     rcx, [rbp+170h+var_10]
0x18003506c  xor     rcx, rsp; StackCookie
0x18003506f  call    __security_check_cookie
0x180035074  lea     r11, [rsp+270h+var_s0]
0x18003507c  mov     rbx, [r11+10h]
0x180035080  mov     rdi, [r11+28h]
0x180035084  mov     rsp, r11
0x180035087  pop     rbp
0x180035088  retn
```
