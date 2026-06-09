# ATL::CComObject<CPimcTablet>::~CComObject<CPimcTablet>(void)

- ea: `0x18000bddc`
- end: `0x18000bf4e`
- name: `??1?$CComObject@VCPimcTablet@@@ATL@@UEAA@XZ`
- size: `370`
- prototype: `__int64 __fastcall(CPimcTablet *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c110`

## callees

- `0x180007e24`
- `0x18000953c`
- `0x18000bddc`
- `0x18000e4a0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000be7c`
- `ole32!CoTaskMemFree` at `0x18000be92`
- `ole32!CoTaskMemFree` at `0x18000bea8`
- `ole32!CoTaskMemFree` at `0x18000bebe`
- `ole32!CoTaskMemFree` at `0x18000bec8`
- `ole32!CoTaskMemFree` at `0x18000be7c`
- `ole32!CoTaskMemFree` at `0x18000be92`
- `ole32!CoTaskMemFree` at `0x18000bea8`
- `ole32!CoTaskMemFree` at `0x18000bebe`
- `ole32!CoTaskMemFree` at `0x18000bec8`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall ATL::CComObject<CPimcTablet>::~CComObject<CPimcTablet>(CPimcTablet *this)
{
  _QWORD *v2; // rdi
  char *v3; // rcx
  _QWORD *v4; // rsi
  char *v5; // rcx
  LPVOID *v6; // rcx
  __int64 result; // rax
  char *v8; // [rsp+38h] [rbp+10h] BYREF

  *(_QWORD *)this = &ATL::CComObject<CPimcTablet>::`vftable';
  *((_DWORD *)this + 2) = -1073741823;
  v2 = (_QWORD *)((char *)this + 16);
  if ( *((_QWORD *)this + 2) )
  {
    v8 = 0;
    v8 = (char *)*v2;
    v3 = v8;
    *v2 = 0;
    if ( v3 )
      (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
  }
  v4 = (_QWORD *)((char *)this + 24);
  if ( *((_QWORD *)this + 3) )
  {
    v8 = 0;
    v8 = (char *)*v4;
    v5 = v8;
    *v4 = 0;
    if ( v5 )
      (*(void (__fastcall **)(char *))(*(_QWORD *)v5 + 16LL))(v5);
  }
  CPimcTablet::ReleaseCursorInfo(this);
  v6 = (LPVOID *)*((_QWORD *)this + 8);
  if ( v6 )
  {
    if ( v6[1] )
    {
      CoTaskMemFree(v6[1]);
      v6 = (LPVOID *)*((_QWORD *)this + 8);
    }
    if ( v6[3] )
    {
      CoTaskMemFree(v6[3]);
      v6 = (LPVOID *)*((_QWORD *)this + 8);
    }
    if ( v6[4] )
    {
      CoTaskMemFree(v6[4]);
      v6 = (LPVOID *)*((_QWORD *)this + 8);
    }
    if ( v6[5] )
    {
      CoTaskMemFree(v6[5]);
      v6 = (LPVOID *)*((_QWORD *)this + 8);
    }
    CoTaskMemFree(v6);
    *((_QWORD *)this + 8) = 0;
  }
  if ( *((_DWORD *)this + 8) )
  {
    LODWORD(v8) = *((_DWORD *)this + 8);
    ATL::CComGITPtr<ITabletContextP>::Revoke(&v8);
    ATL::CComGITPtr<ITabletContextP>::Revoke(&v8);
  }
  result = (*(__int64 (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  v8 = (char *)this + 24;
  if ( *v4 )
    result = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 16LL))(*v4);
  if ( *v2 )
    return (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 16LL))(*v2);
  return result;
}

```

## disassembly

```asm
0x18000bddc  mov     r11, rsp
0x18000bddf  mov     [r11+18h], rbx
0x18000bde3  mov     [r11+20h], rsi
0x18000bde7  mov     [r11+8], rcx
0x18000bdeb  push    rdi
0x18000bdec  sub     rsp, 20h
0x18000bdf0  mov     rbx, rcx
0x18000bdf3  lea     rax, ??_7?$CComObject@VCPimcTablet@@@ATL@@6B@; const ATL::CComObject<CPimcTablet>::`vftable'
0x18000bdfa  mov     [rcx], rax
0x18000bdfd  mov     dword ptr [rcx+8], 0C0000001h
0x18000be04  lea     rdi, [rcx+10h]
0x18000be08  cmp     qword ptr [rdi], 0
0x18000be0c  jz      short loc_18000BE31
0x18000be0e  and     qword ptr [r11+10h], 0
0x18000be13  mov     rcx, [rdi]
0x18000be16  mov     [rsp+28h+arg_8], rcx
0x18000be1b  and     qword ptr [rdi], 0
0x18000be1f  test    rcx, rcx
0x18000be22  jz      short loc_18000BE31
0x18000be24  mov     rax, [rcx]
0x18000be27  mov     rax, [rax+10h]
0x18000be2b  call    cs:__guard_dispatch_icall_fptr
0x18000be31  lea     rsi, [rbx+18h]
0x18000be35  cmp     qword ptr [rsi], 0
0x18000be39  jz      short loc_18000BE5F
0x18000be3b  and     [rsp+28h+arg_8], 0
0x18000be41  mov     rcx, [rsi]
0x18000be44  mov     [rsp+28h+arg_8], rcx
0x18000be49  and     qword ptr [rsi], 0
0x18000be4d  test    rcx, rcx
0x18000be50  jz      short loc_18000BE5F
0x18000be52  mov     rax, [rcx]
0x18000be55  mov     rax, [rax+10h]
0x18000be59  call    cs:__guard_dispatch_icall_fptr
0x18000be5f  mov     rcx, rbx; this
0x18000be62  call    ?ReleaseCursorInfo@CPimcTablet@@QEAAXXZ; CPimcTablet::ReleaseCursorInfo(void)
0x18000be67  mov     rcx, [rbx+40h]
0x18000be6b  test    rcx, rcx
0x18000be6e  jz      short loc_18000BED3
0x18000be70  mov     rax, [rcx+8]
0x18000be74  test    rax, rax
0x18000be77  jz      short loc_18000BE86
0x18000be79  mov     rcx, rax; pv
0x18000be7c  call    cs:__imp_CoTaskMemFree
0x18000be82  mov     rcx, [rbx+40h]
0x18000be86  mov     rax, [rcx+18h]
0x18000be8a  test    rax, rax
0x18000be8d  jz      short loc_18000BE9C
0x18000be8f  mov     rcx, rax; pv
0x18000be92  call    cs:__imp_CoTaskMemFree
0x18000be98  mov     rcx, [rbx+40h]
0x18000be9c  mov     rax, [rcx+20h]
0x18000bea0  test    rax, rax
0x18000bea3  jz      short loc_18000BEB2
0x18000bea5  mov     rcx, rax; pv
0x18000bea8  call    cs:__imp_CoTaskMemFree
0x18000beae  mov     rcx, [rbx+40h]
0x18000beb2  mov     rax, [rcx+28h]
0x18000beb6  test    rax, rax
0x18000beb9  jz      short loc_18000BEC8
0x18000bebb  mov     rcx, rax; pv
0x18000bebe  call    cs:__imp_CoTaskMemFree
0x18000bec4  mov     rcx, [rbx+40h]; pv
0x18000bec8  call    cs:__imp_CoTaskMemFree
0x18000bece  and     qword ptr [rbx+40h], 0
0x18000bed3  mov     eax, [rbx+20h]
0x18000bed6  test    eax, eax
0x18000bed8  jz      short loc_18000BEF3
0x18000beda  mov     dword ptr [rsp+28h+arg_8], eax
0x18000bede  lea     rcx, [rsp+28h+arg_8]
0x18000bee3  call    ?Revoke@?$CComGITPtr@UITabletContextP@@@ATL@@QEAAJXZ; ATL::CComGITPtr<ITabletContextP>::Revoke(void)
0x18000bee8  nop
0x18000bee9  lea     rcx, [rsp+28h+arg_8]
0x18000beee  call    ?Revoke@?$CComGITPtr@UITabletContextP@@@ATL@@QEAAJXZ; ATL::CComGITPtr<ITabletContextP>::Revoke(void)
0x18000bef3  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000befa  mov     rax, [rcx]
0x18000befd  mov     rax, [rax+10h]
0x18000bf01  call    cs:__guard_dispatch_icall_fptr
0x18000bf07  nop
0x18000bf08  mov     [rsp+28h+arg_8], rsi
0x18000bf0d  mov     rcx, [rsi]
0x18000bf10  test    rcx, rcx
0x18000bf13  jz      short loc_18000BF23
0x18000bf15  mov     rax, [rcx]
0x18000bf18  mov     rax, [rax+10h]
0x18000bf1c  call    cs:__guard_dispatch_icall_fptr
0x18000bf22  nop
0x18000bf23  mov     [rsp+28h+arg_0], rdi
0x18000bf28  mov     rcx, [rdi]
0x18000bf2b  test    rcx, rcx
0x18000bf2e  jz      short loc_18000BF3E
0x18000bf30  mov     rax, [rcx]
0x18000bf33  mov     rax, [rax+10h]
0x18000bf37  call    cs:__guard_dispatch_icall_fptr
0x18000bf3d  nop
0x18000bf3e  mov     rbx, [rsp+28h+arg_10]
0x18000bf43  mov     rsi, [rsp+28h+arg_18]
0x18000bf48  add     rsp, 20h
0x18000bf4c  pop     rdi
0x18000bf4d  retn
```
