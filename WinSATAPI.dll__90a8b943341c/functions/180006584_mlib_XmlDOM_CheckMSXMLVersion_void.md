# mlib::XmlDOM::CheckMSXMLVersion(void)

- ea: `0x180006584`
- end: `0x18000660c`
- name: `?CheckMSXMLVersion@XmlDOM@mlib@@SA_NXZ`
- size: `136`
- prototype: `bool(void)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180001640`
- `0x180004c60`
- `0x18000e68c`

## callees

- `0x180006584`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x1800065b6`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x1800065b6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool mlib::XmlDOM::CheckMSXMLVersion(void)
{
  HRESULT ClassObject; // ebx
  bool v1; // bl
  LPVOID v3; // [rsp+50h] [rbp+8h] BYREF

  v3 = 0;
  ClassObject = CoGetClassObject(
                  &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
                  1u,
                  0,
                  &GUID_00000001_0000_0000_c000_000000000046,
                  &v3);
  if ( ClassObject >= 0 )
  {
    mlib::XmlDOM::clsIDDocument = GUID_88d96a05_f192_11d4_a65f_0040963251e5;
    mlib::XmlDOM::clsIDSchema = GUID_88d96a07_f192_11d4_a65f_0040963251e5;
  }
  v1 = ClassObject >= 0;
  if ( v3 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v3 + 16LL))(v3);
  return v1;
}

```

## disassembly

```asm
0x180006584  mov     r11, rsp
0x180006587  push    rbx
0x180006588  sub     rsp, 40h
0x18000658c  mov     qword ptr [r11-18h], 0FFFFFFFFFFFFFFFEh
0x180006594  and     qword ptr [r11+8], 0
0x180006599  lea     rax, [r11+8]
0x18000659d  mov     [r11-28h], rax
0x1800065a1  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x1800065a8  xor     r8d, r8d; pvReserved
0x1800065ab  lea     edx, [r8+1]; dwClsContext
0x1800065af  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x1800065b6  call    cs:__imp_CoGetClassObject
0x1800065bd  nop     dword ptr [rax+rax+00h]
0x1800065c2  mov     ebx, eax
0x1800065c4  test    eax, eax
0x1800065c6  js      short loc_1800065E6
0x1800065c8  movups  xmm0, xmmword ptr cs:_GUID_88d96a05_f192_11d4_a65f_0040963251e5.Data1
0x1800065cf  movdqu  xmmword ptr cs:?clsIDDocument@XmlDOM@mlib@@0U_GUID@@A.Data1, xmm0; _GUID mlib::XmlDOM::clsIDDocument ...
0x1800065d7  movups  xmm1, xmmword ptr cs:_GUID_88d96a07_f192_11d4_a65f_0040963251e5.Data1
0x1800065de  movdqu  xmmword ptr cs:?clsIDSchema@XmlDOM@mlib@@0U_GUID@@A.Data1, xmm1; _GUID mlib::XmlDOM::clsIDSchema ...
0x1800065e6  shr     ebx, 1Fh
0x1800065e9  xor     bl, 1
0x1800065ec  mov     rcx, [rsp+48h+arg_0]
0x1800065f1  test    rcx, rcx
0x1800065f4  jz      short loc_180006603
0x1800065f6  mov     rax, [rcx]
0x1800065f9  mov     rax, [rax+10h]
0x1800065fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006602  nop
0x180006603  mov     al, bl
0x180006605  add     rsp, 40h
0x180006609  pop     rbx
0x18000660a  retn
```
