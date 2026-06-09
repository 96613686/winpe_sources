# PrintableAreaToPrintCapabilities(publicdm::CPrintCapsInfo &)

- ea: `0x1800ff7e8`
- end: `0x1800ffb81`
- name: `?PrintableAreaToPrintCapabilities@@YAJAEAVCPrintCapsInfo@publicdm@@@Z`
- size: `921`
- prototype: `__int64 __fastcall(struct publicdm::CPrintCapsInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800feb70`

## callees

- `0x1800f2724`
- `0x1800ff7e8`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800ff82f`
- `KERNEL32!GetLastError` at `0x1800ff82f`
- `GDI32!DeleteDC` at `0x1800ffb5a`
- `GDI32!DeleteDC` at `0x1800ffb5a`
- `GDI32!GetDeviceCaps` at `0x1800ff85a`
- `GDI32!GetDeviceCaps` at `0x1800ff871`
- `GDI32!GetDeviceCaps` at `0x1800ff888`
- `GDI32!GetDeviceCaps` at `0x1800ff89f`
- `GDI32!GetDeviceCaps` at `0x1800ff8b6`
- `GDI32!GetDeviceCaps` at `0x1800ff8cd`
- `GDI32!GetDeviceCaps` at `0x1800ff8e4`
- `GDI32!GetDeviceCaps` at `0x1800ff8fb`
- `GDI32!GetDeviceCaps` at `0x1800ff85a`
- `GDI32!GetDeviceCaps` at `0x1800ff871`
- `GDI32!GetDeviceCaps` at `0x1800ff888`
- `GDI32!GetDeviceCaps` at `0x1800ff89f`
- `GDI32!GetDeviceCaps` at `0x1800ff8b6`
- `GDI32!GetDeviceCaps` at `0x1800ff8cd`
- `GDI32!GetDeviceCaps` at `0x1800ff8e4`
- `GDI32!GetDeviceCaps` at `0x1800ff8fb`
- `GDI32!CreateICW` at `0x1800ff81b`
- `GDI32!CreateICW` at `0x1800ff81b`

## string_xrefs

- `0x1800ff951`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x1800ff993`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x1800ff9d4`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall PrintableAreaToPrintCapabilities(struct publicdm::CPrintCapsInfo *a1)
{
  int Property; // ebx
  HDC ICW; // rsi
  signed int LastError; // eax
  int v5; // r12d
  int v6; // r13d
  int v7; // r15d
  int v8; // eax
  int v9; // r14d
  int v11; // [rsp+50h] [rbp-20h]
  struct IXMLDOMElement *v12; // [rsp+58h] [rbp-18h] BYREF
  struct IXMLDOMElement *v13[2]; // [rsp+60h] [rbp-10h] BYREF
  int DeviceCaps; // [rsp+B8h] [rbp+48h]
  int v15; // [rsp+C0h] [rbp+50h]
  int v16; // [rsp+C8h] [rbp+58h]

  v13[1] = (struct IXMLDOMElement *)-2LL;
  Property = 0;
  ICW = CreateICW(0, *((LPCWSTR *)a1 + 3), 0, *((const DEVMODEW **)a1 + 2));
  if ( ICW )
    goto LABEL_5;
  LastError = GetLastError();
  Property = LastError;
  if ( LastError > 0 )
    Property = (unsigned __int16)LastError | 0x80070000;
  if ( Property >= 0 )
  {
LABEL_5:
    DeviceCaps = GetDeviceCaps(ICW, 112);
    v16 = GetDeviceCaps(ICW, 8);
    v15 = GetDeviceCaps(ICW, 113);
    v11 = GetDeviceCaps(ICW, 10);
    v5 = GetDeviceCaps(ICW, 110);
    v6 = GetDeviceCaps(ICW, 111);
    v7 = GetDeviceCaps(ICW, 88);
    v8 = GetDeviceCaps(ICW, 90);
    v9 = v8;
    if ( v7 && v8 )
    {
      v13[0] = 0;
      v12 = 0;
      Property = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const OLECHAR *, const wchar_t *, _QWORD, _DWORD, _QWORD, _QWORD, struct IXMLDOMElement **))(**((_QWORD **)a1 + 14) + 8LL))(
                   *((_QWORD *)a1 + 14),
                   0,
                   L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                   L"PageImageableSize",
                   0,
                   0,
                   0,
                   0,
                   v13);
      if ( Property >= 0 )
      {
        Property = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                     *((NPrintTicketUtil::CPrintTicketWrapper **)a1 + 14),
                     v13[0],
                     L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                     L"ImageableSizeWidth",
                     10 * (2540 * v5 / v7),
                     0);
        if ( Property >= 0 )
        {
          Property = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                       *((NPrintTicketUtil::CPrintTicketWrapper **)a1 + 14),
                       v13[0],
                       L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                       L"ImageableSizeHeight",
                       10 * (2540 * v6 / v9),
                       0);
          if ( Property >= 0 )
          {
            Property = (*(__int64 (__fastcall **)(_QWORD, struct IXMLDOMElement *, const OLECHAR *, const wchar_t *, _QWORD, _DWORD, _QWORD, _QWORD, struct IXMLDOMElement **))(**((_QWORD **)a1 + 14) + 8LL))(
                         *((_QWORD *)a1 + 14),
                         v13[0],
                         L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                         L"ImageableArea",
                         0,
                         0,
                         0,
                         0,
                         &v12);
            if ( Property >= 0 )
            {
              Property = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                           *((NPrintTicketUtil::CPrintTicketWrapper **)a1 + 14),
                           v12,
                           L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                           L"OriginWidth",
                           10 * (2540 * DeviceCaps / v7),
                           0);
              if ( Property >= 0 )
              {
                Property = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                             *((NPrintTicketUtil::CPrintTicketWrapper **)a1 + 14),
                             v12,
                             L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                             L"OriginHeight",
                             10 * (2540 * v15 / v9),
                             0);
                if ( Property >= 0 )
                {
                  Property = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                               *((NPrintTicketUtil::CPrintTicketWrapper **)a1 + 14),
                               v12,
                               L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                               L"ExtentWidth",
                               10 * (2540 * v16 / v7),
                               0);
                  if ( Property >= 0 )
                    Property = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                                 *((NPrintTicketUtil::CPrintTicketWrapper **)a1 + 14),
                                 v12,
                                 L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                                 L"ExtentHeight",
                                 10 * (2540 * v11 / v9),
                                 0);
                }
              }
            }
          }
        }
      }
      if ( v12 )
      {
        ((void (__fastcall *)(struct IXMLDOMElement *))v12->lpVtbl->Release)(v12);
        v12 = 0;
      }
      if ( v13[0] )
        ((void (__fastcall *)(struct IXMLDOMElement *))v13[0]->lpVtbl->Release)(v13[0]);
    }
    if ( ICW )
      DeleteDC(ICW);
  }
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x1800ff7e8  mov     rax, rsp
0x1800ff7eb  push    rbp
0x1800ff7ec  push    rsi
0x1800ff7ed  push    rdi
0x1800ff7ee  push    r12
0x1800ff7f0  push    r13
0x1800ff7f2  push    r14
0x1800ff7f4  push    r15
0x1800ff7f6  mov     rbp, rsp
0x1800ff7f9  sub     rsp, 70h
0x1800ff7fd  mov     [rbp+var_8], 0FFFFFFFFFFFFFFFEh
0x1800ff805  mov     [rax+8], rbx
0x1800ff809  mov     rdi, rcx
0x1800ff80c  xor     ebx, ebx
0x1800ff80e  mov     r9, [rcx+10h]; pdm
0x1800ff812  xor     r8d, r8d; pszPort
0x1800ff815  mov     rdx, [rcx+18h]; pszDevice
0x1800ff819  xor     ecx, ecx; pszDriver
0x1800ff81b  call    cs:__imp_CreateICW
0x1800ff822  nop     dword ptr [rax+rax+00h]
0x1800ff827  mov     rsi, rax
0x1800ff82a  test    rax, rax
0x1800ff82d  jnz     short loc_1800FF852
0x1800ff82f  call    cs:__imp_GetLastError
0x1800ff836  nop     dword ptr [rax+rax+00h]
0x1800ff83b  mov     ebx, eax
0x1800ff83d  test    eax, eax
0x1800ff83f  jle     short loc_1800FF84A
0x1800ff841  movzx   ebx, ax
0x1800ff844  or      ebx, 80070000h
0x1800ff84a  test    ebx, ebx
0x1800ff84c  js      loc_1800FFB66
0x1800ff852  mov     edx, 70h ; 'p'; index
0x1800ff857  mov     rcx, rsi; hdc
0x1800ff85a  call    cs:__imp_GetDeviceCaps
0x1800ff861  nop     dword ptr [rax+rax+00h]
0x1800ff866  mov     [rbp+arg_8], eax
0x1800ff869  mov     edx, 8; index
0x1800ff86e  mov     rcx, rsi; hdc
0x1800ff871  call    cs:__imp_GetDeviceCaps
0x1800ff878  nop     dword ptr [rax+rax+00h]
0x1800ff87d  mov     [rbp+arg_18], eax
0x1800ff880  mov     edx, 71h ; 'q'; index
0x1800ff885  mov     rcx, rsi; hdc
0x1800ff888  call    cs:__imp_GetDeviceCaps
0x1800ff88f  nop     dword ptr [rax+rax+00h]
0x1800ff894  mov     [rbp+arg_10], eax
0x1800ff897  mov     edx, 0Ah; index
0x1800ff89c  mov     rcx, rsi; hdc
0x1800ff89f  call    cs:__imp_GetDeviceCaps
0x1800ff8a6  nop     dword ptr [rax+rax+00h]
0x1800ff8ab  mov     [rbp+var_20], eax
0x1800ff8ae  mov     edx, 6Eh ; 'n'; index
0x1800ff8b3  mov     rcx, rsi; hdc
0x1800ff8b6  call    cs:__imp_GetDeviceCaps
0x1800ff8bd  nop     dword ptr [rax+rax+00h]
0x1800ff8c2  mov     r12d, eax
0x1800ff8c5  mov     edx, 6Fh ; 'o'; index
0x1800ff8ca  mov     rcx, rsi; hdc
0x1800ff8cd  call    cs:__imp_GetDeviceCaps
0x1800ff8d4  nop     dword ptr [rax+rax+00h]
0x1800ff8d9  mov     r13d, eax
0x1800ff8dc  mov     edx, 58h ; 'X'; index
0x1800ff8e1  mov     rcx, rsi; hdc
0x1800ff8e4  call    cs:__imp_GetDeviceCaps
0x1800ff8eb  nop     dword ptr [rax+rax+00h]
0x1800ff8f0  mov     r15d, eax
0x1800ff8f3  mov     edx, 5Ah ; 'Z'; index
0x1800ff8f8  mov     rcx, rsi; hdc
0x1800ff8fb  call    cs:__imp_GetDeviceCaps
0x1800ff902  nop     dword ptr [rax+rax+00h]
0x1800ff907  mov     r14d, eax
0x1800ff90a  xor     r8d, r8d
0x1800ff90d  test    r15d, r15d
0x1800ff910  jz      loc_1800FFB52
0x1800ff916  test    eax, eax
0x1800ff918  jz      loc_1800FFB52
0x1800ff91e  mov     [rbp+var_10], r8
0x1800ff922  mov     [rbp+var_18], r8
0x1800ff926  mov     rcx, [rdi+70h]
0x1800ff92a  mov     rax, [rcx]
0x1800ff92d  lea     rdx, [rbp+var_10]
0x1800ff931  mov     [rsp+70h+var_30], rdx
0x1800ff936  mov     [rsp+70h+var_38], r8
0x1800ff93b  mov     [rsp+70h+var_40], r8; struct IXMLDOMElement **
0x1800ff940  mov     [rsp+70h+var_48], r8d
0x1800ff945  mov     qword ptr [rsp+70h+var_50], r8
0x1800ff94a  lea     r9, aPageimageables_0; "PageImageableSize"
0x1800ff951  lea     r8, aHttpSchemasMic_8; "http://schemas.microsoft.com/windows/20"...
0x1800ff958  xor     edx, edx
0x1800ff95a  mov     rax, [rax+8]
0x1800ff95e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff963  mov     ebx, eax
0x1800ff965  test    eax, eax
0x1800ff967  js      loc_1800FFB20
0x1800ff96d  imul    eax, r12d, 9ECh
0x1800ff974  cdq
0x1800ff975  idiv    r15d
0x1800ff978  lea     r8d, [rax+rax*4]
0x1800ff97c  add     r8d, r8d
0x1800ff97f  xor     r12d, r12d
0x1800ff982  mov     [rsp+70h+var_48], r12d; int
0x1800ff987  mov     [rsp+70h+var_50], r8d; int
0x1800ff98c  lea     r9, aImageablesizew_0; "ImageableSizeWidth"
0x1800ff993  lea     r8, aHttpSchemasMic_8; "http://schemas.microsoft.com/windows/20"...
0x1800ff99a  mov     rdx, [rbp+var_10]; struct IXMLDOMElement *
0x1800ff99e  mov     rcx, [rdi+70h]; this
0x1800ff9a2  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1HHPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,int,int,IXMLDOMElement * *)
0x1800ff9a7  mov     ebx, eax
0x1800ff9a9  test    eax, eax
0x1800ff9ab  js      loc_1800FFB23
0x1800ff9b1  imul    eax, r13d, 9ECh
0x1800ff9b8  cdq
0x1800ff9b9  idiv    r14d
0x1800ff9bc  lea     r8d, [rax+rax*4]
0x1800ff9c0  add     r8d, r8d
0x1800ff9c3  mov     [rsp+70h+var_48], r12d; int
0x1800ff9c8  mov     [rsp+70h+var_50], r8d; int
0x1800ff9cd  lea     r9, aImageablesizeh_0; "ImageableSizeHeight"
0x1800ff9d4  lea     r13, aHttpSchemasMic_8; "http://schemas.microsoft.com/windows/20"...
0x1800ff9db  mov     r8, r13; unsigned __int16 *
0x1800ff9de  mov     rdx, [rbp+var_10]; struct IXMLDOMElement *
0x1800ff9e2  mov     rcx, [rdi+70h]; this
0x1800ff9e6  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1HHPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,int,int,IXMLDOMElement * *)
0x1800ff9eb  mov     ebx, eax
0x1800ff9ed  test    eax, eax
0x1800ff9ef  js      loc_1800FFB23
0x1800ff9f5  mov     rcx, [rdi+70h]
0x1800ff9f9  mov     rax, [rcx]
0x1800ff9fc  lea     rdx, [rbp+var_18]
0x1800ffa00  mov     [rsp+70h+var_30], rdx
0x1800ffa05  mov     [rsp+70h+var_38], r12
0x1800ffa0a  mov     [rsp+70h+var_40], r12; struct IXMLDOMElement **
0x1800ffa0f  mov     [rsp+70h+var_48], r12d
0x1800ffa14  mov     qword ptr [rsp+70h+var_50], r12
0x1800ffa19  lea     r9, aImageablearea_1; "ImageableArea"
0x1800ffa20  mov     r8, r13
0x1800ffa23  mov     rdx, [rbp+var_10]
0x1800ffa27  mov     rax, [rax+8]
0x1800ffa2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ffa30  mov     ebx, eax
0x1800ffa32  test    eax, eax
0x1800ffa34  js      loc_1800FFB23
0x1800ffa3a  imul    eax, [rbp+arg_8], 9ECh
0x1800ffa41  cdq
0x1800ffa42  idiv    r15d
0x1800ffa45  lea     r8d, [rax+rax*4]
0x1800ffa49  add     r8d, r8d
0x1800ffa4c  mov     [rsp+70h+var_48], r12d; int
0x1800ffa51  mov     [rsp+70h+var_50], r8d; int
0x1800ffa56  lea     r9, aOriginwidth_0; "OriginWidth"
0x1800ffa5d  mov     r8, r13; unsigned __int16 *
0x1800ffa60  mov     rdx, [rbp+var_18]; struct IXMLDOMElement *
0x1800ffa64  mov     rcx, [rdi+70h]; this
0x1800ffa68  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1HHPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,int,int,IXMLDOMElement * *)
0x1800ffa6d  mov     ebx, eax
0x1800ffa6f  test    eax, eax
0x1800ffa71  js      loc_1800FFB23
0x1800ffa77  imul    eax, [rbp+arg_10], 9ECh
0x1800ffa7e  cdq
0x1800ffa7f  idiv    r14d
0x1800ffa82  lea     r8d, [rax+rax*4]
0x1800ffa86  add     r8d, r8d
0x1800ffa89  mov     [rsp+70h+var_48], r12d; int
0x1800ffa8e  mov     [rsp+70h+var_50], r8d; int
0x1800ffa93  lea     r9, aOriginheight_0; "OriginHeight"
0x1800ffa9a  mov     r8, r13; unsigned __int16 *
0x1800ffa9d  mov     rdx, [rbp+var_18]; struct IXMLDOMElement *
0x1800ffaa1  mov     rcx, [rdi+70h]; this
0x1800ffaa5  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1HHPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,int,int,IXMLDOMElement * *)
0x1800ffaaa  mov     ebx, eax
0x1800ffaac  test    eax, eax
0x1800ffaae  js      short loc_1800FFB23
0x1800ffab0  imul    eax, [rbp+arg_18], 9ECh
0x1800ffab7  cdq
0x1800ffab8  idiv    r15d
0x1800ffabb  lea     r8d, [rax+rax*4]
0x1800ffabf  add     r8d, r8d
0x1800ffac2  mov     [rsp+70h+var_48], r12d; int
0x1800ffac7  mov     [rsp+70h+var_50], r8d; int
0x1800ffacc  lea     r9, aExtentwidth_0; "ExtentWidth"
0x1800ffad3  mov     r8, r13; unsigned __int16 *
0x1800ffad6  mov     rdx, [rbp+var_18]; struct IXMLDOMElement *
0x1800ffada  mov     rcx, [rdi+70h]; this
0x1800ffade  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1HHPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,int,int,IXMLDOMElement * *)
0x1800ffae3  mov     ebx, eax
0x1800ffae5  test    eax, eax
0x1800ffae7  js      short loc_1800FFB23
0x1800ffae9  imul    eax, [rbp+var_20], 9ECh
0x1800ffaf0  cdq
0x1800ffaf1  idiv    r14d
0x1800ffaf4  lea     r9d, [rax+rax*4]
0x1800ffaf8  add     r9d, r9d
0x1800ffafb  mov     [rsp+70h+var_48], r12d; int
0x1800ffb00  mov     [rsp+70h+var_50], r9d; int
0x1800ffb05  lea     r9, aExtentheight_0; "ExtentHeight"
0x1800ffb0c  mov     r8, r13; unsigned __int16 *
0x1800ffb0f  mov     rdx, [rbp+var_18]; struct IXMLDOMElement *
0x1800ffb13  mov     rcx, [rdi+70h]; this
0x1800ffb17  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1HHPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,int,int,IXMLDOMElement * *)
0x1800ffb1c  mov     ebx, eax
0x1800ffb1e  jmp     short loc_1800FFB23
0x1800ffb20  xor     r12d, r12d
0x1800ffb23  mov     rcx, [rbp+var_18]
0x1800ffb27  test    rcx, rcx
0x1800ffb2a  jz      short loc_1800FFB3C
0x1800ffb2c  mov     rax, [rcx]
0x1800ffb2f  mov     rax, [rax+10h]
0x1800ffb33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ffb38  mov     [rbp+var_18], r12
0x1800ffb3c  mov     rcx, [rbp+var_10]
0x1800ffb40  test    rcx, rcx
0x1800ffb43  jz      short loc_1800FFB52
0x1800ffb45  mov     rax, [rcx]
0x1800ffb48  mov     rax, [rax+10h]
0x1800ffb4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ffb51  nop
0x1800ffb52  test    rsi, rsi
0x1800ffb55  jz      short loc_1800FFB66
0x1800ffb57  mov     rcx, rsi; hdc
0x1800ffb5a  call    cs:__imp_DeleteDC
0x1800ffb61  nop     dword ptr [rax+rax+00h]
0x1800ffb66  mov     eax, ebx
0x1800ffb68  mov     rbx, [rsp+70h+arg_0]
0x1800ffb70  add     rsp, 70h
0x1800ffb74  pop     r15
0x1800ffb76  pop     r14
0x1800ffb78  pop     r13
0x1800ffb7a  pop     r12
0x1800ffb7c  pop     rdi
0x1800ffb7d  pop     rsi
0x1800ffb7e  pop     rbp
0x1800ffb7f  retn
```
