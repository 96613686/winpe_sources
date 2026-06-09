# CSMBHelperClass::GetRepairInfo(tagPROBLEM_TYPE,ulong *,tagRepairInfo * *)

- ea: `0x180005830`
- end: `0x1800058b9`
- name: `?GetRepairInfo@CSMBHelperClass@@UEAAJW4tagPROBLEM_TYPE@@PEAKPEAPEAUtagRepairInfo@@@Z`
- size: `137`
- prototype: `__int64 __fastcall(CSMBHelperClass *this, enum tagPROBLEM_TYPE, unsigned int *, struct tagRepairInfo **)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x180005830`
- `0x18000c990`
- `0x18000d750`
- `0x18000dd04`
- `0x18000f624`

## pseudocode

```c
__int64 __fastcall CSMBHelperClass::GetRepairInfo(
        CSMBHelperClass *this,
        enum tagPROBLEM_TYPE a2,
        unsigned int *a3,
        struct tagRepairInfo **a4)
{
  struct AttributeList *v7; // rbx
  __int64 Attribute; // rax
  struct RootCause *RootCause; // rax
  int v11; // [rsp+20h] [rbp-68h] BYREF
  _BYTE v12[24]; // [rsp+28h] [rbp-60h] BYREF
  _BYTE v13[72]; // [rsp+40h] [rbp-48h] BYREF

  v7 = (CSMBHelperClass *)((char *)this + 208);
  if ( !(unsigned int)AttributeList::attributeExists((CSMBHelperClass *)((char *)this + 208), L"RootCause") )
    return 2147500037LL;
  try
  {
    Attribute = AttributeList::getAttribute(v7, v12, L"RootCause", 2);
    RootCause = RootCauseList::getRootCause((CSMBHelperClass *)((char *)this + 184), *(_DWORD *)(Attribute + 8));
    NDFAdapter::ConvertRepairsToNDF(RootCause, v7, a4, a3);
  }
  catch ( TestException v11 )
  {
    if ( !v11 )
      return 2147942414LL;
    return 2147500037LL;
  }
  catch ( exception v13 )
  {
    exception::~exception((exception *)v13);
    return 2147500037LL;
  }
  Attribute = AttributeList::getAttribute(v7, v12, L"RootCause", 2);
}

```

## disassembly

```asm
0x180005830  push    rbx
0x180005832  push    rsi
0x180005833  push    rdi
0x180005834  push    r14
0x180005836  sub     rsp, 68h
0x18000583a  mov     rsi, r9
0x18000583d  mov     r14, r8
0x180005840  mov     rdi, rcx
0x180005843  lea     rbx, [rcx+0D0h]
0x18000584a  lea     rdx, aRootcause; "RootCause"
0x180005851  mov     rcx, rbx; this
0x180005854  call    ?attributeExists@AttributeList@@QEAAHPEAG@Z; AttributeList::attributeExists(ushort *)
0x180005859  test    eax, eax
0x18000585b  jz      short loc_1800058AA
0x18000585d  mov     r9d, 2
0x180005863  lea     r8, aRootcause; "RootCause"
0x18000586a  lea     rdx, [rsp+88h+var_60]
0x18000586f  mov     rcx, rbx
0x180005872  call    ?getAttribute@AttributeList@@QEAA?AUAttribute@@PEAGW4AttributeType@@@Z; AttributeList::getAttribute(ushort *,AttributeType)
0x180005877  lea     rcx, [rdi+0B8h]; this
0x18000587e  mov     edx, [rax+8]; unsigned int
0x180005881  call    ?getRootCause@RootCauseList@@QEAAPEAVRootCause@@K@Z; RootCauseList::getRootCause(ulong)
0x180005886  mov     r9, r14; unsigned int *
0x180005889  mov     r8, rsi; struct tagRepairInfo **
0x18000588c  mov     rdx, rbx; struct AttributeList *
0x18000588f  mov     rcx, rax; struct RootCause *
0x180005892  call    ?ConvertRepairsToNDF@NDFAdapter@@SAXPEAVRootCause@@PEAVAttributeList@@PEAPEAUtagRepairInfo@@PEAK@Z; NDFAdapter::ConvertRepairsToNDF(RootCause *,AttributeList *,tagRepairInfo * *,ulong *)
0x180005897  nop
0x180005898  xor     eax, eax
0x18000589a  jmp     short loc_1800058AF
0x18000589c  mov     eax, 8007000Eh
0x1800058a1  jmp     short loc_1800058A8
0x1800058a3  mov     eax, 80004005h
0x1800058a8  jmp     short loc_1800058AF
0x1800058aa  mov     eax, 80004005h
0x1800058af  add     rsp, 68h
0x1800058b3  pop     r14
0x1800058b5  pop     rdi
0x1800058b6  pop     rsi
0x1800058b7  pop     rbx
0x1800058b8  retn
```
