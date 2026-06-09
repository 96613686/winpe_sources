# JsonHelper::GetJsonString(ushort * *)

- ea: `0x18015f800`
- end: `0x18015fa47`
- name: `?GetJsonString@JsonHelper@@UEAAJPEAPEAG@Z`
- size: `583`
- prototype: `__int64 __fastcall(JsonHelper *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18003b118`
- `0x180076090`
- `0x180077aa0`
- `0x18007f6a4`
- `0x18007f6b0`
- `0x18015ef00`
- `0x18015f800`
- `0x180160464`
- `0x18019c010`

## import_xrefs

- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18015f867`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18015f8fe`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18015f972`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18015f9db`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18015f867`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18015f8fe`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18015f972`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18015f9db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18015f91d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18015f91d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015f8b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015fa21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015f8b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015fa21`

## string_xrefs

- `0x18015f9e1`: `StringCchCopy failed!`
- `0x18015f872`: `spJsonObj.As(&spJsonValue)  failed!`
- `0x18015f909`: `spJsonValue->Stringify  failed!`

## pseudocode

```c
__int64 __fastcall JsonHelper::GetJsonString(JsonHelper *this, unsigned __int16 **a2)
{
  int v3; // ebx
  int v4; // eax
  int v5; // edx
  const char *v6; // rcx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, HSTRING *); // rbx
  const unsigned __int16 *StringRawBuffer; // rbx
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // rdi
  int v12; // eax
  int ActivityIdPrefix; // eax
  UINT32 length; // [rsp+50h] [rbp+20h] BYREF
  HSTRING string; // [rsp+60h] [rbp+30h] BYREF
  __int64 v17; // [rsp+68h] [rbp+38h] BYREF

  v17 = 0;
  string = 0;
  length = 0;
  v3 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(
         (char *)this + 56,
         &v17);
  if ( v3 >= 0 )
  {
    v7 = v17;
    v8 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v17 + 56LL);
    WindowsDeleteString(string);
    string = 0;
    v3 = v8(v7, &string);
    if ( v3 >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
      v10 = (unsigned __int16 *)operator new(saturated_mul(++length, 2u));
      v11 = v10;
      if ( v10 )
      {
        v3 = StringCchCopyW(v10, length, StringRawBuffer);
        if ( v3 >= 0 )
        {
          *a2 = v11;
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            ActivityIdPrefix = RdpX_GetActivityIdPrefix();
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              26,
              (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
              ActivityIdPrefix,
              (__int64)"StringCchCopy failed!",
              v3);
          }
          operator delete(v11);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v12 = RdpX_GetActivityIdPrefix();
          WPP_SF_Ds(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            25,
            (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
            v12,
            (__int64)"WCHAR[]");
        }
        v3 = -2147024882;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v4 = RdpX_GetActivityIdPrefix();
      v5 = 24;
      v6 = "spJsonValue->Stringify  failed!";
      goto LABEL_6;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v4 = RdpX_GetActivityIdPrefix();
    v5 = 23;
    v6 = "spJsonObj.As(&spJsonValue)  failed!";
LABEL_6:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
      v4,
      (__int64)v6,
      v3);
  }
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v17);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18015f800  mov     [rsp-18h+arg_8], rbx
0x18015f805  push    rbp
0x18015f806  push    rsi
0x18015f807  push    rdi
0x18015f808  mov     rbp, rsp
0x18015f80b  sub     rsp, 30h
0x18015f80f  mov     rsi, rdx
0x18015f812  mov     [rbp+arg_18], 0
0x18015f81a  lea     rdx, [rbp+arg_18]
0x18015f81e  mov     [rbp+string], 0
0x18015f826  add     rcx, 38h ; '8'
0x18015f82a  mov     [rbp+length], 0
0x18015f831  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x18015f836  mov     ebx, eax
0x18015f838  test    eax, eax
0x18015f83a  jns     short loc_18015F8A1
0x18015f83c  mov     rax, cs:WPP_GLOBAL_Control
0x18015f843  lea     rcx, WPP_GLOBAL_Control
0x18015f84a  cmp     rax, rcx
0x18015f84d  jz      loc_18015FA1D
0x18015f853  test    byte ptr [rax+1Ch], 8
0x18015f857  jz      loc_18015FA1D
0x18015f85d  cmp     byte ptr [rax+19h], 2
0x18015f861  jb      loc_18015FA1D
0x18015f867  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18015f86d  mov     edx, 17h
0x18015f872  lea     rcx, aSpjsonobjAsSpj; "spJsonObj.As(&spJsonValue)  failed!"
0x18015f879  mov     [rsp+30h+var_8], ebx
0x18015f87d  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x18015f884  mov     [rsp+30h+var_10], rcx
0x18015f889  mov     r9d, eax
0x18015f88c  mov     rcx, cs:WPP_GLOBAL_Control
0x18015f893  mov     rcx, [rcx+10h]
0x18015f897  call    WPP_SF_DsD
0x18015f89c  jmp     loc_18015FA1D
0x18015f8a1  mov     rdi, [rbp+arg_18]
0x18015f8a5  mov     rcx, [rbp+string]; string
0x18015f8a9  mov     rax, [rdi]
0x18015f8ac  mov     rbx, [rax+38h]
0x18015f8b0  call    cs:__imp_WindowsDeleteString
0x18015f8b6  lea     rdx, [rbp+string]
0x18015f8ba  mov     [rbp+string], 0
0x18015f8c2  mov     rcx, rdi
0x18015f8c5  mov     rax, rbx
0x18015f8c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015f8cd  mov     ebx, eax
0x18015f8cf  test    eax, eax
0x18015f8d1  jns     short loc_18015F915
0x18015f8d3  mov     rax, cs:WPP_GLOBAL_Control
0x18015f8da  lea     rcx, WPP_GLOBAL_Control
0x18015f8e1  cmp     rax, rcx
0x18015f8e4  jz      loc_18015FA1D
0x18015f8ea  test    byte ptr [rax+1Ch], 8
0x18015f8ee  jz      loc_18015FA1D
0x18015f8f4  cmp     byte ptr [rax+19h], 2
0x18015f8f8  jb      loc_18015FA1D
0x18015f8fe  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18015f904  mov     edx, 18h
0x18015f909  lea     rcx, aSpjsonvalueStr; "spJsonValue->Stringify  failed!"
0x18015f910  jmp     loc_18015F879
0x18015f915  mov     rcx, [rbp+string]; string
0x18015f919  lea     rdx, [rbp+length]; length
0x18015f91d  call    cs:__imp_WindowsGetStringRawBuffer
0x18015f923  mov     ecx, [rbp+length]
0x18015f926  mov     rbx, rax
0x18015f929  inc     ecx
0x18015f92b  mov     eax, 2
0x18015f930  mov     edx, ecx
0x18015f932  mov     [rbp+length], ecx
0x18015f935  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18015f93c  mul     rdx
0x18015f93f  cmovb   rax, rcx
0x18015f943  mov     rcx, rax; Size
0x18015f946  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18015f94b  mov     rdi, rax
0x18015f94e  test    rax, rax
0x18015f951  jnz     short loc_18015F9A8
0x18015f953  mov     rax, cs:WPP_GLOBAL_Control
0x18015f95a  lea     rcx, WPP_GLOBAL_Control
0x18015f961  cmp     rax, rcx
0x18015f964  jz      short loc_18015F9A1
0x18015f966  test    byte ptr [rax+1Ch], 8
0x18015f96a  jz      short loc_18015F9A1
0x18015f96c  cmp     byte ptr [rax+19h], 2
0x18015f970  jb      short loc_18015F9A1
0x18015f972  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18015f978  lea     rcx, aWchar_0; "WCHAR[]"
0x18015f97f  mov     r9d, eax
0x18015f982  mov     [rsp+30h+var_10], rcx
0x18015f987  lea     edx, [rdi+19h]
0x18015f98a  mov     rcx, cs:WPP_GLOBAL_Control
0x18015f991  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x18015f998  mov     rcx, [rcx+10h]
0x18015f99c  call    WPP_SF_Ds
0x18015f9a1  mov     ebx, 8007000Eh
0x18015f9a6  jmp     short loc_18015FA1D
0x18015f9a8  mov     edx, [rbp+length]; unsigned __int64
0x18015f9ab  mov     r8, rbx; unsigned __int16 *
0x18015f9ae  mov     rcx, rdi; unsigned __int16 *
0x18015f9b1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18015f9b6  mov     ebx, eax
0x18015f9b8  test    eax, eax
0x18015f9ba  jns     short loc_18015FA1A
0x18015f9bc  mov     rax, cs:WPP_GLOBAL_Control
0x18015f9c3  lea     rcx, WPP_GLOBAL_Control
0x18015f9ca  cmp     rax, rcx
0x18015f9cd  jz      short loc_18015FA10
0x18015f9cf  test    byte ptr [rax+1Ch], 8
0x18015f9d3  jz      short loc_18015FA10
0x18015f9d5  cmp     byte ptr [rax+19h], 2
0x18015f9d9  jb      short loc_18015FA10
0x18015f9db  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18015f9e1  lea     rcx, aStringcchcopyF; "StringCchCopy failed!"
0x18015f9e8  mov     [rsp+30h+var_8], ebx
0x18015f9ec  mov     [rsp+30h+var_10], rcx
0x18015f9f1  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x18015f9f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18015f9ff  mov     edx, 1Ah
0x18015fa04  mov     r9d, eax
0x18015fa07  mov     rcx, [rcx+10h]
0x18015fa0b  call    WPP_SF_DsD
0x18015fa10  mov     rcx, rdi; Block
0x18015fa13  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18015fa18  jmp     short loc_18015FA1D
0x18015fa1a  mov     [rsi], rdi
0x18015fa1d  mov     rcx, [rbp+string]; string
0x18015fa21  call    cs:__imp_WindowsDeleteString
0x18015fa27  lea     rcx, [rbp+arg_18]
0x18015fa2b  mov     [rbp+string], 0
0x18015fa33  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x18015fa38  mov     eax, ebx
0x18015fa3a  mov     rbx, [rsp+30h+arg_8]
0x18015fa3f  add     rsp, 30h
0x18015fa43  pop     rdi
0x18015fa44  pop     rsi
0x18015fa45  pop     rbp
0x18015fa46  retn
```
