# EnterpriseFeatureControl::GetFeatureStatusCache(ulong,bool *,bool *)

- ea: `0x180017a80`
- end: `0x180017c10`
- name: `?GetFeatureStatusCache@EnterpriseFeatureControl@@CAJKPEA_N0@Z`
- size: `400`
- prototype: `__int64 __fastcall(unsigned int, bool *, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018ff4`

## callees

- `0x18000970c`
- `0x18000972c`
- `0x180010248`
- `0x180012940`
- `0x180017a80`
- `0x180017dbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017afd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017afd`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180017bd4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180017bd4`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x180017af1`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x180017b90`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x180017af1`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x180017b90`

## pseudocode

```c
__int64 __fastcall EnterpriseFeatureControl::GetFeatureStatusCache(unsigned int a1, bool *a2, bool *a3)
{
  __int64 v5; // rdx
  unsigned int v6; // ebx
  int ProcessEnvName; // eax
  unsigned __int64 v8; // r9
  __int64 v9; // rdx
  DWORD EnvironmentVariableW; // eax
  __int64 v11; // rdx
  __int64 v12; // rdi
  signed int LastError; // eax
  const WCHAR *v14; // rbx
  const char *v15; // r9
  bool v16; // al
  int lpString2; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  LPWSTR lpBuffer; // [rsp+58h] [rbp+10h] BYREF
  LPCWSTR lpName; // [rsp+68h] [rbp+20h] BYREF

  if ( a2 )
  {
    if ( !a3 )
    {
      v5 = 57;
      goto LABEL_3;
    }
    lpName = 0;
    ProcessEnvName = EnterpriseFeatureControl::GetProcessEnvName(a1, (unsigned __int16 **)&lpName);
    v6 = ProcessEnvName;
    if ( ProcessEnvName < 0 )
    {
      v8 = (unsigned int)ProcessEnvName;
      v9 = 60;
LABEL_15:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
        (const char *)v8,
        lpString2);
      goto LABEL_25;
    }
    EnvironmentVariableW = GetEnvironmentVariableW(lpName, 0, 0);
    v12 = EnvironmentVariableW;
    if ( EnvironmentVariableW )
      goto LABEL_16;
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( (v6 & 0x80000000) == 0 )
    {
LABEL_16:
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &lpBuffer,
        v11,
        v12);
      v14 = lpBuffer;
      if ( lpBuffer )
      {
        if ( GetEnvironmentVariableW(lpName, lpBuffer, v12) )
        {
          if ( v14 )
            v16 = CompareStringW(0x7Fu, 0, v14, -1, L"1", -1) == 2;
          else
            v16 = 0;
          *a3 = v16;
          *a2 = 1;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpBuffer);
          v6 = 0;
          goto LABEL_25;
        }
        v6 = wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x48,
               (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
               v15);
      }
      else
      {
        v6 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x45,
          (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
          (const char *)0x8007000ELL,
          lpString2);
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpBuffer);
    }
    else
    {
      if ( v6 != -2147024693 )
      {
        v8 = v6;
        v9 = 65;
        goto LABEL_15;
      }
      v6 = -2147024693;
    }
LABEL_25:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpName);
    return v6;
  }
  v5 = 56;
LABEL_3:
  v6 = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
    (const char *)0x80004003LL,
    lpString2);
  return v6;
}

```

## disassembly

```asm
0x180017a80  mov     [rsp+arg_0], rbx
0x180017a85  push    rsi
0x180017a86  push    rdi
0x180017a87  push    r14
0x180017a89  sub     rsp, 30h
0x180017a8d  mov     rsi, r8
0x180017a90  mov     r14, rdx
0x180017a93  test    rdx, rdx
0x180017a96  jnz     short loc_180017ABA
0x180017a98  lea     edx, [r14+38h]; void *
0x180017a9c  mov     rcx, [rsp+48h]; this
0x180017aa1  lea     r8, aOnecoreInterna_4; "onecore\\internal\\enduser\\inc\\Enterp"...
0x180017aa8  mov     ebx, 80004003h
0x180017aad  mov     r9d, ebx; char *
0x180017ab0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017ab5  jmp     loc_180017C00
0x180017aba  test    rsi, rsi
0x180017abd  jnz     short loc_180017AC4
0x180017abf  lea     edx, [rsi+39h]
0x180017ac2  jmp     short loc_180017A9C
0x180017ac4  lea     rdx, [rsp+48h+lpName]; unsigned __int16 **
0x180017ac9  mov     [rsp+48h+lpName], 0
0x180017ad2  call    ?GetProcessEnvName@EnterpriseFeatureControl@@CAJKPEAPEAG@Z; EnterpriseFeatureControl::GetProcessEnvName(ulong,ushort * *)
0x180017ad7  mov     ebx, eax
0x180017ad9  test    eax, eax
0x180017adb  jns     short loc_180017AE7
0x180017add  mov     r9d, eax
0x180017ae0  mov     edx, 3Ch ; '<'
0x180017ae5  jmp     short loc_180017B2E
0x180017ae7  mov     rcx, [rsp+48h+lpName]; lpName
0x180017aec  xor     r8d, r8d; nSize
0x180017aef  xor     edx, edx; lpBuffer
0x180017af1  call    cs:__imp_GetEnvironmentVariableW
0x180017af7  mov     edi, eax
0x180017af9  test    eax, eax
0x180017afb  jnz     short loc_180017B44
0x180017afd  call    cs:__imp_GetLastError
0x180017b03  mov     ebx, eax
0x180017b05  test    eax, eax
0x180017b07  jle     short loc_180017B12
0x180017b09  movzx   ebx, ax
0x180017b0c  or      ebx, 80070000h
0x180017b12  test    ebx, ebx
0x180017b14  jns     short loc_180017B44
0x180017b16  mov     eax, 800700CBh
0x180017b1b  cmp     ebx, eax
0x180017b1d  jnz     short loc_180017B26
0x180017b1f  mov     ebx, eax
0x180017b21  jmp     loc_180017BF6
0x180017b26  mov     r9d, ebx; char *
0x180017b29  mov     edx, 41h ; 'A'; void *
0x180017b2e  mov     rcx, [rsp+48h]; this
0x180017b33  lea     r8, aOnecoreInterna_4; "onecore\\internal\\enduser\\inc\\Enterp"...
0x180017b3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017b3f  jmp     loc_180017BF6
0x180017b44  mov     r8, rdi
0x180017b47  lea     rcx, [rsp+48h+lpBuffer]
0x180017b4c  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180017b51  mov     rbx, [rsp+48h+lpBuffer]
0x180017b56  test    rbx, rbx
0x180017b59  jnz     short loc_180017B85
0x180017b5b  mov     rcx, [rsp+48h]; this
0x180017b60  lea     r8, aOnecoreInterna_4; "onecore\\internal\\enduser\\inc\\Enterp"...
0x180017b67  mov     ebx, 8007000Eh
0x180017b6c  mov     edx, 45h ; 'E'; void *
0x180017b71  mov     r9d, ebx; char *
0x180017b74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017b79  lea     rcx, [rsp+48h+lpBuffer]
0x180017b7e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180017b83  jmp     short loc_180017BF6
0x180017b85  mov     rcx, [rsp+48h+lpName]; lpName
0x180017b8a  mov     r8d, edi; nSize
0x180017b8d  mov     rdx, rbx; lpBuffer
0x180017b90  call    cs:__imp_GetEnvironmentVariableW
0x180017b96  test    eax, eax
0x180017b98  jnz     short loc_180017BB2
0x180017b9a  mov     rcx, [rsp+48h]; this
0x180017b9f  lea     r8, aOnecoreInterna_4; "onecore\\internal\\enduser\\inc\\Enterp"...
0x180017ba6  lea     edx, [rax+48h]; void *
0x180017ba9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180017bae  mov     ebx, eax
0x180017bb0  jmp     short loc_180017B79
0x180017bb2  test    rbx, rbx
0x180017bb5  jz      short loc_180017BE2
0x180017bb7  xor     edx, edx; dwCmpFlags
0x180017bb9  lea     rax, String2; "1"
0x180017bc0  or      r9d, 0FFFFFFFFh; cchCount1
0x180017bc4  mov     r8, rbx; lpString1
0x180017bc7  mov     [rsp+48h+cchCount2], r9d; cchCount2
0x180017bcc  mov     [rsp+48h+lpString2], rax; lpString2
0x180017bd1  lea     ecx, [rdx+7Fh]; Locale
0x180017bd4  call    cs:__imp_CompareStringW
0x180017bda  cmp     eax, 2
0x180017bdd  setz    al
0x180017be0  jmp     short loc_180017BE4
0x180017be2  xor     al, al
0x180017be4  lea     rcx, [rsp+48h+lpBuffer]
0x180017be9  mov     [rsi], al
0x180017beb  mov     byte ptr [r14], 1
0x180017bef  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180017bf4  xor     ebx, ebx
0x180017bf6  lea     rcx, [rsp+48h+lpName]
0x180017bfb  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180017c00  mov     eax, ebx
0x180017c02  mov     rbx, [rsp+48h+arg_0]
0x180017c07  add     rsp, 30h
0x180017c0b  pop     r14
0x180017c0d  pop     rdi
0x180017c0e  pop     rsi
0x180017c0f  retn
```
