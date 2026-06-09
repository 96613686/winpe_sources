# WimFSFCheckIntegrityOfBlocks

- ea: `0x140027ffc`
- end: `0x1400284d0`
- name: `WimFSFCheckIntegrityOfBlocks`
- size: `1236`
- prototype: `__int64 __fastcall(PRTL_BITMAP BitMapHeader, __int64, __int64, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000cae0`
- `0x140028f44`
- `0x14002a3e4`

## callees

- `0x140011560`
- `0x140011640`
- `0x140027ffc`
- `0x14002962c`
- `0x140029ca0`
- `0x140029f78`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400283e1`
- `ntoskrnl!RtlCompareMemory` at `0x1400283e1`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400280fc`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400280fc`
- `ntoskrnl!RtlSetBit` at `0x14002840d`
- `ntoskrnl!RtlSetBit` at `0x14002840d`
- `ntoskrnl!RtlAreBitsSet` at `0x1400280cd`
- `ntoskrnl!RtlAreBitsSet` at `0x1400280cd`
- `ntoskrnl!PsInitialSystemProcess` at `0x140028396`
- `ntoskrnl!KeStackAttachProcess` at `0x1400283a0`
- `ntoskrnl!KeStackAttachProcess` at `0x1400283a0`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002847f`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002847f`
- `ntoskrnl!RtlTestBit` at `0x1400280b2`
- `ntoskrnl!RtlTestBit` at `0x140028157`
- `ntoskrnl!RtlTestBit` at `0x1400280b2`
- `ntoskrnl!RtlTestBit` at `0x140028157`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140028449`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140028461`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140028449`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140028461`

## pseudocode

```c
__int64 __fastcall WimFSFCheckIntegrityOfBlocks(PRTL_BITMAP BitMapHeader, __int64 a2, __int64 a3, unsigned int a4)
{
  unsigned int v4; // r13d
  int v7; // ebx
  ULONG v8; // r12d
  char *v9; // rsi
  ULONG v10; // ecx
  ULONG v11; // edx
  ULONG v12; // r15d
  unsigned int v13; // r8d
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rdx
  int v20; // eax
  int v21; // eax
  ULONG v22; // eax
  ULONG Length; // [rsp+30h] [rbp-88h] BYREF
  ULONG BitNumber; // [rsp+34h] [rbp-84h] BYREF
  ULONG v27; // [rsp+3Ch] [rbp-7Ch] BYREF
  __int64 v28; // [rsp+40h] [rbp-78h]
  char *v29; // [rsp+48h] [rbp-70h]
  PLOOKASIDE_LIST_EX Lookaside; // [rsp+50h] [rbp-68h]
  _KAPC_STATE ApcState; // [rsp+58h] [rbp-60h] BYREF

  v4 = a4;
  v28 = a3;
  memset(&ApcState, 0, sizeof(ApcState));
  Length = 0;
  v27 = 0;
  BitNumber = 0;
  if ( BitMapHeader && a4 )
  {
    if ( !(unsigned __int8)WimpFSFCalculateBlockIndices(
                             (_DWORD)BitMapHeader,
                             a2,
                             a4,
                             (unsigned int)&BitNumber,
                             (__int64)&Length,
                             (__int64)&v27) )
    {
      WimpFSFIntegrityReportReadFailure(BitMapHeader, a2, v4);
      v7 = -1073741116;
      goto LABEL_39;
    }
    v8 = BitNumber;
    if ( RtlTestBit(BitMapHeader, BitNumber) && RtlAreBitsSet(BitMapHeader, v8, Length) )
    {
      _InterlockedAdd64(&g_PagesFaultedOnAgain, Length);
      return 0;
    }
    Lookaside = (PLOOKASIDE_LIST_EX)&BitMapHeader[4];
    v9 = (char *)ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)&BitMapHeader[4]);
    v29 = v9;
    if ( !v9 )
    {
      v7 = -1073741801;
      goto LABEL_39;
    }
    v7 = 0;
    while ( 1 )
    {
      if ( v8 >= v27 )
      {
        ExFreeToLookasideListEx(Lookaside, v9);
        if ( v7 >= 0 )
          return (unsigned int)v7;
LABEL_39:
        if ( WimSqmIsOptedIn )
          _InterlockedIncrement64(&WimIntegityFailureCount);
        return (unsigned int)v7;
      }
      v10 = 0;
      Length = 0;
      v11 = 32;
      if ( v27 - v8 < 0x20 )
        v11 = v27 - v8;
      BitNumber = v11;
      v12 = 0;
      if ( v11 )
        break;
LABEL_26:
      if ( v10 )
      {
        KeStackAttachProcess(PsInitialSystemProcess, &ApcState);
LABEL_28:
        v22 = Length;
        while ( v12 )
        {
          if ( _bittest((const int *)&v22, --v12) )
          {
            if ( RtlCompareMemory(&v9[32 * v12 + 128], &BitMapHeader[2].Buffer[4 * v12 + 4 * v8], 0x10u) == 16 )
            {
              if ( !LODWORD(BitMapHeader[11].Buffer) )
                RtlSetBit(BitMapHeader, v12 + v8);
              _InterlockedIncrement(&g_PagesValidated);
            }
            else
            {
              WimpFSFIntegrityReportBlockFailure(BitMapHeader, v12 + v8);
              v7 = -1073741116;
            }
            goto LABEL_28;
          }
        }
        KeUnstackDetachProcess(&ApcState);
      }
      v8 += BitNumber;
    }
    while ( 1 )
    {
      if ( RtlTestBit(BitMapHeader, v12 + v8) )
      {
        v28 += 4096;
        _InterlockedIncrement64(&g_PagesFaultedOnAgain);
      }
      else
      {
        v13 = v4;
        if ( v4 > 0x1000 )
          v13 = 4096;
        v14 = v13 >> 2;
        *((_DWORD *)v9 + 290) = 0;
        *((_DWORD *)v9 + 291) = 1;
        v15 = v28;
        *((_QWORD *)v9 + 146) = v28;
        *((_DWORD *)v9 + 294) = v14;
        *((_DWORD *)v9 + 296) = 0;
        *((_DWORD *)v9 + 297) = 2;
        *((_QWORD *)v9 + 149) = v9;
        *((_DWORD *)v9 + 300) = 32;
        v16 = v14 + v15;
        *((_DWORD *)v9 + 302) = 1;
        *((_DWORD *)v9 + 303) = 1;
        *((_QWORD *)v9 + 152) = v16;
        *((_DWORD *)v9 + 306) = v14;
        *((_DWORD *)v9 + 308) = 1;
        *((_DWORD *)v9 + 309) = 2;
        *((_QWORD *)v9 + 155) = v9 + 32;
        *((_DWORD *)v9 + 312) = 32;
        v17 = v14 + v16;
        *((_DWORD *)v9 + 314) = 2;
        *((_DWORD *)v9 + 315) = 1;
        *((_QWORD *)v9 + 158) = v17;
        *((_DWORD *)v9 + 318) = v14;
        *((_DWORD *)v9 + 320) = 2;
        *((_DWORD *)v9 + 321) = 2;
        *((_QWORD *)v9 + 161) = v9 + 64;
        *((_DWORD *)v9 + 324) = 32;
        v18 = v14 + v17;
        *((_DWORD *)v9 + 326) = 3;
        *((_DWORD *)v9 + 327) = 1;
        *((_QWORD *)v9 + 164) = v18;
        v19 = v13 - 3 * (_DWORD)v14;
        *((_DWORD *)v9 + 330) = v19;
        *((_DWORD *)v9 + 332) = 3;
        *((_DWORD *)v9 + 333) = 2;
        *((_QWORD *)v9 + 167) = v9 + 96;
        *((_DWORD *)v9 + 336) = 32;
        v28 = v18 + v19;
        v20 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *, __int64, _DWORD))(g_WimIntegrityCngExtensions + 16))(
                *((_QWORD *)v9 + 144),
                1,
                v9 + 1160,
                192,
                0);
        if ( v20 >= 0 )
        {
          *((_QWORD *)v9 + 146) = v9;
          *((_DWORD *)v9 + 294) = 128;
          *((_QWORD *)v9 + 149) = &v9[32 * v12 + 128];
          *((_DWORD *)v9 + 300) = 32;
          v21 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(g_WimIntegrityCngExtensions + 16))(
                  *((_QWORD *)v9 + 144),
                  1,
                  v9 + 1160);
          v10 = Length;
          if ( v21 >= 0 )
          {
            v10 = Length | (1 << v12);
            Length = v10;
          }
          else
          {
            v7 = v21;
          }
          goto LABEL_25;
        }
        v7 = v20;
      }
      v10 = Length;
LABEL_25:
      ++v12;
      v4 -= 4096;
      if ( v12 >= BitNumber )
        goto LABEL_26;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140027ffc  mov     [rsp+arg_10], rbx
0x140028001  push    rsi
0x140028002  push    r12
0x140028004  push    r13
0x140028006  push    r14
0x140028008  push    r15
0x14002800a  sub     rsp, 90h
0x140028011  mov     rax, cs:__security_cookie
0x140028018  xor     rax, rsp
0x14002801b  mov     [rsp+0B8h+var_30], rax
0x140028023  mov     r13d, r9d
0x140028026  mov     [rsp+0B8h+var_78], r8
0x14002802b  mov     rbx, rdx
0x14002802e  mov     r14, rcx
0x140028031  xorps   xmm0, xmm0
0x140028034  movups  xmmword ptr [rsp+0B8h+ApcState.ApcListHead.Flink], xmm0
0x140028039  movups  xmmword ptr [rsp+0B8h+ApcState.ApcListHead.Flink+10h], xmm0
0x14002803e  movups  xmmword ptr [rsp+0B8h+ApcState.Process], xmm0
0x140028043  mov     [rsp+0B8h+Length], 0
0x14002804b  mov     [rsp+0B8h+var_7C], 0
0x140028053  mov     [rsp+0B8h+BitNumber], 0
0x14002805b  test    rcx, rcx
0x14002805e  jz      loc_1400284A4
0x140028064  test    r9d, r9d
0x140028067  jz      loc_1400284A4
0x14002806d  lea     rax, [rsp+0B8h+var_7C]
0x140028072  mov     [rsp+0B8h+var_90], rax
0x140028077  lea     rax, [rsp+0B8h+Length]
0x14002807c  mov     [rsp+0B8h+var_98], rax
0x140028081  lea     r9, [rsp+0B8h+BitNumber]
0x140028086  mov     r8d, r13d
0x140028089  call    WimpFSFCalculateBlockIndices
0x14002808e  mov     rcx, r14; BitMapHeader
0x140028091  test    al, al
0x140028093  jnz     short loc_1400280AA
0x140028095  mov     r8d, r13d
0x140028098  mov     rdx, rbx
0x14002809b  call    WimpFSFIntegrityReportReadFailure
0x1400280a0  mov     ebx, 0C00002C4h
0x1400280a5  jmp     loc_14002848F
0x1400280aa  mov     r12d, [rsp+0B8h+BitNumber]
0x1400280af  mov     edx, r12d; BitNumber
0x1400280b2  call    cs:__imp_RtlTestBit
0x1400280b9  nop     dword ptr [rax+rax+00h]
0x1400280be  test    al, al
0x1400280c0  jz      short loc_1400280F0
0x1400280c2  mov     r8d, [rsp+0B8h+Length]; Length
0x1400280c7  mov     edx, r12d; StartingIndex
0x1400280ca  mov     rcx, r14; BitMapHeader
0x1400280cd  call    cs:__imp_RtlAreBitsSet
0x1400280d4  nop     dword ptr [rax+rax+00h]
0x1400280d9  test    al, al
0x1400280db  jz      short loc_1400280F0
0x1400280dd  mov     eax, [rsp+0B8h+Length]
0x1400280e1  lock add cs:g_PagesFaultedOnAgain, rax
0x1400280e9  xor     ebx, ebx
0x1400280eb  jmp     loc_1400284A0
0x1400280f0  lea     rax, [r14+40h]
0x1400280f4  mov     [rsp+0B8h+Lookaside], rax
0x1400280f9  mov     rcx, rax; Lookaside
0x1400280fc  call    cs:__imp_ExAllocateFromLookasideListEx
0x140028103  nop     dword ptr [rax+rax+00h]
0x140028108  mov     rsi, rax
0x14002810b  mov     [rsp+0B8h+var_70], rax
0x140028110  test    rax, rax
0x140028113  jnz     short loc_14002811F
0x140028115  mov     ebx, 0C0000017h
0x14002811a  jmp     loc_14002848F
0x14002811f  xor     ebx, ebx
0x140028121  cmp     r12d, [rsp+0B8h+var_7C]
0x140028126  jnb     loc_140028477
0x14002812c  xor     ecx, ecx
0x14002812e  mov     [rsp+0B8h+Length], ecx
0x140028132  mov     eax, [rsp+0B8h+var_7C]
0x140028136  sub     eax, r12d
0x140028139  lea     edx, [rcx+20h]
0x14002813c  cmp     eax, edx
0x14002813e  cmovb   edx, eax
0x140028141  mov     [rsp+0B8h+BitNumber], edx
0x140028145  xor     r15d, r15d
0x140028148  test    edx, edx
0x14002814a  jz      loc_140028389
0x140028150  lea     edx, [r15+r12]; BitNumber
0x140028154  mov     rcx, r14; BitMapHeader
0x140028157  call    cs:__imp_RtlTestBit
0x14002815e  nop     dword ptr [rax+rax+00h]
0x140028163  test    al, al
0x140028165  jz      short loc_140028181
0x140028167  add     [rsp+0B8h+var_78], 1000h
0x140028170  lock inc cs:g_PagesFaultedOnAgain
0x140028178  mov     ecx, [rsp+0B8h+Length]
0x14002817c  jmp     loc_140028374
0x140028181  mov     r8d, r13d
0x140028184  mov     eax, 1000h
0x140028189  cmp     r13d, eax
0x14002818c  cmova   r8d, eax
0x140028190  mov     edx, r8d
0x140028193  shr     edx, 2
0x140028196  lea     r10, [rsi+488h]
0x14002819d  mov     dword ptr [r10], 0
0x1400281a4  mov     dword ptr [rsi+48Ch], 1
0x1400281ae  mov     rcx, [rsp+0B8h+var_78]
0x1400281b3  mov     [rsi+490h], rcx
0x1400281ba  mov     [rsi+498h], edx
0x1400281c0  mov     dword ptr [rsi+4A0h], 0
0x1400281ca  mov     r11d, 2
0x1400281d0  mov     [rsi+4A4h], r11d
0x1400281d7  mov     [rsi+4A8h], rsi
0x1400281de  lea     r9d, [r11+1Eh]
0x1400281e2  mov     [rsi+4B0h], r9d
0x1400281e9  add     rcx, rdx
0x1400281ec  mov     dword ptr [rsi+4B8h], 1
0x1400281f6  mov     dword ptr [rsi+4BCh], 1
0x140028200  mov     [rsi+4C0h], rcx
0x140028207  mov     [rsi+4C8h], edx
0x14002820d  mov     dword ptr [rsi+4D0h], 1
0x140028217  mov     [rsi+4D4h], r11d
0x14002821e  lea     rax, [rsi+20h]
0x140028222  mov     [rsi+4D8h], rax
0x140028229  mov     [rsi+4E0h], r9d
0x140028230  add     rcx, rdx
0x140028233  mov     [rsi+4E8h], r11d
0x14002823a  mov     dword ptr [rsi+4ECh], 1
0x140028244  mov     [rsi+4F0h], rcx
0x14002824b  mov     [rsi+4F8h], edx
0x140028251  mov     [rsi+500h], r11d
0x140028258  mov     [rsi+504h], r11d
0x14002825f  lea     rax, [rsi+40h]
0x140028263  mov     [rsi+508h], rax
0x14002826a  mov     [rsi+510h], r9d
0x140028271  add     rcx, rdx
0x140028274  mov     dword ptr [rsi+518h], 3
0x14002827e  mov     dword ptr [rsi+51Ch], 1
0x140028288  mov     [rsi+520h], rcx
0x14002828f  lea     eax, [rdx+rdx*2]
0x140028292  sub     r8d, eax
0x140028295  mov     edx, r8d
0x140028298  mov     [rsi+528h], edx
0x14002829e  mov     dword ptr [rsi+530h], 3
0x1400282a8  mov     [rsi+534h], r11d
0x1400282af  lea     rax, [rsi+60h]
0x1400282b3  mov     [rsi+538h], rax
0x1400282ba  mov     [rsi+540h], r9d
0x1400282c1  add     rdx, rcx
0x1400282c4  mov     [rsp+0B8h+var_78], rdx
0x1400282c9  mov     rax, cs:g_WimIntegrityCngExtensions
0x1400282d0  mov     rax, [rax+10h]
0x1400282d4  mov     dword ptr [rsp+0B8h+var_98], 0
0x1400282dc  mov     r9d, 0C0h
0x1400282e2  mov     r8, r10
0x1400282e5  lea     edx, [r11-1]
0x1400282e9  mov     rcx, [rsi+480h]
0x1400282f0  call    _guard_dispatch_icall
0x1400282f5  test    eax, eax
0x1400282f7  jns     short loc_140028300
0x1400282f9  mov     ebx, eax
0x1400282fb  jmp     loc_140028178
0x140028300  mov     [rsi+490h], rsi
0x140028307  mov     dword ptr [rsi+498h], 80h
0x140028311  mov     eax, r15d
0x140028314  add     rax, 4
0x140028318  shl     rax, 5
0x14002831c  add     rax, rsi
0x14002831f  mov     [rsi+4A8h], rax
0x140028326  mov     dword ptr [rsi+4B0h], 20h ; ' '
0x140028330  mov     rax, cs:g_WimIntegrityCngExtensions
0x140028337  mov     rax, [rax+10h]
0x14002833b  mov     dword ptr [rsp+0B8h+var_98], 0
0x140028343  mov     r9d, 30h ; '0'
0x140028349  lea     r8, [rsi+488h]
0x140028350  lea     edx, [r9-2Fh]
0x140028354  mov     rcx, [rsi+480h]
0x14002835b  call    _guard_dispatch_icall
0x140028360  mov     ecx, [rsp+0B8h+Length]
0x140028364  test    eax, eax
0x140028366  jns     short loc_14002836C
0x140028368  mov     ebx, eax
0x14002836a  jmp     short loc_140028374
0x14002836c  bts     ecx, r15d
0x140028370  mov     [rsp+0B8h+Length], ecx
0x140028374  inc     r15d
0x140028377  add     r13d, 0FFFFF000h
0x14002837e  cmp     r15d, [rsp+0B8h+BitNumber]
0x140028383  jb      loc_140028150
0x140028389  test    ecx, ecx
0x14002838b  jz      loc_14002846D
0x140028391  lea     rdx, [rsp+0B8h+ApcState]; ApcState
0x140028396  mov     rcx, cs:__imp_PsInitialSystemProcess
0x14002839d  mov     rcx, [rcx]; PROCESS
0x1400283a0  call    cs:__imp_KeStackAttachProcess
0x1400283a7  nop     dword ptr [rax+rax+00h]
0x1400283ac  mov     eax, [rsp+0B8h+Length]
0x1400283b0  test    r15d, r15d
0x1400283b3  jz      loc_14002845C
0x1400283b9  dec     r15d
0x1400283bc  bt      eax, r15d
0x1400283c0  jnb     short loc_1400283B0
0x1400283c2  lea     edx, [r15+r12]
0x1400283c6  shl     edx, 4
0x1400283c9  add     rdx, [r14+28h]; Source2
0x1400283cd  mov     ecx, r15d
0x1400283d0  add     rcx, 4
0x1400283d4  shl     rcx, 5
0x1400283d8  add     rcx, rsi; Source1
0x1400283db  mov     r8d, 10h; Length
0x1400283e1  call    cs:__imp_RtlCompareMemory
0x1400283e8  nop     dword ptr [rax+rax+00h]
0x1400283ed  cmp     rax, 10h
0x1400283f1  setz    al
0x1400283f4  mov     [rsp+0B8h+var_80], al
0x1400283f8  test    al, al
0x1400283fa  jz      short loc_140028422
0x1400283fc  cmp     dword ptr [r14+0B8h], 0
0x140028404  jnz     short loc_140028419
0x140028406  lea     edx, [r15+r12]; BitNumber
0x14002840a  mov     rcx, r14; BitMapHeader
0x14002840d  call    cs:__imp_RtlSetBit
0x140028414  nop     dword ptr [rax+rax+00h]
0x140028419  lock inc cs:g_PagesValidated
0x140028420  jmp     short loc_1400283AC
0x140028422  lea     edx, [r15+r12]
0x140028426  mov     rcx, r14
0x140028429  call    WimpFSFIntegrityReportBlockFailure
0x14002842e  mov     ebx, 0C00002C4h
0x140028433  jmp     loc_1400283AC
0x140028438  mov     ebx, eax
0x14002843a  mov     eax, 0C00002C4h
0x14002843f  test    ebx, ebx
0x140028441  cmovns  ebx, eax
0x140028444  lea     rcx, [rsp+0B8h+ApcState]; ApcState
0x140028449  call    cs:__imp_KeUnstackDetachProcess
0x140028450  nop     dword ptr [rax+rax+00h]
0x140028455  mov     rsi, [rsp+0B8h+var_70]
0x14002845a  jmp     short loc_140028477
0x14002845c  lea     rcx, [rsp+0B8h+ApcState]; ApcState
0x140028461  call    cs:__imp_KeUnstackDetachProcess
0x140028468  nop     dword ptr [rax+rax+00h]
0x14002846d  add     r12d, [rsp+0B8h+BitNumber]
0x140028472  jmp     loc_140028121
0x140028477  mov     rdx, rsi; Entry
0x14002847a  mov     rcx, [rsp+0B8h+Lookaside]; Lookaside
0x14002847f  call    cs:__imp_ExFreeToLookasideListEx
0x140028486  nop     dword ptr [rax+rax+00h]
0x14002848b  test    ebx, ebx
0x14002848d  jns     short loc_1400284A0
0x14002848f  cmp     cs:WimSqmIsOptedIn, 0
0x140028496  jz      short loc_1400284A0
0x140028498  lock inc cs:WimIntegityFailureCount
0x1400284a0  mov     eax, ebx
0x1400284a2  jmp     short loc_1400284A6
0x1400284a4  xor     eax, eax
0x1400284a6  mov     rcx, [rsp+0B8h+var_30]
0x1400284ae  xor     rcx, rsp; StackCookie
0x1400284b1  call    __security_check_cookie
0x1400284b6  mov     rbx, [rsp+0B8h+arg_10]
0x1400284be  add     rsp, 90h
0x1400284c5  pop     r15
0x1400284c7  pop     r14
0x1400284c9  pop     r13
0x1400284cb  pop     r12
0x1400284cd  pop     rsi
0x1400284ce  retn
```
