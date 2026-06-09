# AccessibilityCplCore::EnableDesktopATOnLogonAT(DirectUI::Element *)

- ea: `0x180005cdc`
- end: `0x180005e52`
- name: `?EnableDesktopATOnLogonAT@AccessibilityCplCore@@AEAAJPEAVElement@DirectUI@@@Z`
- size: `374`
- prototype: `__int64 __fastcall(AccessibilityCplCore *__hidden this, struct DirectUI::Element *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800134a0`

## callees

- `0x180005534`
- `0x180005cdc`
- `0x180015780`
- `0x18002d1fa`
- `0x18002e010`

## import_xrefs

- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x180005d95`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x180005d95`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x180005dfe`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x180005dfe`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x180005da3`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x180005da3`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x180005de0`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x180005de0`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x180005e0f`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x180005e0f`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x180005e1e`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x180005e2a`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x180005e1e`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x180005e2a`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x180005e35`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x180005e35`
- `DUI70!GetElementDataEntry` at `0x180005cfc`
- `DUI70!GetElementDataEntry` at `0x180005cfc`
- `DUI70!StrToID` at `0x180005df0`
- `DUI70!StrToID` at `0x180005df0`

## pseudocode

```c
__int64 __fastcall AccessibilityCplCore::EnableDesktopATOnLogonAT(
        AccessibilityCplCore *this,
        struct DirectUI::Element *a2)
{
  __int64 ElementDataEntry; // rax
  _QWORD *v4; // rax
  wchar_t *v5; // r15
  const wchar_t *v6; // rbx
  struct DirectUI::Element *Parent; // rax
  _DWORD *Children; // r14
  __int64 i; // rsi
  _QWORD *v10; // rdi
  DirectUI::Element *v11; // rdi
  unsigned __int16 ID; // bx
  bool v13; // dl
  AccessibilityCplCore *v15; // [rsp+60h] [rbp+8h] BYREF

  v15 = this;
  if ( a2 )
  {
    ElementDataEntry = GetElementDataEntry(a2);
    if ( ElementDataEntry )
    {
      v4 = (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)ElementDataEntry + 16LL))(ElementDataEntry);
      if ( v4 )
      {
        v5 = (wchar_t *)ATL::CSimpleStringT<unsigned short,0>::CloneData(*v4 - 24LL);
        v6 = v5 + 12;
        if ( !wcscmp_0(v5 + 12, L"stickykeys")
          || !wcscmp_0(v6, L"filterkeys")
          || !wcscmp_0(v6, L"mousekeys")
          || !wcscmp_0(v6, L"togglekeys") )
        {
          v15 = 0;
          Parent = DirectUI::Element::GetParent(a2);
          Children = (_DWORD *)DirectUI::Element::GetChildren(Parent, &v15);
          if ( Children )
          {
            for ( i = 0; (unsigned int)i < (*Children & 0xFFFFFFFu); i = (unsigned int)(i + 1) )
            {
              v10 = Children + 2;
              if ( (*Children & 0x10000000) != 0 )
                v10 = (_QWORD *)*v10;
              v11 = (DirectUI::Element *)v10[i];
              if ( v11 )
              {
                ID = DirectUI::Element::GetID(v11);
                if ( ID == (unsigned __int16)StrToID(L"DesktopAT") && DirectUI::Element::GetVisible(v11) )
                {
                  if ( DirectUI::Element::GetSelected(a2) )
                  {
                    DirectUI::Element::SetSelected(v11, 1);
                    v13 = 0;
                  }
                  else
                  {
                    DirectUI::Element::SetSelected(v11, 0);
                    v13 = 1;
                  }
                  DirectUI::Element::SetEnabled(v11, v13);
                  break;
                }
              }
            }
          }
        }
        ATL::CStringData::Release((ATL::CStringData *)v5);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180005cdc  mov     [rsp+arg_0], rcx
0x180005ce1  push    rbx
0x180005ce2  push    rbp
0x180005ce3  push    rsi
0x180005ce4  push    rdi
0x180005ce5  push    r14
0x180005ce7  push    r15
0x180005ce9  sub     rsp, 28h
0x180005ced  mov     rbp, rdx
0x180005cf0  test    rdx, rdx
0x180005cf3  jz      loc_180005E43
0x180005cf9  mov     rcx, rdx
0x180005cfc  call    cs:__imp_GetElementDataEntry
0x180005d02  mov     r8, rax
0x180005d05  test    rax, rax
0x180005d08  jz      loc_180005E43
0x180005d0e  mov     rcx, [rax]
0x180005d11  mov     rax, [rcx+10h]
0x180005d15  mov     rcx, r8
0x180005d18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d1d  test    rax, rax
0x180005d20  jz      loc_180005E43
0x180005d26  mov     rcx, [rax]
0x180005d29  sub     rcx, 18h
0x180005d2d  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180005d32  lea     rdx, aStickykeys; "stickykeys"
0x180005d39  mov     r15, rax
0x180005d3c  lea     rbx, [rax+18h]
0x180005d40  mov     rcx, rbx; String1
0x180005d43  call    wcscmp_0
0x180005d48  test    eax, eax
0x180005d4a  jz      short loc_180005D89
0x180005d4c  lea     rdx, aFilterkeys; "filterkeys"
0x180005d53  mov     rcx, rbx; String1
0x180005d56  call    wcscmp_0
0x180005d5b  test    eax, eax
0x180005d5d  jz      short loc_180005D89
0x180005d5f  lea     rdx, aMousekeys; "mousekeys"
0x180005d66  mov     rcx, rbx; String1
0x180005d69  call    wcscmp_0
0x180005d6e  test    eax, eax
0x180005d70  jz      short loc_180005D89
0x180005d72  lea     rdx, aTogglekeys; "togglekeys"
0x180005d79  mov     rcx, rbx; String1
0x180005d7c  call    wcscmp_0
0x180005d81  test    eax, eax
0x180005d83  jnz     loc_180005E3B
0x180005d89  mov     rcx, rbp
0x180005d8c  mov     [rsp+58h+arg_0], 0
0x180005d95  call    cs:__imp_?GetParent@Element@DirectUI@@QEAAPEAV12@XZ; DirectUI::Element::GetParent(void)
0x180005d9b  mov     rcx, rax
0x180005d9e  lea     rdx, [rsp+58h+arg_0]
0x180005da3  call    cs:__imp_?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z; DirectUI::Element::GetChildren(DirectUI::Value * *)
0x180005da9  mov     r14, rax
0x180005dac  test    rax, rax
0x180005daf  jz      loc_180005E3B
0x180005db5  xor     esi, esi
0x180005db7  mov     ecx, [r14]
0x180005dba  and     ecx, 0FFFFFFFh
0x180005dc0  cmp     esi, ecx
0x180005dc2  jnb     short loc_180005E3B
0x180005dc4  test    dword ptr [r14], 10000000h
0x180005dcb  lea     rdi, [r14+8]
0x180005dcf  jz      short loc_180005DD4
0x180005dd1  mov     rdi, [rdi]
0x180005dd4  mov     rdi, [rdi+rsi*8]
0x180005dd8  test    rdi, rdi
0x180005ddb  jz      short loc_180005E08
0x180005ddd  mov     rcx, rdi
0x180005de0  call    cs:__imp_?GetID@Element@DirectUI@@QEAAGXZ; DirectUI::Element::GetID(void)
0x180005de6  lea     rcx, aDesktopat; "DesktopAT"
0x180005ded  movzx   ebx, ax
0x180005df0  call    cs:__imp_StrToID
0x180005df6  cmp     bx, ax
0x180005df9  jnz     short loc_180005E08
0x180005dfb  mov     rcx, rdi
0x180005dfe  call    cs:__imp_?GetVisible@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetVisible(void)
0x180005e04  test    al, al
0x180005e06  jnz     short loc_180005E0C
0x180005e08  inc     esi
0x180005e0a  jmp     short loc_180005DB7
0x180005e0c  mov     rcx, rbp
0x180005e0f  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x180005e15  mov     rcx, rdi
0x180005e18  test    al, al
0x180005e1a  jz      short loc_180005E28
0x180005e1c  mov     dl, 1
0x180005e1e  call    cs:__imp_?SetSelected@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetSelected(bool)
0x180005e24  xor     edx, edx
0x180005e26  jmp     short loc_180005E32
0x180005e28  xor     edx, edx
0x180005e2a  call    cs:__imp_?SetSelected@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetSelected(bool)
0x180005e30  mov     dl, 1
0x180005e32  mov     rcx, rdi
0x180005e35  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x180005e3b  mov     rcx, r15; this
0x180005e3e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180005e43  xor     eax, eax
0x180005e45  add     rsp, 28h
0x180005e49  pop     r15
0x180005e4b  pop     r14
0x180005e4d  pop     rdi
0x180005e4e  pop     rsi
0x180005e4f  pop     rbp
0x180005e50  pop     rbx
0x180005e51  retn
```
