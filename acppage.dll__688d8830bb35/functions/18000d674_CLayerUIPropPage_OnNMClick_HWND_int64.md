# CLayerUIPropPage::OnNMClick(HWND__ *,__int64)

- ea: `0x18000d674`
- end: `0x18000d6e2`
- name: `?OnNMClick@CLayerUIPropPage@@QEAAXPEAUHWND__@@_J@Z`
- size: `110`
- prototype: `void __fastcall(CLayerUIPropPage *__hidden this, HWND, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000aa90`
- `0x18000c0d0`
- `0x18000cb60`

## callees

- `0x18000d674`

## import_xrefs

- `SHELL32!ShellExecuteW` at `0x18000d6d7`
- `SHELL32!ShellExecuteW` at `0x18000d6d7`

## string_xrefs

- `0x18000d6b3`: `https://go.microsoft.com/fwlink/p/?linkid=839533`
- `0x18000d6aa`: `https://go.microsoft.com/fwlink/?linkid=849812`
- `0x18000d698`: `https://go.microsoft.com/fwlink/?linkid=863197`

## pseudocode

```c
void __fastcall CLayerUIPropPage::OnNMClick(CLayerUIPropPage *this, HWND a2, __int64 a3)
{
  const WCHAR *v3; // r8

  switch ( *(_QWORD *)(a3 + 8) )
  {
    case 0x3E9LL:
      v3 = L"https://go.microsoft.com/fwlink/p/?linkid=839533";
      break;
    case 0x13A8LL:
      v3 = L"https://go.microsoft.com/fwlink/?linkid=849812";
      break;
    case 0x13AALL:
      v3 = L"ms-settings:display-advanced";
      break;
    case 0x13ABLL:
      v3 = L"https://go.microsoft.com/fwlink/?linkid=863197";
      break;
    default:
      return;
  }
  ShellExecuteW(0, L"open", v3, 0, 0, 1);
}

```

## disassembly

```asm
0x18000d674  sub     rsp, 38h
0x18000d678  mov     rax, [r8+8]
0x18000d67c  sub     rax, 3E9h
0x18000d682  jz      short loc_18000D6B3
0x18000d684  sub     rax, 0FBFh
0x18000d68a  jz      short loc_18000D6AA
0x18000d68c  sub     rax, 2
0x18000d690  jz      short loc_18000D6A1
0x18000d692  cmp     rax, 1
0x18000d696  jnz     short loc_18000D6DD
0x18000d698  lea     r8, aHttpsGoMicroso_0; "https://go.microsoft.com/fwlink/?linkid"...
0x18000d69f  jmp     short loc_18000D6BA
0x18000d6a1  lea     r8, aMsSettingsDisp; "ms-settings:display-advanced"
0x18000d6a8  jmp     short loc_18000D6BA
0x18000d6aa  lea     r8, aHttpsGoMicroso_1; "https://go.microsoft.com/fwlink/?linkid"...
0x18000d6b1  jmp     short loc_18000D6BA
0x18000d6b3  lea     r8, File; "https://go.microsoft.com/fwlink/p/?link"...
0x18000d6ba  mov     [rsp+38h+nShowCmd], 1; nShowCmd
0x18000d6c2  lea     rdx, Operation; "open"
0x18000d6c9  xor     r9d, r9d; lpParameters
0x18000d6cc  mov     [rsp+38h+lpDirectory], 0; lpDirectory
0x18000d6d5  xor     ecx, ecx; hwnd
0x18000d6d7  call    cs:__imp_ShellExecuteW
0x18000d6dd  add     rsp, 38h
0x18000d6e1  retn
```
