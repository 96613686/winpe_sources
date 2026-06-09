# wistd::unique_ptr<DirectUI::DUIXmlParser,DuiDestroyer<DirectUI::DUIXmlParser>>::~unique_ptr<DirectUI::DUIXmlParser,DuiDestroyer<DirectUI::DUIXmlParser>>(void)

- ea: `0x140007edc`
- end: `0x140007efe`
- name: `??1?$unique_ptr@VDUIXmlParser@DirectUI@@U?$DuiDestroyer@VDUIXmlParser@DirectUI@@@@@wistd@@QEAA@XZ`
- size: `34`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140009914`

## callees

- `0x140007edc`

## import_xrefs

- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x140007ef2`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x140007ef2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wistd::unique_ptr<DirectUI::DUIXmlParser,DuiDestroyer<DirectUI::DUIXmlParser>>::~unique_ptr<DirectUI::DUIXmlParser,DuiDestroyer<DirectUI::DUIXmlParser>>(
        DirectUI::DUIXmlParser **a1)
{
  DirectUI::DUIXmlParser *v1; // rax

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
    DirectUI::DUIXmlParser::Destroy(v1);
}

```

## disassembly

```asm
0x140007edc  sub     rsp, 28h
0x140007ee0  mov     rax, [rcx]
0x140007ee3  mov     qword ptr [rcx], 0
0x140007eea  test    rax, rax
0x140007eed  jz      short loc_140007EF9
0x140007eef  mov     rcx, rax
0x140007ef2  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x140007ef8  nop
0x140007ef9  add     rsp, 28h
0x140007efd  retn
```
