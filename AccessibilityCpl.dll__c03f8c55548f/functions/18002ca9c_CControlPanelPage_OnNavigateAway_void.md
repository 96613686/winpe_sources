# CControlPanelPage::OnNavigateAway(void)

- ea: `0x18002ca9c`
- end: `0x18002cac5`
- name: `?OnNavigateAway@CControlPanelPage@@UEAAJXZ`
- size: `41`
- prototype: `__int64 __fastcall(CControlPanelPage *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18001c7c0`

## callees

- `0x18002ca9c`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_ProfferService` at `0x18002cab8`
- `SHLWAPI!__imp_IUnknown_ProfferService` at `0x18002cab8`

## pseudocode

```c
__int64 __fastcall CControlPanelPage::OnNavigateAway(CControlPanelPage *this)
{
  if ( *((_DWORD *)this + 2) )
    IUnknown_ProfferService(*((_QWORD *)this - 1), &IID_IShellSearchTargetServices, 0, (char *)this + 8);
  return 0;
}

```

## disassembly

```asm
0x18002ca9c  sub     rsp, 28h
0x18002caa0  lea     r9, [rcx+8]
0x18002caa4  cmp     dword ptr [r9], 0
0x18002caa8  jz      short loc_18002CABE
0x18002caaa  mov     rcx, [rcx-8]
0x18002caae  lea     rdx, IID_IShellSearchTargetServices
0x18002cab5  xor     r8d, r8d
0x18002cab8  call    cs:__imp_IUnknown_ProfferService
0x18002cabe  xor     eax, eax
0x18002cac0  add     rsp, 28h
0x18002cac4  retn
```
