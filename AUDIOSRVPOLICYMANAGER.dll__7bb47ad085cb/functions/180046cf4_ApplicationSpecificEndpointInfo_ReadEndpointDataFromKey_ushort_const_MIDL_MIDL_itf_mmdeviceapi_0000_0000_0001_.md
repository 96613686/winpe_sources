# ApplicationSpecificEndpointInfo::ReadEndpointDataFromKey(ushort const *,__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001 *,__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001 *)

- ea: `0x180046cf4`
- end: `0x180046f0f`
- name: `?ReadEndpointDataFromKey@ApplicationSpecificEndpointInfo@@CAJPEBGPEAW4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001@@PEAW4__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001@@@Z`
- size: `539`
- prototype: `__int64 __fastcall(const unsigned __int16 *, enum __MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001 *, enum __MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001 *)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x18001a134`

## callees

- `0x18000a384`
- `0x180011804`
- `0x180011c10`
- `0x1800128d4`
- `0x1800237d8`
- `0x18002bd9c`
- `0x18002c568`
- `0x18004627c`
- `0x18004633c`
- `0x180046a74`
- `0x180046afc`
- `0x180046cf4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180046dda`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180046e90`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180046dda`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180046e90`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180046d2c`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180046d2c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180046dc2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180046de2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180046e78`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180046e98`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180046dc2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180046de2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180046e78`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180046e98`

## pseudocode

```c
__int64 __fastcall ApplicationSpecificEndpointInfo::ReadEndpointDataFromKey(
        const unsigned __int16 *a1,
        enum __MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001 *a2,
        enum __MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001 *a3)
{
  wchar_t *v5; // rax
  __int64 v6; // rbx
  unsigned int v7; // edi
  __int64 Manager; // rax
  __int64 v9; // rdx
  __int64 Buffer; // rax
  unsigned int v11; // esi
  int v12; // edx
  wchar_t *v13; // rcx
  int v14; // edi
  int v15; // ebx
  ATL::Checked *v16; // rax
  unsigned int v17; // edi
  __int64 v18; // rax
  enum __MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001 v19; // ebx
  unsigned __int16 *v21[3]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+30h]
  wchar_t *Str; // [rsp+88h] [rbp+50h] BYREF

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &Str,
    a1);
  if ( *((int *)Str - 4) < 0 || (v5 = wcsstr(Str, L"_")) == 0 || (v6 = v5 - Str, (_DWORD)v6 == -1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A5,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\applicationspecificendpointinfo\\applicationspecificendpointinfo.cpp",
      (const char *)0x80070057LL,
      (int)v21[0]);
  }
  else
  {
    v7 = 0;
    if ( (int)v6 >= 0 )
      v7 = v5 - Str;
    if ( (signed int)v7 < *((_DWORD *)Str - 4) )
    {
      Manager = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetManager(&Str);
      ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(v21, Str, v7, Manager);
    }
    else
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        v21,
        &Str);
    }
    if ( ApplicationSpecificEndpointInfo::DoesStringRepresentAPositiveNumber(v21[0]) )
    {
      *(_DWORD *)_o__errno() = 0;
      Buffer = ATL::CSimpleStringT<unsigned short,0>::GetBuffer(v21);
      v11 = _o__wtoi(Buffer);
      if ( *(_DWORD *)_o__errno() )
      {
        v9 = 690;
      }
      else if ( v11 <= 5 )
      {
        v12 = 0;
        if ( (int)v6 + 1 >= 0 )
          v12 = v6 + 1;
        if ( 0x7FFFFFFF - v12 < 0 )
          ATL::AtlThrowImpl(-2147024809);
        v13 = Str;
        v14 = *((_DWORD *)Str - 4);
        v15 = v14;
        if ( v12 <= v14 )
          v15 = v12;
        if ( v15 > 0 )
        {
          v16 = (ATL::Checked *)ATL::CSimpleStringT<unsigned short,0>::GetBuffer(&Str);
          v17 = v14 - v15;
          ATL::Checked::memmove_s(
            v16,
            (void *)(2LL * (int)(v17 + 1)),
            (unsigned __int64)v16 + 2 * v15,
            (const void *)(2LL * (int)(v17 + 1)),
            (unsigned __int64)v21[0]);
          ATL::CSimpleStringT<unsigned short,0>::SetLength(&Str, v17);
          v13 = Str;
        }
        if ( ApplicationSpecificEndpointInfo::DoesStringRepresentAPositiveNumber(v13) )
        {
          *(_DWORD *)_o__errno() = 0;
          v18 = ATL::CSimpleStringT<unsigned short,0>::GetBuffer(&Str);
          v19 = (unsigned int)_o__wtoi(v18);
          if ( *(_DWORD *)_o__errno() )
          {
            v9 = 708;
          }
          else
          {
            if ( (unsigned int)v19 <= eCapture )
            {
              *a2 = v19;
              *(_DWORD *)a3 = v11;
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v21);
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&Str);
              return 0;
            }
            v9 = 711;
          }
        }
        else
        {
          v9 = 702;
        }
      }
      else
      {
        v9 = 693;
      }
    }
    else
    {
      v9 = 683;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\applicationspecificendpointinfo\\applicationspecificendpointinfo.cpp",
      (const char *)0x80070057LL,
      (int)v21[0]);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v21);
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&Str);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180046cf4  push    rbp
0x180046cf6  push    rbx
0x180046cf7  push    rsi
0x180046cf8  push    rdi
0x180046cf9  push    r14
0x180046cfb  push    r15
0x180046cfd  mov     rbp, rsp
0x180046d00  sub     rsp, 38h
0x180046d04  mov     r14, r8
0x180046d07  mov     r15, rdx
0x180046d0a  mov     rdx, rcx
0x180046d0d  lea     rcx, [rbp+Str]
0x180046d11  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180046d16  nop
0x180046d17  mov     rcx, [rbp+Str]; Str
0x180046d1b  cmp     dword ptr [rcx-10h], 0
0x180046d1f  jl      loc_180046ED9
0x180046d25  lea     rdx, SubStr; "_"
0x180046d2c  call    cs:__imp_wcsstr
0x180046d32  mov     rbx, rax
0x180046d35  test    rax, rax
0x180046d38  jz      loc_180046ED9
0x180046d3e  mov     rcx, [rbp+Str]
0x180046d42  sub     rbx, rcx
0x180046d45  sar     rbx, 1
0x180046d48  cmp     ebx, 0FFFFFFFFh
0x180046d4b  jz      loc_180046ED9
0x180046d51  xor     edi, edi
0x180046d53  test    ebx, ebx
0x180046d55  cmovns  edi, ebx
0x180046d58  cmp     edi, [rcx-10h]
0x180046d5b  jl      short loc_180046D6C
0x180046d5d  lea     rdx, [rbp+Str]
0x180046d61  lea     rcx, [rbp+var_18]
0x180046d65  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180046d6a  jmp     short loc_180046D89
0x180046d6c  lea     rcx, [rbp+Str]
0x180046d70  call    ?GetManager@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAPEAUIAtlStringMgr@2@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetManager(void)
0x180046d75  mov     r9, rax
0x180046d78  mov     r8d, edi
0x180046d7b  mov     rdx, [rbp+Str]
0x180046d7f  lea     rcx, [rbp+var_18]
0x180046d83  call    ??0?$CSimpleStringT@G$0A@@ATL@@QEAA@PEBGHPEAUIAtlStringMgr@1@@Z; ATL::CSimpleStringT<ushort,0>::CSimpleStringT<ushort,0>(ushort const *,int,ATL::IAtlStringMgr *)
0x180046d88  nop
0x180046d89  mov     rcx, [rbp+var_18]; unsigned __int16 *
0x180046d8d  call    ?DoesStringRepresentAPositiveNumber@ApplicationSpecificEndpointInfo@@CA_NPEBG@Z; ApplicationSpecificEndpointInfo::DoesStringRepresentAPositiveNumber(ushort const *)
0x180046d92  test    al, al
0x180046d94  jnz     short loc_180046DC2
0x180046d96  mov     edx, 2ABh; void *
0x180046d9b  mov     ebx, 80070057h
0x180046da0  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audiosrv\\ap"...
0x180046da7  mov     r9d, ebx; char *
0x180046daa  mov     rcx, [rbp+30h]; this
0x180046dae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046db3  nop
0x180046db4  lea     rcx, [rbp+var_18]
0x180046db8  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180046dbd  jmp     loc_180046EF7
0x180046dc2  call    cs:__imp__o__errno
0x180046dc8  mov     dword ptr [rax], 0
0x180046dce  lea     rcx, [rbp+var_18]
0x180046dd2  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x180046dd7  mov     rcx, rax
0x180046dda  call    cs:__imp__o__wtoi
0x180046de0  mov     esi, eax
0x180046de2  call    cs:__imp__o__errno
0x180046de8  cmp     dword ptr [rax], 0
0x180046deb  jz      short loc_180046DF4
0x180046ded  mov     edx, 2B2h
0x180046df2  jmp     short loc_180046D9B
0x180046df4  cmp     esi, 5
0x180046df7  jbe     short loc_180046E00
0x180046df9  mov     edx, 2B5h
0x180046dfe  jmp     short loc_180046D9B
0x180046e00  lea     eax, [rbx+1]
0x180046e03  xor     edx, edx
0x180046e05  test    eax, eax
0x180046e07  cmovns  edx, eax
0x180046e0a  mov     eax, 7FFFFFFFh
0x180046e0f  cmp     eax, edx
0x180046e11  jns     short loc_180046E1E
0x180046e13  mov     ecx, 80070057h; int
0x180046e18  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180046e1e  mov     rcx, [rbp+Str]
0x180046e22  mov     edi, [rcx-10h]
0x180046e25  mov     ebx, edi
0x180046e27  cmp     edx, edi
0x180046e29  cmovle  ebx, edx
0x180046e2c  test    ebx, ebx
0x180046e2e  jle     short loc_180046E65
0x180046e30  lea     rcx, [rbp+Str]
0x180046e34  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x180046e39  sub     edi, ebx
0x180046e3b  lea     ecx, [rdi+1]
0x180046e3e  movsxd  rdx, ecx
0x180046e41  add     rdx, rdx; void *
0x180046e44  movsxd  rcx, ebx
0x180046e47  lea     r8, [rax+rcx*2]; unsigned __int64
0x180046e4b  mov     r9, rdx; void *
0x180046e4e  mov     rcx, rax; this
0x180046e51  call    ?memmove_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memmove_s(void *,unsigned __int64,void const *,unsigned __int64)
0x180046e56  mov     edx, edi
0x180046e58  lea     rcx, [rbp+Str]
0x180046e5c  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x180046e61  mov     rcx, [rbp+Str]; unsigned __int16 *
0x180046e65  call    ?DoesStringRepresentAPositiveNumber@ApplicationSpecificEndpointInfo@@CA_NPEBG@Z; ApplicationSpecificEndpointInfo::DoesStringRepresentAPositiveNumber(ushort const *)
0x180046e6a  test    al, al
0x180046e6c  jnz     short loc_180046E78
0x180046e6e  mov     edx, 2BEh
0x180046e73  jmp     loc_180046D9B
0x180046e78  call    cs:__imp__o__errno
0x180046e7e  mov     dword ptr [rax], 0
0x180046e84  lea     rcx, [rbp+Str]
0x180046e88  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x180046e8d  mov     rcx, rax
0x180046e90  call    cs:__imp__o__wtoi
0x180046e96  mov     ebx, eax
0x180046e98  call    cs:__imp__o__errno
0x180046e9e  cmp     dword ptr [rax], 0
0x180046ea1  jz      short loc_180046EAD
0x180046ea3  mov     edx, 2C4h
0x180046ea8  jmp     loc_180046D9B
0x180046ead  cmp     ebx, 1
0x180046eb0  jbe     short loc_180046EBC
0x180046eb2  mov     edx, 2C7h
0x180046eb7  jmp     loc_180046D9B
0x180046ebc  mov     [r15], ebx
0x180046ebf  mov     [r14], esi
0x180046ec2  lea     rcx, [rbp+var_18]
0x180046ec6  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180046ecb  nop
0x180046ecc  lea     rcx, [rbp+Str]
0x180046ed0  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180046ed5  xor     eax, eax
0x180046ed7  jmp     short loc_180046F02
0x180046ed9  mov     rcx, [rbp+30h]; this
0x180046edd  mov     ebx, 80070057h
0x180046ee2  mov     r9d, ebx; char *
0x180046ee5  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audiosrv\\ap"...
0x180046eec  mov     edx, 2A5h; void *
0x180046ef1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046ef6  nop
0x180046ef7  lea     rcx, [rbp+Str]
0x180046efb  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180046f00  mov     eax, ebx
0x180046f02  add     rsp, 38h
0x180046f06  pop     r15
0x180046f08  pop     r14
0x180046f0a  pop     rdi
0x180046f0b  pop     rsi
0x180046f0c  pop     rbx
0x180046f0d  pop     rbp
0x180046f0e  retn
```
