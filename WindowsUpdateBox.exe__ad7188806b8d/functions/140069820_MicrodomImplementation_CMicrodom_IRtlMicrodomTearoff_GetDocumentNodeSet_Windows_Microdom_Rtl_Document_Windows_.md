# MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetDocumentNodeSet(Windows::Microdom::Rtl::Document,Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>> *)

- ea: `0x140069820`
- end: `0x140069a1d`
- name: `?GetDocumentNodeSet@CMicrodom_IRtlMicrodomTearoff@MicrodomImplementation@@UEAAJUDocument@Rtl@Microdom@Windows@@PEAV?$Auto@U?$Vector@UNode@Rtl@Microdom@Windows@@@Windows@@@6@@Z`
- size: `509`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1400674ac`
- `0x140069820`
- `0x140072764`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x140069921`
- `ntdll!RtlFreeHeap` at `0x1400699d6`
- `ntdll!RtlFreeHeap` at `0x140069a09`
- `ntdll!RtlFreeHeap` at `0x140069921`
- `ntdll!RtlFreeHeap` at `0x1400699d6`
- `ntdll!RtlFreeHeap` at `0x140069a09`

## string_xrefs

- `0x140069842`: `onecore\base\xml\udom_microdom.cpp`
- `0x140069889`: `onecore\base\xml\udom_microdom.cpp`
- `0x1400698d1`: `onecore\base\xml\udom_microdom.cpp`
- `0x1400698f9`: `TempNodes.Allocate(this->m_LayoutCache.TotalObjectCount())`
- `0x140069860`: `whichDoc.Reserved == m_pTargetObject->m_LayoutCache.DocumentId()`

## pseudocode

```c
__int64 __fastcall MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetDocumentNodeSet(
        __int64 a1,
        __int64 a2,
        void **a3)
{
  __int64 v3; // rsi
  const char *v5; // rax
  __int64 v7; // rdx
  unsigned int v8; // ebx
  unsigned __int64 v9; // rdx
  PVOID v10; // r8
  _DWORD *v11; // r9
  int v12; // ecx
  void *v13; // r8
  int v14; // [rsp+24h] [rbp-4Ch]
  int v15; // [rsp+2Ch] [rbp-44h]
  PVOID P[2]; // [rsp+30h] [rbp-40h] BYREF
  __int64 v17; // [rsp+40h] [rbp-30h]
  const char *v18; // [rsp+48h] [rbp-28h]
  _QWORD v19[4]; // [rsp+50h] [rbp-20h] BYREF

  v3 = *(_QWORD *)(a1 - 8);
  if ( *(_DWORD *)(a2 + 8) != *(_DWORD *)(*(_QWORD *)(v3 + 96) + 16LL) )
  {
    v17 = 3486;
    P[0] = "onecore\\base\\xml\\udom_microdom.cpp";
    P[1] = "MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetDocumentNodeSet";
    v5 = "whichDoc.Reserved == m_pTargetObject->m_LayoutCache.DocumentId()";
LABEL_3:
    v18 = v5;
    RtlReportErrorOrigination(P, a2, 3221225485LL);
    return 3221225485LL;
  }
  if ( !a3 )
  {
    v17 = 3487;
    P[0] = "onecore\\base\\xml\\udom_microdom.cpp";
    P[1] = "MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetDocumentNodeSet";
    v5 = "Not-null check failed: NodeSet";
    goto LABEL_3;
  }
  P[0] = 0;
  P[1] = 0;
  if ( Windows::AutoVectorBase<Windows::Microdom::MicrodomVectorTraits<Windows::Microdom::Rtl::Element>,Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>>::Allocate(P) )
  {
    v9 = 0;
    if ( *(_DWORD *)(*(_QWORD *)(v3 + 96) + 8LL) )
    {
      v10 = P[0];
      v11 = (char *)P[0] + 8;
      while ( 1 )
      {
        v12 = 0;
        if ( v9 > 0xFFFFFFFF )
        {
          v14 = -1073741675;
          LOBYTE(v15) = -107;
        }
        else
        {
          v12 = v9;
          if ( v9 == (unsigned int)v9 )
          {
            v14 = 0;
            LOBYTE(v15) = 0;
          }
          else
          {
            v14 = -1073741595;
            LOBYTE(v15) = -27;
          }
        }
        *(_WORD *)((char *)&v15 + 1) = *(_WORD *)((char *)&v14 + 1);
        HIBYTE(v15) = HIBYTE(v14);
        v8 = v15;
        *v11 = v12;
        if ( v15 < 0 )
          break;
        ++v9;
        v11 += 4;
        if ( v9 == *(_DWORD *)(*(_QWORD *)(v3 + 96) + 8LL) )
          goto LABEL_19;
      }
      if ( v10 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
      if ( v15 < 0 )
        return v8;
    }
    else
    {
LABEL_19:
      v13 = *a3;
      *(_OWORD *)a3 = *(_OWORD *)P;
      if ( v13 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v13);
    }
    return 0;
  }
  v19[2] = 1074;
  v19[0] = "onecore\\base\\xml\\udom_microdom.cpp";
  v19[1] = "MicrodomImplementation::CMicrodom::GetDocumentNodeSet";
  v19[3] = "TempNodes.Allocate(this->m_LayoutCache.TotalObjectCount())";
  RtlReportErrorOrigination(v19, v7, 3221225495LL);
  if ( P[0] )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
  return (unsigned int)-1073741801;
}

```

## disassembly

```asm
0x140069820  mov     [rsp-18h+arg_8], rbx
0x140069825  push    rbp
0x140069826  push    rsi
0x140069827  push    rdi
0x140069828  mov     rbp, rsp
0x14006982b  sub     rsp, 70h
0x14006982f  mov     rsi, [rcx-8]
0x140069833  mov     rdi, r8
0x140069836  mov     rcx, [rsi+60h]
0x14006983a  mov     eax, [rcx+10h]
0x14006983d  cmp     [rdx+8], eax
0x140069840  jz      short loc_140069884
0x140069842  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x140069849  mov     [rbp+var_30], 0D9Eh
0x140069851  mov     [rbp+P], rax
0x140069855  lea     rax, aMicrodomimplem_37; "MicrodomImplementation::CMicrodom_IRtlM"...
0x14006985c  mov     [rbp+P+8], rax
0x140069860  lea     rax, aWhichdocReserv; "whichDoc.Reserved == m_pTargetObject->m"...
0x140069867  mov     r8d, 0C000000Dh
0x14006986d  mov     [rbp+var_28], rax
0x140069871  lea     rcx, [rbp+P]
0x140069875  call    RtlReportErrorOrigination
0x14006987a  mov     eax, 0C000000Dh
0x14006987f  jmp     loc_1400699E4
0x140069884  test    rdi, rdi
0x140069887  jnz     short loc_1400698B0
0x140069889  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x140069890  mov     [rbp+var_30], 0D9Fh
0x140069898  mov     [rbp+P], rax
0x14006989c  lea     rax, aMicrodomimplem_37; "MicrodomImplementation::CMicrodom_IRtlM"...
0x1400698a3  mov     [rbp+P+8], rax
0x1400698a7  lea     rax, aNotNullCheckFa_12; "Not-null check failed: NodeSet"
0x1400698ae  jmp     short loc_140069867
0x1400698b0  mov     edx, [rcx+8]
0x1400698b3  lea     rcx, [rbp+P]
0x1400698b7  mov     [rbp+P], 0
0x1400698bf  mov     [rbp+P+8], 0
0x1400698c7  call    ?Allocate@?$AutoVectorBase@V?$MicrodomVectorTraits@UElement@Rtl@Microdom@Windows@@@Microdom@Windows@@V?$Auto@U?$Vector@UElement@Rtl@Microdom@Windows@@@Windows@@@3@@Windows@@QEAAPEAUElement@Rtl@Microdom@2@_K@Z; Windows::AutoVectorBase<Windows::Microdom::MicrodomVectorTraits<Windows::Microdom::Rtl::Element>,Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>>::Allocate(unsigned __int64)
0x1400698cc  test    rax, rax
0x1400698cf  jnz     short loc_140069937
0x1400698d1  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x1400698d8  mov     [rbp+var_10], 432h
0x1400698e0  mov     [rbp+var_20], rax
0x1400698e4  lea     rcx, [rbp+var_20]
0x1400698e8  lea     rax, aMicrodomimplem_7; "MicrodomImplementation::CMicrodom::GetD"...
0x1400698ef  mov     r8d, 0C0000017h
0x1400698f5  mov     [rbp+var_18], rax
0x1400698f9  lea     rax, aTempnodesAlloc_0; "TempNodes.Allocate(this->m_LayoutCache."...
0x140069900  mov     [rbp+var_8], rax
0x140069904  call    RtlReportErrorOrigination
0x140069909  mov     r8, [rbp+P]; P
0x14006990d  test    r8, r8
0x140069910  jz      short loc_14006992D
0x140069912  mov     rcx, gs:60h
0x14006991b  xor     edx, edx; Flags
0x14006991d  mov     rcx, [rcx+30h]; HeapHandle
0x140069921  call    cs:__imp_RtlFreeHeap
0x140069928  nop     dword ptr [rax+rax+00h]
0x14006992d  mov     ebx, 0C0000017h
0x140069932  jmp     loc_140069A19
0x140069937  mov     rax, [rsi+60h]
0x14006993b  xor     edx, edx
0x14006993d  cmp     [rax+8], edx
0x140069940  jz      short loc_1400699B2
0x140069942  mov     r8, [rbp+P]; P
0x140069946  lea     r9, [r8+8]
0x14006994a  xor     eax, eax
0x14006994c  xor     ecx, ecx
0x14006994e  mov     [rbp+var_4C], eax
0x140069951  mov     eax, 0FFFFFFFFh
0x140069956  cmp     rdx, rax
0x140069959  ja      short loc_14006997C
0x14006995b  mov     ecx, edx
0x14006995d  cmp     rdx, rcx
0x140069960  jz      short loc_14006996F
0x140069962  mov     [rbp+var_4C], 0C00000E5h
0x140069969  mov     byte ptr [rbp+var_44], 0E5h
0x14006996d  jmp     short loc_140069987
0x14006996f  mov     [rbp+var_4C], 0
0x140069976  mov     byte ptr [rbp+var_44], 0
0x14006997a  jmp     short loc_140069987
0x14006997c  mov     [rbp+var_4C], 0C0000095h
0x140069983  mov     byte ptr [rbp+var_44], 95h
0x140069987  movzx   eax, word ptr [rbp+var_4C+1]
0x14006998b  mov     word ptr [rbp+var_44+1], ax
0x14006998f  mov     al, byte ptr [rbp+var_4C+3]
0x140069992  mov     byte ptr [rbp+var_44+3], al
0x140069995  mov     ebx, [rbp+var_44]
0x140069998  mov     [r9], ecx
0x14006999b  test    ebx, ebx
0x14006999d  js      short loc_1400699F5
0x14006999f  mov     rax, [rsi+60h]
0x1400699a3  inc     rdx
0x1400699a6  add     r9, 10h
0x1400699aa  mov     ecx, [rax+8]
0x1400699ad  cmp     rdx, rcx
0x1400699b0  jnz     short loc_14006994A
0x1400699b2  movups  xmm1, xmmword ptr [rdi]
0x1400699b5  movaps  xmm0, xmmword ptr [rbp+P]
0x1400699b9  movq    r8, xmm1; P
0x1400699be  movdqu  xmmword ptr [rdi], xmm0
0x1400699c2  test    r8, r8
0x1400699c5  jz      short loc_1400699E2
0x1400699c7  mov     rcx, gs:60h
0x1400699d0  xor     edx, edx; Flags
0x1400699d2  mov     rcx, [rcx+30h]; HeapHandle
0x1400699d6  call    cs:__imp_RtlFreeHeap
0x1400699dd  nop     dword ptr [rax+rax+00h]
0x1400699e2  xor     eax, eax
0x1400699e4  mov     rbx, [rsp+70h+arg_8]
0x1400699ec  add     rsp, 70h
0x1400699f0  pop     rdi
0x1400699f1  pop     rsi
0x1400699f2  pop     rbp
0x1400699f3  retn
0x1400699f5  test    r8, r8
0x1400699f8  jz      short loc_140069A15
0x1400699fa  mov     rcx, gs:60h
0x140069a03  xor     edx, edx; Flags
0x140069a05  mov     rcx, [rcx+30h]; HeapHandle
0x140069a09  call    cs:__imp_RtlFreeHeap
0x140069a10  nop     dword ptr [rax+rax+00h]
0x140069a15  test    ebx, ebx
0x140069a17  jns     short loc_1400699E2
0x140069a19  mov     eax, ebx
0x140069a1b  jmp     short loc_1400699E4
```
