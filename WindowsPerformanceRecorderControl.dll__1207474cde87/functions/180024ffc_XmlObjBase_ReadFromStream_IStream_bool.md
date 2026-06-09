# XmlObjBase::ReadFromStream(IStream *,bool)

- ea: `0x180024ffc`
- end: `0x1800251aa`
- name: `?ReadFromStream@XmlObjBase@@QEAAJPEAUIStream@@_N@Z`
- size: `430`
- prototype: `__int64 __fastcall(XmlObjBase *__hidden this, IUnknown *pInputStream, bool)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021a88`
- `0x18002d070`
- `0x180039244`

## callees

- `0x180013940`
- `0x180024ffc`
- `0x1800251b0`
- `0x180040a04`
- `0x18008c010`

## import_xrefs

- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x1800250c8`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x1800250c8`
- `XmlLite!CreateXmlReader` at `0x180025048`
- `XmlLite!CreateXmlReader` at `0x180025048`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall XmlObjBase::ReadFromStream(XmlObjBase *this, IUnknown *pInputStream, char a3)
{
  HRESULT v6; // ebx
  __int64 v7; // rax
  int v8; // eax
  void *ppvObject; // [rsp+30h] [rbp-20h] BYREF
  IXmlReaderInput *ppInput; // [rsp+38h] [rbp-18h] BYREF
  _QWORD v12[2]; // [rsp+40h] [rbp-10h] BYREF
  int v13; // [rsp+88h] [rbp+38h] BYREF

  v12[1] = -2;
  ppvObject = 0;
  v13 = 0;
  v12[0] = 0;
  v6 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  if ( v6 < 0 )
    goto LABEL_23;
  v6 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 4);
  if ( v6 < 0 )
  {
    if ( ppvObject )
      (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)ppvObject + 16LL))(ppvObject, *(_QWORD *)ppvObject);
    return (unsigned int)v6;
  }
  if ( !a3 )
  {
    v8 = (*(__int64 (__fastcall **)(void *, IUnknown *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, pInputStream);
    goto LABEL_14;
  }
  ppInput = 0;
  v6 = CreateXmlReaderInputWithEncodingName(pInputStream, 0, L"UTF-16", 1, &LocaleName, &ppInput);
  if ( v6 < 0
    || (v6 = (*(__int64 (__fastcall **)(void *, IXmlReaderInput *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, ppInput),
        v6 < 0) )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppInput);
LABEL_23:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppvObject);
    return (unsigned int)v6;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppInput);
  while ( 1 )
  {
    v7 = *(_QWORD *)ppvObject;
    if ( v13 == 1 )
      break;
    v8 = (*(__int64 (__fastcall **)(void *, int *))(v7 + 48))(ppvObject, &v13);
LABEL_14:
    if ( v8 < 0 )
      goto LABEL_15;
  }
  v8 = (*(__int64 (__fastcall **)(void *, _QWORD *, _QWORD))(v7 + 112))(ppvObject, v12, 0);
  if ( v8 < 0 )
  {
LABEL_15:
    v6 = v8;
    goto LABEL_23;
  }
  if ( !(unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Compare(
                        (char *)this + 8,
                        v12[0]) )
  {
    v8 = XmlObjBase::Read(this, (struct IXmlReader *)ppvObject);
    if ( v8 >= 0 )
    {
      v6 = 0;
      goto LABEL_23;
    }
    goto LABEL_15;
  }
  if ( ppvObject )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
  return 2147942413LL;
}

```

## disassembly

```asm
0x180024ffc  push    rbp
0x180024ffe  push    rdi
0x180024fff  push    r14
0x180025001  mov     rbp, rsp
0x180025004  sub     rsp, 50h
0x180025008  mov     [rbp+var_8], 0FFFFFFFFFFFFFFFEh
0x180025010  mov     [rsp+50h+arg_0], rbx
0x180025015  mov     [rsp+50h+arg_8], rsi
0x18002501a  mov     dil, r8b
0x18002501d  mov     r14, rdx
0x180025020  mov     rsi, rcx
0x180025023  mov     [rbp+ppvObject], 0
0x18002502b  mov     [rbp+arg_18], 0
0x180025032  mov     [rbp+var_10], 0
0x18002503a  xor     r8d, r8d; pMalloc
0x18002503d  lea     rdx, [rbp+ppvObject]; ppvObject
0x180025041  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x180025048  call    cs:__imp_CreateXmlReader
0x18002504e  mov     ebx, eax
0x180025050  test    eax, eax
0x180025052  js      loc_18002518C
0x180025058  mov     rcx, [rbp+ppvObject]
0x18002505c  mov     rax, [rcx]
0x18002505f  xor     r8d, r8d
0x180025062  lea     edx, [r8+4]
0x180025066  mov     rax, [rax+28h]
0x18002506a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002506f  mov     ebx, eax
0x180025071  test    eax, eax
0x180025073  jns     short loc_180025090
0x180025075  mov     rcx, [rbp+ppvObject]
0x180025079  test    rcx, rcx
0x18002507c  jz      short loc_18002508B
0x18002507e  mov     rdx, [rcx]
0x180025081  mov     rax, [rdx+10h]
0x180025085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002508a  nop
0x18002508b  jmp     loc_180025195
0x180025090  test    dil, dil
0x180025093  jz      loc_18002511C
0x180025099  mov     [rbp+var_18], 0
0x1800250a1  lea     rax, [rbp+var_18]
0x1800250a5  mov     [rsp+50h+ppInput], rax; ppInput
0x1800250aa  lea     rax, LocaleName
0x1800250b1  mov     [rsp+50h+pwszBaseUri], rax; pwszBaseUri
0x1800250b6  mov     r9d, 1; fEncodingHint
0x1800250bc  lea     r8, pwszEncodingName; "UTF-16"
0x1800250c3  xor     edx, edx; pMalloc
0x1800250c5  mov     rcx, r14; pInputStream
0x1800250c8  call    cs:__imp_CreateXmlReaderInputWithEncodingName
0x1800250ce  mov     ebx, eax
0x1800250d0  test    eax, eax
0x1800250d2  jns     short loc_1800250E2
0x1800250d4  lea     rcx, [rbp+var_18]
0x1800250d8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800250dd  jmp     loc_18002518C
0x1800250e2  mov     rcx, [rbp+ppvObject]
0x1800250e6  mov     rax, [rcx]
0x1800250e9  mov     rdx, [rbp+var_18]
0x1800250ed  mov     rax, [rax+18h]
0x1800250f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800250f6  mov     ebx, eax
0x1800250f8  lea     rcx, [rbp+var_18]
0x1800250fc  test    eax, eax
0x1800250fe  js      short loc_1800250D8
0x180025100  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180025105  mov     rcx, [rbp+ppvObject]
0x180025109  mov     rax, [rcx]
0x18002510c  cmp     [rbp+arg_18], 1
0x180025110  jz      short loc_180025137
0x180025112  lea     rdx, [rbp+arg_18]
0x180025116  mov     rax, [rax+30h]
0x18002511a  jmp     short loc_18002512A
0x18002511c  mov     rcx, [rbp+ppvObject]
0x180025120  mov     rax, [rcx]
0x180025123  mov     rdx, r14
0x180025126  mov     rax, [rax+18h]
0x18002512a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002512f  test    eax, eax
0x180025131  jns     short loc_180025105
0x180025133  mov     ebx, eax
0x180025135  jmp     short loc_18002518C
0x180025137  xor     r8d, r8d
0x18002513a  lea     rdx, [rbp+var_10]
0x18002513e  mov     rax, [rax+70h]
0x180025142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025147  test    eax, eax
0x180025149  js      short loc_180025133
0x18002514b  lea     rcx, [rsi+8]
0x18002514f  mov     rdx, [rbp+var_10]
0x180025153  call    ?Compare@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Compare(ushort const *)
0x180025158  nop
0x180025159  test    eax, eax
0x18002515b  jz      short loc_18002517A
0x18002515d  mov     rcx, [rbp+ppvObject]
0x180025161  test    rcx, rcx
0x180025164  jz      short loc_180025173
0x180025166  mov     rax, [rcx]
0x180025169  mov     rax, [rax+10h]
0x18002516d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025172  nop
0x180025173  mov     eax, 8007000Dh
0x180025178  jmp     short loc_180025197
0x18002517a  mov     rdx, [rbp+ppvObject]; struct IXmlReader *
0x18002517e  mov     rcx, rsi; this
0x180025181  call    ?Read@XmlObjBase@@QEAAJPEAUIXmlReader@@@Z; XmlObjBase::Read(IXmlReader *)
0x180025186  test    eax, eax
0x180025188  js      short loc_180025133
0x18002518a  xor     ebx, ebx
0x18002518c  lea     rcx, [rbp+ppvObject]
0x180025190  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180025195  mov     eax, ebx
0x180025197  mov     rbx, [rsp+50h+arg_0]
0x18002519c  mov     rsi, [rsp+50h+arg_8]
0x1800251a1  add     rsp, 50h
0x1800251a5  pop     r14
0x1800251a7  pop     rdi
0x1800251a8  pop     rbp
0x1800251a9  retn
```
