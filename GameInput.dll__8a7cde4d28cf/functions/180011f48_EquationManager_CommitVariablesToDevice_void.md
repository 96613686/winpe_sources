# EquationManager::CommitVariablesToDevice(void)

- ea: `0x180011f48`
- end: `0x180012252`
- name: `?CommitVariablesToDevice@EquationManager@@AEAAJXZ`
- size: `778`
- prototype: `__int64 __fastcall(EquationManager *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001f4d0`

## callees

- `0x180001304`
- `0x18000c11c`
- `0x18000f588`
- `0x180011f48`
- `0x18001be98`
- `0x180022cac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800121a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800121a7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011f7a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011f7a`

## pseudocode

```c
__int64 __fastcall EquationManager::CommitVariablesToDevice(EquationManager *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  EquationManager *v2; // r14
  __int16 v3; // dx
  __int16 v4; // r13
  __m128i si128; // xmm6
  _BYTE *v6; // r15
  __int64 v7; // rdx
  unsigned __int8 v8; // cl
  __int64 v9; // rax
  __int64 *v10; // rbx
  int v11; // ecx
  __int64 *v12; // rsi
  __int64 v13; // r12
  __int64 v14; // r10
  __int64 v15; // r11
  __int64 v16; // rax
  char *v17; // r12
  char v18; // al
  char *v19; // rcx
  void *v20; // rcx
  const struct std::nothrow_t *v21; // rdx
  int v22; // ebx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 v26; // [rsp+48h] [rbp-29h] BYREF
  __m128i v27; // [rsp+50h] [rbp-21h] BYREF
  __int64 v28; // [rsp+60h] [rbp-11h]
  PVOID P[3]; // [rsp+68h] [rbp-9h] BYREF
  char v30; // [rsp+80h] [rbp+Fh]
  EquationManager *v31; // [rsp+D8h] [rbp+67h] BYREF
  int v32; // [rsp+E0h] [rbp+6Fh] BYREF
  const char *v33; // [rsp+E8h] [rbp+77h] BYREF

  v31 = this;
  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 4408);
  v2 = this;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 4408));
  v3 = (unsigned __int16)(((__int64)(unsigned int)(*((_DWORD *)v2 + 1032) - *((_DWORD *)v2 + 1030)) >> 3) + 9) / 0xAu;
  v4 = (unsigned __int8)v3;
  if ( (_BYTE)v3 )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    while ( 1 )
    {
      UsbGipRequest::UsbGipRequest((UsbGipRequest *)P, 0x3Cu, 0xBu);
      v6 = P[0];
      LODWORD(v7) = 10;
      v30 = 0;
      v8 = 0;
      do
      {
        *(_WORD *)&v6[v8 + 20] = -1;
        v9 = v8;
        v8 += 6;
        *(_DWORD *)&v6[v9 + 22] = 0;
        v7 = (unsigned int)(v7 - 1);
      }
      while ( (_DWORD)v7 );
      v10 = (__int64 *)*((_QWORD *)v2 + 515);
      v11 = 0;
      v12 = (__int64 *)*((_QWORD *)v2 + 516);
      v13 = -1;
      LOBYTE(v1) = v30;
      v27 = si128;
      v14 = si128.m128i_i64[1];
      v15 = si128.m128i_i64[0];
      v32 = 0;
      v28 = -1;
      while ( v10 != v12 )
      {
        v16 = *v10;
        v26 = *v10;
        if ( (unsigned __int16)v11 >= 0xAu )
        {
          if ( v14 == v13 )
          {
            v17 = (char *)&v26 - v15;
            v18 = utl::vector<utl::pair<unsigned short,unsigned int>,utl::allocator<utl::pair<unsigned short,unsigned int>>>::_Grow(&v27);
            v14 = v27.m128i_i64[1];
            v15 = v27.m128i_i64[0];
            if ( v18 )
            {
              v19 = (char *)&v26;
              if ( (unsigned __int64)v17 < v27.m128i_i64[1] - v27.m128i_i64[0] )
                v19 = &v17[v27.m128i_i64[0]];
              *(_WORD *)v27.m128i_i64[1] = *(_WORD *)v19;
              *(_DWORD *)(v14 + 4) = *((_DWORD *)v19 + 1);
              v14 += 8;
              v27.m128i_i64[1] = v14;
            }
            v11 = v32;
            v13 = v28;
          }
          else
          {
            *(_WORD *)v14 = v16;
            *(_DWORD *)(v14 + 4) = HIDWORD(v16);
            v14 += 8;
            v27.m128i_i64[1] = v14;
          }
        }
        else
        {
          if ( (unsigned __int8)v1 < 0xAu )
          {
            v7 = 512;
            if ( (unsigned __int16)v16 < 0x200u )
            {
              LOBYTE(v11) = 2 * (_BYTE)v1;
              v7 = (unsigned int)(v11 + (_DWORD)v1);
              LOBYTE(v7) = 6 * (_BYTE)v1;
              v6[(unsigned __int8)v7 + 21] = BYTE1(v16);
              v11 = v32;
              v6[(unsigned __int8)v7 + 20] = v16;
              v6[(unsigned __int8)v7 + 25] = HIBYTE(v16);
              v6[(unsigned __int8)v7 + 24] = BYTE6(v16);
              v6[(unsigned __int8)v7 + 23] = BYTE5(v16);
              LOBYTE(v1) = (_BYTE)v1 + 1;
              v6[(unsigned __int8)v7 + 22] = BYTE4(v16);
              v30 = (char)v1;
            }
          }
          LOWORD(v11) = v11 + 1;
          v32 = v11;
        }
        ++v10;
      }
      v2 = v31;
      v20 = (void *)*((_QWORD *)v31 + 515);
      v1 = (struct _RTL_CRITICAL_SECTION *)((char *)v31 + 4408);
      *((_QWORD *)v31 + 515) = v15;
      *((_QWORD *)v2 + 516) = v14;
      *((_QWORD *)v2 + 517) = v13;
      if ( v20 != (void *)-1LL )
        operator delete(v20, (const struct std::nothrow_t *)v7);
      v22 = EquationManager::SendRequest(v2, (const struct UsbGipRequest *)P);
      if ( v22 < 0 )
        break;
      --v4;
      if ( P[0] != (PVOID)-1LL )
        operator delete(P[0], v21);
      if ( !v4 )
        goto LABEL_26;
    }
    if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
    {
      LODWORD(v31) = v22;
      v33 = "onecore\\xbox\\gameinput\\feedback\\gipequationmanager\\EquationManager.cpp";
      v32 = 299;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069018,
        (unsigned __int8 *)byte_18005C249,
        v23,
        v24,
        (__int64 **)&v33,
        (__int64)&v32,
        (__int64)&v31);
    }
    if ( P[0] != (PVOID)-1LL )
      operator delete(P[0], v21);
  }
  else
  {
LABEL_26:
    v22 = 0;
  }
  LeaveCriticalSection(v1);
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x180011f48  mov     rax, rsp
0x180011f4b  mov     [rax+20h], rbx
0x180011f4f  mov     [rax+8], rcx
0x180011f53  push    rbp
0x180011f54  push    rsi
0x180011f55  push    rdi
0x180011f56  push    r12
0x180011f58  push    r13
0x180011f5a  push    r14
0x180011f5c  push    r15
0x180011f5e  lea     rbp, [rax-5Fh]
0x180011f62  sub     rsp, 90h
0x180011f69  lea     rdi, [rcx+1138h]
0x180011f70  movaps  xmmword ptr [rax-48h], xmm6
0x180011f74  mov     r14, rcx
0x180011f77  mov     rcx, rdi; lpCriticalSection
0x180011f7a  call    cs:__imp_EnterCriticalSection
0x180011f81  nop     dword ptr [rax+rax+00h]
0x180011f86  mov     eax, [r14+1020h]
0x180011f8d  xor     esi, esi
0x180011f8f  sub     eax, [r14+1018h]
0x180011f96  sar     rax, 3
0x180011f9a  add     ax, 9
0x180011f9e  movzx   ecx, ax
0x180011fa1  mov     eax, 0CCCCCCCDh
0x180011fa6  mul     ecx
0x180011fa8  shr     edx, 3
0x180011fab  movzx   r13d, dl
0x180011faf  test    dl, dl
0x180011fb1  jz      loc_1800121A2
0x180011fb7  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180011fbf  lea     ebx, [rsi+1]
0x180011fc2  mov     r8b, 0Bh; unsigned __int8
0x180011fc5  lea     rcx, [rbp+57h+P]; this
0x180011fc9  mov     edx, 3Ch ; '<'; unsigned int
0x180011fce  call    ??0UsbGipRequest@@QEAA@IE@Z; UsbGipRequest::UsbGipRequest(uint,uchar)
0x180011fd3  mov     r15, [rbp+57h+P]
0x180011fd7  mov     r8d, 0Ah
0x180011fdd  mov     edx, r8d
0x180011fe0  mov     [rbp+57h+var_48], sil
0x180011fe4  mov     cl, sil
0x180011fe7  movzx   eax, cl
0x180011fea  mov     word ptr [rax+r15+14h], 0FFFFh
0x180011ff2  movzx   eax, cl
0x180011ff5  add     cl, 6
0x180011ff8  mov     dword ptr [rax+r15+16h], 0
0x180012001  sub     edx, ebx; struct std::nothrow_t *
0x180012003  jnz     short loc_180011FE7
0x180012005  mov     rbx, [r14+1018h]
0x18001200c  mov     ecx, esi
0x18001200e  mov     rsi, [r14+1020h]
0x180012015  or      r12, 0FFFFFFFFFFFFFFFFh
0x180012019  mov     dil, [rbp+57h+var_48]
0x18001201d  lea     r14d, [rdx+1]
0x180012021  movdqu  [rbp+57h+var_78], xmm6
0x180012026  mov     r10, qword ptr [rbp+57h+var_78+8]
0x18001202a  mov     r11, qword ptr [rbp+57h+var_78]
0x18001202e  mov     [rbp+57h+arg_8], ecx
0x180012031  mov     [rbp+57h+var_68], r12
0x180012035  cmp     rbx, rsi
0x180012038  jz      loc_180012135
0x18001203e  mov     rax, [rbx]
0x180012041  mov     [rbp+57h+var_80], rax
0x180012045  cmp     cx, r8w
0x180012049  jnb     short loc_1800120BF
0x18001204b  cmp     dil, r8b
0x18001204e  jnb     short loc_1800120B6
0x180012050  mov     edx, 200h
0x180012055  cmp     ax, dx
0x180012058  jnb     short loc_1800120B6
0x18001205a  mov     r9, rax
0x18001205d  mov     cl, dil
0x180012060  add     cl, cl
0x180012062  shr     r9, 20h
0x180012066  lea     edx, [rcx+rdi]
0x180012069  movzx   ecx, ax
0x18001206c  shr     cx, 8
0x180012070  add     dl, dl
0x180012072  movzx   r8d, dl
0x180012076  mov     [r8+r15+15h], cl
0x18001207b  mov     ecx, [rbp+57h+arg_8]
0x18001207e  mov     [r8+r15+14h], al
0x180012083  mov     eax, r9d
0x180012086  shr     eax, 18h
0x180012089  mov     [r8+r15+19h], al
0x18001208e  mov     eax, r9d
0x180012091  shr     eax, 10h
0x180012094  mov     [r8+r15+18h], al
0x180012099  mov     eax, r9d
0x18001209c  shr     eax, 8
0x18001209f  mov     [r8+r15+17h], al
0x1800120a4  add     dil, r14b
0x1800120a7  mov     [r8+r15+16h], r9b
0x1800120ac  mov     r8d, 0Ah
0x1800120b2  mov     [rbp+57h+var_48], dil
0x1800120b6  add     cx, r14w
0x1800120ba  mov     [rbp+57h+arg_8], ecx
0x1800120bd  jmp     short loc_18001212C
0x1800120bf  cmp     r10, r12
0x1800120c2  jz      short loc_1800120DA
0x1800120c4  mov     [r10], ax
0x1800120c8  shr     rax, 20h
0x1800120cc  mov     [r10+4], eax
0x1800120d0  add     r10, 8
0x1800120d4  mov     qword ptr [rbp+57h+var_78+8], r10
0x1800120d8  jmp     short loc_18001212C
0x1800120da  lea     r12, [rbp+57h+var_80]
0x1800120de  lea     rcx, [rbp+57h+var_78]
0x1800120e2  sub     r12, r11
0x1800120e5  call    ?_Grow@?$vector@U?$pair@GI@utl@@V?$allocator@U?$pair@GI@utl@@@2@@utl@@AEAA_NXZ; utl::vector<utl::pair<ushort,uint>,utl::allocator<utl::pair<ushort,uint>>>::_Grow(void)
0x1800120ea  mov     r10, qword ptr [rbp+57h+var_78+8]
0x1800120ee  mov     r11, qword ptr [rbp+57h+var_78]
0x1800120f2  test    al, al
0x1800120f4  jz      short loc_18001211F
0x1800120f6  mov     rax, r10
0x1800120f9  lea     rcx, [rbp+57h+var_80]
0x1800120fd  sub     rax, r11
0x180012100  cmp     r12, rax
0x180012103  jnb     short loc_180012109
0x180012105  lea     rcx, [r12+r11]
0x180012109  movzx   eax, word ptr [rcx]
0x18001210c  mov     [r10], ax
0x180012110  mov     eax, [rcx+4]
0x180012113  mov     [r10+4], eax
0x180012117  add     r10, 8
0x18001211b  mov     qword ptr [rbp+57h+var_78+8], r10
0x18001211f  mov     ecx, [rbp+57h+arg_8]
0x180012122  mov     r8d, 0Ah
0x180012128  mov     r12, [rbp+57h+var_68]
0x18001212c  add     rbx, 8
0x180012130  jmp     loc_180012035
0x180012135  mov     r14, [rbp+57h+arg_0]
0x180012139  mov     rcx, [r14+1018h]; P
0x180012140  lea     rdi, [r14+1138h]
0x180012147  mov     [r14+1018h], r11
0x18001214e  mov     [r14+1020h], r10
0x180012155  mov     [r14+1028h], r12
0x18001215c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180012160  jz      short loc_180012167
0x180012162  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012167  lea     rdx, [rbp+57h+P]; struct UsbGipRequest *
0x18001216b  mov     rcx, r14; this
0x18001216e  call    ?SendRequest@EquationManager@@AEAAJAEBVUsbGipRequest@@@Z; EquationManager::SendRequest(UsbGipRequest const &)
0x180012173  xor     esi, esi
0x180012175  mov     ebx, eax
0x180012177  test    eax, eax
0x180012179  js      short loc_1800121D6
0x18001217b  mov     rcx, [rbp+57h+P]; P
0x18001217f  mov     eax, 0FFFFh
0x180012184  add     r13w, ax
0x180012188  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001218c  jz      short loc_180012193
0x18001218e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012193  mov     ebx, 1
0x180012198  test    r13w, r13w
0x18001219c  jnz     loc_180011FC2
0x1800121a2  mov     ebx, esi
0x1800121a4  mov     rcx, rdi; lpCriticalSection
0x1800121a7  call    cs:__imp_LeaveCriticalSection
0x1800121ae  nop     dword ptr [rax+rax+00h]
0x1800121b3  lea     r11, [rsp+0C0h+var_30]
0x1800121bb  mov     eax, ebx
0x1800121bd  mov     rbx, [r11+58h]
0x1800121c1  movaps  xmm6, xmmword ptr [r11-10h]
0x1800121c6  mov     rsp, r11
0x1800121c9  pop     r15
0x1800121cb  pop     r14
0x1800121cd  pop     r13
0x1800121cf  pop     r12
0x1800121d1  pop     rdi
0x1800121d2  pop     rsi
0x1800121d3  pop     rbp
0x1800121d4  retn
0x1800121d6  mov     eax, cs:dword_180069000
0x1800121dc  cmp     eax, 2
0x1800121df  jbe     short loc_18001223A
0x1800121e1  mov     rcx, cs:qword_180069018
0x1800121e8  mov     rax, cs:qword_180069010
0x1800121ef  test    al, 8
0x1800121f1  jz      short loc_18001223A
0x1800121f3  mov     rax, rcx
0x1800121f6  and     eax, 8
0x1800121f9  cmp     rax, rcx
0x1800121fc  jnz     short loc_18001223A
0x1800121fe  lea     rax, aOnecoreXboxGam_27; "onecore\\xbox\\gameinput\\feedback\\gip"...
0x180012205  mov     dword ptr [rbp+57h+arg_0], ebx
0x180012208  mov     [rbp+57h+arg_10], rax
0x18001220c  lea     rdx, byte_18005C249
0x180012213  lea     rax, [rbp+57h+arg_0]
0x180012217  mov     [rbp+57h+arg_8], 12Bh
0x18001221e  mov     [rsp+0C0h+var_90], rax
0x180012223  lea     rax, [rbp+57h+arg_8]
0x180012227  mov     [rsp+0C0h+var_98], rax
0x18001222c  lea     rax, [rbp+57h+arg_10]
0x180012230  mov     [rsp+0C0h+var_A0], rax
0x180012235  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001223a  mov     rcx, [rbp+57h+P]; P
0x18001223e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180012242  jz      loc_1800121A4
0x180012248  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001224d  jmp     loc_1800121A4
```
