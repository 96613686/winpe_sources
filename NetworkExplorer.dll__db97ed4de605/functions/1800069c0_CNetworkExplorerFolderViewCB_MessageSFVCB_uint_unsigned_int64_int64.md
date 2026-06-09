# CNetworkExplorerFolderViewCB::MessageSFVCB(uint,unsigned __int64,__int64)

- ea: `0x1800069c0`
- end: `0x180006a6d`
- name: `?MessageSFVCB@CNetworkExplorerFolderViewCB@@UEAAJI_K_J@Z`
- size: `173`
- prototype: `__int64 __fastcall(CNetworkExplorerFolderViewCB *__hidden this, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000693c`
- `0x1800069c0`
- `0x18000c984`
- `0x18000caa8`
- `0x18000cb00`
- `0x18000ced8`

## import_xrefs

- `SHELL32!__imp_Create_IEnumUICommandFromDefArray` at `0x180006a48`

## pseudocode

```c
__int64 __fastcall CNetworkExplorerFolderViewCB::MessageSFVCB(
        CNetworkExplorerFolderViewCB *this,
        int a2,
        struct _ITEMIDLIST_ABSOLUTE **a3,
        __int64 a4)
{
  CNetworkExplorerFolderViewCB *v4; // rbx
  int v5; // edx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  int v9; // edx
  int v10; // edx
  int v11; // edx

  v4 = this;
  v5 = a2 - 16;
  if ( !v5 )
  {
LABEL_11:
    CNetworkExplorerFolderViewCB::_StopProgressBar(this);
    return 0;
  }
  v6 = v5 - 1;
  if ( !v6 )
    return CNetworkExplorerFolderViewCB::_OnRefresh(this, 0, (unsigned int)a3);
  v7 = v6 - 32;
  if ( !v7 )
    return CNetworkExplorerFolderViewCB::_OnGetNotify(this, 0, a3, (int *)a4);
  v8 = v7 - 25;
  if ( !v8 )
    return CNetworkExplorerFolderViewCB::_OnDelayWindowCreate(this, 0, (HWND)a3);
  v9 = v8 - 4;
  if ( !v9 )
    return 0;
  v10 = v9 - 6;
  if ( v10 )
  {
    v11 = v10 - 8;
    if ( !v11 )
    {
      *(_DWORD *)a4 = 6;
      *(_DWORD *)(a4 + 4) = 1;
      *(_DWORD *)(a4 + 8) = 1;
      *(_QWORD *)(a4 + 12) = 1;
      return 0;
    }
    if ( v11 != 11 )
      return 2147500037LL;
    CNetworkExplorerFolderViewCB::_StopTimer(this);
    this = v4;
    goto LABEL_11;
  }
  *(_OWORD *)a4 = 0;
  *(_QWORD *)(a4 + 16) = 0;
  return Create_IEnumUICommandFromDefArray(this, &off_180011F40, 3);
}

```

## disassembly

```asm
0x1800069c0  push    rbx
0x1800069c2  sub     rsp, 20h
0x1800069c6  mov     rbx, rcx
0x1800069c9  sub     edx, 10h
0x1800069cc  jz      short loc_180006A04
0x1800069ce  sub     edx, 1; unsigned int
0x1800069d1  jz      loc_180006A63
0x1800069d7  sub     edx, 20h ; ' '; unsigned int
0x1800069da  jz      short loc_180006A59
0x1800069dc  sub     edx, 19h; unsigned int
0x1800069df  jz      short loc_180006A4F
0x1800069e1  sub     edx, 4
0x1800069e4  jz      short loc_180006A09
0x1800069e6  sub     edx, 6
0x1800069e9  jz      short loc_180006A2B
0x1800069eb  sub     edx, 8
0x1800069ee  jz      short loc_180006A11
0x1800069f0  cmp     edx, 0Bh
0x1800069f3  jz      short loc_1800069FC
0x1800069f5  mov     eax, 80004005h
0x1800069fa  jmp     short loc_180006A0B
0x1800069fc  call    ?_StopTimer@CNetworkExplorerFolderViewCB@@AEAAJXZ; CNetworkExplorerFolderViewCB::_StopTimer(void)
0x180006a01  mov     rcx, rbx; this
0x180006a04  call    ?_StopProgressBar@CNetworkExplorerFolderViewCB@@AEAAJXZ; CNetworkExplorerFolderViewCB::_StopProgressBar(void)
0x180006a09  xor     eax, eax
0x180006a0b  add     rsp, 20h
0x180006a0f  pop     rbx
0x180006a10  retn
0x180006a11  mov     eax, 1
0x180006a16  mov     dword ptr [r9], 6
0x180006a1d  mov     [r9+4], eax
0x180006a21  mov     [r9+8], eax
0x180006a25  mov     [r9+0Ch], rax
0x180006a29  jmp     short loc_180006A09
0x180006a2b  xor     eax, eax
0x180006a2d  lea     rdx, off_180011F40
0x180006a34  xorps   xmm0, xmm0
0x180006a37  movups  xmmword ptr [r9], xmm0
0x180006a3b  mov     [r9+10h], rax
0x180006a3f  lea     r8d, [rax+3]; HWND
0x180006a43  add     rsp, 20h
0x180006a47  pop     rbx
0x180006a48  jmp     cs:__imp_Create_IEnumUICommandFromDefArray
0x180006a4f  add     rsp, 20h
0x180006a53  pop     rbx
0x180006a54  jmp     ?_OnDelayWindowCreate@CNetworkExplorerFolderViewCB@@AEAAJKPEAUHWND__@@@Z; CNetworkExplorerFolderViewCB::_OnDelayWindowCreate(ulong,HWND__ *)
0x180006a59  add     rsp, 20h
0x180006a5d  pop     rbx
0x180006a5e  jmp     ?_OnGetNotify@CNetworkExplorerFolderViewCB@@AEAAJKPEAPEAU_ITEMIDLIST_ABSOLUTE@@PEAJ@Z; CNetworkExplorerFolderViewCB::_OnGetNotify(ulong,_ITEMIDLIST_ABSOLUTE * *,long *)
0x180006a63  add     rsp, 20h
0x180006a67  pop     rbx
0x180006a68  jmp     ?_OnRefresh@CNetworkExplorerFolderViewCB@@AEAAJKI@Z; CNetworkExplorerFolderViewCB::_OnRefresh(ulong,uint)
```
