# CSyncHandlerFolder::InitContextMenu(IDataObject *,_QCMINFO *,uint,uint)

- ea: `0x180045040`
- end: `0x1800453c1`
- name: `?InitContextMenu@CSyncHandlerFolder@@MEAAXPEAUIDataObject@@PEAU_QCMINFO@@II@Z`
- size: `897`
- prototype: `void __usercall(CSyncHandlerFolder *__hidden this@<rcx>, struct IDataObject *@<rdx>, struct _QCMINFO *@<r8>, unsigned int@<r9d>, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting`

## callees

- `0x18002fb04`
- `0x18002fb38`
- `0x18004226c`
- `0x18004240c`
- `0x1800425cc`
- `0x180042ab8`
- `0x180042f64`
- `0x180045040`
- `0x18005292a`
- `0x180052950`

## import_xrefs

- `USER32!DeleteMenu` at `0x18004524c`
- `USER32!DeleteMenu` at `0x18004529d`
- `USER32!DeleteMenu` at `0x1800452d5`
- `USER32!DeleteMenu` at `0x18004524c`
- `USER32!DeleteMenu` at `0x18004529d`
- `USER32!DeleteMenu` at `0x1800452d5`
- `USER32!SetMenuDefaultItem` at `0x180045398`
- `USER32!SetMenuDefaultItem` at `0x180045398`

## pseudocode

```c
void __fastcall CSyncHandlerFolder::InitContextMenu(
        CSyncHandlerFolder *this,
        struct IDataObject *a2,
        struct _QCMINFO *a3,
        int a4,
        char a5)
{
  BOOL v5; // ebx
  bool v10; // r15
  CSyncFolderBase *v11; // rcx
  __int16 v12; // kr00_2
  CSyncFolderBase *v13; // rcx
  int v14; // eax
  unsigned int v15; // r12d
  unsigned int v16; // r13d
  UINT v17; // esi
  const struct _ITEMID_CHILD *v18; // rbx
  int FolderItemInfoForPidl; // eax
  CSyncFolderBase *v20; // rcx
  HMENU hmenu; // rdx
  CSyncFolderBase *v22; // rcx
  CSyncFolderBase *v23; // rcx
  CSyncFolderBase *v24; // rcx
  const void *v25; // rcx
  CSyncFolderBase *v26; // rcx
  CSyncFolderBase *v27; // rcx
  CSyncFolderBase *v28; // rcx
  CSyncFolderBase *v29; // rcx
  CSyncFolderBase *v30; // rcx
  CSyncFolderBase *v31; // rcx
  CSyncFolderBase *v32; // rcx
  char v33; // [rsp+30h] [rbp-D0h]
  bool v34; // [rsp+31h] [rbp-CFh]
  bool v35; // [rsp+34h] [rbp-CCh] BYREF
  CSyncFolderBase *v36; // [rsp+35h] [rbp-CBh] BYREF
  BOOL v37; // [rsp+40h] [rbp-C0h]
  struct _IDA *v38; // [rsp+48h] [rbp-B8h] BYREF
  CSyncFolderBase *v39; // [rsp+50h] [rbp-B0h]
  struct tagSTGMEDIUM v40; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v41[276]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v42[258]; // [rsp+184h] [rbp+84h] BYREF
  unsigned int v43; // [rsp+388h] [rbp+288h]
  int v44; // [rsp+394h] [rbp+294h]
  int v45; // [rsp+398h] [rbp+298h]

  v39 = this;
  v34 = 0;
  v35 = 0;
  v33 = 0;
  v36 = 0;
  LOBYTE(v5) = 0;
  v10 = 0;
  v37 = v5;
  memset(&v40, 0, sizeof(v40));
  v38 = 0;
  v12 = 0;
  if ( (int)SHGetItemArrayFromDataObj(a2, &v40, &v38) < 0 )
  {
    v15 = a4 + 3;
    v16 = a4 + 4;
    v17 = a4 + 14;
  }
  else
  {
    CSyncFolderBase::GetEnableDisableSupport(
      this,
      a2,
      (bool *)&v36 + 5,
      (bool *)&v36 + 4,
      (bool *)&v36 + 7,
      (bool *)&v36 + 6);
    CSyncFolderBase::GetSyncSupport(this, a2, &v35, (bool *)&v36, (bool *)&v36 + 1, (bool *)&v36 + 2);
    v14 = *((_DWORD *)this + 244);
    if ( (v14 & 0x400) != 0 )
    {
      v34 = v35;
      LOBYTE(v13) = (_BYTE)v36;
      v33 = (char)v36;
    }
    else
    {
      v34 = 0;
      v33 = 0;
    }
    if ( (v14 & 0x800) != 0 )
      v12 = *(_WORD *)((char *)&v36 + 1);
    else
      v12 = 0;
    v15 = a4 + 3;
    v16 = a4 + 4;
    v17 = a4 + 14;
    if ( v38->cidl == 1 )
    {
      v18 = (const struct _ITEMID_CHILD *)((char *)v38 + v38[1].cidl);
      memset_0(v41, 0, 0x550u);
      FolderItemInfoForPidl = CSyncFolderBase::GetFolderItemInfoForPidl(v39, v18, (struct SYNCMGR_FOLDERITEMINFO *)v41);
      hmenu = a3->hmenu;
      if ( FolderItemInfoForPidl < 0 )
      {
        CSyncFolderBase::FormatNameIntoMenuItem(v20, hmenu, v15, &String2);
        CSyncFolderBase::FormatNameIntoMenuItem(v26, a3->hmenu, v16, &String2);
        DeleteMenu(a3->hmenu, v17, 0);
        LOBYTE(v5) = v37;
      }
      else
      {
        CSyncFolderBase::FormatNameIntoMenuItem(v20, hmenu, v15, v42);
        CSyncFolderBase::FormatNameIntoMenuItem(v22, a3->hmenu, v16, v42);
        if ( (v43 & 0x1000) != 0 )
        {
          v10 = ~(v43 >> 27) & 1;
          CSyncFolderBase::FormatNameIntoMenuItem(v23, a3->hmenu, v17, v42);
          CSyncFolderBase::SetMenuItemDisposition(v24, 1, v10, a3->hmenu, a4 + 14);
        }
        else
        {
          DeleteMenu(a3->hmenu, v17, 0);
        }
        LOBYTE(v5) = v37;
        if ( v45 )
          LOBYTE(v5) = 1;
        if ( v44 )
          BYTE3(v36) = 1;
      }
    }
    else
    {
      CSyncFolderBase::FormatNameIntoMenuItem(v13, a3->hmenu, v15, &String2);
      CSyncFolderBase::FormatNameIntoMenuItem(v27, a3->hmenu, v16, &String2);
      DeleteMenu(a3->hmenu, v17, 0);
    }
    ReleaseStgMediumHGLOBAL(v25, &v40);
  }
  CSyncFolderBase::SetMenuItemDisposition(v11, v34, v33, a3->hmenu, v15);
  CSyncFolderBase::SetMenuItemDisposition(v28, v12, SHIBYTE(v12), a3->hmenu, v16);
  CSyncFolderBase::SetMenuItemDisposition(v29, 1, v5, a3->hmenu, a4 + 5);
  CSyncFolderBase::SetMenuItemDisposition(v30, 1, SBYTE3(v36), a3->hmenu, a4 + 6);
  CSyncFolderBase::SetMenuItemDisposition(v31, SBYTE5(v36), SBYTE4(v36), a3->hmenu, a4 + 7);
  CSyncFolderBase::SetMenuItemDisposition(v32, SHIBYTE(v36), SBYTE6(v36), a3->hmenu, a4 + 8);
  if ( (a5 & 0x20) == 0 && v10 )
    SetMenuDefaultItem(a3->hmenu, v17, 0);
}

```

## disassembly

```asm
0x180045040  push    rbp
0x180045042  push    rbx
0x180045043  push    rsi
0x180045044  push    rdi
0x180045045  push    r12
0x180045047  push    r13
0x180045049  push    r14
0x18004504b  push    r15
0x18004504d  lea     rbp, [rsp-4D8h]
0x180045055  sub     rsp, 5D8h
0x18004505c  mov     rax, cs:__security_cookie
0x180045063  xor     rax, rsp
0x180045066  mov     [rbp+510h+var_50], rax
0x18004506d  xor     r13d, r13d
0x180045070  mov     [rsp+610h+var_5C0], rcx
0x180045075  mov     al, r13b
0x180045078  mov     byte ptr [rsp+610h+var_5DB+5], r13b
0x18004507d  mov     r12, rdx
0x180045080  mov     [rsp+610h+var_5DF], al
0x180045084  mov     [rsp+610h+var_5DC], al
0x180045088  lea     rdx, [rsp+610h+var_5B8]; struct tagSTGMEDIUM *
0x18004508d  mov     [rsp+610h+var_5E0], al
0x180045091  mov     rdi, r8
0x180045094  mov     byte ptr [rsp+610h+var_5DB], al
0x180045098  lea     r8, [rsp+610h+var_5C8]; struct _IDA **
0x18004509d  mov     [rsp+610h+var_5DD], al
0x1800450a1  mov     rsi, rcx
0x1800450a4  mov     byte ptr [rsp+610h+var_5DB+1], al
0x1800450a8  xorps   xmm0, xmm0
0x1800450ab  mov     [rsp+610h+var_5DE], al
0x1800450af  mov     bl, r13b
0x1800450b2  mov     byte ptr [rsp+610h+var_5DB+2], al
0x1800450b6  mov     rcx, r12; struct IDataObject *
0x1800450b9  xor     eax, eax
0x1800450bb  mov     byte ptr [rsp+610h+var_5DB+4], r13b
0x1800450c0  mov     [rsp+610h+var_5B8.pUnkForRelease], rax
0x1800450c5  mov     r14d, r9d
0x1800450c8  mov     byte ptr [rsp+610h+var_5DB+7], r13b
0x1800450cd  mov     r15b, r13b
0x1800450d0  mov     byte ptr [rsp+610h+var_5DB+6], r13b
0x1800450d5  mov     [rsp+610h+var_5D0], ebx
0x1800450d9  mov     byte ptr [rsp+610h+var_5DB+3], r13b
0x1800450de  movups  xmmword ptr [rsp+610h+var_5B8.tymed], xmm0
0x1800450e3  mov     [rsp+610h+var_5C8], r13
0x1800450e8  call    ?SHGetItemArrayFromDataObj@@YAJPEAUIDataObject@@PEAUtagSTGMEDIUM@@PEAPEAU_IDA@@@Z; SHGetItemArrayFromDataObj(IDataObject *,tagSTGMEDIUM *,_IDA * *)
0x1800450ed  test    eax, eax
0x1800450ef  js      loc_1800452E7
0x1800450f5  lea     rax, [rsp+610h+var_5DB+6]
0x1800450fa  mov     rdx, r12; struct IDataObject *
0x1800450fd  mov     [rsp+610h+var_5E8], rax; bool *
0x180045102  lea     r9, [rsp+610h+var_5DB+4]; bool *
0x180045107  lea     rax, [rsp+610h+var_5DB+7]
0x18004510c  mov     rcx, rsi; this
0x18004510f  lea     r8, [rsp+610h+var_5DB+5]; bool *
0x180045114  mov     [rsp+610h+var_5F0], rax; bool *
0x180045119  call    ?GetEnableDisableSupport@CSyncFolderBase@@IEAAXPEAUIDataObject@@PEA_N111@Z; CSyncFolderBase::GetEnableDisableSupport(IDataObject *,bool *,bool *,bool *,bool *)
0x18004511e  lea     rax, [rsp+610h+var_5DB+2]
0x180045123  mov     rdx, r12; struct IDataObject *
0x180045126  mov     [rsp+610h+var_5E8], rax; bool *
0x18004512b  lea     r9, [rsp+610h+var_5DB]; bool *
0x180045130  lea     rax, [rsp+610h+var_5DB+1]
0x180045135  mov     rcx, rsi; this
0x180045138  lea     r8, [rsp+610h+var_5DC]; bool *
0x18004513d  mov     [rsp+610h+var_5F0], rax; bool *
0x180045142  call    ?GetSyncSupport@CSyncFolderBase@@IEAAXPEAUIDataObject@@PEA_N111@Z; CSyncFolderBase::GetSyncSupport(IDataObject *,bool *,bool *,bool *,bool *)
0x180045147  mov     eax, [rsi+3D0h]
0x18004514d  bt      eax, 0Ah
0x180045151  jb      short loc_18004515F
0x180045153  mov     [rsp+610h+var_5DF], r13b
0x180045158  mov     [rsp+610h+var_5E0], r13b
0x18004515d  jmp     short loc_18004516F
0x18004515f  mov     cl, [rsp+610h+var_5DC]
0x180045163  mov     [rsp+610h+var_5DF], cl
0x180045167  mov     cl, byte ptr [rsp+610h+var_5DB]; this
0x18004516b  mov     [rsp+610h+var_5E0], cl
0x18004516f  bt      eax, 0Bh
0x180045173  jb      short loc_180045181
0x180045175  mov     [rsp+610h+var_5DD], r13b
0x18004517a  mov     [rsp+610h+var_5DE], r13b
0x18004517f  jmp     short loc_180045191
0x180045181  mov     al, byte ptr [rsp+610h+var_5DB+1]
0x180045185  mov     [rsp+610h+var_5DD], al
0x180045189  mov     al, byte ptr [rsp+610h+var_5DB+2]
0x18004518d  mov     [rsp+610h+var_5DE], al
0x180045191  mov     rdx, [rsp+610h+var_5C8]
0x180045196  lea     r12d, [r14+3]
0x18004519a  lea     r13d, [r14+4]
0x18004519e  lea     esi, [r14+0Eh]
0x1800451a2  cmp     dword ptr [rdx], 1
0x1800451a5  jnz     loc_1800452A9
0x1800451ab  mov     ebx, [rdx+8]
0x1800451ae  lea     rcx, [rsp+610h+var_5A0]; void *
0x1800451b3  add     rbx, rdx
0x1800451b6  mov     r8d, 550h; Size
0x1800451bc  xor     edx, edx; Val
0x1800451be  call    memset_0
0x1800451c3  mov     rcx, [rsp+610h+var_5C0]; this
0x1800451c8  lea     r8, [rsp+610h+var_5A0]; struct SYNCMGR_FOLDERITEMINFO *
0x1800451cd  mov     rdx, rbx; struct _ITEMID_CHILD *
0x1800451d0  call    ?GetFolderItemInfoForPidl@CSyncFolderBase@@IEAAJPEFBU_ITEMID_CHILD@@PEAUSYNCMGR_FOLDERITEMINFO@@@Z; CSyncFolderBase::GetFolderItemInfoForPidl(_ITEMID_CHILD const *,SYNCMGR_FOLDERITEMINFO *)
0x1800451d5  mov     rdx, [rdi]; HMENU
0x1800451d8  mov     r8d, r12d; unsigned int
0x1800451db  test    eax, eax
0x1800451dd  js      loc_180045277
0x1800451e3  lea     r9, [rbp+510h+var_48C]; unsigned __int16 *
0x1800451ea  call    ?FormatNameIntoMenuItem@CSyncFolderBase@@IEBAJPEAUHMENU__@@IPEBG@Z; CSyncFolderBase::FormatNameIntoMenuItem(HMENU__ *,uint,ushort const *)
0x1800451ef  mov     rdx, [rdi]; HMENU
0x1800451f2  lea     r9, [rbp+510h+var_48C]; unsigned __int16 *
0x1800451f9  mov     r8d, r13d; unsigned int
0x1800451fc  call    ?FormatNameIntoMenuItem@CSyncFolderBase@@IEBAJPEAUHMENU__@@IPEBG@Z; CSyncFolderBase::FormatNameIntoMenuItem(HMENU__ *,uint,ushort const *)
0x180045201  test    [rbp+510h+var_288], 1000h
0x18004520b  jz      short loc_180045244
0x18004520d  mov     r15d, [rbp+510h+var_288]
0x180045214  lea     r9, [rbp+510h+var_48C]; unsigned __int16 *
0x18004521b  mov     rdx, [rdi]; HMENU
0x18004521e  mov     r8d, esi; unsigned int
0x180045221  shr     r15d, 1Bh
0x180045225  not     r15b
0x180045228  and     r15b, 1
0x18004522c  call    ?FormatNameIntoMenuItem@CSyncFolderBase@@IEBAJPEAUHMENU__@@IPEBG@Z; CSyncFolderBase::FormatNameIntoMenuItem(HMENU__ *,uint,ushort const *)
0x180045231  mov     r9, [rdi]; HMENU
0x180045234  mov     r8b, r15b; bool
0x180045237  mov     dl, 1; bool
0x180045239  mov     dword ptr [rsp+610h+var_5F0], esi; unsigned int
0x18004523d  call    ?SetMenuItemDisposition@CSyncFolderBase@@IEBAX_N0PEAUHMENU__@@I@Z; CSyncFolderBase::SetMenuItemDisposition(bool,bool,HMENU__ *,uint)
0x180045242  jmp     short loc_180045252
0x180045244  mov     rcx, [rdi]; hMenu
0x180045247  xor     r8d, r8d; uFlags
0x18004524a  mov     edx, esi; uPosition
0x18004524c  call    cs:__imp_DeleteMenu
0x180045252  cmp     [rbp+510h+var_278], 0
0x180045259  mov     eax, 1
0x18004525e  mov     ebx, [rsp+610h+var_5D0]
0x180045262  movzx   ebx, bl
0x180045265  cmova   ebx, eax
0x180045268  cmp     [rbp+510h+var_27C], 0
0x18004526f  jbe     short loc_1800452DB
0x180045271  mov     byte ptr [rsp+610h+var_5DB+3], al
0x180045275  jmp     short loc_1800452DB
0x180045277  lea     r9, String2; unsigned __int16 *
0x18004527e  call    ?FormatNameIntoMenuItem@CSyncFolderBase@@IEBAJPEAUHMENU__@@IPEBG@Z; CSyncFolderBase::FormatNameIntoMenuItem(HMENU__ *,uint,ushort const *)
0x180045283  mov     rdx, [rdi]; HMENU
0x180045286  lea     r9, String2; unsigned __int16 *
0x18004528d  mov     r8d, r13d; unsigned int
0x180045290  call    ?FormatNameIntoMenuItem@CSyncFolderBase@@IEBAJPEAUHMENU__@@IPEBG@Z; CSyncFolderBase::FormatNameIntoMenuItem(HMENU__ *,uint,ushort const *)
0x180045295  mov     rcx, [rdi]; hMenu
0x180045298  xor     r8d, r8d; uFlags
0x18004529b  mov     edx, esi; uPosition
0x18004529d  call    cs:__imp_DeleteMenu
0x1800452a3  mov     ebx, [rsp+610h+var_5D0]
0x1800452a7  jmp     short loc_1800452DB
0x1800452a9  mov     rdx, [rdi]; HMENU
0x1800452ac  lea     r9, String2; unsigned __int16 *
0x1800452b3  mov     r8d, r12d; unsigned int
0x1800452b6  call    ?FormatNameIntoMenuItem@CSyncFolderBase@@IEBAJPEAUHMENU__@@IPEBG@Z; CSyncFolderBase::FormatNameIntoMenuItem(HMENU__ *,uint,ushort const *)
0x1800452bb  mov     rdx, [rdi]; HMENU
0x1800452be  lea     r9, String2; unsigned __int16 *
0x1800452c5  mov     r8d, r13d; unsigned int
0x1800452c8  call    ?FormatNameIntoMenuItem@CSyncFolderBase@@IEBAJPEAUHMENU__@@IPEBG@Z; CSyncFolderBase::FormatNameIntoMenuItem(HMENU__ *,uint,ushort const *)
0x1800452cd  mov     rcx, [rdi]; hMenu
0x1800452d0  xor     r8d, r8d; uFlags
0x1800452d3  mov     edx, esi; uPosition
0x1800452d5  call    cs:__imp_DeleteMenu
0x1800452db  lea     rdx, [rsp+610h+var_5B8]; struct tagSTGMEDIUM *
0x1800452e0  call    ?ReleaseStgMediumHGLOBAL@@YAXPEBXPEAUtagSTGMEDIUM@@@Z; ReleaseStgMediumHGLOBAL(void const *,tagSTGMEDIUM *)
0x1800452e5  jmp     short loc_1800452F3
0x1800452e7  lea     r12d, [r14+3]
0x1800452eb  lea     r13d, [r14+4]
0x1800452ef  lea     esi, [r14+0Eh]
0x1800452f3  mov     r9, [rdi]; HMENU
0x1800452f6  mov     r8b, [rsp+610h+var_5E0]; bool
0x1800452fb  mov     dl, [rsp+610h+var_5DF]; bool
0x1800452ff  mov     dword ptr [rsp+610h+var_5F0], r12d; unsigned int
0x180045304  call    ?SetMenuItemDisposition@CSyncFolderBase@@IEBAX_N0PEAUHMENU__@@I@Z; CSyncFolderBase::SetMenuItemDisposition(bool,bool,HMENU__ *,uint)
0x180045309  mov     r9, [rdi]; HMENU
0x18004530c  mov     r8b, [rsp+610h+var_5DE]; bool
0x180045311  mov     dl, [rsp+610h+var_5DD]; bool
0x180045315  mov     dword ptr [rsp+610h+var_5F0], r13d; unsigned int
0x18004531a  call    ?SetMenuItemDisposition@CSyncFolderBase@@IEBAX_N0PEAUHMENU__@@I@Z; CSyncFolderBase::SetMenuItemDisposition(bool,bool,HMENU__ *,uint)
0x18004531f  mov     r9, [rdi]; HMENU
0x180045322  lea     eax, [r14+5]
0x180045326  mov     r8b, bl; bool
0x180045329  mov     dword ptr [rsp+610h+var_5F0], eax; unsigned int
0x18004532d  mov     ebx, 1
0x180045332  mov     dl, bl; bool
0x180045334  call    ?SetMenuItemDisposition@CSyncFolderBase@@IEBAX_N0PEAUHMENU__@@I@Z; CSyncFolderBase::SetMenuItemDisposition(bool,bool,HMENU__ *,uint)
0x180045339  mov     r9, [rdi]; HMENU
0x18004533c  lea     eax, [r14+6]
0x180045340  mov     r8b, byte ptr [rsp+610h+var_5DB+3]; bool
0x180045345  mov     dl, bl; bool
0x180045347  mov     dword ptr [rsp+610h+var_5F0], eax; unsigned int
0x18004534b  call    ?SetMenuItemDisposition@CSyncFolderBase@@IEBAX_N0PEAUHMENU__@@I@Z; CSyncFolderBase::SetMenuItemDisposition(bool,bool,HMENU__ *,uint)
0x180045350  mov     r9, [rdi]; HMENU
0x180045353  lea     eax, [r14+7]
0x180045357  mov     r8b, byte ptr [rsp+610h+var_5DB+4]; bool
0x18004535c  mov     dl, byte ptr [rsp+610h+var_5DB+5]; bool
0x180045360  mov     dword ptr [rsp+610h+var_5F0], eax; unsigned int
0x180045364  call    ?SetMenuItemDisposition@CSyncFolderBase@@IEBAX_N0PEAUHMENU__@@I@Z; CSyncFolderBase::SetMenuItemDisposition(bool,bool,HMENU__ *,uint)
0x180045369  mov     r9, [rdi]; HMENU
0x18004536c  lea     eax, [r14+8]
0x180045370  mov     r8b, byte ptr [rsp+610h+var_5DB+6]; bool
0x180045375  mov     dl, byte ptr [rsp+610h+var_5DB+7]; bool
0x180045379  mov     dword ptr [rsp+610h+var_5F0], eax; unsigned int
0x18004537d  call    ?SetMenuItemDisposition@CSyncFolderBase@@IEBAX_N0PEAUHMENU__@@I@Z; CSyncFolderBase::SetMenuItemDisposition(bool,bool,HMENU__ *,uint)
0x180045382  test    byte ptr [rbp+510h+arg_20], 20h
0x180045389  jnz     short loc_18004539E
0x18004538b  cmp     r15b, bl
0x18004538e  jnz     short loc_18004539E
0x180045390  mov     rcx, [rdi]; hMenu
0x180045393  xor     r8d, r8d; fByPos
0x180045396  mov     edx, esi; uItem
0x180045398  call    cs:__imp_SetMenuDefaultItem
0x18004539e  mov     rcx, [rbp+510h+var_50]
0x1800453a5  xor     rcx, rsp; StackCookie
0x1800453a8  call    __security_check_cookie
0x1800453ad  add     rsp, 5D8h
0x1800453b4  pop     r15
0x1800453b6  pop     r14
0x1800453b8  pop     r13
0x1800453ba  pop     r12
0x1800453bc  pop     rdi
0x1800453bd  pop     rsi
0x1800453be  pop     rbx
0x1800453bf  pop     rbp
0x1800453c0  retn
```
