# MdmHttpRequest::AddCorrelationVectorHeader(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001ae24`
- end: `0x18001afd6`
- name: `?AddCorrelationVectorHeader@MdmHttpRequest@@CAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `434`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001be50`

## callees

- `0x180001520`
- `0x180001544`
- `0x180002a24`
- `0x180002de8`
- `0x18000630c`
- `0x1800065c0`
- `0x18001a388`
- `0x18001ae24`
- `0x18001dbfc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001ae7d`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001ae7d`

## string_xrefs

- `0x18001aeac`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`
- `0x18001aef9`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`
- `0x18001ae98`: `CHR(CoCreateGuid(&guid))`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MdmHttpRequest::AddCorrelationVectorHeader(_QWORD *Src)
{
  HRESULT v2; // eax
  int v3; // edx
  MdmBase64Coder *v4; // rcx
  unsigned int v5; // ebx
  int v6; // eax
  int v7; // edx
  int v8; // ecx
  __int64 v9; // rdx
  void **v10; // r9
  __int64 v11; // rcx
  __int64 v12; // r14
  _QWORD *v13; // rsi
  unsigned __int64 v14; // rdx
  __int64 v16; // [rsp+0h] [rbp-A8h] BYREF
  int v17; // [rsp+30h] [rbp-78h]
  __int64 v18; // [rsp+38h] [rbp-70h]
  int v19; // [rsp+40h] [rbp-68h]
  void *Srca[2]; // [rsp+48h] [rbp-60h] BYREF
  __int64 v21; // [rsp+58h] [rbp-50h]
  unsigned __int64 v22; // [rsp+60h] [rbp-48h]
  GUID v23; // [rsp+68h] [rbp-40h] BYREF

  v18 = 0;
  v19 = 0;
  *(_OWORD *)Srca = 0;
  v21 = 0;
  v22 = 7;
  LOWORD(Srca[0]) = 0;
  v23 = 0;
  v2 = CoCreateGuid(&v23);
  v5 = v2;
  if ( v2 >= 0 )
  {
    try
    {
      v6 = MdmBase64Coder::Encode(v4, (const unsigned __int8 *)&v23, 0xCu, (char **)Srca);
    }
    catch ( std::bad_alloc )
    {
      v17 = -2147024882;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v8,
          (unsigned int)&v16,
          -2147024882,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
          250,
          "CHR(((HRESULT)0x8007000EL))");
      v5 = v17;
      goto LABEL_18;
    }
    v5 = v6;
    if ( v6 >= 0 )
    {
      std::wstring::append(Srca, L".0");
      std::wstring::append(Src, L"MS-CV: ");
      v9 = v21;
      v10 = Srca;
      if ( v22 > 7 )
        v10 = (void **)Srca[0];
      v11 = Src[2];
      if ( v21 > (unsigned __int64)(Src[3] - v11) )
      {
        std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
          Src,
          v21);
      }
      else
      {
        v12 = v11 + v21;
        Src[2] = v11 + v21;
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
  }
  else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      (_DWORD)v4,
      v3,
      v2,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
      239,
      "CHR(CoCreateGuid(&guid))");
  }
LABEL_18:
  std::wstring::~wstring(Srca);
  operator delete(0, v14);
  return v5;
}

```

## disassembly

```asm
0x18001ae24  mov     r11, rsp
0x18001ae27  push    rbx
0x18001ae28  push    rsi
0x18001ae29  push    rdi
0x18001ae2a  push    r14
0x18001ae2c  sub     rsp, 88h
0x18001ae33  mov     rax, cs:__security_cookie
0x18001ae3a  xor     rax, rsp
0x18001ae3d  mov     [rsp+0A8h+var_30], rax
0x18001ae42  mov     rdi, rcx
0x18001ae45  mov     qword ptr [r11-70h], 0
0x18001ae4d  mov     [rsp+0A8h+var_68], 0
0x18001ae55  xorps   xmm0, xmm0
0x18001ae58  movups  xmmword ptr [rsp+0A8h+Src], xmm0
0x18001ae5d  mov     qword ptr [r11-50h], 0
0x18001ae65  mov     qword ptr [r11-48h], 7
0x18001ae6d  xor     eax, eax
0x18001ae6f  mov     word ptr [rsp+0A8h+Src], ax
0x18001ae74  movups  [rsp+0A8h+var_40], xmm0
0x18001ae79  lea     rcx, [r11-40h]; pguid
0x18001ae7d  call    cs:__imp_CoCreateGuid
0x18001ae84  nop     dword ptr [rax+rax+00h]
0x18001ae89  mov     ebx, eax
0x18001ae8b  test    eax, eax
0x18001ae8d  jns     short loc_18001AEC1
0x18001ae8f  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001ae96  jz      short loc_18001AEBC
0x18001ae98  lea     rax, aChrCocreategui; "CHR(CoCreateGuid(&guid))"
0x18001ae9f  mov     [rsp+0A8h+var_80], rax
0x18001aea4  mov     dword ptr [rsp+0A8h+var_88], 2EFh
0x18001aeac  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001aeb3  mov     r8d, ebx
0x18001aeb6  call    McTemplateU0dsqs_EventWriteTransfer
0x18001aebb  nop
0x18001aebc  jmp     loc_18001AFA7
0x18001aec1  lea     r9, [rsp+0A8h+Src]
0x18001aec6  mov     r8d, 0Ch
0x18001aecc  lea     rdx, [rsp+0A8h+var_40]
0x18001aed1  call    ?Encode@MdmBase64Coder@@QEAAJPEBEKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmBase64Coder::Encode(uchar const *,ulong,std::wstring &)
0x18001aed6  mov     ebx, eax
0x18001aed8  test    eax, eax
0x18001aeda  jns     short loc_18001AF0E
0x18001aedc  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001aee3  jz      short loc_18001AF09
0x18001aee5  lea     rax, aChrB64coderEnc; "CHR(b64coder.Encode((BYTE *)&guid, 12, "...
0x18001aeec  mov     [rsp+0A8h+var_80], rax
0x18001aef1  mov     dword ptr [rsp+0A8h+var_88], 2F0h
0x18001aef9  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001af00  mov     r8d, ebx
0x18001af03  call    McTemplateU0dsqs_EventWriteTransfer
0x18001af08  nop
0x18001af09  jmp     loc_18001AFA7
0x18001af0e  lea     rdx, a0; ".0"
0x18001af15  lea     rcx, [rsp+0A8h+Src]; Src
0x18001af1a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001af1f  lea     rdx, aMsCv; "MS-CV: "
0x18001af26  mov     rcx, rdi; Src
0x18001af29  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001af2e  mov     rdx, [rsp+0A8h+var_50]
0x18001af33  lea     r9, [rsp+0A8h+Src]
0x18001af38  cmp     [rsp+0A8h+var_48], 7
0x18001af3e  cmova   r9, [rsp+0A8h+Src]
0x18001af44  mov     rcx, [rdi+10h]
0x18001af48  mov     rax, [rdi+18h]
0x18001af4c  sub     rax, rcx
0x18001af4f  cmp     rdx, rax
0x18001af52  ja      short loc_18001AF84
0x18001af54  lea     r14, [rcx+rdx]
0x18001af58  mov     [rdi+10h], r14
0x18001af5c  cmp     qword ptr [rdi+18h], 7
0x18001af61  jbe     short loc_18001AF68
0x18001af63  mov     rsi, [rdi]
0x18001af66  jmp     short loc_18001AF6B
0x18001af68  mov     rsi, rdi
0x18001af6b  lea     r8, [rdx+rdx]; Size
0x18001af6f  lea     rcx, [rsi+rcx*2]; void *
0x18001af73  mov     rdx, r9; Src
0x18001af76  call    memmove_0
0x18001af7b  xor     eax, eax
0x18001af7d  mov     [rsi+r14*2], ax
0x18001af82  jmp     short loc_18001AF91
0x18001af84  mov     [rsp+0A8h+var_88], rdx; __int64
0x18001af89  mov     rcx, rdi; Src
0x18001af8c  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x18001af91  lea     rdx, asc_18002B100; "\r\n"
0x18001af98  mov     rcx, rdi; Src
0x18001af9b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001afa0  nop
0x18001afa1  jmp     short loc_18001AFA7
0x18001afa3  mov     ebx, [rsp+0A8h+var_78]
0x18001afa7  lea     rcx, [rsp+0A8h+Src]
0x18001afac  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001afb1  nop
0x18001afb2  xor     ecx, ecx; void *
0x18001afb4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001afb9  mov     eax, ebx
0x18001afbb  mov     rcx, [rsp+0A8h+var_30]
0x18001afc0  xor     rcx, rsp; StackCookie
0x18001afc3  call    __security_check_cookie
0x18001afc8  add     rsp, 88h
0x18001afcf  pop     r14
0x18001afd1  pop     rdi
0x18001afd2  pop     rsi
0x18001afd3  pop     rbx
0x18001afd4  retn
```
