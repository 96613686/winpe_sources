# ChangeApplicationServices::ReportConflictOnItemChange(SharedRefPtr<ItemChangeWrapper> const &)

- ea: `0x180049120`
- end: `0x180049282`
- name: `?ReportConflictOnItemChange@ChangeApplicationServices@@UEAAJAEBV?$SharedRefPtr@VItemChangeWrapper@@@@@Z`
- size: `354`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `service_task`

## callees

- `0x180005e8c`
- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x180046bb0`
- `0x180046f80`
- `0x1800472c0`
- `0x18004882c`
- `0x180049120`
- `0x180074730`
- `0x180094010`

## string_xrefs

- `0x180049155`: `ChangeApplicationServices::ReportConflictOnItemChange`
- `0x18004924d`: `ChangeApplicationServices::ReportConflictOnItemChange`

## pseudocode

```c
__int64 __fastcall ChangeApplicationServices::ReportConflictOnItemChange(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rsi
  __int64 v5; // rdx
  int v6; // ebx
  __int64 (__fastcall ***v7)(_QWORD, GUID *, __int64 *); // rcx
  void *v8; // rax
  __int64 v10; // [rsp+60h] [rbp+18h] BYREF
  __int64 v11; // [rsp+68h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      42,
      WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      "ChangeApplicationServices::ReportConflictOnItemChange");
  }
  v4 = a1 + 168;
  v5 = *a2 + 152LL;
  v10 = 0;
  if ( (unsigned __int8)HashTable<SyncId,SharedRefPtr<ChangeConflictExclusions>,DefaultHashTableContext>::LookupItem(
                          a1 + 168,
                          v5,
                          &v10) )
  {
    v6 = -2147217407;
    if ( *(_DWORD *)(v10 + 20) == 2 )
      v6 = -2147217379;
  }
  else
  {
    v7 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*a2;
    v11 = 0;
    v6 = (**v7)(v7, &IID_ISyncChange, &v11);
    if ( v6 >= 0 )
    {
      v8 = SeAlloc(0x50u);
      if ( v8 )
        v8 = (void *)ItemChangeApplicationStatus::ItemChangeApplicationStatus(v8, 2, &v11);
      v6 = SharedRefPtr<ChangeUnitChangeApplicationStatus>::Attach(&v10, v8);
    }
    SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v11);
    if ( v6 >= 0 )
      v6 = HashTable<SyncId,SharedRefPtr<ItemChangeApplicationStatus>,DefaultHashTableContext>::AddItem(
             v4,
             *a2 + 152LL,
             &v10);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      43,
      (unsigned int)WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      (unsigned int)"ChangeApplicationServices::ReportConflictOnItemChange",
      v6);
  }
  SharedRefPtr<ChangeUnitChangeApplicationStatus>::~SharedRefPtr<ChangeUnitChangeApplicationStatus>(&v10);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180049120  mov     [rsp+arg_0], rbx
0x180049125  push    rbp
0x180049126  push    rsi
0x180049127  push    rdi
0x180049128  sub     rsp, 30h
0x18004912c  mov     rdi, rdx
0x18004912f  mov     rbx, rcx
0x180049132  mov     rcx, cs:WPP_GLOBAL_Control
0x180049139  lea     rbp, WPP_GLOBAL_Control
0x180049140  cmp     rcx, rbp
0x180049143  jz      short loc_18004916D
0x180049145  test    byte ptr [rcx+1Ch], 80h
0x180049149  jz      short loc_18004916D
0x18004914b  cmp     byte ptr [rcx+19h], 5
0x18004914f  jb      short loc_18004916D
0x180049151  mov     rcx, [rcx+10h]
0x180049155  lea     r9, aChangeapplicat_24; "ChangeApplicationServices::ReportConfli"...
0x18004915c  mov     edx, 2Ah ; '*'
0x180049161  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x180049168  call    WPP_SF_s
0x18004916d  mov     rdx, [rdi]
0x180049170  lea     rsi, [rbx+0A8h]
0x180049177  add     rdx, 98h
0x18004917e  mov     [rsp+48h+arg_10], 0
0x180049187  mov     rcx, rsi
0x18004918a  lea     r8, [rsp+48h+arg_10]
0x18004918f  call    ?LookupItem@?$HashTable@VSyncId@@V?$SharedRefPtr@VChangeConflictExclusions@@@@VDefaultHashTableContext@@@@QEBA_NAEBVSyncId@@AEAV?$SharedRefPtr@VChangeConflictExclusions@@@@@Z; HashTable<SyncId,SharedRefPtr<ChangeConflictExclusions>,DefaultHashTableContext>::LookupItem(SyncId const &,SharedRefPtr<ChangeConflictExclusions> &)
0x180049194  test    al, al
0x180049196  jz      short loc_1800491B1
0x180049198  mov     rax, [rsp+48h+arg_10]
0x18004919d  mov     ebx, 80041001h
0x1800491a2  cmp     dword ptr [rax+14h], 2
0x1800491a6  lea     ecx, [rbx+1Ch]
0x1800491a9  cmovz   ebx, ecx
0x1800491ac  jmp     loc_180049231
0x1800491b1  mov     rcx, [rdi]
0x1800491b4  lea     r8, [rsp+48h+arg_18]
0x1800491b9  mov     [rsp+48h+arg_18], 0
0x1800491c2  lea     rdx, IID_ISyncChange
0x1800491c9  mov     rax, [rcx]
0x1800491cc  mov     rax, [rax]
0x1800491cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800491d4  mov     ebx, eax
0x1800491d6  test    eax, eax
0x1800491d8  js      short loc_18004920A
0x1800491da  mov     ecx, 50h ; 'P'; unsigned __int64
0x1800491df  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x1800491e4  test    rax, rax
0x1800491e7  jz      short loc_1800491FB
0x1800491e9  lea     r8, [rsp+48h+arg_18]
0x1800491ee  mov     edx, 2
0x1800491f3  mov     rcx, rax
0x1800491f6  call    ??0ItemChangeApplicationStatus@@QEAA@W4ChangeApplicationReportStatus@@AEBV?$SharedRefPtr@UISyncChange@@@@@Z; ItemChangeApplicationStatus::ItemChangeApplicationStatus(ChangeApplicationReportStatus,SharedRefPtr<ISyncChange> const &)
0x1800491fb  mov     rdx, rax
0x1800491fe  lea     rcx, [rsp+48h+arg_10]
0x180049203  call    ?Attach@?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@QEAAJPEAVChangeUnitChangeApplicationStatus@@H@Z; SharedRefPtr<ChangeUnitChangeApplicationStatus>::Attach(ChangeUnitChangeApplicationStatus *,int)
0x180049208  mov     ebx, eax
0x18004920a  lea     rcx, [rsp+48h+arg_18]
0x18004920f  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x180049214  test    ebx, ebx
0x180049216  js      short loc_180049231
0x180049218  mov     rdx, [rdi]
0x18004921b  lea     r8, [rsp+48h+arg_10]
0x180049220  add     rdx, 98h
0x180049227  mov     rcx, rsi
0x18004922a  call    ?AddItem@?$HashTable@VSyncId@@V?$SharedRefPtr@VItemChangeApplicationStatus@@@@VDefaultHashTableContext@@@@QEAAJAEBVSyncId@@AEBV?$SharedRefPtr@VItemChangeApplicationStatus@@@@@Z; HashTable<SyncId,SharedRefPtr<ItemChangeApplicationStatus>,DefaultHashTableContext>::AddItem(SyncId const &,SharedRefPtr<ItemChangeApplicationStatus> const &)
0x18004922f  mov     ebx, eax
0x180049231  mov     rcx, cs:WPP_GLOBAL_Control
0x180049238  cmp     rcx, rbp
0x18004923b  jz      short loc_180049269
0x18004923d  test    byte ptr [rcx+1Ch], 80h
0x180049241  jz      short loc_180049269
0x180049243  cmp     byte ptr [rcx+19h], 5
0x180049247  jb      short loc_180049269
0x180049249  mov     rcx, [rcx+10h]
0x18004924d  lea     r9, aChangeapplicat_24; "ChangeApplicationServices::ReportConfli"...
0x180049254  mov     edx, 2Bh ; '+'
0x180049259  mov     [rsp+48h+var_28], ebx
0x18004925d  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x180049264  call    WPP_SF_sD
0x180049269  lea     rcx, [rsp+48h+arg_10]
0x18004926e  call    ??1?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@QEAA@XZ; SharedRefPtr<ChangeUnitChangeApplicationStatus>::~SharedRefPtr<ChangeUnitChangeApplicationStatus>(void)
0x180049273  mov     eax, ebx
0x180049275  mov     rbx, [rsp+48h+arg_0]
0x18004927a  add     rsp, 30h
0x18004927e  pop     rdi
0x18004927f  pop     rsi
0x180049280  pop     rbp
0x180049281  retn
```
