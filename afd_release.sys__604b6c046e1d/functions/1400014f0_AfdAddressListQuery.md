# AfdAddressListQuery

- ea: `0x1400014f0`
- end: `0x140001a82`
- name: `AfdAddressListQuery`
- size: `1426`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned __int16 *, unsigned int, char *Address, SIZE_T Length, _QWORD *)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x1400014f0`
- `0x140001bb4`
- `0x140001d60`
- `0x140001e74`
- `0x140002150`
- `0x14002fd5c`
- `0x1400726a0`
- `0x1400726d0`
- `0x140092008`
- `0x140092188`
- `0x140092254`
- `0x1400930cc`
- `0x140093104`
- `0x1400931d0`
- `0x140093b2c`
- `0x140094954`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x140001647`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x140001647`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400016ac`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000193a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400019cd`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400016ac`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000193a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400019cd`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000194f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400019e2`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000194f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400019e2`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140001699`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140001699`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140001852`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140001852`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400018e4`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140001990`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400018e4`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140001990`
- `ntoskrnl!ProbeForWrite` at `0x1400015c4`
- `ntoskrnl!ProbeForWrite` at `0x1400015c4`

## pseudocode

```c
__int64 __fastcall AfdAddressListQuery(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned int a5,
        char *Address,
        SIZE_T Length,
        _QWORD *a8)
{
  char v9; // r13
  _QWORD *v10; // rbx
  __int64 v11; // rbx
  unsigned __int16 UShortFromUser; // r15
  unsigned int v13; // r14d
  unsigned int v14; // r13d
  __int64 result; // rax
  int v16; // edi
  __int64 Compartment; // rbx
  __int64 v18; // rcx
  __int64 *v19; // rax
  __int64 *v20; // r8
  __int64 *v21; // r9
  char v22; // bl
  _WORD *v23; // rcx
  unsigned __int16 *v24; // rbx
  unsigned int v25; // r11d
  char *v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // r8
  const UNICODE_STRING *v30; // rdx
  _QWORD *v31; // rbx
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // r8
  char v35; // [rsp+40h] [rbp-C8h]
  int v36; // [rsp+44h] [rbp-C4h]
  unsigned int v37; // [rsp+50h] [rbp-B8h] BYREF
  __int64 *v38; // [rsp+58h] [rbp-B0h]
  __int64 v39; // [rsp+60h] [rbp-A8h]
  int v40; // [rsp+68h] [rbp-A0h]
  char *v41; // [rsp+70h] [rbp-98h]
  char *v42; // [rsp+78h] [rbp-90h]
  __int64 *v43; // [rsp+80h] [rbp-88h]
  __int64 *v44; // [rsp+88h] [rbp-80h]
  __int64 v45; // [rsp+90h] [rbp-78h]
  _QWORD *v46; // [rsp+98h] [rbp-70h]
  _QWORD *v47; // [rsp+A0h] [rbp-68h]
  PERESOURCE *v48; // [rsp+A8h] [rbp-60h]
  __int16 v49; // [rsp+B6h] [rbp-52h] BYREF
  __int64 v50; // [rsp+B8h] [rbp-50h] BYREF

  v9 = a3;
  v35 = a3;
  v46 = a8;
  v47 = a8;
  v41 = 0;
  v42 = 0;
  v37 = 0;
  *a8 = 0;
  v10 = (_QWORD *)(a1 + 24);
  if ( (BYTE2(xmmword_1400875E0) & 2) != 0 )
    WPP_SF_qqll(1041, 17, a3, *v10, Address, a5, Length);
  if ( a5 < 2 || (unsigned int)Length < 4 )
  {
    if ( (BYTE10(xmmword_1400875E0) & 2) != 0 )
      WPP_SF_q(1297, 18, WPP_8fbd4859c37b31fb3b8ef6913c458dec_Traceguids, *v10);
    return 3221225485LL;
  }
  v11 = *v10;
  v39 = v11;
  if ( v9 )
  {
    ProbeForWrite(Address, (unsigned int)Length, 4u);
    UShortFromUser = RtlReadUShortFromUser(a4);
  }
  else
  {
    UShortFromUser = *a4;
  }
  v41 = Address;
  v42 = Address;
  v13 = 4;
  if ( v9 )
  {
    RtlWriteULongToUser(Address, 0);
    v14 = 0;
  }
  else
  {
    v14 = 0;
    *(_DWORD *)Address = 0;
  }
  result = AfdQueryCompartmentId(v11, &v37);
  v16 = result;
  v36 = result;
  if ( (int)result < 0 )
    return result;
  ExEnterCriticalRegionAndAcquireResourceShared(AfdGlobalData);
  Compartment = *(_QWORD *)(v11 + 88);
  if ( !Compartment )
  {
    ExReleaseResourceLite(AfdGlobalData);
    ExAcquireResourceExclusiveLite(AfdGlobalData, 1u);
    Compartment = AfdGetCompartment(v37);
    if ( !Compartment )
    {
      v16 = -1073741670;
      goto LABEL_56;
    }
    *(_QWORD *)(v39 + 88) = Compartment;
  }
  if ( (*(_DWORD *)(Compartment + 16) != 1 || *(_QWORD *)(Compartment + 56))
    && (UShortFromUser != 2 || *(_QWORD *)(Compartment + 32))
    && (UShortFromUser != 23 || *(_QWORD *)(Compartment + 48)) )
  {
    goto LABEL_17;
  }
  ExReleaseResourceLite(AfdGlobalData);
  ExAcquireResourceExclusiveLite(AfdGlobalData, 1u);
  if ( (*(_DWORD *)(Compartment + 16) != 1 || *(_QWORD *)(Compartment + 56))
    && (UShortFromUser != 2 || *(_QWORD *)(Compartment + 32))
    && (UShortFromUser != 23 || *(_QWORD *)(Compartment + 48)) )
  {
    v16 = 0;
    v36 = 0;
    goto LABEL_17;
  }
  v16 = AfdInitializeAddressList(Compartment, UShortFromUser);
  v36 = v16;
  if ( v16 < 0 )
  {
LABEL_56:
    ExReleaseResourceAndLeaveCriticalRegion(AfdGlobalData);
    return (unsigned int)v16;
  }
LABEL_17:
  v48 = (PERESOURCE *)(Compartment + 192);
  ExAcquireResourceSharedLite(*(PERESOURCE *)(Compartment + 192), 1u);
  ExReleaseResourceLite(AfdGlobalData);
  v18 = Compartment + 168;
  v45 = Compartment + 168;
  v19 = *(__int64 **)(Compartment + 168);
  v40 = 0;
  while ( v19 != (__int64 *)v18 )
  {
    v20 = v19;
    v38 = v19;
    v21 = v19;
    v43 = v19;
    v44 = (__int64 *)*v19;
    if ( UShortFromUser == 23
      && (v23 = (_WORD *)v19 + 21, *((_WORD *)v19 + 21) == 2)
      && (*(_DWORD *)(v39 + 8) & 0x100000) != 0 )
    {
      v22 = 1;
    }
    else
    {
      v22 = 0;
      v23 = (_WORD *)v19 + 21;
    }
    if ( *v23 == UShortFromUser || v22 )
    {
      if ( UShortFromUser == 17 )
      {
        v30 = *(const UNICODE_STRING **)(v39 + 272);
        if ( v30 )
        {
          if ( !RtlEqualUnicodeString((PCUNICODE_STRING)(v19 + 3), v30 + 2, 1u) )
            goto LABEL_23;
          v20 = v38;
          v21 = v43;
        }
      }
      if ( v22 )
      {
        v24 = (unsigned __int16 *)&v49;
        LODWORD(v38) = 30;
        v49 = 26;
        IN6ADDR_SETV4MAPPED(&v50, (char *)v21 + 46, 0, *((unsigned __int16 *)v21 + 22));
      }
      else
      {
        v24 = (unsigned __int16 *)(v20 + 5);
        v25 = *((unsigned __int16 *)v20 + 20) + 4;
        LODWORD(v38) = v25;
      }
      if ( !v36 )
      {
        if ( v25 + v13 > (unsigned int)Length )
        {
          if ( (BYTE2(xmmword_1400875E0) & 2) != 0 )
            WPP_SF_(1041, 20, WPP_8fbd4859c37b31fb3b8ef6913c458dec_Traceguids);
          v36 = -2147483643;
          v16 = -2147483643;
        }
        else
        {
          v26 = &Address[v13];
          if ( v35 )
            RtlCopyToUser(v26, v24, v25);
          else
            RtlCopyVolatileMemory(v26, v24, v25);
          if ( (BYTE2(xmmword_1400875E0) & 2) != 0 )
            WPP_SF_dd(v28, v27, v29, v24[1], *v24);
        }
      }
      v40 = ++v14;
      v13 += (unsigned int)v38;
    }
LABEL_23:
    v19 = v44;
    v18 = v45;
  }
  if ( v35 )
    RtlWriteULongToUser(Address, v14);
  else
    *(_DWORD *)Address = v14;
  v31 = v46;
  ExReleaseResourceAndLeaveCriticalRegion(*v48);
  if ( (BYTE2(xmmword_1400875E0) & 2) != 0 )
    WPP_SF_ll(v33, v32, v34, *(unsigned int *)Address, v13);
  *v31 = v13;
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1400014f0  mov     [rsp+arg_8], rbx
0x1400014f5  mov     [rsp+arg_10], rsi
0x1400014fa  push    rdi
0x1400014fb  push    r12
0x1400014fd  push    r13
0x1400014ff  push    r14
0x140001501  push    r15
0x140001503  sub     rsp, 0E0h
0x14000150a  mov     rax, cs:__security_cookie
0x140001511  xor     rax, rsp
0x140001514  mov     [rsp+108h+var_30], rax
0x14000151c  mov     r15, r9
0x14000151f  mov     r13b, r8b
0x140001522  mov     [rsp+108h+var_C8], r8b
0x140001527  mov     rsi, [rsp+108h+Address]
0x14000152f  mov     rdx, [rsp+108h+arg_38]
0x140001537  mov     [rsp+108h+var_70], rdx
0x14000153f  mov     [rsp+108h+var_68], rdx
0x140001547  mov     [rsp+108h+var_98], 0
0x140001550  mov     [rsp+108h+var_90], 0
0x140001559  mov     [rsp+108h+var_BC], 0
0x140001561  xor     eax, eax
0x140001563  mov     [rsp+108h+var_C0], ax
0x140001568  mov     [rsp+108h+var_B8], eax
0x14000156c  mov     [rdx], rax
0x14000156f  mov     [rsp+108h+var_C4], eax
0x140001573  lea     rbx, [rcx+18h]
0x140001577  lea     r12d, [rax+2]
0x14000157b  mov     r14d, dword ptr [rsp+108h+Length]
0x140001583  mov     edi, [rsp+108h+arg_20]
0x14000158a  test    byte ptr cs:xmmword_1400875E0+2, r12b
0x140001591  jnz     loc_1400019A1
0x140001597  cmp     edi, r12d
0x14000159a  jb      loc_140001A56
0x1400015a0  mov     edi, 4
0x1400015a5  cmp     r14d, edi
0x1400015a8  jb      loc_140001A56
0x1400015ae  mov     rbx, [rbx]
0x1400015b1  mov     [rsp+108h+var_A8], rbx
0x1400015b6  test    r13b, r13b
0x1400015b9  jz      short loc_140001614
0x1400015bb  mov     edx, r14d; Length
0x1400015be  mov     r8d, edi; Alignment
0x1400015c1  mov     rcx, rsi; Address
0x1400015c4  call    cs:__imp_ProbeForWrite
0x1400015cb  nop     dword ptr [rax+rax+00h]
0x1400015d0  test    r13b, r13b
0x1400015d3  jz      short loc_140001614
0x1400015d5  mov     rcx, r15
0x1400015d8  call    RtlReadUShortFromUser
0x1400015dd  movzx   r15d, ax
0x1400015e1  mov     [rsp+108h+var_C0], r15w
0x1400015e7  mov     [rsp+108h+var_98], rsi
0x1400015ec  mov     [rsp+108h+var_90], rsi
0x1400015f1  mov     r14d, edi
0x1400015f4  mov     [rsp+108h+var_BC], edi
0x1400015f8  test    r13b, r13b
0x1400015fb  jz      short loc_14000160C
0x1400015fd  xor     edx, edx
0x1400015ff  mov     rcx, rsi
0x140001602  call    RtlWriteULongToUser
0x140001607  xor     r13d, r13d
0x14000160a  jmp     short loc_14000161A
0x14000160c  xor     r13d, r13d
0x14000160f  mov     [rsi], r13d
0x140001612  jmp     short loc_14000161A
0x140001614  movzx   r15d, word ptr [r15]
0x140001618  jmp     short loc_1400015E1
0x14000161a  jmp     short loc_140001625
0x14000161c  mov     eax, [rsp+108h+var_C4]
0x140001620  jmp     loc_140001905
0x140001625  lea     rdx, [rsp+108h+var_B8]
0x14000162a  mov     rcx, rbx
0x14000162d  call    AfdQueryCompartmentId
0x140001632  mov     edi, eax
0x140001634  mov     [rsp+108h+var_C4], eax
0x140001638  test    eax, eax
0x14000163a  js      loc_140001905
0x140001640  mov     rcx, cs:AfdGlobalData; Resource
0x140001647  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceShared
0x14000164e  nop     dword ptr [rax+rax+00h]
0x140001653  mov     rbx, [rbx+58h]
0x140001657  test    rbx, rbx
0x14000165a  jz      loc_1400019C6
0x140001660  cmp     dword ptr [rbx+10h], 1
0x140001664  jnz     short loc_140001670
0x140001666  cmp     [rbx+38h], r13
0x14000166a  jz      loc_140001933
0x140001670  cmp     r15w, r12w
0x140001674  jz      loc_140001A0D
0x14000167a  cmp     r15w, 17h
0x14000167f  jz      loc_140001A1C
0x140001685  lea     rax, [rbx+0C0h]
0x14000168c  mov     [rsp+108h+var_60], rax
0x140001694  mov     dl, 1; Wait
0x140001696  mov     rcx, [rax]; Resource
0x140001699  call    cs:__imp_ExAcquireResourceSharedLite
0x1400016a0  nop     dword ptr [rax+rax+00h]
0x1400016a5  mov     rcx, cs:AfdGlobalData; Resource
0x1400016ac  call    cs:__imp_ExReleaseResourceLite
0x1400016b3  nop     dword ptr [rax+rax+00h]
0x1400016b8  lea     rcx, [rbx+0A8h]
0x1400016bf  mov     [rsp+108h+var_78], rcx
0x1400016c7  mov     rax, [rcx]
0x1400016ca  mov     [rsp+108h+var_A0], r13d
0x1400016cf  cmp     rax, rcx
0x1400016d2  jz      loc_14000176F
0x1400016d8  mov     r8, rax
0x1400016db  mov     [rsp+108h+var_B0], rax
0x1400016e0  mov     rdx, rax
0x1400016e3  mov     r9, rax
0x1400016e6  mov     [rsp+108h+var_88], rax
0x1400016ee  mov     rax, [rax]
0x1400016f1  mov     [rsp+108h+var_80], rax
0x1400016f9  mov     r10, [rsp+108h+var_A8]
0x1400016fe  cmp     r15w, 17h
0x140001703  jz      loc_14000178E
0x140001709  xor     bl, bl
0x14000170b  lea     rcx, [rdx+2Ah]
0x14000170f  cmp     [rcx], r15w
0x140001713  jz      short loc_14000172B
0x140001715  test    bl, bl
0x140001717  jnz     short loc_14000172B
0x140001719  mov     rax, [rsp+108h+var_80]
0x140001721  mov     rcx, [rsp+108h+var_78]
0x140001729  jmp     short loc_1400016CF
0x14000172b  mov     eax, 11h
0x140001730  cmp     r15w, ax
0x140001734  jz      loc_140001837
0x14000173a  test    bl, bl
0x14000173c  jnz     loc_140001801
0x140001742  lea     rbx, [r8+28h]
0x140001746  movzx   r11d, word ptr [rbx]
0x14000174a  add     r11d, 4
0x14000174e  mov     dword ptr [rsp+108h+var_B0], r11d
0x140001753  mov     eax, [rsp+108h+var_C4]
0x140001757  test    eax, eax
0x140001759  jz      short loc_1400017B1
0x14000175b  inc     r13d
0x14000175e  mov     [rsp+108h+var_A0], r13d
0x140001763  add     r14d, dword ptr [rsp+108h+var_B0]
0x140001768  mov     [rsp+108h+var_BC], r14d
0x14000176d  jmp     short loc_140001719
0x14000176f  cmp     [rsp+108h+var_C8], 0
0x140001774  jz      short loc_140001786
0x140001776  mov     edx, r13d
0x140001779  mov     rcx, rsi
0x14000177c  call    RtlWriteULongToUser
0x140001781  jmp     loc_1400018B2
0x140001786  mov     [rsi], r13d
0x140001789  jmp     loc_1400018B2
0x14000178e  lea     rcx, [r8+2Ah]
0x140001792  cmp     [rcx], r12w
0x140001796  jnz     loc_140001709
0x14000179c  mov     eax, [r10+8]
0x1400017a0  bt      eax, 14h
0x1400017a4  jnb     loc_140001709
0x1400017aa  mov     bl, 1
0x1400017ac  jmp     loc_14000170F
0x1400017b1  lea     eax, [r11+r14]
0x1400017b5  cmp     eax, dword ptr [rsp+108h+Length]
0x1400017bc  ja      loc_140001882
0x1400017c2  mov     ecx, r14d
0x1400017c5  add     rcx, rsi; void *
0x1400017c8  mov     r8d, r11d; Size
0x1400017cb  mov     rdx, rbx; Src
0x1400017ce  cmp     [rsp+108h+var_C8], 0
0x1400017d3  jz      loc_140001878
0x1400017d9  call    RtlCopyToUser
0x1400017de  test    byte ptr cs:xmmword_1400875E0+2, r12b
0x1400017e5  jz      loc_14000175B
0x1400017eb  movzx   eax, word ptr [rbx]
0x1400017ee  movzx   r9d, word ptr [rbx+2]
0x1400017f3  mov     dword ptr [rsp+108h+var_E8], eax
0x1400017f7  call    WPP_SF_dd
0x1400017fc  jmp     loc_14000175B
0x140001801  xor     r8d, r8d
0x140001804  lea     rcx, [rsp+108h+var_4F]
0x14000180c  and     rcx, 0FFFFFFFFFFFFFFF8h
0x140001810  lea     rbx, [rcx-2]
0x140001814  lea     r11d, [r8+1Eh]
0x140001818  mov     dword ptr [rsp+108h+var_B0], r11d
0x14000181d  lea     eax, [r8+1Ah]
0x140001821  mov     [rbx], ax
0x140001824  lea     rdx, [r9+2Eh]
0x140001828  movzx   r9d, word ptr [r9+2Ch]
0x14000182d  call    IN6ADDR_SETV4MAPPED
0x140001832  jmp     loc_140001753
0x140001837  mov     rdx, [r10+110h]
0x14000183e  test    rdx, rdx
0x140001841  jz      loc_14000173A
0x140001847  add     rdx, 20h ; ' '; String2
0x14000184b  lea     rcx, [r8+18h]; String1
0x14000184f  mov     r8b, 1; CaseInSensitive
0x140001852  call    cs:__imp_RtlEqualUnicodeString
0x140001859  nop     dword ptr [rax+rax+00h]
0x14000185e  test    al, al
0x140001860  jz      loc_140001719
0x140001866  mov     r8, [rsp+108h+var_B0]
0x14000186b  mov     r9, [rsp+108h+var_88]
0x140001873  jmp     loc_14000173A
0x140001878  call    RtlCopyVolatileMemory
0x14000187d  jmp     loc_1400017DE
0x140001882  test    byte ptr cs:xmmword_1400875E0+2, r12b
0x140001889  jz      short loc_1400018A1
0x14000188b  mov     edx, 14h
0x140001890  mov     ecx, 411h
0x140001895  lea     r8, WPP_8fbd4859c37b31fb3b8ef6913c458dec_Traceguids
0x14000189c  call    WPP_SF_
0x1400018a1  mov     [rsp+108h+var_C4], 80000005h
0x1400018a9  mov     edi, [rsp+108h+var_C4]
0x1400018ad  jmp     loc_14000175B
0x1400018b2  mov     rbx, [rsp+108h+var_70]
0x1400018ba  jmp     short loc_1400018D9
0x1400018bc  xor     r14d, r14d
0x1400018bf  mov     [rsp+108h+var_BC], r14d
0x1400018c4  lea     r12d, [r14+2]
0x1400018c8  mov     edi, [rsp+108h+var_C4]
0x1400018cc  mov     rsi, [rsp+108h+var_98]
0x1400018d1  mov     rbx, [rsp+108h+var_68]
0x1400018d9  mov     rcx, [rsp+108h+var_60]
0x1400018e1  mov     rcx, [rcx]; Resource
0x1400018e4  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x1400018eb  nop     dword ptr [rax+rax+00h]
0x1400018f0  test    byte ptr cs:xmmword_1400875E0+2, r12b
0x1400018f7  jnz     loc_140001A44
0x1400018fd  mov     ecx, r14d
0x140001900  mov     [rbx], rcx
0x140001903  mov     eax, edi
0x140001905  mov     rcx, [rsp+108h+var_30]
0x14000190d  xor     rcx, rsp; StackCookie
0x140001910  call    __security_check_cookie
0x140001915  lea     r11, [rsp+108h+var_28]
0x14000191d  mov     rbx, [r11+38h]
0x140001921  mov     rsi, [r11+40h]
0x140001925  mov     rsp, r11
0x140001928  pop     r15
0x14000192a  pop     r14
0x14000192c  pop     r13
0x14000192e  pop     r12
0x140001930  pop     rdi
0x140001931  retn
0x140001933  mov     rcx, cs:AfdGlobalData; Resource
0x14000193a  call    cs:__imp_ExReleaseResourceLite
0x140001941  nop     dword ptr [rax+rax+00h]
0x140001946  mov     dl, 1; Wait
0x140001948  mov     rcx, cs:AfdGlobalData; Resource
0x14000194f  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140001956  nop     dword ptr [rax+rax+00h]
0x14000195b  cmp     dword ptr [rbx+10h], 1
0x14000195f  jnz     loc_140001A2B
0x140001965  cmp     [rbx+38h], r13
0x140001969  jnz     loc_140001A2B
0x14000196f  movzx   edx, r15w
0x140001973  mov     rcx, rbx
0x140001976  call    AfdInitializeAddressList
0x14000197b  mov     edi, eax
0x14000197d  mov     [rsp+108h+var_C4], eax
0x140001981  test    eax, eax
0x140001983  jns     loc_140001685
0x140001989  mov     rcx, cs:AfdGlobalData; Resource
0x140001990  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x140001997  nop     dword ptr [rax+rax+00h]
0x14000199c  jmp     loc_140001903
0x1400019a1  mov     edx, 11h
0x1400019a6  mov     ecx, 411h
0x1400019ab  mov     [rsp+108h+var_D8], r14d
0x1400019b0  mov     [rsp+108h+var_E0], edi
0x1400019b4  mov     [rsp+108h+var_E8], rsi
0x1400019b9  mov     r9, [rbx]
0x1400019bc  call    WPP_SF_qqll
0x1400019c1  jmp     loc_140001597
0x1400019c6  mov     rcx, cs:AfdGlobalData; Resource
0x1400019cd  call    cs:__imp_ExReleaseResourceLite
0x1400019d4  nop     dword ptr [rax+rax+00h]
0x1400019d9  mov     dl, 1; Wait
0x1400019db  mov     rcx, cs:AfdGlobalData; Resource
0x1400019e2  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400019e9  nop     dword ptr [rax+rax+00h]
0x1400019ee  mov     ecx, [rsp+108h+var_B8]
0x1400019f2  call    AfdGetCompartment
0x1400019f7  mov     rbx, rax
0x1400019fa  test    rax, rax
0x1400019fd  jnz     loc_14007477C
0x140001a03  mov     edi, 0C000009Ah
0x140001a08  jmp     loc_140001989
0x140001a0d  cmp     [rbx+20h], r13
0x140001a11  jz      loc_140001933
0x140001a17  jmp     loc_14000167A
0x140001a1c  cmp     [rbx+30h], r13
0x140001a20  jnz     loc_140001685
0x140001a26  jmp     loc_140001933
0x140001a2b  cmp     r15w, r12w
0x140001a2f  jnz     loc_14007478A
0x140001a35  cmp     [rbx+20h], r13
0x140001a39  jz      loc_14000196F
0x140001a3f  jmp     loc_14007478A
0x140001a44  mov     dword ptr [rsp+108h+var_E8], r14d
0x140001a49  mov     r9d, [rsi]
0x140001a4c  call    WPP_SF_ll
  ... truncated ...
```
