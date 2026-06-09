# DllRegisterServer

- ea: `0x1800229c0`
- end: `0x180022b53`
- name: `DllRegisterServer`
- size: `403`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800018f0`
- `0x18001fcb0`
- `0x1800229c0`
- `0x180024010`

## import_xrefs

- `MFPlat!MFTRegister` at `0x180022a66`
- `MFPlat!MFTRegister` at `0x180022a66`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HRESULT __stdcall DllRegisterServer()
{
  HRESULT result; // eax
  __int64 v1; // rbx
  const struct ATL::_ATL_CATMAP_ENTRY *v2; // rax
  __int64 *v3; // rbx
  __int64 *v4; // rcx
  __int64 v5; // rdi
  const struct ATL::_ATL_CATMAP_ENTRY *v6; // rax
  GUID v7; // [rsp+50h] [rbp-78h] BYREF
  CLSID v8; // [rsp+60h] [rbp-68h] BYREF
  MFT_REGISTER_TYPE_INFO pOutputTypes; // [rsp+70h] [rbp-58h] BYREF
  MFT_REGISTER_TYPE_INFO pInputTypes; // [rsp+90h] [rbp-38h] BYREF

  pOutputTypes.guidMajorType = MFMediaType_Audio;
  pOutputTypes.guidSubtype = MFAudioFormat_Float;
  pInputTypes.guidMajorType = MFMediaType_Audio;
  pInputTypes.guidSubtype = (GUID)MFAudioFormat_Opus;
  v7 = MFT_CATEGORY_AUDIO_DECODER;
  v8 = CLSID_CMSOpusDecMFT;
  result = MFTRegister(&v8, &v7, (LPWSTR)L"Microsoft Opus Audio Decoder MFT", 0, 1u, &pInputTypes, 1u, &pOutputTypes, 0);
  if ( result >= 0 )
  {
    v1 = qword_1800353C8;
    if ( qword_1800353C8 )
    {
      while ( *(_QWORD *)v1 )
      {
        result = (*(__int64 (__fastcall **)(__int64))(v1 + 8))(1);
        if ( result < 0 )
          return result;
        v2 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v1 + 56))();
        result = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v1, v2, 1);
        if ( result < 0 )
          return result;
        v1 += 72;
      }
    }
    result = 0;
    v3 = (__int64 *)off_1800350E0;
    v4 = (__int64 *)off_1800350E8;
    while ( v3 < v4 )
    {
      v5 = *v3;
      if ( *v3 )
      {
        result = (*(__int64 (__fastcall **)(__int64))(v5 + 8))(1);
        if ( result < 0 )
          return result;
        v6 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v5 + 56))();
        result = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v5, v6, 1);
        if ( result < 0 )
          return result;
        v4 = (__int64 *)off_1800350E8;
      }
      ++v3;
    }
    if ( ATL::_pPerfRegFunc )
      return ((__int64 (__fastcall *)(HMODULE))ATL::_pPerfRegFunc)(hModule);
  }
  return result;
}

```

## disassembly

```asm
0x1800229c0  mov     r11, rsp
0x1800229c3  mov     [r11+8], rbx
0x1800229c7  mov     [r11+10h], rbp
0x1800229cb  push    rdi
0x1800229cc  sub     rsp, 0C0h
0x1800229d3  mov     rax, cs:__security_cookie
0x1800229da  xor     rax, rsp
0x1800229dd  mov     [rsp+0C8h+var_18], rax
0x1800229e5  movups  xmm1, xmmword ptr cs:MFMediaType_Audio.Data1
0x1800229ec  movdqu  xmmword ptr [rsp+0C8h+var_58], xmm1
0x1800229f2  movups  xmm0, xmmword ptr cs:MFAudioFormat_Float.Data1
0x1800229f9  movdqu  xmmword ptr [r11-48h], xmm0
0x1800229ff  movdqu  xmmword ptr [r11-38h], xmm1
0x180022a05  movups  xmm0, cs:MFAudioFormat_Opus
0x180022a0c  movdqu  xmmword ptr [r11-28h], xmm0
0x180022a12  movups  xmm1, xmmword ptr cs:MFT_CATEGORY_AUDIO_DECODER.Data1
0x180022a19  movdqu  [rsp+0C8h+var_78], xmm1
0x180022a1f  movups  xmm0, xmmword ptr cs:CLSID_CMSOpusDecMFT.Data1
0x180022a26  movdqu  [rsp+0C8h+var_68], xmm0
0x180022a2c  mov     [rsp+0C8h+pAttributes], 0; pAttributes
0x180022a35  lea     rax, [r11-58h]
0x180022a39  mov     [rsp+0C8h+pOutputTypes], rax; pOutputTypes
0x180022a3e  mov     ebp, 1
0x180022a43  mov     [rsp+0C8h+cOutputTypes], ebp; cOutputTypes
0x180022a47  lea     rax, [r11-38h]
0x180022a4b  mov     [rsp+0C8h+pInputTypes], rax; pInputTypes
0x180022a50  mov     [rsp+0C8h+cInputTypes], ebp; cInputTypes
0x180022a54  xor     r9d, r9d; Flags
0x180022a57  lea     r8, pszName; "Microsoft Opus Audio Decoder MFT"
0x180022a5e  lea     rdx, [r11-78h]; guidCategory
0x180022a62  lea     rcx, [r11-68h]; clsidMFT
0x180022a66  call    cs:__imp_MFTRegister
0x180022a6c  test    eax, eax
0x180022a6e  js      loc_180022B2E
0x180022a74  mov     rbx, cs:qword_1800353C8
0x180022a7b  test    rbx, rbx
0x180022a7e  jz      short loc_180022ABA
0x180022a80  jmp     short loc_180022AB4
0x180022a82  mov     ecx, ebp
0x180022a84  mov     rax, [rbx+8]
0x180022a88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a8d  test    eax, eax
0x180022a8f  js      loc_180022B2E
0x180022a95  mov     rax, [rbx+38h]
0x180022a99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a9e  mov     r8d, ebp; int
0x180022aa1  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180022aa4  mov     rcx, [rbx]; rguid
0x180022aa7  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180022aac  test    eax, eax
0x180022aae  js      short loc_180022B2E
0x180022ab0  add     rbx, 48h ; 'H'
0x180022ab4  cmp     qword ptr [rbx], 0
0x180022ab8  jnz     short loc_180022A82
0x180022aba  xor     eax, eax
0x180022abc  mov     rbx, cs:off_1800350E0
0x180022ac3  mov     rcx, cs:off_1800350E8
0x180022aca  jmp     short loc_180022B09
0x180022acc  mov     rdi, [rbx]
0x180022acf  test    rdi, rdi
0x180022ad2  jz      short loc_180022B05
0x180022ad4  mov     ecx, ebp
0x180022ad6  mov     rax, [rdi+8]
0x180022ada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022adf  test    eax, eax
0x180022ae1  js      short loc_180022B2E
0x180022ae3  mov     rax, [rdi+38h]
0x180022ae7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022aec  mov     r8d, ebp; int
0x180022aef  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180022af2  mov     rcx, [rdi]; rguid
0x180022af5  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180022afa  test    eax, eax
0x180022afc  js      short loc_180022B2E
0x180022afe  mov     rcx, cs:off_1800350E8
0x180022b05  add     rbx, 8
0x180022b09  cmp     rbx, rcx
0x180022b0c  jb      short loc_180022ACC
0x180022b0e  test    eax, eax
0x180022b10  js      short loc_180022B2E
0x180022b12  mov     rdx, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x180022b19  test    rdx, rdx
0x180022b1c  jz      short loc_180022B2E
0x180022b1e  mov     rcx, cs:hModule
0x180022b25  mov     rax, rdx
0x180022b28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022b2d  nop
0x180022b2e  mov     rcx, [rsp+0C8h+var_18]
0x180022b36  xor     rcx, rsp; StackCookie
0x180022b39  call    __security_check_cookie
0x180022b3e  lea     r11, [rsp+0C8h+var_8]
0x180022b46  mov     rbx, [r11+10h]
0x180022b4a  mov     rbp, [r11+18h]
0x180022b4e  mov     rsp, r11
0x180022b51  pop     rdi
0x180022b52  retn
```
