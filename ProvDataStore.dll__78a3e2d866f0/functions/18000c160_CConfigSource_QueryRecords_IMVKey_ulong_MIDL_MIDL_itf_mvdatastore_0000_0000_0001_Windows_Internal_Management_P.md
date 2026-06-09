# CConfigSource::QueryRecords(IMVKey * *,ulong,__MIDL___MIDL_itf_mvdatastore_0000_0000_0001,Windows::Internal::Management::Provisioning::IProvisioningFileManager *,std::vector<std::shared_ptr<CConfigSet>,std::allocator<std::shared_ptr<CConfigSet>>> &)

- ea: `0x18000c160`
- end: `0x18000c225`
- name: `?QueryRecords@CConfigSource@@QEAAJPEAPEAUIMVKey@@KW4__MIDL___MIDL_itf_mvdatastore_0000_0000_0001@@PEAVIProvisioningFileManager@Provisioning@Management@Internal@Windows@@AEAV?$vector@V?$shared_ptr@VCConfigSet@@@std@@V?$allocator@V?$shared_ptr@VCConfigSet@@@std@@@2@@std@@@Z`
- size: `197`
- prototype: `__int64 __fastcall(__int64, int, int, int, _QWORD *, __int64 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180009aa0`
- `0x180009bd0`

## callees

- `0x18000a2e4`
- `0x18000c160`
- `0x18000dd4c`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CConfigSource::QueryRecords(__int64 a1, int a2, int a3, int a4, _QWORD *a5, __int64 *a6)
{
  int v10; // eax
  const char *v11; // r9
  unsigned int v12; // ebx
  __int64 result; // rax
  int v14; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *(_DWORD *)(a1 + 1044) = 0;
  try
  {
    (*(void (**)(void))(*a5 + 8LL))();
    v10 = CConfigSource::ParseSourceDatastore(a1, (__int64)a5, a2, a3, a4, a6);
    v12 = v10;
    if ( v10 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x149,
        (int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\sourcedatastore.cpp",
        (const char *)(unsigned int)v10,
        v14);
    if ( a5 )
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*a5 + 16LL))(a5, *a5);
    result = v12;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x14C,
                           (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\sourcedatastore.cpp",
                           v11);
  }
  return result;
}

```

## disassembly

```asm
0x18000c160  mov     r11, rsp
0x18000c163  push    rbx
0x18000c164  push    rsi
0x18000c165  push    rdi
0x18000c166  push    r14
0x18000c168  sub     rsp, 38h
0x18000c16c  mov     edi, r9d
0x18000c16f  mov     esi, r8d
0x18000c172  mov     r14, rdx
0x18000c175  mov     rbx, rcx
0x18000c178  mov     dword ptr [rcx+414h], 0
0x18000c182  mov     rcx, [rsp+58h+arg_20]
0x18000c18a  mov     rax, [rcx]
0x18000c18d  lea     r8, [rbx+20Ch]
0x18000c194  lea     rdx, [r11+28h]
0x18000c198  mov     rax, [rax+8]
0x18000c19c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1a1  nop
0x18000c1a2  mov     rax, [rsp+58h+arg_28]
0x18000c1aa  mov     [rsp+58h+var_30], rax
0x18000c1af  mov     [rsp+58h+var_38], edi; int
0x18000c1b3  mov     r9d, esi
0x18000c1b6  mov     r8, r14
0x18000c1b9  mov     rdx, [rsp+58h+arg_20]
0x18000c1c1  mov     rcx, rbx
0x18000c1c4  call    ?ParseSourceDatastore@CConfigSource@@QEAAJPEAUIStream@@PEAPEAUIMVKey@@KW4__MIDL___MIDL_itf_mvdatastore_0000_0000_0001@@AEAV?$vector@V?$shared_ptr@VCConfigSet@@@std@@V?$allocator@V?$shared_ptr@VCConfigSet@@@std@@@2@@std@@@Z; CConfigSource::ParseSourceDatastore(IStream *,IMVKey * *,ulong,__MIDL___MIDL_itf_mvdatastore_0000_0000_0001,std::vector<std::shared_ptr<CConfigSet>> &)
0x18000c1c9  mov     ebx, eax
0x18000c1cb  mov     rcx, [rsp+58h]; this
0x18000c1d0  test    eax, eax
0x18000c1d2  js      short loc_18000C20F
0x18000c1d4  mov     rcx, [rsp+58h+arg_20]
0x18000c1dc  test    rcx, rcx
0x18000c1df  jz      short loc_18000C1FA
0x18000c1e1  mov     [rsp+58h+arg_20], 0
0x18000c1ed  mov     rdx, [rcx]
0x18000c1f0  mov     rax, [rdx+10h]
0x18000c1f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1f9  nop
0x18000c1fa  mov     eax, ebx
0x18000c1fc  jmp     short loc_18000C205
0x18000c1fe  mov     eax, dword ptr [rsp+58h+arg_20]
0x18000c205  add     rsp, 38h
0x18000c209  pop     r14
0x18000c20b  pop     rdi
0x18000c20c  pop     rsi
0x18000c20d  pop     rbx
0x18000c20e  retn
0x18000c20f  mov     r9d, eax; char *
0x18000c212  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000c219  mov     edx, 149h; void *
0x18000c21e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
