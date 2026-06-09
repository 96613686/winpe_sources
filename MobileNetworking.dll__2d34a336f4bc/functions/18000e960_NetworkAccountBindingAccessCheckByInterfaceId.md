# NetworkAccountBindingAccessCheckByInterfaceId

- ea: `0x18000e960`
- end: `0x18000ea82`
- name: `NetworkAccountBindingAccessCheckByInterfaceId`
- size: `290`
- prototype: `__int64 __fastcall(GUID *rguid, __int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180005e30`
- `0x180009850`
- `0x18000a19a`
- `0x18000b6f4`
- `0x18000de30`
- `0x18000e6a0`
- `0x18000e960`
- `0x18000ea88`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000e9c5`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000e9c5`

## pseudocode

```c
__int64 __fastcall NetworkAccountBindingAccessCheckByInterfaceId(GUID *rguid, __int64 a2, __int64 a3)
{
  int NetworkAccountIdBoundToInterfaceId; // ebx
  OLECHAR sz[40]; // [rsp+20h] [rbp-278h] BYREF
  unsigned __int16 v7[264]; // [rsp+70h] [rbp-228h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, rguid);
  memset_0(sz, 0, sizeof(sz));
  NetworkAccountIdBoundToInterfaceId = StringFromGUID2(rguid, sz, 40);
  memset_0(v7, 0, 0x208u);
  if ( NetworkAccountIdBoundToInterfaceId >= 0 )
  {
    NetworkAccountIdBoundToInterfaceId = GetNetworkAccountIdBoundToInterfaceId(sz, 0x104u, v7);
    if ( NetworkAccountIdBoundToInterfaceId >= 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_bfb02dd78cf433073ae18b437e1fe663_Traceguids, v7);
      NetworkAccountIdBoundToInterfaceId = NetworkAccountBindingAccessCheck(v7);
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      &WPP_bfb02dd78cf433073ae18b437e1fe663_Traceguids,
      (unsigned int)NetworkAccountIdBoundToInterfaceId);
  return (unsigned int)NetworkAccountIdBoundToInterfaceId;
}

```

## disassembly

```asm
0x18000e960  mov     [rsp+arg_8], rbx
0x18000e965  push    rsi
0x18000e966  sub     rsp, 290h
0x18000e96d  mov     rax, cs:__security_cookie
0x18000e974  xor     rax, rsp
0x18000e977  mov     [rsp+298h+var_18], rax
0x18000e97f  mov     rbx, rcx
0x18000e982  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e989  lea     rsi, WPP_GLOBAL_Control
0x18000e990  cmp     rcx, rsi
0x18000e993  jz      short loc_18000E9A7
0x18000e995  test    byte ptr [rcx+1Ch], 10h
0x18000e999  jz      short loc_18000E9A7
0x18000e99b  mov     rcx, [rcx+10h]
0x18000e99f  mov     r9, rbx
0x18000e9a2  call    WPP_SF__guid_
0x18000e9a7  xor     edx, edx; Val
0x18000e9a9  lea     rcx, [rsp+298h+sz]; void *
0x18000e9ae  lea     r8d, [rdx+50h]; Size
0x18000e9b2  call    memset_0
0x18000e9b7  mov     r8d, 28h ; '('; cchMax
0x18000e9bd  lea     rdx, [rsp+298h+sz]; lpsz
0x18000e9c2  mov     rcx, rbx; rguid
0x18000e9c5  call    cs:__imp_StringFromGUID2
0x18000e9cb  xor     edx, edx; Val
0x18000e9cd  lea     rcx, [rsp+298h+var_228]; void *
0x18000e9d2  mov     r8d, 208h; Size
0x18000e9d8  mov     ebx, eax
0x18000e9da  call    memset_0
0x18000e9df  test    ebx, ebx
0x18000e9e1  js      short loc_18000EA35
0x18000e9e3  lea     r8, [rsp+298h+var_228]
0x18000e9e8  mov     edx, 104h
0x18000e9ed  lea     rcx, [rsp+298h+sz]; unsigned __int16 *
0x18000e9f2  call    GetNetworkAccountIdBoundToInterfaceId
0x18000e9f7  mov     ebx, eax
0x18000e9f9  test    eax, eax
0x18000e9fb  js      short loc_18000EA35
0x18000e9fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea04  cmp     rcx, rsi
0x18000ea07  jz      short loc_18000EA29
0x18000ea09  test    byte ptr [rcx+1Ch], 10h
0x18000ea0d  jz      short loc_18000EA29
0x18000ea0f  mov     rcx, [rcx+10h]
0x18000ea13  lea     r9, [rsp+298h+var_228]
0x18000ea18  mov     edx, 11h
0x18000ea1d  lea     r8, WPP_bfb02dd78cf433073ae18b437e1fe663_Traceguids
0x18000ea24  call    WPP_SF_S
0x18000ea29  lea     rcx, [rsp+298h+var_228]; unsigned __int16 *
0x18000ea2e  call    NetworkAccountBindingAccessCheck
0x18000ea33  mov     ebx, eax
0x18000ea35  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea3c  cmp     rcx, rsi
0x18000ea3f  jz      short loc_18000EA5F
0x18000ea41  test    byte ptr [rcx+1Ch], 10h
0x18000ea45  jz      short loc_18000EA5F
0x18000ea47  mov     rcx, [rcx+10h]
0x18000ea4b  lea     r8, WPP_bfb02dd78cf433073ae18b437e1fe663_Traceguids
0x18000ea52  mov     edx, 12h
0x18000ea57  mov     r9d, ebx
0x18000ea5a  call    WPP_SF_d
0x18000ea5f  mov     eax, ebx
0x18000ea61  mov     rcx, [rsp+298h+var_18]
0x18000ea69  xor     rcx, rsp; StackCookie
0x18000ea6c  call    __security_check_cookie
0x18000ea71  mov     rbx, [rsp+298h+arg_8]
0x18000ea79  add     rsp, 290h
0x18000ea80  pop     rsi
0x18000ea81  retn
```
