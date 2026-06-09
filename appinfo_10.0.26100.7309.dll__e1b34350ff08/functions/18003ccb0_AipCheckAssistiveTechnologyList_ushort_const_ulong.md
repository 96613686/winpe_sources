# AipCheckAssistiveTechnologyList(ushort const *,ulong *)

- ea: `0x18003ccb0`
- end: `0x18003d0bf`
- name: `?AipCheckAssistiveTechnologyList@@YAJPEBGPEAK@Z`
- size: `1039`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `14`
- tags: `reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002a1d8`
- `0x18003a8b0`

## callees

- `0x180007c78`
- `0x1800135d4`
- `0x180018530`
- `0x180026948`
- `0x1800271e0`
- `0x180027200`
- `0x1800273f8`
- `0x18003c688`
- `0x18003c784`
- `0x18003cadc`
- `0x18003ccb0`
- `0x18003d0c8`
- `0x18003d778`
- `0x18003d97c`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18003cd72`
- `ntdll!RtlFreeUnicodeString` at `0x18003d05e`
- `ntdll!RtlFreeUnicodeString` at `0x18003d073`
- `ntdll!RtlFreeUnicodeString` at `0x18003cd72`
- `ntdll!RtlFreeUnicodeString` at `0x18003d05e`
- `ntdll!RtlFreeUnicodeString` at `0x18003d073`

## string_xrefs

- `0x18003cd17`: `onecoreuap\ds\security\services\lua\appinfo\paths.cxx`
- `0x18003cd59`: `onecoreuap\ds\security\services\lua\appinfo\paths.cxx`
- `0x18003d045`: `onecoreuap\ds\security\services\lua\appinfo\paths.cxx`
- `0x18003cd40`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\ATs`

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
0x18003ccb0  mov     [rsp-8+arg_0], rbx
0x18003ccb5  push    rbp
0x18003ccb6  push    rsi
0x18003ccb7  push    rdi
0x18003ccb8  push    r12
0x18003ccba  push    r13
0x18003ccbc  push    r14
0x18003ccbe  push    r15
0x18003ccc0  lea     rbp, [rsp-70h]
0x18003ccc5  sub     rsp, 170h
0x18003cccc  xor     r12d, r12d
0x18003cccf  xorps   xmm0, xmm0
0x18003ccd2  mov     r15, rdx
0x18003ccd5  mov     [rbp+0A0h+phkResult], r12
0x18003ccdc  or      r13d, 0FFFFFFFFh
0x18003cce0  mov     [rsp+1A0h+var_140], r12
0x18003cce5  lea     rdx, [rsp+1A0h+UnicodeString]; struct _UNICODE_STRING *
0x18003ccea  mov     [rbp+0A0h+var_110], r13d
0x18003ccee  movdqu  [rbp+0A0h+var_120], xmm0
0x18003ccf3  mov     [rbp+0A0h+var_108], r12
0x18003ccf7  mov     [rbp+0A0h+var_100], r12d
0x18003ccfb  movups  xmmword ptr [rsp+1A0h+UnicodeString.Length], xmm0
0x18003cd00  mov     [rbp+0A0h+arg_10], r12d
0x18003cd07  call    ?AipNormalizePath@@YAKPEBGPEAU_UNICODE_STRING@@@Z; AipNormalizePath(ushort const *,_UNICODE_STRING *)
0x18003cd0c  test    eax, eax
0x18003cd0e  jz      short loc_18003CD32
0x18003cd10  mov     rcx, [rbp+0A8h]; this
0x18003cd17  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18003cd1e  mov     r9d, eax; char *
0x18003cd21  mov     edx, 987h; void *
0x18003cd26  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003cd2b  mov     ebx, eax
0x18003cd2d  jmp     loc_18003D082
0x18003cd32  lea     r8, [rbp+0A0h+phkResult]; phkResult
0x18003cd39  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003cd40  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18003cd47  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x18003cd4c  mov     ebx, eax
0x18003cd4e  test    eax, eax
0x18003cd50  jns     short loc_18003CD83
0x18003cd52  mov     rcx, [rbp+0A8h]; this
0x18003cd59  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18003cd60  mov     r9d, eax; char *
0x18003cd63  mov     edx, 98Dh; void *
0x18003cd68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cd6d  lea     rcx, [rsp+1A0h+UnicodeString]; UnicodeString
0x18003cd72  call    cs:__imp_RtlFreeUnicodeString
0x18003cd79  nop     dword ptr [rax+rax+00h]
0x18003cd7e  jmp     loc_18003D082
0x18003cd83  mov     rax, [rbp+0A0h+phkResult]
0x18003cd8a  mov     [rsp+1A0h+lpSubKey], r12
0x18003cd8f  mov     [rsp+1A0h+var_178], rax
0x18003cd94  mov     [rsp+1A0h+var_170], r13d
0x18003cd99  mov     [rsp+1A0h+var_168], r12
0x18003cd9e  mov     dword ptr [rsp+1A0h+var_160], r12d
0x18003cda3  test    rax, rax
0x18003cda6  jz      short loc_18003CDBB
0x18003cda8  lea     rcx, [rsp+1A0h+lpSubKey]
0x18003cdad  mov     [rsp+1A0h+var_170], r12d
0x18003cdb2  call    ?enumerate_current_index@?$key_iterator_data@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@reg@wil@@AEAAJXZ; wil::reg::key_iterator_data<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::enumerate_current_index(void)
0x18003cdb7  mov     dword ptr [rsp+1A0h+var_160], eax
0x18003cdbb  lea     rdx, [rsp+1A0h+lpSubKey]
0x18003cdc0  lea     rcx, [rbp+0A0h+var_120]
0x18003cdc4  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18003cdc9  mov     rbx, [rsp+1A0h+var_168]
0x18003cdce  lea     rcx, [rsp+1A0h+lpSubKey]
0x18003cdd3  mov     rdi, [rsp+1A0h+var_178]
0x18003cdd8  mov     r14d, [rsp+1A0h+var_170]
0x18003cddd  mov     esi, dword ptr [rsp+1A0h+var_160]
0x18003cde1  mov     qword ptr [rbp+0A0h+var_120+8], rdi
0x18003cde5  mov     [rbp+0A0h+var_108], rbx
0x18003cde9  mov     [rbp+0A0h+var_110], r14d
0x18003cded  mov     [rsp+1A0h+var_168], r12
0x18003cdf2  mov     [rbp+0A0h+var_100], esi
0x18003cdf5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003cdfa  mov     rdx, qword ptr [rbp+0A0h+var_120]
0x18003cdfe  xorps   xmm0, xmm0
0x18003ce01  mov     [rbp+0A0h+var_94], r12d
0x18003ce05  mov     [rbp+0A0h+var_88], r12
0x18003ce09  mov     [rbp+0A0h+var_98], r13d
0x18003ce0d  mov     [rbp+0A0h+var_90], r12
0x18003ce11  mov     [rbp+0A0h+var_E8], r13d
0x18003ce15  mov     [rbp+0A0h+var_E0], r12
0x18003ce19  movdqu  [rbp+0A0h+var_A8], xmm0
0x18003ce1e  movdqu  [rbp+0A0h+var_F8], xmm0
0x18003ce23  test    rdx, rdx
0x18003ce26  jz      short loc_18003CE37
0x18003ce28  mov     r8, rbx
0x18003ce2b  lea     rcx, [rsp+1A0h+var_150]
0x18003ce30  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18003ce35  jmp     short loc_18003CE3C
0x18003ce37  mov     qword ptr [rsp+1A0h+var_150.Length], r12
0x18003ce3c  lea     rdx, [rsp+1A0h+var_150]
0x18003ce41  lea     rcx, [rbp+0A0h+var_F8]
0x18003ce45  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18003ce4a  lea     rcx, [rsp+1A0h+var_150]
0x18003ce4f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003ce54  cmp     qword ptr [rbp+0A0h+var_F8], r12
0x18003ce58  lea     r8, [rbp+0A0h+var_A8]
0x18003ce5c  lea     rdx, [rbp+0A0h+var_F8]
0x18003ce60  mov     qword ptr [rbp+0A0h+var_F8+8], rdi
0x18003ce64  setnz   al
0x18003ce67  mov     [rbp+0A0h+var_E8], r14d
0x18003ce6b  neg     al
0x18003ce6d  mov     [rbp+0A0h+var_D8], esi
0x18003ce70  sbb     rcx, rcx
0x18003ce73  and     rcx, rbx
0x18003ce76  mov     [rbp+0A0h+var_E0], rcx
0x18003ce7a  lea     rcx, [rbp+0A0h+var_80]
0x18003ce7e  call    ??$make_range@V?$iterator_nothrow_t@V?$key_iterator_data@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@reg@wil@@@reg@wil@@@wil@@YA?AV?$pointer_range@V?$iterator_nothrow_t@V?$key_iterator_data@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@reg@wil@@@reg@wil@@@details@0@V?$iterator_nothrow_t@V?$key_iterator_data@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@reg@wil@@@reg@0@0@Z; wil::make_range<wil::reg::iterator_nothrow_t<wil::reg::key_iterator_data<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>>(wil::reg::iterator_nothrow_t<wil::reg::key_iterator_data<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>,wil::reg::iterator_nothrow_t<wil::reg::key_iterator_data<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>)
0x18003ce83  mov     rdx, [rbp+0A0h+var_80]
0x18003ce87  mov     [rsp+1A0h+lpSubKey], r12; int
0x18003ce8c  mov     [rsp+1A0h+var_178], r12
0x18003ce91  mov     [rsp+1A0h+var_170], r13d
0x18003ce96  mov     [rsp+1A0h+var_168], r12
0x18003ce9b  test    rdx, rdx
0x18003ce9e  jz      short loc_18003CEB0
0x18003cea0  mov     r8, [rbp+0A0h+var_68]
0x18003cea4  lea     rcx, [rsp+1A0h+var_150]
0x18003cea9  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18003ceae  jmp     short loc_18003CEB5
0x18003ceb0  mov     qword ptr [rsp+1A0h+var_150.Length], r12
0x18003ceb5  lea     rdx, [rsp+1A0h+var_150]
0x18003ceba  lea     rcx, [rsp+1A0h+lpSubKey]
0x18003cebf  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18003cec4  lea     rcx, [rsp+1A0h+var_150]
0x18003cec9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003cece  mov     rax, [rbp+0A0h+var_78]
0x18003ced2  xorps   xmm0, xmm0
0x18003ced5  cmp     [rsp+1A0h+lpSubKey], r12
0x18003ceda  mov     rdx, [rbp+0A0h+var_58]
0x18003cede  mov     ebx, [rbp+0A0h+var_70]
0x18003cee1  mov     [rsp+1A0h+var_178], rax
0x18003cee6  setnz   al
0x18003cee9  neg     al
0x18003ceeb  mov     [rsp+1A0h+var_170], ebx
0x18003ceef  mov     eax, [rbp+0A0h+var_60]
0x18003cef2  sbb     rcx, rcx
0x18003cef5  mov     dword ptr [rsp+1A0h+var_160], eax
0x18003cef9  and     rcx, [rbp+0A0h+var_68]
0x18003cefd  mov     [rsp+1A0h+var_168], rcx
0x18003cf02  mov     [rbp+0A0h+var_C0], r13d
0x18003cf06  mov     [rbp+0A0h+var_B8], r12
0x18003cf0a  movdqu  [rbp+0A0h+var_D0], xmm0
0x18003cf0f  test    rdx, rdx
0x18003cf12  jz      short loc_18003CF24
0x18003cf14  mov     r8, [rbp+0A0h+var_40]
0x18003cf18  lea     rcx, [rsp+1A0h+var_150]
0x18003cf1d  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18003cf22  jmp     short loc_18003CF29
0x18003cf24  mov     qword ptr [rsp+1A0h+var_150.Length], r12
0x18003cf29  lea     rdx, [rsp+1A0h+var_150]
0x18003cf2e  lea     rcx, [rbp+0A0h+var_D0]
0x18003cf32  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18003cf37  lea     rcx, [rsp+1A0h+var_150]
0x18003cf3c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003cf41  cmp     qword ptr [rbp+0A0h+var_D0], r12
0x18003cf45  mov     r14, [rbp+0A0h+var_50]
0x18003cf49  mov     rdi, [rbp+0A0h+var_48]
0x18003cf4d  setnz   al
0x18003cf50  neg     al
0x18003cf52  mov     qword ptr [rbp+0A0h+var_D0+8], r14
0x18003cf56  mov     eax, [rbp+0A0h+var_38]
0x18003cf59  sbb     rcx, rcx
0x18003cf5c  mov     [rbp+0A0h+var_C0], edi
0x18003cf5f  and     rcx, [rbp+0A0h+var_40]
0x18003cf63  mov     [rbp+0A0h+var_B8], rcx
0x18003cf67  mov     [rbp+0A0h+var_B0], eax
0x18003cf6a  cmp     ebx, r13d
0x18003cf6d  jz      short loc_18003CF7B
0x18003cf6f  cmp     edi, r13d
0x18003cf72  jz      short loc_18003CF7B
0x18003cf74  cmp     [rsp+1A0h+var_178], r14
0x18003cf79  jnz     short loc_18003CF83
0x18003cf7b  cmp     ebx, edi
0x18003cf7d  jz      loc_18003D01E
0x18003cf83  mov     rdx, [rsp+1A0h+lpSubKey]; lpSubKey
0x18003cf88  lea     r8, [rsp+1A0h+var_140]; phkResult
0x18003cf8d  mov     rcx, [rbp+0A0h+phkResult]; hKey
0x18003cf94  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x18003cf99  test    eax, eax
0x18003cf9b  js      short loc_18003CFCB
0x18003cf9d  movaps  xmm0, xmmword ptr [rsp+1A0h+UnicodeString.Length]
0x18003cfa2  lea     r8, [rbp+0A0h+arg_10]; int *
0x18003cfa9  mov     rcx, [rsp+1A0h+var_140]; HKEY
0x18003cfae  lea     rdx, [rsp+1A0h+var_150]; struct _UNICODE_STRING
0x18003cfb3  movdqa  xmmword ptr [rsp+1A0h+var_150.Length], xmm0
0x18003cfb9  call    ?AipCompareSingleAssistiveTechnology@@YAJPEAUHKEY__@@U_UNICODE_STRING@@PEAH@Z; AipCompareSingleAssistiveTechnology(HKEY__ *,_UNICODE_STRING,int *)
0x18003cfbe  test    eax, eax
0x18003cfc0  js      short loc_18003CFCB
0x18003cfc2  cmp     [rbp+0A0h+arg_10], r12d
0x18003cfc9  jnz     short loc_18003D019
0x18003cfcb  lea     eax, [rbx+1]
0x18003cfce  cmp     eax, ebx
0x18003cfd0  jb      short loc_18003CFF6
0x18003cfd2  cmp     eax, r13d
0x18003cfd5  jz      short loc_18003CFF6
0x18003cfd7  lea     rcx, [rsp+1A0h+lpSubKey]
0x18003cfdc  mov     [rsp+1A0h+var_170], eax
0x18003cfe0  call    ?enumerate_current_index@?$key_iterator_data@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@reg@wil@@AEAAJXZ; wil::reg::key_iterator_data<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::enumerate_current_index(void)
0x18003cfe5  mov     dword ptr [rsp+1A0h+var_160], eax
0x18003cfe9  test    eax, eax
0x18003cfeb  js      short loc_18003CFFE
0x18003cfed  mov     ebx, [rsp+1A0h+var_170]
0x18003cff1  jmp     loc_18003CF6A
0x18003cff6  mov     dword ptr [rsp+1A0h+var_160], 80070057h
0x18003cffe  mov     rdx, [rsp+1A0h+var_168]
0x18003d003  lea     rcx, [rsp+1A0h+lpSubKey]
0x18003d008  call    ??$clear_name@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@reg_iterator_details@reg@wil@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@2@_K@Z; wil::reg::reg_iterator_details::clear_name<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &,unsigned __int64)
0x18003d00d  mov     ebx, r13d
0x18003d010  mov     [rsp+1A0h+var_170], ebx
0x18003d014  jmp     loc_18003CF6A
0x18003d019  bts     dword ptr [r15], 1Eh
0x18003d01e  lea     rcx, [rbp+0A0h+var_D0]
0x18003d022  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003d027  lea     rcx, [rsp+1A0h+lpSubKey]
0x18003d02c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003d031  lea     rcx, [rbp+0A0h+var_80]
0x18003d035  call    ??1?$pointer_range@V?$iterator_nothrow_t@V?$key_iterator_data@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@reg@wil@@@reg@wil@@@details@wil@@QEAA@XZ; wil::details::pointer_range<wil::reg::iterator_nothrow_t<wil::reg::key_iterator_data<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>>::~pointer_range<wil::reg::iterator_nothrow_t<wil::reg::key_iterator_data<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>>(void)
0x18003d03a  test    esi, esi
0x18003d03c  jns     short loc_18003D06E
0x18003d03e  mov     rcx, [rbp+0A8h]; this
0x18003d045  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18003d04c  mov     r9d, esi; char *
0x18003d04f  mov     edx, 9A3h; void *
0x18003d054  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d059  lea     rcx, [rsp+1A0h+UnicodeString]; UnicodeString
0x18003d05e  call    cs:__imp_RtlFreeUnicodeString
0x18003d065  nop     dword ptr [rax+rax+00h]
0x18003d06a  mov     ebx, esi
0x18003d06c  jmp     short loc_18003D082
0x18003d06e  lea     rcx, [rsp+1A0h+UnicodeString]; UnicodeString
0x18003d073  call    cs:__imp_RtlFreeUnicodeString
0x18003d07a  nop     dword ptr [rax+rax+00h]
0x18003d07f  mov     ebx, r12d
0x18003d082  lea     rcx, [rbp+0A0h+var_120]
0x18003d086  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003d08b  lea     rcx, [rsp+1A0h+var_140]
0x18003d090  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003d095  lea     rcx, [rbp+0A0h+phkResult]
0x18003d09c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003d0a1  mov     eax, ebx
0x18003d0a3  mov     rbx, [rsp+1A0h+arg_0]
0x18003d0ab  add     rsp, 170h
0x18003d0b2  pop     r15
0x18003d0b4  pop     r14
0x18003d0b6  pop     r13
0x18003d0b8  pop     r12
0x18003d0ba  pop     rdi
0x18003d0bb  pop     rsi
0x18003d0bc  pop     rbp
0x18003d0bd  retn
```
