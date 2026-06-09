# CClassFactory::MarshalInterface(IStream *,_GUID const &,void *,ulong,void *,ulong)

- ea: `0x140003c30`
- end: `0x140003d35`
- name: `?MarshalInterface@CClassFactory@@UEAAJPEAUIStream@@AEBU_GUID@@PEAXK2K@Z`
- size: `261`
- prototype: `__int64 __fastcall(const IID *this, struct IStream *, const struct _GUID *, void *, DWORD dwDestContext, void *pvDestContext, DWORD mshlflags)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140003040`
- `0x140003c30`
- `0x140011010`

## import_xrefs

- `ole32!CoMarshalInterface` at `0x140003ce1`
- `ole32!CoMarshalInterface` at `0x140003ce1`
- `ole32!CoGetClassObject` at `0x140003c68`
- `ole32!CoGetClassObject` at `0x140003c68`

## pseudocode

```c
__int64 __fastcall CClassFactory::MarshalInterface(
        const IID *this,
        struct IStream *a2,
        const struct _GUID *a3,
        void *a4,
        DWORD dwDestContext,
        void *pvDestContext,
        DWORD mshlflags)
{
  HRESULT ClassObject; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  LPUNKNOWN pUnk; // [rsp+40h] [rbp+8h] BYREF

  pUnk = 0;
  ClassObject = CoGetClassObject(this + 1, 1u, 0, &IID_IUnknown, (LPVOID *)&pUnk);
  if ( ClassObject < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v11 = 11;
LABEL_5:
      WPP_SF_d(v10[2], v11, WPP_f2a66fa2f7dd318b6912da7823821443_Traceguids, (unsigned int)ClassObject);
      goto LABEL_6;
    }
    goto LABEL_6;
  }
  ClassObject = CoMarshalInterface(a2, a3, pUnk, dwDestContext, pvDestContext, mshlflags);
  if ( ClassObject < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v11 = 12;
      goto LABEL_5;
    }
LABEL_6:
    if ( pUnk )
      ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
    return (unsigned int)ClassObject;
  }
  if ( pUnk )
    ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
  return 0;
}

```

## disassembly

```asm
0x140003c30  mov     r11, rsp
0x140003c33  mov     [r11+10h], rbx
0x140003c37  mov     [r11+18h], rsi
0x140003c3b  push    rdi
0x140003c3c  sub     rsp, 30h
0x140003c40  mov     rdi, r8
0x140003c43  mov     qword ptr [r11+8], 0
0x140003c4b  xor     r8d, r8d; pvReserved
0x140003c4e  lea     rax, [r11+8]
0x140003c52  mov     rsi, rdx
0x140003c55  mov     [r11-18h], rax
0x140003c59  add     rcx, 10h; rclsid
0x140003c5d  lea     r9, IID_IUnknown; riid
0x140003c64  lea     edx, [r8+1]; dwClsContext
0x140003c68  call    cs:__imp_CoGetClassObject
0x140003c6e  mov     ebx, eax
0x140003c70  test    eax, eax
0x140003c72  jns     short loc_140003CBF
0x140003c74  mov     rcx, cs:WPP_GLOBAL_Control
0x140003c7b  lea     rdx, WPP_GLOBAL_Control
0x140003c82  cmp     rcx, rdx
0x140003c85  jz      short loc_140003CA5
0x140003c87  test    byte ptr [rcx+1Ch], 1
0x140003c8b  jz      short loc_140003CA5
0x140003c8d  mov     edx, 0Bh
0x140003c92  mov     rcx, [rcx+10h]
0x140003c96  lea     r8, WPP_f2a66fa2f7dd318b6912da7823821443_Traceguids
0x140003c9d  mov     r9d, ebx
0x140003ca0  call    WPP_SF_d
0x140003ca5  mov     rcx, [rsp+38h+pUnk]
0x140003caa  test    rcx, rcx
0x140003cad  jz      short loc_140003CBB
0x140003caf  mov     rax, [rcx]
0x140003cb2  mov     rax, [rax+10h]
0x140003cb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003cbb  mov     eax, ebx
0x140003cbd  jmp     short loc_140003D25
0x140003cbf  mov     eax, [rsp+38h+arg_30]
0x140003cc3  mov     rdx, rdi; riid
0x140003cc6  mov     r9d, [rsp+38h+dwDestContext]; dwDestContext
0x140003ccb  mov     rcx, rsi; pStm
0x140003cce  mov     r8, [rsp+38h+pUnk]; pUnk
0x140003cd3  mov     [rsp+38h+mshlflags], eax; mshlflags
0x140003cd7  mov     rax, [rsp+38h+arg_28]
0x140003cdc  mov     [rsp+38h+pvDestContext], rax; pvDestContext
0x140003ce1  call    cs:__imp_CoMarshalInterface
0x140003ce7  mov     ebx, eax
0x140003ce9  test    eax, eax
0x140003ceb  jns     short loc_140003D0D
0x140003ced  mov     rcx, cs:WPP_GLOBAL_Control
0x140003cf4  lea     rdx, WPP_GLOBAL_Control
0x140003cfb  cmp     rcx, rdx
0x140003cfe  jz      short loc_140003CA5
0x140003d00  test    byte ptr [rcx+1Ch], 1
0x140003d04  jz      short loc_140003CA5
0x140003d06  mov     edx, 0Ch
0x140003d0b  jmp     short loc_140003C92
0x140003d0d  mov     rcx, [rsp+38h+pUnk]
0x140003d12  test    rcx, rcx
0x140003d15  jz      short loc_140003D23
0x140003d17  mov     rax, [rcx]
0x140003d1a  mov     rax, [rax+10h]
0x140003d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d23  xor     eax, eax
0x140003d25  mov     rbx, [rsp+38h+arg_8]
0x140003d2a  mov     rsi, [rsp+38h+arg_10]
0x140003d2f  add     rsp, 30h
0x140003d33  pop     rdi
0x140003d34  retn
```
