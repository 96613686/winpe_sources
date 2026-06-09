# CDsmPropertyCache::CommitCachedDevnodeProperties(void)

- ea: `0x180005ed0`
- end: `0x180006146`
- name: `?CommitCachedDevnodeProperties@CDsmPropertyCache@@QEAAXXZ`
- size: `630`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800057f4`
- `0x180012a48`

## callees

- `0x180005ed0`
- `0x18000614c`
- `0x180006a80`
- `0x18001682c`
- `0x180016c18`
- `0x180018be4`
- `0x18001af70`
- `0x18001b410`
- `0x180021790`
- `0x180031850`
- `0x18003197c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005f62`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005f62`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005ef7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005ef7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005fd9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005fd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005f4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800060d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005f4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800060d0`
- `api-ms-win-devices-query-l1-1-0!DevSetObjectProperties` at `0x1800060c5`
- `api-ms-win-devices-query-l1-1-0!DevSetObjectProperties` at `0x1800060c5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CDsmPropertyCache::CommitCachedDevnodeProperties(RTL_SRWLOCK *this)
{
  int v2; // r15d
  CDsmPropertyCache **Ptr; // rax
  PVOID *v4; // r10
  PVOID v5; // rcx
  unsigned int v6; // edx
  CDsmPropertyCache::CPropertySet *v7; // r13
  _QWORD *v8; // rcx
  PROPVARIANT *v9; // r14
  _QWORD *v10; // rax
  CDsmPropertyCache *v12; // rcx
  CDsmPropertyCache *v13; // r13
  _QWORD *v14; // r14
  __int64 v15; // rdi
  __int64 v16; // r8
  PVOID v17; // rcx
  CDsmPropertyCache *v18; // [rsp+30h] [rbp-88h]
  __int128 v19; // [rsp+38h] [rbp-80h] BYREF
  __int128 v20; // [rsp+48h] [rbp-70h]
  LPVOID pv[2]; // [rsp+58h] [rbp-60h]

  AcquireSRWLockExclusive(this + 1);
  if ( this[26].Ptr )
  {
    v2 = 0;
    Ptr = (CDsmPropertyCache **)this[8].Ptr;
    v4 = &WPP_GLOBAL_Control;
    if ( Ptr )
    {
      do
      {
        v12 = *Ptr;
        v18 = *Ptr;
        v13 = Ptr[2];
        v14 = (_QWORD *)*((_QWORD *)v13 + 1);
        if ( v14 )
        {
          do
          {
            v15 = v14[2];
            v14 = (_QWORD *)*v14;
            if ( *(_DWORD *)(v15 + 44)
              && CDsmPropertyCache::_fIsValidDevnodeProperty(
                   v12,
                   (const struct _tagpropertykey *)(v15 + 24),
                   *(_WORD *)v15) )
            {
              v17 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != v4 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF__guid_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, v16, v15 + 24, *(_DWORD *)(v15 + 40));
              v19 = 0;
              v20 = 0;
              *(_OWORD *)pv = 0;
              if ( (int)CDsmPropertyCache::_PropVariantToDevProp(v17, v15, *(unsigned int *)(v15 + 48), &v19) >= 0 )
              {
                v19 = *(_OWORD *)(v15 + 24);
                *(_QWORD *)&v20 = *(unsigned int *)(v15 + 40);
                *((_QWORD *)&v20 + 1) = *(_QWORD *)v13;
                DevSetObjectProperties(3, this[26].Ptr, 1, &v19);
                CoTaskMemFree(pv[1]);
                ++v2;
              }
              v4 = &WPP_GLOBAL_Control;
            }
          }
          while ( v14 );
          v12 = v18;
        }
        Ptr = (CDsmPropertyCache **)v12;
      }
      while ( v12 );
    }
    if ( WPP_GLOBAL_Control != v4 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_81c79e6b29ca30ffa466dc55c7bf2d12_Traceguids);
    while ( this[10].Ptr )
    {
      v7 = (CDsmPropertyCache::CPropertySet *)ATL::CAtlList<CDsmPropertyCache::CPropertySet *,ATL::CElementTraits<CDsmPropertyCache::CPropertySet *>>::RemoveTail(&this[8]);
      while ( *((_QWORD *)v7 + 3) )
      {
        v8 = (_QWORD *)*((_QWORD *)v7 + 2);
        if ( !v8 )
          ATL::AtlThrowImpl(-2147467259);
        v9 = (PROPVARIANT *)v8[2];
        v10 = (_QWORD *)v8[1];
        *((_QWORD *)v7 + 2) = v10;
        if ( v10 )
          *v10 = 0;
        else
          *((_QWORD *)v7 + 1) = 0;
        *v8 = *((_QWORD *)v7 + 5);
        *((_QWORD *)v7 + 5) = v8;
        if ( (*((_QWORD *)v7 + 3))-- == 1 )
          ATL::CAtlList<CDsmPropertyCache::CPropertyElement *,ATL::CElementTraits<CDsmPropertyCache::CPropertyElement *>>::RemoveAll((char *)v7 + 8);
        if ( v9 )
        {
          PropVariantClear(v9);
          operator delete(v9);
        }
      }
      if ( v7 )
        CDsmPropertyCache::CPropertySet::`scalar deleting destructor'(v7, v6);
    }
    v5 = this[26].Ptr;
    if ( v5 )
      CoTaskMemFree(v5);
    this[26].Ptr = 0;
    LODWORD(this[27].Ptr) += v2;
  }
  ReleaseSRWLockExclusive(this + 1);
}

```

## disassembly

```asm
0x180005ed0  push    rbx
0x180005ed2  push    rbp
0x180005ed3  push    rsi
0x180005ed4  push    rdi
0x180005ed5  push    r12
0x180005ed7  push    r13
0x180005ed9  push    r14
0x180005edb  push    r15
0x180005edd  sub     rsp, 78h
0x180005ee1  mov     rax, cs:__security_cookie
0x180005ee8  xor     rax, rsp
0x180005eeb  mov     [rsp+0B8h+var_50], rax
0x180005ef0  mov     rbx, rcx
0x180005ef3  add     rcx, 8; SRWLock
0x180005ef7  call    cs:__imp_AcquireSRWLockExclusive
0x180005efd  cmp     qword ptr [rbx+0D0h], 0
0x180005f05  jz      short loc_180005F5E
0x180005f07  xor     r12d, r12d
0x180005f0a  mov     r15d, r12d
0x180005f0d  mov     rax, [rbx+40h]
0x180005f11  lea     r10, WPP_GLOBAL_Control
0x180005f18  test    rax, rax
0x180005f1b  jnz     loc_180006015
0x180005f21  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f28  cmp     rcx, r10
0x180005f2b  jz      short loc_180005F37
0x180005f2d  test    byte ptr [rcx+1Ch], 1
0x180005f31  jnz     loc_18000612C
0x180005f37  cmp     qword ptr [rbx+50h], 0
0x180005f3c  jnz     short loc_180005F86
0x180005f3e  mov     rcx, [rbx+0D0h]; pv
0x180005f45  test    rcx, rcx
0x180005f48  jz      short loc_180005F50
0x180005f4a  call    cs:__imp_CoTaskMemFree
0x180005f50  mov     [rbx+0D0h], r12
0x180005f57  add     [rbx+0D8h], r15d
0x180005f5e  lea     rcx, [rbx+8]; SRWLock
0x180005f62  call    cs:__imp_ReleaseSRWLockExclusive
0x180005f68  mov     rcx, [rsp+0B8h+var_50]
0x180005f6d  xor     rcx, rsp; StackCookie
0x180005f70  call    __security_check_cookie
0x180005f75  add     rsp, 78h
0x180005f79  pop     r15
0x180005f7b  pop     r14
0x180005f7d  pop     r13
0x180005f7f  pop     r12
0x180005f81  pop     rdi
0x180005f82  pop     rsi
0x180005f83  pop     rbp
0x180005f84  pop     rbx
0x180005f85  retn
0x180005f86  lea     rcx, [rbx+40h]
0x180005f8a  call    ?RemoveTail@?$CAtlList@PEAVCPropertySet@CDsmPropertyCache@@V?$CElementTraits@PEAVCPropertySet@CDsmPropertyCache@@@ATL@@@ATL@@QEAAPEAVCPropertySet@CDsmPropertyCache@@XZ; ATL::CAtlList<CDsmPropertyCache::CPropertySet *,ATL::CElementTraits<CDsmPropertyCache::CPropertySet *>>::RemoveTail(void)
0x180005f8f  mov     r13, rax
0x180005f92  cmp     qword ptr [r13+18h], 0
0x180005f97  jz      short loc_180005FFF
0x180005f99  mov     rcx, [r13+10h]
0x180005f9d  test    rcx, rcx
0x180005fa0  jz      short loc_180005FEE
0x180005fa2  mov     r14, [rcx+10h]
0x180005fa6  mov     rax, [rcx+8]
0x180005faa  mov     [r13+10h], rax
0x180005fae  test    rax, rax
0x180005fb1  jz      short loc_180005FF9
0x180005fb3  mov     [rax], r12
0x180005fb6  mov     rax, [r13+28h]
0x180005fba  mov     [rcx], rax
0x180005fbd  mov     [r13+28h], rcx
0x180005fc1  sub     qword ptr [r13+18h], 1
0x180005fc6  jnz     short loc_180005FD1
0x180005fc8  lea     rcx, [r13+8]
0x180005fcc  call    ?RemoveAll@?$CAtlList@PEAVCPropertyElement@CDsmPropertyCache@@V?$CElementTraits@PEAVCPropertyElement@CDsmPropertyCache@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<CDsmPropertyCache::CPropertyElement *,ATL::CElementTraits<CDsmPropertyCache::CPropertyElement *>>::RemoveAll(void)
0x180005fd1  test    r14, r14
0x180005fd4  jz      short loc_180005F92
0x180005fd6  mov     rcx, r14; pvar
0x180005fd9  call    cs:__imp_PropVariantClear
0x180005fdf  mov     edx, 38h ; '8'
0x180005fe4  mov     rcx, r14; Block
0x180005fe7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180005fec  jmp     short loc_180005F92
0x180005fee  mov     ecx, 80004005h; int
0x180005ff3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180005ff9  mov     [r13+8], r12
0x180005ffd  jmp     short loc_180005FB6
0x180005fff  test    r13, r13
0x180006002  jz      loc_180005F37
0x180006008  mov     rcx, r13; this
0x18000600b  call    ??_GCPropertySet@CDsmPropertyCache@@QEAAPEAXI@Z; CDsmPropertyCache::CPropertySet::`scalar deleting destructor'(uint)
0x180006010  jmp     loc_180005F37
0x180006015  mov     rcx, [rax]; this
0x180006018  mov     [rsp+0B8h+var_88], rcx
0x18000601d  mov     r13, [rax+10h]
0x180006021  mov     r14, [r13+8]
0x180006025  test    r14, r14
0x180006028  jz      loc_1800060EE
0x18000602e  xchg    ax, ax
0x180006030  mov     rdi, [r14+10h]
0x180006034  mov     r14, [r14]
0x180006037  cmp     dword ptr [rdi+2Ch], 0
0x18000603b  jz      loc_1800060E0
0x180006041  movzx   r8d, word ptr [rdi]; unsigned __int16
0x180006045  lea     rdx, [rdi+18h]; struct _tagpropertykey *
0x180006049  call    ?_fIsValidDevnodeProperty@CDsmPropertyCache@@AEAA_NAEBU_tagpropertykey@@G@Z; CDsmPropertyCache::_fIsValidDevnodeProperty(_tagpropertykey const &,ushort)
0x18000604e  test    al, al
0x180006050  jz      loc_180006127
0x180006056  mov     rcx, cs:WPP_GLOBAL_Control
0x18000605d  cmp     rcx, r10
0x180006060  jnz     loc_1800060FF
0x180006066  xorps   xmm0, xmm0
0x180006069  movups  [rsp+0B8h+var_80], xmm0
0x18000606e  movups  [rsp+0B8h+var_70], xmm0
0x180006073  movups  xmmword ptr [rsp+0B8h+pv], xmm0
0x180006078  lea     r9, [rsp+0B8h+var_80]
0x18000607d  mov     r8d, [rdi+30h]
0x180006081  mov     rdx, rdi
0x180006084  call    ?_PropVariantToDevProp@CDsmPropertyCache@@AEAAJPEBUtagPROPVARIANT@@W4__MIDL___MIDL_itf_dsmtask_0000_0000_0001@@PEAU_DEVPROPERTY@@@Z; CDsmPropertyCache::_PropVariantToDevProp(tagPROPVARIANT const *,__MIDL___MIDL_itf_dsmtask_0000_0000_0001,_DEVPROPERTY *)
0x180006089  xor     r12d, r12d
0x18000608c  test    eax, eax
0x18000608e  js      short loc_1800060D9
0x180006090  movups  xmm0, xmmword ptr [rdi+18h]
0x180006094  movups  [rsp+0B8h+var_80], xmm0
0x180006099  mov     eax, [rdi+28h]
0x18000609c  mov     dword ptr [rsp+0B8h+var_70], eax
0x1800060a0  mov     dword ptr [rsp+0B8h+var_70+4], r12d
0x1800060a5  mov     rax, [r13+0]
0x1800060a9  mov     qword ptr [rsp+0B8h+var_70+8], rax
0x1800060ae  lea     r9, [rsp+0B8h+var_80]
0x1800060b3  mov     r8d, 1
0x1800060b9  mov     rdx, [rbx+0D0h]
0x1800060c0  mov     ecx, 3
0x1800060c5  call    cs:__imp_DevSetObjectProperties
0x1800060cb  mov     rcx, [rsp+0B8h+pv+8]; pv
0x1800060d0  call    cs:__imp_CoTaskMemFree
0x1800060d6  inc     r15d
0x1800060d9  lea     r10, WPP_GLOBAL_Control
0x1800060e0  test    r14, r14
0x1800060e3  jnz     loc_180006030
0x1800060e9  mov     rcx, [rsp+0B8h+var_88]
0x1800060ee  mov     rax, rcx
0x1800060f1  test    rcx, rcx
0x1800060f4  jz      loc_180005F21
0x1800060fa  jmp     loc_180006015
0x1800060ff  test    byte ptr [rcx+1Ch], 1
0x180006103  jz      loc_180006066
0x180006109  mov     edx, 0Fh
0x18000610e  mov     eax, [rdi+28h]
0x180006111  mov     [rsp+0B8h+var_98], eax
0x180006115  lea     r9, [rdi+18h]
0x180006119  mov     rcx, [rcx+10h]
0x18000611d  call    WPP_SF__guid_d
0x180006122  jmp     loc_180006066
0x180006127  xor     r12d, r12d
0x18000612a  jmp     short loc_1800060E0
0x18000612c  mov     edx, 10h
0x180006131  lea     r8, WPP_81c79e6b29ca30ffa466dc55c7bf2d12_Traceguids
0x180006138  mov     rcx, [rcx+10h]
0x18000613c  call    WPP_SF_
0x180006141  jmp     loc_180005F37
```
