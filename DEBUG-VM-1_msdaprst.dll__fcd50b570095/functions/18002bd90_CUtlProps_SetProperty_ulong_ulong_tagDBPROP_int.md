# CUtlProps::SetProperty(ulong,ulong,tagDBPROP *,int)

- ea: `0x18002bd90`
- end: `0x18002bfc2`
- name: `?SetProperty@CUtlProps@@AEAAXKKPEAUtagDBPROP@@H@Z`
- size: `562`
- prototype: `void(CUtlProps *__hidden this, unsigned int, unsigned int, struct tagDBPROP *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18002c118`

## callees

- `0x180001d94`
- `0x1800027c0`
- `0x18001a6c8`
- `0x180029f10`
- `0x180029fc0`
- `0x18002a248`
- `0x18002bd90`
- `0x18002cd54`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x18002bed3`
- `OLEAUT32!__imp_VariantCopy` at `0x18002bf72`
- `OLEAUT32!__imp_VariantCopy` at `0x18002bed3`
- `OLEAUT32!__imp_VariantCopy` at `0x18002bf72`

## pseudocode

```c
void __fastcall CUtlProps::SetProperty(CUtlProps *this, unsigned int a2, unsigned int a3, struct tagDBPROP *a4)
{
  __int64 v4; // rbx
  __int64 v5; // r15
  __int64 v8; // rbp
  unsigned int v9; // r10d
  __int64 v10; // r11
  unsigned int v11; // r9d
  __int64 v12; // rdx
  const struct tagDBID *v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rbx
  int v16; // eax
  CColumnIds *v17; // rcx
  unsigned int v18; // edx
  CColumnIds *v19; // rcx
  HRESULT v20; // eax
  int v21; // ebx
  unsigned __int8 *v22; // rax
  HRESULT v23; // eax
  int v24; // ebx

  v4 = *((_QWORD *)this + 3);
  v5 = a2;
  *((_DWORD *)this + 20) = 1;
  v8 = a3;
  v9 = 0;
  v10 = 3LL * a2;
  v11 = *(_DWORD *)(v4 + 24LL * a2);
  if ( v11 )
  {
    v12 = *(_QWORD *)(v4 + 24LL * a2 + 8);
    while ( **(_DWORD **)(v12 + 8LL * v9) != a4->dwPropertyID )
    {
      if ( ++v9 >= v11 )
        goto LABEL_5;
    }
  }
  else
  {
LABEL_5:
    if ( v9 >= v11 )
    {
      a4->dwStatus = 1;
      ThrowHR(-2147467259);
    }
  }
  v13 = (const struct tagDBID *)(5 * v5);
  v14 = *(_QWORD *)(*((_QWORD *)this + 2) + 40 * v5 + 16);
  v15 = 48LL * v9 + *(_QWORD *)(v4 + 8 * v10 + 16);
  *(_DWORD *)(v15 + 40) = (a4->dwOptions != 0) + 1;
  v16 = *(_DWORD *)(v14 + 24 * v8 + 8) & 0x100;
  if ( a4->vValue.vt )
  {
    if ( v16 )
    {
      if ( CompareDBIDs(&a4->colid, v13) == 1 )
      {
        v19 = *(CColumnIds **)(v15 + 8);
        if ( v19 )
          CColumnIds::`scalar deleting destructor'(v19, v18);
        *(_QWORD *)(v15 + 8) = 0;
        *(_DWORD *)v15 = a4->dwOptions;
        v20 = VariantCopy((VARIANTARG *)(v15 + 16), &a4->vValue);
        v21 = v20;
        if ( v20 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180048EB0[0] )
            bidTraceW(off_180048220, 2257920, off_180048EB0[0], (unsigned int)v20, 2205);
          ThrowHR(v21);
        }
      }
      else
      {
        if ( !*(_QWORD *)(v15 + 8) )
        {
          v22 = MMMAlloc(0x18u, v18);
          if ( v22 )
          {
            *(_QWORD *)v22 = 0;
            *((_QWORD *)v22 + 1) = 0;
            *((_DWORD *)v22 + 4) = 0;
          }
          else
          {
            v22 = 0;
          }
          *(_QWORD *)(v15 + 8) = v22;
          OnNullThrowOOM(v22);
        }
        CColumnIds::AddColumnId(*(CColumnIds **)(v15 + 8), a4);
      }
    }
    else
    {
      *(_DWORD *)v15 = a4->dwOptions;
      v23 = VariantCopy((VARIANTARG *)(v15 + 16), &a4->vValue);
      v24 = v23;
      if ( v23 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180048EB8[0] )
          bidTraceW(off_180048220, 2276352, off_180048EB8[0], (unsigned int)v23, 2223);
        ThrowHR(v24);
      }
    }
  }
  else
  {
    if ( v16 )
    {
      v17 = *(CColumnIds **)(v15 + 8);
      if ( v17 )
        CColumnIds::`scalar deleting destructor'(v17, (unsigned int)v13);
      *(_QWORD *)(v15 + 8) = 0;
    }
    (*(void (__fastcall **)(CUtlProps *, _QWORD, _QWORD, __int64, __int64))(*(_QWORD *)this + 40LL))(
      this,
      (unsigned int)v5,
      a4->dwPropertyID,
      v15,
      v15 + 16);
  }
}

```

## disassembly

```asm
0x18002bd90  mov     [rsp+arg_8], rbx
0x18002bd95  mov     [rsp+arg_10], rbp
0x18002bd9a  push    rsi
0x18002bd9b  push    rdi
0x18002bd9c  push    r12
0x18002bd9e  push    r14
0x18002bda0  push    r15
0x18002bda2  sub     rsp, 30h
0x18002bda6  mov     rbx, [rcx+18h]
0x18002bdaa  xor     r12d, r12d
0x18002bdad  mov     r15d, edx
0x18002bdb0  mov     rdi, r9
0x18002bdb3  mov     dword ptr [rcx+50h], 1
0x18002bdba  mov     rsi, rcx
0x18002bdbd  mov     ebp, r8d
0x18002bdc0  mov     r10d, r12d
0x18002bdc3  lea     r11, [r15+r15*2]
0x18002bdc7  mov     r9d, [rbx+r11*8]
0x18002bdcb  test    r9d, r9d
0x18002bdce  jz      short loc_18002BDEC
0x18002bdd0  mov     rdx, [rbx+r11*8+8]
0x18002bdd5  mov     r8d, [rdi]
0x18002bdd8  mov     eax, r10d
0x18002bddb  mov     rcx, [rdx+rax*8]
0x18002bddf  cmp     [rcx], r8d
0x18002bde2  jz      short loc_18002BE03
0x18002bde4  inc     r10d
0x18002bde7  cmp     r10d, r9d
0x18002bdea  jb      short loc_18002BDD8
0x18002bdec  cmp     r10d, r9d
0x18002bdef  jb      short loc_18002BE03
0x18002bdf1  mov     ecx, 80004005h; int
0x18002bdf6  mov     dword ptr [rdi+8], 1
0x18002bdfd  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18002be03  mov     rcx, [rsi+10h]
0x18002be07  lea     r9, ds:0[rbp*2]
0x18002be0f  mov     rbx, [rbx+r11*8+10h]
0x18002be14  lea     rdx, [r15+r15*4]; struct tagDBID *
0x18002be18  add     r9, rbp
0x18002be1b  mov     eax, r10d
0x18002be1e  lea     rbp, [rdi+30h]
0x18002be22  mov     r8, [rcx+rdx*8+10h]
0x18002be27  lea     rcx, [rax+rax*2]
0x18002be2b  mov     eax, [rdi+4]
0x18002be2e  shl     rcx, 4
0x18002be32  add     rbx, rcx
0x18002be35  neg     eax
0x18002be37  sbb     ecx, ecx
0x18002be39  neg     ecx
0x18002be3b  inc     ecx
0x18002be3d  mov     [rbx+28h], ecx
0x18002be40  mov     eax, [r8+r9*8+8]
0x18002be45  and     eax, 100h
0x18002be4a  cmp     [rbp+0], r12w
0x18002be4f  jnz     short loc_18002BE9F
0x18002be51  test    eax, eax
0x18002be53  jz      short loc_18002BE67
0x18002be55  mov     rcx, [rbx+8]; this
0x18002be59  test    rcx, rcx
0x18002be5c  jz      short loc_18002BE63
0x18002be5e  call    ??_GCColumnIds@@QEAAPEAXI@Z; CColumnIds::`scalar deleting destructor'(uint)
0x18002be63  mov     [rbx+8], r12
0x18002be67  mov     rax, [rsi]
0x18002be6a  lea     rcx, [rbx+10h]
0x18002be6e  mov     r8d, [rdi]
0x18002be71  mov     r9, rbx
0x18002be74  mov     [rsp+58h+var_38], rcx
0x18002be79  mov     edx, r15d
0x18002be7c  mov     rcx, rsi
0x18002be7f  mov     rax, [rax+28h]
0x18002be83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be88  mov     rbx, [rsp+58h+arg_8]
0x18002be8d  mov     rbp, [rsp+58h+arg_10]
0x18002be92  add     rsp, 30h
0x18002be96  pop     r15
0x18002be98  pop     r14
0x18002be9a  pop     r12
0x18002be9c  pop     rdi
0x18002be9d  pop     rsi
0x18002be9e  retn
0x18002be9f  test    eax, eax
0x18002bea1  jz      loc_18002BF66
0x18002bea7  lea     rcx, [rdi+10h]; struct tagDBID *
0x18002beab  call    ?CompareDBIDs@@YAKPEBUtagDBID@@0@Z; CompareDBIDs(tagDBID const *,tagDBID const *)
0x18002beb0  cmp     eax, 1
0x18002beb3  jnz     short loc_18002BF1F
0x18002beb5  mov     rcx, [rbx+8]; this
0x18002beb9  test    rcx, rcx
0x18002bebc  jz      short loc_18002BEC3
0x18002bebe  call    ??_GCColumnIds@@QEAAPEAXI@Z; CColumnIds::`scalar deleting destructor'(uint)
0x18002bec3  mov     [rbx+8], r12
0x18002bec7  lea     rcx, [rbx+10h]; pvargDest
0x18002becb  mov     eax, [rdi+4]
0x18002bece  mov     rdx, rbp; pvargSrc
0x18002bed1  mov     [rbx], eax
0x18002bed3  call    cs:__imp_VariantCopy
0x18002bed9  mov     ebx, eax
0x18002bedb  test    eax, eax
0x18002bedd  jns     short loc_18002BE88
0x18002bedf  test    byte ptr cs:_bidGblFlags, 2
0x18002bee6  jz      short loc_18002BF17
0x18002bee8  mov     rcx, cs:off_180048EB0; "<CUtlProps::SetProperty|ADO|ERR>  HRESU"...
0x18002beef  test    rcx, rcx
0x18002bef2  jz      short loc_18002BF17
0x18002bef4  mov     r8, cs:off_180048EB0; "<CUtlProps::SetProperty|ADO|ERR>  HRESU"...
0x18002befb  mov     r9d, eax
0x18002befe  mov     rcx, cs:off_180048220; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18002bf05  mov     edx, 227400h
0x18002bf0a  mov     dword ptr [rsp+58h+var_38], 89Dh
0x18002bf12  call    _bidTraceW
0x18002bf17  mov     ecx, ebx; int
0x18002bf19  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18002bf1f  cmp     [rbx+8], r12
0x18002bf23  jnz     short loc_18002BF55
0x18002bf25  mov     ecx, 18h; unsigned int
0x18002bf2a  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18002bf2f  mov     [rsp+58h+arg_0], rax
0x18002bf34  test    rax, rax
0x18002bf37  jz      short loc_18002BF46
0x18002bf39  mov     [rax], r12
0x18002bf3c  mov     [rax+8], r12
0x18002bf40  mov     [rax+10h], r12d
0x18002bf44  jmp     short loc_18002BF49
0x18002bf46  mov     rax, r12
0x18002bf49  mov     rcx, rax; void *
0x18002bf4c  mov     [rbx+8], rax
0x18002bf50  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x18002bf55  mov     rcx, [rbx+8]; this
0x18002bf59  mov     rdx, rdi; struct tagDBPROP *
0x18002bf5c  call    ?AddColumnId@CColumnIds@@QEAAXPEAUtagDBPROP@@@Z; CColumnIds::AddColumnId(tagDBPROP *)
0x18002bf61  jmp     loc_18002BE88
0x18002bf66  mov     eax, [rdi+4]
0x18002bf69  lea     rcx, [rbx+10h]; pvargDest
0x18002bf6d  mov     rdx, rbp; pvargSrc
0x18002bf70  mov     [rbx], eax
0x18002bf72  call    cs:__imp_VariantCopy
0x18002bf78  mov     ebx, eax
0x18002bf7a  test    eax, eax
0x18002bf7c  jns     loc_18002BE88
0x18002bf82  test    byte ptr cs:_bidGblFlags, 2
0x18002bf89  jz      short loc_18002BFBA
0x18002bf8b  mov     rcx, cs:off_180048EB8; "<CUtlProps::SetProperty|ADO|ERR>  HRESU"...
0x18002bf92  test    rcx, rcx
0x18002bf95  jz      short loc_18002BFBA
0x18002bf97  mov     r8, cs:off_180048EB8; "<CUtlProps::SetProperty|ADO|ERR>  HRESU"...
0x18002bf9e  mov     r9d, eax
0x18002bfa1  mov     rcx, cs:off_180048220; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18002bfa8  mov     edx, 22BC00h
0x18002bfad  mov     dword ptr [rsp+58h+var_38], 8AFh
0x18002bfb5  call    _bidTraceW
0x18002bfba  mov     ecx, ebx; int
0x18002bfbc  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
```
