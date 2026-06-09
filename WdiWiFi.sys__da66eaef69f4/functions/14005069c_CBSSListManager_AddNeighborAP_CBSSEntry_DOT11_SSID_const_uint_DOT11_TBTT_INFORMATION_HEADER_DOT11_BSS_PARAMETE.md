# CBSSListManager::AddNeighborAP(CBSSEntry *,_DOT11_SSID * const,uint,DOT11_TBTT_INFORMATION_HEADER,DOT11_BSS_PARAMETERS,DOT11_MLD_PARAMETERS,uchar (*)[6],_DOT11_BAND_ID,uchar)

- ea: `0x14005069c`
- end: `0x140050991`
- name: `?AddNeighborAP@CBSSListManager@@QEAAPEAVCBSSEntry@@PEAV2@QEAU_DOT11_SSID@@ITDOT11_TBTT_INFORMATION_HEADER@@TDOT11_BSS_PARAMETERS@@TDOT11_MLD_PARAMETERS@@PEAY05EW4_DOT11_BAND_ID@@E@Z`
- size: `757`
- prototype: `struct CBSSEntry *(CBSSListManager *__hidden this, struct CBSSEntry *, struct _DOT11_SSID *const, unsigned int, union DOT11_TBTT_INFORMATION_HEADER, union DOT11_BSS_PARAMETERS, union DOT11_MLD_PARAMETERS *__struct_ptr, unsigned __int8 (*)[6], enum _DOT11_BAND_ID, unsigned __int8)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400500c0`

## callees

- `0x140005eb0`
- `0x140019574`
- `0x14005069c`
- `0x140050a10`
- `0x14005f678`
- `0x14006457c`
- `0x140065338`
- `0x1400bbeec`
- `0x1400da680`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14005073d`
- `ntoskrnl!ExAllocatePool2` at `0x14005073d`

## pseudocode

```c
struct CBSSEntry *__fastcall CBSSListManager::AddNeighborAP(
        CBSSListManager *this,
        struct CBSSEntry *a2,
        struct _DOT11_SSID *const a3,
        unsigned int a4,
        union DOT11_TBTT_INFORMATION_HEADER a5,
        union DOT11_BSS_PARAMETERS a6,
        union DOT11_MLD_PARAMETERS *a7,
        unsigned __int8 (*a8)[6],
        enum _DOT11_BAND_ID a9,
        char a10)
{
  unsigned __int8 *v10; // rsi
  CBSSEntry *CppObjectFromListEntry; // rdi
  _LIST_ENTRY *p_m_BSSEntryList; // r8
  CBSSEntry *v16; // rdx
  struct _LIST_ENTRY *i; // rcx
  struct _LIST_ENTRY **v18; // rcx
  unsigned int m_BssEntryShortSsid; // eax
  CBSSEntry *Pool2; // rax
  int v21; // edx
  int v22; // r8d
  CBSSEntry *v23; // rax
  char v24; // r15
  enum _WDI_BAND_ID v25; // eax
  char v26; // r13
  union DOT11_BSS_PARAMETERS v27; // bl
  int v28; // edx
  int v29; // r8d
  int v30; // edx
  int v31; // r8d
  struct _DOT11_SSID *v33; // [rsp+A0h] [rbp+18h] BYREF

  v33 = a3;
  v10 = (unsigned __int8 *)a8;
  if ( a4 )
  {
    p_m_BSSEntryList = &this->m_BSSEntryList;
    v16 = 0;
    for ( i = this->m_BSSEntryList.Flink; i != p_m_BSSEntryList; i = *v18 )
    {
      CppObjectFromListEntry = (CBSSEntry *)GetCppObjectFromListEntry(i);
      if ( *(_DWORD *)v10 == *(_DWORD *)CppObjectFromListEntry->m_BssID
        && *((_WORD *)v10 + 2) == *(_WORD *)&CppObjectFromListEntry->m_BssID[4] )
      {
        m_BssEntryShortSsid = CppObjectFromListEntry->m_BssEntryShortSsid;
        if ( a4 == m_BssEntryShortSsid )
          goto LABEL_12;
        if ( !m_BssEntryShortSsid )
          v16 = CppObjectFromListEntry;
      }
    }
    CppObjectFromListEntry = v16;
  }
  else
  {
    CppObjectFromListEntry = (CBSSEntry *)this->FindBSSEntry(this, a8);
  }
LABEL_12:
  if ( CppObjectFromListEntry )
  {
    v24 = 0;
    goto LABEL_20;
  }
  Pool2 = (CBSSEntry *)ExAllocatePool2(64, 800, 1198089303);
  if ( Pool2 )
  {
    v23 = CBSSEntry::CBSSEntry(Pool2, (const unsigned __int8 (*)[6])v10, 0);
    CppObjectFromListEntry = v23;
    if ( v23 )
    {
      v24 = 1;
      v23->m_BssEntryShortSsid = a4;
LABEL_20:
      v25 = CDot11ToWabiConverter::MapBandID(a9);
      v26 = a10;
      if ( v25 != WDI_BAND_ID_ANY && a10 && (unsigned int)(CppObjectFromListEntry->m_BssChannelInfo.BandId + 1) <= 1 )
      {
        CppObjectFromListEntry->m_BssChannelInfo.Channel = (unsigned __int8)a10;
        CppObjectFromListEntry->m_BssChannelInfo.BandId = v25;
      }
      v27.0 = a6.0;
      *(union DOT11_MLD_PARAMETERS *)&v33 = (union DOT11_MLD_PARAMETERS)a7->0;
      if ( !(unsigned int)CBSSEntry::AddIncomingLinkFromNeighborAP(
                            CppObjectFromListEntry,
                            a2,
                            a5,
                            a6,
                            (union DOT11_MLD_PARAMETERS *)&v33) )
      {
        *(union DOT11_MLD_PARAMETERS *)&v33 = (union DOT11_MLD_PARAMETERS)a7->0;
        if ( !(unsigned int)CBSSEntry::AddOutgoingLinkToNeighborAP(
                              a2,
                              CppObjectFromListEntry,
                              a4,
                              a5,
                              v27,
                              (union DOT11_MLD_PARAMETERS *)&v33,
                              (unsigned __int8 (*)[6])v10,
                              a9,
                              v26) )
        {
          if ( !v24 || !this->AddBSSEntry(this, CppObjectFromListEntry, a2, 0) )
            return CppObjectFromListEntry;
          if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_D_MAC__MAC_(WPP_GLOBAL_Control->DeviceExtension, v30, v31, 143);
          goto LABEL_33;
        }
        CBSSEntry::RemoveIncomingLinkFromNeighborAP(CppObjectFromListEntry, a2);
      }
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_D_MAC__MAC_(WPP_GLOBAL_Control->DeviceExtension, v28, v29, 144);
LABEL_33:
      if ( CppObjectFromListEntry && v24 )
      {
        ((void (__fastcall *)(CBSSEntry *, __int64))CppObjectFromListEntry->~CBSSEntry)(CppObjectFromListEntry, 1);
        return 0;
      }
      return CppObjectFromListEntry;
    }
  }
  else
  {
    CppObjectFromListEntry = 0;
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_D_MAC__MAC_(WPP_GLOBAL_Control->DeviceExtension, v21, v22, 142);
  return CppObjectFromListEntry;
}

```

## disassembly

```asm
0x14005069c  mov     [rsp+arg_0], rbx
0x1400506a1  mov     [rsp+arg_10], r8
0x1400506a6  push    rbp
0x1400506a7  push    rsi
0x1400506a8  push    rdi
0x1400506a9  push    r12
0x1400506ab  push    r13
0x1400506ad  push    r14
0x1400506af  push    r15
0x1400506b1  sub     rsp, 50h
0x1400506b5  mov     rsi, [rsp+88h+arg_38]
0x1400506bd  mov     ebp, r9d
0x1400506c0  mov     r14, rdx
0x1400506c3  mov     r12, rcx
0x1400506c6  test    r9d, r9d
0x1400506c9  jnz     short loc_1400506DE
0x1400506cb  mov     rax, [rcx]
0x1400506ce  mov     rdx, rsi
0x1400506d1  mov     rax, [rax]
0x1400506d4  call    _guard_dispatch_icall
0x1400506d9  mov     rdi, rax
0x1400506dc  jmp     short loc_140050726
0x1400506de  lea     r8, [rcx+158h]
0x1400506e5  xor     edx, edx
0x1400506e7  mov     rcx, [r8]
0x1400506ea  jmp     short loc_14005071E
0x1400506ec  call    ?GetCppObjectFromListEntry@@YAPEAXPEAU_LIST_ENTRY@@@Z; GetCppObjectFromListEntry(_LIST_ENTRY *)
0x1400506f1  mov     rdi, rax
0x1400506f4  mov     eax, [rsi]
0x1400506f6  cmp     eax, [rdi+1BCh]
0x1400506fc  jnz     short loc_14005071B
0x1400506fe  movzx   eax, word ptr [rsi+4]
0x140050702  cmp     ax, [rdi+1C0h]
0x140050709  jnz     short loc_14005071B
0x14005070b  mov     eax, [rdi+210h]
0x140050711  cmp     ebp, eax
0x140050713  jz      short loc_140050726
0x140050715  test    eax, eax
0x140050717  cmovz   rdx, rdi
0x14005071b  mov     rcx, [rcx]; struct _LIST_ENTRY *
0x14005071e  cmp     rcx, r8
0x140050721  jnz     short loc_1400506EC
0x140050723  mov     rdi, rdx
0x140050726  test    rdi, rdi
0x140050729  jnz     loc_1400507B5
0x14005072f  mov     edx, 320h
0x140050734  lea     ecx, [rdi+40h]
0x140050737  mov     r8d, 47696457h
0x14005073d  call    cs:__imp_ExAllocatePool2
0x140050744  nop     dword ptr [rax+rax+00h]
0x140050749  test    rax, rax
0x14005074c  jz      short loc_14005076F
0x14005074e  xor     r8d, r8d; unsigned __int8
0x140050751  mov     rdx, rsi; unsigned __int8 (*)[6]
0x140050754  mov     rcx, rax; this
0x140050757  call    ??0CBSSEntry@@QEAA@AEAY05$$CBEE@Z; CBSSEntry::CBSSEntry(uchar const (&)[6],uchar)
0x14005075c  mov     rdi, rax
0x14005075f  test    rax, rax
0x140050762  jz      short loc_140050771
0x140050764  mov     r15b, 1
0x140050767  mov     [rax+210h], ebp
0x14005076d  jmp     short loc_1400507B8
0x14005076f  xor     edi, edi
0x140050771  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140050778  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14005077f  jz      loc_140050975
0x140050785  mov     rcx, cs:WPP_GLOBAL_Control
0x14005078c  lea     rax, [r14+1BCh]
0x140050793  mov     qword ptr [rsp+88h+var_50], rax
0x140050798  mov     r9d, 8Eh
0x14005079e  mov     [rsp+88h+var_58], rsi
0x1400507a3  mov     dword ptr [rsp+88h+var_60], ebp
0x1400507a7  mov     rcx, [rcx+40h]
0x1400507ab  call    WPP_RECORDER_SF_D_MAC__MAC_
0x1400507b0  jmp     loc_140050975
0x1400507b5  xor     r15b, r15b
0x1400507b8  mov     ecx, [rsp+88h+arg_40]; enum _DOT11_BAND_ID
0x1400507bf  call    ?MapBandID@CDot11ToWabiConverter@@SA?AW4_WDI_BAND_ID@@W4_DOT11_BAND_ID@@@Z; CDot11ToWabiConverter::MapBandID(_DOT11_BAND_ID)
0x1400507c4  movzx   r13d, [rsp+88h+arg_48]
0x1400507cd  cmp     eax, 0FFFFFFFFh
0x1400507d0  jz      short loc_1400507F1
0x1400507d2  test    r13b, r13b
0x1400507d5  jz      short loc_1400507F1
0x1400507d7  mov     ecx, [rdi+20Ch]
0x1400507dd  inc     ecx
0x1400507df  cmp     ecx, 1
0x1400507e2  ja      short loc_1400507F1
0x1400507e4  mov     [rdi+208h], r13d
0x1400507eb  mov     [rdi+20Ch], eax
0x1400507f1  mov     rcx, [rsp+88h+arg_30]
0x1400507f9  mov     rdx, r14; struct CBSSEntry *
0x1400507fc  mov     bl, byte ptr [rsp+88h+arg_28]
0x140050803  movzx   r8d, word ptr [rsp+88h+arg_20]; union DOT11_TBTT_INFORMATION_HEADER
0x14005080c  mov     r9b, bl; union DOT11_BSS_PARAMETERS
0x14005080f  movzx   eax, word ptr [rcx]
0x140050812  mov     word ptr [rsp+88h+arg_10], ax
0x14005081a  mov     al, [rcx+2]
0x14005081d  mov     rcx, rdi; this
0x140050820  mov     byte ptr [rsp+88h+arg_10+2], al
0x140050827  lea     rax, [rsp+88h+arg_10]
0x14005082f  mov     qword ptr [rsp+88h+var_68], rax; union DOT11_MLD_PARAMETERS *
0x140050834  call    ?AddIncomingLinkFromNeighborAP@CBSSEntry@@QEAAHPEAV1@TDOT11_TBTT_INFORMATION_HEADER@@TDOT11_BSS_PARAMETERS@@TDOT11_MLD_PARAMETERS@@@Z; CBSSEntry::AddIncomingLinkFromNeighborAP(CBSSEntry *,DOT11_TBTT_INFORMATION_HEADER,DOT11_BSS_PARAMETERS,DOT11_MLD_PARAMETERS)
0x140050839  test    eax, eax
0x14005083b  jnz     loc_140050915
0x140050841  mov     rcx, [rsp+88h+arg_30]
0x140050849  mov     r8d, ebp; unsigned int
0x14005084c  movzx   r9d, word ptr [rsp+88h+arg_20]; union DOT11_TBTT_INFORMATION_HEADER
0x140050855  mov     rdx, rdi; struct CBSSEntry *
0x140050858  mov     [rsp+88h+var_48], r13b; char
0x14005085d  movzx   eax, word ptr [rcx]
0x140050860  mov     word ptr [rsp+88h+arg_10], ax
0x140050868  mov     al, [rcx+2]
0x14005086b  mov     rcx, r14; this
0x14005086e  mov     byte ptr [rsp+88h+arg_10+2], al
0x140050875  mov     eax, [rsp+88h+arg_40]
0x14005087c  mov     [rsp+88h+var_50], eax; enum _DOT11_BAND_ID
0x140050880  lea     rax, [rsp+88h+arg_10]
0x140050888  mov     [rsp+88h+var_58], rsi; unsigned __int8 (*)[6]
0x14005088d  mov     [rsp+88h+var_60], rax; union DOT11_MLD_PARAMETERS *
0x140050892  mov     byte ptr [rsp+88h+var_68], bl; union DOT11_BSS_PARAMETERS
0x140050896  call    ?AddOutgoingLinkToNeighborAP@CBSSEntry@@QEAAHPEAV1@ITDOT11_TBTT_INFORMATION_HEADER@@TDOT11_BSS_PARAMETERS@@TDOT11_MLD_PARAMETERS@@PEAY05EW4_DOT11_BAND_ID@@E@Z; CBSSEntry::AddOutgoingLinkToNeighborAP(CBSSEntry *,uint,DOT11_TBTT_INFORMATION_HEADER,DOT11_BSS_PARAMETERS,DOT11_MLD_PARAMETERS,uchar (*)[6],_DOT11_BAND_ID,uchar)
0x14005089b  mov     ebx, eax
0x14005089d  test    eax, eax
0x14005089f  jz      short loc_1400508AE
0x1400508a1  mov     rdx, r14; struct CBSSEntry *
0x1400508a4  mov     rcx, rdi; this
0x1400508a7  call    ?RemoveIncomingLinkFromNeighborAP@CBSSEntry@@QEAAXPEAV1@@Z; CBSSEntry::RemoveIncomingLinkFromNeighborAP(CBSSEntry *)
0x1400508ac  jmp     short loc_140050917
0x1400508ae  test    r15b, r15b
0x1400508b1  jz      loc_140050975
0x1400508b7  mov     rax, [r12]
0x1400508bb  xor     r9d, r9d
0x1400508be  mov     r8, r14
0x1400508c1  mov     rdx, rdi
0x1400508c4  mov     rcx, r12
0x1400508c7  mov     rax, [rax+8]
0x1400508cb  call    _guard_dispatch_icall
0x1400508d0  test    eax, eax
0x1400508d2  jz      loc_140050975
0x1400508d8  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400508df  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400508e6  jz      short loc_140050956
0x1400508e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400508ef  lea     rax, [r14+1BCh]
0x1400508f6  mov     qword ptr [rsp+88h+var_50], rax
0x1400508fb  mov     r9d, 8Fh
0x140050901  mov     [rsp+88h+var_58], rsi
0x140050906  mov     dword ptr [rsp+88h+var_60], ebp
0x14005090a  mov     rcx, [rcx+40h]
0x14005090e  call    WPP_RECORDER_SF_D_MAC__MAC_
0x140050913  jmp     short loc_140050956
0x140050915  mov     ebx, eax
0x140050917  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14005091e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140050925  jz      short loc_140050956
0x140050927  mov     rcx, cs:WPP_GLOBAL_Control
0x14005092e  lea     rax, [r14+1BCh]
0x140050935  mov     qword ptr [rsp+88h+var_50], rax
0x14005093a  mov     r9d, 90h
0x140050940  mov     [rsp+88h+var_58], rsi
0x140050945  mov     dword ptr [rsp+88h+var_60], ebp
0x140050949  mov     rcx, [rcx+40h]
0x14005094d  call    WPP_RECORDER_SF_D_MAC__MAC_
0x140050952  test    ebx, ebx
0x140050954  jz      short loc_140050975
0x140050956  test    rdi, rdi
0x140050959  jz      short loc_140050975
0x14005095b  test    r15b, r15b
0x14005095e  jz      short loc_140050975
0x140050960  mov     rax, [rdi]
0x140050963  mov     edx, 1
0x140050968  mov     rcx, rdi
0x14005096b  mov     rax, [rax]
0x14005096e  call    _guard_dispatch_icall
0x140050973  xor     edi, edi
0x140050975  mov     rbx, [rsp+88h+arg_0]
0x14005097d  mov     rax, rdi
0x140050980  add     rsp, 50h
0x140050984  pop     r15
0x140050986  pop     r14
0x140050988  pop     r13
0x14005098a  pop     r12
0x14005098c  pop     rdi
0x14005098d  pop     rsi
0x14005098e  pop     rbp
0x14005098f  retn
```
