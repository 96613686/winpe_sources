# BCryptCreateHash

- ea: `0x180006020`
- end: `0x1800066e5`
- name: `BCryptCreateHash`
- size: `1733`
- prototype: `NTSTATUS __stdcall(BCRYPT_ALG_HANDLE hAlgorithm, BCRYPT_HASH_HANDLE *phHash, PUCHAR pbHashObject, ULONG cbHashObject, PUCHAR pbSecret, ULONG cbSecret, ULONG dwFlags)`
- caller_count: `8`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005470`
- `0x18000c1e0`
- `0x18000cb70`
- `0x180012cc4`
- `0x180016564`
- `0x1800168c8`
- `0x180016efc`
- `0x1800171b4`

## callees

- `0x180005060`
- `0x180006020`
- `0x1800066f0`
- `0x180006bd0`
- `0x180007a7c`
- `0x180009430`
- `0x1800159dc`
- `0x18001b79d`
- `0x18001c010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800061d2`
- `ntdll!RtlAllocateHeap` at `0x1800061d2`

## string_xrefs

- `0x18000620d`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000623f`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180006387`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800063c3`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800066bc`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptCreateHash(
        BCRYPT_ALG_HANDLE hAlgorithm,
        BCRYPT_HASH_HANDLE *phHash,
        PUCHAR pbHashObject,
        ULONG cbHashObject,
        PUCHAR pbSecret,
        ULONG cbSecret,
        ULONG dwFlags)
{
  ULONG v7; // r14d
  PUCHAR v8; // rdi
  int v11; // edx
  __int64 v12; // rbx
  int v13; // r8d
  void *v14; // r15
  _QWORD *v15; // rsi
  __int64 (__fastcall *v16)(_QWORD, _QWORD *, unsigned __int64, _QWORD, _QWORD, _DWORD, _DWORD); // r10
  __int64 v17; // rax
  unsigned int v18; // r14d
  UCHAR *v19; // r12
  int v20; // eax
  int v21; // edi
  NTSTATUS Property; // eax
  PVOID Heap; // rax
  int v25; // edx
  int v26; // r8d
  UCHAR *v27; // rdx
  __int64 v28; // r8
  int v29; // eax
  __int64 v30; // r9
  __int64 v31; // rcx
  UCHAR *v32; // rax
  __int64 v33; // rcx
  __int64 v34; // r8
  unsigned int i; // ecx
  __int64 v36; // rax
  __int64 (__fastcall *v37)(_QWORD, UCHAR *, __int64, _QWORD); // r14
  int v38; // eax
  __int64 v39; // r8
  unsigned int j; // ecx
  __int64 v41; // rax
  int v42; // eax
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rcx
  __int64 v47; // r9
  __int64 v48; // rax
  unsigned int v49; // r14d
  int v50; // eax
  unsigned __int64 v51; // r9
  unsigned __int64 v52; // r8
  __int64 v53; // r9
  __int64 (__fastcall *v54)(_QWORD, _QWORD *, unsigned __int64, _QWORD, _QWORD, _DWORD, _DWORD); // r14
  int v55; // eax
  int v56; // eax
  int v57; // eax
  int v58; // eax
  int v59; // eax
  unsigned int v60; // [rsp+50h] [rbp-78h] BYREF
  UCHAR pbOutput[4]; // [rsp+54h] [rbp-74h] BYREF
  unsigned int v62; // [rsp+58h] [rbp-70h]
  ULONG pcbResult; // [rsp+5Ch] [rbp-6Ch] BYREF
  int v64; // [rsp+60h] [rbp-68h] BYREF
  unsigned __int64 v65; // [rsp+68h] [rbp-60h]
  __int64 (__fastcall *v66)(_QWORD, UCHAR *, __int64, _QWORD); // [rsp+70h] [rbp-58h]
  __int64 (__fastcall *v67)(_QWORD, _QWORD *, unsigned __int64, _QWORD, _QWORD, _DWORD, _DWORD); // [rsp+78h] [rbp-50h]
  __int64 (__fastcall *v68)(_QWORD, const WCHAR *, unsigned int *, __int64, int *, _DWORD); // [rsp+80h] [rbp-48h]
  __int64 (__fastcall *v69)(_QWORD, UCHAR *, _QWORD, _QWORD); // [rsp+88h] [rbp-40h]
  __int64 (__fastcall *v70)(_QWORD, UCHAR *); // [rsp+90h] [rbp-38h]

  v7 = cbHashObject;
  v8 = pbHashObject;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_qqqdqdD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      33,
      cbSecret,
      hAlgorithm,
      phHash,
      pbHashObject,
      cbHashObject,
      pbSecret,
      cbSecret,
      dwFlags);
  v12 = ValidateBaseAlgHandle(hAlgorithm);
  if ( v12 )
  {
    if ( !v8 && !v7 )
    {
      *(_DWORD *)pbOutput = 0;
      pcbResult = 0;
      Property = BCryptGetProperty(hAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
      v21 = Property;
      if ( Property < 0 )
      {
        v46 = (unsigned int)Property;
        v47 = 995;
      }
      else
      {
        Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, *(unsigned int *)pbOutput);
        v14 = Heap;
        if ( Heap )
        {
          v7 = *(_DWORD *)pbOutput;
          v8 = (PUCHAR)Heap;
LABEL_7:
          if ( phHash )
          {
            if ( v7 >= 0x46 )
            {
              v15 = (_QWORD *)((unsigned __int64)(v8 + 15) & 0xFFFFFFFFFFFFFFF0uLL);
              if ( *(_DWORD *)(v12 + 36) != 2 )
              {
                v21 = -1073741637;
                v30 = 5816;
                v31 = 3221225659LL;
                goto LABEL_73;
              }
              v16 = *(__int64 (__fastcall **)(_QWORD, _QWORD *, unsigned __int64, _QWORD, _QWORD, _DWORD, _DWORD))(v12 + 88);
              v17 = (unsigned int)((_DWORD)v15 - (_DWORD)v8);
              *(_DWORD *)v15 = 40;
              *(_DWORD *)(((unsigned __int64)(v8 + 15) & 0xFFFFFFFFFFFFFFF0uLL) + 4) = 1431655763;
              v18 = v7 - v17 - 40;
              *(_QWORD *)(((unsigned __int64)(v8 + 15) & 0xFFFFFFFFFFFFFFF0uLL) + 8) = v12;
              *(_QWORD *)(((unsigned __int64)(v8 + 15) & 0xFFFFFFFFFFFFFFF0uLL) + 0x20) = v14;
              v67 = v16;
              v19 = &v8[v17 + 40];
              if ( (*(_BYTE *)(v12 + 8) & 8) == 0 )
              {
                v20 = v16(
                        *(_QWORD *)(v12 + 24),
                        v15 + 2,
                        (unsigned __int64)(v19 + 15) & 0xFFFFFFFFFFFFFFF0uLL,
                        v18 + (_DWORD)v19 - (((_DWORD)v19 + 15) & 0xFFFFFFF0),
                        pbSecret,
                        cbSecret,
                        dwFlags);
                v21 = v20;
                if ( v20 >= 0 )
                {
LABEL_12:
                  *phHash = v15;
                  v21 = 0;
LABEL_13:
                  _InterlockedIncrement((volatile signed __int32 *)(v12 + 16));
                  return v21;
                }
                v30 = 6052;
                v31 = (unsigned int)v20;
                goto LABEL_73;
              }
              v48 = *(unsigned int *)(v12 + 12);
              v60 = 0;
              v64 = 0;
              if ( v18 <= (unsigned int)v48 )
              {
                v30 = 5876;
LABEL_72:
                v21 = -1073741811;
                v31 = 3221225485LL;
                goto LABEL_73;
              }
              v66 = *(__int64 (__fastcall **)(_QWORD, UCHAR *, __int64, _QWORD))(v12 + 96);
              v69 = *(__int64 (__fastcall **)(_QWORD, UCHAR *, _QWORD, _QWORD))(v12 + 104);
              v70 = *(__int64 (__fastcall **)(_QWORD, UCHAR *))(v12 + 120);
              v68 = *(__int64 (__fastcall **)(_QWORD, const WCHAR *, unsigned int *, __int64, int *, _DWORD))(v12 + 64);
              v49 = (v18 - (unsigned int)v48) >> 1;
              v65 = (unsigned __int64)&v19[v48 + 15] & 0xFFFFFFFFFFFFFFF0uLL;
              v62 = v49 + (_DWORD)v19 + v48 - (((_DWORD)v19 + v48 + 15) & 0xFFFFFFF0);
              v50 = v16(*(_QWORD *)(v12 + 24), v15 + 2, v65, v62, 0, 0, 0);
              v21 = v50;
              if ( v50 < 0 )
              {
                v30 = 5903;
                v31 = (unsigned int)v50;
                goto LABEL_73;
              }
              v51 = v65 + v62;
              v52 = (v51 + 15) & 0xFFFFFFFFFFFFFFF0uLL;
              v53 = v49 + (_DWORD)v51 - (_DWORD)v52;
              v54 = v67;
              v55 = v67(*(_QWORD *)(v12 + 24), v15 + 3, v52, v53, 0, 0, 0);
              v21 = v55;
              if ( v55 < 0 )
              {
                v30 = 5919;
                v31 = (unsigned int)v55;
                goto LABEL_73;
              }
              if ( *(_DWORD *)(v12 + 12) >= cbSecret )
              {
                memcpy_0(v19, pbSecret, cbSecret);
                v32 = &v19[cbSecret];
                v33 = *(_DWORD *)(v12 + 12) - cbSecret;
                if ( (_DWORD)v33 )
                {
                  do
                  {
                    *v32++ = 0;
                    --v33;
                  }
                  while ( v33 );
                }
              }
              else
              {
                v56 = v68(*(_QWORD *)(v12 + 24), L"HashDigestLength", &v60, 4, &v64, 0);
                v21 = v56;
                if ( v56 < 0 )
                {
                  v30 = 5936;
                  v31 = (unsigned int)v56;
                  goto LABEL_73;
                }
                if ( *(_DWORD *)(v12 + 12) < v60 )
                {
                  v30 = 5944;
                  goto LABEL_72;
                }
                v57 = v66(v15[2], pbSecret, cbSecret, 0);
                v21 = v57;
                if ( v57 < 0 )
                {
                  v30 = 5955;
                  v31 = (unsigned int)v57;
                  goto LABEL_73;
                }
                v58 = v69(v15[2], v19, v60, 0);
                v21 = v58;
                if ( v58 < 0 )
                {
                  v30 = 5966;
                  v31 = (unsigned int)v58;
                  goto LABEL_73;
                }
                v27 = &v19[v60];
                v28 = *(_DWORD *)(v12 + 12) - v60;
                if ( (_DWORD)v28 )
                {
                  do
                  {
                    *v27++ = 0;
                    --v28;
                  }
                  while ( v28 );
                }
                v29 = v70(v15[2], v27);
                v21 = v29;
                if ( v29 < 0 )
                {
                  v30 = 5976;
                  v31 = (unsigned int)v29;
LABEL_73:
                  DebugTraceError(v31, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v30);
LABEL_74:
                  if ( v14 )
                    MSCryptFree(v14);
LABEL_26:
                  if ( v21 < 0 )
                    return v21;
                  goto LABEL_13;
                }
                v59 = v54(*(_QWORD *)(v12 + 24), v15 + 2, v65, v62, 0, 0, 0);
                v21 = v59;
                if ( v59 < 0 )
                {
                  v30 = 5989;
                  v31 = (unsigned int)v59;
                  goto LABEL_73;
                }
              }
              v34 = *(unsigned int *)(v12 + 12);
              for ( i = 0; i < (unsigned int)v34; v34 = *(unsigned int *)(v12 + 12) )
              {
                v36 = i++;
                v19[v36] ^= 0x36u;
              }
              v37 = v66;
              v38 = v66(v15[2], v19, v34, 0);
              v21 = v38;
              if ( v38 < 0 )
              {
                DebugTraceError(
                  (unsigned int)v38,
                  "Status",
                  "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
                  6012);
                v44 = *(unsigned int *)(v12 + 12);
                if ( *(_DWORD *)(v12 + 12) )
                {
                  do
                  {
                    *v19++ = 0;
                    --v44;
                  }
                  while ( v44 );
                }
              }
              else
              {
                v39 = *(unsigned int *)(v12 + 12);
                for ( j = 0; j < (unsigned int)v39; v39 = *(unsigned int *)(v12 + 12) )
                {
                  v41 = j++;
                  v19[v41] ^= 0x6Au;
                }
                v42 = v37(v15[3], v19, v39, 0);
                v21 = v42;
                if ( v42 >= 0 )
                {
                  v45 = *(unsigned int *)(v12 + 12);
                  if ( *(_DWORD *)(v12 + 12) )
                  {
                    do
                    {
                      *v19++ = 0;
                      --v45;
                    }
                    while ( v45 );
                  }
                  goto LABEL_12;
                }
                DebugTraceError(
                  (unsigned int)v42,
                  "Status",
                  "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
                  6030);
                v43 = *(unsigned int *)(v12 + 12);
                if ( *(_DWORD *)(v12 + 12) )
                {
                  do
                  {
                    *v19++ = 0;
                    --v43;
                  }
                  while ( v43 );
                }
              }
              goto LABEL_74;
            }
            v21 = -1073741789;
            v30 = 5803;
            v31 = 3221225507LL;
            goto LABEL_73;
          }
LABEL_71:
          v30 = 5796;
          goto LABEL_72;
        }
        v21 = -1073741801;
        v46 = 3221225495LL;
        v47 = 1003;
      }
      DebugTraceError(v46, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v47);
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v21;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v25,
          v26,
          (unsigned int)"Status",
          v21,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
          148);
      goto LABEL_26;
    }
    v14 = 0;
    if ( !v8 )
      goto LABEL_71;
    goto LABEL_7;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      v13,
      (unsigned int)"Status",
      8,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
      136);
  return -1073741816;
}

```

## disassembly

```asm
0x180006020  mov     [rsp+arg_10], rbx
0x180006025  push    rsi
0x180006026  push    rdi
0x180006027  push    r12
0x180006029  push    r13
0x18000602b  push    r14
0x18000602d  sub     rsp, 0A0h
0x180006034  mov     r14d, r9d
0x180006037  mov     rdi, r8
0x18000603a  mov     r13, rdx
0x18000603d  mov     rsi, rcx
0x180006040  mov     rcx, cs:WPP_GLOBAL_Control
0x180006047  lea     r12, WPP_GLOBAL_Control
0x18000604e  cmp     rcx, r12
0x180006051  jz      short loc_18000605D
0x180006053  test    byte ptr [rcx+1Ch], 4
0x180006057  jnz     loc_18000641A
0x18000605d  mov     rcx, rsi
0x180006060  call    ValidateBaseAlgHandle
0x180006065  mov     rbx, rax
0x180006068  test    rax, rax
0x18000606b  jz      loc_1800061F7
0x180006071  mov     [rsp+0C8h+arg_0], rbp
0x180006079  mov     [rsp+0C8h+arg_8], r15
0x180006081  test    rdi, rdi
0x180006084  jz      loc_180006179
0x18000608a  xor     ebp, ebp
0x18000608c  mov     r15d, ebp
0x18000608f  test    rdi, rdi
0x180006092  jz      loc_1800066AC
0x180006098  test    r13, r13
0x18000609b  jz      loc_1800066AC
0x1800060a1  cmp     r14d, 46h ; 'F'
0x1800060a5  jb      loc_180006486
0x1800060ab  lea     rsi, [rdi+0Fh]
0x1800060af  and     rsi, 0FFFFFFFFFFFFFFF0h
0x1800060b3  cmp     dword ptr [rbx+24h], 2
0x1800060b7  jnz     loc_18000649B
0x1800060bd  mov     r10, [rbx+58h]
0x1800060c1  mov     eax, esi
0x1800060c3  sub     eax, edi
0x1800060c5  mov     dword ptr [rsi], 28h ; '('
0x1800060cb  sub     r14d, eax
0x1800060ce  mov     dword ptr [rsi+4], 55555553h
0x1800060d5  add     r14d, 0FFFFFFD8h
0x1800060d9  mov     [rsi+8], rbx
0x1800060dd  mov     [rsi+20h], r15
0x1800060e1  lea     r12, [rax+28h]
0x1800060e5  mov     [rsp+0C8h+var_50], r10
0x1800060ea  add     r12, rdi
0x1800060ed  test    byte ptr [rbx+8], 8
0x1800060f1  jnz     loc_1800064B0
0x1800060f7  mov     eax, [rsp+0C8h+dwFlags]
0x1800060fe  lea     r8, [r12+0Fh]
0x180006103  mov     rcx, [rbx+18h]
0x180006107  lea     rdx, [rsi+10h]
0x18000610b  mov     [rsp+0C8h+var_98], eax
0x18000610f  and     r8, 0FFFFFFFFFFFFFFF0h
0x180006113  mov     eax, [rsp+0C8h+cbSecret]
0x18000611a  sub     r12d, r8d
0x18000611d  mov     [rsp+0C8h+var_A0], eax
0x180006121  mov     rax, [rsp+0C8h+pbSecret]
0x180006129  mov     [rsp+0C8h+pcbResult], rax
0x18000612e  mov     rax, r10
0x180006131  lea     r9d, [r14+r12]
0x180006135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000613a  mov     edi, eax
0x18000613c  test    eax, eax
0x18000613e  js      loc_1800066A2
0x180006144  mov     [r13+0], rsi
0x180006148  mov     edi, ebp
0x18000614a  lock inc dword ptr [rbx+10h]
0x18000614e  mov     rbp, [rsp+0C8h+arg_0]
0x180006156  mov     eax, edi
0x180006158  mov     r15, [rsp+0C8h+arg_8]
0x180006160  mov     rbx, [rsp+0C8h+arg_10]
0x180006168  add     rsp, 0A0h
0x18000616f  pop     r14
0x180006171  pop     r13
0x180006173  pop     r12
0x180006175  pop     rdi
0x180006176  pop     rsi
0x180006177  retn
0x180006179  test    r14d, r14d
0x18000617c  jnz     loc_18000608A
0x180006182  xor     ebp, ebp
0x180006184  lea     rax, [rsp+0C8h+var_6C]
0x180006189  mov     [rsp+0C8h+var_A0], ebp; dwFlags
0x18000618d  lea     r8, [rsp+0C8h+pbOutput]; pbOutput
0x180006192  mov     r9d, 4; cbOutput
0x180006198  mov     [rsp+0C8h+pcbResult], rax; pcbResult
0x18000619d  lea     rdx, aObjectlength; "ObjectLength"
0x1800061a4  mov     dword ptr [rsp+0C8h+pbOutput], ebp
0x1800061a8  mov     rcx, rsi; hObject
0x1800061ab  mov     [rsp+0C8h+var_6C], ebp
0x1800061af  call    BCryptGetProperty
0x1800061b4  mov     edi, eax
0x1800061b6  test    eax, eax
0x1800061b8  js      loc_180006464
0x1800061be  mov     rcx, gs:60h
0x1800061c7  xor     edx, edx; Flags
0x1800061c9  mov     r8d, dword ptr [rsp+0C8h+pbOutput]; Size
0x1800061ce  mov     rcx, [rcx+30h]; HeapHandle
0x1800061d2  call    cs:__imp_RtlAllocateHeap
0x1800061d9  nop     dword ptr [rax+rax+00h]
0x1800061de  mov     r15, rax
0x1800061e1  test    rax, rax
0x1800061e4  jz      loc_180006471
0x1800061ea  mov     r14d, dword ptr [rsp+0C8h+pbOutput]
0x1800061ef  mov     rdi, rax
0x1800061f2  jmp     loc_180006098
0x1800061f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800061fe  cmp     rcx, r12
0x180006201  jz      short loc_180006235
0x180006203  test    byte ptr [rcx+1Ch], 1
0x180006207  jz      short loc_180006235
0x180006209  mov     rcx, [rcx+10h]
0x18000620d  lea     rsi, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006214  mov     [rsp+0C8h+var_98], 1688h
0x18000621c  lea     r9, aStatus; "Status"
0x180006223  mov     qword ptr [rsp+0C8h+var_A0], rsi
0x180006228  mov     dword ptr [rsp+0C8h+pcbResult], 0C0000008h
0x180006230  call    WPP_SF_sDsd
0x180006235  mov     eax, 0C0000008h
0x18000623a  jmp     loc_180006160
0x18000623f  lea     rsi, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006246  mov     r8, rsi
0x180006249  lea     rdx, aStatus; "Status"
0x180006250  call    DebugTraceError
0x180006255  mov     rcx, cs:WPP_GLOBAL_Control
0x18000625c  cmp     rcx, r12
0x18000625f  jz      loc_18000614E
0x180006265  test    byte ptr [rcx+1Ch], 1
0x180006269  jz      short loc_18000628C
0x18000626b  mov     rcx, [rcx+10h]
0x18000626f  lea     r9, aStatus; "Status"
0x180006276  mov     [rsp+0C8h+var_98], 1694h
0x18000627e  mov     qword ptr [rsp+0C8h+var_A0], rsi
0x180006283  mov     dword ptr [rsp+0C8h+pcbResult], edi
0x180006287  call    WPP_SF_sDsd
0x18000628c  test    edi, edi
0x18000628e  jns     loc_18000614A
0x180006294  jmp     loc_18000614E
0x180006299  mov     ecx, [rsp+0C8h+var_78]
0x18000629d  mov     r8d, [rbx+0Ch]
0x1800062a1  lea     rdx, [r12+rcx]
0x1800062a5  sub     r8d, ecx
0x1800062a8  jz      short loc_1800062B7
0x1800062aa  mov     byte ptr [rdx], 0
0x1800062ad  lea     rdx, [rdx+1]
0x1800062b1  sub     r8, 1
0x1800062b5  jnz     short loc_1800062AA
0x1800062b7  mov     rcx, [rsi+10h]
0x1800062bb  mov     rax, [rsp+0C8h+var_38]
0x1800062c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062c8  mov     edi, eax
0x1800062ca  test    eax, eax
0x1800062cc  jns     loc_180006667
0x1800062d2  mov     r9d, 1758h
0x1800062d8  mov     ecx, eax
0x1800062da  jmp     loc_1800066BC
0x1800062df  mov     rdx, [rsp+0C8h+pbSecret]; Src
0x1800062e7  mov     r8, rax; Size
0x1800062ea  mov     rcx, r12; void *
0x1800062ed  mov     rdi, rax
0x1800062f0  call    memcpy_0
0x1800062f5  mov     ecx, [rbx+0Ch]
0x1800062f8  lea     rax, [rdi+r12]
0x1800062fc  sub     ecx, [rsp+0C8h+cbSecret]
0x180006303  jz      short loc_180006312
0x180006305  mov     byte ptr [rax], 0
0x180006308  lea     rax, [rax+1]
0x18000630c  sub     rcx, 1
0x180006310  jnz     short loc_180006305
0x180006312  mov     r8d, [rbx+0Ch]
0x180006316  mov     ecx, ebp
0x180006318  test    r8d, r8d
0x18000631b  jz      short loc_18000632F
0x18000631d  mov     eax, ecx
0x18000631f  inc     ecx
0x180006321  xor     byte ptr [rax+r12], 36h
0x180006326  mov     r8d, [rbx+0Ch]
0x18000632a  cmp     ecx, r8d
0x18000632d  jb      short loc_18000631D
0x18000632f  mov     r14, [rsp+0C8h+var_58]
0x180006334  xor     r9d, r9d
0x180006337  mov     rcx, [rsi+10h]
0x18000633b  mov     rax, r14
0x18000633e  mov     rdx, r12
0x180006341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006346  mov     edi, eax
0x180006348  test    eax, eax
0x18000634a  js      short loc_1800063BD
0x18000634c  mov     r8d, [rbx+0Ch]
0x180006350  mov     ecx, ebp
0x180006352  test    r8d, r8d
0x180006355  jz      short loc_180006369
0x180006357  mov     eax, ecx
0x180006359  inc     ecx
0x18000635b  xor     byte ptr [rax+r12], 6Ah
0x180006360  mov     r8d, [rbx+0Ch]
0x180006364  cmp     ecx, r8d
0x180006367  jb      short loc_180006357
0x180006369  mov     rcx, [rsi+18h]
0x18000636d  xor     r9d, r9d
0x180006370  mov     rdx, r12
0x180006373  mov     rax, r14
0x180006376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000637b  mov     edi, eax
0x18000637d  test    eax, eax
0x18000637f  jns     short loc_1800063F9
0x180006381  mov     r9d, 178Eh
0x180006387  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000638e  lea     rdx, aStatus; "Status"
0x180006395  mov     ecx, eax
0x180006397  call    DebugTraceError
0x18000639c  mov     eax, [rbx+0Ch]
0x18000639f  test    rax, rax
0x1800063a2  jz      loc_1800066CF
0x1800063a8  mov     byte ptr [r12], 0
0x1800063ad  lea     r12, [r12+1]
0x1800063b2  sub     rax, 1
0x1800063b6  jnz     short loc_1800063A8
0x1800063b8  jmp     loc_1800066CF
0x1800063bd  mov     r9d, 177Ch
0x1800063c3  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800063ca  lea     rdx, aStatus; "Status"
0x1800063d1  mov     ecx, eax
0x1800063d3  call    DebugTraceError
0x1800063d8  mov     eax, [rbx+0Ch]
0x1800063db  test    rax, rax
0x1800063de  jz      loc_1800066CF
0x1800063e4  mov     byte ptr [r12], 0
0x1800063e9  lea     r12, [r12+1]
0x1800063ee  sub     rax, 1
0x1800063f2  jnz     short loc_1800063E4
0x1800063f4  jmp     loc_1800066CF
0x1800063f9  mov     eax, [rbx+0Ch]
0x1800063fc  test    rax, rax
0x1800063ff  jz      loc_180006144
0x180006405  mov     byte ptr [r12], 0
0x18000640a  lea     r12, [r12+1]
0x18000640f  sub     rax, 1
0x180006413  jnz     short loc_180006405
0x180006415  jmp     loc_180006144
0x18000641a  mov     eax, [rsp+0C8h+dwFlags]
0x180006421  mov     edx, 21h ; '!'
0x180006426  mov     r8d, [rsp+0C8h+cbSecret]
0x18000642e  mov     r9, rsi
0x180006431  mov     rcx, [rcx+10h]
0x180006435  mov     [rsp+0C8h+var_80], eax
0x180006439  mov     rax, [rsp+0C8h+pbSecret]
0x180006441  mov     [rsp+0C8h+var_88], r8d
0x180006446  mov     [rsp+0C8h+var_90], rax
0x18000644b  mov     [rsp+0C8h+var_98], r14d
0x180006450  mov     qword ptr [rsp+0C8h+var_A0], rdi
0x180006455  mov     [rsp+0C8h+pcbResult], r13
0x18000645a  call    WPP_SF_qqqdqdD
0x18000645f  jmp     loc_18000605D
0x180006464  mov     ecx, eax
0x180006466  mov     r9d, 3E3h
0x18000646c  jmp     loc_18000623F
0x180006471  mov     edi, 0C0000017h
0x180006476  mov     ecx, 0C0000017h
0x18000647b  mov     r9d, 3EBh
0x180006481  jmp     loc_18000623F
0x180006486  mov     edi, 0C0000023h
0x18000648b  mov     r9d, 16ABh
0x180006491  mov     ecx, 0C0000023h
0x180006496  jmp     loc_1800066BC
0x18000649b  mov     edi, 0C00000BBh
0x1800064a0  mov     r9d, 16B8h
0x1800064a6  mov     ecx, 0C00000BBh
0x1800064ab  jmp     loc_1800066BC
0x1800064b0  mov     eax, [rbx+0Ch]
0x1800064b3  mov     [rsp+0C8h+var_78], ebp
0x1800064b7  mov     [rsp+0C8h+var_68], ebp
0x1800064bb  cmp     r14d, eax
0x1800064be  ja      short loc_1800064CB
0x1800064c0  mov     r9d, 16F4h
0x1800064c6  jmp     loc_1800066B2
0x1800064cb  mov     rcx, [rbx+60h]
0x1800064cf  sub     r14d, eax
0x1800064d2  mov     [rsp+0C8h+var_58], rcx
0x1800064d7  mov     rcx, [rbx+68h]
0x1800064db  mov     [rsp+0C8h+var_40], rcx
0x1800064e3  mov     rcx, [rbx+78h]
0x1800064e7  mov     [rsp+0C8h+var_38], rcx
0x1800064ef  mov     rcx, [rbx+40h]
0x1800064f3  mov     [rsp+0C8h+var_48], rcx
0x1800064fb  lea     rcx, [r12+rax]
0x1800064ff  lea     rdx, [rcx+0Fh]
0x180006503  mov     [rsp+0C8h+var_98], ebp
0x180006507  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18000650b  shr     r14d, 1
0x18000650e  sub     ecx, edx
0x180006510  mov     [rsp+0C8h+var_60], rdx
0x180006515  add     ecx, r14d
0x180006518  mov     [rsp+0C8h+var_A0], ebp
0x18000651c  mov     [rsp+0C8h+var_70], ecx
  ... truncated ...
```
