# CDsmPropertyCache::CommitCachedContainerProperties(void)

- ea: `0x180006770`
- end: `0x180006a6f`
- name: `?CommitCachedContainerProperties@CDsmPropertyCache@@QEAAXXZ`
- size: `767`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800175d4`
- `0x1800345c8`

## callees

- `0x180005df0`
- `0x180006770`
- `0x180006a80`
- `0x180007800`
- `0x18001ba48`
- `0x180022070`
- `0x18003187c`
- `0x18003197c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006a68`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006794`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006794`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800067f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800067f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800069b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006a24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006a33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800069b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006a24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006a33`
- `api-ms-win-devices-query-l1-1-0!DevSetObjectProperties` at `0x1800068f6`
- `api-ms-win-devices-query-l1-1-0!DevSetObjectProperties` at `0x1800068f6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CDsmPropertyCache::CommitCachedContainerProperties(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v1; // rbp
  RTL_SRWLOCK *v2; // r13
  unsigned int v3; // edi
  _QWORD *Ptr; // r8
  _QWORD *i; // rax
  __int64 v6; // rcx
  unsigned int v7; // edx
  _QWORD *v8; // rax
  _QWORD *v9; // r15
  __int64 v10; // r8
  __int64 v11; // r14
  _QWORD *v12; // rax
  _QWORD *v13; // r12
  _QWORD *j; // rax
  _QWORD *v15; // rbp
  __int64 v16; // rbx
  PVOID v17; // rcx
  char *v18; // rsi
  RTL_SRWLOCK *v19; // r12
  int v20; // eax
  __int64 v21; // rcx
  RTL_SRWLOCK *v22; // r14
  _QWORD *v23; // rsi
  void *v24; // rbx
  _QWORD *v25; // r14
  __int64 *v26; // r12
  _QWORD *v27; // rsi
  __int64 v28; // rax
  const unsigned __int16 *v29; // rdx
  char v30; // si
  unsigned int v31; // ebx
  void *v32; // rcx
  __int64 v33; // rcx
  _QWORD *v35; // [rsp+78h] [rbp+10h] BYREF
  RTL_SRWLOCK *v36; // [rsp+80h] [rbp+18h]

  v1 = this + 2;
  v2 = this + 1;
  AcquireSRWLockExclusive(this + 1);
  v3 = 0;
  v36 = v1;
  Ptr = v1->Ptr;
  if ( v1->Ptr )
  {
    do
    {
      for ( i = *(_QWORD **)(Ptr[2] + 8LL); i; v3 = v7 )
      {
        v6 = i[2];
        i = (_QWORD *)*i;
        v7 = v3 + 1;
        if ( !*(_DWORD *)(v6 + 44) )
          v7 = v3;
      }
      Ptr = (_QWORD *)*Ptr;
    }
    while ( Ptr );
  }
  if ( v3 )
  {
    v8 = CoTaskMemAlloc(48LL * v3);
    v9 = v8;
    if ( v8 )
    {
      memset_0(v8, 0, 48LL * v3);
      v11 = 0;
      v12 = v1->Ptr;
LABEL_10:
      if ( v12 )
      {
        v35 = (_QWORD *)*v12;
        v13 = (_QWORD *)v12[2];
        for ( j = (_QWORD *)v13[1]; ; j = v15 )
        {
          if ( !j )
          {
            v12 = v35;
            goto LABEL_10;
          }
          v15 = (_QWORD *)*j;
          v16 = j[2];
          if ( *(_DWORD *)(v16 + 44) )
          {
            v17 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF__guid_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, v10, v16 + 24, *(_DWORD *)(v16 + 40));
            v18 = (char *)&v9[6 * v11];
            if ( (int)CDsmPropertyCache::_PropVariantToDevProp(v17, v16, *(unsigned int *)(v16 + 48), v18) < 0 )
            {
              v19 = this;
              goto LABEL_44;
            }
            *(_OWORD *)v18 = *(_OWORD *)(v16 + 24);
            *((_DWORD *)v18 + 4) = *(_DWORD *)(v16 + 40);
            *((_DWORD *)v18 + 5) = 0;
            *((_QWORD *)v18 + 3) = *v13;
            v11 = (unsigned int)(v11 + 1);
          }
        }
      }
      v19 = this;
      v20 = DevSetObjectProperties(2, &this[16], v3, v9);
      if ( v20 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            &WPP_81c79e6b29ca30ffa466dc55c7bf2d12_Traceguids,
            (unsigned int)v20);
LABEL_44:
        v31 = 0;
        v22 = v19 + 2;
        v30 = 0;
      }
      else
      {
        v22 = this + 2;
        v23 = this[2].Ptr;
        if ( v23 )
        {
          do
          {
            v24 = 0;
            v35 = 0;
            v25 = (_QWORD *)*v23;
            v26 = (__int64 *)v23[2];
            v27 = (_QWORD *)v26[1];
            if ( v27 )
            {
              do
              {
                v21 = v27[2];
                v27 = (_QWORD *)*v27;
                *(_DWORD *)(v21 + 44) = 0;
                if ( *(_DWORD *)(v21 + 40) == 31 )
                {
                  v28 = *(_QWORD *)(v21 + 24) - PKEY_DSM_MetadataExtensionNamespace;
                  if ( !v28 )
                    v28 = *(_QWORD *)(v21 + 32) - 0x12D9B63C90E00A98LL;
                  if ( !v28 && *(_WORD *)v21 == 31 )
                  {
                    v29 = *(const unsigned __int16 **)(v21 + 8);
                    if ( v29 )
                      CCoMemString::Assign((CCoMemString *)&v35, v29);
                  }
                }
              }
              while ( v27 );
              v24 = v35;
            }
            v23 = v25;
            if ( v24 )
            {
              if ( (Microsoft_Windows_DeviceSetupManagerEnableBits & 0x40) != 0 )
                McTemplateU0zzz_EventWriteTransfer(
                  v21,
                  (unsigned int)MetadataExtensionNamespaceAvailable,
                  (_DWORD)this + 128,
                  (_DWORD)v24,
                  *v26);
              CoTaskMemFree(v24);
            }
          }
          while ( v25 );
          v19 = this;
          v22 = v36;
        }
        v30 = 1;
        v31 = 0;
      }
      do
      {
        v32 = (void *)v9[6 * v31 + 5];
        if ( v32 )
          CoTaskMemFree(v32);
        ++v31;
      }
      while ( v31 < v3 );
      CoTaskMemFree(v9);
      if ( v30 )
      {
        CDsmPropertyCache::_PurgePropertyList(v33, v22);
        LODWORD(v19[27].Ptr) += v3;
      }
    }
  }
  ReleaseSRWLockExclusive(v2);
}

```

## disassembly

```asm
0x180006770  mov     [rsp+arg_18], rbx
0x180006775  mov     [rsp+arg_0], rcx
0x18000677a  push    rbp
0x18000677b  push    rsi
0x18000677c  push    rdi
0x18000677d  push    r12
0x18000677f  push    r13
0x180006781  push    r14
0x180006783  push    r15
0x180006785  sub     rsp, 30h
0x180006789  lea     rbp, [rcx+10h]
0x18000678d  lea     r13, [rcx+8]
0x180006791  mov     rcx, r13; SRWLock
0x180006794  call    cs:__imp_AcquireSRWLockExclusive
0x18000679a  xor     edi, edi
0x18000679c  mov     [rsp+68h+arg_10], rbp
0x1800067a4  mov     r8, [rbp+0]
0x1800067a8  test    r8, r8
0x1800067ab  jz      short loc_1800067E0
0x1800067ad  mov     rax, [r8+10h]
0x1800067b1  mov     rax, [rax+8]
0x1800067b5  test    rax, rax
0x1800067b8  jz      short loc_1800067D8
0x1800067ba  nop     word ptr [rax+rax+00h]
0x1800067c0  mov     rcx, [rax+10h]
0x1800067c4  mov     rax, [rax]
0x1800067c7  lea     edx, [rdi+1]
0x1800067ca  cmp     dword ptr [rcx+2Ch], 0
0x1800067ce  cmovz   edx, edi
0x1800067d1  mov     edi, edx
0x1800067d3  test    rax, rax
0x1800067d6  jnz     short loc_1800067C0
0x1800067d8  mov     r8, [r8]
0x1800067db  test    r8, r8
0x1800067de  jnz     short loc_1800067AD
0x1800067e0  test    edi, edi
0x1800067e2  jz      loc_180006A4E
0x1800067e8  mov     eax, edi
0x1800067ea  lea     rbx, [rax+rax*2]
0x1800067ee  shl     rbx, 4
0x1800067f2  mov     rcx, rbx; cb
0x1800067f5  call    cs:__imp_CoTaskMemAlloc
0x1800067fb  mov     r15, rax
0x1800067fe  test    rax, rax
0x180006801  jz      loc_180006A4E
0x180006807  mov     r8, rbx; Size
0x18000680a  xor     edx, edx; Val
0x18000680c  mov     rcx, rax; void *
0x18000680f  call    memset_0
0x180006814  xor     r14d, r14d
0x180006817  mov     rax, [rbp+0]
0x18000681b  lea     rsi, WPP_GLOBAL_Control
0x180006822  test    rax, rax
0x180006825  jz      loc_1800068DB
0x18000682b  mov     rcx, [rax]
0x18000682e  mov     [rsp+68h+arg_8], rcx
0x180006833  mov     r12, [rax+10h]
0x180006837  mov     rax, [r12+8]
0x18000683c  nop     dword ptr [rax+00h]
0x180006840  test    rax, rax
0x180006843  jz      loc_1800068D1
0x180006849  mov     rbp, [rax]
0x18000684c  mov     rbx, [rax+10h]
0x180006850  cmp     dword ptr [rbx+2Ch], 0
0x180006854  jz      short loc_1800068C9
0x180006856  mov     rcx, cs:WPP_GLOBAL_Control
0x18000685d  cmp     rcx, rsi
0x180006860  jz      short loc_180006881
0x180006862  test    byte ptr [rcx+1Ch], 1
0x180006866  jz      short loc_180006881
0x180006868  lea     r9, [rbx+18h]
0x18000686c  mov     edx, 0Dh
0x180006871  mov     eax, [rbx+28h]
0x180006874  mov     dword ptr [rsp+68h+var_48], eax
0x180006878  mov     rcx, [rcx+10h]
0x18000687c  call    WPP_SF__guid_d
0x180006881  lea     rsi, [r14+r14*2]
0x180006885  shl     rsi, 4
0x180006889  add     rsi, r15
0x18000688c  mov     r9, rsi
0x18000688f  mov     r8d, [rbx+30h]
0x180006893  mov     rdx, rbx
0x180006896  call    ?_PropVariantToDevProp@CDsmPropertyCache@@AEAAJPEBUtagPROPVARIANT@@W4__MIDL___MIDL_itf_dsmtask_0000_0000_0001@@PEAU_DEVPROPERTY@@@Z; CDsmPropertyCache::_PropVariantToDevProp(tagPROPVARIANT const *,__MIDL___MIDL_itf_dsmtask_0000_0000_0001,_DEVPROPERTY *)
0x18000689b  test    eax, eax
0x18000689d  js      loc_180006A02
0x1800068a3  movups  xmm0, xmmword ptr [rbx+18h]
0x1800068a7  movups  xmmword ptr [rsi], xmm0
0x1800068aa  mov     eax, [rbx+28h]
0x1800068ad  mov     [rsi+10h], eax
0x1800068b0  mov     dword ptr [rsi+14h], 0
0x1800068b7  mov     rax, [r12]
0x1800068bb  mov     [rsi+18h], rax
0x1800068bf  inc     r14d
0x1800068c2  lea     rsi, WPP_GLOBAL_Control
0x1800068c9  mov     rax, rbp
0x1800068cc  jmp     loc_180006840
0x1800068d1  mov     rax, [rsp+68h+arg_8]
0x1800068d6  jmp     loc_180006822
0x1800068db  mov     r12, [rsp+68h+arg_0]
0x1800068e0  lea     rbp, [r12+80h]
0x1800068e8  mov     r9, r15
0x1800068eb  mov     r8d, edi
0x1800068ee  mov     rdx, rbp
0x1800068f1  mov     ecx, 2
0x1800068f6  call    cs:__imp_DevSetObjectProperties
0x1800068fc  test    eax, eax
0x1800068fe  js      loc_1800069D6
0x180006904  lea     r14, [r12+10h]
0x180006909  mov     rsi, [r14]
0x18000690c  xor     edx, edx
0x18000690e  test    rsi, rsi
0x180006911  jz      loc_1800069CF
0x180006917  mov     rbx, rdx
0x18000691a  mov     [rsp+68h+arg_8], rdx
0x18000691f  mov     r14, [rsi]
0x180006922  mov     r12, [rsi+10h]
0x180006926  mov     rsi, [r12+8]
0x18000692b  test    rsi, rsi
0x18000692e  jz      short loc_180006982
0x180006930  mov     rcx, [rsi+10h]
0x180006934  mov     rsi, [rsi]
0x180006937  mov     [rcx+2Ch], edx
0x18000693a  cmp     dword ptr [rcx+28h], 1Fh
0x18000693e  jnz     short loc_180006978
0x180006940  mov     rax, [rcx+18h]
0x180006944  sub     rax, cs:PKEY_DSM_MetadataExtensionNamespace
0x18000694b  jnz     short loc_180006958
0x18000694d  mov     rax, [rcx+20h]
0x180006951  sub     rax, cs:qword_180048E28
0x180006958  test    rax, rax
0x18000695b  jnz     short loc_180006978
0x18000695d  cmp     word ptr [rcx], 1Fh
0x180006961  jnz     short loc_180006978
0x180006963  mov     rdx, [rcx+8]; unsigned __int16 *
0x180006967  test    rdx, rdx
0x18000696a  jz      short loc_180006976
0x18000696c  lea     rcx, [rsp+68h+arg_8]; this
0x180006971  call    ?Assign@CCoMemString@@QEAAJPEBG@Z; CCoMemString::Assign(ushort const *)
0x180006976  xor     edx, edx
0x180006978  test    rsi, rsi
0x18000697b  jnz     short loc_180006930
0x18000697d  mov     rbx, [rsp+68h+arg_8]
0x180006982  mov     rsi, r14
0x180006985  test    rbx, rbx
0x180006988  jz      short loc_1800069B9
0x18000698a  test    cs:Microsoft_Windows_DeviceSetupManagerEnableBits, 40h
0x180006991  jz      short loc_1800069AE
0x180006993  mov     rax, [r12]
0x180006997  mov     [rsp+68h+var_48], rax
0x18000699c  mov     r9, rbx
0x18000699f  mov     r8, rbp
0x1800069a2  lea     rdx, MetadataExtensionNamespaceAvailable
0x1800069a9  call    McTemplateU0zzz_EventWriteTransfer
0x1800069ae  mov     rcx, rbx; pv
0x1800069b1  call    cs:__imp_CoTaskMemFree
0x1800069b7  xor     edx, edx
0x1800069b9  test    r14, r14
0x1800069bc  jnz     loc_180006917
0x1800069c2  mov     r12, [rsp+68h+arg_0]
0x1800069c7  mov     r14, [rsp+68h+arg_10]
0x1800069cf  mov     sil, 1
0x1800069d2  mov     ebx, edx
0x1800069d4  jmp     short loc_180006A11
0x1800069d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800069dd  cmp     rcx, rsi
0x1800069e0  jz      short loc_180006A07
0x1800069e2  test    byte ptr [rcx+1Ch], 1
0x1800069e6  jz      short loc_180006A07
0x1800069e8  mov     edx, 0Eh
0x1800069ed  mov     r9d, eax
0x1800069f0  lea     r8, WPP_81c79e6b29ca30ffa466dc55c7bf2d12_Traceguids
0x1800069f7  mov     rcx, [rcx+10h]
0x1800069fb  call    WPP_SF_d
0x180006a00  jmp     short loc_180006A07
0x180006a02  mov     r12, [rsp+68h+arg_0]
0x180006a07  xor     ebx, ebx
0x180006a09  lea     r14, [r12+10h]
0x180006a0e  xor     sil, sil
0x180006a11  mov     eax, ebx
0x180006a13  lea     rcx, [rax+rax*2]
0x180006a17  add     rcx, rcx
0x180006a1a  mov     rcx, [r15+rcx*8+28h]; pv
0x180006a1f  test    rcx, rcx
0x180006a22  jz      short loc_180006A2A
0x180006a24  call    cs:__imp_CoTaskMemFree
0x180006a2a  inc     ebx
0x180006a2c  cmp     ebx, edi
0x180006a2e  jb      short loc_180006A11
0x180006a30  mov     rcx, r15; pv
0x180006a33  call    cs:__imp_CoTaskMemFree
0x180006a39  test    sil, sil
0x180006a3c  jz      short loc_180006A4E
0x180006a3e  mov     rdx, r14
0x180006a41  call    ?_PurgePropertyList@CDsmPropertyCache@@AEAAXAEAV?$CAtlList@PEAVCPropertySet@CDsmPropertyCache@@V?$CElementTraits@PEAVCPropertySet@CDsmPropertyCache@@@ATL@@@ATL@@@Z; CDsmPropertyCache::_PurgePropertyList(ATL::CAtlList<CDsmPropertyCache::CPropertySet *,ATL::CElementTraits<CDsmPropertyCache::CPropertySet *>> &)
0x180006a46  add     [r12+0D8h], edi
0x180006a4e  mov     rcx, r13
0x180006a51  mov     rbx, [rsp+68h+arg_18]
0x180006a59  add     rsp, 30h
0x180006a5d  pop     r15
0x180006a5f  pop     r14
0x180006a61  pop     r13
0x180006a63  pop     r12
0x180006a65  pop     rdi
0x180006a66  pop     rsi
0x180006a67  pop     rbp
0x180006a68  jmp     cs:__imp_ReleaseSRWLockExclusive
```
