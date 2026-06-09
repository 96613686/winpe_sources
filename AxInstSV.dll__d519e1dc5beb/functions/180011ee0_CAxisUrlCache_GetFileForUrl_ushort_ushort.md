# CAxisUrlCache::GetFileForUrl(ushort *,ushort * *)

- ea: `0x180011ee0`
- end: `0x180011fe0`
- name: `?GetFileForUrl@CAxisUrlCache@@QEAAJPEAGPEAPEAG@Z`
- size: `256`
- prototype: `int(CAxisUrlCache *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180006dd0`

## callees

- `0x180005da4`
- `0x180011b08`
- `0x180011bb8`
- `0x180011e24`
- `0x180011ee0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180011f78`
- `OLEAUT32!__imp_SysFreeString` at `0x180011f78`
- `OLEAUT32!__imp_SysStringLen` at `0x180011f0d`
- `OLEAUT32!__imp_SysStringLen` at `0x180011f0d`
- `ntdll!RtlReleaseResource` at `0x180011f8f`
- `ntdll!RtlReleaseResource` at `0x180011f8f`
- `ntdll!RtlAcquireResourceShared` at `0x180011f32`
- `ntdll!RtlAcquireResourceShared` at `0x180011f32`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAxisUrlCache::GetFileForUrl(CAxisUrlCache *this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  unsigned int v6; // ebx
  __int64 v7; // rdi
  __int64 v8; // rcx
  ATL::CComBSTR *v9; // rdi
  unsigned __int16 *v10; // rax
  _BYTE v12[16]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v13; // [rsp+30h] [rbp-28h]
  BSTR bstrString; // [rsp+60h] [rbp+8h] BYREF
  char *v15; // [rsp+78h] [rbp+20h]

  v6 = -2147023728;
  if ( *((_DWORD *)this + 6) )
  {
    if ( SysStringLen(a2) && a2 )
    {
      v15 = (char *)this + 32;
      RtlAcquireResourceShared((PRTL_RESOURCE)((char *)this + 32), 1u);
      ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, a2);
      std::_Tree<std::_Tmap_traits<ATL::CComBSTR,CAxISUrlEntry *,AxISCaseInsensitiveLessThan,std::allocator<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>,0>>::_Find_lower_bound<ATL::CComBSTR>(
        (char *)this + 8,
        v12);
      v7 = v13;
      if ( !(unsigned __int8)std::_Tree<std::_Tmap_traits<ATL::CComBSTR,CAxISUrlEntry *,AxISCaseInsensitiveLessThan,std::allocator<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>,0>>::_Lower_bound_duplicate<ATL::CComBSTR>(
                               v8,
                               v13,
                               &bstrString) )
        v7 = *((_QWORD *)this + 1);
      SysFreeString(bstrString);
      if ( v7 == *((_QWORD *)this + 1) )
        v9 = 0;
      else
        v9 = *(ATL::CComBSTR **)(v7 + 40);
      RtlReleaseResource((PRTL_RESOURCE)((char *)this + 32));
      if ( v9 )
      {
        if ( a3 )
        {
          v10 = ATL::CComBSTR::Copy(v9);
          *a3 = v10;
          if ( v10 || !*(_QWORD *)v9 )
            return 0;
          else
            return (unsigned int)-2147024882;
        }
        else
        {
          return (unsigned int)-2147467261;
        }
      }
    }
    else
    {
      return (unsigned int)-2147024809;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180011ee0  mov     [rsp+arg_8], rbx
0x180011ee5  mov     [rsp+arg_10], rbp
0x180011eea  push    rsi
0x180011eeb  push    rdi
0x180011eec  push    r14
0x180011eee  sub     rsp, 40h
0x180011ef2  mov     rsi, r8
0x180011ef5  mov     rdi, rdx
0x180011ef8  mov     r14, rcx
0x180011efb  mov     ebx, 80070490h
0x180011f00  cmp     dword ptr [rcx+18h], 0
0x180011f04  jz      loc_180011FCB
0x180011f0a  mov     rcx, rdx; pbstr
0x180011f0d  call    cs:__imp_SysStringLen
0x180011f13  test    eax, eax
0x180011f15  jz      loc_180011FC6
0x180011f1b  test    rdi, rdi
0x180011f1e  jz      loc_180011FC6
0x180011f24  lea     rbp, [r14+20h]
0x180011f28  mov     [rsp+58h+arg_18], rbp
0x180011f2d  mov     dl, 1; Wait
0x180011f2f  mov     rcx, rbp; Resource
0x180011f32  call    cs:__imp_RtlAcquireResourceShared
0x180011f38  nop
0x180011f39  mov     rdx, rdi; unsigned __int16 *
0x180011f3c  lea     rcx, [rsp+58h+bstrString]; this
0x180011f41  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180011f46  lea     r8, [rsp+58h+bstrString]
0x180011f4b  lea     rdx, [rsp+58h+var_38]
0x180011f50  lea     rcx, [r14+8]
0x180011f54  call    ??$_Find_lower_bound@VCComBSTR@ATL@@@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@PEAVCAxISUrlEntry@@UAxISCaseInsensitiveLessThan@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@std@@@1@AEBVCComBSTR@ATL@@@Z; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,CAxISUrlEntry *,AxISCaseInsensitiveLessThan,std::allocator<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>,0>>::_Find_lower_bound<ATL::CComBSTR>(ATL::CComBSTR const &)
0x180011f59  lea     r8, [rsp+58h+bstrString]
0x180011f5e  mov     rdi, [rsp+58h+var_28]
0x180011f63  mov     rdx, rdi
0x180011f66  call    ??$_Lower_bound_duplicate@VCComBSTR@ATL@@@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@PEAVCAxISUrlEntry@@UAxISCaseInsensitiveLessThan@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@@std@@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@1@AEBVCComBSTR@ATL@@@Z; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,CAxISUrlEntry *,AxISCaseInsensitiveLessThan,std::allocator<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>,0>>::_Lower_bound_duplicate<ATL::CComBSTR>(std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *> * const,ATL::CComBSTR const &)
0x180011f6b  test    al, al
0x180011f6d  jnz     short loc_180011F73
0x180011f6f  mov     rdi, [r14+8]
0x180011f73  mov     rcx, [rsp+58h+bstrString]; bstrString
0x180011f78  call    cs:__imp_SysFreeString
0x180011f7e  cmp     rdi, [r14+8]
0x180011f82  jnz     short loc_180011F88
0x180011f84  xor     edi, edi
0x180011f86  jmp     short loc_180011F8C
0x180011f88  mov     rdi, [rdi+28h]
0x180011f8c  mov     rcx, rbp; Resource
0x180011f8f  call    cs:__imp_RtlReleaseResource
0x180011f95  test    rdi, rdi
0x180011f98  jz      short loc_180011FCB
0x180011f9a  test    rsi, rsi
0x180011f9d  jnz     short loc_180011FA6
0x180011f9f  mov     ebx, 80004003h
0x180011fa4  jmp     short loc_180011FCB
0x180011fa6  mov     rcx, rdi; this
0x180011fa9  call    ?Copy@CComBSTR@ATL@@QEBAPEAGXZ; ATL::CComBSTR::Copy(void)
0x180011fae  mov     [rsi], rax
0x180011fb1  test    rax, rax
0x180011fb4  jnz     short loc_180011FC2
0x180011fb6  cmp     [rdi], rax
0x180011fb9  jz      short loc_180011FC2
0x180011fbb  mov     ebx, 8007000Eh
0x180011fc0  jmp     short loc_180011FCB
0x180011fc2  xor     ebx, ebx
0x180011fc4  jmp     short loc_180011FCB
0x180011fc6  mov     ebx, 80070057h
0x180011fcb  mov     eax, ebx
0x180011fcd  mov     rbx, [rsp+58h+arg_8]
0x180011fd2  mov     rbp, [rsp+58h+arg_10]
0x180011fd7  add     rsp, 40h
0x180011fdb  pop     r14
0x180011fdd  pop     rdi
0x180011fde  pop     rsi
0x180011fdf  retn
```
