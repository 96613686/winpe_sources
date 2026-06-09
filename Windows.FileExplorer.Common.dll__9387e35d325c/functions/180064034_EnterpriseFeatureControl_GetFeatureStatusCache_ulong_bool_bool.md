# EnterpriseFeatureControl::GetFeatureStatusCache(ulong,bool *,bool *)

- ea: `0x180064034`
- end: `0x1800641c4`
- name: `?GetFeatureStatusCache@EnterpriseFeatureControl@@CAJKPEA_N0@Z`
- size: `400`
- prototype: `__int64 __fastcall(unsigned int, bool *, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180066bf4`

## callees

- `0x1800077c8`
- `0x18003169c`
- `0x18005fcdc`
- `0x180060300`
- `0x180064034`
- `0x180064b18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800640b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800640b1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180064188`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180064188`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800640a5`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x180064144`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800640a5`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x180064144`

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
0x180064034  mov     [rsp+arg_0], rbx
0x180064039  push    rsi
0x18006403a  push    rdi
0x18006403b  push    r14
0x18006403d  sub     rsp, 30h
0x180064041  mov     rsi, r8
0x180064044  mov     r14, rdx
0x180064047  test    rdx, rdx
0x18006404a  jnz     short loc_18006406E
0x18006404c  lea     edx, [r14+38h]; void *
0x180064050  mov     rcx, [rsp+48h]; this
0x180064055  lea     r8, aOnecoreInterna_6; "onecore\\internal\\enduser\\inc\\Enterp"...
0x18006405c  mov     ebx, 80004003h
0x180064061  mov     r9d, ebx; char *
0x180064064  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064069  jmp     loc_1800641B4
0x18006406e  test    rsi, rsi
0x180064071  jnz     short loc_180064078
0x180064073  lea     edx, [rsi+39h]
0x180064076  jmp     short loc_180064050
0x180064078  lea     rdx, [rsp+48h+lpName]; unsigned __int16 **
0x18006407d  mov     [rsp+48h+lpName], 0
0x180064086  call    ?GetProcessEnvName@EnterpriseFeatureControl@@CAJKPEAPEAG@Z; EnterpriseFeatureControl::GetProcessEnvName(ulong,ushort * *)
0x18006408b  mov     ebx, eax
0x18006408d  test    eax, eax
0x18006408f  jns     short loc_18006409B
0x180064091  mov     r9d, eax
0x180064094  mov     edx, 3Ch ; '<'
0x180064099  jmp     short loc_1800640E2
0x18006409b  mov     rcx, [rsp+48h+lpName]; lpName
0x1800640a0  xor     r8d, r8d; nSize
0x1800640a3  xor     edx, edx; lpBuffer
0x1800640a5  call    cs:__imp_GetEnvironmentVariableW
0x1800640ab  mov     edi, eax
0x1800640ad  test    eax, eax
0x1800640af  jnz     short loc_1800640F8
0x1800640b1  call    cs:__imp_GetLastError
0x1800640b7  mov     ebx, eax
0x1800640b9  test    eax, eax
0x1800640bb  jle     short loc_1800640C6
0x1800640bd  movzx   ebx, ax
0x1800640c0  or      ebx, 80070000h
0x1800640c6  test    ebx, ebx
0x1800640c8  jns     short loc_1800640F8
0x1800640ca  mov     eax, 800700CBh
0x1800640cf  cmp     ebx, eax
0x1800640d1  jnz     short loc_1800640DA
0x1800640d3  mov     ebx, eax
0x1800640d5  jmp     loc_1800641AA
0x1800640da  mov     r9d, ebx; char *
0x1800640dd  mov     edx, 41h ; 'A'; void *
0x1800640e2  mov     rcx, [rsp+48h]; this
0x1800640e7  lea     r8, aOnecoreInterna_6; "onecore\\internal\\enduser\\inc\\Enterp"...
0x1800640ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800640f3  jmp     loc_1800641AA
0x1800640f8  mov     r8, rdi
0x1800640fb  lea     rcx, [rsp+48h+lpBuffer]
0x180064100  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180064105  mov     rbx, [rsp+48h+lpBuffer]
0x18006410a  test    rbx, rbx
0x18006410d  jnz     short loc_180064139
0x18006410f  mov     rcx, [rsp+48h]; this
0x180064114  lea     r8, aOnecoreInterna_6; "onecore\\internal\\enduser\\inc\\Enterp"...
0x18006411b  mov     ebx, 8007000Eh
0x180064120  mov     edx, 45h ; 'E'; void *
0x180064125  mov     r9d, ebx; char *
0x180064128  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006412d  lea     rcx, [rsp+48h+lpBuffer]
0x180064132  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180064137  jmp     short loc_1800641AA
0x180064139  mov     rcx, [rsp+48h+lpName]; lpName
0x18006413e  mov     r8d, edi; nSize
0x180064141  mov     rdx, rbx; lpBuffer
0x180064144  call    cs:__imp_GetEnvironmentVariableW
0x18006414a  test    eax, eax
0x18006414c  jnz     short loc_180064166
0x18006414e  mov     rcx, [rsp+48h]; this
0x180064153  lea     r8, aOnecoreInterna_6; "onecore\\internal\\enduser\\inc\\Enterp"...
0x18006415a  lea     edx, [rax+48h]; void *
0x18006415d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180064162  mov     ebx, eax
0x180064164  jmp     short loc_18006412D
0x180064166  test    rbx, rbx
0x180064169  jz      short loc_180064196
0x18006416b  xor     edx, edx; dwCmpFlags
0x18006416d  lea     rax, a1; "1"
0x180064174  or      r9d, 0FFFFFFFFh; cchCount1
0x180064178  mov     r8, rbx; lpString1
0x18006417b  mov     [rsp+48h+cchCount2], r9d; cchCount2
0x180064180  mov     [rsp+48h+lpString2], rax; lpString2
0x180064185  lea     ecx, [rdx+7Fh]; Locale
0x180064188  call    cs:__imp_CompareStringW
0x18006418e  cmp     eax, 2
0x180064191  setz    al
0x180064194  jmp     short loc_180064198
0x180064196  xor     al, al
0x180064198  lea     rcx, [rsp+48h+lpBuffer]
0x18006419d  mov     [rsi], al
0x18006419f  mov     byte ptr [r14], 1
0x1800641a3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800641a8  xor     ebx, ebx
0x1800641aa  lea     rcx, [rsp+48h+lpName]
0x1800641af  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800641b4  mov     eax, ebx
0x1800641b6  mov     rbx, [rsp+48h+arg_0]
0x1800641bb  add     rsp, 30h
0x1800641bf  pop     r14
0x1800641c1  pop     rdi
0x1800641c2  pop     rsi
0x1800641c3  retn
```
