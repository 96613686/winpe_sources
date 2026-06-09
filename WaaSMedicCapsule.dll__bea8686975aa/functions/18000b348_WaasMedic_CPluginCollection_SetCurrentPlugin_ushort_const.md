# WaasMedic::CPluginCollection::SetCurrentPlugin(ushort const *)

- ea: `0x18000b348`
- end: `0x18000b51d`
- name: `?SetCurrentPlugin@CPluginCollection@WaasMedic@@QEAAJPEBG@Z`
- size: `469`
- prototype: `int(WaasMedic::CPluginCollection *__hidden this, const unsigned __int16 *)`
- caller_count: `7`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800087a0`
- `0x180008820`
- `0x180009200`
- `0x180009390`
- `0x180009420`
- `0x1800094a0`
- `0x180009520`

## callees

- `0x18000b308`
- `0x18000b348`
- `0x18001f068`
- `0x18002543c`
- `0x180064010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000b37e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000b37e`

## string_xrefs

- `0x18000b363`: `Setting current Plugin to %s`
- `0x18000b3a9`: `Failed to CreateInstance of plugin provider`
- `0x18000b3b8`: `onecore\enduser\waasmedic\lib\plugins\plugincollection.cpp`
- `0x18000b44d`: `onecore\enduser\waasmedic\lib\plugins\plugincollection.cpp`
- `0x18000b4d2`: `onecore\enduser\waasmedic\lib\plugins\plugincollection.cpp`
- `0x18000b43e`: `Failed to set m_pszCurrentPluginName`
- `0x18000b4c3`: `Failed to get Plugin instance of %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WaasMedic::CPluginCollection::SetCurrentPlugin(WaasMedic::CPluginCollection *this, const char *a2)
{
  _WORD *v4; // rdi
  unsigned int v5; // ebx
  __int64 v7; // rax
  const char *v8; // rcx
  __int64 v9; // rdx
  __int16 v10; // r8
  _WORD *v11; // rcx
  struct WaasMedic::IPluginProvider *v12; // rbx
  __int64 (__fastcall *v13)(struct WaasMedic::IPluginProvider *, const char *, char *, WaasMedic::CPluginCollection *); // rdi
  __int64 v14; // rcx
  int v15; // edi
  char *v16; // [rsp+28h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  struct WaasMedic::IPluginProvider *v18; // [rsp+50h] [rbp+8h] BYREF

  LogLevelW(5u, L"Setting current Plugin to %s", a2);
  v4 = (_WORD *)((char *)this + 40);
  if ( (unsigned int)_o__wcsicmp((char *)this + 40, a2) )
  {
    v18 = 0;
    v5 = WaasMedic::CPluginProvider::CreateInstance(&v18);
    if ( (v5 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xF,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\plugincollection.cpp",
        (const char *)v5,
        (int)"Failed to CreateInstance of plugin provider",
        v16);
      if ( v18 )
        (*(void (__fastcall **)(struct WaasMedic::IPluginProvider *))(*(_QWORD *)v18 + 16LL))(v18);
      return v5;
    }
    v7 = 2147483646;
    v8 = a2;
    v9 = 255;
    do
    {
      if ( !v7 )
        break;
      v10 = *(_WORD *)v8;
      if ( !*(_WORD *)v8 )
        break;
      v8 += 2;
      *v4++ = v10;
      --v7;
      --v9;
    }
    while ( v9 );
    v5 = v9 == 0 ? 0x8007007A : 0;
    v11 = v4 - 1;
    if ( v9 )
      v11 = v4;
    *v11 = 0;
    if ( !v9 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x10,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\plugincollection.cpp",
        (const char *)v5,
        (int)"Failed to set m_pszCurrentPluginName",
        v16);
      if ( v18 )
        (*(void (__fastcall **)(struct WaasMedic::IPluginProvider *))(*(_QWORD *)v18 + 16LL))(v18);
      return v5;
    }
    v12 = v18;
    v13 = *(__int64 (__fastcall **)(struct WaasMedic::IPluginProvider *, const char *, char *, WaasMedic::CPluginCollection *))(*(_QWORD *)v18 + 24LL);
    v14 = *(_QWORD *)this;
    if ( *(_QWORD *)this )
    {
      *(_QWORD *)this = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    v15 = v13(v12, a2, (char *)this + 8, this);
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x11,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\plugincollection.cpp",
        (const char *)(unsigned int)v15,
        (int)"Failed to get Plugin instance of %ws",
        a2);
      (*(void (__fastcall **)(struct WaasMedic::IPluginProvider *))(*(_QWORD *)v12 + 16LL))(v12);
      return (unsigned int)v15;
    }
    (*(void (__fastcall **)(struct WaasMedic::IPluginProvider *))(*(_QWORD *)v12 + 16LL))(v12);
  }
  return 0;
}

```

## disassembly

```asm
0x18000b348  mov     [rsp+arg_8], rbx
0x18000b34d  mov     [rsp+arg_10], rbp
0x18000b352  push    rsi
0x18000b353  push    rdi
0x18000b354  push    r14
0x18000b356  sub     rsp, 30h
0x18000b35a  mov     rbp, rdx
0x18000b35d  mov     rsi, rcx
0x18000b360  mov     r8, rdx
0x18000b363  lea     rdx, aSettingCurrent; "Setting current Plugin to %s"
0x18000b36a  mov     ecx, 5; unsigned __int8
0x18000b36f  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18000b374  lea     rdi, [rsi+28h]
0x18000b378  mov     rdx, rbp
0x18000b37b  mov     rcx, rdi
0x18000b37e  call    cs:__imp__o__wcsicmp
0x18000b384  xor     r14d, r14d
0x18000b387  test    eax, eax
0x18000b389  jz      loc_18000B508
0x18000b38f  mov     [rsp+48h+arg_0], r14
0x18000b394  lea     rcx, [rsp+48h+arg_0]; struct WaasMedic::IPluginProvider **
0x18000b399  call    ?CreateInstance@CPluginProvider@WaasMedic@@SAJPEAPEAVIPluginProvider@2@@Z; WaasMedic::CPluginProvider::CreateInstance(WaasMedic::IPluginProvider * *)
0x18000b39e  mov     ebx, eax
0x18000b3a0  test    eax, eax
0x18000b3a2  jns     short loc_18000B3E7
0x18000b3a4  mov     rcx, [rsp+48h]; this
0x18000b3a9  lea     rax, aFailedToCreate_0; "Failed to CreateInstance of plugin prov"...
0x18000b3b0  mov     qword ptr [rsp+48h+var_28], rax; int
0x18000b3b5  mov     r9d, ebx; char *
0x18000b3b8  lea     r8, aOnecoreEnduser_23; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18000b3bf  lea     edx, [r14+0Fh]; void *
0x18000b3c3  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000b3c8  nop
0x18000b3c9  mov     rcx, [rsp+48h+arg_0]
0x18000b3ce  test    rcx, rcx
0x18000b3d1  jz      short loc_18000B3E0
0x18000b3d3  mov     rax, [rcx]
0x18000b3d6  mov     rax, [rax+10h]
0x18000b3da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3df  nop
0x18000b3e0  mov     eax, ebx
0x18000b3e2  jmp     loc_18000B50A
0x18000b3e7  mov     eax, 7FFFFFFEh
0x18000b3ec  mov     rcx, rbp
0x18000b3ef  mov     edx, 0FFh
0x18000b3f4  test    rax, rax
0x18000b3f7  jz      short loc_18000B418
0x18000b3f9  movzx   r8d, word ptr [rcx]
0x18000b3fd  test    r8w, r8w
0x18000b401  jz      short loc_18000B418
0x18000b403  add     rcx, 2
0x18000b407  mov     [rdi], r8w
0x18000b40b  add     rdi, 2
0x18000b40f  dec     rax
0x18000b412  sub     rdx, 1
0x18000b416  jnz     short loc_18000B3F4
0x18000b418  mov     rax, rdx
0x18000b41b  neg     rax
0x18000b41e  sbb     ebx, ebx
0x18000b420  not     ebx
0x18000b422  and     ebx, 8007007Ah
0x18000b428  lea     rcx, [rdi-2]
0x18000b42c  test    rdx, rdx
0x18000b42f  cmovnz  rcx, rdi
0x18000b433  mov     [rcx], r14w
0x18000b437  jnz     short loc_18000B47B
0x18000b439  mov     rcx, [rsp+48h]; this
0x18000b43e  lea     rax, aFailedToSetMPs; "Failed to set m_pszCurrentPluginName"
0x18000b445  mov     qword ptr [rsp+48h+var_28], rax; int
0x18000b44a  mov     r9d, ebx; char *
0x18000b44d  lea     r8, aOnecoreEnduser_23; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18000b454  mov     edx, 10h; void *
0x18000b459  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000b45e  nop
0x18000b45f  mov     rcx, [rsp+48h+arg_0]
0x18000b464  test    rcx, rcx
0x18000b467  jz      short loc_18000B476
0x18000b469  mov     rdx, [rcx]
0x18000b46c  mov     rax, [rdx+10h]
0x18000b470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b475  nop
0x18000b476  jmp     loc_18000B3E0
0x18000b47b  mov     rbx, [rsp+48h+arg_0]
0x18000b480  mov     rax, [rbx]
0x18000b483  mov     rdi, [rax+18h]
0x18000b487  mov     rcx, [rsi]
0x18000b48a  test    rcx, rcx
0x18000b48d  jz      short loc_18000B49E
0x18000b48f  mov     [rsi], r14
0x18000b492  mov     rdx, [rcx]
0x18000b495  mov     rax, [rdx+10h]
0x18000b499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b49e  lea     r8, [rsi+8]
0x18000b4a2  mov     r9, rsi
0x18000b4a5  mov     rdx, rbp
0x18000b4a8  mov     rcx, rbx
0x18000b4ab  mov     rax, rdi
0x18000b4ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4b3  mov     edi, eax
0x18000b4b5  test    eax, eax
0x18000b4b7  jns     short loc_18000B4F8
0x18000b4b9  mov     rcx, [rsp+48h]; this
0x18000b4be  mov     [rsp+48h+var_20], rbp; char *
0x18000b4c3  lea     rax, aFailedToGetPlu; "Failed to get Plugin instance of %ws"
0x18000b4ca  mov     qword ptr [rsp+48h+var_28], rax; int
0x18000b4cf  mov     r9d, edi; char *
0x18000b4d2  lea     r8, aOnecoreEnduser_23; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18000b4d9  mov     edx, 11h; void *
0x18000b4de  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000b4e3  nop
0x18000b4e4  mov     rax, [rbx]
0x18000b4e7  mov     rcx, rbx
0x18000b4ea  mov     rax, [rax+10h]
0x18000b4ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4f3  nop
0x18000b4f4  mov     eax, edi
0x18000b4f6  jmp     short loc_18000B50A
0x18000b4f8  mov     rax, [rbx]
0x18000b4fb  mov     rcx, rbx
0x18000b4fe  mov     rax, [rax+10h]
0x18000b502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b507  nop
0x18000b508  xor     eax, eax
0x18000b50a  mov     rbx, [rsp+48h+arg_8]
0x18000b50f  mov     rbp, [rsp+48h+arg_10]
0x18000b514  add     rsp, 30h
0x18000b518  pop     r14
0x18000b51a  pop     rdi
0x18000b51b  pop     rsi
0x18000b51c  retn
```
