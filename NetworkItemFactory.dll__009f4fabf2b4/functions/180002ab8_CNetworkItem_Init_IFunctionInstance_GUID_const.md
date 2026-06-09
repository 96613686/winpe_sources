# CNetworkItem::Init(IFunctionInstance *,_GUID const &)

- ea: `0x180002ab8`
- end: `0x180002d44`
- name: `?Init@CNetworkItem@@QEAAJPEAUIFunctionInstance@@AEBU_GUID@@@Z`
- size: `652`
- prototype: `__int64 __fastcall(CNetworkItem *this, struct IFunctionInstance *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003d28`

## callees

- `0x180002ab8`
- `0x18000568c`
- `0x1800059e8`
- `0x180005b84`
- `0x180005bec`
- `0x180005c50`
- `0x180005cc0`
- `0x18000a7d0`
- `0x18000b010`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x180002c44`
- `KERNEL32!GlobalAlloc` at `0x180002c44`
- `KERNEL32!GlobalFree` at `0x180002c98`
- `KERNEL32!GlobalFree` at `0x180002c98`
- `ole32!CoTaskMemAlloc` at `0x180002b9e`
- `ole32!CoTaskMemAlloc` at `0x180002b9e`
- `ole32!CoMarshalInterface` at `0x180002c8d`
- `ole32!CoMarshalInterface` at `0x180002c8d`
- `ole32!CoTaskMemFree` at `0x180002bdd`
- `ole32!CoTaskMemFree` at `0x180002bdd`
- `ole32!CreateStreamOnHGlobal` at `0x180002c5e`
- `ole32!CreateStreamOnHGlobal` at `0x180002c5e`
- `USER32!LoadStringW` at `0x180002b3c`
- `USER32!LoadStringW` at `0x180002bcb`
- `USER32!LoadStringW` at `0x180002b3c`
- `USER32!LoadStringW` at `0x180002bcb`
- `PROPSYS!InitPropVariantFromStringVector` at `0x180002b5e`
- `PROPSYS!InitPropVariantFromStringVector` at `0x180002b5e`

## pseudocode

```c
__int64 __fastcall CNetworkItem::Init(CNetworkItem *this, struct IFunctionInstance *a2, const struct _GUID *a3)
{
  LPVOID *v4; // r14
  const struct _tagpropertykey *v7; // rdx
  WCHAR *v8; // rax
  int v9; // ebx
  HGLOBAL v10; // rax
  void *v11; // rbx
  const struct _tagpropertykey *v12; // rdx
  PCWSTR prgsz; // [rsp+30h] [rbp-78h] BYREF
  WCHAR Buffer[32]; // [rsp+40h] [rbp-68h] BYREF

  v4 = (LPVOID *)((char *)this + 24);
  if ( (int)GetFIComputerName(a2, (unsigned __int16 **)this + 3, (unsigned __int16 **)this + 6) < 0 )
  {
    *((_DWORD *)this + 10) = 0;
    if ( GetFIProperty(a2, &PKEY_Device_FriendlyName, (unsigned __int16 **)v4) < 0 )
    {
      v8 = (WCHAR *)CoTaskMemAlloc(0x40u);
      *v4 = v8;
      if ( !v8 )
        return (unsigned int)-2147024882;
      if ( !LoadStringW(g_hInst, 0x3E8u, v8, 32) )
      {
        v9 = -2147467259;
        CoTaskMemFree(*v4);
        return (unsigned int)v9;
      }
    }
    GetFIProperty(a2, &PKEY_PNPX_DeviceCategory, (struct tagPROPVARIANT *)this + 8);
    GetFIProperty(a2, &PKEY_PNPX_DeviceCategory_Desc, (struct tagPROPVARIANT *)this + 3);
    GetFIProperty(a2, &PKEY_PNPX_CompatibleTypes, (struct tagPROPVARIANT *)((char *)this + 152));
    GetFIProperty(a2, &PKEY_PNPX_PresentationUrl, (unsigned __int16 **)this + 35);
    v10 = GlobalAlloc(0x2002u, 0);
    v11 = v10;
    if ( v10 )
    {
      if ( CreateStreamOnHGlobal(v10, 1, (LPSTREAM *)this + 2) < 0 )
        GlobalFree(v11);
      else
        CoMarshalInterface(
          *((LPSTREAM *)this + 2),
          &GUID_33591c10_0bed_4f02_b0ab_1530d5533ee9,
          (LPUNKNOWN)a2,
          3u,
          0,
          1u);
    }
  }
  else
  {
    *((_DWORD *)this + 10) = 1;
    GetFIProperty(a2, v7, (unsigned int *)this + 56);
    if ( LoadStringW(g_hInst, 1002 - (*((_DWORD *)this + 56) != 10), Buffer, 32) )
    {
      prgsz = Buffer;
      InitPropVariantFromStringVector(&prgsz, 1u, (PROPVARIANT *)this + 9);
    }
    GetFIProperty(a2, &PKEY_WNET_Provider, (unsigned __int16 **)this + 27);
  }
  v9 = ((__int64 (__fastcall *)(struct IFunctionInstance *, char *))a2->lpVtbl->GetID)(a2, (char *)this + 32);
  if ( v9 >= 0 )
  {
    *(struct _GUID *)((char *)this + 56) = *a3;
    GetFIProperty(a2, &PKEY_PNPX_PhysicalAddress, (struct tagPROPVARIANT *)this + 4);
    GetFIProperty(a2, &PKEY_PNPX_IpAddress, (struct tagPROPVARIANT *)((char *)this + 232));
    GetFIProperty(a2, v12, (struct _GUID *)this + 11);
    GetFIProperty(a2, &PKEY_PNPX_NetworkInterfaceLuid, (struct tagPROPVARIANT *)((char *)this + 256));
    *((_DWORD *)this + 30) = CNetworkItemFactory::s_GetFIPriority(a2);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180002ab8  mov     [rsp+arg_10], rbx
0x180002abd  mov     [rsp+arg_18], rsi
0x180002ac2  push    rdi
0x180002ac3  push    r14
0x180002ac5  push    r15
0x180002ac7  sub     rsp, 90h
0x180002ace  mov     rax, cs:__security_cookie
0x180002ad5  xor     rax, rsp
0x180002ad8  mov     [rsp+0A8h+var_28], rax
0x180002ae0  mov     rsi, rdx
0x180002ae3  lea     r14, [rcx+18h]
0x180002ae7  mov     r15, r8
0x180002aea  mov     rdi, rcx
0x180002aed  lea     r8, [rcx+30h]; unsigned __int16 **
0x180002af1  mov     rdx, r14; unsigned __int16 **
0x180002af4  mov     rcx, rsi; struct IFunctionInstance *
0x180002af7  call    ?GetFIComputerName@@YAJPEAUIFunctionInstance@@PEAPEAG1@Z; GetFIComputerName(IFunctionInstance *,ushort * *,ushort * *)
0x180002afc  mov     rcx, rsi; struct IFunctionInstance *
0x180002aff  test    eax, eax
0x180002b01  js      short loc_180002B7F
0x180002b03  lea     rbx, [rdi+0E0h]
0x180002b0a  mov     dword ptr [rdi+28h], 1
0x180002b11  mov     r8, rbx; unsigned int *
0x180002b14  call    ?GetFIProperty@@YAJPEAUIFunctionInstance@@AEBU_tagpropertykey@@PEAI@Z; GetFIProperty(IFunctionInstance *,_tagpropertykey const &,uint *)
0x180002b19  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hInstance
0x180002b20  lea     r8, [rsp+0A8h+Buffer]; lpBuffer
0x180002b25  mov     eax, 0Ah
0x180002b2a  mov     r9d, 20h ; ' '; cchBufferMax
0x180002b30  sub     eax, [rbx]
0x180002b32  neg     eax
0x180002b34  sbb     edx, edx
0x180002b36  add     edx, 3EAh; uID
0x180002b3c  call    cs:__imp_LoadStringW
0x180002b42  test    eax, eax
0x180002b44  jz      short loc_180002B64
0x180002b46  lea     rax, [rsp+0A8h+Buffer]
0x180002b4b  mov     edx, 1; cElems
0x180002b50  lea     r8, [rdi+48h]; ppropvar
0x180002b54  mov     [rsp+0A8h+prgsz], rax
0x180002b59  lea     rcx, [rsp+0A8h+prgsz]; prgsz
0x180002b5e  call    cs:__imp_InitPropVariantFromStringVector
0x180002b64  lea     r8, [rdi+0D8h]; unsigned __int16 **
0x180002b6b  mov     rcx, rsi; struct IFunctionInstance *
0x180002b6e  lea     rdx, PKEY_WNET_Provider; struct _tagpropertykey *
0x180002b75  call    ?GetFIProperty@@YAJPEAUIFunctionInstance@@AEBU_tagpropertykey@@PEAPEAG@Z; GetFIProperty(IFunctionInstance *,_tagpropertykey const &,ushort * *)
0x180002b7a  jmp     loc_180002C9E
0x180002b7f  mov     r8, r14; unsigned __int16 **
0x180002b82  mov     dword ptr [rdi+28h], 0
0x180002b89  lea     rdx, PKEY_Device_FriendlyName; struct _tagpropertykey *
0x180002b90  call    ?GetFIProperty@@YAJPEAUIFunctionInstance@@AEBU_tagpropertykey@@PEAPEAG@Z; GetFIProperty(IFunctionInstance *,_tagpropertykey const &,ushort * *)
0x180002b95  test    eax, eax
0x180002b97  jns     short loc_180002BE8
0x180002b99  mov     ecx, 40h ; '@'; cb
0x180002b9e  call    cs:__imp_CoTaskMemAlloc
0x180002ba4  mov     [r14], rax
0x180002ba7  test    rax, rax
0x180002baa  jnz     short loc_180002BB6
0x180002bac  mov     ebx, 8007000Eh
0x180002bb1  jmp     loc_180002D19
0x180002bb6  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hInstance
0x180002bbd  mov     r9d, 20h ; ' '; cchBufferMax
0x180002bc3  mov     r8, rax; lpBuffer
0x180002bc6  mov     edx, 3E8h; uID
0x180002bcb  call    cs:__imp_LoadStringW
0x180002bd1  test    eax, eax
0x180002bd3  jnz     short loc_180002BE8
0x180002bd5  mov     rcx, [r14]; pv
0x180002bd8  mov     ebx, 80004005h
0x180002bdd  call    cs:__imp_CoTaskMemFree
0x180002be3  jmp     loc_180002D19
0x180002be8  lea     r8, [rdi+0C0h]; struct tagPROPVARIANT *
0x180002bef  mov     rcx, rsi; struct IFunctionInstance *
0x180002bf2  lea     rdx, PKEY_PNPX_DeviceCategory; struct _tagpropertykey *
0x180002bf9  call    ?GetFIProperty@@YAJPEAUIFunctionInstance@@AEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; GetFIProperty(IFunctionInstance *,_tagpropertykey const &,tagPROPVARIANT *)
0x180002bfe  lea     r8, [rdi+48h]; struct tagPROPVARIANT *
0x180002c02  mov     rcx, rsi; struct IFunctionInstance *
0x180002c05  lea     rdx, PKEY_PNPX_DeviceCategory_Desc; struct _tagpropertykey *
0x180002c0c  call    ?GetFIProperty@@YAJPEAUIFunctionInstance@@AEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; GetFIProperty(IFunctionInstance *,_tagpropertykey const &,tagPROPVARIANT *)
0x180002c11  lea     r8, [rdi+98h]; struct tagPROPVARIANT *
0x180002c18  mov     rcx, rsi; struct IFunctionInstance *
0x180002c1b  lea     rdx, PKEY_PNPX_CompatibleTypes; struct _tagpropertykey *
0x180002c22  call    ?GetFIProperty@@YAJPEAUIFunctionInstance@@AEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; GetFIProperty(IFunctionInstance *,_tagpropertykey const &,tagPROPVARIANT *)
0x180002c27  lea     r8, [rdi+118h]; unsigned __int16 **
0x180002c2e  mov     rcx, rsi; struct IFunctionInstance *
0x180002c31  lea     rdx, PKEY_PNPX_PresentationUrl; struct _tagpropertykey *
0x180002c38  call    ?GetFIProperty@@YAJPEAUIFunctionInstance@@AEBU_tagpropertykey@@PEAPEAG@Z; GetFIProperty(IFunctionInstance *,_tagpropertykey const &,ushort * *)
0x180002c3d  xor     edx, edx; dwBytes
0x180002c3f  mov     ecx, 2002h; uFlags
0x180002c44  call    cs:__imp_GlobalAlloc
0x180002c4a  mov     rbx, rax
0x180002c4d  test    rax, rax
0x180002c50  jz      short loc_180002C9E
0x180002c52  lea     r8, [rdi+10h]; ppstm
0x180002c56  mov     edx, 1; fDeleteOnRelease
0x180002c5b  mov     rcx, rax; hGlobal
0x180002c5e  call    cs:__imp_CreateStreamOnHGlobal
0x180002c64  test    eax, eax
0x180002c66  js      short loc_180002C95
0x180002c68  mov     rcx, [rdi+10h]; pStm
0x180002c6c  lea     rdx, _GUID_33591c10_0bed_4f02_b0ab_1530d5533ee9; riid
0x180002c73  mov     [rsp+0A8h+mshlflags], 1; mshlflags
0x180002c7b  mov     r9d, 3; dwDestContext
0x180002c81  mov     r8, rsi; pUnk
0x180002c84  mov     [rsp+0A8h+pvDestContext], 0; pvDestContext
0x180002c8d  call    cs:__imp_CoMarshalInterface
0x180002c93  jmp     short loc_180002C9E
0x180002c95  mov     rcx, rbx; hMem
0x180002c98  call    cs:__imp_GlobalFree
0x180002c9e  mov     rax, [rsi]
0x180002ca1  lea     rdx, [rdi+20h]
0x180002ca5  mov     rcx, rsi
0x180002ca8  mov     rax, [rax+20h]
0x180002cac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cb1  mov     ebx, eax
0x180002cb3  test    eax, eax
0x180002cb5  js      short loc_180002D19
0x180002cb7  movups  xmm0, xmmword ptr [r15]
0x180002cbb  lea     r8, [rdi+60h]; struct tagPROPVARIANT *
0x180002cbf  mov     rcx, rsi; struct IFunctionInstance *
0x180002cc2  lea     rdx, PKEY_PNPX_PhysicalAddress; struct _tagpropertykey *
0x180002cc9  movdqu  xmmword ptr [rdi+38h], xmm0
0x180002cce  call    ?GetFIProperty@@YAJPEAUIFunctionInstance@@AEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; GetFIProperty(IFunctionInstance *,_tagpropertykey const &,tagPROPVARIANT *)
0x180002cd3  lea     r8, [rdi+0E8h]; struct tagPROPVARIANT *
0x180002cda  mov     rcx, rsi; struct IFunctionInstance *
0x180002cdd  lea     rdx, PKEY_PNPX_IpAddress; struct _tagpropertykey *
0x180002ce4  call    ?GetFIProperty@@YAJPEAUIFunctionInstance@@AEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; GetFIProperty(IFunctionInstance *,_tagpropertykey const &,tagPROPVARIANT *)
0x180002ce9  lea     r8, [rdi+0B0h]; struct _GUID *
0x180002cf0  mov     rcx, rsi; struct IFunctionInstance *
0x180002cf3  call    ?GetFIProperty@@YAJPEAUIFunctionInstance@@AEBU_tagpropertykey@@PEAU_GUID@@@Z; GetFIProperty(IFunctionInstance *,_tagpropertykey const &,_GUID *)
0x180002cf8  lea     r8, [rdi+100h]; struct tagPROPVARIANT *
0x180002cff  mov     rcx, rsi; struct IFunctionInstance *
0x180002d02  lea     rdx, PKEY_PNPX_NetworkInterfaceLuid; struct _tagpropertykey *
0x180002d09  call    ?GetFIProperty@@YAJPEAUIFunctionInstance@@AEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; GetFIProperty(IFunctionInstance *,_tagpropertykey const &,tagPROPVARIANT *)
0x180002d0e  mov     rcx, rsi; struct IFunctionInstance *
0x180002d11  call    ?s_GetFIPriority@CNetworkItemFactory@@SAHPEAUIFunctionInstance@@@Z; CNetworkItemFactory::s_GetFIPriority(IFunctionInstance *)
0x180002d16  mov     [rdi+78h], eax
0x180002d19  mov     eax, ebx
0x180002d1b  mov     rcx, [rsp+0A8h+var_28]
0x180002d23  xor     rcx, rsp; StackCookie
0x180002d26  call    __security_check_cookie
0x180002d2b  lea     r11, [rsp+0A8h+var_18]
0x180002d33  mov     rbx, [r11+30h]
0x180002d37  mov     rsi, [r11+38h]
0x180002d3b  mov     rsp, r11
0x180002d3e  pop     r15
0x180002d40  pop     r14
0x180002d42  pop     rdi
0x180002d43  retn
```
