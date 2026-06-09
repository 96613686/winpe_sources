# EnumOutboundRoutingGroupsCB(HKEY__ *,ushort const *,ulong,void *)

- ea: `0x14005fb50`
- end: `0x14005fdef`
- name: `?EnumOutboundRoutingGroupsCB@@YAHPEAUHKEY__@@PEBGKPEAX@Z`
- size: `671`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, unsigned int, void *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x140001bac`
- `0x140004c78`
- `0x140004ca8`
- `0x140004f64`
- `0x14000effc`
- `0x14005f7fc`
- `0x14005fb50`
- `0x14005ffe4`
- `0x1400699d0`
- `0x140074f18`
- `0x14007566c`

## import_xrefs

- `ADVAPI32!RegDeleteKeyW` at `0x14005fced`
- `ADVAPI32!RegDeleteKeyW` at `0x14005fced`
- `KERNEL32!GetLastError` at `0x14005fcab`
- `KERNEL32!GetLastError` at `0x14005fcab`
- `msvcrt!_wcsicmp` at `0x14005fbf1`
- `msvcrt!_wcsicmp` at `0x14005fbf1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EnumOutboundRoutingGroupsCB(HKEY a1, const unsigned __int16 *a2, __int64 a3, _DWORD *a4)
{
  CMapDeviceId *v7; // rcx
  _QWORD **v8; // rax
  _QWORD **v9; // rdi
  _QWORD *v10; // rcx
  _QWORD *v11; // rbx
  _QWORD *v12; // rcx
  _QWORD *v13; // rbx
  unsigned int v15; // eax
  unsigned int v16; // edi
  int v17; // ebp
  HKEY v18; // rax
  DWORD LastError; // eax
  LSTATUS v20; // eax
  DWORD v21; // r9d
  unsigned int v22; // eax
  _QWORD *v23; // rdi
  _QWORD *v24; // rcx
  _QWORD *v25; // rbx
  void *Block[2]; // [rsp+30h] [rbp-38h] BYREF

  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, WPP_b9c408ceb555301912c179a0f26e2108_Traceguids);
  }
  Block[1] = 0;
  v8 = (_QWORD **)std::_List_alloc<0,std::_List_base_types<unsigned long>>::_Buynode0(v7, 0, 0);
  v9 = v8;
  Block[0] = v8;
  if ( !a2 )
  {
    v10 = *v8;
    *v8 = v8;
    v8[1] = v8;
    if ( v10 != v8 )
    {
      do
      {
        v11 = (_QWORD *)*v10;
        operator delete(v10);
        v10 = v11;
      }
      while ( v11 != v9 );
    }
LABEL_13:
    operator delete(v9);
    return 1;
  }
  if ( _wcsicmp(a2, L"<All devices>") && !(unsigned int)IsServerSku() )
  {
    v12 = *v9;
    *v9 = v9;
    v9[1] = v9;
    if ( v12 != v9 )
    {
      do
      {
        v13 = (_QWORD *)*v12;
        operator delete(v12);
        v12 = v13;
      }
      while ( v13 != v9 );
    }
    goto LABEL_13;
  }
  v15 = COutboundRoutingGroup::Load((COutboundRoutingGroup *)Block, a1, a2);
  v16 = v15;
  if ( v15 )
  {
    v17 = 0;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        81,
        (unsigned int)WPP_b9c408ceb555301912c179a0f26e2108_Traceguids,
        (_DWORD)a2,
        v15);
    }
    v18 = OpenRegistryKey(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax\\Outbound Routing\\Groups", 0, 0x3001Fu);
    if ( v18 )
    {
      v20 = RegDeleteKeyW(v18, a2);
      if ( v20 )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            83,
            (unsigned int)WPP_b9c408ceb555301912c179a0f26e2108_Traceguids,
            (_DWORD)a2,
            v20);
        }
      }
      else
      {
        v17 = 1;
      }
    }
    else
    {
      LastError = GetLastError();
      v16 = LastError;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, WPP_b9c408ceb555301912c179a0f26e2108_Traceguids, LastError);
      }
    }
    if ( !v16 )
      goto LABEL_40;
    if ( v17 )
    {
      v21 = -1073709757;
LABEL_39:
      FaxLog(1u, 1u, 1u, v21, (char)a2);
      goto LABEL_40;
    }
LABEL_38:
    v21 = -1073709754;
    goto LABEL_39;
  }
  v22 = COutboundRoutingGroupsMap::AddGroup(g_pGroupsMap, a2, (struct COutboundRoutingGroup *)Block);
  if ( v22 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        84,
        (unsigned int)WPP_b9c408ceb555301912c179a0f26e2108_Traceguids,
        (_DWORD)a2,
        v22);
    }
    goto LABEL_38;
  }
LABEL_40:
  *a4 = 0;
  v23 = Block[0];
  v24 = *(_QWORD **)Block[0];
  *(_QWORD *)Block[0] = Block[0];
  v23[1] = v23;
  if ( v24 != v23 )
  {
    do
    {
      v25 = (_QWORD *)*v24;
      operator delete(v24);
      v24 = v25;
    }
    while ( v25 != v23 );
  }
  operator delete(v23);
  return 1;
}

```

## disassembly

```asm
0x14005fb50  mov     [rsp+arg_0], rbx
0x14005fb55  mov     [rsp+arg_10], rbp
0x14005fb5a  push    rsi
0x14005fb5b  push    rdi
0x14005fb5c  push    r12
0x14005fb5e  push    r13
0x14005fb60  push    r14
0x14005fb62  sub     rsp, 40h
0x14005fb66  mov     r14, r9
0x14005fb69  mov     rbx, rdx
0x14005fb6c  mov     rsi, rcx
0x14005fb6f  lea     r12, WPP_GLOBAL_Control
0x14005fb76  lea     r13, WPP_b9c408ceb555301912c179a0f26e2108_Traceguids
0x14005fb7d  mov     rcx, cs:WPP_GLOBAL_Control
0x14005fb84  cmp     rcx, r12
0x14005fb87  jz      short loc_14005FBA6
0x14005fb89  test    byte ptr [rcx+1Ch], 4
0x14005fb8d  jz      short loc_14005FBA6
0x14005fb8f  cmp     byte ptr [rcx+19h], 5
0x14005fb93  jb      short loc_14005FBA6
0x14005fb95  mov     edx, 50h ; 'P'
0x14005fb9a  mov     r8, r13
0x14005fb9d  mov     rcx, [rcx+10h]
0x14005fba1  call    WPP_SF_
0x14005fba6  mov     [rsp+68h+var_30], 0
0x14005fbaf  xor     r8d, r8d
0x14005fbb2  xor     edx, edx
0x14005fbb4  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@KV?$allocator@K@std@@@std@@@std@@QEAAPEAU?$_List_node@KPEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<ulong>>::_Buynode0(std::_List_node<ulong,void *> *,std::_List_node<ulong,void *> *)
0x14005fbb9  mov     rdi, rax
0x14005fbbc  mov     [rsp+68h+Block], rax
0x14005fbc1  test    rbx, rbx
0x14005fbc4  jnz     short loc_14005FBE7
0x14005fbc6  mov     rcx, [rax]; Block
0x14005fbc9  mov     [rax], rax
0x14005fbcc  mov     [rax+8], rax
0x14005fbd0  cmp     rcx, rax
0x14005fbd3  jz      short loc_14005FC29
0x14005fbd5  mov     rbx, [rcx]
0x14005fbd8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14005fbdd  mov     rcx, rbx
0x14005fbe0  cmp     rbx, rdi
0x14005fbe3  jnz     short loc_14005FBD5
0x14005fbe5  jmp     short loc_14005FC29
0x14005fbe7  lea     rdx, aAllDevices; "<All devices>"
0x14005fbee  mov     rcx, rbx; String1
0x14005fbf1  call    cs:__imp__wcsicmp
0x14005fbf8  nop     dword ptr [rax+rax+00h]
0x14005fbfd  test    eax, eax
0x14005fbff  jz      short loc_14005FC3B
0x14005fc01  call    IsServerSku
0x14005fc06  test    eax, eax
0x14005fc08  jnz     short loc_14005FC3B
0x14005fc0a  mov     rcx, [rdi]; Block
0x14005fc0d  mov     [rdi], rdi
0x14005fc10  mov     [rdi+8], rdi
0x14005fc14  cmp     rcx, rdi
0x14005fc17  jz      short loc_14005FC29
0x14005fc19  mov     rbx, [rcx]
0x14005fc1c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14005fc21  mov     rcx, rbx
0x14005fc24  cmp     rbx, rdi
0x14005fc27  jnz     short loc_14005FC19
0x14005fc29  mov     rcx, rdi; Block
0x14005fc2c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14005fc31  mov     eax, 1
0x14005fc36  jmp     loc_14005FDD5
0x14005fc3b  mov     r8, rbx; unsigned __int16 *
0x14005fc3e  mov     rdx, rsi; HKEY
0x14005fc41  lea     rcx, [rsp+68h+Block]; this
0x14005fc46  call    ?Load@COutboundRoutingGroup@@QEAAKPEAUHKEY__@@PEBG@Z; COutboundRoutingGroup::Load(HKEY__ *,ushort const *)
0x14005fc4b  mov     edi, eax
0x14005fc4d  mov     esi, 1
0x14005fc52  test    eax, eax
0x14005fc54  jz      loc_14005FD41
0x14005fc5a  xor     ebp, ebp
0x14005fc5c  mov     rcx, cs:WPP_GLOBAL_Control
0x14005fc63  cmp     rcx, r12
0x14005fc66  jz      short loc_14005FC8A
0x14005fc68  test    byte ptr [rcx+1Ch], 4
0x14005fc6c  jz      short loc_14005FC8A
0x14005fc6e  cmp     byte ptr [rcx+19h], 2
0x14005fc72  jb      short loc_14005FC8A
0x14005fc74  lea     edx, [rsi+50h]
0x14005fc77  mov     dword ptr [rsp+68h+var_48], eax
0x14005fc7b  mov     r9, rbx
0x14005fc7e  mov     r8, r13
0x14005fc81  mov     rcx, [rcx+10h]
0x14005fc85  call    WPP_SF_Sd
0x14005fc8a  mov     r9d, 3001Fh
0x14005fc90  xor     r8d, r8d
0x14005fc93  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\Fax\\Outbound Rout"...
0x14005fc9a  mov     rcx, 0FFFFFFFF80000002h
0x14005fca1  call    OpenRegistryKey
0x14005fca6  test    rax, rax
0x14005fca9  jnz     short loc_14005FCE7
0x14005fcab  call    cs:__imp_GetLastError
0x14005fcb2  nop     dword ptr [rax+rax+00h]
0x14005fcb7  mov     edi, eax
0x14005fcb9  mov     rcx, cs:WPP_GLOBAL_Control
0x14005fcc0  cmp     rcx, r12
0x14005fcc3  jz      short loc_14005FD31
0x14005fcc5  test    byte ptr [rcx+1Ch], 4
0x14005fcc9  jz      short loc_14005FD31
0x14005fccb  cmp     byte ptr [rcx+19h], 2
0x14005fccf  jb      short loc_14005FD31
0x14005fcd1  mov     edx, 52h ; 'R'
0x14005fcd6  mov     r9d, eax
0x14005fcd9  mov     r8, r13
0x14005fcdc  mov     rcx, [rcx+10h]
0x14005fce0  call    WPP_SF_d
0x14005fce5  jmp     short loc_14005FD31
0x14005fce7  mov     rdx, rbx; lpSubKey
0x14005fcea  mov     rcx, rax; hKey
0x14005fced  call    cs:__imp_RegDeleteKeyW
0x14005fcf4  nop     dword ptr [rax+rax+00h]
0x14005fcf9  test    eax, eax
0x14005fcfb  jz      short loc_14005FD2F
0x14005fcfd  mov     rcx, cs:WPP_GLOBAL_Control
0x14005fd04  cmp     rcx, r12
0x14005fd07  jz      short loc_14005FD31
0x14005fd09  test    byte ptr [rcx+1Ch], 4
0x14005fd0d  jz      short loc_14005FD31
0x14005fd0f  cmp     byte ptr [rcx+19h], 2
0x14005fd13  jb      short loc_14005FD31
0x14005fd15  mov     edx, 53h ; 'S'
0x14005fd1a  mov     dword ptr [rsp+68h+var_48], eax
0x14005fd1e  mov     r9, rbx
0x14005fd21  mov     r8, r13
0x14005fd24  mov     rcx, [rcx+10h]
0x14005fd28  call    WPP_SF_Sd
0x14005fd2d  jmp     short loc_14005FD31
0x14005fd2f  mov     ebp, esi
0x14005fd31  test    edi, edi
0x14005fd33  jz      short loc_14005FDA0
0x14005fd35  test    ebp, ebp
0x14005fd37  jz      short loc_14005FD89
0x14005fd39  mov     r9d, 0C0007D43h
0x14005fd3f  jmp     short loc_14005FD8F
0x14005fd41  lea     r8, [rsp+68h+Block]; struct COutboundRoutingGroup *
0x14005fd46  mov     rdx, rbx; unsigned __int16 *
0x14005fd49  mov     rcx, cs:?g_pGroupsMap@@3PEAVCOutboundRoutingGroupsMap@@EA; this
0x14005fd50  call    ?AddGroup@COutboundRoutingGroupsMap@@QEAAKPEBGPEAVCOutboundRoutingGroup@@@Z; COutboundRoutingGroupsMap::AddGroup(ushort const *,COutboundRoutingGroup *)
0x14005fd55  test    eax, eax
0x14005fd57  jz      short loc_14005FDA0
0x14005fd59  mov     rcx, cs:WPP_GLOBAL_Control
0x14005fd60  cmp     rcx, r12
0x14005fd63  jz      short loc_14005FD89
0x14005fd65  test    byte ptr [rcx+1Ch], 4
0x14005fd69  jz      short loc_14005FD89
0x14005fd6b  cmp     byte ptr [rcx+19h], 2
0x14005fd6f  jb      short loc_14005FD89
0x14005fd71  mov     edx, 54h ; 'T'
0x14005fd76  mov     dword ptr [rsp+68h+var_48], eax
0x14005fd7a  mov     r9, rbx
0x14005fd7d  mov     r8, r13
0x14005fd80  mov     rcx, [rcx+10h]
0x14005fd84  call    WPP_SF_Sd
0x14005fd89  mov     r9d, 0C0007D46h
0x14005fd8f  mov     [rsp+68h+var_48], rbx
0x14005fd94  mov     r8d, esi
0x14005fd97  mov     edx, esi
0x14005fd99  mov     ecx, esi
0x14005fd9b  call    FaxLog
0x14005fda0  mov     dword ptr [r14], 0
0x14005fda7  mov     rdi, [rsp+68h+Block]
0x14005fdac  mov     rcx, [rdi]; Block
0x14005fdaf  mov     [rdi], rdi
0x14005fdb2  mov     [rdi+8], rdi
0x14005fdb6  cmp     rcx, rdi
0x14005fdb9  jz      short loc_14005FDCB
0x14005fdbb  mov     rbx, [rcx]
0x14005fdbe  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14005fdc3  mov     rcx, rbx
0x14005fdc6  cmp     rbx, rdi
0x14005fdc9  jnz     short loc_14005FDBB
0x14005fdcb  mov     rcx, rdi; Block
0x14005fdce  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14005fdd3  mov     eax, esi
0x14005fdd5  lea     r11, [rsp+68h+var_28]
0x14005fdda  mov     rbx, [r11+30h]
0x14005fdde  mov     rbp, [r11+40h]
0x14005fde2  mov     rsp, r11
0x14005fde5  pop     r14
0x14005fde7  pop     r13
0x14005fde9  pop     r12
0x14005fdeb  pop     rdi
0x14005fdec  pop     rsi
0x14005fded  retn
```
