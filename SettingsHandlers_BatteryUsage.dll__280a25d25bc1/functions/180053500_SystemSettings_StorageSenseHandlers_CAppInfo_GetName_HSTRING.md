# SystemSettings::StorageSenseHandlers::CAppInfo::GetName(HSTRING__ * *)

- ea: `0x180053500`
- end: `0x1800536f3`
- name: `?GetName@CAppInfo@StorageSenseHandlers@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `499`
- prototype: `int(SystemSettings::StorageSenseHandlers::CAppInfo *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800028d0`
- `0x180004cfc`
- `0x18000fa10`
- `0x180021534`
- `0x1800516bc`
- `0x18005194c`
- `0x180053500`
- `0x180053e84`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180053543`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180053543`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005367e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005367e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800536c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800536c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053662`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053662`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAppInfo::GetName(
        SystemSettings::StorageSenseHandlers::CAppInfo *this,
        HSTRING *a2)
{
  HSTRING *v4; // rsi
  char *v5; // rbx
  int String; // ebx
  __int64 v7; // rdi
  __int64 v9; // [rsp+30h] [rbp-39h] BYREF
  __int64 v10; // [rsp+38h] [rbp-31h] BYREF
  PROPERTYKEY v11; // [rsp+40h] [rbp-29h] BYREF
  char *v12; // [rsp+60h] [rbp-9h] BYREF
  PCNZWCH sourceString[2]; // [rsp+68h] [rbp-1h] BYREF
  _BYTE v14[24]; // [rsp+78h] [rbp+Fh]

  v4 = (HSTRING *)((char *)this + 96);
  if ( *((_QWORD *)this + 12) )
    return (unsigned int)WindowsDuplicateString(*v4, a2);
  v5 = (char *)this + 56;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  v12 = v5;
  v9 = 0;
  v10 = 0;
  if ( (*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 5) + 8LL))((char *)this + 40) )
  {
    String = Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::CopyLocal<IShellItem2>(
               (__int64)this + 40,
               (__int64)&v10);
    if ( String >= 0 )
    {
      *(_OWORD *)sourceString = PKEY_Tile_LongDisplayName;
      *(_DWORD *)v14 = 11;
      *(PROPERTYKEY *)&v14[4] = PKEY_ItemNameDisplay;
      String = CPropertyStoreHelperBase<IPropertyStore>::InitFromItem(
                 (unsigned int)&v9,
                 v10,
                 0,
                 (unsigned int)sourceString,
                 2);
      if ( String >= 0 )
      {
        sourceString[0] = 0;
        sourceString[1] = 0;
        *(_QWORD *)v14 = 0;
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(sourceString);
        v7 = -1;
        sourceString[1] = (PCNZWCH)-1LL;
        *(_QWORD *)v14 = -1;
        v11.fmtid = (GUID)PKEY_Tile_LongDisplayName;
        v11.pid = 11;
        if ( (int)CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(&v9, &v11, sourceString) >= 0
          || (Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(sourceString),
              sourceString[1] = (PCNZWCH)-1LL,
              *(_QWORD *)v14 = -1,
              v11 = PKEY_ItemNameDisplay,
              String = CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(&v9, &v11, sourceString),
              String >= 0) )
        {
          WindowsDeleteString(*v4);
          *v4 = 0;
          do
            ++v7;
          while ( sourceString[0][v7] );
          String = WindowsCreateString(sourceString[0], v7, v4);
        }
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(sourceString);
      }
    }
  }
  else
  {
    String = -2147019873;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    v9 = 0;
  }
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v12);
  if ( String >= 0 )
    return (unsigned int)WindowsDuplicateString(*v4, a2);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x180053500  mov     [rsp-8+arg_10], rbx
0x180053505  push    rbp
0x180053506  push    rsi
0x180053507  push    rdi
0x180053508  push    r14
0x18005350a  push    r15
0x18005350c  lea     rbp, [rsp-37h]
0x180053511  sub     rsp, 0A0h
0x180053518  mov     rax, cs:__security_cookie
0x18005351f  xor     rax, rsp
0x180053522  mov     [rbp+57h+var_30], rax
0x180053526  mov     r14, rdx
0x180053529  mov     rdi, rcx
0x18005352c  lea     rsi, [rcx+60h]
0x180053530  xor     r15d, r15d
0x180053533  cmp     [rsi], r15
0x180053536  jnz     loc_1800536C0
0x18005353c  lea     rbx, [rcx+38h]
0x180053540  mov     rcx, rbx; lpCriticalSection
0x180053543  call    cs:__imp_EnterCriticalSection
0x180053549  mov     [rbp+57h+var_60], rbx
0x18005354d  mov     [rbp+57h+var_90], r15
0x180053551  mov     [rbp+57h+var_88], r15
0x180053555  mov     rax, [rdi+28h]
0x180053559  lea     rcx, [rdi+28h]
0x18005355d  mov     rax, [rax+8]
0x180053561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053566  test    al, al
0x180053568  jnz     short loc_180053574
0x18005356a  mov     ebx, 8007139Fh
0x18005356f  jmp     loc_180053690
0x180053574  lea     rdx, [rbp+57h+var_88]
0x180053578  lea     rcx, [rdi+28h]
0x18005357c  call    ??$CopyLocal@UIShellItem2@@@?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@QEAAJV?$ComPtrRef@V?$ComPtr@UIShellItem2@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::CopyLocal<IShellItem2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IShellItem2>>)
0x180053581  mov     ebx, eax
0x180053583  test    eax, eax
0x180053585  js      loc_180053690
0x18005358b  movups  xmm0, cs:PKEY_Tile_LongDisplayName
0x180053592  movups  xmmword ptr [rbp+57h+sourceString], xmm0
0x180053596  mov     eax, cs:dword_180063708
0x18005359c  mov     dword ptr [rbp+57h+var_48], eax
0x18005359f  movups  xmm0, xmmword ptr cs:PKEY_ItemNameDisplay.fmtid.Data1
0x1800535a6  movups  xmmword ptr [rbp+57h+var_48+4], xmm0
0x1800535aa  mov     eax, cs:PKEY_ItemNameDisplay.pid
0x1800535b0  mov     [rbp+57h+var_34], eax
0x1800535b3  mov     [rsp+0C0h+var_A0], 2
0x1800535bb  lea     r9, [rbp+57h+sourceString]
0x1800535bf  xor     r8d, r8d
0x1800535c2  mov     rdx, [rbp+57h+var_88]
0x1800535c6  lea     rcx, [rbp+57h+var_90]
0x1800535ca  call    ?InitFromItem@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEAAJPEAUIUnknown@@W4GETPROPERTYSTOREFLAGS@@PEBU_tagpropertykey@@I@Z; CPropertyStoreHelperBase<IPropertyStore>::InitFromItem(IUnknown *,GETPROPERTYSTOREFLAGS,_tagpropertykey const *,uint)
0x1800535cf  mov     ebx, eax
0x1800535d1  test    eax, eax
0x1800535d3  js      loc_180053690
0x1800535d9  mov     [rbp+57h+sourceString], r15
0x1800535dd  mov     [rbp+57h+sourceString+8], r15
0x1800535e1  mov     qword ptr [rbp+57h+var_48], r15
0x1800535e5  lea     rcx, [rbp+57h+sourceString]
0x1800535e9  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800535ee  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800535f2  mov     [rbp+57h+sourceString+8], rdi
0x1800535f6  mov     qword ptr [rbp+57h+var_48], rdi
0x1800535fa  movups  xmm0, cs:PKEY_Tile_LongDisplayName
0x180053601  movaps  [rbp+57h+var_80], xmm0
0x180053605  mov     eax, cs:dword_180063708
0x18005360b  mov     [rbp+57h+var_70], eax
0x18005360e  lea     r8, [rbp+57h+sourceString]
0x180053612  lea     rdx, [rbp+57h+var_80]
0x180053616  lea     rcx, [rbp+57h+var_90]
0x18005361a  call    ??$GetString@U_tagpropertykey@@@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEBAJU_tagpropertykey@@PEAPEAG@Z; CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x18005361f  test    eax, eax
0x180053621  jns     short loc_18005365F
0x180053623  lea     rcx, [rbp+57h+sourceString]
0x180053627  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18005362c  mov     [rbp+57h+sourceString+8], rdi
0x180053630  mov     qword ptr [rbp+57h+var_48], rdi
0x180053634  movups  xmm0, xmmword ptr cs:PKEY_ItemNameDisplay.fmtid.Data1
0x18005363b  movaps  [rbp+57h+var_80], xmm0
0x18005363f  mov     eax, cs:PKEY_ItemNameDisplay.pid
0x180053645  mov     [rbp+57h+var_70], eax
0x180053648  lea     r8, [rbp+57h+sourceString]
0x18005364c  lea     rdx, [rbp+57h+var_80]
0x180053650  lea     rcx, [rbp+57h+var_90]
0x180053654  call    ??$GetString@U_tagpropertykey@@@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEBAJU_tagpropertykey@@PEAPEAG@Z; CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x180053659  mov     ebx, eax
0x18005365b  test    eax, eax
0x18005365d  js      short loc_180053686
0x18005365f  mov     rcx, [rsi]; string
0x180053662  call    cs:__imp_WindowsDeleteString
0x180053668  mov     [rsi], r15
0x18005366b  mov     rcx, [rbp+57h+sourceString]; sourceString
0x18005366f  inc     rdi
0x180053672  cmp     [rcx+rdi*2], r15w
0x180053677  jnz     short loc_18005366F
0x180053679  mov     r8, rsi; string
0x18005367c  mov     edx, edi; length
0x18005367e  call    cs:__imp_WindowsCreateString
0x180053684  mov     ebx, eax
0x180053686  lea     rcx, [rbp+57h+sourceString]
0x18005368a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18005368f  nop
0x180053690  lea     rcx, [rbp+57h+var_88]
0x180053694  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180053699  nop
0x18005369a  mov     rcx, [rbp+57h+var_90]
0x18005369e  test    rcx, rcx
0x1800536a1  jz      short loc_1800536B3
0x1800536a3  mov     rax, [rcx]
0x1800536a6  mov     rax, [rax+10h]
0x1800536aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800536af  mov     [rbp+57h+var_90], r15
0x1800536b3  lea     rcx, [rbp+57h+var_60]; this
0x1800536b7  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x1800536bc  test    ebx, ebx
0x1800536be  js      short loc_1800536CE
0x1800536c0  mov     rdx, r14; newString
0x1800536c3  mov     rcx, [rsi]; string
0x1800536c6  call    cs:__imp_WindowsDuplicateString
0x1800536cc  mov     ebx, eax
0x1800536ce  mov     eax, ebx
0x1800536d0  mov     rcx, [rbp+57h+var_30]
0x1800536d4  xor     rcx, rsp; StackCookie
0x1800536d7  call    __security_check_cookie
0x1800536dc  mov     rbx, [rsp+0C0h+arg_10]
0x1800536e4  add     rsp, 0A0h
0x1800536eb  pop     r15
0x1800536ed  pop     r14
0x1800536ef  pop     rdi
0x1800536f0  pop     rsi
0x1800536f1  pop     rbp
0x1800536f2  retn
```
