# CSyncChangeBatchWrapper::GetLearnedFilterForgottenKnowledgeAfterRecoveryComplete(ISyncKnowledge *,IEnumItemIds *,ulong,ISyncKnowledge * *)

- ea: `0x180064950`
- end: `0x180064c91`
- name: `?GetLearnedFilterForgottenKnowledgeAfterRecoveryComplete@CSyncChangeBatchWrapper@@QEAAJPEAUISyncKnowledge@@PEAUIEnumItemIds@@KPEAPEAU2@@Z`
- size: `833`
- prototype: `__int64 __fastcall(CSyncChangeBatchWrapper *__hidden this, struct ISyncKnowledge *, struct IEnumItemIds *, unsigned int, struct ISyncKnowledge **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180039948`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18002dc04`
- `0x18002dc5c`
- `0x18002ebe8`
- `0x180064950`
- `0x1800659c8`
- `0x180094010`

## string_xrefs

- `0x18006499d`: `CSyncChangeBatchWrapper::GetLearnedFilterForgottenKnowledgeAfterRecoveryComplete`
- `0x180064c48`: `CSyncChangeBatchWrapper::GetLearnedFilterForgottenKnowledgeAfterRecoveryComplete`

## pseudocode

```c
__int64 __fastcall CSyncChangeBatchWrapper::GetLearnedFilterForgottenKnowledgeAfterRecoveryComplete(
        CSyncChangeBatchWrapper *this,
        struct ISyncKnowledge *a2,
        struct IEnumItemIds *a3,
        unsigned int a4,
        struct ISyncKnowledge **a5)
{
  __int64 v5; // r15
  PVOID *v9; // rcx
  __int64 (__fastcall ***v10)(_QWORD, GUID *, unsigned __int8 **); // rsi
  unsigned int v11; // ebx
  __int64 v12; // rcx
  unsigned int v13; // eax
  unsigned __int8 *v14; // rcx
  __int64 v15; // rcx
  unsigned __int8 *v16; // rsi
  unsigned int v17; // eax
  IdParameterPair *v18; // rcx
  unsigned __int8 *v19; // r14
  int v20; // eax
  unsigned int v21; // eax
  IdParameterPair *v22; // rcx
  unsigned int v23; // eax
  int v24; // eax
  unsigned int Id; // eax
  __int64 v26; // rax
  __int64 v27; // rcx
  IdParameterPair *v28; // rcx
  unsigned __int8 *v30; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int8 *v31[3]; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int8 *v32; // [rsp+80h] [rbp+30h] BYREF
  unsigned int v33; // [rsp+98h] [rbp+48h] BYREF

  v33 = a4;
  v5 = a4;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      57,
      WPP_238472b3224e399257624831508c69ba_Traceguids,
      "CSyncChangeBatchWrapper::GetLearnedFilterForgottenKnowledgeAfterRecoveryComplete");
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  v10 = (__int64 (__fastcall ***)(_QWORD, GUID *, unsigned __int8 **))*((_QWORD *)this + 5);
  v11 = v10 == 0 ? 0x8004101D : 0;
  if ( (unsigned int)v5 < *((_DWORD *)this + 13) )
  {
    if ( !v10 )
      goto LABEL_30;
    v12 = *((_QWORD *)this + 13);
    LODWORD(v32) = v5;
    if ( (unsigned __int8)HashTable<unsigned long,unsigned long,SimpleHashTableContext>::LookupItem(v12, &v33, &v32) )
    {
      v31[0] = 0;
      v11 = (**v10)(v10, &GUID_de247002_566d_459a_a6ed_a5aab3459fb7, v31);
      if ( !v11 )
      {
        v13 = (*(__int64 (__fastcall **)(unsigned __int8 *, struct ISyncKnowledge *, struct IEnumItemIds *, _QWORD, struct ISyncKnowledge **))(*(_QWORD *)v31[0] + 80LL))(
                v31[0],
                a2,
                a3,
                (unsigned int)v32,
                a5);
        v14 = v31[0];
        v11 = v13;
LABEL_28:
        (*(void (__fastcall **)(unsigned __int8 *))(*(_QWORD *)v14 + 16LL))(v14);
      }
LABEL_29:
      v9 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_30;
    }
    if ( !*((_DWORD *)this + 12) )
    {
      v11 = 1;
      *a5 = 0;
      goto LABEL_29;
    }
    v32 = 0;
    v11 = (**v10)(v10, &GUID_ef64197d_4f44_4ea2_b355_4524713e3bed, &v32);
    if ( v11 )
    {
LABEL_27:
      v14 = v32;
      if ( v32 )
        goto LABEL_28;
      goto LABEL_29;
    }
    v15 = *((_QWORD *)this + 2);
    v16 = 0;
    v30 = 0;
    v31[0] = 0;
    v33 = 0;
    v17 = IdParameterPair::AllocateId((IdParameterPair *)(v15 + 16), &v30, &v33);
    v19 = v30;
    v11 = v17;
    if ( v17 == 1 )
    {
      v20 = (*(__int64 (__fastcall **)(unsigned __int8 *, unsigned __int8 *, unsigned int *))(*(_QWORD *)v32 + 144LL))(
              v32,
              v30,
              &v33);
      v11 = v20;
      if ( v20 == -2147024662 )
      {
        v21 = IdParameterPair::AllocateId((IdParameterPair *)(*((_QWORD *)this + 2) + 16LL), &v30, v33);
        v19 = v30;
        v11 = v21;
      }
      else if ( v20 >= 0 )
      {
        goto LABEL_36;
      }
    }
    if ( v11 )
      goto LABEL_26;
    v11 = (*(__int64 (__fastcall **)(unsigned __int8 *, unsigned __int8 *, unsigned int *))(*(_QWORD *)v32 + 144LL))(
            v32,
            v19,
            &v33);
    if ( v11 )
      goto LABEL_26;
    v22 = (IdParameterPair *)(*((_QWORD *)this + 2) + 16LL);
    v33 = 0;
    v23 = IdParameterPair::AllocateId(v22, v31, &v33);
    v16 = v31[0];
    v11 = v23;
    if ( v23 != 1 )
    {
LABEL_23:
      if ( !v11 )
      {
        v11 = (*(__int64 (__fastcall **)(unsigned __int8 *, unsigned __int8 *, unsigned int *))(*(_QWORD *)v32 + 152LL))(
                v32,
                v16,
                &v33);
        if ( !v11 )
        {
          v26 = *((_QWORD *)this + 8);
          v31[0] = v19;
          v31[1] = v16;
          v27 = *(_QWORD *)(*(_QWORD *)(v26 + 40) + 8 * v5);
          v11 = (*(__int64 (__fastcall **)(__int64, unsigned __int8 **, struct ISyncKnowledge **))(*(_QWORD *)v27 + 128LL))(
                  v27,
                  v31,
                  a5);
        }
      }
      goto LABEL_26;
    }
    v24 = (*(__int64 (__fastcall **)(unsigned __int8 *, unsigned __int8 *, unsigned int *))(*(_QWORD *)v32 + 152LL))(
            v32,
            v31[0],
            &v33);
    v11 = v24;
    if ( v24 == -2147024662 )
    {
      Id = IdParameterPair::AllocateId((IdParameterPair *)(*((_QWORD *)this + 2) + 16LL), v31, v33);
      v16 = v31[0];
      v11 = Id;
      goto LABEL_23;
    }
    if ( v24 < 0 )
      goto LABEL_23;
LABEL_36:
    v11 = -2147217379;
LABEL_26:
    IdParameterPair::FreeId(v18, v19);
    IdParameterPair::FreeId(v28, v16);
    goto LABEL_27;
  }
  v11 = -2147024809;
LABEL_30:
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 8) != 0 && *((_BYTE *)v9 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v9[2],
      58,
      (unsigned int)WPP_238472b3224e399257624831508c69ba_Traceguids,
      (unsigned int)"CSyncChangeBatchWrapper::GetLearnedFilterForgottenKnowledgeAfterRecoveryComplete",
      v11);
  return v11;
}

```

## disassembly

```asm
0x180064950  mov     [rsp-28h+arg_8], rbx
0x180064955  mov     [rsp-28h+arg_10], rsi
0x18006495a  mov     [rsp-28h+arg_18], r9d
0x18006495f  push    rbp
0x180064960  push    rdi
0x180064961  push    r12
0x180064963  push    r14
0x180064965  push    r15
0x180064967  mov     rbp, rsp
0x18006496a  sub     rsp, 50h
0x18006496e  mov     r15d, r9d
0x180064971  mov     r14, r8
0x180064974  mov     r12, rdx
0x180064977  mov     rdi, rcx
0x18006497a  mov     rcx, cs:WPP_GLOBAL_Control
0x180064981  lea     rax, WPP_GLOBAL_Control
0x180064988  cmp     rcx, rax
0x18006498b  jz      short loc_1800649BC
0x18006498d  test    byte ptr [rcx+1Ch], 8
0x180064991  jz      short loc_1800649BC
0x180064993  cmp     byte ptr [rcx+19h], 5
0x180064997  jb      short loc_1800649BC
0x180064999  mov     rcx, [rcx+10h]
0x18006499d  lea     r9, aCsyncchangebat_23; "CSyncChangeBatchWrapper::GetLearnedFilt"...
0x1800649a4  mov     edx, 39h ; '9'
0x1800649a9  lea     r8, WPP_238472b3224e399257624831508c69ba_Traceguids
0x1800649b0  call    WPP_SF_s
0x1800649b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800649bc  mov     rsi, [rdi+28h]
0x1800649c0  mov     rax, rsi
0x1800649c3  neg     rax
0x1800649c6  sbb     ebx, ebx
0x1800649c8  not     ebx
0x1800649ca  and     ebx, 8004101Dh
0x1800649d0  cmp     r15d, [rdi+34h]
0x1800649d4  jb      short loc_1800649E0
0x1800649d6  mov     ebx, 80070057h
0x1800649db  jmp     loc_180064C2C
0x1800649e0  test    rsi, rsi
0x1800649e3  jz      loc_180064C2C
0x1800649e9  mov     rcx, [rdi+68h]
0x1800649ed  lea     r8, [rbp+arg_0]
0x1800649f1  lea     rdx, [rbp+arg_18]
0x1800649f5  mov     dword ptr [rbp+arg_0], r15d
0x1800649f9  call    ?LookupItem@?$HashTable@KKVSimpleHashTableContext@@@@QEBA_NAEBKAEAK@Z; HashTable<ulong,ulong,SimpleHashTableContext>::LookupItem(ulong const &,ulong &)
0x1800649fe  test    al, al
0x180064a00  jz      short loc_180064A5B
0x180064a02  mov     [rbp+var_18], 0
0x180064a0a  lea     r8, [rbp+var_18]
0x180064a0e  mov     rax, [rsi]
0x180064a11  lea     rdx, _GUID_de247002_566d_459a_a6ed_a5aab3459fb7
0x180064a18  mov     rcx, rsi
0x180064a1b  mov     rax, [rax]
0x180064a1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064a23  mov     ebx, eax
0x180064a25  test    eax, eax
0x180064a27  jnz     loc_180064C25
0x180064a2d  mov     rcx, [rbp+var_18]
0x180064a31  mov     r8, r14
0x180064a34  mov     rdx, [rbp+arg_20]
0x180064a38  mov     r9d, dword ptr [rbp+arg_0]
0x180064a3c  mov     [rsp+50h+var_30], rdx
0x180064a41  mov     rdx, r12
0x180064a44  mov     rax, [rcx]
0x180064a47  mov     rax, [rax+50h]
0x180064a4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064a50  mov     rcx, [rbp+var_18]
0x180064a54  mov     ebx, eax
0x180064a56  jmp     loc_180064C19
0x180064a5b  cmp     dword ptr [rdi+30h], 0
0x180064a5f  jnz     short loc_180064A76
0x180064a61  mov     rax, [rbp+arg_20]
0x180064a65  mov     ebx, 1
0x180064a6a  mov     qword ptr [rax], 0
0x180064a71  jmp     loc_180064C25
0x180064a76  mov     [rbp+arg_0], 0
0x180064a7e  lea     r8, [rbp+arg_0]
0x180064a82  mov     rax, [rsi]
0x180064a85  lea     rdx, _GUID_ef64197d_4f44_4ea2_b355_4524713e3bed
0x180064a8c  mov     rcx, rsi
0x180064a8f  mov     rax, [rax]
0x180064a92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064a97  mov     ebx, eax
0x180064a99  test    eax, eax
0x180064a9b  jnz     loc_180064C10
0x180064aa1  mov     rcx, [rdi+10h]
0x180064aa5  lea     r8, [rbp+arg_18]; unsigned int *
0x180064aa9  xor     esi, esi
0x180064aab  mov     [rbp+var_20], 0
0x180064ab3  add     rcx, 10h; this
0x180064ab7  mov     [rbp+var_18], rsi
0x180064abb  lea     rdx, [rbp+var_20]; unsigned __int8 **
0x180064abf  mov     [rbp+arg_18], esi
0x180064ac2  call    ?AllocateId@IdParameterPair@@QEAAJPEAPEAEPEAK@Z; IdParameterPair::AllocateId(uchar * *,ulong *)
0x180064ac7  mov     r14, [rbp+var_20]
0x180064acb  mov     ebx, eax
0x180064acd  mov     r12d, 800700EAh
0x180064ad3  cmp     eax, 1
0x180064ad6  jnz     short loc_180064B1F
0x180064ad8  mov     rcx, [rbp+arg_0]
0x180064adc  lea     r8, [rbp+arg_18]
0x180064ae0  mov     rdx, r14
0x180064ae3  mov     rax, [rcx]
0x180064ae6  mov     rax, [rax+90h]
0x180064aed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064af2  mov     ebx, eax
0x180064af4  cmp     eax, r12d
0x180064af7  jnz     short loc_180064B17
0x180064af9  mov     rcx, [rdi+10h]
0x180064afd  lea     rdx, [rbp+var_20]; unsigned __int8 **
0x180064b01  movzx   r8d, word ptr [rbp+arg_18]; unsigned __int16
0x180064b06  add     rcx, 10h; this
0x180064b0a  call    ?AllocateId@IdParameterPair@@QEAAJPEAPEAEG@Z; IdParameterPair::AllocateId(uchar * *,ushort)
0x180064b0f  mov     r14, [rbp+var_20]
0x180064b13  mov     ebx, eax
0x180064b15  jmp     short loc_180064B1F
0x180064b17  test    eax, eax
0x180064b19  jns     loc_180064C87
0x180064b1f  test    ebx, ebx
0x180064b21  jnz     loc_180064C00
0x180064b27  mov     rcx, [rbp+arg_0]
0x180064b2b  lea     r8, [rbp+arg_18]
0x180064b2f  mov     rdx, r14
0x180064b32  mov     rax, [rcx]
0x180064b35  mov     rax, [rax+90h]
0x180064b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064b41  mov     ebx, eax
0x180064b43  test    eax, eax
0x180064b45  jnz     loc_180064C00
0x180064b4b  mov     rcx, [rdi+10h]
0x180064b4f  lea     r8, [rbp+arg_18]; unsigned int *
0x180064b53  add     rcx, 10h; this
0x180064b57  mov     [rbp+arg_18], esi
0x180064b5a  lea     rdx, [rbp+var_18]; unsigned __int8 **
0x180064b5e  call    ?AllocateId@IdParameterPair@@QEAAJPEAPEAEPEAK@Z; IdParameterPair::AllocateId(uchar * *,ulong *)
0x180064b63  mov     rsi, [rbp+var_18]
0x180064b67  mov     ebx, eax
0x180064b69  cmp     eax, 1
0x180064b6c  jnz     short loc_180064BAF
0x180064b6e  mov     rcx, [rbp+arg_0]
0x180064b72  lea     r8, [rbp+arg_18]
0x180064b76  mov     rdx, rsi
0x180064b79  mov     rax, [rcx]
0x180064b7c  mov     rax, [rax+98h]
0x180064b83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064b88  mov     ebx, eax
0x180064b8a  cmp     eax, r12d
0x180064b8d  jnz     loc_180064C7F
0x180064b93  mov     rcx, [rdi+10h]
0x180064b97  lea     rdx, [rbp+var_18]; unsigned __int8 **
0x180064b9b  movzx   r8d, word ptr [rbp+arg_18]; unsigned __int16
0x180064ba0  add     rcx, 10h; this
0x180064ba4  call    ?AllocateId@IdParameterPair@@QEAAJPEAPEAEG@Z; IdParameterPair::AllocateId(uchar * *,ushort)
0x180064ba9  mov     rsi, [rbp+var_18]
0x180064bad  mov     ebx, eax
0x180064baf  test    ebx, ebx
0x180064bb1  jnz     short loc_180064C00
0x180064bb3  mov     rcx, [rbp+arg_0]
0x180064bb7  lea     r8, [rbp+arg_18]
0x180064bbb  mov     rdx, rsi
0x180064bbe  mov     rax, [rcx]
0x180064bc1  mov     rax, [rax+98h]
0x180064bc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064bcd  mov     ebx, eax
0x180064bcf  test    eax, eax
0x180064bd1  jnz     short loc_180064C00
0x180064bd3  mov     rax, [rdi+40h]
0x180064bd7  lea     rdx, [rbp+var_18]
0x180064bdb  mov     r8, [rbp+arg_20]
0x180064bdf  mov     [rbp+var_18], r14
0x180064be3  mov     [rbp+var_10], rsi
0x180064be7  mov     rax, [rax+28h]
0x180064beb  mov     rcx, [rax+r15*8]
0x180064bef  mov     rax, [rcx]
0x180064bf2  mov     rax, [rax+80h]
0x180064bf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064bfe  mov     ebx, eax
0x180064c00  mov     rdx, r14; unsigned __int8 *
0x180064c03  call    ?FreeId@IdParameterPair@@QEBAXPEAE@Z; IdParameterPair::FreeId(uchar *)
0x180064c08  mov     rdx, rsi; unsigned __int8 *
0x180064c0b  call    ?FreeId@IdParameterPair@@QEBAXPEAE@Z; IdParameterPair::FreeId(uchar *)
0x180064c10  mov     rcx, [rbp+arg_0]
0x180064c14  test    rcx, rcx
0x180064c17  jz      short loc_180064C25
0x180064c19  mov     rax, [rcx]
0x180064c1c  mov     rax, [rax+10h]
0x180064c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064c25  mov     rcx, cs:WPP_GLOBAL_Control
0x180064c2c  lea     rax, WPP_GLOBAL_Control
0x180064c33  cmp     rcx, rax
0x180064c36  jz      short loc_180064C64
0x180064c38  test    byte ptr [rcx+1Ch], 8
0x180064c3c  jz      short loc_180064C64
0x180064c3e  cmp     byte ptr [rcx+19h], 5
0x180064c42  jb      short loc_180064C64
0x180064c44  mov     rcx, [rcx+10h]
0x180064c48  lea     r9, aCsyncchangebat_23; "CSyncChangeBatchWrapper::GetLearnedFilt"...
0x180064c4f  mov     edx, 3Ah ; ':'
0x180064c54  mov     dword ptr [rsp+50h+var_30], ebx
0x180064c58  lea     r8, WPP_238472b3224e399257624831508c69ba_Traceguids
0x180064c5f  call    WPP_SF_sD
0x180064c64  lea     r11, [rsp+50h+var_s0]
0x180064c69  mov     eax, ebx
0x180064c6b  mov     rbx, [r11+38h]
0x180064c6f  mov     rsi, [r11+40h]
0x180064c73  mov     rsp, r11
0x180064c76  pop     r15
0x180064c78  pop     r14
0x180064c7a  pop     r12
0x180064c7c  pop     rdi
0x180064c7d  pop     rbp
0x180064c7e  retn
0x180064c7f  test    eax, eax
0x180064c81  js      loc_180064BAF
0x180064c87  mov     ebx, 8004101Dh
0x180064c8c  jmp     loc_180064C00
```
