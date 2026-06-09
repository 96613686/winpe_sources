# CCastableCommandQueue::LUCCompleteInitialization(void)

- ea: `0x1800852f8`
- end: `0x180085766`
- name: `?LUCCompleteInitialization@CCastableCommandQueue@@QEAAXXZ`
- size: `1134`
- prototype: `void __fastcall(CCastableCommandQueue *__hidden this)`
- caller_count: `5`
- callee_count: `16`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x18006f280`
- `0x1800f6e40`
- `0x1800f6e60`
- `0x1800f6eb0`
- `0x1800f6f30`

## callees

- `0x180004df0`
- `0x1800235dc`
- `0x18002361c`
- `0x180024350`
- `0x180024628`
- `0x1800246ec`
- `0x1800246f8`
- `0x180024924`
- `0x18004bccc`
- `0x1800852f8`
- `0x1800859a0`
- `0x1800b97e8`
- `0x1800b9808`
- `0x1800bb480`
- `0x18012e790`
- `0x180262020`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18008558c`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x1800855aa`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18008558c`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x1800855aa`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_K@Z` at `0x18008559a`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_K@Z` at `0x18008559a`

## string_xrefs

- `0x180085504`: `Compute`
- `0x18008549f`: `Unnamed ID3D12CommandQueue: Type=`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CCastableCommandQueue::LUCCompleteInitialization(CCastableCommandQueue *this)
{
  CCastableCommandQueue *v1; // rdi
  __int64 v2; // r15
  __int64 v3; // r13
  __int64 *v4; // rbx
  char *v5; // rcx
  __int64 v6; // r12
  _DWORD *v7; // rdx
  __int64 v8; // rsi
  __int64 v9; // rsi
  __int64 v10; // r12
  _DWORD *v11; // rdx
  int v12; // eax
  const char *v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rbx
  void (__fastcall *v18)(__int64, const struct _GUID *, _QWORD, __int128 *); // r15
  __int128 *v19; // rsi
  __int64 v20; // rbx
  __int64 *v21; // rdx
  __int64 v22; // rax
  CCastableCommandQueue *v23; // [rsp+78h] [rbp-190h] BYREF
  int v24; // [rsp+80h] [rbp-188h] BYREF
  __int64 v25; // [rsp+88h] [rbp-180h] BYREF
  __int64 v26; // [rsp+90h] [rbp-178h]
  _BYTE v27[8]; // [rsp+A0h] [rbp-168h] BYREF
  _BYTE v28[232]; // [rsp+A8h] [rbp-160h] BYREF
  __int128 v29; // [rsp+190h] [rbp-78h] BYREF
  __int128 v30; // [rsp+1A0h] [rbp-68h]
  __int128 v31; // [rsp+1B0h] [rbp-58h] BYREF
  __int128 v32; // [rsp+1C0h] [rbp-48h]

  v1 = this;
  v23 = this;
  if ( (Microsoft_Windows_Direct3D12EnableBits & 2) != 0 )
  {
    v2 = (__int64)(*((_QWORD *)this + 25) - *((_QWORD *)this + 24)) >> 3;
    v3 = (__int64)(*((_QWORD *)this + 65) - *((_QWORD *)this + 64)) >> 3;
    v4 = (__int64 *)((char *)this + 536);
    v5 = (char *)this + 536;
    try
    {
      std::vector<unsigned int>::reserve(v5, (unsigned int)(v2 + v3));
      v8 = *((_QWORD *)v1 + 24);
      v6 = *((_QWORD *)v1 + 25);
      while ( v8 != v6 )
      {
        v7 = (_DWORD *)v4[1];
        if ( v7 == (_DWORD *)v4[2] )
        {
          std::vector<unsigned int>::_Emplace_reallocate<unsigned int>(v4);
        }
        else
        {
          *v7 = *(_DWORD *)(*(_QWORD *)v8 + 24LL);
          v4[1] += 4;
        }
        v8 += 8;
      }
      v9 = *((_QWORD *)v1 + 64);
      v10 = *((_QWORD *)v1 + 65);
      while ( v9 != v10 )
      {
        v11 = (_DWORD *)v4[1];
        if ( v11 == (_DWORD *)v4[2] )
        {
          std::vector<unsigned int>::_Emplace_reallocate<unsigned int>(v4);
        }
        else
        {
          *v11 = *(_DWORD *)(*(_QWORD *)v9 + 16LL);
          v4[1] += 4;
        }
        v9 += 8;
      }
      if ( (Microsoft_Windows_Direct3D12EnableBits & 2) != 0 )
        McTemplateU0ppqqQR3dqqqQR8j_EtwEventWriteTransfer(
          *(_DWORD *)v4 + 4 * v2,
          (unsigned int)EventD3D12CreateCommandQueue,
          *(_QWORD *)(*((_QWORD *)v1 + 19) + 768LL),
          *((_QWORD *)v1 + 20),
          *((_DWORD *)v1 + 113),
          v2,
          *v4,
          *((_DWORD *)v1 + 114),
          *((_DWORD *)v1 + 115),
          *((_DWORD *)v1 + 116),
          v3,
          *v4 + 4LL * (unsigned int)v2,
          (__int64)v1 + 484);
    }
    catch ( std::bad_alloc )
    {
      v1 = v23;
    }
  }
  if ( *(_BYTE *)(*((_QWORD *)v1 + 19) + 8100LL) )
  {
    std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(v27);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v27, L"Unnamed ID3D12CommandQueue: Type=");
    v12 = *((_DWORD *)v1 + 113);
    if ( v12 == -1 )
    {
      v13 = "Software";
    }
    else if ( v12 )
    {
      switch ( v12 )
      {
        case 1:
          v13 = "Bundle";
          break;
        case 2:
          v13 = "Compute";
          break;
        case 3:
          v13 = "Copy";
          break;
        case 4:
          v13 = "Video Decode";
          break;
        case 5:
          v13 = "Video Process";
          break;
        case 6:
          v13 = "Video Encode";
          break;
        default:
LABEL_34:
          v23 = 0;
          v24 = 8;
          if ( !(*(unsigned int (__fastcall **)(CCastableCommandQueue *, const struct _GUID *, int *, CCastableCommandQueue **))(*(_QWORD *)v1 + 24LL))(
                  v1,
                  &WKPDID_D3D12UniqueObjectId,
                  &v24,
                  &v23) )
          {
            v14 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v27, ", UniqueId=0x");
            v15 = std::basic_ostream<unsigned short>::operator<<(v14, std::hex);
            v16 = std::basic_ostream<unsigned short>::operator<<(v15, v23);
            std::basic_ostream<unsigned short>::operator<<(v16, std::dec);
          }
          v17 = *((_QWORD *)v1 + 20);
          v18 = *(void (__fastcall **)(__int64, const struct _GUID *, _QWORD, __int128 *))(*(_QWORD *)v17 + 32LL);
          v29 = 0;
          v30 = 0;
          std::wstring::_Construct_empty(&v29);
          std::basic_stringbuf<unsigned short>::_Get_buffer_view(v28, &v25);
          if ( v25 )
            std::wstring::assign(&v29, v25, v26);
          v19 = &v29;
          if ( *((_QWORD *)&v30 + 1) > 7u )
            v19 = (__int128 *)v29;
          v31 = 0;
          v32 = 0;
          std::wstring::_Construct_empty(&v31);
          std::basic_stringbuf<unsigned short>::_Get_buffer_view(v28, &v25);
          if ( v25 )
            std::wstring::assign(&v31, v25, v26);
          v18(v17, &WKPDID_D3DAutoDebugObjectNameW, (unsigned int)(2 * v32), v19);
          std::wstring::_Tidy_deallocate(&v31);
          std::wstring::_Tidy_deallocate(&v29);
          std::basic_ostringstream<unsigned short>::`vbase destructor'(v27);
          goto LABEL_43;
      }
    }
    else
    {
      v13 = "Direct";
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v27, v13);
    goto LABEL_34;
  }
LABEL_43:
  v20 = *((_QWORD *)v1 + 19);
  Smtx_lock_exclusive((_Smtx_t *)(v20 + 4808));
  v21 = *(__int64 **)(*((_QWORD *)v1 + 19) + 4824LL);
  *((_QWORD *)v1 + 23) = v21;
  v22 = *v21;
  *((_QWORD *)v1 + 22) = *v21;
  *(_QWORD *)(v22 + 8) = (char *)v1 + 176;
  *v21 = (__int64)v1 + 176;
  Smtx_unlock_exclusive((_Smtx_t *)(v20 + 4808));
}

```

## disassembly

```asm
0x1800852f8  mov     [rsp+arg_8], rbx
0x1800852fd  mov     [rsp+arg_10], rsi
0x180085302  push    rdi
0x180085303  push    r12
0x180085305  push    r13
0x180085307  push    r14
0x180085309  push    r15
0x18008530b  sub     rsp, 1E0h
0x180085312  mov     rax, cs:__security_cookie
0x180085319  xor     rax, rsp
0x18008531c  mov     [rsp+208h+var_38], rax
0x180085324  mov     rdi, rcx
0x180085327  mov     [rsp+208h+var_190], rcx
0x18008532c  xor     r14d, r14d
0x18008532f  mov     [rsp+208h+var_198], r14d
0x180085334  test    cs:Microsoft_Windows_Direct3D12EnableBits, 2
0x18008533b  jz      loc_18008547D
0x180085341  mov     r15, [rcx+0C8h]
0x180085348  sub     r15, [rcx+0C0h]
0x18008534f  sar     r15, 3
0x180085353  mov     r13, [rcx+208h]
0x18008535a  sub     r13, [rcx+200h]
0x180085361  sar     r13, 3
0x180085365  lea     rbx, [rcx+218h]
0x18008536c  lea     edx, [r15+r13]
0x180085370  mov     rcx, rbx
0x180085373  call    ?reserve@?$vector@IV?$allocator@I@std@@@std@@QEAAX_K@Z; std::vector<uint>::reserve(unsigned __int64)
0x180085378  mov     rsi, [rdi+0C0h]
0x18008537f  mov     r12, [rdi+0C8h]
0x180085386  cmp     rsi, r12
0x180085389  jz      short loc_1800853B6
0x18008538b  mov     r8, [rsi]
0x18008538e  add     r8, 18h
0x180085392  mov     rdx, [rbx+8]
0x180085396  cmp     rdx, [rbx+10h]
0x18008539a  jz      short loc_1800853A8
0x18008539c  mov     eax, [r8]
0x18008539f  mov     [rdx], eax
0x1800853a1  add     qword ptr [rbx+8], 4
0x1800853a6  jmp     short loc_1800853B0
0x1800853a8  mov     rcx, rbx
0x1800853ab  call    ??$_Emplace_reallocate@I@?$vector@IV?$allocator@I@std@@@std@@AEAAPEAIQEAI$$QEAI@Z; std::vector<uint>::_Emplace_reallocate<uint>(uint * const,uint &&)
0x1800853b0  add     rsi, 8
0x1800853b4  jmp     short loc_180085386
0x1800853b6  mov     rsi, [rdi+200h]
0x1800853bd  mov     r12, [rdi+208h]
0x1800853c4  cmp     rsi, r12
0x1800853c7  jz      short loc_1800853F4
0x1800853c9  mov     r8, [rsi]
0x1800853cc  add     r8, 10h
0x1800853d0  mov     rdx, [rbx+8]
0x1800853d4  cmp     rdx, [rbx+10h]
0x1800853d8  jz      short loc_1800853E6
0x1800853da  mov     eax, [r8]
0x1800853dd  mov     [rdx], eax
0x1800853df  add     qword ptr [rbx+8], 4
0x1800853e4  jmp     short loc_1800853EE
0x1800853e6  mov     rcx, rbx
0x1800853e9  call    ??$_Emplace_reallocate@I@?$vector@IV?$allocator@I@std@@@std@@AEAAPEAIQEAI$$QEAI@Z; std::vector<uint>::_Emplace_reallocate<uint>(uint * const,uint &&)
0x1800853ee  add     rsi, 8
0x1800853f2  jmp     short loc_1800853C4
0x1800853f4  test    cs:Microsoft_Windows_Direct3D12EnableBits, 2
0x1800853fb  jz      short loc_180085471
0x1800853fd  mov     r9, [rbx]
0x180085400  lea     rdx, [rdi+1E4h]
0x180085407  mov     eax, r15d
0x18008540a  lea     rcx, [r9+rax*4]
0x18008540e  mov     r8, [rdi+98h]
0x180085415  mov     [rsp+208h+var_1A8], rdx
0x18008541a  mov     [rsp+208h+var_1B0], rcx
0x18008541f  mov     [rsp+208h+var_1B8], r13d
0x180085424  mov     eax, [rdi+1D0h]
0x18008542a  mov     [rsp+208h+var_1C0], eax
0x18008542e  mov     eax, [rdi+1CCh]
0x180085434  mov     [rsp+208h+var_1C8], eax
0x180085438  mov     eax, [rdi+1C8h]
0x18008543e  mov     [rsp+208h+var_1D0], eax
0x180085442  mov     [rsp+208h+var_1D8], r9
0x180085447  mov     [rsp+208h+var_1E0], r15d
0x18008544c  mov     eax, [rdi+1C4h]
0x180085452  mov     [rsp+208h+var_1E8], eax
0x180085456  mov     r9, [rdi+0A0h]
0x18008545d  mov     r8, [r8+300h]
0x180085464  lea     rdx, EventD3D12CreateCommandQueue
0x18008546b  call    McTemplateU0ppqqQR3dqqqQR8j_EtwEventWriteTransfer
0x180085470  nop
0x180085471  jmp     short loc_18008547D
0x180085473  mov     r14d, [rsp+208h+var_198]
0x180085478  mov     rdi, [rsp+208h+var_190]
0x18008547d  mov     rax, [rdi+98h]
0x180085484  cmp     byte ptr [rax+1FA4h], 0
0x18008548b  jz      loc_1800856F3
0x180085491  lea     rcx, [rsp+208h+var_168]
0x180085499  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x18008549e  nop
0x18008549f  lea     rdx, aUnnamedId3d12c; "Unnamed ID3D12CommandQueue: Type="
0x1800854a6  lea     rcx, [rsp+208h+var_168]
0x1800854ae  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1800854b3  mov     eax, [rdi+1C4h]
0x1800854b9  cmp     eax, 0FFFFFFFFh
0x1800854bc  jz      short loc_18008551F
0x1800854be  test    eax, eax
0x1800854c0  jz      short loc_180085516
0x1800854c2  cmp     eax, 1
0x1800854c5  jz      short loc_18008550D
0x1800854c7  cmp     eax, 2
0x1800854ca  jz      short loc_180085504
0x1800854cc  cmp     eax, 3
0x1800854cf  jz      short loc_1800854FB
0x1800854d1  cmp     eax, 4
0x1800854d4  jz      short loc_1800854F2
0x1800854d6  cmp     eax, 5
0x1800854d9  jz      short loc_1800854E9
0x1800854db  cmp     eax, 6
0x1800854de  jnz     short loc_180085533
0x1800854e0  lea     rdx, aVideoEncode; "Video Encode"
0x1800854e7  jmp     short loc_180085526
0x1800854e9  lea     rdx, aVideoProcess; "Video Process"
0x1800854f0  jmp     short loc_180085526
0x1800854f2  lea     rdx, aVideoDecode; "Video Decode"
0x1800854f9  jmp     short loc_180085526
0x1800854fb  lea     rdx, aCopy; "Copy"
0x180085502  jmp     short loc_180085526
0x180085504  lea     rdx, aCompute; "Compute"
0x18008550b  jmp     short loc_180085526
0x18008550d  lea     rdx, aBundle; "Bundle"
0x180085514  jmp     short loc_180085526
0x180085516  lea     rdx, aDirect; "Direct"
0x18008551d  jmp     short loc_180085526
0x18008551f  lea     rdx, aSoftware; "Software"
0x180085526  lea     rcx, [rsp+208h+var_168]
0x18008552e  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x180085533  mov     [rsp+208h+var_190], 0
0x18008553c  mov     [rsp+208h+var_188], 8
0x180085547  mov     rax, [rdi]
0x18008554a  lea     r9, [rsp+208h+var_190]
0x18008554f  lea     r8, [rsp+208h+var_188]
0x180085557  lea     rdx, WKPDID_D3D12UniqueObjectId
0x18008555e  mov     rcx, rdi
0x180085561  mov     rax, [rax+18h]
0x180085565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008556a  test    eax, eax
0x18008556c  jnz     short loc_1800855B0
0x18008556e  lea     rdx, aUniqueid0x; ", UniqueId=0x"
0x180085575  lea     rcx, [rsp+208h+var_168]
0x18008557d  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x180085582  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x180085589  mov     rcx, rax
0x18008558c  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::basic_ostream<ushort>::operator<<(std::ios_base & (*)(std::ios_base &))
0x180085592  mov     rdx, [rsp+208h+var_190]
0x180085597  mov     rcx, rax
0x18008559a  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_K@Z; std::basic_ostream<ushort>::operator<<(unsigned __int64)
0x1800855a0  lea     rdx, ?dec@std@@YAAEAVios_base@1@AEAV21@@Z; std::dec(std::ios_base &)
0x1800855a7  mov     rcx, rax
0x1800855aa  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::basic_ostream<ushort>::operator<<(std::ios_base & (*)(std::ios_base &))
0x1800855b0  mov     rbx, [rdi+0A0h]
0x1800855b7  mov     rax, [rbx]
0x1800855ba  mov     r15, [rax+20h]
0x1800855be  xorps   xmm0, xmm0
0x1800855c1  movups  [rsp+208h+var_78], xmm0
0x1800855c9  xorps   xmm1, xmm1
0x1800855cc  movdqu  [rsp+208h+var_68], xmm1
0x1800855d5  lea     rcx, [rsp+208h+var_78]
0x1800855dd  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x1800855e2  or      r14d, 2
0x1800855e6  mov     [rsp+208h+var_198], r14d
0x1800855eb  lea     rdx, [rsp+208h+var_180]
0x1800855f3  lea     rcx, [rsp+208h+var_160]
0x1800855fb  call    ?_Get_buffer_view@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AU_Buffer_view@12@XZ; std::basic_stringbuf<ushort>::_Get_buffer_view(void)
0x180085600  mov     rdx, [rsp+208h+var_180]
0x180085608  test    rdx, rdx
0x18008560b  jz      short loc_180085622
0x18008560d  mov     r8, [rsp+208h+var_178]
0x180085615  lea     rcx, [rsp+208h+var_78]
0x18008561d  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x180085622  and     r14d, 0FFFFFFFDh
0x180085626  or      r14d, 1
0x18008562a  lea     rsi, [rsp+208h+var_78]
0x180085632  cmp     qword ptr [rsp+208h+var_68+8], 7
0x18008563b  cmova   rsi, qword ptr [rsp+208h+var_78]
0x180085644  xorps   xmm0, xmm0
0x180085647  movups  [rsp+208h+var_58], xmm0
0x18008564f  xorps   xmm1, xmm1
0x180085652  movdqu  [rsp+208h+var_48], xmm1
0x18008565b  lea     rcx, [rsp+208h+var_58]
0x180085663  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x180085668  or      r14d, 8
0x18008566c  mov     [rsp+208h+var_198], r14d
0x180085671  lea     rdx, [rsp+208h+var_180]
0x180085679  lea     rcx, [rsp+208h+var_160]
0x180085681  call    ?_Get_buffer_view@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AU_Buffer_view@12@XZ; std::basic_stringbuf<ushort>::_Get_buffer_view(void)
0x180085686  mov     rdx, [rsp+208h+var_180]
0x18008568e  test    rdx, rdx
0x180085691  jz      short loc_1800856A9
0x180085693  mov     r8, [rsp+208h+var_178]
0x18008569b  lea     rcx, [rsp+208h+var_58]
0x1800856a3  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x1800856a8  nop
0x1800856a9  mov     r8d, dword ptr [rsp+208h+var_48]
0x1800856b1  add     r8d, r8d
0x1800856b4  mov     r9, rsi
0x1800856b7  lea     rdx, WKPDID_D3DAutoDebugObjectNameW
0x1800856be  mov     rcx, rbx
0x1800856c1  mov     rax, r15
0x1800856c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800856c9  nop
0x1800856ca  lea     rcx, [rsp+208h+var_58]
0x1800856d2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800856d7  nop
0x1800856d8  lea     rcx, [rsp+208h+var_78]
0x1800856e0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800856e5  nop
0x1800856e6  lea     rcx, [rsp+208h+var_168]
0x1800856ee  call    ??_D?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_ostringstream<ushort>::`vbase destructor'(void)
0x1800856f3  mov     rbx, [rdi+98h]
0x1800856fa  lea     rcx, [rbx+12C8h]; _Smtx_t *
0x180085701  call    _Smtx_lock_exclusive
0x180085706  lea     r8, [rdi+0B0h]
0x18008570d  mov     rax, [rdi+98h]
0x180085714  mov     rdx, [rax+12D8h]
0x18008571b  mov     [r8+8], rdx
0x18008571f  mov     rax, [rdx]
0x180085722  mov     [r8], rax
0x180085725  mov     [rax+8], r8
0x180085729  mov     [rdx], r8
0x18008572c  lea     rcx, [rbx+12C8h]; _Smtx_t *
0x180085733  call    _Smtx_unlock_exclusive
0x180085738  nop
0x180085739  mov     rcx, [rsp+208h+var_38]
0x180085741  xor     rcx, rsp; StackCookie
0x180085744  call    __security_check_cookie
0x180085749  lea     r11, [rsp+208h+var_28]
0x180085751  mov     rbx, [r11+38h]
0x180085755  mov     rsi, [r11+40h]
0x180085759  mov     rsp, r11
0x18008575c  pop     r15
0x18008575e  pop     r14
0x180085760  pop     r13
0x180085762  pop     r12
0x180085764  pop     rdi
0x180085765  retn
```
