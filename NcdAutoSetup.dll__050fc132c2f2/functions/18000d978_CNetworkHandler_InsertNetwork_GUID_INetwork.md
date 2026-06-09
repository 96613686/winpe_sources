# CNetworkHandler::_InsertNetwork(_GUID,INetwork *)

- ea: `0x18000d978`
- end: `0x18000dc7a`
- name: `?_InsertNetwork@CNetworkHandler@@AEAAJU_GUID@@PEAUINetwork@@@Z`
- size: `770`
- prototype: `__int64 __fastcall(CNetworkHandler *__hidden this, struct _GUID *__struct_ptr, struct INetwork *)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18000bc10`
- `0x18000be70`
- `0x18000c9ac`

## callees

- `0x18000a644`
- `0x18000a778`
- `0x18000d978`
- `0x18000dc80`
- `0x18000e28c`
- `0x180013840`
- `0x180014010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000dc54`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dc54`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x18000dac2`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x18000dac2`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x18000dad8`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x18000dad8`

## pseudocode

```c
__int64 __fastcall CNetworkHandler::_InsertNetwork(CNetworkHandler *this, struct _GUID *a2, struct INetwork *a3)
{
  struct INetworkVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetName)(INetwork *, BSTR *); // rax
  int inserted; // ebx
  _QWORD *v9; // r10
  __int64 v10; // rdx
  __int64 i; // rcx
  int v12; // eax
  __int64 v14; // [rsp+30h] [rbp-39h] BYREF
  ULONG InterfaceIndex; // [rsp+38h] [rbp-31h] BYREF
  __int64 v16; // [rsp+40h] [rbp-29h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-21h] BYREF
  NET_LUID InterfaceLuid; // [rsp+50h] [rbp-19h] BYREF
  struct _GUID v19; // [rsp+60h] [rbp-9h] BYREF
  GUID InterfaceGuid; // [rsp+70h] [rbp+7h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 132, a3, a2);
  lpVtbl = a3->lpVtbl;
  bstrString = 0;
  v16 = 0;
  InterfaceGuid = 0;
  GetName = lpVtbl->GetName;
  InterfaceLuid.Value = 0;
  InterfaceIndex = 0;
  inserted = ((__int64 (__fastcall *)(struct INetwork *, BSTR *))GetName)(a3, &bstrString);
  if ( inserted < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_42;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_39;
    v10 = 133;
    goto LABEL_37;
  }
  inserted = ((__int64 (__fastcall *)(struct INetwork *, __int64 *))a3->lpVtbl->GetNetworkConnections)(a3, &v16);
  if ( inserted >= 0 && v16 )
  {
    v14 = 0;
    inserted = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v16 + 64LL))(v16, 1, &v14);
    if ( inserted < 0 )
    {
LABEL_31:
      v9 = WPP_GLOBAL_Control;
LABEL_32:
      if ( !v14 )
        goto LABEL_39;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    else
    {
LABEL_11:
      for ( i = v14; i; i = 0 )
      {
        inserted = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)i + 96LL))(i, &InterfaceGuid);
        if ( inserted < 0 )
          goto LABEL_31;
        if ( ConvertInterfaceGuidToLuid(&InterfaceGuid, &InterfaceLuid) )
        {
          inserted = -2147467259;
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 135, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
            goto LABEL_31;
          }
          goto LABEL_32;
        }
        if ( ConvertInterfaceLuidToIndex(&InterfaceLuid, &InterfaceIndex) )
        {
          inserted = -2147467259;
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_32;
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 134, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
        }
        else
        {
          v19 = *a2;
          inserted = CNetworkHandler::_InsertNetworkConnection(this, &v19, InterfaceIndex, bstrString);
        }
        if ( inserted < 0 )
          goto LABEL_31;
        if ( v14 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
          v14 = 0;
        }
        v12 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v16 + 64LL))(v16, 1, &v14);
        inserted = v12;
        if ( v12 != 1 )
        {
          if ( v12 < 0 )
            goto LABEL_31;
          goto LABEL_11;
        }
        inserted = 0;
        if ( !v14 )
          goto LABEL_38;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        v14 = 0;
      }
    }
    goto LABEL_38;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_42;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v10 = 136;
LABEL_37:
    WPP_SF_d(v9[2], v10, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
LABEL_38:
    v9 = WPP_GLOBAL_Control;
  }
LABEL_39:
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x20) != 0 )
    WPP_SF_(v9[2], 137, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
LABEL_42:
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  SysFreeString(bstrString);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x18000d978  push    rbp
0x18000d97a  push    rbx
0x18000d97b  push    rsi
0x18000d97c  push    rdi
0x18000d97d  push    r12
0x18000d97f  push    r13
0x18000d981  push    r14
0x18000d983  lea     rbp, [rsp-27h]
0x18000d988  sub     rsp, 90h
0x18000d98f  mov     rax, cs:__security_cookie
0x18000d996  xor     rax, rsp
0x18000d999  mov     [rbp+57h+var_40], rax
0x18000d99d  mov     rdi, r8
0x18000d9a0  mov     rsi, rdx
0x18000d9a3  mov     r14, rcx
0x18000d9a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d9ad  lea     r12, WPP_GLOBAL_Control
0x18000d9b4  cmp     rcx, r12
0x18000d9b7  jz      short loc_18000D9D0
0x18000d9b9  test    byte ptr [rcx+1Ch], 20h
0x18000d9bd  jz      short loc_18000D9D0
0x18000d9bf  mov     rcx, [rcx+10h]
0x18000d9c3  mov     edx, 84h
0x18000d9c8  mov     r9, rsi
0x18000d9cb  call    WPP_SF__guid_
0x18000d9d0  mov     rax, [rdi]
0x18000d9d3  lea     rdx, [rbp+57h+bstrString]
0x18000d9d7  xorps   xmm0, xmm0
0x18000d9da  mov     [rbp+57h+bstrString], 0
0x18000d9e2  mov     rcx, rdi
0x18000d9e5  mov     [rbp+57h+var_80], 0
0x18000d9ed  movups  xmmword ptr [rbp+57h+InterfaceGuid.Data1], xmm0
0x18000d9f1  mov     rax, [rax+38h]
0x18000d9f5  mov     qword ptr [rbp+57h+InterfaceLuid], 0
0x18000d9fd  mov     [rbp+57h+InterfaceIndex], 0
0x18000da04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da09  lea     r13, WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids
0x18000da10  mov     ebx, eax
0x18000da12  test    eax, eax
0x18000da14  jns     short loc_18000DA3B
0x18000da16  mov     r10, cs:WPP_GLOBAL_Control
0x18000da1d  cmp     r10, r12
0x18000da20  jz      loc_18000DC3B
0x18000da26  test    byte ptr [r10+1Ch], 2
0x18000da2b  jz      loc_18000DC1E
0x18000da31  mov     edx, 85h
0x18000da36  jmp     loc_18000DC08
0x18000da3b  mov     rax, [rdi]
0x18000da3e  lea     rdx, [rbp+57h+var_80]
0x18000da42  mov     rcx, rdi
0x18000da45  mov     rax, [rax+68h]
0x18000da49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da4e  mov     ebx, eax
0x18000da50  test    eax, eax
0x18000da52  js      loc_18000DBF0
0x18000da58  mov     rcx, [rbp+57h+var_80]
0x18000da5c  test    rcx, rcx
0x18000da5f  jz      loc_18000DBF0
0x18000da65  mov     [rbp+57h+var_90], 0
0x18000da6d  lea     r8, [rbp+57h+var_90]
0x18000da71  mov     rax, [rcx]
0x18000da74  xor     r9d, r9d
0x18000da77  mov     rax, [rax+40h]
0x18000da7b  lea     edx, [r9+1]
0x18000da7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da84  mov     ebx, eax
0x18000da86  test    eax, eax
0x18000da88  js      loc_18000DBD2
0x18000da8e  mov     edi, 80004005h
0x18000da93  mov     rcx, [rbp+57h+var_90]
0x18000da97  test    rcx, rcx
0x18000da9a  jz      loc_18000DC17
0x18000daa0  mov     rax, [rcx]
0x18000daa3  lea     rdx, [rbp+57h+InterfaceGuid]
0x18000daa7  mov     rax, [rax+60h]
0x18000daab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dab0  mov     ebx, eax
0x18000dab2  test    eax, eax
0x18000dab4  js      loc_18000DBD2
0x18000daba  lea     rdx, [rbp+57h+InterfaceLuid]; InterfaceLuid
0x18000dabe  lea     rcx, [rbp+57h+InterfaceGuid]; InterfaceGuid
0x18000dac2  call    cs:__imp_ConvertInterfaceGuidToLuid
0x18000dac8  test    eax, eax
0x18000daca  jnz     loc_18000DBA9
0x18000dad0  lea     rdx, [rbp+57h+InterfaceIndex]; InterfaceIndex
0x18000dad4  lea     rcx, [rbp+57h+InterfaceLuid]; InterfaceLuid
0x18000dad8  call    cs:__imp_ConvertInterfaceLuidToIndex
0x18000dade  test    eax, eax
0x18000dae0  jnz     short loc_18000DB02
0x18000dae2  movaps  xmm0, xmmword ptr [rsi]
0x18000dae5  lea     rdx, [rbp+57h+var_60]; struct _GUID
0x18000dae9  mov     r9, [rbp+57h+bstrString]; unsigned __int16 *
0x18000daed  mov     rcx, r14; this
0x18000daf0  mov     r8d, [rbp+57h+InterfaceIndex]; unsigned int
0x18000daf4  movdqa  xmmword ptr [rbp+57h+var_60.Data1], xmm0
0x18000daf9  call    ?_InsertNetworkConnection@CNetworkHandler@@AEAAJU_GUID@@KPEAG@Z; CNetworkHandler::_InsertNetworkConnection(_GUID,ulong,ushort *)
0x18000dafe  mov     ebx, eax
0x18000db00  jmp     short loc_18000DB33
0x18000db02  mov     ebx, edi
0x18000db04  mov     r10, cs:WPP_GLOBAL_Control
0x18000db0b  cmp     r10, r12
0x18000db0e  jz      loc_18000DBD9
0x18000db14  test    byte ptr [r10+1Ch], 2
0x18000db19  jz      loc_18000DBD9
0x18000db1f  mov     rcx, [r10+10h]
0x18000db23  mov     edx, 86h
0x18000db28  mov     r9d, edi
0x18000db2b  mov     r8, r13
0x18000db2e  call    WPP_SF_d
0x18000db33  test    ebx, ebx
0x18000db35  js      loc_18000DBD2
0x18000db3b  mov     rcx, [rbp+57h+var_90]
0x18000db3f  test    rcx, rcx
0x18000db42  jz      short loc_18000DB58
0x18000db44  mov     rax, [rcx]
0x18000db47  mov     rax, [rax+10h]
0x18000db4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db50  mov     [rbp+57h+var_90], 0
0x18000db58  mov     rcx, [rbp+57h+var_80]
0x18000db5c  lea     r8, [rbp+57h+var_90]
0x18000db60  xor     r9d, r9d
0x18000db63  mov     rax, [rcx]
0x18000db66  lea     edx, [r9+1]
0x18000db6a  mov     rax, [rax+40h]
0x18000db6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db73  mov     ebx, eax
0x18000db75  cmp     eax, 1
0x18000db78  jnz     short loc_18000DBA0
0x18000db7a  mov     rcx, [rbp+57h+var_90]
0x18000db7e  xor     ebx, ebx
0x18000db80  test    rcx, rcx
0x18000db83  jz      loc_18000DC17
0x18000db89  mov     rax, [rcx]
0x18000db8c  mov     rax, [rax+10h]
0x18000db90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db95  xor     ecx, ecx
0x18000db97  mov     [rbp+57h+var_90], rcx
0x18000db9b  jmp     loc_18000DA97
0x18000dba0  test    eax, eax
0x18000dba2  js      short loc_18000DBD2
0x18000dba4  jmp     loc_18000DA93
0x18000dba9  mov     ebx, edi
0x18000dbab  mov     r10, cs:WPP_GLOBAL_Control
0x18000dbb2  cmp     r10, r12
0x18000dbb5  jz      short loc_18000DBD9
0x18000dbb7  test    byte ptr [r10+1Ch], 2
0x18000dbbc  jz      short loc_18000DBD9
0x18000dbbe  mov     rcx, [r10+10h]
0x18000dbc2  mov     edx, 87h
0x18000dbc7  mov     r9d, edi
0x18000dbca  mov     r8, r13
0x18000dbcd  call    WPP_SF_d
0x18000dbd2  mov     r10, cs:WPP_GLOBAL_Control
0x18000dbd9  mov     rcx, [rbp+57h+var_90]
0x18000dbdd  test    rcx, rcx
0x18000dbe0  jz      short loc_18000DC1E
0x18000dbe2  mov     rax, [rcx]
0x18000dbe5  mov     rax, [rax+10h]
0x18000dbe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbee  jmp     short loc_18000DC17
0x18000dbf0  mov     r10, cs:WPP_GLOBAL_Control
0x18000dbf7  cmp     r10, r12
0x18000dbfa  jz      short loc_18000DC3B
0x18000dbfc  test    byte ptr [r10+1Ch], 2
0x18000dc01  jz      short loc_18000DC1E
0x18000dc03  mov     edx, 88h
0x18000dc08  mov     rcx, [r10+10h]
0x18000dc0c  mov     r9d, eax
0x18000dc0f  mov     r8, r13
0x18000dc12  call    WPP_SF_d
0x18000dc17  mov     r10, cs:WPP_GLOBAL_Control
0x18000dc1e  cmp     r10, r12
0x18000dc21  jz      short loc_18000DC3B
0x18000dc23  test    byte ptr [r10+1Ch], 20h
0x18000dc28  jz      short loc_18000DC3B
0x18000dc2a  mov     rcx, [r10+10h]
0x18000dc2e  mov     edx, 89h
0x18000dc33  mov     r8, r13
0x18000dc36  call    WPP_SF_
0x18000dc3b  mov     rcx, [rbp+57h+var_80]
0x18000dc3f  test    rcx, rcx
0x18000dc42  jz      short loc_18000DC50
0x18000dc44  mov     rax, [rcx]
0x18000dc47  mov     rax, [rax+10h]
0x18000dc4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc50  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18000dc54  call    cs:__imp_SysFreeString
0x18000dc5a  mov     eax, ebx
0x18000dc5c  mov     rcx, [rbp+57h+var_40]
0x18000dc60  xor     rcx, rsp; StackCookie
0x18000dc63  call    __security_check_cookie
0x18000dc68  add     rsp, 90h
0x18000dc6f  pop     r14
0x18000dc71  pop     r13
0x18000dc73  pop     r12
0x18000dc75  pop     rdi
0x18000dc76  pop     rsi
0x18000dc77  pop     rbx
0x18000dc78  pop     rbp
0x18000dc79  retn
```
