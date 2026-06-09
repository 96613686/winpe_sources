# ImageView_Fullscreen

- ea: `0x180077780`
- end: `0x18007783b`
- name: `ImageView_Fullscreen`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180044d60`

## callees

- `0x1800456f8`
- `0x1800770b8`
- `0x180077238`
- `0x180077368`
- `0x180077780`
- `0x180077844`
- `0x180080010`

## import_xrefs

- `ole32!OleUninitialize` at `0x180077821`
- `ole32!OleUninitialize` at `0x180077821`
- `SHELL32!__imp_SHILCreateFromPath` at `0x1800777d5`
- `SHELL32!__imp_SHILCreateFromPath` at `0x1800777d5`
- `SHELL32!__imp_ILFree` at `0x1800777f2`
- `SHELL32!__imp_ILFree` at `0x1800777f2`

## pseudocode

```c
void __fastcall ImageView_Fullscreen(ITEMIDLIST *a1, __int64 a2, const WCHAR *a3, int a4)
{
  __int64 v5; // rdx
  __int64 v6; // r8
  int v7; // ebx
  __int64 v8; // [rsp+20h] [rbp-10h] BYREF
  LPITEMIDLIST ppidl; // [rsp+40h] [rbp+10h] BYREF
  int v10; // [rsp+48h] [rbp+18h] BYREF
  int v11; // [rsp+4Ch] [rbp+1Ch]
  int v12; // [rsp+58h] [rbp+28h] BYREF

  v12 = a4;
  v11 = HIDWORD(a2);
  ppidl = a1;
  v10 = -2147467259;
  if ( (int)ComHelpers::CCoInit::Initialize((ComHelpers::CCoInit *)&v10) >= 0 )
  {
    SmartOleInit::SmartOleInit((SmartOleInit *)&v12);
    v8 = 0;
    ppidl = 0;
    if ( SHILCreateFromPath(a3, &ppidl, 0) >= 0 )
    {
      v7 = SHGetUIObjectFromFullPIDL(ppidl, v5, v6, &v8);
      ILFree(ppidl);
      if ( v7 >= 0 )
      {
        InvokePhotoViewerVerb(v8, 0, 3u);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      }
    }
    if ( (_BYTE)v12 )
      OleUninitialize();
  }
  ComHelpers::CCoInit::~CCoInit((ComHelpers::CCoInit *)&v10);
}

```

## disassembly

```asm
0x180077780  mov     rax, rsp
0x180077783  mov     [rax+18h], rbx
0x180077787  mov     [rax+20h], r9d
0x18007778b  mov     [rax+10h], rdx
0x18007778f  mov     [rax+8], rcx
0x180077793  push    rbp
0x180077794  mov     rbp, rsp
0x180077797  sub     rsp, 30h
0x18007779b  lea     rcx, [rbp+arg_8]; this
0x18007779f  mov     [rbp+arg_8], 80004005h
0x1800777a6  mov     rbx, r8
0x1800777a9  call    ?Initialize@CCoInit@ComHelpers@@QEAAJXZ; ComHelpers::CCoInit::Initialize(void)
0x1800777ae  test    eax, eax
0x1800777b0  js      short loc_180077827
0x1800777b2  lea     rcx, [rbp+arg_18]; this
0x1800777b6  call    ??0SmartOleInit@@QEAA@XZ; SmartOleInit::SmartOleInit(void)
0x1800777bb  xor     r8d, r8d; rgfInOut
0x1800777be  mov     [rbp+var_10], 0
0x1800777c6  lea     rdx, [rbp+ppidl]; ppidl
0x1800777ca  mov     [rbp+ppidl], 0
0x1800777d2  mov     rcx, rbx; pszPath
0x1800777d5  call    cs:__imp_SHILCreateFromPath
0x1800777db  test    eax, eax
0x1800777dd  js      short loc_18007781B
0x1800777df  mov     rcx, [rbp+ppidl]
0x1800777e3  lea     r9, [rbp+var_10]
0x1800777e7  call    SHGetUIObjectFromFullPIDL
0x1800777ec  mov     rcx, [rbp+ppidl]; pidl
0x1800777f0  mov     ebx, eax
0x1800777f2  call    cs:__imp_ILFree
0x1800777f8  test    ebx, ebx
0x1800777fa  js      short loc_18007781B
0x1800777fc  mov     rcx, [rbp+var_10]
0x180077800  xor     edx, edx
0x180077802  lea     r8d, [rdx+3]
0x180077806  call    ?InvokePhotoViewerVerb@@YAJPEAUIDataObject@@PEAUIUnknown@@W4VERB_TYPE@@@Z; InvokePhotoViewerVerb(IDataObject *,IUnknown *,VERB_TYPE)
0x18007780b  mov     rcx, [rbp+var_10]
0x18007780f  mov     rax, [rcx]
0x180077812  mov     rax, [rax+10h]
0x180077816  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007781b  cmp     byte ptr [rbp+arg_18], 0
0x18007781f  jz      short loc_180077827
0x180077821  call    cs:__imp_OleUninitialize
0x180077827  lea     rcx, [rbp+arg_8]; this
0x18007782b  call    ??1CCoInit@ComHelpers@@QEAA@XZ; ComHelpers::CCoInit::~CCoInit(void)
0x180077830  mov     rbx, [rsp+30h+arg_10]
0x180077835  add     rsp, 30h
0x180077839  pop     rbp
0x18007783a  retn
```
