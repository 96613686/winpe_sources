# CDsmDeviceTask::_RemovePairedDevnode(ushort const *,ushort const *)

- ea: `0x1800363d8`
- end: `0x180036677`
- name: `?_RemovePairedDevnode@CDsmDeviceTask@@AEAAJPEBG0@Z`
- size: `671`
- prototype: `int(CDsmDeviceTask *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, installer_update`

## callers

- `0x180036680`

## callees

- `0x1800112a4`
- `0x180015404`
- `0x180015494`
- `0x18001af70`
- `0x180021790`
- `0x18002541c`
- `0x180027ba8`
- `0x18002b980`
- `0x18003605c`
- `0x18003607c`
- `0x180036240`
- `0x1800363d8`

## import_xrefs

- `deviceassociation!DafCreateAssociationContext` at `0x18003651e`
- `deviceassociation!DafCreateAssociationContext` at `0x18003656d`
- `deviceassociation!DafCreateAssociationContext` at `0x18003651e`
- `deviceassociation!DafCreateAssociationContext` at `0x18003656d`
- `deviceassociation!DafCloseAssociationContext` at `0x1800364f5`
- `deviceassociation!DafCloseAssociationContext` at `0x180036546`
- `deviceassociation!DafCloseAssociationContext` at `0x1800364f5`
- `deviceassociation!DafCloseAssociationContext` at `0x180036546`
- `deviceassociation!DafStartRemoveAssociation` at `0x1800365cc`
- `deviceassociation!DafStartRemoveAssociation` at `0x1800365cc`

## string_xrefs

- `0x180036582`: `onecoreuap\base\devices\setup\dsm\service\devicetask.cpp`

## pseudocode

```c
__int64 __fastcall CDsmDeviceTask::_RemovePairedDevnode(
        CDsmDeviceTask *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4)
{
  PVOID *v6; // rcx
  __int64 v7; // rcx
  int AssociationContext; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  int v12[2]; // [rsp+30h] [rbp-50h] BYREF
  int v13; // [rsp+38h] [rbp-48h] BYREF
  unsigned int v14; // [rsp+3Ch] [rbp-44h]
  unsigned __int16 *v15; // [rsp+40h] [rbp-40h] BYREF
  __int128 v16; // [rsp+50h] [rbp-30h] BYREF
  int v17; // [rsp+60h] [rbp-20h]
  int v18; // [rsp+64h] [rbp-1Ch]
  int v19; // [rsp+68h] [rbp-18h]
  unsigned __int16 *v20; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_33771ca157e2352e8c67aa8b8aaebcd9_Traceguids, a2);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 )
      WPP_SF_S(v6[2], 19, &WPP_33771ca157e2352e8c67aa8b8aaebcd9_Traceguids, a3);
  }
  *(_QWORD *)v12 = 0;
  v15 = 0;
  if ( (int)CDsmDeviceTask::_GetPairedDevicePerUserSid((CDsmDeviceTask *)v6, a2, &v15, a4) < 0 )
  {
    *(_QWORD *)v12 = 0;
    AssociationContext = DafCreateAssociationContext(a3, 0, 0, 0);
    v9 = AssociationContext;
    if ( AssociationContext < 0 )
    {
      v10 = 310;
      goto LABEL_17;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_33771ca157e2352e8c67aa8b8aaebcd9_Traceguids, v15);
    v7 = -1;
    v17 = 8;
    v16 = DEVPKEY_DasParam_PerUserSid;
    v18 = 18;
    do
      ++v7;
    while ( v15[v7] );
    v19 = 2 * v7 + 2;
    v20 = v15;
    *(_QWORD *)v12 = 0;
    AssociationContext = DafCreateAssociationContext(a3, 0, 1, &v16);
    v9 = AssociationContext;
    if ( AssociationContext < 0 )
    {
      v10 = 301;
LABEL_17:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\devicetask.cpp",
        (const char *)(unsigned int)AssociationContext,
        (int)v12);
      goto LABEL_30;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_33771ca157e2352e8c67aa8b8aaebcd9_Traceguids);
  v13 = 0;
  AssociationContext = DafStartRemoveAssociation(*(_QWORD *)v12, CDsmDeviceTask::_RemoveAssociationCallback, &v13);
  v9 = AssociationContext;
  if ( AssociationContext < 0 )
  {
    v10 = 318;
    goto LABEL_17;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_33771ca157e2352e8c67aa8b8aaebcd9_Traceguids);
  wil::slim_event_t<0>::wait(&v13);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      23,
      (unsigned int)&WPP_33771ca157e2352e8c67aa8b8aaebcd9_Traceguids,
      (_DWORD)a2,
      v14);
  v9 = v14;
LABEL_30:
  wil::details::unique_storage<wil::details::resource_policy<DAF_ASSOCIATION_HANDLE__ *,long (*)(DAF_ASSOCIATION_HANDLE__ *),&long DafCloseAssociationContext(DAF_ASSOCIATION_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,DAF_ASSOCIATION_HANDLE__ *,DAF_ASSOCIATION_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<DAF_ASSOCIATION_HANDLE__ *,long (*)(DAF_ASSOCIATION_HANDLE__ *),&long DafCloseAssociationContext(DAF_ASSOCIATION_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,DAF_ASSOCIATION_HANDLE__ *,DAF_ASSOCIATION_HANDLE__ *,0,std::nullptr_t>>(v12);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v15);
  return v9;
}

```

## disassembly

```asm
0x1800363d8  mov     [rsp-28h+arg_0], rbx
0x1800363dd  mov     [rsp-28h+arg_18], rsi
0x1800363e2  push    rbp
0x1800363e3  push    rdi
0x1800363e4  push    r12
0x1800363e6  push    r13
0x1800363e8  push    r14
0x1800363ea  mov     rbp, rsp
0x1800363ed  sub     rsp, 80h
0x1800363f4  mov     rax, cs:__security_cookie
0x1800363fb  xor     rax, rsp
0x1800363fe  mov     [rbp+var_8], rax
0x180036402  mov     rdi, r8
0x180036405  mov     rsi, rdx
0x180036408  mov     rcx, cs:WPP_GLOBAL_Control
0x18003640f  lea     r12, WPP_GLOBAL_Control
0x180036416  lea     r13, WPP_33771ca157e2352e8c67aa8b8aaebcd9_Traceguids
0x18003641d  mov     ebx, 12h
0x180036422  cmp     rcx, r12
0x180036425  jz      short loc_180036464
0x180036427  test    byte ptr [rcx+1Ch], 1
0x18003642b  jz      short loc_180036445
0x18003642d  mov     rcx, [rcx+10h]
0x180036431  mov     edx, ebx
0x180036433  mov     r9, rsi
0x180036436  mov     r8, r13
0x180036439  call    WPP_SF_S
0x18003643e  mov     rcx, cs:WPP_GLOBAL_Control
0x180036445  cmp     rcx, r12
0x180036448  jz      short loc_180036464
0x18003644a  test    byte ptr [rcx+1Ch], 1
0x18003644e  jz      short loc_180036464
0x180036450  mov     rcx, [rcx+10h]
0x180036454  mov     edx, 13h
0x180036459  mov     r9, rdi
0x18003645c  mov     r8, r13
0x18003645f  call    WPP_SF_S
0x180036464  xor     r14d, r14d
0x180036467  lea     r8, [rbp+var_40]; unsigned __int16 **
0x18003646b  mov     rdx, rsi; unsigned __int16 *
0x18003646e  mov     qword ptr [rbp+var_50], r14
0x180036472  mov     [rbp+var_40], r14
0x180036476  call    ?_GetPairedDevicePerUserSid@CDsmDeviceTask@@AEAAJPEBGPEAPEAG@Z; CDsmDeviceTask::_GetPairedDevicePerUserSid(ushort const *,ushort * *)
0x18003647b  test    eax, eax
0x18003647d  js      loc_180036531
0x180036483  mov     rcx, cs:WPP_GLOBAL_Control
0x18003648a  cmp     rcx, r12
0x18003648d  jz      short loc_1800364A9
0x18003648f  test    byte ptr [rcx+1Ch], 1
0x180036493  jz      short loc_1800364A9
0x180036495  mov     r9, [rbp+var_40]
0x180036499  lea     edx, [r14+14h]
0x18003649d  mov     rcx, [rcx+10h]
0x1800364a1  mov     r8, r13
0x1800364a4  call    WPP_SF_S
0x1800364a9  mov     eax, cs:dword_18004C7A8
0x1800364af  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800364b3  movups  xmm0, cs:DEVPKEY_DasParam_PerUserSid
0x1800364ba  mov     [rbp+var_20], eax
0x1800364bd  mov     rax, [rbp+var_40]
0x1800364c1  movups  [rbp+var_30], xmm0
0x1800364c5  mov     [rbp+var_1C], ebx
0x1800364c8  inc     rcx
0x1800364cb  cmp     [rax+rcx*2], r14w
0x1800364d0  jnz     short loc_1800364C8
0x1800364d2  mov     rbx, qword ptr [rbp+var_50]
0x1800364d6  lea     ecx, ds:2[rcx*2]
0x1800364dd  mov     [rbp+var_18], ecx
0x1800364e0  mov     [rbp+var_10], rax
0x1800364e4  test    rbx, rbx
0x1800364e7  jz      short loc_180036504
0x1800364e9  lea     rcx, [rbp+var_38]; this
0x1800364ed  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800364f2  mov     rcx, rbx
0x1800364f5  call    cs:__imp_DafCloseAssociationContext
0x1800364fb  lea     rcx, [rbp+var_38]; this
0x1800364ff  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180036504  xor     edx, edx
0x180036506  mov     qword ptr [rbp+var_50], r14
0x18003650a  lea     rax, [rbp+var_50]
0x18003650e  mov     rcx, rdi
0x180036511  lea     r9, [rbp+var_30]
0x180036515  mov     qword ptr [rsp+80h+var_60], rax
0x18003651a  lea     r8d, [rdx+1]
0x18003651e  call    cs:__imp_DafCreateAssociationContext
0x180036524  mov     ebx, eax
0x180036526  test    eax, eax
0x180036528  jns     short loc_180036596
0x18003652a  mov     edx, 12Dh
0x18003652f  jmp     short loc_18003657E
0x180036531  mov     rbx, qword ptr [rbp+var_50]
0x180036535  test    rbx, rbx
0x180036538  jz      short loc_180036555
0x18003653a  lea     rcx, [rbp+var_38]; this
0x18003653e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180036543  mov     rcx, rbx
0x180036546  call    cs:__imp_DafCloseAssociationContext
0x18003654c  lea     rcx, [rbp+var_38]; this
0x180036550  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180036555  lea     rax, [rbp+var_50]
0x180036559  mov     qword ptr [rbp+var_50], r14
0x18003655d  xor     r9d, r9d
0x180036560  mov     qword ptr [rsp+80h+var_60], rax; int
0x180036565  xor     r8d, r8d
0x180036568  xor     edx, edx
0x18003656a  mov     rcx, rdi
0x18003656d  call    cs:__imp_DafCreateAssociationContext
0x180036573  mov     ebx, eax
0x180036575  test    eax, eax
0x180036577  jns     short loc_180036596
0x180036579  mov     edx, 136h; void *
0x18003657e  mov     rcx, [rbp+28h]; this
0x180036582  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x180036589  mov     r9d, eax; char *
0x18003658c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036591  jmp     loc_18003663B
0x180036596  mov     rcx, cs:WPP_GLOBAL_Control
0x18003659d  cmp     rcx, r12
0x1800365a0  jz      short loc_1800365B9
0x1800365a2  test    byte ptr [rcx+1Ch], 1
0x1800365a6  jz      short loc_1800365B9
0x1800365a8  mov     rcx, [rcx+10h]
0x1800365ac  mov     edx, 15h
0x1800365b1  mov     r8, r13
0x1800365b4  call    WPP_SF_
0x1800365b9  mov     rcx, qword ptr [rbp+var_50]
0x1800365bd  lea     r8, [rbp+var_48]
0x1800365c1  lea     rdx, ?_RemoveAssociationCallback@CDsmDeviceTask@@CAXPEAXJ@Z; CDsmDeviceTask::_RemoveAssociationCallback(void *,long)
0x1800365c8  mov     [rbp+var_48], r14d
0x1800365cc  call    cs:__imp_DafStartRemoveAssociation
0x1800365d2  mov     ebx, eax
0x1800365d4  test    eax, eax
0x1800365d6  jns     short loc_1800365DF
0x1800365d8  mov     edx, 13Eh
0x1800365dd  jmp     short loc_18003657E
0x1800365df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800365e6  cmp     rcx, r12
0x1800365e9  jz      short loc_180036602
0x1800365eb  test    byte ptr [rcx+1Ch], 1
0x1800365ef  jz      short loc_180036602
0x1800365f1  mov     rcx, [rcx+10h]
0x1800365f5  mov     edx, 16h
0x1800365fa  mov     r8, r13
0x1800365fd  call    WPP_SF_
0x180036602  lea     rcx, [rbp+var_48]
0x180036606  call    ?wait@?$slim_event_t@$0A@@wil@@QEAA_NXZ; wil::slim_event_t<0>::wait(void)
0x18003660b  mov     rcx, cs:WPP_GLOBAL_Control
0x180036612  cmp     rcx, r12
0x180036615  jz      short loc_180036638
0x180036617  test    byte ptr [rcx+1Ch], 1
0x18003661b  jz      short loc_180036638
0x18003661d  mov     eax, [rbp+var_44]
0x180036620  mov     edx, 17h
0x180036625  mov     rcx, [rcx+10h]
0x180036629  mov     r9, rsi
0x18003662c  mov     r8, r13
0x18003662f  mov     [rsp+80h+var_60], eax
0x180036633  call    WPP_SF_Sd
0x180036638  mov     ebx, [rbp+var_44]
0x18003663b  lea     rcx, [rbp+var_50]
0x18003663f  call    ??1?$unique_storage@U?$resource_policy@PEAUDAF_ASSOCIATION_HANDLE__@@P6AJPEAU1@@Z$1?DafCloseAssociationContext@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<DAF_ASSOCIATION_HANDLE__ *,long (*)(DAF_ASSOCIATION_HANDLE__ *),&DafCloseAssociationContext(DAF_ASSOCIATION_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,DAF_ASSOCIATION_HANDLE__ *,DAF_ASSOCIATION_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<DAF_ASSOCIATION_HANDLE__ *,long (*)(DAF_ASSOCIATION_HANDLE__ *),&DafCloseAssociationContext(DAF_ASSOCIATION_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,DAF_ASSOCIATION_HANDLE__ *,DAF_ASSOCIATION_HANDLE__ *,0,std::nullptr_t>>(void)
0x180036644  lea     rcx, [rbp+var_40]
0x180036648  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003664d  mov     eax, ebx
0x18003664f  mov     rcx, [rbp+var_8]
0x180036653  xor     rcx, rsp; StackCookie
0x180036656  call    __security_check_cookie
0x18003665b  lea     r11, [rsp+80h+var_s0]
0x180036663  mov     rbx, [r11+30h]
0x180036667  mov     rsi, [r11+48h]
0x18003666b  mov     rsp, r11
0x18003666e  pop     r14
0x180036670  pop     r13
0x180036672  pop     r12
0x180036674  pop     rdi
0x180036675  pop     rbp
0x180036676  retn
```
