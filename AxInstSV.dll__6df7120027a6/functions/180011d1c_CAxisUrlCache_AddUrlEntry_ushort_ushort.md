# CAxisUrlCache::AddUrlEntry(ushort *,ushort *)

- ea: `0x180011d1c`
- end: `0x180011e1b`
- name: `?AddUrlEntry@CAxisUrlCache@@QEAAJPEAG0@Z`
- size: `255`
- prototype: `__int64 __fastcall(CAxisUrlCache *this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005ee0`

## callees

- `0x1800017c0`
- `0x180002c00`
- `0x180005da4`
- `0x1800119a4`
- `0x180011cb0`
- `0x180011d1c`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180011dc8`
- `OLEAUT32!__imp_SysFreeString` at `0x180011dc8`
- `ntdll!RtlAcquireResourceExclusive` at `0x180011d5c`
- `ntdll!RtlAcquireResourceExclusive` at `0x180011d5c`
- `ntdll!RtlReleaseResource` at `0x180011dfe`
- `ntdll!RtlReleaseResource` at `0x180011dfe`

## pseudocode

```c
__int64 __fastcall CAxisUrlCache::AddUrlEntry(CAxisUrlCache *this, unsigned __int16 *a2, unsigned __int16 *a3)
{
  unsigned int v6; // ebx
  struct _RTL_RESOURCE *v7; // rsi
  OLECHAR *v8; // rax
  OLECHAR *v9; // rdi
  unsigned int v10; // edx
  BSTR bstrString[2]; // [rsp+20h] [rbp-58h] BYREF
  ATL::CAtlException *v13; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v14[64]; // [rsp+38h] [rbp-40h] BYREF
  struct _RTL_RESOURCE *v15; // [rsp+98h] [rbp+20h]

  v6 = -2147467259;
  if ( *((_DWORD *)this + 6) )
  {
    v7 = (struct _RTL_RESOURCE *)((char *)this + 32);
    v15 = (struct _RTL_RESOURCE *)((char *)this + 32);
    RtlAcquireResourceExclusive((PRTL_RESOURCE)((char *)this + 32), 1u);
    v8 = (OLECHAR *)operator new(8u, (const struct std::nothrow_t *)&std::nothrow);
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v9 = v8;
      bstrString[0] = v8;
      if ( v8 )
      {
        *(_QWORD *)v8 = 0;
        ATL::CComBSTR::operator=((BSTR *)v8, a3);
      }
      else
      {
        v9 = 0;
      }
      if ( v9 )
      {
        ((void (__stdcall *)(ATL::CComBSTR *, const unsigned __int16 *))ATL::CComBSTR::CComBSTR)(
          (ATL::CComBSTR *)bstrString,
          a2);
        bstrString[1] = v9;
        std::_Tree<std::_Tmap_traits<ATL::CComBSTR,CAxISUrlEntry *,AxISCaseInsensitiveLessThan,std::allocator<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>,0>>::_Emplace<std::pair<ATL::CComBSTR,CAxISUrlEntry *>>(
          (__int64 *)this + 1,
          (__int64)v14,
          (ATL::CComBSTR *)bstrString);
        SysFreeString(bstrString[0]);
        if ( v14[8] )
          v6 = 0;
        else
          CAxISUrlEntry::`scalar deleting destructor'((CAxISUrlEntry *)v9, v10);
      }
      else
      {
        v6 = -2147024882;
      }
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', &v13) )
      {
        v7 = v15;
        v6 = *(_DWORD *)v13;
        __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_180011DEC);
        goto LABEL_11;
      }
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        v7 = v15;
        v6 = -2147024882;
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180011DEA);
      }
    }
LABEL_11:
    RtlReleaseResource(v7);
  }
  return v6;
}

```

## disassembly

```asm
0x180011d1c  mov     rax, rsp
0x180011d1f  mov     [rax+10h], rbx
0x180011d23  push    rsi
0x180011d24  push    rdi
0x180011d25  push    r12
0x180011d27  push    r14
0x180011d29  push    r15
0x180011d2b  sub     rsp, 50h
0x180011d2f  mov     r15, r8
0x180011d32  mov     r12, rdx
0x180011d35  mov     r14, rcx
0x180011d38  mov     ebx, 80004005h
0x180011d3d  cmp     dword ptr [rcx+18h], 0
0x180011d41  jz      loc_180011E04
0x180011d47  lea     rsi, [rcx+20h]
0x180011d4b  mov     [rsp+78h+arg_18], rsi
0x180011d53  mov     [rax+8], rsi
0x180011d57  mov     dl, 1; Wait
0x180011d59  mov     rcx, rsi; Resource
0x180011d5c  call    cs:__imp_RtlAcquireResourceExclusive
0x180011d62  nop
0x180011d63  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180011d6a  mov     ecx, 8; unsigned __int64
0x180011d6f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180011d74  mov     rdi, rax
0x180011d77  mov     [rsp+78h+bstrString], rax
0x180011d7c  test    rax, rax
0x180011d7f  jz      short loc_180011D96
0x180011d81  mov     qword ptr [rax], 0
0x180011d88  mov     rdx, r15
0x180011d8b  mov     rcx, rax
0x180011d8e  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x180011d93  nop
0x180011d94  jmp     short loc_180011D98
0x180011d96  xor     edi, edi
0x180011d98  test    rdi, rdi
0x180011d9b  jz      short loc_180011DE3
0x180011d9d  mov     rdx, r12; unsigned __int16 *
0x180011da0  lea     rcx, [rsp+78h+bstrString]; this
0x180011da5  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180011daa  mov     [rsp+78h+var_50], rdi
0x180011daf  lea     rcx, [r14+8]
0x180011db3  lea     r8, [rsp+78h+bstrString]
0x180011db8  lea     rdx, [rsp+78h+var_40]
0x180011dbd  call    ??$_Emplace@U?$pair@VCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@PEAVCAxISUrlEntry@@UAxISCaseInsensitiveLessThan@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@@std@@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@VCComBSTR@ATL@@PEAVCAxISUrlEntry@@@1@@Z; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,CAxISUrlEntry *,AxISCaseInsensitiveLessThan,std::allocator<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>,0>>::_Emplace<std::pair<ATL::CComBSTR,CAxISUrlEntry *>>(std::pair<ATL::CComBSTR,CAxISUrlEntry *> &&)
0x180011dc2  nop
0x180011dc3  mov     rcx, [rsp+78h+bstrString]; bstrString
0x180011dc8  call    cs:__imp_SysFreeString
0x180011dce  cmp     [rsp+78h+var_38], 0
0x180011dd3  jnz     short loc_180011DDF
0x180011dd5  mov     rcx, rdi; this
0x180011dd8  call    ??_GCAxISUrlEntry@@QEAAPEAXI@Z; CAxISUrlEntry::`scalar deleting destructor'(uint)
0x180011ddd  jmp     short loc_180011DE8
0x180011ddf  xor     ebx, ebx
0x180011de1  jmp     short loc_180011DE8
0x180011de3  mov     ebx, 8007000Eh
0x180011de8  jmp     short loc_180011DFB
0x180011dea  jmp     short $+2
0x180011dec  mov     rsi, [rsp+78h+arg_18]
0x180011df4  mov     ebx, [rsp+78h+arg_0]
0x180011dfb  mov     rcx, rsi; Resource
0x180011dfe  call    cs:__imp_RtlReleaseResource
0x180011e04  mov     eax, ebx
0x180011e06  mov     rbx, [rsp+78h+arg_8]
0x180011e0e  add     rsp, 50h
0x180011e12  pop     r15
0x180011e14  pop     r14
0x180011e16  pop     r12
0x180011e18  pop     rdi
0x180011e19  pop     rsi
0x180011e1a  retn
```
