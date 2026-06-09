# CNetworkHandler::NetworkDeleted(_GUID)

- ea: `0x18000bde0`
- end: `0x18000be66`
- name: `?NetworkDeleted@CNetworkHandler@@UEAAJU_GUID@@@Z`
- size: `134`
- prototype: `__int64 __fastcall(CNetworkHandler *this, struct _GUID *, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000a644`
- `0x18000bde0`
- `0x18000e28c`
- `0x180013840`

## pseudocode

```c
__int64 __fastcall CNetworkHandler::NetworkDeleted(CNetworkHandler *this, struct _GUID *a2, __int64 a3)
{
  _QWORD *v3; // rcx
  __int128 v5; // [rsp+20h] [rbp-28h] BYREF

  v5 = (__int128)*a2;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, a3, &v5);
      v3 = WPP_GLOBAL_Control;
    }
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 0x20) != 0 )
      WPP_SF_(v3[2], 25, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x18000bde0  push    rbx
0x18000bde2  sub     rsp, 40h
0x18000bde6  mov     rax, cs:__security_cookie
0x18000bded  xor     rax, rsp
0x18000bdf0  mov     [rsp+48h+var_18], rax
0x18000bdf5  movups  xmm0, xmmword ptr [rdx]
0x18000bdf8  movdqu  [rsp+48h+var_28], xmm0
0x18000bdfe  mov     rcx, cs:WPP_GLOBAL_Control
0x18000be05  lea     rbx, WPP_GLOBAL_Control
0x18000be0c  cmp     rcx, rbx
0x18000be0f  jz      short loc_18000BE51
0x18000be11  test    byte ptr [rcx+1Ch], 20h
0x18000be15  jz      short loc_18000BE31
0x18000be17  mov     rcx, [rcx+10h]
0x18000be1b  lea     r9, [rsp+48h+var_28]
0x18000be20  mov     edx, 18h
0x18000be25  call    WPP_SF__guid_
0x18000be2a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000be31  cmp     rcx, rbx
0x18000be34  jz      short loc_18000BE51
0x18000be36  test    byte ptr [rcx+1Ch], 20h
0x18000be3a  jz      short loc_18000BE51
0x18000be3c  mov     rcx, [rcx+10h]
0x18000be40  lea     r8, WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids
0x18000be47  mov     edx, 19h
0x18000be4c  call    WPP_SF_
0x18000be51  xor     eax, eax
0x18000be53  mov     rcx, [rsp+48h+var_18]
0x18000be58  xor     rcx, rsp; StackCookie
0x18000be5b  call    __security_check_cookie
0x18000be60  add     rsp, 40h
0x18000be64  pop     rbx
0x18000be65  retn
```
