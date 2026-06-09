# PrintableAreaToPrintCapabilities(publicdm::CPrintCapsInfo &)

- ea: `0x1800fad30`
- end: `0x1800fb086`
- name: `?PrintableAreaToPrintCapabilities@@YAJAEAVCPrintCapsInfo@publicdm@@@Z`
- size: `854`
- prototype: `__int64 __fastcall(struct publicdm::CPrintCapsInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800fa060`

## callees

- `0x1800ede04`
- `0x1800fad30`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800fad71`
- `KERNEL32!GetLastError` at `0x1800fad71`
- `GDI32!DeleteDC` at `0x1800fb066`
- `GDI32!DeleteDC` at `0x1800fb066`
- `GDI32!GetDeviceCaps` at `0x1800fad96`
- `GDI32!GetDeviceCaps` at `0x1800fada7`
- `GDI32!GetDeviceCaps` at `0x1800fadb8`
- `GDI32!GetDeviceCaps` at `0x1800fadc9`
- `GDI32!GetDeviceCaps` at `0x1800fadda`
- `GDI32!GetDeviceCaps` at `0x1800fadeb`
- `GDI32!GetDeviceCaps` at `0x1800fadfc`
- `GDI32!GetDeviceCaps` at `0x1800fae0d`
- `GDI32!GetDeviceCaps` at `0x1800fad96`
- `GDI32!GetDeviceCaps` at `0x1800fada7`
- `GDI32!GetDeviceCaps` at `0x1800fadb8`
- `GDI32!GetDeviceCaps` at `0x1800fadc9`
- `GDI32!GetDeviceCaps` at `0x1800fadda`
- `GDI32!GetDeviceCaps` at `0x1800fadeb`
- `GDI32!GetDeviceCaps` at `0x1800fadfc`
- `GDI32!GetDeviceCaps` at `0x1800fae0d`
- `GDI32!CreateICW` at `0x1800fad63`
- `GDI32!CreateICW` at `0x1800fad63`

## string_xrefs

- `0x1800fae5d`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x1800fae9f`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x1800faee0`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall PrintableAreaToPrintCapabilities(struct publicdm::CPrintCapsInfo *a1)
{
  signed int Property; // ebx
  HDC ICW; // rsi
  signed int LastError; // eax
  int v5; // r12d
  int v6; // r13d
  int v7; // r15d
  int v8; // eax
  int v9; // r14d
  struct IXMLDOMElement **v11; // [rsp+30h] [rbp-40h]
  struct IXMLDOMElement **v12; // [rsp+30h] [rbp-40h]
  struct IXMLDOMElement **v13; // [rsp+30h] [rbp-40h]
  struct IXMLDOMElement **v14; // [rsp+30h] [rbp-40h]
  int v15; // [rsp+50h] [rbp-20h]
  int DeviceCaps; // [rsp+B8h] [rbp+48h]
  int v17; // [rsp+C0h] [rbp+50h]
  int v18; // [rsp+C8h] [rbp+58h]

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
    v18 = GetDeviceCaps(ICW, 8);
    v17 = GetDeviceCaps(ICW, 113);
    v15 = GetDeviceCaps(ICW, 10);
    v5 = GetDeviceCaps(ICW, 110);
    v6 = GetDeviceCaps(ICW, 111);
    v7 = GetDeviceCaps(ICW, 88);
    v8 = GetDeviceCaps(ICW, 90);
    v9 = v8;
    if ( v7 )
    {
      if ( v8 )
      {
        Property = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const OLECHAR *, const wchar_t *, _QWORD, _DWORD))(**((_QWORD **)a1 + 14) + 8LL))(
                     *((_QWORD *)a1 + 14),
                     0,
                     L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                     L"PageImageableSize",
                     0,
                     0);
        if ( Property >= 0 )
        {
          Property = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                       *((NPrintTicketUtil::CPrintTicketWrapper **)a1 + 14),
                       0,
                       L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                       L"ImageableSizeWidth",
                       10 * (2540 * v5 / v7),
                       0,
                       0);
          if ( Property >= 0 )
          {
            Property = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                         *((NPrintTicketUtil::CPrintTicketWrapper **)a1 + 14),
                         0,
                         L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                         L"ImageableSizeHeight",
                         10 * (2540 * v6 / v9),
                         0,
                         v11);
            if ( Property >= 0 )
            {
              Property = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const OLECHAR *, const wchar_t *, _QWORD, _DWORD))(**((_QWORD **)a1 + 14) + 8LL))(
                           *((_QWORD *)a1 + 14),
                           0,
                           L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                           L"ImageableArea",
                           0,
                           0);
              if ( Property >= 0 )
              {
                Property = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                             *((NPrintTicketUtil::CPrintTicketWrapper **)a1 + 14),
                             0,
                             L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                             L"OriginWidth",
                             10 * (2540 * DeviceCaps / v7),
                             0,
                             0);
                if ( Property >= 0 )
                {
                  Property = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                               *((NPrintTicketUtil::CPrintTicketWrapper **)a1 + 14),
                               0,
                               L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                               L"OriginHeight",
                               10 * (2540 * v17 / v9),
                               0,
                               v12);
                  if ( Property >= 0 )
                  {
                    Property = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                                 *((NPrintTicketUtil::CPrintTicketWrapper **)a1 + 14),
                                 0,
                                 L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                                 L"ExtentWidth",
                                 10 * (2540 * v18 / v7),
                                 0,
                                 v13);
                    if ( Property >= 0 )
                      Property = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                                   *((NPrintTicketUtil::CPrintTicketWrapper **)a1 + 14),
                                   0,
                                   L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                                   L"ExtentHeight",
                                   10 * (2540 * v15 / v9),
                                   0,
                                   v14);
                  }
                }
              }
            }
          }
        }
      }
    }
    if ( ICW )
      DeleteDC(ICW);
  }
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x1800fad30  mov     rax, rsp
0x1800fad33  push    rbp
0x1800fad34  push    rsi
0x1800fad35  push    rdi
0x1800fad36  push    r12
0x1800fad38  push    r13
0x1800fad3a  push    r14
0x1800fad3c  push    r15
0x1800fad3e  mov     rbp, rsp
0x1800fad41  sub     rsp, 70h
0x1800fad45  mov     [rbp+var_8], 0FFFFFFFFFFFFFFFEh
0x1800fad4d  mov     [rax+8], rbx
0x1800fad51  mov     rdi, rcx
0x1800fad54  xor     ebx, ebx
0x1800fad56  mov     r9, [rcx+10h]; pdm
0x1800fad5a  xor     r8d, r8d; pszPort
0x1800fad5d  mov     rdx, [rcx+18h]; pszDevice
0x1800fad61  xor     ecx, ecx; pszDriver
0x1800fad63  call    cs:__imp_CreateICW
0x1800fad69  mov     rsi, rax
0x1800fad6c  test    rax, rax
0x1800fad6f  jnz     short loc_1800FAD8E
0x1800fad71  call    cs:__imp_GetLastError
0x1800fad77  mov     ebx, eax
0x1800fad79  test    eax, eax
0x1800fad7b  jle     short loc_1800FAD86
0x1800fad7d  movzx   ebx, ax
0x1800fad80  or      ebx, 80070000h
0x1800fad86  test    ebx, ebx
0x1800fad88  js      loc_1800FB06C
0x1800fad8e  mov     edx, 70h ; 'p'; index
0x1800fad93  mov     rcx, rsi; hdc
0x1800fad96  call    cs:__imp_GetDeviceCaps
0x1800fad9c  mov     [rbp+arg_8], eax
0x1800fad9f  mov     edx, 8; index
0x1800fada4  mov     rcx, rsi; hdc
0x1800fada7  call    cs:__imp_GetDeviceCaps
0x1800fadad  mov     [rbp+arg_18], eax
0x1800fadb0  mov     edx, 71h ; 'q'; index
0x1800fadb5  mov     rcx, rsi; hdc
0x1800fadb8  call    cs:__imp_GetDeviceCaps
0x1800fadbe  mov     [rbp+arg_10], eax
0x1800fadc1  mov     edx, 0Ah; index
0x1800fadc6  mov     rcx, rsi; hdc
0x1800fadc9  call    cs:__imp_GetDeviceCaps
0x1800fadcf  mov     [rbp+var_20], eax
0x1800fadd2  mov     edx, 6Eh ; 'n'; index
0x1800fadd7  mov     rcx, rsi; hdc
0x1800fadda  call    cs:__imp_GetDeviceCaps
0x1800fade0  mov     r12d, eax
0x1800fade3  mov     edx, 6Fh ; 'o'; index
0x1800fade8  mov     rcx, rsi; hdc
0x1800fadeb  call    cs:__imp_GetDeviceCaps
0x1800fadf1  mov     r13d, eax
0x1800fadf4  mov     edx, 58h ; 'X'; index
0x1800fadf9  mov     rcx, rsi; hdc
0x1800fadfc  call    cs:__imp_GetDeviceCaps
0x1800fae02  mov     r15d, eax
0x1800fae05  mov     edx, 5Ah ; 'Z'; index
0x1800fae0a  mov     rcx, rsi; hdc
0x1800fae0d  call    cs:__imp_GetDeviceCaps
0x1800fae13  mov     r14d, eax
0x1800fae16  xor     r8d, r8d
0x1800fae19  test    r15d, r15d
0x1800fae1c  jz      loc_1800FB05E
0x1800fae22  test    eax, eax
0x1800fae24  jz      loc_1800FB05E
0x1800fae2a  mov     [rbp+var_10], r8
0x1800fae2e  mov     [rbp+var_18], r8
0x1800fae32  mov     rcx, [rdi+70h]
0x1800fae36  mov     rax, [rcx]
0x1800fae39  lea     rdx, [rbp+var_10]
0x1800fae3d  mov     [rsp+70h+var_30], rdx
0x1800fae42  mov     [rsp+70h+var_38], r8
0x1800fae47  mov     [rsp+70h+var_40], r8; struct IXMLDOMElement **
0x1800fae4c  mov     [rsp+70h+var_48], r8d
0x1800fae51  mov     qword ptr [rsp+70h+var_50], r8
0x1800fae56  lea     r9, aPageimageables_0; "PageImageableSize"
0x1800fae5d  lea     r8, aHttpSchemasMic_8; "http://schemas.microsoft.com/windows/20"...
0x1800fae64  xor     edx, edx
0x1800fae66  mov     rax, [rax+8]
0x1800fae6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fae6f  mov     ebx, eax
0x1800fae71  test    eax, eax
0x1800fae73  js      loc_1800FB02C
0x1800fae79  imul    eax, r12d, 9ECh
0x1800fae80  cdq
0x1800fae81  idiv    r15d
0x1800fae84  lea     r8d, [rax+rax*4]
0x1800fae88  add     r8d, r8d
0x1800fae8b  xor     r12d, r12d
0x1800fae8e  mov     [rsp+70h+var_48], r12d; int
0x1800fae93  mov     [rsp+70h+var_50], r8d; int
0x1800fae98  lea     r9, aImageablesizew_0; "ImageableSizeWidth"
0x1800fae9f  lea     r8, aHttpSchemasMic_8; "http://schemas.microsoft.com/windows/20"...
0x1800faea6  mov     rdx, [rbp+var_10]; struct IXMLDOMElement *
0x1800faeaa  mov     rcx, [rdi+70h]; this
0x1800faeae  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1HHPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,int,int,IXMLDOMElement * *)
0x1800faeb3  mov     ebx, eax
0x1800faeb5  test    eax, eax
0x1800faeb7  js      loc_1800FB02F
0x1800faebd  imul    eax, r13d, 9ECh
0x1800faec4  cdq
0x1800faec5  idiv    r14d
0x1800faec8  lea     r8d, [rax+rax*4]
0x1800faecc  add     r8d, r8d
0x1800faecf  mov     [rsp+70h+var_48], r12d; int
0x1800faed4  mov     [rsp+70h+var_50], r8d; int
0x1800faed9  lea     r9, aImageablesizeh_0; "ImageableSizeHeight"
0x1800faee0  lea     r13, aHttpSchemasMic_8; "http://schemas.microsoft.com/windows/20"...
0x1800faee7  mov     r8, r13; unsigned __int16 *
0x1800faeea  mov     rdx, [rbp+var_10]; struct IXMLDOMElement *
0x1800faeee  mov     rcx, [rdi+70h]; this
0x1800faef2  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1HHPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,int,int,IXMLDOMElement * *)
0x1800faef7  mov     ebx, eax
0x1800faef9  test    eax, eax
0x1800faefb  js      loc_1800FB02F
0x1800faf01  mov     rcx, [rdi+70h]
0x1800faf05  mov     rax, [rcx]
0x1800faf08  lea     rdx, [rbp+var_18]
0x1800faf0c  mov     [rsp+70h+var_30], rdx
0x1800faf11  mov     [rsp+70h+var_38], r12
0x1800faf16  mov     [rsp+70h+var_40], r12; struct IXMLDOMElement **
0x1800faf1b  mov     [rsp+70h+var_48], r12d
0x1800faf20  mov     qword ptr [rsp+70h+var_50], r12
0x1800faf25  lea     r9, aImageablearea_1; "ImageableArea"
0x1800faf2c  mov     r8, r13
0x1800faf2f  mov     rdx, [rbp+var_10]
0x1800faf33  mov     rax, [rax+8]
0x1800faf37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800faf3c  mov     ebx, eax
0x1800faf3e  test    eax, eax
0x1800faf40  js      loc_1800FB02F
0x1800faf46  imul    eax, [rbp+arg_8], 9ECh
0x1800faf4d  cdq
0x1800faf4e  idiv    r15d
0x1800faf51  lea     r8d, [rax+rax*4]
0x1800faf55  add     r8d, r8d
0x1800faf58  mov     [rsp+70h+var_48], r12d; int
0x1800faf5d  mov     [rsp+70h+var_50], r8d; int
0x1800faf62  lea     r9, aOriginwidth_0; "OriginWidth"
0x1800faf69  mov     r8, r13; unsigned __int16 *
0x1800faf6c  mov     rdx, [rbp+var_18]; struct IXMLDOMElement *
0x1800faf70  mov     rcx, [rdi+70h]; this
0x1800faf74  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1HHPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,int,int,IXMLDOMElement * *)
0x1800faf79  mov     ebx, eax
0x1800faf7b  test    eax, eax
0x1800faf7d  js      loc_1800FB02F
0x1800faf83  imul    eax, [rbp+arg_10], 9ECh
0x1800faf8a  cdq
0x1800faf8b  idiv    r14d
0x1800faf8e  lea     r8d, [rax+rax*4]
0x1800faf92  add     r8d, r8d
0x1800faf95  mov     [rsp+70h+var_48], r12d; int
0x1800faf9a  mov     [rsp+70h+var_50], r8d; int
0x1800faf9f  lea     r9, aOriginheight_0; "OriginHeight"
0x1800fafa6  mov     r8, r13; unsigned __int16 *
0x1800fafa9  mov     rdx, [rbp+var_18]; struct IXMLDOMElement *
0x1800fafad  mov     rcx, [rdi+70h]; this
0x1800fafb1  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1HHPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,int,int,IXMLDOMElement * *)
0x1800fafb6  mov     ebx, eax
0x1800fafb8  test    eax, eax
0x1800fafba  js      short loc_1800FB02F
0x1800fafbc  imul    eax, [rbp+arg_18], 9ECh
0x1800fafc3  cdq
0x1800fafc4  idiv    r15d
0x1800fafc7  lea     r8d, [rax+rax*4]
0x1800fafcb  add     r8d, r8d
0x1800fafce  mov     [rsp+70h+var_48], r12d; int
0x1800fafd3  mov     [rsp+70h+var_50], r8d; int
0x1800fafd8  lea     r9, aExtentwidth_0; "ExtentWidth"
0x1800fafdf  mov     r8, r13; unsigned __int16 *
0x1800fafe2  mov     rdx, [rbp+var_18]; struct IXMLDOMElement *
0x1800fafe6  mov     rcx, [rdi+70h]; this
0x1800fafea  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1HHPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,int,int,IXMLDOMElement * *)
0x1800fafef  mov     ebx, eax
0x1800faff1  test    eax, eax
0x1800faff3  js      short loc_1800FB02F
0x1800faff5  imul    eax, [rbp+var_20], 9ECh
0x1800faffc  cdq
0x1800faffd  idiv    r14d
0x1800fb000  lea     r9d, [rax+rax*4]
0x1800fb004  add     r9d, r9d
0x1800fb007  mov     [rsp+70h+var_48], r12d; int
0x1800fb00c  mov     [rsp+70h+var_50], r9d; int
0x1800fb011  lea     r9, aExtentheight_0; "ExtentHeight"
0x1800fb018  mov     r8, r13; unsigned __int16 *
0x1800fb01b  mov     rdx, [rbp+var_18]; struct IXMLDOMElement *
0x1800fb01f  mov     rcx, [rdi+70h]; this
0x1800fb023  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1HHPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,int,int,IXMLDOMElement * *)
0x1800fb028  mov     ebx, eax
0x1800fb02a  jmp     short loc_1800FB02F
0x1800fb02c  xor     r12d, r12d
0x1800fb02f  mov     rcx, [rbp+var_18]
0x1800fb033  test    rcx, rcx
0x1800fb036  jz      short loc_1800FB048
0x1800fb038  mov     rax, [rcx]
0x1800fb03b  mov     rax, [rax+10h]
0x1800fb03f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb044  mov     [rbp+var_18], r12
0x1800fb048  mov     rcx, [rbp+var_10]
0x1800fb04c  test    rcx, rcx
0x1800fb04f  jz      short loc_1800FB05E
0x1800fb051  mov     rax, [rcx]
0x1800fb054  mov     rax, [rax+10h]
0x1800fb058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb05d  nop
0x1800fb05e  test    rsi, rsi
0x1800fb061  jz      short loc_1800FB06C
0x1800fb063  mov     rcx, rsi; hdc
0x1800fb066  call    cs:__imp_DeleteDC
0x1800fb06c  mov     eax, ebx
0x1800fb06e  mov     rbx, [rsp+70h+arg_0]
0x1800fb076  add     rsp, 70h
0x1800fb07a  pop     r15
0x1800fb07c  pop     r14
0x1800fb07e  pop     r13
0x1800fb080  pop     r12
0x1800fb082  pop     rdi
0x1800fb083  pop     rsi
0x1800fb084  pop     rbp
0x1800fb085  retn
```
