# GipEffectManager::GipEffectManager(Windows::Gaming::Input::Custom::IGipGameControllerProvider *)

- ea: `0x18000ed50`
- end: `0x18000f003`
- name: `??0GipEffectManager@@QEAA@PEAUIGipGameControllerProvider@Custom@Input@Gaming@Windows@@@Z`
- size: `691`
- prototype: `GipEffectManager *__fastcall(GipEffectManager *__hidden this, struct Windows::Gaming::Input::Custom::IGipGameControllerProvider *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180014f18`

## callees

- `0x180002264`
- `0x18000d68c`
- `0x18000ed50`
- `0x18004c8a5`
- `0x18004d010`

## string_xrefs

- `0x18000ef2c`: `Created GIP effect manager for device`

## pseudocode

```c
GipEffectManager *__fastcall GipEffectManager::GipEffectManager(
        GipEffectManager *this,
        __int64 (__fastcall ***a2)(struct Windows::Gaming::Input::Custom::IGipGameControllerProvider *, GUID *, __int64 *))
{
  char *v2; // rdi
  __int64 (__fastcall **v5)(struct Windows::Gaming::Input::Custom::IGipGameControllerProvider *, GUID *, __int64 *); // rax
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // r8d
  int v11; // r9d
  char *v12; // rax
  __int64 v14; // [rsp+70h] [rbp+7h] BYREF
  __int16 v15; // [rsp+78h] [rbp+Fh] BYREF
  __int16 v16; // [rsp+7Ah] [rbp+11h] BYREF
  __int16 v17; // [rsp+7Ch] [rbp+13h] BYREF
  __int16 v18; // [rsp+7Eh] [rbp+15h] BYREF
  __int64 v19; // [rsp+80h] [rbp+17h] BYREF
  int v20; // [rsp+88h] [rbp+1Fh] BYREF
  const char *v21; // [rsp+90h] [rbp+27h] BYREF
  const char *v22; // [rsp+98h] [rbp+2Fh] BYREF
  __int16 v23; // [rsp+D0h] [rbp+67h] BYREF
  __int16 v24; // [rsp+D8h] [rbp+6Fh] BYREF
  __int16 v25; // [rsp+E0h] [rbp+77h] BYREF
  __int16 v26; // [rsp+E8h] [rbp+7Fh] BYREF

  *((_QWORD *)this + 1) = a2;
  v2 = (char *)this + 16;
  *(_QWORD *)this = &GipEffectManager::`vftable';
  memset_0((char *)this + 16, 0, 0x280u);
  *((_DWORD *)this + 168) = 0;
  *((_QWORD *)this + 83) = (char *)this + 656;
  *((_QWORD *)this + 82) = (char *)this + 656;
  *((_DWORD *)this + 174) = 0;
  *((_QWORD *)this + 86) = (char *)this + 680;
  *((_QWORD *)this + 85) = (char *)this + 680;
  *((_QWORD *)this + 88) = 0xBFF0000000000000uLL;
  *((_QWORD *)this + 89) = 0x3FF0000000000000LL;
  ((void (__fastcall *)(__int64 (__fastcall ***)(struct Windows::Gaming::Input::Custom::IGipGameControllerProvider *, GUID *, __int64 *)))(*a2)[1])(a2);
  v5 = *a2;
  v19 = 0;
  v6 = (*v5)(
         (struct Windows::Gaming::Input::Custom::IGipGameControllerProvider *)a2,
         &GUID_e6d73982_2996_4559_b16c_3e57d46e58d6,
         &v19);
  if ( v6 < 0 )
  {
    GameInputFailFast((unsigned int)v6, 15);
    __debugbreak();
  }
  v24 = 0;
  v23 = 0;
  v14 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v19 + 64LL))(v19, &v24);
  if ( v7 < 0 )
  {
    GameInputFailFast((unsigned int)v7, 19);
    __debugbreak();
  }
  v8 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v19 + 56LL))(v19, &v23);
  if ( v8 < 0 )
  {
    GameInputFailFast((unsigned int)v8, 20);
    JUMPOUT(0x18000F002LL);
  }
  v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v19 + 48LL))(v19, &v14);
  if ( v9 < 0 )
  {
    GameInputFailFast((unsigned int)v9, 21);
    __debugbreak();
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  *((_WORD *)this + 360) = v24;
  *((_WORD *)this + 361) = v23;
  *(_QWORD *)((char *)this + 724) = v14;
  if ( (unsigned int)dword_180069000 > 4 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
  {
    v25 = HIWORD(v14);
    v26 = WORD2(v14);
    v15 = WORD1(v14);
    v16 = v14;
    v17 = v23;
    v18 = v24;
    v21 = "Created GIP effect manager for device";
    v22 = "onecore\\xbox\\gameinput\\feedback\\gip\\GipEffectManager.cpp";
    v20 = 39;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>>(
      qword_180069018,
      (unsigned int)&dword_18005D9AC,
      v10,
      v11,
      (__int64)&v22,
      (__int64)&v20,
      (__int64)&v21,
      (__int64)&v18,
      (__int64)&v17,
      (__int64)&v16,
      (__int64)&v15,
      (__int64)&v26,
      (__int64)&v25);
  }
  v12 = v2 + 640;
  do
  {
    *((_DWORD *)v2 + 2) = -1;
    *((_QWORD *)v2 + 3) = -1;
    v2 += 40;
  }
  while ( v2 != v12 );
  return this;
}

```

## disassembly

```asm
0x18000ed50  push    rbp
0x18000ed52  push    rbx
0x18000ed53  push    rsi
0x18000ed54  push    rdi
0x18000ed55  lea     rbp, [rsp-3Fh]
0x18000ed5a  sub     rsp, 0A8h
0x18000ed61  mov     [rcx+8], rdx
0x18000ed65  lea     rax, ??_7GipEffectManager@@6B@; const GipEffectManager::`vftable'
0x18000ed6c  lea     rdi, [rcx+10h]
0x18000ed70  mov     [rcx], rax
0x18000ed73  mov     rbx, rdx
0x18000ed76  mov     rsi, rcx
0x18000ed79  mov     rcx, rdi; void *
0x18000ed7c  xor     edx, edx; Val
0x18000ed7e  mov     r8d, 280h; Size
0x18000ed84  call    memset_0
0x18000ed89  lea     rax, [rsi+290h]
0x18000ed90  mov     rcx, rbx
0x18000ed93  mov     dword ptr [rax+10h], 0
0x18000ed9a  mov     [rax+8], rax
0x18000ed9e  mov     [rax], rax
0x18000eda1  lea     rax, [rsi+2A8h]
0x18000eda8  mov     dword ptr [rax+10h], 0
0x18000edaf  mov     [rax+8], rax
0x18000edb3  mov     [rax], rax
0x18000edb6  mov     rax, 0BFF0000000000000h
0x18000edc0  mov     [rsi+2C0h], rax
0x18000edc7  mov     rax, 3FF0000000000000h
0x18000edd1  mov     [rsi+2C8h], rax
0x18000edd8  mov     rax, [rbx]
0x18000eddb  mov     rax, [rax+8]
0x18000eddf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ede4  mov     rax, [rbx]
0x18000ede7  lea     r8, [rbp+57h+var_40]
0x18000edeb  lea     rdx, _GUID_e6d73982_2996_4559_b16c_3e57d46e58d6
0x18000edf2  mov     [rbp+57h+var_40], 0
0x18000edfa  mov     rcx, rbx
0x18000edfd  mov     rax, [rax]
0x18000ee00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee05  test    eax, eax
0x18000ee07  js      loc_18000EFDC
0x18000ee0d  mov     rcx, [rbp+57h+var_40]
0x18000ee11  lea     rdx, [rbp+57h+arg_8]
0x18000ee15  xor     eax, eax
0x18000ee17  mov     [rbp+57h+arg_8], ax
0x18000ee1b  mov     [rbp+57h+arg_0], ax
0x18000ee1f  mov     [rbp+57h+var_50], rax
0x18000ee23  mov     rax, [rcx]
0x18000ee26  mov     rax, [rax+40h]
0x18000ee2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee2f  test    eax, eax
0x18000ee31  js      loc_18000EFE9
0x18000ee37  mov     rcx, [rbp+57h+var_40]
0x18000ee3b  lea     rdx, [rbp+57h+arg_0]
0x18000ee3f  mov     rax, [rcx]
0x18000ee42  mov     rax, [rax+38h]
0x18000ee46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee4b  test    eax, eax
0x18000ee4d  js      loc_18000EFF6
0x18000ee53  mov     rcx, [rbp+57h+var_40]
0x18000ee57  lea     rdx, [rbp+57h+var_50]
0x18000ee5b  mov     rax, [rcx]
0x18000ee5e  mov     rax, [rax+30h]
0x18000ee62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee67  test    eax, eax
0x18000ee69  js      loc_18000EFCF
0x18000ee6f  mov     rcx, [rbp+57h+var_40]
0x18000ee73  mov     rax, [rcx]
0x18000ee76  mov     rax, [rax+10h]
0x18000ee7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee7f  movzx   eax, [rbp+57h+arg_8]
0x18000ee83  mov     [rsi+2D0h], ax
0x18000ee8a  movzx   eax, [rbp+57h+arg_0]
0x18000ee8e  mov     [rsi+2D2h], ax
0x18000ee95  movzx   eax, word ptr [rbp+57h+var_50]
0x18000ee99  mov     [rsi+2D4h], ax
0x18000eea0  movzx   eax, word ptr [rbp+57h+var_50+2]
0x18000eea4  mov     [rsi+2D6h], ax
0x18000eeab  movzx   eax, word ptr [rbp+57h+var_50+4]
0x18000eeaf  mov     [rsi+2D8h], ax
0x18000eeb6  movzx   eax, word ptr [rbp+57h+var_50+6]
0x18000eeba  mov     [rsi+2DAh], ax
0x18000eec1  mov     eax, cs:dword_180069000
0x18000eec7  cmp     eax, 4
0x18000eeca  jbe     loc_18000EF9F
0x18000eed0  mov     rcx, cs:qword_180069018
0x18000eed7  mov     rax, cs:qword_180069010
0x18000eede  test    al, 8
0x18000eee0  jz      loc_18000EF9F
0x18000eee6  mov     rax, rcx
0x18000eee9  and     eax, 8
0x18000eeec  cmp     rax, rcx
0x18000eeef  jnz     loc_18000EF9F
0x18000eef5  movzx   eax, word ptr [rbp+57h+var_50+6]
0x18000eef9  lea     rdx, dword_18005D9AC
0x18000ef00  mov     [rbp+57h+arg_10], ax
0x18000ef04  movzx   eax, word ptr [rbp+57h+var_50+4]
0x18000ef08  mov     [rbp+57h+arg_18], ax
0x18000ef0c  movzx   eax, word ptr [rbp+57h+var_50+2]
0x18000ef10  mov     [rbp+57h+var_48], ax
0x18000ef14  movzx   eax, word ptr [rbp+57h+var_50]
0x18000ef18  mov     [rbp+57h+var_46], ax
0x18000ef1c  movzx   eax, [rbp+57h+arg_0]
0x18000ef20  mov     [rbp+57h+var_44], ax
0x18000ef24  movzx   eax, [rbp+57h+arg_8]
0x18000ef28  mov     [rbp+57h+var_42], ax
0x18000ef2c  lea     rax, aCreatedGipEffe; "Created GIP effect manager for device"
0x18000ef33  mov     [rbp+57h+var_30], rax
0x18000ef37  lea     rax, aOnecoreXboxGam_11; "onecore\\xbox\\gameinput\\feedback\\gip"...
0x18000ef3e  mov     [rbp+57h+var_28], rax
0x18000ef42  lea     rax, [rbp+57h+arg_10]
0x18000ef46  mov     [rsp+0C0h+var_60], rax
0x18000ef4b  lea     rax, [rbp+57h+arg_18]
0x18000ef4f  mov     [rsp+0C0h+var_68], rax
0x18000ef54  lea     rax, [rbp+57h+var_48]
0x18000ef58  mov     [rsp+0C0h+var_70], rax
0x18000ef5d  lea     rax, [rbp+57h+var_46]
0x18000ef61  mov     [rsp+0C0h+var_78], rax
0x18000ef66  lea     rax, [rbp+57h+var_44]
0x18000ef6a  mov     [rsp+0C0h+var_80], rax
0x18000ef6f  lea     rax, [rbp+57h+var_42]
0x18000ef73  mov     [rsp+0C0h+var_88], rax
0x18000ef78  lea     rax, [rbp+57h+var_30]
0x18000ef7c  mov     [rsp+0C0h+var_90], rax
0x18000ef81  lea     rax, [rbp+57h+var_38]
0x18000ef85  mov     [rsp+0C0h+var_98], rax
0x18000ef8a  lea     rax, [rbp+57h+var_28]
0x18000ef8e  mov     [rsp+0C0h+var_A0], rax
0x18000ef93  mov     [rbp+57h+var_38], 27h ; '''
0x18000ef9a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$01@@U3@U3@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$01@@55555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &)
0x18000ef9f  lea     rax, [rdi+280h]
0x18000efa6  cmp     rdi, rax
0x18000efa9  jz      short loc_18000EFBF
0x18000efab  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000efaf  mov     [rdi+8], ecx
0x18000efb2  mov     [rdi+18h], rcx
0x18000efb6  add     rdi, 28h ; '('
0x18000efba  cmp     rdi, rax
0x18000efbd  jnz     short loc_18000EFAF
0x18000efbf  mov     rax, rsi
0x18000efc2  add     rsp, 0A8h
0x18000efc9  pop     rdi
0x18000efca  pop     rsi
0x18000efcb  pop     rbx
0x18000efcc  pop     rbp
0x18000efcd  retn
0x18000efcf  mov     edx, 15h
0x18000efd4  mov     ecx, eax
0x18000efd6  call    GameInputFailFast
0x18000efdb  int     3; Trap to Debugger
0x18000efdc  mov     edx, 0Fh
0x18000efe1  mov     ecx, eax
0x18000efe3  call    GameInputFailFast
0x18000efe8  int     3; Trap to Debugger
0x18000efe9  mov     edx, 13h
0x18000efee  mov     ecx, eax
0x18000eff0  call    GameInputFailFast
0x18000eff5  int     3; Trap to Debugger
0x18000eff6  mov     edx, 14h
0x18000effb  mov     ecx, eax
0x18000effd  call    GameInputFailFast
```
