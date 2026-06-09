# TlmiLogHydrationPerformance

- ea: `0x180019384`
- end: `0x1800196dc`
- name: `TlmiLogHydrationPerformance`
- size: `856`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180011e18`
- `0x180017728`

## callees

- `0x180001a80`
- `0x180019384`
- `0x18001b864`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800193de`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800193de`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x1800193f0`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x1800193f0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001941a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180019454`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001941a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180019454`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x180019402`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x180019402`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x180019441`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x180019441`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180019461`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180019461`

## pseudocode

```c
ULONG __fastcall TlmiLogHydrationPerformance(
        int a1,
        const WCHAR *a2,
        const WCHAR *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7,
        unsigned int a8)
{
  int v8; // r14d
  ULONG result; // eax
  __int64 v14; // r15
  __int64 v15; // r12
  __int64 v16; // r8
  __int64 v17; // rax
  int v18; // edx
  __int64 v19; // rcx
  __int64 v20; // rcx
  unsigned __int8 NewElement[4]; // [rsp+30h] [rbp-D0h] BYREF
  int v22; // [rsp+34h] [rbp-CCh] BYREF
  __int64 Buffer; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v24; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v25; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v26; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v27; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v29; // [rsp+68h] [rbp-98h] BYREF
  __int64 v30; // [rsp+70h] [rbp-90h] BYREF
  __int64 v31; // [rsp+78h] [rbp-88h] BYREF
  __int64 v32; // [rsp+80h] [rbp-80h] BYREF
  __int64 v33; // [rsp+88h] [rbp-78h] BYREF
  __int64 v34; // [rsp+90h] [rbp-70h] BYREF
  __int64 v35; // [rsp+98h] [rbp-68h] BYREF
  __int64 v36; // [rsp+A0h] [rbp-60h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v37; // [rsp+B0h] [rbp-50h] BYREF
  __int64 *v38; // [rsp+D0h] [rbp-30h]
  __int64 v39; // [rsp+D8h] [rbp-28h]
  __int64 *v40; // [rsp+E0h] [rbp-20h]
  __int64 v41; // [rsp+E8h] [rbp-18h]
  __int64 *v42; // [rsp+F0h] [rbp-10h]
  __int64 v43; // [rsp+F8h] [rbp-8h]
  __int64 *v44; // [rsp+100h] [rbp+0h]
  __int64 v45; // [rsp+108h] [rbp+8h]
  __int64 *v46; // [rsp+110h] [rbp+10h]
  __int64 v47; // [rsp+118h] [rbp+18h]
  __int64 *v48; // [rsp+120h] [rbp+20h]
  __int64 v49; // [rsp+128h] [rbp+28h]
  __int64 *v50; // [rsp+130h] [rbp+30h]
  __int64 v51; // [rsp+138h] [rbp+38h]
  __int64 *v52; // [rsp+140h] [rbp+40h]
  __int64 v53; // [rsp+148h] [rbp+48h]
  __int64 *v54; // [rsp+150h] [rbp+50h]
  __int64 v55; // [rsp+158h] [rbp+58h]
  const WCHAR *v56; // [rsp+160h] [rbp+60h]
  int v57; // [rsp+168h] [rbp+68h]
  int v58; // [rsp+16Ch] [rbp+6Ch]
  const WCHAR *v59; // [rsp+170h] [rbp+70h]
  int v60; // [rsp+178h] [rbp+78h]
  int v61; // [rsp+17Ch] [rbp+7Ch]
  __int64 *v62; // [rsp+180h] [rbp+80h]
  __int64 v63; // [rsp+188h] [rbp+88h]
  __int64 *v64; // [rsp+190h] [rbp+90h]
  __int64 v65; // [rsp+198h] [rbp+98h]
  __int64 *v66; // [rsp+1A0h] [rbp+A0h]
  __int64 v67; // [rsp+1A8h] [rbp+A8h]
  int *v68; // [rsp+1B0h] [rbp+B0h]
  __int64 v69; // [rsp+1B8h] [rbp+B8h]
  __int64 *v70; // [rsp+1C0h] [rbp+C0h]
  __int64 v71; // [rsp+1C8h] [rbp+C8h]

  v8 = 0;
  Buffer = a4;
  if ( a7 != -2147023899 )
    v8 = a7;
  RtlAcquireSRWLockExclusive(&qword_180028A60);
  if ( !RtlLookupElementGenericTableAvl(qword_180028A68, &Buffer) )
  {
    if ( RtlNumberGenericTableElementsAvl(qword_180028A68) > 0x32 )
    {
      ++dword_180028B40;
      return RtlReleaseSRWLockExclusive(&qword_180028A60);
    }
    NewElement[0] = 0;
    RtlInsertElementGenericTableAvl(qword_180028A68, &Buffer, 8u, NewElement);
  }
  v14 = 0;
  v15 = 0;
  RtlReleaseSRWLockExclusive(&qword_180028A60);
  SetEvent(hEvent);
  if ( a1 )
  {
    v16 = a5;
  }
  else
  {
    v16 = 0;
    if ( v8 < 0 )
      v15 = a5;
    else
      v14 = a5;
  }
  result = dword_1800281A0;
  if ( (unsigned int)dword_1800281A0 > 5 )
  {
    result = qword_1800281B0;
    if ( (qword_1800281B0 & 0x400000000000LL) != 0 )
    {
      result = 0;
      if ( (qword_1800281B8 & 0x400000000000LL) == qword_1800281B8 )
      {
        v24 = 1;
        v38 = &v24;
        v25 = a6;
        v26 = a6;
        v42 = &v26;
        v44 = &v27;
        v46 = &v28;
        v48 = &v29;
        v50 = &v30;
        v31 = v8;
        v52 = &v31;
        v32 = a8;
        v54 = &v32;
        v17 = -1;
        v40 = &v25;
        v18 = 2;
        v39 = 8;
        v41 = 8;
        v43 = 8;
        v27 = v16;
        v45 = 8;
        v28 = v14;
        v47 = 8;
        v29 = v15;
        v49 = 8;
        v30 = a5;
        v51 = 8;
        v53 = 8;
        v55 = 8;
        if ( a2 )
        {
          v19 = -1;
          do
            ++v19;
          while ( a2[v19] );
          v20 = (unsigned int)(2 * v19 + 2);
        }
        else
        {
          a2 = &SourceString;
          v20 = 2;
        }
        v56 = a2;
        v57 = v20;
        v58 = 0;
        if ( a3 )
        {
          do
            ++v17;
          while ( a3[v17] );
          v18 = 2 * v17 + 2;
        }
        else
        {
          a3 = &SourceString;
        }
        v60 = v18;
        v62 = &v33;
        v34 = (unsigned int)dword_180028B78;
        v64 = &v34;
        v35 = qword_180028B70;
        v66 = &v35;
        v22 = dword_180028B7C;
        v68 = &v22;
        v70 = &v36;
        v61 = 0;
        v59 = a3;
        v33 = a4;
        v63 = 8;
        v65 = 8;
        v67 = 8;
        v69 = 4;
        v36 = 0x1000000;
        v71 = 8;
        return tlgWriteAgg(v20, (unsigned __int8 *)byte_180021E11, v16, 0x12u, &v37);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180019384  push    rbp
0x180019386  push    rbx
0x180019387  push    rsi
0x180019388  push    rdi
0x180019389  push    r12
0x18001938b  push    r13
0x18001938d  push    r14
0x18001938f  push    r15
0x180019391  lea     rbp, [rsp-0E8h]
0x180019399  sub     rsp, 1E8h
0x1800193a0  mov     rax, cs:__security_cookie
0x1800193a7  xor     rax, rsp
0x1800193aa  mov     [rbp+120h+var_50], rax
0x1800193b1  xor     r14d, r14d
0x1800193b4  mov     rbx, r9
0x1800193b7  cmp     [rbp+120h+arg_30], 800703E5h
0x1800193c1  mov     r13d, ecx
0x1800193c4  lea     rcx, qword_180028A60
0x1800193cb  mov     [rsp+220h+Buffer], rbx
0x1800193d0  cmovnz  r14d, [rbp+120h+arg_30]
0x1800193d8  mov     rdi, r8
0x1800193db  mov     rsi, rdx
0x1800193de  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800193e4  mov     rcx, cs:qword_180028A68; Table
0x1800193eb  lea     rdx, [rsp+220h+Buffer]; Buffer
0x1800193f0  call    cs:__imp_RtlLookupElementGenericTableAvl
0x1800193f6  test    rax, rax
0x1800193f9  jnz     short loc_180019447
0x1800193fb  mov     rcx, cs:qword_180028A68; Table
0x180019402  call    cs:__imp_RtlNumberGenericTableElementsAvl
0x180019408  cmp     eax, 32h ; '2'
0x18001940b  jbe     short loc_180019425
0x18001940d  inc     cs:dword_180028B40
0x180019413  lea     rcx, qword_180028A60
0x18001941a  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180019420  jmp     loc_1800196B9
0x180019425  mov     rcx, cs:qword_180028A68; Table
0x18001942c  lea     r9, [rsp+220h+NewElement]; NewElement
0x180019431  mov     r8d, 8; BufferSize
0x180019437  mov     [rsp+220h+NewElement], 0
0x18001943c  lea     rdx, [rsp+220h+Buffer]; Buffer
0x180019441  call    cs:__imp_RtlInsertElementGenericTableAvl
0x180019447  lea     rcx, qword_180028A60
0x18001944e  xor     r15d, r15d
0x180019451  xor     r12d, r12d
0x180019454  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001945a  mov     rcx, cs:hEvent; hEvent
0x180019461  call    cs:__imp_SetEvent
0x180019467  mov     rcx, [rbp+120h+arg_20]
0x18001946e  xor     r9d, r9d
0x180019471  test    r13d, r13d
0x180019474  jz      short loc_18001947B
0x180019476  mov     r8, rcx
0x180019479  jmp     short loc_18001948B
0x18001947b  mov     r8, r9
0x18001947e  test    r14d, r14d
0x180019481  js      short loc_180019488
0x180019483  mov     r15, rcx
0x180019486  jmp     short loc_18001948B
0x180019488  mov     r12, rcx
0x18001948b  mov     eax, cs:dword_1800281A0
0x180019491  cmp     eax, 5
0x180019494  jbe     loc_1800196B9
0x18001949a  mov     rdx, cs:qword_1800281B8
0x1800194a1  mov     r10, 400000000000h
0x1800194ab  mov     rax, cs:qword_1800281B0
0x1800194b2  test    r10, rax
0x1800194b5  jz      loc_1800196B9
0x1800194bb  mov     rax, rdx
0x1800194be  and     rax, r10
0x1800194c1  cmp     rax, rdx
0x1800194c4  jnz     loc_1800196B9
0x1800194ca  lea     rax, [rsp+220h+var_1E0]
0x1800194cf  mov     [rsp+220h+var_1E0], 1
0x1800194d8  mov     [rbp+120h+var_150], rax
0x1800194dc  lea     rdx, [rsp+220h+var_1D8]
0x1800194e1  mov     rax, [rbp+120h+arg_28]
0x1800194e8  mov     [rsp+220h+var_1D8], rax
0x1800194ed  mov     [rsp+220h+var_1D0], rax
0x1800194f2  lea     rax, [rsp+220h+var_1D0]
0x1800194f7  mov     [rbp+120h+var_130], rax
0x1800194fb  lea     rax, [rsp+220h+var_1C8]
0x180019500  mov     [rbp+120h+var_120], rax
0x180019504  lea     rax, [rsp+220h+var_1C0]
0x180019509  mov     [rbp+120h+var_110], rax
0x18001950d  lea     rax, [rsp+220h+var_1B8]
0x180019512  mov     [rbp+120h+var_100], rax
0x180019516  lea     rax, [rsp+220h+var_1B0]
0x18001951b  mov     [rbp+120h+var_F0], rax
0x18001951f  movsxd  rax, r14d
0x180019522  mov     [rsp+220h+var_1A8], rax
0x180019527  lea     rax, [rsp+220h+var_1A8]
0x18001952c  mov     [rbp+120h+var_E0], rax
0x180019530  mov     eax, [rbp+120h+arg_38]
0x180019536  mov     [rbp+120h+var_1A0], rax
0x18001953a  lea     rax, [rbp+120h+var_1A0]
0x18001953e  mov     [rbp+120h+var_D0], rax
0x180019542  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019546  mov     [rbp+120h+var_140], rdx
0x18001954a  mov     edx, 2
0x18001954f  mov     [rbp+120h+var_148], 8
0x180019557  mov     [rbp+120h+var_138], 8
0x18001955f  mov     [rbp+120h+var_128], 8
0x180019567  mov     [rsp+220h+var_1C8], r8
0x18001956c  mov     [rbp+120h+var_118], 8
0x180019574  mov     [rsp+220h+var_1C0], r15
0x180019579  mov     [rbp+120h+var_108], 8
0x180019581  mov     [rsp+220h+var_1B8], r12
0x180019586  mov     [rbp+120h+var_F8], 8
0x18001958e  mov     [rsp+220h+var_1B0], rcx
0x180019593  mov     [rbp+120h+var_E8], 8
0x18001959b  mov     [rbp+120h+var_D8], 8
0x1800195a3  mov     [rbp+120h+var_C8], 8
0x1800195ab  test    rsi, rsi
0x1800195ae  jz      short loc_1800195C6
0x1800195b0  mov     rcx, rax
0x1800195b3  inc     rcx
0x1800195b6  cmp     [rsi+rcx*2], r9w
0x1800195bb  jnz     short loc_1800195B3
0x1800195bd  lea     ecx, ds:2[rcx*2]
0x1800195c4  jmp     short loc_1800195CF
0x1800195c6  lea     rsi, SourceString
0x1800195cd  mov     ecx, edx
0x1800195cf  mov     [rbp+120h+var_C0], rsi
0x1800195d3  mov     [rbp+120h+var_B8], ecx
0x1800195d6  mov     [rbp+120h+var_B4], r9d
0x1800195da  test    rdi, rdi
0x1800195dd  jz      short loc_1800195F2
0x1800195df  inc     rax
0x1800195e2  cmp     [rdi+rax*2], r9w
0x1800195e7  jnz     short loc_1800195DF
0x1800195e9  lea     edx, ds:2[rax*2]
0x1800195f0  jmp     short loc_1800195F9
0x1800195f2  lea     rdi, SourceString
0x1800195f9  lea     rax, [rbp+120h+var_198]
0x1800195fd  mov     [rbp+120h+var_A8], edx
0x180019600  mov     [rbp+120h+var_A0], rax
0x180019607  lea     rdx, byte_180021E11
0x18001960e  mov     eax, cs:dword_180028B78
0x180019614  mov     [rbp+120h+var_190], rax
0x180019618  lea     rax, [rbp+120h+var_190]
0x18001961c  mov     [rbp+120h+var_90], rax
0x180019623  mov     rax, cs:qword_180028B70
0x18001962a  mov     [rbp+120h+var_188], rax
0x18001962e  lea     rax, [rbp+120h+var_188]
0x180019632  mov     [rbp+120h+var_80], rax
0x180019639  mov     eax, cs:dword_180028B7C
0x18001963f  mov     [rsp+220h+var_1EC], eax
0x180019643  lea     rax, [rsp+220h+var_1EC]
0x180019648  mov     [rbp+120h+var_70], rax
0x18001964f  lea     rax, [rbp+120h+var_180]
0x180019653  mov     [rbp+120h+var_60], rax
0x18001965a  lea     rax, [rbp+120h+var_170]
0x18001965e  mov     [rbp+120h+var_A4], r9d
0x180019662  mov     r9d, 12h
0x180019668  mov     [rsp+220h+var_200], rax
0x18001966d  mov     [rbp+120h+var_B0], rdi
0x180019671  mov     [rbp+120h+var_198], rbx
0x180019675  mov     [rbp+120h+var_98], 8
0x180019680  mov     [rbp+120h+var_88], 8
0x18001968b  mov     [rbp+120h+var_78], 8
0x180019696  mov     [rbp+120h+var_68], 4
0x1800196a1  mov     [rbp+120h+var_180], 1000000h
0x1800196a9  mov     [rbp+120h+var_58], 8
0x1800196b4  call    _tlgWriteAgg
0x1800196b9  mov     rcx, [rbp+120h+var_50]
0x1800196c0  xor     rcx, rsp; StackCookie
0x1800196c3  call    __security_check_cookie
0x1800196c8  add     rsp, 1E8h
0x1800196cf  pop     r15
0x1800196d1  pop     r14
0x1800196d3  pop     r13
0x1800196d5  pop     r12
0x1800196d7  pop     rdi
0x1800196d8  pop     rsi
0x1800196d9  pop     rbx
0x1800196da  pop     rbp
0x1800196db  retn
```
