# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x18003d248`
- end: `0x18003d5f1`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `937`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x18003f008`

## callees

- `0x180023d86`
- `0x180023dd0`
- `0x180023e60`
- `0x180030bd0`
- `0x18003ce3c`
- `0x18003ce74`
- `0x18003d248`
- `0x18003d5f8`
- `0x18003d7e0`
- `0x18003d840`
- `0x18003e3b4`
- `0x18003e50c`
- `0x18003f6f4`
- `0x18003fc54`

## import_xrefs

- `USER32!CharNextW` at `0x18003d397`
- `USER32!CharNextW` at `0x18003d3b2`
- `USER32!CharNextW` at `0x18003d397`
- `USER32!CharNextW` at `0x18003d3b2`
- `ADVAPI32!RegSetValueExW` at `0x18003d468`
- `ADVAPI32!RegSetValueExW` at `0x18003d556`
- `ADVAPI32!RegSetValueExW` at `0x18003d5a5`
- `ADVAPI32!RegSetValueExW` at `0x18003d468`
- `ADVAPI32!RegSetValueExW` at `0x18003d556`
- `ADVAPI32!RegSetValueExW` at `0x18003d5a5`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18003d424`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18003d424`
- `KERNEL32!lstrcmpiW` at `0x18003d2b7`
- `KERNEL32!lstrcmpiW` at `0x18003d2b7`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  __int64 result; // rax
  int v9; // ebx
  __int16 v10; // bx
  __int64 v11; // rbx
  unsigned __int64 v12; // rax
  unsigned __int16 *v13; // rbx
  WCHAR *i; // rdi
  const WCHAR *v15; // rax
  int v16; // eax
  LSTATUS v17; // edi
  HRESULT v18; // ebx
  HKEY v19; // rcx
  __int64 v20; // rbx
  size_t cbData; // rsi
  unsigned __int64 v22; // rax
  BYTE *v23; // rcx
  __int64 j; // r10
  unsigned __int8 v25; // al
  int v26; // r10d
  char v27; // dl
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 v30; // rbx
  int Token; // eax
  unsigned int v32; // ecx
  ULONG pulOut; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v35[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v36; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v37[264]; // [rsp+58h] [rbp-A8h] BYREF
  BYTE *lpData; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v39[264]; // [rsp+168h] [rbp+68h] BYREF
  OLECHAR String1[4096]; // [rsp+270h] [rbp+170h] BYREF

  result = ATL::CRegParser::NextToken(this, String1);
  if ( (int)result >= 0 )
  {
    v9 = 0;
    while ( lstrcmpiW(String1, (&`ATL::CRegParser::VTFromRegType'::`2'::map)[2 * v9]) )
    {
      if ( (unsigned int)++v9 >= 4 )
        return 2147614729LL;
    }
    v10 = *((_WORD *)&`ATL::CRegParser::VTFromRegType'::`2'::map + 8 * v9 + 4);
    ATL::CRegParser::SkipWhiteSpace(this);
    result = ATL::CRegParser::NextToken(this, String1);
    if ( (int)result >= 0 )
    {
      if ( v10 == 8 )
      {
        v30 = -1;
        do
          ++v30;
        while ( String1[v30] );
        v17 = RegSetValueExW(*a2, a3, 0, 1u, (const BYTE *)String1, 2 * v30 + 2);
        goto LABEL_45;
      }
      if ( v10 != 17 )
      {
        if ( v10 == 19 )
        {
          pulOut = 0;
          v35[0] = 0;
          v18 = VarUI4FromStr(String1, 0, 0, &pulOut);
          if ( v18 < 0 )
          {
            ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(v35);
            return (unsigned int)v18;
          }
          v19 = *a2;
          *(_DWORD *)Data = pulOut;
          v17 = RegSetValueExW(v19, a3, 0, 4u, Data, 4u);
          ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(v35);
        }
        else
        {
          if ( v10 != 16392 )
          {
LABEL_47:
            Token = ATL::CRegParser::NextToken(this, a4);
            v32 = 0;
            if ( Token < 0 )
              return (unsigned int)Token;
            return v32;
          }
          v11 = -1;
          do
            ++v11;
          while ( String1[v11] );
          v36 = 0;
          v12 = ATL::AtlMultiplyThrow<unsigned __int64>((int)v11 + 2, 2);
          if ( v12 <= 0x100 )
          {
            v13 = (unsigned __int16 *)v37;
            v36 = (unsigned __int16 *)v37;
          }
          else
          {
            ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v36, v12);
            v13 = v36;
          }
          if ( v13 )
          {
            for ( i = String1; *i; ++v13 )
            {
              v15 = CharNextW(i);
              if ( *i == 92 && *v15 == 48 )
              {
                *v13 = 0;
                i = CharNextW(v15);
              }
              else
              {
                *v13 = *i++;
              }
            }
            *(_DWORD *)v13 = 0;
            v16 = ATL::CRegKey::SetMultiStringValue((ATL::CRegKey *)a2, a3, v36);
            v13 = v36;
            v17 = v16;
          }
          else
          {
            v17 = 14;
          }
          if ( v13 != (unsigned __int16 *)v37 )
            ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v36);
        }
LABEL_45:
        if ( v17 )
          return ATL::AtlHresultFromWin32(v17);
        goto LABEL_47;
      }
      v20 = -1;
      do
        ++v20;
      while ( String1[v20] );
      if ( (v20 & 1) == 0 )
      {
        lpData = 0;
        cbData = (int)v20 / 2;
        v22 = ATL::AtlMultiplyThrow<unsigned __int64>(cbData, 1);
        if ( v22 <= 0x100 )
        {
          v23 = v39;
          lpData = v39;
        }
        else
        {
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v22);
          v23 = lpData;
        }
        if ( v23 )
        {
          memset_0(v23, 0, cbData);
          for ( j = 0; (int)j < (int)v20; *(_BYTE *)(v29 + v28) |= v25 << (4 - 4 * v27) )
          {
            v25 = ATL::CRegParser::ChToByte(String1[j]);
            v27 = v26 & 1;
            j = (unsigned int)(v26 + 1);
          }
          v17 = RegSetValueExW(*a2, a3, 0, 3u, lpData, cbData);
          ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
          goto LABEL_45;
        }
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
      }
      return 2147500037LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18003d248  push    rbp
0x18003d24a  push    rbx
0x18003d24b  push    rsi
0x18003d24c  push    rdi
0x18003d24d  push    r12
0x18003d24f  push    r13
0x18003d251  push    r14
0x18003d253  push    r15
0x18003d255  lea     rbp, [rsp-2188h]
0x18003d25d  mov     eax, 2288h
0x18003d262  call    _alloca_probe
0x18003d267  sub     rsp, rax
0x18003d26a  mov     rax, cs:__security_cookie
0x18003d271  xor     rax, rsp
0x18003d274  mov     [rbp+21C0h+var_50], rax
0x18003d27b  mov     r14, rdx
0x18003d27e  mov     r13, r9
0x18003d281  lea     rdx, [rbp+21C0h+String1]; unsigned __int16 *
0x18003d288  mov     r15, r8
0x18003d28b  mov     r12, rcx
0x18003d28e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003d293  xor     esi, esi
0x18003d295  test    eax, eax
0x18003d297  js      loc_18003D5CE
0x18003d29d  mov     ebx, esi
0x18003d29f  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18003d2a6  movsxd  rdi, ebx
0x18003d2a9  lea     rcx, [rbp+21C0h+String1]; lpString1
0x18003d2b0  add     rdi, rdi
0x18003d2b3  mov     rdx, [rax+rdi*8]; lpString2
0x18003d2b7  call    cs:__imp_lstrcmpiW
0x18003d2bd  test    eax, eax
0x18003d2bf  jz      short loc_18003D2D9
0x18003d2c1  inc     ebx
0x18003d2c3  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18003d2ca  cmp     ebx, 4
0x18003d2cd  jb      short loc_18003D2A6
0x18003d2cf  mov     eax, 80020009h
0x18003d2d4  jmp     loc_18003D5CE
0x18003d2d9  lea     rbx, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18003d2e0  mov     rcx, r12; this
0x18003d2e3  movzx   ebx, word ptr [rbx+rdi*8+8]
0x18003d2e8  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18003d2ed  lea     rdx, [rbp+21C0h+String1]; unsigned __int16 *
0x18003d2f4  mov     rcx, r12; this
0x18003d2f7  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003d2fc  test    eax, eax
0x18003d2fe  js      loc_18003D5CE
0x18003d304  cmp     bx, 8
0x18003d308  jz      loc_18003D56B
0x18003d30e  cmp     bx, 11h
0x18003d312  jz      loc_18003D47F
0x18003d318  cmp     bx, 13h
0x18003d31c  jz      loc_18003D40A
0x18003d322  mov     eax, 4008h
0x18003d327  cmp     bx, ax
0x18003d32a  jnz     loc_18003D5BA
0x18003d330  lea     rax, [rbp+21C0h+String1]
0x18003d337  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003d33b  inc     rbx
0x18003d33e  cmp     [rax+rbx*2], si
0x18003d342  jnz     short loc_18003D33B
0x18003d344  lea     eax, [rbx+2]
0x18003d347  mov     [rsp+22C0h+var_2270], rsi
0x18003d34c  movsxd  rcx, eax
0x18003d34f  mov     edx, 2
0x18003d354  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18003d359  cmp     rax, 100h
0x18003d35f  jbe     short loc_18003D375
0x18003d361  mov     rdx, rax
0x18003d364  lea     rcx, [rsp+22C0h+var_2270]
0x18003d369  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18003d36e  mov     rbx, [rsp+22C0h+var_2270]
0x18003d373  jmp     short loc_18003D37F
0x18003d375  lea     rbx, [rsp+22C0h+var_2268]
0x18003d37a  mov     [rsp+22C0h+var_2270], rbx
0x18003d37f  test    rbx, rbx
0x18003d382  jz      short loc_18003D3E8
0x18003d384  lea     rdi, [rbp+21C0h+String1]
0x18003d38b  cmp     [rbp+21C0h+String1], si
0x18003d392  jz      short loc_18003D3CD
0x18003d394  mov     rcx, rdi; lpsz
0x18003d397  call    cs:__imp_CharNextW
0x18003d39d  movzx   ecx, word ptr [rdi]
0x18003d3a0  cmp     cx, 5Ch ; '\'
0x18003d3a4  jnz     short loc_18003D3BD
0x18003d3a6  cmp     word ptr [rax], 30h ; '0'
0x18003d3aa  jnz     short loc_18003D3BD
0x18003d3ac  mov     rcx, rax; lpsz
0x18003d3af  mov     [rbx], si
0x18003d3b2  call    cs:__imp_CharNextW
0x18003d3b8  mov     rdi, rax
0x18003d3bb  jmp     short loc_18003D3C4
0x18003d3bd  mov     [rbx], cx
0x18003d3c0  add     rdi, 2
0x18003d3c4  add     rbx, 2
0x18003d3c8  cmp     [rdi], si
0x18003d3cb  jnz     short loc_18003D394
0x18003d3cd  mov     [rbx], esi
0x18003d3cf  mov     rdx, r15; unsigned __int16 *
0x18003d3d2  mov     r8, [rsp+22C0h+var_2270]; unsigned __int16 *
0x18003d3d7  mov     rcx, r14; this
0x18003d3da  call    ?SetMultiStringValue@CRegKey@ATL@@QEAAJPEBG0@Z; ATL::CRegKey::SetMultiStringValue(ushort const *,ushort const *)
0x18003d3df  mov     rbx, [rsp+22C0h+var_2270]
0x18003d3e4  mov     edi, eax
0x18003d3e6  jmp     short loc_18003D3ED
0x18003d3e8  mov     edi, 0Eh
0x18003d3ed  lea     rax, [rsp+22C0h+var_2268]
0x18003d3f2  cmp     rbx, rax
0x18003d3f5  jz      loc_18003D5AD
0x18003d3fb  lea     rcx, [rsp+22C0h+var_2270]
0x18003d400  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18003d405  jmp     loc_18003D5AD
0x18003d40a  lea     r9, [rsp+22C0h+pulOut]; pulOut
0x18003d40f  mov     [rsp+22C0h+pulOut], esi
0x18003d413  xor     r8d, r8d; dwFlags
0x18003d416  mov     [rsp+22C0h+var_2280], rsi
0x18003d41b  xor     edx, edx; lcid
0x18003d41d  lea     rcx, [rbp+21C0h+String1]; strIn
0x18003d424  call    cs:__imp_VarUI4FromStr
0x18003d42a  mov     ebx, eax
0x18003d42c  test    eax, eax
0x18003d42e  jns     short loc_18003D441
0x18003d430  lea     rcx, [rsp+22C0h+var_2280]
0x18003d435  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18003d43a  mov     eax, ebx
0x18003d43c  jmp     loc_18003D5CE
0x18003d441  mov     eax, [rsp+22C0h+pulOut]
0x18003d445  mov     ecx, 4
0x18003d44a  mov     [rsp+22C0h+cbData], ecx; cbData
0x18003d44e  mov     r9d, ecx; dwType
0x18003d451  mov     rcx, [r14]; hKey
0x18003d454  xor     r8d, r8d; Reserved
0x18003d457  mov     dword ptr [rsp+22C0h+Data], eax
0x18003d45b  mov     rdx, r15; lpValueName
0x18003d45e  lea     rax, [rsp+22C0h+Data]
0x18003d463  mov     [rsp+22C0h+lpData], rax; lpData
0x18003d468  call    cs:__imp_RegSetValueExW
0x18003d46e  lea     rcx, [rsp+22C0h+var_2280]
0x18003d473  mov     edi, eax
0x18003d475  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18003d47a  jmp     loc_18003D5AD
0x18003d47f  lea     rax, [rbp+21C0h+String1]
0x18003d486  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003d48a  inc     rbx
0x18003d48d  cmp     [rax+rbx*2], si
0x18003d491  jnz     short loc_18003D48A
0x18003d493  test    bl, 1
0x18003d496  jz      short loc_18003D4A2
0x18003d498  mov     eax, 80004005h
0x18003d49d  jmp     loc_18003D5CE
0x18003d4a2  mov     eax, ebx
0x18003d4a4  mov     [rbp+21C0h+var_2160], 0
0x18003d4ac  cdq
0x18003d4ad  sub     eax, edx
0x18003d4af  mov     edx, 1
0x18003d4b4  sar     eax, 1
0x18003d4b6  movsxd  rsi, eax
0x18003d4b9  mov     rcx, rsi
0x18003d4bc  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18003d4c1  cmp     rax, 100h
0x18003d4c7  jbe     short loc_18003D4DB
0x18003d4c9  mov     rdx, rax
0x18003d4cc  lea     rcx, [rbp+21C0h+var_2160]
0x18003d4d0  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18003d4d5  mov     rcx, [rbp+21C0h+var_2160]
0x18003d4d9  jmp     short loc_18003D4E3
0x18003d4db  lea     rcx, [rbp+21C0h+var_2158]; void *
0x18003d4df  mov     [rbp+21C0h+var_2160], rcx
0x18003d4e3  test    rcx, rcx
0x18003d4e6  jnz     short loc_18003D4F3
0x18003d4e8  lea     rcx, [rbp+21C0h+var_2160]
0x18003d4ec  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18003d4f1  jmp     short loc_18003D498
0x18003d4f3  mov     r8, rsi; Size
0x18003d4f6  xor     edx, edx; Val
0x18003d4f8  call    memset_0
0x18003d4fd  xor     r10d, r10d
0x18003d500  test    ebx, ebx
0x18003d502  jle     short loc_18003D53A
0x18003d504  movzx   ecx, [rbp+r10*2+21C0h+String1]; unsigned __int16
0x18003d50d  mov     r8, [rbp+21C0h+var_2160]
0x18003d511  mov     r9d, r10d
0x18003d514  shr     r9, 1
0x18003d517  call    ?ChToByte@CRegParser@ATL@@KAEG@Z; ATL::CRegParser::ChToByte(ushort)
0x18003d51c  mov     edx, r10d
0x18003d51f  mov     ecx, 4
0x18003d524  and     edx, 1
0x18003d527  inc     r10d
0x18003d52a  shl     edx, 2
0x18003d52d  sub     ecx, edx
0x18003d52f  shl     al, cl
0x18003d531  or      [r9+r8], al
0x18003d535  cmp     r10d, ebx
0x18003d538  jl      short loc_18003D504
0x18003d53a  mov     rax, [rbp+21C0h+var_2160]
0x18003d53e  mov     r9d, 3; dwType
0x18003d544  mov     rcx, [r14]; hKey
0x18003d547  xor     r8d, r8d; Reserved
0x18003d54a  mov     [rsp+22C0h+cbData], esi; cbData
0x18003d54e  mov     rdx, r15; lpValueName
0x18003d551  mov     [rsp+22C0h+lpData], rax; lpData
0x18003d556  call    cs:__imp_RegSetValueExW
0x18003d55c  lea     rcx, [rbp+21C0h+var_2160]
0x18003d560  mov     edi, eax
0x18003d562  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18003d567  xor     esi, esi
0x18003d569  jmp     short loc_18003D5AD
0x18003d56b  lea     rax, [rbp+21C0h+String1]
0x18003d572  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003d576  inc     rbx
0x18003d579  cmp     [rax+rbx*2], si
0x18003d57d  jnz     short loc_18003D576
0x18003d57f  mov     rcx, [r14]; hKey
0x18003d582  lea     eax, ds:2[rbx*2]
0x18003d589  mov     [rsp+22C0h+cbData], eax; cbData
0x18003d58d  mov     r9d, 1; dwType
0x18003d593  lea     rax, [rbp+21C0h+String1]
0x18003d59a  xor     r8d, r8d; Reserved
0x18003d59d  mov     rdx, r15; lpValueName
0x18003d5a0  mov     [rsp+22C0h+lpData], rax; lpData
0x18003d5a5  call    cs:__imp_RegSetValueExW
0x18003d5ab  mov     edi, eax
0x18003d5ad  test    edi, edi
0x18003d5af  jz      short loc_18003D5BA
0x18003d5b1  mov     ecx, edi; unsigned int
0x18003d5b3  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18003d5b8  jmp     short loc_18003D5CE
0x18003d5ba  mov     rdx, r13; unsigned __int16 *
0x18003d5bd  mov     rcx, r12; this
0x18003d5c0  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003d5c5  test    eax, eax
0x18003d5c7  mov     ecx, esi
0x18003d5c9  cmovs   ecx, eax
0x18003d5cc  mov     eax, ecx
0x18003d5ce  mov     rcx, [rbp+21C0h+var_50]
0x18003d5d5  xor     rcx, rsp; StackCookie
0x18003d5d8  call    __security_check_cookie
0x18003d5dd  add     rsp, 2288h
0x18003d5e4  pop     r15
0x18003d5e6  pop     r14
0x18003d5e8  pop     r13
0x18003d5ea  pop     r12
0x18003d5ec  pop     rdi
0x18003d5ed  pop     rsi
0x18003d5ee  pop     rbx
0x18003d5ef  pop     rbp
0x18003d5f0  retn
```
