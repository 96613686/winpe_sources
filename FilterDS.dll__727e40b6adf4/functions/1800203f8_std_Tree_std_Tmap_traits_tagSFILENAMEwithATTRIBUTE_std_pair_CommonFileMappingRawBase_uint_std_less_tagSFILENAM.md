# std::_Tree<std::_Tmap_traits<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>,std::less<tagSFILENAMEwithATTRIBUTE>,std::allocator<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>>,0>>::_Insert_at<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>> &,std::_Tree_node<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>,void *> *>(bool,std::_Tree_node<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>,void *> *,std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>> &,std::_Tree_node<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>,void *> *)

- ea: `0x1800203f8`
- end: `0x18002068c`
- name: `??$_Insert_at@AEAU?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@PEAU?$_Tree_node@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@U?$less@UtagSFILENAMEwithATTRIBUTE@@@3@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@3@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@std@@@std@@@1@_NPEAU?$_Tree_node@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@PEAX@1@AEAU?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@1@1@Z`
- size: `660`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, char, _QWORD *, int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180020694`

## callees

- `0x180001c00`
- `0x1800203f8`
- `0x1800210e0`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,unsigned int>,std::less<tagSFILENAMEwithATTRIBUTE>,std::allocator<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,unsigned int>>>,0>>::_Insert_at<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,unsigned int>> &,std::_Tree_node<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,unsigned int>>,void *> *>(
        __int64 a1,
        _QWORD *a2,
        char a3,
        _QWORD *a4,
        int a5,
        __int64 a6)
{
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 *v10; // rcx
  __int64 *v11; // r9
  __int64 *v12; // rax
  __int64 *v13; // r9
  __int64 **v14; // rax
  _QWORD *v15; // rcx
  _QWORD *v16; // r9
  __int64 v17; // rax
  _QWORD *v18; // rax
  __int64 v19; // r9
  __int64 v20; // rax
  _QWORD *v21; // rax
  _QWORD *v22; // rax
  __int64 v23; // rax
  __int64 v24; // rcx
  _QWORD *result; // rax

  if ( (unsigned __int64)qword_180030CE8 >= 0x2E8BA2E8BA2E8B9LL )
  {
    std::_Tree<std::_Tmap_traits<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,unsigned int>,std::less<tagSFILENAMEwithATTRIBUTE>,std::allocator<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,unsigned int>>>,0>>::_Destroy_if_not_nil(
      0x2E8BA2E8BA2E8B9LL,
      a6);
    std::_Xlength_error("map/set<T> too long");
  }
  ++qword_180030CE8;
  *(_QWORD *)(a6 + 8) = a4;
  if ( a4 == (_QWORD *)CommonFileMapping::m_mapSingleton )
  {
    *(_QWORD *)(CommonFileMapping::m_mapSingleton + 8) = a6;
    *(_QWORD *)CommonFileMapping::m_mapSingleton = a6;
    v7 = CommonFileMapping::m_mapSingleton;
LABEL_8:
    *(_QWORD *)(v7 + 16) = a6;
    goto LABEL_9;
  }
  if ( a3 )
  {
    *a4 = a6;
    if ( a4 == *(_QWORD **)CommonFileMapping::m_mapSingleton )
      *(_QWORD *)CommonFileMapping::m_mapSingleton = a6;
    goto LABEL_9;
  }
  a4[2] = a6;
  v7 = CommonFileMapping::m_mapSingleton;
  if ( a4 == *(_QWORD **)(CommonFileMapping::m_mapSingleton + 16) )
    goto LABEL_8;
LABEL_9:
  v8 = *(_QWORD *)(a6 + 8);
  v9 = a6;
  while ( !*(_BYTE *)(v8 + 24) )
  {
    v10 = *(__int64 **)(v9 + 8);
    v11 = (__int64 *)v10[1];
    v12 = (__int64 *)*v11;
    if ( v10 == (__int64 *)*v11 )
    {
      v12 = (__int64 *)v11[2];
      if ( !*((_BYTE *)v12 + 24) )
        goto LABEL_30;
      v13 = (__int64 *)v10[2];
      if ( (__int64 *)v9 == v13 )
      {
        v9 = *(_QWORD *)(v9 + 8);
        v10[2] = *v13;
        if ( !*(_BYTE *)(*v13 + 25) )
          *(_QWORD *)(*v13 + 8) = v10;
        v13[1] = v10[1];
        if ( v10 == *(__int64 **)(CommonFileMapping::m_mapSingleton + 8) )
        {
          *(_QWORD *)(CommonFileMapping::m_mapSingleton + 8) = v13;
        }
        else
        {
          v14 = (__int64 **)v10[1];
          if ( v10 == *v14 )
            *v14 = v13;
          else
            v14[2] = v13;
        }
        *v13 = (__int64)v10;
        v10[1] = (__int64)v13;
      }
      *(_BYTE *)(*(_QWORD *)(v9 + 8) + 24LL) = 1;
      *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v9 + 8) + 8LL) + 24LL) = 0;
      v15 = *(_QWORD **)(*(_QWORD *)(v9 + 8) + 8LL);
      v16 = (_QWORD *)*v15;
      *v15 = *(_QWORD *)(*v15 + 16LL);
      v17 = v16[2];
      if ( !*(_BYTE *)(v17 + 25) )
        *(_QWORD *)(v17 + 8) = v15;
      v16[1] = v15[1];
      if ( v15 == *(_QWORD **)(CommonFileMapping::m_mapSingleton + 8) )
      {
        *(_QWORD *)(CommonFileMapping::m_mapSingleton + 8) = v16;
      }
      else
      {
        v18 = (_QWORD *)v15[1];
        if ( v15 == (_QWORD *)v18[2] )
          v18[2] = v16;
        else
          *v18 = v16;
      }
      v16[2] = v15;
    }
    else
    {
      if ( !*((_BYTE *)v12 + 24) )
      {
LABEL_30:
        *((_BYTE *)v10 + 24) = 1;
        *((_BYTE *)v12 + 24) = 1;
        *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v9 + 8) + 8LL) + 24LL) = 0;
        v9 = *(_QWORD *)(*(_QWORD *)(v9 + 8) + 8LL);
        goto LABEL_49;
      }
      v19 = *v10;
      if ( v9 == *v10 )
      {
        v9 = *(_QWORD *)(v9 + 8);
        *v10 = *(_QWORD *)(v19 + 16);
        v20 = *(_QWORD *)(v19 + 16);
        if ( !*(_BYTE *)(v20 + 25) )
          *(_QWORD *)(v20 + 8) = v10;
        *(_QWORD *)(v19 + 8) = v10[1];
        if ( v10 == *(__int64 **)(CommonFileMapping::m_mapSingleton + 8) )
        {
          *(_QWORD *)(CommonFileMapping::m_mapSingleton + 8) = v19;
        }
        else
        {
          v21 = (_QWORD *)v10[1];
          if ( v10 == (__int64 *)v21[2] )
            v21[2] = v19;
          else
            *v21 = v19;
        }
        *(_QWORD *)(v19 + 16) = v10;
        v10[1] = v19;
      }
      *(_BYTE *)(*(_QWORD *)(v9 + 8) + 24LL) = 1;
      *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v9 + 8) + 8LL) + 24LL) = 0;
      v15 = *(_QWORD **)(*(_QWORD *)(v9 + 8) + 8LL);
      v16 = (_QWORD *)v15[2];
      v15[2] = *v16;
      if ( !*(_BYTE *)(*v16 + 25LL) )
        *(_QWORD *)(*v16 + 8LL) = v15;
      v16[1] = v15[1];
      if ( v15 == *(_QWORD **)(CommonFileMapping::m_mapSingleton + 8) )
      {
        *(_QWORD *)(CommonFileMapping::m_mapSingleton + 8) = v16;
      }
      else
      {
        v22 = (_QWORD *)v15[1];
        if ( v15 == (_QWORD *)*v22 )
          *v22 = v16;
        else
          v22[2] = v16;
      }
      *v16 = v15;
    }
    v15[1] = v16;
LABEL_49:
    v8 = *(_QWORD *)(v9 + 8);
  }
  v23 = CommonFileMapping::m_mapSingleton;
  *a2 = a6;
  v24 = *(_QWORD *)(v23 + 8);
  result = a2;
  *(_BYTE *)(v24 + 24) = 1;
  return result;
}

```

## disassembly

```asm
0x1800203f8  push    rbx
0x1800203fa  sub     rsp, 20h
0x1800203fe  mov     rax, cs:qword_180030CE8
0x180020405  mov     rcx, 2E8BA2E8BA2E8B9h
0x18002040f  mov     r10b, r8b
0x180020412  mov     r11, rdx
0x180020415  cmp     rax, rcx
0x180020418  jnb     loc_180020675
0x18002041e  mov     r8, [rsp+28h+arg_28]
0x180020423  inc     rax
0x180020426  mov     cs:qword_180030CE8, rax
0x18002042d  xor     ebx, ebx
0x18002042f  mov     [r8+8], r9
0x180020433  mov     rax, cs:?m_mapSingleton@CommonFileMapping@@0V?$map@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@U?$less@UtagSFILENAMEwithATTRIBUTE@@@3@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@3@@std@@A; std::map<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>> CommonFileMapping::m_mapSingleton
0x18002043a  cmp     r9, rax
0x18002043d  jnz     short loc_180020456
0x18002043f  mov     [rax+8], r8
0x180020443  mov     rax, cs:?m_mapSingleton@CommonFileMapping@@0V?$map@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@U?$less@UtagSFILENAMEwithATTRIBUTE@@@3@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@3@@std@@A; std::map<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>> CommonFileMapping::m_mapSingleton
0x18002044a  mov     [rax], r8
0x18002044d  mov     rax, cs:?m_mapSingleton@CommonFileMapping@@0V?$map@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@U?$less@UtagSFILENAMEwithATTRIBUTE@@@3@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@3@@std@@A; std::map<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>> CommonFileMapping::m_mapSingleton
0x180020454  jmp     short loc_180020480
0x180020456  test    r10b, r10b
0x180020459  jz      short loc_18002046F
0x18002045b  mov     [r9], r8
0x18002045e  mov     rax, cs:?m_mapSingleton@CommonFileMapping@@0V?$map@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@U?$less@UtagSFILENAMEwithATTRIBUTE@@@3@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@3@@std@@A; std::map<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>> CommonFileMapping::m_mapSingleton
0x180020465  cmp     r9, [rax]
0x180020468  jnz     short loc_180020484
0x18002046a  mov     [rax], r8
0x18002046d  jmp     short loc_180020484
0x18002046f  mov     [r9+10h], r8
0x180020473  mov     rax, cs:?m_mapSingleton@CommonFileMapping@@0V?$map@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@U?$less@UtagSFILENAMEwithATTRIBUTE@@@3@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@3@@std@@A; std::map<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>> CommonFileMapping::m_mapSingleton
0x18002047a  cmp     r9, [rax+10h]
0x18002047e  jnz     short loc_180020484
0x180020480  mov     [rax+10h], r8
0x180020484  mov     rax, [r8+8]
0x180020488  mov     rdx, r8
0x18002048b  jmp     loc_180020651
0x180020490  mov     rcx, [rdx+8]
0x180020494  mov     r9, [rcx+8]
0x180020498  mov     rax, [r9]
0x18002049b  cmp     rcx, rax
0x18002049e  jnz     loc_18002056D
0x1800204a4  mov     rax, [r9+10h]
0x1800204a8  cmp     [rax+18h], bl
0x1800204ab  jz      loc_180020572
0x1800204b1  mov     r9, [rcx+10h]
0x1800204b5  cmp     rdx, r9
0x1800204b8  jnz     short loc_180020504
0x1800204ba  mov     rax, [r9]
0x1800204bd  mov     rdx, rcx
0x1800204c0  mov     [rcx+10h], rax
0x1800204c4  mov     rax, [r9]
0x1800204c7  cmp     [rax+19h], bl
0x1800204ca  jnz     short loc_1800204D0
0x1800204cc  mov     [rax+8], rcx
0x1800204d0  mov     rax, [rcx+8]
0x1800204d4  mov     [r9+8], rax
0x1800204d8  mov     rax, cs:?m_mapSingleton@CommonFileMapping@@0V?$map@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@U?$less@UtagSFILENAMEwithATTRIBUTE@@@3@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@3@@std@@A; std::map<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>> CommonFileMapping::m_mapSingleton
0x1800204df  cmp     rcx, [rax+8]
0x1800204e3  jnz     short loc_1800204EB
0x1800204e5  mov     [rax+8], r9
0x1800204e9  jmp     short loc_1800204FD
0x1800204eb  mov     rax, [rcx+8]
0x1800204ef  cmp     rcx, [rax]
0x1800204f2  jnz     short loc_1800204F9
0x1800204f4  mov     [rax], r9
0x1800204f7  jmp     short loc_1800204FD
0x1800204f9  mov     [rax+10h], r9
0x1800204fd  mov     [r9], rcx
0x180020500  mov     [rcx+8], r9
0x180020504  mov     rax, [rdx+8]
0x180020508  mov     byte ptr [rax+18h], 1
0x18002050c  mov     rax, [rdx+8]
0x180020510  mov     rcx, [rax+8]
0x180020514  mov     [rcx+18h], bl
0x180020517  mov     rax, [rdx+8]
0x18002051b  mov     rcx, [rax+8]
0x18002051f  mov     r9, [rcx]
0x180020522  mov     rax, [r9+10h]
0x180020526  mov     [rcx], rax
0x180020529  mov     rax, [r9+10h]
0x18002052d  cmp     [rax+19h], bl
0x180020530  jnz     short loc_180020536
0x180020532  mov     [rax+8], rcx
0x180020536  mov     rax, [rcx+8]
0x18002053a  mov     [r9+8], rax
0x18002053e  mov     rax, cs:?m_mapSingleton@CommonFileMapping@@0V?$map@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@U?$less@UtagSFILENAMEwithATTRIBUTE@@@3@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@3@@std@@A; std::map<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>> CommonFileMapping::m_mapSingleton
0x180020545  cmp     rcx, [rax+8]
0x180020549  jnz     short loc_180020551
0x18002054b  mov     [rax+8], r9
0x18002054f  jmp     short loc_180020564
0x180020551  mov     rax, [rcx+8]
0x180020555  cmp     rcx, [rax+10h]
0x180020559  jnz     short loc_180020561
0x18002055b  mov     [rax+10h], r9
0x18002055f  jmp     short loc_180020564
0x180020561  mov     [rax], r9
0x180020564  mov     [r9+10h], rcx
0x180020568  jmp     loc_180020649
0x18002056d  cmp     [rax+18h], bl
0x180020570  jnz     short loc_180020592
0x180020572  mov     byte ptr [rcx+18h], 1
0x180020576  mov     byte ptr [rax+18h], 1
0x18002057a  mov     rax, [rdx+8]
0x18002057e  mov     rcx, [rax+8]
0x180020582  mov     [rcx+18h], bl
0x180020585  mov     rax, [rdx+8]
0x180020589  mov     rdx, [rax+8]
0x18002058d  jmp     loc_18002064D
0x180020592  mov     r9, [rcx]
0x180020595  cmp     rdx, r9
0x180020598  jnz     short loc_1800205E7
0x18002059a  mov     rax, [r9+10h]
0x18002059e  mov     rdx, rcx
0x1800205a1  mov     [rcx], rax
0x1800205a4  mov     rax, [r9+10h]
0x1800205a8  cmp     [rax+19h], bl
0x1800205ab  jnz     short loc_1800205B1
0x1800205ad  mov     [rax+8], rcx
0x1800205b1  mov     rax, [rcx+8]
0x1800205b5  mov     [r9+8], rax
0x1800205b9  mov     rax, cs:?m_mapSingleton@CommonFileMapping@@0V?$map@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@U?$less@UtagSFILENAMEwithATTRIBUTE@@@3@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@3@@std@@A; std::map<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>> CommonFileMapping::m_mapSingleton
0x1800205c0  cmp     rcx, [rax+8]
0x1800205c4  jnz     short loc_1800205CC
0x1800205c6  mov     [rax+8], r9
0x1800205ca  jmp     short loc_1800205DF
0x1800205cc  mov     rax, [rcx+8]
0x1800205d0  cmp     rcx, [rax+10h]
0x1800205d4  jnz     short loc_1800205DC
0x1800205d6  mov     [rax+10h], r9
0x1800205da  jmp     short loc_1800205DF
0x1800205dc  mov     [rax], r9
0x1800205df  mov     [r9+10h], rcx
0x1800205e3  mov     [rcx+8], r9
0x1800205e7  mov     rax, [rdx+8]
0x1800205eb  mov     byte ptr [rax+18h], 1
0x1800205ef  mov     rax, [rdx+8]
0x1800205f3  mov     rcx, [rax+8]
0x1800205f7  mov     [rcx+18h], bl
0x1800205fa  mov     rax, [rdx+8]
0x1800205fe  mov     rcx, [rax+8]
0x180020602  mov     r9, [rcx+10h]
0x180020606  mov     rax, [r9]
0x180020609  mov     [rcx+10h], rax
0x18002060d  mov     rax, [r9]
0x180020610  cmp     [rax+19h], bl
0x180020613  jnz     short loc_180020619
0x180020615  mov     [rax+8], rcx
0x180020619  mov     rax, [rcx+8]
0x18002061d  mov     [r9+8], rax
0x180020621  mov     rax, cs:?m_mapSingleton@CommonFileMapping@@0V?$map@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@U?$less@UtagSFILENAMEwithATTRIBUTE@@@3@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@3@@std@@A; std::map<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>> CommonFileMapping::m_mapSingleton
0x180020628  cmp     rcx, [rax+8]
0x18002062c  jnz     short loc_180020634
0x18002062e  mov     [rax+8], r9
0x180020632  jmp     short loc_180020646
0x180020634  mov     rax, [rcx+8]
0x180020638  cmp     rcx, [rax]
0x18002063b  jnz     short loc_180020642
0x18002063d  mov     [rax], r9
0x180020640  jmp     short loc_180020646
0x180020642  mov     [rax+10h], r9
0x180020646  mov     [r9], rcx
0x180020649  mov     [rcx+8], r9
0x18002064d  mov     rax, [rdx+8]
0x180020651  cmp     [rax+18h], bl
0x180020654  jz      loc_180020490
0x18002065a  mov     rax, cs:?m_mapSingleton@CommonFileMapping@@0V?$map@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@U?$less@UtagSFILENAMEwithATTRIBUTE@@@3@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@3@@std@@A; std::map<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>> CommonFileMapping::m_mapSingleton
0x180020661  mov     [r11], r8
0x180020664  mov     rcx, [rax+8]
0x180020668  mov     rax, r11
0x18002066b  mov     byte ptr [rcx+18h], 1
0x18002066f  add     rsp, 20h
0x180020673  pop     rbx
0x180020674  retn
0x180020675  mov     rdx, [rsp+28h+arg_28]
0x18002067a  call    ?_Destroy_if_not_nil@?$_Tree@V?$_Tmap_traits@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@U?$less@UtagSFILENAMEwithATTRIBUTE@@@3@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@3@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>,std::less<tagSFILENAMEwithATTRIBUTE>,std::allocator<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>>,0>>::_Destroy_if_not_nil(std::_Tree_node<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>,void *> *)
0x18002067f  lea     rcx, aMapSetTTooLong; "map/set<T> too long"
0x180020686  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
