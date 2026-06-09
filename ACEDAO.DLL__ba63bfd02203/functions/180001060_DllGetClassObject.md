# DllGetClassObject

- ea: `0x180001060`
- end: `0x1800014e1`
- name: `DllGetClassObject`
- size: `1153`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001060`
- `0x180003ed8`
- `0x180073ca4`
- `0x180073cdc`
- `0x180074278`
- `0x1800748f0`
- `0x180074b20`
- `0x180076f88`
- `0x18007c376`
- `0x18007c500`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180001123`
- `KERNEL32!GetProcAddress` at `0x180001123`

## string_xrefs

- `0x180001119`: `DllGetClassObject`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT v6; // edi
  HMODULE v7; // rax
  HRESULT (__stdcall *ProcAddress)(const IID *const, const IID *const, LPVOID *); // rax
  _QWORD *v9; // rax
  _DWORD *v10; // rbx
  void **v11; // rax
  _QWORD *v12; // rax
  _QWORD *v13; // rax
  _QWORD *v14; // rax
  _QWORD *v15; // rax
  _QWORD *v16; // rax
  _QWORD *v17; // rax
  _QWORD *v18; // rax
  _QWORD *v19; // rax
  _DWORD Buf2[4]; // [rsp+20h] [rbp-20h] BYREF
  _DWORD v22[4]; // [rsp+30h] [rbp-10h] BYREF
  char v23; // [rsp+70h] [rbp+30h] BYREF

  sub_180076F88(&v23);
  sub_180073CDC();
  sub_1800748F0();
  if ( !ppv )
  {
    v6 = -2147024809;
    goto LABEL_52;
  }
  *ppv = 0;
  Buf2[0] = -1685271532;
  Buf2[1] = 1147803367;
  Buf2[2] = -1001335636;
  Buf2[3] = 319720050;
  v22[0] = 60728512;
  v22[1] = 298903190;
  v22[2] = -1610577273;
  v22[3] = 1455890121;
  if ( !memcmp(rclsid, Buf2, 0x10u) || !memcmp(rclsid, v22, 0x10u) )
  {
    v7 = (HMODULE)sub_180073CA4(524296);
    if ( v7 )
    {
      ProcAddress = (HRESULT (__stdcall *)(const IID *const, const IID *const, LPVOID *))GetProcAddress(
                                                                                           v7,
                                                                                           "DllGetClassObject");
      if ( ProcAddress )
      {
        v6 = ((__int64 (__fastcall *)(const IID *const, const IID *const, LPVOID *))ProcAddress)(rclsid, riid, ppv);
        goto LABEL_52;
      }
    }
  }
  if ( !memcmp(rclsid, qword_18008CCB0, 0x10u) || !memcmp(rclsid, qword_18008CCA0, 0x10u) )
  {
    v19 = (_QWORD *)sub_180003ED8();
    v10 = v19;
    if ( v19 )
    {
      *v19 = &CDAOClassFactory::`vftable';
      v11 = &CDAODBEngineCF::`vftable';
      goto LABEL_45;
    }
  }
  else if ( !memcmp(rclsid, qword_18008CC90, 0x10u) || !memcmp(rclsid, qword_18008CC80, 0x10u) )
  {
    v18 = (_QWORD *)sub_180003ED8();
    v10 = v18;
    if ( v18 )
    {
      *v18 = &CDAOClassFactory::`vftable';
      v11 = &CDAOTableDefCF::`vftable';
      goto LABEL_45;
    }
  }
  else if ( !memcmp(rclsid, qword_18008CC70, 0x10u) || !memcmp(rclsid, qword_18008CC60, 0x10u) )
  {
    v17 = (_QWORD *)sub_180003ED8();
    v10 = v17;
    if ( v17 )
    {
      *v17 = &CDAOClassFactory::`vftable';
      v11 = &CDAOQueryDefCF::`vftable';
      goto LABEL_45;
    }
  }
  else if ( !memcmp(rclsid, qword_18008CC50, 0x10u) || !memcmp(rclsid, qword_18008CC40, 0x10u) )
  {
    v16 = (_QWORD *)sub_180003ED8();
    v10 = v16;
    if ( v16 )
    {
      *v16 = &CDAOClassFactory::`vftable';
      v11 = &CDAOFieldCF::`vftable';
      goto LABEL_45;
    }
  }
  else if ( !memcmp(rclsid, qword_18008CC30, 0x10u) || !memcmp(rclsid, qword_18008CC20, 0x10u) )
  {
    v15 = (_QWORD *)sub_180003ED8();
    v10 = v15;
    if ( v15 )
    {
      *v15 = &CDAOClassFactory::`vftable';
      v11 = &CDAOIndexCF::`vftable';
      goto LABEL_45;
    }
  }
  else if ( !memcmp(rclsid, qword_18008CC10, 0x10u) || !memcmp(rclsid, qword_18008CC00, 0x10u) )
  {
    v14 = (_QWORD *)sub_180003ED8();
    v10 = v14;
    if ( v14 )
    {
      *v14 = &CDAOClassFactory::`vftable';
      v11 = &CDAOGroupCF::`vftable';
      goto LABEL_45;
    }
  }
  else if ( !memcmp(rclsid, qword_18008CBF0, 0x10u) || !memcmp(rclsid, qword_18008CBE0, 0x10u) )
  {
    v13 = (_QWORD *)sub_180003ED8();
    v10 = v13;
    if ( v13 )
    {
      *v13 = &CDAOClassFactory::`vftable';
      v11 = &CDAOUserCF::`vftable';
      goto LABEL_45;
    }
  }
  else if ( !memcmp(rclsid, qword_18008CBD0, 0x10u) || !memcmp(rclsid, qword_18008CBC0, 0x10u) )
  {
    v12 = (_QWORD *)sub_180003ED8();
    v10 = v12;
    if ( v12 )
    {
      *v12 = &CDAOClassFactory::`vftable';
      v11 = &CDAOPrivDBEngineCF::`vftable';
      goto LABEL_45;
    }
  }
  else
  {
    if ( memcmp(rclsid, qword_18008CBB0, 0x10u) && memcmp(rclsid, qword_18008CBA0, 0x10u) )
    {
      v6 = -2147221231;
      goto LABEL_52;
    }
    v9 = (_QWORD *)sub_180003ED8();
    v10 = v9;
    if ( v9 )
    {
      *v9 = &CDAOClassFactory::`vftable';
      v11 = &CDAORelationCF::`vftable';
LABEL_45:
      v10[2] = 1;
      _InterlockedIncrement(&dword_1800B20C8);
      *(_QWORD *)v10 = v11;
      goto LABEL_47;
    }
  }
  v10 = 0;
LABEL_47:
  if ( v10 )
  {
    v6 = (**(__int64 (__fastcall ***)(_DWORD *, const IID *const, LPVOID *))v10)(v10, riid, ppv);
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v10 + 16LL))(v10);
    if ( sub_180074278() && v6 >= 0 )
      sub_180074B20(riid, ppv);
  }
  else
  {
    v6 = -2147024882;
  }
LABEL_52:
  if ( v23 )
    ((void (*)(void))DisableVirtualizationOnThread)();
  return v6;
}

```

## disassembly

```asm
0x180001060  mov     [rsp-18h+arg_0], rbx
0x180001065  mov     [rsp-18h+arg_8], rsi
0x18000106a  push    rbp
0x18000106b  push    rdi
0x18000106c  push    r14
0x18000106e  mov     rbp, rsp
0x180001071  sub     rsp, 40h
0x180001075  mov     rsi, r8
0x180001078  mov     r14, rdx
0x18000107b  mov     rbx, rcx
0x18000107e  lea     rcx, [rbp+arg_10]
0x180001082  call    sub_180076F88
0x180001087  call    sub_180073CDC
0x18000108c  call    sub_1800748F0
0x180001091  test    rsi, rsi
0x180001094  jnz     short loc_1800010A0
0x180001096  mov     edi, 80070057h
0x18000109b  jmp     loc_1800014B8
0x1800010a0  mov     qword ptr [rsi], 0
0x1800010a7  mov     [rbp+Buf2], 9B8CCC14h
0x1800010ae  mov     [rbp+var_1C], 446A16E7h
0x1800010b5  mov     [rbp+var_18], 0C450D4ACh
0x1800010bc  mov     [rbp+var_14], 130E8A72h
0x1800010c3  mov     [rbp+var_10], 39EA4C0h
0x1800010ca  mov     [rbp+var_C], 11D0E696h
0x1800010d1  mov     [rbp+var_8], 0A0008A87h
0x1800010d8  mov     [rbp+var_4], 56C71EC9h
0x1800010df  mov     edi, 10h
0x1800010e4  mov     r8d, edi; Size
0x1800010e7  lea     rdx, [rbp+Buf2]; Buf2
0x1800010eb  mov     rcx, rbx; Buf1
0x1800010ee  call    memcmp
0x1800010f3  test    eax, eax
0x1800010f5  jz      short loc_18000110A
0x1800010f7  mov     r8d, edi; Size
0x1800010fa  lea     rdx, [rbp+var_10]; Buf2
0x1800010fe  mov     rcx, rbx; Buf1
0x180001101  call    memcmp
0x180001106  test    eax, eax
0x180001108  jnz     short loc_180001144
0x18000110a  mov     ecx, 80008h
0x18000110f  call    sub_180073CA4
0x180001114  test    rax, rax
0x180001117  jz      short loc_180001144
0x180001119  lea     rdx, ProcName; "DllGetClassObject"
0x180001120  mov     rcx, rax; hModule
0x180001123  call    cs:GetProcAddress
0x180001129  test    rax, rax
0x18000112c  jz      short loc_180001144
0x18000112e  mov     r8, rsi
0x180001131  mov     rdx, r14
0x180001134  mov     rcx, rbx
0x180001137  call    cs:__guard_dispatch_icall_fptr
0x18000113d  mov     edi, eax
0x18000113f  jmp     loc_1800014B8
0x180001144  mov     r8, rdi; Size
0x180001147  lea     rdx, qword_18008CCB0; Buf2
0x18000114e  mov     rcx, rbx; Buf1
0x180001151  call    memcmp
0x180001156  test    eax, eax
0x180001158  jz      loc_180001439
0x18000115e  mov     r8, rdi; Size
0x180001161  lea     rdx, qword_18008CCA0; Buf2
0x180001168  mov     rcx, rbx; Buf1
0x18000116b  call    memcmp
0x180001170  test    eax, eax
0x180001172  jz      loc_180001439
0x180001178  mov     r8, rdi; Size
0x18000117b  lea     rdx, qword_18008CC90; Buf2
0x180001182  mov     rcx, rbx; Buf1
0x180001185  call    memcmp
0x18000118a  test    eax, eax
0x18000118c  jz      loc_180001419
0x180001192  mov     r8, rdi; Size
0x180001195  lea     rdx, qword_18008CC80; Buf2
0x18000119c  mov     rcx, rbx; Buf1
0x18000119f  call    memcmp
0x1800011a4  test    eax, eax
0x1800011a6  jz      loc_180001419
0x1800011ac  mov     r8, rdi; Size
0x1800011af  lea     rdx, qword_18008CC70; Buf2
0x1800011b6  mov     rcx, rbx; Buf1
0x1800011b9  call    memcmp
0x1800011be  test    eax, eax
0x1800011c0  jz      loc_1800013F9
0x1800011c6  mov     r8, rdi; Size
0x1800011c9  lea     rdx, qword_18008CC60; Buf2
0x1800011d0  mov     rcx, rbx; Buf1
0x1800011d3  call    memcmp
0x1800011d8  test    eax, eax
0x1800011da  jz      loc_1800013F9
0x1800011e0  mov     r8, rdi; Size
0x1800011e3  lea     rdx, qword_18008CC50; Buf2
0x1800011ea  mov     rcx, rbx; Buf1
0x1800011ed  call    memcmp
0x1800011f2  test    eax, eax
0x1800011f4  jz      loc_1800013D5
0x1800011fa  mov     r8, rdi; Size
0x1800011fd  lea     rdx, qword_18008CC40; Buf2
0x180001204  mov     rcx, rbx; Buf1
0x180001207  call    memcmp
0x18000120c  test    eax, eax
0x18000120e  jz      loc_1800013D5
0x180001214  mov     r8, rdi; Size
0x180001217  lea     rdx, qword_18008CC30; Buf2
0x18000121e  mov     rcx, rbx; Buf1
0x180001221  call    memcmp
0x180001226  test    eax, eax
0x180001228  jz      loc_1800013AE
0x18000122e  mov     r8, rdi; Size
0x180001231  lea     rdx, qword_18008CC20; Buf2
0x180001238  mov     rcx, rbx; Buf1
0x18000123b  call    memcmp
0x180001240  test    eax, eax
0x180001242  jz      loc_1800013AE
0x180001248  mov     r8, rdi; Size
0x18000124b  lea     rdx, qword_18008CC10; Buf2
0x180001252  mov     rcx, rbx; Buf1
0x180001255  call    memcmp
0x18000125a  test    eax, eax
0x18000125c  jz      loc_180001387
0x180001262  mov     r8, rdi; Size
0x180001265  lea     rdx, qword_18008CC00; Buf2
0x18000126c  mov     rcx, rbx; Buf1
0x18000126f  call    memcmp
0x180001274  test    eax, eax
0x180001276  jz      loc_180001387
0x18000127c  mov     r8, rdi; Size
0x18000127f  lea     rdx, qword_18008CBF0; Buf2
0x180001286  mov     rcx, rbx; Buf1
0x180001289  call    memcmp
0x18000128e  test    eax, eax
0x180001290  jz      loc_180001360
0x180001296  mov     r8, rdi; Size
0x180001299  lea     rdx, qword_18008CBE0; Buf2
0x1800012a0  mov     rcx, rbx; Buf1
0x1800012a3  call    memcmp
0x1800012a8  test    eax, eax
0x1800012aa  jz      loc_180001360
0x1800012b0  mov     r8, rdi; Size
0x1800012b3  lea     rdx, qword_18008CBD0; Buf2
0x1800012ba  mov     rcx, rbx; Buf1
0x1800012bd  call    memcmp
0x1800012c2  test    eax, eax
0x1800012c4  jz      short loc_180001339
0x1800012c6  mov     r8, rdi; Size
0x1800012c9  lea     rdx, qword_18008CBC0; Buf2
0x1800012d0  mov     rcx, rbx; Buf1
0x1800012d3  call    memcmp
0x1800012d8  test    eax, eax
0x1800012da  jz      short loc_180001339
0x1800012dc  mov     r8, rdi; Size
0x1800012df  lea     rdx, qword_18008CBB0; Buf2
0x1800012e6  mov     rcx, rbx; Buf1
0x1800012e9  call    memcmp
0x1800012ee  test    eax, eax
0x1800012f0  jz      short loc_180001312
0x1800012f2  mov     r8, rdi; Size
0x1800012f5  lea     rdx, qword_18008CBA0; Buf2
0x1800012fc  mov     rcx, rbx; Buf1
0x1800012ff  call    memcmp
0x180001304  test    eax, eax
0x180001306  jz      short loc_180001312
0x180001308  mov     edi, 80040111h
0x18000130d  jmp     loc_1800014B8
0x180001312  call    sub_180003ED8
0x180001317  mov     rbx, rax
0x18000131a  test    rax, rax
0x18000131d  jz      loc_18000146A
0x180001323  lea     rax, ??_7CDAOClassFactory@@6B@; const CDAOClassFactory::`vftable'
0x18000132a  mov     [rbx], rax
0x18000132d  lea     rax, ??_7CDAORelationCF@@6B@; const CDAORelationCF::`vftable'
0x180001334  jmp     loc_180001457
0x180001339  call    sub_180003ED8
0x18000133e  mov     rbx, rax
0x180001341  test    rax, rax
0x180001344  jz      loc_18000146A
0x18000134a  lea     rax, ??_7CDAOClassFactory@@6B@; const CDAOClassFactory::`vftable'
0x180001351  mov     [rbx], rax
0x180001354  lea     rax, ??_7CDAOPrivDBEngineCF@@6B@; const CDAOPrivDBEngineCF::`vftable'
0x18000135b  jmp     loc_180001457
0x180001360  call    sub_180003ED8
0x180001365  mov     rbx, rax
0x180001368  test    rax, rax
0x18000136b  jz      loc_18000146A
0x180001371  lea     rax, ??_7CDAOClassFactory@@6B@; const CDAOClassFactory::`vftable'
0x180001378  mov     [rbx], rax
0x18000137b  lea     rax, ??_7CDAOUserCF@@6B@; const CDAOUserCF::`vftable'
0x180001382  jmp     loc_180001457
0x180001387  call    sub_180003ED8
0x18000138c  mov     rbx, rax
0x18000138f  test    rax, rax
0x180001392  jz      loc_18000146A
0x180001398  lea     rax, ??_7CDAOClassFactory@@6B@; const CDAOClassFactory::`vftable'
0x18000139f  mov     [rbx], rax
0x1800013a2  lea     rax, ??_7CDAOGroupCF@@6B@; const CDAOGroupCF::`vftable'
0x1800013a9  jmp     loc_180001457
0x1800013ae  call    sub_180003ED8
0x1800013b3  mov     rbx, rax
0x1800013b6  test    rax, rax
0x1800013b9  jz      loc_18000146A
0x1800013bf  lea     rax, ??_7CDAOClassFactory@@6B@; const CDAOClassFactory::`vftable'
0x1800013c6  mov     [rbx], rax
0x1800013c9  lea     rax, ??_7CDAOIndexCF@@6B@; const CDAOIndexCF::`vftable'
0x1800013d0  jmp     loc_180001457
0x1800013d5  call    sub_180003ED8
0x1800013da  mov     rbx, rax
0x1800013dd  test    rax, rax
0x1800013e0  jz      loc_18000146A
0x1800013e6  lea     rax, ??_7CDAOClassFactory@@6B@; const CDAOClassFactory::`vftable'
0x1800013ed  mov     [rbx], rax
0x1800013f0  lea     rax, ??_7CDAOFieldCF@@6B@; const CDAOFieldCF::`vftable'
0x1800013f7  jmp     short loc_180001457
0x1800013f9  call    sub_180003ED8
0x1800013fe  mov     rbx, rax
0x180001401  test    rax, rax
0x180001404  jz      short loc_18000146A
0x180001406  lea     rax, ??_7CDAOClassFactory@@6B@; const CDAOClassFactory::`vftable'
0x18000140d  mov     [rbx], rax
0x180001410  lea     rax, ??_7CDAOQueryDefCF@@6B@; const CDAOQueryDefCF::`vftable'
0x180001417  jmp     short loc_180001457
0x180001419  call    sub_180003ED8
0x18000141e  mov     rbx, rax
0x180001421  test    rax, rax
0x180001424  jz      short loc_18000146A
0x180001426  lea     rax, ??_7CDAOClassFactory@@6B@; const CDAOClassFactory::`vftable'
0x18000142d  mov     [rbx], rax
0x180001430  lea     rax, ??_7CDAOTableDefCF@@6B@; const CDAOTableDefCF::`vftable'
0x180001437  jmp     short loc_180001457
0x180001439  call    sub_180003ED8
0x18000143e  mov     rbx, rax
0x180001441  test    rax, rax
0x180001444  jz      short loc_18000146A
0x180001446  lea     rax, ??_7CDAOClassFactory@@6B@; const CDAOClassFactory::`vftable'
0x18000144d  mov     [rbx], rax
0x180001450  lea     rax, ??_7CDAODBEngineCF@@6B@; const CDAODBEngineCF::`vftable'
0x180001457  mov     dword ptr [rbx+8], 1
0x18000145e  lock inc cs:dword_1800B20C8
0x180001465  mov     [rbx], rax
0x180001468  jmp     short loc_18000146C
0x18000146a  xor     ebx, ebx
0x18000146c  test    rbx, rbx
0x18000146f  jnz     short loc_180001478
0x180001471  mov     edi, 8007000Eh
0x180001476  jmp     short loc_1800014B8
0x180001478  mov     rax, [rbx]
0x18000147b  mov     r8, rsi
0x18000147e  mov     rdx, r14
0x180001481  mov     rcx, rbx
0x180001484  mov     rax, [rax]
0x180001487  call    cs:__guard_dispatch_icall_fptr
0x18000148d  mov     edi, eax
0x18000148f  mov     rax, [rbx]
0x180001492  mov     rcx, rbx
0x180001495  mov     rax, [rax+10h]
0x180001499  call    cs:__guard_dispatch_icall_fptr
0x18000149f  call    sub_180074278
0x1800014a4  test    al, al
0x1800014a6  jz      short loc_1800014B8
0x1800014a8  test    edi, edi
0x1800014aa  js      short loc_1800014B8
0x1800014ac  mov     rdx, rsi
0x1800014af  mov     rcx, r14
0x1800014b2  call    sub_180074B20
0x1800014b7  nop
0x1800014b8  cmp     [rbp+arg_10], 0
0x1800014bc  jz      short loc_1800014CC
0x1800014be  mov     rax, cs:DisableVirtualizationOnThread
0x1800014c5  call    cs:__guard_dispatch_icall_fptr
0x1800014cb  nop
0x1800014cc  mov     eax, edi
0x1800014ce  mov     rbx, [rsp+40h+arg_0]
0x1800014d3  mov     rsi, [rsp+40h+arg_8]
0x1800014d8  add     rsp, 40h
0x1800014dc  pop     r14
0x1800014de  pop     rdi
0x1800014df  pop     rbp
0x1800014e0  retn
```
