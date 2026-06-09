# HubPage::VoicingActions(DirectUI::Event *)

- ea: `0x18001df2c`
- end: `0x18001dfce`
- name: `?VoicingActions@HubPage@@AEAAXPEAUEvent@DirectUI@@@Z`
- size: `162`
- prototype: `void __fastcall(HubPage *__hidden this, struct DirectUI::Event *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001d190`

## callees

- `0x1800055c0`
- `0x180014828`
- `0x180018260`
- `0x18001d978`
- `0x18001df2c`
- `0x180029c04`

## import_xrefs

- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x18001df7a`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x18001df7a`

## string_xrefs

- `0x18001df67`: `Software\Microsoft\Ease of Access`

## pseudocode

```c
void __fastcall HubPage::VoicingActions(HubPage *this, DirectUI::Element **a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  unsigned __int16 *v6; // r9
  HKEY v7[5]; // [rsp+20h] [rbp-28h] BYREF

  memset(v7, 0, 24);
  if ( !(unsigned int)ATL::CRegKey::Open(
                        (ATL::CRegKey *)v7,
                        HKEY_CURRENT_USER,
                        L"Software\\Microsoft\\Ease of Access",
                        0x2001Fu) )
  {
    if ( DirectUI::Element::GetSelected(*a2) )
    {
      ATL::CRegKey::SetDWORDValue(v7, L"selfvoice", 1);
      HubPage::SetUpSelfVoicing(this, v4, v5, v6);
    }
    else
    {
      ATL::CRegKey::SetDWORDValue(v7, L"selfvoice", 0);
      DuiVoice::Off((HubPage *)((char *)this + 264));
    }
  }
  ATL::CRegKey::Close((ATL::CRegKey *)v7);
}

```

## disassembly

```asm
0x18001df2c  mov     rax, rsp
0x18001df2f  mov     [rax+8], rbx
0x18001df33  push    rdi
0x18001df34  sub     rsp, 40h
0x18001df38  mov     rdi, rdx
0x18001df3b  mov     qword ptr [rax-28h], 0
0x18001df43  mov     rbx, rcx
0x18001df46  mov     qword ptr [rax-20h], 0
0x18001df4e  mov     rdx, 0FFFFFFFF80000001h; hKey
0x18001df55  mov     qword ptr [rax-18h], 0
0x18001df5d  lea     rcx, [rax-28h]; this
0x18001df61  mov     r9d, 2001Fh; unsigned int
0x18001df67  lea     r8, aSoftwareMicros_0; "Software\\Microsoft\\Ease of Access"
0x18001df6e  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001df73  test    eax, eax
0x18001df75  jnz     short loc_18001DFB9
0x18001df77  mov     rcx, [rdi]
0x18001df7a  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x18001df80  lea     rdx, aSelfvoice; "selfvoice"
0x18001df87  lea     rcx, [rsp+48h+var_28]; this
0x18001df8c  test    al, al
0x18001df8e  jz      short loc_18001DFA5
0x18001df90  mov     r8d, 1; unsigned int
0x18001df96  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x18001df9b  mov     rcx, rbx; this
0x18001df9e  call    ?SetUpSelfVoicing@HubPage@@AEAAJXZ; HubPage::SetUpSelfVoicing(void)
0x18001dfa3  jmp     short loc_18001DFB9
0x18001dfa5  xor     r8d, r8d; unsigned int
0x18001dfa8  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x18001dfad  lea     rcx, [rbx+108h]; this
0x18001dfb4  call    ?Off@DuiVoice@@QEAAXXZ; DuiVoice::Off(void)
0x18001dfb9  lea     rcx, [rsp+48h+var_28]; this
0x18001dfbe  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001dfc3  mov     rbx, [rsp+48h+arg_0]
0x18001dfc8  add     rsp, 40h
0x18001dfcc  pop     rdi
0x18001dfcd  retn
```
