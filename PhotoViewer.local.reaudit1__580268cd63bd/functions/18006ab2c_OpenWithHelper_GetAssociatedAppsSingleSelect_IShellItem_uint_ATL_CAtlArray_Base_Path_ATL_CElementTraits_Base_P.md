# OpenWithHelper::GetAssociatedAppsSingleSelect(IShellItem *,uint,ATL::CAtlArray<Base::Path,ATL::CElementTraits<Base::Path>> const &,ATL::CAtlArray<Base::PtrRef<OpenWithHelper::AssociatedAppInfo>,ATL::CElementTraits<Base::PtrRef<OpenWithHelper::AssociatedAppInfo>>> &)

- ea: `0x18006ab2c`
- end: `0x18006acc4`
- name: `?GetAssociatedAppsSingleSelect@OpenWithHelper@@CA_NPEAUIShellItem@@IAEBV?$CAtlArray@VPath@Base@@V?$CElementTraits@VPath@Base@@@ATL@@@ATL@@AEAV?$CAtlArray@V?$PtrRef@VAssociatedAppInfo@OpenWithHelper@@@Base@@V?$CElementTraits@V?$PtrRef@VAssociatedAppInfo@OpenWithHelper@@@Base@@@ATL@@@4@@Z`
- size: `408`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006aa70`

## callees

- `0x1800032b4`
- `0x18000cb74`
- `0x18000d850`
- `0x1800274f0`
- `0x18006a948`
- `0x18006ab2c`
- `0x180080010`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x18006abfc`
- `SHLWAPI!PathFindFileNameW` at `0x18006abfc`
- `SHLWAPI!PathMatchSpecW` at `0x18006ac23`
- `SHLWAPI!PathMatchSpecW` at `0x18006ac23`
- `PhotoBase!?BaseAtlThrow@ATL@@YAXJ@Z` at `0x18006ac86`
- `PhotoBase!?BaseAtlThrow@ATL@@YAXJ@Z` at `0x18006ac92`
- `PhotoBase!?BaseAtlThrow@ATL@@YAXJ@Z` at `0x18006ac86`
- `PhotoBase!?BaseAtlThrow@ATL@@YAXJ@Z` at `0x18006ac92`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall OpenWithHelper::GetAssociatedAppsSingleSelect(__int64 a1, unsigned int a2, _QWORD *a3, _QWORD *a4)
{
  unsigned int v7; // ebp
  struct OpenWithHelper::AssociatedAppInfo *v8; // rax
  struct OpenWithHelper::AssociatedAppInfo *v9; // rbx
  const WCHAR *FileNameW; // r15
  unsigned __int64 v11; // r14
  unsigned __int64 i; // rdi
  char v13; // al
  unsigned __int64 v14; // rdi
  _QWORD v16[11]; // [rsp+30h] [rbp-58h] BYREF
  struct IUnknown *v17; // [rsp+90h] [rbp+8h] BYREF

  v16[0] = 0;
  if ( (*(int (__fastcall **)(__int64, _QWORD, const GUID *, GUID *, _QWORD *))(*(_QWORD *)a1 + 24LL))(
         a1,
         0,
         &BHID_EnumAssocHandlers,
         &GUID_973810ae_9599_4b88_9e4d_6ee98c9552da,
         v16) >= 0 )
  {
    v17 = 0;
    v7 = 0;
    while ( !(*(unsigned int (__fastcall **)(_QWORD, __int64, struct IUnknown **))(*(_QWORD *)v16[0] + 24LL))(
               v16[0],
               1,
               &v17)
         && v7 < a2 )
    {
      v8 = OpenWithHelper::AssociatedAppInfo::Create((struct IAssocHandler *)v17);
      v9 = v8;
      v16[1] = v8;
      if ( v8 )
        ++*((_DWORD *)v8 + 2);
      if ( v17 )
        ATL::AtlComPtrAssign(&v17, 0);
      if ( v9 )
      {
        FileNameW = PathFindFileNameW(*((LPCWSTR *)v9 + 4));
        v11 = a3[1];
        for ( i = 0; i < v11; ++i )
        {
          if ( i >= a3[1] )
          {
            ATL::BaseAtlThrow(-2147024809);
            goto LABEL_26;
          }
          if ( PathMatchSpecW(FileNameW, *(LPCWSTR *)(*a3 + 8 * i)) )
          {
            v13 = 1;
            goto LABEL_17;
          }
        }
        v13 = 0;
LABEL_17:
        if ( v13 )
          goto LABEL_23;
        v14 = a4[1];
        if ( v14 >= a4[2]
          && !(unsigned __int8)ATL::CAtlArray<Base::PtrRef<OpenWithHelper::AssociatedAppInfo>,ATL::CElementTraits<Base::PtrRef<OpenWithHelper::AssociatedAppInfo>>>::GrowBuffer(
                                 a4,
                                 v14 + 1) )
        {
LABEL_26:
          ATL::BaseAtlThrow(-2147024882);
          break;
        }
        *(_QWORD *)(*a4 + 8 * v14) = v9;
        ++*((_DWORD *)v9 + 2);
        ++a4[1];
        ++v7;
      }
LABEL_23:
      if ( v9 )
        Base::RefCountBase::BaseRelease(v9);
    }
    ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v17);
  }
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(v16);
  return 1;
}

```

## disassembly

```asm
0x18006ab2c  push    rbx
0x18006ab2e  push    rbp
0x18006ab2f  push    rsi
0x18006ab30  push    rdi
0x18006ab31  push    r12
0x18006ab33  push    r13
0x18006ab35  push    r14
0x18006ab37  push    r15
0x18006ab39  sub     rsp, 48h
0x18006ab3d  mov     rsi, r9
0x18006ab40  mov     r12, r8
0x18006ab43  mov     r13d, edx
0x18006ab46  mov     [rsp+88h+var_58], 0
0x18006ab4f  mov     rax, [rcx]
0x18006ab52  lea     rdx, [rsp+88h+var_58]
0x18006ab57  mov     [rsp+88h+var_68], rdx
0x18006ab5c  lea     r9, _GUID_973810ae_9599_4b88_9e4d_6ee98c9552da
0x18006ab63  lea     r8, BHID_EnumAssocHandlers
0x18006ab6a  xor     edx, edx
0x18006ab6c  mov     rax, [rax+18h]
0x18006ab70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ab75  test    eax, eax
0x18006ab77  js      loc_18006ACA7
0x18006ab7d  mov     [rsp+88h+arg_0], 0
0x18006ab89  xor     ebp, ebp
0x18006ab8b  mov     rcx, [rsp+88h+var_58]
0x18006ab90  mov     rax, [rcx]
0x18006ab93  xor     r9d, r9d
0x18006ab96  lea     r8, [rsp+88h+arg_0]
0x18006ab9e  lea     edx, [r9+1]
0x18006aba2  mov     rax, [rax+18h]
0x18006aba6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006abab  test    eax, eax
0x18006abad  jnz     loc_18006AC99
0x18006abb3  cmp     ebp, r13d
0x18006abb6  jnb     loc_18006AC99
0x18006abbc  mov     rcx, [rsp+88h+arg_0]; struct IAssocHandler *
0x18006abc4  call    ?Create@AssociatedAppInfo@OpenWithHelper@@SAPEAV12@PEAUIAssocHandler@@@Z; OpenWithHelper::AssociatedAppInfo::Create(IAssocHandler *)
0x18006abc9  mov     rbx, rax
0x18006abcc  mov     [rsp+88h+var_50], rax
0x18006abd1  test    rax, rax
0x18006abd4  jz      short loc_18006ABD9
0x18006abd6  inc     dword ptr [rax+8]
0x18006abd9  cmp     [rsp+88h+arg_0], 0
0x18006abe2  jz      short loc_18006ABF3
0x18006abe4  xor     edx, edx; struct IUnknown *
0x18006abe6  lea     rcx, [rsp+88h+arg_0]; struct IUnknown **
0x18006abee  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18006abf3  test    rbx, rbx
0x18006abf6  jz      short loc_18006AC6B
0x18006abf8  mov     rcx, [rbx+20h]; pszPath
0x18006abfc  call    cs:__imp_PathFindFileNameW
0x18006ac02  mov     r15, rax
0x18006ac05  mov     r14, [r12+8]
0x18006ac0a  xor     edi, edi
0x18006ac0c  cmp     rdi, r14
0x18006ac0f  jnb     short loc_18006AC36
0x18006ac11  cmp     rdi, [r12+8]
0x18006ac16  jnb     short loc_18006AC81
0x18006ac18  mov     rdx, [r12]
0x18006ac1c  mov     rdx, [rdx+rdi*8]; pszSpec
0x18006ac20  mov     rcx, r15; pszFile
0x18006ac23  call    cs:__imp_PathMatchSpecW
0x18006ac29  test    eax, eax
0x18006ac2b  jnz     short loc_18006AC32
0x18006ac2d  inc     rdi
0x18006ac30  jmp     short loc_18006AC0C
0x18006ac32  mov     al, 1
0x18006ac34  jmp     short loc_18006AC38
0x18006ac36  xor     al, al
0x18006ac38  test    al, al
0x18006ac3a  jnz     short loc_18006AC6B
0x18006ac3c  mov     rdi, [rsi+8]
0x18006ac40  cmp     rdi, [rsi+10h]
0x18006ac44  jb      short loc_18006AC56
0x18006ac46  lea     rdx, [rdi+1]
0x18006ac4a  mov     rcx, rsi
0x18006ac4d  call    ?GrowBuffer@?$CAtlArray@V?$PtrRef@VAssociatedAppInfo@OpenWithHelper@@@Base@@V?$CElementTraits@V?$PtrRef@VAssociatedAppInfo@OpenWithHelper@@@Base@@@ATL@@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<Base::PtrRef<OpenWithHelper::AssociatedAppInfo>,ATL::CElementTraits<Base::PtrRef<OpenWithHelper::AssociatedAppInfo>>>::GrowBuffer(unsigned __int64)
0x18006ac52  test    al, al
0x18006ac54  jz      short loc_18006AC8D
0x18006ac56  mov     rax, [rsi]
0x18006ac59  mov     [rax+rdi*8], rbx
0x18006ac5d  test    rbx, rbx
0x18006ac60  jz      short loc_18006AC65
0x18006ac62  inc     dword ptr [rbx+8]
0x18006ac65  inc     qword ptr [rsi+8]
0x18006ac69  inc     ebp
0x18006ac6b  test    rbx, rbx
0x18006ac6e  jz      loc_18006AB8B
0x18006ac74  mov     rcx, rbx; this
0x18006ac77  call    ?BaseRelease@RefCountBase@Base@@QEAAKXZ; Base::RefCountBase::BaseRelease(void)
0x18006ac7c  jmp     loc_18006AB8B
0x18006ac81  mov     ecx, 80070057h
0x18006ac86  call    cs:__imp_?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18006ac8c  nop
0x18006ac8d  mov     ecx, 8007000Eh
0x18006ac92  call    cs:__imp_?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18006ac98  nop
0x18006ac99  lea     rcx, [rsp+88h+arg_0]
0x18006aca1  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18006aca6  nop
0x18006aca7  lea     rcx, [rsp+88h+var_58]
0x18006acac  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18006acb1  mov     al, 1
0x18006acb3  add     rsp, 48h
0x18006acb7  pop     r15
0x18006acb9  pop     r14
0x18006acbb  pop     r13
0x18006acbd  pop     r12
0x18006acbf  pop     rdi
0x18006acc0  pop     rsi
0x18006acc1  pop     rbp
0x18006acc2  pop     rbx
0x18006acc3  retn
```
