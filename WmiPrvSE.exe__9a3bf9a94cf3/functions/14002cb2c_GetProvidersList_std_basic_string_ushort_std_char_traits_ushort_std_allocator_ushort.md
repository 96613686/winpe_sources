# GetProvidersList(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x14002cb2c`
- end: `0x14002cd45`
- name: `?GetProvidersList@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `537`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140008d40`

## callees

- `0x14000a0f0`
- `0x1400182c4`
- `0x140023c98`
- `0x14002a538`
- `0x14002cb2c`
- `0x14002cd4c`
- `0x14002df20`
- `0x140046430`
- `0x140048010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002cc8c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002cc8c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002cd1f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002cd1f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x14002cc2e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x14002cc2e`

## string_xrefs

- `0x14002cc49`: `SOFTWARE\Classes\CLSID\%s\InprocServer32`

## pseudocode

```c
__int64 __fastcall GetProvidersList(__int64 a1)
{
  __int64 v1; // r15
  __int64 v2; // r14
  char v3; // di
  int (__fastcall ***v5)(_QWORD, GUID *, _QWORD **); // rcx
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  const unsigned __int16 *v9; // rdx
  void *v10; // rsi
  __int64 v11; // r8
  void *lpMem; // [rsp+38h] [rbp-190h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-188h] BYREF
  _QWORD *v14; // [rsp+48h] [rbp-180h] BYREF
  __int64 v15; // [rsp+50h] [rbp-178h] BYREF
  __int64 v16; // [rsp+58h] [rbp-170h]
  __int64 v17; // [rsp+60h] [rbp-168h]
  GUID rguid; // [rsp+68h] [rbp-160h] BYREF
  OLECHAR sz[40]; // [rsp+80h] [rbp-148h] BYREF
  WCHAR SubKey[104]; // [rsp+D0h] [rbp-F8h] BYREF

  v1 = a1;
  v17 = a1;
  v2 = ProviderSubSystem_Globals::s_SyncProviderController;
  v16 = ProviderSubSystem_Globals::s_SyncProviderController;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)ProviderSubSystem_Globals::s_SyncProviderController + 48LL))(ProviderSubSystem_Globals::s_SyncProviderController);
  WmiAvlTree<_GUID,WmiContainerController<_GUID>::WmiContainerElement *>::Begin(v2 + 64, &v15);
  v3 = 1;
  while ( v15 )
  {
    v5 = *(int (__fastcall ****)(_QWORD, GUID *, _QWORD **))(v15 + 48);
    v14 = 0;
    if ( (**v5)(v5, &IID_IUnknown, &v14) >= 0 && v14 )
    {
      rguid = *(GUID *)(v14[75] + 1776LL);
      if ( StringFromGUID2(&rguid, sz, 40) )
      {
        hKey = 0;
        if ( (int)StringCchPrintfW(SubKey, 0x64u, L"SOFTWARE\\Classes\\CLSID\\%s\\InprocServer32", sz) >= 0
          && !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey) )
        {
          lpMem = 0;
          if ( !(unsigned int)GetRegValue(hKey, v9, (unsigned __int8 **)&lpMem) )
          {
            try
            {
              if ( !v3 )
                std::wstring::append(v1, L", ", 2);
              v3 = 0;
              v10 = lpMem;
              if ( *(_WORD *)lpMem )
              {
                v11 = -1;
                do
                  ++v11;
                while ( *((_WORD *)lpMem + v11) );
              }
              else
              {
                v11 = 0;
              }
              std::wstring::append(v1, lpMem, v11);
            }
            catch ( std::bad_alloc )
            {
              v2 = v16;
              v3 = 0;
              v10 = lpMem;
              v1 = v17;
            }
            operator delete(v10);
          }
          RegCloseKey(hKey);
        }
      }
      (*(void (__fastcall **)(_QWORD *))(*v14 + 16LL))(v14);
    }
    WmiAvlTree<_GUID,WmiContainerController<_GUID>::WmiContainerElement *>::Iterator::Increment(&v15, v6, v7, v8);
  }
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 56LL))(v2);
}

```

## disassembly

```asm
0x14002cb2c  mov     [rsp+arg_8], rbx
0x14002cb31  mov     [rsp+arg_10], rsi
0x14002cb36  push    rdi
0x14002cb37  push    r14
0x14002cb39  push    r15
0x14002cb3b  sub     rsp, 1B0h
0x14002cb42  mov     rax, cs:__security_cookie
0x14002cb49  xor     rax, rsp
0x14002cb4c  mov     [rsp+1C8h+var_28], rax
0x14002cb54  mov     r15, rcx
0x14002cb57  mov     [rsp+1C8h+var_168], rcx
0x14002cb5c  mov     r14, cs:?s_SyncProviderController@ProviderSubSystem_Globals@@2PEAV?$WmiContainerController@U_GUID@@@@EA; WmiContainerController<_GUID> * ProviderSubSystem_Globals::s_SyncProviderController
0x14002cb63  mov     [rsp+1C8h+var_170], r14
0x14002cb68  mov     rax, [r14]
0x14002cb6b  mov     rcx, r14
0x14002cb6e  mov     rax, [rax+30h]
0x14002cb72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002cb77  lea     rcx, [r14+40h]
0x14002cb7b  lea     rdx, [rsp+1C8h+var_178]
0x14002cb80  call    ?Begin@?$WmiAvlTree@U_GUID@@PEAVWmiContainerElement@?$WmiContainerController@U_GUID@@@@@@QEAA?AVIterator@1@XZ; WmiAvlTree<_GUID,WmiContainerController<_GUID>::WmiContainerElement *>::Begin(void)
0x14002cb85  mov     dil, 1
0x14002cb88  mov     [rsp+1C8h+var_198], dil
0x14002cb8d  xor     ebx, ebx
0x14002cb8f  mov     rax, [rsp+1C8h+var_178]
0x14002cb94  test    rax, rax
0x14002cb97  jnz     short loc_14002CBD1
0x14002cb99  mov     rax, [r14]
0x14002cb9c  mov     rcx, r14
0x14002cb9f  mov     rax, [rax+38h]
0x14002cba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002cba8  mov     rcx, [rsp+1C8h+var_28]
0x14002cbb0  xor     rcx, rsp; StackCookie
0x14002cbb3  call    __security_check_cookie
0x14002cbb8  lea     r11, [rsp+1C8h+var_18]
0x14002cbc0  mov     rbx, [r11+28h]
0x14002cbc4  mov     rsi, [r11+30h]
0x14002cbc8  mov     rsp, r11
0x14002cbcb  pop     r15
0x14002cbcd  pop     r14
0x14002cbcf  pop     rdi
0x14002cbd0  retn
0x14002cbd1  mov     rcx, [rax+30h]
0x14002cbd5  mov     [rsp+1C8h+var_180], rbx
0x14002cbda  mov     rax, [rcx]
0x14002cbdd  lea     r8, [rsp+1C8h+var_180]
0x14002cbe2  lea     rdx, IID_IUnknown
0x14002cbe9  mov     rax, [rax]
0x14002cbec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002cbf1  test    eax, eax
0x14002cbf3  js      loc_14002CD36
0x14002cbf9  mov     rax, [rsp+1C8h+var_180]
0x14002cbfe  test    rax, rax
0x14002cc01  jz      loc_14002CD36
0x14002cc07  mov     rax, [rax+258h]
0x14002cc0e  movups  xmm0, xmmword ptr [rax+6F0h]
0x14002cc15  movdqu  xmmword ptr [rsp+1C8h+rguid.Data1], xmm0
0x14002cc1b  mov     r8d, 28h ; '('; cchMax
0x14002cc21  lea     rdx, [rsp+1C8h+sz]; lpsz
0x14002cc29  lea     rcx, [rsp+1C8h+rguid]; rguid
0x14002cc2e  call    cs:__imp_StringFromGUID2
0x14002cc34  test    eax, eax
0x14002cc36  jz      loc_14002CD25
0x14002cc3c  mov     [rsp+1C8h+hKey], rbx
0x14002cc41  lea     r9, [rsp+1C8h+sz]
0x14002cc49  lea     r8, aSoftwareClasse; "SOFTWARE\\Classes\\CLSID\\%s\\InprocSer"...
0x14002cc50  mov     edx, 64h ; 'd'; unsigned __int64
0x14002cc55  lea     rcx, [rsp+1C8h+SubKey]; unsigned __int16 *
0x14002cc5d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002cc62  test    eax, eax
0x14002cc64  js      loc_14002CD25
0x14002cc6a  lea     rax, [rsp+1C8h+hKey]
0x14002cc6f  mov     [rsp+1C8h+phkResult], rax; phkResult
0x14002cc74  mov     r9d, 20019h; samDesired
0x14002cc7a  xor     r8d, r8d; ulOptions
0x14002cc7d  lea     rdx, [rsp+1C8h+SubKey]; lpSubKey
0x14002cc85  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14002cc8c  call    cs:__imp_RegOpenKeyExW
0x14002cc92  test    eax, eax
0x14002cc94  jnz     loc_14002CD25
0x14002cc9a  mov     [rsp+1C8h+lpMem], rbx
0x14002cc9f  lea     r8, [rsp+1C8h+lpMem]; unsigned __int8 **
0x14002cca4  mov     rcx, [rsp+1C8h+hKey]; hKey
0x14002cca9  call    ?GetRegValue@@YAJPEAUHKEY__@@PEBGPEAPEAE@Z; GetRegValue(HKEY__ *,ushort const *,uchar * *)
0x14002ccae  test    eax, eax
0x14002ccb0  jnz     short loc_14002CD1A
0x14002ccb2  test    dil, dil
0x14002ccb5  jnz     short loc_14002CCCA
0x14002ccb7  lea     r8d, [rax+2]
0x14002ccbb  lea     rdx, asc_140050204; ", "
0x14002ccc2  mov     rcx, r15
0x14002ccc5  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x14002ccca  mov     dil, bl
0x14002cccd  mov     [rsp+1C8h+var_198], bl
0x14002ccd1  mov     rsi, [rsp+1C8h+lpMem]
0x14002ccd6  cmp     [rsi], bx
0x14002ccd9  jnz     short loc_14002CCE0
0x14002ccdb  mov     r8, rbx
0x14002ccde  jmp     short loc_14002CCEE
0x14002cce0  or      r8, 0FFFFFFFFFFFFFFFFh
0x14002cce4  inc     r8
0x14002cce7  cmp     [rsi+r8*2], bx
0x14002ccec  jnz     short loc_14002CCE4
0x14002ccee  mov     rdx, rsi
0x14002ccf1  mov     rcx, r15
0x14002ccf4  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x14002ccf9  nop
0x14002ccfa  jmp     short loc_14002CD12
0x14002ccfc  xor     ebx, ebx
0x14002ccfe  mov     r14, [rsp+1C8h+var_170]
0x14002cd03  mov     dil, [rsp+1C8h+var_198]
0x14002cd08  mov     rsi, [rsp+1C8h+lpMem]
0x14002cd0d  mov     r15, [rsp+1C8h+var_168]
0x14002cd12  mov     rcx, rsi; lpMem
0x14002cd15  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002cd1a  mov     rcx, [rsp+1C8h+hKey]; hKey
0x14002cd1f  call    cs:__imp_RegCloseKey
0x14002cd25  mov     rcx, [rsp+1C8h+var_180]
0x14002cd2a  mov     rax, [rcx]
0x14002cd2d  mov     rax, [rax+10h]
0x14002cd31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002cd36  lea     rcx, [rsp+1C8h+var_178]
0x14002cd3b  call    ?Increment@Iterator@?$WmiAvlTree@U_GUID@@PEAVWmiContainerElement@?$WmiContainerController@U_GUID@@@@@@QEAAAEAV12@XZ; WmiAvlTree<_GUID,WmiContainerController<_GUID>::WmiContainerElement *>::Iterator::Increment(void)
0x14002cd40  jmp     loc_14002CB8F
```
