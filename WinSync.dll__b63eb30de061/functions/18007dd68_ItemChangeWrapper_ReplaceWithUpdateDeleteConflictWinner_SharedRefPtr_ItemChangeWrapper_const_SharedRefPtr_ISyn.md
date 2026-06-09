# ItemChangeWrapper::ReplaceWithUpdateDeleteConflictWinner(SharedRefPtr<ItemChangeWrapper> const &,SharedRefPtr<ISyncKnowledge> const &)

- ea: `0x18007dd68`
- end: `0x18007df65`
- name: `?ReplaceWithUpdateDeleteConflictWinner@ItemChangeWrapper@@QEAAJAEBV?$SharedRefPtr@VItemChangeWrapper@@@@AEBV?$SharedRefPtr@UISyncKnowledge@@@@@Z`
- size: `509`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x18007edf4`

## callees

- `0x180008624`
- `0x18001a038`
- `0x18001a1f0`
- `0x18001ae20`
- `0x18007aec8`
- `0x18007b208`
- `0x18007dd68`
- `0x180094010`

## string_xrefs

- `0x18007dda5`: `ItemChangeWrapper::ReplaceWithUpdateDeleteConflictWinner`
- `0x18007df36`: `ItemChangeWrapper::ReplaceWithUpdateDeleteConflictWinner`

## pseudocode

```c
__int64 __fastcall ItemChangeWrapper::ReplaceWithUpdateDeleteConflictWinner(__int64 a1, __int64 *a2, _QWORD *a3)
{
  int v6; // edi
  __int64 v7; // rbp
  __int64 v8; // rax
  __int64 v9; // r14
  int v10; // ecx
  _OWORD *v11; // r9
  __int64 v12; // r8
  int v13; // eax
  __int128 v14; // xmm0
  int v16; // [rsp+90h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      WPP_c46487f44df63404f221e65d0a11538d_Traceguids,
      "ItemChangeWrapper::ReplaceWithUpdateDeleteConflictWinner");
  }
  v6 = 0;
  *(_DWORD *)(a1 + 232) = 0;
  HashTable<SyncId,SharedRefPtr<ChangeUnitChangeWrapper>,DefaultHashTableContext>::FreeHashTable(a1 + 256);
  v7 = 0;
  while ( 1 )
  {
    v8 = *a2;
    if ( (unsigned int)v7 >= *(_DWORD *)(*a2 + 232) )
      break;
    v9 = *(_QWORD *)(v8 + 248) + 8 * v7;
    *(_QWORD *)(*(_QWORD *)v9 + 128LL) = a1;
    v6 = Vector<SharedRefPtr<ChangeUnitChangeWrapper>,1>::Add(a1 + 232, v9);
    if ( v6 >= 0 )
      v6 = HashTable<SyncId,SharedRefPtr<ChangeUnitChangeWrapper>,DefaultHashTableContext>::AddItem(
             a1 + 256,
             *(_QWORD *)v9 + 80LL,
             v9);
    v7 = (unsigned int)(v7 + 1);
    if ( v6 < 0 )
      goto LABEL_20;
  }
  v10 = *(_DWORD *)(v8 + 200);
  v11 = (_OWORD *)(a1 + 184);
  *(_DWORD *)(a1 + 200) = v10;
  if ( (v10 & 2) == 0 )
  {
    *v11 = *(_OWORD *)(*a2 + 184);
LABEL_19:
    *(_DWORD *)(a1 + 224) = 1;
    SyncId::operator=(a1 + 152, *a2 + 152);
    SyncId::operator=(a1 + 136, *a2 + 136);
    v14 = *(_OWORD *)(*a2 + 168);
    *(_DWORD *)(a1 + 208) = 0;
    *(_OWORD *)(a1 + 168) = v14;
    goto LABEL_20;
  }
  v16 = 0;
  *(_DWORD *)(a1 + 200) = v10 & 0xFFFFFFFC | 1;
  v12 = *(_QWORD *)(a1 + 144);
  if ( (*(_DWORD *)(a1 + 140) & 0x20000) == 0 )
    v12 += 4;
  v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _OWORD *, _QWORD, int *, __int64))(*(_QWORD *)*a3 + 88LL))(
          *a3,
          *(_QWORD *)(a1 + 104),
          v12,
          v11,
          0,
          &v16,
          a1 + 184);
  v6 = 0;
  if ( v13 != -2147024662 )
    v6 = v13;
  if ( v6 >= 0 )
    goto LABEL_19;
LABEL_20:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      23,
      (unsigned int)WPP_c46487f44df63404f221e65d0a11538d_Traceguids,
      (unsigned int)"ItemChangeWrapper::ReplaceWithUpdateDeleteConflictWinner",
      v6);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18007dd68  push    rbx
0x18007dd6a  push    rbp
0x18007dd6b  push    rsi
0x18007dd6c  push    rdi
0x18007dd6d  push    r12
0x18007dd6f  push    r13
0x18007dd71  push    r14
0x18007dd73  push    r15
0x18007dd75  sub     rsp, 48h
0x18007dd79  mov     r13, r8
0x18007dd7c  mov     rsi, rdx
0x18007dd7f  mov     rbx, rcx
0x18007dd82  mov     rcx, cs:WPP_GLOBAL_Control
0x18007dd89  lea     rax, WPP_GLOBAL_Control
0x18007dd90  cmp     rcx, rax
0x18007dd93  jz      short loc_18007DDBD
0x18007dd95  test    byte ptr [rcx+1Ch], 80h
0x18007dd99  jz      short loc_18007DDBD
0x18007dd9b  cmp     byte ptr [rcx+19h], 5
0x18007dd9f  jb      short loc_18007DDBD
0x18007dda1  mov     rcx, [rcx+10h]
0x18007dda5  lea     r9, aItemchangewrap_21; "ItemChangeWrapper::ReplaceWithUpdateDel"...
0x18007ddac  mov     edx, 16h
0x18007ddb1  lea     r8, WPP_c46487f44df63404f221e65d0a11538d_Traceguids
0x18007ddb8  call    WPP_SF_s
0x18007ddbd  lea     r15, [rbx+100h]
0x18007ddc4  xor     edi, edi
0x18007ddc6  lea     r12, [rbx+0E8h]
0x18007ddcd  mov     rcx, r15
0x18007ddd0  mov     [r12], edi
0x18007ddd4  call    ?FreeHashTable@?$HashTable@VSyncId@@V?$SharedRefPtr@VChangeUnitChangeWrapper@@@@VDefaultHashTableContext@@@@AEAAXXZ; HashTable<SyncId,SharedRefPtr<ChangeUnitChangeWrapper>,DefaultHashTableContext>::FreeHashTable(void)
0x18007ddd9  xor     ebp, ebp
0x18007dddb  mov     rax, [rsi]
0x18007ddde  cmp     ebp, [rax+0E8h]
0x18007dde4  jnb     short loc_18007DE2B
0x18007dde6  mov     rax, [rax+0F8h]
0x18007dded  mov     rcx, r12
0x18007ddf0  lea     r14, [rax+rbp*8]
0x18007ddf4  mov     rax, [r14]
0x18007ddf7  mov     rdx, r14
0x18007ddfa  mov     [rax+80h], rbx
0x18007de01  call    ?Add@?$Vector@V?$SharedRefPtr@VChangeUnitChangeWrapper@@@@$00@@QEAAJAEBV?$SharedRefPtr@VChangeUnitChangeWrapper@@@@@Z; Vector<SharedRefPtr<ChangeUnitChangeWrapper>,1>::Add(SharedRefPtr<ChangeUnitChangeWrapper> const &)
0x18007de06  mov     edi, eax
0x18007de08  test    eax, eax
0x18007de0a  js      short loc_18007DE20
0x18007de0c  mov     rdx, [r14]
0x18007de0f  mov     r8, r14
0x18007de12  add     rdx, 50h ; 'P'
0x18007de16  mov     rcx, r15
0x18007de19  call    ?AddItem@?$HashTable@VSyncId@@V?$SharedRefPtr@VChangeUnitChangeWrapper@@@@VDefaultHashTableContext@@@@QEAAJAEBVSyncId@@AEBV?$SharedRefPtr@VChangeUnitChangeWrapper@@@@@Z; HashTable<SyncId,SharedRefPtr<ChangeUnitChangeWrapper>,DefaultHashTableContext>::AddItem(SyncId const &,SharedRefPtr<ChangeUnitChangeWrapper> const &)
0x18007de1e  mov     edi, eax
0x18007de20  inc     ebp
0x18007de22  test    edi, edi
0x18007de24  jns     short loc_18007DDDB
0x18007de26  jmp     loc_18007DF13
0x18007de2b  mov     ecx, [rax+0C8h]
0x18007de31  lea     r9, [rbx+0B8h]
0x18007de38  mov     [rbx+0C8h], ecx
0x18007de3e  test    cl, 2
0x18007de41  jz      short loc_18007DEB2
0x18007de43  and     ecx, 0FFFFFFFDh
0x18007de46  mov     [rsp+88h+var_58], r9
0x18007de4b  or      ecx, 1
0x18007de4e  mov     [rsp+88h+arg_0], 0
0x18007de59  mov     [rbx+0C8h], ecx
0x18007de5f  mov     r8, [rbx+90h]
0x18007de66  mov     rcx, [r13+0]
0x18007de6a  test    dword ptr [rbx+8Ch], 20000h
0x18007de74  lea     rax, [r8+4]
0x18007de78  mov     rdx, [rcx]
0x18007de7b  cmovz   r8, rax
0x18007de7f  mov     rax, [rdx+58h]
0x18007de83  lea     rdx, [rsp+88h+arg_0]
0x18007de8b  mov     [rsp+88h+var_60], rdx
0x18007de90  mov     rdx, [rbx+68h]
0x18007de94  mov     [rsp+88h+var_68], 0
0x18007de9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dea2  xor     edi, edi
0x18007dea4  cmp     eax, 800700EAh
0x18007dea9  cmovnz  edi, eax
0x18007deac  test    edi, edi
0x18007deae  js      short loc_18007DF13
0x18007deb0  jmp     short loc_18007DEC1
0x18007deb2  mov     rax, [rsi]
0x18007deb5  movups  xmm0, xmmword ptr [rax+0B8h]
0x18007debc  movdqu  xmmword ptr [r9], xmm0
0x18007dec1  mov     dword ptr [rbx+0E0h], 1
0x18007decb  lea     rcx, [rbx+98h]
0x18007ded2  mov     rdx, [rsi]
0x18007ded5  add     rdx, 98h
0x18007dedc  call    ??4SyncId@@QEAAAEAV0@AEBV0@@Z; SyncId::operator=(SyncId const &)
0x18007dee1  mov     rdx, [rsi]
0x18007dee4  lea     rcx, [rbx+88h]
0x18007deeb  add     rdx, 88h
0x18007def2  call    ??4SyncId@@QEAAAEAV0@AEBV0@@Z; SyncId::operator=(SyncId const &)
0x18007def7  mov     rax, [rsi]
0x18007defa  movups  xmm0, xmmword ptr [rax+0A8h]
0x18007df01  mov     dword ptr [rbx+0D0h], 0
0x18007df0b  movdqu  xmmword ptr [rbx+0A8h], xmm0
0x18007df13  mov     rcx, cs:WPP_GLOBAL_Control
0x18007df1a  lea     rax, WPP_GLOBAL_Control
0x18007df21  cmp     rcx, rax
0x18007df24  jz      short loc_18007DF52
0x18007df26  test    byte ptr [rcx+1Ch], 80h
0x18007df2a  jz      short loc_18007DF52
0x18007df2c  cmp     byte ptr [rcx+19h], 5
0x18007df30  jb      short loc_18007DF52
0x18007df32  mov     rcx, [rcx+10h]
0x18007df36  lea     r9, aItemchangewrap_21; "ItemChangeWrapper::ReplaceWithUpdateDel"...
0x18007df3d  mov     edx, 17h
0x18007df42  mov     dword ptr [rsp+88h+var_68], edi
0x18007df46  lea     r8, WPP_c46487f44df63404f221e65d0a11538d_Traceguids
0x18007df4d  call    WPP_SF_sD
0x18007df52  mov     eax, edi
0x18007df54  add     rsp, 48h
0x18007df58  pop     r15
0x18007df5a  pop     r14
0x18007df5c  pop     r13
0x18007df5e  pop     r12
0x18007df60  pop     rdi
0x18007df61  pop     rsi
0x18007df62  pop     rbp
0x18007df63  pop     rbx
0x18007df64  retn
```
