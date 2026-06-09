# CMobileClipboard::SetClipboard(IDataObject *,ushort const *)

- ea: `0x1801f6420`
- end: `0x1801f663f`
- name: `?SetClipboard@CMobileClipboard@@UEAAJPEAUIDataObject@@PEBG@Z`
- size: `543`
- prototype: `__int64 __fastcall(CMobileClipboard *__hidden this, struct IDataObject *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180048d5c`
- `0x1800498d0`
- `0x1800e1204`
- `0x1800e1264`
- `0x1801479e4`
- `0x1801f5a90`
- `0x1801f5dac`
- `0x1801f5f8c`
- `0x1801f6420`
- `0x180205240`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801f654e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801f654e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f649b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f65c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f65d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f649b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f65c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f65d1`

## pseudocode

```c
__int64 __fastcall CMobileClipboard::SetClipboard(
        CMobileClipboard *this,
        struct IDataObject *a2,
        const unsigned __int16 *a3)
{
  unsigned int ClipboardStatics; // ebx
  unsigned int v6; // edi
  __int64 v7; // r14
  struct IDataObjectVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetData)(IDataObject *, FORMATETC *, STGMEDIUM *); // rax
  unsigned int v10; // eax
  __int64 v11; // rcx
  HSTRING v13; // [rsp+20h] [rbp-60h] BYREF
  __int64 v14; // [rsp+28h] [rbp-58h] BYREF
  __int64 v15; // [rsp+30h] [rbp-50h] BYREF
  HSTRING v16; // [rsp+38h] [rbp-48h] BYREF
  struct tagSTGMEDIUM v17; // [rsp+40h] [rbp-40h] BYREF
  __int16 v18; // [rsp+58h] [rbp-28h] BYREF
  int v19; // [rsp+5Ah] [rbp-26h]
  __int16 v20; // [rsp+5Eh] [rbp-22h]
  __int64 v21; // [rsp+60h] [rbp-20h]
  int v22; // [rsp+68h] [rbp-18h]
  int v23; // [rsp+6Ch] [rbp-14h]
  __int64 v24; // [rsp+70h] [rbp-10h]
  HSTRING string; // [rsp+C8h] [rbp+48h] BYREF

  ClipboardStatics = CMobileClipboard::GetClipboardStatics(this);
  v14 = 0;
  if ( !ClipboardStatics )
  {
    ClipboardStatics = OSGetDataPackage(&v14);
    if ( !ClipboardStatics )
    {
      if ( *((_QWORD *)this + 3) )
      {
        ClipboardStatics = 0;
      }
      else
      {
        string = 0;
        ClipboardStatics = Microsoft::WRL::Wrappers::HString::Set(
                             (Microsoft::WRL::Wrappers::HString *)&string,
                             L"Windows.Foundation.PropertyValue",
                             0x20u);
        if ( !ClipboardStatics )
          ClipboardStatics = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(
                               string,
                               (char *)this + 24);
        WindowsDeleteString(string);
      }
    }
  }
  v6 = 0;
  while ( !ClipboardStatics )
  {
    v7 = 2LL * v6;
    v19 = 0;
    v20 = 0;
    v24 = 1;
    v18 = *(_WORD *)((char *)&SupportedFormats + v7 * 8);
    lpVtbl = a2->lpVtbl;
    v22 = 1;
    v23 = -1;
    v21 = 0;
    GetData = lpVtbl->GetData;
    memset(&v17, 0, sizeof(v17));
    ClipboardStatics = ((__int64 (__fastcall *)(struct IDataObject *, __int16 *, struct tagSTGMEDIUM *))GetData)(
                         a2,
                         &v18,
                         &v17);
    if ( ClipboardStatics )
    {
      if ( ClipboardStatics == -2147221404 )
        ClipboardStatics = 0;
    }
    else
    {
      if ( v17.tymed == 1 )
      {
        v16 = 0;
        v13 = 0;
        LODWORD(string) = 0;
        Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&v13, &(&off_18029BE18)[v7]);
        WindowsGetStringRawBuffer(v13, (UINT32 *)&string);
        if ( (_DWORD)string )
        {
          v10 = CW32System::GlobalSize(v17.hBitmap);
          ClipboardStatics = Microsoft::WRL::Wrappers::HString::Set(
                               (Microsoft::WRL::Wrappers::HString *)&v16,
                               v17.lpszFileName,
                               v10 >> 1);
          if ( !ClipboardStatics )
          {
            v11 = *((_QWORD *)this + 3);
            v15 = 0;
            if ( !(*(unsigned int (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v11 + 144LL))(v11, v16, &v15) )
              (*(void (__fastcall **)(__int64, HSTRING, __int64))(*(_QWORD *)v14 + 112LL))(v14, v13, v15);
            Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(&v15);
          }
        }
        WindowsDeleteString(v13);
        v13 = 0;
        WindowsDeleteString(v16);
      }
      CW32System::ReleaseStgMedium(&v17);
    }
    if ( ++v6 >= 3 )
    {
      if ( !ClipboardStatics )
        ClipboardStatics = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 2) + 56LL))(
                             *((_QWORD *)this + 2),
                             v14);
      break;
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
  return ClipboardStatics;
}

```

## disassembly

```asm
0x1801f6420  mov     [rsp-28h+arg_0], rbx
0x1801f6425  mov     [rsp-28h+arg_8], rsi
0x1801f642a  push    rbp
0x1801f642b  push    rdi
0x1801f642c  push    r12
0x1801f642e  push    r14
0x1801f6430  push    r15
0x1801f6432  mov     rbp, rsp
0x1801f6435  sub     rsp, 80h
0x1801f643c  mov     r15, rdx
0x1801f643f  mov     rsi, rcx
0x1801f6442  call    ?GetClipboardStatics@CMobileClipboard@@AEAAJXZ; CMobileClipboard::GetClipboardStatics(void)
0x1801f6447  xor     r12d, r12d
0x1801f644a  mov     ebx, eax
0x1801f644c  mov     [rbp+var_58], r12
0x1801f6450  test    eax, eax
0x1801f6452  jnz     short loc_1801F64A6
0x1801f6454  lea     rcx, [rbp+var_58]
0x1801f6458  call    OSGetDataPackage
0x1801f645d  mov     ebx, eax
0x1801f645f  test    eax, eax
0x1801f6461  jnz     short loc_1801F64A6
0x1801f6463  cmp     [rsi+18h], r12
0x1801f6467  jnz     short loc_1801F64A3
0x1801f6469  lea     r8d, [r12+20h]; unsigned int
0x1801f646e  mov     [rbp+string], r12
0x1801f6472  lea     rdx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x1801f6479  lea     rcx, [rbp+string]; this
0x1801f647d  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x1801f6482  mov     ebx, eax
0x1801f6484  test    eax, eax
0x1801f6486  jnz     short loc_1801F6497
0x1801f6488  mov     rcx, [rbp+string]
0x1801f648c  lea     rdx, [rsi+18h]
0x1801f6490  call    ??$GetActivationFactory@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>)
0x1801f6495  mov     ebx, eax
0x1801f6497  mov     rcx, [rbp+string]; string
0x1801f649b  call    cs:__imp_WindowsDeleteString
0x1801f64a1  jmp     short loc_1801F64A6
0x1801f64a3  mov     ebx, r12d
0x1801f64a6  mov     edi, r12d
0x1801f64a9  lea     rcx, ?SupportedFormats@@3QBUSupportedFormat@@B; SupportedFormat const near * const SupportedFormats
0x1801f64b0  test    ebx, ebx
0x1801f64b2  jnz     loc_1801F6618
0x1801f64b8  xorps   xmm0, xmm0
0x1801f64bb  mov     r14d, edi
0x1801f64be  shl     r14, 4
0x1801f64c2  lea     r8, [rbp+var_40]
0x1801f64c6  lea     rdx, [rbp+var_28]
0x1801f64ca  mov     [rbp+var_26], r12d
0x1801f64ce  mov     [rbp+var_22], r12w
0x1801f64d3  mov     [rbp+var_10], 1
0x1801f64db  movzx   eax, word ptr [r14+rcx]
0x1801f64e0  mov     rcx, r15
0x1801f64e3  mov     [rbp+var_28], ax
0x1801f64e7  xor     eax, eax
0x1801f64e9  mov     [rbp+var_40.pUnkForRelease], rax
0x1801f64ed  mov     rax, [r15]
0x1801f64f0  mov     [rbp+var_18], 1
0x1801f64f7  mov     [rbp+var_14], 0FFFFFFFFh
0x1801f64fe  mov     [rbp+var_20], r12
0x1801f6502  mov     rax, [rax+18h]
0x1801f6506  movups  xmmword ptr [rbp+var_40.tymed], xmm0
0x1801f650a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f650f  mov     ebx, eax
0x1801f6511  test    eax, eax
0x1801f6513  jnz     loc_1801F65E2
0x1801f6519  cmp     [rbp+var_40.tymed], 1
0x1801f651d  jnz     loc_1801F65D7
0x1801f6523  lea     rdx, ?SupportedFormats@@3QBUSupportedFormat@@B; SupportedFormat const near * const SupportedFormats
0x1801f652a  mov     [rbp+var_48], r12
0x1801f652e  add     rdx, 8
0x1801f6532  mov     [rbp+var_60], r12
0x1801f6536  add     rdx, r14
0x1801f6539  mov     dword ptr [rbp+string], r12d
0x1801f653d  lea     rcx, [rbp+var_60]
0x1801f6541  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801f6546  mov     rcx, [rbp+var_60]; string
0x1801f654a  lea     rdx, [rbp+string]; length
0x1801f654e  call    cs:__imp_WindowsGetStringRawBuffer
0x1801f6554  cmp     dword ptr [rbp+string], r12d
0x1801f6558  jz      short loc_1801F65BF
0x1801f655a  mov     rcx, qword ptr [rbp+var_40.8]; void *
0x1801f655e  call    ?GlobalSize@CW32System@@SAKPEAX@Z; CW32System::GlobalSize(void *)
0x1801f6563  mov     rdx, qword ptr [rbp+var_40.8]; unsigned __int16 *
0x1801f6567  lea     rcx, [rbp+var_48]; this
0x1801f656b  shr     eax, 1
0x1801f656d  mov     r8d, eax; unsigned int
0x1801f6570  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x1801f6575  mov     ebx, eax
0x1801f6577  test    eax, eax
0x1801f6579  jnz     short loc_1801F65BF
0x1801f657b  mov     rcx, [rsi+18h]
0x1801f657f  lea     r8, [rbp+var_50]
0x1801f6583  mov     rdx, [rbp+var_48]
0x1801f6587  mov     [rbp+var_50], r12
0x1801f658b  mov     rax, [rcx]
0x1801f658e  mov     rax, [rax+90h]
0x1801f6595  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f659a  test    eax, eax
0x1801f659c  jnz     short loc_1801F65B6
0x1801f659e  mov     rcx, [rbp+var_58]
0x1801f65a2  mov     r8, [rbp+var_50]
0x1801f65a6  mov     rdx, [rbp+var_60]
0x1801f65aa  mov     rax, [rcx]
0x1801f65ad  mov     rax, [rax+70h]
0x1801f65b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f65b6  lea     rcx, [rbp+var_50]; void *
0x1801f65ba  call    ??1?$TCntPtr@UIDataObject@@@Resp@@QEAA@XZ; Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(void)
0x1801f65bf  mov     rcx, [rbp+var_60]; string
0x1801f65c3  call    cs:__imp_WindowsDeleteString
0x1801f65c9  mov     rcx, [rbp+var_48]; string
0x1801f65cd  mov     [rbp+var_60], r12
0x1801f65d1  call    cs:__imp_WindowsDeleteString
0x1801f65d7  lea     rcx, [rbp+var_40]; struct tagSTGMEDIUM *
0x1801f65db  call    ?ReleaseStgMedium@CW32System@@SAXPEAUtagSTGMEDIUM@@@Z; CW32System::ReleaseStgMedium(tagSTGMEDIUM *)
0x1801f65e0  jmp     short loc_1801F65EC
0x1801f65e2  cmp     ebx, 80040064h
0x1801f65e8  cmovz   ebx, r12d
0x1801f65ec  inc     edi
0x1801f65ee  lea     rcx, ?SupportedFormats@@3QBUSupportedFormat@@B; SupportedFormat const near * const SupportedFormats
0x1801f65f5  cmp     edi, 3
0x1801f65f8  jb      loc_1801F64B0
0x1801f65fe  test    ebx, ebx
0x1801f6600  jnz     short loc_1801F6618
0x1801f6602  mov     rcx, [rsi+10h]
0x1801f6606  mov     rdx, [rbp+var_58]
0x1801f660a  mov     rax, [rcx]
0x1801f660d  mov     rax, [rax+38h]
0x1801f6611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f6616  mov     ebx, eax
0x1801f6618  lea     rcx, [rbp+var_58]
0x1801f661c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801f6621  lea     r11, [rsp+80h+var_s0]
0x1801f6629  mov     eax, ebx
0x1801f662b  mov     rbx, [r11+30h]
0x1801f662f  mov     rsi, [r11+38h]
0x1801f6633  mov     rsp, r11
0x1801f6636  pop     r15
0x1801f6638  pop     r14
0x1801f663a  pop     r12
0x1801f663c  pop     rdi
0x1801f663d  pop     rbp
0x1801f663e  retn
```
