# XmlObjBase::ReadFromFile(ushort const *)

- ea: `0x180039244`
- end: `0x1800392c3`
- name: `?ReadFromFile@XmlObjBase@@QEAAJPEBG@Z`
- size: `127`
- prototype: `__int64 __fastcall(XmlObjBase *__hidden this, LPCWSTR pszFile)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800218a8`

## callees

- `0x180024ffc`
- `0x180039244`
- `0x180040a04`
- `0x18008c010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18003926f`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18003926f`

## pseudocode

```c
__int64 __fastcall XmlObjBase::ReadFromFile(XmlObjBase *this, LPCWSTR pszFile)
{
  HRESULT v3; // ebx
  IUnknown *pInputStream; // [rsp+50h] [rbp+18h] BYREF

  pInputStream = 0;
  v3 = SHCreateStreamOnFileW(pszFile, 0, (IStream **)&pInputStream);
  if ( v3 >= 0 )
  {
    v3 = XmlObjBase::ReadFromStream(this, pInputStream, 0);
    if ( v3 >= 0 )
      v3 = 0;
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&pInputStream);
  }
  else if ( pInputStream )
  {
    ((void (__fastcall *)(IUnknown *, struct IUnknownVtbl *))pInputStream->lpVtbl->Release)(
      pInputStream,
      pInputStream->lpVtbl);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180039244  mov     r11, rsp
0x180039247  push    rdi
0x180039248  sub     rsp, 30h
0x18003924c  mov     qword ptr [r11-18h], 0FFFFFFFFFFFFFFFEh
0x180039254  mov     [r11+8], rbx
0x180039258  mov     rax, rdx
0x18003925b  mov     rdi, rcx
0x18003925e  mov     qword ptr [r11+18h], 0
0x180039266  lea     r8, [r11+18h]; ppstm
0x18003926a  xor     edx, edx; grfMode
0x18003926c  mov     rcx, rax; pszFile
0x18003926f  call    cs:__imp_SHCreateStreamOnFileW
0x180039275  mov     ebx, eax
0x180039277  test    eax, eax
0x180039279  jns     short loc_180039294
0x18003927b  mov     rcx, [rsp+38h+pInputStream]
0x180039280  test    rcx, rcx
0x180039283  jz      short loc_180039292
0x180039285  mov     rdx, [rcx]
0x180039288  mov     rax, [rdx+10h]
0x18003928c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039291  nop
0x180039292  jmp     short loc_1800392B6
0x180039294  xor     r8d, r8d; bool
0x180039297  mov     rdx, [rsp+38h+pInputStream]; pInputStream
0x18003929c  mov     rcx, rdi; this
0x18003929f  call    ?ReadFromStream@XmlObjBase@@QEAAJPEAUIStream@@_N@Z; XmlObjBase::ReadFromStream(IStream *,bool)
0x1800392a4  mov     ebx, eax
0x1800392a6  test    eax, eax
0x1800392a8  js      short loc_1800392AC
0x1800392aa  xor     ebx, ebx
0x1800392ac  lea     rcx, [rsp+38h+pInputStream]
0x1800392b1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800392b6  mov     eax, ebx
0x1800392b8  mov     rbx, [rsp+38h+arg_0]
0x1800392bd  add     rsp, 30h
0x1800392c1  pop     rdi
0x1800392c2  retn
```
