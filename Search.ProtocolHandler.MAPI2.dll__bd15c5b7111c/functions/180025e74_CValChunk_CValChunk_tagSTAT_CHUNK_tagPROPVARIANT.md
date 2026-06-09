# CValChunk::CValChunk(tagSTAT_CHUNK *,tagPROPVARIANT *)

- ea: `0x180025e74`
- end: `0x180025f2e`
- name: `??0CValChunk@@QEAA@PEAUtagSTAT_CHUNK@@PEAUtagPROPVARIANT@@@Z`
- size: `186`
- prototype: `CValChunk *__fastcall(CValChunk *__hidden this, struct tagSTAT_CHUNK *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002636c`

## callees

- `0x18000e0d0`
- `0x18000e6e0`
- `0x1800122d8`
- `0x180025e74`
- `0x180026928`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025ebb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025ebb`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
CValChunk *__fastcall CValChunk::CValChunk(CValChunk *this, struct tagSTAT_CHUNK *a2, struct tagPROPVARIANT *a3)
{
  _QWORD *v6; // rax
  const wchar_t *lpwstr; // rcx
  unsigned int v8; // eax
  __int64 v9; // rcx

  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((__int64)this);
  *(struct tagSTAT_CHUNK *)((char *)this + 8) = *a2;
  v6 = CoTaskMemAlloc(0x18u);
  *((_QWORD *)this + 9) = v6;
  if ( v6 )
  {
    *(_OWORD *)v6 = *(_OWORD *)&a3->vt;
    v6[2] = a3->bstrblobVal.pData;
    if ( !a2->attribute.psProperty.ulKind )
    {
      lpwstr = a2->attribute.psProperty.lpwstr;
      if ( lpwstr )
      {
        v8 = ocslen(lpwstr);
        ATL::CSimpleStringT<wchar_t,0>::SetString(this, v9, v8);
        *((_DWORD *)this + 10) = 0;
        *((_QWORD *)this + 6) = ATL::CSimpleStringT<wchar_t,0>::GetBuffer(this);
      }
    }
    *(_OWORD *)&a3->vt = 0;
    a3->bstrblobVal.pData = 0;
  }
  return this;
}

```

## disassembly

```asm
0x180025e74  mov     [rsp+arg_8], rbx
0x180025e79  mov     [rsp+arg_10], rsi
0x180025e7e  mov     [rsp+arg_0], rcx
0x180025e83  push    rdi
0x180025e84  sub     rsp, 20h
0x180025e88  mov     rdi, r8
0x180025e8b  mov     rsi, rdx
0x180025e8e  mov     rbx, rcx
0x180025e91  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x180025e96  nop
0x180025e97  movaps  xmm0, xmmword ptr [rsi]
0x180025e9a  movups  xmmword ptr [rbx+8], xmm0
0x180025e9e  movaps  xmm1, xmmword ptr [rsi+10h]
0x180025ea2  movups  xmmword ptr [rbx+18h], xmm1
0x180025ea6  movaps  xmm0, xmmword ptr [rsi+20h]
0x180025eaa  movups  xmmword ptr [rbx+28h], xmm0
0x180025eae  movaps  xmm1, xmmword ptr [rsi+30h]
0x180025eb2  movups  xmmword ptr [rbx+38h], xmm1
0x180025eb6  mov     ecx, 18h; cb
0x180025ebb  call    cs:__imp_CoTaskMemAlloc
0x180025ec1  mov     [rbx+48h], rax
0x180025ec5  test    rax, rax
0x180025ec8  jz      short loc_180025F1B
0x180025eca  movups  xmm0, xmmword ptr [rdi]
0x180025ecd  movups  xmmword ptr [rax], xmm0
0x180025ed0  movsd   xmm1, qword ptr [rdi+10h]
0x180025ed5  movsd   qword ptr [rax+10h], xmm1
0x180025eda  cmp     dword ptr [rsi+20h], 0
0x180025ede  jnz     short loc_180025F0F
0x180025ee0  mov     rcx, [rsi+28h]; wchar_t *
0x180025ee4  test    rcx, rcx
0x180025ee7  jz      short loc_180025F0F
0x180025ee9  call    ?ocslen@@YAHPEB_W@Z; ocslen(wchar_t const *)
0x180025eee  mov     r8d, eax
0x180025ef1  mov     rdx, rcx
0x180025ef4  mov     rcx, rbx
0x180025ef7  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x180025efc  mov     dword ptr [rbx+28h], 0
0x180025f03  mov     rcx, rbx
0x180025f06  call    ?GetBuffer@?$CSimpleStringT@_W$0A@@ATL@@QEAAPEA_WXZ; ATL::CSimpleStringT<wchar_t,0>::GetBuffer(void)
0x180025f0b  mov     [rbx+30h], rax
0x180025f0f  xorps   xmm0, xmm0
0x180025f12  xor     eax, eax
0x180025f14  movups  xmmword ptr [rdi], xmm0
0x180025f17  mov     [rdi+10h], rax
0x180025f1b  mov     rax, rbx
0x180025f1e  mov     rbx, [rsp+28h+arg_8]
0x180025f23  mov     rsi, [rsp+28h+arg_10]
0x180025f28  add     rsp, 20h
0x180025f2c  pop     rdi
0x180025f2d  retn
```
