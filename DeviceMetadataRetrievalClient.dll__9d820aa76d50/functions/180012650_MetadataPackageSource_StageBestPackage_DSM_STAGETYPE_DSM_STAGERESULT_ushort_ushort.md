# MetadataPackageSource::StageBestPackage(DSM_STAGETYPE,DSM_STAGERESULT *,ushort * *,ushort * *)

- ea: `0x180012650`
- end: `0x1800129cd`
- name: `?StageBestPackage@MetadataPackageSource@@UEAAJW4DSM_STAGETYPE@@PEAW4DSM_STAGERESULT@@PEAPEAG2@Z`
- size: `893`
- prototype: `__int64 __fastcall(__int64, unsigned int, int *, _QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `8`
- tags: `reparse_path, service_task, installer_update`

## callees

- `0x180004dec`
- `0x180004e2c`
- `0x180007380`
- `0x180007b64`
- `0x180007ea0`
- `0x180007f3c`
- `0x180012650`
- `0x180012a04`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180012880`
- `msvcrt!wcscpy_s` at `0x1800128cb`
- `msvcrt!wcscpy_s` at `0x180012880`
- `msvcrt!wcscpy_s` at `0x1800128cb`
- `KERNEL32!GetProcessHeap` at `0x18001291a`
- `KERNEL32!GetProcessHeap` at `0x18001292e`
- `KERNEL32!GetProcessHeap` at `0x18001299e`
- `KERNEL32!GetProcessHeap` at `0x1800129b2`
- `KERNEL32!GetProcessHeap` at `0x18001291a`
- `KERNEL32!GetProcessHeap` at `0x18001292e`
- `KERNEL32!GetProcessHeap` at `0x18001299e`
- `KERNEL32!GetProcessHeap` at `0x1800129b2`
- `KERNEL32!HeapFree` at `0x180012928`
- `KERNEL32!HeapFree` at `0x18001293c`
- `KERNEL32!HeapFree` at `0x1800129ac`
- `KERNEL32!HeapFree` at `0x1800129c0`
- `KERNEL32!HeapFree` at `0x180012928`
- `KERNEL32!HeapFree` at `0x18001293c`
- `KERNEL32!HeapFree` at `0x1800129ac`
- `KERNEL32!HeapFree` at `0x1800129c0`
- `KERNEL32!AcquireSRWLockShared` at `0x1800126d6`
- `KERNEL32!AcquireSRWLockShared` at `0x180012793`
- `KERNEL32!AcquireSRWLockShared` at `0x1800126d6`
- `KERNEL32!AcquireSRWLockShared` at `0x180012793`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800126fc`
- `KERNEL32!ReleaseSRWLockShared` at `0x180012713`
- `KERNEL32!ReleaseSRWLockShared` at `0x180012779`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800127b7`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800126fc`
- `KERNEL32!ReleaseSRWLockShared` at `0x180012713`
- `KERNEL32!ReleaseSRWLockShared` at `0x180012779`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800127b7`
- `ole32!CoTaskMemFree` at `0x18001290c`
- `ole32!CoTaskMemFree` at `0x180012914`
- `ole32!CoTaskMemFree` at `0x18001298a`
- `ole32!CoTaskMemFree` at `0x180012998`
- `ole32!CoTaskMemFree` at `0x18001290c`
- `ole32!CoTaskMemFree` at `0x180012914`
- `ole32!CoTaskMemFree` at `0x18001298a`
- `ole32!CoTaskMemFree` at `0x180012998`
- `ole32!CoTaskMemAlloc` at `0x180012814`
- `ole32!CoTaskMemAlloc` at `0x180012865`
- `ole32!CoTaskMemAlloc` at `0x180012814`
- `ole32!CoTaskMemAlloc` at `0x180012865`

## pseudocode

```c
__int64 __fastcall MetadataPackageSource::StageBestPackage(
        __int64 a1,
        unsigned int a2,
        int *a3,
        _QWORD *a4,
        _QWORD *a5)
{
  __int64 v9; // rbx
  RTL_SRWLOCK *v10; // r14
  int v11; // r12d
  int v12; // eax
  __int64 v13; // r8
  unsigned int v14; // ebx
  _QWORD *v15; // rcx
  unsigned __int16 *ObjectString; // rbp
  unsigned __int16 *ObjectName; // rsi
  __int64 v18; // rax
  rsize_t v19; // r15
  void *v20; // rbx
  unsigned int v21; // eax
  void *v22; // rdi
  __int64 v23; // rax
  rsize_t v24; // r14
  unsigned int v25; // eax
  HANDLE v26; // rax
  HANDLE v27; // rax
  HANDLE ProcessHeap; // rax
  HANDLE v29; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_81786cd8cf3b310d22fd5a7ce0f9edab_Traceguids, a2);
  *a3 = 0;
  *a5 = 0;
  *a4 = 0;
  if ( !*(_BYTE *)(a1 + 89) )
    return 2147549183LL;
  v9 = *((_QWORD *)g_pmrc + 5);
  v10 = (RTL_SRWLOCK *)(v9 + 32);
  AcquireSRWLockShared((PSRWLOCK)(v9 + 32));
  if ( !*(_BYTE *)(a1 + 104) )
    goto LABEL_18;
  if ( IsPackageStaged((struct NDX_OBJREF *)(a1 + 136)) )
  {
    ReleaseSRWLockShared((PSRWLOCK)(v9 + 32));
    v11 = 1;
LABEL_19:
    v15 = WPP_GLOBAL_Control;
    goto LABEL_20;
  }
  if ( !*(_BYTE *)(a1 + 104) )
  {
LABEL_18:
    v11 = 0;
    ReleaseSRWLockShared((PSRWLOCK)(v9 + 32));
    goto LABEL_19;
  }
  ReleaseSRWLockShared((PSRWLOCK)(v9 + 32));
  v12 = InstallSystemCab((struct _INDEX_STRUCT *)v9, (struct NDX_OBJREF *)(a1 + 136));
  v14 = v12;
  if ( v12 > 0 )
    v14 = (unsigned __int16)v12 | 0x80070000;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), (unsigned int)*a3, v13, v14, *a3);
    v15 = WPP_GLOBAL_Control;
  }
  if ( (v14 & 0x80000000) != 0 )
    return v14;
  v11 = 2;
LABEL_20:
  if ( *(_BYTE *)(a1 + 104) )
  {
    AcquireSRWLockShared(v10);
    ObjectString = MemGetObjectString((struct NDX_OBJREF *)(a1 + 136), 2);
    ObjectName = MemGetObjectName((struct NDX_OBJREF *)(a1 + 136));
    ReleaseSRWLockShared(v10);
    if ( !ObjectString || !ObjectName )
      goto LABEL_51;
    v18 = -1;
    do
      ++v18;
    while ( ObjectString[v18] );
    v19 = v18 + 1;
    v20 = 0;
    if ( v18 == -1 )
    {
      v21 = 0;
    }
    else if ( 0xFFFFFFFFFFFFFFFFuLL / v19 < 2 || (v21 = 2 * v19, 2 * v19 > 0x7FFFFFFF) )
    {
      v22 = 0;
      goto LABEL_50;
    }
    v22 = CoTaskMemAlloc(v21);
    if ( !v22 )
    {
LABEL_50:
      CoTaskMemFree(v22);
LABEL_51:
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, ObjectName);
      v29 = GetProcessHeap();
      HeapFree(v29, 0, ObjectString);
      return 2147942414LL;
    }
    v23 = -1;
    do
      ++v23;
    while ( ObjectName[v23] );
    v24 = v23 + 1;
    if ( v23 == -1 )
    {
      v25 = 0;
    }
    else if ( 0xFFFFFFFFFFFFFFFFuLL / v24 < 2 || (v25 = 2 * v24, 2 * v24 > 0x7FFFFFFF) )
    {
LABEL_48:
      CoTaskMemFree(v20);
      goto LABEL_50;
    }
    v20 = CoTaskMemAlloc(v25);
    if ( v20 )
    {
      wcscpy_s((wchar_t *)v22, v19, ObjectString);
      *a5 = v22;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_81786cd8cf3b310d22fd5a7ce0f9edab_Traceguids, v22);
      wcscpy_s((wchar_t *)v20, v24, ObjectName);
      *a4 = v20;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_81786cd8cf3b310d22fd5a7ce0f9edab_Traceguids, v20);
      *a3 = v11;
      CoTaskMemFree(0);
      CoTaskMemFree(0);
      v26 = GetProcessHeap();
      HeapFree(v26, 0, ObjectName);
      v27 = GetProcessHeap();
      HeapFree(v27, 0, ObjectString);
      v15 = WPP_GLOBAL_Control;
      goto LABEL_44;
    }
    goto LABEL_48;
  }
LABEL_44:
  if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 8) != 0 )
    WPP_SF_d(v15[2], 20, &WPP_81786cd8cf3b310d22fd5a7ce0f9edab_Traceguids, (unsigned int)*a3);
  return 0;
}

```

## disassembly

```asm
0x180012650  mov     [rsp+arg_18], r9
0x180012655  push    rbx
0x180012656  push    rbp
0x180012657  push    rsi
0x180012658  push    rdi
0x180012659  push    r12
0x18001265b  push    r13
0x18001265d  push    r14
0x18001265f  push    r15
0x180012661  sub     rsp, 38h
0x180012665  mov     rbx, r9
0x180012668  mov     r13, r8
0x18001266b  mov     r9d, edx
0x18001266e  mov     rdi, rcx
0x180012671  mov     rcx, cs:WPP_GLOBAL_Control
0x180012678  lea     rbp, WPP_GLOBAL_Control
0x18001267f  cmp     rcx, rbp
0x180012682  jz      short loc_18001269F
0x180012684  test    byte ptr [rcx+1Ch], 8
0x180012688  jz      short loc_18001269F
0x18001268a  mov     rcx, [rcx+10h]
0x18001268e  lea     r8, WPP_81786cd8cf3b310d22fd5a7ce0f9edab_Traceguids
0x180012695  mov     edx, 10h
0x18001269a  call    WPP_SF_d
0x18001269f  mov     rax, [rsp+78h+arg_20]
0x1800126a7  xor     r15d, r15d
0x1800126aa  mov     [r13+0], r15d
0x1800126ae  mov     [rax], r15
0x1800126b1  mov     [rbx], r15
0x1800126b4  cmp     [rdi+59h], r15b
0x1800126b8  jnz     short loc_1800126C4
0x1800126ba  mov     eax, 8000FFFFh
0x1800126bf  jmp     loc_180012976
0x1800126c4  mov     rax, cs:?g_pmrc@@3PEAU_MRC_STRUCT@@EA; _MRC_STRUCT * g_pmrc
0x1800126cb  mov     rbx, [rax+28h]
0x1800126cf  lea     r14, [rbx+20h]
0x1800126d3  mov     rcx, r14; SRWLock
0x1800126d6  call    cs:__imp_AcquireSRWLockShared
0x1800126dc  lea     rsi, [rdi+88h]
0x1800126e3  cmp     [rdi+68h], r15b
0x1800126e7  jz      loc_180012773
0x1800126ed  mov     rcx, rsi; struct NDX_OBJREF *
0x1800126f0  call    ?IsPackageStaged@@YA_NAEAUNDX_OBJREF@@@Z; IsPackageStaged(NDX_OBJREF &)
0x1800126f5  test    al, al
0x1800126f7  jz      short loc_18001270A
0x1800126f9  mov     rcx, r14; SRWLock
0x1800126fc  call    cs:__imp_ReleaseSRWLockShared
0x180012702  mov     r12d, 1
0x180012708  jmp     short loc_18001277F
0x18001270a  cmp     [rdi+68h], r15b
0x18001270e  jz      short loc_180012773
0x180012710  mov     rcx, r14; SRWLock
0x180012713  call    cs:__imp_ReleaseSRWLockShared
0x180012719  mov     rdx, rsi; struct NDX_OBJREF *
0x18001271c  mov     rcx, rbx; struct _INDEX_STRUCT *
0x18001271f  call    ?InstallSystemCab@@YAKPEAU_INDEX_STRUCT@@PEAUNDX_OBJREF@@@Z; InstallSystemCab(_INDEX_STRUCT *,NDX_OBJREF *)
0x180012724  mov     ebx, eax
0x180012726  test    eax, eax
0x180012728  jle     short loc_180012733
0x18001272a  movzx   ebx, ax
0x18001272d  or      ebx, 80070000h
0x180012733  mov     rcx, cs:WPP_GLOBAL_Control
0x18001273a  cmp     rcx, rbp
0x18001273d  jz      short loc_180012760
0x18001273f  test    byte ptr [rcx+1Ch], 8
0x180012743  jz      short loc_180012760
0x180012745  mov     edx, [r13+0]
0x180012749  mov     r9d, ebx
0x18001274c  mov     rcx, [rcx+10h]
0x180012750  mov     [rsp+78h+var_58], edx
0x180012754  call    WPP_SF_Dd
0x180012759  mov     rcx, cs:WPP_GLOBAL_Control
0x180012760  test    ebx, ebx
0x180012762  jns     short loc_18001276B
0x180012764  mov     eax, ebx
0x180012766  jmp     loc_180012976
0x18001276b  mov     r12d, 2
0x180012771  jmp     short loc_180012786
0x180012773  mov     rcx, r14; SRWLock
0x180012776  mov     r12d, r15d
0x180012779  call    cs:__imp_ReleaseSRWLockShared
0x18001277f  mov     rcx, cs:WPP_GLOBAL_Control
0x180012786  cmp     [rdi+68h], r15b
0x18001278a  jz      loc_180012950
0x180012790  mov     rcx, r14; SRWLock
0x180012793  call    cs:__imp_AcquireSRWLockShared
0x180012799  mov     edx, 2; int
0x18001279e  mov     rcx, rsi; struct NDX_OBJREF *
0x1800127a1  call    ?MemGetObjectString@@YAPEAGPEAUNDX_OBJREF@@J@Z; MemGetObjectString(NDX_OBJREF *,long)
0x1800127a6  mov     rcx, rsi; struct NDX_OBJREF *
0x1800127a9  mov     rbp, rax
0x1800127ac  call    ?MemGetObjectName@@YAPEAGPEAUNDX_OBJREF@@@Z; MemGetObjectName(NDX_OBJREF *)
0x1800127b1  mov     rcx, r14; SRWLock
0x1800127b4  mov     rsi, rax
0x1800127b7  call    cs:__imp_ReleaseSRWLockShared
0x1800127bd  test    rbp, rbp
0x1800127c0  jz      loc_18001299E
0x1800127c6  test    rsi, rsi
0x1800127c9  jz      loc_18001299E
0x1800127cf  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800127d3  mov     rax, r14
0x1800127d6  inc     rax
0x1800127d9  cmp     [rbp+rax*2+0], r15w
0x1800127df  jnz     short loc_1800127D6
0x1800127e1  lea     r15, [rax+1]
0x1800127e5  xor     ebx, ebx
0x1800127e7  test    r15, r15
0x1800127ea  jnz     short loc_1800127F0
0x1800127ec  mov     eax, ebx
0x1800127ee  jmp     short loc_180012812
0x1800127f0  xor     edx, edx
0x1800127f2  mov     rax, r14
0x1800127f5  div     r15
0x1800127f8  cmp     rax, 2
0x1800127fc  jb      loc_180012992
0x180012802  lea     rax, [r15+r15]
0x180012806  cmp     rax, 7FFFFFFFh
0x18001280c  ja      loc_180012992
0x180012812  mov     ecx, eax; cb
0x180012814  call    cs:__imp_CoTaskMemAlloc
0x18001281a  mov     rdi, rax
0x18001281d  test    rax, rax
0x180012820  jz      loc_180012995
0x180012826  mov     rax, r14
0x180012829  inc     rax
0x18001282c  cmp     [rsi+rax*2], bx
0x180012830  jnz     short loc_180012829
0x180012832  lea     r14, [rax+1]
0x180012836  test    r14, r14
0x180012839  jnz     short loc_180012840
0x18001283b  mov     rax, rbx
0x18001283e  jmp     short loc_180012863
0x180012840  xor     edx, edx
0x180012842  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012846  div     r14
0x180012849  cmp     rax, 2
0x18001284d  jb      loc_180012987
0x180012853  lea     rax, [r14+r14]
0x180012857  cmp     rax, 7FFFFFFFh
0x18001285d  ja      loc_180012987
0x180012863  mov     ecx, eax; cb
0x180012865  call    cs:__imp_CoTaskMemAlloc
0x18001286b  mov     rbx, rax
0x18001286e  test    rax, rax
0x180012871  jz      loc_180012987
0x180012877  mov     r8, rbp; Source
0x18001287a  mov     rdx, r15; SizeInWords
0x18001287d  mov     rcx, rdi; Destination
0x180012880  call    cs:__imp_wcscpy_s
0x180012886  mov     rax, [rsp+78h+arg_20]
0x18001288e  mov     [rax], rdi
0x180012891  mov     rcx, cs:WPP_GLOBAL_Control
0x180012898  lea     r15, WPP_GLOBAL_Control
0x18001289f  cmp     rcx, r15
0x1800128a2  jz      short loc_1800128C2
0x1800128a4  test    byte ptr [rcx+1Ch], 8
0x1800128a8  jz      short loc_1800128C2
0x1800128aa  mov     rcx, [rcx+10h]
0x1800128ae  lea     r8, WPP_81786cd8cf3b310d22fd5a7ce0f9edab_Traceguids
0x1800128b5  mov     edx, 12h
0x1800128ba  mov     r9, rdi
0x1800128bd  call    WPP_SF_S
0x1800128c2  mov     r8, rsi; Source
0x1800128c5  mov     rdx, r14; SizeInWords
0x1800128c8  mov     rcx, rbx; Destination
0x1800128cb  call    cs:__imp_wcscpy_s
0x1800128d1  mov     rax, [rsp+78h+arg_18]
0x1800128d9  mov     [rax], rbx
0x1800128dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800128e3  cmp     rcx, r15
0x1800128e6  jz      short loc_180012906
0x1800128e8  test    byte ptr [rcx+1Ch], 8
0x1800128ec  jz      short loc_180012906
0x1800128ee  mov     rcx, [rcx+10h]
0x1800128f2  lea     r8, WPP_81786cd8cf3b310d22fd5a7ce0f9edab_Traceguids
0x1800128f9  mov     edx, 13h
0x1800128fe  mov     r9, rbx
0x180012901  call    WPP_SF_S
0x180012906  xor     ecx, ecx; pv
0x180012908  mov     [r13+0], r12d
0x18001290c  call    cs:__imp_CoTaskMemFree
0x180012912  xor     ecx, ecx; pv
0x180012914  call    cs:__imp_CoTaskMemFree
0x18001291a  call    cs:__imp_GetProcessHeap
0x180012920  mov     r8, rsi; lpMem
0x180012923  xor     edx, edx; dwFlags
0x180012925  mov     rcx, rax; hHeap
0x180012928  call    cs:__imp_HeapFree
0x18001292e  call    cs:__imp_GetProcessHeap
0x180012934  mov     r8, rbp; lpMem
0x180012937  xor     edx, edx; dwFlags
0x180012939  mov     rcx, rax; hHeap
0x18001293c  call    cs:__imp_HeapFree
0x180012942  mov     rcx, cs:WPP_GLOBAL_Control
0x180012949  lea     rbp, WPP_GLOBAL_Control
0x180012950  cmp     rcx, rbp
0x180012953  jz      short loc_180012974
0x180012955  test    byte ptr [rcx+1Ch], 8
0x180012959  jz      short loc_180012974
0x18001295b  mov     r9d, [r13+0]
0x18001295f  lea     r8, WPP_81786cd8cf3b310d22fd5a7ce0f9edab_Traceguids
0x180012966  mov     rcx, [rcx+10h]
0x18001296a  mov     edx, 14h
0x18001296f  call    WPP_SF_d
0x180012974  xor     eax, eax
0x180012976  add     rsp, 38h
0x18001297a  pop     r15
0x18001297c  pop     r14
0x18001297e  pop     r13
0x180012980  pop     r12
0x180012982  pop     rdi
0x180012983  pop     rsi
0x180012984  pop     rbp
0x180012985  pop     rbx
0x180012986  retn
0x180012987  mov     rcx, rbx; pv
0x18001298a  call    cs:__imp_CoTaskMemFree
0x180012990  jmp     short loc_180012995
0x180012992  mov     rdi, rbx
0x180012995  mov     rcx, rdi; pv
0x180012998  call    cs:__imp_CoTaskMemFree
0x18001299e  call    cs:__imp_GetProcessHeap
0x1800129a4  mov     r8, rsi; lpMem
0x1800129a7  xor     edx, edx; dwFlags
0x1800129a9  mov     rcx, rax; hHeap
0x1800129ac  call    cs:__imp_HeapFree
0x1800129b2  call    cs:__imp_GetProcessHeap
0x1800129b8  mov     r8, rbp; lpMem
0x1800129bb  xor     edx, edx; dwFlags
0x1800129bd  mov     rcx, rax; hHeap
0x1800129c0  call    cs:__imp_HeapFree
0x1800129c6  mov     eax, 8007000Eh
0x1800129cb  jmp     short loc_180012976
```
