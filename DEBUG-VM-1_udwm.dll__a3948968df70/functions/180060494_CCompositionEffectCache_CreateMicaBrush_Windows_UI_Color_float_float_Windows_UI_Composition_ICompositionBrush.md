# CCompositionEffectCache::CreateMicaBrush(Windows::UI::Color,float,float,Windows::UI::Composition::ICompositionBrush * *)

- ea: `0x180060494`
- end: `0x180060580`
- name: `?CreateMicaBrush@CCompositionEffectCache@@CAJUColor@UI@Windows@@MMPEAPEAUICompositionBrush@Composition@34@@Z`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180060080`

## callees

- `0x180060494`
- `0x180081a68`
- `0x180095130`

## import_xrefs

- `wuceffects!CreateMicaBrush` at `0x180060542`
- `wuceffects!CreateMicaBrush` at `0x180060542`

## string_xrefs

- `0x180060553`: `clientcore\windows\dwm\udwm\compositioneffectcache.cpp`

## pseudocode

```c
__int64 __fastcall CCompositionEffectCache::CreateMicaBrush(unsigned int a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  CDesktopManager *v4; // rax
  __int64 v5; // r9
  int MicaBrush; // eax
  unsigned int v7; // ebx
  int v9; // [rsp+20h] [rbp-38h]
  float v10[4]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = CDesktopManager::s_pDesktopManagerInstance;
  *a4 = 0;
  v9 = (int)a4;
  v5 = *(_QWORD *)(*((_QWORD *)v4 + 6) + 40LL);
  v10[0] = (float)BYTE1(a1) / 255.0;
  v10[2] = (float)HIBYTE(a1) / 255.0;
  v10[1] = (float)BYTE2(a1) / 255.0;
  v10[3] = (float)(unsigned __int8)a1 / 255.0;
  MicaBrush = CreateMicaBrush(v5, v10);
  v7 = MicaBrush;
  if ( MicaBrush >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xC1,
    (unsigned int)"clientcore\\windows\\dwm\\udwm\\compositioneffectcache.cpp",
    (const char *)(unsigned int)MicaBrush,
    v9);
  return v7;
}

```

## disassembly

```asm
0x180060494  push    rbx
0x180060496  sub     rsp, 50h
0x18006049a  mov     rax, cs:__security_cookie
0x1800604a1  xor     rax, rsp
0x1800604a4  mov     [rsp+58h+var_18], rax
0x1800604a9  movss   xmm4, cs:__real@437f0000
0x1800604b1  mov     r8d, ecx
0x1800604b4  mov     rax, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x1800604bb  mov     r10d, ecx
0x1800604be  mov     qword ptr [r9], 0
0x1800604c5  mov     rbx, r9
0x1800604c8  shr     r8d, 8
0x1800604cc  mov     r11d, ecx
0x1800604cf  shr     r10d, 10h
0x1800604d3  movaps  xmm3, xmm2
0x1800604d6  mov     rdx, [rax+30h]
0x1800604da  movaps  xmm2, xmm1
0x1800604dd  movzx   eax, r8b
0x1800604e1  shr     r11d, 18h
0x1800604e5  mov     qword ptr [rsp+58h+var_38], rbx; int
0x1800604ea  mov     r9, [rdx+28h]
0x1800604ee  lea     rdx, [rsp+58h+var_28]
0x1800604f3  movd    xmm0, eax
0x1800604f7  cvtdq2ps xmm0, xmm0
0x1800604fa  movzx   eax, r10b
0x1800604fe  movd    xmm1, r11d
0x180060503  divss   xmm0, xmm4
0x180060507  cvtdq2ps xmm1, xmm1
0x18006050a  movss   [rsp+58h+var_28], xmm0
0x180060510  movd    xmm0, eax
0x180060514  cvtdq2ps xmm0, xmm0
0x180060517  movzx   eax, cl
0x18006051a  mov     rcx, r9
0x18006051d  divss   xmm1, xmm4
0x180060521  divss   xmm0, xmm4
0x180060525  movss   [rsp+58h+var_20], xmm1
0x18006052b  movss   [rsp+58h+var_24], xmm0
0x180060531  movd    xmm0, eax
0x180060535  cvtdq2ps xmm0, xmm0
0x180060538  divss   xmm0, xmm4
0x18006053c  movss   [rsp+58h+var_1C], xmm0
0x180060542  call    cs:__imp_CreateMicaBrush
0x180060548  mov     ebx, eax
0x18006054a  test    eax, eax
0x18006054c  jns     short loc_18006057C
0x18006054e  mov     rcx, [rsp+58h]; this
0x180060553  lea     r8, aClientcoreWind_90; "clientcore\\windows\\dwm\\udwm\\composi"...
0x18006055a  mov     r9d, eax; char *
0x18006055d  mov     edx, 0C1h; void *
0x180060562  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180060567  mov     eax, ebx
0x180060569  mov     rcx, [rsp+58h+var_18]
0x18006056e  xor     rcx, rsp; StackCookie
0x180060571  call    __security_check_cookie
0x180060576  add     rsp, 50h
0x18006057a  pop     rbx
0x18006057b  retn
0x18006057c  xor     eax, eax
0x18006057e  jmp     short loc_180060569
```
