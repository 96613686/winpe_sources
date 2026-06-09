# AipCheckAssistiveTechnologyList(ushort const *,ulong *)

- ea: `0x18003fa00`
- end: `0x18003fddd`
- name: `?AipCheckAssistiveTechnologyList@@YAJPEBGPEAK@Z`
- size: `989`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `14`
- tags: `reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002ed98`
- `0x18003d070`

## callees

- `0x18000720c`
- `0x180011c6c`
- `0x180018dbc`
- `0x18001d764`
- `0x18002a8e8`
- `0x18002b084`
- `0x18002b0a0`
- `0x18003f35c`
- `0x18003f454`
- `0x18003f784`
- `0x18003fa00`
- `0x18003fde4`
- `0x1800405b4`
- `0x1800407a4`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18003fd9e`
- `ntdll!RtlFreeUnicodeString` at `0x18003fd9e`

## string_xrefs

- `0x18003fa5c`: `onecoreuap\ds\security\services\lua\appinfo\paths.cxx`
- `0x18003fa98`: `onecoreuap\ds\security\services\lua\appinfo\paths.cxx`
- `0x18003fd80`: `onecoreuap\ds\security\services\lua\appinfo\paths.cxx`
- `0x18003fa82`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\ATs`

## pseudocode

```c
__int64 __fastcall AipCheckAssistiveTechnologyList(const unsigned __int16 *a1, unsigned int *a2)
{
  unsigned int v3; // eax
  unsigned int v4; // ebx
  int v5; // eax
  __int64 v6; // rbx
  const WCHAR *v7; // rsi
  int v8; // r14d
  int v9; // edi
  LPCWSTR v10; // r12
  unsigned int v11; // ebx
  __int64 v12; // r14
  const WCHAR *v13; // r13
  int v14; // esi
  int v15; // eax
  LPCWSTR lpSubKey[2]; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+30h] [rbp-D0h]
  __int64 v19; // [rsp+38h] [rbp-C8h]
  char *v20; // [rsp+40h] [rbp-C0h]
  struct _UNICODE_STRING v21; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v22; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v23; // [rsp+68h] [rbp-98h] BYREF
  int v24; // [rsp+78h] [rbp-88h]
  int v25; // [rsp+7Ch] [rbp-84h]
  __int64 v26; // [rsp+80h] [rbp-80h]
  __int64 v27; // [rsp+88h] [rbp-78h]
  __int128 v28; // [rsp+90h] [rbp-70h] BYREF
  int v29; // [rsp+A0h] [rbp-60h]
  __int64 v30; // [rsp+A8h] [rbp-58h]
  int v31; // [rsp+B0h] [rbp-50h]
  struct _UNICODE_STRING UnicodeString; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v33; // [rsp+D0h] [rbp-30h] BYREF
  const WCHAR *v34; // [rsp+D8h] [rbp-28h]
  unsigned int v35; // [rsp+E0h] [rbp-20h]
  __int64 v36; // [rsp+E8h] [rbp-18h]
  int v37; // [rsp+F0h] [rbp-10h]
  __int64 v38; // [rsp+F8h] [rbp-8h]
  const WCHAR *v39; // [rsp+100h] [rbp+0h]
  __int64 v40; // [rsp+108h] [rbp+8h]
  __int64 v41; // [rsp+110h] [rbp+10h]
  int v42; // [rsp+118h] [rbp+18h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]
  int v44; // [rsp+170h] [rbp+70h] BYREF
  HKEY phkResult; // [rsp+178h] [rbp+78h] BYREF

  phkResult = 0;
  v22 = 0;
  v29 = -1;
  v28 = 0;
  v30 = 0;
  v31 = 0;
  UnicodeString = 0;
  v44 = 0;
  v3 = AipNormalizePath(a1, &UnicodeString);
  if ( v3 )
  {
    v4 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0xA5B,
           (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\paths.cxx",
           (const char *)v3,
           (unsigned int)lpSubKey[0]);
  }
  else
  {
    v5 = wil::reg::open_unique_key_nothrow(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\ATs",
           &phkResult);                         // Registry path-trust audit: Assistive Technology list root is HKLM\...\Accessibility\ATs; StartExe values are compared after client impersonation/path normalization.
    v4 = v5;
    if ( v5 >= 0 )
    {
      lpSubKey[0] = 0;
      lpSubKey[1] = (LPCWSTR)phkResult;
      v18 = -1;
      v19 = 0;
      LODWORD(v20) = 0;
      if ( phkResult )
      {
        v18 = 0;
        LODWORD(v20) = wil::reg::key_iterator_data<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::enumerate_current_index(lpSubKey);
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        &v28,
        lpSubKey);
      v6 = v19;
      v7 = lpSubKey[1];
      v8 = v18;
      v9 = (int)v20;
      *((LPCWSTR *)&v28 + 1) = lpSubKey[1];
      v30 = v19;
      v29 = v18;
      v19 = 0;
      v31 = (int)v20;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(lpSubKey);
      v25 = 0;
      v27 = 0;
      v24 = -1;
      v26 = 0;
      v18 = -1;
      v19 = 0;
      v23 = 0;
      *(_OWORD *)lpSubKey = 0;
      if ( (_QWORD)v28 )
        wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &v21,
          v28,
          v6);
      else
        *(_QWORD *)&v21.Length = 0;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        lpSubKey,
        &v21);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v21);
      lpSubKey[1] = v7;
      v18 = v8;
      LODWORD(v20) = v9;
      v19 = v6 & -(__int64)(lpSubKey[0] != 0);
      wil::make_range<wil::reg::iterator_nothrow_t<wil::reg::key_iterator_data<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>>(
        &v33,
        lpSubKey,
        &v23);
      lpSubKey[0] = 0;
      lpSubKey[1] = 0;
      v18 = -1;
      v19 = 0;
      if ( v33 )
        wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &v21,
          v33,
          v36);
      else
        *(_QWORD *)&v21.Length = 0;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        lpSubKey,
        &v21);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v21);
      v10 = v34;
      v11 = v35;
      lpSubKey[1] = v34;
      v12 = v36 & -(__int64)(lpSubKey[0] != 0);
      v18 = v35;
      v19 = v12;
      LODWORD(v20) = v37;
      v24 = -1;
      v26 = 0;
      v23 = 0;
      if ( v38 )
        wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &v21,
          v38,
          v41);
      else
        *(_QWORD *)&v21.Length = 0;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        &v23,
        &v21);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v21);
      v13 = v39;
      v14 = v40;
      *((_QWORD *)&v23 + 1) = v39;
      v24 = v40;
      v26 = v41 & -(__int64)((_QWORD)v23 != 0);
      LODWORD(v27) = v42;
      while ( v11 != -1 && v14 != -1 && v10 != v13 || v11 != v14 )
      {
        if ( (int)wil::reg::open_unique_key_nothrow(phkResult, lpSubKey[0], &v22) >= 0 )
        {
          v21 = UnicodeString;
          if ( (int)AipCompareSingleAssistiveTechnology(v22, &v21, &v44) >= 0 )
          {
            if ( v44 )
            {
              *a2 |= 0x40000000u;
              break;
            }
          }
        }
        if ( v11 + 1 < v11 || v11 == -2 )
        {
          v15 = -2147024809;
        }
        else
        {
          v18 = v11 + 1;
          v15 = wil::reg::key_iterator_data<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::enumerate_current_index(lpSubKey);
          v12 = v19;
          v11 = v18;
          v10 = lpSubKey[1];
        }
        LODWORD(v20) = v15;
        if ( v15 < 0 )
        {
          wil::reg::reg_iterator_details::clear_name<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            lpSubKey,
            v12);
          v11 = -1;
          v18 = -1;
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v23);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(lpSubKey);
      wil::details::pointer_range<wil::reg::iterator_nothrow_t<wil::reg::key_iterator_data<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>>::~pointer_range<wil::reg::iterator_nothrow_t<wil::reg::key_iterator_data<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>>(&v33);
      if ( v9 >= 0 )
      {
        v4 = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA73,
          (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\paths.cxx",
          (const char *)(unsigned int)v9,
          (int)lpSubKey[0]);
        v4 = v9;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA5D,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\paths.cxx",
        (const char *)(unsigned int)v5,
        (int)lpSubKey[0]);
    }
  }
  RtlFreeUnicodeString(&UnicodeString);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v22);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  return v4;
}

```

## disassembly

```asm
0x18003fa00  mov     [rsp-8+arg_0], rbx
0x18003fa05  push    rbp
0x18003fa06  push    rsi
0x18003fa07  push    rdi
0x18003fa08  push    r12
0x18003fa0a  push    r13
0x18003fa0c  push    r14
0x18003fa0e  push    r15
0x18003fa10  lea     rbp, [rsp-20h]
0x18003fa15  sub     rsp, 120h
0x18003fa1c  xor     r13d, r13d
0x18003fa1f  xorps   xmm0, xmm0
0x18003fa22  mov     r15, rdx
0x18003fa25  mov     [rbp+50h+phkResult], r13
0x18003fa29  or      r12d, 0FFFFFFFFh
0x18003fa2d  mov     [rsp+150h+var_F0], r13
0x18003fa32  lea     rdx, [rbp+50h+UnicodeString]; struct _UNICODE_STRING *
0x18003fa36  mov     [rbp+50h+var_B0], r12d
0x18003fa3a  movdqu  [rbp+50h+var_C0], xmm0
0x18003fa3f  mov     [rbp+50h+var_A8], r13
0x18003fa43  mov     [rbp+50h+var_A0], r13d
0x18003fa47  movups  xmmword ptr [rbp+50h+UnicodeString.Length], xmm0
0x18003fa4b  mov     [rbp+50h+arg_10], r13d
0x18003fa4f  call    ?AipNormalizePath@@YAKPEBGPEAU_UNICODE_STRING@@@Z; AipNormalizePath(ushort const *,_UNICODE_STRING *)
0x18003fa54  test    eax, eax
0x18003fa56  jz      short loc_18003FA77
0x18003fa58  mov     rcx, [rbp+58h]; this
0x18003fa5c  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18003fa63  mov     r9d, eax; char *
0x18003fa66  mov     edx, 0A5Bh; void *
0x18003fa6b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003fa70  mov     ebx, eax
0x18003fa72  jmp     loc_18003FD9A
0x18003fa77  lea     r8, [rbp+50h+phkResult]; phkResult
0x18003fa7b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003fa82  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18003fa89  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; Registry path-trust audit: Assistive Technology list root is HKLM\...\Accessibility\ATs; StartExe values are compared after client impersonation/path normalization.
0x18003fa8e  mov     ebx, eax
0x18003fa90  test    eax, eax
0x18003fa92  jns     short loc_18003FAB1
0x18003fa94  mov     rcx, [rbp+58h]; this
0x18003fa98  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18003fa9f  mov     r9d, eax; char *
0x18003faa2  mov     edx, 0A5Dh; void *
0x18003faa7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003faac  jmp     loc_18003FD9A
0x18003fab1  mov     rax, [rbp+50h+phkResult]
0x18003fab5  mov     [rsp+150h+lpSubKey], r13
0x18003faba  mov     [rsp+150h+lpSubKey+8], rax
0x18003fabf  mov     [rsp+150h+var_120], r12d
0x18003fac4  mov     [rsp+150h+var_118], r13
0x18003fac9  mov     dword ptr [rsp+150h+var_110], r13d
0x18003face  test    rax, rax
0x18003fad1  jz      short loc_18003FAE6
0x18003fad3  lea     rcx, [rsp+150h+lpSubKey]
0x18003fad8  mov     [rsp+150h+var_120], r13d
0x18003fadd  call    ?enumerate_current_index@?$key_iterator_data@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@reg@wil@@AEAAJXZ; wil::reg::key_iterator_data<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::enumerate_current_index(void)
0x18003fae2  mov     dword ptr [rsp+150h+var_110], eax
0x18003fae6  lea     rdx, [rsp+150h+lpSubKey]
0x18003faeb  lea     rcx, [rbp+50h+var_C0]
0x18003faef  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18003faf4  mov     rbx, [rsp+150h+var_118]
0x18003faf9  lea     rcx, [rsp+150h+lpSubKey]
0x18003fafe  mov     rsi, [rsp+150h+lpSubKey+8]
0x18003fb03  mov     r14d, [rsp+150h+var_120]
0x18003fb08  mov     edi, dword ptr [rsp+150h+var_110]
0x18003fb0c  mov     qword ptr [rbp+50h+var_C0+8], rsi
0x18003fb10  mov     [rbp+50h+var_A8], rbx
0x18003fb14  mov     [rbp+50h+var_B0], r14d
0x18003fb18  mov     [rsp+150h+var_118], r13
0x18003fb1d  mov     [rbp+50h+var_A0], edi
0x18003fb20  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003fb25  mov     rdx, qword ptr [rbp+50h+var_C0]
0x18003fb29  xorps   xmm0, xmm0
0x18003fb2c  mov     [rsp+150h+var_D4], r13d
0x18003fb31  mov     [rbp+50h+var_C8], r13
0x18003fb35  mov     [rsp+150h+var_D8], r12d
0x18003fb3a  mov     [rbp+50h+var_D0], r13
0x18003fb3e  mov     [rsp+150h+var_120], r12d
0x18003fb43  mov     [rsp+150h+var_118], r13
0x18003fb48  movdqu  [rsp+150h+var_E8], xmm0
0x18003fb4e  movdqu  xmmword ptr [rsp+150h+lpSubKey], xmm0
0x18003fb54  test    rdx, rdx
0x18003fb57  jnz     short loc_18003FB60
0x18003fb59  mov     qword ptr [rsp+150h+var_100.Length], r13
0x18003fb5e  jmp     short loc_18003FB6D
0x18003fb60  mov     r8, rbx
0x18003fb63  lea     rcx, [rsp+150h+var_100]
0x18003fb68  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18003fb6d  lea     rdx, [rsp+150h+var_100]
0x18003fb72  lea     rcx, [rsp+150h+lpSubKey]
0x18003fb77  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18003fb7c  lea     rcx, [rsp+150h+var_100]
0x18003fb81  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003fb86  cmp     [rsp+150h+lpSubKey], r13
0x18003fb8b  lea     r8, [rsp+150h+var_E8]
0x18003fb90  lea     rdx, [rsp+150h+lpSubKey]
0x18003fb95  mov     [rsp+150h+lpSubKey+8], rsi
0x18003fb9a  setnz   al
0x18003fb9d  mov     [rsp+150h+var_120], r14d
0x18003fba2  neg     al
0x18003fba4  mov     dword ptr [rsp+150h+var_110], edi
0x18003fba8  sbb     rcx, rcx
0x18003fbab  and     rcx, rbx
0x18003fbae  mov     [rsp+150h+var_118], rcx
0x18003fbb3  lea     rcx, [rbp+50h+var_80]
0x18003fbb7  call    ??$make_range@V?$iterator_nothrow_t@V?$key_iterator_data@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@reg@wil@@@reg@wil@@@wil@@YA?AV?$pointer_range@V?$iterator_nothrow_t@V?$key_iterator_data@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@reg@wil@@@reg@wil@@@details@0@V?$iterator_nothrow_t@V?$key_iterator_data@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@reg@wil@@@reg@0@0@Z; wil::make_range<wil::reg::iterator_nothrow_t<wil::reg::key_iterator_data<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>>(wil::reg::iterator_nothrow_t<wil::reg::key_iterator_data<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>,wil::reg::iterator_nothrow_t<wil::reg::key_iterator_data<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>)
0x18003fbbc  mov     rdx, [rbp+50h+var_80]
0x18003fbc0  mov     [rsp+150h+lpSubKey], r13; int
0x18003fbc5  mov     [rsp+150h+lpSubKey+8], r13
0x18003fbca  mov     [rsp+150h+var_120], r12d
0x18003fbcf  mov     [rsp+150h+var_118], r13
0x18003fbd4  test    rdx, rdx
0x18003fbd7  jnz     short loc_18003FBE0
0x18003fbd9  mov     qword ptr [rsp+150h+var_100.Length], r13
0x18003fbde  jmp     short loc_18003FBEE
0x18003fbe0  mov     r8, [rbp+50h+var_68]
0x18003fbe4  lea     rcx, [rsp+150h+var_100]
0x18003fbe9  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18003fbee  lea     rdx, [rsp+150h+var_100]
0x18003fbf3  lea     rcx, [rsp+150h+lpSubKey]
0x18003fbf8  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18003fbfd  lea     rcx, [rsp+150h+var_100]
0x18003fc02  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003fc07  cmp     [rsp+150h+lpSubKey], r13
0x18003fc0c  xorps   xmm0, xmm0
0x18003fc0f  mov     rdx, [rbp+50h+var_58]
0x18003fc13  mov     r12, [rbp+50h+var_78]
0x18003fc17  setnz   al
0x18003fc1a  mov     ebx, [rbp+50h+var_70]
0x18003fc1d  neg     al
0x18003fc1f  mov     eax, [rbp+50h+var_60]
0x18003fc22  sbb     r14, r14
0x18003fc25  mov     [rsp+150h+lpSubKey+8], r12
0x18003fc2a  and     r14, [rbp+50h+var_68]
0x18003fc2e  mov     [rsp+150h+var_120], ebx
0x18003fc32  mov     [rsp+150h+var_118], r14
0x18003fc37  mov     dword ptr [rsp+150h+var_110], eax
0x18003fc3b  mov     [rsp+150h+var_D8], 0FFFFFFFFh
0x18003fc43  mov     [rbp+50h+var_D0], r13
0x18003fc47  movdqu  [rsp+150h+var_E8], xmm0
0x18003fc4d  test    rdx, rdx
0x18003fc50  jnz     short loc_18003FC59
0x18003fc52  mov     qword ptr [rsp+150h+var_100.Length], r13
0x18003fc57  jmp     short loc_18003FC67
0x18003fc59  mov     r8, [rbp+50h+var_40]
0x18003fc5d  lea     rcx, [rsp+150h+var_100]
0x18003fc62  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18003fc67  lea     rdx, [rsp+150h+var_100]
0x18003fc6c  lea     rcx, [rsp+150h+var_E8]
0x18003fc71  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18003fc76  lea     rcx, [rsp+150h+var_100]
0x18003fc7b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003fc80  cmp     qword ptr [rsp+150h+var_E8], 0
0x18003fc86  mov     r13, [rbp+50h+var_50]
0x18003fc8a  mov     rsi, [rbp+50h+var_48]
0x18003fc8e  setnz   al
0x18003fc91  neg     al
0x18003fc93  mov     qword ptr [rsp+150h+var_E8+8], r13
0x18003fc98  mov     [rsp+150h+var_D8], esi
0x18003fc9c  sbb     rax, rax
0x18003fc9f  and     rax, [rbp+50h+var_40]
0x18003fca3  mov     [rbp+50h+var_D0], rax
0x18003fca7  mov     eax, [rbp+50h+var_38]
0x18003fcaa  mov     dword ptr [rbp+50h+var_C8], eax
0x18003fcad  cmp     ebx, 0FFFFFFFFh
0x18003fcb0  jz      short loc_18003FCBC
0x18003fcb2  cmp     esi, 0FFFFFFFFh
0x18003fcb5  jz      short loc_18003FCBC
0x18003fcb7  cmp     r12, r13
0x18003fcba  jnz     short loc_18003FCC4
0x18003fcbc  cmp     ebx, esi
0x18003fcbe  jz      loc_18003FD5B
0x18003fcc4  mov     rdx, [rsp+150h+lpSubKey]; lpSubKey
0x18003fcc9  lea     r8, [rsp+150h+var_F0]; phkResult
0x18003fcce  mov     rcx, [rbp+50h+phkResult]; hKey
0x18003fcd2  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x18003fcd7  test    eax, eax
0x18003fcd9  js      short loc_18003FD02
0x18003fcdb  movaps  xmm0, xmmword ptr [rbp+50h+UnicodeString.Length]
0x18003fcdf  lea     r8, [rbp+50h+arg_10]; int *
0x18003fce3  mov     rcx, [rsp+150h+var_F0]; HKEY
0x18003fce8  lea     rdx, [rsp+150h+var_100]; struct _UNICODE_STRING
0x18003fced  movdqa  xmmword ptr [rsp+150h+var_100.Length], xmm0
0x18003fcf3  call    ?AipCompareSingleAssistiveTechnology@@YAJPEAUHKEY__@@U_UNICODE_STRING@@PEAH@Z; AipCompareSingleAssistiveTechnology(HKEY__ *,_UNICODE_STRING,int *)
0x18003fcf8  test    eax, eax
0x18003fcfa  js      short loc_18003FD02
0x18003fcfc  cmp     [rbp+50h+arg_10], 0
0x18003fd00  jnz     short loc_18003FD56
0x18003fd02  lea     eax, [rbx+1]
0x18003fd05  cmp     eax, ebx
0x18003fd07  jb      short loc_18003FD2C
0x18003fd09  cmp     eax, 0FFFFFFFFh
0x18003fd0c  jz      short loc_18003FD2C
0x18003fd0e  lea     rcx, [rsp+150h+lpSubKey]
0x18003fd13  mov     [rsp+150h+var_120], eax
0x18003fd17  call    ?enumerate_current_index@?$key_iterator_data@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@reg@wil@@AEAAJXZ; wil::reg::key_iterator_data<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::enumerate_current_index(void)
0x18003fd1c  mov     r14, [rsp+150h+var_118]
0x18003fd21  mov     ebx, [rsp+150h+var_120]
0x18003fd25  mov     r12, [rsp+150h+lpSubKey+8]
0x18003fd2a  jmp     short loc_18003FD31
0x18003fd2c  mov     eax, 80070057h
0x18003fd31  mov     dword ptr [rsp+150h+var_110], eax
0x18003fd35  test    eax, eax
0x18003fd37  jns     loc_18003FCAD
0x18003fd3d  mov     rdx, r14
0x18003fd40  lea     rcx, [rsp+150h+lpSubKey]
0x18003fd45  call    ??$clear_name@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@reg_iterator_details@reg@wil@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@2@_K@Z; wil::reg::reg_iterator_details::clear_name<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &,unsigned __int64)
0x18003fd4a  or      ebx, 0FFFFFFFFh
0x18003fd4d  mov     [rsp+150h+var_120], ebx
0x18003fd51  jmp     loc_18003FCAD
0x18003fd56  bts     dword ptr [r15], 1Eh
0x18003fd5b  lea     rcx, [rsp+150h+var_E8]
0x18003fd60  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003fd65  lea     rcx, [rsp+150h+lpSubKey]
0x18003fd6a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003fd6f  lea     rcx, [rbp+50h+var_80]
0x18003fd73  call    ??1?$pointer_range@V?$iterator_nothrow_t@V?$key_iterator_data@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@reg@wil@@@reg@wil@@@details@wil@@QEAA@XZ; wil::details::pointer_range<wil::reg::iterator_nothrow_t<wil::reg::key_iterator_data<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>>::~pointer_range<wil::reg::iterator_nothrow_t<wil::reg::key_iterator_data<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>>(void)
0x18003fd78  test    edi, edi
0x18003fd7a  jns     short loc_18003FD98
0x18003fd7c  mov     rcx, [rbp+58h]; this
0x18003fd80  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18003fd87  mov     r9d, edi; char *
0x18003fd8a  mov     edx, 0A73h; void *
0x18003fd8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fd94  mov     ebx, edi
0x18003fd96  jmp     short loc_18003FD9A
0x18003fd98  xor     ebx, ebx
0x18003fd9a  lea     rcx, [rbp+50h+UnicodeString]; UnicodeString
0x18003fd9e  call    cs:__imp_RtlFreeUnicodeString
0x18003fda4  lea     rcx, [rbp+50h+var_C0]
0x18003fda8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003fdad  lea     rcx, [rsp+150h+var_F0]
0x18003fdb2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003fdb7  lea     rcx, [rbp+50h+phkResult]
0x18003fdbb  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003fdc0  mov     eax, ebx
0x18003fdc2  mov     rbx, [rsp+150h+arg_0]
0x18003fdca  add     rsp, 120h
0x18003fdd1  pop     r15
0x18003fdd3  pop     r14
0x18003fdd5  pop     r13
0x18003fdd7  pop     r12
0x18003fdd9  pop     rdi
0x18003fdda  pop     rsi
0x18003fddb  pop     rbp
0x18003fddc  retn
```
