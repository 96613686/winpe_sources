# Windows::Graphics::Capture::Server::AllowAppSiloAndFailUapAndInsufficientIL(bool *)

- ea: `0x18001e5e4`
- end: `0x18001e741`
- name: `?AllowAppSiloAndFailUapAndInsufficientIL@Server@Capture@Graphics@Windows@@YAJPEA_N@Z`
- size: `349`
- prototype: `__int64 __fastcall(Windows::Graphics::Capture::Server *this, bool *)`
- caller_count: `3`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016240`
- `0x1800162d0`
- `0x180016370`

## callees

- `0x18000907c`
- `0x18001e5e4`
- `0x18001e964`
- `0x18001ec98`
- `0x18001ee10`
- `0x18001f4d0`
- `0x18001f59c`
- `0x18001f668`
- `0x18001f7e0`
- `0x18001fbe0`

## string_xrefs

- `0x18001e611`: `onecoreuap\windows\dwm\capture\svc\dll\clientprocess.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Graphics::Capture::Server::AllowAppSiloAndFailUapAndInsufficientIL(
        Windows::Graphics::Capture::Server *this,
        bool *a2)
{
  int IsAppSilo; // ebx
  __int64 v4; // rdx
  char IsEnabled; // al
  bool *v7; // rdx
  bool *v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // rdx
  Windows::Graphics::Capture::Server *v11; // rcx
  Windows::Graphics::Capture::Server *v12; // rcx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  int v15; // [rsp+40h] [rbp+20h] BYREF
  char v16; // [rsp+48h] [rbp+28h] BYREF
  char v17; // [rsp+50h] [rbp+30h] BYREF

  *(_BYTE *)this = 0;
  LOBYTE(v15) = 0;
  IsAppSilo = Windows::Graphics::Capture::Server::IsAppSilo((Windows::Graphics::Capture::Server *)&v15, a2);
  if ( IsAppSilo < 0 )
  {
    v4 = 218;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\clientprocess.cpp",
      (const char *)(unsigned int)IsAppSilo,
      savedregs);
    return (unsigned int)IsAppSilo;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_CAMIGraphicsCaptureItemInteropFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Capture_CAMIGraphicsCaptureItemInteropFix>::GetImpl'::`2'::impl);
  v16 = 0;
  if ( IsEnabled )
  {
    IsAppSilo = Windows::Graphics::Capture::Server::IsAppContainer((Windows::Graphics::Capture::Server *)&v16, v7);
    if ( IsAppSilo < 0 )
    {
      v4 = 223;
      goto LABEL_3;
    }
    v17 = 0;
    IsAppSilo = Windows::Graphics::Capture::Server::IsAtLeastMediumIL((Windows::Graphics::Capture::Server *)&v17, v8);
    if ( IsAppSilo < 0 )
    {
      v4 = 225;
      goto LABEL_3;
    }
    if ( !v16 && !v17 && !(_BYTE)v15 )
      return 2147942405LL;
    *(_BYTE *)this = 1;
    LOBYTE(v9) = 1;
    v15 = 3;
    IsAppSilo = Windows::Graphics::Capture::Server::CheckCAMCapability(0, v9, &v15);
    if ( IsAppSilo < 0 )
    {
      v4 = 240;
      goto LABEL_3;
    }
    if ( v15 != 4 )
      return 2147942405LL;
    return 0;
  }
  IsAppSilo = Windows::Graphics::Capture::Server::IsCUA((Windows::Graphics::Capture::Server *)&v16, v7);
  if ( IsAppSilo < 0 )
  {
    v4 = 252;
    goto LABEL_3;
  }
  if ( !v16 && !(_BYTE)v15 )
  {
    IsAppSilo = Windows::Graphics::Capture::Server::FailIfUapApplication(v11);
    if ( IsAppSilo < 0 )
    {
      v4 = 274;
      goto LABEL_3;
    }
    IsAppSilo = Windows::Graphics::Capture::Server::FailIfNotAtLeastMediumIL(v12);
    if ( IsAppSilo < 0 )
    {
      v4 = 276;
      goto LABEL_3;
    }
    return 0;
  }
  *(_BYTE *)this = 1;
  LOBYTE(v10) = 1;
  v15 = 3;
  IsAppSilo = Windows::Graphics::Capture::Server::CheckCAMCapability(0, v10, &v15);
  if ( IsAppSilo < 0 )
  {
    v4 = 264;
    goto LABEL_3;
  }
  return v15 != 4 ? 0x80070005 : 0;
}

```

## disassembly

```asm
0x18001e5e4  push    rbp
0x18001e5e6  push    rbx
0x18001e5e7  push    rdi; int
0x18001e5e8  mov     rbp, rsp
0x18001e5eb  sub     rsp, 20h
0x18001e5ef  mov     rdi, rcx
0x18001e5f2  mov     byte ptr [rcx], 0
0x18001e5f5  lea     rcx, [rbp+arg_0]; this
0x18001e5f9  mov     byte ptr [rbp+arg_0], 0
0x18001e5fd  call    ?IsAppSilo@Server@Capture@Graphics@Windows@@YAJPEA_N@Z; Windows::Graphics::Capture::Server::IsAppSilo(bool *)
0x18001e602  mov     ebx, eax
0x18001e604  test    eax, eax
0x18001e606  jns     short loc_18001E627
0x18001e608  mov     edx, 0DAh; void *
0x18001e60d  mov     rcx, [rbp+18h]; this
0x18001e611  lea     r8, aOnecoreuapWind_9; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001e618  mov     r9d, ebx; char *
0x18001e61b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e620  mov     eax, ebx
0x18001e622  jmp     loc_18001E739
0x18001e627  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Capture_CAMIGraphicsCaptureItemInteropFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Capture_CAMIGraphicsCaptureItemInteropFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_CAMIGraphicsCaptureItemInteropFix> `wil::Feature<__WilFeatureTraits_Feature_Capture_CAMIGraphicsCaptureItemInteropFix>::GetImpl(void)'::`2'::impl
0x18001e62e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Capture_CAMIGraphicsCaptureItemInteropFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_CAMIGraphicsCaptureItemInteropFix>::__private_IsEnabled(void)
0x18001e633  mov     [rbp+arg_8], 0
0x18001e637  lea     rcx, [rbp+arg_8]; this
0x18001e63b  test    al, al
0x18001e63d  jz      short loc_18001E6B4
0x18001e63f  call    ?IsAppContainer@Server@Capture@Graphics@Windows@@YAJPEA_N@Z; Windows::Graphics::Capture::Server::IsAppContainer(bool *)
0x18001e644  mov     ebx, eax
0x18001e646  test    eax, eax
0x18001e648  jns     short loc_18001E651
0x18001e64a  mov     edx, 0DFh
0x18001e64f  jmp     short loc_18001E60D
0x18001e651  lea     rcx, [rbp+arg_10]; this
0x18001e655  mov     [rbp+arg_10], 0
0x18001e659  call    ?IsAtLeastMediumIL@Server@Capture@Graphics@Windows@@YAJPEA_N@Z; Windows::Graphics::Capture::Server::IsAtLeastMediumIL(bool *)
0x18001e65e  mov     ebx, eax
0x18001e660  test    eax, eax
0x18001e662  jns     short loc_18001E66B
0x18001e664  mov     edx, 0E1h
0x18001e669  jmp     short loc_18001E60D
0x18001e66b  cmp     [rbp+arg_8], 0
0x18001e66f  jnz     short loc_18001E67D
0x18001e671  cmp     [rbp+arg_10], 0
0x18001e675  jnz     short loc_18001E67D
0x18001e677  cmp     byte ptr [rbp+arg_0], 0
0x18001e67b  jz      short loc_18001E6AA
0x18001e67d  lea     r8, [rbp+arg_0]
0x18001e681  mov     byte ptr [rdi], 1
0x18001e684  mov     dl, 1
0x18001e686  mov     [rbp+arg_0], 3
0x18001e68d  xor     ecx, ecx
0x18001e68f  call    ?CheckCAMCapability@Server@Capture@Graphics@Windows@@YAJW4CaptureServerAccessRequestKind@1234@_NPEAW4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@4@@Z; Windows::Graphics::Capture::Server::CheckCAMCapability(Windows::Graphics::Capture::Server::CaptureServerAccessRequestKind,bool,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus *)
0x18001e694  mov     ebx, eax
0x18001e696  test    eax, eax
0x18001e698  jns     short loc_18001E6A4
0x18001e69a  mov     edx, 0F0h
0x18001e69f  jmp     loc_18001E60D
0x18001e6a4  cmp     [rbp+arg_0], 4
0x18001e6a8  jz      short loc_18001E6FF
0x18001e6aa  mov     eax, 80070005h
0x18001e6af  jmp     loc_18001E739
0x18001e6b4  call    ?IsCUA@Server@Capture@Graphics@Windows@@YAJPEA_N@Z; Windows::Graphics::Capture::Server::IsCUA(bool *)
0x18001e6b9  mov     ebx, eax
0x18001e6bb  test    eax, eax
0x18001e6bd  jns     short loc_18001E6C9
0x18001e6bf  mov     edx, 0FCh
0x18001e6c4  jmp     loc_18001E60D
0x18001e6c9  cmp     [rbp+arg_8], 0
0x18001e6cd  jnz     short loc_18001E703
0x18001e6cf  cmp     byte ptr [rbp+arg_0], 0
0x18001e6d3  jnz     short loc_18001E703
0x18001e6d5  call    ?FailIfUapApplication@Server@Capture@Graphics@Windows@@YAJXZ; Windows::Graphics::Capture::Server::FailIfUapApplication(void)
0x18001e6da  mov     ebx, eax
0x18001e6dc  test    eax, eax
0x18001e6de  jns     short loc_18001E6EA
0x18001e6e0  mov     edx, 112h
0x18001e6e5  jmp     loc_18001E60D
0x18001e6ea  call    ?FailIfNotAtLeastMediumIL@Server@Capture@Graphics@Windows@@YAJXZ; Windows::Graphics::Capture::Server::FailIfNotAtLeastMediumIL(void)
0x18001e6ef  mov     ebx, eax
0x18001e6f1  test    eax, eax
0x18001e6f3  jns     short loc_18001E6FF
0x18001e6f5  mov     edx, 114h
0x18001e6fa  jmp     loc_18001E60D
0x18001e6ff  xor     eax, eax
0x18001e701  jmp     short loc_18001E739
0x18001e703  lea     r8, [rbp+arg_0]
0x18001e707  mov     byte ptr [rdi], 1
0x18001e70a  mov     dl, 1
0x18001e70c  mov     [rbp+arg_0], 3
0x18001e713  xor     ecx, ecx
0x18001e715  call    ?CheckCAMCapability@Server@Capture@Graphics@Windows@@YAJW4CaptureServerAccessRequestKind@1234@_NPEAW4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@4@@Z; Windows::Graphics::Capture::Server::CheckCAMCapability(Windows::Graphics::Capture::Server::CaptureServerAccessRequestKind,bool,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus *)
0x18001e71a  mov     ebx, eax
0x18001e71c  test    eax, eax
0x18001e71e  jns     short loc_18001E72A
0x18001e720  mov     edx, 108h
0x18001e725  jmp     loc_18001E60D
0x18001e72a  mov     eax, [rbp+arg_0]
0x18001e72d  sub     eax, 4
0x18001e730  neg     eax
0x18001e732  sbb     eax, eax
0x18001e734  and     eax, 80070005h
0x18001e739  add     rsp, 20h
0x18001e73d  pop     rdi
0x18001e73e  pop     rbx
0x18001e73f  pop     rbp
0x18001e740  retn
```
