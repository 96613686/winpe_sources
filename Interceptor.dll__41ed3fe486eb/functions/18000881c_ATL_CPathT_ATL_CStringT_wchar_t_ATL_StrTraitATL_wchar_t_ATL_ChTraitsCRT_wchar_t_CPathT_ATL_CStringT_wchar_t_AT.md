# ATL::CPathT<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>::CPathT<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>(wchar_t const *)

- ea: `0x18000881c`
- end: `0x18000891f`
- name: `??0?$CPathT@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@ATL@@QEAA@PEB_W@Z`
- size: `259`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800076b0`

## callees

- `0x180001a14`
- `0x180006d14`
- `0x18000881c`
- `0x180009020`
- `0x180009918`
- `0x180009be0`
- `0x180025bd0`
- `0x18002b3c0`

## import_xrefs

- `KERNEL32!FindResourceExW` at `0x1800088a5`
- `KERNEL32!FindResourceExW` at `0x1800088a5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall ATL::CPathT<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>::CPathT<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>(
        _QWORD *a1,
        __int64 a2)
{
  struct ATL::IAtlStringMgr *Instance; // rax
  unsigned int v5; // esi
  HINSTANCE HInstanceAt; // rbx
  int v7; // ebp
  HRSRC Resource; // rax
  int v9; // edx

  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance )
    ATL::AtlThrowImpl(-2147467259);
  *a1 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance) + 24;
  if ( (unsigned __int64)(a2 - 1) > 0xFFFE )
  {
    ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator=(a1, a2);
  }
  else
  {
    v5 = (unsigned __int16)a2;
    HInstanceAt = ATL::CAtlBaseModule::GetHInstanceAt((ATL::CAtlBaseModule *)ATL::_AtlBaseModule, 0);
    v7 = 1;
    if ( HInstanceAt )
    {
      while ( 1 )
      {
        Resource = FindResourceExW(HInstanceAt, (LPCWSTR)6, (LPCWSTR)(((unsigned __int64)v5 >> 4) + 1), 0);
        if ( Resource )
          Resource = (HRSRC)ATL::_AtlGetStringResourceImage(HInstanceAt, Resource, v5);
        if ( Resource )
          break;
        v9 = v7++;
        HInstanceAt = ATL::CAtlBaseModule::GetHInstanceAt((ATL::CAtlBaseModule *)ATL::_AtlBaseModule, v9);
        if ( !HInstanceAt )
          goto LABEL_8;
      }
    }
    else
    {
LABEL_8:
      HInstanceAt = 0;
    }
    if ( HInstanceAt )
      ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::LoadStringW(a1, HInstanceAt, v5);
  }
  return a1;
}

```

## disassembly

```asm
0x18000881c  mov     rax, rsp
0x18000881f  mov     [rax+10h], rbx
0x180008823  mov     [rax+18h], rbp
0x180008827  mov     [rax+8], rcx
0x18000882b  push    rsi
0x18000882c  push    rdi
0x18000882d  push    r14
0x18000882f  sub     rsp, 20h
0x180008833  mov     rbx, rdx
0x180008836  mov     rdi, rcx
0x180008839  mov     [rax+8], rcx
0x18000883d  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x180008842  mov     rcx, rax
0x180008845  test    rax, rax
0x180008848  jz      loc_180008914
0x18000884e  mov     rax, [rax]
0x180008851  mov     rax, [rax+18h]
0x180008855  call    cs:__guard_dispatch_icall_fptr
0x18000885b  add     rax, 18h
0x18000885f  mov     [rdi], rax
0x180008862  lea     rax, [rbx-1]
0x180008866  cmp     rax, 0FFFEh
0x18000886c  ja      loc_1800088F2
0x180008872  movzx   esi, bx
0x180008875  xor     edx, edx; int
0x180008877  lea     rcx, ?_AtlBaseModule@ATL@@3VCAtlBaseModule@1@A; this
0x18000887e  call    ?GetHInstanceAt@CAtlBaseModule@ATL@@QEAAPEAUHINSTANCE__@@H@Z; ATL::CAtlBaseModule::GetHInstanceAt(int)
0x180008883  mov     rbx, rax
0x180008886  mov     ebp, 1
0x18000888b  test    rax, rax
0x18000888e  jz      short loc_1800088DB
0x180008890  mov     r14d, esi
0x180008893  shr     r14, 4
0x180008897  xor     r9d, r9d; wLanguage
0x18000889a  lea     r8, [r14+1]; lpName
0x18000889e  lea     edx, [r9+6]; lpType
0x1800088a2  mov     rcx, rbx; hModule
0x1800088a5  call    cs:__imp_FindResourceExW
0x1800088ab  test    rax, rax
0x1800088ae  jz      short loc_1800088BE
0x1800088b0  mov     r8d, esi; unsigned int
0x1800088b3  mov     rdx, rax; hResInfo
0x1800088b6  mov     rcx, rbx; hModule
0x1800088b9  call    ?_AtlGetStringResourceImage@ATL@@YAPEBUATLSTRINGRESOURCEIMAGE@1@PEAUHINSTANCE__@@PEAUHRSRC__@@I@Z; ATL::_AtlGetStringResourceImage(HINSTANCE__ *,HRSRC__ *,uint)
0x1800088be  test    rax, rax
0x1800088c1  jnz     short loc_1800088DD
0x1800088c3  mov     edx, ebp; int
0x1800088c5  inc     ebp
0x1800088c7  lea     rcx, ?_AtlBaseModule@ATL@@3VCAtlBaseModule@1@A; this
0x1800088ce  call    ?GetHInstanceAt@CAtlBaseModule@ATL@@QEAAPEAUHINSTANCE__@@H@Z; ATL::CAtlBaseModule::GetHInstanceAt(int)
0x1800088d3  mov     rbx, rax
0x1800088d6  test    rax, rax
0x1800088d9  jnz     short loc_180008897
0x1800088db  xor     ebx, ebx
0x1800088dd  test    rbx, rbx
0x1800088e0  jz      short loc_1800088FE
0x1800088e2  mov     r8d, esi
0x1800088e5  mov     rdx, rbx
0x1800088e8  mov     rcx, rdi
0x1800088eb  call    ?LoadStringW@?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAHPEAUHINSTANCE__@@I@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::LoadStringW(HINSTANCE__ *,uint)
0x1800088f0  jmp     short loc_1800088FE
0x1800088f2  mov     rdx, rbx
0x1800088f5  mov     rcx, rdi
0x1800088f8  call    ??4?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEB_W@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator=(wchar_t const *)
0x1800088fd  nop
0x1800088fe  mov     rax, rdi
0x180008901  mov     rbx, [rsp+38h+arg_8]
0x180008906  mov     rbp, [rsp+38h+arg_10]
0x18000890b  add     rsp, 20h
0x18000890f  pop     r14
0x180008911  pop     rdi
0x180008912  pop     rsi
0x180008913  retn
0x180008914  mov     ecx, 80004005h; int
0x180008919  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
