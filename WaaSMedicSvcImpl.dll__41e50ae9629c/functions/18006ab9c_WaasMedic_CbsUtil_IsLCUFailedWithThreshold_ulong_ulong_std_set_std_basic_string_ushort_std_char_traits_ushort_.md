# WaasMedic::CbsUtil::IsLCUFailedWithThreshold(ulong,ulong,std::set<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,WaasMedic::WstringCaseInsensitiveCompare,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &,bool &,bool &)

- ea: `0x18006ab9c`
- end: `0x18006ae95`
- name: `?IsLCUFailedWithThreshold@CbsUtil@WaasMedic@@SAJKKAEBV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UWstringCaseInsensitiveCompare@WaasMedic@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEA_N1@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180061d00`

## callees

- `0x1800050a0`
- `0x1800098f0`
- `0x180009cd0`
- `0x18000bbd4`
- `0x180020d88`
- `0x1800269f8`
- `0x18002e81c`
- `0x18006a710`
- `0x18006ab9c`
- `0x18006b06c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006ac26`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006adb4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006ac26`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006adb4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006ac34`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006adc2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006ac34`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006adc2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006ac44`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006add2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006ac44`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006add2`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18006ae28`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18006ae28`

## string_xrefs

- `0x18006ae45`: `Found error entry: %s with: %d instances, ConfiguredErrorCount: %d.`
- `0x18006ad71`: `Matched terminal error: %s with: %d instances, ConfiguredTerminalErrorCount: %d.`
- `0x18006ad9d`: `IsLCUFailedWithThreshold: ConfigTerminalErrorCount: %d, ConfigLcuErrorCount:%d, IsTerminalError: %d, IsLcuFailed: %d`
- `0x18006ae5e`: `Software\Microsoft\Windows\CurrentVersion\Component Based Servicing\LCUInstallErrors`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WaasMedic::CbsUtil::IsLCUFailedWithThreshold(
        unsigned int a1,
        unsigned int a2,
        __int64 a3,
        _BYTE *a4,
        _BYTE *a5)
{
  unsigned __int8 v8; // r14
  int LCUFailureErrorCodesEnum; // eax
  unsigned int v10; // edi
  HKEY v11; // rbx
  HANDLE ProcessHeap; // rax
  int v14; // r13d
  LSTATUS i; // eax
  unsigned int *v16; // r9
  bool v17; // sf
  __int64 v18; // r8
  unsigned int v19; // r9d
  const unsigned __int16 *v20; // rdx
  unsigned __int8 v21; // cl
  HANDLE v22; // rax
  DWORD v23; // edx
  int lpReserved; // [rsp+20h] [rbp-71h]
  LPDWORD lpReserveda; // [rsp+20h] [rbp-71h]
  const char *lpType; // [rsp+28h] [rbp-69h]
  _BYTE v27[8]; // [rsp+40h] [rbp-51h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-49h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+50h] [rbp-41h] BYREF
  unsigned __int16 v30[2]; // [rsp+54h] [rbp-3Dh] BYREF
  DWORD Type; // [rsp+58h] [rbp-39h] BYREF
  DWORD cchValueName; // [rsp+5Ch] [rbp-35h] BYREF
  LPVOID lpMem; // [rsp+60h] [rbp-31h] BYREF
  __int64 v34; // [rsp+68h] [rbp-29h]
  _BYTE *v35; // [rsp+70h] [rbp-21h]
  _OWORD v36[2]; // [rsp+78h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+57h]

  v34 = a3;
  v35 = a5;
  v8 = 0;
  cbMaxValueNameLen = 0;
  hKey = 0;
  lpMem = 0;
  *a4 = 0;
  *a5 = 0;
  LCUFailureErrorCodesEnum = WaasMedic::CbsUtil::GetLCUFailureErrorCodesEnum(&hKey, &cbMaxValueNameLen, &lpMem);
  v10 = LCUFailureErrorCodesEnum;
  if ( LCUFailureErrorCodesEnum < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D0,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\cbsutil.cpp",
      (const char *)(unsigned int)LCUFailureErrorCodesEnum,
      lpReserved);
    v11 = (HKEY)lpMem;
LABEL_3:
    if ( v11 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v11);
    }
    if ( hKey )
      RegCloseKey(hKey);
    return v10;
  }
  if ( cbMaxValueNameLen )
  {
    cchValueName = cbMaxValueNameLen;
    Type = 0;
    v14 = 1;
    v11 = (HKEY)lpMem;
    for ( i = RegEnumValueW(hKey, 0, (LPWSTR)lpMem, &cchValueName, 0, &Type, 0, 0);
          ;
          i = RegEnumValueW(hKey, v23, (LPWSTR)v11, &cchValueName, 0, &Type, 0, 0) )
    {
      v10 = i;
      if ( i == 259 )
        goto LABEL_24;
      cchValueName = cbMaxValueNameLen;
      v8 = 0;
      v27[0] = 0;
      *a4 = 0;
      v17 = i < 0;
      if ( i > 0 )
      {
        v10 = (unsigned __int16)i | 0x80070000;
        v17 = 1;
      }
      if ( v17 )
        break;
      if ( Type == 4 )
      {
        *(_DWORD *)v30 = 0;
        if ( WaasMedic::RegQueryDwordValue((WaasMedic *)hKey, v11, v30, v16) >= 0 )
        {
          memset(v36, 0, sizeof(v36));
          v18 = -1;
          do
            ++v18;
          while ( *((_WORD *)v11 + v18) );
          std::wstring::_Construct<1,unsigned short const *>(v36, v11);
          WaasMedic::CbsUtil::IsTerminalError(v34, v36, v27);
          std::wstring::~wstring(v36);
          v8 = v27[0];
          v19 = *(_DWORD *)v30;
          if ( v27[0] )
          {
            *v35 = 1;
            if ( v19 >= a2 )
            {
              v20 = L"Matched terminal error: %s with: %d instances, ConfiguredTerminalErrorCount: %d.";
              v21 = 4;
LABEL_23:
              *a4 = 1;
              LogLevelW(v21, v20, v11);
LABEL_24:
              LODWORD(lpType) = (unsigned __int8)*a4;
              LODWORD(lpReserveda) = v8;
              LogLevelW(
                4u,
                L"IsLCUFailedWithThreshold: ConfigTerminalErrorCount: %d, ConfigLcuErrorCount:%d, IsTerminalError: %d, IsLcuFailed: %d",
                a2,
                a1,
                lpReserveda,
                lpType);
              goto LABEL_25;
            }
          }
          else if ( *(_DWORD *)v30 >= a1 )
          {
            v20 = L"Found error entry: %s with: %d instances, ConfiguredErrorCount: %d.";
            v21 = 5;
            goto LABEL_23;
          }
        }
        else
        {
          LogLevelW(3u, L"Failed to query value for %s under the LCU failures key. Ignoring.", v11);
        }
      }
      else
      {
        LogLevelW(3u, L"Unexpectedly found a value of type %d under the LCU failures key. Ignoring.");
      }
      v23 = v14++;
    }
    LODWORD(lpType) = v14 - 1;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x1E6,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\cbsutil.cpp",
      (const char *)v10,
      (int)"Enumeration failed at index %d, key %ws",
      lpType,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\Component Based Servicing\\LCUInstallErrors");
    goto LABEL_3;
  }
  v11 = (HKEY)lpMem;
LABEL_25:
  if ( v11 )
  {
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v11);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18006ab9c  push    rbp
0x18006ab9e  push    rbx
0x18006ab9f  push    rsi
0x18006aba0  push    rdi
0x18006aba1  push    r12
0x18006aba3  push    r13
0x18006aba5  push    r14
0x18006aba7  push    r15
0x18006aba9  lea     rbp, [rsp-17h]
0x18006abae  sub     rsp, 0A8h
0x18006abb5  mov     rax, cs:__security_cookie
0x18006abbc  xor     rax, rsp
0x18006abbf  mov     [rbp+4Fh+var_48], rax
0x18006abc3  mov     rsi, r9
0x18006abc6  mov     [rbp+4Fh+var_78], r8
0x18006abca  mov     r12d, edx
0x18006abcd  mov     r15d, ecx
0x18006abd0  mov     rax, [rbp+4Fh+arg_20]
0x18006abd4  mov     [rbp+4Fh+var_70], rax
0x18006abd8  xor     r14d, r14d
0x18006abdb  mov     [rbp+4Fh+cbMaxValueNameLen], r14d
0x18006abdf  mov     [rbp+4Fh+hKey], r14
0x18006abe3  mov     [rbp+4Fh+lpMem], r14
0x18006abe7  mov     [r9], r14b
0x18006abea  mov     [rax], r14b
0x18006abed  lea     r8, [rbp+4Fh+lpMem]
0x18006abf1  lea     rdx, [rbp+4Fh+cbMaxValueNameLen]; lpcbMaxValueNameLen
0x18006abf5  lea     rcx, [rbp+4Fh+hKey]; int
0x18006abf9  call    ?GetLCUFailureErrorCodesEnum@CbsUtil@WaasMedic@@CAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAKAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@4@@Z; WaasMedic::CbsUtil::GetLCUFailureErrorCodesEnum(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,ulong &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18006abfe  mov     edi, eax
0x18006ac00  test    eax, eax
0x18006ac02  jns     short loc_18006AC51
0x18006ac04  mov     rcx, [rbp+57h]; this
0x18006ac08  mov     r9d, eax; char *
0x18006ac0b  lea     r8, aOnecoreEnduser_11; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18006ac12  mov     edx, 1D0h; void *
0x18006ac17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006ac1c  nop
0x18006ac1d  mov     rbx, [rbp+4Fh+lpMem]
0x18006ac21  test    rbx, rbx
0x18006ac24  jz      short loc_18006AC3B
0x18006ac26  call    cs:__imp_GetProcessHeap
0x18006ac2c  mov     rcx, rax; hHeap
0x18006ac2f  mov     r8, rbx; lpMem
0x18006ac32  xor     edx, edx; dwFlags
0x18006ac34  call    cs:__imp_HeapFree
0x18006ac3a  nop
0x18006ac3b  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18006ac3f  test    rcx, rcx
0x18006ac42  jz      short loc_18006AC4A
0x18006ac44  call    cs:__imp_RegCloseKey
0x18006ac4a  mov     eax, edi
0x18006ac4c  jmp     loc_18006ADDA
0x18006ac51  mov     eax, [rbp+4Fh+cbMaxValueNameLen]
0x18006ac54  test    eax, eax
0x18006ac56  jnz     short loc_18006AC61
0x18006ac58  mov     rbx, [rbp+4Fh+lpMem]
0x18006ac5c  jmp     loc_18006ADAF
0x18006ac61  mov     [rbp+4Fh+cchValueName], eax
0x18006ac64  mov     [rbp+4Fh+Type], r14d
0x18006ac68  xor     ecx, ecx
0x18006ac6a  lea     r13d, [rcx+1]
0x18006ac6e  mov     [rsp+0E0h+lpcbData], rcx
0x18006ac73  mov     [rsp+0E0h+lpData], rcx
0x18006ac78  lea     rax, [rbp+4Fh+Type]
0x18006ac7c  mov     [rsp+0E0h+lpType], rax
0x18006ac81  mov     [rsp+0E0h+lpReserved], rcx
0x18006ac86  mov     rbx, [rbp+4Fh+lpMem]
0x18006ac8a  xor     edx, edx
0x18006ac8c  jmp     loc_18006AE1D
0x18006ac91  mov     eax, [rbp+4Fh+cbMaxValueNameLen]
0x18006ac94  mov     [rbp+4Fh+cchValueName], eax
0x18006ac97  xor     eax, eax
0x18006ac99  mov     r14b, al
0x18006ac9c  mov     [rbp+4Fh+var_A0], al
0x18006ac9f  mov     [rsi], al
0x18006aca1  test    edi, edi
0x18006aca3  jle     short loc_18006ACB0
0x18006aca5  movzx   edi, di
0x18006aca8  or      edi, 80070000h
0x18006acae  test    edi, edi
0x18006acb0  js      loc_18006AE56
0x18006acb6  mov     r8d, [rbp+4Fh+Type]
0x18006acba  cmp     r8d, 4
0x18006acbe  jz      short loc_18006ACD8
0x18006acc0  lea     rdx, aUnexpectedlyFo; "Unexpectedly found a value of type %d u"...
0x18006acc7  mov     ecx, 3; unsigned __int8
0x18006accc  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18006acd1  xor     edi, edi
0x18006acd3  jmp     loc_18006ADFF
0x18006acd8  xor     edi, edi
0x18006acda  mov     dword ptr [rbp+4Fh+var_8C], edi
0x18006acdd  lea     r8, [rbp+4Fh+var_8C]; unsigned __int16 *
0x18006ace1  mov     rdx, rbx; HKEY
0x18006ace4  mov     rcx, [rbp+4Fh+hKey]; this
0x18006ace8  call    ?RegQueryDwordValue@WaasMedic@@YAJPEAUHKEY__@@PEBGPEAK@Z; WaasMedic::RegQueryDwordValue(HKEY__ *,ushort const *,ulong *)
0x18006aced  test    eax, eax
0x18006acef  jns     short loc_18006AD08
0x18006acf1  mov     r8, rbx
0x18006acf4  lea     rdx, aFailedToQueryV; "Failed to query value for %s under the "...
0x18006acfb  lea     ecx, [rdi+3]; unsigned __int8
0x18006acfe  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18006ad03  jmp     loc_18006ADFF
0x18006ad08  xorps   xmm0, xmm0
0x18006ad0b  movups  [rbp+4Fh+var_68], xmm0
0x18006ad0f  xorps   xmm1, xmm1
0x18006ad12  movdqu  [rbp+4Fh+var_58], xmm1
0x18006ad17  or      r8, 0FFFFFFFFFFFFFFFFh
0x18006ad1b  inc     r8
0x18006ad1e  cmp     [rbx+r8*2], di
0x18006ad23  jnz     short loc_18006AD1B
0x18006ad25  mov     rdx, rbx
0x18006ad28  lea     rcx, [rbp+4Fh+var_68]
0x18006ad2c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18006ad31  lea     r8, [rbp+4Fh+var_A0]
0x18006ad35  lea     rdx, [rbp+4Fh+var_68]
0x18006ad39  mov     rcx, [rbp+4Fh+var_78]
0x18006ad3d  call    ?IsTerminalError@CbsUtil@WaasMedic@@SAXAEBV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UWstringCaseInsensitiveCompare@WaasMedic@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@AEA_N@Z; WaasMedic::CbsUtil::IsTerminalError(std::set<std::wstring,WaasMedic::WstringCaseInsensitiveCompare,std::allocator<std::wstring>> const &,std::wstring const &,bool &)
0x18006ad42  lea     rcx, [rbp+4Fh+var_68]; void *
0x18006ad46  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006ad4b  mov     r14b, [rbp+4Fh+var_A0]
0x18006ad4f  mov     r9d, dword ptr [rbp+4Fh+var_8C]
0x18006ad53  test    r14b, r14b
0x18006ad56  jz      loc_18006ADFA
0x18006ad5c  mov     rax, [rbp+4Fh+var_70]
0x18006ad60  mov     byte ptr [rax], 1
0x18006ad63  cmp     r9d, r12d
0x18006ad66  jb      loc_18006ADFF
0x18006ad6c  mov     dword ptr [rsp+0E0h+lpReserved], r12d
0x18006ad71  lea     rdx, aMatchedTermina; "Matched terminal error: %s with: %d ins"...
0x18006ad78  mov     ecx, 4; unsigned __int8
0x18006ad7d  mov     r8, rbx
0x18006ad80  mov     byte ptr [rsi], 1
0x18006ad83  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18006ad88  movzx   eax, byte ptr [rsi]
0x18006ad8b  movzx   edx, r14b
0x18006ad8f  mov     dword ptr [rsp+0E0h+lpType], eax
0x18006ad93  mov     dword ptr [rsp+0E0h+lpReserved], edx
0x18006ad97  mov     r9d, r15d
0x18006ad9a  mov     r8d, r12d
0x18006ad9d  lea     rdx, aIslcufailedwit; "IsLCUFailedWithThreshold: ConfigTermina"...
0x18006ada4  mov     ecx, 4; unsigned __int8
0x18006ada9  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18006adae  nop
0x18006adaf  test    rbx, rbx
0x18006adb2  jz      short loc_18006ADC9
0x18006adb4  call    cs:__imp_GetProcessHeap
0x18006adba  mov     r8, rbx; lpMem
0x18006adbd  xor     edx, edx; dwFlags
0x18006adbf  mov     rcx, rax; hHeap
0x18006adc2  call    cs:__imp_HeapFree
0x18006adc8  nop
0x18006adc9  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18006adcd  test    rcx, rcx
0x18006add0  jz      short loc_18006ADD8
0x18006add2  call    cs:__imp_RegCloseKey
0x18006add8  xor     eax, eax
0x18006adda  mov     rcx, [rbp+4Fh+var_48]
0x18006adde  xor     rcx, rsp; StackCookie
0x18006ade1  call    __security_check_cookie
0x18006ade6  add     rsp, 0A8h
0x18006aded  pop     r15
0x18006adef  pop     r14
0x18006adf1  pop     r13
0x18006adf3  pop     r12
0x18006adf5  pop     rdi
0x18006adf6  pop     rsi
0x18006adf7  pop     rbx
0x18006adf8  pop     rbp
0x18006adf9  retn
0x18006adfa  cmp     r9d, r15d
0x18006adfd  jnb     short loc_18006AE40
0x18006adff  mov     edx, r13d; dwIndex
0x18006ae02  inc     r13d
0x18006ae05  mov     [rsp+0E0h+lpcbData], rdi; lpcbData
0x18006ae0a  mov     [rsp+0E0h+lpData], rdi; lpData
0x18006ae0f  lea     rax, [rbp+4Fh+Type]
0x18006ae13  mov     [rsp+0E0h+lpType], rax; lpType
0x18006ae18  mov     [rsp+0E0h+lpReserved], rdi; lpReserved
0x18006ae1d  lea     r9, [rbp+4Fh+cchValueName]; lpcchValueName
0x18006ae21  mov     r8, rbx; lpValueName
0x18006ae24  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18006ae28  call    cs:__imp_RegEnumValueW
0x18006ae2e  cmp     eax, 103h
0x18006ae33  mov     edi, eax
0x18006ae35  jnz     loc_18006AC91
0x18006ae3b  jmp     loc_18006AD88
0x18006ae40  mov     dword ptr [rsp+0E0h+lpReserved], r15d
0x18006ae45  lea     rdx, aFoundErrorEntr; "Found error entry: %s with: %d instance"...
0x18006ae4c  mov     ecx, 5
0x18006ae51  jmp     loc_18006AD7D
0x18006ae56  lea     eax, [r13-1]
0x18006ae5a  mov     rcx, [rbp+57h]; this
0x18006ae5e  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18006ae65  mov     [rsp+0E0h+lpData], rdx
0x18006ae6a  mov     dword ptr [rsp+0E0h+lpType], eax; char *
0x18006ae6e  lea     rax, aEnumerationFai; "Enumeration failed at index %d, key %ws"
0x18006ae75  mov     [rsp+0E0h+lpReserved], rax; int
0x18006ae7a  mov     r9d, edi; char *
0x18006ae7d  lea     r8, aOnecoreEnduser_11; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18006ae84  mov     edx, 1E6h; void *
0x18006ae89  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18006ae8e  nop
0x18006ae8f  jmp     loc_18006AC21
```
