# CEseSyncMetadataStore::GetReplicaMetadata(uchar *,_ID_PARAMETERS *,IReplicaMetadata * *)

- ea: `0x1800d4870`
- end: `0x1800d4bb9`
- name: `?GetReplicaMetadata@CEseSyncMetadataStore@@UEAAJPEAEPEAU_ID_PARAMETERS@@PEAPEAUIReplicaMetadata@@@Z`
- size: `841`
- prototype: `__int64 __fastcall(CEseSyncMetadataStore *__hidden this, unsigned __int8 *, struct _ID_PARAMETERS *, struct IReplicaMetadata **)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180002ab0`
- `0x1800091ac`
- `0x18000a694`
- `0x1800a0c30`
- `0x1800ad07c`
- `0x1800d4870`
- `0x1800d53bc`
- `0x1800d62b4`
- `0x1800d6d54`
- `0x1800d7024`
- `0x1800d7788`
- `0x1800d7b74`
- `0x1800d7c88`
- `0x1800d83a0`
- `0x1800d8638`
- `0x1800d93ec`
- `0x1800dbcd4`
- `0x1800e0718`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d4931`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d4931`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d4a23`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d4a23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d4aec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d4aec`
- `SHLWAPI!SHStrDupW` at `0x1800d4ac6`
- `SHLWAPI!SHStrDupW` at `0x1800d4ac6`

## pseudocode

```c
__int64 __fastcall CEseSyncMetadataStore::GetReplicaMetadata(
        CEseSyncMetadataStore *this,
        unsigned __int8 *a2,
        struct _ID_PARAMETERS *a3,
        struct IReplicaMetadata **a4)
{
  struct IReplicaMetadata **v4; // r13
  struct IUnknown *v8; // r14
  unsigned __int16 ReplicaIdSize; // ax
  int AsString; // ebx
  const WCHAR *v11; // rbx
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rdi
  struct IUnknown *v15; // rdx
  HRESULT IsReplicaInDB; // edi
  int v17; // eax
  struct CDbOperationManager *v18; // rdx
  __int64 v19; // rdx
  int v20; // r8d
  struct IUnknown *v21; // rdx
  struct IUnknown *v23; // [rsp+30h] [rbp-49h] BYREF
  LPWSTR ppwsz; // [rsp+38h] [rbp-41h] BYREF
  LPCWSTR psz; // [rsp+40h] [rbp-39h] BYREF
  struct IReplicaMetadata **v26; // [rsp+48h] [rbp-31h]
  _BYTE v27[12]; // [rsp+50h] [rbp-29h] BYREF
  int v28; // [rsp+5Ch] [rbp-1Dh]
  struct IUnknown *v29[2]; // [rsp+68h] [rbp-11h] BYREF
  char v30; // [rsp+7Ch] [rbp+3h]

  v26 = a4;
  v4 = a4;
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( !a2 || !a3 )
    return 2147500035LL;
  psz = 0;
  v30 = 0;
  v8 = 0;
  v23 = 0;
  ReplicaIdSize = CMetaStoreUtils::GetReplicaIdSize(a2, a3);
  AsString = CSha1Hash::HashBytes((CSha1Hash *)v29, a2, ReplicaIdSize);
  if ( AsString >= 0 )
  {
    AsString = CSha1Hash::GetAsString((CSha1Hash *)v29, (unsigned __int16 **)&psz);
    if ( AsString >= 0 )
    {
      CImplicitTransaction::CImplicitTransaction(
        (CImplicitTransaction *)v27,
        *((struct CDbOperationManager **)this + 12),
        0);
      AsString = v28;
      if ( v28 >= 0 )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
        if ( *((_DWORD *)this + 16) )
        {
          v11 = psz;
          v12 = *((_QWORD *)this + 22);
          ppwsz = (LPWSTR)psz;
          if ( v12
            && (v13 = CSimpleHashTable<unsigned short const *,CEseSyncMetadataStore::ReplicaObjectCacheEntry,CStringHashPolicy,CStringCompare,CDefaultResizePolicy,CDefaultRehashPolicy>::s_LookupEntry(
                        v12,
                        *((unsigned int *)this + 41),
                        &ppwsz),
                v14 = v13,
                *(_DWORD *)v13 == 1) )
          {
            if ( *(_QWORD *)(v13 + 24) )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                WPP_SF_sq(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  10,
                  (_DWORD)WPP_GLOBAL_Control,
                  (unsigned int)"CEseSyncMetadataStore::GetReplicaMetadata",
                  *(_QWORD *)(v13 + 16));
              *(_QWORD *)(v14 + 24) = 0;
              ++*((_DWORD *)this + 48);
            }
            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            {
              WPP_SF_sq(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                11,
                (_DWORD)WPP_GLOBAL_Control,
                (unsigned int)"CEseSyncMetadataStore::GetReplicaMetadata",
                *(_QWORD *)(v13 + 16));
            }
            v15 = *(struct IUnknown **)(v14 + 16);
            if ( v15 )
            {
              ATL::AtlComPtrAssign(&v23, v15);
              v8 = v23;
            }
            IsReplicaInDB = 0;
          }
          else
          {
            IsReplicaInDB = CReplicaTable::IsReplicaInDB(*((CReplicaTable **)this + 13), (const struct CSha1Hash *)v29);
            if ( IsReplicaInDB >= 0 )
            {
              v18 = (struct CDbOperationManager *)*((_QWORD *)this + 12);
              v29[0] = 0;
              v29[1] = 0;
              ppwsz = 0;
              IsReplicaInDB = CReplicaMetadata::CreateInstance(
                                this,
                                v18,
                                a2,
                                a3,
                                *((struct CReplicaTable **)this + 13),
                                (struct CReplicaMetadata **)&ppwsz);
              if ( IsReplicaInDB >= 0 )
              {
                ATL::CComPtrBase<IFileInfoFromDisk>::Attach(v29, ppwsz);
                ppwsz = 0;
                IsReplicaInDB = SHStrDupW(v11, &ppwsz);
                if ( IsReplicaInDB < 0
                  || (IsReplicaInDB = CSimpleHashTable<unsigned short const *,CEseSyncMetadataStore::ReplicaObjectCacheEntry,CStringHashPolicy,CStringCompare,CDefaultResizePolicy,CDefaultRehashPolicy>::_AddUpdateItem(
                                        (char *)this + 160,
                                        v19,
                                        &ppwsz,
                                        v29),
                      IsReplicaInDB >= 0) )
                {
                  if ( IsReplicaInDB >= 0 )
                  {
                    v21 = v29[0];
                    ++*((_DWORD *)this + 48);
                    if ( v21 )
                    {
                      ATL::AtlComPtrAssign(&v23, v21);
                      v8 = v23;
                    }
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                      WPP_SF_sq(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        12,
                        v20,
                        (unsigned int)"CEseSyncMetadataStore::GetReplicaMetadata",
                        (char)v8);
                  }
                }
                else
                {
                  CoTaskMemFree(ppwsz);
                }
              }
              ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(v29);
            }
          }
          v4 = v26;
        }
        else
        {
          IsReplicaInDB = -2147216747;
        }
        if ( this != (CEseSyncMetadataStore *)-24LL )
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
        if ( IsReplicaInDB < 0 )
        {
          AsString = CImplicitTransaction::CommitOrRollbackTransaction((CImplicitTransaction *)v27, IsReplicaInDB);
        }
        else
        {
          v17 = CReplicaMetadata::LoadFromDatabase((CReplicaMetadata *)v8);
          AsString = CImplicitTransaction::CommitOrRollbackTransaction((CImplicitTransaction *)v27, v17);
          if ( AsString >= 0 )
          {
            v23 = 0;
            *v4 = (struct IReplicaMetadata *)v8;
          }
        }
        CEseSyncMetadataStore::PruneDormantReplicas(this, 0);
      }
    }
  }
  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v23);
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&psz);
  return (unsigned int)AsString;
}

```

## disassembly

```asm
0x1800d4870  push    rbp
0x1800d4872  push    rbx
0x1800d4873  push    rsi
0x1800d4874  push    rdi
0x1800d4875  push    r12
0x1800d4877  push    r13
0x1800d4879  push    r14
0x1800d487b  push    r15
0x1800d487d  lea     rbp, [rsp-1Fh]
0x1800d4882  sub     rsp, 98h
0x1800d4889  mov     rax, cs:__security_cookie
0x1800d4890  xor     rax, rsp
0x1800d4893  mov     [rbp+57h+var_50], rax
0x1800d4897  xor     edi, edi
0x1800d4899  mov     [rbp+57h+var_88], r9
0x1800d489d  mov     r13, r9
0x1800d48a0  mov     r12, r8
0x1800d48a3  mov     r15, rdx
0x1800d48a6  mov     rsi, rcx
0x1800d48a9  test    r9, r9
0x1800d48ac  jz      loc_1800D4B94
0x1800d48b2  mov     [r9], rdi
0x1800d48b5  test    rdx, rdx
0x1800d48b8  jz      loc_1800D4B94
0x1800d48be  test    r8, r8
0x1800d48c1  jz      loc_1800D4B94
0x1800d48c7  mov     rdx, r8; struct _ID_PARAMETERS *
0x1800d48ca  mov     [rbp+57h+psz], rdi
0x1800d48ce  mov     rcx, r15; unsigned __int8 *
0x1800d48d1  mov     [rbp+57h+var_54], dil
0x1800d48d5  mov     r14d, edi
0x1800d48d8  mov     [rbp+57h+var_A0], rdi
0x1800d48dc  call    ?GetReplicaIdSize@CMetaStoreUtils@@SAGPEBEPEBU_ID_PARAMETERS@@@Z; CMetaStoreUtils::GetReplicaIdSize(uchar const *,_ID_PARAMETERS const *)
0x1800d48e1  movzx   r8d, ax; dwDataLen
0x1800d48e5  lea     rcx, [rbp+57h+var_68]; this
0x1800d48e9  mov     rdx, r15; pbData
0x1800d48ec  call    ?HashBytes@CSha1Hash@@QEAAJPEBE_K@Z; CSha1Hash::HashBytes(uchar const *,unsigned __int64)
0x1800d48f1  mov     ebx, eax
0x1800d48f3  test    eax, eax
0x1800d48f5  js      loc_1800D4B7E
0x1800d48fb  lea     rdx, [rbp+57h+psz]; unsigned __int16 **
0x1800d48ff  lea     rcx, [rbp+57h+var_68]; this
0x1800d4903  call    ?GetAsString@CSha1Hash@@QEBAJPEAPEAG@Z; CSha1Hash::GetAsString(ushort * *)
0x1800d4908  mov     ebx, eax
0x1800d490a  test    eax, eax
0x1800d490c  js      loc_1800D4B7E
0x1800d4912  mov     rdx, [rsi+60h]; struct CDbOperationManager *
0x1800d4916  lea     rcx, [rbp+57h+var_80]; this
0x1800d491a  xor     r8d, r8d; struct CReplicaMetadata *
0x1800d491d  call    ??0CImplicitTransaction@@QEAA@PEAVCDbOperationManager@@PEAVCReplicaMetadata@@@Z; CImplicitTransaction::CImplicitTransaction(CDbOperationManager *,CReplicaMetadata *)
0x1800d4922  mov     ebx, [rbp+57h+var_74]
0x1800d4925  test    ebx, ebx
0x1800d4927  js      loc_1800D4B7E
0x1800d492d  lea     rcx, [rsi+18h]; lpCriticalSection
0x1800d4931  call    cs:__imp_EnterCriticalSection
0x1800d4937  cmp     [rsi+40h], edi
0x1800d493a  jz      loc_1800D4B5D
0x1800d4940  mov     rbx, [rbp+57h+psz]
0x1800d4944  lea     r13, [rsi+0A0h]
0x1800d494b  mov     rcx, [r13+10h]
0x1800d494f  mov     [rbp+57h+ppwsz], rbx
0x1800d4953  test    rcx, rcx
0x1800d4956  jz      loc_1800D4A5F
0x1800d495c  mov     edx, [r13+4]
0x1800d4960  lea     r8, [rbp+57h+ppwsz]
0x1800d4964  call    ?s_LookupEntry@?$CSimpleHashTable@PEBGUReplicaObjectCacheEntry@CEseSyncMetadataStore@@VCStringHashPolicy@@VCStringCompare@@VCDefaultResizePolicy@@VCDefaultRehashPolicy@@@@CAAEAVHashBucket@1@PEAV21@IAEBQEBG@Z; CSimpleHashTable<ushort const *,CEseSyncMetadataStore::ReplicaObjectCacheEntry,CStringHashPolicy,CStringCompare,CDefaultResizePolicy,CDefaultRehashPolicy>::s_LookupEntry(CSimpleHashTable<ushort const *,CEseSyncMetadataStore::ReplicaObjectCacheEntry,CStringHashPolicy,CStringCompare,CDefaultResizePolicy,CDefaultRehashPolicy>::HashBucket *,uint,ushort const * const &)
0x1800d4969  mov     rdi, rax
0x1800d496c  cmp     dword ptr [rax], 1
0x1800d496f  jnz     loc_1800D4A5F
0x1800d4975  cmp     [rax+18h], r14
0x1800d4979  jbe     short loc_1800D49C6
0x1800d497b  mov     r8, cs:WPP_GLOBAL_Control
0x1800d4982  lea     rcx, WPP_GLOBAL_Control
0x1800d4989  cmp     r8, rcx
0x1800d498c  jz      short loc_1800D49B2
0x1800d498e  test    byte ptr [r8+1Ch], 8
0x1800d4993  jz      short loc_1800D49B2
0x1800d4995  mov     rax, [rax+10h]
0x1800d4999  lea     edx, [r14+0Ah]
0x1800d499d  mov     rcx, [r8+10h]
0x1800d49a1  lea     r9, aCesesyncmetada_5; "CEseSyncMetadataStore::GetReplicaMetada"...
0x1800d49a8  mov     [rsp+0D0h+var_B0], rax
0x1800d49ad  call    WPP_SF_sq
0x1800d49b2  mov     [rdi+18h], r14
0x1800d49b6  mov     eax, [rsi+0C0h]
0x1800d49bc  inc     eax
0x1800d49be  mov     [rsi+0C0h], eax
0x1800d49c4  jmp     short loc_1800D49FE
0x1800d49c6  mov     r8, cs:WPP_GLOBAL_Control
0x1800d49cd  lea     rcx, WPP_GLOBAL_Control
0x1800d49d4  cmp     r8, rcx
0x1800d49d7  jz      short loc_1800D49FE
0x1800d49d9  test    byte ptr [r8+1Ch], 8
0x1800d49de  jz      short loc_1800D49FE
0x1800d49e0  mov     rax, [rax+10h]
0x1800d49e4  lea     r9, aCesesyncmetada_5; "CEseSyncMetadataStore::GetReplicaMetada"...
0x1800d49eb  mov     rcx, [r8+10h]
0x1800d49ef  mov     edx, 0Bh
0x1800d49f4  mov     [rsp+0D0h+var_B0], rax
0x1800d49f9  call    WPP_SF_sq
0x1800d49fe  mov     rdx, [rdi+10h]; struct IUnknown *
0x1800d4a02  cmp     r14, rdx
0x1800d4a05  jz      short loc_1800D4A14
0x1800d4a07  lea     rcx, [rbp+57h+var_A0]; struct IUnknown **
0x1800d4a0b  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800d4a10  mov     r14, [rbp+57h+var_A0]
0x1800d4a14  xor     edi, edi
0x1800d4a16  mov     r13, [rbp+57h+var_88]
0x1800d4a1a  lea     rcx, [rsi+18h]; lpCriticalSection
0x1800d4a1e  test    rcx, rcx
0x1800d4a21  jz      short loc_1800D4A29
0x1800d4a23  call    cs:__imp_LeaveCriticalSection
0x1800d4a29  test    edi, edi
0x1800d4a2b  js      loc_1800D4B67
0x1800d4a31  mov     rcx, r14; this
0x1800d4a34  call    ?LoadFromDatabase@CReplicaMetadata@@QEAAJXZ; CReplicaMetadata::LoadFromDatabase(void)
0x1800d4a39  mov     edx, eax; int
0x1800d4a3b  lea     rcx, [rbp+57h+var_80]; this
0x1800d4a3f  call    ?CommitOrRollbackTransaction@CImplicitTransaction@@QEAAJJ@Z; CImplicitTransaction::CommitOrRollbackTransaction(long)
0x1800d4a44  mov     ebx, eax
0x1800d4a46  test    eax, eax
0x1800d4a48  js      loc_1800D4B74
0x1800d4a4e  mov     [rbp+57h+var_A0], 0
0x1800d4a56  mov     [r13+0], r14
0x1800d4a5a  jmp     loc_1800D4B74
0x1800d4a5f  mov     rcx, [rsi+68h]; this
0x1800d4a63  lea     rdx, [rbp+57h+var_68]; struct CSha1Hash *
0x1800d4a67  call    ?IsReplicaInDB@CReplicaTable@@QEAAJAEBVCSha1Hash@@@Z; CReplicaTable::IsReplicaInDB(CSha1Hash const &)
0x1800d4a6c  mov     edi, eax
0x1800d4a6e  xor     eax, eax
0x1800d4a70  test    edi, edi
0x1800d4a72  js      short loc_1800D4A16
0x1800d4a74  mov     rdx, [rsi+60h]; struct CDbOperationManager *
0x1800d4a78  mov     r9, r12; struct _ID_PARAMETERS *
0x1800d4a7b  mov     [rbp+57h+var_68], rax
0x1800d4a7f  mov     r8, r15; unsigned __int8 *
0x1800d4a82  mov     [rbp+57h+var_60], rax
0x1800d4a86  mov     rcx, rsi; struct CEseSyncMetadataStore *
0x1800d4a89  mov     [rbp+57h+ppwsz], rax
0x1800d4a8d  lea     rax, [rbp+57h+ppwsz]
0x1800d4a91  mov     [rsp+0D0h+var_A8], rax; struct CReplicaMetadata **
0x1800d4a96  mov     rax, [rsi+68h]
0x1800d4a9a  mov     [rsp+0D0h+var_B0], rax; struct CReplicaTable *
0x1800d4a9f  call    ?CreateInstance@CReplicaMetadata@@SAJPEAVCEseSyncMetadataStore@@PEAVCDbOperationManager@@PEBEPEAU_ID_PARAMETERS@@PEAVCReplicaTable@@PEAPEAV1@@Z; CReplicaMetadata::CreateInstance(CEseSyncMetadataStore *,CDbOperationManager *,uchar const *,_ID_PARAMETERS *,CReplicaTable *,CReplicaMetadata * *)
0x1800d4aa4  mov     edi, eax
0x1800d4aa6  test    eax, eax
0x1800d4aa8  js      loc_1800D4B4F
0x1800d4aae  mov     rdx, [rbp+57h+ppwsz]
0x1800d4ab2  lea     rcx, [rbp+57h+var_68]
0x1800d4ab6  call    ?Attach@?$CComPtrBase@UIFileInfoFromDisk@@@ATL@@QEAAXPEAUIFileInfoFromDisk@@@Z; ATL::CComPtrBase<IFileInfoFromDisk>::Attach(IFileInfoFromDisk *)
0x1800d4abb  lea     rdx, [rbp+57h+ppwsz]; ppwsz
0x1800d4abf  mov     [rbp+57h+ppwsz], r14
0x1800d4ac3  mov     rcx, rbx; psz
0x1800d4ac6  call    cs:__imp_SHStrDupW
0x1800d4acc  mov     edi, eax
0x1800d4ace  test    eax, eax
0x1800d4ad0  js      short loc_1800D4AF4
0x1800d4ad2  lea     r9, [rbp+57h+var_68]
0x1800d4ad6  mov     rcx, r13
0x1800d4ad9  lea     r8, [rbp+57h+ppwsz]
0x1800d4add  call    ?_AddUpdateItem@?$CSimpleHashTable@PEBGUReplicaObjectCacheEntry@CEseSyncMetadataStore@@VCStringHashPolicy@@VCStringCompare@@VCDefaultResizePolicy@@VCDefaultRehashPolicy@@@@AEAAJHAEBQEBGAEBUReplicaObjectCacheEntry@CEseSyncMetadataStore@@PEAU23@@Z; CSimpleHashTable<ushort const *,CEseSyncMetadataStore::ReplicaObjectCacheEntry,CStringHashPolicy,CStringCompare,CDefaultResizePolicy,CDefaultRehashPolicy>::_AddUpdateItem(int,ushort const * const &,CEseSyncMetadataStore::ReplicaObjectCacheEntry const &,CEseSyncMetadataStore::ReplicaObjectCacheEntry *)
0x1800d4ae2  mov     edi, eax
0x1800d4ae4  test    eax, eax
0x1800d4ae6  jns     short loc_1800D4AF4
0x1800d4ae8  mov     rcx, [rbp+57h+ppwsz]; pv
0x1800d4aec  call    cs:__imp_CoTaskMemFree
0x1800d4af2  jmp     short loc_1800D4B4F
0x1800d4af4  test    edi, edi
0x1800d4af6  js      short loc_1800D4B4F
0x1800d4af8  mov     eax, [rsi+0C0h]
0x1800d4afe  mov     rdx, [rbp+57h+var_68]; struct IUnknown *
0x1800d4b02  inc     eax
0x1800d4b04  mov     [rsi+0C0h], eax
0x1800d4b0a  test    rdx, rdx
0x1800d4b0d  jz      short loc_1800D4B1C
0x1800d4b0f  lea     rcx, [rbp+57h+var_A0]; struct IUnknown **
0x1800d4b13  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800d4b18  mov     r14, [rbp+57h+var_A0]
0x1800d4b1c  mov     rax, cs:WPP_GLOBAL_Control
0x1800d4b23  lea     rcx, WPP_GLOBAL_Control
0x1800d4b2a  cmp     rax, rcx
0x1800d4b2d  jz      short loc_1800D4B4F
0x1800d4b2f  test    byte ptr [rax+1Ch], 8
0x1800d4b33  jz      short loc_1800D4B4F
0x1800d4b35  mov     rcx, [rax+10h]
0x1800d4b39  lea     r9, aCesesyncmetada_5; "CEseSyncMetadataStore::GetReplicaMetada"...
0x1800d4b40  mov     edx, 0Ch
0x1800d4b45  mov     [rsp+0D0h+var_B0], r14
0x1800d4b4a  call    WPP_SF_sq
0x1800d4b4f  lea     rcx, [rbp+57h+var_68]
0x1800d4b53  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1800d4b58  jmp     loc_1800D4A16
0x1800d4b5d  mov     edi, 80041295h
0x1800d4b62  jmp     loc_1800D4A1A
0x1800d4b67  mov     edx, edi; int
0x1800d4b69  lea     rcx, [rbp+57h+var_80]; this
0x1800d4b6d  call    ?CommitOrRollbackTransaction@CImplicitTransaction@@QEAAJJ@Z; CImplicitTransaction::CommitOrRollbackTransaction(long)
0x1800d4b72  mov     ebx, eax
0x1800d4b74  xor     edx, edx; int
0x1800d4b76  mov     rcx, rsi; this
0x1800d4b79  call    ?PruneDormantReplicas@CEseSyncMetadataStore@@AEAAXH@Z; CEseSyncMetadataStore::PruneDormantReplicas(int)
0x1800d4b7e  lea     rcx, [rbp+57h+var_A0]
0x1800d4b82  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1800d4b87  lea     rcx, [rbp+57h+psz]
0x1800d4b8b  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x1800d4b90  mov     eax, ebx
0x1800d4b92  jmp     short loc_1800D4B99
0x1800d4b94  mov     eax, 80004003h
0x1800d4b99  mov     rcx, [rbp+57h+var_50]
0x1800d4b9d  xor     rcx, rsp; StackCookie
0x1800d4ba0  call    __security_check_cookie
0x1800d4ba5  add     rsp, 98h
0x1800d4bac  pop     r15
0x1800d4bae  pop     r14
0x1800d4bb0  pop     r13
0x1800d4bb2  pop     r12
0x1800d4bb4  pop     rdi
0x1800d4bb5  pop     rsi
0x1800d4bb6  pop     rbx
0x1800d4bb7  pop     rbp
0x1800d4bb8  retn
```
