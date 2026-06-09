# JsonHelper::GetJsonString(ushort * *)

- ea: `0x180090610`
- end: `0x180090853`
- name: `?GetJsonString@JsonHelper@@UEAAJPEAPEAG@Z`
- size: `579`
- prototype: `__int64 __fastcall(JsonHelper *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180038984`
- `0x1800711c8`
- `0x180071a60`
- `0x1800787d4`
- `0x180078820`
- `0x18008fcdc`
- `0x180090610`
- `0x180091270`
- `0x1800923f8`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800906bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009082d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800906bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009082d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009072b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009072b`

## string_xrefs

- `0x1800907ed`: `StringCchCopy failed!`
- `0x180090681`: `spJsonObj.As(&spJsonValue)  failed!`
- `0x180090717`: `spJsonValue->Stringify  failed!`

## pseudocode

```c
__int64 __fastcall JsonHelper::GetJsonString(JsonHelper *this, unsigned __int16 **a2)
{
  __int64 v3; // rdx
  int v4; // ebx
  __int64 v5; // r8
  int v6; // eax
  int v7; // edx
  const char *v8; // rcx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, HSTRING *); // rbx
  __int64 v11; // rdx
  __int64 v12; // r8
  const unsigned __int16 *StringRawBuffer; // rbx
  unsigned __int16 *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r8
  unsigned __int16 *v17; // rdi
  int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // r8
  int ActivityIdPrefix; // eax
  UINT32 length; // [rsp+50h] [rbp+20h] BYREF
  HSTRING string; // [rsp+60h] [rbp+30h] BYREF
  __int64 v25; // [rsp+68h] [rbp+38h] BYREF

  v25 = 0;
  string = 0;
  length = 0;
  v4 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(
         (char *)this + 56,
         &v25);
  if ( v4 >= 0 )
  {
    v9 = v25;
    v10 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v25 + 56LL);
    WindowsDeleteString(string);
    string = 0;
    v4 = v10(v9, &string);
    if ( v4 >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
      v14 = (unsigned __int16 *)operator new(saturated_mul(++length, 2u));
      v17 = v14;
      if ( v14 )
      {
        v4 = StringCchCopyW(v14, length, StringRawBuffer);
        if ( v4 >= 0 )
        {
          *a2 = v17;
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v19, v20);
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              26,
              (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
              ActivityIdPrefix,
              (__int64)"StringCchCopy failed!",
              v4);
          }
          operator delete(v17);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v18 = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v15, v16);
          WPP_SF_Ds(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            25,
            (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
            v18,
            (__int64)"WCHAR[]");
        }
        v4 = -2147024882;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v11, v12);
      v7 = 24;
      v8 = "spJsonValue->Stringify  failed!";
      goto LABEL_6;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v6 = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v3, v5);
    v7 = 23;
    v8 = "spJsonObj.As(&spJsonValue)  failed!";
LABEL_6:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
      v6,
      (__int64)v8,
      v4);
  }
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v25);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180090610  mov     [rsp-18h+arg_8], rbx
0x180090615  push    rbp
0x180090616  push    rsi
0x180090617  push    rdi
0x180090618  mov     rbp, rsp
0x18009061b  sub     rsp, 30h
0x18009061f  mov     rsi, rdx
0x180090622  mov     [rbp+arg_18], 0
0x18009062a  lea     rdx, [rbp+arg_18]
0x18009062e  mov     [rbp+string], 0
0x180090636  add     rcx, 38h ; '8'
0x18009063a  mov     [rbp+length], 0
0x180090641  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x180090646  mov     ebx, eax
0x180090648  test    eax, eax
0x18009064a  jns     short loc_1800906B0
0x18009064c  mov     rax, cs:WPP_GLOBAL_Control
0x180090653  lea     rcx, WPP_GLOBAL_Control
0x18009065a  cmp     rax, rcx
0x18009065d  jz      loc_180090829
0x180090663  test    byte ptr [rax+1Ch], 8
0x180090667  jz      loc_180090829
0x18009066d  cmp     byte ptr [rax+19h], 2
0x180090671  jb      loc_180090829
0x180090677  call    RdpX_GetActivityIdPrefix
0x18009067c  mov     edx, 17h
0x180090681  lea     rcx, aSpjsonobjAsSpj; "spJsonObj.As(&spJsonValue)  failed!"
0x180090688  mov     [rsp+30h+var_8], ebx
0x18009068c  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x180090693  mov     [rsp+30h+var_10], rcx
0x180090698  mov     r9d, eax
0x18009069b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800906a2  mov     rcx, [rcx+10h]
0x1800906a6  call    WPP_SF_DsD
0x1800906ab  jmp     loc_180090829
0x1800906b0  mov     rdi, [rbp+arg_18]
0x1800906b4  mov     rcx, [rbp+string]; string
0x1800906b8  mov     rax, [rdi]
0x1800906bb  mov     rbx, [rax+38h]
0x1800906bf  call    cs:__imp_WindowsDeleteString
0x1800906c5  lea     rdx, [rbp+string]
0x1800906c9  mov     [rbp+string], 0
0x1800906d1  mov     rcx, rdi
0x1800906d4  mov     rax, rbx
0x1800906d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800906dc  mov     ebx, eax
0x1800906de  test    eax, eax
0x1800906e0  jns     short loc_180090723
0x1800906e2  mov     rax, cs:WPP_GLOBAL_Control
0x1800906e9  lea     rcx, WPP_GLOBAL_Control
0x1800906f0  cmp     rax, rcx
0x1800906f3  jz      loc_180090829
0x1800906f9  test    byte ptr [rax+1Ch], 8
0x1800906fd  jz      loc_180090829
0x180090703  cmp     byte ptr [rax+19h], 2
0x180090707  jb      loc_180090829
0x18009070d  call    RdpX_GetActivityIdPrefix
0x180090712  mov     edx, 18h
0x180090717  lea     rcx, aSpjsonvalueStr; "spJsonValue->Stringify  failed!"
0x18009071e  jmp     loc_180090688
0x180090723  mov     rcx, [rbp+string]; string
0x180090727  lea     rdx, [rbp+length]; length
0x18009072b  call    cs:__imp_WindowsGetStringRawBuffer
0x180090731  mov     ecx, [rbp+length]
0x180090734  mov     rbx, rax
0x180090737  inc     ecx
0x180090739  mov     eax, 2
0x18009073e  mov     edx, ecx
0x180090740  mov     [rbp+length], ecx
0x180090743  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18009074a  mul     rdx
0x18009074d  cmovb   rax, rcx
0x180090751  mov     rcx, rax; Size
0x180090754  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180090759  mov     rdi, rax
0x18009075c  test    rax, rax
0x18009075f  jnz     short loc_1800907B5
0x180090761  mov     rax, cs:WPP_GLOBAL_Control
0x180090768  lea     rcx, WPP_GLOBAL_Control
0x18009076f  cmp     rax, rcx
0x180090772  jz      short loc_1800907AE
0x180090774  test    byte ptr [rax+1Ch], 8
0x180090778  jz      short loc_1800907AE
0x18009077a  cmp     byte ptr [rax+19h], 2
0x18009077e  jb      short loc_1800907AE
0x180090780  call    RdpX_GetActivityIdPrefix
0x180090785  lea     rcx, aWchar; "WCHAR[]"
0x18009078c  mov     r9d, eax
0x18009078f  mov     [rsp+30h+var_10], rcx
0x180090794  lea     edx, [rdi+19h]
0x180090797  mov     rcx, cs:WPP_GLOBAL_Control
0x18009079e  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x1800907a5  mov     rcx, [rcx+10h]
0x1800907a9  call    WPP_SF_Ds
0x1800907ae  mov     ebx, 8007000Eh
0x1800907b3  jmp     short loc_180090829
0x1800907b5  mov     edx, [rbp+length]; unsigned __int64
0x1800907b8  mov     r8, rbx; unsigned __int16 *
0x1800907bb  mov     rcx, rdi; unsigned __int16 *
0x1800907be  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800907c3  mov     ebx, eax
0x1800907c5  test    eax, eax
0x1800907c7  jns     short loc_180090826
0x1800907c9  mov     rax, cs:WPP_GLOBAL_Control
0x1800907d0  lea     rcx, WPP_GLOBAL_Control
0x1800907d7  cmp     rax, rcx
0x1800907da  jz      short loc_18009081C
0x1800907dc  test    byte ptr [rax+1Ch], 8
0x1800907e0  jz      short loc_18009081C
0x1800907e2  cmp     byte ptr [rax+19h], 2
0x1800907e6  jb      short loc_18009081C
0x1800907e8  call    RdpX_GetActivityIdPrefix
0x1800907ed  lea     rcx, aStringcchcopyF; "StringCchCopy failed!"
0x1800907f4  mov     [rsp+30h+var_8], ebx
0x1800907f8  mov     [rsp+30h+var_10], rcx
0x1800907fd  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x180090804  mov     rcx, cs:WPP_GLOBAL_Control
0x18009080b  mov     edx, 1Ah
0x180090810  mov     r9d, eax
0x180090813  mov     rcx, [rcx+10h]
0x180090817  call    WPP_SF_DsD
0x18009081c  mov     rcx, rdi; Block
0x18009081f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180090824  jmp     short loc_180090829
0x180090826  mov     [rsi], rdi
0x180090829  mov     rcx, [rbp+string]; string
0x18009082d  call    cs:__imp_WindowsDeleteString
0x180090833  lea     rcx, [rbp+arg_18]
0x180090837  mov     [rbp+string], 0
0x18009083f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x180090844  mov     eax, ebx
0x180090846  mov     rbx, [rsp+30h+arg_8]
0x18009084b  add     rsp, 30h
0x18009084f  pop     rdi
0x180090850  pop     rsi
0x180090851  pop     rbp
0x180090852  retn
```
