# `wil::svchost_service<ADPService::AdpServiceTraits,winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::main(void)'::`2'::_lambda_1_::_lambda_invoker_cdecl_(ulong,ulong,void *,void *)

- ea: `0x18000ff90`
- end: `0x18001005e`
- name: `?_lambda_invoker_cdecl_@_lambda_1_@?1??main@?$svchost_service@UAdpServiceTraits@ADPService@@UAggregatedDataPlatform@3Internal@Windows@winrt@@@wil@@QEAAXXZ@SA@KKPEAX0@Z`
- size: `206`
- prototype: `__int64 __fastcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, HANDLE *lpContext)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update`

## callees

- `0x180005290`
- `0x18000771c`
- `0x18000ff90`
- `0x180010a40`
- `0x180011ec8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180010021`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180010021`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000ffc7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000ffc7`

## string_xrefs

- `0x18001003a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18001004c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall `wil::svchost_service<ADPService::AdpServiceTraits,winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::main'::`2'::_lambda_1_::_lambda_invoker_cdecl_(
        DWORD dwControl,
        DWORD dwEventType,
        LPVOID lpEventData,
        HANDLE *lpContext)
{
  DWORD v5; // ecx
  DWORD v6; // ecx
  unsigned int v7; // ebx
  DWORD v9; // eax
  const char *v10; // r9
  char v11; // bl
  const char *v12; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v5 = dwControl - 1;
  if ( v5 )
  {
    v6 = v5 - 3;
    if ( v6 )
    {
      if ( v6 == 28 )
      {
        v9 = WaitForSingleObjectEx(lpContext[2], 0, 0);
        if ( v9 == 258 )
        {
          v11 = 0;
        }
        else
        {
          if ( v9 )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0xB0F,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
              v10);
          v11 = 1;
        }
        return v11 != 0 ? 0x45B : 0;
      }
      else
      {
        return 120;
      }
    }
    else
    {
      return 0;
    }
  }
  else
  {
    wil::svchost_service<ADPService::AdpServiceTraits,winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::update_status(
      lpContext,
      3);
    v7 = 0;
    if ( (unsigned __int8)ADPService::AdpServiceTraits::try_stop_service<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>() )
    {
      if ( !SetEvent(lpContext[2]) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA01,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v12);
    }
    else
    {
      wil::svchost_service<ADPService::AdpServiceTraits,winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::update_status(
        lpContext,
        4);
      return 170;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18000ff90  mov     [rsp+arg_0], rbx
0x18000ff95  push    rdi
0x18000ff96  sub     rsp, 20h
0x18000ff9a  mov     rdi, r9
0x18000ff9d  sub     ecx, 1
0x18000ffa0  jz      short loc_18000FFEE
0x18000ffa2  sub     ecx, 3
0x18000ffa5  jz      short loc_18000FFEA
0x18000ffa7  cmp     ecx, 1Ch
0x18000ffaa  jz      short loc_18000FFBE
0x18000ffac  mov     ebx, 78h ; 'x'
0x18000ffb1  mov     eax, ebx
0x18000ffb3  mov     rbx, [rsp+28h+arg_0]
0x18000ffb8  add     rsp, 20h
0x18000ffbc  pop     rdi
0x18000ffbd  retn
0x18000ffbe  xor     r8d, r8d; bAlertable
0x18000ffc1  xor     edx, edx; dwMilliseconds
0x18000ffc3  mov     rcx, [r9+10h]; hHandle
0x18000ffc7  call    cs:__imp_WaitForSingleObjectEx
0x18000ffcd  cmp     eax, 102h
0x18000ffd2  jz      short loc_18000FFDC
0x18000ffd4  test    eax, eax
0x18000ffd6  jnz     short loc_180010035
0x18000ffd8  mov     bl, 1
0x18000ffda  jmp     short loc_18000FFDE
0x18000ffdc  xor     ebx, ebx
0x18000ffde  neg     bl
0x18000ffe0  sbb     ebx, ebx
0x18000ffe2  and     ebx, 45Bh
0x18000ffe8  jmp     short loc_18000FFB1
0x18000ffea  xor     ebx, ebx
0x18000ffec  jmp     short loc_18000FFB1
0x18000ffee  xor     r8d, r8d
0x18000fff1  lea     edx, [r8+3]
0x18000fff5  mov     rcx, rdi
0x18000fff8  call    ?update_status@?$svchost_service@UAdpServiceTraits@ADPService@@UAggregatedDataPlatform@3Internal@Windows@winrt@@@wil@@AEAAXKK@Z; wil::svchost_service<ADPService::AdpServiceTraits,winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::update_status(ulong,ulong)
0x18000fffd  call    ??$try_stop_service@UAggregatedDataPlatform@1Internal@Windows@winrt@@@AdpServiceTraits@ADPService@@SA_NXZ; ADPService::AdpServiceTraits::try_stop_service<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>(void)
0x180010002  xor     ebx, ebx
0x180010004  test    al, al
0x180010006  jnz     short loc_18001001D
0x180010008  xor     r8d, r8d
0x18001000b  lea     edx, [rbx+4]
0x18001000e  mov     rcx, rdi
0x180010011  call    ?update_status@?$svchost_service@UAdpServiceTraits@ADPService@@UAggregatedDataPlatform@3Internal@Windows@winrt@@@wil@@AEAAXKK@Z; wil::svchost_service<ADPService::AdpServiceTraits,winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::update_status(ulong,ulong)
0x180010016  mov     ebx, 0AAh
0x18001001b  jmp     short loc_18000FFB1
0x18001001d  mov     rcx, [rdi+10h]; hEvent
0x180010021  call    cs:__imp_SetEvent
0x180010027  mov     rcx, [rsp+28h]; this
0x18001002c  test    eax, eax
0x18001002e  jz      short loc_18001004C
0x180010030  jmp     loc_18000FFB1
0x180010035  mov     rcx, [rsp+28h]; this
0x18001003a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010041  mov     edx, 0B0Fh; void *
0x180010046  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001004c  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010053  mov     edx, 0A01h; void *
0x180010058  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
