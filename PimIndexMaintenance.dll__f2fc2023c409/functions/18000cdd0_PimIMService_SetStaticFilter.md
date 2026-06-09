# PimIMService_SetStaticFilter

- ea: `0x18000cdd0`
- end: `0x18000ced5`
- name: `PimIMService_SetStaticFilter`
- size: `261`
- prototype: `__int64 __fastcall(int, int, int, int, void *Src)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800012fc`
- `0x180002da8`
- `0x180003c88`
- `0x180003d60`
- `0x180003f90`
- `0x18000cdd0`
- `0x1800211f2`
- `0x180022010`

## string_xrefs

- `0x18000ce26`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x18000ce82`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x18000cea1`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall PimIMService_SetStaticFilter(__int64 a1, __int64 a2, unsigned int a3, unsigned int a4, void *Src)
{
  void **v5; // rbx
  __int64 v6; // rdi
  _QWORD *v10; // rax
  void **v11; // rax
  unsigned int v12; // edi
  int v13; // eax

  v5 = 0;
  v6 = a4;
  if ( a4 )
  {
    v10 = operator new(0x18u);
    if ( !v10
      || (v11 = (void **)utl::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>(v10),
          (v5 = v11) == 0) )
    {
      v12 = -2147024882;
      Log_HREvent(
        2147942414LL,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
        3816);
      return v12;
    }
    if ( !(unsigned __int8)utl::vector<OLITEMID,utl::allocator<OLITEMID>>::_Resize<,0>(v11, (unsigned int)v6) )
    {
      v12 = -2147024882;
      Log_HREvent(
        2147942414LL,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
        3817);
LABEL_6:
      tlx::_delete<utl::vector<OLITEMID,utl::allocator<OLITEMID>>>(v5);
      return v12;
    }
    memcpy_0(*v5, Src, 12 * v6);
  }
  v13 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, void **))(*(_QWORD *)a1 + 32LL))(a1, a2, a3, v5);
  v12 = v13;
  if ( v13 < 0 )
  {
    Log_HREvent(
      (unsigned int)v13,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      3826);
    if ( !v5 )
      return v12;
    goto LABEL_6;
  }
  if ( v5 )
    tlx::_delete<utl::vector<OLITEMID,utl::allocator<OLITEMID>>>(v5);
  return 0;
}

```

## disassembly

```asm
0x18000cdd0  push    rbx
0x18000cdd2  push    rbp
0x18000cdd3  push    rsi
0x18000cdd4  push    rdi
0x18000cdd5  push    r14
0x18000cdd7  sub     rsp, 30h
0x18000cddb  xor     ebx, ebx
0x18000cddd  mov     edi, r9d
0x18000cde0  mov     ebp, r8d
0x18000cde3  mov     r14, rdx
0x18000cde6  mov     rsi, rcx
0x18000cde9  test    r9d, r9d
0x18000cdec  jz      short loc_18000CE5E
0x18000cdee  lea     ecx, [rbx+18h]; Size
0x18000cdf1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000cdf6  test    rax, rax
0x18000cdf9  jz      loc_18000CE9C
0x18000cdff  mov     rcx, rax
0x18000ce02  call    ??0?$vector@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@V?$allocator@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>(void)
0x18000ce07  mov     rbx, rax
0x18000ce0a  test    rax, rax
0x18000ce0d  jz      loc_18000CE9C
0x18000ce13  mov     edx, edi
0x18000ce15  mov     rcx, rax
0x18000ce18  call    ??$_Resize@$$V$0A@@?$vector@UOLITEMID@@V?$allocator@UOLITEMID@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<OLITEMID,utl::allocator<OLITEMID>>::_Resize<,0>(unsigned __int64)
0x18000ce1d  test    al, al
0x18000ce1f  jnz     short loc_18000CE46
0x18000ce21  mov     edi, 8007000Eh
0x18000ce26  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000ce2d  mov     ecx, edi
0x18000ce2f  mov     r9d, 0EE9h
0x18000ce35  xor     edx, edx
0x18000ce37  call    Log_HREvent
0x18000ce3c  mov     rcx, rbx; Block
0x18000ce3f  call    ??$_delete@V?$vector@UOLITEMID@@V?$allocator@UOLITEMID@@@utl@@@utl@@@tlx@@YAXPEAV?$vector@UOLITEMID@@V?$allocator@UOLITEMID@@@utl@@@utl@@@Z; tlx::_delete<utl::vector<OLITEMID,utl::allocator<OLITEMID>>>(utl::vector<OLITEMID,utl::allocator<OLITEMID>> *)
0x18000ce44  jmp     short loc_18000CEB7
0x18000ce46  mov     rdx, [rsp+58h+Src]; Src
0x18000ce4e  lea     r8, [rdi+rdi*2]
0x18000ce52  mov     rcx, [rbx]; void *
0x18000ce55  shl     r8, 2; Size
0x18000ce59  call    memcpy_0
0x18000ce5e  mov     rax, [rsi]
0x18000ce61  mov     r9, rbx
0x18000ce64  mov     r8d, ebp
0x18000ce67  mov     rdx, r14
0x18000ce6a  mov     rcx, rsi
0x18000ce6d  mov     rax, [rax+20h]
0x18000ce71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce76  mov     edi, eax
0x18000ce78  test    eax, eax
0x18000ce7a  jns     short loc_18000CEBB
0x18000ce7c  mov     r9d, 0EF2h
0x18000ce82  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000ce89  mov     edx, 1
0x18000ce8e  mov     ecx, eax
0x18000ce90  call    Log_HREvent
0x18000ce95  test    rbx, rbx
0x18000ce98  jz      short loc_18000CEB7
0x18000ce9a  jmp     short loc_18000CE3C
0x18000ce9c  mov     edi, 8007000Eh
0x18000cea1  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000cea8  mov     ecx, edi
0x18000ceaa  mov     r9d, 0EE8h
0x18000ceb0  xor     edx, edx
0x18000ceb2  call    Log_HREvent
0x18000ceb7  mov     eax, edi
0x18000ceb9  jmp     short loc_18000CECA
0x18000cebb  test    rbx, rbx
0x18000cebe  jz      short loc_18000CEC8
0x18000cec0  mov     rcx, rbx; Block
0x18000cec3  call    ??$_delete@V?$vector@UOLITEMID@@V?$allocator@UOLITEMID@@@utl@@@utl@@@tlx@@YAXPEAV?$vector@UOLITEMID@@V?$allocator@UOLITEMID@@@utl@@@utl@@@Z; tlx::_delete<utl::vector<OLITEMID,utl::allocator<OLITEMID>>>(utl::vector<OLITEMID,utl::allocator<OLITEMID>> *)
0x18000cec8  xor     eax, eax
0x18000ceca  add     rsp, 30h
0x18000cece  pop     r14
0x18000ced0  pop     rdi
0x18000ced1  pop     rsi
0x18000ced2  pop     rbp
0x18000ced3  pop     rbx
0x18000ced4  retn
```
