# sub_1800BBD2C

- ea: `0x1800bbd2c`
- end: `0x1800bbddf`
- name: `sub_1800BBD2C`
- size: `179`
- prototype: `__int64 __fastcall(LPSTREAM *ppstm, HPTPROVIDER hProvider)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800bb6a0`

## callees

- `0x180018910`
- `0x18001f878`
- `0x18002b7f8`
- `0x1800bbd2c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800bbd5d`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800bbd5d`
- `ext-ms-win-printer-prntvpt-l1-1-2!PTGetPrintDeviceCapabilities` at `0x1800bbd8e`
- `ext-ms-win-printer-prntvpt-l1-1-2!PTGetPrintDeviceCapabilities` at `0x1800bbd8e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPSTREAM *__fastcall sub_1800BBD2C(LPSTREAM *ppstm, HPTPROVIDER hProvider)
{
  HRESULT StreamOnHGlobal; // eax
  HRESULT v5; // eax
  _UNKNOWN *retaddr; // [rsp+38h] [rbp+0h]
  BSTR pbstrErrorMessage; // [rsp+50h] [rbp+18h] BYREF

  *ppstm = 0;
  StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, ppstm);
  if ( StreamOnHGlobal < 0 )
    sub_180018910(
      (int)retaddr,
      93,
      (int)"onecoreuap\\printscan\\Print\\Workflow\\inc\\PrintTicketUtils.h",
      StreamOnHGlobal);
  pbstrErrorMessage = 0;
  sub_18002B7F8((void **)&pbstrErrorMessage, 0);
  v5 = PTGetPrintDeviceCapabilities(hProvider, 0, *ppstm, &pbstrErrorMessage);
  if ( v5 < 0 )
    sub_180018910((int)retaddr, 95, (int)"onecoreuap\\printscan\\Print\\Workflow\\inc\\PrintTicketUtils.h", v5);
  Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam((void **)&pbstrErrorMessage);
  return ppstm;
}

```

## disassembly

```asm
0x1800bbd2c  mov     rax, rsp
0x1800bbd2f  mov     [rax+10h], rbx
0x1800bbd33  mov     [rax+8], rcx
0x1800bbd37  push    rdi
0x1800bbd38  sub     rsp, 30h
0x1800bbd3c  mov     rdi, rdx
0x1800bbd3f  mov     rbx, rcx
0x1800bbd42  mov     dword ptr [rax-18h], 0
0x1800bbd49  mov     qword ptr [rcx], 0
0x1800bbd50  mov     edx, 1; fDeleteOnRelease
0x1800bbd55  mov     [rax-18h], edx
0x1800bbd58  mov     r8, rcx; ppstm
0x1800bbd5b  xor     ecx, ecx; hGlobal
0x1800bbd5d  call    cs:CreateStreamOnHGlobal
0x1800bbd63  mov     rcx, [rsp+38h]
0x1800bbd68  test    eax, eax
0x1800bbd6a  js      short loc_1800BBDCA
0x1800bbd6c  mov     [rsp+38h+pbstrErrorMessage], 0
0x1800bbd75  xor     edx, edx
0x1800bbd77  lea     rcx, [rsp+38h+pbstrErrorMessage]
0x1800bbd7c  call    sub_18002B7F8
0x1800bbd81  lea     r9, [rsp+38h+pbstrErrorMessage]; pbstrErrorMessage
0x1800bbd86  mov     r8, [rbx]; pDeviceCapabilities
0x1800bbd89  xor     edx, edx; pPrintTicket
0x1800bbd8b  mov     rcx, rdi; hProvider
0x1800bbd8e  call    cs:PTGetPrintDeviceCapabilities
0x1800bbd94  mov     rcx, [rsp+38h]
0x1800bbd99  test    eax, eax
0x1800bbd9b  js      short loc_1800BBDB5
0x1800bbd9d  lea     rcx, [rsp+38h+pbstrErrorMessage]; this
0x1800bbda2  call    ??1InitialThreadParam@UMSFreeVirtualProcessorRoot@details@Concurrency@@QEAA@XZ_3; Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(void)
0x1800bbda7  mov     rax, rbx
0x1800bbdaa  mov     rbx, [rsp+38h+arg_8]
0x1800bbdaf  add     rsp, 30h
0x1800bbdb3  pop     rdi
0x1800bbdb4  retn
0x1800bbdb5  mov     r9d, eax
0x1800bbdb8  lea     r8, aOnecoreuapPrin_73; "onecoreuap\\printscan\\Print\\Workflow"...
0x1800bbdbf  mov     edx, 5Fh ; '_'
0x1800bbdc4  call    sub_180018910
0x1800bbdca  mov     r9d, eax
0x1800bbdcd  lea     r8, aOnecoreuapPrin_73; "onecoreuap\\printscan\\Print\\Workflow"...
0x1800bbdd4  mov     edx, 5Dh ; ']'
0x1800bbdd9  call    sub_180018910
```
