# CSyncChangeWrapper::RemoveChangeUnitWrapperMapping(CSyncChangeUnitWrapper *)

- ea: `0x18006c458`
- end: `0x18006c59b`
- name: `?RemoveChangeUnitWrapperMapping@CSyncChangeWrapper@@QEAAJPEAVCSyncChangeUnitWrapper@@@Z`
- size: `323`
- prototype: `int(CSyncChangeWrapper *__hidden this, struct CSyncChangeUnitWrapper *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180021918`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18001fc38`
- `0x18003b298`
- `0x18003fda8`
- `0x18006c458`
- `0x180071f70`

## string_xrefs

- `0x18006c48e`: `CSyncChangeWrapper::RemoveChangeUnitWrapperMapping`
- `0x18006c56f`: `CSyncChangeWrapper::RemoveChangeUnitWrapperMapping`

## pseudocode

```c
__int64 __fastcall CSyncChangeWrapper::RemoveChangeUnitWrapperMapping(
        CSyncChangeWrapper *this,
        struct CSyncChangeUnitWrapper *a2)
{
  PVOID *v4; // rcx
  int v5; // ebx
  IdParameterPair **v6; // rdi
  __int64 v7; // rsi
  unsigned int v8; // eax
  int ExistingBucket; // eax
  unsigned int v11; // [rsp+58h] [rbp+10h] BYREF
  unsigned __int8 *v12; // [rsp+60h] [rbp+18h] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      155,
      WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids,
      "CSyncChangeWrapper::RemoveChangeUnitWrapperMapping");
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v5 = -2147467261;
  if ( a2 )
  {
    v12 = 0;
    v5 = CSyncChangeUnitWrapper::GetChangeUnitIdInternal(a2, &v12);
    if ( v5 < 0 || !v12 )
      goto LABEL_14;
    v6 = (IdParameterPair **)((char *)this + 208);
    v11 = 0;
    v7 = *((_QWORD *)this + 27);
    if ( v7 )
    {
      v8 = IdParameterPair::HashKey(v6[3], v12);
      ExistingBucket = HashTable<unsigned char *,CSyncChangeUnitWrapper *,IdParameterPair *>::FindExistingBucket(
                         (_DWORD)v6,
                         v8,
                         (unsigned int)&v12,
                         v7,
                         *(_DWORD *)v6,
                         (__int64)&v11);
      v5 = ExistingBucket;
      if ( !ExistingBucket )
      {
        *(_BYTE *)(v7 + 24LL * v11 + 16) &= ~1u;
        --*((_DWORD *)v6 + 4);
LABEL_13:
        IdParameters::FreeId(v12);
LABEL_14:
        v4 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_15;
      }
      if ( ExistingBucket != 1 )
        goto LABEL_13;
    }
    v5 = -2147024809;
    goto LABEL_13;
  }
LABEL_15:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v4[2],
      156,
      (unsigned int)WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids,
      (unsigned int)"CSyncChangeWrapper::RemoveChangeUnitWrapperMapping",
      v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18006c458  mov     [rsp+arg_0], rbx
0x18006c45d  push    rsi
0x18006c45e  push    rdi
0x18006c45f  push    r14
0x18006c461  sub     rsp, 30h
0x18006c465  mov     rdi, rdx
0x18006c468  mov     rsi, rcx
0x18006c46b  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c472  lea     r14, WPP_GLOBAL_Control
0x18006c479  cmp     rcx, r14
0x18006c47c  jz      short loc_18006C4AD
0x18006c47e  test    byte ptr [rcx+1Ch], 8
0x18006c482  jz      short loc_18006C4AD
0x18006c484  cmp     byte ptr [rcx+19h], 5
0x18006c488  jb      short loc_18006C4AD
0x18006c48a  mov     rcx, [rcx+10h]
0x18006c48e  lea     r9, aCsyncchangewra_57; "CSyncChangeWrapper::RemoveChangeUnitWra"...
0x18006c495  mov     edx, 9Bh
0x18006c49a  lea     r8, WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids
0x18006c4a1  call    WPP_SF_s
0x18006c4a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c4ad  mov     ebx, 80004003h
0x18006c4b2  test    rdi, rdi
0x18006c4b5  jz      loc_18006C55A
0x18006c4bb  lea     rdx, [rsp+48h+arg_10]; unsigned __int8 **
0x18006c4c0  mov     [rsp+48h+arg_10], 0
0x18006c4c9  mov     rcx, rdi; this
0x18006c4cc  call    ?GetChangeUnitIdInternal@CSyncChangeUnitWrapper@@QEAAJPEAPEAE@Z; CSyncChangeUnitWrapper::GetChangeUnitIdInternal(uchar * *)
0x18006c4d1  mov     ebx, eax
0x18006c4d3  test    eax, eax
0x18006c4d5  js      short loc_18006C553
0x18006c4d7  cmp     [rsp+48h+arg_10], 0
0x18006c4dd  jz      short loc_18006C553
0x18006c4df  lea     rdi, [rsi+0D0h]
0x18006c4e6  mov     [rsp+48h+arg_8], 0
0x18006c4ee  mov     rsi, [rdi+8]
0x18006c4f2  test    rsi, rsi
0x18006c4f5  jz      short loc_18006C544
0x18006c4f7  mov     rdx, [rsp+48h+arg_10]; unsigned __int8 *
0x18006c4fc  mov     rcx, [rdi+18h]; this
0x18006c500  call    ?HashKey@IdParameterPair@@QEBAKPEBE@Z; IdParameterPair::HashKey(uchar const *)
0x18006c505  lea     rcx, [rsp+48h+arg_8]
0x18006c50a  mov     r9, rsi
0x18006c50d  mov     [rsp+48h+var_20], rcx
0x18006c512  lea     r8, [rsp+48h+arg_10]
0x18006c517  mov     ecx, [rdi]
0x18006c519  mov     edx, eax
0x18006c51b  mov     [rsp+48h+var_28], ecx
0x18006c51f  mov     rcx, rdi
0x18006c522  call    ?FindExistingBucket@?$HashTable@PEAEPEAVCSyncChangeUnitWrapper@@PEAUIdParameterPair@@@@AEBAJKAEBQEAEPEAV?$TableBucket@PEAEPEAVCSyncChangeUnitWrapper@@PEAUIdParameterPair@@@@KPEAK@Z; HashTable<uchar *,CSyncChangeUnitWrapper *,IdParameterPair *>::FindExistingBucket(ulong,uchar * const &,TableBucket<uchar *,CSyncChangeUnitWrapper *,IdParameterPair *> *,ulong,ulong *)
0x18006c527  mov     ebx, eax
0x18006c529  test    eax, eax
0x18006c52b  jnz     short loc_18006C53F
0x18006c52d  mov     eax, [rsp+48h+arg_8]
0x18006c531  lea     rcx, [rax+rax*2]
0x18006c535  and     byte ptr [rsi+rcx*8+10h], 0FEh
0x18006c53a  dec     dword ptr [rdi+10h]
0x18006c53d  jmp     short loc_18006C549
0x18006c53f  cmp     eax, 1
0x18006c542  jnz     short loc_18006C549
0x18006c544  mov     ebx, 80070057h
0x18006c549  mov     rcx, [rsp+48h+arg_10]; unsigned __int8 *
0x18006c54e  call    ?FreeId@IdParameters@@SAXPEAE@Z; IdParameters::FreeId(uchar *)
0x18006c553  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c55a  cmp     rcx, r14
0x18006c55d  jz      short loc_18006C58B
0x18006c55f  test    byte ptr [rcx+1Ch], 8
0x18006c563  jz      short loc_18006C58B
0x18006c565  cmp     byte ptr [rcx+19h], 5
0x18006c569  jb      short loc_18006C58B
0x18006c56b  mov     rcx, [rcx+10h]
0x18006c56f  lea     r9, aCsyncchangewra_57; "CSyncChangeWrapper::RemoveChangeUnitWra"...
0x18006c576  mov     edx, 9Ch
0x18006c57b  mov     [rsp+48h+var_28], ebx
0x18006c57f  lea     r8, WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids
0x18006c586  call    WPP_SF_sD
0x18006c58b  mov     eax, ebx
0x18006c58d  mov     rbx, [rsp+48h+arg_0]
0x18006c592  add     rsp, 30h
0x18006c596  pop     r14
0x18006c598  pop     rdi
0x18006c599  pop     rsi
0x18006c59a  retn
```
