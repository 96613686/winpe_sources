# CMetadataHandler::GetEnumerator(IWICEnumMetadataItem * *)

- ea: `0x18002be80`
- end: `0x18002bf7c`
- name: `?GetEnumerator@CMetadataHandler@@UEAAJPEAPEAUIWICEnumMetadataItem@@@Z`
- size: `252`
- prototype: `__int64 __fastcall(struct IWICMetadataReader *this, struct IWICEnumMetadataItem **)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800058c0`
- `0x180008c00`
- `0x180008d60`
- `0x180009f30`
- `0x18000f1d0`
- `0x1800171c4`
- `0x1800215e8`
- `0x18002be80`
- `0x18002d930`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CMetadataHandler::GetEnumerator(struct IWICMetadataReader *this, struct IWICEnumMetadataItem **a2)
{
  unsigned int v4; // ebx
  CEnumMetadataItem *v5; // rax
  CMILCOMBase *v6; // rax
  const unsigned __int16 *v7; // rdx
  const unsigned __int16 *v8; // r8
  const unsigned __int16 *v9; // r9
  CMILCOMBase *v10; // rdi
  int v11; // eax
  void *v13; // [rsp+30h] [rbp+8h] BYREF
  struct IWICMetadataReader *v14; // [rsp+40h] [rbp+18h] BYREF

  v13 = 0;
  v14 = this + 5;
  CMTALock::Enter((CMTALock *)&this[5]);
  if ( !a2 )
  {
    v4 = -2147024809;
    goto LABEL_12;
  }
  v5 = (CEnumMetadataItem *)operator new(0x68u);
  if ( !v5 || (v6 = CEnumMetadataItem::CEnumMetadataItem(v5, this), (v10 = v6) == 0) )
  {
    v4 = -2147024882;
LABEL_12:
    if ( g_doStackCaptures )
      DoStackCapture(v4);
    goto LABEL_14;
  }
  CMILCOMBase::InternalAddRef(v6, v7, v8, v9);
  v11 = CMILCOMBase::InternalQueryInterface(v10, &IID_IWICEnumMetadataItem, &v13);
  v4 = v11;
  if ( v11 >= 0 )
  {
    *a2 = (struct IWICEnumMetadataItem *)v13;
    v13 = 0;
  }
  else if ( g_doStackCaptures )
  {
    DoStackCapture(v11);
  }
  CMILCOMBase::InternalRelease(v10);
LABEL_14:
  if ( v13 )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)v13 + 16LL))(v13);
    v13 = 0;
  }
  CGuard<CMTALock>::~CGuard<CMTALock>(&v14);
  return v4;
}

```

## disassembly

```asm
0x18002be80  mov     rax, rsp
0x18002be83  mov     [rax+10h], rbx
0x18002be87  mov     [rax+20h], rsi
0x18002be8b  push    rdi
0x18002be8c  sub     rsp, 20h
0x18002be90  mov     rbx, rcx
0x18002be93  mov     qword ptr [rax+8], 0
0x18002be9b  add     rcx, 28h ; '('; this
0x18002be9f  mov     rsi, rdx
0x18002bea2  mov     [rax+18h], rcx
0x18002bea6  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x18002beab  test    rsi, rsi
0x18002beae  jnz     short loc_18002BEB7
0x18002beb0  mov     ebx, 80070057h
0x18002beb5  jmp     short loc_18002BF31
0x18002beb7  mov     ecx, 68h ; 'h'; Size
0x18002bebc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002bec1  test    rax, rax
0x18002bec4  jz      short loc_18002BF2C
0x18002bec6  mov     rdx, rbx; struct IWICMetadataReader *
0x18002bec9  mov     rcx, rax; this
0x18002becc  call    ??0CEnumMetadataItem@@QEAA@PEAUIWICMetadataReader@@@Z; CEnumMetadataItem::CEnumMetadataItem(IWICMetadataReader *)
0x18002bed1  mov     rdi, rax
0x18002bed4  test    rax, rax
0x18002bed7  jz      short loc_18002BF2C
0x18002bed9  mov     rcx, rax; this
0x18002bedc  call    ?InternalAddRef@CMILCOMBase@@QEAAKXZ; CMILCOMBase::InternalAddRef(void)
0x18002bee1  lea     r8, [rsp+28h+arg_0]; void **
0x18002bee6  mov     rcx, rdi; this
0x18002bee9  lea     rdx, IID_IWICEnumMetadataItem; struct _GUID *
0x18002bef0  call    ?InternalQueryInterface@CMILCOMBase@@QEAAJAEBU_GUID@@PEAPEAX@Z; CMILCOMBase::InternalQueryInterface(_GUID const &,void * *)
0x18002bef5  mov     ebx, eax
0x18002bef7  test    eax, eax
0x18002bef9  jns     short loc_18002BF11
0x18002befb  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18002bf02  jz      short loc_18002BF0D
0x18002bf04  mov     ecx, eax; int
0x18002bf06  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18002bf0b  jmp     short loc_18002BF22
0x18002bf0d  test    eax, eax
0x18002bf0f  js      short loc_18002BF22
0x18002bf11  mov     rax, [rsp+28h+arg_0]
0x18002bf16  mov     [rsi], rax
0x18002bf19  mov     [rsp+28h+arg_0], 0
0x18002bf22  mov     rcx, rdi; this
0x18002bf25  call    ?InternalRelease@CMILCOMBase@@QEAAKXZ; CMILCOMBase::InternalRelease(void)
0x18002bf2a  jmp     short loc_18002BF41
0x18002bf2c  mov     ebx, 8007000Eh
0x18002bf31  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18002bf38  jz      short loc_18002BF41
0x18002bf3a  mov     ecx, ebx; int
0x18002bf3c  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18002bf41  mov     rcx, [rsp+28h+arg_0]
0x18002bf46  test    rcx, rcx
0x18002bf49  jz      short loc_18002BF60
0x18002bf4b  mov     rdx, [rcx]
0x18002bf4e  mov     rax, [rdx+10h]
0x18002bf52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bf57  mov     [rsp+28h+arg_0], 0
0x18002bf60  lea     rcx, [rsp+28h+arg_10]
0x18002bf65  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x18002bf6a  mov     rsi, [rsp+28h+arg_18]
0x18002bf6f  mov     eax, ebx
0x18002bf71  mov     rbx, [rsp+28h+arg_8]
0x18002bf76  add     rsp, 20h
0x18002bf7a  pop     rdi
0x18002bf7b  retn
```
