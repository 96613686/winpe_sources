# HubPage::ScanningActions(DirectUI::Event *)

- ea: `0x18001d62c`
- end: `0x18001d6d4`
- name: `?ScanningActions@HubPage@@AEAAXPEAUEvent@DirectUI@@@Z`
- size: `168`
- prototype: `void __fastcall(HubPage *__hidden this, struct DirectUI::Event *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001d190`

## callees

- `0x1800055c0`
- `0x180014828`
- `0x180018260`
- `0x18001d62c`
- `0x18001d6dc`

## import_xrefs

- `USER32!KillTimer` at `0x18001d6b9`
- `USER32!KillTimer` at `0x18001d6b9`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x18001d67a`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x18001d67a`

## string_xrefs

- `0x18001d667`: `Software\Microsoft\Ease of Access`

## pseudocode

```c
void __fastcall HubPage::ScanningActions(HWND *this, DirectUI::Element **a2)
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
      ATL::CRegKey::SetDWORDValue(v7, L"selfscan", 1);
      HubPage::SetUpScanning((HubPage *)this, v4, v5, v6);
    }
    else
    {
      ATL::CRegKey::SetDWORDValue(v7, L"selfscan", 0);
      KillTimer(this[41], 0x123u);
    }
  }
  ATL::CRegKey::Close((ATL::CRegKey *)v7);
}

```

## disassembly

```asm
0x18001d62c  mov     rax, rsp
0x18001d62f  mov     [rax+8], rbx
0x18001d633  push    rdi
0x18001d634  sub     rsp, 40h
0x18001d638  mov     rdi, rdx
0x18001d63b  mov     qword ptr [rax-28h], 0
0x18001d643  mov     rbx, rcx
0x18001d646  mov     qword ptr [rax-20h], 0
0x18001d64e  mov     rdx, 0FFFFFFFF80000001h; hKey
0x18001d655  mov     qword ptr [rax-18h], 0
0x18001d65d  lea     rcx, [rax-28h]; this
0x18001d661  mov     r9d, 2001Fh; unsigned int
0x18001d667  lea     r8, aSoftwareMicros_0; "Software\\Microsoft\\Ease of Access"
0x18001d66e  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001d673  test    eax, eax
0x18001d675  jnz     short loc_18001D6BF
0x18001d677  mov     rcx, [rdi]
0x18001d67a  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x18001d680  lea     rdx, aSelfscan; "selfscan"
0x18001d687  lea     rcx, [rsp+48h+var_28]; this
0x18001d68c  test    al, al
0x18001d68e  jz      short loc_18001D6A5
0x18001d690  mov     r8d, 1; unsigned int
0x18001d696  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x18001d69b  mov     rcx, rbx; this
0x18001d69e  call    ?SetUpScanning@HubPage@@AEAAJXZ; HubPage::SetUpScanning(void)
0x18001d6a3  jmp     short loc_18001D6BF
0x18001d6a5  xor     r8d, r8d; unsigned int
0x18001d6a8  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x18001d6ad  mov     rcx, [rbx+148h]; hWnd
0x18001d6b4  mov     edx, 123h; uIDEvent
0x18001d6b9  call    cs:__imp_KillTimer
0x18001d6bf  lea     rcx, [rsp+48h+var_28]; this
0x18001d6c4  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001d6c9  mov     rbx, [rsp+48h+arg_0]
0x18001d6ce  add     rsp, 40h
0x18001d6d2  pop     rdi
0x18001d6d3  retn
```
