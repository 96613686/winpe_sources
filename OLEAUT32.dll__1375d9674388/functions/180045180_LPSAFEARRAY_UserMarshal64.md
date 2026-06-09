# LPSAFEARRAY_UserMarshal64

- ea: `0x180045180`
- end: `0x180045612`
- name: `LPSAFEARRAY_UserMarshal64`
- size: `1170`
- prototype: `unsigned __int8 *__stdcall(unsigned int *, unsigned __int8 *, LPSAFEARRAY *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180045d50`

## callees

- `0x18001c6e0`
- `0x18001f440`
- `0x18002fa80`
- `0x1800419c0`
- `0x180042870`
- `0x180045040`
- `0x180045180`
- `0x180045d50`
- `0x18004d900`
- `0x1800716f0`
- `0x180071720`
- `0x18009a624`
- `0x18009c010`

## import_xrefs

- `combase!WdtpInterfacePointer_UserMarshal64` at `0x180045546`
- `combase!WdtpInterfacePointer_UserMarshal64` at `0x180045546`
- `combase!__imp_CoDoesOtherSideSupportUDTMarshaling` at `0x18004521a`
- `combase!__imp_CoDoesOtherSideSupportUDTMarshaling` at `0x18004521a`
- `RPCRT4!RpcRaiseException` at `0x18004531a`
- `RPCRT4!RpcRaiseException` at `0x1800453b0`
- `RPCRT4!RpcRaiseException` at `0x18004541b`
- `RPCRT4!RpcRaiseException` at `0x180045439`
- `RPCRT4!RpcRaiseException` at `0x18004531a`
- `RPCRT4!RpcRaiseException` at `0x1800453b0`
- `RPCRT4!RpcRaiseException` at `0x18004541b`
- `RPCRT4!RpcRaiseException` at `0x180045439`

## pseudocode

```c
unsigned __int8 *__stdcall LPSAFEARRAY_UserMarshal64(unsigned int *a1, unsigned __int8 *a2, LPSAFEARRAY *a3)
{
  unsigned __int8 *v6; // rbx
  LPSAFEARRAY v7; // rsi
  int cLocks; // edi
  int DoesOtherSideSupportUDTMarshaling; // eax
  USHORT fFeatures; // cx
  int SafeArrayDiscr; // r14d
  int cbElements; // eax
  unsigned __int8 *v13; // rcx
  int v14; // r8d
  __int64 v15; // rcx
  int v16; // r12d
  int v17; // r10d
  unsigned __int8 *v18; // rcx
  GUID *Data4; // rbx
  RPC_STATUS IID; // eax
  GUID *p_pguid; // r13
  GUID *v22; // r8
  GUID *v23; // rdi
  __int64 v24; // rdx
  unsigned __int8 *v25; // rdi
  unsigned __int8 *v26; // r15
  int v27; // ebx
  int v28; // r14d
  int v29; // r14d
  int v30; // r14d
  int v31; // r14d
  RPC_STATUS RecordInfo; // eax
  void *v33; // rbx
  VARIANT *v34; // r14
  unsigned int *v35; // r13
  GUID *v36; // rax
  GUID *v37; // r14
  _QWORD *v38; // r13
  __int64 v39; // rcx
  char *v40; // r14
  unsigned int *v41; // r13
  BSTR *v42; // r8
  BSTR v43; // rcx
  unsigned int v44; // r12d
  unsigned __int8 *v45; // [rsp+30h] [rbp-88h] BYREF
  void *ppvData; // [rsp+38h] [rbp-80h] BYREF
  int v47; // [rsp+40h] [rbp-78h]
  unsigned int *v48; // [rsp+48h] [rbp-70h]
  int v49; // [rsp+50h] [rbp-68h]
  unsigned __int8 *v50; // [rsp+58h] [rbp-60h]
  LPSAFEARRAY v51; // [rsp+60h] [rbp-58h]
  GUID pguid; // [rsp+68h] [rbp-50h] BYREF

  v48 = a1;
  v45 = a2;
  if ( !a3 )
    return a2;
  AlignAndZeroGap(&v45, 7u);
  v6 = v45;
  *(_QWORD *)v45 = *a3 != 0;
  v7 = *a3;
  if ( !v7 )
    return v6 + 8;
  v51 = v7;
  if ( SLOBYTE(v7->fFeatures) >= 0 )
    cLocks = (unsigned __int16)v7->cLocks;
  else
    cLocks = (unsigned __int16)v7->cLocks | (v7[-1].rgsabound[0].lLbound << 16);
  *((_QWORD *)v6 + 1) = v7->cDims;
  *((_WORD *)v6 + 8) = v7->cDims;
  DoesOtherSideSupportUDTMarshaling = CoDoesOtherSideSupportUDTMarshaling(a1);
  fFeatures = v7->fFeatures;
  if ( !DoesOtherSideSupportUDTMarshaling )
    fFeatures &= 0xFF3Fu;
  *((_WORD *)v6 + 9) = fFeatures;
  SafeArrayDiscr = GetSafeArrayDiscr(v7, a1);
  if ( SafeArrayDiscr != 8 && SafeArrayDiscr != 9 )
  {
    if ( SafeArrayDiscr == 12 )
    {
      cbElements = 16;
      goto LABEL_18;
    }
    if ( SafeArrayDiscr != 13 && SafeArrayDiscr != 32781 )
    {
      cbElements = v7->cbElements;
      goto LABEL_18;
    }
  }
  cbElements = 4;
LABEL_18:
  *((_DWORD *)v6 + 5) = cbElements;
  *((_DWORD *)v6 + 6) = cLocks;
  v45 = v6 + 28;
  AlignAndZeroGap(&v45, 7u);
  v13 = v45;
  *(_DWORD *)v45 = SafeArrayDiscr;
  v45 = v13 + 4;
  v14 = 1;
  v15 = 0;
  if ( v7->cDims )
  {
    do
    {
      v14 *= v7->rgsabound[v15].cElements;
      v15 = (unsigned int)(v15 + 1);
    }
    while ( (int)v15 < v7->cDims );
  }
  v16 = v14;
  if ( SafeArrayDiscr == 36 )
    v16 = 1;
  else
    v14 = 0;
  v49 = v14;
  AlignAndZeroGap(&v45, 7u);
  v18 = v45;
  *(_QWORD *)v45 = v16;
  *((_QWORD *)v18 + 1) = v7->pvData;
  Data4 = (GUID *)(v18 + 16);
  pguid = 0;
  if ( SafeArrayDiscr == 32781 )
  {
    IID = SafeArrayGetIID(v7, &pguid);
    if ( IID < 0 )
      RpcRaiseException(IID);
    *Data4++ = pguid;
    p_pguid = &pguid;
    SafeArrayDiscr = 13;
    v17 = 1;
  }
  else
  {
    p_pguid = 0;
  }
  v22 = Data4;
  v23 = Data4;
  v24 = (unsigned int)v7->cDims - v17;
  if ( (int)v24 >= 0 )
  {
    do
    {
      Data4->Data1 = v7->rgsabound[v24].cElements;
      *(_DWORD *)&v22->Data2 = v7->rgsabound[v24].lLbound;
      Data4 = (GUID *)v22->Data4;
      v24 = (unsigned int)(v24 - v17);
      v22 = (GUID *)((char *)v22 + 8);
    }
    while ( (int)v24 >= 0 );
    v23 = Data4;
  }
  *(_QWORD *)&Data4->Data1 = v16;
  v25 = v23->Data4;
  v45 = v25;
  ppvData = 0;
  if ( SafeArrayAccessData(v7, &ppvData) )
    RpcRaiseException(-2147418113);
  if ( SafeArrayDiscr != 2 && SafeArrayDiscr != 3 && SafeArrayDiscr != 16 )
  {
    if ( SafeArrayDiscr != 20 )
    {
      v26 = &v25[8 * v16];
      v27 = 0;
      v47 = 0;
      v28 = SafeArrayDiscr - 8;
      if ( !v28 )
      {
        v40 = (char *)ppvData;
        v41 = v48;
        while ( v27 < v16 )
        {
          v42 = (BSTR *)&v40[8 * v27];
          v43 = *v42;
          *(_QWORD *)v25 = *v42 != 0;
          v25 += 8;
          v45 = v25;
          if ( v43 )
          {
            v26 = BSTR_UserMarshal64(v41, v26, v42);
            v50 = v26;
          }
          v47 = ++v27;
        }
        goto LABEL_65;
      }
      v29 = v28 - 1;
      if ( v29 )
      {
        v30 = v29 - 3;
        if ( !v30 )
        {
          v34 = (VARIANT *)ppvData;
          v35 = v48;
          while ( v27 < v16 )
          {
            *(_QWORD *)v25 = 1919251285;
            v25 += 8;
            v45 = v25;
            v26 = VARIANT_UserMarshal64(v35, v26, &v34[v27]);
            v50 = v26;
            v47 = ++v27;
          }
LABEL_65:
          v45 = v26;
          SafeArrayUnaccessData(v7);
          return v26;
        }
        v31 = v30 - 1;
        if ( v31 )
        {
          if ( v31 != 23 )
            RpcRaiseException(-2147024809);
          ppvData = 0;
          RecordInfo = SafeArrayGetRecordInfo(v7, (IRecordInfo **)&ppvData);
          if ( RecordInfo < 0 )
            RpcRaiseException(RecordInfo);
          *(_QWORD *)v25 = 1919251285;
          v45 = v25 + 8;
          v33 = ppvData;
          v26 = (unsigned __int8 *)BRECORD_UserMarshal64(
                                     (_DWORD)v48,
                                     (_DWORD)v26,
                                     v49,
                                     (_DWORD)ppvData,
                                     (__int64)v7->pvData);
          v50 = v26;
          if ( v33 )
            (*(void (__fastcall **)(void *))(*(_QWORD *)v33 + 16LL))(v33);
          goto LABEL_65;
        }
      }
      else
      {
        v36 = &IID_IDispatch;
        if ( p_pguid )
          v36 = p_pguid;
        p_pguid = v36;
      }
      v37 = &IID_IUnknown;
      if ( p_pguid )
        v37 = p_pguid;
      v38 = ppvData;
      while ( v27 < v16 )
      {
        v39 = v38[v27];
        *(_QWORD *)v25 = v39 != 0;
        v25 += 8;
        v45 = v25;
        if ( v39 )
        {
          v26 = (unsigned __int8 *)WdtpInterfacePointer_UserMarshal64(v48, *v48, v26, v38[v27], v37);
          v50 = v26;
        }
        v47 = ++v27;
      }
      goto LABEL_65;
    }
    AlignAndZeroGap(&v45, 7u);
    v25 = v45;
  }
  v44 = v7->cbElements * v16;
  memcpy_0(v25, ppvData, v44);
  SafeArrayUnaccessData(v7);
  return &v25[v44];
}

```

## disassembly

```asm
0x180045180  push    rbx
0x180045182  push    rsi
0x180045183  push    rdi
0x180045184  push    r12
0x180045186  push    r13
0x180045188  push    r14
0x18004518a  push    r15
0x18004518c  sub     rsp, 80h
0x180045193  mov     rax, cs:__security_cookie
0x18004519a  xor     rax, rsp
0x18004519d  mov     [rsp+0B8h+var_40], rax
0x1800451a2  mov     rsi, r8
0x1800451a5  mov     r14, rcx
0x1800451a8  mov     [rsp+0B8h+var_70], rcx
0x1800451ad  mov     [rsp+0B8h+var_88], rdx
0x1800451b2  test    r8, r8
0x1800451b5  jnz     short loc_1800451BF
0x1800451b7  mov     rax, rdx
0x1800451ba  jmp     loc_1800455F2
0x1800451bf  mov     dl, 7; unsigned __int8
0x1800451c1  lea     rcx, [rsp+0B8h+var_88]; unsigned __int8 **
0x1800451c6  call    ?AlignAndZeroGap@@YAXAEAPEAEE@Z; AlignAndZeroGap(uchar * &,uchar)
0x1800451cb  xor     ecx, ecx
0x1800451cd  cmp     [rsi], rcx
0x1800451d0  setnz   cl
0x1800451d3  mov     rbx, [rsp+0B8h+var_88]
0x1800451d8  mov     [rbx], rcx
0x1800451db  mov     rsi, [rsi]
0x1800451de  test    rsi, rsi
0x1800451e1  jnz     short loc_1800451EC
0x1800451e3  lea     rax, [rbx+8]
0x1800451e7  jmp     loc_1800455F2
0x1800451ec  mov     [rsp+0B8h+var_58], rsi
0x1800451f1  mov     eax, [rsi+8]
0x1800451f4  movzx   eax, ax
0x1800451f7  test    byte ptr [rsi+2], 80h
0x1800451fb  jz      short loc_180045207
0x1800451fd  mov     edi, [rsi-4]
0x180045200  shl     edi, 10h
0x180045203  or      edi, eax
0x180045205  jmp     short loc_180045209
0x180045207  mov     edi, eax
0x180045209  movzx   eax, word ptr [rsi]
0x18004520c  mov     [rbx+8], rax
0x180045210  movzx   eax, word ptr [rsi]
0x180045213  mov     [rbx+10h], ax
0x180045217  mov     rcx, r14
0x18004521a  call    cs:__imp_CoDoesOtherSideSupportUDTMarshaling
0x180045220  movzx   ecx, word ptr [rsi+2]
0x180045224  test    eax, eax
0x180045226  jnz     short loc_180045230
0x180045228  mov     eax, 0FF3Fh
0x18004522d  and     cx, ax
0x180045230  mov     [rbx+12h], cx
0x180045234  mov     rdx, r14; unsigned int *
0x180045237  mov     rcx, rsi; struct tagSAFEARRAY *
0x18004523a  call    ?GetSafeArrayDiscr@@YA?AW4tagSF_TYPE@@PEAUtagSAFEARRAY@@PEAK@Z; GetSafeArrayDiscr(tagSAFEARRAY *,ulong *)
0x18004523f  mov     r14d, eax
0x180045242  sub     eax, 8
0x180045245  jz      short loc_180045269
0x180045247  sub     eax, 1
0x18004524a  jz      short loc_180045269
0x18004524c  sub     eax, 3
0x18004524f  jz      short loc_180045262
0x180045251  sub     eax, 1
0x180045254  jz      short loc_180045269
0x180045256  cmp     eax, 8000h
0x18004525b  jz      short loc_180045269
0x18004525d  mov     eax, [rsi+4]
0x180045260  jmp     short loc_18004526E
0x180045262  mov     eax, 10h
0x180045267  jmp     short loc_18004526E
0x180045269  mov     eax, 4
0x18004526e  mov     [rbx+14h], eax
0x180045271  mov     [rbx+18h], edi
0x180045274  lea     rax, [rbx+1Ch]
0x180045278  mov     [rsp+0B8h+var_88], rax
0x18004527d  mov     dl, 7; unsigned __int8
0x18004527f  lea     rcx, [rsp+0B8h+var_88]; unsigned __int8 **
0x180045284  call    ?AlignAndZeroGap@@YAXAEAPEAEE@Z; AlignAndZeroGap(uchar * &,uchar)
0x180045289  mov     rcx, [rsp+0B8h+var_88]
0x18004528e  mov     [rcx], r14d
0x180045291  add     rcx, 4
0x180045295  mov     [rsp+0B8h+var_88], rcx
0x18004529a  mov     r10d, 1
0x1800452a0  mov     r8d, r10d
0x1800452a3  movzx   edx, word ptr [rsi]
0x1800452a6  xor     ecx, ecx
0x1800452a8  test    edx, edx
0x1800452aa  jz      short loc_1800452B9
0x1800452ac  imul    r8d, [rsi+rcx*8+18h]
0x1800452b2  add     ecx, r10d
0x1800452b5  cmp     ecx, edx
0x1800452b7  jl      short loc_1800452AC
0x1800452b9  mov     r12d, r8d
0x1800452bc  cmp     r14d, 24h ; '$'
0x1800452c0  cmovz   r12d, r10d
0x1800452c4  xor     eax, eax
0x1800452c6  cmp     r14d, 24h ; '$'
0x1800452ca  cmovnz  r8d, eax
0x1800452ce  mov     [rsp+0B8h+var_68], r8d
0x1800452d3  mov     dl, 7; unsigned __int8
0x1800452d5  lea     rcx, [rsp+0B8h+var_88]; unsigned __int8 **
0x1800452da  call    ?AlignAndZeroGap@@YAXAEAPEAEE@Z; AlignAndZeroGap(uchar * &,uchar)
0x1800452df  movsxd  r15, r12d
0x1800452e2  mov     rcx, [rsp+0B8h+var_88]
0x1800452e7  mov     [rcx], r15
0x1800452ea  mov     rax, [rsi+10h]
0x1800452ee  mov     [rcx+8], rax
0x1800452f2  lea     rbx, [rcx+10h]
0x1800452f6  xorps   xmm0, xmm0
0x1800452f9  movups  xmmword ptr [rsp+0B8h+pguid.Data1], xmm0
0x1800452fe  cmp     r14d, 800Dh
0x180045305  jnz     short loc_180045357
0x180045307  lea     rdx, [rsp+0B8h+pguid]; pguid
0x18004530c  mov     rcx, rsi; psa
0x18004530f  call    SafeArrayGetIID
0x180045314  test    eax, eax
0x180045316  jns     short loc_180045321
0x180045318  mov     ecx, eax; exception
0x18004531a  call    cs:__imp_RpcRaiseException
0x180045320  int     3; Trap to Debugger
0x180045321  mov     eax, [rsp+0B8h+pguid.Data1]
0x180045325  mov     [rbx], eax
0x180045327  movzx   eax, [rsp+0B8h+pguid.Data2]
0x18004532c  mov     [rbx+4], ax
0x180045330  movzx   eax, [rsp+0B8h+pguid.Data3]
0x180045335  mov     [rbx+6], ax
0x180045339  mov     rax, qword ptr [rsp+0B8h+pguid.Data4]
0x18004533e  mov     [rbx+8], rax
0x180045342  add     rbx, 10h
0x180045346  lea     r13, [rsp+0B8h+pguid]
0x18004534b  mov     r14d, 0Dh
0x180045351  lea     r10d, [r14-0Ch]
0x180045355  jmp     short loc_18004535A
0x180045357  xor     r13d, r13d
0x18004535a  mov     r8, rbx
0x18004535d  mov     rdi, rbx
0x180045360  movzx   edx, word ptr [rsi]
0x180045363  sub     edx, r10d
0x180045366  js      short loc_180045385
0x180045368  mov     eax, [rsi+rdx*8+18h]
0x18004536c  mov     [rbx], eax
0x18004536e  mov     eax, [rsi+rdx*8+1Ch]
0x180045372  mov     [r8+4], eax
0x180045376  lea     rbx, [r8+8]
0x18004537a  sub     edx, r10d
0x18004537d  mov     r8, rbx
0x180045380  jns     short loc_180045368
0x180045382  mov     rdi, rbx
0x180045385  mov     [rbx], r15
0x180045388  add     rdi, 8
0x18004538c  mov     [rsp+0B8h+var_88], rdi
0x180045391  mov     [rsp+0B8h+ppvData], 0
0x18004539a  lea     rdx, [rsp+0B8h+ppvData]; ppvData
0x18004539f  mov     rcx, rsi; psa
0x1800453a2  call    SafeArrayAccessData
0x1800453a7  test    eax, eax
0x1800453a9  jz      short loc_1800453B7
0x1800453ab  mov     ecx, 8000FFFFh; exception
0x1800453b0  call    cs:__imp_RpcRaiseException
0x1800453b6  int     3; Trap to Debugger
0x1800453b7  mov     ecx, r14d
0x1800453ba  sub     ecx, 2
0x1800453bd  jz      loc_1800455CC
0x1800453c3  sub     ecx, 1
0x1800453c6  jz      loc_1800455CC
0x1800453cc  sub     ecx, 0Dh
0x1800453cf  jz      loc_1800455CC
0x1800453d5  cmp     ecx, 4
0x1800453d8  jz      loc_1800455BB
0x1800453de  lea     r15, [rdi+r15*8]
0x1800453e2  xor     ebx, ebx
0x1800453e4  mov     [rsp+0B8h+var_78], ebx
0x1800453e8  sub     r14d, 8
0x1800453ec  jz      loc_18004555C
0x1800453f2  sub     r14d, 1
0x1800453f6  jz      loc_1800454E1
0x1800453fc  sub     r14d, 3
0x180045400  jz      loc_180045498
0x180045406  sub     r14d, 1
0x18004540a  jz      loc_1800454F2
0x180045410  cmp     r14d, 17h
0x180045414  jz      short loc_180045421
0x180045416  mov     ecx, 80070057h; exception
0x18004541b  call    cs:__imp_RpcRaiseException
0x180045421  mov     [rsp+0B8h+ppvData], rbx
0x180045426  lea     rdx, [rsp+0B8h+ppvData]; prinfo
0x18004542b  mov     rcx, rsi; psa
0x18004542e  call    SafeArrayGetRecordInfo
0x180045433  test    eax, eax
0x180045435  jns     short loc_180045440
0x180045437  mov     ecx, eax; exception
0x180045439  call    cs:__imp_RpcRaiseException
0x18004543f  nop
0x180045440  mov     qword ptr [rdi], 72657355h
0x180045447  lea     rax, [rdi+8]
0x18004544b  mov     [rsp+0B8h+var_88], rax
0x180045450  mov     rax, [rsi+10h]
0x180045454  mov     [rsp+0B8h+var_98], rax
0x180045459  mov     rbx, [rsp+0B8h+ppvData]
0x18004545e  mov     r9, rbx
0x180045461  mov     r8d, [rsp+0B8h+var_68]
0x180045466  mov     rdx, r15
0x180045469  mov     rcx, [rsp+0B8h+var_70]
0x18004546e  call    BRECORD_UserMarshal64
0x180045473  mov     r15, rax
0x180045476  mov     [rsp+0B8h+var_60], rax
0x18004547b  test    rbx, rbx
0x18004547e  jz      loc_1800455A9
0x180045484  mov     rax, [rbx]
0x180045487  mov     rcx, rbx
0x18004548a  mov     rax, [rax+10h]
0x18004548e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045493  jmp     loc_1800455A9
0x180045498  mov     r14, [rsp+0B8h+ppvData]
0x18004549d  mov     r13, [rsp+0B8h+var_70]
0x1800454a2  cmp     ebx, r12d
0x1800454a5  jge     loc_1800455A9
0x1800454ab  mov     qword ptr [rdi], 72657355h
0x1800454b2  add     rdi, 8
0x1800454b6  mov     [rsp+0B8h+var_88], rdi
0x1800454bb  movsxd  rax, ebx
0x1800454be  lea     rcx, [rax+rax*2]
0x1800454c2  lea     r8, [r14+rcx*8]; VARIANT *
0x1800454c6  mov     rdx, r15; unsigned __int8 *
0x1800454c9  mov     rcx, r13; unsigned int *
0x1800454cc  call    VARIANT_UserMarshal64
0x1800454d1  mov     r15, rax
0x1800454d4  mov     [rsp+0B8h+var_60], rax
0x1800454d9  inc     ebx
0x1800454db  mov     [rsp+0B8h+var_78], ebx
0x1800454df  jmp     short loc_1800454A2
0x1800454e1  lea     rax, IID_IDispatch
0x1800454e8  test    r13, r13
0x1800454eb  cmovnz  rax, r13
0x1800454ef  mov     r13, rax
0x1800454f2  lea     r14, IID_IUnknown
0x1800454f9  test    r13, r13
0x1800454fc  cmovnz  r14, r13
0x180045500  mov     r13, [rsp+0B8h+ppvData]
0x180045505  cmp     ebx, r12d
0x180045508  jge     loc_1800455A9
0x18004550e  movsxd  r9, ebx
0x180045511  mov     rcx, [r13+r9*8+0]
0x180045516  xor     eax, eax
0x180045518  test    rcx, rcx
0x18004551b  setnz   al
0x18004551e  mov     [rdi], rax
0x180045521  add     rdi, 8
0x180045525  mov     [rsp+0B8h+var_88], rdi
0x18004552a  test    rcx, rcx
0x18004552d  jz      short loc_180045554
0x18004552f  mov     [rsp+0B8h+var_98], r14
0x180045534  mov     r9, [r13+r9*8+0]
0x180045539  mov     r8, r15
0x18004553c  mov     rax, [rsp+0B8h+var_70]
0x180045541  mov     edx, [rax]
0x180045543  mov     rcx, rax
0x180045546  call    cs:__imp_WdtpInterfacePointer_UserMarshal64
0x18004554c  mov     r15, rax
0x18004554f  mov     [rsp+0B8h+var_60], rax
0x180045554  inc     ebx
0x180045556  mov     [rsp+0B8h+var_78], ebx
0x18004555a  jmp     short loc_180045505
0x18004555c  mov     r14, [rsp+0B8h+ppvData]
0x180045561  mov     r13, [rsp+0B8h+var_70]
0x180045566  cmp     ebx, r12d
0x180045569  jge     short loc_1800455A9
0x18004556b  movsxd  rax, ebx
0x18004556e  lea     r8, [r14+rax*8]; BSTR *
0x180045572  mov     rcx, [r8]
0x180045575  xor     eax, eax
0x180045577  test    rcx, rcx
0x18004557a  setnz   al
0x18004557d  mov     [rdi], rax
0x180045580  add     rdi, 8
0x180045584  mov     [rsp+0B8h+var_88], rdi
0x180045589  test    rcx, rcx
0x18004558c  jz      short loc_1800455A1
0x18004558e  mov     rdx, r15; unsigned __int8 *
0x180045591  mov     rcx, r13; unsigned int *
0x180045594  call    BSTR_UserMarshal64
0x180045599  mov     r15, rax
0x18004559c  mov     [rsp+0B8h+var_60], rax
0x1800455a1  inc     ebx
0x1800455a3  mov     [rsp+0B8h+var_78], ebx
0x1800455a7  jmp     short loc_180045566
0x1800455a9  mov     [rsp+0B8h+var_88], r15
0x1800455ae  mov     rcx, rsi; psa
0x1800455b1  call    SafeArrayUnaccessData
0x1800455b6  mov     rax, r15
0x1800455b9  jmp     short loc_1800455F2
0x1800455bb  mov     dl, 7; unsigned __int8
0x1800455bd  lea     rcx, [rsp+0B8h+var_88]; unsigned __int8 **
0x1800455c2  call    ?AlignAndZeroGap@@YAXAEAPEAEE@Z; AlignAndZeroGap(uchar * &,uchar)
0x1800455c7  mov     rdi, [rsp+0B8h+var_88]
0x1800455cc  imul    r12d, [rsi+4]
0x1800455d1  mov     ebx, r12d
0x1800455d4  mov     r8d, r12d; Size
  ... truncated ...
```
