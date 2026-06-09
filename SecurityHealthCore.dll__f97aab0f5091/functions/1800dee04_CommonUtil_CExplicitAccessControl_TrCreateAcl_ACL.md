# CommonUtil::CExplicitAccessControl::TrCreateAcl(_ACL *)

- ea: `0x1800dee04`
- end: `0x1800def82`
- name: `?TrCreateAcl@CExplicitAccessControl@CommonUtil@@QEAA?AV?$AutoRef@UIWinSecurityAcl@CommonUtil@@@2@PEAU_ACL@@@Z`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800deba0`

## callees

- `0x180004b64`
- `0x18000d7fc`
- `0x180011ad0`
- `0x18001739c`
- `0x1800dbcdc`
- `0x1800dee04`
- `0x1800df2dc`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800def4a`
- `KERNEL32!LocalFree` at `0x1800def69`
- `KERNEL32!LocalFree` at `0x1800def4a`
- `KERNEL32!LocalFree` at `0x1800def69`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800deeb3`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800deeb3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct _ACL **__fastcall CommonUtil::CExplicitAccessControl::TrCreateAcl(__int64 a1, struct _ACL **a2, struct _ACL *a3)
{
  struct _EXPLICIT_ACCESS_W **v4; // rax
  struct _EXPLICIT_ACCESS_W *v5; // rcx
  unsigned int EmptyAcl; // eax
  __int64 v7; // rcx
  _DWORD *v8; // r8
  struct _ACL *v9; // r8
  struct _EXPLICIT_ACCESS_W *v10; // rdx
  signed int v11; // eax
  int v12; // edx
  unsigned int v13; // ebx
  _DWORD *v14; // rbx
  PACL v15; // rsi
  PACL v16; // rcx
  PACL NewAcl; // [rsp+40h] [rbp+8h] BYREF
  _DWORD *v19; // [rsp+58h] [rbp+20h] BYREF

  v4 = (struct _EXPLICIT_ACCESS_W **)(a1 + 24);
  v5 = *(struct _EXPLICIT_ACCESS_W **)(a1 + 32);
  if ( *v4 != v5 || a3 )
  {
    NewAcl = 0;
    v10 = *v4;
    if ( *v4 == v5 )
      v10 = (struct _EXPLICIT_ACCESS_W *)v4;
    v11 = SetEntriesInAclW(-1431655765 * (((char *)v5 - (char *)*v4) >> 4), v10, a3, &NewAcl);
    v13 = v11;
    if ( v11 )
    {
      if ( v11 > 0 )
        v13 = (unsigned __int16)v11 | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_ee4acfd975e835558bdcbd8589408d45_Traceguids, v13);
      CommonUtil::CommonThrowHr((CommonUtil *)v13, v12);
    }
    v14 = operator new(0x18u);
    v19 = v14;
    v14[2] = 0;
    *(_QWORD *)v14 = &CommonUtil::CWinSecurityAclAlloc<CommonUtil::CAutoLocalPtr<_ACL *>>::`vftable';
    *((_QWORD *)v14 + 2) = 0;
    v15 = NewAcl;
    NewAcl = 0;
    v16 = (PACL)*((_QWORD *)v14 + 2);
    if ( v16 != v15 )
    {
      if ( v16 )
        LocalFree(v16);
      *((_QWORD *)v14 + 2) = v15;
    }
    CommonUtil::CRefObjectFor<ShieldProvider::IDropFolderInfo>::AddRef(v14);
    *a2 = (struct _ACL *)v14;
    if ( NewAcl )
      LocalFree(NewAcl);
  }
  else
  {
    v19 = 0;
    EmptyAcl = CommonUtil::UtilCreateEmptyAcl((CommonUtil *)&v19, a2);
    CommonUtil::CCommonThrowHR::operator=(v7, EmptyAcl);
    v8 = operator new(0x18u);
    v8[2] = 0;
    *(_QWORD *)v8 = &CommonUtil::CWinSecurityAclAlloc<CommonUtil::CAutoUniquePtr<_ACL,void>>::`vftable';
    *((_QWORD *)v8 + 2) = 0;
    if ( v19 )
      *((_QWORD *)v8 + 2) = v19;
    CommonUtil::CRefObjectFor<ShieldProvider::IDropFolderInfo>::AddRef(v8);
    *a2 = v9;
  }
  return a2;
}

```

## disassembly

```asm
0x1800dee04  mov     r11, rsp
0x1800dee07  mov     [r11+10h], rbx
0x1800dee0b  mov     [r11+18h], rsi
0x1800dee0f  push    rdi
0x1800dee10  sub     rsp, 30h
0x1800dee14  mov     rdi, rdx
0x1800dee17  lea     rax, [rcx+18h]
0x1800dee1b  mov     rcx, [rax+8]
0x1800dee1f  cmp     [rax], rcx
0x1800dee22  jnz     short loc_1800DEE86
0x1800dee24  test    r8, r8
0x1800dee27  jnz     short loc_1800DEE86
0x1800dee29  mov     [r11+20h], r8
0x1800dee2d  lea     rcx, [r11+20h]; this
0x1800dee31  call    ?UtilCreateEmptyAcl@CommonUtil@@YAJPEAPEAU_ACL@@@Z; CommonUtil::UtilCreateEmptyAcl(_ACL * *)
0x1800dee36  mov     edx, eax
0x1800dee38  call    ??4CCommonThrowHR@CommonUtil@@QEAAXJ@Z; CommonUtil::CCommonThrowHR::operator=(long)
0x1800dee3d  mov     ecx, 18h; Size
0x1800dee42  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800dee47  mov     r8, rax
0x1800dee4a  mov     [rsp+38h+var_10], rax
0x1800dee4f  mov     dword ptr [rax+8], 0
0x1800dee56  lea     rax, ??_7?$CWinSecurityAclAlloc@V?$CAutoUniquePtr@U_ACL@@X@CommonUtil@@@CommonUtil@@6B@; const CommonUtil::CWinSecurityAclAlloc<CommonUtil::CAutoUniquePtr<_ACL,void>>::`vftable'
0x1800dee5d  mov     [r8], rax
0x1800dee60  mov     qword ptr [r8+10h], 0
0x1800dee68  mov     rax, [rsp+38h+arg_18]
0x1800dee6d  test    rax, rax
0x1800dee70  jz      short loc_1800DEE76
0x1800dee72  mov     [r8+10h], rax
0x1800dee76  mov     rcx, r8
0x1800dee79  call    ?AddRef@?$CRefObjectFor@UIDropFolderInfo@ShieldProvider@@@CommonUtil@@UEBAJXZ; CommonUtil::CRefObjectFor<ShieldProvider::IDropFolderInfo>::AddRef(void)
0x1800dee7e  mov     [rdi], r8
0x1800dee81  jmp     loc_1800DEF6F
0x1800dee86  mov     [rsp+38h+NewAcl], 0
0x1800dee8f  mov     rdx, [rax]
0x1800dee92  cmp     rdx, rcx
0x1800dee95  cmovz   rdx, rax; pListOfExplicitEntries
0x1800dee99  sub     rcx, [rax]
0x1800dee9c  sar     rcx, 4
0x1800deea0  mov     rax, 0AAAAAAAAAAAAAAABh
0x1800deeaa  imul    rcx, rax; cCountOfExplicitEntries
0x1800deeae  lea     r9, [rsp+38h+NewAcl]; NewAcl
0x1800deeb3  call    cs:__imp_SetEntriesInAclW
0x1800deeb9  mov     ebx, eax
0x1800deebb  test    eax, eax
0x1800deebd  jz      short loc_1800DEF03
0x1800deebf  jle     short loc_1800DEECA
0x1800deec1  movzx   ebx, ax
0x1800deec4  or      ebx, 80070000h
0x1800deeca  lea     rax, WPP_GLOBAL_Control
0x1800deed1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800deed8  cmp     rcx, rax
0x1800deedb  jz      short loc_1800DEEFB
0x1800deedd  test    byte ptr [rcx+1Ch], 1
0x1800deee1  jz      short loc_1800DEEFB
0x1800deee3  mov     edx, 0Bh
0x1800deee8  mov     r9d, ebx
0x1800deeeb  lea     r8, WPP_ee4acfd975e835558bdcbd8589408d45_Traceguids
0x1800deef2  mov     rcx, [rcx+10h]
0x1800deef6  call    WPP_SF_d
0x1800deefb  mov     ecx, ebx; this
0x1800deefd  call    ?CommonThrowHr@CommonUtil@@YAXJ@Z; CommonUtil::CommonThrowHr(long)
0x1800def03  mov     ecx, 18h; Size
0x1800def08  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800def0d  mov     rbx, rax
0x1800def10  mov     [rsp+38h+arg_18], rax
0x1800def15  mov     dword ptr [rax+8], 0
0x1800def1c  lea     rax, ??_7?$CWinSecurityAclAlloc@U?$CAutoLocalPtr@PEAU_ACL@@@CommonUtil@@@CommonUtil@@6B@; const CommonUtil::CWinSecurityAclAlloc<CommonUtil::CAutoLocalPtr<_ACL *>>::`vftable'
0x1800def23  mov     [rbx], rax
0x1800def26  mov     qword ptr [rbx+10h], 0
0x1800def2e  mov     rsi, [rsp+38h+NewAcl]
0x1800def33  mov     [rsp+38h+NewAcl], 0
0x1800def3c  mov     rcx, [rbx+10h]; hMem
0x1800def40  cmp     rcx, rsi
0x1800def43  jz      short loc_1800DEF54
0x1800def45  test    rcx, rcx
0x1800def48  jz      short loc_1800DEF50
0x1800def4a  call    cs:__imp_LocalFree
0x1800def50  mov     [rbx+10h], rsi
0x1800def54  mov     rcx, rbx
0x1800def57  call    ?AddRef@?$CRefObjectFor@UIDropFolderInfo@ShieldProvider@@@CommonUtil@@UEBAJXZ; CommonUtil::CRefObjectFor<ShieldProvider::IDropFolderInfo>::AddRef(void)
0x1800def5c  mov     [rdi], rbx
0x1800def5f  mov     rcx, [rsp+38h+NewAcl]; hMem
0x1800def64  test    rcx, rcx
0x1800def67  jz      short loc_1800DEF6F
0x1800def69  call    cs:__imp_LocalFree
0x1800def6f  mov     rax, rdi
0x1800def72  mov     rbx, [rsp+38h+arg_8]
0x1800def77  mov     rsi, [rsp+38h+arg_10]
0x1800def7c  add     rsp, 30h
0x1800def80  pop     rdi
0x1800def81  retn
```
