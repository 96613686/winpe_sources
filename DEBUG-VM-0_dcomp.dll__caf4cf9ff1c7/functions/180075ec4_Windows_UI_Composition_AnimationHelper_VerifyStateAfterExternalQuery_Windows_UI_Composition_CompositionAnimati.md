# Windows::UI::Composition::AnimationHelper::VerifyStateAfterExternalQuery(Windows::UI::Composition::CompositionAnimation *,std::unordered_map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,Windows::UI::Composition::ParameterOverrideEntry,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,Windows::UI::Composition::ParameterOverrideEntry>>> *,uint,uint,HSTRING__ *,Windows::UI::Composition::CompositionObject *)

- ea: `0x180075ec4`
- end: `0x180076058`
- name: `?VerifyStateAfterExternalQuery@AnimationHelper@Composition@UI@Windows@@YAJPEAVCompositionAnimation@234@PEAV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@IIPEAUHSTRING__@@PEAVCompositionObject@234@@Z`
- size: `404`
- prototype: `__int64 __fastcall(int, int, int, int, HSTRING string, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800764d4`

## callees

- `0x18000f810`
- `0x18001358c`
- `0x180033bb4`
- `0x180073388`
- `0x180075ec4`
- `0x180076834`
- `0x18008ac78`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18017f544`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18017f544`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180075fe4`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180075fe4`

## string_xrefs

- `0x180075fd9`: `The given object has already been closed / disposed and may no longer be used.`
- `0x180075ff2`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtanimationhelper.cpp`
- `0x18007603d`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtanimationhelper.cpp`
- `0x18017f552`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtanimationhelper.cpp`
- `0x180076029`: `Animation template was modified during PopulatePropertyInfo call`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::AnimationHelper::VerifyStateAfterExternalQuery(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4,
        HSTRING string,
        __int64 a6)
{
  _QWORD *v6; // rbx
  char v11; // si
  _QWORD *v12; // rax
  _QWORD *v13; // rdi
  __int64 v14; // rdx
  unsigned int v16; // ebx
  const char *v17; // rax
  __int64 v18; // rdx
  const char *StringRawBuffer; // rax
  int v20; // [rsp+20h] [rbp-88h]
  char *v21; // [rsp+28h] [rbp-80h]
  _BYTE v22[8]; // [rsp+38h] [rbp-70h] BYREF
  _QWORD *v23; // [rsp+40h] [rbp-68h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]
  Microsoft::WRL2::NestableRuntimeClass *v25; // [rsp+B8h] [rbp+10h] BYREF

  v6 = *(_QWORD **)(a2 + 8);
  v11 = 0;
LABEL_2:
  v6 = (_QWORD *)*v6;
  if ( v6 != *(_QWORD **)(a2 + 8) )
  {
    std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::RedirectedPropertyInfo,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::RedirectedPropertyInfo>>,0>>::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::RedirectedPropertyInfo,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::RedirectedPropertyInfo>>,0>>(
      v22,
      v6 + 7);
    v12 = v23;
    v13 = (_QWORD *)*v23;
    while ( 1 )
    {
      if ( v13 == v12 )
      {
        std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::RedirectedPropertyInfo,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::RedirectedPropertyInfo>>,0>>::~_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::RedirectedPropertyInfo,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::RedirectedPropertyInfo>>,0>>(v22);
        goto LABEL_2;
      }
      v14 = v13[8];
      v25 = 0;
      Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionObject>::operator=(&v25, v14);
      if ( v25 )
      {
        if ( (*((_BYTE *)v25 + 48) & 2) == 0 )
        {
          v11 = 1;
          if ( v25 )
            Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v25);
          std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::RedirectedPropertyInfo,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::RedirectedPropertyInfo>>,0>>::~_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::RedirectedPropertyInfo,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::RedirectedPropertyInfo>>,0>>(v22);
          break;
        }
        if ( v25 )
          Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v25);
      }
      v13 = (_QWORD *)*v13;
      v12 = v23;
    }
  }
  if ( !a6 )
  {
    if ( string )
    {
      StringRawBuffer = (const char *)WindowsGetStringRawBuffer(string, 0);
      v16 = -2147024809;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x1E7,
        (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtanimationhelper.cpp",
        (const char *)0x80070057LL,
        (int)"Failed to animate property: %ws (could not resolve target)",
        StringRawBuffer);
      return v16;
    }
    v17 = "Property to animate not provided";
    v18 = 482;
    goto LABEL_25;
  }
  if ( (*(_BYTE *)(a6 + 48) & 2) != 0 && (*(_BYTE *)(a1 + 48) & 2) != 0 && !v11 )
  {
    if ( a3 == a4 )
      return 0;
    v17 = "Animation template was modified during PopulatePropertyInfo call";
    v18 = 501;
LABEL_25:
    v16 = -2147024809;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)v18,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtanimationhelper.cpp",
      (const char *)0x80070057LL,
      (int)v17,
      v21);
    return v16;
  }
  v16 = -2147483629;
  RoOriginateErrorW(2147483667LL, 0, L"The given object has already been closed / disposed and may no longer be used.");
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1EF,
    (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtanimationhelper.cpp",
    (const char *)0x80000013LL,
    v20);
  return v16;
}

```

## disassembly

```asm
0x180075ec4  mov     [rsp+arg_0], rbx
0x180075ec9  mov     [rsp+arg_10], rbp
0x180075ece  push    rsi
0x180075ecf  push    rdi
0x180075ed0  push    r12
0x180075ed2  push    r14
0x180075ed4  push    r15
0x180075ed6  sub     rsp, 80h
0x180075edd  mov     rbx, [rdx+8]
0x180075ee1  mov     r14d, r9d
0x180075ee4  mov     r15d, r8d
0x180075ee7  mov     rbp, rdx
0x180075eea  mov     r12, rcx
0x180075eed  xor     sil, sil
0x180075ef0  mov     rbx, [rbx]
0x180075ef3  cmp     rbx, [rbp+8]
0x180075ef7  jz      loc_180075F7E
0x180075efd  mov     eax, [rbx+30h]
0x180075f00  lea     rdx, [rbx+38h]
0x180075f04  lea     rcx, [rsp+0A8h+var_70]
0x180075f09  mov     [rsp+0A8h+var_78], eax
0x180075f0d  call    ??$?0V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@URedirectedPropertyInfo@Composition@UI@Windows@@@std@@PEAX@std@@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@URedirectedPropertyInfo@Composition@UI@Windows@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@URedirectedPropertyInfo@Composition@UI@Windows@@@std@@@2@$0A@@std@@@std@@IEAA@AEBV01@AEBV?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@URedirectedPropertyInfo@Composition@UI@Windows@@@std@@PEAX@std@@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::RedirectedPropertyInfo,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::RedirectedPropertyInfo>>,0>>::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::RedirectedPropertyInfo,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::RedirectedPropertyInfo>>,0>>(std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::RedirectedPropertyInfo,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::RedirectedPropertyInfo>>,0>> const &,std::allocator<std::_List_node<std::pair<std::wstring const,Windows::UI::Composition::RedirectedPropertyInfo>,void *>> const &)
0x180075f12  mov     rax, [rsp+0A8h+var_68]
0x180075f17  mov     rdi, [rax]
0x180075f1a  cmp     rdi, rax
0x180075f1d  jz      loc_180075FC5
0x180075f23  mov     rdx, [rdi+40h]
0x180075f27  lea     rcx, [rsp+0A8h+arg_8]
0x180075f2f  mov     [rsp+0A8h+arg_8], 0
0x180075f3b  call    ??4?$RefPtr@VCompositionObject@Composition@UI@Windows@@@WRL2@Microsoft@@QEAAAEAV012@PEAVCompositionObject@Composition@UI@Windows@@@Z; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionObject>::operator=(Windows::UI::Composition::CompositionObject *)
0x180075f40  mov     rcx, [rsp+0A8h+arg_8]; this
0x180075f48  test    rcx, rcx
0x180075f4b  jz      short loc_180075F5D
0x180075f4d  test    byte ptr [rcx+30h], 2
0x180075f51  jz      short loc_180075F67
0x180075f53  test    rcx, rcx
0x180075f56  jz      short loc_180075F5D
0x180075f58  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x180075f5d  mov     rdi, [rdi]
0x180075f60  mov     rax, [rsp+0A8h+var_68]
0x180075f65  jmp     short loc_180075F1A
0x180075f67  mov     sil, 1
0x180075f6a  test    rcx, rcx
0x180075f6d  jz      short loc_180075F74
0x180075f6f  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x180075f74  lea     rcx, [rsp+0A8h+var_70]
0x180075f79  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@URedirectedPropertyInfo@Composition@UI@Windows@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@URedirectedPropertyInfo@Composition@UI@Windows@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::RedirectedPropertyInfo,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::RedirectedPropertyInfo>>,0>>::~_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::RedirectedPropertyInfo,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::RedirectedPropertyInfo>>,0>>(void)
0x180075f7e  mov     rax, [rsp+0A8h+arg_28]
0x180075f86  test    rax, rax
0x180075f89  jz      short loc_18007600A
0x180075f8b  test    byte ptr [rax+30h], 2
0x180075f8f  jz      short loc_180075FD4
0x180075f91  test    byte ptr [r12+30h], 2
0x180075f97  jz      short loc_180075FD4
0x180075f99  test    sil, sil
0x180075f9c  jnz     short loc_180075FD4
0x180075f9e  cmp     r15d, r14d
0x180075fa1  jnz     loc_180076029
0x180075fa7  xor     eax, eax
0x180075fa9  lea     r11, [rsp+0A8h+var_28]
0x180075fb1  mov     rbx, [r11+30h]
0x180075fb5  mov     rbp, [r11+40h]
0x180075fb9  mov     rsp, r11
0x180075fbc  pop     r15
0x180075fbe  pop     r14
0x180075fc0  pop     r12
0x180075fc2  pop     rdi
0x180075fc3  pop     rsi
0x180075fc4  retn
0x180075fc5  lea     rcx, [rsp+0A8h+var_70]
0x180075fca  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@URedirectedPropertyInfo@Composition@UI@Windows@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@URedirectedPropertyInfo@Composition@UI@Windows@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::RedirectedPropertyInfo,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::RedirectedPropertyInfo>>,0>>::~_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::RedirectedPropertyInfo,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::RedirectedPropertyInfo>>,0>>(void)
0x180075fcf  jmp     loc_180075EF0
0x180075fd4  mov     ebx, 80000013h
0x180075fd9  lea     r8, aTheGivenObject; "The given object has already been close"...
0x180075fe0  mov     ecx, ebx
0x180075fe2  xor     edx, edx
0x180075fe4  call    cs:__imp_RoOriginateErrorW
0x180075fea  mov     rcx, [rsp+0A8h]; this
0x180075ff2  lea     r8, aOnecoreuapWind_275; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180075ff9  mov     r9d, ebx; char *
0x180075ffc  mov     edx, 1EFh; void *
0x180076001  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076006  mov     eax, ebx
0x180076008  jmp     short loc_180075FA9
0x18007600a  mov     rcx, [rsp+0A8h+string]; string
0x180076012  test    rcx, rcx
0x180076015  jnz     loc_18017F542
0x18007601b  lea     rax, aPropertyToAnim; "Property to animate not provided"
0x180076022  mov     edx, 1E2h
0x180076027  jmp     short loc_180076035
0x180076029  lea     rax, aAnimationTempl; "Animation template was modified during "...
0x180076030  mov     edx, 1F5h; void *
0x180076035  mov     rcx, [rsp+0A8h]; this
0x18007603d  lea     r8, aOnecoreuapWind_275; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180076044  mov     ebx, 80070057h
0x180076049  mov     qword ptr [rsp+0A8h+var_88], rax; int
0x18007604e  mov     r9d, ebx; char *
0x180076051  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180076056  jmp     short loc_180076006
0x18017f542  xor     edx, edx; length
0x18017f544  call    cs:__imp_WindowsGetStringRawBuffer
0x18017f54a  mov     rcx, [rsp+0A8h]; this
0x18017f552  lea     r8, aOnecoreuapWind_275; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x18017f559  mov     [rsp+0A8h+var_80], rax; char *
0x18017f55e  mov     ebx, 80070057h
0x18017f563  lea     rax, aFailedToAnimat; "Failed to animate property: %ws (could "...
0x18017f56a  mov     r9d, ebx; char *
0x18017f56d  mov     edx, 1E7h; void *
0x18017f572  mov     qword ptr [rsp+0A8h+var_88], rax; int
0x18017f577  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18017f57c  nop
0x18017f57d  jmp     loc_180076006
```
