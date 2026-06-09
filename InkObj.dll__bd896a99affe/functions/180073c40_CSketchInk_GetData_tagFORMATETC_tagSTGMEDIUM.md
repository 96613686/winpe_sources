# CSketchInk::GetData(tagFORMATETC *,tagSTGMEDIUM *)

- ea: `0x180073c40`
- end: `0x180073d97`
- name: `?GetData@CSketchInk@@UEAAJPEAUtagFORMATETC@@PEAUtagSTGMEDIUM@@@Z`
- size: `343`
- prototype: `__int64 __fastcall(CSketchInk *__hidden this, struct tagFORMATETC *, struct tagSTGMEDIUM *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18005eba0`
- `0x1800731f8`
- `0x180073c14`
- `0x180073c40`
- `0x18010c010`

## import_xrefs

- `USER32!RegisterClipboardFormatW` at `0x180073c8f`
- `USER32!RegisterClipboardFormatW` at `0x180073d59`
- `USER32!RegisterClipboardFormatW` at `0x180073c8f`
- `USER32!RegisterClipboardFormatW` at `0x180073d59`
- `ole32!WriteClassStg` at `0x180073d11`
- `ole32!WriteClassStg` at `0x180073d11`
- `ole32!CreateILockBytesOnHGlobal` at `0x180073cc4`
- `ole32!CreateILockBytesOnHGlobal` at `0x180073cc4`
- `ole32!StgCreateDocfileOnILockBytes` at `0x180073ce0`
- `ole32!StgCreateDocfileOnILockBytes` at `0x180073ce0`

## string_xrefs

- `0x180073d52`: `Object Descriptor`

## pseudocode

```c
HRESULT __fastcall CSketchInk::GetData(CSketchInk *this, struct tagFORMATETC *a2, struct tagSTGMEDIUM *a3)
{
  DWORD v6; // edx
  HRESULT result; // eax
  int cfFormat; // ebx
  HRESULT v9; // ebx
  IStorage *Descriptor; // rbx
  int v11; // ebx
  unsigned int v12; // edx
  LPLOCKBYTES pplkbyt; // [rsp+48h] [rbp+10h] BYREF
  IStorage *ppstgOpen; // [rsp+58h] [rbp+20h] BYREF

  if ( !a2 || !a3 )
    return -2147467261;
  v6 = a2->tymed - 1;
  if ( v6 )
  {
    if ( v6 != 7 )
      return ATL::IDataObjectImpl<CSketchInk>::GetData(this, a2);
    cfFormat = a2->cfFormat;
    if ( cfFormat == RegisterClipboardFormatW(L"Embed Source") && a2->dwAspect == 1 )
    {
      pplkbyt = 0;
      ppstgOpen = 0;
      if ( CreateILockBytesOnHGlobal(0, 1, &pplkbyt) >= 0 )
      {
        v9 = StgCreateDocfileOnILockBytes(pplkbyt, 0x1012u, 0, &ppstgOpen);
        ((void (__fastcall *)(LPLOCKBYTES))pplkbyt->lpVtbl->Release)(pplkbyt);
        if ( v9 >= 0 )
        {
          Descriptor = ppstgOpen;
          if ( ppstgOpen )
          {
            result = WriteClassStg(ppstgOpen, &CLSID_SketchInk);
            if ( result < 0 )
              return result;
            ATL::IPersistStorageImpl<CSketchInk>::Save((char *)this - 16, Descriptor, 0);
            ((void (__fastcall *)(IStorage *, _QWORD))Descriptor->lpVtbl->Commit)(Descriptor, 0);
            goto LABEL_13;
          }
        }
      }
      return -2147418113;
    }
    return -2147221399;
  }
  v11 = a2->cfFormat;
  if ( v11 != RegisterClipboardFormatW(L"Object Descriptor") )
    return -2147221399;
  Descriptor = (IStorage *)CSketchInk::CreateDescriptor((CSketchInk *)((char *)this - 256), v12);
  if ( Descriptor )
  {
LABEL_13:
    a3->hBitmap = (HBITMAP)Descriptor;
    a3->tymed = a2->tymed;
    return 0;
  }
  return -2147467259;
}

```

## disassembly

```asm
0x180073c40  mov     [rsp+arg_0], rbx
0x180073c45  push    rbp
0x180073c46  push    rsi
0x180073c47  push    rdi
0x180073c48  sub     rsp, 20h
0x180073c4c  mov     rsi, r8
0x180073c4f  mov     rdi, rdx
0x180073c52  mov     rbp, rcx
0x180073c55  test    rdx, rdx
0x180073c58  jz      loc_180073D85
0x180073c5e  test    r8, r8
0x180073c61  jz      loc_180073D85
0x180073c67  mov     edx, [rdx+18h]
0x180073c6a  sub     edx, 1
0x180073c6d  jz      loc_180073D4F
0x180073c73  cmp     edx, 7
0x180073c76  jz      short loc_180073C85
0x180073c78  mov     rdx, rdi
0x180073c7b  call    ?GetData@?$IDataObjectImpl@VCSketchInk@@@ATL@@UEAAJPEAUtagFORMATETC@@PEAUtagSTGMEDIUM@@@Z; ATL::IDataObjectImpl<CSketchInk>::GetData(tagFORMATETC *,tagSTGMEDIUM *)
0x180073c80  jmp     loc_180073D8A
0x180073c85  movzx   ebx, word ptr [rdi]
0x180073c88  lea     rcx, aEmbedSource; "Embed Source"
0x180073c8f  call    cs:__imp_RegisterClipboardFormatW
0x180073c95  cmp     ebx, eax
0x180073c97  jnz     loc_180073D63
0x180073c9d  mov     edx, 1; fDeleteOnRelease
0x180073ca2  cmp     [rdi+10h], edx
0x180073ca5  jnz     loc_180073D63
0x180073cab  lea     r8, [rsp+38h+pplkbyt]; pplkbyt
0x180073cb0  mov     [rsp+38h+pplkbyt], 0
0x180073cb9  xor     ecx, ecx; hGlobal
0x180073cbb  mov     [rsp+38h+ppstgOpen], 0
0x180073cc4  call    cs:__imp_CreateILockBytesOnHGlobal
0x180073cca  test    eax, eax
0x180073ccc  js      short loc_180073D48
0x180073cce  mov     rcx, [rsp+38h+pplkbyt]; plkbyt
0x180073cd3  lea     r9, [rsp+38h+ppstgOpen]; ppstgOpen
0x180073cd8  xor     r8d, r8d; reserved
0x180073cdb  mov     edx, 1012h; grfMode
0x180073ce0  call    cs:__imp_StgCreateDocfileOnILockBytes
0x180073ce6  mov     rcx, [rsp+38h+pplkbyt]
0x180073ceb  mov     ebx, eax
0x180073ced  mov     rdx, [rcx]
0x180073cf0  mov     rax, [rdx+10h]
0x180073cf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073cf9  test    ebx, ebx
0x180073cfb  js      short loc_180073D48
0x180073cfd  mov     rbx, [rsp+38h+ppstgOpen]
0x180073d02  test    rbx, rbx
0x180073d05  jz      short loc_180073D48
0x180073d07  lea     rdx, CLSID_SketchInk; rclsid
0x180073d0e  mov     rcx, rbx; pStg
0x180073d11  call    cs:__imp_WriteClassStg
0x180073d17  test    eax, eax
0x180073d19  js      short loc_180073D8A
0x180073d1b  lea     rcx, [rbp-10h]
0x180073d1f  xor     r8d, r8d
0x180073d22  mov     rdx, rbx
0x180073d25  call    ?Save@?$IPersistStorageImpl@VCSketchInk@@@ATL@@UEAAJPEAUIStorage@@H@Z; ATL::IPersistStorageImpl<CSketchInk>::Save(IStorage *,int)
0x180073d2a  mov     rax, [rbx]
0x180073d2d  xor     edx, edx
0x180073d2f  mov     rcx, rbx
0x180073d32  mov     rax, [rax+48h]
0x180073d36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073d3b  mov     [rsi+8], rbx
0x180073d3f  mov     eax, [rdi+18h]
0x180073d42  mov     [rsi], eax
0x180073d44  xor     eax, eax
0x180073d46  jmp     short loc_180073D8A
0x180073d48  mov     eax, 8000FFFFh
0x180073d4d  jmp     short loc_180073D8A
0x180073d4f  movzx   ebx, word ptr [rdi]
0x180073d52  lea     rcx, aObjectDescript; "Object Descriptor"
0x180073d59  call    cs:__imp_RegisterClipboardFormatW
0x180073d5f  cmp     ebx, eax
0x180073d61  jz      short loc_180073D6A
0x180073d63  mov     eax, 80040069h
0x180073d68  jmp     short loc_180073D8A
0x180073d6a  lea     rcx, [rbp-100h]; this
0x180073d71  call    ?CreateDescriptor@CSketchInk@@IEAAPEAXK@Z; CSketchInk::CreateDescriptor(ulong)
0x180073d76  mov     rbx, rax
0x180073d79  test    rax, rax
0x180073d7c  jnz     short loc_180073D3B
0x180073d7e  mov     eax, 80004005h
0x180073d83  jmp     short loc_180073D8A
0x180073d85  mov     eax, 80004003h
0x180073d8a  mov     rbx, [rsp+38h+arg_0]
0x180073d8f  add     rsp, 20h
0x180073d93  pop     rdi
0x180073d94  pop     rsi
0x180073d95  pop     rbp
0x180073d96  retn
```
