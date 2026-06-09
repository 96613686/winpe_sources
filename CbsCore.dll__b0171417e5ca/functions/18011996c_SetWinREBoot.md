# SetWinREBoot

- ea: `0x18011996c`
- end: `0x180119b2b`
- name: `SetWinREBoot`
- size: `447`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180117dac`
- `0x180118418`

## callees

- `0x180010cc0`
- `0x1800aa1a4`
- `0x1800d3940`
- `0x1800eb920`
- `0x18011996c`

## import_xrefs

- `bcd!BcdOpenObject` at `0x180119a44`
- `bcd!BcdOpenObject` at `0x180119a44`
- `bcd!BcdCloseObject` at `0x180119a04`
- `bcd!BcdCloseObject` at `0x180119ae9`
- `bcd!BcdCloseObject` at `0x180119a04`
- `bcd!BcdCloseObject` at `0x180119ae9`
- `bcd!BcdSetElementData` at `0x180119a9e`
- `bcd!BcdSetElementData` at `0x180119a9e`
- `bcd!BcdOpenSystemStore` at `0x1801199b0`
- `bcd!BcdOpenSystemStore` at `0x1801199b0`
- `bcd!BcdDeleteElement` at `0x180119a6f`
- `bcd!BcdDeleteElement` at `0x180119a6f`

## pseudocode

```c
__int64 __fastcall SetWinREBoot(__int128 *a1)
{
  __int64 InitPointer; // rax
  int v3; // eax
  __int128 *v4; // rdx
  __int64 v5; // rdx
  unsigned int v6; // ebx
  __int64 v8; // rax
  __int64 v9; // rdx
  _QWORD v10[4]; // [rsp+20h] [rbp-60h] BYREF
  __int64 v11; // [rsp+40h] [rbp-40h] BYREF
  int v12; // [rsp+48h] [rbp-38h] BYREF
  void *v13; // [rsp+50h] [rbp-30h] BYREF
  __int128 v14; // [rsp+58h] [rbp-28h] BYREF
  __int64 v15; // [rsp+68h] [rbp-18h]
  const char *v16; // [rsp+70h] [rbp-10h]

  v12 = 0;
  v13 = 0;
  v11 = 0;
  InitPointer = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v13);
  v3 = BcdOpenSystemStore(InitPointer);
  if ( v3 < 0 )
  {
    v15 = 317;
LABEL_3:
    *(_QWORD *)&v14 = "onecore\\base\\wcp\\rtllib\\nativelib-transactions\\transactions.cpp";
    v4 = &v14;
    *((_QWORD *)&v14 + 1) = "SetWinREBoot";
    v16 = "Status";
LABEL_4:
    v6 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
           &v12,
           v4,
           (unsigned int)v3);
    if ( v11 )
    {
      BcdCloseObject(v11, v5);
      v11 = 0;
    }
    if ( v13 )
      CloseBcdStore(v13);
    return v6;
  }
  v8 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v11);
  v3 = BcdOpenObject(v13, &GUID_WINDOWS_BOOTMGR, v8);
  if ( v3 < 0 )
  {
    v15 = 325;
    goto LABEL_3;
  }
  if ( a1 )
  {
    v14 = *a1;
    v3 = BcdSetElementData(v11, 603979778, &v14, 16);
    if ( v3 < 0 )
    {
      v10[2] = 346;
      v10[0] = "onecore\\base\\wcp\\rtllib\\nativelib-transactions\\transactions.cpp";
      v4 = (__int128 *)v10;
      v10[1] = "SetWinREBoot";
      v10[3] = "Status";
      goto LABEL_4;
    }
  }
  else
  {
    v3 = BcdDeleteElement(v11, 603979778);
    if ( v3 < 0 )
    {
      v15 = 334;
      goto LABEL_3;
    }
  }
  if ( v11 )
  {
    BcdCloseObject(v11, v9);
    v11 = 0;
  }
  if ( v13 )
    CloseBcdStore(v13);
  return 0;
}

```

## disassembly

```asm
0x18011996c  mov     [rsp-8+arg_8], rbx
0x180119971  push    rbp
0x180119972  mov     rbp, rsp
0x180119975  sub     rsp, 80h
0x18011997c  mov     rax, cs:__security_cookie
0x180119983  xor     rax, rsp
0x180119986  mov     [rbp+var_8], rax
0x18011998a  mov     rbx, rcx
0x18011998d  mov     [rbp+var_38], 0
0x180119994  lea     rcx, [rbp+var_30]
0x180119998  mov     [rbp+var_30], 0
0x1801199a0  mov     [rbp+var_40], 0
0x1801199a8  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1801199ad  mov     rcx, rax
0x1801199b0  call    cs:__imp_BcdOpenSystemStore
0x1801199b7  nop     dword ptr [rax+rax+00h]
0x1801199bc  test    eax, eax
0x1801199be  jns     short loc_180119A2D
0x1801199c0  mov     [rbp+var_18], 13Dh
0x1801199c8  lea     rcx, aOnecoreBaseWcp_48; "onecore\\base\\wcp\\rtllib\\nativelib-t"...
0x1801199cf  mov     qword ptr [rbp+var_28], rcx
0x1801199d3  lea     rdx, [rbp+var_28]
0x1801199d7  lea     rcx, aSetwinreboot; "SetWinREBoot"
0x1801199de  mov     qword ptr [rbp+var_28+8], rcx
0x1801199e2  lea     rcx, aStatus_0; "Status"
0x1801199e9  mov     [rbp+var_10], rcx
0x1801199ed  mov     r8d, eax
0x1801199f0  lea     rcx, [rbp+var_38]
0x1801199f4  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1801199f9  mov     rcx, [rbp+var_40]
0x1801199fd  mov     ebx, eax
0x1801199ff  test    rcx, rcx
0x180119a02  jz      short loc_180119A18
0x180119a04  call    cs:__imp_BcdCloseObject
0x180119a0b  nop     dword ptr [rax+rax+00h]
0x180119a10  mov     [rbp+var_40], 0
0x180119a18  mov     rcx, [rbp+var_30]; void *
0x180119a1c  test    rcx, rcx
0x180119a1f  jz      short loc_180119A26
0x180119a21  call    ?CloseBcdStore@@YAXPEAX@Z; CloseBcdStore(void *)
0x180119a26  mov     eax, ebx
0x180119a28  jmp     loc_180119B0D
0x180119a2d  lea     rcx, [rbp+var_40]
0x180119a31  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x180119a36  mov     rcx, [rbp+var_30]
0x180119a3a  lea     rdx, GUID_WINDOWS_BOOTMGR
0x180119a41  mov     r8, rax
0x180119a44  call    cs:__imp_BcdOpenObject
0x180119a4b  nop     dword ptr [rax+rax+00h]
0x180119a50  test    eax, eax
0x180119a52  jns     short loc_180119A61
0x180119a54  mov     [rbp+var_18], 145h
0x180119a5c  jmp     loc_1801199C8
0x180119a61  mov     rcx, [rbp+var_40]
0x180119a65  mov     edx, 24000002h
0x180119a6a  test    rbx, rbx
0x180119a6d  jnz     short loc_180119A8C
0x180119a6f  call    cs:__imp_BcdDeleteElement
0x180119a76  nop     dword ptr [rax+rax+00h]
0x180119a7b  test    eax, eax
0x180119a7d  jns     short loc_180119AE0
0x180119a7f  mov     [rbp+var_18], 14Eh
0x180119a87  jmp     loc_1801199C8
0x180119a8c  movups  xmm0, xmmword ptr [rbx]
0x180119a8f  mov     r9d, 10h
0x180119a95  lea     r8, [rbp+var_28]
0x180119a99  movdqu  [rbp+var_28], xmm0
0x180119a9e  call    cs:__imp_BcdSetElementData
0x180119aa5  nop     dword ptr [rax+rax+00h]
0x180119aaa  test    eax, eax
0x180119aac  jns     short loc_180119AE0
0x180119aae  lea     rcx, aOnecoreBaseWcp_48; "onecore\\base\\wcp\\rtllib\\nativelib-t"...
0x180119ab5  mov     [rbp+var_50], 15Ah
0x180119abd  mov     [rbp+var_60], rcx
0x180119ac1  lea     rdx, [rbp+var_60]
0x180119ac5  lea     rcx, aSetwinreboot; "SetWinREBoot"
0x180119acc  mov     [rbp+var_58], rcx
0x180119ad0  lea     rcx, aStatus_0; "Status"
0x180119ad7  mov     [rbp+var_48], rcx
0x180119adb  jmp     loc_1801199ED
0x180119ae0  mov     rcx, [rbp+var_40]
0x180119ae4  test    rcx, rcx
0x180119ae7  jz      short loc_180119AFD
0x180119ae9  call    cs:__imp_BcdCloseObject
0x180119af0  nop     dword ptr [rax+rax+00h]
0x180119af5  mov     [rbp+var_40], 0
0x180119afd  mov     rcx, [rbp+var_30]; void *
0x180119b01  test    rcx, rcx
0x180119b04  jz      short loc_180119B0B
0x180119b06  call    ?CloseBcdStore@@YAXPEAX@Z; CloseBcdStore(void *)
0x180119b0b  xor     eax, eax
0x180119b0d  mov     rcx, [rbp+var_8]
0x180119b11  xor     rcx, rsp; StackCookie
0x180119b14  call    __security_check_cookie
0x180119b19  mov     rbx, [rsp+80h+arg_8]
0x180119b21  add     rsp, 80h
0x180119b28  pop     rbp
0x180119b29  retn
```
