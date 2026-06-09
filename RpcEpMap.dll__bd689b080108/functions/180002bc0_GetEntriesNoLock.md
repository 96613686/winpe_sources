# GetEntriesNoLock

- ea: `0x180002bc0`
- end: `0x18000320c`
- name: `GetEntriesNoLock`
- size: `1612`
- prototype: `RPC_STATUS __fastcall(__int64, __int64, unsigned int, __int64, void *, __int64 *, __int64, int, unsigned int, unsigned int, unsigned int *, int, int, unsigned int (__fastcall *)(__int64 *, __int64, __int64, _QWORD, int, int), _DWORD *)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180002ae0`
- `0x180003a1c`

## callees

- `0x180002bc0`
- `0x1800033f0`
- `0x180003660`
- `0x180004950`
- `0x180004a50`
- `0x180004c40`
- `0x180004ef8`
- `0x18000a8b4`
- `0x18000a980`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!atoi` at `0x180002f71`
- `api-ms-win-core-crt-l1-1-0!atoi` at `0x180002f71`
- `api-ms-win-core-crt-l1-1-0!_stricmp` at `0x180002eb3`
- `api-ms-win-core-crt-l1-1-0!_stricmp` at `0x180002ecc`
- `api-ms-win-core-crt-l1-1-0!_stricmp` at `0x180002ee1`
- `api-ms-win-core-crt-l1-1-0!_stricmp` at `0x180002eb3`
- `api-ms-win-core-crt-l1-1-0!_stricmp` at `0x180002ecc`
- `api-ms-win-core-crt-l1-1-0!_stricmp` at `0x180002ee1`
- `RPCRT4!I_RpcServerInqLocalConnAddress` at `0x180002ddb`
- `RPCRT4!I_RpcServerInqLocalConnAddress` at `0x180002ddb`
- `RPCRT4!I_RpcServerInqRemoteConnAddress` at `0x180002e3e`
- `RPCRT4!I_RpcServerInqRemoteConnAddress` at `0x180002e3e`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180002fb9`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180002fb9`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180002ff4`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180002ff4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002d20`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002d20`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180003106`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180003132`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180003106`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180003132`

## pseudocode

```c
RPC_STATUS __fastcall GetEntriesNoLock(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        void *a5,
        __int64 *a6,
        __int64 a7,
        int a8,
        unsigned int a9,
        unsigned int a10,
        unsigned int *a11,
        int a12,
        int a13,
        unsigned int (__fastcall *a14)(__int64 *, __int64, __int64, _QWORD, int, int),
        _DWORD *a15)
{
  __int64 v15; // r13
  __int64 v16; // rdi
  bool v17; // zf
  RPC_STATUS result; // eax
  int v19; // esi
  __int64 *v20; // rcx
  __int64 *IFOBJNode; // r13
  RPC_STATUS v22; // eax
  __int64 i; // rcx
  __int64 PSEP; // rax
  __int64 v25; // r14
  const char *v26; // rcx
  __int64 v27; // r9
  __int64 v28; // rax
  unsigned __int64 v29; // rax
  unsigned int v30; // r8d
  __int64 j; // rdx
  __int64 v32; // rax
  __int64 NewContext; // rax
  ULONGLONG TickCount64; // rax
  unsigned int v35; // r9d
  _DWORD *v36; // r14
  unsigned int v37; // eax
  unsigned int BufferSize; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int AddressFormat; // [rsp+54h] [rbp-ACh] BYREF
  int v40; // [rsp+58h] [rbp-A8h]
  int v41; // [rsp+5Ch] [rbp-A4h]
  int v42; // [rsp+60h] [rbp-A0h]
  unsigned int v43; // [rsp+64h] [rbp-9Ch]
  unsigned int ClientLocalFlag; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v45; // [rsp+6Ch] [rbp-94h]
  int v46; // [rsp+70h] [rbp-90h]
  int v47; // [rsp+74h] [rbp-8Ch] BYREF
  int v48; // [rsp+78h] [rbp-88h] BYREF
  __int64 v49; // [rsp+80h] [rbp-80h] BYREF
  _BYTE *v50; // [rsp+88h] [rbp-78h]
  __int64 v51; // [rsp+90h] [rbp-70h] BYREF
  _BYTE *v52; // [rsp+98h] [rbp-68h]
  int v53; // [rsp+A0h] [rbp-60h]
  int v54; // [rsp+A4h] [rbp-5Ch]
  _WORD *v55; // [rsp+A8h] [rbp-58h]
  __int64 v56; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v57; // [rsp+B8h] [rbp-48h]
  unsigned int (__fastcall *v58)(__int64 *, __int64, __int64, _QWORD, int, int); // [rsp+C0h] [rbp-40h]
  void *v59; // [rsp+C8h] [rbp-38h]
  __int64 v60; // [rsp+D0h] [rbp-30h]
  __int64 v61; // [rsp+D8h] [rbp-28h]
  __int64 v62; // [rsp+E0h] [rbp-20h]
  _DWORD *v63; // [rsp+E8h] [rbp-18h]
  _QWORD v64[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int16 v65; // [rsp+100h] [rbp+0h]
  __int16 v66; // [rsp+102h] [rbp+2h]
  int v67; // [rsp+104h] [rbp+4h]
  __int64 v68; // [rsp+108h] [rbp+8h]
  __int64 v69; // [rsp+110h] [rbp+10h]
  char v70; // [rsp+118h] [rbp+18h]
  char v71; // [rsp+119h] [rbp+19h]
  char v72; // [rsp+11Ah] [rbp+1Ah]
  int v73; // [rsp+11Bh] [rbp+1Bh]
  char v74; // [rsp+11Fh] [rbp+1Fh]
  __int64 *v75; // [rsp+120h] [rbp+20h]
  __int16 v76; // [rsp+128h] [rbp+28h]
  int v77; // [rsp+12Ah] [rbp+2Ah]
  __int16 v78; // [rsp+12Eh] [rbp+2Eh]
  _WORD *v79; // [rsp+130h] [rbp+30h]
  __int64 *v80; // [rsp+138h] [rbp+38h]
  __int16 v81; // [rsp+140h] [rbp+40h]
  int v82; // [rsp+142h] [rbp+42h]
  __int16 v83; // [rsp+146h] [rbp+46h]
  _DWORD RpcCallAttributes[2]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v85[120]; // [rsp+158h] [rbp+58h] BYREF
  _BYTE Buffer[4]; // [rsp+1D0h] [rbp+D0h] BYREF
  int v87; // [rsp+1D4h] [rbp+D4h]
  _BYTE v88[120]; // [rsp+1D8h] [rbp+D8h] BYREF
  _WORD v89[264]; // [rsp+250h] [rbp+150h] BYREF

  v15 = a2;
  v16 = *a6;
  v59 = a5;
  v54 = a12;
  v53 = a13;
  v45 = a3;
  v57 = a2;
  v60 = a1;
  v58 = a14;
  v61 = a4;
  v62 = a7;
  v43 = a9;
  v63 = a15;
  v56 = a7;
  memset_0(Buffer, 0, 0x80u);
  *a11 = 0;
  v17 = *a6 == 0;
  BufferSize = 0;
  AddressFormat = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v47 = 0;
  v48 = 0;
  if ( !v17 )
  {
    if ( *a6 == -1 )
    {
      *a6 = 0;
      return 382312662;
    }
    if ( *(_DWORD *)(v16 + 8) != -84215046 || a9 != *(_DWORD *)(v16 + 20) )
      return 382312653;
    result = GetEntriesFromSavedContext(v16, a7, a8, a10, (__int64)a11);
    v19 = result;
    if ( *(_QWORD *)(v16 + 24) )
      return result;
    HeapFree(hEpMapperHeap, 0, (LPVOID)v16);
    *a6 = (a10 > 1) - 1LL;
    return v19;
  }
  v20 = (__int64 *)IFObjList;
  v19 = 0;
  v41 = 0;
  v46 = 0;
  v55 = 0;
  *a6 = 0;
LABEL_10:
  if ( !v19 )
  {
    IFOBJNode = FindIFOBJNode(v20, v60, v15, v45, v59, v54, v53, v58, 0, &v48);
    if ( IFOBJNode )
    {
      v40 = 0;
      BufferSize = 128;
      v22 = I_RpcServerInqLocalConnAddress(0, Buffer, &BufferSize, &AddressFormat);
      if ( v22 )
      {
        if ( v22 != 1764 )
          return 5;
      }
      else if ( AddressFormat == 1 )
      {
        v41 = v87;
        LODWORD(v50) = v87;
        v40 = 1;
        LODWORD(v49) = 1;
      }
      else
      {
        LODWORD(v49) = 2;
        v50 = v88;
      }
      BufferSize = 128;
      result = I_RpcServerInqRemoteConnAddress(0, Buffer, &BufferSize, &AddressFormat);
      if ( result )
      {
        if ( result != 1764 )
          return result;
      }
      else if ( AddressFormat == 1 )
      {
        LODWORD(v52) = v87;
        LODWORD(v51) = 1;
      }
      else
      {
        LODWORD(v51) = 2;
        v52 = v88;
      }
      for ( i = IFOBJNode[4]; ; i = *(_QWORD *)v25 )
      {
        if ( !i || (PSEP = FindPSEP(i, v61, 0), (v25 = PSEP) == 0) )
        {
LABEL_56:
          v20 = (__int64 *)*IFOBJNode;
          v15 = v57;
          goto LABEL_10;
        }
        v26 = *(const char **)(PSEP + 24);
        v42 = 0;
        if ( !_stricmp(v26, "ncacn_ip_tcp") || !_stricmp(*(const char **)(v25 + 24), "ncacn_http") )
        {
          if ( v40 )
          {
            v32 = *(_QWORD *)(v25 + 40);
            if ( *(_DWORD *)(v32 + 75) )
            {
              if ( v41 != *(_DWORD *)(v32 + 75) )
                continue;
            }
            else
            {
              v42 = 1;
            }
          }
          LOWORD(v46) = atoi(*(const char **)(v25 + 32));
        }
        else if ( !_stricmp(*(const char **)(v25 + 24), "ncacn_np") )
        {
          v27 = *(_QWORD *)(v25 + 32);
          v28 = -1;
          do
            ++v28;
          while ( *(_BYTE *)(v27 + v28) );
          v29 = v28 + 1;
          v30 = 260;
          if ( v29 < 0x104 )
            v30 = v29;
          for ( j = 0; (unsigned int)j < v30; j = (unsigned int)(j + 1) )
            v89[j] = *(char *)(j + v27);
          v89[v30 - 1] = 0;
          v55 = v89;
        }
        if ( gFwManagerExtensionState != 1
          || !*((_DWORD *)IFOBJNode + 32) && !(*(unsigned int (**)(void))(qword_180013BE8 + 8))() )
        {
          goto LABEL_48;
        }
        ClientLocalFlag = 0;
        if ( I_RpcBindingIsClientLocal(0, &ClientLocalFlag) != 1764 )
        {
          if ( ClientLocalFlag )
            goto LABEL_48;
        }
        memset_0(v85, 0, 0x70u);
        RpcCallAttributes[0] = 3;
        RpcCallAttributes[1] = 64;
        result = RpcServerInqCallAttributesW(0, RpcCallAttributes);
        if ( result )
          return result;
        v64[1] = v57;
        v65 = HIWORD(v45);
        v66 = 0;
        v70 = v85[48];
        v71 = v85[36];
        v72 = v85[32];
        v73 = 0;
        v74 = 0;
        v75 = &v49;
        v76 = v46;
        v77 = 0;
        v78 = 0;
        v79 = v55;
        v80 = &v51;
        v82 = 0;
        v83 = 0;
        v64[0] = 0;
        v67 = 0;
        v68 = 0;
        v69 = 0;
        v81 = 0;
        result = (*(__int64 (__fastcall **)(__int64, _QWORD *, int *, _QWORD, _QWORD, _QWORD))(qword_180013BE8 + 32))(
                   1,
                   v64,
                   &v47,
                   0,
                   0,
                   0);
        if ( result )
          return result;
        if ( v47 )
        {
LABEL_48:
          if ( *a11 >= a10 )
          {
            if ( !v16 )
            {
              NewContext = GetNewContext(v43);
              *a6 = NewContext;
              v16 = NewContext;
              if ( !NewContext )
              {
                v19 = 14;
                goto LABEL_56;
              }
            }
            TickCount64 = GetTickCount64();
            v35 = v43;
            IFOBJNode[19] = TickCount64;
            AddToSavedContext(v16, (_DWORD)IFOBJNode, v25, v35, v42, v40 != 0 ? v41 : 0);
          }
          else
          {
            v19 = PackDataIntoBuffer(
                    (unsigned int)&v56,
                    a8 + (int)v62 - (int)v56,
                    (_DWORD)IFOBJNode,
                    v25,
                    v43,
                    v42,
                    v41 & (unsigned int)-(v40 != 0));
            if ( v19 )
              goto LABEL_56;
            IFOBJNode[19] = GetTickCount64();
            ++*a11;
          }
        }
      }
    }
  }
  v36 = v63;
  if ( v63 )
    *v63 = 0;
  v37 = *a11;
  if ( !*a11 )
  {
    if ( !a10 )
      goto LABEL_70;
    if ( v19 )
    {
      v37 = 0;
    }
    else
    {
      if ( v48 == 5 && v36 )
      {
        *v36 = 1;
        v37 = *a11;
      }
      else
      {
        v37 = 0;
      }
      v19 = 382312662;
    }
  }
  if ( v37 <= a10 )
  {
LABEL_70:
    if ( !v16 )
      *a6 = (a10 > 1) - 1LL;
  }
  return v19;
}

```

## disassembly

```asm
0x180002bc0  push    rbp
0x180002bc2  push    rbx
0x180002bc3  push    rsi
0x180002bc4  push    rdi
0x180002bc5  push    r12
0x180002bc7  push    r13
0x180002bc9  push    r14
0x180002bcb  push    r15
0x180002bcd  lea     rbp, [rsp-378h]
0x180002bd5  sub     rsp, 478h
0x180002bdc  mov     rax, cs:__security_cookie
0x180002be3  xor     rax, rsp
0x180002be6  mov     [rbp+3B0h+var_50], rax
0x180002bed  mov     rax, [rbp+3B0h+arg_20]
0x180002bf4  mov     r13, rdx
0x180002bf7  mov     rsi, [rbp+3B0h+arg_30]
0x180002bfe  mov     r15, [rbp+3B0h+arg_28]
0x180002c05  mov     r14, [rbp+3B0h+arg_70]
0x180002c0c  mov     ebx, [rbp+3B0h+arg_40]
0x180002c12  mov     r12, [rbp+3B0h+arg_50]
0x180002c19  mov     rdi, [r15]
0x180002c1c  mov     [rbp+3B0h+var_3E8], rax
0x180002c20  mov     eax, [rbp+3B0h+arg_58]
0x180002c26  mov     [rbp+3B0h+var_40C], eax
0x180002c29  mov     eax, [rbp+3B0h+arg_60]
0x180002c2f  mov     [rbp+3B0h+var_410], eax
0x180002c32  mov     rax, [rbp+3B0h+arg_68]
0x180002c39  mov     [rsp+4B0h+var_444], r8d
0x180002c3e  mov     r8d, 80h; Size
0x180002c44  mov     [rbp+3B0h+var_3F8], rdx
0x180002c48  xor     edx, edx; Val
0x180002c4a  mov     [rbp+3B0h+var_3E0], rcx
0x180002c4e  lea     rcx, [rbp+3B0h+Buffer]; void *
0x180002c55  mov     [rbp+3B0h+var_3F0], rax
0x180002c59  mov     [rbp+3B0h+var_3D8], r9
0x180002c5d  mov     [rbp+3B0h+var_3D0], rsi
0x180002c61  mov     [rsp+4B0h+var_44C], ebx
0x180002c65  mov     [rbp+3B0h+var_3C8], r14
0x180002c69  mov     [rbp+3B0h+var_400], rsi
0x180002c6d  call    memset_0
0x180002c72  mov     dword ptr [r12], 0
0x180002c7a  cmp     qword ptr [r15], 0
0x180002c7e  mov     [rsp+4B0h+BufferSize], 0
0x180002c86  mov     [rsp+4B0h+AddressFormat], 0
0x180002c8e  mov     [rbp+3B0h+var_430], 0
0x180002c96  mov     [rbp+3B0h+var_428], 0
0x180002c9e  mov     [rbp+3B0h+var_420], 0
0x180002ca6  mov     [rbp+3B0h+var_418], 0
0x180002cae  mov     [rsp+4B0h+var_43C], 0
0x180002cb6  mov     [rsp+4B0h+var_438], 0
0x180002cbe  jz      loc_180002D49
0x180002cc4  cmp     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x180002cc8  jnz     short loc_180002CDB
0x180002cca  mov     qword ptr [r15], 0
0x180002cd1  mov     eax, 16C9A0D6h
0x180002cd6  jmp     loc_1800031E9
0x180002cdb  cmp     dword ptr [rdi+8], 0FAFAFAFAh
0x180002ce2  jnz     short loc_180002D3F
0x180002ce4  cmp     ebx, [rdi+14h]
0x180002ce7  jnz     short loc_180002D3F
0x180002ce9  mov     r9d, [rbp+3B0h+arg_48]
0x180002cf0  mov     rdx, rsi
0x180002cf3  mov     r8d, [rbp+3B0h+arg_38]
0x180002cfa  mov     rcx, rdi
0x180002cfd  mov     [rsp+4B0h+var_490], r12
0x180002d02  call    GetEntriesFromSavedContext
0x180002d07  cmp     qword ptr [rdi+18h], 0
0x180002d0c  mov     esi, eax
0x180002d0e  jnz     loc_1800031E9
0x180002d14  mov     rcx, cs:hEpMapperHeap; hHeap
0x180002d1b  mov     r8, rdi; lpMem
0x180002d1e  xor     edx, edx; dwFlags
0x180002d20  call    cs:__imp_HeapFree
0x180002d26  xor     ecx, ecx
0x180002d28  lea     ebx, [rcx+1]
0x180002d2b  cmp     [rbp+3B0h+arg_48], ebx
0x180002d31  setnbe  cl
0x180002d34  sub     rcx, rbx
0x180002d37  mov     [r15], rcx
0x180002d3a  jmp     loc_1800031E7
0x180002d3f  mov     eax, 16C9A0CDh
0x180002d44  jmp     loc_1800031E9
0x180002d49  mov     rcx, cs:IFObjList
0x180002d50  xor     esi, esi
0x180002d52  mov     [rsp+4B0h+var_454], esi
0x180002d56  mov     [rsp+4B0h+var_440], esi
0x180002d5a  mov     [rbp+3B0h+var_408], rsi
0x180002d5e  lea     ebx, [rsi+1]
0x180002d61  mov     [r15], rsi
0x180002d64  test    esi, esi
0x180002d66  jnz     loc_18000318B
0x180002d6c  mov     r9d, [rsp+4B0h+var_444]
0x180002d71  lea     rax, [rsp+4B0h+var_438]
0x180002d76  mov     rdx, [rbp+3B0h+var_3E0]
0x180002d7a  mov     r8, r13
0x180002d7d  mov     [rsp+4B0h+var_468], rax
0x180002d82  mov     rax, [rbp+3B0h+var_3F0]
0x180002d86  mov     [rsp+4B0h+var_470], 0
0x180002d8f  mov     [rsp+4B0h+var_478], rax
0x180002d94  mov     eax, [rbp+3B0h+var_410]
0x180002d97  mov     [rsp+4B0h+var_480], eax
0x180002d9b  mov     eax, [rbp+3B0h+var_40C]
0x180002d9e  mov     dword ptr [rsp+4B0h+var_488], eax
0x180002da2  mov     rax, [rbp+3B0h+var_3E8]
0x180002da6  mov     [rsp+4B0h+var_490], rax
0x180002dab  call    FindIFOBJNode
0x180002db0  mov     r13, rax
0x180002db3  test    rax, rax
0x180002db6  jz      loc_18000318B
0x180002dbc  lea     r9, [rsp+4B0h+AddressFormat]; AddressFormat
0x180002dc1  mov     [rsp+4B0h+var_458], esi
0x180002dc5  lea     r8, [rsp+4B0h+BufferSize]; BufferSize
0x180002dca  mov     [rsp+4B0h+BufferSize], 80h
0x180002dd2  lea     rdx, [rbp+3B0h+Buffer]; Buffer
0x180002dd9  xor     ecx, ecx; Binding
0x180002ddb  call    cs:__imp_I_RpcServerInqLocalConnAddress
0x180002de1  test    eax, eax
0x180002de3  jnz     short loc_180002E18
0x180002de5  cmp     [rsp+4B0h+AddressFormat], ebx
0x180002de9  jnz     short loc_180002E04
0x180002deb  mov     r14d, [rbp+3B0h+var_2DC]
0x180002df2  mov     [rsp+4B0h+var_454], r14d
0x180002df7  mov     dword ptr [rbp+3B0h+var_428], r14d
0x180002dfb  mov     [rsp+4B0h+var_458], ebx
0x180002dff  mov     dword ptr [rbp+3B0h+var_430], ebx
0x180002e02  jmp     short loc_180002E23
0x180002e04  lea     rax, [rbp+3B0h+var_2D8]
0x180002e0b  mov     dword ptr [rbp+3B0h+var_430], 2
0x180002e12  mov     [rbp+3B0h+var_428], rax
0x180002e16  jmp     short loc_180002E23
0x180002e18  cmp     eax, 6E4h
0x180002e1d  jnz     loc_180003184
0x180002e23  lea     r9, [rsp+4B0h+AddressFormat]; AddressFormat
0x180002e28  mov     [rsp+4B0h+BufferSize], 80h
0x180002e30  lea     r8, [rsp+4B0h+BufferSize]; BufferSize
0x180002e35  xor     ecx, ecx; Binding
0x180002e37  lea     rdx, [rbp+3B0h+Buffer]; Buffer
0x180002e3e  call    cs:__imp_I_RpcServerInqRemoteConnAddress
0x180002e44  test    eax, eax
0x180002e46  jnz     short loc_180002E70
0x180002e48  cmp     [rsp+4B0h+AddressFormat], ebx
0x180002e4c  jnz     short loc_180002E5C
0x180002e4e  mov     eax, [rbp+3B0h+var_2DC]
0x180002e54  mov     dword ptr [rbp+3B0h+var_418], eax
0x180002e57  mov     dword ptr [rbp+3B0h+var_420], ebx
0x180002e5a  jmp     short loc_180002E7B
0x180002e5c  lea     rax, [rbp+3B0h+var_2D8]
0x180002e63  mov     dword ptr [rbp+3B0h+var_420], 2
0x180002e6a  mov     [rbp+3B0h+var_418], rax
0x180002e6e  jmp     short loc_180002E7B
0x180002e70  cmp     eax, 6E4h
0x180002e75  jnz     loc_1800031E9
0x180002e7b  mov     rcx, [r13+20h]
0x180002e7f  test    rcx, rcx
0x180002e82  jz      loc_180003177
0x180002e88  mov     rdx, [rbp+3B0h+var_3D8]
0x180002e8c  xor     r8d, r8d
0x180002e8f  call    FindPSEP
0x180002e94  mov     r14, rax
0x180002e97  test    rax, rax
0x180002e9a  jz      loc_180003177
0x180002ea0  mov     rcx, [rax+18h]; String1
0x180002ea4  lea     rdx, String2; "ncacn_ip_tcp"
0x180002eab  mov     [rsp+4B0h+var_450], 0
0x180002eb3  call    cs:__imp__stricmp
0x180002eb9  test    eax, eax
0x180002ebb  jz      loc_180002F49
0x180002ec1  mov     rcx, [r14+18h]; String1
0x180002ec5  lea     rdx, aNcacnHttp; "ncacn_http"
0x180002ecc  call    cs:__imp__stricmp
0x180002ed2  test    eax, eax
0x180002ed4  jz      short loc_180002F49
0x180002ed6  mov     rcx, [r14+18h]; String1
0x180002eda  lea     rdx, aNcacnNp; "ncacn_np"
0x180002ee1  call    cs:__imp__stricmp
0x180002ee7  test    eax, eax
0x180002ee9  jnz     loc_180002F7C
0x180002eef  mov     r9, [r14+20h]
0x180002ef3  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002ef7  inc     rax
0x180002efa  cmp     byte ptr [r9+rax], 0
0x180002eff  jnz     short loc_180002EF7
0x180002f01  inc     rax
0x180002f04  mov     ecx, 104h
0x180002f09  cmp     rax, rcx
0x180002f0c  mov     r8d, ecx
0x180002f0f  cmovb   r8, rax
0x180002f13  xor     edx, edx
0x180002f15  test    r8d, r8d
0x180002f18  jz      short loc_180002F2E
0x180002f1a  movsx   eax, byte ptr [rdx+r9]
0x180002f1f  mov     [rbp+rdx*2+3B0h+var_260], ax
0x180002f27  add     edx, ebx
0x180002f29  cmp     edx, r8d
0x180002f2c  jb      short loc_180002F1A
0x180002f2e  xor     eax, eax
0x180002f30  lea     ecx, [r8-1]
0x180002f34  mov     [rbp+rcx*2+3B0h+var_260], ax
0x180002f3c  lea     rax, [rbp+3B0h+var_260]
0x180002f43  mov     [rbp+3B0h+var_408], rax
0x180002f47  jmp     short loc_180002F7C
0x180002f49  cmp     [rsp+4B0h+var_458], 0
0x180002f4e  jz      short loc_180002F6D
0x180002f50  mov     rax, [r14+28h]
0x180002f54  cmp     dword ptr [rax+4Bh], 0
0x180002f58  jnz     short loc_180002F60
0x180002f5a  mov     [rsp+4B0h+var_450], ebx
0x180002f5e  jmp     short loc_180002F6D
0x180002f60  mov     ecx, [rsp+4B0h+var_454]
0x180002f64  cmp     ecx, [rax+4Bh]
0x180002f67  jnz     loc_18000316A
0x180002f6d  mov     rcx, [r14+20h]; String
0x180002f71  call    cs:__imp_atoi
0x180002f77  mov     word ptr [rsp+4B0h+var_440], ax
0x180002f7c  cmp     cs:?gFwManagerExtensionState@@3W4FwManagerExtensionState@@A, ebx; FwManagerExtensionState gFwManagerExtensionState
0x180002f82  jnz     loc_1800030B9
0x180002f88  cmp     dword ptr [r13+80h], 0
0x180002f90  jnz     short loc_180002FAA
0x180002f92  mov     rax, cs:qword_180013BE8
0x180002f99  mov     rax, [rax+8]
0x180002f9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fa2  test    eax, eax
0x180002fa4  jz      loc_1800030B9
0x180002faa  lea     rdx, [rsp+4B0h+ClientLocalFlag]; ClientLocalFlag
0x180002faf  mov     [rsp+4B0h+ClientLocalFlag], 0
0x180002fb7  xor     ecx, ecx; BindingHandle
0x180002fb9  call    cs:__imp_I_RpcBindingIsClientLocal
0x180002fbf  cmp     eax, 6E4h
0x180002fc4  jz      short loc_180002FD1
0x180002fc6  cmp     [rsp+4B0h+ClientLocalFlag], 0
0x180002fcb  jnz     loc_1800030B9
0x180002fd1  xor     edx, edx; Val
0x180002fd3  lea     rcx, [rbp+3B0h+var_358]; void *
0x180002fd7  lea     r8d, [rdx+70h]; Size
0x180002fdb  call    memset_0
0x180002fe0  lea     rdx, [rbp+3B0h+RpcCallAttributes]; RpcCallAttributes
0x180002fe4  mov     [rbp+3B0h+RpcCallAttributes], 3
0x180002feb  xor     ecx, ecx; ClientBinding
0x180002fed  mov     [rbp+3B0h+var_35C], 40h ; '@'
0x180002ff4  call    cs:__imp_RpcServerInqCallAttributesW
0x180002ffa  xor     ecx, ecx
0x180002ffc  test    eax, eax
0x180002ffe  jnz     loc_1800031E9
0x180003004  mov     rax, [rbp+3B0h+var_3F8]
0x180003008  lea     r8, [rsp+4B0h+var_43C]
0x18000300d  mov     [rbp+3B0h+var_3B8], rax
0x180003011  lea     rdx, [rbp+3B0h+var_3C0]
0x180003015  mov     eax, [rsp+4B0h+var_444]
0x180003019  xor     r9d, r9d
0x18000301c  shr     eax, 10h
0x18000301f  mov     [rbp+3B0h+var_3B0], ax
0x180003023  xor     eax, eax
0x180003025  mov     [rbp+3B0h+var_3AE], ax
0x180003029  mov     al, [rbp+3B0h+var_328]
0x18000302f  mov     [rbp+3B0h+var_398], al
0x180003032  mov     al, [rbp+3B0h+var_334]
0x180003035  mov     [rbp+3B0h+var_397], al
0x180003038  mov     al, [rbp+3B0h+var_338]
0x18000303b  mov     [rbp+3B0h+var_396], al
0x18000303e  xor     eax, eax
0x180003040  mov     [rbp+3B0h+var_395], eax
0x180003043  mov     [rbp+3B0h+var_391], al
0x180003046  lea     rax, [rbp+3B0h+var_430]
0x18000304a  mov     [rbp+3B0h+var_390], rax
0x18000304e  mov     eax, [rsp+4B0h+var_440]
0x180003052  mov     [rbp+3B0h+var_388], ax
0x180003056  xor     eax, eax
0x180003058  mov     [rbp+3B0h+var_386], eax
0x18000305b  mov     [rbp+3B0h+var_382], ax
0x18000305f  mov     rax, [rbp+3B0h+var_408]
0x180003063  mov     [rbp+3B0h+var_380], rax
0x180003067  lea     rax, [rbp+3B0h+var_420]
0x18000306b  mov     [rbp+3B0h+var_378], rax
0x18000306f  xor     eax, eax
0x180003071  mov     [rbp+3B0h+var_36E], eax
0x180003074  mov     [rbp+3B0h+var_36A], ax
0x180003078  mov     rax, cs:qword_180013BE8
0x18000307f  mov     [rsp+4B0h+var_488], rcx
0x180003084  mov     [rbp+3B0h+var_3C0], rcx
0x180003088  mov     [rbp+3B0h+var_3AC], ecx
0x18000308b  mov     [rbp+3B0h+var_3A8], rcx
0x18000308f  mov     [rbp+3B0h+var_3A0], rcx
0x180003093  mov     [rbp+3B0h+var_370], cx
0x180003097  mov     rax, [rax+20h]
0x18000309b  mov     [rsp+4B0h+var_490], rcx
0x1800030a0  mov     ecx, ebx
0x1800030a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030a7  test    eax, eax
0x1800030a9  jnz     loc_1800031E9
0x1800030af  cmp     [rsp+4B0h+var_43C], eax
0x1800030b3  jz      loc_18000316A
0x1800030b9  mov     eax, [rbp+3B0h+arg_48]
0x1800030bf  cmp     [r12], eax
0x1800030c3  jnb     short loc_180003119
0x1800030c5  mov     eax, [rsp+4B0h+var_458]
0x1800030c9  mov     r9, r14
0x1800030cc  mov     edx, dword ptr [rbp+3B0h+var_3D0]
0x1800030cf  neg     eax
0x1800030d1  mov     eax, [rsp+4B0h+var_450]
0x1800030d5  mov     r8, r13
  ... truncated ...
```
