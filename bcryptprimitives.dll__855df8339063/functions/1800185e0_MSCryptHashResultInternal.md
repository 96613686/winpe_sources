# MSCryptHashResultInternal

- ea: `0x1800185e0`
- end: `0x180018a8c`
- name: `MSCryptHashResultInternal`
- size: `1196`
- prototype: ``
- caller_count: `2`
- callee_count: `31`
- tags: `broker_com_uri`

## callers

- `0x180013b70`
- `0x180017240`

## callees

- `0x180001630`
- `0x180001830`
- `0x180001a30`
- `0x180001b30`
- `0x18000ecb0`
- `0x18000ee60`
- `0x180014340`
- `0x180014750`
- `0x1800152e0`
- `0x180015640`
- `0x180016ad0`
- `0x180016d30`
- `0x180016d60`
- `0x180017590`
- `0x180018590`
- `0x1800185e0`
- `0x180018e70`
- `0x180018f60`
- `0x180032130`
- `0x180032430`
- `0x1800324d0`
- `0x1800326b0`
- `0x1800412d0`
- `0x1800454f0`
- `0x1800496c0`
- `0x1800706ec`
- `0x18007080c`
- `0x180070b28`
- `0x180070ee0`
- `0x180078008`
- `0x180078090`

## string_xrefs

- `0x1800186af`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x1800812c4`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`

## pseudocode

```c
__int64 __fastcall MSCryptHashResultInternal(__int64 a1, __int64 a2, unsigned int a3, __int64 a4)
{
  __int64 v4; // r15
  unsigned int v7; // esi
  int v8; // ebx
  bool v9; // r14
  __int64 v11; // r9
  __int64 v12; // rcx
  __int64 v13; // rcx

  v4 = a3;
  v7 = 0;
  v8 = 1;
  v9 = (a4 & 1) == 0;
  switch ( *(_DWORD *)(a1 + 8) )
  {
    case 0x20001:
      if ( *(_DWORD *)(a1 + 12) == 16 )
      {
        SymCryptMd5Result(a1 + 128);
      }
      else
      {
        v7 = -1073741816;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            a2,
            (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
            (unsigned int)"Status",
            8,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
            95);
      }
      return v7;
    case 0x20002:
      if ( *(_DWORD *)(a1 + 12) != 20 )
      {
        v11 = 2416;
        goto LABEL_70;
      }
      SymCryptSha1Result(a1 + 128);
      return v7;
    case 0x20003:
      if ( *(_DWORD *)(a1 + 12) != 16 )
      {
        v11 = 2433;
        goto LABEL_70;
      }
      SymCryptMd2Result(a1 + 128);
      return v7;
    case 0x20004:
      if ( *(_DWORD *)(a1 + 12) != 16 )
      {
        v11 = 2450;
        goto LABEL_70;
      }
      SymCryptMd4Result(a1 + 128);
      return v7;
    case 0x20005:
      if ( *(_DWORD *)(a1 + 12) != 32 )
      {
        v11 = 2467;
        goto LABEL_70;
      }
      SymCryptSha256Result(a1 + 128);
      return v7;
    case 0x20006:
      if ( *(_DWORD *)(a1 + 12) != 48 )
      {
        v11 = 2484;
        goto LABEL_70;
      }
      SymCryptSha384Result(a1 + 128);
      return v7;
    case 0x20007:
      if ( *(_DWORD *)(a1 + 12) == 64 )
      {
        SymCryptSha512Result(a1 + 128, a2);
      }
      else
      {
        v7 = -1073741816;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            a2,
            (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
            (unsigned int)"Status",
            8,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
            197);
      }
      return v7;
    case 0x20008:
      if ( !*(_DWORD *)(a1 + 116) )
      {
        v7 = -1073740758;
        v11 = 2518;
        v12 = 3221226538LL;
        goto LABEL_71;
      }
      if ( *(_DWORD *)(a1 + 12) != 16 )
      {
        v11 = 2525;
        goto LABEL_70;
      }
      SymCryptGcmEncryptFinal(a1 + 2736, a2, 16);
      *(_DWORD *)(a1 + 116) = 0;
      return v7;
    case 0x20009:
      if ( *(_DWORD *)(a1 + 12) != 20 )
      {
        v11 = 2548;
        goto LABEL_70;
      }
      SymCryptHmacSha1Result(a1 + 208);
      SymCryptHmacSha1Init(a1 + 208, a1 + 128);
      return v7;
    case 0x2000A:
      if ( *(_DWORD *)(a1 + 12) != 16 )
      {
        v11 = 2566;
        goto LABEL_70;
      }
      SymCryptHmacMd5Result(a1 + 176);
      SymCryptHmacMd5Init(a1 + 176, a1 + 128);
      return v7;
    case 0x2000B:
      if ( *(_DWORD *)(a1 + 12) != 32 )
      {
        v11 = 2584;
        goto LABEL_70;
      }
      SymCryptHmacSha256Result(a1 + 208);
      SymCryptHmacSha256Init(a1 + 208, a1 + 128);
      return v7;
    case 0x2000C:
      if ( *(_DWORD *)(a1 + 12) == 48 )
      {
        SymCryptHmacSha384Result(a1 + 272);
        SymCryptHmacSha512Init(a1 + 272, a1 + 128);
      }
      else
      {
        v7 = -1073741816;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            a2,
            (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
            (unsigned int)"Status",
            8,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
            42);
      }
      return v7;
    case 0x2000D:
      if ( *(_DWORD *)(a1 + 12) != 64 )
      {
        v11 = 2620;
        goto LABEL_70;
      }
      SymCryptHmacSha512Result(a1 + 272);
      SymCryptHmacSha512Init(a1 + 272, a1 + 128);
      return v7;
    case 0x2000E:
      if ( *(_DWORD *)(a1 + 12) != 16 )
      {
        v11 = 2638;
        goto LABEL_70;
      }
      SymCryptAesCmacResult(a1 + 672);
      *(_QWORD *)(a1 + 704) = 0;
      *(_QWORD *)(a1 + 672) = 0;
      *(_QWORD *)(a1 + 680) = 0;
      *(_QWORD *)(a1 + 712) = a1 + 128;
      return v7;
    case 0x2000F:
      if ( *(_DWORD *)(a1 + 12) != 32 )
      {
        v11 = 2656;
        goto LABEL_70;
      }
      SymCryptShake128Result(a1 + 128, a2);
      return v7;
    case 0x20010:
      if ( *(_DWORD *)(a1 + 12) != 48 )
      {
        v11 = 2673;
        goto LABEL_70;
      }
      SymCryptSha3_384Result(a1 + 128);
      return v7;
    case 0x20011:
      if ( *(_DWORD *)(a1 + 12) != 64 )
      {
        v11 = 2690;
        goto LABEL_70;
      }
      SymCryptSha3_512Result(a1 + 128, a2);
      return v7;
    case 0x20012:
      if ( *(_DWORD *)(a1 + 12) == 32 )
        goto LABEL_81;
      v11 = 2707;
      goto LABEL_70;
    case 0x20013:
      if ( *(_DWORD *)(a1 + 12) == 48 )
        goto LABEL_81;
      v11 = 2725;
      goto LABEL_70;
    case 0x20014:
      if ( *(_DWORD *)(a1 + 12) == 64 )
      {
LABEL_81:
        SymCryptHmacResult(a1 + 640);
        SymCryptHmacInit(a1 + 640, a1 + 128);
      }
      else
      {
        v11 = 2743;
LABEL_70:
        v7 = -1073741816;
        v12 = 3221225480LL;
LABEL_71:
        DebugTraceError(v12, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c", v11);
      }
      return v7;
    case 0x20015:
      if ( *(_DWORD *)(a1 + 280) <= 1u )
        goto LABEL_83;
      goto LABEL_84;
    case 0x20016:
      if ( *(_DWORD *)(a1 + 280) > 1u )
        goto LABEL_84;
LABEL_83:
      MSCryptHashDataInternal(a1, 0);
LABEL_84:
      LOBYTE(a4) = v9;
      SymCryptCShake256Extract(a1 + 528, a2, v4, a4);
      *(_DWORD *)(a1 + 280) = 2 * !v9 + 1;
      return v7;
    case 0x20017:
      if ( *(_DWORD *)(a1 + 528) <= 1u )
        MSCryptHashDataInternal(a1, 0);
      v13 = a1 + 544;
      if ( v9 )
      {
        SymCryptKmac128ResultEx(v13, a2, v4);
        goto LABEL_90;
      }
      SymCryptKmac256Extract(v13, a2, v4);
      goto LABEL_89;
    case 0x20018:
      if ( *(_DWORD *)(a1 + 528) <= 1u )
        MSCryptHashDataInternal(a1, 0);
      if ( v9 )
      {
        ((void (*)(void))SymCryptKmac128ResultEx)();
      }
      else
      {
        SymCryptKmac256Extract(a1 + 544, a2, v4);
LABEL_89:
        v8 = 3;
      }
LABEL_90:
      *(_DWORD *)(a1 + 528) = v8;
      return v7;
    case 0x20019:
    case 0x2001A:
      LOBYTE(a4) = (a4 & 1) == 0;
      SymCryptShake256Extract(a1 + 128, a2, a3, a4);
      return v7;
    default:
      v7 = -1073741637;
      v11 = 2886;
      v12 = 3221225659LL;
      goto LABEL_71;
  }
}

```

## disassembly

```asm
0x1800185e0  push    rbx
0x1800185e2  push    rbp
0x1800185e3  push    rsi
0x1800185e4  push    rdi
0x1800185e5  push    r14
0x1800185e7  push    r15
0x1800185e9  sub     rsp, 48h
0x1800185ed  mov     eax, [rcx+8]
0x1800185f0  mov     r14d, r9d
0x1800185f3  add     eax, 0FFFDFFFFh; switch 26 cases
0x1800185f8  mov     r15d, r8d
0x1800185fb  mov     rbp, rdx
0x1800185fe  mov     rdi, rcx
0x180018601  cmp     eax, 19h
0x180018604  ja      def_180018626; jumptable 0000000180018626 default case
0x18001860a  xor     esi, esi
0x18001860c  lea     rcx, cs:180000000h
0x180018613  mov     eax, ds:(jpt_180018626 - 180000000h)[rcx+rax*4]
0x18001861a  not     r14b
0x18001861d  lea     ebx, [rsi+1]
0x180018620  and     r14b, bl
0x180018623  add     rax, rcx
0x180018626  jmp     rax; switch jump
0x18001862c  cmp     dword ptr [rdi+0Ch], 20h ; ' '; jumptable 0000000180018626 case 131077
0x180018630  jnz     loc_18001884F
0x180018636  lea     rcx, [rdi+80h]
0x18001863d  call    SymCryptSha256Result
0x180018642  mov     eax, esi
0x180018644  add     rsp, 48h
0x180018648  pop     r15
0x18001864a  pop     r14
0x18001864c  pop     rdi
0x18001864d  pop     rsi
0x18001864e  pop     rbp
0x18001864f  pop     rbx
0x180018650  retn
0x180018652  cmp     dword ptr [rdi+0Ch], 40h ; '@'; jumptable 0000000180018626 case 131085
0x180018656  jnz     loc_1800188D8
0x18001865c  lea     rbx, [rdi+110h]
0x180018663  mov     rcx, rbx
0x180018666  call    SymCryptHmacSha512Result
0x18001866b  lea     rdx, [rdi+80h]
0x180018672  mov     rcx, rbx
0x180018675  call    SymCryptHmacSha512Init
0x18001867a  jmp     short loc_180018642
0x18001867c  cmp     dword ptr [rdi+0Ch], 40h ; '@'; jumptable 0000000180018626 case 131079
0x180018680  jz      loc_180018865
0x180018686  mov     esi, 0C0000008h
0x18001868b  mov     rcx, cs:WPP_GLOBAL_Control
0x180018692  lea     rax, WPP_GLOBAL_Control
0x180018699  cmp     rcx, rax
0x18001869c  jz      short loc_180018642
0x18001869e  test    [rcx+1Ch], bl
0x1800186a1  jz      short loc_180018642
0x1800186a3  mov     [rsp+78h+var_48], 9C5h
0x1800186ab  mov     rcx, [rcx+10h]
0x1800186af  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800186b6  mov     [rsp+78h+var_50], r8
0x1800186bb  lea     r9, aStatus; "Status"
0x1800186c2  mov     [rsp+78h+var_58], 0C0000008h
0x1800186ca  call    WPP_SF_sDsd
0x1800186cf  jmp     loc_180018642
0x1800186d4  cmp     dword ptr [rdi+0Ch], 14h; jumptable 0000000180018626 case 131081
0x1800186d8  jnz     loc_180018894
0x1800186de  lea     rbx, [rdi+0D0h]
0x1800186e5  mov     rcx, rbx
0x1800186e8  call    SymCryptHmacSha1Result
0x1800186ed  lea     rdx, [rdi+80h]
0x1800186f4  mov     rcx, rbx
0x1800186f7  call    SymCryptHmacSha1Init
0x1800186fc  jmp     loc_180018642
0x180018701  cmp     dword ptr [rdi+0Ch], 10h; jumptable 0000000180018626 case 131082
0x180018705  jnz     loc_18001889F
0x18001870b  lea     rbx, [rdi+0B0h]
0x180018712  mov     rcx, rbx
0x180018715  call    SymCryptHmacMd5Result
0x18001871a  lea     rdx, [rdi+80h]
0x180018721  mov     rcx, rbx
0x180018724  call    SymCryptHmacMd5Init
0x180018729  jmp     loc_180018642
0x18001872e  cmp     dword ptr [rdi+0Ch], 10h; jumptable 0000000180018626 case 131073
0x180018732  jz      loc_180018809
0x180018738  mov     esi, 0C0000008h
0x18001873d  mov     rcx, cs:WPP_GLOBAL_Control
0x180018744  lea     rax, WPP_GLOBAL_Control
0x18001874b  cmp     rcx, rax
0x18001874e  jz      loc_180018642
0x180018754  test    [rcx+1Ch], bl
0x180018757  jz      loc_180018642
0x18001875d  mov     [rsp+78h+var_48], 95Fh
0x180018765  jmp     loc_1800186AB
0x18001876a  cmp     dword ptr [rdi+0Ch], 14h; jumptable 0000000180018626 case 131074
0x18001876e  jnz     loc_18001881A
0x180018774  lea     rcx, [rdi+80h]
0x18001877b  call    SymCryptSha1Result
0x180018780  jmp     loc_180018642
0x180018785  cmp     dword ptr [rdi+0Ch], 30h ; '0'; jumptable 0000000180018626 case 131078
0x180018789  jnz     loc_18001885A
0x18001878f  lea     rcx, [rdi+80h]
0x180018796  call    SymCryptSha384Result
0x18001879b  jmp     loc_180018642
0x1800187a0  cmp     dword ptr [rdi+0Ch], 30h ; '0'; jumptable 0000000180018626 case 131084
0x1800187a4  jz      loc_1800188B5
0x1800187aa  mov     esi, 0C0000008h
0x1800187af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800187b6  lea     rax, WPP_GLOBAL_Control
0x1800187bd  cmp     rcx, rax
0x1800187c0  jz      loc_180018642
0x1800187c6  test    [rcx+1Ch], bl
0x1800187c9  jz      loc_180018642
0x1800187cf  mov     [rsp+78h+var_48], 0A2Ah
0x1800187d7  jmp     loc_1800186AB
0x1800187dc  cmp     dword ptr [rdi+0Ch], 20h ; ' '; jumptable 0000000180018626 case 131083
0x1800187e0  jnz     loc_1800188AA
0x1800187e6  lea     rbx, [rdi+0D0h]
0x1800187ed  mov     rcx, rbx
0x1800187f0  call    SymCryptHmacSha256Result
0x1800187f5  lea     rdx, [rdi+80h]
0x1800187fc  mov     rcx, rbx
0x1800187ff  call    SymCryptHmacSha256Init
0x180018804  jmp     loc_180018642
0x180018809  lea     rcx, [rdi+80h]
0x180018810  call    SymCryptMd5Result
0x180018815  jmp     loc_180018642
0x18001881a  mov     r9d, 970h
0x180018820  jmp     loc_1800812BA
0x180018825  cmp     dword ptr [rdi+0Ch], 10h; jumptable 0000000180018626 case 131075
0x180018829  jz      loc_1800812DD
0x18001882f  mov     r9d, 981h
0x180018835  jmp     loc_1800812BA
0x18001883a  cmp     dword ptr [rdi+0Ch], 10h; jumptable 0000000180018626 case 131076
0x18001883e  jz      loc_1800812EF
0x180018844  mov     r9d, 992h
0x18001884a  jmp     loc_1800812BA
0x18001884f  mov     r9d, 9A3h
0x180018855  jmp     loc_1800812BA
0x18001885a  mov     r9d, 9B4h
0x180018860  jmp     loc_1800812BA
0x180018865  lea     rcx, [rdi+80h]
0x18001886c  call    SymCryptSha512Result
0x180018871  jmp     loc_180018642
0x180018876  cmp     [rdi+74h], esi; jumptable 0000000180018626 case 131080
0x180018879  jnz     loc_180081301
0x18001887f  mov     esi, 0C000042Ah
0x180018884  mov     r9d, 9D6h
0x18001888a  mov     ecx, 0C000042Ah
0x18001888f  jmp     loc_1800812C4
0x180018894  mov     r9d, 9F4h
0x18001889a  jmp     loc_1800812BA
0x18001889f  mov     r9d, 0A06h
0x1800188a5  jmp     loc_1800812BA
0x1800188aa  mov     r9d, 0A18h
0x1800188b0  jmp     loc_1800812BA
0x1800188b5  lea     rbx, [rdi+110h]
0x1800188bc  mov     rcx, rbx
0x1800188bf  call    SymCryptHmacSha384Result
0x1800188c4  lea     rdx, [rdi+80h]
0x1800188cb  mov     rcx, rbx
0x1800188ce  call    SymCryptHmacSha512Init
0x1800188d3  jmp     loc_180018642
0x1800188d8  mov     r9d, 0A3Ch
0x1800188de  jmp     loc_1800812BA
0x1800188e3  cmp     dword ptr [rdi+0Ch], 10h; jumptable 0000000180018626 case 131086
0x1800188e7  jz      loc_180081329
0x1800188ed  mov     r9d, 0A4Eh
0x1800188f3  jmp     loc_1800812BA
0x1800188f8  cmp     dword ptr [rdi+0Ch], 20h ; ' '; jumptable 0000000180018626 case 131087
0x1800188fc  jz      loc_180081353
0x180018902  mov     r9d, 0A60h
0x180018908  jmp     loc_1800812BA
0x18001890d  cmp     dword ptr [rdi+0Ch], 30h ; '0'; jumptable 0000000180018626 case 131088
0x180018911  jz      loc_180081365
0x180018917  mov     r9d, 0A71h
0x18001891d  jmp     loc_1800812BA
0x180018922  cmp     dword ptr [rdi+0Ch], 40h ; '@'; jumptable 0000000180018626 case 131089
0x180018926  jz      loc_180081377
0x18001892c  mov     r9d, 0A82h
0x180018932  jmp     loc_1800812BA
0x180018937  cmp     dword ptr [rdi+0Ch], 20h ; ' '; jumptable 0000000180018626 case 131090
0x18001893b  jz      loc_180081389
0x180018941  mov     r9d, 0A93h
0x180018947  jmp     loc_1800812BA
0x18001894c  cmp     dword ptr [rdi+0Ch], 30h ; '0'; jumptable 0000000180018626 case 131091
0x180018950  jz      loc_180081389
0x180018956  mov     r9d, 0AA5h
0x18001895c  jmp     loc_1800812BA
0x180018961  cmp     dword ptr [rdi+0Ch], 40h ; '@'; jumptable 0000000180018626 case 131092
0x180018965  jnz     loc_1800812B4
0x18001896b  jmp     loc_180081389
0x180018970  cmp     [rdi+118h], ebx; jumptable 0000000180018626 case 131093
0x180018976  ja      loc_1800813AD
0x18001897c  xor     r8d, r8d
0x18001897f  xor     edx, edx
0x180018981  mov     rcx, rdi
0x180018984  call    MSCryptHashDataInternal
0x180018989  nop
0x18001898a  jmp     loc_1800813AD
0x18001898f  cmp     [rdi+118h], ebx; jumptable 0000000180018626 case 131094
0x180018995  jbe     loc_1800813C4
0x18001899b  jmp     loc_1800813D1
0x1800189a0  cmp     [rdi+210h], ebx; jumptable 0000000180018626 case 131095
0x1800189a6  ja      loc_1800813FE
0x1800189ac  xor     r8d, r8d
0x1800189af  xor     edx, edx
0x1800189b1  mov     rcx, rdi
0x1800189b4  call    MSCryptHashDataInternal
0x1800189b9  nop
0x1800189ba  jmp     loc_1800813FE
0x1800189bf  cmp     [rdi+210h], ebx; jumptable 0000000180018626 case 131096
0x1800189c5  ja      loc_18008143A
0x1800189cb  xor     r8d, r8d
0x1800189ce  xor     edx, edx
0x1800189d0  mov     rcx, rdi
0x1800189d3  call    MSCryptHashDataInternal
0x1800189d8  nop
0x1800189d9  jmp     loc_18008143A
0x1800189de  mov     r8, r15; jumptable 0000000180018626 case 131097
0x1800189e1  lea     rcx, [rdi+80h]
0x1800189e8  mov     r9b, r14b
0x1800189eb  call    SymCryptShake256Extract
0x1800189f0  jmp     loc_180018642
0x1800189f5  mov     r8, r15; jumptable 0000000180018626 case 131098
0x1800189f8  lea     rcx, [rdi+80h]
0x1800189ff  mov     r9b, r14b
0x180018a02  call    SymCryptShake256Extract
0x180018a07  jmp     loc_180018642
0x180018a0c  mov     esi, 0C00000BBh; jumptable 0000000180018626 default case
0x180018a11  mov     r9d, 0B46h
0x180018a17  mov     ecx, 0C00000BBh
0x180018a1c  jmp     loc_1800812C4
0x1800812b4  mov     r9d, 0AB7h
0x1800812ba  mov     esi, 0C0000008h
0x1800812bf  mov     ecx, 0C0000008h
0x1800812c4  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800812cb  lea     rdx, aStatus; "Status"
0x1800812d2  call    DebugTraceError
0x1800812d7  nop
0x1800812d8  jmp     loc_180018642
0x1800812dd  lea     rcx, [rdi+80h]
0x1800812e4  call    SymCryptMd2Result
0x1800812e9  nop
0x1800812ea  jmp     loc_180018642
0x1800812ef  lea     rcx, [rdi+80h]
0x1800812f6  call    SymCryptMd4Result
0x1800812fb  nop
0x1800812fc  jmp     loc_180018642
0x180081301  cmp     dword ptr [rdi+0Ch], 10h
0x180081305  jz      short loc_18008130F
0x180081307  mov     r9d, 9DDh
0x18008130d  jmp     short loc_1800812BA
0x18008130f  lea     rcx, [rdi+0AB0h]
0x180081316  mov     r8d, 10h
0x18008131c  call    SymCryptGcmEncryptFinal
0x180081321  mov     [rdi+74h], esi
0x180081324  jmp     loc_180018642
0x180081329  lea     rbx, [rdi+2A0h]
0x180081330  mov     rcx, rbx
0x180081333  call    SymCryptAesCmacResult
0x180081338  mov     [rbx+20h], rsi
0x18008133c  lea     rax, [rdi+80h]
0x180081343  mov     [rbx], rsi
0x180081346  mov     [rbx+8], rsi
0x18008134a  mov     [rbx+28h], rax
0x18008134e  jmp     loc_180018642
0x180081353  lea     rcx, [rdi+80h]
0x18008135a  call    SymCryptShake128Result
0x18008135f  nop
0x180081360  jmp     loc_180018642
0x180081365  lea     rcx, [rdi+80h]
0x18008136c  call    SymCryptSha3_384Result
0x180081371  nop
0x180081372  jmp     loc_180018642
0x180081377  lea     rcx, [rdi+80h]
0x18008137e  call    SymCryptSha3_512Result
0x180081383  nop
0x180081384  jmp     loc_180018642
0x180081389  lea     rbx, [rdi+280h]
0x180081390  mov     rcx, rbx
0x180081393  call    SymCryptHmacResult
0x180081398  lea     rdx, [rdi+80h]
0x18008139f  mov     rcx, rbx
0x1800813a2  call    SymCryptHmacInit
0x1800813a7  nop
0x1800813a8  jmp     loc_180018642
0x1800813ad  mov     r8, r15
0x1800813b0  lea     rcx, [rdi+210h]
0x1800813b7  mov     r9b, r14b
0x1800813ba  mov     rdx, rbp
0x1800813bd  call    SymCryptCShake256Extract
0x1800813c2  jmp     short loc_1800813E6
0x1800813c4  xor     r8d, r8d
0x1800813c7  xor     edx, edx
0x1800813c9  mov     rcx, rdi
0x1800813cc  call    MSCryptHashDataInternal
0x1800813d1  mov     r8, r15
0x1800813d4  lea     rcx, [rdi+210h]
0x1800813db  mov     r9b, r14b
0x1800813de  mov     rdx, rbp
0x1800813e1  call    SymCryptCShake256Extract
0x1800813e6  movzx   eax, r14b
  ... truncated ...
```
