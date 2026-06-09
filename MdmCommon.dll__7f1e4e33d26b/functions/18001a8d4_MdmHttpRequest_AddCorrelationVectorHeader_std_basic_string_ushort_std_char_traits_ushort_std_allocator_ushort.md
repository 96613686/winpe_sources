# MdmHttpRequest::AddCorrelationVectorHeader(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001a8d4`
- end: `0x18001aa7f`
- name: `?AddCorrelationVectorHeader@MdmHttpRequest@@CAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `427`
- prototype: `__int64 __fastcall(_QWORD *Src)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001b8b0`

## callees

- `0x180001520`
- `0x180001544`
- `0x180002a24`
- `0x180002de4`
- `0x1800062a4`
- `0x180006548`
- `0x180019e74`
- `0x18001a8d4`
- `0x18001d51c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001a92d`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001a92d`

## string_xrefs

- `0x18001a956`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`
- `0x18001a9a3`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`
- `0x18001a942`: `CHR(CoCreateGuid(&guid))`

## pseudocode

```c
__int64 __fastcall MdmHttpRequest::AddCorrelationVectorHeader(_QWORD *Src)
{
  HRESULT v2; // eax
  int v3; // edx
  unsigned __int64 v4; // rcx
  unsigned int v5; // ebx
  int v6; // eax
  int v7; // edx
  int v8; // ecx
  __int64 v9; // rdx
  void **v10; // r9
  __int64 v11; // rcx
  __int64 v12; // r14
  _QWORD *v13; // rsi
  __int64 v15; // [rsp+0h] [rbp-A8h] BYREF
  int v16; // [rsp+30h] [rbp-78h]
  __int64 v17; // [rsp+38h] [rbp-70h]
  int v18; // [rsp+40h] [rbp-68h]
  void *Srca[2]; // [rsp+48h] [rbp-60h] BYREF
  __int64 v20; // [rsp+58h] [rbp-50h]
  unsigned __int64 v21; // [rsp+60h] [rbp-48h]
  GUID v22; // [rsp+68h] [rbp-40h] BYREF

  v17 = 0;
  v18 = 0;
  *(_OWORD *)Srca = 0;
  v20 = 0;
  v21 = 7;
  LOWORD(Srca[0]) = 0;
  v22 = 0;
  v2 = CoCreateGuid(&v22);
  v5 = v2;
  if ( v2 < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v4,
        v3,
        v2,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
        239,
        "CHR(CoCreateGuid(&guid))");
    goto LABEL_18;
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v6 = MdmBase64Coder::Encode(v4, (const unsigned __int8 *)&v22, 12u, (__int64)Srca);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      v16 = -2147024882;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v8,
          (unsigned int)&v15,
          -2147024882,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
          250,
          "CHR(((HRESULT)0x8007000EL))");
      v5 = v16;
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18001AA4D);
      goto LABEL_18;
    }
  }
  v5 = v6;
  if ( v6 >= 0 )
  {
    std::wstring::append(Srca, L".0");
    std::wstring::append(Src, L"MS-CV: ");
    v9 = v20;
    v10 = Srca;
    if ( v21 > 7 )
      v10 = (void **)Srca[0];
    v11 = Src[2];
    if ( v20 > (unsigned __int64)(Src[3] - v11) )
    {
      std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
        Src,
        v20);
    }
    else
    {
      v12 = v11 + v20;
      Src[2] = v11 + v20;
      if ( Src[3] <= 7u )
        v13 = Src;
      else
        v13 = (_QWORD *)*Src;
      memmove_0((char *)v13 + 2 * v11, v10, 2 * v9);
      *((_WORD *)v13 + v12) = 0;
    }
    std::wstring::append(Src, L"\r\n");
  }
  else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v8,
      v7,
      v6,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
      240,
      "CHR(b64coder.Encode((BYTE *)&guid, 12, wstrCorrelationVector))");
  }
LABEL_18:
  std::wstring::~wstring((char **)Srca);
  operator delete(0);
  return v5;
}

```

## disassembly

```asm
0x18001a8d4  mov     r11, rsp
0x18001a8d7  push    rbx
0x18001a8d8  push    rsi
0x18001a8d9  push    rdi
0x18001a8da  push    r14
0x18001a8dc  sub     rsp, 88h
0x18001a8e3  mov     rax, cs:__security_cookie
0x18001a8ea  xor     rax, rsp
0x18001a8ed  mov     [rsp+0A8h+var_30], rax
0x18001a8f2  mov     rdi, rcx
0x18001a8f5  mov     qword ptr [r11-70h], 0
0x18001a8fd  mov     [rsp+0A8h+var_68], 0
0x18001a905  xorps   xmm0, xmm0
0x18001a908  movups  xmmword ptr [rsp+0A8h+Src], xmm0
0x18001a90d  mov     qword ptr [r11-50h], 0
0x18001a915  mov     qword ptr [r11-48h], 7
0x18001a91d  xor     eax, eax
0x18001a91f  mov     word ptr [rsp+0A8h+Src], ax
0x18001a924  movups  [rsp+0A8h+var_40], xmm0
0x18001a929  lea     rcx, [r11-40h]; pguid
0x18001a92d  call    cs:__imp_CoCreateGuid
0x18001a933  mov     ebx, eax
0x18001a935  test    eax, eax
0x18001a937  jns     short loc_18001A96B
0x18001a939  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001a940  jz      short loc_18001A966
0x18001a942  lea     rax, aChrCocreategui; "CHR(CoCreateGuid(&guid))"
0x18001a949  mov     [rsp+0A8h+var_80], rax
0x18001a94e  mov     dword ptr [rsp+0A8h+var_88], 2EFh
0x18001a956  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001a95d  mov     r8d, ebx
0x18001a960  call    McTemplateU0dsqs_EventWriteTransfer
0x18001a965  nop
0x18001a966  jmp     loc_18001AA51
0x18001a96b  lea     r9, [rsp+0A8h+Src]
0x18001a970  mov     r8d, 0Ch
0x18001a976  lea     rdx, [rsp+0A8h+var_40]
0x18001a97b  call    ?Encode@MdmBase64Coder@@QEAAJPEBEKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmBase64Coder::Encode(uchar const *,ulong,std::wstring &)
0x18001a980  mov     ebx, eax
0x18001a982  test    eax, eax
0x18001a984  jns     short loc_18001A9B8
0x18001a986  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001a98d  jz      short loc_18001A9B3
0x18001a98f  lea     rax, aChrB64coderEnc; "CHR(b64coder.Encode((BYTE *)&guid, 12, "...
0x18001a996  mov     [rsp+0A8h+var_80], rax
0x18001a99b  mov     dword ptr [rsp+0A8h+var_88], 2F0h
0x18001a9a3  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001a9aa  mov     r8d, ebx
0x18001a9ad  call    McTemplateU0dsqs_EventWriteTransfer
0x18001a9b2  nop
0x18001a9b3  jmp     loc_18001AA51
0x18001a9b8  lea     rdx, a0; ".0"
0x18001a9bf  lea     rcx, [rsp+0A8h+Src]; Src
0x18001a9c4  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001a9c9  lea     rdx, aMsCv; "MS-CV: "
0x18001a9d0  mov     rcx, rdi; Src
0x18001a9d3  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001a9d8  mov     rdx, [rsp+0A8h+var_50]
0x18001a9dd  lea     r9, [rsp+0A8h+Src]
0x18001a9e2  cmp     [rsp+0A8h+var_48], 7
0x18001a9e8  cmova   r9, [rsp+0A8h+Src]
0x18001a9ee  mov     rcx, [rdi+10h]
0x18001a9f2  mov     rax, [rdi+18h]
0x18001a9f6  sub     rax, rcx
0x18001a9f9  cmp     rdx, rax
0x18001a9fc  ja      short loc_18001AA2E
0x18001a9fe  lea     r14, [rcx+rdx]
0x18001aa02  mov     [rdi+10h], r14
0x18001aa06  cmp     qword ptr [rdi+18h], 7
0x18001aa0b  jbe     short loc_18001AA12
0x18001aa0d  mov     rsi, [rdi]
0x18001aa10  jmp     short loc_18001AA15
0x18001aa12  mov     rsi, rdi
0x18001aa15  lea     r8, [rdx+rdx]; Size
0x18001aa19  lea     rcx, [rsi+rcx*2]; void *
0x18001aa1d  mov     rdx, r9; Src
0x18001aa20  call    memmove_0
0x18001aa25  xor     eax, eax
0x18001aa27  mov     [rsi+r14*2], ax
0x18001aa2c  jmp     short loc_18001AA3B
0x18001aa2e  mov     [rsp+0A8h+var_88], rdx; __int64
0x18001aa33  mov     rcx, rdi; Src
0x18001aa36  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x18001aa3b  lea     rdx, asc_18002B100; "\r\n"
0x18001aa42  mov     rcx, rdi; Src
0x18001aa45  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001aa4a  nop
0x18001aa4b  jmp     short loc_18001AA51
0x18001aa4d  mov     ebx, [rsp+0A8h+var_78]
0x18001aa51  lea     rcx, [rsp+0A8h+Src]
0x18001aa56  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001aa5b  nop
0x18001aa5c  xor     ecx, ecx; void *
0x18001aa5e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001aa63  mov     eax, ebx
0x18001aa65  mov     rcx, [rsp+0A8h+var_30]
0x18001aa6a  xor     rcx, rsp; StackCookie
0x18001aa6d  call    __security_check_cookie
0x18001aa72  add     rsp, 88h
0x18001aa79  pop     r14
0x18001aa7b  pop     rdi
0x18001aa7c  pop     rsi
0x18001aa7d  pop     rbx
0x18001aa7e  retn
```
