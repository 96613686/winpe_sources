# HubPage::BringUpHelpPane(void)

- ea: `0x18001caf8`
- end: `0x18001cb70`
- name: `?BringUpHelpPane@HubPage@@AEAAXXZ`
- size: `120`
- prototype: `void __fastcall(HubPage *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001d190`
- `0x18001d280`

## callees

- `0x180005fec`
- `0x18000659c`
- `0x18001caf8`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001cb2d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001cb2d`

## pseudocode

```c
void __fastcall HubPage::BringUpHelpPane(HubPage *this)
{
  HRESULT v2; // eax
  unsigned int v3; // edx
  LPVOID ppv; // [rsp+48h] [rbp+10h] BYREF

  FireHelpEntryDataPoint((const unsigned __int16 *)this);
  ppv = 0;
  v2 = CoCreateInstance(
         &GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee,
         0,
         1u,
         &GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee,
         &ppv);
  if ( v2 < 0 )
  {
    v3 = 6006;
  }
  else
  {
    v2 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *))(*(_QWORD *)ppv + 24LL))(
           ppv,
           L"mshelp://windows/?id=106e6689-2545-4d29-8821-f0c22259a63a");
    if ( v2 >= 0 )
      return;
    v3 = 6005;
  }
  AccessibilityCplCore::ErrorMessage(this, v3, v2);
}

```

## disassembly

```asm
0x18001caf8  push    rbx
0x18001cafa  sub     rsp, 30h
0x18001cafe  mov     rbx, rcx
0x18001cb01  call    ?FireHelpEntryDataPoint@@YAXPEBG@Z; FireHelpEntryDataPoint(ushort const *)
0x18001cb06  xor     edx, edx; pUnkOuter
0x18001cb08  mov     [rsp+38h+arg_8], 0
0x18001cb11  lea     rax, [rsp+38h+arg_8]
0x18001cb16  lea     r9, _GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee; riid
0x18001cb1d  mov     [rsp+38h+ppv], rax; ppv
0x18001cb22  lea     rcx, _GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee; rclsid
0x18001cb29  lea     r8d, [rdx+1]; dwClsContext
0x18001cb2d  call    cs:__imp_CoCreateInstance
0x18001cb33  test    eax, eax
0x18001cb35  js      short loc_18001CB5A
0x18001cb37  mov     rcx, [rsp+38h+arg_8]
0x18001cb3c  lea     rdx, aMshelpWindowsI; "mshelp://windows/?id=106e6689-2545-4d29"...
0x18001cb43  mov     rax, [rcx]
0x18001cb46  mov     rax, [rax+18h]
0x18001cb4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb4f  test    eax, eax
0x18001cb51  jns     short loc_18001CB6A
0x18001cb53  mov     edx, 1775h
0x18001cb58  jmp     short loc_18001CB5F
0x18001cb5a  mov     edx, 1776h; unsigned int
0x18001cb5f  mov     r8d, eax; int
0x18001cb62  mov     rcx, rbx; this
0x18001cb65  call    ?ErrorMessage@AccessibilityCplCore@@AEAAXIJ@Z; AccessibilityCplCore::ErrorMessage(uint,long)
0x18001cb6a  add     rsp, 30h
0x18001cb6e  pop     rbx
0x18001cb6f  retn
```
