# CNetworkItemFactory::_AddNewItem(IFunctionInstance *,CNetworkItem * *)

- ea: `0x180003d28`
- end: `0x180003faa`
- name: `?_AddNewItem@CNetworkItemFactory@@AEAAJPEAUIFunctionInstance@@PEAPEAVCNetworkItem@@@Z`
- size: `642`
- prototype: `__int64 __fastcall(CProfileCache **this, struct IFunctionInstance *, struct CNetworkItem **)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000488c`
- `0x18000531c`

## callees

- `0x180002ab8`
- `0x180003d28`
- `0x18000442c`
- `0x18000542c`
- `0x180005c50`
- `0x180006438`
- `0x1800070c8`
- `0x1800070f4`
- `0x18000842c`
- `0x18000a7a7`
- `0x18000a7d0`
- `0x18000b010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180003f07`
- `ole32!CoTaskMemFree` at `0x180003f1a`
- `ole32!CoTaskMemFree` at `0x180003f47`
- `ole32!CoTaskMemFree` at `0x180003f5a`
- `ole32!CoTaskMemFree` at `0x180003f07`
- `ole32!CoTaskMemFree` at `0x180003f1a`
- `ole32!CoTaskMemFree` at `0x180003f47`
- `ole32!CoTaskMemFree` at `0x180003f5a`

## pseudocode

```c
__int64 __fastcall CNetworkItemFactory::_AddNewItem(
        CProfileCache **this,
        struct IFunctionInstance *a2,
        struct CNetworkItem **a3)
{
  _DWORD *v6; // rax
  _DWORD *v7; // rdi
  signed int ComputerNameAlloc; // ebx
  struct IDToNetworkItemRecord *Item; // rax
  struct IDToNetworkItemRecord *v10; // rsi
  struct IDToNetworkItemRecord *v11; // rax
  struct IDToNetworkItemRecord *v12; // r14
  int v14; // [rsp+20h] [rbp-30h] BYREF
  LPVOID pv[2]; // [rsp+28h] [rbp-28h] BYREF
  struct _GUID v16; // [rsp+38h] [rbp-18h] BYREF

  *(GUID *)pv = GUID_NULL;
  if ( this[17] )
  {
    v16 = 0;
    if ( GetFIProperty(a2, (const struct _tagpropertykey *)a2, &v16) >= 0 )
      CProfileCache::GetProfileGuid(this[17], &v16, (struct _GUID *)pv);
  }
  v6 = operator new(0x120u);
  v7 = v6;
  if ( v6 )
  {
    memset_0(v6, 0, 0x120u);
    _InterlockedIncrement(&g_cRefThisDll);
    *(_QWORD *)v7 = &CNetworkItem::`vftable';
    v7[2] = 1;
    *((_QWORD *)v7 + 2) = 0;
    *((_QWORD *)v7 + 3) = 0;
    *((_QWORD *)v7 + 4) = 0;
    *((_QWORD *)v7 + 6) = 0;
    *((_QWORD *)v7 + 27) = 0;
    ComputerNameAlloc = CNetworkItem::Init((CNetworkItem *)v7, a2, (const struct _GUID *)pv);
    if ( ComputerNameAlloc >= 0 )
    {
      *(_QWORD *)&v16.Data1 = 0;
      ComputerNameAlloc = ((__int64 (__fastcall *)(struct IFunctionInstance *, struct _GUID *))a2->lpVtbl->GetID)(
                            a2,
                            &v16);
      if ( ComputerNameAlloc >= 0 )
      {
        Item = CNetworkItemFactory::s_CreateItem(*(const unsigned __int16 **)&v16.Data1, (struct CNetworkItem *)v7);
        v10 = Item;
        if ( Item )
        {
          if ( (unsigned int)LKRhash::CLKRHashTable::InsertRecord(this[10], Item) )
          {
            ComputerNameAlloc = -2147467259;
          }
          else
          {
            ComputerNameAlloc = 0;
            v14 = 0;
            (*(void (__fastcall **)(_DWORD *, int *))(*(_QWORD *)v7 + 48LL))(v7, &v14);
            if ( v14 )
            {
              pv[0] = 0;
              ComputerNameAlloc = CNetworkItemFactory::_GetComputerNameAlloc(
                                    (struct INetworkItem *)v7,
                                    (unsigned __int16 **)pv);
              if ( ComputerNameAlloc >= 0 )
              {
                v11 = CNetworkItemFactory::s_CreateItem((const unsigned __int16 *)pv[0], (struct CNetworkItem *)v7);
                v12 = v11;
                if ( v11 )
                {
                  ComputerNameAlloc = (unsigned int)LKRhash::CLKRHashTable::InsertRecord(this[11], v11) != 0
                                    ? 0x80004005
                                    : 0;
                  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 + 4, 0xFFFFFFFF) == 1 )
                  {
                    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v12 + 1) + 16LL))(*((_QWORD *)v12 + 1));
                    CoTaskMemFree(*(LPVOID *)v12);
                    operator delete(v12);
                  }
                }
                else
                {
                  ComputerNameAlloc = -2147024882;
                }
                CoTaskMemFree(pv[0]);
              }
            }
          }
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v10 + 4, 0xFFFFFFFF) == 1 )
          {
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v10 + 1) + 16LL))(*((_QWORD *)v10 + 1));
            CoTaskMemFree(*(LPVOID *)v10);
            operator delete(v10);
          }
        }
        else
        {
          ComputerNameAlloc = -2147024882;
        }
        CoTaskMemFree(*(LPVOID *)&v16.Data1);
      }
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v7 + 16LL))(v7);
      if ( ComputerNameAlloc >= 0 )
      {
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v7 + 8LL))(v7);
        *a3 = (struct CNetworkItem *)v7;
      }
    }
    else
    {
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v7 + 16LL))(v7);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)ComputerNameAlloc;
}

```

## disassembly

```asm
0x180003d28  push    rbp
0x180003d2a  push    rbx
0x180003d2b  push    rsi
0x180003d2c  push    rdi
0x180003d2d  push    r12
0x180003d2f  push    r14
0x180003d31  push    r15
0x180003d33  mov     rbp, rsp
0x180003d36  sub     rsp, 50h
0x180003d3a  mov     rax, cs:__security_cookie
0x180003d41  xor     rax, rsp
0x180003d44  mov     [rbp+var_8], rax
0x180003d48  mov     r12, r8
0x180003d4b  mov     rsi, rdx
0x180003d4e  mov     r15, rcx
0x180003d51  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180003d58  movdqu  xmmword ptr [rbp+pv], xmm0
0x180003d5d  cmp     qword ptr [rcx+88h], 0
0x180003d65  jz      short loc_180003D92
0x180003d67  xorps   xmm0, xmm0
0x180003d6a  movups  xmmword ptr [rbp+var_18.Data1], xmm0
0x180003d6e  lea     r8, [rbp+var_18]; struct _GUID *
0x180003d72  mov     rcx, rdx; struct IFunctionInstance *
0x180003d75  call    ?GetFIProperty@@YAJPEAUIFunctionInstance@@AEBU_tagpropertykey@@PEAU_GUID@@@Z; GetFIProperty(IFunctionInstance *,_tagpropertykey const &,_GUID *)
0x180003d7a  test    eax, eax
0x180003d7c  js      short loc_180003D92
0x180003d7e  lea     r8, [rbp+pv]; struct _GUID *
0x180003d82  lea     rdx, [rbp+var_18]; struct _GUID *
0x180003d86  mov     rcx, [r15+88h]; this
0x180003d8d  call    ?GetProfileGuid@CProfileCache@@QEAAJAEBU_GUID@@PEAU2@@Z; CProfileCache::GetProfileGuid(_GUID const &,_GUID *)
0x180003d92  mov     ebx, 120h
0x180003d97  mov     ecx, ebx; unsigned __int64
0x180003d99  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003d9e  mov     rdi, rax
0x180003da1  test    rax, rax
0x180003da4  jz      loc_180003F88
0x180003daa  mov     r8d, ebx; Size
0x180003dad  xor     edx, edx; Val
0x180003daf  mov     rcx, rax; void *
0x180003db2  call    memset_0
0x180003db7  lock inc cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x180003dbe  lea     rax, ??_7CNetworkItem@@6B@; const CNetworkItem::`vftable'
0x180003dc5  mov     [rdi], rax
0x180003dc8  mov     dword ptr [rdi+8], 1
0x180003dcf  mov     qword ptr [rdi+10h], 0
0x180003dd7  mov     qword ptr [rdi+18h], 0
0x180003ddf  mov     qword ptr [rdi+20h], 0
0x180003de7  mov     qword ptr [rdi+30h], 0
0x180003def  mov     qword ptr [rdi+0D8h], 0
0x180003dfa  lea     r8, [rbp+pv]; struct _GUID *
0x180003dfe  mov     rdx, rsi; struct IFunctionInstance *
0x180003e01  mov     rcx, rdi; this
0x180003e04  call    ?Init@CNetworkItem@@QEAAJPEAUIFunctionInstance@@AEBU_GUID@@@Z; CNetworkItem::Init(IFunctionInstance *,_GUID const &)
0x180003e09  mov     ebx, eax
0x180003e0b  test    eax, eax
0x180003e0d  jns     short loc_180003E23
0x180003e0f  mov     rax, [rdi]
0x180003e12  mov     rcx, rdi
0x180003e15  mov     rax, [rax+10h]
0x180003e19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e1e  jmp     loc_180003F8D
0x180003e23  mov     qword ptr [rbp+var_18.Data1], 0
0x180003e2b  mov     rax, [rsi]
0x180003e2e  lea     rdx, [rbp+var_18]
0x180003e32  mov     rcx, rsi
0x180003e35  mov     rax, [rax+20h]
0x180003e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e3e  mov     ebx, eax
0x180003e40  test    eax, eax
0x180003e42  js      loc_180003F60
0x180003e48  mov     rdx, rdi; struct CNetworkItem *
0x180003e4b  mov     rcx, qword ptr [rbp+var_18.Data1]; unsigned __int16 *
0x180003e4f  call    ?s_CreateItem@CNetworkItemFactory@@CAPEAVIDToNetworkItemRecord@@PEBGPEAVCNetworkItem@@@Z; CNetworkItemFactory::s_CreateItem(ushort const *,CNetworkItem *)
0x180003e54  mov     rsi, rax
0x180003e57  test    rax, rax
0x180003e5a  jnz     short loc_180003E66
0x180003e5c  mov     ebx, 8007000Eh
0x180003e61  jmp     loc_180003F56
0x180003e66  mov     rdx, rsi
0x180003e69  mov     rcx, [r15+50h]
0x180003e6d  call    ?InsertRecord@CLKRHashTable@LKRhash@@QEAA?AW4LK_RETCODE@2@PEBX_NPEAPEBX@Z; LKRhash::CLKRHashTable::InsertRecord(void const *,bool,void const * *)
0x180003e72  test    eax, eax
0x180003e74  jnz     loc_180003F22
0x180003e7a  xor     ebx, ebx
0x180003e7c  mov     [rbp+var_30], ebx
0x180003e7f  mov     rax, [rdi]
0x180003e82  lea     rdx, [rbp+var_30]
0x180003e86  mov     rcx, rdi
0x180003e89  mov     rax, [rax+30h]
0x180003e8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e92  cmp     [rbp+var_30], ebx
0x180003e95  jz      loc_180003F27
0x180003e9b  mov     [rbp+pv], rbx
0x180003e9f  lea     rdx, [rbp+pv]; unsigned __int16 **
0x180003ea3  mov     rcx, rdi; struct INetworkItem *
0x180003ea6  call    ?_GetComputerNameAlloc@CNetworkItemFactory@@CAJPEAUINetworkItem@@PEAPEAG@Z; CNetworkItemFactory::_GetComputerNameAlloc(INetworkItem *,ushort * *)
0x180003eab  mov     ebx, eax
0x180003ead  test    eax, eax
0x180003eaf  js      short loc_180003F27
0x180003eb1  mov     rdx, rdi; struct CNetworkItem *
0x180003eb4  mov     rcx, [rbp+pv]; unsigned __int16 *
0x180003eb8  call    ?s_CreateItem@CNetworkItemFactory@@CAPEAVIDToNetworkItemRecord@@PEBGPEAVCNetworkItem@@@Z; CNetworkItemFactory::s_CreateItem(ushort const *,CNetworkItem *)
0x180003ebd  mov     r14, rax
0x180003ec0  test    rax, rax
0x180003ec3  jnz     short loc_180003ECC
0x180003ec5  mov     ebx, 8007000Eh
0x180003eca  jmp     short loc_180003F16
0x180003ecc  mov     rdx, r14
0x180003ecf  mov     rcx, [r15+58h]
0x180003ed3  call    ?InsertRecord@CLKRHashTable@LKRhash@@QEAA?AW4LK_RETCODE@2@PEBX_NPEAPEBX@Z; LKRhash::CLKRHashTable::InsertRecord(void const *,bool,void const * *)
0x180003ed8  xor     ecx, ecx
0x180003eda  sub     ecx, eax
0x180003edc  neg     ecx
0x180003ede  sbb     ebx, ebx
0x180003ee0  and     ebx, 80004005h
0x180003ee6  or      eax, 0FFFFFFFFh
0x180003ee9  lock xadd [r14+10h], eax
0x180003eef  cmp     eax, 1
0x180003ef2  jnz     short loc_180003F16
0x180003ef4  mov     rcx, [r14+8]
0x180003ef8  mov     rax, [rcx]
0x180003efb  mov     rax, [rax+10h]
0x180003eff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f04  mov     rcx, [r14]; pv
0x180003f07  call    cs:__imp_CoTaskMemFree
0x180003f0d  nop
0x180003f0e  mov     rcx, r14; lpMem
0x180003f11  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003f16  mov     rcx, [rbp+pv]; pv
0x180003f1a  call    cs:__imp_CoTaskMemFree
0x180003f20  jmp     short loc_180003F27
0x180003f22  mov     ebx, 80004005h
0x180003f27  or      eax, 0FFFFFFFFh
0x180003f2a  lock xadd [rsi+10h], eax
0x180003f2f  cmp     eax, 1
0x180003f32  jnz     short loc_180003F56
0x180003f34  mov     rcx, [rsi+8]
0x180003f38  mov     rax, [rcx]
0x180003f3b  mov     rax, [rax+10h]
0x180003f3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f44  mov     rcx, [rsi]; pv
0x180003f47  call    cs:__imp_CoTaskMemFree
0x180003f4d  nop
0x180003f4e  mov     rcx, rsi; lpMem
0x180003f51  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003f56  mov     rcx, qword ptr [rbp+var_18.Data1]; pv
0x180003f5a  call    cs:__imp_CoTaskMemFree
0x180003f60  mov     rax, [rdi]
0x180003f63  mov     rcx, rdi
0x180003f66  mov     rax, [rax+10h]
0x180003f6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f6f  test    ebx, ebx
0x180003f71  js      short loc_180003F8D
0x180003f73  mov     rax, [rdi]
0x180003f76  mov     rcx, rdi
0x180003f79  mov     rax, [rax+8]
0x180003f7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f82  mov     [r12], rdi
0x180003f86  jmp     short loc_180003F8D
0x180003f88  mov     ebx, 8007000Eh
0x180003f8d  mov     eax, ebx
0x180003f8f  mov     rcx, [rbp+var_8]
0x180003f93  xor     rcx, rsp; StackCookie
0x180003f96  call    __security_check_cookie
0x180003f9b  add     rsp, 50h
0x180003f9f  pop     r15
0x180003fa1  pop     r14
0x180003fa3  pop     r12
0x180003fa5  pop     rdi
0x180003fa6  pop     rsi
0x180003fa7  pop     rbx
0x180003fa8  pop     rbp
0x180003fa9  retn
```
