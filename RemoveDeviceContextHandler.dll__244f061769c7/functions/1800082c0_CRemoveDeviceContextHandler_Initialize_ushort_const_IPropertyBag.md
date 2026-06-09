# CRemoveDeviceContextHandler::Initialize(ushort const *,IPropertyBag *)

- ea: `0x1800082c0`
- end: `0x180008353`
- name: `?Initialize@CRemoveDeviceContextHandler@@UEAAJPEBGPEAUIPropertyBag@@@Z`
- size: `147`
- prototype: `__int64 __fastcall(CRemoveDeviceContextHandler *this, const unsigned __int16 *, struct IPropertyBag *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800082c0`
- `0x18000bdec`
- `0x18000be1c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000830c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000830c`

## string_xrefs

- `0x180008302`: `Windows.RemoveDevice`

## pseudocode

```c
__int64 __fastcall CRemoveDeviceContextHandler::Initialize(
        CRemoveDeviceContextHandler *this,
        const unsigned __int16 *a2,
        struct IPropertyBag *a3)
{
  unsigned int v4; // ebx
  __int64 v5; // r8

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10);
  v4 = CompareStringOrdinal(L"Windows.RemoveDevice", -1, a2, -1, 0) != 2 ? 0x8000FFFF : 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v5, v4);
  return v4;
}

```

## disassembly

```asm
0x1800082c0  mov     [rsp+arg_0], rbx
0x1800082c5  push    rdi
0x1800082c6  sub     rsp, 30h
0x1800082ca  mov     rbx, rdx
0x1800082cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800082d4  lea     rdi, WPP_GLOBAL_Control
0x1800082db  cmp     rcx, rdi
0x1800082de  jz      short loc_1800082F4
0x1800082e0  test    byte ptr [rcx+1Ch], 20h
0x1800082e4  jz      short loc_1800082F4
0x1800082e6  mov     rcx, [rcx+10h]
0x1800082ea  mov     edx, 0Ah
0x1800082ef  call    WPP_SF_
0x1800082f4  or      edx, 0FFFFFFFFh; cchCount1
0x1800082f7  mov     [rsp+38h+bIgnoreCase], 0; bIgnoreCase
0x1800082ff  mov     r9d, edx; cchCount2
0x180008302  lea     rcx, String1; "Windows.RemoveDevice"
0x180008309  mov     r8, rbx; lpString2
0x18000830c  call    cs:__imp_CompareStringOrdinal
0x180008312  mov     ecx, 2
0x180008317  sub     ecx, eax
0x180008319  neg     ecx
0x18000831b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008322  sbb     ebx, ebx
0x180008324  and     ebx, 8000FFFFh
0x18000832a  cmp     rcx, rdi
0x18000832d  jz      short loc_180008346
0x18000832f  test    byte ptr [rcx+1Ch], 20h
0x180008333  jz      short loc_180008346
0x180008335  mov     rcx, [rcx+10h]
0x180008339  mov     edx, 0Bh
0x18000833e  mov     r9d, ebx
0x180008341  call    WPP_SF_d
0x180008346  mov     eax, ebx
0x180008348  mov     rbx, [rsp+38h+arg_0]
0x18000834d  add     rsp, 30h
0x180008351  pop     rdi
0x180008352  retn
```
