# AipCheckAssistiveTechnologyList(ushort const *,ulong *)

- ea: `0x18003d1f0`
- end: `0x18003d5ff`
- name: `?AipCheckAssistiveTechnologyList@@YAJPEBGPEAK@Z`
- size: `1039`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `14`
- tags: `reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002a2a8`
- `0x18003ac30`

## callees

- `0x180007c78`
- `0x1800135d4`
- `0x180018530`
- `0x180026a18`
- `0x1800272b0`
- `0x1800272d0`
- `0x1800274c8`
- `0x18003cbc8`
- `0x18003ccc4`
- `0x18003d01c`
- `0x18003d1f0`
- `0x18003d608`
- `0x18003dcb8`
- `0x18003debc`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18003d2b2`
- `ntdll!RtlFreeUnicodeString` at `0x18003d59e`
- `ntdll!RtlFreeUnicodeString` at `0x18003d5b3`
- `ntdll!RtlFreeUnicodeString` at `0x18003d2b2`
- `ntdll!RtlFreeUnicodeString` at `0x18003d59e`
- `ntdll!RtlFreeUnicodeString` at `0x18003d5b3`

## string_xrefs

- `0x18003d257`: `onecoreuap\ds\security\services\lua\appinfo\paths.cxx`
- `0x18003d299`: `onecoreuap\ds\security\services\lua\appinfo\paths.cxx`
- `0x18003d585`: `onecoreuap\ds\security\services\lua\appinfo\paths.cxx`
- `0x18003d280`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\ATs`

## pseudocode

```c
__int64 __fastcall AipCheckAssistiveTechnologyList(const unsigned __int16 *a1, unsigned int *a2)
{
  unsigned int v3; // eax
  unsigned int v4; // ebx
  LSTATUS v5; // eax
  __int64 v6; // rbx
  HKEY v7; // rdi
  int v8; // r14d
  int v9; // esi
  unsigned int v10; // ebx
  HKEY v11; // r14
  int v12; // edi
  LPCWSTR lpSubKey; // [rsp+20h] [rbp-E0h] BYREF
  HKEY v15; // [rsp+28h] [rbp-D8h]
  int v16; // [rsp+30h] [rbp-D0h]
  __int64 v17; // [rsp+38h] [rbp-C8h]
  char *v18; // [rsp+40h] [rbp-C0h]
  struct _UNICODE_STRING v19; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v20[2]; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+70h] [rbp-90h] BYREF
  __int128 v22; // [rsp+80h] [rbp-80h] BYREF
  int v23; // [rsp+90h] [rbp-70h]
  __int64 v24; // [rsp+98h] [rbp-68h]
  int v25; // [rsp+A0h] [rbp-60h]
  __int128 v26; // [rsp+A8h] [rbp-58h] BYREF
  int v27; // [rsp+B8h] [rbp-48h]
  __int64 v28; // [rsp+C0h] [rbp-40h]
  int v29; // [rsp+C8h] [rbp-38h]
  __int128 v30; // [rsp+D0h] [rbp-30h] BYREF
  int v31; // [rsp+E0h] [rbp-20h]
  __int64 v32; // [rsp+E8h] [rbp-18h]
  int v33; // [rsp+F0h] [rbp-10h]
  __int128 v34; // [rsp+F8h] [rbp-8h] BYREF
  int v35; // [rsp+108h] [rbp+8h]
  int v36; // [rsp+10Ch] [rbp+Ch]
  __int64 v37; // [rsp+110h] [rbp+10h]
  __int64 v38; // [rsp+118h] [rbp+18h]
  _QWORD v39[2]; // [rsp+120h] [rbp+20h] BYREF
  unsigned int v40; // [rsp+130h] [rbp+30h]
  __int64 v41; // [rsp+138h] [rbp+38h]
  int v42; // [rsp+140h] [rbp+40h]
  __int64 v43; // [rsp+148h] [rbp+48h]
  HKEY v44; // [rsp+150h] [rbp+50h]
  __int64 v45; // [rsp+158h] [rbp+58h]
  __int64 v46; // [rsp+160h] [rbp+60h]
  int v47; // [rsp+168h] [rbp+68h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]
  int v49; // [rsp+1C0h] [rbp+C0h] BYREF
  HKEY phkResult; // [rsp+1C8h] [rbp+C8h] BYREF

  phkResult = 0;
  v20[0] = 0;
  v23 = -1;
  v22 = 0;
  v24 = 0;
  v25 = 0;
  UnicodeString = 0;
  v49 = 0;
  v3 = AipNormalizePath(a1, &UnicodeString);
  if ( v3 )
  {
    v4 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x987,
           (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\paths.cxx",
           (const char *)v3,
           (unsigned int)lpSubKey);
    goto LABEL_34;
  }
  v5 = wil::reg::open_unique_key_nothrow(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\ATs",
         &phkResult);
  v4 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x98D,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\paths.cxx",
      (const char *)(unsigned int)v5,
      (int)lpSubKey);
    RtlFreeUnicodeString(&UnicodeString);
    goto LABEL_34;
  }
  lpSubKey = 0;
  v15 = phkResult;
  v16 = -1;
  v17 = 0;
  LODWORD(v18) = 0;
  if ( phkResult )
  {
    v16 = 0;
    LODWORD(v18) = wil::reg::key_iterator_data<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::enumerate_current_index(&lpSubKey);
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    &v22,
    &lpSubKey);
  v6 = v17;
  v7 = v15;
  v8 = v16;
  v9 = (int)v18;
  *((_QWORD *)&v22 + 1) = v15;
  v24 = v17;
  v23 = v16;
  v17 = 0;
  v25 = (int)v18;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSubKey);
  v36 = 0;
  v38 = 0;
  v35 = -1;
  v37 = 0;
  v27 = -1;
  v28 = 0;
  v34 = 0;
  v26 = 0;
  if ( (_QWORD)v22 )
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v19,
      v22,
      v6);
  else
    *(_QWORD *)&v19.Length = 0;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    &v26,
    &v19);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v19);
  *((_QWORD *)&v26 + 1) = v7;
  v27 = v8;
  v29 = v9;
  v28 = v6 & -(__int64)((_QWORD)v26 != 0);
  wil::make_range<wil::reg::iterator_nothrow_t<wil::reg::key_iterator_data<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>>(
    v39,
    &v26,
    &v34);
  lpSubKey = 0;
  v15 = 0;
  v16 = -1;
  v17 = 0;
  if ( v39[0] )
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v19,
      v39[0],
      v41);
  else
    *(_QWORD *)&v19.Length = 0;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    &lpSubKey,
    &v19);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v19);
  v10 = v40;
  v15 = (HKEY)v39[1];
  v16 = v40;
  LODWORD(v18) = v42;
  v17 = v41 & -(__int64)(lpSubKey != 0);
  v31 = -1;
  v32 = 0;
  v30 = 0;
  if ( v43 )
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v19,
      v43,
      v46);
  else
    *(_QWORD *)&v19.Length = 0;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    &v30,
    &v19);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v19);
  v11 = v44;
  v12 = v45;
  *((_QWORD *)&v30 + 1) = v44;
  v31 = v45;
  v32 = v46 & -(__int64)((_QWORD)v30 != 0);
  v33 = v47;
  while ( v10 != -1 && v12 != -1 && v15 != v11 || v10 != v12 )
  {
    if ( wil::reg::open_unique_key_nothrow(phkResult, lpSubKey, v20) >= 0 )
    {
      v19 = UnicodeString;
      if ( (int)AipCompareSingleAssistiveTechnology(v20[0], &v19, &v49) >= 0 )
      {
        if ( v49 )
        {
          *a2 |= 0x40000000u;
          break;
        }
      }
    }
    if ( v10 + 1 < v10 || v10 == -2 )
    {
      LODWORD(v18) = -2147024809;
LABEL_29:
      wil::reg::reg_iterator_details::clear_name<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &lpSubKey,
        v17);
      v10 = -1;
      v16 = -1;
    }
    else
    {
      v16 = v10 + 1;
      LODWORD(v18) = wil::reg::key_iterator_data<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::enumerate_current_index(&lpSubKey);
      if ( (int)v18 < 0 )
        goto LABEL_29;
      v10 = v16;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v30);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSubKey);
  wil::details::pointer_range<wil::reg::iterator_nothrow_t<wil::reg::key_iterator_data<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>>::~pointer_range<wil::reg::iterator_nothrow_t<wil::reg::key_iterator_data<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>>(v39);
  if ( v9 >= 0 )
  {
    RtlFreeUnicodeString(&UnicodeString);
    v4 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9A3,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\paths.cxx",
      (const char *)(unsigned int)v9,
      (int)lpSubKey);
    RtlFreeUnicodeString(&UnicodeString);
    v4 = v9;
  }
LABEL_34:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v22);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v20);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  return v4;
}

```

## disassembly

```asm
0x18003d1f0  mov     [rsp-8+arg_0], rbx
0x18003d1f5  push    rbp
0x18003d1f6  push    rsi
0x18003d1f7  push    rdi
0x18003d1f8  push    r12
0x18003d1fa  push    r13
0x18003d1fc  push    r14
0x18003d1fe  push    r15
0x18003d200  lea     rbp, [rsp-70h]
0x18003d205  sub     rsp, 170h
0x18003d20c  xor     r12d, r12d
0x18003d20f  xorps   xmm0, xmm0
0x18003d212  mov     r15, rdx
0x18003d215  mov     [rbp+0A0h+phkResult], r12
0x18003d21c  or      r13d, 0FFFFFFFFh
0x18003d220  mov     [rsp+1A0h+var_140], r12
0x18003d225  lea     rdx, [rsp+1A0h+UnicodeString]; struct _UNICODE_STRING *
0x18003d22a  mov     [rbp+0A0h+var_110], r13d
0x18003d22e  movdqu  [rbp+0A0h+var_120], xmm0
0x18003d233  mov     [rbp+0A0h+var_108], r12
0x18003d237  mov     [rbp+0A0h+var_100], r12d
0x18003d23b  movups  xmmword ptr [rsp+1A0h+UnicodeString.Length], xmm0
0x18003d240  mov     [rbp+0A0h+arg_10], r12d
0x18003d247  call    ?AipNormalizePath@@YAKPEBGPEAU_UNICODE_STRING@@@Z; AipNormalizePath(ushort const *,_UNICODE_STRING *)
0x18003d24c  test    eax, eax
0x18003d24e  jz      short loc_18003D272
0x18003d250  mov     rcx, [rbp+0A8h]; this
0x18003d257  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18003d25e  mov     r9d, eax; char *
0x18003d261  mov     edx, 987h; void *
0x18003d266  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003d26b  mov     ebx, eax
0x18003d26d  jmp     loc_18003D5C2
0x18003d272  lea     r8, [rbp+0A0h+phkResult]; phkResult
0x18003d279  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003d280  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18003d287  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x18003d28c  mov     ebx, eax
0x18003d28e  test    eax, eax
0x18003d290  jns     short loc_18003D2C3
0x18003d292  mov     rcx, [rbp+0A8h]; this
0x18003d299  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18003d2a0  mov     r9d, eax; char *
0x18003d2a3  mov     edx, 98Dh; void *
0x18003d2a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d2ad  lea     rcx, [rsp+1A0h+UnicodeString]; UnicodeString
0x18003d2b2  call    cs:__imp_RtlFreeUnicodeString
0x18003d2b9  nop     dword ptr [rax+rax+00h]
0x18003d2be  jmp     loc_18003D5C2
0x18003d2c3  mov     rax, [rbp+0A0h+phkResult]
0x18003d2ca  mov     [rsp+1A0h+lpSubKey], r12
0x18003d2cf  mov     [rsp+1A0h+var_178], rax
0x18003d2d4  mov     [rsp+1A0h+var_170], r13d
0x18003d2d9  mov     [rsp+1A0h+var_168], r12
0x18003d2de  mov     dword ptr [rsp+1A0h+var_160], r12d
0x18003d2e3  test    rax, rax
0x18003d2e6  jz      short loc_18003D2FB
0x18003d2e8  lea     rcx, [rsp+1A0h+lpSubKey]
0x18003d2ed  mov     [rsp+1A0h+var_170], r12d
0x18003d2f2  call    ?enumerate_current_index@?$key_iterator_data@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@reg@wil@@AEAAJXZ; wil::reg::key_iterator_data<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::enumerate_current_index(void)
0x18003d2f7  mov     dword ptr [rsp+1A0h+var_160], eax
0x18003d2fb  lea     rdx, [rsp+1A0h+lpSubKey]
0x18003d300  lea     rcx, [rbp+0A0h+var_120]
0x18003d304  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18003d309  mov     rbx, [rsp+1A0h+var_168]
0x18003d30e  lea     rcx, [rsp+1A0h+lpSubKey]
0x18003d313  mov     rdi, [rsp+1A0h+var_178]
0x18003d318  mov     r14d, [rsp+1A0h+var_170]
0x18003d31d  mov     esi, dword ptr [rsp+1A0h+var_160]
0x18003d321  mov     qword ptr [rbp+0A0h+var_120+8], rdi
0x18003d325  mov     [rbp+0A0h+var_108], rbx
0x18003d329  mov     [rbp+0A0h+var_110], r14d
0x18003d32d  mov     [rsp+1A0h+var_168], r12
0x18003d332  mov     [rbp+0A0h+var_100], esi
0x18003d335  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003d33a  mov     rdx, qword ptr [rbp+0A0h+var_120]
0x18003d33e  xorps   xmm0, xmm0
0x18003d341  mov     [rbp+0A0h+var_94], r12d
0x18003d345  mov     [rbp+0A0h+var_88], r12
0x18003d349  mov     [rbp+0A0h+var_98], r13d
0x18003d34d  mov     [rbp+0A0h+var_90], r12
0x18003d351  mov     [rbp+0A0h+var_E8], r13d
0x18003d355  mov     [rbp+0A0h+var_E0], r12
0x18003d359  movdqu  [rbp+0A0h+var_A8], xmm0
0x18003d35e  movdqu  [rbp+0A0h+var_F8], xmm0
0x18003d363  test    rdx, rdx
0x18003d366  jz      short loc_18003D377
0x18003d368  mov     r8, rbx
0x18003d36b  lea     rcx, [rsp+1A0h+var_150]
0x18003d370  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18003d375  jmp     short loc_18003D37C
0x18003d377  mov     qword ptr [rsp+1A0h+var_150.Length], r12
0x18003d37c  lea     rdx, [rsp+1A0h+var_150]
0x18003d381  lea     rcx, [rbp+0A0h+var_F8]
0x18003d385  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18003d38a  lea     rcx, [rsp+1A0h+var_150]
0x18003d38f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003d394  cmp     qword ptr [rbp+0A0h+var_F8], r12
0x18003d398  lea     r8, [rbp+0A0h+var_A8]
0x18003d39c  lea     rdx, [rbp+0A0h+var_F8]
0x18003d3a0  mov     qword ptr [rbp+0A0h+var_F8+8], rdi
0x18003d3a4  setnz   al
0x18003d3a7  mov     [rbp+0A0h+var_E8], r14d
0x18003d3ab  neg     al
0x18003d3ad  mov     [rbp+0A0h+var_D8], esi
0x18003d3b0  sbb     rcx, rcx
0x18003d3b3  and     rcx, rbx
0x18003d3b6  mov     [rbp+0A0h+var_E0], rcx
0x18003d3ba  lea     rcx, [rbp+0A0h+var_80]
0x18003d3be  call    ??$make_range@V?$iterator_nothrow_t@V?$key_iterator_data@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@reg@wil@@@reg@wil@@@wil@@YA?AV?$pointer_range@V?$iterator_nothrow_t@V?$key_iterator_data@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@reg@wil@@@reg@wil@@@details@0@V?$iterator_nothrow_t@V?$key_iterator_data@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@reg@wil@@@reg@0@0@Z; wil::make_range<wil::reg::iterator_nothrow_t<wil::reg::key_iterator_data<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>>(wil::reg::iterator_nothrow_t<wil::reg::key_iterator_data<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>,wil::reg::iterator_nothrow_t<wil::reg::key_iterator_data<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>)
0x18003d3c3  mov     rdx, [rbp+0A0h+var_80]
0x18003d3c7  mov     [rsp+1A0h+lpSubKey], r12; int
0x18003d3cc  mov     [rsp+1A0h+var_178], r12
0x18003d3d1  mov     [rsp+1A0h+var_170], r13d
0x18003d3d6  mov     [rsp+1A0h+var_168], r12
0x18003d3db  test    rdx, rdx
0x18003d3de  jz      short loc_18003D3F0
0x18003d3e0  mov     r8, [rbp+0A0h+var_68]
0x18003d3e4  lea     rcx, [rsp+1A0h+var_150]
0x18003d3e9  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18003d3ee  jmp     short loc_18003D3F5
0x18003d3f0  mov     qword ptr [rsp+1A0h+var_150.Length], r12
0x18003d3f5  lea     rdx, [rsp+1A0h+var_150]
0x18003d3fa  lea     rcx, [rsp+1A0h+lpSubKey]
0x18003d3ff  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18003d404  lea     rcx, [rsp+1A0h+var_150]
0x18003d409  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003d40e  mov     rax, [rbp+0A0h+var_78]
0x18003d412  xorps   xmm0, xmm0
0x18003d415  cmp     [rsp+1A0h+lpSubKey], r12
0x18003d41a  mov     rdx, [rbp+0A0h+var_58]
0x18003d41e  mov     ebx, [rbp+0A0h+var_70]
0x18003d421  mov     [rsp+1A0h+var_178], rax
0x18003d426  setnz   al
0x18003d429  neg     al
0x18003d42b  mov     [rsp+1A0h+var_170], ebx
0x18003d42f  mov     eax, [rbp+0A0h+var_60]
0x18003d432  sbb     rcx, rcx
0x18003d435  mov     dword ptr [rsp+1A0h+var_160], eax
0x18003d439  and     rcx, [rbp+0A0h+var_68]
0x18003d43d  mov     [rsp+1A0h+var_168], rcx
0x18003d442  mov     [rbp+0A0h+var_C0], r13d
0x18003d446  mov     [rbp+0A0h+var_B8], r12
0x18003d44a  movdqu  [rbp+0A0h+var_D0], xmm0
0x18003d44f  test    rdx, rdx
0x18003d452  jz      short loc_18003D464
0x18003d454  mov     r8, [rbp+0A0h+var_40]
0x18003d458  lea     rcx, [rsp+1A0h+var_150]
0x18003d45d  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18003d462  jmp     short loc_18003D469
0x18003d464  mov     qword ptr [rsp+1A0h+var_150.Length], r12
0x18003d469  lea     rdx, [rsp+1A0h+var_150]
0x18003d46e  lea     rcx, [rbp+0A0h+var_D0]
0x18003d472  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18003d477  lea     rcx, [rsp+1A0h+var_150]
0x18003d47c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003d481  cmp     qword ptr [rbp+0A0h+var_D0], r12
0x18003d485  mov     r14, [rbp+0A0h+var_50]
0x18003d489  mov     rdi, [rbp+0A0h+var_48]
0x18003d48d  setnz   al
0x18003d490  neg     al
0x18003d492  mov     qword ptr [rbp+0A0h+var_D0+8], r14
0x18003d496  mov     eax, [rbp+0A0h+var_38]
0x18003d499  sbb     rcx, rcx
0x18003d49c  mov     [rbp+0A0h+var_C0], edi
0x18003d49f  and     rcx, [rbp+0A0h+var_40]
0x18003d4a3  mov     [rbp+0A0h+var_B8], rcx
0x18003d4a7  mov     [rbp+0A0h+var_B0], eax
0x18003d4aa  cmp     ebx, r13d
0x18003d4ad  jz      short loc_18003D4BB
0x18003d4af  cmp     edi, r13d
0x18003d4b2  jz      short loc_18003D4BB
0x18003d4b4  cmp     [rsp+1A0h+var_178], r14
0x18003d4b9  jnz     short loc_18003D4C3
0x18003d4bb  cmp     ebx, edi
0x18003d4bd  jz      loc_18003D55E
0x18003d4c3  mov     rdx, [rsp+1A0h+lpSubKey]; lpSubKey
0x18003d4c8  lea     r8, [rsp+1A0h+var_140]; phkResult
0x18003d4cd  mov     rcx, [rbp+0A0h+phkResult]; hKey
0x18003d4d4  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x18003d4d9  test    eax, eax
0x18003d4db  js      short loc_18003D50B
0x18003d4dd  movaps  xmm0, xmmword ptr [rsp+1A0h+UnicodeString.Length]
0x18003d4e2  lea     r8, [rbp+0A0h+arg_10]; int *
0x18003d4e9  mov     rcx, [rsp+1A0h+var_140]; HKEY
0x18003d4ee  lea     rdx, [rsp+1A0h+var_150]; struct _UNICODE_STRING
0x18003d4f3  movdqa  xmmword ptr [rsp+1A0h+var_150.Length], xmm0
0x18003d4f9  call    ?AipCompareSingleAssistiveTechnology@@YAJPEAUHKEY__@@U_UNICODE_STRING@@PEAH@Z; AipCompareSingleAssistiveTechnology(HKEY__ *,_UNICODE_STRING,int *)
0x18003d4fe  test    eax, eax
0x18003d500  js      short loc_18003D50B
0x18003d502  cmp     [rbp+0A0h+arg_10], r12d
0x18003d509  jnz     short loc_18003D559
0x18003d50b  lea     eax, [rbx+1]
0x18003d50e  cmp     eax, ebx
0x18003d510  jb      short loc_18003D536
0x18003d512  cmp     eax, r13d
0x18003d515  jz      short loc_18003D536
0x18003d517  lea     rcx, [rsp+1A0h+lpSubKey]
0x18003d51c  mov     [rsp+1A0h+var_170], eax
0x18003d520  call    ?enumerate_current_index@?$key_iterator_data@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@reg@wil@@AEAAJXZ; wil::reg::key_iterator_data<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::enumerate_current_index(void)
0x18003d525  mov     dword ptr [rsp+1A0h+var_160], eax
0x18003d529  test    eax, eax
0x18003d52b  js      short loc_18003D53E
0x18003d52d  mov     ebx, [rsp+1A0h+var_170]
0x18003d531  jmp     loc_18003D4AA
0x18003d536  mov     dword ptr [rsp+1A0h+var_160], 80070057h
0x18003d53e  mov     rdx, [rsp+1A0h+var_168]
0x18003d543  lea     rcx, [rsp+1A0h+lpSubKey]
0x18003d548  call    ??$clear_name@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@reg_iterator_details@reg@wil@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@2@_K@Z; wil::reg::reg_iterator_details::clear_name<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &,unsigned __int64)
0x18003d54d  mov     ebx, r13d
0x18003d550  mov     [rsp+1A0h+var_170], ebx
0x18003d554  jmp     loc_18003D4AA
0x18003d559  bts     dword ptr [r15], 1Eh
0x18003d55e  lea     rcx, [rbp+0A0h+var_D0]
0x18003d562  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003d567  lea     rcx, [rsp+1A0h+lpSubKey]
0x18003d56c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003d571  lea     rcx, [rbp+0A0h+var_80]
0x18003d575  call    ??1?$pointer_range@V?$iterator_nothrow_t@V?$key_iterator_data@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@reg@wil@@@reg@wil@@@details@wil@@QEAA@XZ; wil::details::pointer_range<wil::reg::iterator_nothrow_t<wil::reg::key_iterator_data<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>>::~pointer_range<wil::reg::iterator_nothrow_t<wil::reg::key_iterator_data<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>>(void)
0x18003d57a  test    esi, esi
0x18003d57c  jns     short loc_18003D5AE
0x18003d57e  mov     rcx, [rbp+0A8h]; this
0x18003d585  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18003d58c  mov     r9d, esi; char *
0x18003d58f  mov     edx, 9A3h; void *
0x18003d594  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d599  lea     rcx, [rsp+1A0h+UnicodeString]; UnicodeString
0x18003d59e  call    cs:__imp_RtlFreeUnicodeString
0x18003d5a5  nop     dword ptr [rax+rax+00h]
0x18003d5aa  mov     ebx, esi
0x18003d5ac  jmp     short loc_18003D5C2
0x18003d5ae  lea     rcx, [rsp+1A0h+UnicodeString]; UnicodeString
0x18003d5b3  call    cs:__imp_RtlFreeUnicodeString
0x18003d5ba  nop     dword ptr [rax+rax+00h]
0x18003d5bf  mov     ebx, r12d
0x18003d5c2  lea     rcx, [rbp+0A0h+var_120]
0x18003d5c6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003d5cb  lea     rcx, [rsp+1A0h+var_140]
0x18003d5d0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003d5d5  lea     rcx, [rbp+0A0h+phkResult]
0x18003d5dc  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003d5e1  mov     eax, ebx
0x18003d5e3  mov     rbx, [rsp+1A0h+arg_0]
0x18003d5eb  add     rsp, 170h
0x18003d5f2  pop     r15
0x18003d5f4  pop     r14
0x18003d5f6  pop     r13
0x18003d5f8  pop     r12
0x18003d5fa  pop     rdi
0x18003d5fb  pop     rsi
0x18003d5fc  pop     rbp
0x18003d5fd  retn
```
