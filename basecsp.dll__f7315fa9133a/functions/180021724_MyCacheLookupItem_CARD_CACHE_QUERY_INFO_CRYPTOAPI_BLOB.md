# MyCacheLookupItem(_CARD_CACHE_QUERY_INFO *,_CRYPTOAPI_BLOB *)

- ea: `0x180021724`
- end: `0x18002191f`
- name: `?MyCacheLookupItem@@YAKPEAU_CARD_CACHE_QUERY_INFO@@PEAU_CRYPTOAPI_BLOB@@@Z`
- size: `507`
- prototype: `unsigned int __fastcall(struct _CARD_CACHE_QUERY_INFO *, struct _CRYPTOAPI_BLOB *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180021bc8`

## callees

- `0x18000a766`
- `0x18000de80`
- `0x180017bac`
- `0x180019430`
- `0x180019650`
- `0x18001f3a4`
- `0x180021724`
- `0x18002896c`

## import_xrefs

- `WinSCard!SCardFreeMemory` at `0x180021902`
- `WinSCard!SCardFreeMemory` at `0x180021902`
- `WinSCard!SCardReadCacheW` at `0x180021811`
- `WinSCard!SCardReadCacheW` at `0x180021811`

## pseudocode

```c
__int64 __fastcall MyCacheLookupItem(struct _CARD_CACHE_QUERY_INFO *a1, struct _CRYPTOAPI_BLOB *a2)
{
  __int64 v3; // rdx
  _DWORD *v5; // rcx
  unsigned int v6; // ebx
  int v7; // r9d
  DWORD v8; // r8d
  int v9; // eax
  int v10; // ebp
  LONG CacheW; // eax
  struct _RTL_CRITICAL_SECTION *v12; // rcx
  size_t v13; // rcx
  BYTE *v14; // rax
  __int64 v15; // rcx
  int Data; // [rsp+20h] [rbp-58h]
  int DataLen; // [rsp+28h] [rbp-50h]
  BYTE v19[16]; // [rsp+40h] [rbp-38h] BYREF

  v3 = *(_QWORD *)a1;
  *(_OWORD *)v19 = 0;
  v5 = *(_DWORD **)(v3 + 8);
  if ( !v5 )
  {
    v6 = 87;
    WppTraceIndent(0, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_ss(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids,
        v7,
        (__int64)"pInfo->pCardState->pCardData");
    }
    return v6;
  }
  v8 = 0;
  if ( (*((_BYTE *)a1 + 8) & 2) != 0 )
    v8 = *((unsigned __int16 *)a1 + 271);
  if ( (*((_BYTE *)a1 + 8) & 4) != 0 )
    v8 += *((unsigned __int16 *)a1 + 272);
  v9 = *((_DWORD *)a1 + 4);
  if ( v9 )
  {
    if ( v9 != 1 )
      return 1359;
    v12 = *(struct _RTL_CRITICAL_SECTION **)(v3 + 680);
  }
  else
  {
    if ( *((_DWORD *)a1 + 2) != 1 && (*v5 < 6u || *(_DWORD *)(v3 + 696) != 2) )
    {
      *(_DWORD *)v19 = -1;
      v10 = 1;
      CacheW = SCardReadCacheW(
                 *(_QWORD *)(*(_QWORD *)(v3 + 8) + 96LL),
                 *(UUID **)(v3 + 552),
                 v8,
                 (LPWSTR)a1 + 10,
                 &v19[8],
                 (DWORD *)v19);
      goto LABEL_20;
    }
    v12 = *(struct _RTL_CRITICAL_SECTION **)(v3 + 672);
  }
  v10 = 0;
  CacheW = ScCacheRead(v12, Data, DataLen, (__int64)&v19[8], (__int64)v19);
LABEL_20:
  v6 = CacheW;
  if ( CacheW )
  {
    if ( CacheW == -2146434960 || CacheW == -2146434959 )
      return 1168;
  }
  else
  {
    v13 = *(unsigned int *)v19;
    a2->cbData = *(_DWORD *)v19;
    v14 = (BYTE *)MIDL_user_allocate(v13);
    a2->pbData = v14;
    if ( v14 )
    {
      memcpy_0(v14, *(const void **)&v19[8], a2->cbData);
    }
    else
    {
      WppTraceIndent(v15, 2);
      v6 = 8;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids,
          WPP_pszIndent);
      }
    }
    if ( v10 )
      SCardFreeMemory(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 8LL) + 96LL), *(LPCVOID *)&v19[8]);
    else
      CspFreeH(*(_QWORD *)&v19[8]);
  }
  return v6;
}

```

## disassembly

```asm
0x180021724  push    rbx
0x180021726  push    rbp
0x180021727  push    rsi
0x180021728  push    rdi
0x180021729  sub     rsp, 58h
0x18002172d  mov     rsi, rdx
0x180021730  xorps   xmm0, xmm0
0x180021733  mov     rdx, [rcx]
0x180021736  mov     rdi, rcx
0x180021739  movups  xmmword ptr [rsp+78h+var_38], xmm0
0x18002173e  mov     rcx, [rdx+8]
0x180021742  test    rcx, rcx
0x180021745  jnz     short loc_1800217A1
0x180021747  lea     edx, [rcx+2]
0x18002174a  lea     ebx, [rcx+57h]
0x18002174d  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180021752  mov     rcx, cs:WPP_GLOBAL_Control
0x180021759  lea     rax, WPP_GLOBAL_Control
0x180021760  cmp     rcx, rax
0x180021763  jz      loc_180021914
0x180021769  test    byte ptr [rcx+1Ch], 1
0x18002176d  jz      loc_180021914
0x180021773  cmp     byte ptr [rcx+19h], 2
0x180021777  jb      loc_180021914
0x18002177d  mov     rcx, [rcx+10h]
0x180021781  lea     rax, aPinfoPcardstat; "pInfo->pCardState->pCardData"
0x180021788  lea     edx, [rbx-4Ch]
0x18002178b  mov     [rsp+78h+Data], rax
0x180021790  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x180021797  call    WPP_SF_ss
0x18002179c  jmp     loc_180021914
0x1800217a1  xor     r8d, r8d
0x1800217a4  test    byte ptr [rdi+8], 2
0x1800217a8  jz      short loc_1800217B2
0x1800217aa  movzx   r8d, word ptr [rdi+21Eh]
0x1800217b2  test    byte ptr [rdi+8], 4
0x1800217b6  jz      short loc_1800217C2
0x1800217b8  movzx   eax, word ptr [rdi+220h]
0x1800217bf  add     r8d, eax; FreshnessCounter
0x1800217c2  mov     eax, [rdi+10h]
0x1800217c5  test    eax, eax
0x1800217c7  jnz     short loc_180021819
0x1800217c9  cmp     dword ptr [rdi+8], 1
0x1800217cd  jz      short loc_180021831
0x1800217cf  cmp     dword ptr [rcx], 6
0x1800217d2  jb      short loc_1800217DD
0x1800217d4  cmp     dword ptr [rdx+2B8h], 2
0x1800217db  jz      short loc_180021831
0x1800217dd  mov     dword ptr [rsp+78h+var_38], 0FFFFFFFFh
0x1800217e5  lea     rax, [rsp+78h+var_38]
0x1800217ea  mov     rcx, [rdx+8]
0x1800217ee  lea     r9, [rdi+14h]; LookupName
0x1800217f2  mov     rdx, [rdx+228h]; CardIdentifier
0x1800217f9  mov     ebp, 1
0x1800217fe  mov     [rsp+78h+DataLen], rax; DataLen
0x180021803  lea     rax, [rsp+78h+var_38+8]
0x180021808  mov     [rsp+78h+Data], rax; Data
0x18002180d  mov     rcx, [rcx+60h]; hContext
0x180021811  call    cs:__imp_SCardReadCacheW
0x180021817  jmp     short loc_18002185E
0x180021819  cmp     eax, 1
0x18002181c  jz      short loc_180021828
0x18002181e  mov     ebx, 54Fh
0x180021823  jmp     loc_180021914
0x180021828  mov     rcx, [rdx+2A8h]
0x18002182f  jmp     short loc_180021838
0x180021831  mov     rcx, [rdx+2A0h]; lpCriticalSection
0x180021838  mov     rdx, [rdx+228h]
0x18002183f  lea     rax, [rsp+78h+var_38]
0x180021844  mov     [rsp+78h+var_40], rax; __int64
0x180021849  lea     r9, [rdi+14h]
0x18002184d  lea     rax, [rsp+78h+var_38+8]
0x180021852  xor     ebp, ebp
0x180021854  mov     [rsp+78h+var_48], rax; __int64
0x180021859  call    ScCacheRead
0x18002185e  mov     ebx, eax
0x180021860  test    eax, eax
0x180021862  jz      short loc_180021880
0x180021864  cmp     eax, 80100070h
0x180021869  jz      short loc_180021876
0x18002186b  cmp     eax, 80100071h
0x180021870  jnz     loc_180021914
0x180021876  mov     ebx, 490h
0x18002187b  jmp     loc_180021914
0x180021880  mov     eax, dword ptr [rsp+78h+var_38]
0x180021884  mov     ecx, eax; size
0x180021886  mov     [rsi], eax
0x180021888  call    MIDL_user_allocate
0x18002188d  mov     [rsi+8], rax
0x180021891  test    rax, rax
0x180021894  jnz     short loc_1800218DE
0x180021896  lea     edx, [rax+2]
0x180021899  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002189e  mov     ebx, 8
0x1800218a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800218aa  lea     rax, WPP_GLOBAL_Control
0x1800218b1  cmp     rcx, rax
0x1800218b4  jz      short loc_1800218EE
0x1800218b6  test    byte ptr [rcx+1Ch], 1
0x1800218ba  jz      short loc_1800218EE
0x1800218bc  cmp     byte ptr [rcx+19h], 2
0x1800218c0  jb      short loc_1800218EE
0x1800218c2  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800218c9  lea     edx, [rbx+4]
0x1800218cc  mov     rcx, [rcx+10h]
0x1800218d0  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x1800218d7  call    WPP_SF_s
0x1800218dc  jmp     short loc_1800218EE
0x1800218de  mov     r8d, [rsi]; Size
0x1800218e1  mov     rcx, rax; void *
0x1800218e4  mov     rdx, qword ptr [rsp+78h+var_38+8]; Src
0x1800218e9  call    memcpy_0
0x1800218ee  test    ebp, ebp
0x1800218f0  jz      short loc_18002190A
0x1800218f2  mov     rax, [rdi]
0x1800218f5  mov     rdx, qword ptr [rsp+78h+var_38+8]; pvMem
0x1800218fa  mov     rcx, [rax+8]
0x1800218fe  mov     rcx, [rcx+60h]; hContext
0x180021902  call    cs:__imp_SCardFreeMemory
0x180021908  jmp     short loc_180021914
0x18002190a  mov     rcx, qword ptr [rsp+78h+var_38+8]
0x18002190f  call    CspFreeH
0x180021914  mov     eax, ebx
0x180021916  add     rsp, 58h
0x18002191a  pop     rdi
0x18002191b  pop     rsi
0x18002191c  pop     rbp
0x18002191d  pop     rbx
0x18002191e  retn
```
