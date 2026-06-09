# MosStorageGetStorageSizesInBytes(_STORAGE_DEVICE_DATA const &,unsigned __int64 *,unsigned __int64 *)

- ea: `0x1800090a0`
- end: `0x180009202`
- name: `?MosStorageGetStorageSizesInBytes@@YAJAEBU_STORAGE_DEVICE_DATA@@PEA_K1@Z`
- size: `354`
- prototype: `__int64 __fastcall(const struct _STORAGE_DEVICE_DATA *, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180009370`
- `0x180009cc0`

## callees

- `0x180002ab8`
- `0x1800090a0`
- `0x180010010`

## import_xrefs

- `ZTrace_Maps!ZTraceReportIgnoreNoThis` at `0x1800091d1`
- `ZTrace_Maps!ZTraceReportIgnoreNoThis` at `0x1800091d1`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180009114`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180009114`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000913a`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000913a`
- `ext-ms-win-storage-sense-l1-1-0!OpenStorageTypeSearch` at `0x180009125`
- `ext-ms-win-storage-sense-l1-1-0!OpenStorageTypeSearch` at `0x180009125`
- `ext-ms-win-storage-sense-l1-1-0!SelectStorageVolumeEx` at `0x180009186`
- `ext-ms-win-storage-sense-l1-1-0!SelectStorageVolumeEx` at `0x180009186`
- `ext-ms-win-storage-sense-l1-1-0!CloseFindStorageSearch` at `0x1800091bc`
- `ext-ms-win-storage-sense-l1-1-0!CloseFindStorageSearch` at `0x1800091bc`

## pseudocode

```c
__int64 __fastcall MosStorageGetStorageSizesInBytes(
        const struct _STORAGE_DEVICE_DATA *a1,
        unsigned __int64 *a2,
        unsigned __int64 *a3)
{
  unsigned int v6; // ebx
  int v7; // r8d
  unsigned int v8; // eax
  unsigned int v9; // edi
  int v10; // eax
  int v11; // r8d
  int StorageSearch; // eax
  __int64 v14; // [rsp+40h] [rbp-28h] BYREF
  unsigned __int64 v15; // [rsp+48h] [rbp-20h] BYREF
  unsigned __int64 v16[3]; // [rsp+50h] [rbp-18h] BYREF

  v14 = 0;
  v15 = 0;
  v16[0] = 0;
  v6 = 0;
  if ( qword_1800184A8 )
    v6 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)qword_1800184A8 + 24LL))(qword_1800184A8, 2);
  if ( (unsigned __int8)IsSelectStorageVolumeExPresent() )
  {
    v10 = OpenStorageTypeSearch(&v14);
    if ( v10 >= 0 )
    {
      if ( !(unsigned __int8)IsSelectStorageVolumeExPresent() )
      {
        v7 = 581;
        goto LABEL_5;
      }
      v10 = SelectStorageVolumeEx(v14, *((unsigned int *)a1 + 133), *(unsigned int *)a1, 0, 0, 0, &v15, v16);
      if ( v10 >= 0 )
      {
        v9 = 0;
        *a2 = v15;
        *a3 = v16[0];
        goto LABEL_15;
      }
      v11 = 590;
    }
    else
    {
      v11 = 580;
    }
    v8 = ZTraceReportPropagationNoThis(v10, "MosStorageGetStorageSizesInBytes", v11);
    goto LABEL_6;
  }
  v7 = 579;
LABEL_5:
  v8 = ZTraceReportOriginationNoThis(-2147024769, "MosStorageGetStorageSizesInBytes", v7);
LABEL_6:
  v9 = v8;
LABEL_15:
  if ( v14 )
  {
    if ( (unsigned __int8)IsSelectStorageVolumeExPresent() )
    {
      StorageSearch = CloseFindStorageSearch(&v14);
      if ( StorageSearch < 0 )
        ZTraceReportIgnoreNoThis(StorageSearch, "MosStorageGetStorageSizesInBytes", 601);
    }
  }
  if ( qword_1800184A8 )
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)qword_1800184A8 + 24LL))(qword_1800184A8, v6);
  return v9;
}

```

## disassembly

```asm
0x1800090a0  push    rbp
0x1800090a2  push    rbx
0x1800090a3  push    rsi
0x1800090a4  push    rdi
0x1800090a5  push    r12
0x1800090a7  push    r14
0x1800090a9  mov     rbp, rsp
0x1800090ac  sub     rsp, 68h
0x1800090b0  mov     rsi, r8
0x1800090b3  mov     r14, rdx
0x1800090b6  mov     rdi, rcx
0x1800090b9  mov     [rbp+var_28], 0
0x1800090c1  mov     [rbp+var_20], 0
0x1800090c9  mov     [rbp+var_18], 0
0x1800090d1  xor     ebx, ebx
0x1800090d3  mov     [rbp+arg_18], ebx
0x1800090d6  mov     rcx, cs:qword_1800184A8
0x1800090dd  test    rcx, rcx
0x1800090e0  jz      short loc_1800090F6
0x1800090e2  mov     rax, [rcx]
0x1800090e5  lea     edx, [rbx+2]
0x1800090e8  mov     rax, [rax+18h]
0x1800090ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090f1  mov     ebx, eax
0x1800090f3  mov     [rbp+arg_18], eax
0x1800090f6  call    IsSelectStorageVolumeExPresent
0x1800090fb  lea     r12, aMosstoragegets_3; "MosStorageGetStorageSizesInBytes"
0x180009102  test    al, al
0x180009104  jnz     short loc_180009121
0x180009106  mov     r8d, 243h
0x18000910c  mov     rdx, r12
0x18000910f  mov     ecx, 8007007Fh
0x180009114  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18000911a  mov     edi, eax
0x18000911c  jmp     loc_1800091A8
0x180009121  lea     rcx, [rbp+var_28]
0x180009125  call    cs:__imp_OpenStorageTypeSearch
0x18000912b  test    eax, eax
0x18000912d  jns     short loc_180009142
0x18000912f  mov     r8d, 244h
0x180009135  mov     rdx, r12
0x180009138  mov     ecx, eax
0x18000913a  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180009140  jmp     short loc_18000911A
0x180009142  call    IsSelectStorageVolumeExPresent
0x180009147  test    al, al
0x180009149  jnz     short loc_180009153
0x18000914b  mov     r8d, 245h
0x180009151  jmp     short loc_18000910C
0x180009153  lea     rax, [rbp+var_18]
0x180009157  mov     [rsp+68h+var_30], rax
0x18000915c  lea     rax, [rbp+var_20]
0x180009160  mov     [rsp+68h+var_38], rax
0x180009165  mov     [rsp+68h+var_40], 0
0x18000916d  mov     [rsp+68h+var_48], 0
0x180009176  xor     r9d, r9d
0x180009179  mov     r8d, [rdi]
0x18000917c  mov     edx, [rdi+214h]
0x180009182  mov     rcx, [rbp+var_28]
0x180009186  call    cs:__imp_SelectStorageVolumeEx
0x18000918c  test    eax, eax
0x18000918e  jns     short loc_180009198
0x180009190  mov     r8d, 24Eh
0x180009196  jmp     short loc_180009135
0x180009198  xor     edi, edi
0x18000919a  mov     rax, [rbp+var_20]
0x18000919e  mov     [r14], rax
0x1800091a1  mov     rax, [rbp+var_18]
0x1800091a5  mov     [rsi], rax
0x1800091a8  cmp     [rbp+var_28], 0
0x1800091ad  jz      short loc_1800091D8
0x1800091af  call    IsSelectStorageVolumeExPresent
0x1800091b4  test    al, al
0x1800091b6  jz      short loc_1800091D8
0x1800091b8  lea     rcx, [rbp+var_28]
0x1800091bc  call    cs:__imp_CloseFindStorageSearch
0x1800091c2  test    eax, eax
0x1800091c4  jns     short loc_1800091D8
0x1800091c6  mov     r8d, 259h
0x1800091cc  mov     rdx, r12
0x1800091cf  mov     ecx, eax
0x1800091d1  call    cs:__imp_?ZTraceReportIgnoreNoThis@@YAXHPEBDH@Z; ZTraceReportIgnoreNoThis(int,char const *,int)
0x1800091d7  nop
0x1800091d8  mov     rcx, cs:qword_1800184A8
0x1800091df  test    rcx, rcx
0x1800091e2  jz      short loc_1800091F3
0x1800091e4  mov     rax, [rcx]
0x1800091e7  mov     edx, ebx
0x1800091e9  mov     rax, [rax+18h]
0x1800091ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091f2  nop
0x1800091f3  mov     eax, edi
0x1800091f5  add     rsp, 68h
0x1800091f9  pop     r14
0x1800091fb  pop     r12
0x1800091fd  pop     rdi
0x1800091fe  pop     rsi
0x1800091ff  pop     rbx
0x180009200  pop     rbp
0x180009201  retn
```
