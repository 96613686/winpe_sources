# CResponse::WriteResponse(int)

- ea: `0x180017ac0`
- end: `0x180017fba`
- name: `?WriteResponse@CResponse@@QEAAJH@Z`
- size: `1274`
- prototype: `__int64 __fastcall(CResponse *__hidden this, int)`
- caller_count: `6`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ca50`
- `0x180018de0`
- `0x180051460`
- `0x180051ca0`
- `0x180052fe0`
- `0x180053428`

## callees

- `0x180017ac0`
- `0x180017fc0`
- `0x1800183f0`
- `0x180023dd0`
- `0x1800406b0`
- `0x180051764`

## import_xrefs

- `msvcrt!_stricmp` at `0x180017c2b`
- `msvcrt!_stricmp` at `0x180017c2b`
- `KERNEL32!HeapFree` at `0x180017efb`
- `KERNEL32!HeapFree` at `0x180017f14`
- `KERNEL32!HeapFree` at `0x180017efb`
- `KERNEL32!HeapFree` at `0x180017f14`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180017dfe`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180017e6e`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180017dfe`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180017e6e`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180017cca`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180017cca`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180017cdd`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180017cdd`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180017b3d`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180017b3d`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180017ba6`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180017f5c`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180017f7e`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180017faa`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180017ba6`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180017f5c`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180017f7e`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180017faa`

## pseudocode

```c
__int64 __fastcall CResponse::WriteResponse(CResponse *this, int a2)
{
  __int64 v3; // rax
  __int64 v5; // rcx
  __int64 v6; // r12
  __int64 v7; // rax
  int v8; // ebx
  __int64 v10; // rcx
  BOOL v11; // eax
  int v12; // eax
  bool v13; // zf
  struct WSABUF_VECTORS *v14; // r9
  int v15; // edi
  __int64 v16; // rdi
  unsigned int v17; // r14d
  unsigned int v18; // r8d
  __int64 v19; // r10
  int v20; // r9d
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // r8
  unsigned int v24; // edx
  void *v25; // r8
  CIsapiReqInfo *v26; // rcx
  void (*v27)(void *); // rdx
  _DWORD *v28; // rax
  _DWORD *v29; // rdx
  __int64 v30; // rax
  _QWORD *v31; // rbx
  int v32; // edi
  _DWORD *v33; // rax
  __int64 v34; // rcx
  CResponseBuffer *v35; // rcx
  __int128 v36; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v37; // [rsp+40h] [rbp-C0h]
  struct _HSE_SEND_HEADER_EX_INFO lpMem; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v39; // [rsp+68h] [rbp-98h]
  _BYTE v40[56]; // [rsp+78h] [rbp-88h] BYREF
  _OWORD v41[8]; // [rsp+B0h] [rbp-50h] BYREF

  v37 = 0;
  v3 = *((_QWORD *)this + 7);
  v39 = 0;
  v5 = *(_QWORD *)(v3 + 152);
  v36 = 0;
  v6 = *(_QWORD *)(v5 + 16);
  memset(v41, 0, sizeof(v41));
  BUFFER::BUFFER((BUFFER *)v40, (unsigned __int8 *)v41, 0x80u);
  if ( (*((_BYTE *)this + 40) & 1) == 0 )
  {
    ExceptionId(&IID_IResponse, 0x1770u, 0x6Fu, 0);
    BUFFER::~BUFFER((BUFFER *)v40);
    return 2147500037LL;
  }
  v7 = *((_QWORD *)this + 7);
  if ( (*(_BYTE *)(v7 + 280) & 6) != 0 )
  {
    BUFFER::~BUFFER((BUFFER *)v40);
    return 0;
  }
  v8 = 0;
  v13 = (*(_DWORD *)(*(_QWORD *)(v7 + 48) + 52LL) & 0x800) == 0;
  memset(&lpMem, 0, sizeof(lpMem));
  if ( !v13 || (v8 = CResponse::ConstructHeaders(this, &lpMem), v8 >= 0) )
  {
    v10 = *((_QWORD *)this + 7);
    DWORD2(v39) = 0;
    v11 = *(_DWORD *)(v10 + 292) & 1;
    *(_QWORD *)&v39 = 0;
    v13 = (*((_BYTE *)this + 40) & 1) == 0;
    lpMem.fKeepConn = v11;
    if ( v13 )
    {
      ExceptionId(&IID_IResponse, 0x1770u, 0x6Fu, 0);
      v10 = *((_QWORD *)this + 7);
    }
    else
    {
      v12 = *(_DWORD *)(v10 + 160);
      if ( v12 )
      {
        v13 = v12 == 2;
      }
      else
      {
        *(_DWORD *)(*((_QWORD *)this + 7) + 160LL) = 2
                                                   - (_stricmp(
                                                        *(const char **)(*(_QWORD *)(*(_QWORD *)(v10 + 48) + 8LL) + 104LL),
                                                        "HEAD") != 0);
        v10 = *((_QWORD *)this + 7);
        v13 = *(_DWORD *)(v10 + 160) == 2;
      }
      if ( v13 )
      {
        if ( (*(_DWORD *)(*(_QWORD *)(v10 + 48) + 52LL) & 0x800) != 0 )
        {
LABEL_56:
          BUFFER::~BUFFER((BUFFER *)v40);
          return (unsigned int)v8;
        }
        v14 = 0;
        v15 = 0;
        goto LABEL_33;
      }
    }
    if ( *(char *)(v10 + 280) < 0 )
    {
      v16 = *(_QWORD *)(*(_QWORD *)(v10 + 152) + 8LL);
      if ( v16 )
      {
        v17 = *(_DWORD *)(v16 + 2100);
        if ( v17 )
        {
          DWORD2(v39) = *(_DWORD *)(v16 + 2100);
          if ( !BUFFER::Resize((BUFFER *)v40, 16 * v17) )
            goto LABEL_47;
          *(_QWORD *)&v39 = BUFFER::QueryPtr((BUFFER *)v40);
          v18 = 0;
          v19 = v39;
          do
          {
            if ( v18 == *(_DWORD *)(v16 + 2100) - 1 )
              v20 = *(_DWORD *)(v16 + 2108);
            else
              v20 = 2048;
            v21 = 2LL * v18;
            v22 = v18++;
            *(_DWORD *)(v19 + 8 * v21) = v20;
            *(_QWORD *)(v19 + 8 * v21 + 8) = *(_QWORD *)(*(_QWORD *)(v16 + 2080) + 8 * v22);
          }
          while ( v18 < v17 );
        }
      }
    }
    v10 = *((_QWORD *)this + 7);
    v15 = 1;
    v23 = **(_QWORD **)(v10 + 152);
    v24 = *(_DWORD *)(v23 + 20) + 1;
    if ( (*(_BYTE *)(v23 + 24) & 1) == 0 )
      v24 = *(_DWORD *)(v23 + 20);
    if ( v24 <= 0x80 )
    {
      if ( v24 )
      {
        LODWORD(v37) = v24;
        *(_QWORD *)&v36 = v23 + 32;
      }
      else
      {
        *(_QWORD *)&v36 = 0;
        LODWORD(v37) = 0;
      }
      *((_QWORD *)&v36 + 1) = 0;
      HIDWORD(v37) = 0;
    }
    else
    {
      LODWORD(v37) = 128;
      *(_QWORD *)&v36 = v23 + 32;
      *((_QWORD *)&v36 + 1) = *(_QWORD *)(v23 + 8);
      HIDWORD(v37) = v24 - 128;
    }
    v14 = (struct WSABUF_VECTORS *)&v36;
LABEL_33:
    if ( a2 )
      v25 = *(void **)(v10 + 152);
    else
      v25 = 0;
    v26 = *(CIsapiReqInfo **)(v10 + 48);
    v27 = (void (*)(void *))CResponseBufferSet::SendResponseCompletion;
    if ( !a2 )
      v27 = 0;
    if ( (unsigned int)CIsapiReqInfo::SendClientResponse(
                         v26,
                         a2,
                         (struct _HSE_SEND_ENTIRE_RESPONSE_INFO *)&lpMem,
                         v14,
                         v27,
                         v25) )
    {
      if ( a2 )
      {
        v28 = ALLOC_CACHE_HANDLER::Alloc(CResponseBufferSet::sm_pach);
        v29 = v28;
        if ( v28 )
        {
          v28[42] &= 0xFFFFFFFC;
          *((_QWORD *)v28 + 3) = 0;
          *((_QWORD *)v28 + 19) = v28 + 6;
          *(_QWORD *)v28 = 0;
          *((_QWORD *)v28 + 1) = 0;
          *((_QWORD *)v28 + 2) = 0;
          v28[40] = 0;
          v28[41] = 16;
        }
        else
        {
          v29 = 0;
        }
        *(_QWORD *)(*((_QWORD *)this + 7) + 152LL) = v29;
        v30 = *((_QWORD *)this + 7);
        v31 = *(_QWORD **)(v30 + 152);
        if ( v31 )
        {
          v32 = *(_DWORD *)(v30 + 288);
          v33 = ALLOC_CACHE_HANDLER::Alloc(CResponseBuffer::sm_pach);
          if ( v33 )
          {
            v33[6] &= ~1u;
            *((_QWORD *)v33 + 260) = v33 + 522;
            *((_QWORD *)v33 + 261) = 0;
            *((_QWORD *)v33 + 1) = 0;
            *((_QWORD *)v33 + 2) = 0;
            v33[7] = 0;
            *((_QWORD *)v33 + 262) = 1;
            *((_QWORD *)v33 + 263) = 0;
            *v31 = v33;
            *(_QWORD *)v33 = v31;
            v8 = 0;
            v33[528] = v32;
            v33[529] = 1;
            v34 = *(_QWORD *)(*((_QWORD *)this + 7) + 152LL);
            *(_DWORD *)(v34 + 168) &= ~1u;
            *(_QWORD *)(v34 + 16) = v6;
            goto LABEL_56;
          }
          *v31 = 0;
        }
LABEL_47:
        v8 = -2147024882;
        if ( lpMem.pszStatus )
          HeapFree(g_hDenaliHeap, 0, (LPVOID)lpMem.pszStatus);
        if ( lpMem.pszHeader )
          HeapFree(g_hDenaliHeap, 0, (LPVOID)lpMem.pszHeader);
        goto LABEL_56;
      }
    }
    else
    {
      *(_DWORD *)(*((_QWORD *)this + 7) + 280LL) |= 2u;
    }
    if ( v15 )
    {
      v35 = *(CResponseBuffer **)(*(_QWORD *)(*((_QWORD *)this + 7) + 152LL) + 8LL);
      if ( v35 )
        CResponseBuffer::Clear(v35);
      CResponseBuffer::Clear(**(CResponseBuffer ***)(*((_QWORD *)this + 7) + 152LL));
    }
    goto LABEL_56;
  }
  BUFFER::~BUFFER((BUFFER *)v40);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180017ac0  push    rbp
0x180017ac2  push    rsi
0x180017ac3  push    r12
0x180017ac5  push    r15
0x180017ac7  lea     rbp, [rsp-48h]
0x180017acc  sub     rsp, 148h
0x180017ad3  mov     rax, cs:__security_cookie
0x180017ada  xor     rax, rsp
0x180017add  mov     [rbp+60h+var_30], rax
0x180017ae1  xorps   xmm0, xmm0
0x180017ae4  xor     eax, eax
0x180017ae6  mov     rsi, rcx
0x180017ae9  mov     [rsp+160h+var_120], rax
0x180017aee  mov     rax, [rcx+38h]
0x180017af2  mov     r15d, edx
0x180017af5  xorps   xmm1, xmm1
0x180017af8  lea     rdx, [rbp+60h+var_B0]
0x180017afc  mov     r8d, 80h
0x180017b02  movdqu  [rsp+160h+var_F8], xmm0
0x180017b08  mov     rcx, [rax+98h]
0x180017b0f  movups  [rsp+160h+var_130], xmm1
0x180017b14  mov     r12, [rcx+10h]
0x180017b18  lea     rcx, [rsp+160h+var_E8]
0x180017b1d  movups  [rbp+60h+var_B0], xmm0
0x180017b21  movups  [rbp+60h+var_A0], xmm0
0x180017b25  movups  [rbp+60h+var_90], xmm0
0x180017b29  movups  [rbp+60h+var_80], xmm0
0x180017b2d  movups  [rbp+60h+var_70], xmm0
0x180017b31  movups  [rbp+60h+var_60], xmm0
0x180017b35  movups  [rbp+60h+var_50], xmm0
0x180017b39  movups  [rbp+60h+var_40], xmm0
0x180017b3d  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x180017b43  test    byte ptr [rsi+28h], 1
0x180017b47  jz      loc_180017F8B
0x180017b4d  mov     rax, [rsi+38h]
0x180017b51  test    byte ptr [rax+118h], 6
0x180017b58  jnz     loc_180017F79
0x180017b5e  mov     rax, [rax+30h]
0x180017b62  xorps   xmm0, xmm0
0x180017b65  mov     [rsp+160h+arg_8], rbx
0x180017b6d  mov     [rsp+160h+arg_18], r13
0x180017b75  xor     r13d, r13d
0x180017b78  mov     ebx, r13d
0x180017b7b  test    dword ptr [rax+34h], 800h
0x180017b82  movups  xmmword ptr [rsp+160h+lpMem], xmm0
0x180017b87  movups  [rsp+160h+var_108], xmm0
0x180017b8c  jnz     short loc_180017BD8
0x180017b8e  lea     rdx, [rsp+160h+lpMem]; struct _HSE_SEND_HEADER_EX_INFO *
0x180017b93  mov     rcx, rsi; this
0x180017b96  call    ?ConstructHeaders@CResponse@@QEAAJPEAU_HSE_SEND_HEADER_EX_INFO@@@Z; CResponse::ConstructHeaders(_HSE_SEND_HEADER_EX_INFO *)
0x180017b9b  mov     ebx, eax
0x180017b9d  test    eax, eax
0x180017b9f  jns     short loc_180017BD8
0x180017ba1  lea     rcx, [rsp+160h+var_E8]
0x180017ba6  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180017bac  mov     eax, ebx
0x180017bae  mov     rbx, [rsp+160h+arg_8]
0x180017bb6  mov     r13, [rsp+160h+arg_18]
0x180017bbe  mov     rcx, [rbp+60h+var_30]
0x180017bc2  xor     rcx, rsp; StackCookie
0x180017bc5  call    __security_check_cookie
0x180017bca  add     rsp, 148h
0x180017bd1  pop     r15
0x180017bd3  pop     r12
0x180017bd5  pop     rsi
0x180017bd6  pop     rbp
0x180017bd7  retn
0x180017bd8  mov     rcx, [rsi+38h]
0x180017bdc  mov     [rsp+160h+arg_10], rdi
0x180017be4  mov     [rsp+160h+var_20], r14
0x180017bec  mov     dword ptr [rsp+160h+var_F8+8], r13d
0x180017bf1  mov     eax, [rcx+124h]
0x180017bf7  and     eax, 1
0x180017bfa  mov     qword ptr [rsp+160h+var_F8], r13
0x180017bff  test    byte ptr [rsi+28h], 1
0x180017c03  mov     dword ptr [rsp+160h+var_108+8], eax
0x180017c07  jz      short loc_180017C6B
0x180017c09  mov     eax, [rcx+0A0h]
0x180017c0f  test    eax, eax
0x180017c11  jz      short loc_180017C18
0x180017c13  cmp     eax, 2
0x180017c16  jmp     short loc_180017C4D
0x180017c18  mov     rax, [rcx+30h]
0x180017c1c  lea     rdx, aHead; "HEAD"
0x180017c23  mov     rcx, [rax+8]
0x180017c27  mov     rcx, [rcx+68h]; String1
0x180017c2b  call    cs:__imp__stricmp
0x180017c31  neg     eax
0x180017c33  mov     rax, [rsi+38h]
0x180017c37  sbb     ecx, ecx
0x180017c39  add     ecx, 2
0x180017c3c  mov     [rax+0A0h], ecx
0x180017c42  mov     rcx, [rsi+38h]
0x180017c46  cmp     dword ptr [rcx+0A0h], 2
0x180017c4d  jnz     short loc_180017C89
0x180017c4f  mov     rax, [rcx+30h]
0x180017c53  test    dword ptr [rax+34h], 800h
0x180017c5a  jnz     loc_180017F57
0x180017c60  mov     r9, r13
0x180017c63  mov     edi, r13d
0x180017c66  jmp     loc_180017DAC
0x180017c6b  xor     r9d, r9d; int
0x180017c6e  lea     rcx, IID_IResponse; struct _GUID *
0x180017c75  mov     edx, 1770h; unsigned int
0x180017c7a  mov     r8d, 6Fh ; 'o'; unsigned int
0x180017c80  call    ?ExceptionId@@YAXAEBU_GUID@@IIJ@Z; ExceptionId(_GUID const &,uint,uint,long)
0x180017c85  mov     rcx, [rsi+38h]
0x180017c89  test    byte ptr [rcx+118h], 80h
0x180017c90  jz      loc_180017D34
0x180017c96  mov     rax, [rcx+98h]
0x180017c9d  mov     rdi, [rax+8]
0x180017ca1  test    rdi, rdi
0x180017ca4  jz      loc_180017D34
0x180017caa  mov     r14d, [rdi+834h]
0x180017cb1  test    r14d, r14d
0x180017cb4  jz      loc_180017D34
0x180017cba  mov     edx, r14d
0x180017cbd  mov     dword ptr [rsp+160h+var_F8+8], r14d
0x180017cc2  shl     edx, 4
0x180017cc5  lea     rcx, [rsp+160h+var_E8]
0x180017cca  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180017cd0  test    al, al
0x180017cd2  jz      loc_180017EE3
0x180017cd8  lea     rcx, [rsp+160h+var_E8]
0x180017cdd  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180017ce3  mov     qword ptr [rsp+160h+var_F8], rax
0x180017ce8  mov     r8d, r13d
0x180017ceb  mov     r10, rax
0x180017cee  test    r14d, r14d
0x180017cf1  jz      short loc_180017D34
0x180017cf3  mov     ecx, [rdi+834h]
0x180017cf9  dec     ecx
0x180017cfb  cmp     r8d, ecx
0x180017cfe  jnz     short loc_180017D09
0x180017d00  mov     r9d, [rdi+83Ch]
0x180017d07  jmp     short loc_180017D0F
0x180017d09  mov     r9d, 800h
0x180017d0f  mov     edx, r8d
0x180017d12  add     rdx, rdx
0x180017d15  mov     ecx, r8d
0x180017d18  inc     r8d
0x180017d1b  mov     [r10+rdx*8], r9d
0x180017d1f  mov     rax, [rdi+820h]
0x180017d26  mov     rcx, [rax+rcx*8]
0x180017d2a  mov     [r10+rdx*8+8], rcx
0x180017d2f  cmp     r8d, r14d
0x180017d32  jb      short loc_180017CF3
0x180017d34  mov     rcx, [rsi+38h]
0x180017d38  mov     edi, 1
0x180017d3d  mov     rax, [rcx+98h]
0x180017d44  mov     r8, [rax]
0x180017d47  mov     eax, [r8+14h]
0x180017d4b  test    [r8+18h], dil
0x180017d4f  lea     edx, [rax+1]
0x180017d52  cmovz   edx, eax
0x180017d55  cmp     edx, 80h
0x180017d5b  jbe     short loc_180017D80
0x180017d5d  lea     rax, [r8+20h]
0x180017d61  mov     dword ptr [rsp+160h+var_120], 80h
0x180017d69  mov     qword ptr [rsp+160h+var_130], rax
0x180017d6e  mov     rax, [r8+8]
0x180017d72  mov     qword ptr [rsp+160h+var_130+8], rax
0x180017d77  lea     eax, [rdx-80h]
0x180017d7a  mov     dword ptr [rsp+160h+var_120+4], eax
0x180017d7e  jmp     short loc_180017DA7
0x180017d80  test    edx, edx
0x180017d82  jz      short loc_180017D93
0x180017d84  lea     rax, [r8+20h]
0x180017d88  mov     dword ptr [rsp+160h+var_120], edx
0x180017d8c  mov     qword ptr [rsp+160h+var_130], rax
0x180017d91  jmp     short loc_180017D9D
0x180017d93  mov     qword ptr [rsp+160h+var_130], r13
0x180017d98  mov     dword ptr [rsp+160h+var_120], r13d
0x180017d9d  mov     qword ptr [rsp+160h+var_130+8], r13
0x180017da2  mov     dword ptr [rsp+160h+var_120+4], r13d
0x180017da7  lea     r9, [rsp+160h+var_130]; struct WSABUF_VECTORS *
0x180017dac  test    r15d, r15d
0x180017daf  jz      short loc_180017DBA
0x180017db1  mov     r8, [rcx+98h]
0x180017db8  jmp     short loc_180017DBD
0x180017dba  mov     r8, r13
0x180017dbd  mov     rcx, [rcx+30h]; this
0x180017dc1  lea     rdx, ?SendResponseCompletion@CResponseBufferSet@@SAXPEAX@Z; CResponseBufferSet::SendResponseCompletion(void *)
0x180017dc8  mov     [rsp+160h+var_138], r8; void *
0x180017dcd  test    r15d, r15d
0x180017dd0  lea     r8, [rsp+160h+lpMem]; struct _HSE_SEND_ENTIRE_RESPONSE_INFO *
0x180017dd5  cmovz   rdx, r13
0x180017dd9  mov     [rsp+160h+var_140], rdx; void (*)(void *)
0x180017dde  mov     edx, r15d; int
0x180017de1  call    ?SendClientResponse@CIsapiReqInfo@@QEAAHHPEAU_HSE_SEND_ENTIRE_RESPONSE_INFO@@PEAUWSABUF_VECTORS@@P6AXPEAX@Z2@Z; CIsapiReqInfo::SendClientResponse(int,_HSE_SEND_ENTIRE_RESPONSE_INFO *,WSABUF_VECTORS *,void (*)(void *),void *)
0x180017de6  test    eax, eax
0x180017de8  jz      loc_180017F1C
0x180017dee  test    r15d, r15d
0x180017df1  jz      loc_180017F27
0x180017df7  mov     rcx, cs:?sm_pach@CResponseBufferSet@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CResponseBufferSet::sm_pach
0x180017dfe  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x180017e04  mov     rdx, rax
0x180017e07  test    rax, rax
0x180017e0a  jz      short loc_180017E3F
0x180017e0c  and     dword ptr [rax+0A8h], 0FFFFFFFCh
0x180017e13  lea     rcx, [rax+18h]
0x180017e17  mov     [rcx], r13
0x180017e1a  mov     [rax+98h], rcx
0x180017e21  mov     [rax], r13
0x180017e24  mov     [rax+8], r13
0x180017e28  mov     [rax+10h], r13
0x180017e2c  mov     [rax+0A0h], r13d
0x180017e33  mov     dword ptr [rax+0A4h], 10h
0x180017e3d  jmp     short loc_180017E42
0x180017e3f  mov     rdx, r13
0x180017e42  mov     rax, [rsi+38h]
0x180017e46  mov     [rax+98h], rdx
0x180017e4d  mov     rax, [rsi+38h]
0x180017e51  mov     rbx, [rax+98h]
0x180017e58  test    rbx, rbx
0x180017e5b  jz      loc_180017EE3
0x180017e61  mov     rcx, cs:?sm_pach@CResponseBuffer@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CResponseBuffer::sm_pach
0x180017e68  mov     edi, [rax+120h]
0x180017e6e  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x180017e74  test    rax, rax
0x180017e77  jz      short loc_180017EE0
0x180017e79  and     dword ptr [rax+18h], 0FFFFFFFEh
0x180017e7d  lea     rcx, [rax+828h]
0x180017e84  mov     [rax+820h], rcx
0x180017e8b  mov     [rcx], r13
0x180017e8e  mov     [rax+8], r13
0x180017e92  mov     [rax+10h], r13
0x180017e96  mov     [rax+1Ch], r13d
0x180017e9a  mov     qword ptr [rax+830h], 1
0x180017ea5  mov     [rax+838h], r13
0x180017eac  mov     [rbx], rax
0x180017eaf  mov     [rax], rbx
0x180017eb2  mov     ebx, r13d
0x180017eb5  mov     [rax+840h], edi
0x180017ebb  mov     dword ptr [rax+844h], 1
0x180017ec5  mov     rax, [rsi+38h]
0x180017ec9  mov     rcx, [rax+98h]
0x180017ed0  and     dword ptr [rcx+0A8h], 0FFFFFFFEh
0x180017ed7  mov     [rcx+10h], r12
0x180017edb  jmp     loc_180017F57
0x180017ee0  mov     [rbx], r13
0x180017ee3  mov     r8, [rsp+160h+lpMem]; lpMem
0x180017ee8  mov     ebx, 8007000Eh
0x180017eed  test    r8, r8
0x180017ef0  jz      short loc_180017F01
0x180017ef2  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180017ef9  xor     edx, edx; dwFlags
0x180017efb  call    cs:__imp_HeapFree
0x180017f01  mov     r8, [rsp+160h+lpMem+8]; lpMem
0x180017f06  test    r8, r8
0x180017f09  jz      short loc_180017F57
0x180017f0b  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180017f12  xor     edx, edx; dwFlags
0x180017f14  call    cs:__imp_HeapFree
0x180017f1a  jmp     short loc_180017F57
0x180017f1c  mov     rax, [rsi+38h]
0x180017f20  or      dword ptr [rax+118h], 2
0x180017f27  test    edi, edi
0x180017f29  jz      short loc_180017F57
0x180017f2b  mov     rax, [rsi+38h]
0x180017f2f  mov     rcx, [rax+98h]
0x180017f36  mov     rcx, [rcx+8]; this
0x180017f3a  test    rcx, rcx
0x180017f3d  jz      short loc_180017F44
0x180017f3f  call    ?Clear@CResponseBuffer@@QEAAJXZ; CResponseBuffer::Clear(void)
0x180017f44  mov     rax, [rsi+38h]
0x180017f48  mov     rcx, [rax+98h]
0x180017f4f  mov     rcx, [rcx]; this
0x180017f52  call    ?Clear@CResponseBuffer@@QEAAJXZ; CResponseBuffer::Clear(void)
0x180017f57  lea     rcx, [rsp+160h+var_E8]
0x180017f5c  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180017f62  mov     r14, [rsp+160h+var_20]
0x180017f6a  mov     eax, ebx
0x180017f6c  mov     rdi, [rsp+160h+arg_10]
0x180017f74  jmp     loc_180017BAE
0x180017f79  lea     rcx, [rsp+160h+var_E8]
0x180017f7e  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180017f84  xor     eax, eax
0x180017f86  jmp     loc_180017BBE
0x180017f8b  xor     r9d, r9d; int
0x180017f8e  lea     rcx, IID_IResponse; struct _GUID *
0x180017f95  mov     edx, 1770h; unsigned int
0x180017f9a  mov     r8d, 6Fh ; 'o'; unsigned int
0x180017fa0  call    ?ExceptionId@@YAXAEBU_GUID@@IIJ@Z; ExceptionId(_GUID const &,uint,uint,long)
0x180017fa5  lea     rcx, [rsp+160h+var_E8]
0x180017faa  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180017fb0  mov     eax, 80004005h
0x180017fb5  jmp     loc_180017BBE
```
