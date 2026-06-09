# CFilterWrapper::GetChunk(tagSTAT_CHUNK *)

- ea: `0x14001f490`
- end: `0x14001f716`
- name: `?GetChunk@CFilterWrapper@@UEAAJPEAUtagSTAT_CHUNK@@@Z`
- size: `646`
- prototype: `__int64 __fastcall(CFilterWrapper *__hidden this, struct tagSTAT_CHUNK *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400030a0`
- `0x140003c74`
- `0x14001e440`
- `0x14001f490`
- `0x14001fdfc`
- `0x140024808`
- `0x140024efc`
- `0x14004f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001f5e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001f5e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14001f68c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14001f68c`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x14001f5b5`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x14001f5b5`

## string_xrefs

- `0x14001f5c7`: `[SrchFilterDaemon] Filter with CLSID %s timed out on GetChunk`

## pseudocode

```c
__int64 __fastcall CFilterWrapper::GetChunk(CFilterWrapper *this, struct tagSTAT_CHUNK *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rbx
  _BYTE *v6; // rax
  int v7; // eax
  const wchar_t *v8; // r9
  unsigned __int64 CurrentProcessTime; // rax
  __int64 v10; // rcx
  PROPSPEC v11; // xmm2
  GUID v12; // xmm1
  __int128 v13; // xmm0
  unsigned __int64 v14; // xmm2_8
  __int64 v15; // rax
  unsigned __int64 v16; // rax
  unsigned int v17; // ebx
  void *v18; // rax
  const wchar_t *v19; // r8
  LPOLESTR lpsz; // [rsp+20h] [rbp-39h] BYREF
  _OWORD v22[2]; // [rsp+30h] [rbp-29h] BYREF
  wchar_t *v23[2]; // [rsp+50h] [rbp-9h]
  __int128 v24; // [rsp+60h] [rbp+7h]
  IID rclsid; // [rsp+70h] [rbp+17h] BYREF

  CFilterProcessBackoffCtrl::Wait((CFilterWrapper *)((char *)this + 160));
  if ( a2 )
  {
    if ( *((_QWORD *)this + 6) )
    {
      if ( *((_DWORD *)this + 21) )
      {
        return (unsigned int)-2147215616;
      }
      else
      {
        v5 = 64;
        memset_0(v22, 0, 0x40u);
        v6 = v22;
        do
        {
          *v6++ = 0;
          --v5;
        }
        while ( v5 );
        v7 = (*(__int64 (__fastcall **)(_QWORD, _OWORD *))(**((_QWORD **)this + 6) + 32LL))(*((_QWORD *)this + 6), v22);
        v4 = v7;
        if ( v7 < 0 )
        {
          if ( v7 == -2147215616 )
          {
            *((_DWORD *)this + 21) = 1;
            a2->breakType = CHUNK_EOS;
            v4 = 0;
            a2->attribute.guidPropSet = GUID_0b63e350_9ccc_11d0_bcdb_00805fccce04;
            *(_QWORD *)&a2->flags = 2;
            *(_QWORD *)&a2->idChunkSource = 0;
            a2->cwcLenSource = 0;
            a2->idChunk = 0;
            a2->attribute.psProperty.ulKind = 1;
            LODWORD(a2->attribute.psProperty.propid) = 10;
          }
        }
        else
        {
          if ( *((_BYTE *)this + 96) )
          {
            CurrentProcessTime = CTimeLapse::GetCurrentProcessTime((CFilterWrapper *)((char *)this + 96));
            if ( *((int *)this + 30) >= 0 )
            {
              *((_QWORD *)this + 14) += CurrentProcessTime - *((_QWORD *)this + 13);
              *((_QWORD *)this + 13) = CurrentProcessTime;
            }
          }
          if ( *((_QWORD *)this + 14) / 0x2710uLL <= g_dwMaxMillisecondsInFilter )
          {
            if ( *((_DWORD *)this + 20) )
            {
              DWORD1(v22[0]) = 3;
              *((_DWORD *)this + 20) = 0;
            }
            v11 = *(PROPSPEC *)v23;
            v12 = (GUID)v22[1];
            *(_OWORD *)&a2->idChunk = v22[0];
            v13 = v24;
            a2->attribute.guidPropSet = v12;
            a2->attribute.psProperty = v11;
            *(_OWORD *)&a2->idChunkSource = v13;
            if ( !_mm_cvtsi128_si32((__m128i)v11) )
            {
              v14 = _mm_srli_si128((__m128i)v11, 8).m128i_u64[0];
              if ( v14 )
              {
                v15 = -1;
                do
                  ++v15;
                while ( *(_WORD *)(v14 + 2 * v15) );
                if ( (_DWORD)v15 )
                {
                  if ( (int)v15 + 1 < (unsigned int)v15 )
                    return (unsigned int)-2147024362;
                  v16 = 2LL * (unsigned int)(v15 + 1);
                  if ( v16 > 0xFFFFFFFF )
                  {
                    return (unsigned int)-2147024362;
                  }
                  else
                  {
                    v17 = v16;
                    v18 = CoTaskMemAlloc((unsigned int)v16);
                    v19 = v23[1];
                    a2->attribute.psProperty.propid = v18;
                    return (unsigned int)StringCbCopyW((wchar_t *)v18, v17, v19);
                  }
                }
              }
              else
              {
                return (unsigned int)-2147215613;
              }
            }
          }
          else
          {
            v10 = *((_QWORD *)this + 8);
            v4 = -2147215616;
            rclsid = 0;
            if ( v10 && (*(int (__fastcall **)(__int64, IID *))(*(_QWORD *)v10 + 24LL))(v10, &rclsid) >= 0 )
            {
              lpsz = 0;
              if ( StringFromCLSID(&rclsid, &lpsz) >= 0 )
              {
                SearchIndexerTrace::Error(
                  (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\searchfilterhost\\\\fltrhost.cxx\"",
                  (const wchar_t *)0x106,
                  (unsigned int)L"[SrchFilterDaemon] Filter with CLSID %s timed out on GetChunk",
                  lpsz);
                CoTaskMemFree(lpsz);
              }
            }
            else
            {
              SearchIndexerTrace::Error(
                (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\searchfilterhost\\\\fltrhost.cxx\"",
                (const wchar_t *)0x10C,
                (unsigned int)L"[SrchFilterDaemon] Filter timed out on GetChunk",
                v8);
            }
          }
        }
      }
    }
    else
    {
      return (unsigned int)-2147483638;
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v4;
}

```

## disassembly

```asm
0x14001f490  mov     [rsp-8+arg_10], rbx
0x14001f495  push    rbp
0x14001f496  push    rsi
0x14001f497  push    rdi
0x14001f498  push    r14
0x14001f49a  push    r15
0x14001f49c  lea     rbp, [rsp-37h]
0x14001f4a1  sub     rsp, 90h
0x14001f4a8  mov     rax, cs:__security_cookie
0x14001f4af  xor     rax, rsp
0x14001f4b2  mov     [rbp+57h+var_30], rax
0x14001f4b6  mov     rsi, rcx
0x14001f4b9  mov     rdi, rdx
0x14001f4bc  add     rcx, 0A0h; this
0x14001f4c3  call    ?Wait@CFilterProcessBackoffCtrl@@QEAAXXZ; CFilterProcessBackoffCtrl::Wait(void)
0x14001f4c8  xor     r15d, r15d
0x14001f4cb  test    rdi, rdi
0x14001f4ce  jnz     short loc_14001F4DA
0x14001f4d0  mov     ebx, 80004003h
0x14001f4d5  jmp     loc_14001F6F1
0x14001f4da  cmp     [rsi+30h], r15
0x14001f4de  jnz     short loc_14001F4EA
0x14001f4e0  mov     ebx, 8000000Ah
0x14001f4e5  jmp     loc_14001F6F1
0x14001f4ea  cmp     [rsi+54h], r15d
0x14001f4ee  jz      short loc_14001F4FA
0x14001f4f0  mov     ebx, 80041700h
0x14001f4f5  jmp     loc_14001F6F1
0x14001f4fa  mov     ebx, 40h ; '@'
0x14001f4ff  lea     rcx, [rbp+57h+var_80]; void *
0x14001f503  mov     r8d, ebx; Size
0x14001f506  xor     edx, edx; Val
0x14001f508  call    memset_0
0x14001f50d  lea     rax, [rbp+57h+var_80]
0x14001f511  mov     [rax], r15b
0x14001f514  inc     rax
0x14001f517  sub     rbx, 1
0x14001f51b  jnz     short loc_14001F511
0x14001f51d  mov     rcx, [rsi+30h]
0x14001f521  lea     rdx, [rbp+57h+var_80]
0x14001f525  mov     rax, [rcx]
0x14001f528  mov     rax, [rax+20h]
0x14001f52c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f531  mov     ebx, eax
0x14001f533  test    eax, eax
0x14001f535  js      loc_14001F6AF
0x14001f53b  cmp     [rsi+60h], r15b
0x14001f53f  jz      short loc_14001F55F
0x14001f541  lea     rcx, [rsi+60h]; this
0x14001f545  call    ?GetCurrentProcessTime@CTimeLapse@@AEAA_KXZ; CTimeLapse::GetCurrentProcessTime(void)
0x14001f54a  cmp     [rsi+78h], r15d
0x14001f54e  jl      short loc_14001F55F
0x14001f550  mov     rcx, rax
0x14001f553  sub     rcx, [rsi+68h]
0x14001f557  add     [rsi+70h], rcx
0x14001f55b  mov     [rsi+68h], rax
0x14001f55f  mov     rax, 346DC5D63886594Bh
0x14001f569  mul     qword ptr [rsi+70h]
0x14001f56d  mov     eax, cs:?g_dwMaxMillisecondsInFilter@@3KA; ulong g_dwMaxMillisecondsInFilter
0x14001f573  shr     rdx, 0Bh
0x14001f577  cmp     rdx, rax
0x14001f57a  jbe     loc_14001F60B
0x14001f580  mov     rcx, [rsi+40h]
0x14001f584  xorps   xmm0, xmm0
0x14001f587  mov     ebx, 80041700h
0x14001f58c  movups  xmmword ptr [rbp+57h+rclsid.Data1], xmm0
0x14001f590  test    rcx, rcx
0x14001f593  jz      short loc_14001F5EE
0x14001f595  mov     rax, [rcx]
0x14001f598  lea     rdx, [rbp+57h+rclsid]
0x14001f59c  mov     rax, [rax+18h]
0x14001f5a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f5a5  test    eax, eax
0x14001f5a7  js      short loc_14001F5EE
0x14001f5a9  lea     rdx, [rbp+57h+lpsz]; lplpsz
0x14001f5ad  mov     [rbp+57h+lpsz], r15
0x14001f5b1  lea     rcx, [rbp+57h+rclsid]; rclsid
0x14001f5b5  call    cs:__imp_StringFromCLSID
0x14001f5bb  test    eax, eax
0x14001f5bd  js      loc_14001F6F1
0x14001f5c3  mov     r9, [rbp+57h+lpsz]; wchar_t *
0x14001f5c7  lea     r8, aSrchfilterdaem_2; "[SrchFilterDaemon] Filter with CLSID %s"...
0x14001f5ce  mov     edx, 106h; wchar_t *
0x14001f5d3  lea     rcx, aOnecoreuapBase_20; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x14001f5da  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x14001f5df  mov     rcx, [rbp+57h+lpsz]; pv
0x14001f5e3  call    cs:__imp_CoTaskMemFree
0x14001f5e9  jmp     loc_14001F6F1
0x14001f5ee  lea     r8, aSrchfilterdaem_1; "[SrchFilterDaemon] Filter timed out on "...
0x14001f5f5  mov     edx, 10Ch; wchar_t *
0x14001f5fa  lea     rcx, aOnecoreuapBase_20; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x14001f601  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x14001f606  jmp     loc_14001F6F1
0x14001f60b  cmp     [rsi+50h], r15d
0x14001f60f  jz      short loc_14001F61C
0x14001f611  mov     dword ptr [rbp+57h+var_80+4], 3
0x14001f618  mov     [rsi+50h], r15d
0x14001f61c  movaps  xmm2, xmmword ptr [rbp+57h+var_60]
0x14001f620  movaps  xmm0, [rbp+57h+var_80]
0x14001f624  movaps  xmm1, [rbp+57h+var_70]
0x14001f628  movups  xmmword ptr [rdi], xmm0
0x14001f62b  movaps  xmm0, [rbp+57h+var_50]
0x14001f62f  movups  xmmword ptr [rdi+10h], xmm1
0x14001f633  movd    eax, xmm2
0x14001f637  movups  xmmword ptr [rdi+20h], xmm2
0x14001f63b  movups  xmmword ptr [rdi+30h], xmm0
0x14001f63f  test    eax, eax
0x14001f641  jnz     loc_14001F6F1
0x14001f647  psrldq  xmm2, 8
0x14001f64c  movq    rcx, xmm2
0x14001f651  test    rcx, rcx
0x14001f654  jnz     short loc_14001F660
0x14001f656  mov     ebx, 80041703h
0x14001f65b  jmp     loc_14001F6F1
0x14001f660  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001f664  inc     rax
0x14001f667  cmp     [rcx+rax*2], r15w
0x14001f66c  jnz     short loc_14001F664
0x14001f66e  test    eax, eax
0x14001f670  jz      short loc_14001F6F1
0x14001f672  lea     ecx, [rax+1]
0x14001f675  cmp     ecx, eax
0x14001f677  jb      short loc_14001F6A8
0x14001f679  mov     eax, ecx
0x14001f67b  mov     ecx, 0FFFFFFFFh
0x14001f680  add     rax, rax
0x14001f683  cmp     rax, rcx
0x14001f686  ja      short loc_14001F6A8
0x14001f688  mov     ecx, eax; cb
0x14001f68a  mov     ebx, eax
0x14001f68c  call    cs:__imp_CoTaskMemAlloc
0x14001f692  mov     r8, [rbp+57h+var_60+8]; wchar_t *
0x14001f696  mov     edx, ebx; unsigned __int64
0x14001f698  mov     rcx, rax; wchar_t *
0x14001f69b  mov     [rdi+28h], rax
0x14001f69f  call    ?StringCbCopyW@@YAJPEA_W_KPEB_W@Z; StringCbCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x14001f6a4  mov     ebx, eax
0x14001f6a6  jmp     short loc_14001F6F1
0x14001f6a8  mov     ebx, 80070216h
0x14001f6ad  jmp     short loc_14001F6F1
0x14001f6af  cmp     eax, 80041700h
0x14001f6b4  jnz     short loc_14001F6F1
0x14001f6b6  movups  xmm0, xmmword ptr cs:_GUID_0b63e350_9ccc_11d0_bcdb_00805fccce04.Data1
0x14001f6bd  mov     dword ptr [rsi+54h], 1
0x14001f6c4  mov     eax, 2
0x14001f6c9  mov     [rdi+4], eax
0x14001f6cc  mov     ebx, r15d
0x14001f6cf  movdqu  xmmword ptr [rdi+10h], xmm0
0x14001f6d4  mov     [rdi+8], rax
0x14001f6d8  mov     [rdi+30h], r15
0x14001f6dc  mov     [rdi+38h], r15d
0x14001f6e0  mov     [rdi], r15d
0x14001f6e3  mov     dword ptr [rdi+20h], 1
0x14001f6ea  mov     dword ptr [rdi+28h], 0Ah
0x14001f6f1  mov     eax, ebx
0x14001f6f3  mov     rcx, [rbp+57h+var_30]
0x14001f6f7  xor     rcx, rsp; StackCookie
0x14001f6fa  call    __security_check_cookie
0x14001f6ff  mov     rbx, [rsp+0B0h+arg_10]
0x14001f707  add     rsp, 90h
0x14001f70e  pop     r15
0x14001f710  pop     r14
0x14001f712  pop     rdi
0x14001f713  pop     rsi
0x14001f714  pop     rbp
0x14001f715  retn
```
