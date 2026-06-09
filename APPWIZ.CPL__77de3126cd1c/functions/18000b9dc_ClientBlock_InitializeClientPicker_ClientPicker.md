# ClientBlock::InitializeClientPicker(ClientPicker *)

- ea: `0x18000b9dc`
- end: `0x18000bc90`
- name: `?InitializeClientPicker@ClientBlock@@QEAAJPEAVClientPicker@@@Z`
- size: `692`
- prototype: `__int64 __fastcall(ClientBlock *__hidden this, struct ClientPicker *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e3d4`

## callees

- `0x1800089f0`
- `0x180008a88`
- `0x180009380`
- `0x18000b9dc`
- `0x18000bc98`
- `0x18000f908`
- `0x18000f99c`
- `0x18000fa5c`
- `0x18000fb18`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bb6b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bb6b`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18000ba7d`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18000ba7d`
- `DUI70!?Insert@Element@DirectUI@@QEAAJPEAV12@I@Z` at `0x18000bab5`
- `DUI70!?Insert@Element@DirectUI@@QEAAJPEAV12@I@Z` at `0x18000bab5`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x18000ba4f`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x18000ba99`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x18000ba4f`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x18000ba99`
- `DUI70!?GetIndex@Element@DirectUI@@QEAAHXZ` at `0x18000baa5`
- `DUI70!?GetIndex@Element@DirectUI@@QEAAHXZ` at `0x18000baa5`

## pseudocode

```c
__int64 __fastcall ClientBlock::InitializeClientPicker(ClientBlock *this, struct DirectUI::Element **a2)
{
  int v4; // ebp
  __int64 Ancestor; // rbx
  HKEY v6; // r12
  struct DirectUI::Element **v7; // rsi
  DirectUI::Element *Parent; // r15
  DirectUI::Element *v9; // rbx
  int Index; // eax
  unsigned int v11; // ebx
  _DWORD *v12; // rcx
  int v13; // edx
  _QWORD *v14; // rcx
  const struct CLIENTINFO *v15; // r15
  int FilterShowAdd; // ecx
  int v17; // ecx
  const unsigned __int16 *v18; // rdx
  ClientBlock *v19; // rcx
  ClientBlock **v20; // rbx
  int v21; // ecx
  int v22; // ecx
  struct DirectUI::Element *v23; // rcx
  _DWORD *v24; // rax
  _QWORD *v25; // r8
  _QWORD *v26; // r8
  _DWORD *v27; // rax
  _QWORD *v28; // r8
  struct DirectUI::Element *v29; // rdx
  _DWORD *v30; // rax
  _QWORD *v31; // r8
  ClientBlock *v32; // rcx
  char v34; // [rsp+68h] [rbp+10h] BYREF

  v4 = 0;
  Ancestor = FindAncestorElement<ARPFrame>();
  v6 = ClientBlock::_OpenClientKey(this, HKEY_LOCAL_MACHINE, 131097, 0);
  if ( !v6 )
  {
    v6 = ClientBlock::_OpenClientKey(this, HKEY_LOCAL_MACHINE, 131097, 1u);
    if ( !v6 )
    {
      v7 = a2 + 32;
      goto LABEL_20;
    }
  }
  v7 = a2 + 32;
  Parent = DirectUI::Element::GetParent((DirectUI::Element *)a2);
  if ( (int)DirectUI::DUIXmlParser::CreateElement(
              *(DirectUI::DUIXmlParser **)(Ancestor + 280),
              L"oemclientshowhide",
              0,
              Parent,
              0,
              a2 + 32) >= 0 )
  {
    TraverseTree<DirectUI::Button>(*v7, (int (*)(struct DirectUI::Element *, __int64))FixDUIButtonAccessibilityCB);
    v9 = DirectUI::Element::GetParent(Parent);
    Index = DirectUI::Element::GetIndex(Parent);
    DirectUI::Element::Insert(v9, *v7, Index + 1);
  }
  v11 = 2;
  do
  {
    v12 = (_DWORD *)*((_QWORD *)this + 25);
    v13 = *v12;
    if ( v11 >= (*v12 & 0xFFFFFFFu) )
      break;
    v14 = v12 + 2;
    if ( (v13 & 0x10000000) != 0 )
      v14 = (_QWORD *)*v14;
    v34 = 0;
    v15 = (const struct CLIENTINFO *)v14[v11];
    FilterShowAdd = ClientBlock::_GetFilterShowAdd(this, v15, a2, &v34);
    if ( !*v7 )
      goto LABEL_16;
    v17 = FilterShowAdd - 1;
    if ( !v17 )
    {
      v18 = L"show";
      goto LABEL_15;
    }
    if ( v17 == 1 )
    {
      v18 = L"hide";
LABEL_15:
      ClientPicker::AddClientToOEMRow((ClientPicker *)a2, v18, v15);
      *((_BYTE *)a2 + 209) = 0;
    }
LABEL_16:
    if ( v34 )
    {
      v4 = DirectUI::DynamicArrayBase<CLIENTINFO *,DirectUI::DoubleAllocationPolicy<CLIENTINFO *>,1,0>::Insert(
             a2[28],
             *(_DWORD *)a2[28] & 0xFFFFFFF,
             v15);
      *((_BYTE *)a2 + 209) = 0;
    }
    ++v11;
  }
  while ( v4 >= 0 );
  RegCloseKey(v6);
  if ( v4 >= 0 )
  {
LABEL_20:
    v20 = a2 + 28;
    v21 = *((_DWORD *)a2 + 51);
    if ( v21 )
    {
      v22 = v21 - 1;
      if ( v22 )
      {
        if ( v22 == 1 )
        {
          v20 = a2 + 28;
          v23 = a2[28];
          if ( (*(_DWORD *)v23 & 0xFFFFFFFu) > 1 )
          {
            v24 = (_DWORD *)*((_QWORD *)this + 25);
            v25 = v24 + 2;
            if ( (*v24 & 0x10000000) != 0 )
              v25 = (_QWORD *)*v25;
            v26 = (_QWORD *)*v25;
            goto LABEL_27;
          }
        }
      }
      else if ( ClientBlock::_IsCurrentClientNonWindowsMS(this) )
      {
        v27 = (_DWORD *)*((_QWORD *)this + 25);
        v28 = v27 + 2;
        if ( (*v27 & 0x10000000) != 0 )
          v28 = (_QWORD *)*v28;
        v26 = (_QWORD *)v28[1];
        v23 = a2[28];
LABEL_27:
        v4 = DirectUI::DynamicArrayBase<CLIENTINFO *,DirectUI::DoubleAllocationPolicy<CLIENTINFO *>,1,0>::Insert(
               v23,
               0,
               v26);
      }
    }
    else
    {
      v20 = a2 + 28;
      v29 = a2[28];
      if ( (*(_DWORD *)v29 & 0xFFFFFFF) != 1 )
        *(_DWORD *)v29 &= 0xF0000000;
    }
    v19 = *v20;
    if ( (*(_DWORD *)*v20 & 0xFFFFFFF) == 0 )
    {
      v30 = (_DWORD *)*((_QWORD *)this + 25);
      v31 = v30 + 2;
      if ( (*v30 & 0x10000000) != 0 )
        v31 = (_QWORD *)*v31;
      v4 = DirectUI::DynamicArrayBase<CLIENTINFO *,DirectUI::DoubleAllocationPolicy<CLIENTINFO *>,1,0>::Insert(
             v19,
             0,
             v31[1]);
    }
  }
  if ( *v7 )
  {
    ClientBlock::_RemoveEmptyOEMRow(v19, *v7, L"show");
    ClientBlock::_RemoveEmptyOEMRow(v32, *v7, L"hide");
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000b9dc  mov     [rsp+arg_0], rbx
0x18000b9e1  mov     [rsp+arg_10], rbp
0x18000b9e6  push    rsi
0x18000b9e7  push    rdi
0x18000b9e8  push    r12
0x18000b9ea  push    r14
0x18000b9ec  push    r15
0x18000b9ee  sub     rsp, 30h
0x18000b9f2  mov     rdi, rdx
0x18000b9f5  mov     r14, rcx
0x18000b9f8  xor     ebp, ebp
0x18000b9fa  call    ??$FindAncestorElement@VARPFrame@@@@YAPEAVARPFrame@@PEAVElement@DirectUI@@@Z; FindAncestorElement<ARPFrame>(DirectUI::Element *)
0x18000b9ff  mov     esi, 20019h
0x18000ba04  mov     r15, 0FFFFFFFF80000002h
0x18000ba0b  mov     r8d, esi; unsigned int
0x18000ba0e  mov     rdx, r15; HKEY
0x18000ba11  xor     r9d, r9d; bool
0x18000ba14  mov     rcx, r14; this
0x18000ba17  mov     rbx, rax
0x18000ba1a  call    ?_OpenClientKey@ClientBlock@@AEAAPEAUHKEY__@@PEAU2@K_N@Z; ClientBlock::_OpenClientKey(HKEY__ *,ulong,bool)
0x18000ba1f  mov     r12, rax
0x18000ba22  test    rax, rax
0x18000ba25  jnz     short loc_18000BA4C
0x18000ba27  mov     r9b, 1; bool
0x18000ba2a  mov     r8d, esi; unsigned int
0x18000ba2d  mov     rdx, r15; HKEY
0x18000ba30  mov     rcx, r14; this
0x18000ba33  call    ?_OpenClientKey@ClientBlock@@AEAAPEAUHKEY__@@PEAU2@K_N@Z; ClientBlock::_OpenClientKey(HKEY__ *,ulong,bool)
0x18000ba38  mov     r12, rax
0x18000ba3b  test    rax, rax
0x18000ba3e  jnz     short loc_18000BA4C
0x18000ba40  lea     rsi, [rdi+100h]
0x18000ba47  jmp     loc_18000BB79
0x18000ba4c  mov     rcx, rdi
0x18000ba4f  call    cs:__imp_?GetParent@Element@DirectUI@@QEAAPEAV12@XZ; DirectUI::Element::GetParent(void)
0x18000ba55  mov     rcx, [rbx+118h]
0x18000ba5c  lea     rsi, [rdi+100h]
0x18000ba63  mov     [rsp+58h+var_30], rsi
0x18000ba68  lea     rdx, aOemclientshowh; "oemclientshowhide"
0x18000ba6f  mov     r9, rax
0x18000ba72  mov     [rsp+58h+var_38], rbp
0x18000ba77  xor     r8d, r8d
0x18000ba7a  mov     r15, rax
0x18000ba7d  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x18000ba83  test    eax, eax
0x18000ba85  js      short loc_18000BABB
0x18000ba87  mov     rcx, [rsi]; struct DirectUI::Element *
0x18000ba8a  lea     rdx, ?FixDUIButtonAccessibilityCB@@YAJPEAVButton@DirectUI@@_J@Z; int (*)(struct DirectUI::Element *, __int64)
0x18000ba91  call    ??$TraverseTree@VButton@DirectUI@@@@YAJPEAVElement@DirectUI@@P6AJPEAVButton@1@_J@Z2@Z; TraverseTree<DirectUI::Button>(DirectUI::Element *,long (*)(DirectUI::Button *,__int64),__int64)
0x18000ba96  mov     rcx, r15
0x18000ba99  call    cs:__imp_?GetParent@Element@DirectUI@@QEAAPEAV12@XZ; DirectUI::Element::GetParent(void)
0x18000ba9f  mov     rcx, r15
0x18000baa2  mov     rbx, rax
0x18000baa5  call    cs:__imp_?GetIndex@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetIndex(void)
0x18000baab  mov     rdx, [rsi]
0x18000baae  mov     rcx, rbx
0x18000bab1  lea     r8d, [rax+1]
0x18000bab5  call    cs:__imp_?Insert@Element@DirectUI@@QEAAJPEAV12@I@Z; DirectUI::Element::Insert(DirectUI::Element *,uint)
0x18000babb  mov     ebx, 2
0x18000bac0  mov     rcx, [r14+0C8h]
0x18000bac7  mov     edx, [rcx]
0x18000bac9  mov     eax, edx
0x18000bacb  and     eax, 0FFFFFFFh
0x18000bad0  cmp     ebx, eax
0x18000bad2  jnb     loc_18000BB68
0x18000bad8  add     rcx, 8
0x18000badc  bt      edx, 1Ch
0x18000bae0  jnb     short loc_18000BAE5
0x18000bae2  mov     rcx, [rcx]
0x18000bae5  mov     eax, ebx
0x18000bae7  lea     r9, [rsp+58h+arg_8]
0x18000baec  mov     r8, rdi
0x18000baef  mov     [rsp+58h+arg_8], 0
0x18000baf4  mov     r15, [rcx+rax*8]
0x18000baf8  mov     rcx, r14
0x18000bafb  mov     rdx, r15
0x18000bafe  call    ?_GetFilterShowAdd@ClientBlock@@AEAA?AW4TRIBIT@@PEAVCLIENTINFO@@PEAVClientPicker@@PEA_N@Z; ClientBlock::_GetFilterShowAdd(CLIENTINFO *,ClientPicker *,bool *)
0x18000bb03  cmp     qword ptr [rsi], 0
0x18000bb07  mov     ecx, eax
0x18000bb09  jz      short loc_18000BB37
0x18000bb0b  sub     ecx, 1
0x18000bb0e  jz      short loc_18000BB1E
0x18000bb10  cmp     ecx, 1
0x18000bb13  jnz     short loc_18000BB37
0x18000bb15  lea     rdx, aHide; "hide"
0x18000bb1c  jmp     short loc_18000BB25
0x18000bb1e  lea     rdx, aShow; "show"
0x18000bb25  mov     r8, r15; struct CLIENTINFO *
0x18000bb28  mov     rcx, rdi; this
0x18000bb2b  call    ?AddClientToOEMRow@ClientPicker@@QEAAXPEBGPEBVCLIENTINFO@@@Z; ClientPicker::AddClientToOEMRow(ushort const *,CLIENTINFO const *)
0x18000bb30  mov     byte ptr [rdi+0D1h], 0
0x18000bb37  cmp     [rsp+58h+arg_8], 0
0x18000bb3c  jz      short loc_18000BB5E
0x18000bb3e  mov     rcx, [rdi+0E0h]
0x18000bb45  mov     r8, r15
0x18000bb48  mov     edx, [rcx]
0x18000bb4a  and     edx, 0FFFFFFFh
0x18000bb50  call    ?Insert@?$DynamicArrayBase@PEAVCLIENTINFO@@V?$DoubleAllocationPolicy@PEAVCLIENTINFO@@@DirectUI@@$00$0A@@DirectUI@@QEAAJIPEAVCLIENTINFO@@@Z; DirectUI::DynamicArrayBase<CLIENTINFO *,DirectUI::DoubleAllocationPolicy<CLIENTINFO *>,1,0>::Insert(uint,CLIENTINFO *)
0x18000bb55  mov     ebp, eax
0x18000bb57  mov     byte ptr [rdi+0D1h], 0
0x18000bb5e  inc     ebx
0x18000bb60  test    ebp, ebp
0x18000bb62  jns     loc_18000BAC0
0x18000bb68  mov     rcx, r12; hKey
0x18000bb6b  call    cs:__imp_RegCloseKey
0x18000bb71  test    ebp, ebp
0x18000bb73  js      loc_18000BC54
0x18000bb79  mov     rcx, rdi
0x18000bb7c  mov     eax, 0E0h
0x18000bb81  lea     rbx, [rcx+rax]
0x18000bb85  mov     ecx, [rdi+0CCh]
0x18000bb8b  test    ecx, ecx
0x18000bb8d  jz      short loc_18000BC06
0x18000bb8f  sub     ecx, 1
0x18000bb92  jz      short loc_18000BBD7
0x18000bb94  cmp     ecx, 1
0x18000bb97  jnz     loc_18000BC26
0x18000bb9d  lea     rbx, [rdi+0E0h]
0x18000bba4  mov     rcx, [rbx]
0x18000bba7  mov     eax, [rcx]
0x18000bba9  and     eax, 0FFFFFFFh
0x18000bbae  cmp     eax, 1
0x18000bbb1  jbe     short loc_18000BC26
0x18000bbb3  mov     rax, [r14+0C8h]
0x18000bbba  test    dword ptr [rax], 10000000h
0x18000bbc0  lea     r8, [rax+8]
0x18000bbc4  jz      short loc_18000BBC9
0x18000bbc6  mov     r8, [r8]
0x18000bbc9  mov     r8, [r8]
0x18000bbcc  xor     edx, edx
0x18000bbce  call    ?Insert@?$DynamicArrayBase@PEAVCLIENTINFO@@V?$DoubleAllocationPolicy@PEAVCLIENTINFO@@@DirectUI@@$00$0A@@DirectUI@@QEAAJIPEAVCLIENTINFO@@@Z; DirectUI::DynamicArrayBase<CLIENTINFO *,DirectUI::DoubleAllocationPolicy<CLIENTINFO *>,1,0>::Insert(uint,CLIENTINFO *)
0x18000bbd3  mov     ebp, eax
0x18000bbd5  jmp     short loc_18000BC26
0x18000bbd7  mov     rcx, r14; this
0x18000bbda  call    ?_IsCurrentClientNonWindowsMS@ClientBlock@@AEAA_NXZ; ClientBlock::_IsCurrentClientNonWindowsMS(void)
0x18000bbdf  test    al, al
0x18000bbe1  jz      short loc_18000BC26
0x18000bbe3  mov     rax, [r14+0C8h]
0x18000bbea  test    dword ptr [rax], 10000000h
0x18000bbf0  lea     r8, [rax+8]
0x18000bbf4  jz      short loc_18000BBF9
0x18000bbf6  mov     r8, [r8]
0x18000bbf9  mov     r8, [r8+8]
0x18000bbfd  mov     rcx, [rdi+0E0h]
0x18000bc04  jmp     short loc_18000BBCC
0x18000bc06  lea     rbx, [rdi+0E0h]
0x18000bc0d  mov     rdx, [rbx]
0x18000bc10  mov     ecx, [rdx]
0x18000bc12  mov     eax, ecx
0x18000bc14  and     eax, 0FFFFFFFh
0x18000bc19  cmp     eax, 1
0x18000bc1c  jz      short loc_18000BC26
0x18000bc1e  and     ecx, 0F0000000h
0x18000bc24  mov     [rdx], ecx
0x18000bc26  mov     rcx, [rbx]
0x18000bc29  test    dword ptr [rcx], 0FFFFFFFh
0x18000bc2f  jnz     short loc_18000BC54
0x18000bc31  mov     rax, [r14+0C8h]
0x18000bc38  test    dword ptr [rax], 10000000h
0x18000bc3e  lea     r8, [rax+8]
0x18000bc42  jz      short loc_18000BC47
0x18000bc44  mov     r8, [r8]
0x18000bc47  mov     r8, [r8+8]
0x18000bc4b  xor     edx, edx
0x18000bc4d  call    ?Insert@?$DynamicArrayBase@PEAVCLIENTINFO@@V?$DoubleAllocationPolicy@PEAVCLIENTINFO@@@DirectUI@@$00$0A@@DirectUI@@QEAAJIPEAVCLIENTINFO@@@Z; DirectUI::DynamicArrayBase<CLIENTINFO *,DirectUI::DoubleAllocationPolicy<CLIENTINFO *>,1,0>::Insert(uint,CLIENTINFO *)
0x18000bc52  mov     ebp, eax
0x18000bc54  mov     rdx, [rsi]; struct DirectUI::Element *
0x18000bc57  test    rdx, rdx
0x18000bc5a  jz      short loc_18000BC77
0x18000bc5c  lea     r8, aShow; "show"
0x18000bc63  call    ?_RemoveEmptyOEMRow@ClientBlock@@AEAAXPEAVElement@DirectUI@@PEBG@Z; ClientBlock::_RemoveEmptyOEMRow(DirectUI::Element *,ushort const *)
0x18000bc68  mov     rdx, [rsi]; struct DirectUI::Element *
0x18000bc6b  lea     r8, aHide; "hide"
0x18000bc72  call    ?_RemoveEmptyOEMRow@ClientBlock@@AEAAXPEAVElement@DirectUI@@PEBG@Z; ClientBlock::_RemoveEmptyOEMRow(DirectUI::Element *,ushort const *)
0x18000bc77  mov     rbx, [rsp+58h+arg_0]
0x18000bc7c  mov     eax, ebp
0x18000bc7e  mov     rbp, [rsp+58h+arg_10]
0x18000bc83  add     rsp, 30h
0x18000bc87  pop     r15
0x18000bc89  pop     r14
0x18000bc8b  pop     r12
0x18000bc8d  pop     rdi
0x18000bc8e  pop     rsi
0x18000bc8f  retn
```
