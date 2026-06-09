# AuthHostWebInstance::InitializeInputPanel(void)

- ea: `0x140007cd4`
- end: `0x140007e35`
- name: `?InitializeInputPanel@AuthHostWebInstance@@AEAAJXZ`
- size: `353`
- prototype: `__int64 __fastcall(AuthHostWebInstance *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140004ac0`

## callees

- `0x1400022e4`
- `0x140002c98`
- `0x140003a8c`
- `0x140007cd4`
- `0x140014010`

## import_xrefs

- `ext-ms-win-security-authbrokerui-l1-1-0!WabCreateWebRuntimeCoreVisualViewport` at `0x140007d02`
- `ext-ms-win-security-authbrokerui-l1-1-0!WabCreateWebRuntimeCoreVisualViewport` at `0x140007d02`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AuthHostWebInstance::InitializeInputPanel(
        __int64 (__fastcall ***this)(AuthHostWebInstance *, GUID *, __int64 *))
{
  int WebRuntimeCoreVisualViewport; // eax
  int v3; // ebx
  __int64 (__fastcall *v5)(AuthHostWebInstance *, GUID *, __int64 *); // rbx
  _QWORD *v6; // r10
  __int64 v7; // rdx
  __int64 v8; // [rsp+48h] [rbp+10h] BYREF

  if ( (unsigned __int8)IsWabCreateWebRuntimeCoreControlPresent() )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this + 12);
    WebRuntimeCoreVisualViewport = WabCreateWebRuntimeCoreVisualViewport(this + 12);
    v3 = WebRuntimeCoreVisualViewport;
    if ( WebRuntimeCoreVisualViewport < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          35,
          WPP_bfa95fea1b46398427ec08da96c2d59a_Traceguids,
          (unsigned int)WebRuntimeCoreVisualViewport);
      }
      return (unsigned int)v3;
    }
    v8 = 0;
    v5 = **this;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v8);
    v3 = v5((AuthHostWebInstance *)this, &GUID_5396d4ce_6bac_447a_9271_b233b6d4bc25, &v8);
    if ( v3 >= 0 )
    {
      v3 = (*((__int64 (__fastcall **)(__int64 (__fastcall **)(AuthHostWebInstance *, GUID *, __int64 *), __int64 (__fastcall **)(AuthHostWebInstance *, GUID *, __int64 *), __int64 (__fastcall **)(AuthHostWebInstance *, GUID *, __int64 *), __int64 (__fastcall **)(AuthHostWebInstance *, GUID *, __int64 *), __int64))*this[12]
            + 4))(
             this[12],
             this[10],
             this[8],
             this[9],
             v8);
      if ( v3 >= 0 )
        goto LABEL_14;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 65) < 2u )
      {
        goto LABEL_14;
      }
      v7 = 37;
    }
    else
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 65) < 2u )
      {
        goto LABEL_14;
      }
      v7 = 36;
    }
    WPP_SF_d(v6[7], v7, WPP_bfa95fea1b46398427ec08da96c2d59a_Traceguids, (unsigned int)v3);
LABEL_14:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v8);
    return (unsigned int)v3;
  }
  return 2147500033LL;
}

```

## disassembly

```asm
0x140007cd4  mov     [rsp+arg_0], rbx
0x140007cd9  mov     [rsp+arg_10], rsi
0x140007cde  push    rdi
0x140007cdf  sub     rsp, 30h
0x140007ce3  mov     rdi, rcx
0x140007ce6  call    IsWabCreateWebRuntimeCoreControlPresent
0x140007ceb  test    al, al
0x140007ced  jz      loc_140007E20
0x140007cf3  lea     rsi, [rdi+60h]
0x140007cf7  mov     rcx, rsi
0x140007cfa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140007cff  mov     rcx, rsi
0x140007d02  call    cs:__imp_WabCreateWebRuntimeCoreVisualViewport
0x140007d08  mov     ebx, eax
0x140007d0a  test    eax, eax
0x140007d0c  jns     short loc_140007D4E
0x140007d0e  lea     rcx, WPP_GLOBAL_Control
0x140007d15  mov     r10, cs:WPP_GLOBAL_Control
0x140007d1c  cmp     r10, rcx
0x140007d1f  jz      short loc_140007D47
0x140007d21  test    byte ptr [r10+44h], 2
0x140007d26  jz      short loc_140007D47
0x140007d28  cmp     byte ptr [r10+41h], 2
0x140007d2d  jb      short loc_140007D47
0x140007d2f  mov     edx, 23h ; '#'
0x140007d34  mov     r9d, eax
0x140007d37  lea     r8, WPP_bfa95fea1b46398427ec08da96c2d59a_Traceguids
0x140007d3e  mov     rcx, [r10+38h]
0x140007d42  call    WPP_SF_d
0x140007d47  mov     eax, ebx
0x140007d49  jmp     loc_140007E25
0x140007d4e  mov     [rsp+38h+arg_8], 0
0x140007d57  mov     rax, [rdi]
0x140007d5a  mov     rbx, [rax]
0x140007d5d  lea     rcx, [rsp+38h+arg_8]
0x140007d62  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140007d67  lea     r8, [rsp+38h+arg_8]
0x140007d6c  lea     rdx, _GUID_5396d4ce_6bac_447a_9271_b233b6d4bc25
0x140007d73  mov     rcx, rdi
0x140007d76  mov     rax, rbx
0x140007d79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007d7e  mov     ebx, eax
0x140007d80  test    eax, eax
0x140007d82  jns     short loc_140007DCD
0x140007d84  lea     rcx, WPP_GLOBAL_Control
0x140007d8b  mov     r10, cs:WPP_GLOBAL_Control
0x140007d92  cmp     r10, rcx
0x140007d95  jz      short loc_140007DBE
0x140007d97  test    byte ptr [r10+44h], 2
0x140007d9c  jz      short loc_140007DBE
0x140007d9e  cmp     byte ptr [r10+41h], 2
0x140007da3  jb      short loc_140007DBE
0x140007da5  mov     edx, 24h ; '$'
0x140007daa  mov     r9d, ebx
0x140007dad  lea     r8, WPP_bfa95fea1b46398427ec08da96c2d59a_Traceguids
0x140007db4  mov     rcx, [r10+38h]
0x140007db8  call    WPP_SF_d
0x140007dbd  nop
0x140007dbe  lea     rcx, [rsp+38h+arg_8]
0x140007dc3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140007dc8  jmp     loc_140007D47
0x140007dcd  mov     rcx, [rsi]
0x140007dd0  mov     rdx, [rsp+38h+arg_8]
0x140007dd5  mov     rax, [rcx]
0x140007dd8  mov     [rsp+38h+var_18], rdx
0x140007ddd  mov     r9, [rdi+48h]
0x140007de1  mov     r8, [rdi+40h]
0x140007de5  mov     rdx, [rdi+50h]
0x140007de9  mov     rax, [rax+20h]
0x140007ded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007df2  mov     ebx, eax
0x140007df4  test    eax, eax
0x140007df6  jns     short loc_140007DBE
0x140007df8  lea     rcx, WPP_GLOBAL_Control
0x140007dff  mov     r10, cs:WPP_GLOBAL_Control
0x140007e06  cmp     r10, rcx
0x140007e09  jz      short loc_140007DBE
0x140007e0b  test    byte ptr [r10+44h], 2
0x140007e10  jz      short loc_140007DBE
0x140007e12  cmp     byte ptr [r10+41h], 2
0x140007e17  jb      short loc_140007DBE
0x140007e19  mov     edx, 25h ; '%'
0x140007e1e  jmp     short loc_140007DAA
0x140007e20  mov     eax, 80004001h
0x140007e25  mov     rbx, [rsp+38h+arg_0]
0x140007e2a  mov     rsi, [rsp+38h+arg_10]
0x140007e2f  add     rsp, 30h
0x140007e33  pop     rdi
0x140007e34  retn
```
