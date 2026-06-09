# ItemChangeWrapper::RemoveChangeUnitChangeWrappers(Vector<SyncId,1> const &)

- ea: `0x18007dbe4`
- end: `0x18007dd62`
- name: `?RemoveChangeUnitChangeWrappers@ItemChangeWrapper@@QEAAJAEBV?$Vector@VSyncId@@$00@@@Z`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800802fc`

## callees

- `0x18000a2b8`
- `0x18000a9e0`
- `0x18001a038`
- `0x18001ae20`
- `0x18001bf08`
- `0x18007dab4`
- `0x18007dbe4`

## string_xrefs

- `0x18007dc1e`: `ItemChangeWrapper::RemoveChangeUnitChangeWrappers`
- `0x18007dd33`: `ItemChangeWrapper::RemoveChangeUnitChangeWrappers`

## pseudocode

```c
__int64 __fastcall ItemChangeWrapper::RemoveChangeUnitChangeWrappers(__int64 a1, int *a2)
{
  int v4; // edi
  int v5; // ebx
  __int64 v6; // rsi
  int v7; // r12d
  unsigned int v8; // r14d
  __int64 v9; // rdi
  unsigned int HashValue; // eax
  __int64 v11; // r10
  int ExistingBucket; // eax
  unsigned int v14; // [rsp+88h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      WPP_c46487f44df63404f221e65d0a11538d_Traceguids,
      "ItemChangeWrapper::RemoveChangeUnitChangeWrappers");
  }
  v4 = *a2;
  v5 = 0;
  while ( v4 )
  {
    LODWORD(v6) = *(_DWORD *)(a1 + 232);
    v7 = v4 - 1;
    v8 = v4 - 1;
    while ( (_DWORD)v6 )
    {
      v8 = v4 - 1;
      v6 = (unsigned int)(v6 - 1);
      if ( (unsigned int)SyncId::operator==(
                           *(_QWORD *)(*(_QWORD *)(a1 + 248) + 8 * v6) + 80LL,
                           *((_QWORD *)a2 + 2) + 16LL * (unsigned int)(v4 - 1)) )
      {
        v5 = Vector<SharedRefPtr<ChangeUnitChangeWrapper>,1>::Remove(a1 + 232, (unsigned int)v6);
        break;
      }
    }
    if ( v5 < 0 )
      goto LABEL_17;
    v9 = *(_QWORD *)(a1 + 264);
    v14 = 0;
    if ( !v9 )
    {
LABEL_16:
      v5 = -2147024809;
      goto LABEL_17;
    }
    HashValue = SyncId::GetHashValue((SyncId *)(*((_QWORD *)a2 + 2) + 16LL * v8));
    ExistingBucket = HashTable<SyncId,SharedRefPtr<ItemChangeApplicationStatus>,DefaultHashTableContext>::FindExistingBucket(
                       *(unsigned int *)(a1 + 256),
                       HashValue,
                       v11,
                       v9,
                       *(_DWORD *)(a1 + 256),
                       &v14);
    v5 = ExistingBucket;
    if ( ExistingBucket )
    {
      if ( ExistingBucket == 1 )
        goto LABEL_16;
    }
    else
    {
      *(_BYTE *)(32LL * v14 + v9 + 24) &= ~1u;
      --*(_DWORD *)(a1 + 272);
    }
LABEL_17:
    v4 = v7;
    if ( v5 < 0 )
      break;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      25,
      (unsigned int)WPP_c46487f44df63404f221e65d0a11538d_Traceguids,
      (unsigned int)"ItemChangeWrapper::RemoveChangeUnitChangeWrappers",
      v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18007dbe4  push    rbx
0x18007dbe6  push    rbp
0x18007dbe7  push    rsi
0x18007dbe8  push    rdi
0x18007dbe9  push    r12
0x18007dbeb  push    r13
0x18007dbed  push    r14
0x18007dbef  push    r15
0x18007dbf1  sub     rsp, 38h
0x18007dbf5  mov     r13, rdx
0x18007dbf8  mov     rbp, rcx
0x18007dbfb  mov     rcx, cs:WPP_GLOBAL_Control
0x18007dc02  lea     rax, WPP_GLOBAL_Control
0x18007dc09  cmp     rcx, rax
0x18007dc0c  jz      short loc_18007DC36
0x18007dc0e  test    byte ptr [rcx+1Ch], 80h
0x18007dc12  jz      short loc_18007DC36
0x18007dc14  cmp     byte ptr [rcx+19h], 5
0x18007dc18  jb      short loc_18007DC36
0x18007dc1a  mov     rcx, [rcx+10h]
0x18007dc1e  lea     r9, aItemchangewrap_2; "ItemChangeWrapper::RemoveChangeUnitChan"...
0x18007dc25  mov     edx, 18h
0x18007dc2a  lea     r8, WPP_c46487f44df63404f221e65d0a11538d_Traceguids
0x18007dc31  call    WPP_SF_s
0x18007dc36  mov     edi, [r13+0]
0x18007dc3a  lea     r15, [rbp+0E8h]
0x18007dc41  xor     ebx, ebx
0x18007dc43  test    edi, edi
0x18007dc45  jz      loc_18007DD10
0x18007dc4b  mov     esi, [r15]
0x18007dc4e  lea     r12d, [rdi-1]
0x18007dc52  mov     r14d, r12d
0x18007dc55  test    esi, esi
0x18007dc57  jz      short loc_18007DC8B
0x18007dc59  mov     rax, [r15+10h]
0x18007dc5d  lea     r14d, [rdi-1]
0x18007dc61  dec     esi
0x18007dc63  mov     edx, r14d
0x18007dc66  shl     rdx, 4
0x18007dc6a  add     rdx, [r13+10h]
0x18007dc6e  mov     rcx, [rax+rsi*8]
0x18007dc72  add     rcx, 50h ; 'P'
0x18007dc76  call    ??8SyncId@@QEBAHAEBV0@@Z; SyncId::operator==(SyncId const &)
0x18007dc7b  test    eax, eax
0x18007dc7d  jz      short loc_18007DC55
0x18007dc7f  mov     edx, esi
0x18007dc81  mov     rcx, r15
0x18007dc84  call    ?Remove@?$Vector@V?$SharedRefPtr@VChangeUnitChangeWrapper@@@@$00@@QEAAJKH@Z; Vector<SharedRefPtr<ChangeUnitChangeWrapper>,1>::Remove(ulong,int)
0x18007dc89  mov     ebx, eax
0x18007dc8b  test    ebx, ebx
0x18007dc8d  js      short loc_18007DD05
0x18007dc8f  mov     rdi, [rbp+108h]
0x18007dc96  mov     [rsp+78h+arg_8], 0
0x18007dca1  test    rdi, rdi
0x18007dca4  jz      short loc_18007DD00
0x18007dca6  mov     r10d, r14d
0x18007dca9  shl     r10, 4
0x18007dcad  add     r10, [r13+10h]
0x18007dcb1  mov     rcx, r10; this
0x18007dcb4  call    ?GetHashValue@SyncId@@QEBAKXZ; SyncId::GetHashValue(void)
0x18007dcb9  lea     rcx, [rsp+78h+arg_8]
0x18007dcc1  mov     r9, rdi
0x18007dcc4  mov     [rsp+78h+var_50], rcx
0x18007dcc9  mov     r8, r10
0x18007dccc  mov     ecx, [rbp+100h]
0x18007dcd2  mov     edx, eax
0x18007dcd4  mov     [rsp+78h+var_58], ecx
0x18007dcd8  call    ?FindExistingBucket@?$HashTable@VSyncId@@V?$SharedRefPtr@VItemChangeApplicationStatus@@@@VDefaultHashTableContext@@@@AEBAJKAEBVSyncId@@PEAV?$TableBucket@VSyncId@@V?$SharedRefPtr@VItemChangeApplicationStatus@@@@VDefaultHashTableContext@@@@KPEAK@Z; HashTable<SyncId,SharedRefPtr<ItemChangeApplicationStatus>,DefaultHashTableContext>::FindExistingBucket(ulong,SyncId const &,TableBucket<SyncId,SharedRefPtr<ItemChangeApplicationStatus>,DefaultHashTableContext> *,ulong,ulong *)
0x18007dcdd  mov     ebx, eax
0x18007dcdf  test    eax, eax
0x18007dce1  jnz     short loc_18007DCFB
0x18007dce3  mov     eax, [rsp+78h+arg_8]
0x18007dcea  shl     rax, 5
0x18007dcee  and     byte ptr [rax+rdi+18h], 0FEh
0x18007dcf3  dec     dword ptr [rbp+110h]
0x18007dcf9  jmp     short loc_18007DD05
0x18007dcfb  cmp     eax, 1
0x18007dcfe  jnz     short loc_18007DD05
0x18007dd00  mov     ebx, 80070057h
0x18007dd05  mov     edi, r12d
0x18007dd08  test    ebx, ebx
0x18007dd0a  jns     loc_18007DC43
0x18007dd10  mov     rcx, cs:WPP_GLOBAL_Control
0x18007dd17  lea     rax, WPP_GLOBAL_Control
0x18007dd1e  cmp     rcx, rax
0x18007dd21  jz      short loc_18007DD4F
0x18007dd23  test    byte ptr [rcx+1Ch], 80h
0x18007dd27  jz      short loc_18007DD4F
0x18007dd29  cmp     byte ptr [rcx+19h], 5
0x18007dd2d  jb      short loc_18007DD4F
0x18007dd2f  mov     rcx, [rcx+10h]
0x18007dd33  lea     r9, aItemchangewrap_2; "ItemChangeWrapper::RemoveChangeUnitChan"...
0x18007dd3a  mov     edx, 19h
0x18007dd3f  mov     [rsp+78h+var_58], ebx
0x18007dd43  lea     r8, WPP_c46487f44df63404f221e65d0a11538d_Traceguids
0x18007dd4a  call    WPP_SF_sD
0x18007dd4f  mov     eax, ebx
0x18007dd51  add     rsp, 38h
0x18007dd55  pop     r15
0x18007dd57  pop     r14
0x18007dd59  pop     r13
0x18007dd5b  pop     r12
0x18007dd5d  pop     rdi
0x18007dd5e  pop     rsi
0x18007dd5f  pop     rbp
0x18007dd60  pop     rbx
0x18007dd61  retn
```
