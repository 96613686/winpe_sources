# JsonHelper::GetJsonStringAsByteArray(uchar * *,ulong *)

- ea: `0x18015fa50`
- end: `0x18015fbf4`
- name: `?GetJsonStringAsByteArray@JsonHelper@@UEAAJPEAPEAEPEAK@Z`
- size: `420`
- prototype: `int(JsonHelper *__hidden this, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180076090`
- `0x18015ef00`
- `0x18015fa50`
- `0x180160464`
- `0x1801613a0`
- `0x18019c010`

## import_xrefs

- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18015fac0`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18015fb34`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18015fb8f`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18015fac0`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18015fb34`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18015fb8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18015fb50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18015fb50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015fae6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015fbc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015fae6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015fbc8`

## string_xrefs

- `0x18015facb`: `spJsonObj.As(&spJsonValue)  failed!`
- `0x18015fb3f`: `spJsonValue->Stringify  failed!`

## pseudocode

```c
__int64 __fastcall JsonHelper::GetJsonStringAsByteArray(JsonHelper *this, unsigned __int8 **a2, unsigned int *a3)
{
  __int64 v5; // rdx
  int v6; // ebx
  int ActivityIdPrefix; // eax
  int v8; // edx
  const char *v9; // rcx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, HSTRING *); // rbx
  __int64 v12; // rdx
  const unsigned __int16 *StringRawBuffer; // rax
  JsonHelper *v14; // rcx
  __int64 v15; // rdx
  _QWORD v17[2]; // [rsp+30h] [rbp-10h] BYREF
  UINT32 length; // [rsp+60h] [rbp+20h] BYREF
  HSTRING string; // [rsp+78h] [rbp+38h] BYREF

  v17[0] = 0;
  string = 0;
  length = 0;
  v6 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(
         (char *)this + 56,
         v17);
  if ( v6 >= 0 )
  {
    v10 = v17[0];
    v11 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v17[0] + 56LL);
    WindowsDeleteString(string);
    string = 0;
    v6 = v11(v10, &string);
    if ( v6 >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
      v6 = JsonHelper::WideCharToUTF8AsByteArray(v14, StringRawBuffer, length, a2, a3);
      if ( v6 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v15);
        v8 = 29;
        v9 = "WideCharToUTF8AsByteArray  failed!";
        goto LABEL_16;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v12);
      v8 = 28;
      v9 = "spJsonValue->Stringify  failed!";
      goto LABEL_16;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v5);
    v8 = 27;
    v9 = "spJsonObj.As(&spJsonValue)  failed!";
LABEL_16:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v8,
      (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
      ActivityIdPrefix,
      (__int64)v9,
      v6);
  }
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(v17);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18015fa50  mov     [rsp-18h+arg_8], rbx
0x18015fa55  mov     [rsp-18h+arg_10], rsi
0x18015fa5a  push    rbp
0x18015fa5b  push    rdi
0x18015fa5c  push    r14
0x18015fa5e  mov     rbp, rsp
0x18015fa61  sub     rsp, 40h
0x18015fa65  mov     r14, rdx
0x18015fa68  mov     [rbp+var_10], 0
0x18015fa70  lea     rdx, [rbp+var_10]
0x18015fa74  mov     [rbp+string], 0
0x18015fa7c  add     rcx, 38h ; '8'
0x18015fa80  mov     [rbp+length], 0
0x18015fa87  mov     rsi, r8
0x18015fa8a  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x18015fa8f  mov     ebx, eax
0x18015fa91  test    eax, eax
0x18015fa93  jns     short loc_18015FAD7
0x18015fa95  mov     rax, cs:WPP_GLOBAL_Control
0x18015fa9c  lea     rcx, WPP_GLOBAL_Control
0x18015faa3  cmp     rax, rcx
0x18015faa6  jz      loc_18015FBC4
0x18015faac  test    byte ptr [rax+1Ch], 8
0x18015fab0  jz      loc_18015FBC4
0x18015fab6  cmp     byte ptr [rax+19h], 2
0x18015faba  jb      loc_18015FBC4
0x18015fac0  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18015fac6  mov     edx, 1Bh
0x18015facb  lea     rcx, aSpjsonobjAsSpj; "spJsonObj.As(&spJsonValue)  failed!"
0x18015fad2  jmp     loc_18015FBA1
0x18015fad7  mov     rdi, [rbp+var_10]
0x18015fadb  mov     rcx, [rbp+string]; string
0x18015fadf  mov     rax, [rdi]
0x18015fae2  mov     rbx, [rax+38h]
0x18015fae6  call    cs:__imp_WindowsDeleteString
0x18015faec  lea     rdx, [rbp+string]
0x18015faf0  mov     [rbp+string], 0
0x18015faf8  mov     rcx, rdi
0x18015fafb  mov     rax, rbx
0x18015fafe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015fb03  mov     ebx, eax
0x18015fb05  test    eax, eax
0x18015fb07  jns     short loc_18015FB48
0x18015fb09  mov     rax, cs:WPP_GLOBAL_Control
0x18015fb10  lea     rcx, WPP_GLOBAL_Control
0x18015fb17  cmp     rax, rcx
0x18015fb1a  jz      loc_18015FBC4
0x18015fb20  test    byte ptr [rax+1Ch], 8
0x18015fb24  jz      loc_18015FBC4
0x18015fb2a  cmp     byte ptr [rax+19h], 2
0x18015fb2e  jb      loc_18015FBC4
0x18015fb34  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18015fb3a  mov     edx, 1Ch
0x18015fb3f  lea     rcx, aSpjsonvalueStr; "spJsonValue->Stringify  failed!"
0x18015fb46  jmp     short loc_18015FBA1
0x18015fb48  mov     rcx, [rbp+string]; string
0x18015fb4c  lea     rdx, [rbp+length]; length
0x18015fb50  call    cs:__imp_WindowsGetStringRawBuffer
0x18015fb56  mov     r8d, [rbp+length]; int
0x18015fb5a  mov     r9, r14; unsigned __int8 **
0x18015fb5d  mov     rdx, rax; unsigned __int16 *
0x18015fb60  mov     [rsp+40h+var_20], rsi; unsigned int *
0x18015fb65  call    ?WideCharToUTF8AsByteArray@JsonHelper@@AEAAJPEBGHPEAPEAEPEAK@Z; JsonHelper::WideCharToUTF8AsByteArray(ushort const *,int,uchar * *,ulong *)
0x18015fb6a  mov     ebx, eax
0x18015fb6c  test    eax, eax
0x18015fb6e  jns     short loc_18015FBC4
0x18015fb70  mov     rax, cs:WPP_GLOBAL_Control
0x18015fb77  lea     rcx, WPP_GLOBAL_Control
0x18015fb7e  cmp     rax, rcx
0x18015fb81  jz      short loc_18015FBC4
0x18015fb83  test    byte ptr [rax+1Ch], 8
0x18015fb87  jz      short loc_18015FBC4
0x18015fb89  cmp     byte ptr [rax+19h], 2
0x18015fb8d  jb      short loc_18015FBC4
0x18015fb8f  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18015fb95  mov     edx, 1Dh
0x18015fb9a  lea     rcx, aWidechartoutf8; "WideCharToUTF8AsByteArray  failed!"
0x18015fba1  mov     [rsp+40h+var_18], ebx
0x18015fba5  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x18015fbac  mov     [rsp+40h+var_20], rcx
0x18015fbb1  mov     r9d, eax
0x18015fbb4  mov     rcx, cs:WPP_GLOBAL_Control
0x18015fbbb  mov     rcx, [rcx+10h]
0x18015fbbf  call    WPP_SF_DsD
0x18015fbc4  mov     rcx, [rbp+string]; string
0x18015fbc8  call    cs:__imp_WindowsDeleteString
0x18015fbce  lea     rcx, [rbp+var_10]
0x18015fbd2  mov     [rbp+string], 0
0x18015fbda  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x18015fbdf  mov     rsi, [rsp+40h+arg_10]
0x18015fbe4  mov     eax, ebx
0x18015fbe6  mov     rbx, [rsp+40h+arg_8]
0x18015fbeb  add     rsp, 40h
0x18015fbef  pop     r14
0x18015fbf1  pop     rdi
0x18015fbf2  pop     rbp
0x18015fbf3  retn
```
