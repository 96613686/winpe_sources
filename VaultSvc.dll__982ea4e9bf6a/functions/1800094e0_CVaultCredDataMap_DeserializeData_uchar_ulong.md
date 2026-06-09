# CVaultCredDataMap::DeserializeData(uchar *,ulong)

- ea: `0x1800094e0`
- end: `0x180009a00`
- name: `?DeserializeData@CVaultCredDataMap@@QEAAKPEAEK@Z`
- size: `1312`
- prototype: `__int64 __fastcall(CVaultCredDataMap *this, unsigned __int8 *, unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180008050`
- `0x1800256b0`
- `0x1800495c0`

## callees

- `0x1800094e0`
- `0x180009a08`
- `0x180037e58`
- `0x18003bb9c`
- `0x18004b43c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800095cb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800095cb`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800099a4`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800099a4`

## pseudocode

```c
__int64 __fastcall CVaultCredDataMap::DeserializeData(CVaultCredDataMap *this, unsigned __int8 *a2, unsigned int a3)
{
  CVaultCredDataMap *v3; // r11
  int v4; // eax
  int v5; // eax
  unsigned __int8 *v6; // r12
  unsigned int v7; // r15d
  unsigned int i; // eax
  int v9; // edi
  __int64 v10; // rbx
  HLOCAL v11; // rax
  HLOCAL v12; // rsi
  char *v13; // r13
  __int64 *v14; // rdx
  __int64 *v15; // rax
  int v16; // r14d
  __int64 *v17; // rcx
  _QWORD *v18; // rsi
  _QWORD *v19; // rbx
  _QWORD *v20; // rax
  __int64 v21; // rcx
  __int64 v22; // r9
  __int64 v23; // r9
  __int64 v24; // r9
  __int64 v25; // r9
  _QWORD *v26; // r8
  __int64 *v27; // rcx
  __int64 *v28; // rdx
  __int64 *v29; // rax
  __int64 v30; // rax
  __int64 *v31; // rdx
  __int64 **v32; // rax
  _QWORD *v33; // rcx
  _QWORD *v34; // rdx
  __int64 v35; // rax
  _QWORD *v36; // rax
  __int64 v37; // rdx
  __int64 v38; // rax
  _QWORD *v39; // rax
  _QWORD *v40; // rax
  __int64 *v42; // [rsp+20h] [rbp-88h] BYREF
  __int128 v43; // [rsp+28h] [rbp-80h]
  char *v44; // [rsp+38h] [rbp-70h]
  __int64 v45; // [rsp+40h] [rbp-68h]
  int v46; // [rsp+48h] [rbp-60h] BYREF
  __int64 v47; // [rsp+50h] [rbp-58h]
  HLOCAL v48; // [rsp+58h] [rbp-50h]
  __int64 *v49; // [rsp+60h] [rbp-48h]
  int v50; // [rsp+6Ch] [rbp-3Ch]
  unsigned int v52; // [rsp+C8h] [rbp+20h]

  v3 = this;
  if ( *((_DWORD *)this + 4) != 1 )
    return 5023;
  if ( a3 < 4 )
    return 122;
  v4 = *(_DWORD *)a2;
  *((_DWORD *)this + 5) = *(_DWORD *)a2;
  if ( v4 != 1 )
    return 1392;
  if ( a3 - 4 < 4 )
    return 122;
  *(_DWORD *)this = *((_DWORD *)a2 + 1);
  if ( a3 - 8 < 4 )
    return 122;
  v5 = *((_DWORD *)a2 + 2);
  *((_DWORD *)this + 6) = v5;
  if ( (v5 & 0xFFFFFFFC) != 0 )
    return 1392;
  v6 = a2 + 12;
  v7 = a3 - 12;
  for ( i = 0; ; i = v52 + 1 )
  {
    v52 = i;
    if ( i >= *(_DWORD *)v3 )
      return 0;
    if ( v7 < 4 )
      return 122;
    v43 = 0;
    if ( v7 - 4 < 4 )
      return 122;
    v9 = *(_DWORD *)v6;
    v10 = *((unsigned int *)v6 + 1);
    LODWORD(v43) = v10;
    v7 -= 8;
    if ( (unsigned int)v10 > v7 )
      return 122;
    v6 += 8;
    if ( (_DWORD)v10 )
      break;
    v12 = (HLOCAL)*((_QWORD *)&v43 + 1);
LABEL_15:
    v46 = v9;
    v47 = v43;
    v48 = v12;
    v13 = (char *)v3 + 32;
    v14 = (__int64 *)*((_QWORD *)v3 + 4);
    v15 = (__int64 *)v14[1];
    v16 = 0;
    v50 = 0;
    v17 = v14;
    if ( *((_BYTE *)v15 + 25) )
    {
      v19 = v15;
      v18 = v15;
    }
    else
    {
      do
      {
        v18 = v15;
        v19 = v15;
        v49 = v15;
        if ( *((_DWORD *)v15 + 8) >= v9 )
        {
          v16 = 1;
          v17 = v15;
        }
        else
        {
          v16 = 0;
          v15 += 2;
        }
        v15 = (__int64 *)*v15;
      }
      while ( !*((_BYTE *)v15 + 25) );
    }
    if ( *((_BYTE *)v17 + 25) || v9 < *((_DWORD *)v17 + 8) )
    {
      if ( *((_QWORD *)v3 + 5) == 0x492492492492492LL )
        std::_Xlength_error("map/set too long");
      v42 = v14;
      v44 = (char *)v3 + 32;
      v45 = 0;
      v20 = std::_Allocate<16,std::_Default_allocate_traits>(0x38u);
      std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<enum VAULT_SCHEMA_ELEMENT_ID const,_VAULT_CAUB>,void *>>>::construct<std::pair<enum VAULT_SCHEMA_ELEMENT_ID const,_VAULT_CAUB>,std::pair<enum VAULT_SCHEMA_ELEMENT_ID,_VAULT_CAUB>>(
        v21,
        v20 + 4,
        &v46,
        v20,
        v42);
      std::_Construct_in_place<std::_Tree_node<std::pair<enum VAULT_SCHEMA_ELEMENT_ID const,_VAULT_CAUB>,void *> *,std::_Tree_node<std::pair<enum VAULT_SCHEMA_ELEMENT_ID const,_VAULT_CAUB>,void *> * &>(
        v22,
        &v42);
      std::_Construct_in_place<std::_Tree_node<std::pair<enum VAULT_SCHEMA_ELEMENT_ID const,_VAULT_CAUB>,void *> *,std::_Tree_node<std::pair<enum VAULT_SCHEMA_ELEMENT_ID const,_VAULT_CAUB>,void *> * &>(
        v23 + 8,
        &v42);
      std::_Construct_in_place<std::_Tree_node<std::pair<enum VAULT_SCHEMA_ELEMENT_ID const,_VAULT_CAUB>,void *> *,std::_Tree_node<std::pair<enum VAULT_SCHEMA_ELEMENT_ID const,_VAULT_CAUB>,void *> * &>(
        v24 + 16,
        &v42);
      *(_WORD *)(v25 + 24) = 0;
      v45 = 0;
      v3 = this;
      ++*((_QWORD *)this + 5);
      v26 = *(_QWORD **)v13;
      *(_QWORD *)(v25 + 8) = v18;
      if ( v19 != v26 )
      {
        if ( v16 )
        {
          *v18 = v25;
          if ( v19 == (_QWORD *)*v26 )
            *v26 = v25;
        }
        else
        {
          v18[2] = v25;
          if ( v19 == (_QWORD *)v26[2] )
            v26[2] = v25;
        }
        if ( *(_BYTE *)(*(_QWORD *)(v25 + 8) + 24LL) )
        {
LABEL_49:
          *(_BYTE *)(v26[1] + 24LL) = 1;
          continue;
        }
        while ( 2 )
        {
          v27 = *(__int64 **)(v25 + 8);
          v28 = (__int64 *)v27[1];
          v29 = (__int64 *)*v28;
          if ( v27 == (__int64 *)*v28 )
          {
            v30 = v28[2];
            if ( *(_BYTE *)(v30 + 24) )
            {
              v31 = (__int64 *)v27[2];
              if ( (__int64 *)v25 == v31 )
              {
                v25 = *(_QWORD *)(v25 + 8);
                v27[2] = *v31;
                if ( !*(_BYTE *)(*v31 + 25) )
                  *(_QWORD *)(*v31 + 8) = v27;
                v31[1] = v27[1];
                if ( v27 == *(__int64 **)(*(_QWORD *)v13 + 8LL) )
                {
                  *(_QWORD *)(*(_QWORD *)v13 + 8LL) = v31;
                }
                else
                {
                  v32 = (__int64 **)v27[1];
                  if ( v27 == *v32 )
                    *v32 = v31;
                  else
                    v32[2] = v31;
                }
                *v31 = (__int64)v27;
                v27[1] = (__int64)v31;
              }
              *(_BYTE *)(*(_QWORD *)(v25 + 8) + 24LL) = 1;
              *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v25 + 8) + 8LL) + 24LL) = 0;
              v33 = *(_QWORD **)(*(_QWORD *)(v25 + 8) + 8LL);
              v34 = (_QWORD *)*v33;
              *v33 = *(_QWORD *)(*v33 + 16LL);
              v35 = v34[2];
              if ( !*(_BYTE *)(v35 + 25) )
                *(_QWORD *)(v35 + 8) = v33;
              v34[1] = v33[1];
              if ( v33 == *(_QWORD **)(*(_QWORD *)v13 + 8LL) )
              {
                *(_QWORD *)(*(_QWORD *)v13 + 8LL) = v34;
                v34[2] = v33;
              }
              else
              {
                v36 = (_QWORD *)v33[1];
                if ( v33 == (_QWORD *)v36[2] )
                  v36[2] = v34;
                else
                  *v36 = v34;
                v34[2] = v33;
              }
              goto LABEL_47;
            }
            *((_BYTE *)v27 + 24) = 1;
            *(_BYTE *)(v30 + 24) = 1;
            *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v25 + 8) + 8LL) + 24LL) = 0;
            v25 = *(_QWORD *)(*(_QWORD *)(v25 + 8) + 8LL);
          }
          else if ( *((_BYTE *)v29 + 24) )
          {
            v37 = *v27;
            if ( v25 == *v27 )
            {
              v25 = *(_QWORD *)(v25 + 8);
              *v27 = *(_QWORD *)(v37 + 16);
              v38 = *(_QWORD *)(v37 + 16);
              if ( !*(_BYTE *)(v38 + 25) )
                *(_QWORD *)(v38 + 8) = v27;
              *(_QWORD *)(v37 + 8) = v27[1];
              if ( v27 == *(__int64 **)(*(_QWORD *)v13 + 8LL) )
              {
                *(_QWORD *)(*(_QWORD *)v13 + 8LL) = v37;
              }
              else
              {
                v39 = (_QWORD *)v27[1];
                if ( v27 == (__int64 *)v39[2] )
                  v39[2] = v37;
                else
                  *v39 = v37;
              }
              *(_QWORD *)(v37 + 16) = v27;
              v27[1] = v37;
            }
            *(_BYTE *)(*(_QWORD *)(v25 + 8) + 24LL) = 1;
            *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v25 + 8) + 8LL) + 24LL) = 0;
            v33 = *(_QWORD **)(*(_QWORD *)(v25 + 8) + 8LL);
            v34 = (_QWORD *)v33[2];
            v33[2] = *v34;
            if ( !*(_BYTE *)(*v34 + 25LL) )
              *(_QWORD *)(*v34 + 8LL) = v33;
            v34[1] = v33[1];
            if ( v33 == *(_QWORD **)(*(_QWORD *)v13 + 8LL) )
            {
              *(_QWORD *)(*(_QWORD *)v13 + 8LL) = v34;
            }
            else
            {
              v40 = (_QWORD *)v33[1];
              if ( v33 == (_QWORD *)*v40 )
                *v40 = v34;
              else
                v40[2] = v34;
            }
            *v34 = v33;
LABEL_47:
            v33[1] = v34;
          }
          else
          {
            *((_BYTE *)v27 + 24) = 1;
            *((_BYTE *)v29 + 24) = 1;
            *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v25 + 8) + 8LL) + 24LL) = 0;
            v25 = *(_QWORD *)(*(_QWORD *)(v25 + 8) + 8LL);
          }
          if ( *(_BYTE *)(*(_QWORD *)(v25 + 8) + 24LL) )
            goto LABEL_49;
          continue;
        }
      }
      *v26 = v25;
      v26[1] = v25;
      v26[2] = v25;
      *(_BYTE *)(v25 + 24) = 1;
    }
  }
  v11 = LocalAlloc(0x40u, (unsigned int)v10);
  v12 = v11;
  *((_QWORD *)&v43 + 1) = v11;
  if ( v11 )
  {
    memcpy_0(v11, v6, (unsigned int)v10);
    v6 += v10;
    v7 -= v10;
    v3 = this;
    goto LABEL_15;
  }
  return 14;
}

```

## disassembly

```asm
0x1800094e0  mov     [rsp+arg_8], rbx
0x1800094e5  mov     [rsp+arg_10], rsi
0x1800094ea  mov     [rsp+arg_0], rcx
0x1800094ef  push    rdi
0x1800094f0  push    r12
0x1800094f2  push    r13
0x1800094f4  push    r14
0x1800094f6  push    r15
0x1800094f8  sub     rsp, 80h
0x1800094ff  mov     r11, rcx
0x180009502  cmp     dword ptr [rcx+10h], 1
0x180009506  jnz     loc_180009993
0x18000950c  cmp     r8d, 4
0x180009510  jb      loc_180009989
0x180009516  mov     eax, [rdx]
0x180009518  mov     [rcx+14h], eax
0x18000951b  lea     r15d, [r8-4]
0x18000951f  cmp     eax, 1
0x180009522  jnz     loc_1800099F6
0x180009528  cmp     r15d, 4
0x18000952c  jb      loc_180009989
0x180009532  mov     eax, [rdx+4]
0x180009535  mov     [rcx], eax
0x180009537  add     r15d, 0FFFFFFFCh
0x18000953b  cmp     r15d, 4
0x18000953f  jb      loc_180009989
0x180009545  lea     r12, [rdx+8]
0x180009549  mov     eax, [r12]
0x18000954d  mov     [rcx+18h], eax
0x180009550  test    eax, 0FFFFFFFCh
0x180009555  jnz     loc_1800099F6
0x18000955b  add     r12, 4
0x18000955f  add     r15d, 0FFFFFFFCh
0x180009563  xor     eax, eax
0x180009565  mov     r8, 492492492492492h
0x18000956f  mov     [rsp+0A8h+arg_18], eax
0x180009576  cmp     eax, [r11]
0x180009579  jnb     loc_18000990D
0x18000957f  cmp     r15d, 4
0x180009583  jb      loc_180009989
0x180009589  lea     eax, [r15-4]
0x18000958d  xorps   xmm0, xmm0
0x180009590  movups  [rsp+0A8h+var_80], xmm0
0x180009595  cmp     eax, 4
0x180009598  jb      loc_180009989
0x18000959e  mov     edi, [r12]
0x1800095a2  mov     ebx, [r12+4]
0x1800095a7  mov     dword ptr [rsp+0A8h+var_80], ebx
0x1800095ab  lea     r15d, [rax-4]
0x1800095af  cmp     ebx, r15d
0x1800095b2  ja      loc_180009989
0x1800095b8  add     r12, 8
0x1800095bc  test    ebx, ebx
0x1800095be  jz      loc_18000997F
0x1800095c4  mov     edx, ebx; uBytes
0x1800095c6  mov     ecx, 40h ; '@'; uFlags
0x1800095cb  call    cs:__imp_LocalAlloc
0x1800095d1  mov     rsi, rax
0x1800095d4  mov     qword ptr [rsp+0A8h+var_80+8], rax
0x1800095d9  test    rax, rax
0x1800095dc  jz      loc_1800099EC
0x1800095e2  mov     r8d, ebx; Size
0x1800095e5  mov     rdx, r12; Src
0x1800095e8  mov     rcx, rax; void *
0x1800095eb  call    memcpy_0
0x1800095f0  add     r12, rbx
0x1800095f3  sub     r15d, ebx
0x1800095f6  mov     r11, [rsp+0A8h+arg_0]
0x1800095fe  mov     r8, 492492492492492h
0x180009608  mov     [rsp+0A8h+var_60], edi
0x18000960c  mov     rax, qword ptr [rsp+0A8h+var_80]
0x180009611  mov     [rsp+0A8h+var_58], rax
0x180009616  mov     [rsp+0A8h+var_50], rsi
0x18000961b  lea     r13, [r11+20h]
0x18000961f  mov     rdx, [r13+0]
0x180009623  mov     rax, [rdx+8]
0x180009627  xor     r14d, r14d
0x18000962a  xor     ecx, ecx
0x18000962c  mov     [rsp+0A8h+var_3C], ecx
0x180009630  mov     rcx, rdx
0x180009633  cmp     [rax+19h], r14b
0x180009637  jnz     short loc_18000967D
0x180009639  mov     rsi, rax
0x18000963c  mov     rbx, rax
0x18000963f  mov     [rsp+0A8h+var_48], rax
0x180009644  cmp     [rax+20h], edi
0x180009647  jge     short loc_180009672
0x180009649  xor     r14d, r14d
0x18000964c  add     rax, 10h
0x180009650  mov     rax, [rax]
0x180009653  cmp     byte ptr [rax+19h], 0
0x180009657  jz      short loc_180009639
0x180009659  cmp     byte ptr [rcx+19h], 0
0x18000965d  jnz     short loc_180009685
0x18000965f  cmp     edi, [rcx+20h]
0x180009662  jl      short loc_180009685
0x180009664  mov     eax, [rsp+0A8h+arg_18]
0x18000966b  inc     eax
0x18000966d  jmp     loc_180009565
0x180009672  mov     r14d, 1
0x180009678  mov     rcx, rax
0x18000967b  jmp     short loc_180009650
0x18000967d  mov     rbx, rax
0x180009680  mov     rsi, rax
0x180009683  jmp     short loc_180009659
0x180009685  cmp     [r13+8], r8
0x180009689  jz      loc_18000999D
0x18000968f  mov     [rsp+0A8h+var_88], rdx
0x180009694  mov     [rsp+0A8h+var_70], r13
0x180009699  mov     [rsp+0A8h+var_68], 0
0x1800096a2  mov     ecx, 38h ; '8'
0x1800096a7  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800096ac  mov     r9, rax
0x1800096af  lea     rdx, [rax+20h]
0x1800096b3  lea     r8, [rsp+0A8h+var_60]
0x1800096b8  call    ??$construct@U?$pair@$$CBW4VAULT_SCHEMA_ELEMENT_ID@@U_VAULT_CAUB@@@std@@U?$pair@W4VAULT_SCHEMA_ELEMENT_ID@@U_VAULT_CAUB@@@2@@?$_Default_allocator_traits@V?$allocator@U?$_Tree_node@U?$pair@$$CBW4VAULT_SCHEMA_ELEMENT_ID@@U_VAULT_CAUB@@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBW4VAULT_SCHEMA_ELEMENT_ID@@U_VAULT_CAUB@@@std@@PEAX@std@@@1@QEAU?$pair@$$CBW4VAULT_SCHEMA_ELEMENT_ID@@U_VAULT_CAUB@@@1@$$QEAU?$pair@W4VAULT_SCHEMA_ELEMENT_ID@@U_VAULT_CAUB@@@1@@Z; std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<VAULT_SCHEMA_ELEMENT_ID const,_VAULT_CAUB>,void *>>>::construct<std::pair<VAULT_SCHEMA_ELEMENT_ID const,_VAULT_CAUB>,std::pair<VAULT_SCHEMA_ELEMENT_ID,_VAULT_CAUB>>(std::allocator<std::_Tree_node<std::pair<VAULT_SCHEMA_ELEMENT_ID const,_VAULT_CAUB>,void *>> &,std::pair<VAULT_SCHEMA_ELEMENT_ID const,_VAULT_CAUB> * const,std::pair<VAULT_SCHEMA_ELEMENT_ID,_VAULT_CAUB> &&)
0x1800096bd  lea     rdx, [rsp+0A8h+var_88]
0x1800096c2  mov     rcx, r9
0x1800096c5  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CBW4VAULT_SCHEMA_ELEMENT_ID@@U_VAULT_CAUB@@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CBW4VAULT_SCHEMA_ELEMENT_ID@@U_VAULT_CAUB@@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<VAULT_SCHEMA_ELEMENT_ID const,_VAULT_CAUB>,void *> *,std::_Tree_node<std::pair<VAULT_SCHEMA_ELEMENT_ID const,_VAULT_CAUB>,void *> * &>(std::_Tree_node<std::pair<VAULT_SCHEMA_ELEMENT_ID const,_VAULT_CAUB>,void *> * &,std::_Tree_node<std::pair<VAULT_SCHEMA_ELEMENT_ID const,_VAULT_CAUB>,void *> * &)
0x1800096ca  lea     rdx, [rsp+0A8h+var_88]
0x1800096cf  lea     rcx, [r9+8]
0x1800096d3  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CBW4VAULT_SCHEMA_ELEMENT_ID@@U_VAULT_CAUB@@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CBW4VAULT_SCHEMA_ELEMENT_ID@@U_VAULT_CAUB@@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<VAULT_SCHEMA_ELEMENT_ID const,_VAULT_CAUB>,void *> *,std::_Tree_node<std::pair<VAULT_SCHEMA_ELEMENT_ID const,_VAULT_CAUB>,void *> * &>(std::_Tree_node<std::pair<VAULT_SCHEMA_ELEMENT_ID const,_VAULT_CAUB>,void *> * &,std::_Tree_node<std::pair<VAULT_SCHEMA_ELEMENT_ID const,_VAULT_CAUB>,void *> * &)
0x1800096d8  lea     rcx, [r9+10h]
0x1800096dc  lea     rdx, [rsp+0A8h+var_88]
0x1800096e1  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CBW4VAULT_SCHEMA_ELEMENT_ID@@U_VAULT_CAUB@@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CBW4VAULT_SCHEMA_ELEMENT_ID@@U_VAULT_CAUB@@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<VAULT_SCHEMA_ELEMENT_ID const,_VAULT_CAUB>,void *> *,std::_Tree_node<std::pair<VAULT_SCHEMA_ELEMENT_ID const,_VAULT_CAUB>,void *> * &>(std::_Tree_node<std::pair<VAULT_SCHEMA_ELEMENT_ID const,_VAULT_CAUB>,void *> * &,std::_Tree_node<std::pair<VAULT_SCHEMA_ELEMENT_ID const,_VAULT_CAUB>,void *> * &)
0x1800096e6  mov     word ptr [r9+18h], 0
0x1800096ed  mov     [rsp+0A8h+var_68], 0
0x1800096f6  mov     r11, [rsp+0A8h+arg_0]
0x1800096fe  inc     qword ptr [r11+28h]
0x180009702  mov     r8, [r13+0]
0x180009706  mov     [r9+8], rsi
0x18000970a  cmp     rbx, r8
0x18000970d  jz      loc_18000982E
0x180009713  test    r14d, r14d
0x180009716  jnz     loc_180009843
0x18000971c  mov     [rsi+10h], r9
0x180009720  cmp     rbx, [r8+10h]
0x180009724  jnz     short loc_18000972A
0x180009726  mov     [r8+10h], r9
0x18000972a  mov     rax, [r9+8]
0x18000972e  cmp     byte ptr [rax+18h], 0
0x180009732  jnz     loc_180009821
0x180009738  mov     rcx, [r9+8]
0x18000973c  mov     rdx, [rcx+8]
0x180009740  mov     rax, [rdx]
0x180009743  cmp     rcx, rax
0x180009746  jnz     loc_180009857
0x18000974c  mov     rax, [rdx+10h]
0x180009750  cmp     byte ptr [rax+18h], 0
0x180009754  jz      loc_1800099AA
0x18000975a  mov     rdx, [rcx+10h]
0x18000975e  cmp     r9, rdx
0x180009761  jnz     short loc_1800097A7
0x180009763  mov     r9, rcx
0x180009766  mov     rax, [rdx]
0x180009769  mov     [rcx+10h], rax
0x18000976d  mov     rax, [rdx]
0x180009770  cmp     byte ptr [rax+19h], 0
0x180009774  jnz     short loc_18000977A
0x180009776  mov     [rax+8], rcx
0x18000977a  mov     rax, [rcx+8]
0x18000977e  mov     [rdx+8], rax
0x180009782  mov     rax, [r13+0]
0x180009786  cmp     rcx, [rax+8]
0x18000978a  jz      loc_18000992C
0x180009790  mov     rax, [rcx+8]
0x180009794  cmp     rcx, [rax]
0x180009797  jnz     loc_180009935
0x18000979d  mov     [rax], rdx
0x1800097a0  mov     [rdx], rcx
0x1800097a3  mov     [rcx+8], rdx
0x1800097a7  mov     rax, [r9+8]
0x1800097ab  mov     byte ptr [rax+18h], 1
0x1800097af  mov     rax, [r9+8]
0x1800097b3  mov     rcx, [rax+8]
0x1800097b7  mov     byte ptr [rcx+18h], 0
0x1800097bb  mov     rax, [r9+8]
0x1800097bf  mov     rcx, [rax+8]
0x1800097c3  mov     rdx, [rcx]
0x1800097c6  mov     rax, [rdx+10h]
0x1800097ca  mov     [rcx], rax
0x1800097cd  mov     rax, [rdx+10h]
0x1800097d1  cmp     byte ptr [rax+19h], 0
0x1800097d5  jz      loc_180009947
0x1800097db  mov     rax, [rcx+8]
0x1800097df  mov     [rdx+8], rax
0x1800097e3  mov     rax, [r13+0]
0x1800097e7  cmp     rcx, [rax+8]
0x1800097eb  jz      loc_180009950
0x1800097f1  mov     rax, [rcx+8]
0x1800097f5  cmp     rcx, [rax+10h]
0x1800097f9  jnz     loc_18000995D
0x1800097ff  mov     [rax+10h], rdx
0x180009803  mov     [rdx+10h], rcx
0x180009807  jmp     short loc_18000980F
0x180009809  mov     [rax], rdx
0x18000980c  mov     [rdx], rcx
0x18000980f  mov     [rcx+8], rdx
0x180009813  mov     rax, [r9+8]
0x180009817  cmp     byte ptr [rax+18h], 0
0x18000981b  jz      loc_180009738
0x180009821  mov     rax, [r8+8]
0x180009825  mov     byte ptr [rax+18h], 1
0x180009829  jmp     loc_180009664
0x18000982e  mov     [r8], r9
0x180009831  mov     [r8+8], r9
0x180009835  mov     [r8+10h], r9
0x180009839  mov     byte ptr [r9+18h], 1
0x18000983e  jmp     loc_180009664
0x180009843  mov     [rsi], r9
0x180009846  cmp     rbx, [r8]
0x180009849  jnz     loc_18000972A
0x18000984f  mov     [r8], r9
0x180009852  jmp     loc_18000972A
0x180009857  cmp     byte ptr [rax+18h], 0
0x18000985b  jz      loc_1800099CB
0x180009861  mov     rdx, [rcx]
0x180009864  cmp     r9, rdx
0x180009867  jnz     short loc_1800098B1
0x180009869  mov     r9, rcx
0x18000986c  mov     rax, [rdx+10h]
0x180009870  mov     [rcx], rax
0x180009873  mov     rax, [rdx+10h]
0x180009877  cmp     byte ptr [rax+19h], 0
0x18000987b  jz      loc_180009965
0x180009881  mov     rax, [rcx+8]
0x180009885  mov     [rdx+8], rax
0x180009889  mov     rax, [r13+0]
0x18000988d  cmp     rcx, [rax+8]
0x180009891  jz      loc_18000996E
0x180009897  mov     rax, [rcx+8]
0x18000989b  cmp     rcx, [rax+10h]
0x18000989f  jnz     loc_180009977
0x1800098a5  mov     [rax+10h], rdx
0x1800098a9  mov     [rdx+10h], rcx
0x1800098ad  mov     [rcx+8], rdx
0x1800098b1  mov     rax, [r9+8]
0x1800098b5  mov     byte ptr [rax+18h], 1
0x1800098b9  mov     rax, [r9+8]
0x1800098bd  mov     rcx, [rax+8]
0x1800098c1  mov     byte ptr [rcx+18h], 0
0x1800098c5  mov     rax, [r9+8]
0x1800098c9  mov     rcx, [rax+8]
0x1800098cd  mov     rdx, [rcx+10h]
0x1800098d1  mov     rax, [rdx]
0x1800098d4  mov     [rcx+10h], rax
0x1800098d8  mov     rax, [rdx]
0x1800098db  cmp     byte ptr [rax+19h], 0
0x1800098df  jnz     short loc_1800098E5
0x1800098e1  mov     [rax+8], rcx
0x1800098e5  mov     rax, [rcx+8]
0x1800098e9  mov     [rdx+8], rax
0x1800098ed  mov     rax, [r13+0]
0x1800098f1  cmp     rcx, [rax+8]
0x1800098f5  jz      short loc_18000993E
0x1800098f7  mov     rax, [rcx+8]
0x1800098fb  cmp     rcx, [rax]
0x1800098fe  jz      loc_180009809
0x180009904  mov     [rax+10h], rdx
0x180009908  jmp     loc_18000980C
0x18000990d  xor     eax, eax
0x18000990f  lea     r11, [rsp+0A8h+var_28]
0x180009917  mov     rbx, [r11+38h]
0x18000991b  mov     rsi, [r11+40h]
0x18000991f  mov     rsp, r11
0x180009922  pop     r15
0x180009924  pop     r14
0x180009926  pop     r13
0x180009928  pop     r12
0x18000992a  pop     rdi
0x18000992b  retn
0x18000992c  mov     [rax+8], rdx
0x180009930  jmp     loc_1800097A0
0x180009935  mov     [rax+10h], rdx
0x180009939  jmp     loc_1800097A0
0x18000993e  mov     [rax+8], rdx
0x180009942  jmp     loc_18000980C
0x180009947  mov     [rax+8], rcx
0x18000994b  jmp     loc_1800097DB
0x180009950  mov     [rax+8], rdx
0x180009954  mov     [rdx+10h], rcx
0x180009958  jmp     loc_18000980F
0x18000995d  mov     [rax], rdx
0x180009960  jmp     loc_180009803
0x180009965  mov     [rax+8], rcx
0x180009969  jmp     loc_180009881
0x18000996e  mov     [rax+8], rdx
0x180009972  jmp     loc_1800098A9
0x180009977  mov     [rax], rdx
0x18000997a  jmp     loc_1800098A9
0x18000997f  mov     rsi, qword ptr [rsp+0A8h+var_80+8]
0x180009984  jmp     loc_180009608
0x180009989  mov     eax, 7Ah ; 'z'
0x18000998e  jmp     loc_18000990F
0x180009993  mov     eax, 139Fh
0x180009998  jmp     loc_18000990F
0x18000999d  lea     rcx, aMapSetTooLong; "map/set too long"
0x1800099a4  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800099aa  mov     byte ptr [rcx+18h], 1
0x1800099ae  mov     byte ptr [rax+18h], 1
  ... truncated ...
```
