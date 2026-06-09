# Microsoft::Bluetooth::Profiles::MediaControl::Interface::MediaControlOperationHandler::UpdateMediaPlayer(void)

- ea: `0x18004e0cc`
- end: `0x18004e23c`
- name: `?UpdateMediaPlayer@MediaControlOperationHandler@Interface@MediaControl@Profiles@Bluetooth@Microsoft@@AEAAJXZ`
- size: `368`
- prototype: `__int64 __fastcall(Microsoft::Bluetooth::Profiles::MediaControl::Interface::MediaControlOperationHandler *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004cd40`
- `0x18004d9e0`
- `0x18004dbd0`

## callees

- `0x18000751c`
- `0x1800235bc`
- `0x180025ad0`
- `0x18004dca0`
- `0x18004e0cc`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e1ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e1ad`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Profiles::MediaControl::Interface::MediaControlOperationHandler::UpdateMediaPlayer(
        Microsoft::Bluetooth::Profiles::MediaControl::Interface::MediaControlOperationHandler *this)
{
  __int64 v2; // rcx
  int v3; // eax
  HSTRING v4; // r8
  unsigned int v5; // edi
  Microsoft::Bluetooth::Profiles::MediaControl::Interface *v7; // rcx
  unsigned __int16 *v8; // rdx
  HSTRING v9; // rax
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rcx
  int v13; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  Microsoft::Bluetooth::Profiles::MediaControl::Interface *v15; // [rsp+40h] [rbp+8h] BYREF

  v2 = *((_QWORD *)this + 9);
  v15 = 0;
  v3 = (*(__int64 (__fastcall **)(__int64, Microsoft::Bluetooth::Profiles::MediaControl::Interface **))(*(_QWORD *)v2 + 112LL))(
         v2,
         &v15);
  v5 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1DF,
      (unsigned int)"onecore\\drivers\\bluetooth\\profiles\\mcp\\bthavmediacontrollerbridge\\lib\\bthavmediacontrollerbridge.cpp",
      (const char *)(unsigned int)v3,
      v13);
    return v5;
  }
  v7 = v15;
  if ( v15 )
  {
    v8 = (unsigned __int16 *)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      goto LABEL_13;
    }
    WPP_SF_Sq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      34,
      (unsigned int)&WPP_f26752851b2d3f90d31187047271b4d2_Traceguids,
      (_DWORD)v15,
      (char)this);
  }
  else
  {
    v8 = (unsigned __int16 *)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      goto LABEL_13;
    }
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_f26752851b2d3f90d31187047271b4d2_Traceguids, this);
  }
  v7 = v15;
LABEL_13:
  if ( *((_QWORD *)this + 13) )
  {
    WindowsDeleteString(*((HSTRING *)this + 13));
    v7 = v15;
    *((_QWORD *)this + 13) = 0;
  }
  if ( v7
    && *(_WORD *)v7
    && (*((_BYTE *)this + 112) = 0,
        v9 = Microsoft::Bluetooth::Profiles::MediaControl::Interface::SessionAumidFromAppSourceId(v7, v8),
        *((_QWORD *)this + 13) = v9,
        (v4 = v9) != 0) )
  {
    v10 = (*(__int64 (__fastcall **)(_QWORD, HSTRING))(**((_QWORD **)this + 10) + 64LL))(*((_QWORD *)this + 10), v9);
    v11 = v10;
    if ( v10 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1FA,
        (unsigned int)"onecore\\drivers\\bluetooth\\profiles\\mcp\\bthavmediacontrollerbridge\\lib\\bthavmediacontrollerbridge.cpp",
        (const char *)(unsigned int)v10,
        v13);
      return v11;
    }
  }
  else
  {
    v12 = *((_QWORD *)this + 10);
    *((_DWORD *)this + 29) = 0;
    *((_BYTE *)this + 112) = 1;
    return (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, HSTRING))(*(_QWORD *)v12 + 48LL))(v12, v8, v4);
  }
}

```

## disassembly

```asm
0x18004e0cc  mov     r11, rsp
0x18004e0cf  mov     [r11+10h], rbx
0x18004e0d3  mov     [r11+18h], rsi
0x18004e0d7  push    rdi
0x18004e0d8  sub     rsp, 30h
0x18004e0dc  mov     rbx, rcx
0x18004e0df  lea     rdx, [r11+8]
0x18004e0e3  mov     rcx, [rcx+48h]
0x18004e0e7  xor     esi, esi
0x18004e0e9  mov     [r11+8], rsi
0x18004e0ed  mov     rax, [rcx]
0x18004e0f0  mov     rax, [rax+70h]
0x18004e0f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e0f9  mov     edi, eax
0x18004e0fb  test    eax, eax
0x18004e0fd  jns     short loc_18004E11F
0x18004e0ff  mov     rcx, [rsp+38h]; this
0x18004e104  lea     r8, aOnecoreDrivers_9; "onecore\\drivers\\bluetooth\\profiles\\"...
0x18004e10b  mov     r9d, eax; char *
0x18004e10e  mov     edx, 1DFh; void *
0x18004e113  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e118  mov     eax, edi
0x18004e11a  jmp     loc_18004E22C
0x18004e11f  mov     rcx, [rsp+38h+arg_0]
0x18004e124  test    rcx, rcx
0x18004e127  jz      short loc_18004E167
0x18004e129  mov     rax, cs:WPP_GLOBAL_Control
0x18004e130  lea     rdx, WPP_GLOBAL_Control
0x18004e137  cmp     rax, rdx
0x18004e13a  jz      short loc_18004E1A3
0x18004e13c  test    byte ptr [rax+1Ch], 1
0x18004e140  jz      short loc_18004E1A3
0x18004e142  cmp     byte ptr [rax+19h], 4
0x18004e146  jb      short loc_18004E1A3
0x18004e148  mov     r9, rcx
0x18004e14b  mov     qword ptr [rsp+38h+var_18], rbx
0x18004e150  mov     rcx, [rax+10h]
0x18004e154  lea     r8, WPP_f26752851b2d3f90d31187047271b4d2_Traceguids
0x18004e15b  mov     edx, 22h ; '"'
0x18004e160  call    WPP_SF_Sq
0x18004e165  jmp     short loc_18004E19E
0x18004e167  mov     rax, cs:WPP_GLOBAL_Control
0x18004e16e  lea     rdx, WPP_GLOBAL_Control
0x18004e175  cmp     rax, rdx
0x18004e178  jz      short loc_18004E1A3
0x18004e17a  test    byte ptr [rax+1Ch], 1
0x18004e17e  jz      short loc_18004E1A3
0x18004e180  cmp     byte ptr [rax+19h], 4
0x18004e184  jb      short loc_18004E1A3
0x18004e186  mov     rcx, [rax+10h]
0x18004e18a  lea     r8, WPP_f26752851b2d3f90d31187047271b4d2_Traceguids
0x18004e191  mov     edx, 23h ; '#'
0x18004e196  mov     r9, rbx
0x18004e199  call    WPP_SF_q
0x18004e19e  mov     rcx, [rsp+38h+arg_0]
0x18004e1a3  cmp     [rbx+68h], rsi
0x18004e1a7  jz      short loc_18004E1BC
0x18004e1a9  mov     rcx, [rbx+68h]; string
0x18004e1ad  call    cs:__imp_WindowsDeleteString
0x18004e1b3  mov     rcx, [rsp+38h+arg_0]; this
0x18004e1b8  mov     [rbx+68h], rsi
0x18004e1bc  test    rcx, rcx
0x18004e1bf  jz      short loc_18004E215
0x18004e1c1  cmp     [rcx], si
0x18004e1c4  jz      short loc_18004E215
0x18004e1c6  mov     [rbx+70h], sil
0x18004e1ca  call    ?SessionAumidFromAppSourceId@Interface@MediaControl@Profiles@Bluetooth@Microsoft@@YAPEAUHSTRING__@@PEAG@Z; Microsoft::Bluetooth::Profiles::MediaControl::Interface::SessionAumidFromAppSourceId(ushort *)
0x18004e1cf  mov     [rbx+68h], rax
0x18004e1d3  mov     r8, rax
0x18004e1d6  test    rax, rax
0x18004e1d9  jz      short loc_18004E215
0x18004e1db  mov     rcx, [rbx+50h]
0x18004e1df  mov     rdx, [rcx]
0x18004e1e2  mov     rax, [rdx+40h]
0x18004e1e6  mov     rdx, r8
0x18004e1e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e1ee  mov     ebx, eax
0x18004e1f0  test    eax, eax
0x18004e1f2  jns     short loc_18004E211
0x18004e1f4  mov     rcx, [rsp+38h]; this
0x18004e1f9  lea     r8, aOnecoreDrivers_9; "onecore\\drivers\\bluetooth\\profiles\\"...
0x18004e200  mov     r9d, eax; char *
0x18004e203  mov     edx, 1FAh; void *
0x18004e208  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e20d  mov     eax, ebx
0x18004e20f  jmp     short loc_18004E22C
0x18004e211  xor     eax, eax
0x18004e213  jmp     short loc_18004E22C
0x18004e215  mov     rcx, [rbx+50h]
0x18004e219  mov     [rbx+74h], esi
0x18004e21c  mov     byte ptr [rbx+70h], 1
0x18004e220  mov     rax, [rcx]
0x18004e223  mov     rax, [rax+30h]
0x18004e227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e22c  mov     rbx, [rsp+38h+arg_8]
0x18004e231  mov     rsi, [rsp+38h+arg_10]
0x18004e236  add     rsp, 30h
0x18004e23a  pop     rdi
0x18004e23b  retn
```
