# CSyncChangeBatchWrapper::AddForgottenDelete(uchar *)

- ea: `0x180063e18`
- end: `0x18006403f`
- name: `?AddForgottenDelete@CSyncChangeBatchWrapper@@QEAAJPEAE@Z`
- size: `551`
- prototype: `__int64 __fastcall(CSyncChangeBatchWrapper *this, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18003a64c`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18001fc38`
- `0x18002dc04`
- `0x18002dc5c`
- `0x180031fa4`
- `0x180063e18`
- `0x180066f84`
- `0x180094010`

## string_xrefs

- `0x180063e54`: `CSyncChangeBatchWrapper::AddForgottenDelete`
- `0x180064002`: `CSyncChangeBatchWrapper::AddForgottenDelete`

## pseudocode

```c
__int64 __fastcall CSyncChangeBatchWrapper::AddForgottenDelete(CSyncChangeBatchWrapper *this, unsigned __int8 *a2)
{
  PVOID *v4; // rcx
  int v5; // ebx
  __int64 v6; // rax
  unsigned __int8 *v7; // rsi
  IdParameterPair *v8; // rcx
  int v9; // eax
  __int64 v10; // r9
  struct IdParameters *v11; // rcx
  unsigned int v12; // eax
  struct ISyncKnowledge *v13; // r9
  struct CSyncChangeWrapper *v14; // r14
  struct ISyncKnowledge **v16; // [rsp+28h] [rbp-48h]
  struct ISyncKnowledge **v17; // [rsp+30h] [rbp-40h]
  struct ISyncKnowledge *v18; // [rsp+38h] [rbp-38h]
  struct ISyncKnowledge *v19; // [rsp+40h] [rbp-30h]
  struct ISyncKnowledge *v20; // [rsp+48h] [rbp-28h]
  struct IForgottenKnowledge *v21; // [rsp+50h] [rbp-20h]
  struct ISyncFilterInfo *v22; // [rsp+58h] [rbp-18h]
  struct CSyncChangeWrapper *v23; // [rsp+A8h] [rbp+38h] BYREF
  unsigned __int8 *v24; // [rsp+B0h] [rbp+40h] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      27,
      WPP_238472b3224e399257624831508c69ba_Traceguids,
      "CSyncChangeBatchWrapper::AddForgottenDelete");
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v5 = -2147467261;
  if ( a2 )
  {
    v6 = *((_QWORD *)this + 8);
    v7 = 0;
    v24 = 0;
    v5 = -2147217379;
    if ( v6 && *(_QWORD *)(v6 + 8) )
    {
      v8 = (IdParameterPair *)*((_QWORD *)this + 2);
      LODWORD(v23) = 0;
      v5 = IdParameterPair::AllocateId(v8, &v24, (unsigned int *)&v23);
      if ( v5 == 1 )
      {
        v7 = v24;
        v9 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 *, struct CSyncChangeWrapper **))(**(_QWORD **)(*((_QWORD *)this + 8) + 8LL)
                                                                                                + 24LL))(
               *(_QWORD *)(*((_QWORD *)this + 8) + 8LL),
               v24,
               &v23);
        v5 = v9;
        if ( v9 != -2147024662 )
        {
          if ( v9 >= 0 )
            v5 = -2147217379;
          goto LABEL_18;
        }
        v5 = IdParameterPair::AllocateId(*((IdParameterPair **)this + 2), &v24, (unsigned __int16)v23);
      }
      v7 = v24;
      if ( v5 >= 0 )
      {
        v5 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 *, struct CSyncChangeWrapper **))(**(_QWORD **)(*((_QWORD *)this + 8) + 8LL)
                                                                                                + 24LL))(
               *(_QWORD *)(*((_QWORD *)this + 8) + 8LL),
               v24,
               &v23);
        if ( v5 >= 0 )
        {
          v10 = *((_QWORD *)this + 8);
          v11 = (struct IdParameters *)*((_QWORD *)this + 2);
          v22 = (struct ISyncFilterInfo *)*((_QWORD *)this + 12);
          v21 = (struct IForgottenKnowledge *)*((_QWORD *)this + 11);
          v20 = (struct ISyncKnowledge *)*((_QWORD *)this + 10);
          v19 = (struct ISyncKnowledge *)*((_QWORD *)this + 9);
          v18 = *(struct ISyncKnowledge **)(v10 + 48);
          v17 = *(struct ISyncKnowledge ***)(v10 + 40);
          v16 = *(struct ISyncKnowledge ***)(v10 + 32);
          v12 = *(_DWORD *)(v10 + 24);
          v13 = *(struct ISyncKnowledge **)(v10 + 8);
          v23 = 0;
          v5 = CSyncChangeWrapper_CreateInstance(v11, a2, v7, v13, v12, v16, v17, v18, v19, v20, v21, v22, &v23);
          if ( v5 >= 0 )
          {
            v14 = v23;
            v5 = CollectionManager<CSyncChange>::Add(*((_QWORD *)this + 4), v23);
            if ( v5 >= 0 && !*((_QWORD *)this + 3) )
            {
              v5 = 0;
              *((_QWORD *)this + 3) = *(_QWORD *)(*((_QWORD *)this + 4) + 16LL);
            }
            (*(void (__fastcall **)(struct CSyncChangeWrapper *))(*(_QWORD *)v14 + 16LL))(v14);
          }
        }
      }
    }
LABEL_18:
    IdParameters::FreeId(v7);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v4[2],
      28,
      (unsigned int)WPP_238472b3224e399257624831508c69ba_Traceguids,
      (unsigned int)"CSyncChangeBatchWrapper::AddForgottenDelete",
      v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180063e18  mov     [rsp-28h+arg_0], rbx
0x180063e1d  push    rbp
0x180063e1e  push    rsi
0x180063e1f  push    rdi
0x180063e20  push    r13
0x180063e22  push    r14
0x180063e24  mov     rbp, rsp
0x180063e27  sub     rsp, 70h
0x180063e2b  mov     r14, rdx
0x180063e2e  mov     rdi, rcx
0x180063e31  mov     rcx, cs:WPP_GLOBAL_Control
0x180063e38  lea     r13, WPP_GLOBAL_Control
0x180063e3f  cmp     rcx, r13
0x180063e42  jz      short loc_180063E73
0x180063e44  test    byte ptr [rcx+1Ch], 8
0x180063e48  jz      short loc_180063E73
0x180063e4a  cmp     byte ptr [rcx+19h], 5
0x180063e4e  jb      short loc_180063E73
0x180063e50  mov     rcx, [rcx+10h]
0x180063e54  lea     r9, aCsyncchangebat_63; "CSyncChangeBatchWrapper::AddForgottenDe"...
0x180063e5b  mov     edx, 1Bh
0x180063e60  lea     r8, WPP_238472b3224e399257624831508c69ba_Traceguids
0x180063e67  call    WPP_SF_s
0x180063e6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180063e73  mov     ebx, 80004003h
0x180063e78  test    r14, r14
0x180063e7b  jz      loc_180063FED
0x180063e81  mov     rax, [rdi+40h]
0x180063e85  xor     esi, esi
0x180063e87  mov     [rbp+arg_10], rsi
0x180063e8b  mov     ebx, 8004101Dh
0x180063e90  test    rax, rax
0x180063e93  jz      loc_180063FDE
0x180063e99  cmp     [rax+8], rsi
0x180063e9d  jz      loc_180063FDE
0x180063ea3  mov     rcx, [rdi+10h]; this
0x180063ea7  lea     r8, [rbp+arg_8]; unsigned int *
0x180063eab  lea     rdx, [rbp+arg_10]; unsigned __int8 **
0x180063eaf  mov     dword ptr [rbp+arg_8], esi
0x180063eb2  call    ?AllocateId@IdParameterPair@@QEAAJPEAPEAEPEAK@Z; IdParameterPair::AllocateId(uchar * *,ulong *)
0x180063eb7  mov     ebx, eax
0x180063eb9  cmp     eax, 1
0x180063ebc  jnz     short loc_180063EFE
0x180063ebe  mov     rax, [rdi+40h]
0x180063ec2  lea     r8, [rbp+arg_8]
0x180063ec6  mov     rsi, [rbp+arg_10]
0x180063eca  mov     rdx, rsi
0x180063ecd  mov     rcx, [rax+8]
0x180063ed1  mov     rax, [rcx]
0x180063ed4  mov     rax, [rax+18h]
0x180063ed8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063edd  mov     ebx, eax
0x180063edf  cmp     eax, 800700EAh
0x180063ee4  jnz     loc_180064034
0x180063eea  movzx   r8d, word ptr [rbp+arg_8]; unsigned __int16
0x180063eef  lea     rdx, [rbp+arg_10]; unsigned __int8 **
0x180063ef3  mov     rcx, [rdi+10h]; this
0x180063ef7  call    ?AllocateId@IdParameterPair@@QEAAJPEAPEAEG@Z; IdParameterPair::AllocateId(uchar * *,ushort)
0x180063efc  mov     ebx, eax
0x180063efe  mov     rsi, [rbp+arg_10]
0x180063f02  test    ebx, ebx
0x180063f04  js      loc_180063FDE
0x180063f0a  mov     rax, [rdi+40h]
0x180063f0e  lea     r8, [rbp+arg_8]
0x180063f12  mov     rdx, rsi
0x180063f15  mov     rcx, [rax+8]
0x180063f19  mov     rax, [rcx]
0x180063f1c  mov     rax, [rax+18h]
0x180063f20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063f25  mov     ebx, eax
0x180063f27  test    eax, eax
0x180063f29  js      loc_180063FDE
0x180063f2f  mov     r9, [rdi+40h]
0x180063f33  lea     rax, [rbp+arg_8]
0x180063f37  mov     rcx, [rdi+10h]; struct IdParameters *
0x180063f3b  mov     r8, rsi; unsigned __int8 *
0x180063f3e  mov     [rsp+70h+var_10], rax; struct CSyncChangeWrapper **
0x180063f43  mov     rdx, r14; unsigned __int8 *
0x180063f46  mov     rax, [rdi+60h]
0x180063f4a  mov     [rsp+70h+var_18], rax; struct ISyncFilterInfo *
0x180063f4f  mov     rax, [rdi+58h]
0x180063f53  mov     [rsp+70h+var_20], rax; struct IForgottenKnowledge *
0x180063f58  mov     rax, [rdi+50h]
0x180063f5c  mov     [rsp+70h+var_28], rax; struct ISyncKnowledge *
0x180063f61  mov     rax, [rdi+48h]
0x180063f65  mov     [rsp+70h+var_30], rax; struct ISyncKnowledge *
0x180063f6a  mov     rax, [r9+30h]
0x180063f6e  mov     [rsp+70h+var_38], rax; struct ISyncKnowledge *
0x180063f73  mov     rax, [r9+28h]
0x180063f77  mov     [rsp+70h+var_40], rax; struct ISyncKnowledge **
0x180063f7c  mov     rax, [r9+20h]
0x180063f80  mov     [rsp+70h+var_48], rax; struct ISyncKnowledge **
0x180063f85  mov     eax, [r9+18h]
0x180063f89  mov     r9, [r9+8]; struct ISyncKnowledge *
0x180063f8d  mov     [rbp+arg_8], 0
0x180063f95  mov     [rsp+70h+var_50], eax; unsigned int
0x180063f99  call    ?CSyncChangeWrapper_CreateInstance@@YAJPEAVIdParameters@@PEAE1PEAUISyncKnowledge@@KPEAPEAU2@3222PEAUIForgottenKnowledge@@PEAUISyncFilterInfo@@PEAPEAVCSyncChangeWrapper@@@Z; CSyncChangeWrapper_CreateInstance(IdParameters *,uchar *,uchar *,ISyncKnowledge *,ulong,ISyncKnowledge * *,ISyncKnowledge * *,ISyncKnowledge *,ISyncKnowledge *,ISyncKnowledge *,IForgottenKnowledge *,ISyncFilterInfo *,CSyncChangeWrapper * *)
0x180063f9e  mov     ebx, eax
0x180063fa0  test    eax, eax
0x180063fa2  js      short loc_180063FDE
0x180063fa4  mov     r14, [rbp+arg_8]
0x180063fa8  mov     rcx, [rdi+20h]
0x180063fac  mov     rdx, r14
0x180063faf  call    ?Add@?$CollectionManager@VCSyncChange@@@@QEAAJPEAVCSyncChange@@@Z; CollectionManager<CSyncChange>::Add(CSyncChange *)
0x180063fb4  mov     ebx, eax
0x180063fb6  test    eax, eax
0x180063fb8  js      short loc_180063FCF
0x180063fba  cmp     qword ptr [rdi+18h], 0
0x180063fbf  jnz     short loc_180063FCF
0x180063fc1  mov     rax, [rdi+20h]
0x180063fc5  xor     ebx, ebx
0x180063fc7  mov     rdx, [rax+10h]
0x180063fcb  mov     [rdi+18h], rdx
0x180063fcf  mov     rax, [r14]
0x180063fd2  mov     rcx, r14
0x180063fd5  mov     rax, [rax+10h]
0x180063fd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063fde  mov     rcx, rsi; unsigned __int8 *
0x180063fe1  call    ?FreeId@IdParameters@@SAXPEAE@Z; IdParameters::FreeId(uchar *)
0x180063fe6  mov     rcx, cs:WPP_GLOBAL_Control
0x180063fed  cmp     rcx, r13
0x180063ff0  jz      short loc_18006401E
0x180063ff2  test    byte ptr [rcx+1Ch], 8
0x180063ff6  jz      short loc_18006401E
0x180063ff8  cmp     byte ptr [rcx+19h], 5
0x180063ffc  jb      short loc_18006401E
0x180063ffe  mov     rcx, [rcx+10h]
0x180064002  lea     r9, aCsyncchangebat_63; "CSyncChangeBatchWrapper::AddForgottenDe"...
0x180064009  mov     edx, 1Ch
0x18006400e  mov     [rsp+70h+var_50], ebx
0x180064012  lea     r8, WPP_238472b3224e399257624831508c69ba_Traceguids
0x180064019  call    WPP_SF_sD
0x18006401e  mov     eax, ebx
0x180064020  mov     rbx, [rsp+70h+arg_0]
0x180064028  add     rsp, 70h
0x18006402c  pop     r14
0x18006402e  pop     r13
0x180064030  pop     rdi
0x180064031  pop     rsi
0x180064032  pop     rbp
0x180064033  retn
0x180064034  test    eax, eax
0x180064036  js      short loc_180063FDE
0x180064038  mov     ebx, 8004101Dh
0x18006403d  jmp     short loc_180063FDE
```
