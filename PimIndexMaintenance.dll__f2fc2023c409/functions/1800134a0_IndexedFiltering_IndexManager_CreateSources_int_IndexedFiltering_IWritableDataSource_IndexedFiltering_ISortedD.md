# IndexedFiltering::IndexManager::CreateSources(int,IndexedFiltering::IWritableDataSource *,IndexedFiltering::ISortedDataSource * *,IndexedFiltering::_IndexSourceData const *,uint)

- ea: `0x1800134a0`
- end: `0x18001366f`
- name: `?CreateSources@IndexManager@IndexedFiltering@@MEAAJHPEAUIWritableDataSource@2@PEAPEAUISortedDataSource@2@PEBU_IndexSourceData@2@I@Z`
- size: `463`
- prototype: `__int64 __fastcall(IndexedFiltering::IndexManager *this, int, struct IUnknown *, struct IndexedFiltering::ISortedDataSource **, const struct IndexedFiltering::_IndexSourceData *, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002da8`
- `0x18000502c`
- `0x1800086a0`
- `0x1800134a0`
- `0x180016db0`
- `0x18001be30`
- `0x180021240`

## string_xrefs

- `0x1800134ef`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexmanager.cpp`
- `0x18001362b`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexmanager.cpp`

## pseudocode

```c
__int64 __fastcall IndexedFiltering::IndexManager::CreateSources(
        IndexedFiltering::IndexManager *this,
        int a2,
        struct IUnknown *a3,
        struct IndexedFiltering::ISortedDataSource **a4,
        const struct IndexedFiltering::_IndexSourceData *a5,
        unsigned int a6)
{
  __int64 i; // rdi
  struct IUnknown *v11; // rdx
  __int64 v12; // rax
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  int IndexSource; // eax
  unsigned int v26; // esi
  __int64 v28; // [rsp+20h] [rbp-E0h]
  _OWORD v29[3]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int128 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+90h] [rbp-70h]
  __int128 v33; // [rsp+A0h] [rbp-60h]
  __int128 v34; // [rsp+B0h] [rbp-50h]
  __int128 v35; // [rsp+C0h] [rbp-40h]
  __int128 v36; // [rsp+D0h] [rbp-30h]
  __int128 v37; // [rsp+E0h] [rbp-20h]
  __int128 v38; // [rsp+F0h] [rbp-10h]
  __int128 v39; // [rsp+100h] [rbp+0h]

  if ( !a6 )
    Log_AssertionEvent(
      this,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexmanager.cpp",
      777);
  if ( *((struct IUnknown **)this + 3) != a3 )
    ATL::AtlComPtrAssign((struct IUnknown **)this + 3, a3);
  for ( i = 0; (unsigned int)i < a6; i = (unsigned int)(i + 1) )
  {
    v11 = (struct IUnknown *)a4[i];
    v12 = 208LL * (unsigned int)i;
    v13 = *(_OWORD *)((char *)a5 + v12 + 16);
    v29[0] = *(_OWORD *)((char *)a5 + v12);
    v14 = *(_OWORD *)((char *)a5 + v12 + 32);
    v29[1] = v13;
    v15 = *(_OWORD *)((char *)a5 + v12 + 48);
    v29[2] = v14;
    v16 = *(_OWORD *)((char *)a5 + v12 + 64);
    v30 = v15;
    v17 = *(_OWORD *)((char *)a5 + v12 + 80);
    v31 = v16;
    v18 = *(_OWORD *)((char *)a5 + v12 + 96);
    v32 = v17;
    v19 = *(_OWORD *)((char *)a5 + v12 + 112);
    v33 = v18;
    v20 = *(_OWORD *)((char *)a5 + v12 + 128);
    v34 = v19;
    v21 = *(_OWORD *)((char *)a5 + v12 + 144);
    v35 = v20;
    v22 = *(_OWORD *)((char *)a5 + v12 + 160);
    v36 = v21;
    v23 = *(_OWORD *)((char *)a5 + v12 + 176);
    v37 = v22;
    v24 = *(_OWORD *)((char *)a5 + v12 + 192);
    v38 = v23;
    v39 = v24;
    if ( *((struct IUnknown **)this + i + 4) != v11 )
      ATL::AtlComPtrAssign((struct IUnknown **)this + i + 4, v11);
    LODWORD(v28) = DWORD1(v39);
    IndexSource = IndexedFiltering::CreateIndexSource(
                    DWORD2(v39),
                    *((_QWORD *)this + i + 4),
                    (__int64)v29 + 8,
                    DWORD2(v30),
                    v28,
                    *((_QWORD *)this + 15),
                    (__int64 *)this + i + 9);
    v26 = IndexSource;
    if ( IndexSource < 0 )
    {
      Log_HREvent(
        (unsigned int)IndexSource,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexmanager.cpp",
        794);
      return v26;
    }
    if ( a2 )
      ESESession::DeleteTable(*((_QWORD *)this + 15), DWORD2(v39), 1);
  }
  *((_DWORD *)this + 28) = a6;
  return 0;
}

```

## disassembly

```asm
0x1800134a0  mov     [rsp-8+arg_8], rbx
0x1800134a5  push    rbp
0x1800134a6  push    rsi
0x1800134a7  push    rdi
0x1800134a8  push    r12
0x1800134aa  push    r13
0x1800134ac  push    r14
0x1800134ae  push    r15
0x1800134b0  lea     rbp, [rsp-20h]
0x1800134b5  sub     rsp, 120h
0x1800134bc  mov     rax, cs:__security_cookie
0x1800134c3  xor     rax, rsp
0x1800134c6  mov     [rbp+50h+var_40], rax
0x1800134ca  mov     r14d, [rbp+50h+arg_28]
0x1800134d1  mov     r13, r9
0x1800134d4  mov     r15, [rbp+50h+arg_20]
0x1800134db  mov     rdi, r8
0x1800134de  mov     r12d, edx
0x1800134e1  mov     rbx, rcx
0x1800134e4  test    r14d, r14d
0x1800134e7  jnz     short loc_1800134FB
0x1800134e9  mov     r8d, 309h
0x1800134ef  lea     rdx, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800134f6  call    Log_AssertionEvent
0x1800134fb  lea     rcx, [rbx+18h]; struct IUnknown **
0x1800134ff  cmp     [rcx], rdi
0x180013502  jz      short loc_18001350C
0x180013504  mov     rdx, rdi; struct IUnknown *
0x180013507  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18001350c  xor     edi, edi
0x18001350e  cmp     edi, r14d
0x180013511  jnb     loc_180013642
0x180013517  mov     rdx, [r13+rdi*8+0]; struct IUnknown *
0x18001351c  mov     esi, edi
0x18001351e  imul    rax, rsi, 0D0h
0x180013525  movups  xmm0, xmmword ptr [rax+r15]
0x18001352a  movups  xmm1, xmmword ptr [rax+r15+10h]
0x180013530  movups  [rsp+150h+var_110], xmm0
0x180013535  movups  xmm0, xmmword ptr [rax+r15+20h]
0x18001353b  movups  [rsp+150h+var_100], xmm1
0x180013540  movups  xmm1, xmmword ptr [rax+r15+30h]
0x180013546  movups  [rsp+150h+var_F0], xmm0
0x18001354b  movups  xmm0, xmmword ptr [rax+r15+40h]
0x180013551  movups  [rsp+150h+var_E0], xmm1
0x180013556  movups  xmm1, xmmword ptr [rax+r15+50h]
0x18001355c  movups  [rbp+50h+var_D0], xmm0
0x180013560  movups  xmm0, xmmword ptr [rax+r15+60h]
0x180013566  movups  [rbp+50h+var_C0], xmm1
0x18001356a  movups  xmm1, xmmword ptr [rax+r15+70h]
0x180013570  movups  [rbp+50h+var_B0], xmm0
0x180013574  movups  xmm0, xmmword ptr [rax+r15+80h]
0x18001357d  movups  [rbp+50h+var_A0], xmm1
0x180013581  movups  xmm1, xmmword ptr [rax+r15+90h]
0x18001358a  movups  [rbp+50h+var_90], xmm0
0x18001358e  movups  xmm0, xmmword ptr [rax+r15+0A0h]
0x180013597  movups  [rbp+50h+var_80], xmm1
0x18001359b  movups  xmm1, xmmword ptr [rax+r15+0B0h]
0x1800135a4  movups  [rbp+50h+var_70], xmm0
0x1800135a8  movups  xmm0, xmmword ptr [rax+r15+0C0h]
0x1800135b1  movups  [rbp+50h+var_60], xmm1
0x1800135b5  movups  [rbp+50h+var_50], xmm0
0x1800135b9  cmp     [rbx+rdi*8+20h], rdx
0x1800135be  jz      short loc_1800135CD
0x1800135c0  lea     rcx, [rbx+20h]
0x1800135c4  lea     rcx, [rcx+rdi*8]; struct IUnknown **
0x1800135c8  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800135cd  mov     r9d, dword ptr [rsp+150h+var_E0+8]
0x1800135d2  lea     rax, [rbx+48h]
0x1800135d6  mov     rdx, [rbx+rdi*8+20h]
0x1800135db  lea     rax, [rax+rdi*8]
0x1800135df  mov     ecx, dword ptr [rbp+50h+var_50+8]
0x1800135e2  lea     r8, [rsp+150h+var_110+8]
0x1800135e7  mov     [rsp+150h+var_120], rax
0x1800135ec  mov     rax, [rbx+78h]
0x1800135f0  mov     [rsp+150h+var_128], rax
0x1800135f5  mov     eax, dword ptr [rbp+50h+var_50+4]
0x1800135f8  mov     dword ptr [rsp+150h+var_130], eax
0x1800135fc  call    ?CreateIndexSource@IndexedFiltering@@YAJW4_INDEXTABLE_ID@@PEAUISortedDataSource@1@PEAKIKPEAVESESession@@PEAPEAUIIndexSource@1@@Z; IndexedFiltering::CreateIndexSource(_INDEXTABLE_ID,IndexedFiltering::ISortedDataSource *,ulong *,uint,ulong,ESESession *,IndexedFiltering::IIndexSource * *)
0x180013601  mov     esi, eax
0x180013603  test    eax, eax
0x180013605  js      short loc_180013625
0x180013607  test    r12d, r12d
0x18001360a  jz      short loc_18001361E
0x18001360c  mov     edx, dword ptr [rbp+50h+var_50+8]
0x18001360f  mov     r8d, 1
0x180013615  mov     rcx, [rbx+78h]
0x180013619  call    ?DeleteTable@ESESession@@QEAAJW4_INDEXTABLE_ID@@H@Z; ESESession::DeleteTable(_INDEXTABLE_ID,int)
0x18001361e  inc     edi
0x180013620  jmp     loc_18001350E
0x180013625  mov     r9d, 31Ah
0x18001362b  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180013632  mov     edx, 1
0x180013637  mov     ecx, esi
0x180013639  call    Log_HREvent
0x18001363e  mov     eax, esi
0x180013640  jmp     short loc_180013648
0x180013642  mov     [rbx+70h], r14d
0x180013646  xor     eax, eax
0x180013648  mov     rcx, [rbp+50h+var_40]
0x18001364c  xor     rcx, rsp; StackCookie
0x18001364f  call    __security_check_cookie
0x180013654  mov     rbx, [rsp+150h+arg_8]
0x18001365c  add     rsp, 120h
0x180013663  pop     r15
0x180013665  pop     r14
0x180013667  pop     r13
0x180013669  pop     r12
0x18001366b  pop     rdi
0x18001366c  pop     rsi
0x18001366d  pop     rbp
0x18001366e  retn
```
