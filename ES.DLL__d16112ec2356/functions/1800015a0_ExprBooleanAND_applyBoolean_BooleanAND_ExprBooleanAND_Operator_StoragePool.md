# ExprBooleanAND::applyBoolean_BooleanAND(ExprBooleanAND &,Operator,StoragePool &)

- ea: `0x1800015a0`
- end: `0x18000185e`
- name: `?applyBoolean_BooleanAND@ExprBooleanAND@@UEAAPEAVExprNode@@AEAV1@W4Operator@@AEAVStoragePool@@@Z`
- size: `702`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800015a0`
- `0x180001870`
- `0x180001c14`
- `0x180003d54`
- `0x18001a7d0`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800016c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180001755`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800016c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180001755`

## string_xrefs

- `0x180001720`: `com\complus\src\events\queryengine\pool.cpp`
- `0x1800017b7`: `com\complus\src\events\queryengine\pool.cpp`
- `0x1800017f7`: `com\complus\src\events\queryengine\pool.cpp`
- `0x18000181c`: `com\complus\src\events\queryengine\pool.cpp`

## pseudocode

```c
ExprBooleanAND *__fastcall ExprBooleanAND::applyBoolean_BooleanAND(ExprBooleanAND *a1, _QWORD *a2, int a3, __int64 a4)
{
  __int64 v7; // rcx
  unsigned __int64 v8; // rax
  __int64 v9; // rbx
  __int64 v10; // rdx
  int v11; // edi
  unsigned __int64 v12; // rax
  __int64 v13; // rax
  struct ExprConstant *v14; // r8
  __int64 v15; // rcx
  ExprBooleanAND *result; // rax
  unsigned __int64 v17; // rbx
  StoragePool::Blob *v18; // rax
  __int64 v19; // rbp
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // r15
  StoragePool::Blob *v22; // rax
  __int64 v23; // rbp
  unsigned __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rbx

  if ( a3 != 4 )
  {
    v7 = *(_QWORD *)(a4 + 8);
    v8 = *(_QWORD *)(v7 + 16);
    if ( v8 >= 0x18 )
    {
      v9 = *(_QWORD *)(v7 + 8);
      *(_QWORD *)(v7 + 16) = v8 - 24;
      *(_QWORD *)(v7 + 8) = v9 + 24;
      if ( v9 )
        goto LABEL_4;
    }
    v17 = *(_QWORD *)a4;
    if ( *(_QWORD *)a4 < 0x18u )
      v17 = 48;
    v18 = (StoragePool::Blob *)CoTaskMemAlloc(0x20u);
    if ( v18 )
    {
      v19 = StoragePool::Blob::Blob(v18, v17, *(struct StoragePool::Blob **)(a4 + 8));
      if ( v19 )
      {
LABEL_16:
        *(_QWORD *)a4 = v17;
        *(_QWORD *)(a4 + 8) = v19;
        v20 = *(_QWORD *)(v19 + 16);
        if ( v20 < 0x18
          || (v9 = *(_QWORD *)(v19 + 8), *(_QWORD *)(v19 + 16) = v20 - 24, *(_QWORD *)(v19 + 8) = v9 + 24, !v9) )
        {
          InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x64u, 0xC0001204, 0x10u);
          v9 = 0;
          goto LABEL_5;
        }
LABEL_4:
        *(_QWORD *)(v9 + 8) = 0;
        *(_QWORD *)v9 = &ExprBooleanOR::`vftable';
        *(_BYTE *)(v9 + 16) = 0;
        (*(void (__fastcall **)(_QWORD *, __int64, __int64))(*a2 + 72LL))(a2, v9, a4);
LABEL_5:
        v10 = *(_QWORD *)(a4 + 8);
        v11 = 1;
        v12 = *(_QWORD *)(v10 + 16);
        if ( v12 >= 0x18 )
        {
          *(_QWORD *)(v10 + 16) = v12 - 24;
          v13 = *(_QWORD *)(v10 + 8);
          *(_QWORD *)(v10 + 8) = v13 + 24;
          if ( v13 )
            goto LABEL_7;
        }
        v21 = *(_QWORD *)a4;
        if ( *(_QWORD *)a4 < 0x18u )
          v21 = 48;
        v22 = (StoragePool::Blob *)CoTaskMemAlloc(0x20u);
        if ( v22 )
        {
          v23 = StoragePool::Blob::Blob(v22, v21, *(struct StoragePool::Blob **)(a4 + 8));
          if ( v23 )
          {
LABEL_23:
            *(_QWORD *)a4 = v21;
            *(_QWORD *)(a4 + 8) = v23;
            v24 = *(_QWORD *)(v23 + 16);
            if ( v24 < 0x18
              || (*(_QWORD *)(v23 + 16) = v24 - 24, v13 = *(_QWORD *)(v23 + 8), *(_QWORD *)(v23 + 8) = v13 + 24, !v13) )
            {
              InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x64u, 0xC0001204, 0x10u);
              v13 = 0;
LABEL_8:
              v14 = (struct ExprConstant *)*((_QWORD *)a1 + 3);
              if ( v14 )
              {
                ExprBooleanOR::InsertChild((ExprBooleanOR *)v9, (struct ExprBooleanOR::Element *)v13, v14);
                return (ExprBooleanAND *)v9;
              }
              else
              {
                *(_QWORD *)(v13 + 16) = *(_QWORD *)(v9 + 8);
                v15 = *(_QWORD *)(v9 + 8);
                if ( v15 )
                  v11 = *(_DWORD *)(v15 + 8) + 1;
                *(_DWORD *)(v13 + 8) = v11;
                *(_QWORD *)(v9 + 8) = v13;
                result = (ExprBooleanAND *)v9;
                *(_BYTE *)(v9 + 16) = 0;
              }
              return result;
            }
LABEL_7:
            *(_QWORD *)v13 = a1;
            *(_DWORD *)(v13 + 8) = 1;
            *(_QWORD *)(v13 + 16) = 0;
            goto LABEL_8;
          }
        }
        else
        {
          v23 = 0;
        }
        InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x5Eu, 0xC0001204, 0x10u);
        goto LABEL_23;
      }
    }
    else
    {
      v19 = 0;
    }
    InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x5Eu, 0xC0001204, 0x10u);
    goto LABEL_16;
  }
  v25 = a2[1];
  if ( v25 )
  {
    do
    {
      v26 = *(_QWORD *)(v25 + 8);
      ExprBooleanAND::InsertChild(a1, (struct ExprBooleanAND::Element *)v25);
      v25 = v26;
    }
    while ( v26 );
  }
  return a1;
}

```

## disassembly

```asm
0x1800015a0  push    rbx
0x1800015a2  push    rsi
0x1800015a3  push    rdi
0x1800015a4  push    r14
0x1800015a6  sub     rsp, 28h
0x1800015aa  mov     r14, r9
0x1800015ad  mov     rdi, rdx
0x1800015b0  mov     rsi, rcx
0x1800015b3  cmp     r8d, 4
0x1800015b7  jz      loc_180001839
0x1800015bd  mov     rcx, [r9+8]
0x1800015c1  mov     [rsp+48h+arg_0], rbp
0x1800015c6  mov     [rsp+48h+arg_8], r12
0x1800015cb  xor     r12d, r12d
0x1800015ce  mov     [rsp+48h+arg_10], r13
0x1800015d3  mov     r13d, 30h ; '0'
0x1800015d9  mov     rax, [rcx+10h]
0x1800015dd  cmp     rax, 18h
0x1800015e1  jb      loc_1800016B3
0x1800015e7  mov     rbx, [rcx+8]
0x1800015eb  add     rax, 0FFFFFFFFFFFFFFE8h
0x1800015ef  mov     [rcx+10h], rax
0x1800015f3  lea     rax, [rbx+18h]
0x1800015f7  mov     [rcx+8], rax
0x1800015fb  test    rbx, rbx
0x1800015fe  jz      loc_1800016B3
0x180001604  lea     rax, ??_7ExprBooleanOR@@6B@; const ExprBooleanOR::`vftable'
0x18000160b  mov     [rbx+8], r12
0x18000160f  mov     [rbx], rax
0x180001612  mov     r8, r14
0x180001615  mov     [rbx+10h], r12b
0x180001619  mov     rdx, rbx
0x18000161c  mov     rax, [rdi]
0x18000161f  mov     rcx, rdi
0x180001622  mov     rax, [rax+48h]
0x180001626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000162b  mov     rdx, [r14+8]
0x18000162f  mov     edi, 1
0x180001634  mov     rax, [rdx+10h]
0x180001638  cmp     rax, 18h
0x18000163c  jb      loc_180001740
0x180001642  add     rax, 0FFFFFFFFFFFFFFE8h
0x180001646  mov     [rdx+10h], rax
0x18000164a  mov     rax, [rdx+8]
0x18000164e  lea     rcx, [rax+18h]
0x180001652  mov     [rdx+8], rcx
0x180001656  test    rax, rax
0x180001659  jz      loc_180001740
0x18000165f  mov     [rax], rsi
0x180001662  mov     [rax+8], edi
0x180001665  mov     [rax+10h], r12
0x180001669  mov     r8, [rsi+18h]; struct ExprConstant *
0x18000166d  mov     r13, [rsp+48h+arg_10]
0x180001672  mov     r12, [rsp+48h+arg_8]
0x180001677  mov     rbp, [rsp+48h+arg_0]
0x18000167c  test    r8, r8
0x18000167f  jnz     loc_1800017D7
0x180001685  mov     rcx, [rbx+8]
0x180001689  mov     [rax+10h], rcx
0x18000168d  mov     rcx, [rbx+8]
0x180001691  test    rcx, rcx
0x180001694  jz      short loc_18000169B
0x180001696  mov     edi, [rcx+8]
0x180001699  inc     edi
0x18000169b  mov     [rax+8], edi
0x18000169e  mov     [rbx+8], rax
0x1800016a2  mov     rax, rbx
0x1800016a5  mov     byte ptr [rbx+10h], 0
0x1800016a9  add     rsp, 28h
0x1800016ad  pop     r14
0x1800016af  pop     rdi
0x1800016b0  pop     rsi
0x1800016b1  pop     rbx
0x1800016b2  retn
0x1800016b3  mov     rbx, [r9]
0x1800016b6  mov     ecx, 20h ; ' '; cb
0x1800016bb  cmp     rbx, 18h
0x1800016bf  cmovb   rbx, r13
0x1800016c3  call    cs:__imp_CoTaskMemAlloc
0x1800016c9  test    rax, rax
0x1800016cc  jz      loc_1800017EF
0x1800016d2  mov     r8, [r14+8]; struct StoragePool::Blob *
0x1800016d6  mov     rdx, rbx; unsigned __int64
0x1800016d9  mov     rcx, rax; this
0x1800016dc  call    ??0Blob@StoragePool@@QEAA@_KPEAU01@@Z; StoragePool::Blob::Blob(unsigned __int64,StoragePool::Blob *)
0x1800016e1  mov     rbp, rax
0x1800016e4  test    rax, rax
0x1800016e7  jz      loc_1800017F2
0x1800016ed  mov     [r14], rbx
0x1800016f0  mov     [r14+8], rbp
0x1800016f4  mov     rax, [rbp+10h]
0x1800016f8  cmp     rax, 18h
0x1800016fc  jb      short loc_18000171B
0x1800016fe  mov     rbx, [rbp+8]
0x180001702  add     rax, 0FFFFFFFFFFFFFFE8h
0x180001706  mov     [rbp+10h], rax
0x18000170a  lea     rax, [rbx+18h]
0x18000170e  mov     [rbp+8], rax
0x180001712  test    rbx, rbx
0x180001715  jnz     loc_180001604
0x18000171b  mov     edx, 64h ; 'd'; unsigned int
0x180001720  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x180001727  mov     r9d, 10h; unsigned __int16
0x18000172d  mov     r8d, 0C0001204h; unsigned int
0x180001733  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180001738  mov     rbx, r12
0x18000173b  jmp     loc_18000162B
0x180001740  mov     [rsp+48h+var_28], r15
0x180001745  mov     ecx, 20h ; ' '; cb
0x18000174a  mov     r15, [r14]
0x18000174d  cmp     r15, 18h
0x180001751  cmovb   r15, r13
0x180001755  call    cs:__imp_CoTaskMemAlloc
0x18000175b  test    rax, rax
0x18000175e  jz      loc_180001814
0x180001764  mov     r8, [r14+8]; struct StoragePool::Blob *
0x180001768  mov     rdx, r15; unsigned __int64
0x18000176b  mov     rcx, rax; this
0x18000176e  call    ??0Blob@StoragePool@@QEAA@_KPEAU01@@Z; StoragePool::Blob::Blob(unsigned __int64,StoragePool::Blob *)
0x180001773  mov     rbp, rax
0x180001776  test    rax, rax
0x180001779  jz      loc_180001817
0x18000177f  mov     [r14], r15
0x180001782  mov     r15, [rsp+48h+var_28]
0x180001787  mov     [r14+8], rbp
0x18000178b  mov     rax, [rbp+10h]
0x18000178f  cmp     rax, 18h
0x180001793  jb      short loc_1800017B2
0x180001795  add     rax, 0FFFFFFFFFFFFFFE8h
0x180001799  mov     [rbp+10h], rax
0x18000179d  mov     rax, [rbp+8]
0x1800017a1  lea     rcx, [rax+18h]
0x1800017a5  mov     [rbp+8], rcx
0x1800017a9  test    rax, rax
0x1800017ac  jnz     loc_18000165F
0x1800017b2  mov     edx, 64h ; 'd'; unsigned int
0x1800017b7  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x1800017be  mov     r9d, 10h; unsigned __int16
0x1800017c4  mov     r8d, 0C0001204h; unsigned int
0x1800017ca  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x1800017cf  mov     rax, r12
0x1800017d2  jmp     loc_180001669
0x1800017d7  mov     rdx, rax; struct ExprBooleanOR::Element *
0x1800017da  mov     rcx, rbx; this
0x1800017dd  call    ?InsertChild@ExprBooleanOR@@AEAAXPEAUElement@1@AEAVExprConstant@@@Z; ExprBooleanOR::InsertChild(ExprBooleanOR::Element *,ExprConstant &)
0x1800017e2  mov     rax, rbx
0x1800017e5  add     rsp, 28h
0x1800017e9  pop     r14
0x1800017eb  pop     rdi
0x1800017ec  pop     rsi
0x1800017ed  pop     rbx
0x1800017ee  retn
0x1800017ef  mov     rbp, r12
0x1800017f2  mov     edx, 5Eh ; '^'; unsigned int
0x1800017f7  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x1800017fe  mov     r9d, 10h; unsigned __int16
0x180001804  mov     r8d, 0C0001204h; unsigned int
0x18000180a  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18000180f  jmp     loc_1800016ED
0x180001814  mov     rbp, r12
0x180001817  mov     edx, 5Eh ; '^'; unsigned int
0x18000181c  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x180001823  mov     r9d, 10h; unsigned __int16
0x180001829  mov     r8d, 0C0001204h; unsigned int
0x18000182f  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180001834  jmp     loc_18000177F
0x180001839  mov     rdx, [rdx+8]; struct ExprBooleanAND::Element *
0x18000183d  test    rdx, rdx
0x180001840  jz      short loc_180001856
0x180001842  mov     rbx, [rdx+8]
0x180001846  mov     rcx, rsi; this
0x180001849  call    ?InsertChild@ExprBooleanAND@@AEAAXPEAUElement@1@@Z; ExprBooleanAND::InsertChild(ExprBooleanAND::Element *)
0x18000184e  mov     rdx, rbx
0x180001851  test    rbx, rbx
0x180001854  jnz     short loc_180001842
0x180001856  mov     rax, rsi
0x180001859  jmp     loc_1800016A9
```
