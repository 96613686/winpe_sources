# CSyncMgrFolder::InitContextMenu(IDataObject *,_QCMINFO *,uint,uint)

- ea: `0x18002f000`
- end: `0x18002f30d`
- name: `?InitContextMenu@CSyncMgrFolder@@MEAAXPEAUIDataObject@@PEAU_QCMINFO@@II@Z`
- size: `781`
- prototype: `void __fastcall(CSyncMgrFolder *__hidden this, struct IDataObject *, struct _QCMINFO *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x18002f000`
- `0x18002fb04`
- `0x18002fb38`
- `0x18004226c`
- `0x18004240c`
- `0x1800425cc`
- `0x180042ab8`
- `0x180042f64`
- `0x18005292a`
- `0x180052950`

## import_xrefs

- `USER32!DeleteMenu` at `0x18002f18b`
- `USER32!DeleteMenu` at `0x18002f1e2`
- `USER32!DeleteMenu` at `0x18002f236`
- `USER32!DeleteMenu` at `0x18002f245`
- `USER32!DeleteMenu` at `0x18002f18b`
- `USER32!DeleteMenu` at `0x18002f1e2`
- `USER32!DeleteMenu` at `0x18002f236`
- `USER32!DeleteMenu` at `0x18002f245`

## pseudocode

```c
void __fastcall CSyncMgrFolder::InitContextMenu(
        CSyncMgrFolder *this,
        struct IDataObject *a2,
        struct _QCMINFO *a3,
        int a4)
{
  bool v8; // r14
  CSyncFolderBase *v9; // rcx
  CSyncFolderBase *v10; // rcx
  unsigned int v11; // r12d
  unsigned int v12; // r13d
  unsigned int v13; // r15d
  const struct _ITEMID_CHILD *v14; // rbx
  int FolderItemInfoForPidl; // eax
  HMENU hmenu; // rdx
  unsigned int v17; // r8d
  CSyncFolderBase *v18; // rcx
  CSyncFolderBase *v19; // rcx
  CSyncFolderBase *v20; // rcx
  unsigned int v21; // ebx
  CSyncFolderBase *v22; // rcx
  const void *v23; // rcx
  CSyncFolderBase *v24; // rcx
  CSyncFolderBase *v25; // rcx
  CSyncFolderBase *v26; // rcx
  CSyncFolderBase *v27; // rcx
  CSyncFolderBase *v28; // rcx
  CSyncFolderBase *v29; // rcx
  bool v30; // [rsp+30h] [rbp-D0h] BYREF
  bool v31; // [rsp+31h] [rbp-CFh] BYREF
  bool v32; // [rsp+32h] [rbp-CEh] BYREF
  bool v33; // [rsp+33h] [rbp-CDh] BYREF
  bool v34; // [rsp+34h] [rbp-CCh]
  bool v35; // [rsp+35h] [rbp-CBh] BYREF
  bool v36; // [rsp+36h] [rbp-CAh] BYREF
  bool v37; // [rsp+37h] [rbp-C9h] BYREF
  bool v38; // [rsp+38h] [rbp-C8h] BYREF
  struct _IDA *v39; // [rsp+40h] [rbp-C0h] BYREF
  CSyncFolderBase *v40; // [rsp+48h] [rbp-B8h]
  struct tagSTGMEDIUM v41; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v42[276]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v43[258]; // [rsp+184h] [rbp+84h] BYREF
  unsigned int v44; // [rsp+388h] [rbp+288h]
  int v45; // [rsp+394h] [rbp+294h]
  int v46; // [rsp+398h] [rbp+298h]

  v40 = this;
  v31 = 0;
  v30 = 0;
  v33 = 0;
  v32 = 0;
  v36 = 0;
  v35 = 0;
  v38 = 0;
  v37 = 0;
  v8 = 0;
  v34 = 0;
  memset(&v41, 0, sizeof(v41));
  v39 = 0;
  if ( (int)SHGetItemArrayFromDataObj(a2, &v41, &v39) < 0 )
  {
    v11 = a4 + 3;
    v12 = a4 + 4;
    goto LABEL_18;
  }
  CSyncFolderBase::GetEnableDisableSupport(this, a2, &v36, &v35, &v38, &v37);
  CSyncFolderBase::GetSyncSupport(this, a2, &v31, &v30, &v33, &v32);
  v11 = a4 + 3;
  v12 = a4 + 4;
  v13 = a4 + 10;
  if ( v39->cidl == 1 )
  {
    v14 = (const struct _ITEMID_CHILD *)((char *)v39 + v39[1].cidl);
    memset_0(v42, 0, 0x550u);
    FolderItemInfoForPidl = CSyncFolderBase::GetFolderItemInfoForPidl(v40, v14, (struct SYNCMGR_FOLDERITEMINFO *)v42);
    hmenu = a3->hmenu;
    v17 = a4 + 3;
    if ( FolderItemInfoForPidl >= 0 )
    {
      CSyncFolderBase::FormatNameIntoMenuItem(v10, hmenu, v11, v43);
      CSyncFolderBase::FormatNameIntoMenuItem(v18, a3->hmenu, v12, v43);
      if ( (v44 & 0x2000) != 0 )
        CSyncFolderBase::FormatNameIntoMenuItem(v19, a3->hmenu, v13, v43);
      else
        DeleteMenu(a3->hmenu, v13, 0);
      v21 = a4 + 14;
      if ( (v44 & 0x1000) != 0 )
      {
        CSyncFolderBase::FormatNameIntoMenuItem(v20, a3->hmenu, v21, v43);
        CSyncFolderBase::SetMenuItemDisposition(v22, 1, ~(v44 >> 27) & 1, a3->hmenu, a4 + 14);
      }
      else
      {
        DeleteMenu(a3->hmenu, v21, 0);
      }
      if ( v46 )
        v8 = 1;
      if ( v45 )
        v34 = 1;
      goto LABEL_16;
    }
  }
  else
  {
    hmenu = a3->hmenu;
    v17 = a4 + 3;
  }
  CSyncFolderBase::FormatNameIntoMenuItem(v10, hmenu, v17, &String2);
  CSyncFolderBase::FormatNameIntoMenuItem(v24, a3->hmenu, v12, &String2);
  DeleteMenu(a3->hmenu, v13, 0);
  DeleteMenu(a3->hmenu, a4 + 14, 0);
LABEL_16:
  ReleaseStgMediumHGLOBAL(v23, &v41);
LABEL_18:
  CSyncFolderBase::SetMenuItemDisposition(v9, v31, v30, a3->hmenu, v11);
  CSyncFolderBase::SetMenuItemDisposition(v25, v33, v32, a3->hmenu, v12);
  CSyncFolderBase::SetMenuItemDisposition(v26, 1, v8, a3->hmenu, a4 + 5);
  CSyncFolderBase::SetMenuItemDisposition(v27, 1, v34, a3->hmenu, a4 + 6);
  CSyncFolderBase::SetMenuItemDisposition(v28, v36, v35, a3->hmenu, a4 + 7);
  CSyncFolderBase::SetMenuItemDisposition(v29, v38, v37, a3->hmenu, a4 + 8);
}

```

## disassembly

```asm
0x18002f000  push    rbp
0x18002f002  push    rbx
0x18002f003  push    rsi
0x18002f004  push    rdi
0x18002f005  push    r12
0x18002f007  push    r13
0x18002f009  push    r14
0x18002f00b  push    r15
0x18002f00d  lea     rbp, [rsp-4D8h]
0x18002f015  sub     rsp, 5D8h
0x18002f01c  mov     rax, cs:__security_cookie
0x18002f023  xor     rax, rsp
0x18002f026  mov     [rbp+510h+var_50], rax
0x18002f02d  xor     r12d, r12d
0x18002f030  mov     [rsp+610h+var_5C8], rcx
0x18002f035  mov     r15, rdx
0x18002f038  mov     [rsp+610h+var_5DF], r12b
0x18002f03d  mov     rdi, r8
0x18002f040  mov     [rsp+610h+var_5E0], r12b
0x18002f045  mov     rbx, rcx
0x18002f048  mov     [rsp+610h+var_5DD], r12b
0x18002f04d  xorps   xmm0, xmm0
0x18002f050  mov     [rsp+610h+var_5DE], r12b
0x18002f055  xor     eax, eax
0x18002f057  mov     [rsp+610h+var_5DA], r12b
0x18002f05c  mov     rcx, r15; struct IDataObject *
0x18002f05f  mov     [rsp+610h+var_5DB], r12b
0x18002f064  lea     r8, [rsp+610h+var_5D0]; struct _IDA **
0x18002f069  mov     [rsp+610h+var_5D8], r12b
0x18002f06e  lea     rdx, [rsp+610h+var_5C0]; struct tagSTGMEDIUM *
0x18002f073  mov     [rsp+610h+var_5D9], r12b
0x18002f078  mov     esi, r9d
0x18002f07b  movzx   r14d, r12b
0x18002f07f  mov     [rsp+610h+var_5DC], r12b
0x18002f084  movups  xmmword ptr [rsp+610h+var_5C0.tymed], xmm0
0x18002f089  mov     [rsp+610h+var_5C0.pUnkForRelease], rax
0x18002f08e  mov     [rsp+610h+var_5D0], r12
0x18002f093  call    ?SHGetItemArrayFromDataObj@@YAJPEAUIDataObject@@PEAUtagSTGMEDIUM@@PEAPEAU_IDA@@@Z; SHGetItemArrayFromDataObj(IDataObject *,tagSTGMEDIUM *,_IDA * *)
0x18002f098  test    eax, eax
0x18002f09a  js      loc_18002F257
0x18002f0a0  lea     rax, [rsp+610h+var_5D9]
0x18002f0a5  mov     rdx, r15; struct IDataObject *
0x18002f0a8  mov     [rsp+610h+var_5E8], rax; bool *
0x18002f0ad  lea     r9, [rsp+610h+var_5DB]; bool *
0x18002f0b2  lea     rax, [rsp+610h+var_5D8]
0x18002f0b7  mov     rcx, rbx; this
0x18002f0ba  lea     r8, [rsp+610h+var_5DA]; bool *
0x18002f0bf  mov     [rsp+610h+var_5F0], rax; bool *
0x18002f0c4  call    ?GetEnableDisableSupport@CSyncFolderBase@@IEAAXPEAUIDataObject@@PEA_N111@Z; CSyncFolderBase::GetEnableDisableSupport(IDataObject *,bool *,bool *,bool *,bool *)
0x18002f0c9  lea     rax, [rsp+610h+var_5DE]
0x18002f0ce  mov     rdx, r15; struct IDataObject *
0x18002f0d1  mov     [rsp+610h+var_5E8], rax; bool *
0x18002f0d6  lea     r9, [rsp+610h+var_5E0]; bool *
0x18002f0db  lea     rax, [rsp+610h+var_5DD]
0x18002f0e0  mov     rcx, rbx; this
0x18002f0e3  lea     r8, [rsp+610h+var_5DF]; bool *
0x18002f0e8  mov     [rsp+610h+var_5F0], rax; bool *
0x18002f0ed  call    ?GetSyncSupport@CSyncFolderBase@@IEAAXPEAUIDataObject@@PEA_N111@Z; CSyncFolderBase::GetSyncSupport(IDataObject *,bool *,bool *,bool *,bool *)
0x18002f0f2  mov     rdx, [rsp+610h+var_5D0]
0x18002f0f7  lea     r12d, [rsi+3]
0x18002f0fb  lea     r13d, [rsi+4]
0x18002f0ff  lea     r15d, [rsi+0Ah]
0x18002f103  cmp     dword ptr [rdx], 1
0x18002f106  jnz     loc_18002F209
0x18002f10c  mov     ebx, [rdx+8]
0x18002f10f  lea     rcx, [rsp+610h+var_5A0]; void *
0x18002f114  add     rbx, rdx
0x18002f117  mov     r8d, 550h; Size
0x18002f11d  xor     edx, edx; Val
0x18002f11f  call    memset_0
0x18002f124  mov     rcx, [rsp+610h+var_5C8]; this
0x18002f129  lea     r8, [rsp+610h+var_5A0]; struct SYNCMGR_FOLDERITEMINFO *
0x18002f12e  mov     rdx, rbx; struct _ITEMID_CHILD *
0x18002f131  call    ?GetFolderItemInfoForPidl@CSyncFolderBase@@IEAAJPEFBU_ITEMID_CHILD@@PEAUSYNCMGR_FOLDERITEMINFO@@@Z; CSyncFolderBase::GetFolderItemInfoForPidl(_ITEMID_CHILD const *,SYNCMGR_FOLDERITEMINFO *)
0x18002f136  mov     rdx, [rdi]; HMENU
0x18002f139  mov     r8d, r12d; unsigned int
0x18002f13c  test    eax, eax
0x18002f13e  js      loc_18002F20F
0x18002f144  lea     r9, [rbp+510h+var_48C]; unsigned __int16 *
0x18002f14b  call    ?FormatNameIntoMenuItem@CSyncFolderBase@@IEBAJPEAUHMENU__@@IPEBG@Z; CSyncFolderBase::FormatNameIntoMenuItem(HMENU__ *,uint,ushort const *)
0x18002f150  mov     rdx, [rdi]; HMENU
0x18002f153  lea     r9, [rbp+510h+var_48C]; unsigned __int16 *
0x18002f15a  mov     r8d, r13d; unsigned int
0x18002f15d  call    ?FormatNameIntoMenuItem@CSyncFolderBase@@IEBAJPEAUHMENU__@@IPEBG@Z; CSyncFolderBase::FormatNameIntoMenuItem(HMENU__ *,uint,ushort const *)
0x18002f162  test    [rbp+510h+var_288], 2000h
0x18002f16c  jz      short loc_18002F182
0x18002f16e  mov     rdx, [rdi]; HMENU
0x18002f171  lea     r9, [rbp+510h+var_48C]; unsigned __int16 *
0x18002f178  mov     r8d, r15d; unsigned int
0x18002f17b  call    ?FormatNameIntoMenuItem@CSyncFolderBase@@IEBAJPEAUHMENU__@@IPEBG@Z; CSyncFolderBase::FormatNameIntoMenuItem(HMENU__ *,uint,ushort const *)
0x18002f180  jmp     short loc_18002F191
0x18002f182  mov     rcx, [rdi]; hMenu
0x18002f185  xor     r8d, r8d; uFlags
0x18002f188  mov     edx, r15d; uPosition
0x18002f18b  call    cs:__imp_DeleteMenu
0x18002f191  test    [rbp+510h+var_288], 1000h
0x18002f19b  lea     ebx, [rsi+0Eh]
0x18002f19e  jz      short loc_18002F1DA
0x18002f1a0  mov     rdx, [rdi]; HMENU
0x18002f1a3  lea     r9, [rbp+510h+var_48C]; unsigned __int16 *
0x18002f1aa  mov     r8d, ebx; unsigned int
0x18002f1ad  call    ?FormatNameIntoMenuItem@CSyncFolderBase@@IEBAJPEAUHMENU__@@IPEBG@Z; CSyncFolderBase::FormatNameIntoMenuItem(HMENU__ *,uint,ushort const *)
0x18002f1b2  mov     r8d, [rbp+510h+var_288]
0x18002f1b9  mov     r15d, 1
0x18002f1bf  mov     r9, [rdi]; HMENU
0x18002f1c2  mov     dl, r15b; bool
0x18002f1c5  shr     r8d, 1Bh
0x18002f1c9  not     r8b
0x18002f1cc  mov     dword ptr [rsp+610h+var_5F0], ebx; unsigned int
0x18002f1d0  and     r8b, r15b; bool
0x18002f1d3  call    ?SetMenuItemDisposition@CSyncFolderBase@@IEBAX_N0PEAUHMENU__@@I@Z; CSyncFolderBase::SetMenuItemDisposition(bool,bool,HMENU__ *,uint)
0x18002f1d8  jmp     short loc_18002F1EE
0x18002f1da  mov     rcx, [rdi]; hMenu
0x18002f1dd  xor     r8d, r8d; uFlags
0x18002f1e0  mov     edx, ebx; uPosition
0x18002f1e2  call    cs:__imp_DeleteMenu
0x18002f1e8  mov     r15d, 1
0x18002f1ee  cmp     [rbp+510h+var_278], 0
0x18002f1f5  cmova   r14d, r15d
0x18002f1f9  cmp     [rbp+510h+var_27C], 0
0x18002f200  jbe     short loc_18002F24B
0x18002f202  mov     [rsp+610h+var_5DC], r15b
0x18002f207  jmp     short loc_18002F24B
0x18002f209  mov     rdx, [rdi]; HMENU
0x18002f20c  mov     r8d, r12d; unsigned int
0x18002f20f  lea     r9, String2; unsigned __int16 *
0x18002f216  call    ?FormatNameIntoMenuItem@CSyncFolderBase@@IEBAJPEAUHMENU__@@IPEBG@Z; CSyncFolderBase::FormatNameIntoMenuItem(HMENU__ *,uint,ushort const *)
0x18002f21b  mov     rdx, [rdi]; HMENU
0x18002f21e  lea     r9, String2; unsigned __int16 *
0x18002f225  mov     r8d, r13d; unsigned int
0x18002f228  call    ?FormatNameIntoMenuItem@CSyncFolderBase@@IEBAJPEAUHMENU__@@IPEBG@Z; CSyncFolderBase::FormatNameIntoMenuItem(HMENU__ *,uint,ushort const *)
0x18002f22d  mov     rcx, [rdi]; hMenu
0x18002f230  xor     r8d, r8d; uFlags
0x18002f233  mov     edx, r15d; uPosition
0x18002f236  call    cs:__imp_DeleteMenu
0x18002f23c  mov     rcx, [rdi]; hMenu
0x18002f23f  lea     edx, [rsi+0Eh]; uPosition
0x18002f242  xor     r8d, r8d; uFlags
0x18002f245  call    cs:__imp_DeleteMenu
0x18002f24b  lea     rdx, [rsp+610h+var_5C0]; struct tagSTGMEDIUM *
0x18002f250  call    ?ReleaseStgMediumHGLOBAL@@YAXPEBXPEAUtagSTGMEDIUM@@@Z; ReleaseStgMediumHGLOBAL(void const *,tagSTGMEDIUM *)
0x18002f255  jmp     short loc_18002F25F
0x18002f257  lea     r12d, [rsi+3]
0x18002f25b  lea     r13d, [rsi+4]
0x18002f25f  mov     r9, [rdi]; HMENU
0x18002f262  mov     r8b, [rsp+610h+var_5E0]; bool
0x18002f267  mov     dl, [rsp+610h+var_5DF]; bool
0x18002f26b  mov     dword ptr [rsp+610h+var_5F0], r12d; unsigned int
0x18002f270  call    ?SetMenuItemDisposition@CSyncFolderBase@@IEBAX_N0PEAUHMENU__@@I@Z; CSyncFolderBase::SetMenuItemDisposition(bool,bool,HMENU__ *,uint)
0x18002f275  mov     r9, [rdi]; HMENU
0x18002f278  mov     r8b, [rsp+610h+var_5DE]; bool
0x18002f27d  mov     dl, [rsp+610h+var_5DD]; bool
0x18002f281  mov     dword ptr [rsp+610h+var_5F0], r13d; unsigned int
0x18002f286  call    ?SetMenuItemDisposition@CSyncFolderBase@@IEBAX_N0PEAUHMENU__@@I@Z; CSyncFolderBase::SetMenuItemDisposition(bool,bool,HMENU__ *,uint)
0x18002f28b  mov     r9, [rdi]; HMENU
0x18002f28e  lea     eax, [rsi+5]
0x18002f291  mov     ebx, 1
0x18002f296  mov     dword ptr [rsp+610h+var_5F0], eax; unsigned int
0x18002f29a  mov     dl, bl; bool
0x18002f29c  mov     r8b, r14b; bool
0x18002f29f  call    ?SetMenuItemDisposition@CSyncFolderBase@@IEBAX_N0PEAUHMENU__@@I@Z; CSyncFolderBase::SetMenuItemDisposition(bool,bool,HMENU__ *,uint)
0x18002f2a4  mov     r9, [rdi]; HMENU
0x18002f2a7  lea     eax, [rsi+6]
0x18002f2aa  mov     r8b, [rsp+610h+var_5DC]; bool
0x18002f2af  mov     dl, bl; bool
0x18002f2b1  mov     dword ptr [rsp+610h+var_5F0], eax; unsigned int
0x18002f2b5  call    ?SetMenuItemDisposition@CSyncFolderBase@@IEBAX_N0PEAUHMENU__@@I@Z; CSyncFolderBase::SetMenuItemDisposition(bool,bool,HMENU__ *,uint)
0x18002f2ba  mov     r9, [rdi]; HMENU
0x18002f2bd  lea     eax, [rsi+7]
0x18002f2c0  mov     r8b, [rsp+610h+var_5DB]; bool
0x18002f2c5  mov     dl, [rsp+610h+var_5DA]; bool
0x18002f2c9  mov     dword ptr [rsp+610h+var_5F0], eax; unsigned int
0x18002f2cd  call    ?SetMenuItemDisposition@CSyncFolderBase@@IEBAX_N0PEAUHMENU__@@I@Z; CSyncFolderBase::SetMenuItemDisposition(bool,bool,HMENU__ *,uint)
0x18002f2d2  mov     r9, [rdi]; HMENU
0x18002f2d5  lea     eax, [rsi+8]
0x18002f2d8  mov     r8b, [rsp+610h+var_5D9]; bool
0x18002f2dd  mov     dl, [rsp+610h+var_5D8]; bool
0x18002f2e1  mov     dword ptr [rsp+610h+var_5F0], eax; unsigned int
0x18002f2e5  call    ?SetMenuItemDisposition@CSyncFolderBase@@IEBAX_N0PEAUHMENU__@@I@Z; CSyncFolderBase::SetMenuItemDisposition(bool,bool,HMENU__ *,uint)
0x18002f2ea  mov     rcx, [rbp+510h+var_50]
0x18002f2f1  xor     rcx, rsp; StackCookie
0x18002f2f4  call    __security_check_cookie
0x18002f2f9  add     rsp, 5D8h
0x18002f300  pop     r15
0x18002f302  pop     r14
0x18002f304  pop     r13
0x18002f306  pop     r12
0x18002f308  pop     rdi
0x18002f309  pop     rsi
0x18002f30a  pop     rbx
0x18002f30b  pop     rbp
0x18002f30c  retn
```
