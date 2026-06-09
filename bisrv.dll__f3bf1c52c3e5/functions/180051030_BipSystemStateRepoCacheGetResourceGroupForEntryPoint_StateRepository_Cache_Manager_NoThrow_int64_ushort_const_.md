# BipSystemStateRepoCacheGetResourceGroupForEntryPoint(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,ushort const *,uchar *,ushort *)

- ea: `0x180051030`
- end: `0x180051499`
- name: `?BipSystemStateRepoCacheGetResourceGroupForEntryPoint@@YAJAEAVManager_NoThrow@Cache@StateRepository@@_JPEBG2PEAEPEAG@Z`
- size: `1129`
- prototype: `__int64 __usercall@<rax>(struct StateRepository::Cache::Manager_NoThrow *@<rcx>, __int64@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, unsigned __int8 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800514a0`

## callees

- `0x180019430`
- `0x180019804`
- `0x18001a1f0`
- `0x18001bfcc`
- `0x180051030`
- `0x1800946a0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800512bc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800512bc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800513e9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800513e9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800512f7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18005130a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18005131d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180051330`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180051343`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180051358`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18005136d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180051380`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180051393`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800513a6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800513b9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800513cc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800512f7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18005130a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18005131d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180051330`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180051343`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180051358`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18005136d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180051380`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180051393`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800513a6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800513b9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800513cc`

## string_xrefs

- `0x1800510f7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`

## pseudocode

```c
__int64 __fastcall BipSystemStateRepoCacheGetResourceGroupForEntryPoint(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int8 *a5,
        unsigned __int16 *a6)
{
  int v9; // eax
  __int64 v10; // rdx
  int v11; // ebx
  int v12; // edx
  unsigned __int8 v13; // si
  unsigned __int16 *v14; // rbx
  int v15; // eax
  __int64 v16; // rdx
  const unsigned __int16 *v17; // rax
  int v18; // ecx
  unsigned __int16 *v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  unsigned __int64 v33; // rax
  __int64 v34; // rcx
  __int64 v35; // rax
  unsigned __int16 *v36; // rcx
  int UserDataCount; // [rsp+28h] [rbp-E0h]
  bool v38[4]; // [rsp+38h] [rbp-D0h] BYREF
  int v39; // [rsp+3Ch] [rbp-CCh] BYREF
  _DWORD v40[2]; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v41; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v42; // [rsp+50h] [rbp-B8h]
  __int64 v43; // [rsp+58h] [rbp-B0h]
  __int128 v44; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v45; // [rsp+78h] [rbp-90h]
  __int64 v46; // [rsp+80h] [rbp-88h]
  __int128 v47; // [rsp+88h] [rbp-80h]
  __int128 v48; // [rsp+98h] [rbp-70h]
  unsigned __int16 *v49; // [rsp+A8h] [rbp-60h]
  __int128 v50; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v51; // [rsp+C8h] [rbp-40h]
  __int64 v52; // [rsp+D0h] [rbp-38h]
  __int128 v53; // [rsp+D8h] [rbp-30h]
  __int128 v54; // [rsp+E8h] [rbp-20h]
  __int64 v55; // [rsp+F8h] [rbp-10h]
  int v56; // [rsp+100h] [rbp-8h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+108h] [rbp+0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+118h] [rbp+10h] BYREF
  char *v59; // [rsp+128h] [rbp+20h]
  int v60; // [rsp+130h] [rbp+28h]
  int v61; // [rsp+134h] [rbp+2Ch]
  _DWORD *v62; // [rsp+138h] [rbp+30h]
  __int64 v63; // [rsp+140h] [rbp+38h]
  int *v64; // [rsp+148h] [rbp+40h]
  __int64 v65; // [rsp+150h] [rbp+48h]
  wil::details::in1diag3 *retaddr; // [rsp+1A0h] [rbp+98h]

  v41 = 0;
  LODWORD(v42) = 0;
  v43 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v44 = 0;
  LODWORD(v45) = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v38[0] = 0;
  v9 = StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::OpenByApplicationAndCategory(
         (StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow *)&v41,
         a1,
         a2,
         a3);
  LOWORD(v11) = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B9,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)(unsigned int)v9,
      UserDataCount);
    v12 = 1000;
    v11 = (unsigned __int16)v11;
    goto LABEL_14;
  }
  v13 = 0;
  v14 = 0;
  v15 = StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::Get(&v41, v10, &v50, v38);
  if ( v15 < 0 )
  {
LABEL_13:
    v12 = 3000;
    v11 = (unsigned __int16)v15;
LABEL_14:
    if ( v11 )
      v11 |= 0xC0070000;
    if ( v11 < 0 )
    {
LABEL_17:
      if ( (unsigned int)dword_1800C3098 > 2 && (qword_1800C30A8 & 3) != 0 && (qword_1800C30B0 & 3) == qword_1800C30B0 )
      {
        v39 = v12;
        v64 = &v39;
        v40[0] = v11;
        v62 = v40;
        *(_DWORD *)&EventDescriptor.Level = 2;
        UserData.Ptr = (ULONGLONG)off_1800C30A0;
        v65 = 4;
        v63 = 4;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 3;
        UserData.Size = *(unsigned __int16 *)off_1800C30A0;
        v59 = &byte_1800ADE2F;
        UserData.Reserved = 2;
        v60 = 58;
        v61 = 1;
        v40[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
      }
    }
    goto LABEL_21;
  }
  while ( 1 )
  {
    if ( !v38[0] )
    {
      *a5 = 0;
      v11 = 0;
      goto LABEL_21;
    }
    if ( (int)StateRepository::Cache::Entity::ApplicationExtension_NoThrow::GetActivation(
                (StateRepository::Cache::Entity::ApplicationExtension_NoThrow *)&v50,
                a1,
                (struct StateRepository::Cache::Entity::Activation_NoThrow *)&v44,
                v38) >= 0
      && v38[0]
      && *((_QWORD *)&v47 + 1) )
    {
      v17 = a4;
      do
      {
        v18 = *(const unsigned __int16 *)((char *)v17 + *((_QWORD *)&v47 + 1) - (_QWORD)a4);
        v16 = (unsigned int)*v17 - v18;
        if ( (_DWORD)v16 )
          break;
        ++v17;
      }
      while ( v18 );
      if ( !(_DWORD)v16 )
        break;
    }
    LODWORD(v42) = v42 + 1;
    v15 = StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::Get(&v41, v16, &v50, v38);
    if ( v15 < 0 )
      goto LABEL_13;
  }
  if ( v49 )
  {
    v33 = -1;
    do
      ++v33;
    while ( v49[v33] );
    if ( v33 > 0xFF )
    {
      v12 = 2000;
      v11 = -1073741789;
      goto LABEL_17;
    }
    v14 = v49;
    v13 = 1;
  }
  *a5 = v13;
  if ( v13 )
  {
    v34 = 2147483646;
    v35 = 256;
    do
    {
      if ( !v34 )
        break;
      if ( !*v14 )
        break;
      *a6++ = *v14++;
      --v34;
      --v35;
    }
    while ( v35 );
    v36 = a6 - 1;
    if ( v35 )
      v36 = a6;
    *v36 = 0;
  }
  v11 = 0;
LABEL_21:
  v19 = v49;
  v49 = 0;
  if ( v19 )
    SRCache_Free(v19);
  v20 = *((_QWORD *)&v48 + 1);
  *((_QWORD *)&v48 + 1) = 0;
  if ( v20 )
    SRCache_Free(v20);
  v21 = v48;
  *(_QWORD *)&v48 = 0;
  if ( v21 )
    SRCache_Free(v21);
  v22 = *((_QWORD *)&v47 + 1);
  *((_QWORD *)&v47 + 1) = 0;
  if ( v22 )
    SRCache_Free(v22);
  v23 = v47;
  *(_QWORD *)&v47 = 0;
  if ( v23 )
    SRCache_Free(v23);
  v24 = v46;
  v46 = 0;
  if ( v24 )
    SRCache_Free(v24);
  v25 = *((_QWORD *)&v44 + 1);
  *((_QWORD *)&v44 + 1) = 0;
  if ( v25 )
    SRCache_Free(v25);
  v26 = v55;
  v55 = 0;
  if ( v26 )
    SRCache_Free(v26);
  v27 = *((_QWORD *)&v54 + 1);
  *((_QWORD *)&v54 + 1) = 0;
  if ( v27 )
    SRCache_Free(v27);
  v28 = v54;
  *(_QWORD *)&v54 = 0;
  if ( v28 )
    SRCache_Free(v28);
  v29 = *((_QWORD *)&v53 + 1);
  *((_QWORD *)&v53 + 1) = 0;
  if ( v29 )
    SRCache_Free(v29);
  v30 = v52;
  v52 = 0;
  if ( v30 )
    SRCache_Free(v30);
  v31 = v41;
  v41 = 0;
  if ( v31 )
    SRCacheContext_Close(v31);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180051030  mov     r11, rsp
0x180051033  push    rbp
0x180051034  push    rbx
0x180051035  lea     rbp, [r11-98h]
0x18005103c  sub     rsp, 188h
0x180051043  mov     rax, cs:__security_cookie
0x18005104a  xor     rax, rsp
0x18005104d  mov     [rbp+90h+var_40], rax
0x180051051  mov     [r11+20h], rsi
0x180051055  xorps   xmm0, xmm0
0x180051058  mov     [r11-18h], rdi
0x18005105c  xorps   xmm1, xmm1
0x18005105f  mov     rdi, [rbp+90h+arg_28]
0x180051066  mov     [r11-20h], r12
0x18005106a  mov     r12, [rbp+90h+arg_20]
0x180051071  mov     [r11-28h], r13
0x180051075  xor     r13d, r13d
0x180051078  mov     [r11-30h], r14
0x18005107c  mov     r14, rcx
0x18005107f  mov     [r11-38h], r15
0x180051083  mov     r15, r9
0x180051086  mov     r9, r8; unsigned __int16 *
0x180051089  mov     [rsp+190h+var_150], r13
0x18005108e  mov     r8, rdx; __int64
0x180051091  mov     dword ptr [rsp+190h+var_148], r13d
0x180051096  mov     rdx, rcx; struct StateRepository::Cache::Manager_NoThrow *
0x180051099  mov     [rsp+190h+var_140], r13
0x18005109e  lea     rcx, [rsp+190h+var_150]; this
0x1800510a3  movdqa  [rbp+90h+var_E0], xmm0
0x1800510a8  mov     [rbp+90h+var_D0], r13
0x1800510ac  mov     [rbp+90h+var_C8], r13
0x1800510b0  movdqa  [rbp+90h+var_C0], xmm0
0x1800510b5  movdqa  [rbp+90h+var_B0], xmm1
0x1800510ba  mov     [rbp+90h+var_A0], r13
0x1800510be  mov     [rbp+90h+var_98], r13d
0x1800510c2  movdqa  [rsp+190h+var_138+8], xmm0
0x1800510c8  mov     dword ptr [rsp+190h+var_120], r13d
0x1800510cd  mov     [rsp+190h+var_118], r13
0x1800510d2  movdqa  [rbp+90h+var_110], xmm0
0x1800510d7  movdqa  [rbp+90h+var_100], xmm1
0x1800510dc  mov     [rbp+90h+var_F0], r13
0x1800510e0  mov     [rsp+190h+var_160], r13b
0x1800510e5  call    ?OpenByApplicationAndCategory@ApplicationExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_JPEBG@Z; StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::OpenByApplicationAndCategory(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *)
0x1800510ea  mov     ebx, eax
0x1800510ec  test    eax, eax
0x1800510ee  jns     short loc_180051118
0x1800510f0  mov     rcx, [rbp+98h]; this
0x1800510f7  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800510fe  mov     r9d, eax; char *
0x180051101  mov     edx, 3B9h; void *
0x180051106  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005110b  mov     edx, 3E8h
0x180051110  movzx   ebx, bx
0x180051113  jmp     loc_1800511C6
0x180051118  lea     r9, [rsp+190h+var_160]
0x18005111d  xor     sil, sil
0x180051120  lea     r8, [rbp+90h+var_E0]
0x180051124  mov     rbx, r13
0x180051127  lea     rcx, [rsp+190h+var_150]
0x18005112c  call    ?Get@ApplicationExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@ApplicationExtension_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,bool &)
0x180051131  test    eax, eax
0x180051133  js      loc_1800511BE
0x180051139  nop     dword ptr [rax+00000000h]
0x180051140  movzx   r9d, [rsp+190h+var_160]
0x180051146  test    r9b, r9b
0x180051149  jz      loc_180051442
0x18005114f  lea     r9, [rsp+190h+var_160]; bool *
0x180051154  mov     rdx, r14; struct StateRepository::Cache::Manager_NoThrow *
0x180051157  lea     r8, [rsp+190h+var_138+8]; struct StateRepository::Cache::Entity::Activation_NoThrow *
0x18005115c  lea     rcx, [rbp+90h+var_E0]; this
0x180051160  call    ?GetActivation@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEBAJAEAVManager_NoThrow@34@AEAVActivation_NoThrow@234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::GetActivation(StateRepository::Cache::Manager_NoThrow &,StateRepository::Cache::Entity::Activation_NoThrow &,bool &)
0x180051165  test    eax, eax
0x180051167  js      short loc_18005119F
0x180051169  movzx   r9d, [rsp+190h+var_160]
0x18005116f  test    r9b, r9b
0x180051172  jz      short loc_18005119F
0x180051174  mov     r8, qword ptr [rbp+90h+var_110+8]
0x180051178  test    r8, r8
0x18005117b  jz      short loc_18005119F
0x18005117d  mov     rax, r15
0x180051180  sub     r8, r15
0x180051183  movzx   edx, word ptr [rax]
0x180051186  movzx   ecx, word ptr [rax+r8]
0x18005118b  sub     edx, ecx
0x18005118d  jnz     short loc_180051197
0x18005118f  add     rax, 2
0x180051193  test    ecx, ecx
0x180051195  jnz     short loc_180051183
0x180051197  test    edx, edx
0x180051199  jz      loc_180051407
0x18005119f  inc     dword ptr [rsp+190h+var_148]
0x1800511a3  lea     r9, [rsp+190h+var_160]
0x1800511a8  lea     r8, [rbp+90h+var_E0]
0x1800511ac  lea     rcx, [rsp+190h+var_150]
0x1800511b1  call    ?Get@ApplicationExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@ApplicationExtension_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,bool &)
0x1800511b6  test    eax, eax
0x1800511b8  jns     loc_180051140
0x1800511be  mov     edx, 0BB8h
0x1800511c3  movzx   ebx, ax
0x1800511c6  mov     eax, ebx
0x1800511c8  or      eax, 0C0070000h
0x1800511cd  test    ebx, ebx
0x1800511cf  cmovnz  ebx, eax
0x1800511d2  test    ebx, ebx
0x1800511d4  jns     loc_1800512C2
0x1800511da  mov     eax, cs:dword_1800C3098
0x1800511e0  cmp     eax, 2
0x1800511e3  jbe     loc_1800512C2
0x1800511e9  mov     rcx, cs:qword_1800C30B0
0x1800511f0  mov     rax, cs:qword_1800C30A8
0x1800511f7  test    al, 3
0x1800511f9  jz      loc_1800512C2
0x1800511ff  mov     rax, rcx
0x180051202  and     eax, 3
0x180051205  cmp     rax, rcx
0x180051208  jnz     loc_1800512C2
0x18005120e  mov     [rsp+190h+var_15C], edx
0x180051212  lea     rax, [rsp+190h+var_15C]
0x180051217  mov     [rbp+90h+var_50], rax
0x18005121b  lea     rcx, _TraceLoggingMetadata
0x180051222  lea     rax, [rsp+190h+var_158]
0x180051227  mov     dword ptr [rsp+190h+var_158], ebx
0x18005122b  mov     [rbp+90h+var_60], rax
0x18005122f  lea     rdx, [rbp+90h+EventDescriptor]; EventDescriptor
0x180051233  movzx   eax, cs:word_1800ADE25
0x18005123a  xor     r9d, r9d; RelatedActivityId
0x18005123d  mov     dword ptr [rbp+90h+EventDescriptor.Level], eax
0x180051240  xor     r8d, r8d; ActivityId
0x180051243  mov     rax, cs:off_1800C30A0
0x18005124a  mov     [rbp+90h+var_80.Ptr], rax
0x18005124e  mov     [rbp+90h+var_48], 4
0x180051256  mov     [rbp+90h+var_58], 4
0x18005125e  mov     dword ptr [rbp+90h+EventDescriptor.Id], 0B000000h
0x180051265  mov     [rbp+90h+EventDescriptor.Keyword], 3
0x18005126d  movzx   eax, word ptr [rax]
0x180051270  mov     [rbp+90h+var_80.Size], eax
0x180051273  lea     rax, byte_1800ADE2F
0x18005127a  mov     [rbp+90h+var_70], rax
0x18005127e  lea     rax, _TraceLoggingMetadataEnd
0x180051285  sub     eax, ecx
0x180051287  mov     dword ptr [rbp+90h+var_80.0Ch], 2
0x18005128e  mov     [rbp+90h+var_68], 3Ah ; ':'
0x180051295  mov     [rbp+90h+var_64], 1
0x18005129c  mov     dword ptr [rsp+190h+var_158+4], eax
0x1800512a0  mov     eax, dword ptr [rsp+190h+var_158+4]
0x1800512a4  mov     rcx, cs:RegHandle; RegHandle
0x1800512ab  lea     rax, [rbp+90h+var_80]
0x1800512af  mov     [rsp+190h+UserData], rax; UserData
0x1800512b4  mov     [rsp+190h+UserDataCount], 4; UserDataCount
0x1800512bc  call    cs:__imp_EventWriteTransfer
0x1800512c2  mov     rcx, [rbp+90h+var_F0]
0x1800512c6  mov     r15, [rsp+190h+var_30]
0x1800512ce  mov     r14, [rsp+190h+var_28]
0x1800512d6  mov     r12, [rsp+190h+var_18]
0x1800512de  mov     rdi, [rsp+180h]
0x1800512e6  mov     rsi, [rsp+190h+arg_18]
0x1800512ee  mov     [rbp+90h+var_F0], r13
0x1800512f2  test    rcx, rcx
0x1800512f5  jz      short loc_1800512FD
0x1800512f7  call    cs:__imp_SRCache_Free
0x1800512fd  mov     rcx, qword ptr [rbp+90h+var_100+8]
0x180051301  mov     qword ptr [rbp+90h+var_100+8], r13
0x180051305  test    rcx, rcx
0x180051308  jz      short loc_180051310
0x18005130a  call    cs:__imp_SRCache_Free
0x180051310  mov     rcx, qword ptr [rbp+90h+var_100]
0x180051314  mov     qword ptr [rbp+90h+var_100], r13
0x180051318  test    rcx, rcx
0x18005131b  jz      short loc_180051323
0x18005131d  call    cs:__imp_SRCache_Free
0x180051323  mov     rcx, qword ptr [rbp+90h+var_110+8]
0x180051327  mov     qword ptr [rbp+90h+var_110+8], r13
0x18005132b  test    rcx, rcx
0x18005132e  jz      short loc_180051336
0x180051330  call    cs:__imp_SRCache_Free
0x180051336  mov     rcx, qword ptr [rbp+90h+var_110]
0x18005133a  mov     qword ptr [rbp+90h+var_110], r13
0x18005133e  test    rcx, rcx
0x180051341  jz      short loc_180051349
0x180051343  call    cs:__imp_SRCache_Free
0x180051349  mov     rcx, [rsp+190h+var_118]
0x18005134e  mov     [rsp+190h+var_118], r13
0x180051353  test    rcx, rcx
0x180051356  jz      short loc_18005135E
0x180051358  call    cs:__imp_SRCache_Free
0x18005135e  mov     rcx, qword ptr [rsp+190h+var_128]
0x180051363  mov     qword ptr [rsp+190h+var_128], r13
0x180051368  test    rcx, rcx
0x18005136b  jz      short loc_180051373
0x18005136d  call    cs:__imp_SRCache_Free
0x180051373  mov     rcx, [rbp+90h+var_A0]
0x180051377  mov     [rbp+90h+var_A0], r13
0x18005137b  test    rcx, rcx
0x18005137e  jz      short loc_180051386
0x180051380  call    cs:__imp_SRCache_Free
0x180051386  mov     rcx, qword ptr [rbp+90h+var_B0+8]
0x18005138a  mov     qword ptr [rbp+90h+var_B0+8], r13
0x18005138e  test    rcx, rcx
0x180051391  jz      short loc_180051399
0x180051393  call    cs:__imp_SRCache_Free
0x180051399  mov     rcx, qword ptr [rbp+90h+var_B0]
0x18005139d  mov     qword ptr [rbp+90h+var_B0], r13
0x1800513a1  test    rcx, rcx
0x1800513a4  jz      short loc_1800513AC
0x1800513a6  call    cs:__imp_SRCache_Free
0x1800513ac  mov     rcx, qword ptr [rbp+90h+var_C0+8]
0x1800513b0  mov     qword ptr [rbp+90h+var_C0+8], r13
0x1800513b4  test    rcx, rcx
0x1800513b7  jz      short loc_1800513BF
0x1800513b9  call    cs:__imp_SRCache_Free
0x1800513bf  mov     rcx, [rbp+90h+var_C8]
0x1800513c3  mov     [rbp+90h+var_C8], r13
0x1800513c7  test    rcx, rcx
0x1800513ca  jz      short loc_1800513D2
0x1800513cc  call    cs:__imp_SRCache_Free
0x1800513d2  mov     rcx, [rsp+190h+var_150]
0x1800513d7  mov     [rsp+190h+var_150], r13
0x1800513dc  mov     r13, [rsp+190h+var_20]
0x1800513e4  test    rcx, rcx
0x1800513e7  jz      short loc_1800513EF
0x1800513e9  call    cs:__imp_SRCacheContext_Close
0x1800513ef  mov     eax, ebx
0x1800513f1  mov     rcx, [rbp+90h+var_40]
0x1800513f5  xor     rcx, rsp; StackCookie
0x1800513f8  call    __security_check_cookie
0x1800513fd  add     rsp, 188h
0x180051404  pop     rbx
0x180051405  pop     rbp
0x180051406  retn
0x180051407  mov     rcx, [rbp+90h+var_F0]
0x18005140b  test    rcx, rcx
0x18005140e  jz      short loc_18005143D
0x180051410  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180051417  inc     rax
0x18005141a  cmp     [rcx+rax*2], bx
0x18005141e  jnz     short loc_180051417
0x180051420  cmp     rax, 0FFh
0x180051426  jbe     short loc_180051437
0x180051428  mov     edx, 7D0h
0x18005142d  mov     ebx, 0C0000023h
0x180051432  jmp     loc_1800511DA
0x180051437  mov     rbx, rcx
0x18005143a  mov     sil, 1
0x18005143d  test    r9b, r9b
0x180051440  jnz     short loc_18005144E
0x180051442  mov     [r12], r13b
0x180051446  mov     ebx, r13d
0x180051449  jmp     loc_1800512C2
0x18005144e  mov     [r12], sil
0x180051452  test    sil, sil
0x180051455  jz      short loc_180051491
0x180051457  mov     ecx, 7FFFFFFEh
0x18005145c  mov     eax, 100h
0x180051461  test    rcx, rcx
0x180051464  jz      short loc_180051482
0x180051466  movzx   edx, word ptr [rbx]
0x180051469  test    dx, dx
0x18005146c  jz      short loc_180051482
0x18005146e  mov     [rdi], dx
0x180051471  add     rbx, 2
0x180051475  add     rdi, 2
0x180051479  dec     rcx
0x18005147c  sub     rax, 1
0x180051480  jnz     short loc_180051461
0x180051482  test    rax, rax
0x180051485  lea     rcx, [rdi-2]
0x180051489  cmovnz  rcx, rdi
0x18005148d  mov     [rcx], r13w
0x180051491  mov     ebx, r13d
0x180051494  jmp     loc_1800512C2
```
